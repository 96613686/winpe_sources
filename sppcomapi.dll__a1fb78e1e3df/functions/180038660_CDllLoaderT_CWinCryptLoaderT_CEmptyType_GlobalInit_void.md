# CDllLoaderT<CWinCryptLoaderT<CEmptyType>>::GlobalInit(void)

- ea: `0x180038660`
- end: `0x1800386e3`
- name: `?GlobalInit@?$CDllLoaderT@V?$CWinCryptLoaderT@VCEmptyType@@@@@@KAJXZ`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180038660`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038672`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038672`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003869d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003869d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800386bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800386bb`

## pseudocode

```c
__int64 CDllLoaderT<CWinCryptLoaderT<CEmptyType>>::GlobalInit()
{
  unsigned int v0; // ebx
  signed int LastError; // eax

  if ( qword_180047008 )
  {
    FreeLibrary(qword_180047008);
    qword_180047008 = 0;
  }
  v0 = -2147467259;
  CWinCryptLoaderT<CEmptyType>::g_Instance = -2147467259;
  if ( InitializeCriticalSectionAndSpinCount(&stru_180047040, 0) )
  {
    dword_180047068 = 1;
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      else
        return (unsigned int)LastError;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180038660  push    rbx
0x180038662  sub     rsp, 20h
0x180038666  mov     rcx, cs:qword_180047008; hLibModule
0x18003866d  test    rcx, rcx
0x180038670  jz      short loc_180038689
0x180038672  call    cs:__imp_FreeLibrary
0x180038679  nop     dword ptr [rax+rax+00h]
0x18003867e  mov     cs:qword_180047008, 0
0x180038689  mov     ebx, 80004005h
0x18003868e  lea     rcx, stru_180047040; lpCriticalSection
0x180038695  xor     edx, edx; dwSpinCount
0x180038697  mov     cs:?g_Instance@?$CWinCryptLoaderT@VCEmptyType@@@@0V1@A, ebx; CWinCryptLoaderT<CEmptyType> CWinCryptLoaderT<CEmptyType>::g_Instance
0x18003869d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800386a4  nop     dword ptr [rax+rax+00h]
0x1800386a9  test    eax, eax
0x1800386ab  jz      short loc_1800386BB
0x1800386ad  mov     cs:dword_180047068, 1
0x1800386b7  xor     ebx, ebx
0x1800386b9  jmp     short loc_1800386DA
0x1800386bb  call    cs:__imp_GetLastError
0x1800386c2  nop     dword ptr [rax+rax+00h]
0x1800386c7  test    eax, eax
0x1800386c9  jz      short loc_1800386DA
0x1800386cb  jg      short loc_1800386D1
0x1800386cd  mov     ebx, eax
0x1800386cf  jmp     short loc_1800386DA
0x1800386d1  movzx   ebx, ax
0x1800386d4  or      ebx, 80070000h
0x1800386da  mov     eax, ebx
0x1800386dc  add     rsp, 20h
0x1800386e0  pop     rbx
0x1800386e1  retn
```
