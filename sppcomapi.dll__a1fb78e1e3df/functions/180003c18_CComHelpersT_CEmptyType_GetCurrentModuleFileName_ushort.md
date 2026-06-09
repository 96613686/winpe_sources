# CComHelpersT<CEmptyType>::GetCurrentModuleFileName(ushort * *)

- ea: `0x180003c18`
- end: `0x180003d77`
- name: `?GetCurrentModuleFileName@?$CComHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003020`

## callees

- `0x1800031fc`
- `0x180003520`
- `0x1800036ec`
- `0x180003c18`
- `0x180003d80`
- `0x180004288`
- `0x18003c560`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d46`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180003c7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180003c7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c93`

## pseudocode

```c
__int64 __fastcall CComHelpersT<CEmptyType>::GetCurrentModuleFileName(_QWORD *a1)
{
  __int64 v2; // rbx
  int CurrentModuleHandle; // eax
  unsigned int v4; // edi
  __int64 v5; // rcx
  DWORD ModuleFileNameW; // eax
  signed int LastError; // eax
  int StringCch; // eax
  int v9; // eax
  __int64 v10; // rax
  HANDLE ProcessHeap; // rax
  HMODULE hModule; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Filename[264]; // [rsp+30h] [rbp-D0h] BYREF

  v2 = 0;
  v14 = 0;
  hModule = 0;
  CurrentModuleHandle = CMiscHelpersT<CEmptyType>::GetCurrentModuleHandle(&hModule);
  v4 = CurrentModuleHandle;
  if ( CurrentModuleHandle < 0 )
  {
    v5 = (unsigned int)CurrentModuleHandle;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_20;
  }
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x105u);
  Filename[260] = 0;
  if ( ModuleFileNameW )
  {
    if ( ModuleFileNameW >= 0x105 )
    {
      v4 = -2147024774;
LABEL_14:
      v5 = v4;
      goto LABEL_3;
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    if ( (v4 & 0x80000000) != 0 )
      goto LABEL_14;
  }
  LODWORD(hModule) = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Filename, &hModule);
  v4 = StringCch;
  if ( StringCch >= 0 )
  {
    v9 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
           Filename,
           (unsigned int)hModule,
           &v14);
    v4 = v9;
    if ( v9 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v9);
    v2 = v14;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_14;
  v10 = v2;
  v2 = 0;
  *a1 = v10;
LABEL_20:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v2 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v4;
}

```

## disassembly

```asm
0x180003c18  push    rbp
0x180003c1a  push    rbx
0x180003c1b  push    rsi
0x180003c1c  push    rdi
0x180003c1d  lea     rbp, [rsp-158h]
0x180003c25  sub     rsp, 258h
0x180003c2c  mov     rax, cs:__security_cookie
0x180003c33  xor     rax, rsp
0x180003c36  mov     [rbp+170h+var_30], rax
0x180003c3d  mov     rsi, rcx
0x180003c40  xor     ebx, ebx
0x180003c42  lea     rcx, [rsp+270h+hModule]
0x180003c47  mov     [rsp+270h+var_248], rbx
0x180003c4c  mov     [rsp+270h+hModule], rbx
0x180003c51  call    ?GetCurrentModuleHandle@?$CMiscHelpersT@VCEmptyType@@@@SAJPEAPEAUHINSTANCE__@@@Z; CMiscHelpersT<CEmptyType>::GetCurrentModuleHandle(HINSTANCE__ * *)
0x180003c56  mov     edi, eax
0x180003c58  test    eax, eax
0x180003c5a  jns     short loc_180003C68
0x180003c5c  mov     ecx, eax
0x180003c5e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180003c63  jmp     loc_180003D25
0x180003c68  mov     rcx, [rsp+270h+hModule]; hModule
0x180003c6d  lea     rdx, [rsp+270h+Filename]; lpFilename
0x180003c72  mov     edi, 105h
0x180003c77  mov     r8d, edi; nSize
0x180003c7a  call    cs:__imp_GetModuleFileNameW
0x180003c81  nop     dword ptr [rax+rax+00h]
0x180003c86  xor     ecx, ecx
0x180003c88  mov     [rbp+170h+var_38], cx
0x180003c8f  test    eax, eax
0x180003c91  jnz     short loc_180003CDD
0x180003c93  call    cs:__imp_GetLastError
0x180003c9a  nop     dword ptr [rax+rax+00h]
0x180003c9f  mov     edi, eax
0x180003ca1  test    eax, eax
0x180003ca3  jnz     short loc_180003CAC
0x180003ca5  mov     edi, 80004005h
0x180003caa  jmp     short loc_180003CB7
0x180003cac  jle     short loc_180003CB7
0x180003cae  movzx   edi, ax
0x180003cb1  or      edi, 80070000h
0x180003cb7  test    edi, edi
0x180003cb9  js      short loc_180003CE6
0x180003cbb  lea     rdx, [rsp+270h+hModule]
0x180003cc0  mov     dword ptr [rsp+270h+hModule], ebx
0x180003cc4  lea     rcx, [rsp+270h+Filename]
0x180003cc9  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180003cce  mov     edi, eax
0x180003cd0  test    eax, eax
0x180003cd2  jns     short loc_180003CED
0x180003cd4  mov     ecx, eax
0x180003cd6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180003cdb  jmp     short loc_180003D12
0x180003cdd  cmp     eax, edi
0x180003cdf  jb      short loc_180003CBB
0x180003ce1  mov     edi, 8007007Ah
0x180003ce6  mov     ecx, edi
0x180003ce8  jmp     loc_180003C5E
0x180003ced  mov     edx, dword ptr [rsp+270h+hModule]
0x180003cf1  lea     r8, [rsp+270h+var_248]
0x180003cf6  lea     rcx, [rsp+270h+Filename]; Src
0x180003cfb  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180003d00  mov     edi, eax
0x180003d02  test    eax, eax
0x180003d04  jns     short loc_180003D0D
0x180003d06  mov     ecx, eax
0x180003d08  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180003d0d  mov     rbx, [rsp+270h+var_248]
0x180003d12  mov     ecx, edi
0x180003d14  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180003d19  test    edi, edi
0x180003d1b  js      short loc_180003CE6
0x180003d1d  mov     rax, rbx
0x180003d20  xor     ebx, ebx
0x180003d22  mov     [rsi], rax
0x180003d25  mov     ecx, edi
0x180003d27  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180003d2c  test    rbx, rbx
0x180003d2f  jz      short loc_180003D59
0x180003d31  call    cs:__imp_GetProcessHeap
0x180003d38  nop     dword ptr [rax+rax+00h]
0x180003d3d  lea     r8, [rbx-4]; lpMem
0x180003d41  xor     edx, edx; dwFlags
0x180003d43  mov     rcx, rax; hHeap
0x180003d46  call    cs:__imp_HeapFree
0x180003d4d  nop     dword ptr [rax+rax+00h]
0x180003d52  xor     ecx, ecx
0x180003d54  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180003d59  mov     eax, edi
0x180003d5b  mov     rcx, [rbp+170h+var_30]
0x180003d62  xor     rcx, rsp; StackCookie
0x180003d65  call    __security_check_cookie
0x180003d6a  add     rsp, 258h
0x180003d71  pop     rdi
0x180003d72  pop     rsi
0x180003d73  pop     rbx
0x180003d74  pop     rbp
0x180003d75  retn
```
