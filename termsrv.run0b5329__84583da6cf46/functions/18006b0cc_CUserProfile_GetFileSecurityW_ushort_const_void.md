# CUserProfile::GetFileSecurityW(ushort const *,void * *)

- ea: `0x18006b0cc`
- end: `0x18006b1c6`
- name: `?GetFileSecurityW@CUserProfile@@CAJPEBGPEAPEAX@Z`
- size: `250`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18006ac5c`

## callees

- `0x18000a210`
- `0x18003269c`
- `0x180032700`
- `0x18006b0cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b17a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b17a`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18006b0fe`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18006b170`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18006b0fe`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18006b170`

## string_xrefs

- `0x18006b111`: `GetFileSecurity failed: 0x%x in %s`
- `0x18006b19d`: `GetFileSecurity failed: 0x%x in %s`
- `0x18006b11b`: `CUserProfile::GetFileSecurityW`
- `0x18006b193`: `CUserProfile::GetFileSecurityW`

## pseudocode

```c
__int64 __fastcall CUserProfile::GetFileSecurityW(LPCWSTR lpFileName, void **a2)
{
  signed int v4; // ebx
  void *v5; // rdi
  signed int LastError; // eax
  DWORD nLengthNeeded; // [rsp+68h] [rbp+10h] BYREF

  *a2 = 0;
  nLengthNeeded = 0;
  GetFileSecurityW(lpFileName, 4u, 0, 0, &nLengthNeeded);
  if ( nLengthNeeded )
  {
    v5 = operator new[](nLengthNeeded, (const struct std::nothrow_t *)std::nothrow);
    if ( v5 )
    {
      v4 = 0;
      if ( GetFileSecurityW(lpFileName, 4u, v5, nLengthNeeded, &nLengthNeeded) )
        goto LABEL_11;
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_11:
        *a2 = v5;
      }
      else
      {
        _DbgPrintMessage(8, "GetFileSecurity failed: 0x%x in %s", v4, "CUserProfile::GetFileSecurityW");
        operator delete(v5);
      }
    }
    else
    {
      v4 = -2147024882;
      _DbgPrintMessage(8, "memory allocation failed: 0x%x in %s", 2147942414LL, "CUserProfile::GetFileSecurityW");
    }
  }
  else
  {
    v4 = -2147467259;
    _DbgPrintMessage(8, "GetFileSecurity failed: 0x%x in %s", 2147500037LL, "CUserProfile::GetFileSecurityW");
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006b0cc  push    rbx
0x18006b0ce  push    rbp
0x18006b0cf  push    rsi
0x18006b0d0  push    rdi
0x18006b0d1  sub     rsp, 38h
0x18006b0d5  xor     r9d, r9d; nLength
0x18006b0d8  mov     qword ptr [rdx], 0
0x18006b0df  mov     rsi, rdx
0x18006b0e2  mov     [rsp+58h+nLengthNeeded], 0
0x18006b0ea  lea     rax, [rsp+58h+nLengthNeeded]
0x18006b0ef  xor     r8d, r8d; pSecurityDescriptor
0x18006b0f2  mov     rbp, rcx
0x18006b0f5  mov     [rsp+58h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18006b0fa  lea     edx, [r9+4]; RequestedInformation
0x18006b0fe  call    cs:__imp_GetFileSecurityW
0x18006b104  mov     eax, [rsp+58h+nLengthNeeded]
0x18006b108  test    eax, eax
0x18006b10a  jnz     short loc_18006B131
0x18006b10c  mov     ebx, 80004005h
0x18006b111  lea     rdx, aGetfilesecurit; "GetFileSecurity failed: 0x%x in %s"
0x18006b118  mov     r8d, ebx
0x18006b11b  lea     r9, aCuserprofileGe; "CUserProfile::GetFileSecurityW"
0x18006b122  mov     ecx, 8; int
0x18006b127  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b12c  jmp     loc_18006B1BB
0x18006b131  mov     rcx, rax; unsigned __int64
0x18006b134  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006b13b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006b140  mov     rdi, rax
0x18006b143  test    rax, rax
0x18006b146  jnz     short loc_18006B156
0x18006b148  mov     ebx, 8007000Eh
0x18006b14d  lea     rdx, aMemoryAllocati_0; "memory allocation failed: 0x%x in %s"
0x18006b154  jmp     short loc_18006B118
0x18006b156  mov     r9d, [rsp+58h+nLengthNeeded]; nLength
0x18006b15b  lea     rax, [rsp+58h+nLengthNeeded]
0x18006b160  xor     ebx, ebx
0x18006b162  mov     [rsp+58h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18006b167  mov     r8, rdi; pSecurityDescriptor
0x18006b16a  mov     rcx, rbp; lpFileName
0x18006b16d  lea     edx, [rbx+4]; RequestedInformation
0x18006b170  call    cs:__imp_GetFileSecurityW
0x18006b176  test    eax, eax
0x18006b178  jnz     short loc_18006B1B8
0x18006b17a  call    cs:__imp_GetLastError
0x18006b180  mov     ebx, eax
0x18006b182  test    eax, eax
0x18006b184  jle     short loc_18006B18F
0x18006b186  movzx   ebx, ax
0x18006b189  or      ebx, 80070000h
0x18006b18f  test    ebx, ebx
0x18006b191  jns     short loc_18006B1B8
0x18006b193  lea     r9, aCuserprofileGe; "CUserProfile::GetFileSecurityW"
0x18006b19a  mov     r8d, ebx
0x18006b19d  lea     rdx, aGetfilesecurit; "GetFileSecurity failed: 0x%x in %s"
0x18006b1a4  mov     ecx, 8; int
0x18006b1a9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b1ae  mov     rcx, rdi; Block
0x18006b1b1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006b1b6  jmp     short loc_18006B1BB
0x18006b1b8  mov     [rsi], rdi
0x18006b1bb  mov     eax, ebx
0x18006b1bd  add     rsp, 38h
0x18006b1c1  pop     rdi
0x18006b1c2  pop     rsi
0x18006b1c3  pop     rbp
0x18006b1c4  pop     rbx
0x18006b1c5  retn
```
