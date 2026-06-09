# CXWizardPageWTLBaseClass<1570,CWcnPageCFETransferFailed,&_GUID const CLSID_WcnPageCFETransferFailed,0,700,0,0,0,0,0>::PageDlgProcBase(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18000af30`
- end: `0x18000b1a8`
- name: `?PageDlgProcBase@?$CXWizardPageWTLBaseClass@$0GCC@VCWcnPageCFETransferFailed@@$1?CLSID_WcnPageCFETransferFailed@@3U_GUID@@B$0A@$0CLM@$0A@$0A@$0A@$0A@$0A@@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `632`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800034c4`
- `0x18000a494`
- `0x18000af30`
- `0x18000ea20`
- `0x18000ea98`
- `0x18000eb34`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000afa3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000afa3`
- `USER32!GetPropW` at `0x18000af54`
- `USER32!GetPropW` at `0x18000af54`
- `USER32!SetWindowLongPtrW` at `0x18000b18e`
- `USER32!SetWindowLongPtrW` at `0x18000b18e`
- `USER32!SetPropW` at `0x18000b03d`
- `USER32!SetPropW` at `0x18000b03d`
- `USER32!GetParent` at `0x18000b069`
- `USER32!GetParent` at `0x18000b079`
- `USER32!GetParent` at `0x18000b089`
- `USER32!GetParent` at `0x18000b091`
- `USER32!GetParent` at `0x18000b069`
- `USER32!GetParent` at `0x18000b079`
- `USER32!GetParent` at `0x18000b089`
- `USER32!GetParent` at `0x18000b091`

## pseudocode

```c
__int64 __fastcall CXWizardPageWTLBaseClass<1570,CWcnPageCFETransferFailed,&_GUID const CLSID_WcnPageCFETransferFailed,0,700,0,0,0,0,0>::PageDlgProcBase(
        HWND hWnd,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  __int64 *PropW; // rbx
  __int64 v9; // rsi
  __int64 v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // rdx
  void *v13; // rsi
  AtlThunkData_t *Data; // rax
  bool v15; // cc
  HWND Parent; // rax
  HWND v17; // rax
  int v18; // r14d
  LONG_PTR v19; // rdi
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  int v24; // eax
  __int64 (__fastcall *v25)(HANDLE); // rax
  __int64 v26; // rax
  WNDPROC v27; // rax
  __int64 *v29; // [rsp+30h] [rbp-58h] BYREF
  char v30; // [rsp+38h] [rbp-50h]

  PropW = (__int64 *)GetPropW(hWnd, L"_xwizard_wtl_this_pointer_");
  if ( PropW )
    goto LABEL_18;
  v30 = 0;
  v29 = qword_18004D8E8;
  if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v29) < 0 )
  {
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v29);
    return 0;
  }
  v10 = qword_18004D910;
  PropW = 0;
  if ( qword_18004D910 )
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
          qword_18004D910 = *(_QWORD *)(v10 + 16);
        PropW = *(__int64 **)v10;
        break;
      }
      v12 = v10;
      v10 = *(_QWORD *)(v10 + 16);
    }
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v29);
  if ( !PropW )
  {
LABEL_18:
    v9 = 0;
    if ( !PropW )
      return v9;
  }
  else
  {
    PropW[19] = (__int64)hWnd;
    v13 = (void *)(*(__int64 (__fastcall **)(__int64 *))(PropW[18] + 16))(PropW + 18);
    Data = (AtlThunkData_t *)PropW[23];
    if ( Data || (Data = AtlThunk_AllocateData(), (PropW[23] = (__int64)Data) != 0) )
      AtlThunk_InitData(Data, v13, (size_t)(PropW + 18));
    SetPropW(hWnd, L"_xwizard_wtl_this_pointer_", PropW);
  }
  if ( hWnd != (HWND)PropW[42] )
  {
    v15 = *((_DWORD *)PropW + 30) <= 2;
    PropW[42] = (__int64)hWnd;
    Parent = GetParent(hWnd);
    if ( v15 )
    {
      PropW[40] = (__int64)Parent;
      PropW[41] = (__int64)Parent;
    }
    else
    {
      PropW[41] = (__int64)Parent;
      v17 = GetParent(Parent);
      PropW[40] = (__int64)v17;
      Parent = GetParent(v17);
    }
    PropW[39] = (__int64)Parent;
  }
  v9 = 0;
  v18 = 0;
  v19 = 0;
  if ( a2 != 78 )
    goto LABEL_42;
  v20 = *(_DWORD *)(a4 + 16);
  switch ( v20 )
  {
    case -207:
      v26 = *PropW;
      if ( a3 == 4294967088LL )
        v25 = *(__int64 (__fastcall **)(HANDLE))(v26 + 152);
      else
        v25 = *(__int64 (__fastcall **)(HANDLE))(v26 + 160);
      goto LABEL_40;
    case -206:
      v25 = *(__int64 (__fastcall **)(HANDLE))(*PropW + 168);
LABEL_40:
      v22 = v25(PropW);
LABEL_41:
      v19 = v22;
      break;
    case -201:
      v23 = *PropW;
      v18 = 1;
      if ( a3 == 4294967089LL )
        v24 = (*(__int64 (__fastcall **)(__int64 *))(v23 + 128))(PropW);
      else
        v24 = (*(__int64 (__fastcall **)(__int64 *))(v23 + 136))(PropW);
      v9 = v24;
      break;
    case -200:
      v21 = *PropW;
      if ( a3 == 4294967089LL )
        v22 = (*(__int64 (__fastcall **)(__int64 *))(v21 + 104))(PropW);
      else
        v22 = (*(__int64 (__fastcall **)(__int64 *))(v21 + 112))(PropW);
      goto LABEL_41;
  }
