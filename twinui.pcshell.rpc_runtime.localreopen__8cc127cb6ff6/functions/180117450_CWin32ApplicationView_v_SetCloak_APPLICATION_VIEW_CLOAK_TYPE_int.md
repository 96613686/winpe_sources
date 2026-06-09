# CWin32ApplicationView::v_SetCloak(APPLICATION_VIEW_CLOAK_TYPE,int)

- ea: `0x180117450`
- end: `0x180117797`
- name: `?v_SetCloak@CWin32ApplicationView@@EEAAJW4APPLICATION_VIEW_CLOAK_TYPE@@H@Z`
- size: `839`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x180031c70`
- `0x18008a290`
- `0x18008a6f0`
- `0x18008b0d0`
- `0x180117450`
- `0x1801177d0`
- `0x180279e50`
- `0x18028913c`
- `0x18039097c`
- `0x1803909dc`
- `0x180391da4`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180117474`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180117474`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801174dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801174dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801174c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801175df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801174c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801175df`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180117534`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1801176f3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180117534`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1801176f3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindow` at `0x18011775c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindow` at `0x1806f49d8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindow` at `0x18011775c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindow` at `0x1806f49d8`
- `ext-ms-win-ntuser-window-l1-1-4!GhostWindowFromHungWindow` at `0x1801175ad`
- `ext-ms-win-ntuser-window-l1-1-4!GhostWindowFromHungWindow` at `0x1801175ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWin32ApplicationView::v_SetCloak(__int64 a1, int a2, int a3)
{
  RTL_SRWLOCK *v6; // rdi
  int v7; // esi
  int v8; // ebx
  unsigned __int16 *v9; // rcx
  LPVOID *v10; // r15
  HWND v11; // rax
  DWORD WindowThreadProcessId; // esi
  __int64 i; // rdi
  RTL_SRWLOCK *v14; // rsi
  __int64 (__fastcall *v15)(RTL_SRWLOCK *, __int64, bool, __int64); // rdi
  __int64 v16; // rax
  int v17; // eax
  unsigned int v18; // edi
  __int64 v19; // rax
  HWND v20; // rdi
  _QWORD *v21; // rdi
  __int64 v22; // rsi
  RTL_SRWLOCK *v23; // rcx
  RTL_SRWLOCK *v25; // rcx
  RTL_SRWLOCK *v26; // rcx
  int v27; // esi
  HWND v28; // rax
  int v29; // [rsp+20h] [rbp-58h]
  __int128 v30; // [rsp+30h] [rbp-48h] BYREF
  char v31[16]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int16 *v32; // [rsp+50h] [rbp-28h] BYREF
  __int64 v33; // [rsp+58h] [rbp-20h]
  __int64 v34; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  RTL_SRWLOCK *v36; // [rsp+C0h] [rbp+48h] BYREF

  v6 = (RTL_SRWLOCK *)(a1 + 48);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 48));
  v36 = v6;
  v7 = *(_DWORD *)(a1 + 264);
  if ( a3 )
    v8 = a2 | v7;
  else
    v8 = v7 & ~a2;
  *(_DWORD *)(a1 + 264) = v8;
  v9 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  if ( v7 != v8 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v32);
    v33 = -1;
    v34 = -1;
    if ( (int)CWin32ApplicationView::GetViewId((CWin32ApplicationView *)(a1 + 16), &v32) >= 0 )
    {
      v30 = *(_OWORD *)_lambda_6b6168dda817c5975ee7d3438d2331fe_::_lambda_6b6168dda817c5975ee7d3438d2331fe_(
                         v31,
                         &v32,
                         a1);
      GlobalsUtility::CGlobals_ApplicationViewManagement::CGlobals_::Get__lambda_807778e6719fb664354e7e91ff2b2b86___(&v30);
      ApplicationViewManagement::ApplicationViewTraceLogging::CloakTypeChange<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>> &,enum APPLICATION_VIEW_CLOAK_TYPE &>(
        &v32,
        a1 + 264);
    }
    v9 = v32;
  }
  if ( v9 )
  {
    CoTaskMemFree(v9);
    v32 = 0;
  }
  v33 = 0;
  v34 = 0;
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  if ( (v8 != 0) == (v7 != 0) && v8 )
    return 0;
  v36 = 0;
  GlobalsUtility::CGlobals_ApplicationViewManagement::CGlobals_::Get__lambda_ee3e0a0da20eb1cf2fabc213f82c029b___(&v36);
  if ( v36 )
  {
    v10 = (LPVOID *)(a1 + 232);
    v11 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 216) + 24LL))(*(_QWORD *)(a1 + 216));
    if ( v8 )
    {
      ApplicationViewManagement::ToolWindowGathererTemplated<ApplicationViewManagement::AssociatedWindowWin32Calls>::GatherWindows(
        a1 + 232,
        v11);
    }
    else
    {
      WindowThreadProcessId = GetWindowThreadProcessId(v11, 0);
      if ( WindowThreadProcessId )
      {
        for ( i = *(_QWORD *)(a1 + 240); i; --i )
        {
          if ( GetWindowThreadProcessId(*((HWND *)*v10 + i - 1), 0) != WindowThreadProcessId )
            CTSimpleArray<UiaPropertyChangedEventArgs *,4294967294,CTPolicyCoTaskMem<UiaPropertyChangedEventArgs *>,CSimpleArrayStandardCompareHelper<UiaPropertyChangedEventArgs *>,CSimpleArrayStandardMergeHelper<UiaPropertyChangedEventArgs *>>::RemoveAt(
              a1 + 232,
              i - 1);
        }
      }
    }
    v14 = v36;
    v15 = (__int64 (__fastcall *)(RTL_SRWLOCK *, __int64, bool, __int64))*((_QWORD *)v36->Ptr + 3);
    v16 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 216) + 24LL))(*(_QWORD *)(a1 + 216));
    v17 = v15(v14, v16, v8 != 0, 1);
    v18 = v17;
    if ( v17 == -2147024809 )
    {
      if ( !v8 )
      {
        v28 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 216) + 24LL))(*(_QWORD *)(a1 + 216));
        if ( GetWindow(v28, 4u) )
        {
          if ( *(_QWORD *)(a1 + 240) )
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x13D,
              (unsigned int)"pcshell\\twinui\\appviewmanager\\lib\\appview.cpp",
              (const char *)0x80070057LL,
              v29);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
          return 0;
        }
      }
    }
    else
    {
      if ( v17 >= 0 )
      {
        v19 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 216) + 24LL))(*(_QWORD *)(a1 + 216));
        v20 = (HWND)GhostWindowFromHungWindow(v19);
        if ( v20 )
        {
          v27 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, HWND, bool, _QWORD))v36->Ptr + 3))(v36, v20, v8 != 0, 0);
          if ( (v27 != -2147024809 || v8 || !GetWindow(v20, 4u)) && v27 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x158,
              (unsigned int)"pcshell\\twinui\\appviewmanager\\lib\\appview.cpp",
              (const char *)(unsigned int)v27,
              v29);
        }
        v21 = *v10;
        v22 = (__int64)*v10 + 8 * *(_QWORD *)(a1 + 240);
        if ( *v10 != (LPVOID)v22 )
        {
          do
            (*((void (__fastcall **)(RTL_SRWLOCK *, _QWORD, bool, _QWORD))v36->Ptr + 3))(v36, *v21++, v8 != 0, 0);
          while ( v21 != (_QWORD *)v22 );
        }
        if ( !v8 )
        {
          if ( *v10 )
          {
            CoTaskMemFree(*v10);
            *v10 = 0;
          }
          *(_QWORD *)(a1 + 240) = 0;
          *(_QWORD *)(a1 + 256) = 0;
        }
        v23 = v36;
        if ( v36 )
        {
          v36 = 0;
          (*((void (__fastcall **)(RTL_SRWLOCK *))v23->Ptr + 2))(v23);
        }
        return 0;
      }
      if ( v17 == -2147024890 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
        return 2147942406LL;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x143,
      (unsigned int)"pcshell\\twinui\\appviewmanager\\lib\\appview.cpp",
      (const char *)v18,
      v29);
    v25 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*((void (__fastcall **)(RTL_SRWLOCK *))v25->Ptr + 2))(v25);
    }
    return v18;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x115,
      (unsigned int)"pcshell\\twinui\\appviewmanager\\lib\\appview.cpp",
      (const char *)0x8007000CLL,
      v29);
    v26 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*((void (__fastcall **)(RTL_SRWLOCK *))v26->Ptr + 2))(v26);
    }
    return 2147942412LL;
  }
}

