# CXWizardUIPageBase<CInfraSetupPage,&_GUID const CLSID_InfraSetupPage,10602,10102>::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180020030`
- end: `0x18002020c`
- name: `?PageDlgProc@?$CXWizardUIPageBase@VCInfraSetupPage@@$1?CLSID_InfraSetupPage@@3U_GUID@@B$0CJGK@$0CHHG@@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `476`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003014`
- `0x180008560`
- `0x180020030`
- `0x180026ce0`
- `0x180026d58`
- `0x180026df4`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800200a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800200a3`
- `USER32!SetWindowLongPtrW` at `0x1800201f2`
- `USER32!SetWindowLongPtrW` at `0x1800201f2`
- `USER32!GetPropW` at `0x180020054`
- `USER32!GetPropW` at `0x180020054`
- `USER32!SetPropW` at `0x1800200f2`
- `USER32!SetPropW` at `0x1800200f2`

## pseudocode

```c
__int64 __fastcall CXWizardUIPageBase<CInfraSetupPage,&_GUID const CLSID_InfraSetupPage,10602,10102>::PageDlgProc(
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
0x180020030  push    rbx
0x180020032  push    rbp
0x180020033  push    rsi
0x180020034  push    rdi
0x180020035  push    r12
0x180020037  push    r13
0x180020039  push    r14
0x18002003b  push    r15
0x18002003d  sub     rsp, 48h
0x180020041  mov     r12d, edx
0x180020044  mov     r13, r9
0x180020047  lea     rdx, aSignupwizard_0; "SignupWizard"
0x18002004e  mov     r15, r8
0x180020051  mov     rbp, rcx
0x180020054  call    cs:__imp_GetPropW
0x18002005a  mov     rbx, rax
0x18002005d  test    rax, rax
0x180020060  jnz     loc_1800200FA
0x180020066  lea     rax, qword_18003FA18
0x18002006d  mov     [rsp+88h+var_50], bl
0x180020071  lea     rcx, [rsp+88h+var_58]
0x180020076  mov     [rsp+88h+var_58], rax
0x18002007b  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180020080  test    eax, eax
0x180020082  jns     short loc_180020095
0x180020084  lea     rcx, [rsp+88h+var_58]
0x180020089  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002008e  xor     esi, esi
0x180020090  jmp     loc_1800201F8
0x180020095  mov     rdi, cs:qword_18003FA40
0x18002009c  xor     ebx, ebx
0x18002009e  test    rdi, rdi
0x1800200a1  jz      short loc_1800200D6
0x1800200a3  call    cs:__imp_GetCurrentThreadId
0x1800200a9  xor     edx, edx
0x1800200ab  test    rdi, rdi
0x1800200ae  jz      short loc_1800200D6
0x1800200b0  mov     rcx, [rdi+10h]
0x1800200b4  cmp     [rdi+8], eax
0x1800200b7  jz      short loc_1800200C1
0x1800200b9  mov     rdx, rdi
0x1800200bc  mov     rdi, rcx
0x1800200bf  jmp     short loc_1800200AB
0x1800200c1  test    rdx, rdx
0x1800200c4  jnz     short loc_1800200CF
0x1800200c6  mov     cs:qword_18003FA40, rcx
0x1800200cd  jmp     short loc_1800200D3
0x1800200cf  mov     [rdx+10h], rcx
0x1800200d3  mov     rbx, [rdi]
0x1800200d6  lea     rcx, [rsp+88h+var_58]
0x1800200db  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800200e0  test    rbx, rbx
0x1800200e3  jz      short loc_1800200FA
0x1800200e5  mov     r8, rbx; hData
0x1800200e8  lea     rdx, aSignupwizard_0; "SignupWizard"
0x1800200ef  mov     rcx, rbp; hWnd
0x1800200f2  call    cs:__imp_SetPropW
0x1800200f8  jmp     short loc_180020105
0x1800200fa  xor     esi, esi
0x1800200fc  test    rbx, rbx
0x1800200ff  jz      loc_1800201F8
0x180020105  xor     edi, edi
0x180020107  cmp     r12d, 4Eh ; 'N'
0x18002010b  jnz     short loc_180020177
0x18002010d  mov     ecx, 0FFFFFF31h
0x180020112  cmp     [r13+10h], ecx
0x180020116  jz      short loc_18002014F
0x180020118  cmp     dword ptr [r13+10h], 0FFFFFF32h
0x180020120  jz      short loc_180020143
0x180020122  cmp     dword ptr [r13+10h], 0FFFFFF38h
0x18002012a  jnz     short loc_180020177
0x18002012c  mov     rax, [rbx]
0x18002012f  cmp     r15, rcx
0x180020132  mov     rcx, rbx
0x180020135  jnz     short loc_18002013D
0x180020137  mov     rax, [rax+68h]
0x18002013b  jmp     short loc_18002016F
0x18002013d  mov     rax, [rax+70h]
0x180020141  jmp     short loc_18002016F
0x180020143  mov     rax, [rbx]
0x180020146  mov     rax, [rax+90h]
0x18002014d  jmp     short loc_18002016C
0x18002014f  mov     rax, [rbx]
0x180020152  mov     ecx, 0FFFFFF30h
0x180020157  cmp     r15, rcx
0x18002015a  jnz     short loc_180020165
0x18002015c  mov     rax, [rax+80h]
0x180020163  jmp     short loc_18002016C
0x180020165  mov     rax, [rax+88h]
0x18002016c  mov     rcx, rbx
0x18002016f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020174  mov     rdi, rax
0x180020177  lea     rcx, [rbx+60h]
0x18002017b  mov     [rbx+68h], rbp
0x18002017f  mov     rax, rbx
0x180020182  neg     rax
0x180020185  mov     rax, [rcx]
0x180020188  sbb     rsi, rsi
0x18002018b  and     rsi, rcx
0x18002018e  mov     rax, [rax+10h]
0x180020192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020197  mov     r14, rax
0x18002019a  mov     rax, [rbx+88h]
0x1800201a1  test    rax, rax
0x1800201a4  jnz     short loc_1800201B7
0x1800201a6  call    AtlThunk_AllocateData
0x1800201ab  mov     [rbx+88h], rax
0x1800201b2  test    rax, rax
0x1800201b5  jz      short loc_1800201C5
0x1800201b7  mov     r8, rsi; FirstParameter
0x1800201ba  mov     rdx, r14; Proc
0x1800201bd  mov     rcx, rax; Thunk
0x1800201c0  call    AtlThunk_InitData
0x1800201c5  mov     rcx, [rbx+88h]; AtlThunkData_t *
0x1800201cc  call    AtlThunk_DataToCode
0x1800201d1  mov     r9, r13
0x1800201d4  mov     r8, r15
0x1800201d7  mov     edx, r12d
0x1800201da  mov     rcx, rbp
0x1800201dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201e2  mov     rsi, rax
0x1800201e5  test    rdi, rdi
0x1800201e8  jz      short loc_1800201F8
0x1800201ea  mov     r8, rdi; dwNewLong
0x1800201ed  xor     edx, edx; nIndex
0x1800201ef  mov     rcx, rbp; hWnd
0x1800201f2  call    cs:__imp_SetWindowLongPtrW
0x1800201f8  mov     rax, rsi
0x1800201fb  add     rsp, 48h
0x1800201ff  pop     r15
0x180020201  pop     r14
0x180020203  pop     r13
0x180020205  pop     r12
0x180020207  pop     rdi
0x180020208  pop     rsi
0x180020209  pop     rbp
0x18002020a  pop     rbx
0x18002020b  retn
```
