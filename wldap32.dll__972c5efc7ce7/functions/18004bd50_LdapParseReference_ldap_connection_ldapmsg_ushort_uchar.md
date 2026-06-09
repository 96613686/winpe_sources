# LdapParseReference(ldap_connection *,ldapmsg *,ushort * * *,uchar)

- ea: `0x18004bd50`
- end: `0x18004beba`
- name: `?LdapParseReference@@YAKPEAUldap_connection@@PEAUldapmsg@@PEAPEAPEAGE@Z`
- size: `362`
- prototype: `unsigned int __fastcall(struct ldap_connection *, struct ldapmsg *, unsigned __int16 ***, unsigned __int8)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18004c130`
- `0x18004c200`

## callees

- `0x1800022c0`
- `0x1800037a8`
- `0x180003840`
- `0x18000b440`
- `0x180029750`
- `0x180031c98`
- `0x18004bd50`
- `0x18004c440`

## string_xrefs

- `0x18004be8e`: `HandleReferral error 0x%x while reading referral for 0x%x\n`

## pseudocode

```c
__int64 __fastcall LdapParseReference(struct ldap_connection *a1, struct ldapmsg *a2, unsigned __int16 ***a3, char a4)
{
  CLdapBer *lm_ber; // rsi
  __int64 result; // rax
  struct ldapmsg *v9; // r10
  unsigned int v10; // eax
  unsigned int v11; // ebx
  int v12; // edi
  unsigned int v13; // eax
  unsigned int v14; // ebx
  char *v15[9]; // [rsp+20h] [rbp-48h] BYREF
  int v16; // [rsp+70h] [rbp+8h] BYREF

  v15[0] = 0;
  v16 = 0;
  if ( !a1
    || (unsigned __int64)(&a2[-1].ConnectionReferenced + 7) > 0xFFFFFFFFFFFFFFFDuLL
    || a2->lm_msgtype != 115
    || !a3 )
  {
    return 89;
  }
  *a3 = 0;
  lm_ber = (CLdapBer *)a2->lm_ber;
  if ( !lm_ber )
    return 82;
  CLdapBer::Reset(lm_ber, 0);
  v10 = LdapInitialDecodeMessage(a1, v9);
  v11 = v10;
  if ( v10 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(0x800000, "HandleReferral error 0x%x while decoding referral for 0x%x\n", v10, (_DWORD)a1);
    return v11;
  }
  else
  {
    v12 = 0;
    while ( 1 )
    {
      v13 = a4
          ? CLdapBer::HrGetValueWithAlloc(lm_ber, (unsigned __int16 **)v15, 0)
          : CLdapBer::HrGetValueWithAlloc(lm_ber, v15, 0);
      v14 = v13;
      if ( v13 || !v15[0] )
        break;
      if ( (unsigned int)add_string_to_list(a3, &v16, v15[0], 0) )
        ++v12;
      else
        ldapFree((__int64)v15[0], 1818318412);
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(0x800000, "HandleReferral error 0x%x while reading referral for 0x%x\n", v13, (_DWORD)a1);
    result = 0;
    if ( !v12 )
      return v14;
  }
  return result;
}

```

## disassembly

