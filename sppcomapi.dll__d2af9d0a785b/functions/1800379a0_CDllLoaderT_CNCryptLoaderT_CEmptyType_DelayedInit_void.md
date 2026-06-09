# CDllLoaderT<CNCryptLoaderT<CEmptyType>>::DelayedInit(void)

- ea: `0x1800379a0`
- end: `0x180037ac8`
- name: `?DelayedInit@?$CDllLoaderT@V?$CNCryptLoaderT@VCEmptyType@@@@@@KAJXZ`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001ecb0`
- `0x1800379a0`
- `0x180038aec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037a94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037a94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037aa9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037aa9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180037a5b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180037a83`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180037a5b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180037a83`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800379e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800379e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800379f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800379f5`

## string_xrefs

- `0x1800379b7`: `Ncrypt.dll`

## pseudocode

```c
__int64 CDllLoaderT<CNCryptLoaderT<CEmptyType>>::DelayedInit()
{
  int v0; // eax
  unsigned int v1; // edi
  HMODULE v2; // rbx
  HMODULE Library; // rax
  HMODULE v4; // rsi
  signed int LastError; // eax
  int inited; // eax

  v0 = CMiscHelpersT<CEmptyType>::AppendToSystemPath(L"Ncrypt.dll");
  v1 = v0;
  if ( v0 < 0 )
  {
    v2 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v0);
LABEL_12:
    CNCryptLoaderT<CEmptyType>::g_Instance = v1;
    v1 = 1;
    goto LABEL_16;
  }
  Library = LoadLibraryExW(0, 0, 0);
  v4 = Library;
  if ( Library )
  {
    inited = CNCryptLoaderT<CEmptyType>::InitFunctionPointers(Library);
    v1 = inited;
    if ( inited < 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)inited);
      v2 = v4;
      goto LABEL_12;
    }
    v2 = 0;
    if ( qword_180047138 )
      FreeLibrary(qword_180047138);
    qword_180047138 = v4;
    CNCryptLoaderT<CEmptyType>::g_Instance = 0;
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v1 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v1);
    v2 = 0;
    if ( (v1 & 0x80000000) != 0 )
      goto LABEL_12;
  }
LABEL_16:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v1);
  if ( v2 )
    FreeLibrary(v2);
  return v1;
}

```

## disassembly

```asm
0x1800379a0  push    rbx
0x1800379a2  push    rbp
0x1800379a3  push    rsi
0x1800379a4  push    rdi
0x1800379a5  sub     rsp, 28h
0x1800379a9  lea     rdx, [rsp+48h+lpLibFileName]
0x1800379ae  mov     [rsp+48h+lpLibFileName], 0
0x1800379b7  lea     rcx, aNcryptDll; "Ncrypt.dll"
0x1800379be  call    ?AppendToSystemPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::AppendToSystemPath(ushort const *,ushort * *)
0x1800379c3  mov     rbp, [rsp+48h+lpLibFileName]
0x1800379c8  mov     edi, eax
0x1800379ca  test    eax, eax
0x1800379cc  jns     short loc_1800379D9
0x1800379ce  xor     ebx, ebx
0x1800379d0  mov     ecx, eax
0x1800379d2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800379d7  jmp     short loc_180037A40
0x1800379d9  xor     r8d, r8d; dwFlags
0x1800379dc  xor     edx, edx; hFile
0x1800379de  mov     rcx, rbp; lpLibFileName
0x1800379e1  call    cs:__imp_LoadLibraryExW
0x1800379e8  nop     dword ptr [rax+rax+00h]
0x1800379ed  mov     rsi, rax
0x1800379f0  test    rax, rax
0x1800379f3  jnz     short loc_180037A28
0x1800379f5  call    cs:__imp_GetLastError
0x1800379fc  nop     dword ptr [rax+rax+00h]
0x180037a01  mov     edi, eax
0x180037a03  test    eax, eax
0x180037a05  jnz     short loc_180037A0E
0x180037a07  mov     edi, 80004005h
0x180037a0c  jmp     short loc_180037A19
0x180037a0e  jle     short loc_180037A19
0x180037a10  movzx   edi, ax
0x180037a13  or      edi, 80070000h
0x180037a19  mov     ecx, edi
0x180037a1b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180037a20  xor     ebx, ebx
0x180037a22  test    edi, edi
0x180037a24  jns     short loc_180037A74
0x180037a26  jmp     short loc_180037A40
0x180037a28  mov     rcx, rsi; hModule
0x180037a2b  call    ?InitFunctionPointers@?$CNCryptLoaderT@VCEmptyType@@@@SAJPEAUHINSTANCE__@@@Z; CNCryptLoaderT<CEmptyType>::InitFunctionPointers(HINSTANCE__ *)
0x180037a30  mov     edi, eax
0x180037a32  test    eax, eax
0x180037a34  jns     short loc_180037A4D
0x180037a36  mov     ecx, eax
0x180037a38  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180037a3d  mov     rbx, rsi
0x180037a40  mov     cs:?g_Instance@?$CNCryptLoaderT@VCEmptyType@@@@0V1@A, edi; CNCryptLoaderT<CEmptyType> CNCryptLoaderT<CEmptyType>::g_Instance
0x180037a46  mov     edi, 1
0x180037a4b  jmp     short loc_180037A74
0x180037a4d  mov     rcx, cs:qword_180047138; hLibModule
0x180037a54  xor     ebx, ebx
0x180037a56  test    rcx, rcx
0x180037a59  jz      short loc_180037A67
0x180037a5b  call    cs:__imp_FreeLibrary
0x180037a62  nop     dword ptr [rax+rax+00h]
0x180037a67  mov     cs:qword_180047138, rsi
0x180037a6e  mov     cs:?g_Instance@?$CNCryptLoaderT@VCEmptyType@@@@0V1@A, ebx; CNCryptLoaderT<CEmptyType> CNCryptLoaderT<CEmptyType>::g_Instance
0x180037a74  mov     ecx, edi
0x180037a76  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180037a7b  test    rbx, rbx
0x180037a7e  jz      short loc_180037A8F
0x180037a80  mov     rcx, rbx; hLibModule
0x180037a83  call    cs:__imp_FreeLibrary
0x180037a8a  nop     dword ptr [rax+rax+00h]
0x180037a8f  test    rbp, rbp
0x180037a92  jz      short loc_180037ABC
0x180037a94  call    cs:__imp_GetProcessHeap
0x180037a9b  nop     dword ptr [rax+rax+00h]
0x180037aa0  lea     r8, [rbp-4]; lpMem
0x180037aa4  xor     edx, edx; dwFlags
0x180037aa6  mov     rcx, rax; hHeap
0x180037aa9  call    cs:__imp_HeapFree
0x180037ab0  nop     dword ptr [rax+rax+00h]
0x180037ab5  xor     ecx, ecx
0x180037ab7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180037abc  mov     eax, edi
0x180037abe  add     rsp, 28h
0x180037ac2  pop     rdi
0x180037ac3  pop     rsi
0x180037ac4  pop     rbp
0x180037ac5  pop     rbx
0x180037ac6  retn
```
