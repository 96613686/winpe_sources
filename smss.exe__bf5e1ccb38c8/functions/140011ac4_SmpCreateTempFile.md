# SmpCreateTempFile

- ea: `0x140011ac4`
- end: `0x140011ba7`
- name: `SmpCreateTempFile`
- size: `227`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x140011d24`
- `0x140016958`

## callees

- `0x140004e30`
- `0x140011ac4`
- `0x140012078`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x140011b6d`
- `ntdll!RtlFreeUnicodeString` at `0x140011b6d`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x140011b50`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x140011b50`

## pseudocode

```c
NTSTATUS __fastcall SmpCreateTempFile(__int64 a1, __int64 a2, struct _UNICODE_STRING *a3)
{
  unsigned __int64 v6; // rdi
  unsigned int i; // ebx
  NTSTATUS result; // eax
  __int64 v9; // [rsp+28h] [rbp-260h]
  struct _UNICODE_STRING NtPathName; // [rsp+30h] [rbp-258h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-248h] BYREF

  NtPathName = 0;
  v6 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
  for ( i = 0; i < 0x64; ++i )
  {
    LODWORD(v9) = (unsigned __int16)(v6 + i);
    result = RtlStringCbPrintfW(pszDest, 0x208u, L"%s\\%s%4.4x.tmp", *(_QWORD *)(a1 + 8), a2, v9);
    if ( result < 0 )
      return result;
    if ( !RtlDosPathNameToNtPathName_U(pszDest, &NtPathName, 0, 0) )
      break;
    if ( !(unsigned __int8)SmpQueryFileExists(&NtPathName) )
    {
      result = 0;
      *a3 = NtPathName;
      return result;
    }
    RtlFreeUnicodeString(&NtPathName);
  }
  return -1073741823;
}

```

## disassembly

```asm
0x140011ac4  push    rbx
0x140011ac6  push    rbp
0x140011ac7  push    rsi
0x140011ac8  push    rdi
0x140011ac9  push    r14
0x140011acb  sub     rsp, 260h
0x140011ad2  mov     rax, cs:__security_cookie
0x140011ad9  xor     rax, rsp
0x140011adc  mov     [rsp+288h+var_38], rax
0x140011ae4  mov     eax, 7FFE0320h
0x140011ae9  xorps   xmm0, xmm0
0x140011aec  movups  xmmword ptr [rsp+288h+NtPathName.Length], xmm0
0x140011af1  mov     rsi, r8
0x140011af4  mov     r14, rdx
0x140011af7  mov     rbp, rcx
0x140011afa  mov     rax, [rax]
0x140011afd  mov     edi, ds:7FFE0004h
0x140011b04  imul    rdi, rax
0x140011b08  shr     rdi, 18h
0x140011b0c  xor     ebx, ebx
0x140011b0e  cmp     ebx, 64h ; 'd'
0x140011b11  jnb     short loc_140011B84
0x140011b13  mov     r9, [rbp+8]
0x140011b17  lea     eax, [rdi+rbx]
0x140011b1a  movzx   ecx, ax
0x140011b1d  lea     r8, aSS44xTmp; "%s\\%s%4.4x.tmp"
0x140011b24  mov     dword ptr [rsp+288h+var_260], ecx
0x140011b28  mov     edx, 208h; cbDest
0x140011b2d  lea     rcx, [rsp+288h+pszDest]; pszDest
0x140011b32  mov     [rsp+288h+var_268], r14
0x140011b37  call    RtlStringCbPrintfW
0x140011b3c  test    eax, eax
0x140011b3e  js      short loc_140011B89
0x140011b40  xor     r9d, r9d; DirectoryInfo
0x140011b43  lea     rdx, [rsp+288h+NtPathName]; NtPathName
0x140011b48  xor     r8d, r8d; NtFileNamePart
0x140011b4b  lea     rcx, [rsp+288h+pszDest]; DosPathName
0x140011b50  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x140011b56  test    al, al
0x140011b58  jz      short loc_140011B84
0x140011b5a  lea     rcx, [rsp+288h+NtPathName]
0x140011b5f  call    SmpQueryFileExists
0x140011b64  test    al, al
0x140011b66  jz      short loc_140011B77
0x140011b68  lea     rcx, [rsp+288h+NtPathName]; UnicodeString
0x140011b6d  call    cs:__imp_RtlFreeUnicodeString
0x140011b73  inc     ebx
0x140011b75  jmp     short loc_140011B0E
0x140011b77  movups  xmm0, xmmword ptr [rsp+288h+NtPathName.Length]
0x140011b7c  xor     eax, eax
0x140011b7e  movdqu  xmmword ptr [rsi], xmm0
0x140011b82  jmp     short loc_140011B89
0x140011b84  mov     eax, 0C0000001h
0x140011b89  mov     rcx, [rsp+288h+var_38]
0x140011b91  xor     rcx, rsp; StackCookie
0x140011b94  call    __security_check_cookie
0x140011b99  add     rsp, 260h
0x140011ba0  pop     r14
0x140011ba2  pop     rdi
0x140011ba3  pop     rsi
0x140011ba4  pop     rbp
0x140011ba5  pop     rbx
0x140011ba6  retn
```
