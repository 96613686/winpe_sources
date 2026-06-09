# SASetNSAccountInformation

- ea: `0x1800157e0`
- end: `0x180015a2c`
- name: `SASetNSAccountInformation`
- size: `588`
- prototype: `__int64 __fastcall(__int64, wchar_t *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180003f64`
- `0x180004d84`
- `0x1800050a8`
- `0x1800050fc`
- `0x18000518c`
- `0x1800053b8`
- `0x1800058f0`
- `0x180005b98`
- `0x180006f08`
- `0x1800074c8`
- `0x1800157e0`
- `0x18002b330`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180015854`
- `RPCRT4!RpcImpersonateClient` at `0x18001580f`
- `RPCRT4!RpcImpersonateClient` at `0x18001580f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SASetNSAccountInformation(__int64 a1, wchar_t *a2, unsigned __int16 *a3)
{
  RPC_STATUS v6; // eax
  EventManager *v7; // rcx
  int v8; // ebx
  unsigned __int64 v9; // rax
  const unsigned __int16 *v10; // rdx
  int v11; // ebx
  void *v12; // [rsp+20h] [rbp-68h]
  const struct _GUID *v13; // [rsp+28h] [rbp-60h]
  _QWORD v14[3]; // [rsp+30h] [rbp-58h] BYREF
  _QWORD v15[8]; // [rsp+48h] [rbp-40h] BYREF
  unsigned int v16; // [rsp+A8h] [rbp+20h]

  if ( !CompatibilityAdapter::GetAdapter() )
    return 2147500037LL;
  v6 = RpcImpersonateClient(0);
  v8 = v6;
  if ( v6 )
  {
    EventManager::EvtReport(v7, &IMPERSONATION_FAILURE, L"SASetNSAccountInformation", v6, v12, v13);
    if ( (v8 & 0x1FFF0000) == 0 && v8 > 0 )
      return (unsigned __int16)v8 | 0x80070000;
    return (unsigned int)v8;
  }
  else
  {
    LOBYTE(v15[0]) = 0;
    v15[1] = RpcRevertToSelf;
    if ( !(unsigned int)IsThreadCallerAnAdmin(0) )
    {
      wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v15);
      return 2147942405LL;
    }
    wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v15);
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
    v14[1] = 0;
    v14[2] = 0;
    v15[0] = 0;
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
    v14[0] = 0;
    v11 = User::FromUsername((struct User *)v14, a2);
    if ( v11 < 0 )
      goto LABEL_23;
    if ( *(_DWORD *)(v14[0] + 40LL) != 1 && !User::IsLocalSystem((User *)v14) )
    {
      wmi::AutoRef<User::UserEntry>::Release(v14);
      operator delete(0);
      operator delete(0);
      operator delete(0);
      return 2147942487LL;
    }
    if ( a3 )
    {
      v11 = CredStore::ValidateNtCredential((const struct User *)v14, a3);
      if ( v11 < 0 )
      {
LABEL_23:
        wmi::AutoRef<User::UserEntry>::Release(v14);
        operator delete(0);
        operator delete(0);
        operator delete(0);
        return (unsigned int)v11;
      }
    }
    v16 = CredStore::StoreAlias((CredStore *)CredStore::g_pCommonStore, v10, (const struct User *)v14, a3);
    wmi::AutoRef<User::UserEntry>::Release(v14);
    operator delete(0);
    operator delete(0);
    operator delete(0);
    return v16;
  }
}

