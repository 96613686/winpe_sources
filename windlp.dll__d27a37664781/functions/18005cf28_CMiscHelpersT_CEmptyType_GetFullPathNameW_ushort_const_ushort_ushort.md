# CMiscHelpersT<CEmptyType>::GetFullPathNameW(ushort const *,ushort * *,ushort * *)

- ea: `0x18005cf28`
- end: `0x18005d0f5`
- name: `?GetFullPathNameW@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG1@Z`
- size: `461`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180063bb0`
- `0x180076190`
- `0x180076590`

## callees

- `0x180002898`
- `0x18000aba4`
- `0x18000d778`
- `0x18000ea20`
- `0x18001fd60`
- `0x18005cf28`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18005cf77`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18005d06b`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18005cf77`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18005d06b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005d0b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005d0b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d0c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d0c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d077`

## pseudocode

```c
__int64 __fastcall CMiscHelpersT<CEmptyType>::GetFullPathNameW(LPCWSTR lpFileName, LPWSTR *a2)
{
  LPWSTR v3; // rbx
  DWORD FullPathNameW; // eax
  DWORD v6; // esi
  int StringCch; // eax
  unsigned int v8; // edi
  __int64 v9; // rcx
  int v10; // eax
  DWORD v11; // ecx
  signed int LastError; // eax
  LPWSTR v13; // rax
  HANDLE ProcessHeap; // rax
  LPWSTR lpBuffer; // [rsp+20h] [rbp-E0h] BYREF
  LPWSTR FilePart; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-D0h] BYREF

  v3 = 0;
  lpBuffer = 0;
  FilePart = 0;
  FullPathNameW = GetFullPathNameW(lpFileName, 0x104u, Buffer, &FilePart);
  v6 = FullPathNameW;
  if ( !FullPathNameW )
    goto LABEL_18;
  if ( FullPathNameW > 0x104 )
  {
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v10 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateCchBufferN(v9, v6, &lpBuffer);
    v8 = v10;
    if ( v10 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v10);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
    if ( (v8 & 0x80000000) != 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
      v3 = lpBuffer;
      goto LABEL_23;
    }
    v3 = lpBuffer;
    v11 = GetFullPathNameW(lpFileName, v6, lpBuffer, &FilePart);
    if ( v11 )
    {
      if ( v11 == v6 - 1 )
      {
        v13 = v3;
        v3 = 0;
        *a2 = v13;
        goto LABEL_23;
      }
      v8 = -2147024774;
LABEL_12:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
      goto LABEL_23;
    }
LABEL_18:
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    goto LABEL_12;
  }
  LODWORD(lpBuffer) = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Buffer, &lpBuffer);
  v8 = StringCch;
  if ( StringCch < 0
    || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Buffer),
        v8 = StringCch,
        StringCch < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_12;
  if ( FilePart )
    FilePart = &(*a2)[FilePart - Buffer];
LABEL_23:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v8;
}