LABEL_42:
  v27 = AtlThunk_DataToCode((AtlThunkData_t *)PropW[23]);
  if ( v18 )
    ((void (__fastcall *)(HWND, _QWORD, __int64, __int64))v27)(hWnd, a2, a3, a4);
  else
    v9 = ((__int64 (__fastcall *)(HWND, _QWORD, __int64, __int64))v27)(hWnd, a2, a3, a4);
  if ( v19 )
    SetWindowLongPtrW(hWnd, 0, v19);
  return v9;
}

```

## disassembly

```asm
0x18000af30  push    rbx
0x18000af32  push    rbp
0x18000af33  push    rsi
0x18000af34  push    rdi
0x18000af35  push    r12
0x18000af37  push    r13
0x18000af39  push    r14
0x18000af3b  push    r15
0x18000af3d  sub     rsp, 48h
0x18000af41  mov     r12d, edx
0x18000af44  mov     r13, r9
0x18000af47  lea     rdx, String; "_xwizard_wtl_this_pointer_"
0x18000af4e  mov     r15, r8
0x18000af51  mov     rbp, rcx
0x18000af54  call    cs:__imp_GetPropW
0x18000af5a  mov     rbx, rax
0x18000af5d  test    rax, rax
0x18000af60  jnz     loc_18000B045
0x18000af66  lea     rax, qword_18004D8E8
0x18000af6d  mov     [rsp+88h+var_50], bl
0x18000af71  lea     rcx, [rsp+88h+var_58]
0x18000af76  mov     [rsp+88h+var_58], rax
0x18000af7b  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000af80  test    eax, eax
0x18000af82  jns     short loc_18000AF95
0x18000af84  lea     rcx, [rsp+88h+var_58]
0x18000af89  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000af8e  xor     esi, esi
0x18000af90  jmp     loc_18000B194
0x18000af95  mov     rdi, cs:qword_18004D910
0x18000af9c  xor     ebx, ebx
0x18000af9e  test    rdi, rdi
0x18000afa1  jz      short loc_18000AFD6
0x18000afa3  call    cs:__imp_GetCurrentThreadId
0x18000afa9  xor     edx, edx
0x18000afab  test    rdi, rdi
0x18000afae  jz      short loc_18000AFD6
0x18000afb0  mov     rcx, [rdi+10h]
0x18000afb4  cmp     [rdi+8], eax
0x18000afb7  jz      short loc_18000AFC1
0x18000afb9  mov     rdx, rdi
0x18000afbc  mov     rdi, rcx
0x18000afbf  jmp     short loc_18000AFAB
0x18000afc1  test    rdx, rdx
0x18000afc4  jnz     short loc_18000AFCF
0x18000afc6  mov     cs:qword_18004D910, rcx
0x18000afcd  jmp     short loc_18000AFD3
0x18000afcf  mov     [rdx+10h], rcx
0x18000afd3  mov     rbx, [rdi]
0x18000afd6  lea     rcx, [rsp+88h+var_58]
0x18000afdb  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000afe0  test    rbx, rbx
0x18000afe3  jz      short loc_18000B045
0x18000afe5  lea     rdi, [rbx+90h]
0x18000afec  mov     [rbx+98h], rbp
0x18000aff3  mov     rax, [rdi]
0x18000aff6  mov     rcx, rdi
0x18000aff9  mov     rax, [rax+10h]
0x18000affd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b002  mov     rsi, rax
0x18000b005  mov     rax, [rbx+0B8h]
0x18000b00c  test    rax, rax
0x18000b00f  jnz     short loc_18000B022
0x18000b011  call    AtlThunk_AllocateData
0x18000b016  mov     [rbx+0B8h], rax
0x18000b01d  test    rax, rax
0x18000b020  jz      short loc_18000B030
0x18000b022  mov     r8, rdi; FirstParameter
0x18000b025  mov     rdx, rsi; Proc
0x18000b028  mov     rcx, rax; Thunk
0x18000b02b  call    AtlThunk_InitData
0x18000b030  mov     r8, rbx; hData
0x18000b033  lea     rdx, String; "_xwizard_wtl_this_pointer_"
0x18000b03a  mov     rcx, rbp; hWnd
0x18000b03d  call    cs:__imp_SetPropW
0x18000b043  jmp     short loc_18000B050
0x18000b045  xor     esi, esi
0x18000b047  test    rbx, rbx
0x18000b04a  jz      loc_18000B194
0x18000b050  cmp     rbp, [rbx+150h]
0x18000b057  jz      short loc_18000B0AC
0x18000b059  cmp     dword ptr [rbx+78h], 2
0x18000b05d  mov     rcx, rbp; hWnd
0x18000b060  mov     [rbx+150h], rbp
0x18000b067  jle     short loc_18000B091
0x18000b069  call    cs:__imp_GetParent
0x18000b06f  mov     rcx, rax; hWnd
0x18000b072  mov     [rbx+148h], rax
0x18000b079  call    cs:__imp_GetParent
0x18000b07f  mov     rcx, rax; hWnd
0x18000b082  mov     [rbx+140h], rax
0x18000b089  call    cs:__imp_GetParent
0x18000b08f  jmp     short loc_18000B0A5
0x18000b091  call    cs:__imp_GetParent
0x18000b097  mov     [rbx+140h], rax
0x18000b09e  mov     [rbx+148h], rax
0x18000b0a5  mov     [rbx+138h], rax
0x18000b0ac  xor     esi, esi
0x18000b0ae  xor     r14d, r14d
0x18000b0b1  xor     edi, edi
0x18000b0b3  cmp     r12d, 4Eh ; 'N'
0x18000b0b7  jnz     loc_18000B155
0x18000b0bd  mov     eax, [r13+10h]
0x18000b0c1  mov     ecx, 0FFFFFF31h
0x18000b0c6  cmp     eax, ecx
0x18000b0c8  jz      short loc_18000B12D
0x18000b0ca  cmp     eax, 0FFFFFF32h
0x18000b0cf  jz      short loc_18000B121
0x18000b0d1  cmp     eax, 0FFFFFF37h
0x18000b0d6  jz      short loc_18000B0F6
0x18000b0d8  cmp     eax, 0FFFFFF38h
0x18000b0dd  jnz     short loc_18000B155
0x18000b0df  mov     rax, [rbx]
0x18000b0e2  cmp     r15, rcx
0x18000b0e5  mov     rcx, rbx
0x18000b0e8  jnz     short loc_18000B0F0
0x18000b0ea  mov     rax, [rax+68h]
0x18000b0ee  jmp     short loc_18000B14D
0x18000b0f0  mov     rax, [rax+70h]
0x18000b0f4  jmp     short loc_18000B14D
0x18000b0f6  mov     rax, [rbx]
0x18000b0f9  cmp     r15, rcx
0x18000b0fc  mov     rcx, rbx
0x18000b0ff  mov     r14d, 1
0x18000b105  jnz     short loc_18000B110
0x18000b107  mov     rax, [rax+80h]
0x18000b10e  jmp     short loc_18000B117
0x18000b110  mov     rax, [rax+88h]
0x18000b117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b11c  movsxd  rsi, eax
0x18000b11f  jmp     short loc_18000B155
0x18000b121  mov     rax, [rbx]
0x18000b124  mov     rax, [rax+0A8h]
0x18000b12b  jmp     short loc_18000B14A
0x18000b12d  mov     rax, [rbx]
0x18000b130  mov     ecx, 0FFFFFF30h
0x18000b135  cmp     r15, rcx
0x18000b138  jnz     short loc_18000B143
0x18000b13a  mov     rax, [rax+98h]
0x18000b141  jmp     short loc_18000B14A
0x18000b143  mov     rax, [rax+0A0h]
0x18000b14a  mov     rcx, rbx
0x18000b14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b152  mov     rdi, rax
0x18000b155  mov     rcx, [rbx+0B8h]; AtlThunkData_t *
0x18000b15c  call    AtlThunk_DataToCode
0x18000b161  mov     r9, r13
0x18000b164  mov     r8, r15
0x18000b167  mov     edx, r12d
0x18000b16a  mov     rcx, rbp
0x18000b16d  test    r14d, r14d
0x18000b170  jz      short loc_18000B179
0x18000b172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b177  jmp     short loc_18000B181
0x18000b179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b17e  mov     rsi, rax
0x18000b181  test    rdi, rdi
0x18000b184  jz      short loc_18000B194
0x18000b186  mov     r8, rdi; dwNewLong
0x18000b189  xor     edx, edx; nIndex
0x18000b18b  mov     rcx, rbp; hWnd
0x18000b18e  call    cs:__imp_SetWindowLongPtrW
0x18000b194  mov     rax, rsi
0x18000b197  add     rsp, 48h
0x18000b19b  pop     r15
0x18000b19d  pop     r14
0x18000b19f  pop     r13
0x18000b1a1  pop     r12
0x18000b1a3  pop     rdi
0x18000b1a4  pop     rsi
0x18000b1a5  pop     rbp
0x18000b1a6  pop     rbx
0x18000b1a7  retn
```
