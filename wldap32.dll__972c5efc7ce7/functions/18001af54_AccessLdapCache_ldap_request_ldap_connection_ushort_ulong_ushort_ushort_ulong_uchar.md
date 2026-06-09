# AccessLdapCache(ldap_request *,ldap_connection *,ushort *,ulong,ushort *,ushort * *,ulong,uchar)

- ea: `0x18001af54`
- end: `0x18001b0cd`
- name: `?AccessLdapCache@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGK2PEAPEAGKE@Z`
- size: `377`
- prototype: `unsigned int __usercall@<eax>(struct ldap_request *@<rcx>, struct ldap_connection *@<rdx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned __int16 *, unsigned __int16 **, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015640`

## callees

- `0x18000e0d0`
- `0x1800112b0`
- `0x18001af54`
- `0x18001cf70`

## pseudocode

```c
__int64 __fastcall AccessLdapCache(
        struct ldap_request *a1,
        struct _RTL_CRITICAL_SECTION *a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned __int16 **a6,
        unsigned int a7,
        char a8)
{
  unsigned int v10; // eax
  unsigned int v11; // ecx
  unsigned __int16 **v12; // r9
  unsigned __int16 *v13; // r8
  unsigned int v14; // eax
  __int64 v15; // rsi
  char v16; // di
  int v17; // ebx
  int v18; // r9d
  unsigned __int16 *v19; // r8
  unsigned __int16 *v20; // rax
  char v22; // [rsp+20h] [rbp-58h]

  v10 = AllAttributesAreCacheable((const wchar_t **)a2, (LPCCH *)a6, a8);
  v11 = v10;
  if ( !v10 )
  {
    v12 = (unsigned __int16 **)*((_QWORD *)a1 + 31);
    v13 = (unsigned __int16 *)*((_QWORD *)a1 + 24);
    v22 = *((_BYTE *)a1 + 260);
    *(_WORD *)((char *)a1 + 273) = 256;
    return (unsigned int)FabricateLdapResult(a1, a2, v13, v12, v22);
  }
  if ( v10 - 1 <= 1 )
  {
    v15 = *((_QWORD *)a1 + 31);
    v16 = *((_BYTE *)a1 + 260);
    v17 = *((_DWORD *)a1 + 64);
    v18 = *((_DWORD *)a1 + 58);
    v19 = (unsigned __int16 *)*((_QWORD *)a1 + 24);
    v20 = (unsigned __int16 *)*((_QWORD *)a1 + 30);
    *((_QWORD *)a1 + 31) = &off_180065000;
    *((_DWORD *)a1 + 64) = 0;
    *((_BYTE *)a1 + 260) = 1;
    v14 = SendLdapSearch(
            a1,
            (struct ldap_connection *)a2,
            v19,
            v18,
            v20,
            &off_180065000,
            0,
            1u,
            (struct CLdapBer **)a1 + 20,
            0);
    *((_QWORD *)a1 + 31) = v15;
    *((_BYTE *)a1 + 260) = v16;
    *((_DWORD *)a1 + 64) = v17;
    *(_WORD *)((char *)a1 + 273) = 1;
    return v14;
  }
  if ( v10 == 3 )
    return (unsigned int)SendLdapSearch(
                           a1,
                           (struct ldap_connection *)a2,
                           *((unsigned __int16 **)a1 + 24),
                           *((_DWORD *)a1 + 58),
                           *((unsigned __int16 **)a1 + 30),
                           *((unsigned __int16 ***)a1 + 31),
                           *((_DWORD *)a1 + 64),
                           *((_BYTE *)a1 + 260),
                           (struct CLdapBer **)a1 + 20,
                           0);
  return v11;
}

```

## disassembly

