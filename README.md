# timelines
Data for timelines

Each file contains a json object that conforms to the following structure


````javascript
export interface Timeline {
    title: string; // This is the name of the timeline.
    legend: Legend[]; 
    entries: Entry[] 
}
export interface Legend {
    name: string; // Name of the legend entry (not currently used).
    id: number; // The id used to reference back to.
    colour: string; // The colour for the associated entries. Can be the colour name or css rgba value.
    contrast: string; // A contrast colour for text when the colour is provided as a background. Can be the colour name or css rgba value.
}

export interface Entry {
    name: string; // The Name of the entry - a publication or event of the timeline.
    type: EntryType; // The positional details for the entry.
    date?: string; // Optional date in YYYY-MM-DD format.
    description?: string; // Details of the entry.
    footnote?: string; // Optional foot note.
    cid?: number; // Associates this entry to a legend entry, which provides the colour information.
}
export enum EntryType {
    chapter = 0, // Chapter entries appear in the middle of the timeline
    entry = 1, // A normal entry, appears onthe left or right hand side of the timeline
    summary = 2 // This is primarily used for the introduction / starting entry of the timeline. It is centred when collapsed and spans the whole width when not. 
}
