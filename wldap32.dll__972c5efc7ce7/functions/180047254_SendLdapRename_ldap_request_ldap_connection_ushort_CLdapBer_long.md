# SendLdapRename(ldap_request *,ldap_connection *,ushort *,CLdapBer * *,long)

- ea: `0x180047254`
- end: `0x1800475c1`
- name: `?SendLdapRename@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGPEAPEAVCLdapBer@@J@Z`
- size: `877`
- prototype: `unsigned int __usercall@<eax>(struct ldap_request *@<rcx>, struct ldap_connection *@<rdx>, unsigned __int16 *@<r8>, struct CLdapBer **@<r9>, int)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x18002cf6c`
- `0x180046f48`

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
- `0x18002ba24`
- `0x18002dbac`
- `0x180047254`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047514`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047514`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047584`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047584`

## string_xrefs

- `0x18004730e`: `ldap_modrdn startWrite connection 0x%x encoding error of 0x%x.\n`
- `0x180047562`: `SendLdapRename connection 0x%x send with error of 0x%x.\n`

## pseudocode

```c
__int64 __fastcall SendLdapRename(
        struct ldap_request *a1,
        struct ldap_connection *a2,
        unsigned __int16 *a3,
        struct CLdapBer **a4,
        int a5)
{
  const unsigned __int16 *v5; // r13
  const unsigned __int16 *v7; // rdi
  int v9; // r12d
  __int64 v12; // rbx
  int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // edx
  unsigned int inserted; // edi
  int v17; // edx
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v24; // eax

  v5 = (const unsigned __int16 *)*((_QWORD *)a1 + 29);
  v7 = (const unsigned __int16 *)*((_QWORD *)a1 + 30);
  v9 = *((_DWORD *)a1 + 62);
  v12 = ldapMalloc(872, 1816347212);
  if ( v12 )
  {
    v13 = *((_DWORD *)a2 + 250) - 2;
    *(_QWORD *)v12 = 0;
    *(_DWORD *)(v12 + 8) = 0;
    *(_QWORD *)(v12 + 16) = 0;
    *(_QWORD *)(v12 + 836) = 0;
    *(_QWORD *)(v12 + 24) = 0;
    *(_BYTE *)(v12 + 856) = 0;
    *(_DWORD *)(v12 + 864) = 0;
    *(_DWORD *)(v12 + 860) = v13 != 0 ? 0xFDE9 : 0;
    *(_DWORD *)(v12 + 32) = 0;
    v14 = CLdapBer::HrStartWriteSequence((CLdapBer *)v12, 0x30u);
    if ( v14 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_modrdn startWrite connection 0x%x encoding error of 0x%x.\n", a2, v14);
    }
    else
    {
      v17 = a5;
      if ( !a5 )
        v17 = *((_DWORD *)a1 + 27);
      v18 = CLdapBer::HrAddValue((CLdapBer *)v12, v17, 2u);
      if ( v18 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
          LDAPClientPrint(0x400000, "ldap_modrdn MsgNo connection 0x%x encoding error of 0x%x.\n", a2, v18);
      }
      else
      {
        v19 = CLdapBer::HrStartWriteSequence((CLdapBer *)v12, 0x6Cu);
        if ( v19 )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
            LDAPClientPrint(0x400000, "ldap_modrdn cmd connection 0x%x encoding error of 0x%x.\n", a2, v19);
        }
        else
        {
          v20 = CLdapBer::HrAddValue((CLdapBer *)v12, a3, 4u);
          if ( v20 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
              LDAPClientPrint(0x400000, "ldap_modrdn DN connection 0x%x encoding error of 0x%x.\n", a2, v20);
          }
          else
          {
            v21 = CLdapBer::HrAddValue((CLdapBer *)v12, v5, 4u);
            if ( !v21 )
            {
              v22 = CLdapBer::HrAddValue((CLdapBer *)v12, v9, 1u);
              if ( v22 )
              {
                if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
                  LDAPClientPrint(0x400000, "ldap_modrdn delOldRdn connection 0x%x encoding error of 0x%x.\n", a2, v22);
                goto LABEL_7;
              }
              if ( *((_DWORD *)a2 + 250) == 2 || !v7 || (v21 = CLdapBer::HrAddValue((CLdapBer *)v12, v7, 0x80u)) == 0 )
              {
                CLdapBer::HrEndWriteSequence((CLdapBer *)v12);
                if ( *((_DWORD *)a2 + 250) == 2
                  || !*((_QWORD *)a1 + 25)
                  || (inserted = InsertServerControls(a1, a2, (struct CLdapBer *)v12)) == 0 )
                {
                  CLdapBer::HrEndWriteSequence((CLdapBer *)v12);
                  EnterCriticalSection((LPCRITICAL_SECTION)a2 + 14);
                  AddToPendingList((__int64)a1, (__int64)a2);
                  v24 = LdapSend(a2, (struct CLdapBer *)v12, 0);
                  inserted = v24;
                  if ( v24 )
                  {
                    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
                      LDAPClientPrint(
                        0x100000,
                        "SendLdapRename connection 0x%x send with error of 0x%x.\n",
                        (_DWORD)a2,
                        v24);
                    DecrementPendingList(a1, a2);
                  }
                  else
                  {
                    v12 = _InterlockedExchange64((volatile __int64 *)a4, v12);
                  }
                  LeaveCriticalSection((LPCRITICAL_SECTION)a2 + 14);
                  if ( !v12 )
                    return inserted;
                }
                goto LABEL_41;
              }
            }
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
              LDAPClientPrint(0x400000, "ldap_modrdn newDN connection 0x%x encoding error of 0x%x.\n", a2, v21);
          }
        }
      }
    }
LABEL_7:
    inserted = 83;
LABEL_41:
    CLdapBer::`scalar deleting destructor'((CLdapBer *)v12, v15);
    return inserted;
  }
  SetConnectionError(a2, 90);
  return 90;
}

