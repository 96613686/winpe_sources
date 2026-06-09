# OSDeploymentRemote::RemoteDeploymentSession::GenerateDownloadRequest(IDeploymentInformation *,IDeploymentProgress *,RemoteDeploymentDownloadRequest * *)

- ea: `0x140012990`
- end: `0x140012bd8`
- name: `?GenerateDownloadRequest@RemoteDeploymentSession@OSDeploymentRemote@@UEAAJPEAUIDeploymentInformation@@PEAUIDeploymentProgress@@PEAPEAURemoteDeploymentDownloadRequest@@@Z`
- size: `584`
- prototype: `__int64 __fastcall(OSDeploymentRemote::RemoteDeploymentSession *__hidden this, struct IDeploymentInformation *, struct IDeploymentProgress *, struct RemoteDeploymentDownloadRequest **)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140002ac0`
- `0x14000fd28`
- `0x140011ca0`
- `0x140012990`
- `0x140012be0`
- `0x14001aa60`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012bb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012bb3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OSDeploymentRemote::RemoteDeploymentSession::GenerateDownloadRequest(
        OSDeploymentRemote::RemoteDeploymentSession *this,
        struct IDeploymentInformation *a2,
        struct IDeploymentProgress *a3,
        struct RemoteDeploymentDownloadRequest **a4)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  LPVOID v13; // r12
  int v14; // eax
  __int64 v15; // rdx
  unsigned __int64 v16; // r9
  __int64 *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  unsigned __int64 v20; // r9
  __int64 v21; // rdx
  int v22; // eax
  int v24; // [rsp+20h] [rbp-48h]
  int v25; // [rsp+20h] [rbp-48h]
  _QWORD v26[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v27; // [rsp+40h] [rbp-28h]
  struct IDeploymentDownloadRequest *v28; // [rsp+48h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]

  if ( !a2 )
  {
    v8 = 308;
LABEL_3:
    v9 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
      (const char *)v9,
      v24);
    return v9;
  }
  if ( !a3 )
  {
    v8 = 309;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v9 = -2147467261;
    v8 = 310;
    goto LABEL_4;
  }
  if ( !*((_QWORD *)this + 4) )
  {
    v9 = -2145112065;
    v8 = 311;
    goto LABEL_4;
  }
  *a4 = 0;
  pv = 0;
  v10 = (__int64 *)*((_QWORD *)this + 4);
  v11 = *v10;
  pv = 0;
  v12 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v11 + 24))(v10, &pv);
  v9 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13E,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
      (const char *)(unsigned int)v12,
      v24);
    goto LABEL_28;
  }
  v27 = 0;
  v26[0] = (char *)this + 40;
  v13 = pv;
  v26[1] = pv;
  v14 = (*(__int64 (__fastcall **)(char *, LPVOID, struct IDeploymentInformation *))(*((_QWORD *)this + 12) + 24LL))(
          (char *)this + 96,
          pv,
          a2);
  v9 = v14;
  if ( v14 >= 0 )
  {
    LOBYTE(v27) = 1;
    v9 = (*(__int64 (__fastcall **)(char *, LPVOID, struct IDeploymentProgress *))(*((_QWORD *)this + 12) + 32LL))(
           (char *)this + 96,
           v13,
           a3);
    v16 = v9;
    if ( (v9 & 0x80000000) != 0 )
    {
      v15 = 31;
      goto LABEL_17;
    }
    BYTE1(v27) = 1;
    WUTrace(0, 0, 4096, 4);
    v28 = 0;
    v17 = (__int64 *)*((_QWORD *)this + 4);
    v18 = *v17;
    v28 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64 *, struct IDeploymentDownloadRequest **))(v18 + 32))(v17, &v28);
    v9 = v19;
    if ( v19 >= 0 )
    {
      v22 = OSDeploymentRemote::RemoteDeploymentSession::BuildRemoteDeploymentDownloadRequest(this, v28, a4);
      v9 = v22;
      if ( v22 >= 0 )
      {
        v9 = 0;
LABEL_25:
        if ( v28 )
          (*(void (__fastcall **)(struct IDeploymentDownloadRequest *))(*(_QWORD *)v28 + 16LL))(v28);
        goto LABEL_27;
      }
      v20 = (unsigned int)v22;
      v21 = 339;
    }
    else
    {
      if ( (unsigned int)(v19 + 2147024894) <= 1 )
        goto LABEL_25;
      v20 = (unsigned int)v19;
      v21 = 336;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
      (const char *)v20,
      0);
    goto LABEL_25;
  }
  v15 = 28;
  v16 = (unsigned int)v14;
