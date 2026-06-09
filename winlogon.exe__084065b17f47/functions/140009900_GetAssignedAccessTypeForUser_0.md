# GetAssignedAccessTypeForUser_0

- ea: `0x140009900`
- end: `0x14000a0c4`
- name: `GetAssignedAccessTypeForUser_0`
- size: `1988`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140009544`
- `0x140009828`

## callees

- `0x140008d48`
- `0x140009510`
- `0x140009900`
- `0x14000a1d8`
- `0x14000a20c`
- `0x14000a240`
- `0x14000a680`
- `0x14000a7b0`
- `0x14000aa04`
- `0x14000aa28`
- `0x140053398`
- `0x1400533f0`
- `0x14009be20`
- `0x14009c080`
- `0x14009c308`
- `0x14009c420`
- `0x1400a1010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009e69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009eae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a02c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a050`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009e69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009eae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a02c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a050`

## string_xrefs

- `0x140009963`: `onecoreuap\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x14000a080`: `onecoreuap\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`

## pseudocode

```c
__int64 __fastcall GetAssignedAccessTypeForUser_0(
        unsigned __int16 *a1,
        char a2,
        enum Windows::Internal::AssignedAccess::AssignedAccessType *a3)
{
  _QWORD *v3; // rax
  _DWORD *v4; // rsi
  __int64 *v6; // r15
  unsigned int v7; // edi
  _QWORD *v8; // rax
  const char *v9; // r9
  _QWORD *v10; // rdi
  _QWORD *v11; // rdx
  void (__fastcall **v12)(_QWORD, __int64); // rcx
  _QWORD *v13; // rax
  void (__fastcall ***v14)(_QWORD, __int64); // r13
  void (__fastcall ***v15)(LPVOID, __int64); // r14
  void (__fastcall ***v16)(_QWORD, __int64); // r12
  _QWORD *v17; // r15
  unsigned int v18; // edi
  unsigned __int16 *v19; // rdi
  _QWORD *v20; // rax
  const char *v21; // r9
  _QWORD *v22; // rdi
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  void (__fastcall ***v25)(_QWORD, __int64); // r13
  void (__fastcall ***v26)(_QWORD, __int64); // r12
  void (__fastcall ***v27)(LPVOID, __int64); // r14
  LPVOID v28; // r14
  char v29; // al
  void *v30; // rcx
  LPVOID v31; // r14
  char v32; // al
  void *v33; // rcx
  int AssignedAccessTypeForUserWithoutGroup; // eax
  unsigned int v35; // ebx
  void (__fastcall ***v36)(_QWORD, __int64); // [rsp+20h] [rbp-59h] BYREF
  char v37; // [rsp+28h] [rbp-51h]
  LPVOID pv; // [rsp+30h] [rbp-49h] BYREF
  _DWORD *v39; // [rsp+38h] [rbp-41h] BYREF
  void (__fastcall ***v40)(_QWORD, __int64); // [rsp+40h] [rbp-39h] BYREF
  unsigned __int16 *v41; // [rsp+48h] [rbp-31h]
  enum Windows::Internal::AssignedAccess::AssignedAccessType *v42; // [rsp+50h] [rbp-29h]
  void (__fastcall ***v43)(_QWORD, __int64); // [rsp+58h] [rbp-21h] BYREF
  _BYTE v44[16]; // [rsp+60h] [rbp-19h] BYREF
  _QWORD v45[3]; // [rsp+70h] [rbp-9h] BYREF
  _QWORD v46[3]; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v47; // [rsp+A0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v41 = a1;
  v42 = a3;
  v37 = a2;
  v3 = operator new(0x20u);
  v4 = v3;
  if ( v3 )
  {
    v3[3] = 0;
    *v3 = 0;
    v3[1] = 0;
    v3[2] = 0;
    v39 = v3;
    if ( Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::Initialize((Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *)v3) )
      goto LABEL_3;
  }
  else
  {
    v39 = 0;
  }
  wistd::unique_ptr<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper>>::reset(&v39);
  v4 = v39;
LABEL_3:
  if ( !v4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
      (const char *)0x8000FFFFLL,
      (int)v36);
    return 2147549183LL;
  }
  v8 = operator new(0x20u);
  v10 = v8;
  if ( !v8 )
  {
    v36 = 0;
LABEL_24:
    wistd::unique_ptr<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0>>::reset(&v36);
    goto LABEL_25;
  }
  *v8 = &Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::`vftable';
  v8[1] = 0;
  v8[2] = 0;
  v8[3] = 0;
  v36 = (void (__fastcall ***)(_QWORD, __int64))v8;
  pv = 0;
  if ( (int)Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(
              L"SOFTWARE\\Microsoft\\Windows Embedded\\Lockdown",
              0,
              (char *)&pv,
              v9) < 0 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_24;
  }
  v28 = pv;
  v29 = 0;
  if ( pv )
  {
    v30 = (void *)v10[1];
    if ( v30 )
      CoTaskMemFree(v30);
    v10[1] = v28;
    v29 = 1;
    v10[3] = -1;
    v10[2] = -1;
  }
  if ( !v29 )
    goto LABEL_24;
