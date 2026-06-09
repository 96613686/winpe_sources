# CDllLoaderT<CWinCryptLoaderT<CEmptyType>>::DelayedInit(void)

- ea: `0x180037ad0`
- end: `0x180037c5f`
- name: `?DelayedInit@?$CDllLoaderT@V?$CWinCryptLoaderT@VCEmptyType@@@@@@KAJXZ`
- size: `399`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001ecb0`
- `0x180037ad0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037c2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037c2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037c40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037c40`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180037bf2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180037c1a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180037bf2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180037c1a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180037b14`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180037b14`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037b69`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037b69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b7a`

## string_xrefs

- `0x180037ae7`: `Crypt32.dll`

## pseudocode

```c
__int64 CDllLoaderT<CWinCryptLoaderT<CEmptyType>>::DelayedInit()
{
  int v0; // eax
  unsigned int v1; // edi
  HMODULE v2; // rbx
  HMODULE Library; // rax
  HMODULE v4; // rbp
  signed int v5; // eax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax

  v0 = CMiscHelpersT<CEmptyType>::AppendToSystemPath(L"Crypt32.dll");
  v1 = v0;
  if ( v0 < 0 )
  {
    v2 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v0);
LABEL_21:
    CWinCryptLoaderT<CEmptyType>::g_Instance = v1;
    v1 = 1;
    goto LABEL_25;
  }
  Library = LoadLibraryExW(0, 0, 0);
  v4 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "CryptImportPublicKeyInfoEx2");
    if ( ProcAddress )
    {
      v1 = 0;
      qword_180047010 = (__int64)ProcAddress;
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
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v1);
    if ( (v1 & 0x80000000) != 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v1);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v1);
    if ( (v1 & 0x80000000) != 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v1);
      v2 = v4;
      goto LABEL_21;
    }
    v2 = 0;
    if ( qword_180047008 )
      FreeLibrary(qword_180047008);
    qword_180047008 = v4;
    CWinCryptLoaderT<CEmptyType>::g_Instance = 0;
  }
  else
  {
    v5 = GetLastError();
    v1 = v5;
    if ( v5 )
    {
      if ( v5 > 0 )
        v1 = (unsigned __int16)v5 | 0x80070000;
    }
    else
    {
      v1 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v1);
    v2 = 0;
    if ( (v1 & 0x80000000) != 0 )
      goto LABEL_21;
  }
LABEL_25:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v1);
  if ( v2 )
    FreeLibrary(v2);
  return v1;
}

