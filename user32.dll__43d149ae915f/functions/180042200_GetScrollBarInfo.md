# GetScrollBarInfo

- ea: `0x180042200`
- end: `0x18004243d`
- name: `GetScrollBarInfo`
- size: `573`
- prototype: `BOOL __stdcall(HWND hwnd, LONG idObject, PSCROLLBARINFO psbi)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000d210`
- `0x180020e80`
- `0x180042200`
- `0x1800432d0`
- `0x180043794`
- `0x1800437c4`
- `0x18004389c`
- `0x180057d24`
- `0x18005b678`
- `0x180074ef0`
- `0x18008a120`

## import_xrefs

- `win32u!NtUserGetScrollBarInfo` at `0x1800423bc`
- `win32u!NtUserGetScrollBarInfo` at `0x1800423bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004231a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800423aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004231a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800423aa`

## pseudocode

```c
BOOL __stdcall GetScrollBarInfo(HWND hwnd, LONG idObject, PSCROLLBARINFO psbi)
{
  Scrollbar *v6; // rax
  const struct tagWND *v7; // rdx
  Scrollbar *v8; // rbx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  const char *FnidString; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 ObjectIdString; // rax
  __int64 v15; // r10
  __int64 v16; // r9
  int RealWindowOwner; // ebx
  Scrollbar *v18; // rax
  struct tagSCROLLBARINFO *v19; // r9
  Scrollbar *v20; // r12
  int v22; // ebx
  struct tagSCROLLBARINFO *v23; // r9

  v6 = ValidateHwnd(hwnd);
  v8 = v6;
  if ( !v6 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v10 = 33;
LABEL_22:
    WPP_SF_q(v9[2], v10, &WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids, hwnd);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    FnidString = Scrollbar::GetFnidString(v6, v7);
    ObjectIdString = GetObjectIdString((unsigned int)idObject, v12, v13, FnidString);
    WPP_SF_qsls(*(_QWORD *)(v15 + 16), v16, (*((_BYTE *)v8 + 234) & 4) != 0, ObjectIdString);
  }
  if ( idObject != -4 && (*((_BYTE *)v8 + 234) & 4) != 0 )
    MicrosoftTelemetryAssertTriggeredArgs("IXPTellMeIf", 0x20000, 546);
  if ( idObject != -4 )
  {
    RealWindowOwner = GetRealWindowOwner(hwnd);
    if ( GetCurrentProcessId() != RealWindowOwner )
      MicrosoftTelemetryAssertTriggeredArgs("IXPTellMeIf", 0x20000, 550);
    if ( !(unsigned int)Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline() )
      return NtUserGetScrollBarInfo(hwnd, (unsigned int)idObject, psbi);
  }
  v18 = ValidateHwnd(hwnd);
  v20 = v18;
  if ( !v18 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v10 = 35;
    goto LABEL_22;
  }
  if ( idObject == -4 )
    return Scrollbar::GetScrollBarInfo(v18, (struct tagWND *)0xFFFFFFFCLL, (int)psbi, v19);
  v22 = GetRealWindowOwner(hwnd);
  if ( GetCurrentProcessId() != v22 )
    return NtUserGetScrollBarInfo(hwnd, (unsigned int)idObject, psbi);
  return Scrollbar::GetScrollBarInfo(v20, (struct tagWND *)(unsigned int)idObject, (int)psbi, v23);
}

```

## disassembly