```

## disassembly

```asm
0x180047254  push    rbx
0x180047256  push    rbp
0x180047257  push    rsi
0x180047258  push    rdi
0x180047259  push    r12
0x18004725b  push    r13
0x18004725d  push    r14
0x18004725f  push    r15
0x180047261  sub     rsp, 28h
0x180047265  mov     r13, [rcx+0E8h]
0x18004726c  mov     rsi, rdx
0x18004726f  mov     rdi, [rcx+0F0h]
0x180047276  mov     rbp, rcx
0x180047279  mov     r12d, [rcx+0F8h]
0x180047280  mov     edx, 6C43424Ch
0x180047285  mov     ecx, 368h
0x18004728a  mov     r15, r9
0x18004728d  mov     r14, r8
0x180047290  call    ldapMalloc
0x180047295  xor     ecx, ecx
0x180047297  mov     rbx, rax
0x18004729a  test    rax, rax
0x18004729d  jz      loc_18004759E
0x1800472a3  mov     eax, [rsi+3E8h]
0x1800472a9  lea     edx, [rcx+30h]; unsigned int
0x1800472ac  sub     eax, 2
0x1800472af  mov     [rbx], rcx
0x1800472b2  neg     eax
0x1800472b4  mov     [rbx+8], ecx
0x1800472b7  mov     [rbx+10h], rcx
0x1800472bb  mov     [rbx+344h], rcx
0x1800472c2  sbb     eax, eax
0x1800472c4  mov     [rbx+18h], rcx
0x1800472c8  and     eax, 0FDE9h
0x1800472cd  mov     [rbx+358h], cl
0x1800472d3  mov     [rbx+360h], ecx
0x1800472d9  mov     [rbx+35Ch], eax
0x1800472df  mov     [rbx+20h], ecx
0x1800472e2  mov     rcx, rbx; this
0x1800472e5  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x1800472ea  test    eax, eax
0x1800472ec  jz      short loc_18004732A
0x1800472ee  cmp     cs:g_fTracingOn, 0
0x1800472f5  jz      short loc_180047320
0x1800472f7  cmp     cs:g_fProviderEnabled, 0
0x1800472fe  jz      short loc_180047320
0x180047300  mov     ecx, 400000h
0x180047305  test    cs:g_ulTraceFlags, rcx
0x18004730c  jz      short loc_180047320
0x18004730e  lea     rdx, aLdapModrdnStar; "ldap_modrdn startWrite connection 0x%x "...
0x180047315  mov     r8, rsi
0x180047318  mov     r9d, eax
0x18004731b  call    LDAPClientPrint
0x180047320  mov     edi, 53h ; 'S'
0x180047325  jmp     loc_1800474F3
0x18004732a  mov     edx, [rsp+68h+arg_20]
0x180047331  test    edx, edx
0x180047333  jnz     short loc_180047338
0x180047335  mov     edx, [rbp+6Ch]; int
0x180047338  mov     r8d, 2; unsigned int
0x18004733e  mov     rcx, rbx; this
0x180047341  call    ?HrAddValue@CLdapBer@@QEAAKJK@Z; CLdapBer::HrAddValue(long,ulong)
0x180047346  test    eax, eax
0x180047348  jz      short loc_180047373
0x18004734a  cmp     cs:g_fTracingOn, 0
0x180047351  jz      short loc_180047320
0x180047353  cmp     cs:g_fProviderEnabled, 0
0x18004735a  jz      short loc_180047320
0x18004735c  mov     ecx, 400000h
0x180047361  test    cs:g_ulTraceFlags, rcx
0x180047368  jz      short loc_180047320
0x18004736a  lea     rdx, aLdapModrdnMsgn; "ldap_modrdn MsgNo connection 0x%x encod"...
0x180047371  jmp     short loc_180047315
0x180047373  mov     edx, 6Ch ; 'l'; unsigned int
0x180047378  mov     rcx, rbx; this
0x18004737b  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x180047380  test    eax, eax
0x180047382  jz      short loc_1800473B4
0x180047384  cmp     cs:g_fTracingOn, 0
0x18004738b  jz      short loc_180047320
0x18004738d  cmp     cs:g_fProviderEnabled, 0
0x180047394  jz      short loc_180047320
0x180047396  mov     ecx, 400000h
0x18004739b  test    cs:g_ulTraceFlags, rcx
0x1800473a2  jz      loc_180047320
0x1800473a8  lea     rdx, aLdapModrdnCmdC; "ldap_modrdn cmd connection 0x%x encodin"...
0x1800473af  jmp     loc_180047315
0x1800473b4  mov     r8d, 4; unsigned int
0x1800473ba  mov     rdx, r14; unsigned __int16 *
0x1800473bd  mov     rcx, rbx; this
0x1800473c0  call    ?HrAddValue@CLdapBer@@QEAAKPEBGK@Z; CLdapBer::HrAddValue(ushort const *,ulong)
0x1800473c5  test    eax, eax
0x1800473c7  jz      short loc_180047401
0x1800473c9  cmp     cs:g_fTracingOn, 0
0x1800473d0  jz      loc_180047320
0x1800473d6  cmp     cs:g_fProviderEnabled, 0
0x1800473dd  jz      loc_180047320
0x1800473e3  mov     ecx, 400000h
0x1800473e8  test    cs:g_ulTraceFlags, rcx
0x1800473ef  jz      loc_180047320
0x1800473f5  lea     rdx, aLdapModrdnDnCo; "ldap_modrdn DN connection 0x%x encoding"...
0x1800473fc  jmp     loc_180047315
0x180047401  mov     r8d, 4; unsigned int
0x180047407  mov     rdx, r13; unsigned __int16 *
0x18004740a  mov     rcx, rbx; this
0x18004740d  call    ?HrAddValue@CLdapBer@@QEAAKPEBGK@Z; CLdapBer::HrAddValue(ushort const *,ulong)
0x180047412  xor     r13d, r13d
0x180047415  test    eax, eax
0x180047417  jz      short loc_180047451
0x180047419  cmp     cs:g_fTracingOn, r13d
0x180047420  jz      loc_180047320
0x180047426  cmp     cs:g_fProviderEnabled, r13d
0x18004742d  jz      loc_180047320
0x180047433  mov     ecx, 400000h
0x180047438  test    cs:g_ulTraceFlags, rcx
0x18004743f  jz      loc_180047320
0x180047445  lea     rdx, aLdapModrdnNewd; "ldap_modrdn newDN connection 0x%x encod"...
0x18004744c  jmp     loc_180047315
0x180047451  mov     dl, r12b; unsigned __int8
0x180047454  mov     r8d, 1; unsigned int
0x18004745a  mov     rcx, rbx; this
0x18004745d  call    ?HrAddValue@CLdapBer@@QEAAKEK@Z; CLdapBer::HrAddValue(uchar,ulong)
0x180047462  test    eax, eax
0x180047464  jz      short loc_18004749E
0x180047466  cmp     cs:g_fTracingOn, r13d
0x18004746d  jz      loc_180047320
0x180047473  cmp     cs:g_fProviderEnabled, r13d
0x18004747a  jz      loc_180047320
0x180047480  mov     ecx, 400000h
0x180047485  test    cs:g_ulTraceFlags, rcx
0x18004748c  jz      loc_180047320
0x180047492  lea     rdx, aLdapModrdnDelo; "ldap_modrdn delOldRdn connection 0x%x e"...
0x180047499  jmp     loc_180047315
0x18004749e  cmp     dword ptr [rsi+3E8h], 2
0x1800474a5  jz      short loc_1800474C5
0x1800474a7  test    rdi, rdi
0x1800474aa  jz      short loc_1800474C5
0x1800474ac  mov     r8d, 80h; unsigned int
0x1800474b2  mov     rdx, rdi; unsigned __int16 *
0x1800474b5  mov     rcx, rbx; this
0x1800474b8  call    ?HrAddValue@CLdapBer@@QEAAKPEBGK@Z; CLdapBer::HrAddValue(ushort const *,ulong)
0x1800474bd  test    eax, eax
0x1800474bf  jnz     loc_180047419
0x1800474c5  mov     rcx, rbx; this
0x1800474c8  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x1800474cd  cmp     dword ptr [rsi+3E8h], 2
0x1800474d4  jz      short loc_180047502
0x1800474d6  cmp     [rbp+0C8h], r13
0x1800474dd  jz      short loc_180047502
0x1800474df  mov     r8, rbx; struct CLdapBer *
0x1800474e2  mov     rdx, rsi; struct ldap_connection *
0x1800474e5  mov     rcx, rbp; struct ldap_request *
0x1800474e8  call    ?InsertServerControls@@YAKPEAUldap_request@@PEAUldap_connection@@PEAVCLdapBer@@@Z; InsertServerControls(ldap_request *,ldap_connection *,CLdapBer *)
0x1800474ed  mov     edi, eax
0x1800474ef  test    eax, eax
0x1800474f1  jz      short loc_180047502
0x1800474f3  mov     rcx, rbx; this
0x1800474f6  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x1800474fb  mov     eax, edi
0x1800474fd  jmp     loc_1800475AF
0x180047502  mov     rcx, rbx; this
0x180047505  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x18004750a  lea     r14, [rsi+230h]
0x180047511  mov     rcx, r14; lpCriticalSection
0x180047514  call    cs:__imp_EnterCriticalSection
0x18004751b  nop     dword ptr [rax+rax+00h]
0x180047520  mov     rdx, rsi
0x180047523  mov     rcx, rbp
0x180047526  call    AddToPendingList
0x18004752b  xor     r8d, r8d; struct CLdapBer *
0x18004752e  mov     rdx, rbx; struct CLdapBer *
0x180047531  mov     rcx, rsi; struct ldap_connection *
0x180047534  call    ?LdapSend@@YAKPEAUldap_connection@@PEAVCLdapBer@@1@Z; LdapSend(ldap_connection *,CLdapBer *,CLdapBer *)
0x180047539  mov     edi, eax
0x18004753b  test    eax, eax
0x18004753d  jz      short loc_18004757E
0x18004753f  cmp     cs:g_fTracingOn, r13d
0x180047546  jz      short loc_180047571
0x180047548  cmp     cs:g_fProviderEnabled, r13d
0x18004754f  jz      short loc_180047571
0x180047551  mov     ecx, 100000h
0x180047556  test    cs:g_ulTraceFlags, rcx
0x18004755d  jz      short loc_180047571
0x18004755f  mov     r9d, eax
0x180047562  lea     rdx, aSendldaprename; "SendLdapRename connection 0x%x send wit"...
0x180047569  mov     r8, rsi
0x18004756c  call    LDAPClientPrint
0x180047571  mov     rdx, rsi
0x180047574  mov     rcx, rbp
0x180047577  call    DecrementPendingList
0x18004757c  jmp     short loc_180047581
0x18004757e  xchg    rbx, [r15]
0x180047581  mov     rcx, r14; lpCriticalSection
0x180047584  call    cs:__imp_LeaveCriticalSection
0x18004758b  nop     dword ptr [rax+rax+00h]
0x180047590  test    rbx, rbx
0x180047593  jz      loc_1800474FB
0x180047599  jmp     loc_1800474F3
0x18004759e  mov     ebx, 5Ah ; 'Z'
0x1800475a3  mov     rcx, rsi
0x1800475a6  mov     edx, ebx
0x1800475a8  call    SetConnectionError
0x1800475ad  mov     eax, ebx
0x1800475af  add     rsp, 28h
0x1800475b3  pop     r15
0x1800475b5  pop     r14
0x1800475b7  pop     r13
0x1800475b9  pop     r12
0x1800475bb  pop     rdi
0x1800475bc  pop     rsi
0x1800475bd  pop     rbp
0x1800475be  pop     rbx
0x1800475bf  retn
```
