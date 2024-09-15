<script lang="ts">
	import {
		AccordionItem,
		AccordionTrigger,
		AccordionContent,
		Accordion
	} from '$lib/components/ui/accordion/index.js';
	const a = 5;

	console.log(a);
</script>

<Accordion>
	<AccordionItem value="item-1">
		<AccordionTrigger>Hi There</AccordionTrigger>
		<AccordionContent>Wassup wasabi</AccordionContent>
	</AccordionItem>
</Accordion>

<Accordion class="w-full sm:max-w-[70%]">
	<AccordionItem value="item-1">
		<AccordionTrigger>Is it accessible?</AccordionTrigger>
		<AccordionContent>Yes It adheres to the WAI-ARIA design pattern</AccordionContent>
	</AccordionItem>
	<AccordionItem value="item-2">
		<AccordionTrigger>Is it styled?</AccordionTrigger>
		<AccordionContent>
			Yes It comes with default styles that matches the other components' aesthetic
		</AccordionContent>
	</AccordionItem>
	<AccordionItem value="item-3">
		<AccordionTrigger>Is it animated?</AccordionTrigger>
		<AccordionContent>
			Yes It's animated by default, but you can disable it if you prefer
		</AccordionContent>
	</AccordionItem>
</Accordion>