LABEL_17:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
    (const char *)v16,
    v24);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x141,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
    (const char *)v9,
    v25);
LABEL_27:
  OSDeploymentRemote::details::InformationFactoryWrapper::~InformationFactoryWrapper((OSDeploymentRemote::details::InformationFactoryWrapper *)v26);
LABEL_28:
  if ( pv )
    CoTaskMemFree(pv);
  return v9;
}

```

## disassembly

```asm
0x140012990  push    rbp
0x140012992  push    rbx
0x140012993  push    rsi
0x140012994  push    rdi
0x140012995  push    r12
0x140012997  push    r13
0x140012999  push    r14
0x14001299b  push    r15
0x14001299d  mov     rbp, rsp
0x1400129a0  sub     rsp, 68h
0x1400129a4  mov     rax, cs:__security_cookie
0x1400129ab  xor     rax, rsp
0x1400129ae  mov     [rbp+var_10], rax
0x1400129b2  mov     rsi, r9
0x1400129b5  mov     r14, r8
0x1400129b8  mov     r15, rdx
0x1400129bb  mov     rdi, rcx
0x1400129be  xor     r12d, r12d
0x1400129c1  test    rdx, rdx
0x1400129c4  jnz     short loc_1400129E8
0x1400129c6  mov     edx, 134h; void *
0x1400129cb  mov     ebx, 80070057h
0x1400129d0  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1400129d7  mov     r9d, ebx; char *
0x1400129da  mov     rcx, [rbp+40h]; this
0x1400129de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400129e3  jmp     loc_140012BB9
0x1400129e8  test    r14, r14
0x1400129eb  jnz     short loc_1400129F4
0x1400129ed  mov     edx, 135h
0x1400129f2  jmp     short loc_1400129CB
0x1400129f4  test    rsi, rsi
0x1400129f7  jnz     short loc_140012A05
0x1400129f9  mov     ebx, 80004003h
0x1400129fe  mov     edx, 136h
0x140012a03  jmp     short loc_1400129D0
0x140012a05  cmp     [rcx+20h], r12
0x140012a09  jnz     short loc_140012A17
0x140012a0b  mov     ebx, 80242FFFh
0x140012a10  mov     edx, 137h
0x140012a15  jmp     short loc_1400129D0
0x140012a17  mov     [r9], r12
0x140012a1a  mov     [rbp+pv], r12
0x140012a1e  mov     rcx, [rcx+20h]
0x140012a22  mov     rax, [rcx]
0x140012a25  mov     [rbp+pv], r12
0x140012a29  lea     rdx, [rbp+pv]
0x140012a2d  mov     rax, [rax+18h]
0x140012a31  call    _guard_dispatch_icall
0x140012a36  mov     ebx, eax
0x140012a38  test    eax, eax
0x140012a3a  jns     short loc_140012A59
0x140012a3c  mov     rcx, [rbp+40h]; this
0x140012a40  mov     r9d, eax; char *
0x140012a43  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140012a4a  mov     edx, 13Eh; void *
0x140012a4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012a54  jmp     loc_140012BAA
0x140012a59  xorps   xmm0, xmm0
0x140012a5c  xor     eax, eax
0x140012a5e  movups  [rbp+var_38], xmm0
0x140012a62  mov     [rbp+var_28], rax
0x140012a66  lea     r13, [rdi+28h]
0x140012a6a  mov     qword ptr [rbp+var_38], r13
0x140012a6e  mov     r12, [rbp+pv]
0x140012a72  mov     qword ptr [rbp+var_38+8], r12
0x140012a76  mov     word ptr [rbp+var_28], ax
0x140012a7a  lea     rcx, [r13+38h]
0x140012a7e  mov     rax, [r13+38h]
0x140012a82  mov     r8, r15
0x140012a85  mov     rdx, r12
0x140012a88  mov     rax, [rax+18h]
0x140012a8c  call    _guard_dispatch_icall
0x140012a91  mov     ebx, eax
0x140012a93  test    eax, eax
0x140012a95  jns     short loc_140012AA1
0x140012a97  mov     edx, 1Ch
0x140012a9c  mov     r9d, eax
0x140012a9f  jmp     short loc_140012ACD
0x140012aa1  mov     byte ptr [rbp+var_28], 1
0x140012aa5  mov     rax, [r13+38h]
0x140012aa9  mov     r8, r14
0x140012aac  mov     rdx, r12
0x140012aaf  lea     rcx, [r13+38h]
0x140012ab3  mov     rax, [rax+20h]
0x140012ab7  call    _guard_dispatch_icall
0x140012abc  mov     ebx, eax
0x140012abe  mov     r9d, eax; char *
0x140012ac1  xor     r12d, r12d
0x140012ac4  test    eax, eax
0x140012ac6  jns     short loc_140012AFA
0x140012ac8  lea     edx, [r12+1Fh]; void *
0x140012acd  mov     rcx, [rbp+40h]; this
0x140012ad1  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140012ad8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012add  mov     rcx, [rbp+40h]; this
0x140012ae1  mov     r9d, ebx; char *
0x140012ae4  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140012aeb  mov     edx, 141h; void *
0x140012af0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012af5  jmp     loc_140012BA0
0x140012afa  mov     byte ptr [rbp+var_28+1], 1
0x140012afe  lea     rax, aInvokingIdeplo; "Invoking IDeploymentSession::GenerateDo"...
0x140012b05  mov     [rsp+68h+var_40], rax
0x140012b0a  mov     qword ptr [rsp+68h+var_48], r12; int
0x140012b0f  xor     edx, edx
0x140012b11  xor     ecx, ecx
0x140012b13  lea     r9d, [rdx+4]
0x140012b17  mov     r8d, 1000h
0x140012b1d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140012b22  mov     [rbp+var_20], r12
0x140012b26  mov     rcx, [rdi+20h]
0x140012b2a  mov     rax, [rcx]
0x140012b2d  mov     [rbp+var_20], r12
0x140012b31  lea     rdx, [rbp+var_20]
0x140012b35  mov     rax, [rax+20h]
0x140012b39  call    _guard_dispatch_icall
0x140012b3e  mov     ebx, eax
0x140012b40  test    eax, eax
0x140012b42  jns     short loc_140012B58
0x140012b44  add     eax, 7FF8FFFEh
0x140012b49  cmp     eax, 1
0x140012b4c  jbe     short loc_140012B8A
0x140012b4e  mov     r9d, ebx
0x140012b51  mov     edx, 150h
0x140012b56  jmp     short loc_140012B75
0x140012b58  mov     r8, rsi; struct RemoteDeploymentDownloadRequest **
0x140012b5b  mov     rdx, [rbp+var_20]; struct IDeploymentDownloadRequest *
0x140012b5f  mov     rcx, rdi; this
0x140012b62  call    ?BuildRemoteDeploymentDownloadRequest@RemoteDeploymentSession@OSDeploymentRemote@@AEAAJAEAUIDeploymentDownloadRequest@@PEAPEAURemoteDeploymentDownloadRequest@@@Z; OSDeploymentRemote::RemoteDeploymentSession::BuildRemoteDeploymentDownloadRequest(IDeploymentDownloadRequest &,RemoteDeploymentDownloadRequest * *)
0x140012b67  mov     ebx, eax
0x140012b69  test    eax, eax
0x140012b6b  jns     short loc_140012B87
0x140012b6d  mov     r9d, eax; char *
0x140012b70  mov     edx, 153h; void *
0x140012b75  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140012b7c  mov     rcx, [rbp+40h]; this
0x140012b80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012b85  jmp     short loc_140012B8A
0x140012b87  mov     ebx, r12d
0x140012b8a  mov     rcx, [rbp+var_20]
0x140012b8e  test    rcx, rcx
0x140012b91  jz      short loc_140012BA0
0x140012b93  mov     rax, [rcx]
0x140012b96  mov     rax, [rax+10h]
0x140012b9a  call    _guard_dispatch_icall
0x140012b9f  nop
0x140012ba0  lea     rcx, [rbp+var_38]; this
0x140012ba4  call    ??1InformationFactoryWrapper@details@OSDeploymentRemote@@QEAA@XZ; OSDeploymentRemote::details::InformationFactoryWrapper::~InformationFactoryWrapper(void)
0x140012ba9  nop
0x140012baa  mov     rcx, [rbp+pv]; pv
0x140012bae  test    rcx, rcx
0x140012bb1  jz      short loc_140012BB9
0x140012bb3  call    cs:__imp_CoTaskMemFree
0x140012bb9  mov     eax, ebx
0x140012bbb  mov     rcx, [rbp+var_10]
0x140012bbf  xor     rcx, rsp; StackCookie
0x140012bc2  call    __security_check_cookie
0x140012bc7  add     rsp, 68h
0x140012bcb  pop     r15
0x140012bcd  pop     r14
0x140012bcf  pop     r13
0x140012bd1  pop     r12
0x140012bd3  pop     rdi
0x140012bd4  pop     rsi
0x140012bd5  pop     rbx
0x140012bd6  pop     rbp
0x140012bd7  retn
```
