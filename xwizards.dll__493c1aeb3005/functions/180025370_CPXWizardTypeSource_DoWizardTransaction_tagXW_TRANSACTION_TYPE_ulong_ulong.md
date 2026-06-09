# CPXWizardTypeSource::DoWizardTransaction(tagXW_TRANSACTION_TYPE,ulong,ulong)

- ea: `0x180025370`
- end: `0x180025645`
- name: `?DoWizardTransaction@CPXWizardTypeSource@@UEAAJW4tagXW_TRANSACTION_TYPE@@KK@Z`
- size: `725`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001588`
- `0x18000ae04`
- `0x180021164`
- `0x180021260`
- `0x1800250e4`
- `0x180025370`
- `0x180026090`
- `0x180026178`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180025599`
- `msvcrt!??3@YAXPEAX@Z` at `0x180025599`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002540e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002540e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002556b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002556b`

## pseudocode

```c
__int64 __fastcall CPXWizardTypeSource::DoWizardTransaction(__int64 a1, int a2, int a3, int a4)
{
  CXWCriticalSection *v8; // r13
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  volatile signed __int32 *v12; // rsi
  _DWORD *v13; // rax
  __int64 v14; // r14
  __int64 v15; // rdx
  unsigned int v16; // r9d
  __int64 v17; // rax
  CTask **v18; // r12
  unsigned int *v19; // r15
  int v20; // edx
  int v21; // eax
  int v22; // edx
  _QWORD ***v23; // rax
  _QWORD **v24; // rcx
  void *v26; // [rsp+30h] [rbp-48h]
  __int64 v27; // [rsp+80h] [rbp+8h]

  v8 = (CXWCriticalSection *)(a1 + 200);
  v9 = CXWCriticalSection::HrEnterCriticalSection((CXWCriticalSection *)(a1 + 200));
  if ( (v9 & 0x80000000) != 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v11 = 36;
      goto LABEL_5;
    }
    return v9;
  }
  v27 = *(_QWORD *)(a1 + 192);
  v12 = (volatile signed __int32 *)(a1 + 248);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 248));
  v13 = CoTaskMemAlloc(0xCu);
  v26 = v13;
  if ( !v13 )
  {
    v9 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids, 2147942414LL);
    goto LABEL_37;
  }
  *v13 = a2;
  v13[1] = a3;
  v13[2] = a4;
  v14 = *(_QWORD *)(a1 + 184);
  try
  {
    v15 = std::_List_buy<_XWIZARD_TRANSACTION_ELEMENT *>::_Buynode<_XWIZARD_TRANSACTION_ELEMENT * const &>();
    v17 = *(_QWORD *)(a1 + 192);
    if ( v17 == 0xAAAAAAAAAAAAAA9LL )
      std::_Xlength_error("list<T> too long");
    *(_QWORD *)(a1 + 192) = v17 + 1;
    *(_QWORD *)(v14 + 8) = v15;
    **(_QWORD **)(v15 + 8) = v15;
  }
  catch ( std::bad_alloc )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids, 2147942414LL);
    CoTaskMemFree(v26);
    v9 = -2147024882;
    v12 = (volatile signed __int32 *)(a1 + 248);
    goto LABEL_37;
  }
  if ( v27 )
  {
LABEL_37:
    _InterlockedDecrement(v12);
    CXWCriticalSection::HrLeaveCriticalSection(v8);
    return v9;
  }
  v18 = (CTask **)(a1 + 64);
  while ( *(_QWORD *)(a1 + 192) )
  {
    v19 = *(unsigned int **)(**(_QWORD **)(a1 + 184) + 16LL);
    switch ( *v19 )
    {
      case 1u:
        v22 = 0;
        goto LABEL_24;
      case 2u:
        v22 = 1;
LABEL_24:
        v21 = CTask::HrApplyOrResetWizard(*v18, v22, v19[1], v16);
        goto LABEL_25;
      case 3u:
        v20 = 0;
LABEL_20:
        v21 = CTask::HrCommitOrAbortWizard(*v18, v20, v19[1], v19[2]);
LABEL_25:
        v9 = v21;
        if ( v21 >= 0 )
          goto LABEL_29;
        goto LABEL_26;
      case 4u:
        v20 = 1;
        goto LABEL_20;
    }
    v9 = -2147418113;
LABEL_26:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids, v9);
LABEL_29:
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int))(**((_QWORD **)*v18 + 36) + 136LL))(
      *((_QWORD *)*v18 + 36),
      *v19,
      *((unsigned int *)*v18 + 60),
      v9,
      v19[2]);
    CoTaskMemFree(v19);
    v23 = *(_QWORD ****)(a1 + 184);
    v24 = *v23;
    if ( *v23 != v23 )
    {
      *v24[1] = *v24;
      (*v24)[1] = v24[1];
      operator delete(v24);
      --*(_QWORD *)(a1 + 192);
    }
  }
  _InterlockedDecrement(v12);
  CXWCriticalSection::HrLeaveCriticalSection(v8);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v11 = 40;
