# TaskDefinitionImpl::InitDefaultValues(void)

- ea: `0x180006fb0`
- end: `0x1800074c0`
- name: `?InitDefaultValues@TaskDefinitionImpl@@AEAAXXZ`
- size: `1296`
- prototype: `void __fastcall(TaskDefinitionImpl *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800066a8`
- `0x180006c90`

## callees

- `0x180006730`
- `0x18000684c`
- `0x180006970`
- `0x180006a90`
- `0x180006bb0`
- `0x180006fb0`
- `0x18003e88c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000726c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800072cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007329`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000726c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800072cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007329`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007232`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007298`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800072f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007232`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007298`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800072f5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800071ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800071e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800071f8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800071ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800071e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800071f8`

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
    v32 = &qword_18007B2F0;
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
    v32 = &qword_18007B2F0;
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
    v32 = &qword_18007B2F0;
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
    v32 = &qword_18007B2F0;
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
    v32 = &qword_18007B2F0;
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
0x180006fb0  push    rbp
0x180006fb2  push    rbx
0x180006fb3  push    rsi
0x180006fb4  push    rdi
0x180006fb5  push    r12
0x180006fb7  push    r13
0x180006fb9  push    r14
0x180006fbb  push    r15
0x180006fbd  mov     rbp, rsp
0x180006fc0  sub     rsp, 68h
0x180006fc4  mov     rbx, rcx
0x180006fc7  lea     r12, [rcx+60h]
0x180006fcb  mov     rcx, [r12]
0x180006fcf  xor     r15d, r15d
0x180006fd2  test    rcx, rcx
0x180006fd5  jz      short loc_180006FFC
0x180006fd7  mov     [r12], r15
0x180006fdb  mov     rax, [rcx]
0x180006fde  mov     rax, [rax+10h]
0x180006fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fe7  mov     rcx, [r12]
0x180006feb  test    rcx, rcx
0x180006fee  jz      short loc_180006FFC
0x180006ff0  mov     rax, [rcx]
0x180006ff3  mov     rax, [rax+10h]
0x180006ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ffc  mov     [rbp+arg_0], r15
0x180007000  lea     rcx, [rbp+arg_0]
0x180007004  call    ?CreateInstance@?$CComObject@VActionCollectionImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<ActionCollectionImpl>::CreateInstance(ATL::CComObject<ActionCollectionImpl> * *)
0x180007009  test    eax, eax
0x18000700b  js      loc_1800073C3
0x180007011  mov     rcx, [rbp+arg_0]
0x180007015  mov     rax, [rcx]
0x180007018  mov     r8, r12
0x18000701b  lea     rdx, _GUID_02820e19_7b98_4ed2_b2e8_fdccceff619b
0x180007022  mov     rax, [rax]
0x180007025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000702a  test    eax, eax
0x18000702c  js      loc_1800073C3
0x180007032  mov     rcx, [rbx+48h]
0x180007036  test    rcx, rcx
0x180007039  jz      short loc_180007060
0x18000703b  mov     [rbx+48h], r15
0x18000703f  mov     rax, [rcx]
0x180007042  mov     rax, [rax+10h]
0x180007046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000704b  mov     rcx, [rbx+48h]
0x18000704f  test    rcx, rcx
0x180007052  jz      short loc_180007060
0x180007054  mov     rax, [rcx]
0x180007057  mov     rax, [rax+10h]
0x18000705b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007060  mov     [rbp+arg_0], r15
0x180007064  lea     rcx, [rbp+arg_0]
0x180007068  call    ?CreateInstance@?$CComObject@VRegistrationInfoImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<RegistrationInfoImpl>::CreateInstance(ATL::CComObject<RegistrationInfoImpl> * *)
0x18000706d  test    eax, eax
0x18000706f  js      loc_180007482
0x180007075  mov     rcx, [rbp+arg_0]
0x180007079  mov     rax, [rcx]
0x18000707c  lea     r8, [rbx+48h]
0x180007080  lea     rdx, _GUID_416d8b73_cb41_4ea1_805c_9be9a5ac4a74
0x180007087  mov     rax, [rax]
0x18000708a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000708f  test    eax, eax
0x180007091  js      loc_180007482
0x180007097  mov     rcx, [rbx+50h]
0x18000709b  test    rcx, rcx
0x18000709e  jz      short loc_1800070C5
0x1800070a0  mov     [rbx+50h], r15
0x1800070a4  mov     rax, [rcx]
0x1800070a7  mov     rax, [rax+10h]
0x1800070ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070b0  mov     rcx, [rbx+50h]
0x1800070b4  test    rcx, rcx
0x1800070b7  jz      short loc_1800070C5
0x1800070b9  mov     rax, [rcx]
0x1800070bc  mov     rax, [rax+10h]
0x1800070c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070c5  mov     [rbp+arg_0], r15
0x1800070c9  lea     rcx, [rbp+arg_0]
0x1800070cd  call    ?CreateInstance@?$CComObject@VTaskSettingsImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<TaskSettingsImpl>::CreateInstance(ATL::CComObject<TaskSettingsImpl> * *)
0x1800070d2  test    eax, eax
0x1800070d4  js      loc_180007347
0x1800070da  mov     rcx, [rbp+arg_0]
0x1800070de  mov     rax, [rcx]
0x1800070e1  lea     r8, [rbx+50h]
0x1800070e5  lea     rdx, _GUID_8fd4711d_2d02_4c8c_87e3_eff699de127e
0x1800070ec  mov     rax, [rax]
0x1800070ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070f4  test    eax, eax
0x1800070f6  js      loc_180007347
0x1800070fc  lea     rsi, [rbx+58h]
0x180007100  mov     rcx, [rsi]
0x180007103  test    rcx, rcx
0x180007106  jz      short loc_18000712B
0x180007108  mov     [rsi], r15
0x18000710b  mov     rax, [rcx]
0x18000710e  mov     rax, [rax+10h]
0x180007112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007117  mov     rcx, [rsi]
0x18000711a  test    rcx, rcx
0x18000711d  jz      short loc_18000712B
0x18000711f  mov     rax, [rcx]
0x180007122  mov     rax, [rax+10h]
0x180007126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000712b  mov     [rbp+arg_0], r15
0x18000712f  lea     rcx, [rbp+arg_0]
0x180007133  call    ?CreateInstance@?$CComObject@VTriggerCollectionImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<TriggerCollectionImpl>::CreateInstance(ATL::CComObject<TriggerCollectionImpl> * *)
0x180007138  test    eax, eax
0x18000713a  js      loc_180007385
0x180007140  mov     rcx, [rbp+arg_0]
0x180007144  mov     rax, [rcx]
0x180007147  mov     r8, rsi
0x18000714a  lea     rdx, _GUID_85df5081_1b24_4f32_878a_d9d14df4cb77
0x180007151  mov     rax, [rax]
0x180007154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007159  test    eax, eax
0x18000715b  js      loc_180007385
0x180007161  lea     rdi, [rbx+68h]
0x180007165  mov     rcx, [rdi]
0x180007168  test    rcx, rcx
0x18000716b  jz      short loc_180007190
0x18000716d  mov     [rdi], r15
0x180007170  mov     rax, [rcx]
0x180007173  mov     rax, [rax+10h]
0x180007177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000717c  mov     rcx, [rdi]
0x18000717f  test    rcx, rcx
0x180007182  jz      short loc_180007190
0x180007184  mov     rax, [rcx]
0x180007187  mov     rax, [rax+10h]
0x18000718b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007190  mov     [rbp+arg_0], r15
0x180007194  lea     rcx, [rbp+arg_0]
0x180007198  call    ?CreateInstance@?$CComObject@VPrincipalImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<PrincipalImpl>::CreateInstance(ATL::CComObject<PrincipalImpl> * *)
0x18000719d  test    eax, eax
0x18000719f  js      loc_180007401
0x1800071a5  mov     rcx, [rbp+arg_0]
0x1800071a9  mov     rax, [rcx]
0x1800071ac  mov     r8, rdi
0x1800071af  lea     rdx, _GUID_d98d51e5_c9b4_496a_a9c1_18980261cf0f
0x1800071b6  mov     rax, [rax]
0x1800071b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071be  test    eax, eax
0x1800071c0  js      loc_180007401
0x1800071c6  mov     rcx, [rbx+70h]; bstrString
0x1800071ca  call    cs:__imp_SysFreeString
0x1800071d1  nop     dword ptr [rax+rax+00h]
0x1800071d6  mov     [rbx+70h], r15
0x1800071da  mov     rcx, [rbx+80h]; bstrString
0x1800071e1  call    cs:__imp_SysFreeString
0x1800071e8  nop     dword ptr [rax+rax+00h]
0x1800071ed  mov     [rbx+80h], r15
0x1800071f4  mov     rcx, [rbx+78h]; bstrString
0x1800071f8  call    cs:__imp_SysFreeString
0x1800071ff  nop     dword ptr [rax+rax+00h]
0x180007204  mov     [rbx+78h], r15
0x180007208  mov     rbx, [rbx+50h]
0x18000720c  mov     r13, [rdi]
0x18000720f  lea     r15, [r13+10h]
0x180007213  xor     eax, eax
0x180007215  test    r13, r13
0x180007218  cmovz   r15, rax
0x18000721c  mov     r14d, 8
0x180007222  test    r15, r15
0x180007225  jz      loc_18000743F
0x18000722b  lea     rdi, [r15+8]
0x18000722f  mov     rcx, rdi; lpCriticalSection
0x180007232  call    cs:__imp_EnterCriticalSection
0x180007239  nop     dword ptr [rax+rax+00h]
0x18000723e  mov     rcx, [r13+0B8h]
0x180007245  test    rcx, rcx
0x180007248  jnz     loc_180007447
0x18000724e  mov     [r13+0B8h], rbx
0x180007255  mov     rax, [rbx]
0x180007258  mov     rcx, rbx
0x18000725b  mov     rax, [rax+8]
0x18000725f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007264  test    r15, r15
0x180007267  jz      short loc_180007278
0x180007269  mov     rcx, rdi; lpCriticalSection
0x18000726c  call    cs:__imp_LeaveCriticalSection
0x180007273  nop     dword ptr [rax+rax+00h]
0x180007278  mov     rsi, [rsi]
0x18000727b  lea     rdi, [rsi+20h]
0x18000727f  xor     eax, eax
0x180007281  test    rsi, rsi
0x180007284  cmovz   rdi, rax
0x180007288  test    rdi, rdi
0x18000728b  jz      loc_180007458
0x180007291  lea     r15, [rdi+8]
0x180007295  mov     rcx, r15; lpCriticalSection
0x180007298  call    cs:__imp_EnterCriticalSection
0x18000729f  nop     dword ptr [rax+rax+00h]
0x1800072a4  mov     rcx, [rsi+58h]
0x1800072a8  test    rcx, rcx
0x1800072ab  jnz     loc_180007460
0x1800072b1  mov     [rsi+58h], rbx
0x1800072b5  mov     rax, [rbx]
0x1800072b8  mov     rcx, rbx
0x1800072bb  mov     rax, [rax+8]
0x1800072bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072c4  test    rdi, rdi
0x1800072c7  jz      short loc_1800072D8
0x1800072c9  mov     rcx, r15; lpCriticalSection
0x1800072cc  call    cs:__imp_LeaveCriticalSection
0x1800072d3  nop     dword ptr [rax+rax+00h]
0x1800072d8  mov     rsi, [r12]
0x1800072dc  lea     rdi, [rsi+20h]
0x1800072e0  xor     eax, eax
0x1800072e2  test    rsi, rsi
0x1800072e5  cmovz   rdi, rax
0x1800072e9  test    rdi, rdi
0x1800072ec  jz      short loc_180007301
0x1800072ee  lea     r14, [rdi+8]
0x1800072f2  mov     rcx, r14; lpCriticalSection
0x1800072f5  call    cs:__imp_EnterCriticalSection
0x1800072fc  nop     dword ptr [rax+rax+00h]
0x180007301  mov     rcx, [rsi+68h]
0x180007305  test    rcx, rcx
0x180007308  jnz     loc_180007471
0x18000730e  mov     [rsi+68h], rbx
0x180007312  mov     rax, [rbx]
0x180007315  mov     rcx, rbx
0x180007318  mov     rax, [rax+8]
0x18000731c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007321  test    rdi, rdi
0x180007324  jz      short loc_180007335
0x180007326  mov     rcx, r14; lpCriticalSection
0x180007329  call    cs:__imp_LeaveCriticalSection
0x180007330  nop     dword ptr [rax+rax+00h]
0x180007335  add     rsp, 68h
0x180007339  pop     r15
0x18000733b  pop     r14
0x18000733d  pop     r13
0x18000733f  pop     r12
0x180007341  pop     rdi
0x180007342  pop     rsi
0x180007343  pop     rbx
0x180007344  pop     rbp
0x180007345  retn
0x180007347  mov     [rbp+var_40], 0
0x18000734b  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180007352  mov     [rbp+pExceptionObject], rcx
0x180007356  lea     rcx, qword_18007B2F0
0x18000735d  mov     [rbp+var_38], rcx
0x180007361  mov     [rbp+var_30], r15
0x180007365  mov     [rbp+var_28], r15
0x180007369  mov     [rbp+var_20], eax
0x18000736c  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x180007374  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000737b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000737f  call    _CxxThrowException_0
0x180007385  mov     [rbp+var_40], 0
0x180007389  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180007390  mov     [rbp+pExceptionObject], rcx
0x180007394  lea     rcx, qword_18007B2F0
0x18000739b  mov     [rbp+var_38], rcx
0x18000739f  mov     [rbp+var_30], r15
0x1800073a3  mov     [rbp+var_28], r15
0x1800073a7  mov     [rbp+var_20], eax
0x1800073aa  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x1800073b2  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800073b9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800073bd  call    _CxxThrowException_0
0x1800073c3  mov     [rbp+var_40], 0
0x1800073c7  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800073ce  mov     [rbp+pExceptionObject], rcx
0x1800073d2  lea     rcx, qword_18007B2F0
0x1800073d9  mov     [rbp+var_38], rcx
0x1800073dd  mov     [rbp+var_30], r15
0x1800073e1  mov     [rbp+var_28], r15
0x1800073e5  mov     [rbp+var_20], eax
0x1800073e8  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x1800073f0  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800073f7  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800073fb  call    _CxxThrowException_0
0x180007401  mov     [rbp+var_40], 0
0x180007405  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000740c  mov     [rbp+pExceptionObject], rcx
0x180007410  lea     rcx, qword_18007B2F0
0x180007417  mov     [rbp+var_38], rcx
0x18000741b  mov     [rbp+var_30], r15
0x18000741f  mov     [rbp+var_28], r15
0x180007423  mov     [rbp+var_20], eax
0x180007426  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x18000742e  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180007435  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180007439  call    _CxxThrowException_0
0x18000743f  mov     rdi, r14
0x180007442  jmp     loc_18000723E
0x180007447  mov     rax, [rcx]
0x18000744a  mov     rax, [rax+10h]
0x18000744e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007453  jmp     loc_18000724E
0x180007458  mov     r15, r14
0x18000745b  jmp     loc_1800072A4
0x180007460  mov     rax, [rcx]
0x180007463  mov     rax, [rax+10h]
0x180007467  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
