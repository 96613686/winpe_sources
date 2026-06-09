# CDllLoaderT<CNCryptLoaderT<CEmptyType>>::GlobalInit(void)

- ea: `0x1800385d0`
- end: `0x180038653`
- name: `?GlobalInit@?$CDllLoaderT@V?$CNCryptLoaderT@VCEmptyType@@@@@@KAJXZ`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800385d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800385e2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800385e2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003860d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003860d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003862b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003862b`

## pseudocode

```c
__int64 CDllLoaderT<CNCryptLoaderT<CEmptyType>>::GlobalInit()
{
  unsigned int v0; // ebx
  signed int LastError; // eax

  if ( qword_180047138 )
  {
    FreeLibrary(qword_180047138);
    qword_180047138 = 0;
  }
  v0 = -2147467259;
  CNCryptLoaderT<CEmptyType>::g_Instance = -2147467259;
  if ( InitializeCriticalSectionAndSpinCount(&stru_180047190, 0) )
  {
    dword_1800471B8 = 1;
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
0x1800385d0  push    rbx
0x1800385d2  sub     rsp, 20h
0x1800385d6  mov     rcx, cs:qword_180047138; hLibModule
0x1800385dd  test    rcx, rcx
0x1800385e0  jz      short loc_1800385F9
0x1800385e2  call    cs:__imp_FreeLibrary
0x1800385e9  nop     dword ptr [rax+rax+00h]
0x1800385ee  mov     cs:qword_180047138, 0
0x1800385f9  mov     ebx, 80004005h
0x1800385fe  lea     rcx, stru_180047190; lpCriticalSection
0x180038605  xor     edx, edx; dwSpinCount
0x180038607  mov     cs:?g_Instance@?$CNCryptLoaderT@VCEmptyType@@@@0V1@A, ebx; CNCryptLoaderT<CEmptyType> CNCryptLoaderT<CEmptyType>::g_Instance
0x18003860d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180038614  nop     dword ptr [rax+rax+00h]
0x180038619  test    eax, eax
0x18003861b  jz      short loc_18003862B
0x18003861d  mov     cs:dword_1800471B8, 1
0x180038627  xor     ebx, ebx
0x180038629  jmp     short loc_18003864A
0x18003862b  call    cs:__imp_GetLastError
0x180038632  nop     dword ptr [rax+rax+00h]
0x180038637  test    eax, eax
0x180038639  jz      short loc_18003864A
0x18003863b  jg      short loc_180038641
0x18003863d  mov     ebx, eax
0x18003863f  jmp     short loc_18003864A
0x180038641  movzx   ebx, ax
0x180038644  or      ebx, 80070000h
0x18003864a  mov     eax, ebx
0x18003864c  add     rsp, 20h
0x180038650  pop     rbx
0x180038651  retn
```
