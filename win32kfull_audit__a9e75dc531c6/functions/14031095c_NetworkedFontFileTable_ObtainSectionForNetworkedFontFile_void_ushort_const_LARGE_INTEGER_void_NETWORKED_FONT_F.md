# NetworkedFontFileTable::ObtainSectionForNetworkedFontFile(void *,ushort const *,_LARGE_INTEGER *,void * *,NETWORKED_FONT_FILE_NODE * *)

- ea: `0x14031095c`
- end: `0x140310c5a`
- name: `?ObtainSectionForNetworkedFontFile@NetworkedFontFileTable@@YAJPEAXPEBGPEAT_LARGE_INTEGER@@PEAPEAXPEAPEAUNETWORKED_FONT_FILE_NODE@@@Z`
- size: `766`
- prototype: `__int64 __fastcall(NetworkedFontFileTable *this, const WCHAR *, union _LARGE_INTEGER *, union _LARGE_INTEGER *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1401082f0`

## callees

- `0x14011a3e4`
- `0x14011a60c`
- `0x14020207c`
- `0x140310688`
- `0x14031095c`
- `0x140310d14`
- `0x140310da0`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140310b0e`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140310b0e`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140310a05`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140310a05`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1403109e5`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1403109e5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140310af5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140310af5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403109b4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403109b4`
- `win32kbase!GreReleasePushLockExclusive` at `0x140310bdf`
- `win32kbase!GreReleasePushLockExclusive` at `0x140310bdf`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140310b56`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140310b56`
- `win32kbase!GreInitializePushLock` at `0x140310b47`
- `win32kbase!GreInitializePushLock` at `0x140310b47`
- `win32kbase!??0SectionObj@Gre@@QEAA@PEAXPEAT_LARGE_INTEGER@@_NPEAPEAX@Z` at `0x140310b7c`
- `win32kbase!??0SectionObj@Gre@@QEAA@PEAXPEAT_LARGE_INTEGER@@_NPEAPEAX@Z` at `0x140310ba5`
- `win32kbase!??0SectionObj@Gre@@QEAA@PEAXPEAT_LARGE_INTEGER@@_NPEAPEAX@Z` at `0x140310b7c`
- `win32kbase!??0SectionObj@Gre@@QEAA@PEAXPEAT_LARGE_INTEGER@@_NPEAPEAX@Z` at `0x140310ba5`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x140310a8f`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x140310bd0`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x140310c0e`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x140310a8f`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x140310bd0`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x140310c0e`
- `win32kbase!GreReleasePushLockShared` at `0x140310a42`
- `win32kbase!GreReleasePushLockShared` at `0x140310a42`
- `win32kbase!UserGetSiloGlobals` at `0x14031099e`
- `win32kbase!UserGetSiloGlobals` at `0x1403109f1`
- `win32kbase!UserGetSiloGlobals` at `0x14031099e`
- `win32kbase!UserGetSiloGlobals` at `0x1403109f1`
- `win32kbase!GreAcquirePushLockShared` at `0x140310a32`
- `win32kbase!GreAcquirePushLockShared` at `0x140310a32`
- `win32kbase!??0SectionObj@Gre@@QEAA@$$QEAVSectionHandle@01@W4AccessMode@01@D@Z` at `0x140310a69`
- `win32kbase!??0SectionObj@Gre@@QEAA@$$QEAVSectionHandle@01@W4AccessMode@01@D@Z` at `0x140310a69`

## pseudocode

```c

```