LABEL_25:
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v43, &v36);
  if ( v36 )
    (**v36)(v36, 1);
  v11 = operator new(0x20u);
  if ( !v11 )
  {
    v36 = 0;
LABEL_29:
    wistd::unique_ptr<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0>>::reset(&v36);
    goto LABEL_31;
  }
  *v11 = &Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::`vftable';
  v11[1] = 0;
  v11[2] = 0;
  v11[3] = 0;
  v12 = (void (__fastcall **)(_QWORD, __int64))*v11;
  v36 = (void (__fastcall ***)(_QWORD, __int64))v11;
  if ( !((unsigned __int8 (__fastcall *)(_QWORD *))v12[5])(v11) )
    goto LABEL_29;
LABEL_31:
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v40, &v36);
  if ( v36 )
    (**v36)(v36, 1);
  v13 = operator new(0x20u);
  if ( v13 )
  {
    v13[1] = 0;
    v13[2] = 0;
    v13[3] = 0;
    *v13 = &Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::`vftable';
    v36 = (void (__fastcall ***)(_QWORD, __int64))v13;
    if ( Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::Initialize((Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *)v13) )
      goto LABEL_35;
  }
  else
  {
    v36 = 0;
  }
  wistd::unique_ptr<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2>>::reset(&v36);
LABEL_35:
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&pv, &v36);
  if ( v36 )
    (**v36)(v36, 1);
  v14 = v43;
  v15 = (void (__fastcall ***)(LPVOID, __int64))pv;
  v16 = v40;
  if ( v43 && v40 )
  {
    if ( pv )
    {
      v45[0] = v43;
      v17 = v45;
      v45[1] = v40;
      v45[2] = pv;
      while ( v17 != v46 )
      {
        v18 = v4[6];
        if ( v18 <= (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 32LL))(*v17) )
        {
          v19 = v41;
          if ( (*(unsigned __int8 (__fastcall **)(_QWORD, unsigned __int16 *))(*(_QWORD *)*v17 + 8LL))(*v17, v41) )
          {
            if ( v15 )
              (**v15)(v15, 1);
            if ( v16 )
              (**v16)(v16, 1);
            if ( v14 )
              (**v14)(v14, 1);
            goto LABEL_103;
          }
        }
        ++v17;
      }
      if ( v15 )
        (**v15)(v15, 1);
      if ( v16 )
        (**v16)(v16, 1);
      if ( v14 )
        goto LABEL_56;
      goto LABEL_57;
    }
  }
  else if ( pv )
  {
    (**(void (__fastcall ***)(LPVOID, __int64))pv)(pv, 1);
  }
  if ( v16 )
    (**v16)(v16, 1);
  if ( v14 )
LABEL_56:
    (**v14)(v14, 1);