```asm
0x18001af54  push    rbx
0x18001af56  push    rbp
0x18001af57  push    rsi
0x18001af58  push    rdi
0x18001af59  push    r14
0x18001af5b  sub     rsp, 50h
0x18001af5f  mov     r8b, [rsp+78h+arg_38]; unsigned __int8
0x18001af67  mov     r14, rdx
0x18001af6a  mov     rdx, [rsp+78h+arg_28]; unsigned __int16 **
0x18001af72  mov     rbp, rcx
0x18001af75  mov     rcx, r14; struct ldap_connection *
0x18001af78  call    ?AllAttributesAreCacheable@@YAKPEAUldap_connection@@QEAPEAGE@Z; AllAttributesAreCacheable(ldap_connection *,ushort * * const,uchar)
0x18001af7d  mov     ecx, eax
0x18001af7f  test    eax, eax
0x18001af81  jnz     short loc_18001AFB4
0x18001af83  mov     al, [rbp+104h]
0x18001af89  mov     rdx, r14; struct ldap_connection *
0x18001af8c  mov     r9, [rbp+0F8h]; unsigned __int16 **
0x18001af93  mov     rcx, rbp; struct ldap_request *
0x18001af96  mov     r8, [rbp+0C0h]; unsigned __int16 *
0x18001af9d  mov     byte ptr [rsp+78h+var_58], al; unsigned __int8
0x18001afa1  mov     word ptr [rbp+111h], 100h
0x18001afaa  call    ?FabricateLdapResult@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGPEAPEAGE@Z; FabricateLdapResult(ldap_request *,ldap_connection *,ushort *,ushort * *,uchar)
0x18001afaf  jmp     loc_18001B0BD
0x18001afb4  dec     eax
0x18001afb6  cmp     eax, 1
0x18001afb9  jbe     short loc_18001B022
0x18001afbb  cmp     ecx, 3
0x18001afbe  jnz     loc_18001B0BF
0x18001afc4  mov     r9d, [rbp+0E8h]; unsigned int
0x18001afcb  lea     rax, [rbp+0A0h]
0x18001afd2  mov     r8, [rbp+0C0h]; unsigned __int16 *
0x18001afd9  mov     rdx, r14; struct ldap_connection *
0x18001afdc  mov     [rsp+78h+var_30], 0; int
0x18001afe4  mov     rcx, rbp; struct ldap_request *
0x18001afe7  mov     [rsp+78h+var_38], rax; struct CLdapBer **
0x18001afec  mov     al, [rbp+104h]
0x18001aff2  mov     [rsp+78h+var_40], al; unsigned __int8
0x18001aff6  mov     eax, [rbp+100h]
0x18001affc  mov     [rsp+78h+var_48], eax; unsigned int
0x18001b000  mov     rax, [rbp+0F8h]
0x18001b007  mov     [rsp+78h+var_50], rax; unsigned __int16 **
0x18001b00c  mov     rax, [rbp+0F0h]
0x18001b013  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18001b018  call    ?SendLdapSearch@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGK2PEAPEAGKEPEAPEAVCLdapBer@@J@Z; SendLdapSearch(ldap_request *,ldap_connection *,ushort *,ulong,ushort *,ushort * *,ulong,uchar,CLdapBer * *,long)
0x18001b01d  jmp     loc_18001B0BD
0x18001b022  mov     rsi, [rbp+0F8h]
0x18001b029  lea     rcx, off_180065000; "subschemaSubentry"
0x18001b030  mov     dil, [rbp+104h]
0x18001b037  lea     rax, [rbp+0A0h]
0x18001b03e  mov     ebx, [rbp+100h]
0x18001b044  mov     rdx, r14; struct ldap_connection *
0x18001b047  mov     r9d, [rbp+0E8h]; unsigned int
0x18001b04e  mov     r8, [rbp+0C0h]; unsigned __int16 *
0x18001b055  mov     [rsp+78h+var_30], 0; int
0x18001b05d  mov     [rsp+78h+var_38], rax; struct CLdapBer **
0x18001b062  mov     rax, [rbp+0F0h]
0x18001b069  mov     [rsp+78h+var_40], 1; unsigned __int8
0x18001b06e  mov     [rsp+78h+var_48], 0; unsigned int
0x18001b076  mov     [rsp+78h+var_50], rcx; unsigned __int16 **
0x18001b07b  mov     [rbp+0F8h], rcx
0x18001b082  mov     rcx, rbp; struct ldap_request *
0x18001b085  mov     dword ptr [rbp+100h], 0
0x18001b08f  mov     byte ptr [rbp+104h], 1
0x18001b096  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18001b09b  call    ?SendLdapSearch@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGK2PEAPEAGKEPEAPEAVCLdapBer@@J@Z; SendLdapSearch(ldap_request *,ldap_connection *,ushort *,ulong,ushort *,ushort * *,ulong,uchar,CLdapBer * *,long)
0x18001b0a0  mov     [rbp+0F8h], rsi
0x18001b0a7  mov     [rbp+104h], dil
0x18001b0ae  mov     [rbp+100h], ebx
0x18001b0b4  mov     word ptr [rbp+111h], 1
0x18001b0bd  mov     ecx, eax
0x18001b0bf  mov     eax, ecx
0x18001b0c1  add     rsp, 50h
0x18001b0c5  pop     r14
0x18001b0c7  pop     rdi
0x18001b0c8  pop     rsi
0x18001b0c9  pop     rbp
0x18001b0ca  pop     rbx
0x18001b0cb  retn
```