```

## disassembly

```asm
0x180117450  push    rbp
0x180117452  push    rbx
0x180117453  push    rsi
0x180117454  push    rdi
0x180117455  push    r12
0x180117457  push    r13
0x180117459  push    r14
0x18011745b  push    r15
0x18011745d  mov     rbp, rsp
0x180117460  sub     rsp, 78h
0x180117464  mov     ebx, r8d
0x180117467  mov     r12d, edx
0x18011746a  mov     r14, rcx
0x18011746d  lea     rdi, [rcx+30h]
0x180117471  mov     rcx, rdi; SRWLock
0x180117474  call    cs:__imp_AcquireSRWLockExclusive
0x18011747a  mov     [rbp+arg_0], rdi
0x18011747e  mov     esi, [r14+108h]
0x180117485  test    ebx, ebx
0x180117487  jnz     loc_180117627
0x18011748d  mov     ebx, r12d
0x180117490  not     ebx
0x180117492  and     ebx, esi
0x180117494  mov     [r14+108h], ebx
0x18011749b  xor     r13d, r13d
0x18011749e  mov     r12d, r13d
0x1801174a1  test    ebx, ebx
0x1801174a3  setnz   r12b
0x1801174a7  mov     ecx, r13d; pv
0x1801174aa  mov     [rbp+var_28], rcx
0x1801174ae  mov     [rbp+var_20], r13
0x1801174b2  mov     [rbp+var_18], r13
0x1801174b6  cmp     esi, ebx
0x1801174b8  jnz     loc_1806F4940
0x1801174be  test    rcx, rcx
0x1801174c1  jz      short loc_1801174CD
0x1801174c3  call    cs:__imp_CoTaskMemFree
0x1801174c9  mov     [rbp+var_28], r13
0x1801174cd  mov     [rbp+var_20], r13
0x1801174d1  mov     [rbp+var_18], r13
0x1801174d5  test    rdi, rdi
0x1801174d8  jz      short loc_1801174E3
0x1801174da  mov     rcx, rdi; SRWLock
0x1801174dd  call    cs:__imp_ReleaseSRWLockExclusive
0x1801174e3  mov     eax, r13d
0x1801174e6  test    esi, esi
0x1801174e8  setnz   al
0x1801174eb  cmp     r12d, eax
0x1801174ee  jz      loc_18011761D
0x1801174f4  mov     [rbp+arg_0], r13
0x1801174f8  lea     rcx, [rbp+arg_0]
0x1801174fc  call    GlobalsUtility__CGlobals_ApplicationViewManagement__CGlobals___Get__lambda_ee3e0a0da20eb1cf2fabc213f82c029b___
0x180117501  nop
0x180117502  cmp     [rbp+arg_0], 0
0x180117507  jz      loc_180117684
0x18011750d  lea     r15, [r14+0E8h]
0x180117514  mov     rcx, [r14+0D8h]
0x18011751b  mov     rax, [rcx]
0x18011751e  mov     rax, [rax+18h]
0x180117522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117527  test    ebx, ebx
0x180117529  jnz     loc_180117674
0x18011752f  xor     edx, edx; lpdwProcessId
0x180117531  mov     rcx, rax; hWnd
0x180117534  call    cs:__imp_GetWindowThreadProcessId
0x18011753a  mov     esi, eax
0x18011753c  test    eax, eax
0x18011753e  jz      short loc_18011754D
0x180117540  mov     rdi, [r15+8]
0x180117544  test    rdi, rdi
0x180117547  jnz     loc_1801176E9
0x18011754d  mov     rsi, [rbp+arg_0]
0x180117551  mov     rax, [rsi]
0x180117554  mov     rdi, [rax+18h]
0x180117558  mov     rcx, [r14+0D8h]
0x18011755f  mov     rdx, [rcx]
0x180117562  mov     rax, [rdx+18h]
0x180117566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011756b  mov     r9d, 1
0x180117571  mov     r8d, r12d
0x180117574  mov     rdx, rax
0x180117577  mov     rcx, rsi
0x18011757a  mov     rax, rdi
0x18011757d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117582  mov     edi, eax
0x180117584  cmp     eax, 80070057h
0x180117589  jz      loc_1806F49B5
0x18011758f  test    eax, eax
0x180117591  js      loc_180117631
0x180117597  mov     rcx, [r14+0D8h]
0x18011759e  mov     rax, [rcx]
0x1801175a1  mov     rax, [rax+18h]
0x1801175a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801175aa  mov     rcx, rax
0x1801175ad  call    cs:__imp_GhostWindowFromHungWindow
0x1801175b3  mov     rdi, rax
0x1801175b6  test    rax, rax
0x1801175b9  jnz     loc_180117726
0x1801175bf  mov     rdi, [r15]
0x1801175c2  mov     rax, [r15+8]
0x1801175c6  lea     rsi, [rdi+rax*8]
0x1801175ca  cmp     rdi, rsi
0x1801175cd  jnz     loc_180117770
0x1801175d3  test    ebx, ebx
0x1801175d5  jnz     short loc_1801175F0
0x1801175d7  mov     rcx, [r15]; pv
0x1801175da  test    rcx, rcx
0x1801175dd  jz      short loc_1801175E8
0x1801175df  call    cs:__imp_CoTaskMemFree
0x1801175e5  mov     [r15], r13
0x1801175e8  mov     [r15+8], r13
0x1801175ec  mov     [r15+18h], r13
0x1801175f0  mov     rcx, [rbp+arg_0]
0x1801175f4  test    rcx, rcx
0x1801175f7  jz      short loc_18011760A
0x1801175f9  mov     [rbp+arg_0], r13
0x1801175fd  mov     rax, [rcx]
0x180117600  mov     rax, [rax+10h]
0x180117604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117609  nop
0x18011760a  xor     eax, eax
0x18011760c  add     rsp, 78h
0x180117610  pop     r15
0x180117612  pop     r14
0x180117614  pop     r13
0x180117616  pop     r12
0x180117618  pop     rdi
0x180117619  pop     rsi
0x18011761a  pop     rbx
0x18011761b  pop     rbp
0x18011761c  retn
0x18011761d  test    ebx, ebx
0x18011761f  jz      loc_1801174F4
0x180117625  jmp     short loc_18011760A
0x180117627  mov     ebx, esi
0x180117629  or      ebx, r12d
0x18011762c  jmp     loc_180117494
0x180117631  cmp     edi, 80070006h
0x180117637  jz      loc_180117713
0x18011763d  mov     rcx, [rbp+40h]; this
0x180117641  mov     r9d, edi; char *
0x180117644  lea     r8, aPcshellTwinuiA_1; "pcshell\\twinui\\appviewmanager\\lib\\a"...
0x18011764b  mov     edx, 143h; void *
0x180117650  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117655  nop
0x180117656  mov     rcx, [rbp+arg_0]
0x18011765a  test    rcx, rcx
0x18011765d  jz      short loc_180117670
0x18011765f  mov     [rbp+arg_0], r13
0x180117663  mov     rax, [rcx]
0x180117666  mov     rax, [rax+10h]
0x18011766a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011766f  nop
0x180117670  mov     eax, edi
0x180117672  jmp     short loc_18011760C
0x180117674  mov     rdx, rax
0x180117677  mov     rcx, r15
0x18011767a  call    ?GatherWindows@?$ToolWindowGathererTemplated@VAssociatedWindowWin32Calls@ApplicationViewManagement@@@ApplicationViewManagement@@QEAAJPEAUHWND__@@@Z; ApplicationViewManagement::ToolWindowGathererTemplated<ApplicationViewManagement::AssociatedWindowWin32Calls>::GatherWindows(HWND__ *)
0x18011767f  jmp     loc_18011754D
0x180117684  mov     rcx, [rbp+40h]; this
0x180117688  mov     r9d, 8007000Ch; char *
0x18011768e  lea     r8, aPcshellTwinuiA_1; "pcshell\\twinui\\appviewmanager\\lib\\a"...
0x180117695  mov     edx, 115h; void *
0x18011769a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011769f  nop
0x1801176a0  mov     rcx, [rbp+arg_0]
0x1801176a4  test    rcx, rcx
0x1801176a7  jz      short loc_1801176BA
0x1801176a9  mov     [rbp+arg_0], r13
0x1801176ad  mov     rdx, [rcx]
0x1801176b0  mov     rax, [rdx+10h]
0x1801176b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801176b9  nop
0x1801176ba  mov     eax, 8007000Ch
0x1801176bf  jmp     loc_18011760C
0x1801176c4  mov     rcx, [rbp+40h]; this
0x1801176c8  test    esi, esi
0x1801176ca  jns     loc_1801175BF
0x1801176d0  mov     r9d, esi; char *
0x1801176d3  lea     r8, aPcshellTwinuiA_1; "pcshell\\twinui\\appviewmanager\\lib\\a"...
0x1801176da  mov     edx, 158h; void *
0x1801176df  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801176e4  jmp     loc_1801175BF
0x1801176e9  mov     rcx, [r15]
0x1801176ec  xor     edx, edx; lpdwProcessId
0x1801176ee  mov     rcx, [rcx+rdi*8-8]; hWnd
0x1801176f3  call    cs:__imp_GetWindowThreadProcessId
0x1801176f9  cmp     eax, esi
0x1801176fb  jz      loc_1806F49A3
0x180117701  lea     rdx, [rdi-1]
0x180117705  mov     rcx, r15
0x180117708  call    ?RemoveAt@?$CTSimpleArray@PEAUUiaPropertyChangedEventArgs@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUUiaPropertyChangedEventArgs@@@@V?$CSimpleArrayStandardCompareHelper@PEAUUiaPropertyChangedEventArgs@@@@V?$CSimpleArrayStandardMergeHelper@PEAUUiaPropertyChangedEventArgs@@@@@@QEAAJ_K@Z; CTSimpleArray<UiaPropertyChangedEventArgs *,4294967294,CTPolicyCoTaskMem<UiaPropertyChangedEventArgs *>,CSimpleArrayStandardCompareHelper<UiaPropertyChangedEventArgs *>,CSimpleArrayStandardMergeHelper<UiaPropertyChangedEventArgs *>>::RemoveAt(unsigned __int64)
0x18011770d  nop
0x18011770e  jmp     loc_1806F49A3
0x180117713  lea     rcx, [rbp+arg_0]
0x180117717  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18011771c  mov     eax, 80070006h
0x180117721  jmp     loc_18011760C
0x180117726  mov     rcx, [rbp+arg_0]
0x18011772a  mov     rdx, [rcx]
0x18011772d  mov     rax, [rdx+18h]
0x180117731  xor     r9d, r9d
0x180117734  mov     r8d, r12d
0x180117737  mov     rdx, rdi
0x18011773a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011773f  mov     esi, eax
0x180117741  cmp     eax, 80070057h
0x180117746  jnz     loc_1801176C4
0x18011774c  test    ebx, ebx
0x18011774e  jnz     loc_1801176C4
0x180117754  mov     edx, 4; uCmd
0x180117759  mov     rcx, rdi; hWnd
0x18011775c  call    cs:__imp_GetWindow
0x180117762  test    rax, rax
0x180117765  jnz     loc_1801175BF
0x18011776b  jmp     loc_1801176C4
0x180117770  mov     rcx, [rbp+arg_0]
0x180117774  mov     rax, [rcx]
0x180117777  xor     r9d, r9d
0x18011777a  mov     r8d, r12d
0x18011777d  mov     rdx, [rdi]
0x180117780  mov     rax, [rax+18h]
0x180117784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117789  add     rdi, 8
0x18011778d  cmp     rdi, rsi
0x180117790  jnz     short loc_180117770
0x180117792  jmp     loc_1801175D3
0x1806f4940  lea     rcx, [rbp+var_28]
0x1806f4944  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1806f4949  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFFh
0x1806f4951  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFFh
0x1806f4959  lea     rcx, [r14+10h]; this
0x1806f495d  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x1806f4961  call    ?GetViewId@CWin32ApplicationView@@UEAAJPEAPEAG@Z; CWin32ApplicationView::GetViewId(ushort * *)
0x1806f4966  test    eax, eax
0x1806f4968  js      short loc_1806F499A
0x1806f496a  mov     r8, r14
0x1806f496d  lea     rdx, [rbp+var_28]
0x1806f4971  lea     rcx, [rbp+var_38]
0x1806f4975  call    ??0_lambda_6b6168dda817c5975ee7d3438d2331fe_@@QEAA@AEBUMeetAndChatFallbackProp@Shell@Internal@Windows@winrt@@PEBU?$vector_view_base@U?$vector_impl@UMeetAndChatFallbackProp@Shell@Internal@Windows@winrt@@V?$vector@UMeetAndChatFallbackProp@Shell@Internal@Windows@winrt@@V?$allocator@UMeetAndChatFallbackProp@Shell@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UMeetAndChatFallbackProp@Shell@Internal@Windows@3@Ucollection_version@23@@5@@Z; _lambda_6b6168dda817c5975ee7d3438d2331fe_::_lambda_6b6168dda817c5975ee7d3438d2331fe_(winrt::Windows::Internal::Shell::MeetAndChatFallbackProp const &,winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Internal::Shell::MeetAndChatFallbackProp,std::vector<winrt::Windows::Internal::Shell::MeetAndChatFallbackProp>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Shell::MeetAndChatFallbackProp,winrt::impl::collection_version> const *)
0x1806f497a  movups  xmm0, xmmword ptr [rax]
0x1806f497d  movaps  [rbp+var_48], xmm0
0x1806f4981  lea     rcx, [rbp+var_48]
0x1806f4985  call    GlobalsUtility__CGlobals_ApplicationViewManagement__CGlobals___Get__lambda_807778e6719fb664354e7e91ff2b2b86___
0x1806f498a  lea     rdx, [r14+108h]
0x1806f4991  lea     rcx, [rbp+var_28]
0x1806f4995  call    ??$CloakTypeChange@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAW4APPLICATION_VIEW_CLOAK_TYPE@@@ApplicationViewTraceLogging@ApplicationViewManagement@@SAXAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAW4APPLICATION_VIEW_CLOAK_TYPE@@@Z; ApplicationViewManagement::ApplicationViewTraceLogging::CloakTypeChange<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,APPLICATION_VIEW_CLOAK_TYPE &>(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,APPLICATION_VIEW_CLOAK_TYPE &)
0x1806f499a  mov     rcx, [rbp+var_28]
0x1806f499e  jmp     loc_1801174BE
0x1806f49a3  sub     rdi, 1
0x1806f49a7  jnz     loc_1801176E9
0x1806f49ad  xor     r13d, r13d
0x1806f49b0  jmp     loc_18011754D
0x1806f49b5  test    ebx, ebx
0x1806f49b7  jnz     loc_18011763D
0x1806f49bd  mov     rcx, [r14+0D8h]
0x1806f49c4  mov     rdx, [rcx]
0x1806f49c7  mov     rax, [rdx+18h]
0x1806f49cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f49d0  mov     rcx, rax; hWnd
0x1806f49d3  mov     edx, 4; uCmd
0x1806f49d8  call    cs:__imp_GetWindow
0x1806f49de  test    rax, rax
0x1806f49e1  jz      loc_18011763D
0x1806f49e7  cmp     qword ptr [r14+0F0h], 0
0x1806f49ef  jbe     short loc_1806F4A0D
0x1806f49f1  mov     rcx, [rbp+40h]; this
0x1806f49f5  mov     r9d, 80070057h; char *
0x1806f49fb  lea     r8, aPcshellTwinuiA_1; "pcshell\\twinui\\appviewmanager\\lib\\a"...
0x1806f4a02  mov     edx, 13Dh; void *
0x1806f4a07  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1806f4a0c  nop
0x1806f4a0d  lea     rcx, [rbp+arg_0]
0x1806f4a11  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1806f4a16  nop
0x1806f4a17  jmp     loc_18011760A
```