LABEL_57:
  v20 = operator new(0x20u);
  v22 = v20;
  if ( !v20 )
  {
    v36 = 0;
LABEL_59:
    wistd::unique_ptr<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0>>::reset(&v36);
    goto LABEL_60;
  }
  *v20 = &Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::`vftable';
  v20[1] = 0;
  v20[2] = 0;
  v20[3] = 0;
  v36 = (void (__fastcall ***)(_QWORD, __int64))v20;
  pv = 0;
  if ( (int)Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(
              L"SOFTWARE\\Microsoft\\Windows Embedded\\Lockdown",
              0,
              (char *)&pv,
              v21) < 0 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_59;
  }
  v31 = pv;
  v32 = 0;
  if ( pv )
  {
    v33 = (void *)v22[1];
    if ( v33 )
      CoTaskMemFree(v33);
    v22[1] = v31;
    v32 = 1;
    v22[3] = -1;
    v22[2] = -1;
  }
  if ( !v32 )
    goto LABEL_59;
LABEL_60:
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v43, &v36);
  if ( v36 )
    (**v36)(v36, 1);
  v23 = operator new(0x20u);
  if ( !v23 )
  {
    v36 = 0;
LABEL_64:
    wistd::unique_ptr<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0>>::reset(&v36);
    goto LABEL_66;
  }
  v36 = (void (__fastcall ***)(_QWORD, __int64))v23;
  *v23 = &Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::`vftable';
  v23[1] = 0;
  v23[2] = 0;
  v23[3] = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD *))(*v23 + 40LL))(v23) )
    goto LABEL_64;
