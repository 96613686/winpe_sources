# CDllLoaderT<CNCryptLoaderT<CEmptyType>>::GlobalDone(void)

- ea: `0x180038460`
- end: `0x1800384c9`
- name: `?GlobalDone@?$CDllLoaderT@V?$CNCryptLoaderT@VCEmptyType@@@@@@KAJXZ`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180038460`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038470`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038470`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800384a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800384a1`

## pseudocode

```c
__int64 CDllLoaderT<CNCryptLoaderT<CEmptyType>>::GlobalDone()
{
  if ( qword_180047138 )
  {
    FreeLibrary(qword_180047138);
    qword_180047138 = 0;
  }
  CNCryptLoaderT<CEmptyType>::g_Instance = -2147467259;
  if ( dword_1800471B8 )
  {
    DeleteCriticalSection(&stru_180047190);
    dword_1800471B8 = 0;
  }
  dword_1800471BC = 0;
  return 0;
}

```

## disassembly

```asm
0x180038460  sub     rsp, 28h
0x180038464  mov     rcx, cs:qword_180047138; hLibModule
0x18003846b  test    rcx, rcx
0x18003846e  jz      short loc_180038487
0x180038470  call    cs:__imp_FreeLibrary
0x180038477  nop     dword ptr [rax+rax+00h]
0x18003847c  mov     cs:qword_180047138, 0
0x180038487  cmp     cs:dword_1800471B8, 0
0x18003848e  mov     cs:?g_Instance@?$CNCryptLoaderT@VCEmptyType@@@@0V1@A, 80004005h; CNCryptLoaderT<CEmptyType> CNCryptLoaderT<CEmptyType>::g_Instance
0x180038498  jz      short loc_1800384B7
0x18003849a  lea     rcx, stru_180047190; lpCriticalSection
0x1800384a1  call    cs:__imp_DeleteCriticalSection
0x1800384a8  nop     dword ptr [rax+rax+00h]
0x1800384ad  mov     cs:dword_1800471B8, 0
0x1800384b7  mov     cs:dword_1800471BC, 0
0x1800384c1  xor     eax, eax
0x1800384c3  add     rsp, 28h
0x1800384c7  retn
```
