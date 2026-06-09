# LdapParseSortControl(ldap_connection *,ldapcontrolW * *,ulong *,ushort * *,ulong)

- ea: `0x18004a6c4`
- end: `0x18004a97b`
- name: `?LdapParseSortControl@@YAKPEAUldap_connection@@PEAPEAUldapcontrolW@@PEAKPEAPEAGK@Z`
- size: `695`
- prototype: `unsigned int(struct ldap_connection *, struct ldapcontrolW **, unsigned int *, unsigned __int16 **, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004ad80`
- `0x18004ae50`

## callees

- `0x180001550`
- `0x1800022c0`
- `0x1800030f0`
- `0x1800037a8`
- `0x180006510`
- `0x180014460`
- `0x18001ce90`
- `0x180020910`
- `0x18002884c`
- `0x180031c98`
- `0x18004a6c4`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18004a771`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18004a771`

## pseudocode

```c
__int64 __fastcall LdapParseSortControl(
        struct ldap_connection *a1,
        struct ldapcontrolW **a2,
        unsigned int *a3,
        char **a4,
        unsigned int a5)
{
  struct ldapcontrolW **v7; // rdi
  unsigned int v9; // ebx
  struct ldapcontrolW *v10; // rbp
  bool v11; // zf
  __int64 v12; // rax
  CLdapBer *v13; // rdi
  int v14; // ecx
  unsigned int Sequence; // eax
  unsigned int v16; // edx
  unsigned int EnumValue; // eax
  unsigned int v18; // eax
  int v20; // [rsp+68h] [rbp+10h] BYREF
  unsigned int v21; // [rsp+70h] [rbp+18h] BYREF

  v7 = a2;
  v9 = 93;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a2 )
  {
    v21 = 0;
    v20 = 0;
    while ( 1 )
    {
      v10 = *v7;
      if ( !*v7 )
        break;
      if ( a5 )
      {
        if ( a5 != 1 )
          goto LABEL_13;
        v11 = CompareStringA(0x400u, 1u, (PCNZCH)v10->ldctl_oid, -1, "1.2.840.113556.1.4.474", 23) == 2;
      }
      else
      {
        v11 = ldapWStringsIdentical(v10->ldctl_oid, -1, L"1.2.840.113556.1.4.474", -1);
      }
      if ( v11 )
      {
        v12 = ldapMalloc(872, 1816347212);
        v13 = (CLdapBer *)v12;
        if ( v12 )
        {
          v14 = *((_DWORD *)a1 + 250);
          *(_QWORD *)v12 = 0;
          *(_DWORD *)(v12 + 8) = 0;
          *(_QWORD *)(v12 + 16) = 0;
          *(_QWORD *)(v12 + 836) = 0;
          *(_QWORD *)(v12 + 24) = 0;
          *(_BYTE *)(v12 + 856) = 0;
          *(_DWORD *)(v12 + 864) = 0;
          *(_DWORD *)(v12 + 860) = v14 != 2 ? 0xFDE9 : 0;
          *(_DWORD *)(v12 + 32) = 0;
          Sequence = CLdapBer::HrLoadBer(
                       (CLdapBer *)v12,
                       (const unsigned __int8 *)v10->ldctl_value.bv_val,
                       v10->ldctl_value.bv_len,
                       &v21,
                       1u,
                       0);
          v9 = Sequence;
          if ( Sequence || (Sequence = CLdapBer::HrStartReadSequence(v13, 0x30u, 0), (v9 = Sequence) != 0) )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
              LDAPClientPrint(0x400000, "LdapParseSortControl: loadBer error of 0x%x for 0x%x.\n", Sequence, a1);
          }
          else
          {
            EnumValue = CLdapBer::HrGetEnumValue(v13, &v20);
            v9 = EnumValue;
            if ( EnumValue )
            {
              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
                LDAPClientPrint(0x400000, "LdapParseSortControl: getEnumValue error of 0x%x for 0x%x.\n", EnumValue, a1);
            }
            else
            {
              if ( a3 )
                *a3 = v20;
              if ( !a4 )
                goto LABEL_40;
              v18 = a5
                  ? CLdapBer::HrGetValueWithAlloc(v13, a4, 0)
                  : CLdapBer::HrGetValueWithAlloc(v13, (unsigned __int16 **)a4, 0);
              v9 = v18;
              if ( !v18 )
                goto LABEL_40;
              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
                LDAPClientPrint(
                  0x400000,
                  "LdapParseSortControl: GetAttribute error of 0x%x for 0x%x.\n",
                  v18,
                  (_DWORD)a1);
              if ( v9 == 16 || v9 == 84 )
LABEL_40:
                v9 = 0;
            }
          }
          CLdapBer::`scalar deleting destructor'(v13, v16);
        }
        else
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
            LDAPClientPrint(0x4000, "LdapParseSortControl: unable to allocate message for 0x%x.\n", (_DWORD)a1);
          v9 = 90;
        }
        break;
      }
