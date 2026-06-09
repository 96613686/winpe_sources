# SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(ulong,wchar_t const *,_GUID,ulong,void const *,SessionDataUtil::WUDeploymentSessionInfoWrapper * *)

- ea: `0x140017db0`
- end: `0x140017f52`
- name: `?CreateInstance@WUDeploymentSessionInfoWrapper@SessionDataUtil@@SAJKPEB_WU_GUID@@KPEBXPEAPEAV12@@Z`
- size: `418`
- prototype: `static int(unsigned int, const wchar_t *, struct _GUID *__struct_ptr, unsigned int, const void *, struct SessionDataUtil::WUDeploymentSessionInfoWrapper **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140012128`
- `0x1400126b8`

## callees

- `0x140002ac0`
- `0x140013600`
- `0x14001593c`
- `0x140017db0`
- `0x140017f58`
- `0x14001aa60`
- `0x14001ad2c`
- `0x1400206e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(
        __int64 a1,
        const wchar_t *a2,
        struct _GUID *a3,
        unsigned int a4,
        const WCHAR **a5,
        struct SessionDataUtil::WUDeploymentSessionInfoWrapper **a6)
{
  unsigned int DeploymentSessionInfoOverride; // ebx
  SessionDataUtil::WUDeploymentSessionInfoWrapper *v10; // rax
  SessionDataUtil::WUDeploymentSessionInfoWrapper *v11; // rdi
  const WCHAR *v12; // rcx
  const WCHAR *v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  unsigned int v17; // [rsp+20h] [rbp-50h]
  _QWORD v18[2]; // [rsp+40h] [rbp-30h] BYREF
  struct _GUID v19; // [rsp+50h] [rbp-20h] BYREF
  struct IUnknown *v20; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  if ( a6 )
  {
    v18[0] = 0;
    WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v18);
    v10 = (SessionDataUtil::WUDeploymentSessionInfoWrapper *)operator new(
                                                               0x28u,
                                                               (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( v10 )
    {
      *(_QWORD *)v10 = 0;
      *((_QWORD *)v10 + 2) = 0;
      *((_QWORD *)v10 + 3) = 0;
      *((_QWORD *)v10 + 1) = 0;
      *((_QWORD *)v10 + 4) = 0;
    }
    else
    {
      v11 = 0;
    }
    v18[0] = v11;
    DeploymentSessionInfoOverride = v11 == 0 ? 0x8007000E : 0;
    if ( !v11 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D0,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
        (const char *)DeploymentSessionInfoOverride,
        v17);
LABEL_18:
      WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v18);
      return DeploymentSessionInfoOverride;
    }
    v12 = 0;
    v13 = 0;
    if ( a5 )
    {
      v12 = a5[1];
      v13 = *a5;
    }
    v20 = 0;
    DeploymentSessionInfoOverride = SessionDataUtil::GetDeploymentSessionInfoOverride(v12, v13, &v20);
    if ( (DeploymentSessionInfoOverride & 0x80000000) == 0 )
    {
      v19 = *a3;
      DeploymentSessionInfoOverride = SessionDataUtil::WUDeploymentSessionInfoWrapper::Initialize(
                                        v11,
                                        v14,
                                        a2,
                                        &v19,
                                        a4,
                                        a5,
                                        v20);
      if ( (DeploymentSessionInfoOverride & 0x80000000) == 0 )
      {
        v18[0] = 0;
        *a6 = v11;
        DeploymentSessionInfoOverride = 0;
LABEL_16:
        if ( v20 )
          ((void (__fastcall *)(struct IUnknown *))v20->lpVtbl->Release)(v20);
        goto LABEL_18;
      }
      v15 = 996;
    }
    else
    {
      v15 = 989;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)DeploymentSessionInfoOverride,
      v17);
    goto LABEL_16;
  }
  DeploymentSessionInfoOverride = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3CD,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
    (const char *)0x80004003LL,
    v17);
  return DeploymentSessionInfoOverride;
}

```

## disassembly

