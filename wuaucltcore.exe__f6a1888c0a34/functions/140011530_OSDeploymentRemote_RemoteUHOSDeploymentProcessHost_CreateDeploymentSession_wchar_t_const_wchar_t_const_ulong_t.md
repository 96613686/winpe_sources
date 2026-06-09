# OSDeploymentRemote::RemoteUHOSDeploymentProcessHost::CreateDeploymentSession(wchar_t const *,wchar_t const *,ulong,tagOptionalSessionInfo6 *,IRemoteDeploymentSession * *)

- ea: `0x140011530`
- end: `0x1400116d3`
- name: `?CreateDeploymentSession@RemoteUHOSDeploymentProcessHost@OSDeploymentRemote@@UEAAJPEB_W0KPEAUtagOptionalSessionInfo6@@PEAPEAUIRemoteDeploymentSession@@@Z`
- size: `419`
- prototype: `__int64 __fastcall(OSDeploymentRemote::RemoteUHOSDeploymentProcessHost *__hidden this, const wchar_t *, const wchar_t *, unsigned int, struct tagOptionalSessionInfo6 *, struct IRemoteDeploymentSession **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002ac0`
- `0x140011530`
- `0x140011f2c`
- `0x140018c14`
- `0x14001ad2c`
- `0x1400206e0`

## pseudocode

```c
__int64 __fastcall OSDeploymentRemote::RemoteUHOSDeploymentProcessHost::CreateDeploymentSession(
        OSDeploymentRemote::RemoteUHOSDeploymentProcessHost *this,
        const wchar_t *a2,
        const wchar_t *a3,
        unsigned int a4,
        struct tagOptionalSessionInfo6 *a5,
        struct IRemoteDeploymentSession **a6)
{
  unsigned int v9; // ebx
  __int64 v10; // rdx
  _DWORD *v12; // rax
  _DWORD *v13; // rdi
  int v14; // esi
  __int64 v15; // rax
  int v16; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( !a5 )
  {
    v9 = -2147024809;
    v10 = 32;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteUHOSDeploymentProcessHost.cpp",
      (const char *)v9,
      v16);
    return v9;
  }
  if ( !a6 )
  {
    v9 = -2147467261;
    v10 = 33;
    goto LABEL_3;
  }
  v12 = operator new(0x208u, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v12;
  if ( v12 )
  {
    v12[5] = 1;
    *(_QWORD *)v12 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteDeploymentSession,ICancelMethodCalls>::`vftable'{for `IRemoteDeploymentSession'};
    *((_QWORD *)v12 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteDeploymentSession,ICancelMethodCalls>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICancelMethodCalls>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v13 = &OSDeploymentRemote::RemoteDeploymentSession::`vftable'{for `IRemoteDeploymentSession'};
    *((_QWORD *)v13 + 1) = &OSDeploymentRemote::RemoteDeploymentSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICancelMethodCalls>'};
    *((_QWORD *)v13 + 3) = 0;
    *((_QWORD *)v13 + 4) = 0;
    OSDeploymentInformationFactory::OSDeploymentInformationFactory((OSDeploymentInformationFactory *)(v13 + 10));
    *((_BYTE *)v13 + 512) = 0;
    v14 = OSDeploymentRemote::RemoteDeploymentSession::RuntimeClassInitialize(
            (OSDeploymentRemote::RemoteDeploymentSession *)v13,
            a2,
            a3,
            a4,
            a5);
    v15 = *(_QWORD *)v13;
    if ( v14 >= 0 )
    {
      (*(void (__fastcall **)(_DWORD *))(v15 + 8))(v13);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v13 + 16LL))(v13);
      *a6 = (struct IRemoteDeploymentSession *)v13;
      return 0;
    }
    (*(void (__fastcall **)(_DWORD *))(v15 + 16))(v13);
  }
  else
  {
    v14 = -2147024882;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x28,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteUHOSDeploymentProcessHost.cpp",
    (const char *)(unsigned int)v14,
    v16);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140011530  push    rbx
