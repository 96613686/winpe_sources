# TaskDefinitionImpl::InitDefaultValues(void)

- ea: `0x180006c20`
- end: `0x1800070f9`
- name: `?InitDefaultValues@TaskDefinitionImpl@@AEAAXXZ`
- size: `1241`
- prototype: `void __fastcall(TaskDefinitionImpl *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006350`
- `0x180006920`

## callees

- `0x1800063e0`
- `0x1800064f8`
- `0x180006620`
- `0x180006740`
- `0x180006860`
- `0x180006c20`
- `0x18003b51c`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ec4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ec4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e90`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006eea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e90`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006eea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f3b`
- `OLEAUT32!__imp_SysFreeString` at `0x180006e3a`
- `OLEAUT32!__imp_SysFreeString` at `0x180006e4b`
- `OLEAUT32!__imp_SysFreeString` at `0x180006e5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180006e3a`
- `OLEAUT32!__imp_SysFreeString` at `0x180006e4b`
- `OLEAUT32!__imp_SysFreeString` at `0x180006e5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TaskDefinitionImpl::InitDefaultValues(TaskDefinitionImpl *this)
{
  _QWORD *v2; // r12
  __int64 v3; // rcx
  int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // eax
  _QWORD *v11; // rsi
  __int64 v12; // rcx
  int v13; // eax
  _QWORD *v14; // rdi
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rbx
  __int64 v18; // r13
  __int64 v19; // r15
  __int64 v20; // r14
  __int64 v21; // rdi
  __int64 v22; // rcx
  __int64 v23; // rsi
  __int64 v24; // rdi
  __int64 v25; // r15
  __int64 v26; // rcx
  __int64 v27; // rsi
  __int64 v28; // rdi
  __int64 v29; // rcx
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v31; // [rsp+28h] [rbp-40h]
  __int64 *v32; // [rsp+30h] [rbp-38h]
  __int64 v33; // [rsp+38h] [rbp-30h]
  __int64 v34; // [rsp+40h] [rbp-28h]
  int v35; // [rsp+48h] [rbp-20h]
  __int64 v36; // [rsp+4Ch] [rbp-1Ch]
  __int64 (__fastcall ***v37)(_QWORD, _QWORD, _QWORD); // [rsp+B0h] [rbp+48h] BYREF

  v2 = (_QWORD *)((char *)this + 96);
  v3 = *((_QWORD *)this + 12);
  if ( v3 )
  {
    *v2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    if ( *v2 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
  }
  v37 = 0;
  v4 = ATL::CComObject<ActionCollectionImpl>::CreateInstance(&v37);
  if ( v4 < 0 || (v4 = (**v37)(v37, &GUID_02820e19_7b98_4ed2_b2e8_fdccceff619b, v2), v4 < 0) )
  {
    v31 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v32 = &qword_180077320;
    v33 = 0;
    v34 = 0;
    v35 = v4;
    v36 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v5 = *((_QWORD *)this + 9);
  if ( v5 )
  {
    *((_QWORD *)this + 9) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v6 = *((_QWORD *)this + 9);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  v37 = 0;
  v7 = ATL::CComObject<RegistrationInfoImpl>::CreateInstance(&v37);
  if ( v7 < 0 || (v7 = (**v37)(v37, &GUID_416d8b73_cb41_4ea1_805c_9be9a5ac4a74, (char *)this + 72), v7 < 0) )
  {
    v31 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v32 = &qword_180077320;
    v33 = 0;
    v34 = 0;
    v35 = v7;
    v36 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v8 = *((_QWORD *)this + 10);
  if ( v8 )
  {
    *((_QWORD *)this + 10) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v9 = *((_QWORD *)this + 10);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v37 = 0;
  v10 = ATL::CComObject<TaskSettingsImpl>::CreateInstance(&v37);
  if ( v10 < 0 || (v10 = (**v37)(v37, &GUID_8fd4711d_2d02_4c8c_87e3_eff699de127e, (char *)this + 80), v10 < 0) )
  {
    v31 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v32 = &qword_180077320;
    v33 = 0;
    v34 = 0;
    v35 = v10;
    v36 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v11 = (_QWORD *)((char *)this + 88);
  v12 = *((_QWORD *)this + 11);
  if ( v12 )
  {
    *v11 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    if ( *v11 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11);
  }
  v37 = 0;
  v13 = ATL::CComObject<TriggerCollectionImpl>::CreateInstance(&v37);
  if ( v13 < 0 || (v13 = (**v37)(v37, &GUID_85df5081_1b24_4f32_878a_d9d14df4cb77, (char *)this + 88), v13 < 0) )
  {
    v31 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v32 = &qword_180077320;
    v33 = 0;
    v34 = 0;
    v35 = v13;
    v36 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v14 = (_QWORD *)((char *)this + 104);
  v15 = *((_QWORD *)this + 13);
  if ( v15 )
  {
    *v14 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    if ( *v14 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 16LL))(*v14);
  }
  v37 = 0;
  v16 = ATL::CComObject<PrincipalImpl>::CreateInstance(&v37);
  if ( v16 < 0 || (v16 = (**v37)(v37, &GUID_d98d51e5_c9b4_496a_a9c1_18980261cf0f, (char *)this + 104), v16 < 0) )
  {
    v31 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v32 = &qword_180077320;
    v33 = 0;
    v34 = 0;
    v35 = v16;
    v36 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  SysFreeString(*((BSTR *)this + 14));
  *((_QWORD *)this + 14) = 0;
  SysFreeString(*((BSTR *)this + 16));
  *((_QWORD *)this + 16) = 0;
  SysFreeString(*((BSTR *)this + 15));
  *((_QWORD *)this + 15) = 0;
  v17 = *((_QWORD *)this + 10);
  v18 = *v14;
  v19 = *v14 + 16LL;
  if ( !*v14 )
    v19 = 0;
  v20 = 8;
  if ( v19 )
  {
    v21 = v19 + 8;
    EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 8));
  }
  else
  {
    v21 = 8;
  }
  v22 = *(_QWORD *)(v18 + 184);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  *(_QWORD *)(v18 + 184) = v17;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
  if ( v19 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v21);
  v23 = *v11;
  v24 = v23 + 32;
  if ( !v23 )
    v24 = 0;
  if ( v24 )
  {
    v25 = v24 + 8;
    EnterCriticalSection((LPCRITICAL_SECTION)(v24 + 8));
  }
  else
  {
    v25 = 8;
  }
  v26 = *(_QWORD *)(v23 + 88);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  *(_QWORD *)(v23 + 88) = v17;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
  if ( v24 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v25);
  v27 = *v2;
  v28 = *v2 + 32LL;
  if ( !*v2 )
    v28 = 0;
  if ( v28 )
  {
    v20 = v28 + 8;
    EnterCriticalSection((LPCRITICAL_SECTION)(v28 + 8));
  }
  v29 = *(_QWORD *)(v27 + 104);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  *(_QWORD *)(v27 + 104) = v17;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
  if ( v28 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v20);
}

```

## disassembly

```asm
0x180006c20  push    rbp
0x180006c22  push    rbx
0x180006c23  push    rsi
0x180006c24  push    rdi
0x180006c25  push    r12
0x180006c27  push    r13
0x180006c29  push    r14
0x180006c2b  push    r15
0x180006c2d  mov     rbp, rsp
0x180006c30  sub     rsp, 68h
0x180006c34  mov     rbx, rcx
0x180006c37  lea     r12, [rcx+60h]
0x180006c3b  mov     rcx, [r12]
0x180006c3f  xor     r15d, r15d
0x180006c42  test    rcx, rcx
0x180006c45  jz      short loc_180006C6C
0x180006c47  mov     [r12], r15
0x180006c4b  mov     rax, [rcx]
0x180006c4e  mov     rax, [rax+10h]
0x180006c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c57  mov     rcx, [r12]
0x180006c5b  test    rcx, rcx
0x180006c5e  jz      short loc_180006C6C
0x180006c60  mov     rax, [rcx]
0x180006c63  mov     rax, [rax+10h]
0x180006c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c6c  mov     [rbp+arg_0], r15
0x180006c70  lea     rcx, [rbp+arg_0]
0x180006c74  call    ?CreateInstance@?$CComObject@VActionCollectionImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<ActionCollectionImpl>::CreateInstance(ATL::CComObject<ActionCollectionImpl> * *)
0x180006c79  test    eax, eax
0x180006c7b  js      loc_180006FFC
0x180006c81  mov     rcx, [rbp+arg_0]
0x180006c85  mov     rax, [rcx]
0x180006c88  mov     r8, r12
0x180006c8b  lea     rdx, _GUID_02820e19_7b98_4ed2_b2e8_fdccceff619b
0x180006c92  mov     rax, [rax]
0x180006c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c9a  test    eax, eax
0x180006c9c  js      loc_180006FFC
0x180006ca2  mov     rcx, [rbx+48h]
0x180006ca6  test    rcx, rcx
0x180006ca9  jz      short loc_180006CD0
0x180006cab  mov     [rbx+48h], r15
0x180006caf  mov     rax, [rcx]
0x180006cb2  mov     rax, [rax+10h]
0x180006cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cbb  mov     rcx, [rbx+48h]
0x180006cbf  test    rcx, rcx
0x180006cc2  jz      short loc_180006CD0
0x180006cc4  mov     rax, [rcx]
0x180006cc7  mov     rax, [rax+10h]
0x180006ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cd0  mov     [rbp+arg_0], r15
0x180006cd4  lea     rcx, [rbp+arg_0]
0x180006cd8  call    ?CreateInstance@?$CComObject@VRegistrationInfoImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<RegistrationInfoImpl>::CreateInstance(ATL::CComObject<RegistrationInfoImpl> * *)
0x180006cdd  test    eax, eax
0x180006cdf  js      loc_1800070BB
0x180006ce5  mov     rcx, [rbp+arg_0]
0x180006ce9  mov     rax, [rcx]
0x180006cec  lea     r8, [rbx+48h]
0x180006cf0  lea     rdx, _GUID_416d8b73_cb41_4ea1_805c_9be9a5ac4a74
0x180006cf7  mov     rax, [rax]
0x180006cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cff  test    eax, eax
0x180006d01  js      loc_1800070BB
0x180006d07  mov     rcx, [rbx+50h]
0x180006d0b  test    rcx, rcx
0x180006d0e  jz      short loc_180006D35
0x180006d10  mov     [rbx+50h], r15
0x180006d14  mov     rax, [rcx]
0x180006d17  mov     rax, [rax+10h]
0x180006d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d20  mov     rcx, [rbx+50h]
0x180006d24  test    rcx, rcx
0x180006d27  jz      short loc_180006D35
0x180006d29  mov     rax, [rcx]
0x180006d2c  mov     rax, [rax+10h]
0x180006d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d35  mov     [rbp+arg_0], r15
0x180006d39  lea     rcx, [rbp+arg_0]
0x180006d3d  call    ?CreateInstance@?$CComObject@VTaskSettingsImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<TaskSettingsImpl>::CreateInstance(ATL::CComObject<TaskSettingsImpl> * *)
0x180006d42  test    eax, eax
0x180006d44  js      loc_180006F80
0x180006d4a  mov     rcx, [rbp+arg_0]
0x180006d4e  mov     rax, [rcx]
0x180006d51  lea     r8, [rbx+50h]
0x180006d55  lea     rdx, _GUID_8fd4711d_2d02_4c8c_87e3_eff699de127e
0x180006d5c  mov     rax, [rax]
0x180006d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d64  test    eax, eax
0x180006d66  js      loc_180006F80
0x180006d6c  lea     rsi, [rbx+58h]
0x180006d70  mov     rcx, [rsi]
0x180006d73  test    rcx, rcx
0x180006d76  jz      short loc_180006D9B
0x180006d78  mov     [rsi], r15
0x180006d7b  mov     rax, [rcx]
0x180006d7e  mov     rax, [rax+10h]
0x180006d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d87  mov     rcx, [rsi]
0x180006d8a  test    rcx, rcx
0x180006d8d  jz      short loc_180006D9B
0x180006d8f  mov     rax, [rcx]
0x180006d92  mov     rax, [rax+10h]
0x180006d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d9b  mov     [rbp+arg_0], r15
0x180006d9f  lea     rcx, [rbp+arg_0]
0x180006da3  call    ?CreateInstance@?$CComObject@VTriggerCollectionImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<TriggerCollectionImpl>::CreateInstance(ATL::CComObject<TriggerCollectionImpl> * *)
0x180006da8  test    eax, eax
0x180006daa  js      loc_180006FBE
0x180006db0  mov     rcx, [rbp+arg_0]
0x180006db4  mov     rax, [rcx]
0x180006db7  mov     r8, rsi
0x180006dba  lea     rdx, _GUID_85df5081_1b24_4f32_878a_d9d14df4cb77
0x180006dc1  mov     rax, [rax]
0x180006dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dc9  test    eax, eax
0x180006dcb  js      loc_180006FBE
0x180006dd1  lea     rdi, [rbx+68h]
0x180006dd5  mov     rcx, [rdi]
0x180006dd8  test    rcx, rcx
0x180006ddb  jz      short loc_180006E00
0x180006ddd  mov     [rdi], r15
0x180006de0  mov     rax, [rcx]
0x180006de3  mov     rax, [rax+10h]
0x180006de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dec  mov     rcx, [rdi]
0x180006def  test    rcx, rcx
0x180006df2  jz      short loc_180006E00
0x180006df4  mov     rax, [rcx]
0x180006df7  mov     rax, [rax+10h]
0x180006dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e00  mov     [rbp+arg_0], r15
0x180006e04  lea     rcx, [rbp+arg_0]
0x180006e08  call    ?CreateInstance@?$CComObject@VPrincipalImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<PrincipalImpl>::CreateInstance(ATL::CComObject<PrincipalImpl> * *)
0x180006e0d  test    eax, eax
0x180006e0f  js      loc_18000703A
0x180006e15  mov     rcx, [rbp+arg_0]
0x180006e19  mov     rax, [rcx]
0x180006e1c  mov     r8, rdi
0x180006e1f  lea     rdx, _GUID_d98d51e5_c9b4_496a_a9c1_18980261cf0f
0x180006e26  mov     rax, [rax]
0x180006e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e2e  test    eax, eax
0x180006e30  js      loc_18000703A
0x180006e36  mov     rcx, [rbx+70h]; bstrString
0x180006e3a  call    cs:__imp_SysFreeString
0x180006e40  mov     [rbx+70h], r15
0x180006e44  mov     rcx, [rbx+80h]; bstrString
0x180006e4b  call    cs:__imp_SysFreeString
0x180006e51  mov     [rbx+80h], r15
0x180006e58  mov     rcx, [rbx+78h]; bstrString
0x180006e5c  call    cs:__imp_SysFreeString
0x180006e62  mov     [rbx+78h], r15
0x180006e66  mov     rbx, [rbx+50h]
0x180006e6a  mov     r13, [rdi]
0x180006e6d  lea     r15, [r13+10h]
0x180006e71  xor     eax, eax
0x180006e73  test    r13, r13
0x180006e76  cmovz   r15, rax
0x180006e7a  mov     r14d, 8
0x180006e80  test    r15, r15
0x180006e83  jz      loc_180007078
0x180006e89  lea     rdi, [r15+8]
0x180006e8d  mov     rcx, rdi; lpCriticalSection
0x180006e90  call    cs:__imp_EnterCriticalSection
0x180006e96  mov     rcx, [r13+0B8h]
0x180006e9d  test    rcx, rcx
0x180006ea0  jnz     loc_180007080
0x180006ea6  mov     [r13+0B8h], rbx
0x180006ead  mov     rax, [rbx]
0x180006eb0  mov     rcx, rbx
0x180006eb3  mov     rax, [rax+8]
0x180006eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ebc  test    r15, r15
0x180006ebf  jz      short loc_180006ECA
0x180006ec1  mov     rcx, rdi; lpCriticalSection
0x180006ec4  call    cs:__imp_LeaveCriticalSection
0x180006eca  mov     rsi, [rsi]
0x180006ecd  lea     rdi, [rsi+20h]
0x180006ed1  xor     eax, eax
0x180006ed3  test    rsi, rsi
0x180006ed6  cmovz   rdi, rax
0x180006eda  test    rdi, rdi
0x180006edd  jz      loc_180007091
0x180006ee3  lea     r15, [rdi+8]
0x180006ee7  mov     rcx, r15; lpCriticalSection
0x180006eea  call    cs:__imp_EnterCriticalSection
0x180006ef0  mov     rcx, [rsi+58h]
0x180006ef4  test    rcx, rcx
0x180006ef7  jnz     loc_180007099
0x180006efd  mov     [rsi+58h], rbx
0x180006f01  mov     rax, [rbx]
0x180006f04  mov     rcx, rbx
0x180006f07  mov     rax, [rax+8]
0x180006f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f10  test    rdi, rdi
0x180006f13  jz      short loc_180006F1E
0x180006f15  mov     rcx, r15; lpCriticalSection
0x180006f18  call    cs:__imp_LeaveCriticalSection
0x180006f1e  mov     rsi, [r12]
0x180006f22  lea     rdi, [rsi+20h]
0x180006f26  xor     eax, eax
0x180006f28  test    rsi, rsi
0x180006f2b  cmovz   rdi, rax
0x180006f2f  test    rdi, rdi
0x180006f32  jz      short loc_180006F41
0x180006f34  lea     r14, [rdi+8]
0x180006f38  mov     rcx, r14; lpCriticalSection
0x180006f3b  call    cs:__imp_EnterCriticalSection
0x180006f41  mov     rcx, [rsi+68h]
0x180006f45  test    rcx, rcx
0x180006f48  jnz     loc_1800070AA
0x180006f4e  mov     [rsi+68h], rbx
0x180006f52  mov     rax, [rbx]
0x180006f55  mov     rcx, rbx
0x180006f58  mov     rax, [rax+8]
0x180006f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f61  test    rdi, rdi
0x180006f64  jz      short loc_180006F6F
0x180006f66  mov     rcx, r14; lpCriticalSection
0x180006f69  call    cs:__imp_LeaveCriticalSection
0x180006f6f  add     rsp, 68h
0x180006f73  pop     r15
0x180006f75  pop     r14
0x180006f77  pop     r13
0x180006f79  pop     r12
0x180006f7b  pop     rdi
0x180006f7c  pop     rsi
0x180006f7d  pop     rbx
0x180006f7e  pop     rbp
0x180006f7f  retn
0x180006f80  mov     [rbp+var_40], 0
0x180006f84  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180006f8b  mov     [rbp+pExceptionObject], rcx
0x180006f8f  lea     rcx, qword_180077320
0x180006f96  mov     [rbp+var_38], rcx
0x180006f9a  mov     [rbp+var_30], r15
0x180006f9e  mov     [rbp+var_28], r15
0x180006fa2  mov     [rbp+var_20], eax
0x180006fa5  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x180006fad  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180006fb4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180006fb8  call    _CxxThrowException_0
0x180006fbe  mov     [rbp+var_40], 0
0x180006fc2  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180006fc9  mov     [rbp+pExceptionObject], rcx
0x180006fcd  lea     rcx, qword_180077320
0x180006fd4  mov     [rbp+var_38], rcx
0x180006fd8  mov     [rbp+var_30], r15
0x180006fdc  mov     [rbp+var_28], r15
0x180006fe0  mov     [rbp+var_20], eax
0x180006fe3  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x180006feb  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180006ff2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180006ff6  call    _CxxThrowException_0
0x180006ffc  mov     [rbp+var_40], 0
0x180007000  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180007007  mov     [rbp+pExceptionObject], rcx
0x18000700b  lea     rcx, qword_180077320
0x180007012  mov     [rbp+var_38], rcx
0x180007016  mov     [rbp+var_30], r15
0x18000701a  mov     [rbp+var_28], r15
0x18000701e  mov     [rbp+var_20], eax
0x180007021  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x180007029  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180007030  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180007034  call    _CxxThrowException_0
0x18000703a  mov     [rbp+var_40], 0
0x18000703e  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180007045  mov     [rbp+pExceptionObject], rcx
0x180007049  lea     rcx, qword_180077320
0x180007050  mov     [rbp+var_38], rcx
0x180007054  mov     [rbp+var_30], r15
0x180007058  mov     [rbp+var_28], r15
0x18000705c  mov     [rbp+var_20], eax
0x18000705f  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x180007067  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000706e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180007072  call    _CxxThrowException_0
0x180007078  mov     rdi, r14
0x18000707b  jmp     loc_180006E96
0x180007080  mov     rax, [rcx]
0x180007083  mov     rax, [rax+10h]
0x180007087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000708c  jmp     loc_180006EA6
0x180007091  mov     r15, r14
0x180007094  jmp     loc_180006EF0
0x180007099  mov     rax, [rcx]
0x18000709c  mov     rax, [rax+10h]
0x1800070a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070a5  jmp     loc_180006EFD
0x1800070aa  mov     rax, [rcx]
0x1800070ad  mov     rax, [rax+10h]
0x1800070b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070b6  jmp     loc_180006F4E
0x1800070bb  mov     [rbp+var_40], 0
0x1800070bf  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800070c6  mov     [rbp+pExceptionObject], rcx
0x1800070ca  lea     rcx, qword_180077320
  ... truncated ...
```
