# SessionDataUtil::WUOptionalSessionInfoWrapper::CreateInstance(ulong,void const *,IUnknown *,SessionDataUtil::WUOptionalSessionInfoWrapper * *)

- ea: `0x1400178a0`
- end: `0x140017b42`
- name: `?CreateInstance@WUOptionalSessionInfoWrapper@SessionDataUtil@@SAJKPEBXPEAUIUnknown@@PEAPEAV12@@Z`
- size: `674`
- prototype: `static int(unsigned int, const void *, struct IUnknown *, struct SessionDataUtil::WUOptionalSessionInfoWrapper **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x140017f58`

## callees

- `0x140002ac0`
- `0x140013a74`
- `0x1400178a0`
- `0x140017b48`
- `0x1400186e8`
- `0x14001aa60`
- `0x14001acf4`
- `0x14001ad2c`
- `0x1400206e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfoWrapper::CreateInstance(
        int a1,
        const void *a2,
        struct IUnknown *a3,
        struct SessionDataUtil::WUOptionalSessionInfoWrapper **a4)
{
  double v4; // xmm3_8
  unsigned int v8; // ebx
  __int64 v9; // rdx
  SessionDataUtil::WUOptionalSessionInfoWrapper *v11; // rax
  SessionDataUtil::WUOptionalSessionInfoWrapper *v12; // rdi
  SessionDataUtil::WUOptionalSessionInfoWrapper *v13; // rbx
  unsigned int v14; // esi
  __int64 v15; // rdx
  int OptionalSessionInfo; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  int v18; // eax
  const wchar_t *v19; // r8
  int NumberPropertyWithDefault; // eax
  int v21; // eax
  int v22; // [rsp+20h] [rbp-40h]
  int v23; // [rsp+20h] [rbp-40h]
  int v24; // [rsp+20h] [rbp-40h]
  int v25; // [rsp+20h] [rbp-40h]
  JsonUtil *v27; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  if ( !a2 )
  {
    v8 = -2147024809;
    v9 = 812;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)v8,
      v22);
    return v8;
  }
  if ( !a4 )
  {
    v8 = -2147467261;
    v9 = 813;
    goto LABEL_3;
  }
  v11 = (SessionDataUtil::WUOptionalSessionInfoWrapper *)operator new(
                                                           0x38u,
                                                           (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( v11 )
  {
    *(_QWORD *)v11 = 0;
    *((_QWORD *)v11 + 1) = 0;
    *((_QWORD *)v11 + 2) = 0;
    *((_QWORD *)v11 + 3) = 0;
    *((_QWORD *)v11 + 4) = 0;
    *((_QWORD *)v11 + 5) = 0;
    *((_QWORD *)v11 + 6) = 0;
  }
  else
  {
    v12 = 0;
  }
  v13 = v12;
  v14 = v12 == 0 ? 0x8007000E : 0;
  if ( v12 )
  {
    *(_DWORD *)v12 = a1;
    OptionalSessionInfo = SessionDataUtil::WUOptionalSessionInfoWrapper::CreateOptionalSessionInfo(v12, a1, a2, 0, 0);
    v14 = OptionalSessionInfo;
    if ( OptionalSessionInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x382,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
        (const char *)(unsigned int)OptionalSessionInfo,
        v23);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x38B,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
        (const char *)v14,
        v24);
LABEL_25:
      v15 = 820;
      goto LABEL_26;
    }
    if ( a3 )
    {
      lpVtbl = a3->lpVtbl;
      v27 = 0;
      v18 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, JsonUtil **))lpVtbl->QueryInterface)(
              a3,
              &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
              &v27);
      v14 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x390,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
          (const char *)(unsigned int)v18,
          v23);
        if ( v27 )
          (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v27 + 16LL))(v27);
        goto LABEL_25;
      }
      NumberPropertyWithDefault = JsonUtil::GetNumberPropertyWithDefault(v27, L"OptionalSessionInfoVersion", v19, v4);
      v14 = NumberPropertyWithDefault;
      if ( NumberPropertyWithDefault < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x396,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
          (const char *)(unsigned int)NumberPropertyWithDefault,
          v23);
        if ( v27 )
          (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v27 + 16LL))(v27);
        goto LABEL_25;
      }
      *(_DWORD *)v12 = (int)0.0;
      v21 = SessionDataUtil::WUOptionalSessionInfoWrapper::CreateOptionalSessionInfo(v12, a1, a2, (int)0.0, a3);
      v14 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x39D,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
          (const char *)(unsigned int)v21,
          v25);
        if ( v27 )
          (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v27 + 16LL))(v27);
        goto LABEL_25;
      }
      if ( v27 )
        (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v13 = 0;
    *a4 = v12;
    v14 = 0;
    goto LABEL_30;
  }
  v15 = 816;
LABEL_26:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
    (const char *)v14,
    v22);
LABEL_30:
  if ( v13 )
  {
    SessionDataUtil::WUOptionalSessionInfoWrapper::~WUOptionalSessionInfoWrapper(v13);
    operator delete(v13, (const struct std::nothrow_t *)0x38);
  }
  return v14;
}

```

