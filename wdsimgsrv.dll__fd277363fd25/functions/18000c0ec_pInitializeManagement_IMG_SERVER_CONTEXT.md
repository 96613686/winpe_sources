# pInitializeManagement(_IMG_SERVER_CONTEXT *)

- ea: `0x18000c0ec`
- end: `0x18000c3ef`
- name: `?pInitializeManagement@@YAKPEAU_IMG_SERVER_CONTEXT@@@Z`
- size: `771`
- prototype: `unsigned int __fastcall(struct _IMG_SERVER_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007120`

## callees

- `0x18000b370`
- `0x18000c0ec`
- `0x18000cbd4`
- `0x180016020`
- `0x180017010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000c1ab`
- `ole32!CoCreateInstance` at `0x18000c1f0`
- `ole32!CoCreateInstance` at `0x18000c1ab`
- `ole32!CoCreateInstance` at `0x18000c1f0`
- `ole32!CoInitializeEx` at `0x18000c1c2`
- `ole32!CoInitializeEx` at `0x18000c1c2`
- `ole32!CLSIDFromProgID` at `0x18000c17d`
- `ole32!CLSIDFromProgID` at `0x18000c17d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c156`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c156`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c2d9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c2d9`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000c2aa`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000c2aa`

## pseudocode

```c
__int64 __fastcall pInitializeManagement(struct _IMG_SERVER_CONTEXT *a1)
{
  unsigned int v2; // ebx
  OLECHAR *v3; // rsi
  HRESULT v4; // eax
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v9; // [rsp+30h] [rbp-50h] BYREF
  __int64 v10; // [rsp+38h] [rbp-48h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-40h] BYREF
  __int64 v12; // [rsp+48h] [rbp-38h] BYREF
  __int64 v13; // [rsp+50h] [rbp-30h] BYREF
  __int64 v14; // [rsp+58h] [rbp-28h] BYREF
  __int64 v15; // [rsp+60h] [rbp-20h] BYREF
  GUID clsid; // [rsp+68h] [rbp-18h] BYREF

  ppv = 0;
  v10 = 0;
  v9 = 0;
  v2 = 0;
  v12 = 0;
  clsid = 0;
  v13 = 0;
  v15 = 0;
  v14 = 0;
  WdsImgTrace(0x10000u, L"-> pInitializeManagement");
  v3 = SysAllocString(&pszSrch);
  if ( !v3 )
  {
    v2 = 8;
    goto LABEL_15;
  }
  v4 = CLSIDFromProgID(L"WdsMgmt.WdsManager", &clsid);
  if ( v4 < 0 )
    goto LABEL_14;
  v4 = CoCreateInstance(&clsid, 0, 1u, &GUID_f5c420af_ced9_4b92_809b_9debd7e32b03, &ppv);
  if ( v4 == -2147221008 )
  {
    if ( CoInitializeEx(0, 0) < 0 )
      goto LABEL_15;
    v4 = CoCreateInstance(&clsid, 0, 1u, &GUID_f5c420af_ced9_4b92_809b_9debd7e32b03, &ppv);
  }
  if ( v4 < 0
    || (v4 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, v3, &v10), v4 < 0)
    || (v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 72LL))(v10, &v9), v4 < 0)
    || (v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 112LL))(v9, &v12), v4 < 0)
    || (v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 64LL))(v9, &v14),
        (int)ElValidateHr_1(v5, v6, v7, 162) >= 0)
    && ((v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 120LL))(v10, &v13), v4 < 0)
     || (v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 80LL))(v9, &v15), v4 < 0)) )
  {
LABEL_14:
    v2 = WIN32_FROM_HRESULT(v4);
  }
LABEL_15:
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = 0;
  }
  if ( v3 )
    SysFreeString(v3);
  if ( v2 )
  {
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      v10 = 0;
    }
    if ( v12 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      v12 = 0;
    }
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      v13 = 0;
    }
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v14 = 0;
    }
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v15 = 0;
    }
    if ( ppv )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      ppv = 0;
    }
  }
  else
  {
    *((_QWORD *)a1 + 5) = v10;
    *((_QWORD *)a1 + 6) = v12;
    *((_QWORD *)a1 + 7) = v13;
    *((_QWORD *)a1 + 8) = v14;
    *((_QWORD *)a1 + 4) = ppv;
    *((_QWORD *)a1 + 11) = v15;
  }
  WdsImgTrace(0x10000u, L"<- pInitializeManagement=%x", v2);
  return v2;
}

```

## disassembly

