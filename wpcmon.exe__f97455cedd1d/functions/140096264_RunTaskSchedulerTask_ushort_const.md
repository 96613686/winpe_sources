# RunTaskSchedulerTask(ushort const *)

- ea: `0x140096264`
- end: `0x1400965b7`
- name: `?RunTaskSchedulerTask@@YAJPEBG@Z`
- size: `851`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140096b28`

## callees

- `0x140006536`
- `0x140016854`
- `0x140096264`
- `0x1400a8010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400963b4`
- `OLEAUT32!__imp_SysAllocString` at `0x1400963b4`
- `OLEAUT32!__imp_SysFreeString` at `0x140096456`
- `OLEAUT32!__imp_SysFreeString` at `0x1400964bc`
- `OLEAUT32!__imp_SysFreeString` at `0x140096456`
- `OLEAUT32!__imp_SysFreeString` at `0x1400964bc`
- `OLEAUT32!__imp_VariantClear` at `0x14009633f`
- `OLEAUT32!__imp_VariantClear` at `0x14009639f`
- `OLEAUT32!__imp_VariantClear` at `0x140096500`
- `OLEAUT32!__imp_VariantClear` at `0x14009633f`
- `OLEAUT32!__imp_VariantClear` at `0x14009639f`
- `OLEAUT32!__imp_VariantClear` at `0x140096500`

## string_xrefs

- `0x140096317`: `shell\lib\comtaskserverutil.cpp`
- `0x140096349`: `shell\lib\comtaskserverutil.cpp`
- `0x1400963c6`: `shell\lib\comtaskserverutil.cpp`
- `0x14009642f`: `shell\lib\comtaskserverutil.cpp`
- `0x140096460`: `shell\lib\comtaskserverutil.cpp`
- `0x14009650e`: `shell\lib\comtaskserverutil.cpp`
- `0x1400963a5`: `\Microsoft\Windows\Shell\CreateObjectTask`

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
  v1 = CoCreateInstance_0(
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
0x140096264  mov     [rsp-8+arg_18], rbx
0x140096269  mov     [rsp-8+arg_0], rcx
0x14009626e  push    rbp
0x14009626f  push    rsi
0x140096270  push    rdi
0x140096271  lea     rbp, [rsp-47h]
0x140096276  sub     rsp, 0D0h
0x14009627d  xor     eax, eax
0x14009627f  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x140096286  xor     edx, edx; pUnkOuter
0x140096288  mov     word ptr [rbp+57h+pvarg], ax
0x14009628c  mov     [rbp+57h+arg_0], rax
0x140096290  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x140096297  lea     rax, [rbp+57h+arg_0]
0x14009629b  mov     [rsp+0E0h+ppv], rax; ppv
0x1400962a0  lea     r8d, [rdx+1]; dwClsContext
0x1400962a4  call    CoCreateInstance_0
0x1400962a9  mov     ebx, eax
0x1400962ab  test    eax, eax
0x1400962ad  jns     short loc_1400962B6
0x1400962af  mov     edx, 1Fh
0x1400962b4  jmp     short loc_140096313
0x1400962b6  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x1400962ba  lea     rdx, [rbp+57h+var_70]
0x1400962be  mov     rcx, [rbp+57h+arg_0]
0x1400962c2  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x1400962c7  lea     r9, [rbp+57h+var_50]
0x1400962cb  mov     [rsp+0E0h+ppv], rdx; int
0x1400962d0  lea     r8, [rbp+57h+var_30]
0x1400962d4  lea     rdx, [rbp+57h+var_90]
0x1400962d8  movaps  xmmword ptr [rbp+57h+var_70], xmm1
0x1400962dc  mov     rax, [rcx]
0x1400962df  movsd   [rbp+57h+var_60], xmm0
0x1400962e4  movaps  [rbp+57h+var_50], xmm1
0x1400962e8  movsd   [rbp+57h+var_40], xmm0
0x1400962ed  mov     rax, [rax+50h]
0x1400962f1  movaps  [rbp+57h+var_30], xmm1
0x1400962f5  movsd   [rbp+57h+var_20], xmm0
0x1400962fa  movaps  [rbp+57h+var_90], xmm1
0x1400962fe  movsd   [rbp+57h+var_80], xmm0
0x140096303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096308  mov     ebx, eax
0x14009630a  test    eax, eax
0x14009630c  jns     short loc_140096364
0x14009630e  mov     edx, 20h ; ' '; void *
0x140096313  mov     rcx, [rbp+5Fh]; this
0x140096317  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x14009631e  mov     r9d, eax; char *
0x140096321  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140096326  mov     rcx, [rbp+57h+arg_0]
0x14009632a  test    rcx, rcx
0x14009632d  jz      short loc_14009633B
0x14009632f  mov     rax, [rcx]
0x140096332  mov     rax, [rax+10h]
0x140096336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009633b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x14009633f  call    cs:__imp_VariantClear
0x140096345  mov     rcx, [rbp+5Fh]; this
0x140096349  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x140096350  mov     r9d, ebx; char *
0x140096353  mov     edx, 37h ; '7'; void *
0x140096358  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009635d  mov     eax, ebx
0x14009635f  jmp     loc_1400965A4
0x140096364  mov     rdi, [rbp+57h+arg_0]
0x140096368  test    rdi, rdi
0x14009636b  jz      short loc_140096385
0x14009636d  mov     rax, [rdi]
0x140096370  mov     rcx, rdi
0x140096373  mov     rax, [rax+8]
0x140096377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009637c  mov     rbx, rdi
0x14009637f  mov     rdi, [rbp+57h+arg_0]
0x140096383  jmp     short loc_140096387
0x140096385  xor     ebx, ebx
0x140096387  test    rdi, rdi
0x14009638a  jz      short loc_14009639B
0x14009638c  mov     rax, [rdi]
0x14009638f  mov     rcx, rdi
0x140096392  mov     rax, [rax+10h]
0x140096396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009639b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x14009639f  call    cs:__imp_VariantClear
0x1400963a5  lea     rcx, psz; "\\Microsoft\\Windows\\Shell\\CreateObje"...
0x1400963ac  mov     [rbp+57h+arg_8], 0
0x1400963b4  call    cs:__imp_SysAllocString
0x1400963ba  mov     rdi, rax
0x1400963bd  test    rax, rax
0x1400963c0  jnz     short loc_1400963DF
0x1400963c2  mov     rcx, [rbp+5Fh]; this
0x1400963c6  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x1400963cd  mov     esi, 8007000Eh
0x1400963d2  lea     edx, [rax+2Bh]; void *
0x1400963d5  mov     r9d, esi; char *
0x1400963d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400963dd  jmp     short loc_14009645C
0x1400963df  mov     rax, [rbx]
0x1400963e2  lea     r8, [rbp+57h+arg_0]
0x1400963e6  xor     edx, edx
0x1400963e8  mov     [rbp+57h+arg_0], 0
0x1400963f0  mov     rcx, rbx
0x1400963f3  mov     rax, [rax+38h]
0x1400963f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400963fc  mov     esi, eax
0x1400963fe  test    eax, eax
0x140096400  jns     short loc_140096409
0x140096402  mov     edx, 2Eh ; '.'
0x140096407  jmp     short loc_14009642B
0x140096409  mov     rcx, [rbp+57h+arg_0]
0x14009640d  lea     r8, [rbp+57h+arg_8]
0x140096411  mov     rdx, rdi
0x140096414  mov     rax, [rcx]
0x140096417  mov     rax, [rax+68h]
0x14009641b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096420  mov     esi, eax
0x140096422  test    eax, eax
0x140096424  jns     short loc_1400964A4
0x140096426  mov     edx, 2Fh ; '/'; void *
0x14009642b  mov     rcx, [rbp+5Fh]; this
0x14009642f  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x140096436  mov     r9d, eax; char *
0x140096439  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009643e  mov     rcx, [rbp+57h+arg_0]
0x140096442  test    rcx, rcx
0x140096445  jz      short loc_140096453
0x140096447  mov     rax, [rcx]
0x14009644a  mov     rax, [rax+10h]
0x14009644e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096453  mov     rcx, rdi; bstrString
0x140096456  call    cs:__imp_SysFreeString
0x14009645c  mov     rcx, [rbp+5Fh]; this
0x140096460  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x140096467  mov     r9d, esi; char *
0x14009646a  mov     edx, 3Ah ; ':'; void *
0x14009646f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140096474  mov     rcx, [rbp+57h+arg_8]
0x140096478  test    rcx, rcx
0x14009647b  jz      short loc_140096489
0x14009647d  mov     rax, [rcx]
0x140096480  mov     rax, [rax+10h]
0x140096484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096489  test    rbx, rbx
0x14009648c  jz      short loc_14009649D
0x14009648e  mov     rcx, [rbx]
0x140096491  mov     rax, [rcx+10h]
0x140096495  mov     rcx, rbx
0x140096498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009649d  mov     eax, esi
0x14009649f  jmp     loc_1400965A4
0x1400964a4  mov     rcx, [rbp+57h+arg_0]
0x1400964a8  test    rcx, rcx
0x1400964ab  jz      short loc_1400964B9
0x1400964ad  mov     rax, [rcx]
0x1400964b0  mov     rax, [rax+10h]
0x1400964b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400964b9  mov     rcx, rdi; bstrString
0x1400964bc  call    cs:__imp_SysFreeString
0x1400964c2  mov     rcx, [rbp+57h+arg_8]
0x1400964c6  lea     r8, [rbp+57h+arg_10]
0x1400964ca  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1400964cf  xor     edx, edx
0x1400964d1  mov     [rbp+57h+arg_10], 0
0x1400964d9  movsd   [rbp+57h+var_80], xmm1
0x1400964de  mov     rax, [rcx]
0x1400964e1  mov     word ptr [rbp+57h+pvarg], dx
0x1400964e5  lea     rdx, [rbp+57h+var_90]
0x1400964e9  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1400964ed  mov     rax, [rax+60h]
0x1400964f1  movaps  [rbp+57h+var_90], xmm0
0x1400964f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400964fa  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1400964fe  mov     edi, eax
0x140096500  call    cs:__imp_VariantClear
0x140096506  test    edi, edi
0x140096508  jns     short loc_140096564
0x14009650a  mov     rcx, [rbp+5Fh]; this
0x14009650e  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x140096515  mov     r9d, edi; char *
0x140096518  mov     edx, 3Dh ; '='; void *
0x14009651d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140096522  mov     rcx, [rbp+57h+arg_10]
0x140096526  test    rcx, rcx
0x140096529  jz      short loc_140096537
0x14009652b  mov     rax, [rcx]
0x14009652e  mov     rax, [rax+10h]
0x140096532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096537  mov     rcx, [rbp+57h+arg_8]
0x14009653b  test    rcx, rcx
0x14009653e  jz      short loc_14009654C
0x140096540  mov     rax, [rcx]
0x140096543  mov     rax, [rax+10h]
0x140096547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009654c  test    rbx, rbx
0x14009654f  jz      short loc_140096560
0x140096551  mov     rax, [rbx]
0x140096554  mov     rcx, rbx
0x140096557  mov     rax, [rax+10h]
0x14009655b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096560  mov     eax, edi
0x140096562  jmp     short loc_1400965A4
0x140096564  mov     rcx, [rbp+57h+arg_10]
0x140096568  test    rcx, rcx
0x14009656b  jz      short loc_140096579
0x14009656d  mov     rax, [rcx]
0x140096570  mov     rax, [rax+10h]
0x140096574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096579  mov     rcx, [rbp+57h+arg_8]
0x14009657d  test    rcx, rcx
0x140096580  jz      short loc_14009658E
0x140096582  mov     rax, [rcx]
0x140096585  mov     rax, [rax+10h]
0x140096589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009658e  test    rbx, rbx
0x140096591  jz      short loc_1400965A2
0x140096593  mov     rax, [rbx]
0x140096596  mov     rcx, rbx
0x140096599  mov     rax, [rax+10h]
0x14009659d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400965a2  xor     eax, eax
0x1400965a4  mov     rbx, [rsp+0E0h+arg_18]
0x1400965ac  add     rsp, 0D0h
0x1400965b3  pop     rdi
0x1400965b4  pop     rsi
0x1400965b5  pop     rbp
0x1400965b6  retn
```