## disassembly

```asm
0x1400178a0  push    rbp
0x1400178a2  push    rbx
0x1400178a3  push    rsi
0x1400178a4  push    rdi
0x1400178a5  push    r12
0x1400178a7  push    r13
0x1400178a9  push    r15
0x1400178ab  mov     rbp, rsp
0x1400178ae  sub     rsp, 60h
0x1400178b2  mov     rax, cs:__security_cookie
0x1400178b9  xor     rax, rsp
0x1400178bc  mov     [rbp+var_10], rax
0x1400178c0  mov     r13, r9
0x1400178c3  mov     r12, r8
0x1400178c6  mov     [rbp+var_28], rdx
0x1400178ca  mov     r15d, ecx
0x1400178cd  xor     ebx, ebx
0x1400178cf  test    rdx, rdx
0x1400178d2  jnz     short loc_1400178F8
0x1400178d4  mov     ebx, 80070057h
0x1400178d9  mov     edx, 32Ch; void *
0x1400178de  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400178e5  mov     r9d, ebx; char *
0x1400178e8  mov     rcx, [rbp+38h]; this
0x1400178ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400178f1  mov     eax, ebx
0x1400178f3  jmp     loc_140017B27
0x1400178f8  test    r13, r13
0x1400178fb  jnz     short loc_140017909
0x1400178fd  mov     ebx, 80004003h
0x140017902  mov     edx, 32Dh
0x140017907  jmp     short loc_1400178DE
0x140017909  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140017910  mov     ecx, 38h ; '8'; unsigned __int64
0x140017915  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001791a  mov     rdi, rax
0x14001791d  test    rax, rax
0x140017920  jz      short loc_14001793F
0x140017922  mov     [rax], rbx
0x140017925  mov     [rax+8], rbx
0x140017929  mov     [rax+10h], rbx
0x14001792d  mov     [rax+18h], rbx
0x140017931  mov     [rax+20h], rbx
0x140017935  mov     [rax+28h], rbx
0x140017939  mov     [rax+30h], rbx
0x14001793d  jmp     short loc_140017942
0x14001793f  mov     rdi, rbx
0x140017942  mov     rbx, rdi
0x140017945  mov     [rbp+var_20], rbx
0x140017949  mov     rax, rdi
0x14001794c  neg     rax
0x14001794f  sbb     esi, esi
0x140017951  not     esi
0x140017953  and     esi, 8007000Eh
0x140017959  test    rdi, rdi
0x14001795c  jnz     short loc_140017968
0x14001795e  mov     edx, 330h
0x140017963  jmp     loc_140017AD8
0x140017968  mov     [rdi], r15d
0x14001796b  mov     qword ptr [rsp+60h+var_40], 0; int
0x140017974  xor     r9d, r9d; unsigned int
0x140017977  mov     r8, [rbp+var_28]; void *
0x14001797b  mov     edx, r15d; unsigned int
0x14001797e  mov     rcx, rdi; this
0x140017981  call    ?CreateOptionalSessionInfo@WUOptionalSessionInfoWrapper@SessionDataUtil@@QEAAJKPEBXKPEAUIUnknown@@@Z; SessionDataUtil::WUOptionalSessionInfoWrapper::CreateOptionalSessionInfo(ulong,void const *,ulong,IUnknown *)
0x140017986  mov     esi, eax
0x140017988  test    eax, eax
0x14001798a  jns     short loc_1400179C1
0x14001798c  mov     rcx, [rbp+38h]; this
0x140017990  mov     r9d, eax; char *
0x140017993  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14001799a  mov     edx, 382h; void *
0x14001799f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400179a4  mov     rcx, [rbp+38h]; this
0x1400179a8  mov     r9d, esi; char *
0x1400179ab  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400179b2  mov     edx, 38Bh; void *
0x1400179b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400179bc  jmp     loc_140017AD3
0x1400179c1  test    r12, r12
0x1400179c4  jz      loc_140017B03
0x1400179ca  mov     rax, [r12]
0x1400179ce  mov     [rbp+var_18], 0
0x1400179d6  lea     r8, [rbp+var_18]
0x1400179da  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x1400179e1  mov     rcx, r12
0x1400179e4  mov     rax, [rax]
0x1400179e7  call    _guard_dispatch_icall
0x1400179ec  mov     esi, eax
0x1400179ee  test    eax, eax
0x1400179f0  jns     short loc_140017A26
0x1400179f2  mov     rcx, [rbp+38h]; this
0x1400179f6  mov     r9d, eax; char *
0x1400179f9  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140017a00  mov     edx, 390h; void *
0x140017a05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017a0a  nop
0x140017a0b  mov     rcx, [rbp+var_18]
0x140017a0f  test    rcx, rcx
0x140017a12  jz      short loc_140017A21
0x140017a14  mov     rax, [rcx]
0x140017a17  mov     rax, [rax+10h]
0x140017a1b  call    _guard_dispatch_icall
0x140017a20  nop
0x140017a21  jmp     loc_140017AD3
0x140017a26  xorps   xmm0, xmm0
0x140017a29  movsd   [rbp+var_30], xmm0
0x140017a2e  xorps   xmm2, xmm2
0x140017a31  cvtsi2sd xmm2, r15
0x140017a36  lea     r9, [rbp+var_30]
0x140017a3a  lea     rdx, aOptionalsessio_0; "OptionalSessionInfoVersion"
0x140017a41  mov     rcx, [rbp+var_18]; this
0x140017a45  call    ?GetNumberPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WNPEAN@Z; JsonUtil::GetNumberPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,double,double *)
0x140017a4a  mov     esi, eax
0x140017a4c  test    eax, eax
0x140017a4e  jns     short loc_140017A81
0x140017a50  mov     rcx, [rbp+38h]; this
0x140017a54  mov     r9d, eax; char *
0x140017a57  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140017a5e  mov     edx, 396h; void *
0x140017a63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017a68  nop
0x140017a69  mov     rcx, [rbp+var_18]
0x140017a6d  test    rcx, rcx
0x140017a70  jz      short loc_140017A7F
0x140017a72  mov     rax, [rcx]
0x140017a75  mov     rax, [rax+10h]
0x140017a79  call    _guard_dispatch_icall
0x140017a7e  nop
0x140017a7f  jmp     short loc_140017AD3
0x140017a81  cvttsd2si r9, [rbp+var_30]; unsigned int
0x140017a87  mov     [rdi], r9d
0x140017a8a  mov     qword ptr [rsp+60h+var_40], r12; int
0x140017a8f  mov     r8, [rbp+var_28]; void *
0x140017a93  mov     edx, r15d; unsigned int
0x140017a96  mov     rcx, rdi; this
0x140017a99  call    ?CreateOptionalSessionInfo@WUOptionalSessionInfoWrapper@SessionDataUtil@@QEAAJKPEBXKPEAUIUnknown@@@Z; SessionDataUtil::WUOptionalSessionInfoWrapper::CreateOptionalSessionInfo(ulong,void const *,ulong,IUnknown *)
0x140017a9e  mov     esi, eax
0x140017aa0  test    eax, eax
0x140017aa2  jns     short loc_140017AED
0x140017aa4  mov     rcx, [rbp+38h]; this
0x140017aa8  mov     r9d, eax; char *
0x140017aab  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140017ab2  mov     edx, 39Dh; void *
0x140017ab7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017abc  nop
0x140017abd  mov     rcx, [rbp+var_18]
0x140017ac1  test    rcx, rcx
0x140017ac4  jz      short loc_140017AD3
0x140017ac6  mov     rax, [rcx]
0x140017ac9  mov     rax, [rax+10h]
0x140017acd  call    _guard_dispatch_icall
0x140017ad2  nop
0x140017ad3  mov     edx, 334h; void *
0x140017ad8  mov     rcx, [rbp+38h]; this
0x140017adc  mov     r9d, esi; char *
0x140017adf  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140017ae6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017aeb  jmp     short loc_140017B0B
0x140017aed  mov     rcx, [rbp+var_18]
0x140017af1  test    rcx, rcx
0x140017af4  jz      short loc_140017B03
0x140017af6  mov     rax, [rcx]
0x140017af9  mov     rax, [rax+10h]
0x140017afd  call    _guard_dispatch_icall
0x140017b02  nop
0x140017b03  xor     ebx, ebx
0x140017b05  mov     [r13+0], rdi
0x140017b09  xor     esi, esi
0x140017b0b  test    rbx, rbx
0x140017b0e  jz      short loc_140017B25
0x140017b10  mov     rcx, rbx; this
0x140017b13  call    ??1WUOptionalSessionInfoWrapper@SessionDataUtil@@QEAA@XZ; SessionDataUtil::WUOptionalSessionInfoWrapper::~WUOptionalSessionInfoWrapper(void)
0x140017b18  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x140017b1d  mov     rcx, rbx; void *
0x140017b20  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017b25  mov     eax, esi
0x140017b27  mov     rcx, [rbp+var_10]
0x140017b2b  xor     rcx, rsp; StackCookie
0x140017b2e  call    __security_check_cookie
0x140017b33  add     rsp, 60h
0x140017b37  pop     r15
0x140017b39  pop     r13
0x140017b3b  pop     r12
0x140017b3d  pop     rdi
0x140017b3e  pop     rsi
0x140017b3f  pop     rbx
0x140017b40  pop     rbp
0x140017b41  retn
```
