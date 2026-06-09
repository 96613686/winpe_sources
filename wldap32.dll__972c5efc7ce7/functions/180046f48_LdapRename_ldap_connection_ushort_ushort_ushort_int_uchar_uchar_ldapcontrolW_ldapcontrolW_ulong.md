# LdapRename(ldap_connection *,ushort *,ushort *,ushort *,int,uchar,uchar,ldapcontrolW * *,ldapcontrolW * *,ulong *)

- ea: `0x180046f48`
- end: `0x18004724b`
- name: `?LdapRename@@YAKPEAUldap_connection@@PEAG11HEEPEAPEAUldapcontrolW@@2PEAK@Z`
- size: `771`
- prototype: `unsigned int(struct ldap_connection *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int, unsigned __int8, unsigned __int8, struct ldapcontrolW **, struct ldapcontrolW **, unsigned int *)`
- caller_count: `5`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180047770`
- `0x180047c30`
- `0x180047e70`
- `0x180047f80`
- `0x180048210`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x180008710`
- `0x180014b60`
- `0x180015bd8`
- `0x180020320`
- `0x180022e80`
- `0x18002a284`
- `0x180046f48`
- `0x180047254`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800471c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800471c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047213`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004722b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047213`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004722b`

## string_xrefs

- `0x180047077`: `ldap_comp connection 0x%x trouble with SControl, error 0x%x.\n`
- `0x180047192`: `ldap_rename connection 0x%x errored with 0x%x.\n`
- `0x180046fd8`: `ldap_rename connection 0x%x couldn't allocate request.\n`

## pseudocode

```c
__int64 __fastcall LdapRename(
        struct ldap_connection *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int a5,
        unsigned __int8 a6,
        unsigned __int8 a7,
        struct ldapcontrolW **a8,
        struct ldapcontrolW **a9,
        unsigned int *a10)
{
  __int64 result; // rax
  __int64 v15; // rdx
  __int64 Request; // rax
  __int64 v17; // rbx
  unsigned int v18; // edi
  unsigned int v19; // r13d
  unsigned int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  struct _RTL_CRITICAL_SECTION *v24; // rcx

  if ( !a10 )
  {
    SetConnectionError(a1, 89);
    return 89;
  }
  *a10 = -1;
  result = LdapConnect(a1, 0, 0);
  if ( !(_DWORD)result )
  {
    SetConnectionError(a1, 0);
    LOBYTE(v15) = 108;
    Request = LdapCreateRequest(a1, v15);
    v17 = Request;
    if ( !Request )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
        LDAPClientPrint(0x4000, "ldap_rename connection 0x%x couldn't allocate request.\n", (_DWORD)a1);
      v18 = 90;
      SetConnectionError(a1, 90);
      return v18;
    }
    v19 = *(_DWORD *)(Request + 108);
    *(_BYTE *)(Request + 187) = a7;
    if ( a8 || (v18 = 0, a9) )
    {
      v20 = LdapCheckControls((struct ldap_request *)Request, a8, a9, a6, 0);
      v18 = v20;
      if ( v20 )
      {
        if ( !g_fTracingOn )
        {
LABEL_34:
          v19 = -1;
          SetConnectionError(a1, v18);
          CloseLdapRequest(v17);
LABEL_35:
          *a10 = v19;
          EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 48));
          --*(_DWORD *)(v17 + 16);
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
            LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", v17, *(_DWORD *)(v17 + 16));
          v24 = (struct _RTL_CRITICAL_SECTION *)(v17 + 48);
          if ( *(_DWORD *)(v17 + 16) )
          {
            LeaveCriticalSection(v24);
          }
          else
          {
            LeaveCriticalSection(v24);
            DereferenceLdapRequest2((__int64 *)v17, 0);
          }
          return v18;
        }
        if ( g_fProviderEnabled && (g_ulTraceFlags & 0x8000) != 0 )
          LDAPClientPrint(0x8000, "ldap_comp connection 0x%x trouble with SControl, error 0x%x.\n", (_DWORD)a1, v20);
LABEL_30:
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
          LDAPClientPrint(0x100000, "ldap_rename connection 0x%x errored with 0x%x.\n", (_DWORD)a1, v18);
        goto LABEL_34;
      }
    }
    *(_DWORD *)(v17 + 248) = a5;
    if ( a7 || !*(_BYTE *)(v17 + 185) )
    {
      *(_BYTE *)(v17 + 269) = 0;
      *(_QWORD *)(v17 + 192) = a2;
      *(_QWORD *)(v17 + 232) = a3;
      *(_QWORD *)(v17 + 240) = a4;
      if ( v18 )
        goto LABEL_30;
    }
    else
    {
      *(_BYTE *)(v17 + 269) = 1;
      if ( a2 )
      {
        v21 = ldap_dup_stringW(a2);
        *(_QWORD *)(v17 + 192) = v21;
        if ( !v21 )
          goto LABEL_24;
      }
      if ( v18 )
        goto LABEL_30;
      if ( a3 && (v22 = ldap_dup_stringW(a3), (*(_QWORD *)(v17 + 232) = v22) == 0)
        || a4 && (v23 = ldap_dup_stringW(a4), (*(_QWORD *)(v17 + 240) = v23) == 0) )
      {
LABEL_24:
        v18 = 90;
        goto LABEL_30;
      }
    }
    v18 = SendLdapRename(
            (struct ldap_request *)v17,
            a1,
            *(unsigned __int16 **)(v17 + 192),
            (struct CLdapBer **)(v17 + 160),
            0);
    if ( !v18 )
      goto LABEL_35;
    goto LABEL_30;
  }
  return result;
}

```

