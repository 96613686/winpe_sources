# CUHOSDeploymentHandler::ParseEx(IUnknown *,ISusParse2 *,tagDSDataBlob *)

- ea: `0x180016e70`
- end: `0x1800170a4`
- name: `?ParseEx@CUHOSDeploymentHandler@@UEAAJPEAUIUnknown@@PEAUISusParse2@@PEAUtagDSDataBlob@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(CUHOSDeploymentHandler *__hidden this, struct IUnknown *, struct ISusParse2 *, struct tagDSDataBlob *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003950`
- `0x180016e70`
- `0x180042630`
- `0x180049260`
- `0x1800496a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016ff3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016ff3`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f4c`
- `OLEAUT32!__imp_SysFreeString` at `0x180017041`
- `OLEAUT32!__imp_SysFreeString` at `0x180017083`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f4c`
- `OLEAUT32!__imp_SysFreeString` at `0x180017041`
- `OLEAUT32!__imp_SysFreeString` at `0x180017083`
- `OLEAUT32!__imp_SysStringLen` at `0x180016fa6`
- `OLEAUT32!__imp_SysStringLen` at `0x180016fa6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUHOSDeploymentHandler::ParseEx(
        CUHOSDeploymentHandler *this,
        struct IUnknown *a2,
        struct ISusParse2 *a3,
        struct tagDSDataBlob *a4)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v8; // eax
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, BSTR *); // rdi
  int v11; // eax
  UINT v12; // ebx
  void *v13; // rax
  __int64 v14; // [rsp+20h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]

  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 74;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Handler\\UHOSDeployment.cpp",
      (const char *)v5,
      v14);
    return v5;
  }
  if ( !a4 )
  {
    v5 = -2147467261;
    v6 = 78;
    goto LABEL_3;
  }
  bstrString = 0;
  v14 = 0;
  *(_OWORD *)a4 = 0;
  v8 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
         &v14);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13A,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\dsutil\\dsmisc.cpp",
      (const char *)(unsigned int)v8,
      v14);
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v14 = 0;
    }
LABEL_21:
    SysFreeString(bstrString);
    v6 = 80;
    goto LABEL_3;
  }
  v9 = v14;
  v10 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v14 + 272LL);
  SysFreeString(bstrString);
  v11 = v10(v9, &bstrString);
  v5 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\dsutil\\dsmisc.cpp",
      (const char *)(unsigned int)v11,
      v14);
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v14 = 0;
    }
    goto LABEL_21;
  }
  v12 = 2 * SysStringLen(bstrString);
  if ( !v12 )
  {
    v5 = -2145124338;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x141,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\dsutil\\dsmisc.cpp",
      (const char *)0x8024000ELL,
      v14);
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v14 = 0;
    }
    goto LABEL_21;
  }
  v13 = CoTaskMemAlloc(v12);
  *((_QWORD *)a4 + 1) = v13;
  if ( !v13 )
  {
    v5 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\dsutil\\dsmisc.cpp",
      (const char *)0x8007000ELL,
      v14);
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v14 = 0;
    }
    goto LABEL_21;
  }
  memmove(v13, bstrString, v12);
  *(_DWORD *)a4 = v12;
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  SysFreeString(bstrString);
  return 0;
}

```

## disassembly

