# GetNtFilePathFromWin32Path(ushort const *,_UNICODE_STRING *)

- ea: `0x18001b95c`
- end: `0x18001ba89`
- name: `?GetNtFilePathFromWin32Path@@YAJPEBGPEAU_UNICODE_STRING@@@Z`
- size: `301`
- prototype: `__int64 __fastcall(PCWSTR DosPathName, PUNICODE_STRING DestinationString)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x18000eb50`

## callees

- `0x18000aba4`
- `0x18001b95c`
- `0x18001fd60`

## import_xrefs

- `msvcrt!wcsstr` at `0x18001b995`
- `msvcrt!wcsstr` at `0x18001b9aa`
- `msvcrt!wcsstr` at `0x18001b995`
- `msvcrt!wcsstr` at `0x18001b9aa`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001b9c1`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001b9c1`
- `ntdll!RtlInitUnicodeString` at `0x18001ba6f`
- `ntdll!RtlInitUnicodeString` at `0x18001ba6f`
- `ntdll!RtlAllocateHeap` at `0x18001ba16`
- `ntdll!RtlAllocateHeap` at `0x18001ba16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9cf`

## pseudocode

```c
__int64 __fastcall GetNtFilePathFromWin32Path(wchar_t *DosPathName, PUNICODE_STRING DestinationString)
{
  const WCHAR *v3; // rdi
  __int64 v4; // rcx
  unsigned int v5; // ebx
  signed int LastError; // eax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rsi
  const WCHAR *Heap; // rax
  __int64 v11; // rdx
  WCHAR *v12; // rcx
  WCHAR *v13; // rdx

  v3 = DosPathName;
  if ( !DosPathName || !DestinationString )
  {
    v4 = 2147942487LL;
    v5 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    goto LABEL_25;
  }
  v5 = 0;
  if ( wcsstr(DosPathName, L"\\??") != DosPathName && wcsstr(v3, L"\\\\") != v3 )
  {
    if ( RtlDosPathNameToNtPathName_U(v3, DestinationString, 0, 0) )
      goto LABEL_25;
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    v4 = v5;
    goto LABEL_3;
  }
  v7 = -1;
  do
    ++v7;
  while ( v3[v7] );
  v8 = (unsigned int)(v7 + 1);
  v9 = (unsigned int)v8;
  Heap = (const WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * v8);
  if ( Heap )
  {
    *Heap = 0;
    v11 = 2147483646;
    if ( (unsigned __int64)(v9 - 1) <= 0x7FFFFFFE )
    {
      v12 = (WCHAR *)Heap;
      do
      {
        if ( !v11 )
          break;
        if ( !*v3 )
          break;
        *v12++ = *v3++;
        --v11;
        --v9;
      }
      while ( v9 );
      v13 = v12 - 1;
      if ( v9 )
        v13 = v12;
      *v13 = 0;
    }
    RtlInitUnicodeString(DestinationString, Heap);
  }
LABEL_25:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return v5;
}

```

## disassembly

```asm
0x18001b95c  push    rbx
0x18001b95e  push    rbp
0x18001b95f  push    rsi
0x18001b960  push    rdi
0x18001b961  push    r14
0x18001b963  sub     rsp, 20h
0x18001b967  xor     r14d, r14d
0x18001b96a  mov     rbp, rdx
0x18001b96d  mov     rdi, rcx
0x18001b970  test    rcx, rcx
0x18001b973  jnz     short loc_18001B986
0x18001b975  mov     ecx, 80070057h
0x18001b97a  mov     ebx, ecx
0x18001b97c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b981  jmp     loc_18001BA75
0x18001b986  test    rbp, rbp
0x18001b989  jz      short loc_18001B975
0x18001b98b  lea     rdx, SubStr; "\\??"
0x18001b992  mov     ebx, r14d
0x18001b995  call    cs:__imp_wcsstr
0x18001b99b  cmp     rax, rdi
0x18001b99e  jz      short loc_18001B9F1
0x18001b9a0  lea     rdx, asc_180085898; "\\\\"
0x18001b9a7  mov     rcx, rdi; Str
0x18001b9aa  call    cs:__imp_wcsstr
0x18001b9b0  cmp     rax, rdi
0x18001b9b3  jz      short loc_18001B9F1
0x18001b9b5  xor     r9d, r9d; DirectoryInfo
0x18001b9b8  xor     r8d, r8d; NtFileNamePart
0x18001b9bb  mov     rdx, rbp; NtPathName
0x18001b9be  mov     rcx, rdi; DosPathName
0x18001b9c1  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18001b9c7  test    al, al
0x18001b9c9  jnz     loc_18001BA75
0x18001b9cf  call    cs:__imp_GetLastError
0x18001b9d5  mov     ebx, eax
0x18001b9d7  test    eax, eax
0x18001b9d9  jnz     short loc_18001B9E2
0x18001b9db  mov     ebx, 80004005h
0x18001b9e0  jmp     short loc_18001B9ED
0x18001b9e2  jle     short loc_18001B9ED
0x18001b9e4  movzx   ebx, ax
0x18001b9e7  or      ebx, 80070000h
0x18001b9ed  mov     ecx, ebx
0x18001b9ef  jmp     short loc_18001B97C
0x18001b9f1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b9f5  inc     rax
0x18001b9f8  cmp     [rdi+rax*2], r14w
0x18001b9fd  jnz     short loc_18001B9F5
0x18001b9ff  mov     rcx, gs:60h
0x18001ba08  inc     eax
0x18001ba0a  xor     edx, edx; Flags
0x18001ba0c  mov     esi, eax
0x18001ba0e  mov     rcx, [rcx+30h]; HeapHandle
0x18001ba12  lea     r8, [rax+rax]; Size
0x18001ba16  call    cs:__imp_RtlAllocateHeap
0x18001ba1c  test    rax, rax
0x18001ba1f  jz      short loc_18001BA75
0x18001ba21  lea     rcx, [rsi-1]
0x18001ba25  mov     [rax], r14w
0x18001ba29  mov     edx, 7FFFFFFEh
0x18001ba2e  cmp     rcx, rdx
0x18001ba31  ja      short loc_18001BA69
0x18001ba33  mov     rcx, rax
0x18001ba36  test    rdx, rdx
0x18001ba39  jz      short loc_18001BA5A
0x18001ba3b  movzx   r8d, word ptr [rdi]
0x18001ba3f  test    r8w, r8w
0x18001ba43  jz      short loc_18001BA5A
0x18001ba45  mov     [rcx], r8w
0x18001ba49  add     rdi, 2
0x18001ba4d  add     rcx, 2
0x18001ba51  dec     rdx
0x18001ba54  sub     rsi, 1
0x18001ba58  jnz     short loc_18001BA36
0x18001ba5a  test    rsi, rsi
0x18001ba5d  lea     rdx, [rcx-2]
0x18001ba61  cmovnz  rdx, rcx
0x18001ba65  mov     [rdx], r14w
0x18001ba69  mov     rdx, rax; SourceString
0x18001ba6c  mov     rcx, rbp; DestinationString
0x18001ba6f  call    cs:__imp_RtlInitUnicodeString
0x18001ba75  mov     ecx, ebx
0x18001ba77  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001ba7c  mov     eax, ebx
0x18001ba7e  add     rsp, 20h
0x18001ba82  pop     r14
0x18001ba84  pop     rdi
0x18001ba85  pop     rsi
0x18001ba86  pop     rbp
0x18001ba87  pop     rbx
0x18001ba88  retn
```
