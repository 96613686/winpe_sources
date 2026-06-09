# SASetNSAccountInformation

- ea: `0x180016620`
- end: `0x180016872`
- name: `SASetNSAccountInformation`
- size: `594`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180004138`
- `0x180004ff0`
- `0x180005354`
- `0x1800053bc`
- `0x1800053e8`
- `0x180005650`
- `0x180005c10`
- `0x180005efc`
- `0x180007370`
- `0x180007988`
- `0x180016620`
- `0x18002cf68`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18001669a`
- `RPCRT4!RpcImpersonateClient` at `0x18001664f`
- `RPCRT4!RpcImpersonateClient` at `0x18001664f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall SASetNSAccountInformation(__int64 a1, wchar_t *a2, unsigned __int16 *a3)
{
  RPC_STATUS v6; // eax
  EventManager *v7; // rcx
  int v8; // ebx
  unsigned __int64 v9; // rax
  const unsigned __int16 *v10; // rdx
  int v11; // ebx
  _QWORD v12[3]; // [rsp+30h] [rbp-58h] BYREF
  _QWORD v13[8]; // [rsp+48h] [rbp-40h] BYREF
  unsigned int v14; // [rsp+A8h] [rbp+20h]

  if ( !CompatibilityAdapter::GetAdapter() )
    return 2147500037LL;
  v6 = RpcImpersonateClient(0);
  v8 = v6;
  if ( v6 )
  {
    EventManager::EvtReport(v7, &IMPERSONATION_FAILURE, L"SASetNSAccountInformation", v6);
    if ( (v8 & 0x1FFF0000) == 0 && v8 > 0 )
      return (unsigned __int16)v8 | 0x80070000;
    return (unsigned int)v8;
  }
  else
  {
    LOBYTE(v13[0]) = 0;
    v13[1] = RpcRevertToSelf;
    if ( !(unsigned int)IsThreadCallerAnAdmin(0) )
    {
      wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v13);
      return 2147942405LL;
    }
    wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v13);
    if ( a3 )
    {
      v9 = -1;
      do
        ++v9;
      while ( a3[v9] );
      if ( v9 > 0x7F )
        return 2147942413LL;
    }
    if ( !a2 || !*a2 )
      a2 = (wchar_t *)L"System";
    v12[1] = 0;
    v12[2] = 0;
    v13[0] = 0;
    if ( User::IsLocalSystem(a2) )
    {
      a3 = 0;
    }
    else if ( !a3 )
    {
      operator delete(0);
      operator delete(0);
      operator delete(0);
      return 2147942487LL;
    }
    v12[0] = 0;
    v11 = User::FromUsername((struct User *)v12, a2);
    if ( v11 < 0 )
      goto LABEL_23;
    if ( *(_DWORD *)(v12[0] + 40LL) != 1 && !User::IsLocalSystem((User *)v12) )
    {
      wmi::AutoRef<User::UserEntry>::Release(v12);
      operator delete(0);
      operator delete(0);
      operator delete(0);
      return 2147942487LL;
    }
    if ( a3 )
    {
      v11 = CredStore::ValidateNtCredential((const struct User *)v12, a3);
      if ( v11 < 0 )
      {
LABEL_23:
        wmi::AutoRef<User::UserEntry>::Release(v12);
        operator delete(0);
        operator delete(0);
        operator delete(0);
        return (unsigned int)v11;
      }
    }
    v14 = CredStore::StoreAlias((CredStore *)CredStore::g_pCommonStore, v10, (const struct User *)v12, a3);
    wmi::AutoRef<User::UserEntry>::Release(v12);
    operator delete(0);
    operator delete(0);
    operator delete(0);
    return v14;
  }
}

```

## disassembly