```asm
0x180016e70  mov     [rsp-18h+arg_0], rbx
0x180016e75  push    rbp
0x180016e76  push    rsi
0x180016e77  push    rdi
0x180016e78  mov     rbp, rsp
0x180016e7b  sub     rsp, 40h
0x180016e7f  mov     rax, cs:__security_cookie
0x180016e86  xor     rax, rsp
0x180016e89  mov     [rbp+var_10], rax
0x180016e8d  mov     rsi, r9
0x180016e90  mov     r9, rdx
0x180016e93  test    rdx, rdx
0x180016e96  jnz     short loc_180016EBB
0x180016e98  mov     ebx, 80070057h
0x180016e9d  lea     edx, [r9+4Ah]; void *
0x180016ea1  mov     rcx, [rbp+18h]; this
0x180016ea5  mov     r9d, ebx; char *
0x180016ea8  lea     r8, aCW1SSrcClientE_9; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180016eaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016eb4  mov     eax, ebx
0x180016eb6  jmp     loc_18001708B
0x180016ebb  test    rsi, rsi
0x180016ebe  jnz     short loc_180016ECA
0x180016ec0  mov     ebx, 80004003h
0x180016ec5  lea     edx, [rsi+4Eh]
0x180016ec8  jmp     short loc_180016EA1
0x180016eca  mov     [rbp+bstrString], 0
0x180016ed2  mov     [rbp+var_20], 0
0x180016eda  xorps   xmm0, xmm0
0x180016edd  movups  xmmword ptr [rsi], xmm0
0x180016ee0  mov     rax, [rdx]
0x180016ee3  lea     r8, [rbp+var_20]
0x180016ee7  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x180016eee  mov     rcx, r9
0x180016ef1  mov     rax, [rax]
0x180016ef4  call    _guard_dispatch_icall
0x180016ef9  mov     ebx, eax
0x180016efb  test    eax, eax
0x180016efd  jns     short loc_180016F3A
0x180016eff  mov     rcx, [rbp+18h]; this
0x180016f03  mov     r9d, eax; char *
0x180016f06  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\dsutil"...
0x180016f0d  mov     edx, 13Ah; void *
0x180016f12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016f17  nop
0x180016f18  mov     rcx, [rbp+var_20]
0x180016f1c  test    rcx, rcx
0x180016f1f  jz      short loc_180016F35
0x180016f21  mov     rax, [rcx]
0x180016f24  mov     rax, [rax+10h]
0x180016f28  call    _guard_dispatch_icall
0x180016f2d  mov     [rbp+var_20], 0
0x180016f35  jmp     loc_18001703D
0x180016f3a  mov     rbx, [rbp+var_20]
0x180016f3e  mov     rax, [rbx]
0x180016f41  mov     rdi, [rax+110h]
0x180016f48  mov     rcx, [rbp+bstrString]; bstrString
0x180016f4c  call    cs:__imp_SysFreeString
0x180016f52  lea     rdx, [rbp+bstrString]
0x180016f56  mov     rcx, rbx
0x180016f59  mov     rax, rdi
0x180016f5c  call    _guard_dispatch_icall
0x180016f61  mov     ebx, eax
0x180016f63  test    eax, eax
0x180016f65  jns     short loc_180016FA2
0x180016f67  mov     rcx, [rbp+18h]; this
0x180016f6b  mov     r9d, eax; char *
0x180016f6e  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\dsutil"...
0x180016f75  mov     edx, 13Bh; void *
0x180016f7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016f7f  nop
0x180016f80  mov     rcx, [rbp+var_20]
0x180016f84  test    rcx, rcx
0x180016f87  jz      short loc_180016F9D
0x180016f89  mov     rax, [rcx]
0x180016f8c  mov     rax, [rax+10h]
0x180016f90  call    _guard_dispatch_icall
0x180016f95  mov     [rbp+var_20], 0
0x180016f9d  jmp     loc_18001703D
0x180016fa2  mov     rcx, [rbp+bstrString]; pbstr
0x180016fa6  call    cs:__imp_SysStringLen
0x180016fac  mov     ebx, eax
0x180016fae  add     ebx, ebx
0x180016fb0  jnz     short loc_180016FEF
0x180016fb2  mov     rcx, [rbp+18h]; this
0x180016fb6  mov     ebx, 8024000Eh
0x180016fbb  mov     r9d, ebx; char *
0x180016fbe  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\dsutil"...
0x180016fc5  mov     edx, 141h; void *
0x180016fca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016fcf  nop
0x180016fd0  mov     rcx, [rbp+var_20]
0x180016fd4  test    rcx, rcx
0x180016fd7  jz      short loc_180016FED
0x180016fd9  mov     rax, [rcx]
0x180016fdc  mov     rax, [rax+10h]
0x180016fe0  call    _guard_dispatch_icall
0x180016fe5  mov     [rbp+var_20], 0
0x180016fed  jmp     short loc_18001703D
0x180016fef  mov     edi, ebx
0x180016ff1  mov     ecx, ebx; cb
0x180016ff3  call    cs:__imp_CoTaskMemAlloc
0x180016ff9  mov     [rsi+8], rax
0x180016ffd  test    rax, rax
0x180017000  jnz     short loc_180017051
0x180017002  mov     rcx, [rbp+18h]; this
0x180017006  mov     ebx, 8007000Eh
0x18001700b  mov     r9d, ebx; char *
0x18001700e  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\dsutil"...
0x180017015  mov     edx, 147h; void *
0x18001701a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001701f  nop
0x180017020  mov     rcx, [rbp+var_20]
0x180017024  test    rcx, rcx
0x180017027  jz      short loc_18001703D
0x180017029  mov     rax, [rcx]
0x18001702c  mov     rax, [rax+10h]
0x180017030  call    _guard_dispatch_icall
0x180017035  mov     [rbp+var_20], 0
0x18001703d  mov     rcx, [rbp+bstrString]; bstrString
0x180017041  call    cs:__imp_SysFreeString
0x180017047  mov     edx, 50h ; 'P'
0x18001704c  jmp     loc_180016EA1
0x180017051  mov     r8, rdi; Size
0x180017054  mov     rdx, [rbp+bstrString]; Src
0x180017058  mov     rcx, rax; void *
0x18001705b  call    memmove
0x180017060  mov     [rsi], ebx
0x180017062  mov     rcx, [rbp+var_20]
0x180017066  test    rcx, rcx
0x180017069  jz      short loc_18001707F
0x18001706b  mov     rax, [rcx]
0x18001706e  mov     rax, [rax+10h]
0x180017072  call    _guard_dispatch_icall
0x180017077  mov     [rbp+var_20], 0
0x18001707f  mov     rcx, [rbp+bstrString]; bstrString
0x180017083  call    cs:__imp_SysFreeString
0x180017089  xor     eax, eax
0x18001708b  mov     rcx, [rbp+var_10]
0x18001708f  xor     rcx, rsp; StackCookie
0x180017092  call    __security_check_cookie
0x180017097  mov     rbx, [rsp+40h+arg_0]
0x18001709c  add     rsp, 40h
0x1800170a0  pop     rdi
0x1800170a1  pop     rsi
0x1800170a2  pop     rbp
0x1800170a3  retn
```
