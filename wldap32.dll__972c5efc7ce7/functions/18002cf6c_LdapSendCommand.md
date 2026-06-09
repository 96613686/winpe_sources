# LdapSendCommand

- ea: `0x18002cf6c`
- end: `0x18002d1a2`
- name: `LdapSendCommand`
- size: `566`
- prototype: `__int64 __fastcall(struct ldap_connection *, struct ldap_request *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180006d80`
- `0x18002e6d4`

## callees

- `0x1800037a8`
- `0x18000e0d0`
- `0x18002cf6c`
- `0x18002d1a8`
- `0x18003a274`
- `0x18003c5bc`
- `0x18003e508`
- `0x18003f138`
- `0x180047254`

## string_xrefs

- `0x18002d04a`: `LdapSendCommand asked to send command of 0x%x handling 0x%x\n`

## pseudocode

```c
__int64 __fastcall LdapSendCommand(struct ldap_connection *a1, struct ldap_request *a2, unsigned __int16 a3)
{
  int v3; // r9d
  unsigned __int16 *v6; // r11
  struct CLdapBer **v7; // r8
  unsigned __int64 v8; // rdx
  int v9; // ecx
  char v10; // al
  unsigned int v11; // ebx
  unsigned __int16 **v13; // r9
  unsigned __int16 *v14; // rax
  int v15; // edx

  v3 = a3;
  if ( a3 )
  {
    v8 = ((unsigned __int64)a3 << 6) + *((_QWORD *)a2 + 21) - 64LL;
    v6 = *(unsigned __int16 **)(v8 + 8);
    v7 = (struct CLdapBer **)(v8 + 40);
  }
  else
  {
    v6 = (unsigned __int16 *)*((_QWORD *)a2 + 24);
    v7 = (struct CLdapBer **)((char *)a2 + 160);
    v8 = 0;
  }
  v9 = (v3 << 25) + *((_DWORD *)a2 + 27);
  if ( v8 && *(_DWORD *)(v8 + 16) == 3 && *((_BYTE *)a2 + 186) == 99 )
    *(_DWORD *)(v8 + 16) = *((_DWORD *)a2 + 58);
  v10 = *((_BYTE *)a2 + 186);
  switch ( v10 )
  {
    case 'f':
      return SendLdapModify(a2, a1, v6, v7, *((struct ldapmodW **const *)a2 + 29), *((_BYTE *)a2 + 240), v9);
    case 'J':
      return (unsigned int)SendLdapDelete(a2, a1, v6, v7, v9);
    case 'c':
      if ( (v8 && (v13 = *(unsigned __int16 ***)(v8 + 32)) != 0 || (v13 = (unsigned __int16 **)*((_QWORD *)a2 + 31), v8))
        && (v14 = *(unsigned __int16 **)(v8 + 24)) != 0
        || (v14 = (unsigned __int16 *)*((_QWORD *)a2 + 30), v8) )
      {
        v15 = *(_DWORD *)(v8 + 16);
      }
      else
      {
        v15 = 0;
      }
      return (unsigned int)SendLdapSearch(a2, a1, v6, v15, v14, v13, *((_DWORD *)a2 + 64), *((_BYTE *)a2 + 260), v7, v9);
    case 'h':
      return SendLdapAdd(a2, a1, v6, *((struct ldapmodW **const *)a2 + 29), v7, *((_BYTE *)a2 + 240), v9);
    case 'l':
      return (unsigned int)SendLdapRename(a2, a1, v6, v7, v9);
    case 'n':
      return (unsigned int)SendLdapCompare(a2, a1, v7, v6, v9);
    case 'w':
      return SendLdapExtendedOp(a2, a1, *((unsigned __int16 **)a2 + 24), v7, v9);
  }
  v11 = 82;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
    LDAPClientPrint(
      0x800000,
      "LdapSendCommand asked to send command of 0x%x handling 0x%x\n",
      *((unsigned __int8 *)a2 + 186),
      (_DWORD)a2);
  return v11;
}

```

## disassembly