```

## disassembly

```asm
0x180037ad0  push    rbx
0x180037ad2  push    rbp
0x180037ad3  push    rsi
0x180037ad4  push    rdi
0x180037ad5  sub     rsp, 28h
0x180037ad9  lea     rdx, [rsp+48h+lpLibFileName]
0x180037ade  mov     [rsp+48h+lpLibFileName], 0
0x180037ae7  lea     rcx, aCrypt32Dll_0; "Crypt32.dll"
0x180037aee  call    ?AppendToSystemPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::AppendToSystemPath(ushort const *,ushort * *)
0x180037af3  mov     rsi, [rsp+48h+lpLibFileName]
0x180037af8  mov     edi, eax
0x180037afa  test    eax, eax
0x180037afc  jns     short loc_180037B0C
0x180037afe  xor     ebx, ebx
0x180037b00  mov     ecx, eax
0x180037b02  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180037b07  jmp     loc_180037BD7
0x180037b0c  xor     r8d, r8d; dwFlags
0x180037b0f  xor     edx, edx; hFile
0x180037b11  mov     rcx, rsi; lpLibFileName
0x180037b14  call    cs:__imp_LoadLibraryExW
0x180037b1b  nop     dword ptr [rax+rax+00h]
0x180037b20  mov     rbp, rax
0x180037b23  test    rax, rax
0x180037b26  jnz     short loc_180037B5F
0x180037b28  call    cs:__imp_GetLastError
0x180037b2f  nop     dword ptr [rax+rax+00h]
0x180037b34  mov     edi, eax
0x180037b36  test    eax, eax
0x180037b38  jnz     short loc_180037B41
0x180037b3a  mov     edi, 80004005h
0x180037b3f  jmp     short loc_180037B4C
0x180037b41  jle     short loc_180037B4C
0x180037b43  movzx   edi, ax
0x180037b46  or      edi, 80070000h
0x180037b4c  mov     ecx, edi
0x180037b4e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180037b53  xor     ebx, ebx
0x180037b55  test    edi, edi
0x180037b57  jns     loc_180037C0B
0x180037b5d  jmp     short loc_180037BD7
0x180037b5f  mov     rcx, rbp; hModule
0x180037b62  lea     rdx, aCryptimportpub; "CryptImportPublicKeyInfoEx2"
0x180037b69  call    cs:__imp_GetProcAddress
0x180037b70  nop     dword ptr [rax+rax+00h]
0x180037b75  test    rax, rax
0x180037b78  jnz     short loc_180037BA7
0x180037b7a  call    cs:__imp_GetLastError
0x180037b81  nop     dword ptr [rax+rax+00h]
0x180037b86  mov     edi, eax
0x180037b88  test    eax, eax
0x180037b8a  jnz     short loc_180037B93
0x180037b8c  mov     edi, 80004005h
0x180037b91  jmp     short loc_180037B9E
0x180037b93  jle     short loc_180037B9E
0x180037b95  movzx   edi, ax
0x180037b98  or      edi, 80070000h
0x180037b9e  mov     ecx, edi
0x180037ba0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180037ba5  jmp     short loc_180037BB0
0x180037ba7  xor     edi, edi
0x180037ba9  mov     cs:qword_180047010, rax
0x180037bb0  mov     ecx, edi
0x180037bb2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180037bb7  test    edi, edi
0x180037bb9  jns     short loc_180037BC2
0x180037bbb  mov     ecx, edi
0x180037bbd  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180037bc2  mov     ecx, edi
0x180037bc4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180037bc9  test    edi, edi
0x180037bcb  jns     short loc_180037BE4
0x180037bcd  mov     ecx, edi
0x180037bcf  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180037bd4  mov     rbx, rbp
0x180037bd7  mov     cs:?g_Instance@?$CWinCryptLoaderT@VCEmptyType@@@@0V1@A, edi; CWinCryptLoaderT<CEmptyType> CWinCryptLoaderT<CEmptyType>::g_Instance
0x180037bdd  mov     edi, 1
0x180037be2  jmp     short loc_180037C0B
0x180037be4  mov     rcx, cs:qword_180047008; hLibModule
0x180037beb  xor     ebx, ebx
0x180037bed  test    rcx, rcx
0x180037bf0  jz      short loc_180037BFE
0x180037bf2  call    cs:__imp_FreeLibrary
0x180037bf9  nop     dword ptr [rax+rax+00h]
0x180037bfe  mov     cs:qword_180047008, rbp
0x180037c05  mov     cs:?g_Instance@?$CWinCryptLoaderT@VCEmptyType@@@@0V1@A, ebx; CWinCryptLoaderT<CEmptyType> CWinCryptLoaderT<CEmptyType>::g_Instance
0x180037c0b  mov     ecx, edi
0x180037c0d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180037c12  test    rbx, rbx
0x180037c15  jz      short loc_180037C26
0x180037c17  mov     rcx, rbx; hLibModule
0x180037c1a  call    cs:__imp_FreeLibrary
0x180037c21  nop     dword ptr [rax+rax+00h]
0x180037c26  test    rsi, rsi
0x180037c29  jz      short loc_180037C53
0x180037c2b  call    cs:__imp_GetProcessHeap
0x180037c32  nop     dword ptr [rax+rax+00h]
0x180037c37  lea     r8, [rsi-4]; lpMem
0x180037c3b  xor     edx, edx; dwFlags
0x180037c3d  mov     rcx, rax; hHeap
0x180037c40  call    cs:__imp_HeapFree
0x180037c47  nop     dword ptr [rax+rax+00h]
0x180037c4c  xor     ecx, ecx
0x180037c4e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180037c53  mov     eax, edi
0x180037c55  add     rsp, 28h
0x180037c59  pop     rdi
0x180037c5a  pop     rsi
0x180037c5b  pop     rbp
0x180037c5c  pop     rbx
0x180037c5d  retn
```
