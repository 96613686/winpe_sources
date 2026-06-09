# CDllLoaderT<CWinCryptLoaderT<CEmptyType>>::GlobalDone(void)

- ea: `0x1800384d0`
- end: `0x180038539`
- name: `?GlobalDone@?$CDllLoaderT@V?$CWinCryptLoaderT@VCEmptyType@@@@@@KAJXZ`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800384d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800384e0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800384e0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038511`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038511`

## pseudocode

```c
__int64 CDllLoaderT<CWinCryptLoaderT<CEmptyType>>::GlobalDone()
{
  if ( qword_180047008 )
  {
    FreeLibrary(qword_180047008);
    qword_180047008 = 0;
  }
  CWinCryptLoaderT<CEmptyType>::g_Instance = -2147467259;
  if ( dword_180047068 )
  {
    DeleteCriticalSection(&stru_180047040);
    dword_180047068 = 0;
  }
  dword_18004706C = 0;
  return 0;
}

```

## disassembly

```asm
0x1800384d0  sub     rsp, 28h
0x1800384d4  mov     rcx, cs:qword_180047008; hLibModule
0x1800384db  test    rcx, rcx
0x1800384de  jz      short loc_1800384F7
0x1800384e0  call    cs:__imp_FreeLibrary
0x1800384e7  nop     dword ptr [rax+rax+00h]
0x1800384ec  mov     cs:qword_180047008, 0
0x1800384f7  cmp     cs:dword_180047068, 0
0x1800384fe  mov     cs:?g_Instance@?$CWinCryptLoaderT@VCEmptyType@@@@0V1@A, 80004005h; CWinCryptLoaderT<CEmptyType> CWinCryptLoaderT<CEmptyType>::g_Instance
0x180038508  jz      short loc_180038527
0x18003850a  lea     rcx, stru_180047040; lpCriticalSection
0x180038511  call    cs:__imp_DeleteCriticalSection
0x180038518  nop     dword ptr [rax+rax+00h]
0x18003851d  mov     cs:dword_180047068, 0
0x180038527  mov     cs:dword_18004706C, 0
0x180038531  xor     eax, eax
0x180038533  add     rsp, 28h
0x180038537  retn
```