```asm
0x18002cf6c  push    rbx
0x18002cf6e  push    rbp
0x18002cf6f  push    rsi
0x18002cf70  push    rdi
0x18002cf71  sub     rsp, 58h
0x18002cf75  xor     ebp, ebp
0x18002cf77  movzx   r9d, r8w
0x18002cf7b  mov     r10, rdx
0x18002cf7e  mov     rbx, rcx
0x18002cf81  test    r8w, r8w
0x18002cf85  jnz     short loc_18002CF99
0x18002cf87  mov     r11, [r10+0C0h]
0x18002cf8e  lea     r8, [r10+0A0h]
0x18002cf95  mov     edx, ebp
0x18002cf97  jmp     short loc_18002CFB6
0x18002cf99  mov     rdx, [rdx+0A8h]
0x18002cfa0  mov     rcx, r9
0x18002cfa3  shl     rcx, 6
0x18002cfa7  add     rdx, 0FFFFFFFFFFFFFFC0h
0x18002cfab  add     rdx, rcx
0x18002cfae  mov     r11, [rdx+8]
0x18002cfb2  lea     r8, [rdx+28h]; struct CLdapBer **
0x18002cfb6  mov     ecx, [r10+6Ch]
0x18002cfba  shl     r9d, 19h
0x18002cfbe  add     ecx, r9d
0x18002cfc1  test    rdx, rdx
0x18002cfc4  jz      short loc_18002CFE0
0x18002cfc6  cmp     dword ptr [rdx+10h], 3
0x18002cfca  jnz     short loc_18002CFE0
0x18002cfcc  cmp     byte ptr [r10+0BAh], 63h ; 'c'
0x18002cfd4  jnz     short loc_18002CFE0
0x18002cfd6  mov     eax, [r10+0E8h]
0x18002cfdd  mov     [rdx+10h], eax
0x18002cfe0  movzx   eax, byte ptr [r10+0BAh]
0x18002cfe8  cmp     al, 66h ; 'f'
0x18002cfea  jz      loc_18002D0DB
0x18002cff0  cmp     al, 4Ah ; 'J'
0x18002cff2  jz      loc_18002D17F
0x18002cff8  cmp     al, 63h ; 'c'
0x18002cffa  jz      loc_18002D10C
0x18002d000  cmp     al, 68h ; 'h'
0x18002d002  jz      loc_18002D0AD
0x18002d008  cmp     al, 6Ch ; 'l'
0x18002d00a  jz      loc_18002D093
0x18002d010  cmp     al, 6Eh ; 'n'
0x18002d012  jz      short loc_18002D07C
0x18002d014  cmp     al, 77h ; 'w'
0x18002d016  jz      short loc_18002D05E
0x18002d018  cmp     cs:g_fTracingOn, ebp
0x18002d01e  mov     ebx, 52h ; 'R'
0x18002d023  jz      loc_18002D196
0x18002d029  cmp     cs:g_fProviderEnabled, ebp
0x18002d02f  jz      loc_18002D196
0x18002d035  mov     ecx, 800000h
0x18002d03a  test    cs:g_ulTraceFlags, rcx
0x18002d041  jz      loc_18002D196
0x18002d047  mov     r8d, eax
0x18002d04a  lea     rdx, aLdapsendcomman; "LdapSendCommand asked to send command o"...
0x18002d051  mov     r9, r10
0x18002d054  call    LDAPClientPrint
0x18002d059  jmp     loc_18002D196
0x18002d05e  mov     dword ptr [rsp+78h+var_58], ecx; int
0x18002d062  mov     r9, r8; struct CLdapBer **
0x18002d065  mov     r8, [r10+0C0h]; unsigned __int16 *
0x18002d06c  mov     rcx, r10; struct ldap_request *
0x18002d06f  mov     rdx, rbx; struct ldap_connection *
0x18002d072  call    ?SendLdapExtendedOp@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGPEAPEAVCLdapBer@@J@Z; SendLdapExtendedOp(ldap_request *,ldap_connection *,ushort *,CLdapBer * *,long)
0x18002d077  jmp     loc_18002D194
0x18002d07c  mov     dword ptr [rsp+78h+var_58], ecx; int
0x18002d080  mov     r9, r11; unsigned __int16 *
0x18002d083  mov     rcx, r10; struct ldap_request *
0x18002d086  mov     rdx, rbx; struct ldap_connection *
0x18002d089  call    ?SendLdapCompare@@YAKPEAUldap_request@@PEAUldap_connection@@PEAPEAVCLdapBer@@PEAGJ@Z; SendLdapCompare(ldap_request *,ldap_connection *,CLdapBer * *,ushort *,long)
0x18002d08e  jmp     loc_18002D194
0x18002d093  mov     dword ptr [rsp+78h+var_58], ecx; int
0x18002d097  mov     r9, r8; struct CLdapBer **
0x18002d09a  mov     r8, r11; unsigned __int16 *
0x18002d09d  mov     rcx, r10; struct ldap_request *
0x18002d0a0  mov     rdx, rbx; struct ldap_connection *
0x18002d0a3  call    ?SendLdapRename@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGPEAPEAVCLdapBer@@J@Z; SendLdapRename(ldap_request *,ldap_connection *,ushort *,CLdapBer * *,long)
0x18002d0a8  jmp     loc_18002D194
0x18002d0ad  mov     al, [r10+0F0h]
0x18002d0b4  mov     rdx, rbx; struct ldap_connection *
0x18002d0b7  mov     r9, [r10+0E8h]; struct ldapmodW **
0x18002d0be  mov     [rsp+78h+var_48], ecx; int
0x18002d0c2  mov     rcx, r10; struct ldap_request *
0x18002d0c5  mov     byte ptr [rsp+78h+var_50], al; unsigned __int8
0x18002d0c9  mov     [rsp+78h+var_58], r8; struct CLdapBer **
0x18002d0ce  mov     r8, r11; unsigned __int16 *
0x18002d0d1  call    ?SendLdapAdd@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGQEAPEAUldapmodW@@PEAPEAVCLdapBer@@EJ@Z; SendLdapAdd(ldap_request *,ldap_connection *,ushort *,ldapmodW * * const,CLdapBer * *,uchar,long)
0x18002d0d6  jmp     loc_18002D194
0x18002d0db  mov     al, [r10+0F0h]
0x18002d0e2  mov     r9, r8; struct CLdapBer **
0x18002d0e5  mov     [rsp+78h+var_48], ecx; int
0x18002d0e9  mov     r8, r11; unsigned __int16 *
0x18002d0ec  mov     byte ptr [rsp+78h+var_50], al; unsigned __int8
0x18002d0f0  mov     rdx, rbx; struct ldap_connection *
0x18002d0f3  mov     rax, [r10+0E8h]
0x18002d0fa  mov     rcx, r10; struct ldap_request *
0x18002d0fd  mov     [rsp+78h+var_58], rax; struct ldapmodW **
0x18002d102  call    ?SendLdapModify@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGPEAPEAVCLdapBer@@QEAPEAUldapmodW@@EJ@Z; SendLdapModify(ldap_request *,ldap_connection *,ushort *,CLdapBer * *,ldapmodW * * const,uchar,long)
0x18002d107  jmp     loc_18002D194
0x18002d10c  mov     dil, [r10+104h]
0x18002d113  mov     esi, [r10+100h]
0x18002d11a  test    rdx, rdx
0x18002d11d  jz      short loc_18002D128
0x18002d11f  mov     r9, [rdx+20h]
0x18002d123  test    r9, r9
0x18002d126  jnz     short loc_18002D134
0x18002d128  mov     r9, [r10+0F8h]
0x18002d12f  test    rdx, rdx
0x18002d132  jz      short loc_18002D13D
0x18002d134  mov     rax, [rdx+18h]
0x18002d138  test    rax, rax
0x18002d13b  jnz     short loc_18002D149
0x18002d13d  mov     rax, [r10+0F0h]
0x18002d144  test    rdx, rdx
0x18002d147  jz      short loc_18002D14E
0x18002d149  mov     edx, [rdx+10h]
0x18002d14c  jmp     short loc_18002D150
0x18002d14e  mov     edx, ebp
0x18002d150  mov     [rsp+78h+var_30], ecx; int
0x18002d154  mov     rcx, r10; struct ldap_request *
0x18002d157  mov     [rsp+78h+var_38], r8; struct CLdapBer **
0x18002d15c  mov     r8, r11; unsigned __int16 *
0x18002d15f  mov     [rsp+78h+var_40], dil; unsigned __int8
0x18002d164  mov     [rsp+78h+var_48], esi; unsigned int
0x18002d168  mov     [rsp+78h+var_50], r9; unsigned __int16 **
0x18002d16d  mov     r9d, edx; unsigned int
0x18002d170  mov     rdx, rbx; struct ldap_connection *
0x18002d173  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18002d178  call    ?SendLdapSearch@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGK2PEAPEAGKEPEAPEAVCLdapBer@@J@Z; SendLdapSearch(ldap_request *,ldap_connection *,ushort *,ulong,ushort *,ushort * *,ulong,uchar,CLdapBer * *,long)
0x18002d17d  jmp     short loc_18002D194
0x18002d17f  mov     dword ptr [rsp+78h+var_58], ecx; int
0x18002d183  mov     r9, r8; struct CLdapBer **
0x18002d186  mov     r8, r11; unsigned __int16 *
0x18002d189  mov     rcx, r10; struct ldap_request *
0x18002d18c  mov     rdx, rbx; struct ldap_connection *
0x18002d18f  call    ?SendLdapDelete@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGPEAPEAVCLdapBer@@J@Z; SendLdapDelete(ldap_request *,ldap_connection *,ushort *,CLdapBer * *,long)
0x18002d194  mov     ebx, eax
0x18002d196  mov     eax, ebx
0x18002d198  add     rsp, 58h
0x18002d19c  pop     rdi
0x18002d19d  pop     rsi
0x18002d19e  pop     rbp
0x18002d19f  pop     rbx
0x18002d1a0  retn
```
