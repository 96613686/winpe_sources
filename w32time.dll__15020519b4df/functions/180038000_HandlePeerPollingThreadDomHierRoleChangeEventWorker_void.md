# HandlePeerPollingThreadDomHierRoleChangeEventWorker(void *)

- ea: `0x180038000`
- end: `0x180038295`
- name: `?HandlePeerPollingThreadDomHierRoleChangeEventWorker@@YAKPEAX@Z`
- size: `661`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x1800144f0`
- `0x180015020`
- `0x180017240`
- `0x180018138`
- `0x18001bbe0`
- `0x18001d9a0`
- `0x180034c08`
- `0x180038000`
- `0x18004124c`
- `0x180048b58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180038051`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180038243`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180038051`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180038243`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038180`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038269`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038180`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038269`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800380a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800380a1`

## string_xrefs

- `0x180038034`: `PeerPollingThread: DomHier Role Change\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall HandlePeerPollingThreadDomHierRoleChangeEventWorker(PVOID Parameter)
{
  char *v1; // r14
  char *v2; // r15
  int v3; // edi
  _NtpProvState *v4; // rcx
  volatile signed __int32 **i; // rbx
  volatile signed __int32 **v6; // rdi
  volatile signed __int32 ***v7; // rax
  volatile signed __int32 **v8; // r8
  volatile signed __int32 ***v9; // rax
  volatile signed __int32 **v10; // rax
  char v12; // [rsp+20h] [rbp-88h]
  __int64 v13; // [rsp+30h] [rbp-78h]
  volatile signed __int32 **v14; // [rsp+38h] [rbp-70h] BYREF
  volatile signed __int32 **v15; // [rsp+40h] [rbp-68h] BYREF
  volatile signed __int32 **v16; // [rsp+B8h] [rbp+10h] BYREF
  volatile signed __int32 **v17; // [rsp+C0h] [rbp+18h] BYREF
  volatile signed __int32 *v18; // [rsp+C8h] [rbp+20h] BYREF

  v1 = (char *)g_pnpstate + 408;
  v2 = (char *)g_pnpstate + 432;
  if ( (unsigned __int8)FileLogAllowEntry(103) )
    FileLogAdd(L"PeerPollingThread: DomHier Role Change\n");
  v12 = 0;
  v13 = _set_se_translator(SeTransFunc);
  v3 = TrapThreads(1);
  if ( v3 >= 0 )
  {
    UpdatePeerListTimes();
    v4 = g_pnpstate;
    if ( (*((_DWORD *)g_pnpstate + 36) & 2) != 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
      v12 = 1;
      for ( i = *(volatile signed __int32 ***)v1; ; ++i )
      {
        v6 = (volatile signed __int32 **)*((_QWORD *)v1 + 1);
        v16 = v6;
        if ( i == v6 )
          break;
        if ( *(_DWORD *)(*((_QWORD *)*i + 1) + 48LL) == 1 )
        {
          v17 = &v18;
          v10 = AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v18, i);
          v3 = Reachability_RemovePeer(v10, 0);
          if ( v3 < 0 )
            goto LABEL_15;
        }
        v16 = i;
      }
      HIDWORD(v16) = HIDWORD(v6);
      LODWORD(v16) = 1;
      v17 = v6;
      v17 = *(volatile signed __int32 ***)v1;
      v7 = std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
             &v14,
             v17,
             v6,
             1);
      std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(v1, &v17, *v7);
      v16 = (volatile signed __int32 **)*((_QWORD *)v2 + 1);
      LODWORD(v17) = 1;
      v16 = (volatile signed __int32 **)*((_QWORD *)v2 + 1);
      v8 = v16;
      v16 = *(volatile signed __int32 ***)v2;
      v9 = std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
             &v15,
             v16,
             v8,
             1);
      std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(v2, &v16, *v9);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
      v12 = 0;
      if ( (unsigned __int8)FileLogAllowEntry(52) )
        FileLogAdd(L"  DomainHierarchy: LSA role change notification. Redetecting.\n");
      v3 = AddNewPendingDomHierPeer(0);
      if ( v3 < 0 )
        goto LABEL_15;
      v4 = g_pnpstate;
    }
    *((_BYTE *)v4 + 481) = 0;
    *((_BYTE *)v4 + 257) = 0;
    *((_BYTE *)v4 + 482) = 0;
    _set_se_translator(v13);
    v3 = 0;
