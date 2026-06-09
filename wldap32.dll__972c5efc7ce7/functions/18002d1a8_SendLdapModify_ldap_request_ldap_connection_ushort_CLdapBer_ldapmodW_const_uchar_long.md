# SendLdapModify(ldap_request *,ldap_connection *,ushort *,CLdapBer * *,ldapmodW * * const,uchar,long)

- ea: `0x18002d1a8`
- end: `0x18002d529`
- name: `?SendLdapModify@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGPEAPEAVCLdapBer@@QEAPEAUldapmodW@@EJ@Z`
- size: `897`
- prototype: `unsigned int __usercall@<eax>(struct ldap_request *@<rcx>, struct ldap_connection *@<rdx>, unsigned __int16 *@<r8>, struct CLdapBer **@<r9>, struct ldapmodW **const, unsigned __int8, int)`
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x18002cf6c`
- `0x180040440`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000df44`
- `0x180010ef0`
- `0x180011c80`
- `0x180011f50`
- `0x180014060`
- `0x180014460`
- `0x18001ce90`
- `0x18002a9f8`
- `0x18002b020`
- `0x18002d1a8`
- `0x18002dbac`
- `0x18003d2b8`
- `0x1800400e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d47f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d47f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d4ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d4ee`

## string_xrefs

- `0x18002d2ad`: `ldap_modify startWrite connection 0x%x encoding error of 0x%x.\n`

## pseudocode

```c
__int64 __fastcall SendLdapModify(
        struct ldap_request *a1,
        struct ldap_connection *a2,
        unsigned __int16 *a3,
        struct CLdapBer **a4,
        struct ldapmodW **const a5,
        unsigned __int8 a6,
        int a7)
{
  int v11; // edx
  unsigned int v12; // ebx
  __int64 v13; // rdi
  int v14; // eax
  unsigned int v15; // eax
  int v16; // edx
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int inserted; // ebp
  unsigned int v22; // eax
  unsigned int v24; // eax

  if ( *((_DWORD *)a2 + 250) == 2 && (unsigned __int8)LdapCheckForMandatoryControl(*((_QWORD *)a1 + 25)) == 1 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000) != 0 )
      LDAPClientPrint(0x8000, "SendLdapModify Connection 0x%x has mandatory controls.\n", v11);
    v12 = 12;
    goto LABEL_57;
  }
  v13 = ldapMalloc(872, 1816347212);
  if ( v13 )
  {
    v14 = *((_DWORD *)a2 + 250) - 2;
    *(_QWORD *)v13 = 0;
    *(_DWORD *)(v13 + 8) = 0;
    *(_QWORD *)(v13 + 16) = 0;
    *(_QWORD *)(v13 + 836) = 0;
    *(_QWORD *)(v13 + 24) = 0;
    *(_BYTE *)(v13 + 856) = 0;
    *(_DWORD *)(v13 + 864) = 0;
    *(_DWORD *)(v13 + 860) = v14 != 0 ? 0xFDE9 : 0;
    *(_DWORD *)(v13 + 32) = 0;
    v15 = CLdapBer::HrStartWriteSequence((CLdapBer *)v13, 0x30u);
    if ( v15 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_modify startWrite connection 0x%x encoding error of 0x%x.\n", a2, v15);
    }
    else
    {
      v16 = a7;
      if ( !a7 )
        v16 = *((_DWORD *)a1 + 27);
      v17 = CLdapBer::HrAddValue((CLdapBer *)v13, v16, 2u);
      if ( v17 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
          LDAPClientPrint(0x400000, "ldap_modify MsgNo connection 0x%x encoding error of 0x%x.\n", a2, v17);
      }
      else
      {
        v18 = CLdapBer::HrStartWriteSequence((CLdapBer *)v13, 0x66u);
        if ( v18 )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
            LDAPClientPrint(0x400000, "ldap_modify cmd connection 0x%x encoding error of 0x%x.\n", a2, v18);
        }
        else
        {
          v19 = CLdapBer::HrAddValue((CLdapBer *)v13, a3, 4u);
          if ( v19 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
              LDAPClientPrint(0x400000, "ldap_modify DN connection 0x%x encoding error of 0x%x.\n", a2, v19);
          }
          else
          {
            v20 = CLdapBer::HrStartWriteSequence((CLdapBer *)v13, 0x30u);
            if ( !v20 )
            {
              v22 = EncodeModifyList((struct CLdapBer *)v13, a5, a6);
              inserted = v22;
              if ( v22 )
              {
                if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
                  LDAPClientPrint(
                    0x400000,
                    "ldap_modify attrlist connection 0x%x encoding error of 0x%x.\n",
                    (_DWORD)a2,
                    v22);
              }
              else
              {
                CLdapBer::HrEndWriteSequence((CLdapBer *)v13);
                CLdapBer::HrEndWriteSequence((CLdapBer *)v13);
                if ( *((_DWORD *)a2 + 250) == 2
                  || !*((_QWORD *)a1 + 25)
                  || (inserted = InsertServerControls(a1, a2, (struct CLdapBer *)v13)) == 0 )
                {
                  CLdapBer::HrEndWriteSequence((CLdapBer *)v13);
                  EnterCriticalSection((LPCRITICAL_SECTION)a2 + 14);
                  AddToPendingList((__int64)a1, (__int64)a2);
                  v24 = LdapSend(a2, (struct CLdapBer *)v13, 0);
                  inserted = v24;
                  if ( v24 )
                  {
                    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
                      LDAPClientPrint(
                        0x100000,
                        "ldap_modify connection 0x%x send with error of 0x%x.\n",
                        (_DWORD)a2,
                        v24);
                    DecrementPendingList(a1, a2);
                  }
                  else
                  {
                    v13 = _InterlockedExchange64((volatile __int64 *)a4, v13);
                  }
                  LeaveCriticalSection((LPCRITICAL_SECTION)a2 + 14);
                  if ( !v13 )
                    return inserted;
                }
              }
LABEL_45:
              CLdapBer::`scalar deleting destructor'((CLdapBer *)v13);
              return inserted;
            }
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
              LDAPClientPrint(0x400000, "ldap_modify attrlist connection 0x%x encoding error of 0x%x.\n", a2, v20);
          }
        }
      }
    }
    inserted = 83;
    goto LABEL_45;
  }
  v12 = 90;
