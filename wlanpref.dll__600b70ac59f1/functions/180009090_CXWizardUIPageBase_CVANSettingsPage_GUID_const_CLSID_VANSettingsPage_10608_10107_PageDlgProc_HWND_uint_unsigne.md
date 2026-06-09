# CXWizardUIPageBase<CVANSettingsPage,&_GUID const CLSID_VANSettingsPage,10608,10107>::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180009090`
- end: `0x18000926c`
- name: `?PageDlgProc@?$CXWizardUIPageBase@VCVANSettingsPage@@$1?CLSID_VANSettingsPage@@3U_GUID@@B$0CJHA@$0CHHL@@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `476`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003014`
- `0x180008560`
- `0x180009090`
- `0x180026ce0`
- `0x180026d58`
- `0x180026df4`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009103`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009103`
- `USER32!SetWindowLongPtrW` at `0x180009252`
- `USER32!SetWindowLongPtrW` at `0x180009252`
- `USER32!GetPropW` at `0x1800090b4`
- `USER32!GetPropW` at `0x1800090b4`
- `USER32!SetPropW` at `0x180009152`
- `USER32!SetPropW` at `0x180009152`

## pseudocode

```c
__int64 __fastcall CXWizardUIPageBase<CVANSettingsPage,&_GUID const CLSID_VANSettingsPage,10608,10107>::PageDlgProc(
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
0x180009090  push    rbx
0x180009092  push    rbp
0x180009093  push    rsi
0x180009094  push    rdi
0x180009095  push    r12
0x180009097  push    r13
0x180009099  push    r14
0x18000909b  push    r15
0x18000909d  sub     rsp, 48h
0x1800090a1  mov     r12d, edx
0x1800090a4  mov     r13, r9
0x1800090a7  lea     rdx, String; "SignupWizard"
0x1800090ae  mov     r15, r8
0x1800090b1  mov     rbp, rcx
0x1800090b4  call    cs:__imp_GetPropW
0x1800090ba  mov     rbx, rax
0x1800090bd  test    rax, rax
0x1800090c0  jnz     loc_18000915A
0x1800090c6  lea     rax, qword_18003FA18
0x1800090cd  mov     [rsp+88h+var_50], bl
0x1800090d1  lea     rcx, [rsp+88h+var_58]
0x1800090d6  mov     [rsp+88h+var_58], rax
0x1800090db  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x1800090e0  test    eax, eax
0x1800090e2  jns     short loc_1800090F5
0x1800090e4  lea     rcx, [rsp+88h+var_58]
0x1800090e9  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800090ee  xor     esi, esi
0x1800090f0  jmp     loc_180009258
0x1800090f5  mov     rdi, cs:qword_18003FA40
0x1800090fc  xor     ebx, ebx
0x1800090fe  test    rdi, rdi
0x180009101  jz      short loc_180009136
0x180009103  call    cs:__imp_GetCurrentThreadId
0x180009109  xor     edx, edx
0x18000910b  test    rdi, rdi
0x18000910e  jz      short loc_180009136
0x180009110  mov     rcx, [rdi+10h]
0x180009114  cmp     [rdi+8], eax
0x180009117  jz      short loc_180009121
0x180009119  mov     rdx, rdi
0x18000911c  mov     rdi, rcx
0x18000911f  jmp     short loc_18000910B
0x180009121  test    rdx, rdx
0x180009124  jnz     short loc_18000912F
0x180009126  mov     cs:qword_18003FA40, rcx
0x18000912d  jmp     short loc_180009133
0x18000912f  mov     [rdx+10h], rcx
0x180009133  mov     rbx, [rdi]
0x180009136  lea     rcx, [rsp+88h+var_58]
0x18000913b  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180009140  test    rbx, rbx
0x180009143  jz      short loc_18000915A
0x180009145  mov     r8, rbx; hData
0x180009148  lea     rdx, String; "SignupWizard"
0x18000914f  mov     rcx, rbp; hWnd
0x180009152  call    cs:__imp_SetPropW
0x180009158  jmp     short loc_180009165
0x18000915a  xor     esi, esi
0x18000915c  test    rbx, rbx
0x18000915f  jz      loc_180009258
0x180009165  xor     edi, edi
0x180009167  cmp     r12d, 4Eh ; 'N'
0x18000916b  jnz     short loc_1800091D7
0x18000916d  mov     ecx, 0FFFFFF31h
0x180009172  cmp     [r13+10h], ecx
0x180009176  jz      short loc_1800091AF
0x180009178  cmp     dword ptr [r13+10h], 0FFFFFF32h
0x180009180  jz      short loc_1800091A3
0x180009182  cmp     dword ptr [r13+10h], 0FFFFFF38h
0x18000918a  jnz     short loc_1800091D7
0x18000918c  mov     rax, [rbx]
0x18000918f  cmp     r15, rcx
0x180009192  mov     rcx, rbx
0x180009195  jnz     short loc_18000919D
0x180009197  mov     rax, [rax+68h]
0x18000919b  jmp     short loc_1800091CF
0x18000919d  mov     rax, [rax+70h]
0x1800091a1  jmp     short loc_1800091CF
0x1800091a3  mov     rax, [rbx]
0x1800091a6  mov     rax, [rax+90h]
0x1800091ad  jmp     short loc_1800091CC
0x1800091af  mov     rax, [rbx]
0x1800091b2  mov     ecx, 0FFFFFF30h
0x1800091b7  cmp     r15, rcx
0x1800091ba  jnz     short loc_1800091C5
0x1800091bc  mov     rax, [rax+80h]
0x1800091c3  jmp     short loc_1800091CC
0x1800091c5  mov     rax, [rax+88h]
0x1800091cc  mov     rcx, rbx
0x1800091cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091d4  mov     rdi, rax
0x1800091d7  lea     rcx, [rbx+60h]
0x1800091db  mov     [rbx+68h], rbp
0x1800091df  mov     rax, rbx
0x1800091e2  neg     rax
0x1800091e5  mov     rax, [rcx]
0x1800091e8  sbb     rsi, rsi
0x1800091eb  and     rsi, rcx
0x1800091ee  mov     rax, [rax+10h]
0x1800091f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091f7  mov     r14, rax
0x1800091fa  mov     rax, [rbx+88h]
0x180009201  test    rax, rax
0x180009204  jnz     short loc_180009217
0x180009206  call    AtlThunk_AllocateData
0x18000920b  mov     [rbx+88h], rax
0x180009212  test    rax, rax
0x180009215  jz      short loc_180009225
0x180009217  mov     r8, rsi; FirstParameter
0x18000921a  mov     rdx, r14; Proc
0x18000921d  mov     rcx, rax; Thunk
0x180009220  call    AtlThunk_InitData
0x180009225  mov     rcx, [rbx+88h]; AtlThunkData_t *
0x18000922c  call    AtlThunk_DataToCode
0x180009231  mov     r9, r13
0x180009234  mov     r8, r15
0x180009237  mov     edx, r12d
0x18000923a  mov     rcx, rbp
0x18000923d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009242  mov     rsi, rax
0x180009245  test    rdi, rdi
0x180009248  jz      short loc_180009258
0x18000924a  mov     r8, rdi; dwNewLong
0x18000924d  xor     edx, edx; nIndex
0x18000924f  mov     rcx, rbp; hWnd
0x180009252  call    cs:__imp_SetWindowLongPtrW
0x180009258  mov     rax, rsi
0x18000925b  add     rsp, 48h
0x18000925f  pop     r15
0x180009261  pop     r14
0x180009263  pop     r13
0x180009265  pop     r12
0x180009267  pop     rdi
0x180009268  pop     rsi
0x180009269  pop     rbp
0x18000926a  pop     rbx
0x18000926b  retn
```
