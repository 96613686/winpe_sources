# ValidateServerReturnedAttrList(ldap_connection *,ldapmsg *)

- ea: `0x18000461c`
- end: `0x180004730`
- name: `?ValidateServerReturnedAttrList@@YAEPEAUldap_connection@@PEAUldapmsg@@@Z`
- size: `276`
- prototype: `unsigned __int8 __fastcall(struct ldap_connection *, struct ldapmsg *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800057a0`

## callees

- `0x1800037a8`
- `0x18000461c`
- `0x180004740`
- `0x180005170`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000467e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000467e`

## pseudocode

```c
unsigned __int8 __fastcall ValidateServerReturnedAttrList(struct ldap_connection *a1, struct ldapmsg *a2)
{
  unsigned int v2; // edi
  __int64 Attribute; // rax
  const WCHAR *v6; // rsi
  __int64 v7; // rbx
  const WCHAR *lpString2; // rcx
  unsigned int *v10; // [rsp+60h] [rbp+18h] BYREF

  v2 = 0;
  v10 = 0;
  Attribute = LdapFirstAttribute(a1, (__int64)a2, &v10, 1);
LABEL_2:
  v6 = (const WCHAR *)Attribute;
  if ( Attribute )
  {
    v7 = 0;
    while ( 1 )
    {
      lpString2 = (&off_180065000)[v7];
      if ( lpString2 && CompareStringW(0x400u, 1u, v6, -1, lpString2, -1) == 2 )
      {
LABEL_8:
        ++v2;
        Attribute = (__int64)LdapNextAttribute((__int64)a1, (__int64)a2, v10, 1);
        goto LABEL_2;
      }
      v7 = (unsigned int)(v7 + 1);
      if ( (_DWORD)v7 == 15 )
        break;
      if ( (unsigned int)v7 >= 0xF )
        goto LABEL_8;
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10) != 0 )
      LDAPClientPrint(16, "Server returned bad attribute '%S'\n", v6);
  }
  else
  {
    if ( v2 <= 0xF )
      return 1;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10) != 0 )
      LDAPClientPrint(16, "Server returned too many (%d) attributes\n", v2);
  }
  return 0;
}

```

## disassembly

```asm
0x18000461c  mov     rax, rsp
0x18000461f  mov     [rax+8], rbx
0x180004623  mov     [rax+10h], rbp
0x180004627  push    rsi
0x180004628  push    rdi
0x180004629  push    r14
0x18000462b  sub     rsp, 30h
0x18000462f  xor     edi, edi
0x180004631  lea     r8, [rax+18h]
0x180004635  mov     r9b, 1
0x180004638  mov     [rax+18h], rdi
0x18000463c  mov     rbp, rdx
0x18000463f  mov     r14, rcx
0x180004642  call    LdapFirstAttribute
0x180004647  mov     rsi, rax
0x18000464a  test    rax, rax
0x18000464d  jz      short loc_1800046AF
0x18000464f  xor     ebx, ebx
0x180004651  lea     rcx, off_180065000; "subschemaSubentry"
0x180004658  mov     rcx, [rcx+rbx*8]
0x18000465c  test    rcx, rcx
0x18000465f  jz      short loc_18000468F
0x180004661  or      r9d, 0FFFFFFFFh; cchCount1
0x180004665  mov     [rsp+48h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000466d  mov     [rsp+48h+lpString2], rcx; lpString2
0x180004672  mov     r8, rsi; lpString1
0x180004675  mov     ecx, 400h; Locale
0x18000467a  lea     edx, [r9+2]; dwCmpFlags
0x18000467e  call    cs:__imp_CompareStringW
0x180004685  nop     dword ptr [rax+rax+00h]
0x18000468a  cmp     eax, 2
0x18000468d  jz      short loc_180004698
0x18000468f  inc     ebx
0x180004691  cmp     ebx, 0Fh
0x180004694  jz      short loc_1800046CA
0x180004696  jb      short loc_180004651
0x180004698  mov     r8, [rsp+48h+arg_10]
0x18000469d  inc     edi
0x18000469f  mov     r9b, 1
0x1800046a2  mov     rdx, rbp
0x1800046a5  mov     rcx, r14
0x1800046a8  call    LdapNextAttribute
0x1800046ad  jmp     short loc_180004647
0x1800046af  cmp     edi, 0Fh
0x1800046b2  ja      short loc_1800046FF
0x1800046b4  mov     al, 1
0x1800046b6  mov     rbx, [rsp+48h+arg_0]
0x1800046bb  mov     rbp, [rsp+48h+arg_8]
0x1800046c0  add     rsp, 30h
0x1800046c4  pop     r14
0x1800046c6  pop     rdi
0x1800046c7  pop     rsi
0x1800046c8  retn
0x1800046ca  cmp     cs:g_fTracingOn, 0
0x1800046d1  jnz     short loc_1800046D7
0x1800046d3  xor     al, al
0x1800046d5  jmp     short loc_1800046B6
0x1800046d7  cmp     cs:g_fProviderEnabled, 0
0x1800046de  jz      short loc_1800046D3
0x1800046e0  test    byte ptr cs:g_ulTraceFlags, 10h
0x1800046e7  jz      short loc_1800046D3
0x1800046e9  mov     r8, rsi
0x1800046ec  lea     rdx, aServerReturned; "Server returned bad attribute '%S'\n"
0x1800046f3  mov     ecx, 10h
0x1800046f8  call    LDAPClientPrint
0x1800046fd  jmp     short loc_1800046D3
0x1800046ff  cmp     cs:g_fTracingOn, 0
0x180004706  jz      short loc_1800046D3
0x180004708  cmp     cs:g_fProviderEnabled, 0
0x18000470f  jz      short loc_1800046D3
0x180004711  test    byte ptr cs:g_ulTraceFlags, 10h
0x180004718  jz      short loc_1800046D3
0x18000471a  mov     r8d, edi
0x18000471d  lea     rdx, aServerReturned_0; "Server returned too many (%d) attribute"...
0x180004724  mov     ecx, 10h
0x180004729  call    LDAPClientPrint
0x18000472e  jmp     short loc_1800046D3
```
