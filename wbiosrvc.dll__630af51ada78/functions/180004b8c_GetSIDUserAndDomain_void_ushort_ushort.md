# GetSIDUserAndDomain(void *,ushort * *,ushort * *)

- ea: `0x180004b8c`
- end: `0x180004cb9`
- name: `?GetSIDUserAndDomain@@YAJPEAXPEAPEAG1@Z`
- size: `301`
- prototype: `__int64 __fastcall(PSID Sid, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004808`

## callees

- `0x180004b8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c5d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004c06`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004c1b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004c06`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004c1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004c7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004c9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ca4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004c7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004c9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ca4`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180004bcd`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180004c53`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180004bcd`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180004c53`

## pseudocode

```c
__int64 __fastcall GetSIDUserAndDomain(PSID Sid, unsigned __int16 **a2, unsigned __int16 **a3)
{
  WCHAR *v3; // rsi
  WCHAR *v7; // rdi
  signed int LastError; // eax
  signed int v9; // ebx
  WCHAR *v10; // rax
  signed int v11; // eax
  WCHAR *v12; // rcx
  DWORD cchName; // [rsp+30h] [rbp-48h] BYREF
  enum _SID_NAME_USE peUse[17]; // [rsp+34h] [rbp-44h] BYREF
  DWORD cchReferencedDomainName; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse[0] = 0;
  v7 = 0;
  if ( LookupAccountSidLocalW(Sid, 0, &cchName, 0, &cchReferencedDomainName, peUse) )
  {
    v9 = -2147467259;
    goto LABEL_15;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( v9 == -2147024774 )
  {
    v3 = (WCHAR *)LocalAlloc(0x40u, 2LL * cchName);
    v10 = (WCHAR *)LocalAlloc(0x40u, 2LL * cchReferencedDomainName);
    v7 = v10;
    if ( !v3 || !v10 )
    {
      v9 = -2147024882;
      goto LABEL_15;
    }
    if ( LookupAccountSidLocalW(Sid, v3, &cchName, v10, &cchReferencedDomainName, peUse) )
    {
      v9 = 0;
      goto LABEL_11;
    }
    v11 = GetLastError();
    v9 = v11;
    if ( v11 > 0 )
      v9 = (unsigned __int16)v11 | 0x80070000;
  }
  if ( v9 < 0 )
  {
LABEL_15:
    LocalFree(v7);
    v12 = v3;
    goto LABEL_16;
  }
LABEL_11:
  *a2 = v3;
  *a3 = v7;
  LocalFree(0);
  v12 = 0;
LABEL_16:
  LocalFree(v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004b8c  mov     r11, rsp
0x180004b8f  push    rbx
0x180004b90  push    rbp
0x180004b91  push    rsi
0x180004b92  push    rdi
0x180004b93  push    r14
0x180004b95  push    r15
0x180004b97  sub     rsp, 48h
0x180004b9b  lea     rax, [r11-44h]
0x180004b9f  xor     esi, esi
0x180004ba1  mov     [r11-50h], rax
0x180004ba5  mov     r14, r8
0x180004ba8  lea     rax, [r11+20h]
0x180004bac  mov     [rsp+78h+cchName], esi
0x180004bb0  mov     r15, rdx
0x180004bb3  mov     [r11-58h], rax
0x180004bb7  xor     r9d, r9d; ReferencedDomainName
0x180004bba  mov     [r11+20h], esi
0x180004bbe  lea     r8, [r11-48h]; cchName
0x180004bc2  mov     [rsp+78h+var_44], esi
0x180004bc6  xor     edx, edx; Name
0x180004bc8  mov     rbp, rcx
0x180004bcb  xor     edi, edi
0x180004bcd  call    cs:__imp_LookupAccountSidLocalW
0x180004bd3  test    eax, eax
0x180004bd5  jnz     loc_180004C93
0x180004bdb  call    cs:__imp_GetLastError
0x180004be1  mov     ebx, eax
0x180004be3  test    eax, eax
0x180004be5  jle     short loc_180004BF0
0x180004be7  movzx   ebx, ax
0x180004bea  or      ebx, 80070000h
0x180004bf0  cmp     ebx, 8007007Ah
0x180004bf6  jnz     short loc_180004C72
0x180004bf8  mov     edx, [rsp+78h+cchName]
0x180004bfc  mov     ebx, 40h ; '@'
0x180004c01  add     rdx, rdx; uBytes
0x180004c04  mov     ecx, ebx; uFlags
0x180004c06  call    cs:__imp_LocalAlloc
0x180004c0c  mov     edx, [rsp+78h+arg_18]
0x180004c13  mov     ecx, ebx; uFlags
0x180004c15  add     rdx, rdx; uBytes
0x180004c18  mov     rsi, rax
0x180004c1b  call    cs:__imp_LocalAlloc
0x180004c21  mov     rdi, rax
0x180004c24  test    rsi, rsi
0x180004c27  jz      short loc_180004C8C
0x180004c29  test    rax, rax
0x180004c2c  jz      short loc_180004C8C
0x180004c2e  lea     rax, [rsp+78h+var_44]
0x180004c33  mov     r9, rdi; ReferencedDomainName
0x180004c36  mov     [rsp+78h+peUse], rax; peUse
0x180004c3b  lea     r8, [rsp+78h+cchName]; cchName
0x180004c40  lea     rax, [rsp+78h+arg_18]
0x180004c48  mov     rdx, rsi; Name
0x180004c4b  mov     rcx, rbp; Sid
0x180004c4e  mov     [rsp+78h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180004c53  call    cs:__imp_LookupAccountSidLocalW
0x180004c59  test    eax, eax
0x180004c5b  jnz     short loc_180004C88
0x180004c5d  call    cs:__imp_GetLastError
0x180004c63  mov     ebx, eax
0x180004c65  test    eax, eax
0x180004c67  jle     short loc_180004C72
0x180004c69  movzx   ebx, ax
0x180004c6c  or      ebx, 80070000h
0x180004c72  test    ebx, ebx
0x180004c74  js      short loc_180004C98
0x180004c76  mov     [r15], rsi
0x180004c79  xor     ecx, ecx; hMem
0x180004c7b  mov     [r14], rdi
0x180004c7e  call    cs:__imp_LocalFree
0x180004c84  xor     ecx, ecx
0x180004c86  jmp     short loc_180004CA4
0x180004c88  xor     ebx, ebx
0x180004c8a  jmp     short loc_180004C76
0x180004c8c  mov     ebx, 8007000Eh
0x180004c91  jmp     short loc_180004C98
0x180004c93  mov     ebx, 80004005h
0x180004c98  mov     rcx, rdi; hMem
0x180004c9b  call    cs:__imp_LocalFree
0x180004ca1  mov     rcx, rsi; hMem
0x180004ca4  call    cs:__imp_LocalFree
0x180004caa  mov     eax, ebx
0x180004cac  add     rsp, 48h
0x180004cb0  pop     r15
0x180004cb2  pop     r14
0x180004cb4  pop     rdi
0x180004cb5  pop     rsi
0x180004cb6  pop     rbp
0x180004cb7  pop     rbx
0x180004cb8  retn
```