LABEL_66:
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v40, &v36);
  if ( v36 )
    (**v36)(v36, 1);
  v24 = operator new(0x20u);
  if ( v24 )
  {
    v24[1] = 0;
    v24[2] = 0;
    v24[3] = 0;
    *v24 = &Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::`vftable';
    v36 = (void (__fastcall ***)(_QWORD, __int64))v24;
    if ( Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::Initialize((Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *)v24) )
      goto LABEL_70;
  }
  else
  {
    v36 = 0;
  }
  wistd::unique_ptr<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2>>::reset(&v36);
LABEL_70:
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&pv, &v36);
  if ( v36 )
    (**v36)(v36, 1);
  v25 = v43;
  v26 = v40;
  v27 = (void (__fastcall ***)(LPVOID, __int64))pv;
  if ( v43 && v40 )
  {
    if ( !pv )
      goto LABEL_10;
    v46[0] = v43;
    v6 = v46;
    v46[1] = v40;
    v46[2] = pv;
    while ( v6 != &v47 )
    {
      v7 = v4[6];
      if ( v7 <= (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)*v6 + 32LL))(*v6)
        && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)*v6 + 16LL))(*v6) )
      {
        if ( v27 )
          (**v27)(v27, 1);
        if ( v26 )
          (**v26)(v26, 1);
        if ( v25 )
          (**v25)(v25, 1);
        goto LABEL_111;
      }
      ++v6;
    }
  }
  if ( v27 )
    (**v27)(v27, 1);
LABEL_10:
  if ( v26 )
    (**v26)(v26, 1);
  if ( v25 )
    (**v25)(v25, 1);
  if ( !Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::IsGlobalProfileConfigured((Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *)v4) )
  {
    *(_DWORD *)v42 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v4);
    operator delete(v4);
    return 0;
  }
LABEL_111:
  v19 = v41;
LABEL_103:
  Windows::Internal::AssignedAccess::AAManagerHelper::AAManagerHelper((Windows::Internal::AssignedAccess::AAManagerHelper *)v44);
  if ( v37 )
    AssignedAccessTypeForUserWithoutGroup = Windows::Internal::AssignedAccess::AAManagerHelper::GetAssignedAccessTypeForUserWithoutGroup(
                                              (Windows::Internal::AssignedAccess::AAManagerHelper *)v44,
                                              v19,
                                              v42);
  else
    AssignedAccessTypeForUserWithoutGroup = Windows::Internal::AssignedAccess::AAManagerHelper::GetAssignedAccessTypeForUserWithGroup(
                                              (Windows::Internal::AssignedAccess::AAManagerHelper *)v44,
                                              v19,
                                              v42);
  v35 = AssignedAccessTypeForUserWithoutGroup;
  if ( AssignedAccessTypeForUserWithoutGroup >= 0 )
  {
    wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfiguration,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfiguration,wil::err_returncode_policy>(v44);
    wistd::unique_ptr<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper>>::reset(&v39);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x33,
    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
    (const char *)(unsigned int)AssignedAccessTypeForUserWithoutGroup,
    (int)v36);
  wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfiguration,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfiguration,wil::err_returncode_policy>(v44);
  wistd::unique_ptr<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper>>::reset(&v39);
  return v35;
}

```

## disassembly

```asm
0x140009900  push    rbp
0x140009902  push    rbx
0x140009903  push    rsi
0x140009904  lea     rbp, [rsp-47h]
0x140009909  sub     rsp, 0C0h
0x140009910  mov     [rbp+57h+var_88], rcx
0x140009914  mov     ecx, 20h ; ' '; Size
0x140009919  mov     [rbp+57h+var_80], r8
0x14000991d  mov     [rbp+57h+var_A8], dl
0x140009920  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009925  xor     ebx, ebx
0x140009927  mov     rsi, rax
0x14000992a  test    rax, rax
0x14000992d  jz      loc_140009A82
0x140009933  mov     [rax+18h], rbx
0x140009937  mov     rcx, rax; this
0x14000993a  mov     [rax], rbx
0x14000993d  mov     [rax+8], rbx
0x140009941  mov     [rax+10h], rbx
0x140009945  mov     [rbp+57h+var_98], rax
0x140009949  call    ?Initialize@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@AEAA_NXZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::Initialize(void)
0x14000994e  test    al, al
0x140009950  jz      loc_140009A86
0x140009956  test    rsi, rsi
0x140009959  jnz     loc_140009A98
0x14000995f  mov     rcx, [rbp+5Fh]; this
0x140009963  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x14000996a  mov     r9d, 8000FFFFh; char *
0x140009970  mov     edx, 2Bh ; '+'; void *
0x140009975  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000997a  mov     eax, 8000FFFFh
0x14000997f  add     rsp, 0C0h
0x140009986  pop     rsi
0x140009987  pop     rbx
0x140009988  pop     rbp
0x140009989  retn
0x14000998a  test    r14, r14
0x14000998d  jz      short loc_1400099C5
0x14000998f  mov     [rbp+57h+var_48], r13
0x140009993  lea     r15, [rbp+57h+var_48]
0x140009997  mov     [rbp+57h+var_40], r12
0x14000999b  mov     [rbp+57h+var_38], r14
0x14000999f  nop
0x1400099a0  lea     rax, [rbp+57h+var_30]
0x1400099a4  cmp     r15, rax
0x1400099a7  jnz     loc_140009A4C
0x1400099ad  test    r14, r14
0x1400099b0  jz      short loc_1400099C5
0x1400099b2  mov     rax, [r14]
0x1400099b5  mov     edx, 1
0x1400099ba  mov     rcx, r14
0x1400099bd  mov     rax, [rax]
0x1400099c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400099c5  test    r12, r12
0x1400099c8  jz      short loc_1400099DE
0x1400099ca  mov     rax, [r12]
0x1400099ce  mov     edx, 1
0x1400099d3  mov     rcx, r12
0x1400099d6  mov     rax, [rax]
0x1400099d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400099de  test    r13, r13
0x1400099e1  jz      short loc_1400099F7
0x1400099e3  mov     rax, [r13+0]
0x1400099e7  mov     edx, 1
0x1400099ec  mov     rcx, r13
0x1400099ef  mov     rax, [rax]
0x1400099f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400099f7  mov     rcx, rsi; this
0x1400099fa  call    ?IsGlobalProfileConfigured@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@QEAA_NXZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::IsGlobalProfileConfigured(void)
0x1400099ff  test    al, al
0x140009a01  jnz     loc_14000A026
0x140009a07  mov     r8, [rbp+57h+var_80]
0x140009a0b  mov     [r8], ebx
0x140009a0e  test    rsi, rsi
0x140009a11  jnz     loc_140009EB9
0x140009a17  xor     eax, eax
0x140009a19  mov     r12, [rsp+0D0h+var_18]
0x140009a21  mov     r13, [rsp+0D0h+var_20]
0x140009a29  mov     r14, [rsp+0D0h+var_28]
0x140009a31  mov     rdi, [rsp+0D0h+arg_8]
0x140009a39  mov     r15, [rsp+0D0h+var_30]
0x140009a41  add     rsp, 0C0h
0x140009a48  pop     rsi
0x140009a49  pop     rbx
0x140009a4a  pop     rbp
0x140009a4b  retn
0x140009a4c  mov     rcx, [r15]
0x140009a4f  mov     edi, [rsi+18h]
0x140009a52  mov     rax, [rcx]
0x140009a55  mov     rax, [rax+20h]
0x140009a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a5e  cmp     edi, eax
0x140009a60  ja      short loc_140009A79
0x140009a62  mov     rcx, [r15]
0x140009a65  mov     rax, [rcx]
0x140009a68  mov     rax, [rax+10h]
0x140009a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a71  test    al, al
0x140009a73  jnz     loc_140009FF0
0x140009a79  add     r15, 8
0x140009a7d  jmp     loc_1400099A0
0x140009a82  mov     [rbp+57h+var_98], rbx
0x140009a86  lea     rcx, [rbp+57h+var_98]
0x140009a8a  call    ?reset@?$unique_ptr@VAssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVAssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper>>::reset(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *)
0x140009a8f  mov     rsi, [rbp+57h+var_98]
0x140009a93  jmp     loc_140009956
0x140009a98  mov     [rsp+0D0h+arg_8], rdi
0x140009aa0  mov     ecx, 20h ; ' '; Size
0x140009aa5  mov     [rsp+0D0h+var_20], r13
0x140009aad  mov     [rsp+0D0h+var_28], r14
0x140009ab5  mov     [rsp+0D0h+var_30], r15
0x140009abd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009ac2  lea     r15, ??_7AssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@6B@; const Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::`vftable'
0x140009ac9  mov     rdi, rax
0x140009acc  test    rax, rax
0x140009acf  jnz     loc_140009E2F
0x140009ad5  mov     [rbp+57h+var_B0], rbx
0x140009ad9  lea     rcx, [rbp+57h+var_B0]
0x140009add  call    ?reset@?$unique_ptr@VAssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVAssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0>>::reset(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0 *)
0x140009ae2  lea     rdx, [rbp+57h+var_B0]
0x140009ae6  lea     rcx, [rbp+57h+var_78]
0x140009aea  call    ??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x140009aef  mov     rcx, [rbp+57h+var_B0]
0x140009af3  test    rcx, rcx
0x140009af6  jz      short loc_140009B08
0x140009af8  mov     rax, [rcx]
0x140009afb  mov     edx, 1
0x140009b00  mov     rax, [rax]
0x140009b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b08  mov     ecx, 20h ; ' '; Size
0x140009b0d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009b12  mov     rdx, rax
0x140009b15  lea     rax, ??_7AssignedAccessConfigStoreV1@AssignedAccess@Internal@Windows@@6B@; const Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::`vftable'
0x140009b1c  test    rdx, rdx
0x140009b1f  jnz     short loc_140009B30
0x140009b21  mov     [rbp+57h+var_B0], rbx
0x140009b25  lea     rcx, [rbp+57h+var_B0]
0x140009b29  call    ?reset@?$unique_ptr@VAssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVAssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0>>::reset(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0 *)
0x140009b2e  jmp     short loc_140009B56
0x140009b30  mov     [rdx], rax
0x140009b33  mov     [rdx+8], rbx
0x140009b37  mov     [rdx+10h], rbx
0x140009b3b  mov     [rdx+18h], rbx
0x140009b3f  mov     rcx, [rdx]
0x140009b42  mov     [rbp+57h+var_B0], rdx
0x140009b46  mov     rax, [rcx+28h]
0x140009b4a  mov     rcx, rdx
0x140009b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b52  test    al, al
0x140009b54  jz      short loc_140009B25
0x140009b56  lea     rdx, [rbp+57h+var_B0]
0x140009b5a  lea     rcx, [rbp+57h+var_90]
0x140009b5e  call    ??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x140009b63  mov     rcx, [rbp+57h+var_B0]
0x140009b67  test    rcx, rcx
0x140009b6a  jz      short loc_140009B7C
0x140009b6c  mov     rax, [rcx]
0x140009b6f  mov     edx, 1
0x140009b74  mov     rax, [rax]
0x140009b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b7c  mov     ecx, 20h ; ' '; Size
0x140009b81  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009b86  test    rax, rax
0x140009b89  jz      loc_140009F44
0x140009b8f  mov     [rax+8], rbx
0x140009b93  lea     rdi, ??_7AssignedAccessConfigStoreV2@AssignedAccess@Internal@Windows@@6B@; const Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::`vftable'
0x140009b9a  mov     [rax+10h], rbx
0x140009b9e  mov     rcx, rax
0x140009ba1  mov     [rax+18h], rbx
0x140009ba5  mov     [rax], rdi
0x140009ba8  mov     [rbp+57h+var_B0], rax
0x140009bac  mov     rax, [rdi+28h]
0x140009bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009bb5  test    al, al
0x140009bb7  jz      loc_140009F48
0x140009bbd  lea     rdx, [rbp+57h+var_B0]
0x140009bc1  lea     rcx, [rbp+57h+pv]
0x140009bc5  call    ??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x140009bca  mov     rcx, [rbp+57h+var_B0]
0x140009bce  test    rcx, rcx
0x140009bd1  jnz     loc_140009F68
0x140009bd7  mov     r13, [rbp+57h+var_78]
0x140009bdb  mov     r14, [rbp+57h+pv]
0x140009bdf  mov     [rsp+0D0h+var_18], r12
0x140009be7  mov     r12, [rbp+57h+var_90]
0x140009beb  test    r13, r13
0x140009bee  jz      short loc_140009BF5
0x140009bf0  test    r12, r12
0x140009bf3  jnz     short loc_140009C48
0x140009bf5  test    r14, r14
0x140009bf8  jz      short loc_140009C0D
0x140009bfa  mov     rax, [r14]
0x140009bfd  mov     edx, 1
0x140009c02  mov     rcx, r14
0x140009c05  mov     rax, [rax]
0x140009c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c0d  test    r12, r12
0x140009c10  jz      short loc_140009C26
0x140009c12  mov     rax, [r12]
0x140009c16  mov     edx, 1
0x140009c1b  mov     rcx, r12
0x140009c1e  mov     rax, [rax]
0x140009c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c26  test    r13, r13
0x140009c29  jz      loc_140009CF4
0x140009c2f  mov     rax, [r13+0]
0x140009c33  mov     edx, 1
0x140009c38  mov     rcx, r13
0x140009c3b  mov     rax, [rax]
0x140009c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c43  jmp     loc_140009CF4
0x140009c48  test    r14, r14
0x140009c4b  jz      short loc_140009C0D
0x140009c4d  mov     [rbp+57h+var_60], r13
0x140009c51  lea     r15, [rbp+57h+var_60]
0x140009c55  mov     [rbp+57h+var_58], r12
0x140009c59  mov     [rbp+57h+var_50], r14
0x140009c5d  nop     dword ptr [rax]
0x140009c60  lea     rax, [rbp+57h+var_48]
0x140009c64  cmp     r15, rax
0x140009c67  jz      short loc_140009CA3
0x140009c69  mov     rcx, [r15]
0x140009c6c  mov     edi, [rsi+18h]
0x140009c6f  mov     rax, [rcx]
0x140009c72  mov     rax, [rax+20h]
0x140009c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c7b  cmp     edi, eax
0x140009c7d  ja      short loc_140009C9D
0x140009c7f  mov     rcx, [r15]
0x140009c82  mov     rdi, [rbp+57h+var_88]
0x140009c86  mov     rdx, rdi
0x140009c89  mov     rax, [rcx]
0x140009c8c  mov     rax, [rax+8]
0x140009c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c95  test    al, al
0x140009c97  jnz     loc_140009F92
0x140009c9d  add     r15, 8
0x140009ca1  jmp     short loc_140009C60
0x140009ca3  test    r14, r14
0x140009ca6  jz      short loc_140009CBB
0x140009ca8  mov     rax, [r14]
0x140009cab  mov     edx, 1
0x140009cb0  mov     rcx, r14
0x140009cb3  mov     rax, [rax]
0x140009cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009cbb  test    r12, r12
0x140009cbe  jz      short loc_140009CD4
0x140009cc0  mov     rax, [r12]
0x140009cc4  mov     edx, 1
0x140009cc9  mov     rcx, r12
0x140009ccc  mov     rax, [rax]
0x140009ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009cd4  test    r13, r13
0x140009cd7  jz      short loc_140009CED
0x140009cd9  mov     rax, [r13+0]
0x140009cdd  mov     edx, 1
0x140009ce2  mov     rcx, r13
0x140009ce5  mov     rax, [rax]
0x140009ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ced  lea     r15, ??_7AssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@6B@; const Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::`vftable'
0x140009cf4  mov     ecx, 20h ; ' '; Size
0x140009cf9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009cfe  mov     rdi, rax
0x140009d01  test    rax, rax
0x140009d04  jnz     loc_140009E74
0x140009d0a  mov     [rbp+57h+var_B0], rbx
0x140009d0e  lea     rcx, [rbp+57h+var_B0]
0x140009d12  call    ?reset@?$unique_ptr@VAssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVAssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0>>::reset(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0 *)
0x140009d17  lea     rdx, [rbp+57h+var_B0]
0x140009d1b  lea     rcx, [rbp+57h+var_78]
0x140009d1f  call    ??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x140009d24  mov     rcx, [rbp+57h+var_B0]
0x140009d28  test    rcx, rcx
0x140009d2b  jz      short loc_140009D3D
0x140009d2d  mov     rax, [rcx]
0x140009d30  mov     edx, 1
0x140009d35  mov     rax, [rax]
0x140009d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d3d  mov     ecx, 20h ; ' '; Size
0x140009d42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009d47  mov     rdx, rax
0x140009d4a  test    rax, rax
0x140009d4d  jnz     short loc_140009D5E
0x140009d4f  mov     [rbp+57h+var_B0], rbx
0x140009d53  lea     rcx, [rbp+57h+var_B0]
0x140009d57  call    ?reset@?$unique_ptr@VAssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVAssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0>>::reset(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0 *)
0x140009d5c  jmp     short loc_140009D8B
0x140009d5e  lea     rax, ??_7AssignedAccessConfigStoreV1@AssignedAccess@Internal@Windows@@6B@; const Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::`vftable'
0x140009d65  mov     [rbp+57h+var_B0], rdx
0x140009d69  mov     [rdx], rax
0x140009d6c  mov     [rdx+8], rbx
0x140009d70  mov     [rdx+10h], rbx
0x140009d74  mov     [rdx+18h], rbx
0x140009d78  mov     rcx, [rdx]
0x140009d7b  mov     rax, [rcx+28h]
0x140009d7f  mov     rcx, rdx
0x140009d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d87  test    al, al
0x140009d89  jz      short loc_140009D53
0x140009d8b  lea     rdx, [rbp+57h+var_B0]
  ... truncated ...
```
