<img src="d3.PNG" align="right" />
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

#3 Basics and styling
##3.1 Selecting and data-binding
	d3.select('h1') //selectAll('.className')
			.text('Selected').insert().classed('name',true.remove)
			.style('color', 'red');

##3.2 Binding data to elements
	var li = d3.selectAll('.item').data(number).text(function(d){
											return 'i am num '+ d;
										});
	li.enter().append('li').text(fun);
	li.exit().remove();

##3.3 Complex data and styling
	var styles = [
			{'background':'#58FA58','color':'#FF0000','width': '10%'},
			{'background':'#58FAF4','color':'#2A0A1B','width': '50%'},
			{'background':'#F5A9BC','color':'#0B3B39','width': '70%'},
			{'background':'#C8FE2E','color':'#3B0B17','width': '30%'},
			{'background':'#FA5858','color':'#0B0B61','width': '60%'}
		];		
		d3.selectAll('.listItem')
			.data(styles)
			.style({
				'font-size':'24px',
				'color': function(d){return d.color},
				'background': function(d){return d.background;},
				'width': function(d){return d.width},
				'padding':'5px',
				'margin': '4px',
				'list-style':'none'
			});

#4 SVG-scalable vector graphics
	->XML based vector image format for 2d graphics
	->SVG supports interactivity and animation
	->images and behavior are stored in XML file

##4.1 Basic Shapes
	-><svg></svg>
	-><text>text</text>
	-><rect x y height='' width='' fill='' stroke-width='' stroke='color'>
	-><circle cx='' cy='' r='' fill>
	-><ellipse cx='' cy rx ry>
	-<line x1 y1 x2 y2 style>

##4.2 Simple Bar Chart
	var chartData = [200,85,350,100,400,450,150], height = 500, width = 450, barWidth = 40, barOffset = 5;
	var chart = d3.select('#charts').append('svg')
					.attr('height', height).attr('width', width).style('background', 'yellow')
					.selectAll('rect').data(chartData).enter().append('rect')
						.style('fill','steelblue')
						.attr('x', function(d, index){
							return index * (barWidth + barOffset);
						})
						.attr('y', function(d){
							return (height - d);
						})
						.attr('width', barWidth)
						.attr('height', function(d){
							return d;
						})
						
#5 Scaling
	Convert high quantity into low range data to display it on screen
	-Quantitative-- for continuous input domains, such as number
	-Ordinal--for discrete input domain,such as name or categories
	-Time Scales--for time domains						
	##scaling to y-axis
		var y = d3.scale.linear().domain([0, d3.max(chartData)]).range([0, height]);
		var x = d3.scale.ordinal().domain(d3.range(0, chartData.length)).rangeBands([0, width]);						
