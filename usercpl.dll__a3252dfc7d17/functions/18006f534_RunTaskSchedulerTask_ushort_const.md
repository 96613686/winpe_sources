# RunTaskSchedulerTask(ushort const *)

- ea: `0x18006f534`
- end: `0x18006f888`
- name: `?RunTaskSchedulerTask@@YAJPEBG@Z`
- size: `852`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006feac`

## callees

- `0x180006a74`
- `0x18006f534`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006f574`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006f574`
- `OLEAUT32!__imp_SysAllocString` at `0x18006f685`
- `OLEAUT32!__imp_SysAllocString` at `0x18006f685`
- `OLEAUT32!__imp_SysFreeString` at `0x18006f727`
- `OLEAUT32!__imp_SysFreeString` at `0x18006f78d`
- `OLEAUT32!__imp_SysFreeString` at `0x18006f727`
- `OLEAUT32!__imp_SysFreeString` at `0x18006f78d`
- `OLEAUT32!__imp_VariantClear` at `0x18006f610`
- `OLEAUT32!__imp_VariantClear` at `0x18006f670`
- `OLEAUT32!__imp_VariantClear` at `0x18006f7d1`
- `OLEAUT32!__imp_VariantClear` at `0x18006f610`
- `OLEAUT32!__imp_VariantClear` at `0x18006f670`
- `OLEAUT32!__imp_VariantClear` at `0x18006f7d1`

## string_xrefs

- `0x18006f676`: `\Microsoft\Windows\Shell\CreateObjectTask`
- `0x18006f5e8`: `shell\lib\comtaskserverutil.cpp`
- `0x18006f61a`: `shell\lib\comtaskserverutil.cpp`
- `0x18006f697`: `shell\lib\comtaskserverutil.cpp`
- `0x18006f700`: `shell\lib\comtaskserverutil.cpp`
- `0x18006f731`: `shell\lib\comtaskserverutil.cpp`
- `0x18006f7df`: `shell\lib\comtaskserverutil.cpp`

## pseudocode

```c
__int64 __fastcall RunTaskSchedulerTask(const unsigned __int16 *a1)
{
  HRESULT v1; // eax
  unsigned int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 (__fastcall *v5)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *); // rax
  __int64 *v7; // rdi
  __int64 *v8; // rbx
  OLECHAR *v9; // rdi
  unsigned int v10; // esi
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 (__fastcall *v15)(__int64 *, VARIANTARG *, __int64 *); // rax
  int v16; // edi
  int *ppv; // [rsp+20h] [rbp-69h]
  int ppva; // [rsp+20h] [rbp-69h]
  int ppvb; // [rsp+20h] [rbp-69h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-59h] BYREF
  VARIANTARG v21; // [rsp+50h] [rbp-39h] BYREF
  int v22[4]; // [rsp+70h] [rbp-19h] BYREF
  IRecordInfo *pRecInfo; // [rsp+80h] [rbp-9h]
  VARIANTARG v24; // [rsp+90h] [rbp+7h] BYREF
  VARIANTARG v25; // [rsp+B0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  LPVOID v27; // [rsp+F0h] [rbp+67h] BYREF
  __int64 *v28; // [rsp+F8h] [rbp+6Fh] BYREF
  __int64 v29; // [rsp+100h] [rbp+77h] BYREF

  pvarg.vt = 0;
  v27 = 0;
  v1 = CoCreateInstance(
         &GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd,
         0,
         1u,
         &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
         &v27);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 31;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
      (const char *)(unsigned int)v1,
      (int)ppv);
    if ( v27 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
    VariantClear(&pvarg);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
      (const char *)v2,
      ppva);
    return v2;
  }
  ppv = v22;
  *(_OWORD *)v22 = *(_OWORD *)&pvarg.vt;
  v4 = *(_QWORD *)v27;
  pRecInfo = pvarg.pRecInfo;
  v24 = pvarg;
  v5 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *))(v4 + 80);
  v25 = pvarg;
  v21 = pvarg;
  v1 = v5(v27, &v21, &v25, &v24);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 32;
    goto LABEL_5;
  }
  v7 = (__int64 *)v27;
  if ( v27 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 8LL))(v27);
    v8 = v7;
    v7 = (__int64 *)v27;
  }
  else
  {
    v8 = 0;
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64 *))(*v7 + 16))(v7);
  VariantClear(&pvarg);
  v28 = 0;
  v9 = SysAllocString(L"\\Microsoft\\Windows\\Shell\\CreateObjectTask");
  if ( !v9 )
  {
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
      (const char *)0x8007000ELL,
      (int)v22);
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
      (const char *)v10,
      ppvb);
    if ( v28 )
      (*(void (__fastcall **)(__int64 *))(*v28 + 16))(v28);
    if ( v8 )
      (*(void (__fastcall **)(__int64 *))(*v8 + 16))(v8);
    return v10;
  }
  v11 = *v8;
  v27 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, LPVOID *))(v11 + 56))(v8, 0, &v27);
  v10 = v12;
  if ( v12 < 0 )
  {
    v13 = 46;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
      (const char *)(unsigned int)v12,
      (int)v22);
    if ( v27 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
    SysFreeString(v9);
    goto LABEL_22;
  }
  v12 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 **))(*(_QWORD *)v27 + 104LL))(v27, v9, &v28);
  v10 = v12;
  if ( v12 < 0 )
  {
    v13 = 47;
    goto LABEL_19;
  }
  if ( v27 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
  SysFreeString(v9);
  v29 = 0;
  v21.pRecInfo = pvarg.pRecInfo;
  v14 = *v28;
  pvarg.vt = 0;
  v15 = *(__int64 (__fastcall **)(__int64 *, VARIANTARG *, __int64 *))(v14 + 96);
  *(_OWORD *)&v21.vt = *(_OWORD *)&pvarg.vt;
  v16 = v15(v28, &v21, &v29);
  VariantClear(&pvarg);
  if ( v16 >= 0 )
  {
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    if ( v28 )
      (*(void (__fastcall **)(__int64 *))(*v28 + 16))(v28);
    if ( v8 )
      (*(void (__fastcall **)(__int64 *))(*v8 + 16))(v8);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
      (const char *)(unsigned int)v16,
      (int)v22);
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    if ( v28 )
      (*(void (__fastcall **)(__int64 *))(*v28 + 16))(v28);
    if ( v8 )
      (*(void (__fastcall **)(__int64 *))(*v8 + 16))(v8);
    return (unsigned int)v16;
  }
}

