# W3_STATIC_FILE_HANDLER::Terminate(void)

- ea: `0x180002c04`
- end: `0x180002cea`
- name: `?Terminate@W3_STATIC_FILE_HANDLER@@SAXXZ`
- size: `230`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180002bd0`
- `0x180003bbc`

## callees

- `0x180001398`
- `0x180002c04`
- `0x180004528`
- `0x18000455c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002cca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002cca`
- `iisutil!?Terminate@LANG_STRING@@QEAAJXZ` at `0x180002c9c`
- `iisutil!?Terminate@LANG_STRING@@QEAAJXZ` at `0x180002c9c`

## pseudocode

```c
void W3_STATIC_FILE_HANDLER::Terminate(void)
{
  if ( W3_STATIC_FILE_HANDLER::sm_StartupState != 1 )
  {
    if ( W3_STATIC_FILE_HANDLER::sm_StartupState == 2 )
      goto LABEL_14;
    if ( W3_STATIC_FILE_HANDLER::sm_StartupState != 3 )
    {
      if ( W3_STATIC_FILE_HANDLER::sm_StartupState != 4 )
      {
        if ( (unsigned int)(W3_STATIC_FILE_HANDLER::sm_StartupState - 5) > 1 )
          goto LABEL_18;
        if ( _InterlockedExchangeAdd(&META_SCRIPT_MAP_TABLE::sm_lInitializeCount, 0xFFFFFFFF) == 1
          && META_SCRIPT_MAP_TABLE::sm_pGlobalTable )
        {
          META_SCRIPT_MAP_TABLE::Dereference(META_SCRIPT_MAP_TABLE::sm_pGlobalTable);
          META_SCRIPT_MAP_TABLE::sm_pGlobalTable = 0;
        }
      }
      if ( _InterlockedExchangeAdd(&MIME_MAP_TABLE::sm_lInitializeCount, 0xFFFFFFFF) == 1
        && MIME_MAP_TABLE::sm_pGlobalTable )
      {
        MIME_MAP_TABLE::Dereference(MIME_MAP_TABLE::sm_pGlobalTable);
        MIME_MAP_TABLE::sm_pGlobalTable = 0;
      }
    }
    if ( W3_STATIC_FILE_HANDLER::sm_pLangString )
    {
      LANG_STRING::Terminate((LANG_STRING *)W3_STATIC_FILE_HANDLER::sm_pLangString);
LABEL_14:
      if ( W3_STATIC_FILE_HANDLER::sm_pLangString )
      {
        operator delete(W3_STATIC_FILE_HANDLER::sm_pLangString);
        W3_STATIC_FILE_HANDLER::sm_pLangString = 0;
      }
    }
  }
  if ( W3_STATIC_FILE_HANDLER::sm_hResourceDll )
  {
    FreeLibrary(W3_STATIC_FILE_HANDLER::sm_hResourceDll);
    W3_STATIC_FILE_HANDLER::sm_hResourceDll = 0;
  }
LABEL_18:
  W3_STATIC_FILE_HANDLER::sm_StartupState = 7;
}

```

## disassembly

```asm
0x180002c04  sub     rsp, 28h
0x180002c08  mov     ecx, cs:?sm_StartupState@W3_STATIC_FILE_HANDLER@@0W4StaticStartup@@A; StaticStartup W3_STATIC_FILE_HANDLER::sm_StartupState
0x180002c0e  sub     ecx, 1
0x180002c11  jz      loc_180002CBE
0x180002c17  sub     ecx, 1
0x180002c1a  jz      loc_180002CA2
0x180002c20  sub     ecx, 1
0x180002c23  jz      short loc_180002C90
0x180002c25  sub     ecx, 1
0x180002c28  jz      short loc_180002C64
0x180002c2a  sub     ecx, 1
0x180002c2d  jz      short loc_180002C38
0x180002c2f  cmp     ecx, 1
0x180002c32  jnz     loc_180002CDB
0x180002c38  or      eax, 0FFFFFFFFh
0x180002c3b  lock xadd cs:?sm_lInitializeCount@META_SCRIPT_MAP_TABLE@@0JA, eax; long META_SCRIPT_MAP_TABLE::sm_lInitializeCount
0x180002c43  cmp     eax, 1
0x180002c46  jnz     short loc_180002C64
0x180002c48  mov     rcx, cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA; this
0x180002c4f  test    rcx, rcx
0x180002c52  jz      short loc_180002C64
0x180002c54  call    ?Dereference@META_SCRIPT_MAP_TABLE@@QEAAXXZ; META_SCRIPT_MAP_TABLE::Dereference(void)
0x180002c59  mov     cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA, 0; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x180002c64  or      eax, 0FFFFFFFFh
0x180002c67  lock xadd cs:?sm_lInitializeCount@MIME_MAP_TABLE@@0JA, eax; long MIME_MAP_TABLE::sm_lInitializeCount
0x180002c6f  cmp     eax, 1
0x180002c72  jnz     short loc_180002C90
0x180002c74  mov     rcx, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; this
0x180002c7b  test    rcx, rcx
0x180002c7e  jz      short loc_180002C90
0x180002c80  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x180002c85  mov     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, 0; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180002c90  mov     rcx, cs:?sm_pLangString@W3_STATIC_FILE_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * W3_STATIC_FILE_HANDLER::sm_pLangString
0x180002c97  test    rcx, rcx
0x180002c9a  jz      short loc_180002CBE
0x180002c9c  call    cs:__imp_?Terminate@LANG_STRING@@QEAAJXZ; LANG_STRING::Terminate(void)
0x180002ca2  mov     rcx, cs:?sm_pLangString@W3_STATIC_FILE_HANDLER@@2PEAVLANG_STRING@@EA; Block
0x180002ca9  test    rcx, rcx
0x180002cac  jz      short loc_180002CBE
0x180002cae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002cb3  mov     cs:?sm_pLangString@W3_STATIC_FILE_HANDLER@@2PEAVLANG_STRING@@EA, 0; LANG_STRING * W3_STATIC_FILE_HANDLER::sm_pLangString
0x180002cbe  mov     rcx, cs:?sm_hResourceDll@W3_STATIC_FILE_HANDLER@@0PEAUHINSTANCE__@@EA; hLibModule
0x180002cc5  test    rcx, rcx
0x180002cc8  jz      short loc_180002CDB
0x180002cca  call    cs:__imp_FreeLibrary
0x180002cd0  mov     cs:?sm_hResourceDll@W3_STATIC_FILE_HANDLER@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * W3_STATIC_FILE_HANDLER::sm_hResourceDll
0x180002cdb  mov     cs:?sm_StartupState@W3_STATIC_FILE_HANDLER@@0W4StaticStartup@@A, 7; StaticStartup W3_STATIC_FILE_HANDLER::sm_StartupState
0x180002ce5  add     rsp, 28h
0x180002ce9  retn
```