LABEL_15:
    if ( v12 )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
    TrapThreads(0);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180038000  push    rbx
0x180038002  push    rsi
0x180038003  push    rdi
0x180038004  push    r14
0x180038006  push    r15
0x180038008  sub     rsp, 80h
0x18003800f  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180038016  lea     r14, [rax+198h]
0x18003801d  lea     r15, [rax+1B0h]
0x180038024  mov     ecx, 67h ; 'g'
0x180038029  call    FileLogAllowEntry
0x18003802e  xor     esi, esi
0x180038030  test    al, al
0x180038032  jz      short loc_180038040
0x180038034  lea     rcx, aPeerpollingthr_2; "PeerPollingThread: DomHier Role Change"...
0x18003803b  call    FileLogAdd
0x180038040  mov     [rsp+0A8h+var_87], sil
0x180038045  mov     [rsp+0A8h+var_88], sil
0x18003804a  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x180038051  call    cs:__imp__set_se_translator
0x180038058  nop     dword ptr [rax+rax+00h]
0x18003805d  mov     [rsp+0A8h+var_78], rax
0x180038062  mov     ecx, 1; int
0x180038067  call    ?TrapThreads@@YAJH@Z; TrapThreads(int)
0x18003806c  mov     edi, eax
0x18003806e  mov     [rsp+0A8h+var_84], eax
0x180038072  test    eax, eax
0x180038074  jns     short loc_18003807B
0x180038076  jmp     loc_180038283
0x18003807b  mov     [rsp+0A8h+var_87], 1
0x180038080  call    ?UpdatePeerListTimes@@YAXXZ; UpdatePeerListTimes(void)
0x180038085  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18003808c  mov     eax, [rcx+90h]
0x180038092  test    al, 2
0x180038094  jz      loc_1800381C8
0x18003809a  add     rcx, 148h; lpCriticalSection
0x1800380a1  call    cs:__imp_EnterCriticalSection
0x1800380a8  nop     dword ptr [rax+rax+00h]
0x1800380ad  mov     [rsp+0A8h+var_88], 1
0x1800380b2  mov     rbx, [r14]
0x1800380b5  mov     [rsp+0A8h+var_80], rbx
0x1800380ba  mov     rdi, [r14+8]
0x1800380be  mov     [rsp+0A8h+arg_8], rdi
0x1800380c6  cmp     rbx, rdi
0x1800380c9  jnz     loc_1800381DF
0x1800380cf  mov     [rsp+0A8h+arg_8], rdi
0x1800380d7  mov     dword ptr [rsp+0A8h+arg_8], 1
0x1800380e2  mov     [rsp+0A8h+arg_10], rdi
0x1800380ea  mov     rdx, [r14]
0x1800380ed  mov     [rsp+0A8h+arg_10], rdx
0x1800380f5  mov     r9d, 1
0x1800380fb  mov     r8, rdi
0x1800380fe  lea     rcx, [rsp+0A8h+var_70]
0x180038103  call    ??$remove_if@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@std@@UIsPeerType@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@0@V10@V10@UIsPeerType@@@Z; std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType)
0x180038108  mov     r9, rdi
0x18003810b  mov     r8, [rax]
0x18003810e  lea     rdx, [rsp+0A8h+arg_10]
0x180038116  mov     rcx, r14
0x180038119  call    ?erase@?$vector@V?$AutoPtr@UNtpPeer@@@@V?$MyThrowingAllocator@V?$AutoPtr@UNtpPeer@@@@@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@2@0@Z; std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>)
0x18003811e  mov     rbx, [r15+8]
0x180038122  mov     [rsp+0A8h+arg_8], rbx
0x18003812a  mov     dword ptr [rsp+0A8h+arg_10], 1
0x180038135  mov     r8, [r15+8]
0x180038139  mov     [rsp+0A8h+arg_8], r8
0x180038141  mov     rdx, [r15]
0x180038144  mov     [rsp+0A8h+arg_8], rdx
0x18003814c  mov     r9d, 1
0x180038152  lea     rcx, [rsp+0A8h+var_68]
0x180038157  call    ??$remove_if@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@std@@UIsPeerType@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@0@V10@V10@UIsPeerType@@@Z; std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType)
0x18003815c  mov     r9, rbx
0x18003815f  mov     r8, [rax]
0x180038162  lea     rdx, [rsp+0A8h+arg_8]
0x18003816a  mov     rcx, r15
0x18003816d  call    ?erase@?$vector@V?$AutoPtr@UNtpPeer@@@@V?$MyThrowingAllocator@V?$AutoPtr@UNtpPeer@@@@@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@2@0@Z; std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>)
0x180038172  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180038179  add     rcx, 148h; lpCriticalSection
0x180038180  call    cs:__imp_LeaveCriticalSection
0x180038187  nop     dword ptr [rax+rax+00h]
0x18003818c  mov     [rsp+0A8h+var_88], sil
0x180038191  mov     ecx, 34h ; '4'
0x180038196  call    FileLogAllowEntry
0x18003819b  test    al, al
0x18003819d  jz      short loc_1800381AB
0x18003819f  lea     rcx, aDomainhierarch; "  DomainHierarchy: LSA role change noti"...
0x1800381a6  call    FileLogAdd
0x1800381ab  xor     ecx, ecx; unsigned __int16 *
0x1800381ad  call    ?AddNewPendingDomHierPeer@@YAJPEBG@Z; AddNewPendingDomHierPeer(ushort const *)
0x1800381b2  mov     edi, eax
0x1800381b4  mov     [rsp+0A8h+var_84], eax
0x1800381b8  test    eax, eax
0x1800381ba  jns     short loc_1800381C1
0x1800381bc  jmp     loc_180038254
0x1800381c1  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800381c8  mov     [rcx+1E1h], sil
0x1800381cf  mov     [rcx+101h], sil
0x1800381d6  mov     [rcx+1E2h], sil
0x1800381dd  jmp     short loc_18003823E
0x1800381df  mov     rax, [rbx]
0x1800381e2  mov     rcx, [rax+8]
0x1800381e6  cmp     dword ptr [rcx+30h], 1
0x1800381ea  jnz     short loc_180038223
0x1800381ec  lea     rax, [rsp+0A8h+arg_18]
0x1800381f4  mov     [rsp+0A8h+arg_10], rax
0x1800381fc  mov     rdx, rbx
0x1800381ff  lea     rcx, [rsp+0A8h+arg_18]
0x180038207  call    ??0?$AutoPtr@UNtpPeer@@@@QEAA@AEBV0@@Z; AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(AutoPtr<NtpPeer> const &)
0x18003820c  nop
0x18003820d  xor     edx, edx
0x18003820f  mov     rcx, rax
0x180038212  call    ?Reachability_RemovePeer@@YAJV?$AutoPtr@UNtpPeer@@@@PEA_N_N@Z; Reachability_RemovePeer(AutoPtr<NtpPeer>,bool *,bool)
0x180038217  mov     edi, eax
0x180038219  mov     [rsp+0A8h+var_84], eax
0x18003821d  test    eax, eax
0x18003821f  jns     short loc_180038223
0x180038221  jmp     short loc_180038254
0x180038223  mov     [rsp+0A8h+arg_8], rbx
0x18003822b  add     rbx, 8
0x18003822f  jmp     loc_1800380B5
0x180038234  jmp     short loc_180038238
0x180038236  jmp     short $+2
0x180038238  xor     esi, esi
0x18003823a  mov     edi, [rsp+0A8h+var_84]
0x18003823e  mov     rcx, [rsp+0A8h+var_78]
0x180038243  call    cs:__imp__set_se_translator
0x18003824a  nop     dword ptr [rax+rax+00h]
0x18003824f  test    edi, edi
0x180038251  cmovns  edi, esi
0x180038254  cmp     [rsp+0A8h+var_88], sil
0x180038259  jz      short loc_180038275
0x18003825b  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180038262  add     rcx, 148h; lpCriticalSection
0x180038269  call    cs:__imp_LeaveCriticalSection
0x180038270  nop     dword ptr [rax+rax+00h]
0x180038275  cmp     [rsp+0A8h+var_87], 1
0x18003827a  jnz     short loc_180038283
0x18003827c  xor     ecx, ecx; int
0x18003827e  call    ?TrapThreads@@YAJH@Z; TrapThreads(int)
0x180038283  mov     eax, edi
0x180038285  add     rsp, 80h
0x18003828c  pop     r15
0x18003828e  pop     r14
0x180038290  pop     rdi
0x180038291  pop     rsi
0x180038292  pop     rbx
0x180038293  retn
```