```

## disassembly

```asm
0x18006f534  mov     [rsp-8+arg_18], rbx
0x18006f539  mov     [rsp-8+arg_0], rcx
0x18006f53e  push    rbp
0x18006f53f  push    rsi
0x18006f540  push    rdi
0x18006f541  lea     rbp, [rsp-47h]
0x18006f546  sub     rsp, 0D0h
0x18006f54d  xor     eax, eax
0x18006f54f  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18006f556  xor     edx, edx; pUnkOuter
0x18006f558  mov     word ptr [rbp+57h+pvarg], ax
0x18006f55c  mov     [rbp+57h+arg_0], rax
0x18006f560  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x18006f567  lea     rax, [rbp+57h+arg_0]
0x18006f56b  mov     [rsp+0E0h+ppv], rax; ppv
0x18006f570  lea     r8d, [rdx+1]; dwClsContext
0x18006f574  call    cs:__imp_CoCreateInstance
0x18006f57a  mov     ebx, eax
0x18006f57c  test    eax, eax
0x18006f57e  jns     short loc_18006F587
0x18006f580  mov     edx, 1Fh
0x18006f585  jmp     short loc_18006F5E4
0x18006f587  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18006f58b  lea     rdx, [rbp+57h+var_70]
0x18006f58f  mov     rcx, [rbp+57h+arg_0]
0x18006f593  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18006f598  lea     r9, [rbp+57h+var_50]
0x18006f59c  mov     [rsp+0E0h+ppv], rdx; int
0x18006f5a1  lea     r8, [rbp+57h+var_30]
0x18006f5a5  lea     rdx, [rbp+57h+var_90]
0x18006f5a9  movaps  xmmword ptr [rbp+57h+var_70], xmm1
0x18006f5ad  mov     rax, [rcx]
0x18006f5b0  movsd   [rbp+57h+var_60], xmm0
0x18006f5b5  movaps  [rbp+57h+var_50], xmm1
0x18006f5b9  movsd   [rbp+57h+var_40], xmm0
0x18006f5be  mov     rax, [rax+50h]
0x18006f5c2  movaps  [rbp+57h+var_30], xmm1
0x18006f5c6  movsd   [rbp+57h+var_20], xmm0
0x18006f5cb  movaps  [rbp+57h+var_90], xmm1
0x18006f5cf  movsd   [rbp+57h+var_80], xmm0
0x18006f5d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f5d9  mov     ebx, eax
0x18006f5db  test    eax, eax
0x18006f5dd  jns     short loc_18006F635
0x18006f5df  mov     edx, 20h ; ' '; void *
0x18006f5e4  mov     rcx, [rbp+5Fh]; this
0x18006f5e8  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18006f5ef  mov     r9d, eax; char *
0x18006f5f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f5f7  mov     rcx, [rbp+57h+arg_0]
0x18006f5fb  test    rcx, rcx
0x18006f5fe  jz      short loc_18006F60C
0x18006f600  mov     rax, [rcx]
0x18006f603  mov     rax, [rax+10h]
0x18006f607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f60c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18006f610  call    cs:__imp_VariantClear
0x18006f616  mov     rcx, [rbp+5Fh]; this
0x18006f61a  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18006f621  mov     r9d, ebx; char *
0x18006f624  mov     edx, 37h ; '7'; void *
0x18006f629  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f62e  mov     eax, ebx
0x18006f630  jmp     loc_18006F875
0x18006f635  mov     rdi, [rbp+57h+arg_0]
0x18006f639  test    rdi, rdi
0x18006f63c  jz      short loc_18006F656
0x18006f63e  mov     rax, [rdi]
0x18006f641  mov     rcx, rdi
0x18006f644  mov     rax, [rax+8]
0x18006f648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f64d  mov     rbx, rdi
0x18006f650  mov     rdi, [rbp+57h+arg_0]
0x18006f654  jmp     short loc_18006F658
0x18006f656  xor     ebx, ebx
0x18006f658  test    rdi, rdi
0x18006f65b  jz      short loc_18006F66C
0x18006f65d  mov     rax, [rdi]
0x18006f660  mov     rcx, rdi
0x18006f663  mov     rax, [rax+10h]
0x18006f667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f66c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18006f670  call    cs:__imp_VariantClear
0x18006f676  lea     rcx, psz; "\\Microsoft\\Windows\\Shell\\CreateObje"...
0x18006f67d  mov     [rbp+57h+arg_8], 0
0x18006f685  call    cs:__imp_SysAllocString
0x18006f68b  mov     rdi, rax
0x18006f68e  test    rax, rax
0x18006f691  jnz     short loc_18006F6B0
0x18006f693  mov     rcx, [rbp+5Fh]; this
0x18006f697  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18006f69e  mov     esi, 8007000Eh
0x18006f6a3  lea     edx, [rax+2Bh]; void *
0x18006f6a6  mov     r9d, esi; char *
0x18006f6a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f6ae  jmp     short loc_18006F72D
0x18006f6b0  mov     rax, [rbx]
0x18006f6b3  lea     r8, [rbp+57h+arg_0]
0x18006f6b7  xor     edx, edx
0x18006f6b9  mov     [rbp+57h+arg_0], 0
0x18006f6c1  mov     rcx, rbx
0x18006f6c4  mov     rax, [rax+38h]
0x18006f6c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f6cd  mov     esi, eax
0x18006f6cf  test    eax, eax
0x18006f6d1  jns     short loc_18006F6DA
0x18006f6d3  mov     edx, 2Eh ; '.'
0x18006f6d8  jmp     short loc_18006F6FC
0x18006f6da  mov     rcx, [rbp+57h+arg_0]
0x18006f6de  lea     r8, [rbp+57h+arg_8]
0x18006f6e2  mov     rdx, rdi
0x18006f6e5  mov     rax, [rcx]
0x18006f6e8  mov     rax, [rax+68h]
0x18006f6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f6f1  mov     esi, eax
0x18006f6f3  test    eax, eax
0x18006f6f5  jns     short loc_18006F775
0x18006f6f7  mov     edx, 2Fh ; '/'; void *
0x18006f6fc  mov     rcx, [rbp+5Fh]; this
0x18006f700  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18006f707  mov     r9d, eax; char *
0x18006f70a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f70f  mov     rcx, [rbp+57h+arg_0]
0x18006f713  test    rcx, rcx
0x18006f716  jz      short loc_18006F724
0x18006f718  mov     rax, [rcx]
0x18006f71b  mov     rax, [rax+10h]
0x18006f71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f724  mov     rcx, rdi; bstrString
0x18006f727  call    cs:__imp_SysFreeString
0x18006f72d  mov     rcx, [rbp+5Fh]; this
0x18006f731  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18006f738  mov     r9d, esi; char *
0x18006f73b  mov     edx, 3Ah ; ':'; void *
0x18006f740  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f745  mov     rcx, [rbp+57h+arg_8]
0x18006f749  test    rcx, rcx
0x18006f74c  jz      short loc_18006F75A
0x18006f74e  mov     rax, [rcx]
0x18006f751  mov     rax, [rax+10h]
0x18006f755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f75a  test    rbx, rbx
0x18006f75d  jz      short loc_18006F76E
0x18006f75f  mov     rcx, [rbx]
0x18006f762  mov     rax, [rcx+10h]
0x18006f766  mov     rcx, rbx
0x18006f769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f76e  mov     eax, esi
0x18006f770  jmp     loc_18006F875
0x18006f775  mov     rcx, [rbp+57h+arg_0]
0x18006f779  test    rcx, rcx
0x18006f77c  jz      short loc_18006F78A
0x18006f77e  mov     rax, [rcx]
0x18006f781  mov     rax, [rax+10h]
0x18006f785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f78a  mov     rcx, rdi; bstrString
0x18006f78d  call    cs:__imp_SysFreeString
0x18006f793  mov     rcx, [rbp+57h+arg_8]
0x18006f797  lea     r8, [rbp+57h+arg_10]
0x18006f79b  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18006f7a0  xor     edx, edx
0x18006f7a2  mov     [rbp+57h+arg_10], 0
0x18006f7aa  movsd   [rbp+57h+var_80], xmm1
0x18006f7af  mov     rax, [rcx]
0x18006f7b2  mov     word ptr [rbp+57h+pvarg], dx
0x18006f7b6  lea     rdx, [rbp+57h+var_90]
0x18006f7ba  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18006f7be  mov     rax, [rax+60h]
0x18006f7c2  movaps  [rbp+57h+var_90], xmm0
0x18006f7c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f7cb  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18006f7cf  mov     edi, eax
0x18006f7d1  call    cs:__imp_VariantClear
0x18006f7d7  test    edi, edi
0x18006f7d9  jns     short loc_18006F835
0x18006f7db  mov     rcx, [rbp+5Fh]; this
0x18006f7df  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18006f7e6  mov     r9d, edi; char *
0x18006f7e9  mov     edx, 3Dh ; '='; void *
0x18006f7ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f7f3  mov     rcx, [rbp+57h+arg_10]
0x18006f7f7  test    rcx, rcx
0x18006f7fa  jz      short loc_18006F808
0x18006f7fc  mov     rax, [rcx]
0x18006f7ff  mov     rax, [rax+10h]
0x18006f803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f808  mov     rcx, [rbp+57h+arg_8]
0x18006f80c  test    rcx, rcx
0x18006f80f  jz      short loc_18006F81D
0x18006f811  mov     rax, [rcx]
0x18006f814  mov     rax, [rax+10h]
0x18006f818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f81d  test    rbx, rbx
0x18006f820  jz      short loc_18006F831
0x18006f822  mov     rax, [rbx]
0x18006f825  mov     rcx, rbx
0x18006f828  mov     rax, [rax+10h]
0x18006f82c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f831  mov     eax, edi
0x18006f833  jmp     short loc_18006F875
0x18006f835  mov     rcx, [rbp+57h+arg_10]
0x18006f839  test    rcx, rcx
0x18006f83c  jz      short loc_18006F84A
0x18006f83e  mov     rax, [rcx]
0x18006f841  mov     rax, [rax+10h]
0x18006f845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f84a  mov     rcx, [rbp+57h+arg_8]
0x18006f84e  test    rcx, rcx
0x18006f851  jz      short loc_18006F85F
0x18006f853  mov     rax, [rcx]
0x18006f856  mov     rax, [rax+10h]
0x18006f85a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f85f  test    rbx, rbx
0x18006f862  jz      short loc_18006F873
0x18006f864  mov     rax, [rbx]
0x18006f867  mov     rcx, rbx
0x18006f86a  mov     rax, [rax+10h]
0x18006f86e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f873  xor     eax, eax
0x18006f875  mov     rbx, [rsp+0E0h+arg_18]
0x18006f87d  add     rsp, 0D0h
0x18006f884  pop     rdi
0x18006f885  pop     rsi
0x18006f886  pop     rbp
0x18006f887  retn
```
