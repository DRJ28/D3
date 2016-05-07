# D3
	learning javascript D3 data visualization library.
#1	
	frontend development
	D3 Library
	JQuery
	Data VisualiZation
	JSON
	Arrays & Objects
	SVG
	Transitions
	Data Scaling
	Data Binding
	Data Display & Charting

#2	Data Visualization
	The presentation of data in graphical/pictorial format.
	D3 allows us to display data using HTML,SVG,CSS

#3 Selecting and data-binding
	d3.select('h1') //selectAll('.className')
			.text('Selected').insert().classed('name',true.remove)
			.style('color', 'red');

#3.1 Binding data to elements
	var li = d3.selectAll('.item').data(number).text(function(d){
											return 'i am num '+ d;
										});
	li.enter().append('li').text(fun);
	li.exit().remove();