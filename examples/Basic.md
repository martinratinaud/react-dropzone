This example shows Dropzone with default properties and displays list of the dropped files.
```
class DropzoneDemo extends React.Component {
  constructor() {
    this.state = {
      files: []
    }
    this.onDrop = this.onDrop.bind(this)
  }
  
  onDrop(files) {
    this.setState({
      files
    })
  }

  render() {
    return (
      <section>
        <Dropzone onDrop={this.onDrop}>
          <div>Try dropping some files here, or click to select files to upload.</div>
        </Dropzone>
        <aside>
          <h2>Dropped files</h2>
          <ul>
            {
              this.state.files.map(f => <li>{f.name} - {f.size} bytes</li>)
            }
          </ul>
        </aside>
      </section>
    );
  }
};

<DropzoneDemo />
```