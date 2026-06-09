# CPopupTaskFlow::Initialize(IUserManager *,TASK_FLOW_ID)

- ea: `0x1800367a0`
- end: `0x1800369b8`
- name: `?Initialize@CPopupTaskFlow@@UEAAJPEAUIUserManager@@W4TASK_FLOW_ID@@@Z`
- size: `536`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000d9a4`
- `0x1800367a0`
- `0x1800369c0`
- `0x180038ca4`
- `0x180063810`
- `0x180063b30`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800368b0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800368b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800368bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800368bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003687f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003687f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036986`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036986`

## pseudocode

```c
__int64 __fastcall CPopupTaskFlow::Initialize(__int64 a1, struct IUserManager *a2, __int64 a3)
{
  __int64 v4; // r15
  HDPA v6; // rax
  HDPA v7; // rax
  HDPA v8; // rax
  DWORD CurrentProcessId; // eax
  int v10; // eax
  void *v11; // rsi
  const WCHAR *v12; // r9
  HANDLE EventW; // rax
  signed int LastError; // eax
  int TaskFlowPages; // ebx
  void *p; // [rsp+30h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-48h] BYREF
  LPVOID v19[2]; // [rsp+40h] [rbp-40h] BYREF
  LPVOID *p_pv; // [rsp+50h] [rbp-30h]
  __int64 v21; // [rsp+58h] [rbp-28h]
  void **p_p; // [rsp+60h] [rbp-20h]
  __int64 v23; // [rsp+68h] [rbp-18h]

  v4 = (int)a3;
  if ( (Microsoft_Windows_User_ControlPanelEnableBits & 0x10) != 0 )
  {
    LODWORD(pv) = *(_DWORD *)(a1 + 80);
    LODWORD(p) = 0;
    p_pv = &pv;
    p_p = &p;
    v21 = 4;
    v23 = 4;
    McGenEventWrite_EventWriteTransfer(a1, PerfTrack_UAM_TaskFlowPageChange_Start, a3, 3, v19);
  }
  v6 = g_pfn_DPA_Create(7);
  *(_QWORD *)(a1 + 88) = v6;
  if ( v6
    && (v7 = g_pfn_DPA_Create(7), (*(_QWORD *)(a1 + 56) = v7) != 0)
    && (v8 = g_pfn_DPA_Create(1), (*(_QWORD *)(a1 + 40) = v8) != 0) )
  {
    v19[0] = 0;
    v19[1] = 0;
    p_pv = 0;
    CurrentProcessId = GetCurrentProcessId();
    v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
            v19,
            L"Local\\UAMCloseFlow%d",
            CurrentProcessId);
    v11 = v19[0];
    if ( v10 < 0 )
      v12 = 0;
    else
      v12 = (const WCHAR *)v19[0];
    EventW = CreateEventW(0, 1, 0, v12);
    *(_QWORD *)(a1 + 24) = EventW;
    if ( EventW )
    {
      p = 0;
      TaskFlowPages = (*(&off_18007AE30 + 11 * v4))(a2, (struct ITaskFlowPluginInfo **)&p);
      if ( TaskFlowPages >= 0 )
      {
        pv = 0;
        TaskFlowPages = (*(__int64 (__fastcall **)(void *, LPVOID *))(*(_QWORD *)p + 24LL))(p, &pv);
        if ( TaskFlowPages >= 0 )
        {
          if ( DPA_InsertPtr(*(HDPA *)(a1 + 40), 0x7FFFFFFF, p) == -1 )
          {
            TaskFlowPages = -2147024882;
            (*(void (__fastcall **)(void *))(*(_QWORD *)p + 16LL))(p);
          }
          else
          {
            TaskFlowPages = CPopupTaskFlow::_CreateTaskFlowPages(
                              (HDPA *)a1,
                              (const unsigned __int16 *)pv,
                              (const struct TASK_FLOW_DEFINITION *)(&off_18007AE30 + 11 * v4));
            *(_DWORD *)(a1 + 80) = v4;
          }
          CoTaskMemFree(pv);
        }
      }
    }
    else
    {
      LastError = GetLastError();
      TaskFlowPages = LastError;
      if ( LastError > 0 )
        TaskFlowPages = (unsigned __int16)LastError | 0x80070000;
      if ( TaskFlowPages >= 0 )
        TaskFlowPages = -2147467259;
    }
    if ( v11 )
      CoTaskMemFree(v11);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)TaskFlowPages;
}