## disassembly

```asm
0x180046f48  push    rbx
0x180046f4a  push    rbp
0x180046f4b  push    rsi
0x180046f4c  push    rdi
0x180046f4d  push    r12
0x180046f4f  push    r13
0x180046f51  push    r14
0x180046f53  push    r15
0x180046f55  sub     rsp, 38h
0x180046f59  mov     rax, [rsp+78h+arg_48]
0x180046f61  mov     r15, r9
0x180046f64  mov     r14, r8
0x180046f67  mov     rbp, rdx
0x180046f6a  mov     rsi, rcx
0x180046f6d  test    rax, rax
0x180046f70  jnz     short loc_180046F83
0x180046f72  lea     ebx, [rax+59h]
0x180046f75  mov     edx, ebx
0x180046f77  call    SetConnectionError
0x180046f7c  mov     eax, ebx
0x180046f7e  jmp     loc_180047239
0x180046f83  xor     r8d, r8d
0x180046f86  mov     dword ptr [rax], 0FFFFFFFFh
0x180046f8c  xor     edx, edx
0x180046f8e  call    LdapConnect
0x180046f93  test    eax, eax
0x180046f95  jnz     loc_180047239
0x180046f9b  xor     edx, edx
0x180046f9d  mov     rcx, rsi
0x180046fa0  call    SetConnectionError
0x180046fa5  mov     dl, 6Ch ; 'l'
0x180046fa7  mov     rcx, rsi
0x180046faa  call    LdapCreateRequest
0x180046faf  mov     rbx, rax
0x180046fb2  test    rax, rax
0x180046fb5  jnz     short loc_180046FF8
0x180046fb7  cmp     cs:g_fTracingOn, eax
0x180046fbd  jz      short loc_180046FE4
0x180046fbf  cmp     cs:g_fProviderEnabled, eax
0x180046fc5  jz      short loc_180046FE4
0x180046fc7  mov     ecx, 4000h
0x180046fcc  test    cs:g_ulTraceFlags, rcx
0x180046fd3  jz      short loc_180046FE4
0x180046fd5  mov     r8, rsi
0x180046fd8  lea     rdx, aLdapRenameConn_0; "ldap_rename connection 0x%x couldn't al"...
0x180046fdf  call    LDAPClientPrint
0x180046fe4  mov     edi, 5Ah ; 'Z'
0x180046fe9  mov     rcx, rsi
0x180046fec  mov     edx, edi
0x180046fee  call    SetConnectionError
0x180046ff3  jmp     loc_180047237
0x180046ff8  mov     rdx, [rsp+78h+arg_38]; struct ldapcontrolW **
0x180047000  mov     r12b, [rsp+78h+arg_30]
0x180047008  mov     r13d, [rax+6Ch]
0x18004700c  mov     r8, [rsp+78h+arg_40]; struct ldapcontrolW **
0x180047014  mov     [rax+0BBh], r12b
0x18004701b  test    rdx, rdx
0x18004701e  jnz     short loc_180047027
0x180047020  xor     edi, edi
0x180047022  test    r8, r8
0x180047025  jz      short loc_18004708B
0x180047027  mov     r9b, [rsp+78h+arg_28]; unsigned __int8
0x18004702f  mov     rcx, rbx; struct ldap_request *
0x180047032  mov     [rsp+78h+var_58], 0; unsigned int
0x18004703a  call    LdapCheckControls
0x18004703f  mov     edi, eax
0x180047041  test    eax, eax
0x180047043  jz      short loc_18004708B
0x180047045  xor     r12d, r12d
0x180047048  cmp     cs:g_fTracingOn, r12d
0x18004704f  jz      loc_1800471A1
0x180047055  cmp     cs:g_fProviderEnabled, r12d
0x18004705c  jz      loc_18004716F
0x180047062  mov     ecx, 8000h
0x180047067  test    cs:g_ulTraceFlags, rcx
0x18004706e  jz      loc_18004716F
0x180047074  mov     r9d, eax
0x180047077  lea     rdx, aLdapCompConnec; "ldap_comp connection 0x%x trouble with "...
0x18004707e  mov     r8, rsi
0x180047081  call    LDAPClientPrint
0x180047086  jmp     loc_18004716F
0x18004708b  mov     eax, [rsp+78h+arg_20]
0x180047092  mov     [rbx+0F8h], eax
0x180047098  test    r12b, r12b
0x18004709b  jnz     loc_180047128
0x1800470a1  xor     r12d, r12d
0x1800470a4  cmp     [rbx+0B9h], r12b
0x1800470ab  jz      short loc_18004712B
0x1800470ad  mov     byte ptr [rbx+10Dh], 1
0x1800470b4  test    rbp, rbp
0x1800470b7  jz      short loc_1800470D5
0x1800470b9  xor     edx, edx
0x1800470bb  mov     r8d, 696E554Ch
0x1800470c1  mov     rcx, rbp; Src
0x1800470c4  call    ldap_dup_stringW
0x1800470c9  mov     [rbx+0C0h], rax
0x1800470d0  test    rax, rax
0x1800470d3  jz      short loc_1800470FE
0x1800470d5  test    edi, edi
0x1800470d7  jnz     loc_18004716F
0x1800470dd  test    r14, r14
0x1800470e0  jz      short loc_180047105
0x1800470e2  xor     edx, edx
0x1800470e4  mov     r8d, 696E554Ch
0x1800470ea  mov     rcx, r14; Src
0x1800470ed  call    ldap_dup_stringW
0x1800470f2  mov     [rbx+0E8h], rax
0x1800470f9  test    rax, rax
0x1800470fc  jnz     short loc_180047105
0x1800470fe  mov     edi, 5Ah ; 'Z'
0x180047103  jmp     short loc_18004716F
0x180047105  test    r15, r15
0x180047108  jz      short loc_18004714B
0x18004710a  xor     edx, edx
0x18004710c  mov     r8d, 696E554Ch
0x180047112  mov     rcx, r15; Src
0x180047115  call    ldap_dup_stringW
0x18004711a  mov     [rbx+0F0h], rax
0x180047121  test    rax, rax
0x180047124  jnz     short loc_18004714B
0x180047126  jmp     short loc_1800470FE
0x180047128  xor     r12d, r12d
0x18004712b  mov     [rbx+10Dh], r12b
0x180047132  mov     [rbx+0C0h], rbp
0x180047139  mov     [rbx+0E8h], r14
0x180047140  mov     [rbx+0F0h], r15
0x180047147  test    edi, edi
0x180047149  jnz     short loc_18004716F
0x18004714b  mov     r8, [rbx+0C0h]; unsigned __int16 *
0x180047152  lea     r9, [rbx+0A0h]; struct CLdapBer **
0x180047159  mov     rdx, rsi; struct ldap_connection *
0x18004715c  mov     [rsp+78h+var_58], r12d; int
0x180047161  mov     rcx, rbx; struct ldap_request *
0x180047164  call    ?SendLdapRename@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGPEAPEAVCLdapBer@@J@Z; SendLdapRename(ldap_request *,ldap_connection *,ushort *,CLdapBer * *,long)
0x180047169  mov     edi, eax
0x18004716b  test    eax, eax
0x18004716d  jz      short loc_1800471B7
0x18004716f  cmp     cs:g_fTracingOn, r12d
0x180047176  jz      short loc_1800471A1
0x180047178  cmp     cs:g_fProviderEnabled, r12d
0x18004717f  jz      short loc_1800471A1
0x180047181  mov     ecx, 100000h
0x180047186  test    cs:g_ulTraceFlags, rcx
0x18004718d  jz      short loc_1800471A1
0x18004718f  mov     r9d, edi
0x180047192  lea     rdx, aLdapRenameConn; "ldap_rename connection 0x%x errored wit"...
0x180047199  mov     r8, rsi
0x18004719c  call    LDAPClientPrint
0x1800471a1  mov     edx, edi
0x1800471a3  mov     rcx, rsi
0x1800471a6  or      r13d, 0FFFFFFFFh
0x1800471aa  call    SetConnectionError
0x1800471af  mov     rcx, rbx
0x1800471b2  call    CloseLdapRequest
0x1800471b7  mov     rax, [rsp+78h+arg_48]
0x1800471bf  lea     rsi, [rbx+30h]
0x1800471c3  mov     rcx, rsi; lpCriticalSection
0x1800471c6  mov     [rax], r13d
0x1800471c9  call    cs:__imp_EnterCriticalSection
0x1800471d0  nop     dword ptr [rax+rax+00h]
0x1800471d5  dec     dword ptr [rbx+10h]
0x1800471d8  cmp     cs:g_fTracingOn, r12d
0x1800471df  jz      short loc_18004720A
0x1800471e1  cmp     cs:g_fProviderEnabled, r12d
0x1800471e8  jz      short loc_18004720A
0x1800471ea  mov     ecx, 4
0x1800471ef  test    byte ptr cs:g_ulTraceFlags, cl
0x1800471f5  jz      short loc_18004720A
0x1800471f7  mov     r9d, [rbx+10h]
0x1800471fb  lea     rdx, aLdapDerefReq0x; "LDAP deref req 0x%x, new count = 0x%x\n"
0x180047202  mov     r8, rbx
0x180047205  call    LDAPClientPrint
0x18004720a  mov     rcx, rsi; lpCriticalSection
0x18004720d  cmp     [rbx+10h], r12d
0x180047211  jnz     short loc_18004722B
0x180047213  call    cs:__imp_LeaveCriticalSection
0x18004721a  nop     dword ptr [rax+rax+00h]
0x18004721f  xor     edx, edx
0x180047221  mov     rcx, rbx
0x180047224  call    DereferenceLdapRequest2
0x180047229  jmp     short loc_180047237
0x18004722b  call    cs:__imp_LeaveCriticalSection
0x180047232  nop     dword ptr [rax+rax+00h]
0x180047237  mov     eax, edi
0x180047239  add     rsp, 38h
0x18004723d  pop     r15
0x18004723f  pop     r14
0x180047241  pop     r13
0x180047243  pop     r12
0x180047245  pop     rdi
0x180047246  pop     rsi
0x180047247  pop     rbp
0x180047248  pop     rbx
0x180047249  retn
```