```asm
0x180016620  mov     rax, rsp
0x180016623  push    rbx
0x180016624  push    rsi
0x180016625  push    rdi
0x180016626  push    r14
0x180016628  sub     rsp, 68h
0x18001662c  mov     rdi, r8
0x18001662f  mov     rsi, rdx
0x180016632  xor     r14d, r14d
0x180016635  mov     [rax+20h], r14d
0x180016639  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x18001663e  test    rax, rax
0x180016641  jnz     short loc_18001664D
0x180016643  mov     eax, 80004005h
0x180016648  jmp     loc_180016867
0x18001664d  xor     ecx, ecx; BindingHandle
0x18001664f  call    cs:__imp_RpcImpersonateClient
0x180016656  nop     dword ptr [rax+rax+00h]
0x18001665b  mov     ebx, eax
0x18001665d  test    eax, eax
0x18001665f  jz      short loc_18001669A
0x180016661  mov     r9d, eax; unsigned int
0x180016664  lea     r8, aSasetnsaccount; "SASetNSAccountInformation"
0x18001666b  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x180016672  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180016677  test    ebx, 1FFF0000h
0x18001667d  jnz     short loc_18001668C
0x18001667f  test    ebx, ebx
0x180016681  jle     short loc_18001668C
0x180016683  movzx   ebx, bx
0x180016686  or      ebx, 80070000h
0x18001668c  mov     [rsp+88h+arg_18], ebx
0x180016693  mov     eax, ebx
0x180016695  jmp     loc_180016867
0x18001669a  mov     rax, cs:__imp_RpcRevertToSelf
0x1800166a1  mov     byte ptr [rsp+88h+var_40], r14b
0x1800166a6  mov     [rsp+88h+var_38], rax
0x1800166ab  xor     ecx, ecx; void *
0x1800166ad  call    ?IsThreadCallerAnAdmin@@YAHPEAX@Z; IsThreadCallerAnAdmin(void *)
0x1800166b2  lea     rcx, [rsp+88h+var_40]
0x1800166b7  test    eax, eax
0x1800166b9  jnz     short loc_1800166CA
0x1800166bb  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x1800166c0  mov     eax, 80070005h
0x1800166c5  jmp     loc_180016867
0x1800166ca  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x1800166cf  test    rdi, rdi
0x1800166d2  jz      short loc_1800166F2
0x1800166d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800166d8  inc     rax
0x1800166db  cmp     [rdi+rax*2], r14w
0x1800166e0  jnz     short loc_1800166D8
0x1800166e2  cmp     rax, 7Fh
0x1800166e6  jbe     short loc_1800166F2
0x1800166e8  mov     eax, 8007000Dh
0x1800166ed  jmp     loc_180016867
0x1800166f2  test    rsi, rsi
0x1800166f5  jz      short loc_1800166FD
0x1800166f7  cmp     [rsi], r14w
0x1800166fb  jnz     short loc_180016704
0x1800166fd  lea     rsi, aSystem; "System"
0x180016704  mov     [rsp+88h+var_50], r14
0x180016709  mov     [rsp+88h+var_48], r14
0x18001670e  mov     [rsp+88h+var_40], r14
0x180016713  mov     rcx, rsi; String1
0x180016716  call    ?IsLocalSystem@User@@SA_NPEBG@Z; User::IsLocalSystem(ushort const *)
0x18001671b  test    al, al
0x18001671d  jz      short loc_180016724
0x18001671f  mov     rdi, r14
0x180016722  jmp     short loc_18001674A
0x180016724  test    rdi, rdi
0x180016727  jnz     short loc_18001674A
0x180016729  xor     ecx, ecx; Block
0x18001672b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016730  nop
0x180016731  xor     ecx, ecx; Block
0x180016733  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016738  nop
0x180016739  xor     ecx, ecx; Block
0x18001673b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016740  mov     eax, 80070057h
0x180016745  jmp     loc_180016867
0x18001674a  mov     [rsp+88h+var_58], r14
0x18001674f  mov     rdx, rsi; lpAccountName
0x180016752  lea     rcx, [rsp+88h+var_58]; this
0x180016757  call    ?FromUsername@User@@SAJAEAV1@PEBG@Z; User::FromUsername(User &,ushort const *)
0x18001675c  mov     ebx, eax
0x18001675e  mov     [rsp+88h+arg_18], eax
0x180016765  test    eax, eax
0x180016767  jns     short loc_180016792
0x180016769  lea     rcx, [rsp+88h+var_58]
0x18001676e  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180016773  nop
0x180016774  xor     ecx, ecx; Block
0x180016776  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001677b  nop
0x18001677c  xor     ecx, ecx; Block
0x18001677e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016783  nop
0x180016784  xor     ecx, ecx; Block
0x180016786  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001678b  mov     eax, ebx
0x18001678d  jmp     loc_180016867
0x180016792  mov     rax, [rsp+88h+var_58]
0x180016797  cmp     dword ptr [rax+28h], 1
0x18001679b  jz      short loc_1800167D7
0x18001679d  lea     rcx, [rsp+88h+var_58]; this
0x1800167a2  call    ?IsLocalSystem@User@@QEBA_NXZ; User::IsLocalSystem(void)
0x1800167a7  test    al, al
0x1800167a9  jnz     short loc_1800167D7
0x1800167ab  lea     rcx, [rsp+88h+var_58]
0x1800167b0  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x1800167b5  nop
0x1800167b6  xor     ecx, ecx; Block
0x1800167b8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800167bd  nop
0x1800167be  xor     ecx, ecx; Block
0x1800167c0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800167c5  nop
0x1800167c6  xor     ecx, ecx; Block
0x1800167c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800167cd  mov     eax, 80070057h
0x1800167d2  jmp     loc_180016867
0x1800167d7  test    rdi, rdi
0x1800167da  jz      short loc_18001681C
0x1800167dc  mov     rdx, rdi; unsigned __int16 *
0x1800167df  lea     rcx, [rsp+88h+var_58]; struct User *
0x1800167e4  call    ?ValidateNtCredential@CredStore@@SAJAEBVUser@@PEBG@Z; CredStore::ValidateNtCredential(User const &,ushort const *)
0x1800167e9  mov     ebx, eax
0x1800167eb  mov     [rsp+88h+arg_18], eax
0x1800167f2  test    eax, eax
0x1800167f4  jns     short loc_18001681C
0x1800167f6  lea     rcx, [rsp+88h+var_58]
0x1800167fb  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180016800  nop
0x180016801  xor     ecx, ecx; Block
0x180016803  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016808  nop
0x180016809  xor     ecx, ecx; Block
0x18001680b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016810  nop
0x180016811  xor     ecx, ecx; Block
0x180016813  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016818  mov     eax, ebx
0x18001681a  jmp     short loc_180016867
0x18001681c  mov     r9, rdi; unsigned __int16 *
0x18001681f  lea     r8, [rsp+88h+var_58]; struct User *
0x180016824  mov     rcx, cs:?g_pCommonStore@CredStore@@0PEAV1@EA; this
0x18001682b  call    ?StoreAlias@CredStore@@QEAAJPEBGAEBVUser@@PEAG@Z; CredStore::StoreAlias(ushort const *,User const &,ushort *)
0x180016830  mov     ebx, eax
0x180016832  mov     [rsp+88h+arg_18], eax
0x180016839  lea     rcx, [rsp+88h+var_58]
0x18001683e  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180016843  nop
0x180016844  xor     ecx, ecx; Block
0x180016846  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001684b  nop
0x18001684c  xor     ecx, ecx; Block
0x18001684e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016853  nop
0x180016854  xor     ecx, ecx; Block
0x180016856  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001685b  nop
0x18001685c  jmp     short loc_180016865
0x18001685e  mov     ebx, [rsp+88h+arg_18]
0x180016865  mov     eax, ebx
0x180016867  add     rsp, 68h
0x18001686b  pop     r14
0x18001686d  pop     rdi
0x18001686e  pop     rsi
0x18001686f  pop     rbx
0x180016870  retn
```
