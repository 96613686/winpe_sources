# CXWizardUIPageBase<CInfraAdapterPage,&_GUID const CLSID_InfraAdapterPage,10607,10106>::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800247f0`
- end: `0x1800249cc`
- name: `?PageDlgProc@?$CXWizardUIPageBase@VCInfraAdapterPage@@$1?CLSID_InfraAdapterPage@@3U_GUID@@B$0CJGP@$0CHHK@@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `476`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003014`
- `0x180008560`
- `0x1800247f0`
- `0x180026ce0`
- `0x180026d58`
- `0x180026df4`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024863`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024863`
- `USER32!SetWindowLongPtrW` at `0x1800249b2`
- `USER32!SetWindowLongPtrW` at `0x1800249b2`
- `USER32!GetPropW` at `0x180024814`
- `USER32!GetPropW` at `0x180024814`
- `USER32!SetPropW` at `0x1800248b2`
- `USER32!SetPropW` at `0x1800248b2`

## pseudocode

```c
__int64 __fastcall CXWizardUIPageBase<CInfraAdapterPage,&_GUID const CLSID_InfraAdapterPage,10607,10106>::PageDlgProc(
        AtlThunkData_t *hWnd,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  AtlThunkData_t **PropW; // rbx
  __int64 v9; // rsi
  __int64 v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // rdx
  LONG_PTR v13; // rdi
  AtlThunkData_t *v14; // rax
  __int64 v15; // rax
  __int64 (__fastcall *v16)(AtlThunkData_t **); // rax
  AtlThunkData_t *v17; // rax
  void *v18; // r14
  AtlThunkData_t *Data; // rax
  WNDPROC v20; // rax
  __int64 *v22; // [rsp+30h] [rbp-58h] BYREF
  char v23; // [rsp+38h] [rbp-50h]

  PropW = (AtlThunkData_t **)GetPropW((HWND)hWnd, L"SignupWizard");
  if ( PropW )
    goto LABEL_15;
  v23 = 0;
  v22 = qword_18003FA18;
  if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v22) < 0 )
  {
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v22);
    return 0;
  }
  v10 = qword_18003FA40;
  PropW = 0;
  if ( qword_18003FA40 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v12 = 0;
    while ( v10 )
    {
      if ( *(_DWORD *)(v10 + 8) == CurrentThreadId )
      {
        if ( v12 )
          *(_QWORD *)(v12 + 16) = *(_QWORD *)(v10 + 16);
        else
          qword_18003FA40 = *(_QWORD *)(v10 + 16);
        PropW = *(AtlThunkData_t ***)v10;
        break;
      }
      v12 = v10;
      v10 = *(_QWORD *)(v10 + 16);
    }
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v22);
  if ( !PropW )
  {
LABEL_15:
    v9 = 0;
    if ( !PropW )
      return v9;
  }
  else
  {
    SetPropW((HWND)hWnd, L"SignupWizard", PropW);
  }
  v13 = 0;
  if ( a2 == 78 )
  {
    switch ( *(_DWORD *)(a4 + 16) )
    {
      case 0xFFFFFF31:
        v17 = *PropW;
        if ( a3 == 4294967088LL )
          v16 = (__int64 (__fastcall *)(AtlThunkData_t **))*((_QWORD *)v17 + 16);
        else
          v16 = (__int64 (__fastcall *)(AtlThunkData_t **))*((_QWORD *)v17 + 17);
        break;
      case 0xFFFFFF32:
        v16 = (__int64 (__fastcall *)(AtlThunkData_t **))*((_QWORD *)*PropW + 18);
        break;
      case 0xFFFFFF38:
        v14 = *PropW;
        if ( a3 == 4294967089LL )
          v15 = (*((__int64 (__fastcall **)(AtlThunkData_t **))v14 + 13))(PropW);
        else
          v15 = (*((__int64 (__fastcall **)(AtlThunkData_t **))v14 + 14))(PropW);
        goto LABEL_28;
      default:
        goto LABEL_29;
    }
    v15 = v16(PropW);
LABEL_28:
    v13 = v15;
  }
LABEL_29:
  PropW[13] = hWnd;
  v18 = (void *)(*((__int64 (__fastcall **)(AtlThunkData_t **))PropW[12] + 2))(PropW + 12);
  Data = PropW[17];
  if ( Data || (Data = AtlThunk_AllocateData(), (PropW[17] = Data) != 0) )
    AtlThunk_InitData(Data, v18, (unsigned __int64)(PropW + 12) & -(__int64)(PropW != 0));
  v20 = AtlThunk_DataToCode(PropW[17]);
  v9 = ((__int64 (__fastcall *)(AtlThunkData_t *, _QWORD, __int64, __int64))v20)(hWnd, a2, a3, a4);
  if ( v13 )
    SetWindowLongPtrW((HWND)hWnd, 0, v13);
  return v9;
}

```

## disassembly