```asm
0x18000c0ec  mov     [rsp-18h+arg_8], rbx
0x18000c0f1  mov     [rsp-18h+arg_10], rsi
0x18000c0f6  push    rbp
0x18000c0f7  push    rdi
0x18000c0f8  push    r14
0x18000c0fa  mov     rbp, rsp
0x18000c0fd  sub     rsp, 80h
0x18000c104  mov     rax, cs:__security_cookie
0x18000c10b  xor     rax, rsp
0x18000c10e  mov     [rbp+var_8], rax
0x18000c112  xor     r14d, r14d
0x18000c115  lea     rdx, aPinitializeman; "-> pInitializeManagement"
0x18000c11c  mov     rdi, rcx
0x18000c11f  mov     [rbp+var_40], r14
0x18000c123  xorps   xmm0, xmm0
0x18000c126  mov     [rbp+var_48], r14
0x18000c12a  mov     ecx, 10000h; unsigned int
0x18000c12f  mov     [rbp+var_50], r14
0x18000c133  mov     ebx, r14d
0x18000c136  mov     [rbp+var_38], r14
0x18000c13a  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x18000c13e  mov     [rbp+var_30], r14
0x18000c142  mov     [rbp+var_20], r14
0x18000c146  mov     [rbp+var_28], r14
0x18000c14a  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x18000c14f  lea     rcx, pszSrch; psz
0x18000c156  call    cs:__imp_SysAllocString
0x18000c15d  nop     dword ptr [rax+rax+00h]
0x18000c162  mov     rsi, rax
0x18000c165  test    rax, rax
0x18000c168  jnz     short loc_18000C172
0x18000c16a  lea     ebx, [rax+8]
0x18000c16d  jmp     loc_18000C2B8
0x18000c172  lea     rdx, [rbp+clsid]; lpclsid
0x18000c176  lea     rcx, szProgID; "WdsMgmt.WdsManager"
0x18000c17d  call    cs:__imp_CLSIDFromProgID
0x18000c184  nop     dword ptr [rax+rax+00h]
0x18000c189  test    eax, eax
0x18000c18b  js      loc_18000C2A8
0x18000c191  xor     edx, edx; pUnkOuter
0x18000c193  lea     rax, [rbp+var_40]
0x18000c197  lea     r9, _GUID_f5c420af_ced9_4b92_809b_9debd7e32b03; riid
0x18000c19e  mov     [rsp+80h+ppv], rax; ppv
0x18000c1a3  lea     rcx, [rbp+clsid]; rclsid
0x18000c1a7  lea     r8d, [rdx+1]; dwClsContext
0x18000c1ab  call    cs:__imp_CoCreateInstance
0x18000c1b2  nop     dword ptr [rax+rax+00h]
0x18000c1b7  cmp     eax, 800401F0h
0x18000c1bc  jnz     short loc_18000C1FC
0x18000c1be  xor     edx, edx; dwCoInit
0x18000c1c0  xor     ecx, ecx; pvReserved
0x18000c1c2  call    cs:__imp_CoInitializeEx
0x18000c1c9  nop     dword ptr [rax+rax+00h]
0x18000c1ce  test    eax, eax
0x18000c1d0  js      loc_18000C2B8
0x18000c1d6  xor     edx, edx; pUnkOuter
0x18000c1d8  lea     rax, [rbp+var_40]
0x18000c1dc  lea     r9, _GUID_f5c420af_ced9_4b92_809b_9debd7e32b03; riid
0x18000c1e3  mov     [rsp+80h+ppv], rax; ppv
0x18000c1e8  lea     rcx, [rbp+clsid]; rclsid
0x18000c1ec  lea     r8d, [rdx+1]; dwClsContext
0x18000c1f0  call    cs:__imp_CoCreateInstance
0x18000c1f7  nop     dword ptr [rax+rax+00h]
0x18000c1fc  test    eax, eax
0x18000c1fe  js      loc_18000C2A8
0x18000c204  mov     rcx, [rbp+var_40]
0x18000c208  lea     r8, [rbp+var_48]
0x18000c20c  mov     rdx, rsi
0x18000c20f  mov     rax, [rcx]
0x18000c212  mov     rax, [rax+38h]
0x18000c216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c21b  test    eax, eax
0x18000c21d  js      loc_18000C2A8
0x18000c223  mov     rcx, [rbp+var_48]
0x18000c227  lea     rdx, [rbp+var_50]
0x18000c22b  mov     rax, [rcx]
0x18000c22e  mov     rax, [rax+48h]
0x18000c232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c237  test    eax, eax
0x18000c239  js      short loc_18000C2A8
0x18000c23b  mov     rcx, [rbp+var_50]
0x18000c23f  lea     rdx, [rbp+var_38]
0x18000c243  mov     rax, [rcx]
0x18000c246  mov     rax, [rax+70h]
0x18000c24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c24f  test    eax, eax
0x18000c251  js      short loc_18000C2A8
0x18000c253  mov     rcx, [rbp+var_50]
0x18000c257  lea     rdx, [rbp+var_28]
0x18000c25b  mov     rax, [rcx]
0x18000c25e  mov     rax, [rax+40h]
0x18000c262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c267  mov     r9d, 0A2h
0x18000c26d  mov     ecx, eax
0x18000c26f  call    ElValidateHr_1
0x18000c274  test    eax, eax
0x18000c276  js      short loc_18000C2B8
0x18000c278  mov     rcx, [rbp+var_48]
0x18000c27c  lea     rdx, [rbp+var_30]
0x18000c280  mov     rax, [rcx]
0x18000c283  mov     rax, [rax+78h]
0x18000c287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c28c  test    eax, eax
0x18000c28e  js      short loc_18000C2A8
0x18000c290  mov     rcx, [rbp+var_50]
0x18000c294  lea     rdx, [rbp+var_20]
0x18000c298  mov     rax, [rcx]
0x18000c29b  mov     rax, [rax+50h]
0x18000c29f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2a4  test    eax, eax
0x18000c2a6  jns     short loc_18000C2B8
0x18000c2a8  mov     ecx, eax
0x18000c2aa  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000c2b1  nop     dword ptr [rax+rax+00h]
0x18000c2b6  mov     ebx, eax
0x18000c2b8  mov     rcx, [rbp+var_50]
0x18000c2bc  test    rcx, rcx
0x18000c2bf  jz      short loc_18000C2D1
0x18000c2c1  mov     rax, [rcx]
0x18000c2c4  mov     rax, [rax+10h]
0x18000c2c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2cd  mov     [rbp+var_50], r14
0x18000c2d1  test    rsi, rsi
0x18000c2d4  jz      short loc_18000C2E5
0x18000c2d6  mov     rcx, rsi; bstrString
0x18000c2d9  call    cs:__imp_SysFreeString
0x18000c2e0  nop     dword ptr [rax+rax+00h]
0x18000c2e5  test    ebx, ebx
0x18000c2e7  jnz     short loc_18000C31E
0x18000c2e9  mov     rax, [rbp+var_48]
0x18000c2ed  mov     [rdi+28h], rax
0x18000c2f1  mov     rax, [rbp+var_38]
0x18000c2f5  mov     [rdi+30h], rax
0x18000c2f9  mov     rax, [rbp+var_30]
0x18000c2fd  mov     [rdi+38h], rax
0x18000c301  mov     rax, [rbp+var_28]
0x18000c305  mov     [rdi+40h], rax
0x18000c309  mov     rax, [rbp+var_40]
0x18000c30d  mov     [rdi+20h], rax
0x18000c311  mov     rax, [rbp+var_20]
0x18000c315  mov     [rdi+58h], rax
0x18000c319  jmp     loc_18000C3B4
0x18000c31e  mov     rcx, [rbp+var_48]
0x18000c322  test    rcx, rcx
0x18000c325  jz      short loc_18000C337
0x18000c327  mov     rax, [rcx]
0x18000c32a  mov     rax, [rax+10h]
0x18000c32e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c333  mov     [rbp+var_48], r14
0x18000c337  mov     rcx, [rbp+var_38]
0x18000c33b  test    rcx, rcx
0x18000c33e  jz      short loc_18000C350
0x18000c340  mov     rax, [rcx]
0x18000c343  mov     rax, [rax+10h]
0x18000c347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c34c  mov     [rbp+var_38], r14
0x18000c350  mov     rcx, [rbp+var_30]
0x18000c354  test    rcx, rcx
0x18000c357  jz      short loc_18000C369
0x18000c359  mov     rax, [rcx]
0x18000c35c  mov     rax, [rax+10h]
0x18000c360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c365  mov     [rbp+var_30], r14
0x18000c369  mov     rcx, [rbp+var_28]
0x18000c36d  test    rcx, rcx
0x18000c370  jz      short loc_18000C382
0x18000c372  mov     rax, [rcx]
0x18000c375  mov     rax, [rax+10h]
0x18000c379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c37e  mov     [rbp+var_28], r14
0x18000c382  mov     rcx, [rbp+var_20]
0x18000c386  test    rcx, rcx
0x18000c389  jz      short loc_18000C39B
0x18000c38b  mov     rax, [rcx]
0x18000c38e  mov     rax, [rax+10h]
0x18000c392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c397  mov     [rbp+var_20], r14
0x18000c39b  mov     rcx, [rbp+var_40]
0x18000c39f  test    rcx, rcx
0x18000c3a2  jz      short loc_18000C3B4
0x18000c3a4  mov     rax, [rcx]
0x18000c3a7  mov     rax, [rax+10h]
0x18000c3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3b0  mov     [rbp+var_40], r14
0x18000c3b4  mov     r8d, ebx
0x18000c3b7  lea     rdx, aPinitializeman_0; "<- pInitializeManagement=%x"
0x18000c3be  mov     ecx, 10000h; unsigned int
0x18000c3c3  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x18000c3c8  mov     eax, ebx
0x18000c3ca  mov     rcx, [rbp+var_8]
0x18000c3ce  xor     rcx, rsp; StackCookie
0x18000c3d1  call    __security_check_cookie
0x18000c3d6  lea     r11, [rsp+80h+var_s0]
0x18000c3de  mov     rbx, [r11+28h]
0x18000c3e2  mov     rsi, [r11+30h]
0x18000c3e6  mov     rsp, r11
0x18000c3e9  pop     r14
0x18000c3eb  pop     rdi
0x18000c3ec  pop     rbp
0x18000c3ed  retn
```