```

## disassembly

```asm
0x18005cf28  mov     [rsp-8+arg_10], rbx
0x18005cf2d  push    rbp
0x18005cf2e  push    rsi
0x18005cf2f  push    rdi
0x18005cf30  push    r14
0x18005cf32  push    r15
0x18005cf34  lea     rbp, [rsp-150h]
0x18005cf3c  sub     rsp, 250h
0x18005cf43  mov     rax, cs:__security_cookie
0x18005cf4a  xor     rax, rsp
0x18005cf4d  mov     [rbp+170h+var_30], rax
0x18005cf54  mov     r14, rdx
0x18005cf57  lea     r9, [rsp+270h+FilePart]; lpFilePart
0x18005cf5c  xor     ebx, ebx
0x18005cf5e  lea     r8, [rsp+270h+Buffer]; lpBuffer
0x18005cf63  mov     edi, 104h
0x18005cf68  mov     [rsp+270h+lpBuffer], rbx
0x18005cf6d  mov     edx, edi; nBufferLength
0x18005cf6f  mov     [rsp+270h+FilePart], rbx
0x18005cf74  mov     r15, rcx
0x18005cf77  call    cs:__imp_GetFullPathNameW
0x18005cf7d  mov     esi, eax
0x18005cf7f  test    eax, eax
0x18005cf81  jz      loc_18005D077
0x18005cf87  cmp     eax, edi
0x18005cf89  ja      loc_18005D019
0x18005cf8f  lea     rdx, [rsp+270h+lpBuffer]
0x18005cf94  mov     dword ptr [rsp+270h+lpBuffer], ebx
0x18005cf98  lea     rcx, [rsp+270h+Buffer]
0x18005cf9d  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18005cfa2  mov     edi, eax
0x18005cfa4  test    eax, eax
0x18005cfa6  js      short loc_18005CFBF
0x18005cfa8  mov     edx, dword ptr [rsp+270h+lpBuffer]
0x18005cfac  lea     rcx, [rsp+270h+Buffer]; Src
0x18005cfb1  mov     r8, r14
0x18005cfb4  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18005cfb9  mov     edi, eax
0x18005cfbb  test    eax, eax
0x18005cfbd  jns     short loc_18005CFC6
0x18005cfbf  mov     ecx, eax
0x18005cfc1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18005cfc6  mov     ecx, edi
0x18005cfc8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18005cfcd  test    edi, edi
0x18005cfcf  js      short loc_18005D00D
0x18005cfd1  mov     rcx, [rsp+270h+FilePart]
0x18005cfd6  test    rcx, rcx
0x18005cfd9  jz      loc_18005D0A5
0x18005cfdf  lea     rax, [rsp+270h+Buffer]
0x18005cfe4  sub     rcx, rax
0x18005cfe7  mov     rax, [r14]
0x18005cfea  sar     rcx, 1
0x18005cfed  lea     rcx, [rax+rcx*2]
0x18005cff1  mov     [rsp+270h+FilePart], rcx
0x18005cff6  jmp     loc_18005D0A5
0x18005cffb  mov     edi, 80004005h
0x18005d000  jmp     short loc_18005D00D
0x18005d002  jle     short loc_18005D00D
0x18005d004  movzx   edi, ax
0x18005d007  or      edi, 80070000h
0x18005d00d  mov     ecx, edi
0x18005d00f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18005d014  jmp     loc_18005D0A5
0x18005d019  xor     ecx, ecx
0x18005d01b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18005d020  xor     ecx, ecx
0x18005d022  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18005d027  lea     r8, [rsp+270h+lpBuffer]
0x18005d02c  mov     edx, esi
0x18005d02e  call    ?CreateCchBufferN@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateCchBufferN(ushort,ulong,ushort * *)
0x18005d033  mov     edi, eax
0x18005d035  test    eax, eax
0x18005d037  jns     short loc_18005D040
0x18005d039  mov     ecx, eax
0x18005d03b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18005d040  mov     ecx, edi
0x18005d042  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18005d047  test    edi, edi
0x18005d049  jns     short loc_18005D059
0x18005d04b  mov     ecx, edi
0x18005d04d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18005d052  mov     rbx, [rsp+270h+lpBuffer]
0x18005d057  jmp     short loc_18005D0A5
0x18005d059  mov     rbx, [rsp+270h+lpBuffer]
0x18005d05e  lea     r9, [rsp+270h+FilePart]; lpFilePart
0x18005d063  mov     r8, rbx; lpBuffer
0x18005d066  mov     edx, esi; nBufferLength
0x18005d068  mov     rcx, r15; lpFileName
0x18005d06b  call    cs:__imp_GetFullPathNameW
0x18005d071  mov     ecx, eax
0x18005d073  test    eax, eax
0x18005d075  jnz     short loc_18005D08C
0x18005d077  call    cs:__imp_GetLastError
0x18005d07d  mov     edi, eax
0x18005d07f  test    eax, eax
0x18005d081  jz      loc_18005CFFB
0x18005d087  jmp     loc_18005D002
0x18005d08c  lea     eax, [rsi-1]
0x18005d08f  cmp     ecx, eax
0x18005d091  jz      short loc_18005D09D
0x18005d093  mov     edi, 8007007Ah
0x18005d098  jmp     loc_18005D00D
0x18005d09d  mov     rax, rbx
0x18005d0a0  xor     ebx, ebx
0x18005d0a2  mov     [r14], rax
0x18005d0a5  mov     ecx, edi
0x18005d0a7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18005d0ac  test    rbx, rbx
0x18005d0af  jz      short loc_18005D0CD
0x18005d0b1  call    cs:__imp_GetProcessHeap
0x18005d0b7  lea     r8, [rbx-4]; lpMem
0x18005d0bb  xor     edx, edx; dwFlags
0x18005d0bd  mov     rcx, rax; hHeap
0x18005d0c0  call    cs:__imp_HeapFree
0x18005d0c6  xor     ecx, ecx
0x18005d0c8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18005d0cd  mov     eax, edi
0x18005d0cf  mov     rcx, [rbp+170h+var_30]
0x18005d0d6  xor     rcx, rsp; StackCookie
0x18005d0d9  call    __security_check_cookie
0x18005d0de  mov     rbx, [rsp+270h+arg_10]
0x18005d0e6  add     rsp, 250h
0x18005d0ed  pop     r15
0x18005d0ef  pop     r14
0x18005d0f1  pop     rdi
0x18005d0f2  pop     rsi
0x18005d0f3  pop     rbp
0x18005d0f4  retn
```