```

## disassembly

```asm
0x1800367a0  mov     [rsp-28h+arg_18], rbx
0x1800367a5  push    rbp
0x1800367a6  push    rsi
0x1800367a7  push    rdi
0x1800367a8  push    r14
0x1800367aa  push    r15
0x1800367ac  mov     rbp, rsp
0x1800367af  sub     rsp, 80h
0x1800367b6  mov     rax, cs:__security_cookie
0x1800367bd  xor     rax, rsp
0x1800367c0  mov     [rbp+var_10], rax
0x1800367c4  test    cs:Microsoft_Windows_User_ControlPanelEnableBits, 10h
0x1800367cb  mov     rbx, rdx
0x1800367ce  movsxd  r15, r8d
0x1800367d1  mov     rdi, rcx
0x1800367d4  jz      short loc_18003681E
0x1800367d6  mov     eax, [rcx+50h]
0x1800367d9  lea     rdx, PerfTrack_UAM_TaskFlowPageChange_Start
0x1800367e0  mov     dword ptr [rbp+pv], eax
0x1800367e3  mov     r9d, 3
0x1800367e9  lea     rax, [rbp+pv]
0x1800367ed  mov     dword ptr [rbp+p], 0
0x1800367f4  mov     [rbp+var_30], rax
0x1800367f8  lea     rax, [rbp+p]
0x1800367fc  mov     [rbp+var_20], rax
0x180036800  lea     rax, [rbp+var_40]
0x180036804  mov     [rsp+80h+var_60], rax
0x180036809  mov     [rbp+var_28], 4
0x180036811  mov     [rbp+var_18], 4
0x180036819  call    McGenEventWrite_EventWriteTransfer
0x18003681e  mov     esi, 7
0x180036823  mov     ecx, esi; cItemGrow
0x180036825  call    cs:g_pfn_DPA_Create
0x18003682b  mov     [rdi+58h], rax
0x18003682f  test    rax, rax
0x180036832  jz      loc_18003698E
0x180036838  mov     ecx, esi; cItemGrow
0x18003683a  call    cs:g_pfn_DPA_Create
0x180036840  mov     [rdi+38h], rax
0x180036844  test    rax, rax
0x180036847  jz      loc_18003698E
0x18003684d  lea     r14d, [rsi-6]
0x180036851  mov     ecx, r14d; cItemGrow
0x180036854  call    cs:g_pfn_DPA_Create
0x18003685a  mov     [rdi+28h], rax
0x18003685e  test    rax, rax
0x180036861  jz      loc_18003698E
0x180036867  mov     [rbp+var_40], 0
0x18003686f  mov     [rbp+var_38], 0
0x180036877  mov     [rbp+var_30], 0
0x18003687f  call    cs:__imp_GetCurrentProcessId
0x180036885  mov     r8d, eax
0x180036888  lea     rdx, aLocalUamclosef; "Local\\UAMCloseFlow%d"
0x18003688f  lea     rcx, [rbp+var_40]
0x180036893  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180036898  mov     rsi, [rbp+var_40]
0x18003689c  xor     r8d, r8d; bInitialState
0x18003689f  xor     ecx, ecx; lpEventAttributes
0x1800368a1  mov     edx, r14d; bManualReset
0x1800368a4  test    eax, eax
0x1800368a6  js      short loc_1800368AD
0x1800368a8  mov     r9, rsi
0x1800368ab  jmp     short loc_1800368B0
0x1800368ad  xor     r9d, r9d; lpName
0x1800368b0  call    cs:__imp_CreateEventW
0x1800368b6  mov     [rdi+18h], rax
0x1800368ba  test    rax, rax
0x1800368bd  jnz     short loc_1800368E3
0x1800368bf  call    cs:__imp_GetLastError
0x1800368c5  mov     ebx, eax
0x1800368c7  test    eax, eax
0x1800368c9  jle     short loc_1800368D4
0x1800368cb  movzx   ebx, ax
0x1800368ce  or      ebx, 80070000h
0x1800368d4  test    ebx, ebx
0x1800368d6  mov     eax, 80004005h
0x1800368db  cmovns  ebx, eax
0x1800368de  jmp     loc_18003697E
0x1800368e3  lea     rax, off_18007AE30
0x1800368ea  mov     [rbp+p], 0
0x1800368f2  imul    r14, r15, 58h ; 'X'
0x1800368f6  lea     rdx, [rbp+p]
0x1800368fa  mov     rcx, rbx
0x1800368fd  add     r14, rax
0x180036900  mov     rax, [r14]
0x180036903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036908  mov     ebx, eax
0x18003690a  test    eax, eax
0x18003690c  js      short loc_18003697E
0x18003690e  mov     rcx, [rbp+p]
0x180036912  lea     rdx, [rbp+pv]
0x180036916  mov     [rbp+pv], 0
0x18003691e  mov     rax, [rcx]
0x180036921  mov     rax, [rax+18h]
0x180036925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003692a  mov     ebx, eax
0x18003692c  test    eax, eax
0x18003692e  js      short loc_18003697E
0x180036930  mov     r8, [rbp+p]; p
0x180036934  mov     edx, 7FFFFFFFh; i
0x180036939  mov     rcx, [rdi+28h]; hdpa
0x18003693d  call    cs:__imp_DPA_InsertPtr
0x180036943  cmp     eax, 0FFFFFFFFh
0x180036946  jz      short loc_18003695F
0x180036948  mov     rdx, [rbp+pv]; unsigned __int16 *
0x18003694c  mov     r8, r14; struct TASK_FLOW_DEFINITION *
0x18003694f  mov     rcx, rdi; this
0x180036952  call    ?_CreateTaskFlowPages@CPopupTaskFlow@@AEAAJPEBGAEBUTASK_FLOW_DEFINITION@@@Z; CPopupTaskFlow::_CreateTaskFlowPages(ushort const *,TASK_FLOW_DEFINITION const &)
0x180036957  mov     ebx, eax
0x180036959  mov     [rdi+50h], r15d
0x18003695d  jmp     short loc_180036974
0x18003695f  mov     rcx, [rbp+p]
0x180036963  mov     ebx, 8007000Eh
0x180036968  mov     rax, [rcx]
0x18003696b  mov     rax, [rax+10h]
0x18003696f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036974  mov     rcx, [rbp+pv]; pv
0x180036978  call    cs:__imp_CoTaskMemFree
0x18003697e  test    rsi, rsi
0x180036981  jz      short loc_180036993
0x180036983  mov     rcx, rsi; pv
0x180036986  call    cs:__imp_CoTaskMemFree
0x18003698c  jmp     short loc_180036993
0x18003698e  mov     ebx, 8007000Eh
0x180036993  mov     eax, ebx
0x180036995  mov     rcx, [rbp+var_10]
0x180036999  xor     rcx, rsp; StackCookie
0x18003699c  call    __security_check_cookie
0x1800369a1  mov     rbx, [rsp+80h+arg_18]
0x1800369a9  add     rsp, 80h
0x1800369b0  pop     r15
0x1800369b2  pop     r14
0x1800369b4  pop     rdi
0x1800369b5  pop     rsi
0x1800369b6  pop     rbp
0x1800369b7  retn
```