```asm
0x180042200  mov     [rsp+arg_8], rbx
0x180042205  mov     [rsp+arg_10], rsi
0x18004220a  mov     [rsp+arg_0], rcx
0x18004220f  push    rdi
0x180042210  push    r12
0x180042212  push    r13
0x180042214  push    r14
0x180042216  push    r15
0x180042218  sub     rsp, 50h
0x18004221c  mov     r13, r8
0x18004221f  mov     esi, edx
0x180042221  mov     rdi, rcx
0x180042224  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180042229  mov     rbx, rax
0x18004222c  test    rax, rax
0x18004222f  jnz     short loc_180042268
0x180042231  lea     r15, WPP_GLOBAL_Control
0x180042238  mov     rcx, cs:WPP_GLOBAL_Control
0x18004223f  cmp     rcx, r15
0x180042242  jz      loc_180042394
0x180042248  test    byte ptr [rcx+1Ch], 20h
0x18004224c  jz      loc_180042394
0x180042252  lea     r14d, [rax+2]
0x180042256  cmp     [rcx+19h], r14b
0x18004225a  jb      loc_180042394
0x180042260  lea     edx, [rax+21h]
0x180042263  jmp     loc_180042381
0x180042268  lea     r15, WPP_GLOBAL_Control
0x18004226f  mov     r10, cs:WPP_GLOBAL_Control
0x180042276  cmp     r10, r15
0x180042279  jz      short loc_1800422CB
0x18004227b  test    byte ptr [r10+1Ch], 20h
0x180042280  jz      short loc_1800422CB
0x180042282  cmp     byte ptr [r10+19h], 4
0x180042287  jb      short loc_1800422CB
0x180042289  mov     rcx, rbx; this
0x18004228c  call    ?GetFnidString@Scrollbar@@YAPEBDPEBUtagWND@@@Z; Scrollbar::GetFnidString(tagWND const *)
0x180042291  mov     r9, rax
0x180042294  mov     ecx, esi
0x180042296  call    GetObjectIdString
0x18004229b  movzx   r8d, byte ptr [rbx+0EAh]
0x1800422a3  shr     r8d, 2
0x1800422a7  and     r8d, 1
0x1800422ab  mov     edx, 22h ; '"'
0x1800422b0  mov     [rsp+78h+var_48], rax; __int64
0x1800422b5  mov     dword ptr [rsp+78h+var_50], r8d; char
0x1800422ba  mov     [rsp+78h+var_58], r9; __int64
0x1800422bf  mov     r9, rdi
0x1800422c2  mov     rcx, [r10+10h]; LoggerHandle
0x1800422c6  call    WPP_SF_qsls
0x1800422cb  cmp     esi, 0FFFFFFFCh
0x1800422ce  jz      short loc_180042305
0x1800422d0  test    byte ptr [rbx+0EAh], 4
0x1800422d7  jz      short loc_180042305
0x1800422d9  mov     [rsp+78h+arg_18], 20000h
0x1800422e4  mov     r14d, 2
0x1800422ea  mov     r8d, 222h
0x1800422f0  mov     edx, [rsp+78h+arg_18]
0x1800422f7  lea     rcx, aIxptellmeif; "IXPTellMeIf"
0x1800422fe  call    MicrosoftTelemetryAssertTriggeredArgs
0x180042303  jmp     short loc_18004230B
0x180042305  mov     r14d, 2
0x18004230b  cmp     esi, 0FFFFFFFCh
0x18004230e  jz      short loc_180042356
0x180042310  mov     rcx, rdi
0x180042313  call    GetRealWindowOwner
0x180042318  mov     ebx, eax
0x18004231a  call    cs:__imp_GetCurrentProcessId
0x180042320  cmp     eax, ebx
0x180042322  jz      short loc_180042348
0x180042324  mov     [rsp+78h+arg_18], 20000h
0x18004232f  mov     r8d, 226h
0x180042335  mov     edx, [rsp+78h+arg_18]
0x18004233c  lea     rcx, aIxptellmeif; "IXPTellMeIf"
0x180042343  call    MicrosoftTelemetryAssertTriggeredArgs
0x180042348  cmp     esi, 0FFFFFFFCh
0x18004234b  jz      short loc_180042356
0x18004234d  call    Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline
0x180042352  test    eax, eax
0x180042354  jz      short loc_1800423B4
0x180042356  mov     rcx, rdi; HWND
0x180042359  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x18004235e  mov     r12, rax
0x180042361  test    rax, rax
0x180042364  jnz     short loc_18004239B
0x180042366  mov     rcx, cs:WPP_GLOBAL_Control
0x18004236d  cmp     rcx, r15
0x180042370  jz      short loc_180042394
0x180042372  test    byte ptr [rcx+1Ch], 20h
0x180042376  jz      short loc_180042394
0x180042378  cmp     [rcx+19h], r14b
0x18004237c  jb      short loc_180042394
0x18004237e  lea     edx, [rax+23h]
0x180042381  mov     r9, rdi
0x180042384  lea     r8, WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids
0x18004238b  mov     rcx, [rcx+10h]
0x18004238f  call    WPP_SF_q
0x180042394  xor     eax, eax
0x180042396  jmp     loc_180042423
0x18004239b  cmp     esi, 0FFFFFFFCh
0x18004239e  jz      short loc_180042413
0x1800423a0  mov     rcx, rdi
0x1800423a3  call    GetRealWindowOwner
0x1800423a8  mov     ebx, eax
0x1800423aa  call    cs:__imp_GetCurrentProcessId
0x1800423b0  cmp     eax, ebx
0x1800423b2  jz      short loc_1800423C4
0x1800423b4  mov     r8, r13
0x1800423b7  mov     edx, esi
0x1800423b9  mov     rcx, rdi
0x1800423bc  call    cs:__imp_NtUserGetScrollBarInfo
0x1800423c2  jmp     short loc_180042423
0x1800423c4  mov     r8, r13; int
0x1800423c7  mov     edx, esi; struct tagWND *
0x1800423c9  mov     rcx, r12; this
0x1800423cc  call    ?GetScrollBarInfo@Scrollbar@@YAHPEAUtagWND@@JPEAUtagSCROLLBARINFO@@@Z; Scrollbar::GetScrollBarInfo(tagWND *,long,tagSCROLLBARINFO *)
0x1800423d1  jmp     short loc_180042423
0x1800423d3  lea     rax, WPP_GLOBAL_Control
0x1800423da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800423e1  cmp     rcx, rax
0x1800423e4  jz      short loc_18004240F
0x1800423e6  test    byte ptr [rcx+1Ch], 20h
0x1800423ea  jz      short loc_18004240F
0x1800423ec  cmp     byte ptr [rcx+19h], 2
0x1800423f0  jb      short loc_18004240F
0x1800423f2  mov     edx, 24h ; '$'
0x1800423f7  mov     r9, [rsp+78h+arg_0]
0x1800423ff  lea     r8, WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids
0x180042406  mov     rcx, [rcx+10h]
0x18004240a  call    WPP_SF_q
0x18004240f  xor     eax, eax
0x180042411  jmp     short loc_180042423
0x180042413  mov     r8, r13; int
0x180042416  mov     edx, 0FFFFFFFCh; struct tagWND *
0x18004241b  mov     rcx, r12; this
0x18004241e  call    ?GetScrollBarInfo@Scrollbar@@YAHPEAUtagWND@@JPEAUtagSCROLLBARINFO@@@Z; Scrollbar::GetScrollBarInfo(tagWND *,long,tagSCROLLBARINFO *)
0x180042423  lea     r11, [rsp+78h+var_28]
0x180042428  mov     rbx, [r11+38h]
0x18004242c  mov     rsi, [r11+40h]
0x180042430  mov     rsp, r11
0x180042433  pop     r15
0x180042435  pop     r14
0x180042437  pop     r13
0x180042439  pop     r12
0x18004243b  pop     rdi
0x18004243c  retn
0x18009792b  push    rbp
0x18009792d  sub     rsp, 40h
0x180097931  mov     rbp, rdx
0x180097934  mov     rax, [rcx]
0x180097937  mov     ecx, [rax]
0x180097939  mov     [rbp+40h], ecx
0x18009793c  mov     ecx, [rbp+40h]
0x18009793f  call    SetLastNtError
0x180097944  mov     dword ptr [rbp+48h], 1
0x18009794b  mov     eax, [rbp+48h]
0x18009794e  add     rsp, 40h
0x180097952  pop     rbp
0x180097953  retn
```