LABEL_13:
      ++v7;
    }
  }
  SetConnectionError(a1, v9);
  return v9;
}

```

## disassembly

```asm
0x18004a6c4  mov     [rsp+arg_0], rbx
0x18004a6c9  mov     [rsp+arg_18], rbp
0x18004a6ce  push    rsi
0x18004a6cf  push    rdi
0x18004a6d0  push    r13
0x18004a6d2  push    r14
0x18004a6d4  push    r15
0x18004a6d6  sub     rsp, 30h
0x18004a6da  xor     r13d, r13d
0x18004a6dd  mov     r14, r9
0x18004a6e0  mov     r15, r8
0x18004a6e3  mov     rdi, rdx
0x18004a6e6  mov     rsi, rcx
0x18004a6e9  mov     ebx, 5Dh ; ']'
0x18004a6ee  test    r8, r8
0x18004a6f1  jz      short loc_18004A6F6
0x18004a6f3  mov     [r8], r13d
0x18004a6f6  test    r14, r14
0x18004a6f9  jz      short loc_18004A6FE
0x18004a6fb  mov     [r9], r13
0x18004a6fe  test    rdx, rdx
0x18004a701  jz      loc_18004A957
0x18004a707  mov     [rsp+58h+arg_10], r13d
0x18004a70c  mov     [rsp+58h+arg_8], r13d
0x18004a711  mov     rbp, [rdi]
0x18004a714  test    rbp, rbp
0x18004a717  jz      loc_18004A957
0x18004a71d  cmp     [rsp+58h+arg_20], r13d
0x18004a725  jnz     short loc_18004A742
0x18004a727  mov     rcx, [rbp+0]; lpString1
0x18004a72b  lea     r8, a12840113556144_0; "1.2.840.113556.1.4.474"
0x18004a732  or      r9d, 0FFFFFFFFh; cchCount2
0x18004a736  or      edx, r9d; cchCount1
0x18004a739  call    ldapWStringsIdentical
0x18004a73e  cmp     al, 1
0x18004a740  jmp     short loc_18004A780
0x18004a742  cmp     [rsp+58h+arg_20], 1
0x18004a74a  jnz     short loc_18004A782
0x18004a74c  mov     r8, [rbp+0]; lpString1
0x18004a750  lea     rax, a12840113556144_2; "1.2.840.113556.1.4.474"
0x18004a757  or      r9d, 0FFFFFFFFh; cchCount1
0x18004a75b  mov     [rsp+58h+cchCount2], 17h; cchCount2
0x18004a763  mov     ecx, 400h; Locale
0x18004a768  mov     [rsp+58h+lpString2], rax; lpString2
0x18004a76d  lea     edx, [r9+2]; dwCmpFlags
0x18004a771  call    cs:__imp_CompareStringA
0x18004a778  nop     dword ptr [rax+rax+00h]
0x18004a77d  cmp     eax, 2
0x18004a780  jz      short loc_18004A788
0x18004a782  add     rdi, 8
0x18004a786  jmp     short loc_18004A711
0x18004a788  mov     edx, 6C43424Ch
0x18004a78d  mov     ecx, 368h
0x18004a792  call    ldapMalloc
0x18004a797  mov     rdi, rax
0x18004a79a  test    rax, rax
0x18004a79d  jz      loc_18004A923
0x18004a7a3  mov     ecx, [rsi+3E8h]
0x18004a7a9  lea     r9, [rsp+58h+arg_10]; unsigned int *
0x18004a7ae  mov     [rax], r13
0x18004a7b1  sub     ecx, 2
0x18004a7b4  mov     [rax+8], r13d
0x18004a7b8  neg     ecx
0x18004a7ba  mov     [rax+10h], r13
0x18004a7be  mov     rcx, rdi; this
0x18004a7c1  mov     [rax+344h], r13
0x18004a7c8  mov     [rax+18h], r13
0x18004a7cc  mov     [rax+358h], r13b
0x18004a7d3  mov     [rax+360h], r13d
0x18004a7da  sbb     eax, eax
0x18004a7dc  and     eax, 0FDE9h
0x18004a7e1  mov     byte ptr [rsp+58h+cchCount2], r13b; unsigned __int8
0x18004a7e6  mov     [rdi+35Ch], eax
0x18004a7ec  mov     [rdi+20h], r13d
0x18004a7f0  mov     r8d, [rbp+8]; unsigned int
0x18004a7f4  mov     rdx, [rbp+10h]; Src
0x18004a7f8  mov     byte ptr [rsp+58h+lpString2], 1; unsigned __int8
0x18004a7fd  call    ?HrLoadBer@CLdapBer@@QEAAKPEBEKPEAKEE@Z; CLdapBer::HrLoadBer(uchar const *,ulong,ulong *,uchar,uchar)
0x18004a802  mov     ebx, eax
0x18004a804  test    eax, eax
0x18004a806  jz      short loc_18004A84B
0x18004a808  cmp     cs:g_fTracingOn, r13d
0x18004a80f  jz      loc_18004A919
0x18004a815  cmp     cs:g_fProviderEnabled, r13d
0x18004a81c  jz      loc_18004A919
0x18004a822  mov     ecx, 400000h
0x18004a827  test    cs:g_ulTraceFlags, rcx
0x18004a82e  jz      loc_18004A919
0x18004a834  lea     rdx, aLdapparsesortc_2; "LdapParseSortControl: loadBer error of "...
0x18004a83b  mov     r8d, eax
0x18004a83e  mov     r9, rsi
0x18004a841  call    LDAPClientPrint
0x18004a846  jmp     loc_18004A919
0x18004a84b  xor     r8d, r8d; unsigned __int8
0x18004a84e  mov     rcx, rdi; this
0x18004a851  lea     edx, [r8+30h]; unsigned int
0x18004a855  call    ?HrStartReadSequence@CLdapBer@@QEAAKKE@Z; CLdapBer::HrStartReadSequence(ulong,uchar)
0x18004a85a  mov     ebx, eax
0x18004a85c  test    eax, eax
0x18004a85e  jnz     short loc_18004A808
0x18004a860  lea     rdx, [rsp+58h+arg_8]; int *
0x18004a865  mov     rcx, rdi; this
0x18004a868  call    ?HrGetEnumValue@CLdapBer@@QEAAKPEAJ@Z; CLdapBer::HrGetEnumValue(long *)
0x18004a86d  mov     ebx, eax
0x18004a86f  test    eax, eax
0x18004a871  jz      short loc_18004A8A4
0x18004a873  cmp     cs:g_fTracingOn, r13d
0x18004a87a  jz      loc_18004A919
0x18004a880  cmp     cs:g_fProviderEnabled, r13d
0x18004a887  jz      loc_18004A919
0x18004a88d  mov     ecx, 400000h
0x18004a892  test    cs:g_ulTraceFlags, rcx
0x18004a899  jz      short loc_18004A919
0x18004a89b  lea     rdx, aLdapparsesortc_0; "LdapParseSortControl: getEnumValue erro"...
0x18004a8a2  jmp     short loc_18004A83B
0x18004a8a4  test    r15, r15
0x18004a8a7  jz      short loc_18004A8B0
0x18004a8a9  mov     eax, [rsp+58h+arg_8]
0x18004a8ad  mov     [r15], eax
0x18004a8b0  test    r14, r14
0x18004a8b3  jz      short loc_18004A916
0x18004a8b5  xor     r8d, r8d; unsigned __int8
0x18004a8b8  mov     rdx, r14; char **
0x18004a8bb  mov     rcx, rdi; this
0x18004a8be  cmp     [rsp+58h+arg_20], r13d
0x18004a8c6  jnz     short loc_18004A8CF
0x18004a8c8  call    ?HrGetValueWithAlloc@CLdapBer@@QEAAKPEAPEAGE@Z; CLdapBer::HrGetValueWithAlloc(ushort * *,uchar)
0x18004a8cd  jmp     short loc_18004A8D4
0x18004a8cf  call    ?HrGetValueWithAlloc@CLdapBer@@QEAAKPEAPEADE@Z; CLdapBer::HrGetValueWithAlloc(char * *,uchar)
0x18004a8d4  mov     ebx, eax
0x18004a8d6  test    eax, eax
0x18004a8d8  jz      short loc_18004A916
0x18004a8da  cmp     cs:g_fTracingOn, r13d
0x18004a8e1  jz      short loc_18004A90C
0x18004a8e3  cmp     cs:g_fProviderEnabled, r13d
0x18004a8ea  jz      short loc_18004A90C
0x18004a8ec  mov     ecx, 400000h
0x18004a8f1  test    cs:g_ulTraceFlags, rcx
0x18004a8f8  jz      short loc_18004A90C
0x18004a8fa  mov     r9, rsi
0x18004a8fd  lea     rdx, aLdapparsesortc; "LdapParseSortControl: GetAttribute erro"...
0x18004a904  mov     r8d, eax
0x18004a907  call    LDAPClientPrint
0x18004a90c  cmp     ebx, 10h
0x18004a90f  jz      short loc_18004A916
0x18004a911  cmp     ebx, 54h ; 'T'
0x18004a914  jnz     short loc_18004A919
0x18004a916  mov     ebx, r13d
0x18004a919  mov     rcx, rdi; this
0x18004a91c  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x18004a921  jmp     short loc_18004A957
0x18004a923  cmp     cs:g_fTracingOn, r13d
0x18004a92a  jz      short loc_18004A952
0x18004a92c  cmp     cs:g_fProviderEnabled, r13d
0x18004a933  jz      short loc_18004A952
0x18004a935  mov     ecx, 4000h
0x18004a93a  test    cs:g_ulTraceFlags, rcx
0x18004a941  jz      short loc_18004A952
0x18004a943  mov     r8, rsi
0x18004a946  lea     rdx, aLdapparsesortc_1; "LdapParseSortControl: unable to allocat"...
0x18004a94d  call    LDAPClientPrint
0x18004a952  mov     ebx, 5Ah ; 'Z'
0x18004a957  mov     edx, ebx
0x18004a959  mov     rcx, rsi
0x18004a95c  call    SetConnectionError
0x18004a961  mov     rbp, [rsp+58h+arg_18]
0x18004a966  mov     eax, ebx
0x18004a968  mov     rbx, [rsp+58h+arg_0]
0x18004a96d  add     rsp, 30h
0x18004a971  pop     r15
0x18004a973  pop     r14
0x18004a975  pop     r13
0x18004a977  pop     rdi
0x18004a978  pop     rsi
0x18004a979  retn
```
