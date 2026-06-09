# SessionDataUtil::WUOptionalSessionInfoWrapper::CreateOptionalSessionInfo(ulong,void const *,ulong,IUnknown *)

- ea: `0x140017b48`
- end: `0x140017daa`
- name: `?CreateOptionalSessionInfo@WUOptionalSessionInfoWrapper@SessionDataUtil@@QEAAJKPEBXKPEAUIUnknown@@@Z`
- size: `610`
- prototype: `int(SessionDataUtil::WUOptionalSessionInfoWrapper *__hidden this, unsigned int, const void *, unsigned int, struct IUnknown *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x1400178a0`

## callees

- `0x140002ac0`
- `0x14000d4cc`
- `0x140013cf0`
- `0x140013d70`
- `0x140013de4`
- `0x140013e54`
- `0x140013ec4`
- `0x140015c4c`
- `0x140016318`
- `0x14001671c`
- `0x140016b20`
- `0x140016ef8`
- `0x1400174fc`
- `0x140017b48`
- `0x14001acf4`

## pseudocode

```c
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfoWrapper::CreateOptionalSessionInfo(
        SessionDataUtil::WUOptionalSessionInfoWrapper *this,
        int a2,
        const void *a3,
        unsigned int a4,
        struct IUnknown *a5)
{
  struct SessionDataUtil::WUOptionalSessionInfo **v7; // rdi
  void *v8; // rbx
  int Instance; // ebx
  __int64 v10; // rdx
  struct SessionDataUtil::WUOptionalSessionInfo2 **v11; // rdi
  void *v12; // rbx
  struct SessionDataUtil::WUOptionalSessionInfo3 **v13; // rdi
  void *v14; // rbx
  struct SessionDataUtil::WUOptionalSessionInfo4 **v15; // rbx
  struct SessionDataUtil::WUOptionalSessionInfo5 **v16; // rdi
  _QWORD *v17; // rbx
  void *v18; // rcx
  struct SessionDataUtil::WUOptionalSessionInfo6 **v19; // rdi
  void *v20; // rbx
  int v22; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a2 != 1 )
  {
    switch ( a2 )
    {
      case 2:
        v11 = (struct SessionDataUtil::WUOptionalSessionInfo2 **)((char *)this + 16);
        v12 = (void *)*((_QWORD *)this + 2);
        if ( v12 )
        {
          SessionDataUtil::WUOptionalSessionInfo2::~WUOptionalSessionInfo2(*((SessionDataUtil::WUOptionalSessionInfo2 **)this
                                                                           + 2));
          operator delete(v12, (const struct std::nothrow_t *)0x18);
          *v11 = 0;
        }
        Instance = SessionDataUtil::WUOptionalSessionInfo2::CreateInstance(2u, a3, a4, a5, v11);
        if ( Instance < 0 )
        {
          v10 = 846;
          goto LABEL_33;
        }
        break;
      case 3:
        v13 = (struct SessionDataUtil::WUOptionalSessionInfo3 **)((char *)this + 24);
        v14 = (void *)*((_QWORD *)this + 3);
        if ( v14 )
        {
          SessionDataUtil::WUOptionalSessionInfo3::~WUOptionalSessionInfo3(*((SessionDataUtil::WUOptionalSessionInfo3 **)this
                                                                           + 3));
          operator delete(v14, (const struct std::nothrow_t *)0x18);
          *v13 = 0;
        }
        Instance = SessionDataUtil::WUOptionalSessionInfo3::CreateInstance(3u, a3, a4, a5, v13);
        if ( Instance < 0 )
        {
          v10 = 854;
          goto LABEL_33;
        }
        break;
      case 4:
        v15 = (struct SessionDataUtil::WUOptionalSessionInfo4 **)((char *)this + 32);
        WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>::InternalRelease((char *)this + 32);
        Instance = SessionDataUtil::WUOptionalSessionInfo4::CreateInstance(4u, a3, a4, a5, v15);
        if ( Instance < 0 )
        {
          v10 = 862;
          goto LABEL_33;
        }
        break;
      case 5:
        v16 = (struct SessionDataUtil::WUOptionalSessionInfo5 **)((char *)this + 40);
        v17 = (_QWORD *)*((_QWORD *)this + 5);
        if ( v17 )
        {
          v18 = (void *)v17[6];
          if ( v18 )
          {
            SusFree(v18);
            v17[6] = 0;
          }
          WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>::InternalRelease(v17 + 5);
          operator delete(v17, (const struct std::nothrow_t *)0x38);
          *v16 = 0;
        }
        Instance = SessionDataUtil::WUOptionalSessionInfo5::CreateInstance(5u, a3, a4, a5, v16);
        if ( Instance < 0 )
        {
          v10 = 870;
          goto LABEL_33;
        }
        break;
      case 6:
        v19 = (struct SessionDataUtil::WUOptionalSessionInfo6 **)((char *)this + 48);
        v20 = (void *)*((_QWORD *)this + 6);
        if ( v20 )
        {
          SessionDataUtil::WUOptionalSessionInfo6::~WUOptionalSessionInfo6(*((SessionDataUtil::WUOptionalSessionInfo6 **)this
                                                                           + 6));
          operator delete(v20, (const struct std::nothrow_t *)0x18);
          *v19 = 0;
        }
        Instance = SessionDataUtil::WUOptionalSessionInfo6::CreateInstance(6u, a3, a4, a5, v19);
        if ( Instance < 0 )
        {
          v10 = 878;
          goto LABEL_33;
        }
        break;
      default:
        Instance = -2147024809;
        v10 = 882;
        goto LABEL_33;
    }
    return 0;
  }
  v7 = (struct SessionDataUtil::WUOptionalSessionInfo **)((char *)this + 8);
  v8 = (void *)*((_QWORD *)this + 1);
  if ( v8 )
  {
    SessionDataUtil::WUOptionalSessionInfo::~WUOptionalSessionInfo(*((SessionDataUtil::WUOptionalSessionInfo **)this + 1));
    operator delete(v8, (const struct std::nothrow_t *)0x38);
    *v7 = 0;
  }
  Instance = SessionDataUtil::WUOptionalSessionInfo::CreateInstance(1u, a3, a4, a5, v7);
  if ( Instance >= 0 )
    return 0;
  v10 = 838;
LABEL_33:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
    (const char *)(unsigned int)Instance,
    v22);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140017b48  mov     [rsp+arg_0], rbx
0x140017b4d  mov     [rsp+arg_8], rbp
0x140017b52  mov     [rsp+arg_10], rsi
0x140017b57  push    rdi
0x140017b58  sub     rsp, 30h
0x140017b5c  mov     esi, r9d
0x140017b5f  mov     rbp, r8
0x140017b62  cmp     edx, 1
0x140017b65  jnz     short loc_140017BBD
0x140017b67  lea     rdi, [rcx+8]
0x140017b6b  mov     rbx, [rdi]
0x140017b6e  test    rbx, rbx
0x140017b71  jz      short loc_140017B8F
0x140017b73  mov     rcx, rbx; this
0x140017b76  call    ??1WUOptionalSessionInfo@SessionDataUtil@@QEAA@XZ; SessionDataUtil::WUOptionalSessionInfo::~WUOptionalSessionInfo(void)
0x140017b7b  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x140017b80  mov     rcx, rbx; void *
0x140017b83  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017b88  mov     qword ptr [rdi], 0
0x140017b8f  mov     r9, [rsp+38h+arg_20]; struct IUnknown *
0x140017b94  mov     r8d, esi; unsigned int
0x140017b97  mov     rdx, rbp; void *
0x140017b9a  mov     qword ptr [rsp+38h+var_18], rdi; struct SessionDataUtil::WUOptionalSessionInfo **
0x140017b9f  mov     ecx, 1; unsigned int
0x140017ba4  call    ?CreateInstance@WUOptionalSessionInfo@SessionDataUtil@@SAJKPEBXKPEAUIUnknown@@PEAPEAV12@@Z; SessionDataUtil::WUOptionalSessionInfo::CreateInstance(ulong,void const *,ulong,IUnknown *,SessionDataUtil::WUOptionalSessionInfo * *)
0x140017ba9  mov     ebx, eax
0x140017bab  test    eax, eax
0x140017bad  jns     loc_140017D71
0x140017bb3  mov     edx, 346h
0x140017bb8  jmp     loc_140017D7F
0x140017bbd  cmp     edx, 2
0x140017bc0  jnz     short loc_140017C18
0x140017bc2  lea     rdi, [rcx+10h]
0x140017bc6  mov     rbx, [rdi]
0x140017bc9  test    rbx, rbx
0x140017bcc  jz      short loc_140017BEA
0x140017bce  mov     rcx, rbx; this
0x140017bd1  call    ??1WUOptionalSessionInfo2@SessionDataUtil@@QEAA@XZ; SessionDataUtil::WUOptionalSessionInfo2::~WUOptionalSessionInfo2(void)
0x140017bd6  mov     edx, 18h; struct std::nothrow_t *
0x140017bdb  mov     rcx, rbx; void *
0x140017bde  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017be3  mov     qword ptr [rdi], 0
0x140017bea  mov     r9, [rsp+38h+arg_20]; struct IUnknown *
0x140017bef  mov     r8d, esi; unsigned int
0x140017bf2  mov     rdx, rbp; void *
0x140017bf5  mov     qword ptr [rsp+38h+var_18], rdi; struct SessionDataUtil::WUOptionalSessionInfo2 **
0x140017bfa  mov     ecx, 2; unsigned int
0x140017bff  call    ?CreateInstance@WUOptionalSessionInfo2@SessionDataUtil@@SAJKPEBXKPEAUIUnknown@@PEAPEAV12@@Z; SessionDataUtil::WUOptionalSessionInfo2::CreateInstance(ulong,void const *,ulong,IUnknown *,SessionDataUtil::WUOptionalSessionInfo2 * *)
0x140017c04  mov     ebx, eax
0x140017c06  test    eax, eax
0x140017c08  jns     loc_140017D71
0x140017c0e  mov     edx, 34Eh
0x140017c13  jmp     loc_140017D7F
0x140017c18  cmp     edx, 3
0x140017c1b  jnz     short loc_140017C73
0x140017c1d  lea     rdi, [rcx+18h]
0x140017c21  mov     rbx, [rdi]
0x140017c24  test    rbx, rbx
0x140017c27  jz      short loc_140017C45
0x140017c29  mov     rcx, rbx; this
0x140017c2c  call    ??1WUOptionalSessionInfo3@SessionDataUtil@@QEAA@XZ; SessionDataUtil::WUOptionalSessionInfo3::~WUOptionalSessionInfo3(void)
0x140017c31  mov     edx, 18h; struct std::nothrow_t *
0x140017c36  mov     rcx, rbx; void *
0x140017c39  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017c3e  mov     qword ptr [rdi], 0
0x140017c45  mov     r9, [rsp+38h+arg_20]; struct IUnknown *
0x140017c4a  mov     r8d, esi; unsigned int
0x140017c4d  mov     rdx, rbp; void *
0x140017c50  mov     qword ptr [rsp+38h+var_18], rdi; struct SessionDataUtil::WUOptionalSessionInfo3 **
0x140017c55  mov     ecx, 3; unsigned int
0x140017c5a  call    ?CreateInstance@WUOptionalSessionInfo3@SessionDataUtil@@SAJKPEBXKPEAUIUnknown@@PEAPEAV12@@Z; SessionDataUtil::WUOptionalSessionInfo3::CreateInstance(ulong,void const *,ulong,IUnknown *,SessionDataUtil::WUOptionalSessionInfo3 * *)
0x140017c5f  mov     ebx, eax
0x140017c61  test    eax, eax
0x140017c63  jns     loc_140017D71
0x140017c69  mov     edx, 356h
0x140017c6e  jmp     loc_140017D7F
0x140017c73  cmp     edx, 4
0x140017c76  jnz     short loc_140017CB2
0x140017c78  lea     rbx, [rcx+20h]
0x140017c7c  mov     rcx, rbx
0x140017c7f  call    ?InternalRelease@?$XPtrBase@VWUOptionalSessionInfo4@SessionDataUtil@@U?$STPolicy@VWUOptionalSessionInfo4@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>::InternalRelease(void)
0x140017c84  mov     r9, [rsp+38h+arg_20]; struct IUnknown *
0x140017c89  mov     r8d, esi; unsigned int
0x140017c8c  mov     rdx, rbp; void *
0x140017c8f  mov     qword ptr [rsp+38h+var_18], rbx; struct SessionDataUtil::WUOptionalSessionInfo4 **
0x140017c94  mov     ecx, 4; unsigned int
0x140017c99  call    ?CreateInstance@WUOptionalSessionInfo4@SessionDataUtil@@SAJKPEBXKPEAUIUnknown@@PEAPEAV12@@Z; SessionDataUtil::WUOptionalSessionInfo4::CreateInstance(ulong,void const *,ulong,IUnknown *,SessionDataUtil::WUOptionalSessionInfo4 * *)
0x140017c9e  mov     ebx, eax
0x140017ca0  test    eax, eax
0x140017ca2  jns     loc_140017D71
0x140017ca8  mov     edx, 35Eh
0x140017cad  jmp     loc_140017D7F
0x140017cb2  cmp     edx, 5
0x140017cb5  jnz     short loc_140017D1D
0x140017cb7  lea     rdi, [rcx+28h]
0x140017cbb  mov     rbx, [rdi]
0x140017cbe  test    rbx, rbx
0x140017cc1  jz      short loc_140017CF6
0x140017cc3  mov     rcx, [rbx+30h]; lpMem
0x140017cc7  test    rcx, rcx
0x140017cca  jz      short loc_140017CD9
0x140017ccc  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140017cd1  mov     qword ptr [rbx+30h], 0
0x140017cd9  lea     rcx, [rbx+28h]
0x140017cdd  call    ?InternalRelease@?$XPtrBase@VWUOptionalSessionInfo4@SessionDataUtil@@U?$STPolicy@VWUOptionalSessionInfo4@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>::InternalRelease(void)
0x140017ce2  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x140017ce7  mov     rcx, rbx; void *
0x140017cea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017cef  mov     qword ptr [rdi], 0
0x140017cf6  mov     r9, [rsp+38h+arg_20]; struct IUnknown *
0x140017cfb  mov     r8d, esi; unsigned int
0x140017cfe  mov     rdx, rbp; void *
0x140017d01  mov     qword ptr [rsp+38h+var_18], rdi; struct SessionDataUtil::WUOptionalSessionInfo5 **
0x140017d06  mov     ecx, 5; unsigned int
0x140017d0b  call    ?CreateInstance@WUOptionalSessionInfo5@SessionDataUtil@@SAJKPEBXKPEAUIUnknown@@PEAPEAV12@@Z; SessionDataUtil::WUOptionalSessionInfo5::CreateInstance(ulong,void const *,ulong,IUnknown *,SessionDataUtil::WUOptionalSessionInfo5 * *)
0x140017d10  mov     ebx, eax
0x140017d12  test    eax, eax
0x140017d14  jns     short loc_140017D71
0x140017d16  mov     edx, 366h
0x140017d1b  jmp     short loc_140017D7F
0x140017d1d  cmp     edx, 6
0x140017d20  jnz     short loc_140017D75
0x140017d22  lea     rdi, [rcx+30h]
0x140017d26  mov     rbx, [rdi]
0x140017d29  test    rbx, rbx
0x140017d2c  jz      short loc_140017D4A
0x140017d2e  mov     rcx, rbx; this
0x140017d31  call    ??1WUOptionalSessionInfo6@SessionDataUtil@@QEAA@XZ; SessionDataUtil::WUOptionalSessionInfo6::~WUOptionalSessionInfo6(void)
0x140017d36  mov     edx, 18h; struct std::nothrow_t *
0x140017d3b  mov     rcx, rbx; void *
0x140017d3e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017d43  mov     qword ptr [rdi], 0
0x140017d4a  mov     r9, [rsp+38h+arg_20]; struct IUnknown *
0x140017d4f  mov     r8d, esi; unsigned int
0x140017d52  mov     rdx, rbp; void *
0x140017d55  mov     qword ptr [rsp+38h+var_18], rdi; struct SessionDataUtil::WUOptionalSessionInfo6 **
0x140017d5a  mov     ecx, 6; unsigned int
0x140017d5f  call    ?CreateInstance@WUOptionalSessionInfo6@SessionDataUtil@@SAJKPEBXKPEAUIUnknown@@PEAPEAV12@@Z; SessionDataUtil::WUOptionalSessionInfo6::CreateInstance(ulong,void const *,ulong,IUnknown *,SessionDataUtil::WUOptionalSessionInfo6 * *)
0x140017d64  mov     ebx, eax
0x140017d66  test    eax, eax
0x140017d68  jns     short loc_140017D71
0x140017d6a  mov     edx, 36Eh
0x140017d6f  jmp     short loc_140017D7F
0x140017d71  xor     eax, eax
0x140017d73  jmp     short loc_140017D95
0x140017d75  mov     ebx, 80070057h
0x140017d7a  mov     edx, 372h; void *
0x140017d7f  mov     rcx, [rsp+38h]; this
0x140017d84  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140017d8b  mov     r9d, ebx; char *
0x140017d8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017d93  mov     eax, ebx
0x140017d95  mov     rbx, [rsp+38h+arg_0]
0x140017d9a  mov     rbp, [rsp+38h+arg_8]
0x140017d9f  mov     rsi, [rsp+38h+arg_10]
0x140017da4  add     rsp, 30h
0x140017da8  pop     rdi
0x140017da9  retn
```