LABEL_57:
  SetConnectionError(a2, v12);
  return v12;
}

```

## disassembly

```asm
0x18002d1a8  push    rbx
0x18002d1aa  push    rbp
0x18002d1ab  push    rsi
0x18002d1ac  push    rdi
0x18002d1ad  push    r12
0x18002d1af  push    r14
0x18002d1b1  push    r15
0x18002d1b3  sub     rsp, 20h
0x18002d1b7  mov     r15d, 2
0x18002d1bd  mov     r12, r9
0x18002d1c0  mov     rbp, r8
0x18002d1c3  mov     rsi, rdx
0x18002d1c6  mov     r14, rcx
0x18002d1c9  cmp     [rdx+3E8h], r15d
0x18002d1d0  jnz     short loc_18002D21B
0x18002d1d2  mov     rcx, [rcx+0C8h]
0x18002d1d9  call    LdapCheckForMandatoryControl
0x18002d1de  cmp     al, 1
0x18002d1e0  jnz     short loc_18002D21B
0x18002d1e2  xor     ebx, ebx
0x18002d1e4  cmp     cs:g_fTracingOn, ebx
0x18002d1ea  jz      short loc_18002D211
0x18002d1ec  cmp     cs:g_fProviderEnabled, ebx
0x18002d1f2  jz      short loc_18002D211
0x18002d1f4  mov     ecx, 8000h
0x18002d1f9  test    cs:g_ulTraceFlags, rcx
0x18002d200  jz      short loc_18002D211
0x18002d202  mov     r8, rdx
0x18002d205  lea     rdx, aSendldapmodify; "SendLdapModify Connection 0x%x has mand"...
0x18002d20c  call    LDAPClientPrint
0x18002d211  mov     ebx, 0Ch
0x18002d216  jmp     loc_18002D50D
0x18002d21b  mov     edx, 6C43424Ch
0x18002d220  mov     ecx, 368h
0x18002d225  call    ldapMalloc
0x18002d22a  xor     ebx, ebx
0x18002d22c  mov     rdi, rax
0x18002d22f  test    rax, rax
0x18002d232  jz      loc_18002D508
0x18002d238  mov     eax, [rsi+3E8h]
0x18002d23e  lea     edx, [rbx+30h]; unsigned int
0x18002d241  sub     eax, r15d
0x18002d244  mov     [rdi], rbx
0x18002d247  neg     eax
0x18002d249  mov     [rdi+8], ebx
0x18002d24c  mov     [rdi+10h], rbx
0x18002d250  mov     rcx, rdi; this
0x18002d253  sbb     eax, eax
0x18002d255  mov     [rdi+344h], rbx
0x18002d25c  and     eax, 0FDE9h
0x18002d261  mov     [rdi+18h], rbx
0x18002d265  mov     [rdi+358h], bl
0x18002d26b  mov     [rdi+360h], ebx
0x18002d271  mov     [rdi+35Ch], eax
0x18002d277  mov     [rdi+20h], ebx
0x18002d27a  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x18002d27f  test    eax, eax
0x18002d281  jz      short loc_18002D2B9
0x18002d283  cmp     cs:g_fTracingOn, ebx
0x18002d289  jz      loc_18002D3CE
0x18002d28f  cmp     cs:g_fProviderEnabled, ebx
0x18002d295  jz      loc_18002D3CE
0x18002d29b  mov     ecx, 400000h
0x18002d2a0  test    cs:g_ulTraceFlags, rcx
0x18002d2a7  jz      loc_18002D3CE
0x18002d2ad  lea     rdx, aLdapModifyStar; "ldap_modify startWrite connection 0x%x "...
0x18002d2b4  jmp     loc_18002D3C3
0x18002d2b9  mov     edx, [rsp+58h+arg_30]
0x18002d2c0  test    edx, edx
0x18002d2c2  jnz     short loc_18002D2C8
0x18002d2c4  mov     edx, [r14+6Ch]; int
0x18002d2c8  mov     r8d, r15d; unsigned int
0x18002d2cb  mov     rcx, rdi; this
0x18002d2ce  call    ?HrAddValue@CLdapBer@@QEAAKJK@Z; CLdapBer::HrAddValue(long,ulong)
0x18002d2d3  test    eax, eax
0x18002d2d5  jz      short loc_18002D30D
0x18002d2d7  cmp     cs:g_fTracingOn, ebx
0x18002d2dd  jz      loc_18002D3CE
0x18002d2e3  cmp     cs:g_fProviderEnabled, ebx
0x18002d2e9  jz      loc_18002D3CE
0x18002d2ef  mov     ecx, 400000h
0x18002d2f4  test    cs:g_ulTraceFlags, rcx
0x18002d2fb  jz      loc_18002D3CE
0x18002d301  lea     rdx, aLdapModifyMsgn; "ldap_modify MsgNo connection 0x%x encod"...
0x18002d308  jmp     loc_18002D3C3
0x18002d30d  mov     edx, 66h ; 'f'; unsigned int
0x18002d312  mov     rcx, rdi; this
0x18002d315  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x18002d31a  test    eax, eax
0x18002d31c  jz      short loc_18002D351
0x18002d31e  cmp     cs:g_fTracingOn, ebx
0x18002d324  jz      loc_18002D3CE
0x18002d32a  cmp     cs:g_fProviderEnabled, ebx
0x18002d330  jz      loc_18002D3CE
0x18002d336  mov     ecx, 400000h
0x18002d33b  test    cs:g_ulTraceFlags, rcx
0x18002d342  jz      loc_18002D3CE
0x18002d348  lea     rdx, aLdapModifyCmdC; "ldap_modify cmd connection 0x%x encodin"...
0x18002d34f  jmp     short loc_18002D3C3
0x18002d351  mov     r8d, 4; unsigned int
0x18002d357  mov     rdx, rbp; unsigned __int16 *
0x18002d35a  mov     rcx, rdi; this
0x18002d35d  call    ?HrAddValue@CLdapBer@@QEAAKPEBGK@Z; CLdapBer::HrAddValue(ushort const *,ulong)
0x18002d362  test    eax, eax
0x18002d364  jz      short loc_18002D38D
0x18002d366  cmp     cs:g_fTracingOn, ebx
0x18002d36c  jz      short loc_18002D3CE
0x18002d36e  cmp     cs:g_fProviderEnabled, ebx
0x18002d374  jz      short loc_18002D3CE
0x18002d376  mov     ecx, 400000h
0x18002d37b  test    cs:g_ulTraceFlags, rcx
0x18002d382  jz      short loc_18002D3CE
0x18002d384  lea     rdx, aLdapModifyDnCo; "ldap_modify DN connection 0x%x encoding"...
0x18002d38b  jmp     short loc_18002D3C3
0x18002d38d  mov     edx, 30h ; '0'; unsigned int
0x18002d392  mov     rcx, rdi; this
0x18002d395  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x18002d39a  test    eax, eax
0x18002d39c  jz      short loc_18002D3D8
0x18002d39e  cmp     cs:g_fTracingOn, ebx
0x18002d3a4  jz      short loc_18002D3CE
0x18002d3a6  cmp     cs:g_fProviderEnabled, ebx
0x18002d3ac  jz      short loc_18002D3CE
0x18002d3ae  mov     ecx, 400000h
0x18002d3b3  test    cs:g_ulTraceFlags, rcx
0x18002d3ba  jz      short loc_18002D3CE
0x18002d3bc  lea     rdx, aLdapModifyAttr; "ldap_modify attrlist connection 0x%x en"...
0x18002d3c3  mov     r9d, eax
0x18002d3c6  mov     r8, rsi
0x18002d3c9  call    LDAPClientPrint
0x18002d3ce  mov     ebp, 53h ; 'S'
0x18002d3d3  jmp     loc_18002D45E
0x18002d3d8  mov     r8b, [rsp+58h+arg_28]; unsigned __int8
0x18002d3e0  mov     rcx, rdi; this
0x18002d3e3  mov     rdx, [rsp+58h+arg_20]; struct ldapmodW **
0x18002d3eb  call    ?EncodeModifyList@@YAKPEAVCLdapBer@@QEAPEAUldapmodW@@E@Z; EncodeModifyList(CLdapBer *,ldapmodW * * const,uchar)
0x18002d3f0  mov     ebp, eax
0x18002d3f2  test    eax, eax
0x18002d3f4  jz      short loc_18002D428
0x18002d3f6  cmp     cs:g_fTracingOn, ebx
0x18002d3fc  jz      short loc_18002D45E
0x18002d3fe  cmp     cs:g_fProviderEnabled, ebx
0x18002d404  jz      short loc_18002D45E
0x18002d406  mov     ecx, 400000h
0x18002d40b  test    cs:g_ulTraceFlags, rcx
0x18002d412  jz      short loc_18002D45E
0x18002d414  mov     r9d, eax
0x18002d417  lea     rdx, aLdapModifyAttr; "ldap_modify attrlist connection 0x%x en"...
0x18002d41e  mov     r8, rsi
0x18002d421  call    LDAPClientPrint
0x18002d426  jmp     short loc_18002D45E
0x18002d428  mov     rcx, rdi; this
0x18002d42b  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x18002d430  mov     rcx, rdi; this
0x18002d433  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x18002d438  cmp     [rsi+3E8h], r15d
0x18002d43f  jz      short loc_18002D46D
0x18002d441  cmp     [r14+0C8h], rbx
0x18002d448  jz      short loc_18002D46D
0x18002d44a  mov     r8, rdi; struct CLdapBer *
0x18002d44d  mov     rdx, rsi; struct ldap_connection *
0x18002d450  mov     rcx, r14; struct ldap_request *
0x18002d453  call    ?InsertServerControls@@YAKPEAUldap_request@@PEAUldap_connection@@PEAVCLdapBer@@@Z; InsertServerControls(ldap_request *,ldap_connection *,CLdapBer *)
0x18002d458  mov     ebp, eax
0x18002d45a  test    eax, eax
0x18002d45c  jz      short loc_18002D46D
0x18002d45e  mov     rcx, rdi; this
0x18002d461  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x18002d466  mov     eax, ebp
0x18002d468  jmp     loc_18002D519
0x18002d46d  mov     rcx, rdi; this
0x18002d470  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x18002d475  lea     r15, [rsi+230h]
0x18002d47c  mov     rcx, r15; lpCriticalSection
0x18002d47f  call    cs:__imp_EnterCriticalSection
0x18002d486  nop     dword ptr [rax+rax+00h]
0x18002d48b  mov     rdx, rsi
0x18002d48e  mov     rcx, r14
0x18002d491  call    AddToPendingList
0x18002d496  xor     r8d, r8d; struct CLdapBer *
0x18002d499  mov     rdx, rdi; struct CLdapBer *
0x18002d49c  mov     rcx, rsi; struct ldap_connection *
0x18002d49f  call    ?LdapSend@@YAKPEAUldap_connection@@PEAVCLdapBer@@1@Z; LdapSend(ldap_connection *,CLdapBer *,CLdapBer *)
0x18002d4a4  mov     ebp, eax
0x18002d4a6  test    eax, eax
0x18002d4a8  jz      short loc_18002D4E7
0x18002d4aa  cmp     cs:g_fTracingOn, ebx
0x18002d4b0  jz      short loc_18002D4DA
0x18002d4b2  cmp     cs:g_fProviderEnabled, ebx
0x18002d4b8  jz      short loc_18002D4DA
0x18002d4ba  mov     ecx, 100000h
0x18002d4bf  test    cs:g_ulTraceFlags, rcx
0x18002d4c6  jz      short loc_18002D4DA
0x18002d4c8  mov     r9d, eax
0x18002d4cb  lea     rdx, aLdapModifyConn_0; "ldap_modify connection 0x%x send with e"...
0x18002d4d2  mov     r8, rsi
0x18002d4d5  call    LDAPClientPrint
0x18002d4da  mov     rdx, rsi
0x18002d4dd  mov     rcx, r14
0x18002d4e0  call    DecrementPendingList
0x18002d4e5  jmp     short loc_18002D4EB
0x18002d4e7  xchg    rdi, [r12]
0x18002d4eb  mov     rcx, r15; lpCriticalSection
0x18002d4ee  call    cs:__imp_LeaveCriticalSection
0x18002d4f5  nop     dword ptr [rax+rax+00h]
0x18002d4fa  test    rdi, rdi
0x18002d4fd  jz      loc_18002D466
0x18002d503  jmp     loc_18002D45E
0x18002d508  mov     ebx, 5Ah ; 'Z'
0x18002d50d  mov     edx, ebx
0x18002d50f  mov     rcx, rsi
0x18002d512  call    SetConnectionError
0x18002d517  mov     eax, ebx
0x18002d519  add     rsp, 20h
0x18002d51d  pop     r15
0x18002d51f  pop     r14
0x18002d521  pop     r12
0x18002d523  pop     rdi
0x18002d524  pop     rsi
0x18002d525  pop     rbp
0x18002d526  pop     rbx
0x18002d527  retn
```