```

## disassembly

```asm
0x1800157e0  mov     rax, rsp
0x1800157e3  push    rbx
0x1800157e4  push    rsi
0x1800157e5  push    rdi
0x1800157e6  push    r14
0x1800157e8  sub     rsp, 68h
0x1800157ec  mov     rdi, r8
0x1800157ef  mov     rsi, rdx
0x1800157f2  xor     r14d, r14d
0x1800157f5  mov     [rax+20h], r14d
0x1800157f9  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x1800157fe  test    rax, rax
0x180015801  jnz     short loc_18001580D
0x180015803  mov     eax, 80004005h
0x180015808  jmp     loc_180015A21
0x18001580d  xor     ecx, ecx; BindingHandle
0x18001580f  call    cs:__imp_RpcImpersonateClient
0x180015815  mov     ebx, eax
0x180015817  test    eax, eax
0x180015819  jz      short loc_180015854
0x18001581b  mov     r9d, eax; unsigned int
0x18001581e  lea     r8, aSasetnsaccount; "SASetNSAccountInformation"
0x180015825  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x18001582c  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180015831  test    ebx, 1FFF0000h
0x180015837  jnz     short loc_180015846
0x180015839  test    ebx, ebx
0x18001583b  jle     short loc_180015846
0x18001583d  movzx   ebx, bx
0x180015840  or      ebx, 80070000h
0x180015846  mov     [rsp+88h+arg_18], ebx
0x18001584d  mov     eax, ebx
0x18001584f  jmp     loc_180015A21
0x180015854  mov     rax, cs:__imp_RpcRevertToSelf
0x18001585b  mov     byte ptr [rsp+88h+var_40], r14b
0x180015860  mov     [rsp+88h+var_38], rax
0x180015865  xor     ecx, ecx; void *
0x180015867  call    ?IsThreadCallerAnAdmin@@YAHPEAX@Z; IsThreadCallerAnAdmin(void *)
0x18001586c  lea     rcx, [rsp+88h+var_40]
0x180015871  test    eax, eax
0x180015873  jnz     short loc_180015884
0x180015875  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x18001587a  mov     eax, 80070005h
0x18001587f  jmp     loc_180015A21
0x180015884  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x180015889  test    rdi, rdi
0x18001588c  jz      short loc_1800158AC
0x18001588e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015892  inc     rax
0x180015895  cmp     [rdi+rax*2], r14w
0x18001589a  jnz     short loc_180015892
0x18001589c  cmp     rax, 7Fh
0x1800158a0  jbe     short loc_1800158AC
0x1800158a2  mov     eax, 8007000Dh
0x1800158a7  jmp     loc_180015A21
0x1800158ac  test    rsi, rsi
0x1800158af  jz      short loc_1800158B7
0x1800158b1  cmp     [rsi], r14w
0x1800158b5  jnz     short loc_1800158BE
0x1800158b7  lea     rsi, aSystem; "System"
0x1800158be  mov     [rsp+88h+var_50], r14
0x1800158c3  mov     [rsp+88h+var_48], r14
0x1800158c8  mov     [rsp+88h+var_40], r14
0x1800158cd  mov     rcx, rsi; String1
0x1800158d0  call    ?IsLocalSystem@User@@SA_NPEBG@Z; User::IsLocalSystem(ushort const *)
0x1800158d5  test    al, al
0x1800158d7  jz      short loc_1800158DE
0x1800158d9  mov     rdi, r14
0x1800158dc  jmp     short loc_180015904
0x1800158de  test    rdi, rdi
0x1800158e1  jnz     short loc_180015904
0x1800158e3  xor     ecx, ecx; Block
0x1800158e5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800158ea  nop
0x1800158eb  xor     ecx, ecx; Block
0x1800158ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800158f2  nop
0x1800158f3  xor     ecx, ecx; Block
0x1800158f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800158fa  mov     eax, 80070057h
0x1800158ff  jmp     loc_180015A21
0x180015904  mov     [rsp+88h+var_58], r14
0x180015909  mov     rdx, rsi; lpAccountName
0x18001590c  lea     rcx, [rsp+88h+var_58]; this
0x180015911  call    ?FromUsername@User@@SAJAEAV1@PEBG@Z; User::FromUsername(User &,ushort const *)
0x180015916  mov     ebx, eax
0x180015918  mov     [rsp+88h+arg_18], eax
0x18001591f  test    eax, eax
0x180015921  jns     short loc_18001594C
0x180015923  lea     rcx, [rsp+88h+var_58]
0x180015928  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001592d  nop
0x18001592e  xor     ecx, ecx; Block
0x180015930  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015935  nop
0x180015936  xor     ecx, ecx; Block
0x180015938  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001593d  nop
0x18001593e  xor     ecx, ecx; Block
0x180015940  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015945  mov     eax, ebx
0x180015947  jmp     loc_180015A21
0x18001594c  mov     rax, [rsp+88h+var_58]
0x180015951  cmp     dword ptr [rax+28h], 1
0x180015955  jz      short loc_180015991
0x180015957  lea     rcx, [rsp+88h+var_58]; this
0x18001595c  call    ?IsLocalSystem@User@@QEBA_NXZ; User::IsLocalSystem(void)
0x180015961  test    al, al
0x180015963  jnz     short loc_180015991
0x180015965  lea     rcx, [rsp+88h+var_58]
0x18001596a  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001596f  nop
0x180015970  xor     ecx, ecx; Block
0x180015972  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015977  nop
0x180015978  xor     ecx, ecx; Block
0x18001597a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001597f  nop
0x180015980  xor     ecx, ecx; Block
0x180015982  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015987  mov     eax, 80070057h
0x18001598c  jmp     loc_180015A21
0x180015991  test    rdi, rdi
0x180015994  jz      short loc_1800159D6
0x180015996  mov     rdx, rdi; unsigned __int16 *
0x180015999  lea     rcx, [rsp+88h+var_58]; struct User *
0x18001599e  call    ?ValidateNtCredential@CredStore@@SAJAEBVUser@@PEBG@Z; CredStore::ValidateNtCredential(User const &,ushort const *)
0x1800159a3  mov     ebx, eax
0x1800159a5  mov     [rsp+88h+arg_18], eax
0x1800159ac  test    eax, eax
0x1800159ae  jns     short loc_1800159D6
0x1800159b0  lea     rcx, [rsp+88h+var_58]
0x1800159b5  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x1800159ba  nop
0x1800159bb  xor     ecx, ecx; Block
0x1800159bd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800159c2  nop
0x1800159c3  xor     ecx, ecx; Block
0x1800159c5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800159ca  nop
0x1800159cb  xor     ecx, ecx; Block
0x1800159cd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800159d2  mov     eax, ebx
0x1800159d4  jmp     short loc_180015A21
0x1800159d6  mov     r9, rdi; unsigned __int16 *
0x1800159d9  lea     r8, [rsp+88h+var_58]; struct User *
0x1800159de  mov     rcx, cs:?g_pCommonStore@CredStore@@0PEAV1@EA; this
0x1800159e5  call    ?StoreAlias@CredStore@@QEAAJPEBGAEBVUser@@PEAG@Z; CredStore::StoreAlias(ushort const *,User const &,ushort *)
0x1800159ea  mov     ebx, eax
0x1800159ec  mov     [rsp+88h+arg_18], eax
0x1800159f3  lea     rcx, [rsp+88h+var_58]
0x1800159f8  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x1800159fd  nop
0x1800159fe  xor     ecx, ecx; Block
0x180015a00  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015a05  nop
0x180015a06  xor     ecx, ecx; Block
0x180015a08  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015a0d  nop
0x180015a0e  xor     ecx, ecx; Block
0x180015a10  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015a15  nop
0x180015a16  jmp     short loc_180015A1F
0x180015a18  mov     ebx, [rsp+88h+arg_18]
0x180015a1f  mov     eax, ebx
0x180015a21  add     rsp, 68h
0x180015a25  pop     r14
0x180015a27  pop     rdi
0x180015a28  pop     rsi
0x180015a29  pop     rbx
0x180015a2a  retn
```
