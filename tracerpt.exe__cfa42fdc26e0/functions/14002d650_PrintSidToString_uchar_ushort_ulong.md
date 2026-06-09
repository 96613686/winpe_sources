# PrintSidToString(uchar *,ushort *,ulong)

- ea: `0x14002d650`
- end: `0x14002d74d`
- name: `?PrintSidToString@@YAKPEAEPEAGK@Z`
- size: `253`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002d754`
- `0x14002da1c`

## callees

- `0x140009c78`
- `0x14002d650`
- `0x140040130`
- `0x1400401c0`

## import_xrefs

- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x14002d6c3`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x14002d6c3`

## pseudocode

```c
__int64 __fastcall PrintSidToString(unsigned __int8 *a1, unsigned __int16 *a2)
{
  int v4; // eax
  unsigned int v5; // ecx
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[1024]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ReferencedDomainName[1024]; // [rsp+850h] [rbp+750h] BYREF

  peUse = 0;
  cchName = 1024;
  cchReferencedDomainName = 1024;
  if ( LookupAccountSidW(0, a1, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse)
    && (int)StringCchPrintfW(a2, 0x800u, L"\\\\%s\\%s", ReferencedDomainName, Name) >= 0 )
  {
    return 0;
  }
  v4 = StringCchPrintfW(a2, 0x800u, L"\\\\%s\\%s", ReferencedDomainName, Name);
  v5 = 0;
  if ( v4 < 0 )
    return 1359;
  return v5;
}

```

## disassembly

```asm
0x14002d650  mov     [rsp-8+arg_10], rbx
0x14002d655  push    rbp
0x14002d656  lea     rbp, [rsp-0F60h]
0x14002d65e  mov     eax, 1060h
0x14002d663  call    _alloca_probe
0x14002d668  sub     rsp, rax
0x14002d66b  mov     rax, cs:__security_cookie
0x14002d672  xor     rax, rsp
0x14002d675  mov     [rbp+0F60h+var_10], rax
0x14002d67c  mov     eax, 400h
0x14002d681  mov     [rsp+1060h+var_1020], 0
0x14002d689  mov     [rsp+1060h+cchName], eax
0x14002d68d  lea     r9, [rsp+1060h+cchName]; cchName
0x14002d692  mov     [rsp+1060h+var_101C], eax
0x14002d696  lea     r8, [rsp+1060h+Name]; Name
0x14002d69b  lea     rax, [rsp+1060h+var_1020]
0x14002d6a0  mov     rbx, rdx
0x14002d6a3  mov     [rsp+1060h+peUse], rax; peUse
0x14002d6a8  mov     rdx, rcx; Sid
0x14002d6ab  lea     rax, [rsp+1060h+var_101C]
0x14002d6b0  xor     ecx, ecx; lpSystemName
0x14002d6b2  mov     [rsp+1060h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14002d6b7  lea     rax, [rbp+0F60h+var_810]
0x14002d6be  mov     [rsp+1060h+ReferencedDomainName], rax; ReferencedDomainName
0x14002d6c3  call    cs:__imp_LookupAccountSidW
0x14002d6c9  test    eax, eax
0x14002d6cb  jz      short loc_14002D6FA
0x14002d6cd  lea     rax, [rsp+1060h+Name]
0x14002d6d2  mov     edx, 800h; unsigned __int64
0x14002d6d7  lea     r9, [rbp+0F60h+var_810]
0x14002d6de  mov     [rsp+1060h+ReferencedDomainName], rax
0x14002d6e3  lea     r8, aSS_2; "\\\\%s\\%s"
0x14002d6ea  mov     rcx, rbx; unsigned __int16 *
0x14002d6ed  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002d6f2  test    eax, eax
0x14002d6f4  js      short loc_14002D6FA
0x14002d6f6  xor     eax, eax
0x14002d6f8  jmp     short loc_14002D72D
0x14002d6fa  lea     rax, [rsp+1060h+Name]
0x14002d6ff  mov     edx, 800h; unsigned __int64
0x14002d704  lea     r9, [rbp+0F60h+var_810]
0x14002d70b  mov     [rsp+1060h+ReferencedDomainName], rax
0x14002d710  lea     r8, aSS_2; "\\\\%s\\%s"
0x14002d717  mov     rcx, rbx; unsigned __int16 *
0x14002d71a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002d71f  xor     ecx, ecx
0x14002d721  mov     edx, 54Fh
0x14002d726  test    eax, eax
0x14002d728  cmovs   ecx, edx
0x14002d72b  mov     eax, ecx
0x14002d72d  mov     rcx, [rbp+0F60h+var_10]
0x14002d734  xor     rcx, rsp; StackCookie
0x14002d737  call    __security_check_cookie
0x14002d73c  mov     rbx, [rsp+1060h+arg_10]
0x14002d744  add     rsp, 1060h
0x14002d74b  pop     rbp
0x14002d74c  retn
```