LABEL_5:
    WPP_SF_d(v10[2], v11, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x180025370  mov     [rsp+arg_8], rbx
0x180025375  mov     [rsp+arg_10], rsi
0x18002537a  push    rdi
0x18002537b  push    r12
0x18002537d  push    r13
0x18002537f  push    r14
0x180025381  push    r15
0x180025383  sub     rsp, 50h
0x180025387  mov     r14d, r9d
0x18002538a  mov     r15d, r8d
0x18002538d  mov     r12d, edx
0x180025390  mov     rdi, rcx
0x180025393  lea     r13, [rcx+0C8h]
0x18002539a  mov     rcx, r13; this
0x18002539d  call    ?HrEnterCriticalSection@CXWCriticalSection@@QEAAJXZ; CXWCriticalSection::HrEnterCriticalSection(void)
0x1800253a2  mov     ebx, eax
0x1800253a4  test    eax, eax
0x1800253a6  jns     short loc_1800253E6
0x1800253a8  lea     r14, WPP_GLOBAL_Control
0x1800253af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800253b6  cmp     rcx, r14
0x1800253b9  jz      loc_180025629
0x1800253bf  test    byte ptr [rcx+1Ch], 4
0x1800253c3  jz      loc_180025629
0x1800253c9  mov     edx, 24h ; '$'
0x1800253ce  mov     r9d, ebx
0x1800253d1  lea     r8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids
0x1800253d8  mov     rcx, [rcx+10h]
0x1800253dc  call    WPP_SF_d
0x1800253e1  jmp     loc_180025629
0x1800253e6  mov     [rsp+78h+var_40], r13
0x1800253eb  mov     rax, [rdi+0C0h]
0x1800253f2  mov     [rsp+78h+arg_0], rax
0x1800253fa  lea     rsi, [rdi+0F8h]
0x180025401  mov     [rsp+78h+var_38], rsi
0x180025406  lock inc dword ptr [rsi]
0x180025409  mov     ecx, 0Ch; cb
0x18002540e  call    cs:__imp_CoTaskMemAlloc
0x180025414  mov     [rsp+78h+var_48], rax
0x180025419  test    rax, rax
0x18002541c  jz      loc_1800255E5
0x180025422  mov     [rax], r12d
0x180025425  mov     [rax+4], r15d
0x180025429  mov     [rax+8], r14d
0x18002542d  mov     r14, [rdi+0B8h]
0x180025434  lea     r9, [rsp+78h+var_48]
0x180025439  mov     r8, [r14+8]
0x18002543d  mov     rdx, r14
0x180025440  call    ??$_Buynode@AEBQEAU_XWIZARD_TRANSACTION_ELEMENT@@@?$_List_buy@PEAU_XWIZARD_TRANSACTION_ELEMENT@@V?$allocator@PEAU_XWIZARD_TRANSACTION_ELEMENT@@@std@@@std@@QEAAPEAU?$_List_node@PEAU_XWIZARD_TRANSACTION_ELEMENT@@PEAX@1@PEAU21@0AEBQEAU_XWIZARD_TRANSACTION_ELEMENT@@@Z; std::_List_buy<_XWIZARD_TRANSACTION_ELEMENT *>::_Buynode<_XWIZARD_TRANSACTION_ELEMENT * const &>(std::_List_node<_XWIZARD_TRANSACTION_ELEMENT *,void *> *,std::_List_node<_XWIZARD_TRANSACTION_ELEMENT *,void *> *,_XWIZARD_TRANSACTION_ELEMENT * const &)
0x180025445  mov     rdx, rax
0x180025448  mov     rax, [rdi+0C0h]
0x18002544f  mov     rcx, 0AAAAAAAAAAAAAA9h
0x180025459  sub     rcx, rax
0x18002545c  cmp     rcx, 1
0x180025460  jnb     short loc_18002546E
0x180025462  lea     rcx, aListTTooLong; "list<T> too long"
0x180025469  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002546e  inc     rax
0x180025471  mov     [rdi+0C0h], rax
0x180025478  mov     [r14+8], rdx
0x18002547c  mov     rax, [rdx+8]
0x180025480  mov     [rax], rdx
0x180025483  cmp     [rsp+78h+arg_0], 0
0x18002548c  jnz     loc_18002561E
0x180025492  lea     r12, [rdi+40h]
0x180025496  lea     r14, WPP_GLOBAL_Control
0x18002549d  cmp     qword ptr [rdi+0C0h], 0
0x1800254a5  jz      loc_1800255AB
0x1800254ab  mov     rax, [rdi+0B8h]
0x1800254b2  mov     rcx, [rax]
0x1800254b5  mov     r15, [rcx+10h]
0x1800254b9  mov     ecx, [r15]
0x1800254bc  sub     ecx, 1
0x1800254bf  jz      short loc_1800254FA
0x1800254c1  sub     ecx, 1
0x1800254c4  jz      short loc_1800254F3
0x1800254c6  sub     ecx, 1
0x1800254c9  jz      short loc_1800254EF
0x1800254cb  cmp     ecx, 1
0x1800254ce  jz      short loc_1800254D7
0x1800254d0  mov     ebx, 8000FFFFh
0x1800254d5  jmp     short loc_18002550F
0x1800254d7  mov     edx, 1; int
0x1800254dc  mov     r8d, [r15+4]; unsigned int
0x1800254e0  mov     r9d, [r15+8]; unsigned int
0x1800254e4  mov     rcx, [r12]; this
0x1800254e8  call    ?HrCommitOrAbortWizard@CTask@@AEAAJHKK@Z; CTask::HrCommitOrAbortWizard(int,ulong,ulong)
0x1800254ed  jmp     short loc_180025509
0x1800254ef  xor     edx, edx
0x1800254f1  jmp     short loc_1800254DC
0x1800254f3  mov     edx, 1
0x1800254f8  jmp     short loc_1800254FC
0x1800254fa  xor     edx, edx; int
0x1800254fc  mov     r8d, [r15+4]; unsigned int
0x180025500  mov     rcx, [r12]; this
0x180025504  call    ?HrApplyOrResetWizard@CTask@@AEAAJHKK@Z; CTask::HrApplyOrResetWizard(int,ulong,ulong)
0x180025509  mov     ebx, eax
0x18002550b  test    eax, eax
0x18002550d  jns     short loc_180025539
0x18002550f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025516  cmp     rcx, r14
0x180025519  jz      short loc_180025539
0x18002551b  test    byte ptr [rcx+1Ch], 4
0x18002551f  jz      short loc_180025539
0x180025521  mov     edx, 27h ; '''
0x180025526  mov     r9d, ebx
0x180025529  lea     r8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids
0x180025530  mov     rcx, [rcx+10h]
0x180025534  call    WPP_SF_d
0x180025539  mov     r8, [r12]
0x18002553d  mov     rcx, [r8+120h]
0x180025544  mov     rax, [rcx]
0x180025547  mov     edx, [r15+8]
0x18002554b  mov     [rsp+78h+var_58], edx
0x18002554f  mov     r9d, ebx
0x180025552  mov     r8d, [r8+0F0h]
0x180025559  mov     edx, [r15]
0x18002555c  mov     rax, [rax+88h]
0x180025563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025568  mov     rcx, r15; pv
0x18002556b  call    cs:__imp_CoTaskMemFree
0x180025571  mov     rax, [rdi+0B8h]
0x180025578  mov     rcx, [rax]
0x18002557b  cmp     rcx, rax
0x18002557e  jz      loc_18002549D
0x180025584  mov     rdx, [rcx+8]
0x180025588  mov     rax, [rcx]
0x18002558b  mov     [rdx], rax
0x18002558e  mov     rdx, [rcx]
0x180025591  mov     rax, [rcx+8]
0x180025595  mov     [rdx+8], rax
0x180025599  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002559f  dec     qword ptr [rdi+0C0h]
0x1800255a6  jmp     loc_18002549D
0x1800255ab  lock dec dword ptr [rsi]
0x1800255ae  mov     rcx, r13; this
0x1800255b1  call    ?HrLeaveCriticalSection@CXWCriticalSection@@QEAAJXZ; CXWCriticalSection::HrLeaveCriticalSection(void)
0x1800255b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800255bd  cmp     rcx, r14
0x1800255c0  jz      short loc_180025629
0x1800255c2  test    byte ptr [rcx+1Ch], 10h
0x1800255c6  jz      short loc_180025629
0x1800255c8  mov     edx, 28h ; '('
0x1800255cd  jmp     loc_1800253CE
0x1800255d2  mov     ebx, dword ptr [rsp+78h+arg_0]
0x1800255d9  mov     r13, [rsp+78h+var_40]
0x1800255de  mov     rsi, [rsp+78h+var_38]
0x1800255e3  jmp     short loc_18002561E
0x1800255e5  mov     ebx, 8007000Eh
0x1800255ea  lea     r14, WPP_GLOBAL_Control
0x1800255f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800255f8  cmp     rcx, r14
0x1800255fb  jz      short loc_18002561E
0x1800255fd  test    byte ptr [rcx+1Ch], 4
0x180025601  jz      short loc_18002561E
0x180025603  mov     edx, 25h ; '%'
0x180025608  mov     r9d, 8007000Eh
0x18002560e  lea     r8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids
0x180025615  mov     rcx, [rcx+10h]
0x180025619  call    WPP_SF_d
0x18002561e  lock dec dword ptr [rsi]
0x180025621  mov     rcx, r13; this
0x180025624  call    ?HrLeaveCriticalSection@CXWCriticalSection@@QEAAJXZ; CXWCriticalSection::HrLeaveCriticalSection(void)
0x180025629  mov     eax, ebx
0x18002562b  lea     r11, [rsp+78h+var_28]
0x180025630  mov     rbx, [r11+38h]
0x180025634  mov     rsi, [r11+40h]
0x180025638  mov     rsp, r11
0x18002563b  pop     r15
0x18002563d  pop     r14
0x18002563f  pop     r13
0x180025641  pop     r12
0x180025643  pop     rdi
0x180025644  retn
```