0x140011532  push    rbp
0x140011533  push    rsi
0x140011534  push    rdi
0x140011535  push    r12
0x140011537  push    r14
0x140011539  push    r15
0x14001153b  sub     rsp, 50h
0x14001153f  mov     r12d, r9d
0x140011542  mov     r15, r8
0x140011545  mov     rbp, rdx
0x140011548  mov     rsi, [rsp+88h+arg_20]
0x140011550  mov     r14, [rsp+88h+arg_28]
0x140011558  test    rsi, rsi
0x14001155b  jnz     short loc_140011583
0x14001155d  mov     ebx, 80070057h
0x140011562  lea     edx, [rsi+20h]; void *
0x140011565  lea     r8, aCW1SSrcClientE; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x14001156c  mov     r9d, ebx; char *
0x14001156f  mov     rcx, [rsp+88h]; this
0x140011577  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001157c  mov     eax, ebx
0x14001157e  jmp     loc_1400116C4
0x140011583  test    r14, r14
0x140011586  jnz     short loc_140011593
0x140011588  mov     ebx, 80004003h
0x14001158d  lea     edx, [r14+21h]
0x140011591  jmp     short loc_140011565
0x140011593  xor     ebx, ebx
0x140011595  mov     [rsp+88h+var_48], rbx
0x14001159a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400115a1  mov     ecx, 208h; unsigned __int64
0x1400115a6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400115ab  mov     rdi, rax
0x1400115ae  mov     [rsp+88h+var_50], rax
0x1400115b3  test    rax, rax
0x1400115b6  jnz     short loc_1400115C2
0x1400115b8  mov     esi, 8007000Eh
0x1400115bd  jmp     loc_140011666
0x1400115c2  mov     dword ptr [rax+14h], 1
0x1400115c9  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIRemoteDeploymentSession@@UICancelMethodCalls@@@WRL@Microsoft@@6BIRemoteDeploymentSession@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteDeploymentSession,ICancelMethodCalls>::`vftable'{for `IRemoteDeploymentSession'}
0x1400115d0  mov     [rdi], rax
0x1400115d3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIRemoteDeploymentSession@@UICancelMethodCalls@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICancelMethodCalls@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteDeploymentSession,ICancelMethodCalls>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICancelMethodCalls>'}
0x1400115da  mov     [rdi+8], rax
0x1400115de  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1400115e5  test    rcx, rcx
0x1400115e8  jz      short loc_1400115F7
0x1400115ea  mov     rax, [rcx]
0x1400115ed  mov     rax, [rax+8]
0x1400115f1  call    _guard_dispatch_icall
0x1400115f6  nop
0x1400115f7  lea     rax, ??_7RemoteDeploymentSession@OSDeploymentRemote@@6BIRemoteDeploymentSession@@@; const OSDeploymentRemote::RemoteDeploymentSession::`vftable'{for `IRemoteDeploymentSession'}
0x1400115fe  mov     [rdi], rax
0x140011601  lea     rax, ??_7RemoteDeploymentSession@OSDeploymentRemote@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICancelMethodCalls@@@Details@WRL@Microsoft@@@; const OSDeploymentRemote::RemoteDeploymentSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICancelMethodCalls>'}
0x140011608  mov     [rdi+8], rax
0x14001160c  mov     qword ptr [rdi+18h], 0
0x140011614  mov     qword ptr [rdi+20h], 0
0x14001161c  lea     rcx, [rdi+28h]; this
0x140011620  call    ??0OSDeploymentInformationFactory@@QEAA@XZ; OSDeploymentInformationFactory::OSDeploymentInformationFactory(void)
0x140011625  mov     byte ptr [rdi+200h], 0
0x14001162c  mov     [rsp+88h+var_58], rdi
0x140011631  mov     [rsp+88h+var_50], 0
0x14001163a  mov     qword ptr [rsp+88h+var_68], rsi; int
0x14001163f  mov     r9d, r12d; unsigned int
0x140011642  mov     r8, r15; wchar_t *
0x140011645  mov     rdx, rbp; wchar_t *
0x140011648  mov     rcx, rdi; this
0x14001164b  call    ?RuntimeClassInitialize@RemoteDeploymentSession@OSDeploymentRemote@@QEAAJPEB_W0KPEAUtagOptionalSessionInfo6@@@Z; OSDeploymentRemote::RemoteDeploymentSession::RuntimeClassInitialize(wchar_t const *,wchar_t const *,ulong,tagOptionalSessionInfo6 *)
0x140011650  mov     esi, eax
0x140011652  mov     rax, [rdi]
0x140011655  test    esi, esi
0x140011657  jns     short loc_140011684
0x140011659  mov     rcx, rdi
0x14001165c  mov     rax, [rax+10h]
0x140011660  call    _guard_dispatch_icall
0x140011665  nop
0x140011666  mov     rcx, [rsp+88h]; this
0x14001166e  mov     r9d, esi; char *
0x140011671  lea     r8, aCW1SSrcClientE; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140011678  mov     edx, 28h ; '('; void *
0x14001167d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011682  jmp     short loc_1400116AD
0x140011684  mov     rcx, rdi
0x140011687  mov     rax, [rax+8]
0x14001168b  call    _guard_dispatch_icall
0x140011690  nop
0x140011691  mov     [rsp+88h+var_48], rdi
0x140011696  mov     rax, [rdi]
0x140011699  mov     rcx, rdi
0x14001169c  mov     rax, [rax+10h]
0x1400116a0  call    _guard_dispatch_icall
0x1400116a5  nop
0x1400116a6  xor     ebx, ebx
0x1400116a8  mov     [r14], rdi
0x1400116ab  xor     esi, esi
0x1400116ad  test    rbx, rbx
0x1400116b0  jz      short loc_1400116C2
0x1400116b2  mov     rdx, [rbx]
0x1400116b5  mov     rcx, rbx
0x1400116b8  mov     rax, [rdx+10h]
0x1400116bc  call    _guard_dispatch_icall
0x1400116c1  nop
0x1400116c2  mov     eax, esi
0x1400116c4  add     rsp, 50h
0x1400116c8  pop     r15
0x1400116ca  pop     r14
0x1400116cc  pop     r12
0x1400116ce  pop     rdi
0x1400116cf  pop     rsi
0x1400116d0  pop     rbp
0x1400116d1  pop     rbx
0x1400116d2  retn
```