```asm
0x140017db0  mov     [rsp-38h+arg_0], rbx
0x140017db5  push    rbp
0x140017db6  push    rsi
0x140017db7  push    rdi
0x140017db8  push    r12
0x140017dba  push    r13
0x140017dbc  push    r14
0x140017dbe  push    r15
0x140017dc0  mov     rbp, rsp
0x140017dc3  sub     rsp, 70h
0x140017dc7  mov     rax, cs:__security_cookie
0x140017dce  xor     rax, rsp
0x140017dd1  mov     [rbp+var_8], rax
0x140017dd5  mov     r13d, r9d
0x140017dd8  mov     r12, r8
0x140017ddb  mov     r15, rdx
0x140017dde  mov     rsi, [rbp+arg_20]
0x140017de2  mov     r14, [rbp+arg_28]
0x140017de6  test    r14, r14
0x140017de9  jnz     short loc_140017E0D
0x140017deb  mov     rcx, [rbp+38h]; this
0x140017def  mov     ebx, 80004003h
0x140017df4  mov     r9d, ebx; char *
0x140017df7  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140017dfe  mov     edx, 3CDh; void *
0x140017e03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017e08  jmp     loc_140017F2C
0x140017e0d  mov     [rbp+var_30], 0
0x140017e15  lea     rcx, [rbp+var_30]
0x140017e19  call    ?InternalRelease@?$XPtrBase@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(void)
0x140017e1e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140017e25  mov     ecx, 28h ; '('; unsigned __int64
0x140017e2a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140017e2f  mov     rdi, rax
0x140017e32  xor     r8d, r8d
0x140017e35  test    rax, rax
0x140017e38  jz      short loc_140017E4F
0x140017e3a  mov     [rax], r8
0x140017e3d  mov     [rax+10h], r8
0x140017e41  mov     [rax+18h], r8
0x140017e45  mov     [rax+8], r8
0x140017e49  mov     [rax+20h], r8
0x140017e4d  jmp     short loc_140017E52
0x140017e4f  mov     rdi, r8
0x140017e52  mov     [rbp+var_30], rdi
0x140017e56  mov     rax, rdi
0x140017e59  neg     rax
0x140017e5c  sbb     ebx, ebx
0x140017e5e  not     ebx
0x140017e60  and     ebx, 8007000Eh
0x140017e66  test    rdi, rdi
0x140017e69  jnz     short loc_140017E88
0x140017e6b  mov     rcx, [rbp+38h]; this
0x140017e6f  mov     r9d, ebx; char *
0x140017e72  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140017e79  mov     edx, 3D0h; void *
0x140017e7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017e83  jmp     loc_140017F23
0x140017e88  mov     rcx, r8
0x140017e8b  mov     rdx, r8
0x140017e8e  test    rsi, rsi
0x140017e91  jz      short loc_140017E9A
0x140017e93  mov     rcx, [rsi+8]; this
0x140017e97  mov     rdx, [rsi]
0x140017e9a  mov     [rbp+var_10], r8
0x140017e9e  lea     r8, [rbp+var_10]
0x140017ea2  call    SessionDataUtil__GetDeploymentSessionInfoOverride
0x140017ea7  mov     ebx, eax
0x140017ea9  test    eax, eax
0x140017eab  jns     short loc_140017EB4
0x140017ead  mov     edx, 3DDh
0x140017eb2  jmp     short loc_140017EEB
0x140017eb4  mov     rax, [rbp+var_10]
0x140017eb8  movaps  xmm0, xmmword ptr [r12]
0x140017ebd  movdqa  xmmword ptr [rbp+var_20.Data1], xmm0
0x140017ec2  mov     [rsp+70h+var_40], rax; struct IUnknown *
0x140017ec7  mov     [rsp+70h+var_48], rsi; void *
0x140017ecc  mov     [rsp+70h+var_50], r13d; int
0x140017ed1  lea     r9, [rbp+var_20]; struct _GUID
0x140017ed5  mov     r8, r15; wchar_t *
0x140017ed8  mov     rcx, rdi; this
0x140017edb  call    ?Initialize@WUDeploymentSessionInfoWrapper@SessionDataUtil@@AEAAJKPEB_WU_GUID@@KPEBXPEAUIUnknown@@@Z; SessionDataUtil::WUDeploymentSessionInfoWrapper::Initialize(ulong,wchar_t const *,_GUID,ulong,void const *,IUnknown *)
0x140017ee0  mov     ebx, eax
0x140017ee2  test    eax, eax
0x140017ee4  jns     short loc_140017F00
0x140017ee6  mov     edx, 3E4h; void *
0x140017eeb  mov     rcx, [rbp+38h]; this
0x140017eef  mov     r9d, ebx; char *
0x140017ef2  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140017ef9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017efe  jmp     short loc_140017F0D
0x140017f00  mov     [rbp+var_30], 0
0x140017f08  mov     [r14], rdi
0x140017f0b  xor     ebx, ebx
0x140017f0d  mov     rcx, [rbp+var_10]
0x140017f11  test    rcx, rcx
0x140017f14  jz      short loc_140017F23
0x140017f16  mov     rdx, [rcx]
0x140017f19  mov     rax, [rdx+10h]
0x140017f1d  call    _guard_dispatch_icall
0x140017f22  nop
0x140017f23  lea     rcx, [rbp+var_30]
0x140017f27  call    ?InternalRelease@?$XPtrBase@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(void)
0x140017f2c  mov     eax, ebx
0x140017f2e  mov     rcx, [rbp+var_8]
0x140017f32  xor     rcx, rsp; StackCookie
0x140017f35  call    __security_check_cookie
0x140017f3a  mov     rbx, [rsp+70h+arg_0]
0x140017f42  add     rsp, 70h
0x140017f46  pop     r15
0x140017f48  pop     r14
0x140017f4a  pop     r13
0x140017f4c  pop     r12
0x140017f4e  pop     rdi
0x140017f4f  pop     rsi
0x140017f50  pop     rbp
0x140017f51  retn
```