```asm
0x18004bd50  push    rbx
0x18004bd52  push    rsi
0x18004bd53  push    rdi
0x18004bd54  push    r12
0x18004bd56  push    r14
0x18004bd58  push    r15
0x18004bd5a  sub     rsp, 38h
0x18004bd5e  mov     [rsp+68h+var_48], 0
0x18004bd67  mov     r12b, r9b
0x18004bd6a  mov     [rsp+68h+arg_0], 0
0x18004bd72  mov     r14, r8
0x18004bd75  mov     r10, rdx
0x18004bd78  mov     r15, rcx
0x18004bd7b  test    rcx, rcx
0x18004bd7e  jz      loc_18004BEA6
0x18004bd84  lea     rax, [rdx-1]
0x18004bd88  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004bd8c  ja      loc_18004BEA6
0x18004bd92  cmp     dword ptr [rdx+4], 73h ; 's'
0x18004bd96  jnz     loc_18004BEA6
0x18004bd9c  test    r8, r8
0x18004bd9f  jz      loc_18004BEA6
0x18004bda5  mov     qword ptr [r8], 0
0x18004bdac  mov     rsi, [rdx+8]
0x18004bdb0  test    rsi, rsi
0x18004bdb3  jnz     short loc_18004BDBD
0x18004bdb5  lea     eax, [rsi+52h]
0x18004bdb8  jmp     loc_18004BEAB
0x18004bdbd  xor     edx, edx; unsigned __int8
0x18004bdbf  mov     rcx, rsi; this
0x18004bdc2  call    ?Reset@CLdapBer@@QEAAXE@Z; CLdapBer::Reset(uchar)
0x18004bdc7  mov     rdx, r10; struct ldapmsg *
0x18004bdca  mov     rcx, r15; struct ldap_connection *
0x18004bdcd  call    ?LdapInitialDecodeMessage@@YAKPEAUldap_connection@@PEAUldapmsg@@@Z; LdapInitialDecodeMessage(ldap_connection *,ldapmsg *)
0x18004bdd2  mov     ebx, eax
0x18004bdd4  test    eax, eax
0x18004bdd6  jz      short loc_18004BE11
0x18004bdd8  cmp     cs:g_fTracingOn, 0
0x18004bddf  jz      short loc_18004BE0A
0x18004bde1  cmp     cs:g_fProviderEnabled, 0
0x18004bde8  jz      short loc_18004BE0A
0x18004bdea  mov     ecx, 800000h
0x18004bdef  test    cs:g_ulTraceFlags, rcx
0x18004bdf6  jz      short loc_18004BE0A
0x18004bdf8  mov     r9, r15
0x18004bdfb  lea     rdx, aHandlereferral_20; "HandleReferral error 0x%x while decodin"...
0x18004be02  mov     r8d, eax
0x18004be05  call    LDAPClientPrint
0x18004be0a  mov     eax, ebx
0x18004be0c  jmp     loc_18004BEAB
0x18004be11  xor     edi, edi
0x18004be13  xor     r8d, r8d; unsigned __int8
0x18004be16  lea     rdx, [rsp+68h+var_48]; char **
0x18004be1b  mov     rcx, rsi; this
0x18004be1e  test    r12b, r12b
0x18004be21  jz      short loc_18004BE2A
0x18004be23  call    ?HrGetValueWithAlloc@CLdapBer@@QEAAKPEAPEAGE@Z; CLdapBer::HrGetValueWithAlloc(ushort * *,uchar)
0x18004be28  jmp     short loc_18004BE2F
0x18004be2a  call    ?HrGetValueWithAlloc@CLdapBer@@QEAAKPEAPEADE@Z; CLdapBer::HrGetValueWithAlloc(char * *,uchar)
0x18004be2f  mov     ebx, eax
0x18004be31  test    eax, eax
0x18004be33  jnz     short loc_18004BE6B
0x18004be35  cmp     [rsp+68h+var_48], 0
0x18004be3b  jz      short loc_18004BE6B
0x18004be3d  mov     r8, [rsp+68h+var_48]
0x18004be42  lea     rdx, [rsp+68h+arg_0]
0x18004be47  xor     r9d, r9d
0x18004be4a  mov     rcx, r14
0x18004be4d  call    add_string_to_list
0x18004be52  test    eax, eax
0x18004be54  jz      short loc_18004BE5A
0x18004be56  inc     edi
0x18004be58  jmp     short loc_18004BE13
0x18004be5a  mov     rcx, [rsp+68h+var_48]
0x18004be5f  mov     edx, 6C61564Ch
0x18004be64  call    ldapFree
0x18004be69  jmp     short loc_18004BE13
0x18004be6b  cmp     cs:g_fTracingOn, 0
0x18004be72  jz      short loc_18004BE9D
0x18004be74  cmp     cs:g_fProviderEnabled, 0
0x18004be7b  jz      short loc_18004BE9D
0x18004be7d  mov     ecx, 800000h
0x18004be82  test    cs:g_ulTraceFlags, rcx
0x18004be89  jz      short loc_18004BE9D
0x18004be8b  mov     r9, r15
0x18004be8e  lea     rdx, aHandlereferral_33; "HandleReferral error 0x%x while reading"...
0x18004be95  mov     r8d, ebx
0x18004be98  call    LDAPClientPrint
0x18004be9d  xor     eax, eax
0x18004be9f  test    edi, edi
0x18004bea1  cmovz   eax, ebx
0x18004bea4  jmp     short loc_18004BEAB
0x18004bea6  mov     eax, 59h ; 'Y'
0x18004beab  add     rsp, 38h
0x18004beaf  pop     r15
0x18004beb1  pop     r14
0x18004beb3  pop     r12
0x18004beb5  pop     rdi
0x18004beb6  pop     rsi
0x18004beb7  pop     rbx
0x18004beb8  retn
```