```asm
0x1800247f0  push    rbx
0x1800247f2  push    rbp
0x1800247f3  push    rsi
0x1800247f4  push    rdi
0x1800247f5  push    r12
0x1800247f7  push    r13
0x1800247f9  push    r14
0x1800247fb  push    r15
0x1800247fd  sub     rsp, 48h
0x180024801  mov     r12d, edx
0x180024804  mov     r13, r9
0x180024807  lea     rdx, aSignupwizard_1; "SignupWizard"
0x18002480e  mov     r15, r8
0x180024811  mov     rbp, rcx
0x180024814  call    cs:__imp_GetPropW
0x18002481a  mov     rbx, rax
0x18002481d  test    rax, rax
0x180024820  jnz     loc_1800248BA
0x180024826  lea     rax, qword_18003FA18
0x18002482d  mov     [rsp+88h+var_50], bl
0x180024831  lea     rcx, [rsp+88h+var_58]
0x180024836  mov     [rsp+88h+var_58], rax
0x18002483b  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180024840  test    eax, eax
0x180024842  jns     short loc_180024855
0x180024844  lea     rcx, [rsp+88h+var_58]
0x180024849  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002484e  xor     esi, esi
0x180024850  jmp     loc_1800249B8
0x180024855  mov     rdi, cs:qword_18003FA40
0x18002485c  xor     ebx, ebx
0x18002485e  test    rdi, rdi
0x180024861  jz      short loc_180024896
0x180024863  call    cs:__imp_GetCurrentThreadId
0x180024869  xor     edx, edx
0x18002486b  test    rdi, rdi
0x18002486e  jz      short loc_180024896
0x180024870  mov     rcx, [rdi+10h]
0x180024874  cmp     [rdi+8], eax
0x180024877  jz      short loc_180024881
0x180024879  mov     rdx, rdi
0x18002487c  mov     rdi, rcx
0x18002487f  jmp     short loc_18002486B
0x180024881  test    rdx, rdx
0x180024884  jnz     short loc_18002488F
0x180024886  mov     cs:qword_18003FA40, rcx
0x18002488d  jmp     short loc_180024893
0x18002488f  mov     [rdx+10h], rcx
0x180024893  mov     rbx, [rdi]
0x180024896  lea     rcx, [rsp+88h+var_58]
0x18002489b  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800248a0  test    rbx, rbx
0x1800248a3  jz      short loc_1800248BA
0x1800248a5  mov     r8, rbx; hData
0x1800248a8  lea     rdx, aSignupwizard_1; "SignupWizard"
0x1800248af  mov     rcx, rbp; hWnd
0x1800248b2  call    cs:__imp_SetPropW
0x1800248b8  jmp     short loc_1800248C5
0x1800248ba  xor     esi, esi
0x1800248bc  test    rbx, rbx
0x1800248bf  jz      loc_1800249B8
0x1800248c5  xor     edi, edi
0x1800248c7  cmp     r12d, 4Eh ; 'N'
0x1800248cb  jnz     short loc_180024937
0x1800248cd  mov     ecx, 0FFFFFF31h
0x1800248d2  cmp     [r13+10h], ecx
0x1800248d6  jz      short loc_18002490F
0x1800248d8  cmp     dword ptr [r13+10h], 0FFFFFF32h
0x1800248e0  jz      short loc_180024903
0x1800248e2  cmp     dword ptr [r13+10h], 0FFFFFF38h
0x1800248ea  jnz     short loc_180024937
0x1800248ec  mov     rax, [rbx]
0x1800248ef  cmp     r15, rcx
0x1800248f2  mov     rcx, rbx
0x1800248f5  jnz     short loc_1800248FD
0x1800248f7  mov     rax, [rax+68h]
0x1800248fb  jmp     short loc_18002492F
0x1800248fd  mov     rax, [rax+70h]
0x180024901  jmp     short loc_18002492F
0x180024903  mov     rax, [rbx]
0x180024906  mov     rax, [rax+90h]
0x18002490d  jmp     short loc_18002492C
0x18002490f  mov     rax, [rbx]
0x180024912  mov     ecx, 0FFFFFF30h
0x180024917  cmp     r15, rcx
0x18002491a  jnz     short loc_180024925
0x18002491c  mov     rax, [rax+80h]
0x180024923  jmp     short loc_18002492C
0x180024925  mov     rax, [rax+88h]
0x18002492c  mov     rcx, rbx
0x18002492f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024934  mov     rdi, rax
0x180024937  lea     rcx, [rbx+60h]
0x18002493b  mov     [rbx+68h], rbp
0x18002493f  mov     rax, rbx
0x180024942  neg     rax
0x180024945  mov     rax, [rcx]
0x180024948  sbb     rsi, rsi
0x18002494b  and     rsi, rcx
0x18002494e  mov     rax, [rax+10h]
0x180024952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024957  mov     r14, rax
0x18002495a  mov     rax, [rbx+88h]
0x180024961  test    rax, rax
0x180024964  jnz     short loc_180024977
0x180024966  call    AtlThunk_AllocateData
0x18002496b  mov     [rbx+88h], rax
0x180024972  test    rax, rax
0x180024975  jz      short loc_180024985
0x180024977  mov     r8, rsi; FirstParameter
0x18002497a  mov     rdx, r14; Proc
0x18002497d  mov     rcx, rax; Thunk
0x180024980  call    AtlThunk_InitData
0x180024985  mov     rcx, [rbx+88h]; AtlThunkData_t *
0x18002498c  call    AtlThunk_DataToCode
0x180024991  mov     r9, r13
0x180024994  mov     r8, r15
0x180024997  mov     edx, r12d
0x18002499a  mov     rcx, rbp
0x18002499d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249a2  mov     rsi, rax
0x1800249a5  test    rdi, rdi
0x1800249a8  jz      short loc_1800249B8
0x1800249aa  mov     r8, rdi; dwNewLong
0x1800249ad  xor     edx, edx; nIndex
0x1800249af  mov     rcx, rbp; hWnd
0x1800249b2  call    cs:__imp_SetWindowLongPtrW
0x1800249b8  mov     rax, rsi
0x1800249bb  add     rsp, 48h
0x1800249bf  pop     r15
0x1800249c1  pop     r14
0x1800249c3  pop     r13
0x1800249c5  pop     r12
0x1800249c7  pop     rdi
0x1800249c8  pop     rsi
0x1800249c9  pop     rbp
0x1800249ca  pop     rbx
0x1800249cb  retn
```
