# CDllLoaderT<CBCryptLoaderT<CEmptyType>>::DelayedInit(void)

- ea: `0x180037870`
- end: `0x180037998`
- name: `?DelayedInit@?$CDllLoaderT@V?$CBCryptLoaderT@VCEmptyType@@@@@@KAJXZ`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001ecb0`
- `0x180037870`
- `0x1800386ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037964`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037964`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037979`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037979`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003792b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180037953`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003792b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180037953`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800378b1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800378b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800378c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800378c5`

## string_xrefs

- `0x180037887`: `Bcrypt.dll`

## pseudocode

```c
__int64 CDllLoaderT<CBCryptLoaderT<CEmptyType>>::DelayedInit()
{
  int v0; // eax
  unsigned int v1; // edi
  HMODULE v2; // rbx
  HMODULE Library; // rax
  HMODULE v4; // rsi
  signed int LastError; // eax
  int inited; // eax

  v0 = CMiscHelpersT<CEmptyType>::AppendToSystemPath(L"Bcrypt.dll");
  v1 = v0;
  if ( v0 < 0 )
  {
    v2 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v0);
LABEL_12:
    CBCryptLoaderT<CEmptyType>::g_Instance = v1;
    v1 = 1;
    goto LABEL_16;
  }
  Library = LoadLibraryExW(0, 0, 0);
  v4 = Library;
  if ( Library )
  {
    inited = CBCryptLoaderT<CEmptyType>::InitFunctionPointers(Library);
    v1 = inited;
    if ( inited < 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)inited);
      v2 = v4;
      goto LABEL_12;
    }
    v2 = 0;
    if ( hLibModule )
      FreeLibrary(hLibModule);
    hLibModule = v4;
    CBCryptLoaderT<CEmptyType>::g_Instance = 0;
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
0x180037870  push    rbx
0x180037872  push    rbp
0x180037873  push    rsi
0x180037874  push    rdi
0x180037875  sub     rsp, 28h
0x180037879  lea     rdx, [rsp+48h+lpLibFileName]
0x18003787e  mov     [rsp+48h+lpLibFileName], 0
0x180037887  lea     rcx, aBcryptDll; "Bcrypt.dll"
0x18003788e  call    ?AppendToSystemPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::AppendToSystemPath(ushort const *,ushort * *)
0x180037893  mov     rbp, [rsp+48h+lpLibFileName]
0x180037898  mov     edi, eax
0x18003789a  test    eax, eax
0x18003789c  jns     short loc_1800378A9
0x18003789e  xor     ebx, ebx
0x1800378a0  mov     ecx, eax
0x1800378a2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800378a7  jmp     short loc_180037910
0x1800378a9  xor     r8d, r8d; dwFlags
0x1800378ac  xor     edx, edx; hFile
0x1800378ae  mov     rcx, rbp; lpLibFileName
0x1800378b1  call    cs:__imp_LoadLibraryExW
0x1800378b8  nop     dword ptr [rax+rax+00h]
0x1800378bd  mov     rsi, rax
0x1800378c0  test    rax, rax
0x1800378c3  jnz     short loc_1800378F8
0x1800378c5  call    cs:__imp_GetLastError
0x1800378cc  nop     dword ptr [rax+rax+00h]
0x1800378d1  mov     edi, eax
0x1800378d3  test    eax, eax
0x1800378d5  jnz     short loc_1800378DE
0x1800378d7  mov     edi, 80004005h
0x1800378dc  jmp     short loc_1800378E9
0x1800378de  jle     short loc_1800378E9
0x1800378e0  movzx   edi, ax
0x1800378e3  or      edi, 80070000h
0x1800378e9  mov     ecx, edi
0x1800378eb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800378f0  xor     ebx, ebx
0x1800378f2  test    edi, edi
0x1800378f4  jns     short loc_180037944
0x1800378f6  jmp     short loc_180037910
0x1800378f8  mov     rcx, rsi; hModule
0x1800378fb  call    ?InitFunctionPointers@?$CBCryptLoaderT@VCEmptyType@@@@CAJPEAUHINSTANCE__@@@Z; CBCryptLoaderT<CEmptyType>::InitFunctionPointers(HINSTANCE__ *)
0x180037900  mov     edi, eax
0x180037902  test    eax, eax
0x180037904  jns     short loc_18003791D
0x180037906  mov     ecx, eax
0x180037908  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003790d  mov     rbx, rsi
0x180037910  mov     cs:?g_Instance@?$CBCryptLoaderT@VCEmptyType@@@@0V1@A, edi; CBCryptLoaderT<CEmptyType> CBCryptLoaderT<CEmptyType>::g_Instance
0x180037916  mov     edi, 1
0x18003791b  jmp     short loc_180037944
0x18003791d  mov     rcx, cs:hLibModule; hLibModule
0x180037924  xor     ebx, ebx
0x180037926  test    rcx, rcx
0x180037929  jz      short loc_180037937
0x18003792b  call    cs:__imp_FreeLibrary
0x180037932  nop     dword ptr [rax+rax+00h]
0x180037937  mov     cs:hLibModule, rsi
0x18003793e  mov     cs:?g_Instance@?$CBCryptLoaderT@VCEmptyType@@@@0V1@A, ebx; CBCryptLoaderT<CEmptyType> CBCryptLoaderT<CEmptyType>::g_Instance
0x180037944  mov     ecx, edi
0x180037946  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003794b  test    rbx, rbx
0x18003794e  jz      short loc_18003795F
0x180037950  mov     rcx, rbx; hLibModule
0x180037953  call    cs:__imp_FreeLibrary
0x18003795a  nop     dword ptr [rax+rax+00h]
0x18003795f  test    rbp, rbp
0x180037962  jz      short loc_18003798C
0x180037964  call    cs:__imp_GetProcessHeap
0x18003796b  nop     dword ptr [rax+rax+00h]
0x180037970  lea     r8, [rbp-4]; lpMem
0x180037974  xor     edx, edx; dwFlags
0x180037976  mov     rcx, rax; hHeap
0x180037979  call    cs:__imp_HeapFree
0x180037980  nop     dword ptr [rax+rax+00h]
0x180037985  xor     ecx, ecx
0x180037987  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003798c  mov     eax, edi
0x18003798e  add     rsp, 28h
0x180037992  pop     rdi
0x180037993  pop     rsi
0x180037994  pop     rbp
0x180037995  pop     rbx
0x180037996  retn
```
