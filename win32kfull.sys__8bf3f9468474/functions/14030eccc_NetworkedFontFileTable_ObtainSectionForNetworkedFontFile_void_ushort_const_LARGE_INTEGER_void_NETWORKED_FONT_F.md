# NetworkedFontFileTable::ObtainSectionForNetworkedFontFile(void *,ushort const *,_LARGE_INTEGER *,void * *,NETWORKED_FONT_FILE_NODE * *)

- ea: `0x14030eccc`
- end: `0x14030efca`
- name: `?ObtainSectionForNetworkedFontFile@NetworkedFontFileTable@@YAJPEAXPEBGPEAT_LARGE_INTEGER@@PEAPEAXPEAPEAUNETWORKED_FONT_FILE_NODE@@@Z`
- size: `766`
- prototype: `int(NetworkedFontFileTable *__hidden this, void *, const unsigned __int16 *, union _LARGE_INTEGER *, void **, struct NETWORKED_FONT_FILE_NODE **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14005381c`

## callees

- `0x1401a22fc`
- `0x1401a44ac`
- `0x14020145c`
- `0x14030e9f8`
- `0x14030eccc`
- `0x14030f084`
- `0x14030f110`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14030ee7e`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14030ee7e`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14030ed75`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14030ed75`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14030ed55`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14030ed55`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14030ee65`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14030ee65`
- `ntoskrnl!RtlInitUnicodeString` at `0x14030ed24`
- `ntoskrnl!RtlInitUnicodeString` at `0x14030ed24`
- `win32kbase!GreReleasePushLockExclusive` at `0x14030ef4f`
- `win32kbase!GreReleasePushLockExclusive` at `0x14030ef4f`
- `win32kbase!GreAcquirePushLockExclusive` at `0x14030eec6`
- `win32kbase!GreAcquirePushLockExclusive` at `0x14030eec6`
- `win32kbase!GreInitializePushLock` at `0x14030eeb7`
- `win32kbase!GreInitializePushLock` at `0x14030eeb7`
- `win32kbase!??0SectionObj@Gre@@QEAA@PEAXPEAT_LARGE_INTEGER@@_NPEAPEAX@Z` at `0x14030eeec`
- `win32kbase!??0SectionObj@Gre@@QEAA@PEAXPEAT_LARGE_INTEGER@@_NPEAPEAX@Z` at `0x14030ef15`
- `win32kbase!??0SectionObj@Gre@@QEAA@PEAXPEAT_LARGE_INTEGER@@_NPEAPEAX@Z` at `0x14030eeec`
- `win32kbase!??0SectionObj@Gre@@QEAA@PEAXPEAT_LARGE_INTEGER@@_NPEAPEAX@Z` at `0x14030ef15`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x14030edff`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x14030ef40`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x14030ef7e`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x14030edff`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x14030ef40`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x14030ef7e`
- `win32kbase!GreReleasePushLockShared` at `0x14030edb2`
- `win32kbase!GreReleasePushLockShared` at `0x14030edb2`
- `win32kbase!UserGetSiloGlobals` at `0x14030ed0e`
- `win32kbase!UserGetSiloGlobals` at `0x14030ed61`
- `win32kbase!UserGetSiloGlobals` at `0x14030ed0e`
- `win32kbase!UserGetSiloGlobals` at `0x14030ed61`
- `win32kbase!GreAcquirePushLockShared` at `0x14030eda2`
- `win32kbase!GreAcquirePushLockShared` at `0x14030eda2`
- `win32kbase!??0SectionObj@Gre@@QEAA@$$QEAVSectionHandle@01@W4AccessMode@01@D@Z` at `0x14030edd9`
- `win32kbase!??0SectionObj@Gre@@QEAA@$$QEAVSectionHandle@01@W4AccessMode@01@D@Z` at `0x14030edd9`

## pseudocode

```c

```
