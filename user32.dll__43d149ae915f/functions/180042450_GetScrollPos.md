# GetScrollPos

- ea: `0x180042450`
- end: `0x180042780`
- name: `GetScrollPos`
- size: `816`
- prototype: `int __stdcall(HWND hWnd, int nBar)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000cf20`
- `0x18000d210`
- `0x180020e80`
- `0x180042450`
- `0x1800432d0`
- `0x180043794`
- `0x1800437c4`
- `0x18004389c`
- `0x18004397c`
- `0x18004acf8`
- `0x18005b678`
- `0x18006bbac`
- `0x18006c5d8`
- `0x180074ef0`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800425ba`
- `ntdll!RtlSetLastWin32Error` at `0x180042689`
- `ntdll!RtlSetLastWin32Error` at `0x18004272e`
- `ntdll!RtlSetLastWin32Error` at `0x1800425ba`
- `ntdll!RtlSetLastWin32Error` at `0x180042689`
- `ntdll!RtlSetLastWin32Error` at `0x18004272e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180042575`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180042575`

## pseudocode

```c
int __stdcall GetScrollPos(HWND hWnd, int nBar)
{
  Scrollbar *v4; // rax
  const struct tagWND *v5; // rdx
  Scrollbar *v6; // rbx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rdi
  const char *FnidString; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 ScrollbarTypeString; // rax
  __int64 v14; // r10
  __int64 v15; // r9
  bool v16; // r13
  int RealWindowOwner; // ebx
  struct tagWND *v19; // rbx
  const struct tagWND *v20; // rdx
  struct tagSBINFO *PSBInfo; // rax
  __int64 v22; // rax

  v4 = ValidateHwnd(hWnd);
  v6 = v4;
  if ( !v4 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v8 = 37;
LABEL_46:
    WPP_SF_q(v7[2], v8, &WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids, hWnd);
    return 0;
  }
  v9 = 32;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    FnidString = Scrollbar::GetFnidString(v4, v5);
    ScrollbarTypeString = GetScrollbarTypeString((unsigned int)nBar, v11, v12, FnidString);
    WPP_SF_qsls(*(_QWORD *)(v14 + 16), v15, (*((_BYTE *)v6 + 234) & 4) != 0, ScrollbarTypeString);
  }
  v16 = IsNonClientScrollBarCode(nBar);
  if ( v16 && (*((_BYTE *)v6 + 234) & 4) != 0 )
    MicrosoftTelemetryAssertTriggeredArgs("IXPTellMeIf", 0x20000, 625);
  if ( v16 )
  {
    RealWindowOwner = GetRealWindowOwner(hWnd);
    if ( GetCurrentProcessId() != RealWindowOwner )
      MicrosoftTelemetryAssertTriggeredArgs("IXPTellMeIf", 0x20000, 629);
  }
  if ( (unsigned int)nBar >= 2 )
  {
    if ( nBar == 2 )
      return SendMessageW(hWnd, 0xE1u, 0, 0);
    RtlSetLastWin32Error(0x57u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        &WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids,
        (unsigned int)nBar);
    }
    return 0;
  }
  v19 = ValidateHwnd(hWnd);
  if ( !v19 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v8 = 39;
    goto LABEL_46;
  }
  if ( (unsigned int)Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline() )
  {
    PSBInfo = Scrollbar::NonClient::GetPSBInfo(v19, v20);
    if ( !PSBInfo )
    {
      RtlSetLastWin32Error(0x5A7u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids, hWnd);
      }
      return 0;
    }
    if ( nBar != 1 )
      v9 = 16;
    return *(_DWORD *)((char *)PSBInfo + v9);
  }
  else
  {
    v22 = *((_QWORD *)v19 + 18);
    if ( !v22 )
    {
      RtlSetLastWin32Error(0x5A7u);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 0;
      }
      v8 = 42;
      goto LABEL_46;
    }
    if ( nBar != 1 )
      v9 = 16;
    return *(_DWORD *)((char *)v19 + v22 + v9 - *((_QWORD *)v19 + 1));
  }
}

```

## disassembly

```asm
0x180042450  mov     [rsp+arg_8], rbx
0x180042455  mov     [rsp+arg_18], rsi
0x18004245a  mov     [rsp+arg_0], rcx
0x18004245f  push    rdi
0x180042460  push    r12
0x180042462  push    r13
0x180042464  push    r14
0x180042466  push    r15
0x180042468  sub     rsp, 50h
0x18004246c  mov     r12d, edx
0x18004246f  mov     r14, rcx
0x180042472  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180042477  mov     rbx, rax
0x18004247a  test    rax, rax
0x18004247d  jnz     short loc_1800424B8
0x18004247f  lea     r15, WPP_GLOBAL_Control
0x180042486  mov     rcx, cs:WPP_GLOBAL_Control
0x18004248d  cmp     rcx, r15
0x180042490  jz      loc_180042764
0x180042496  lea     edi, [rax+20h]
0x180042499  test    [rcx+1Ch], dil
0x18004249d  jz      loc_180042764
0x1800424a3  lea     esi, [rax+2]
0x1800424a6  cmp     [rcx+19h], sil
0x1800424aa  jb      loc_180042764
0x1800424b0  lea     edx, [rax+25h]
0x1800424b3  jmp     loc_180042751
0x1800424b8  lea     r15, WPP_GLOBAL_Control
0x1800424bf  mov     r10, cs:WPP_GLOBAL_Control
0x1800424c6  mov     edi, 20h ; ' '
0x1800424cb  cmp     r10, r15
0x1800424ce  jz      short loc_18004251E
0x1800424d0  test    [r10+1Ch], dil
0x1800424d4  jz      short loc_18004251E
0x1800424d6  cmp     byte ptr [r10+19h], 4
0x1800424db  jb      short loc_18004251E
0x1800424dd  mov     rcx, rbx; this
0x1800424e0  call    ?GetFnidString@Scrollbar@@YAPEBDPEBUtagWND@@@Z; Scrollbar::GetFnidString(tagWND const *)
0x1800424e5  mov     r9, rax
0x1800424e8  mov     ecx, r12d
0x1800424eb  call    GetScrollbarTypeString
0x1800424f0  movzx   r8d, byte ptr [rbx+0EAh]
0x1800424f8  shr     r8d, 2
0x1800424fc  and     r8d, 1
0x180042500  lea     edx, [rdi+6]
0x180042503  mov     [rsp+78h+var_48], rax; __int64
0x180042508  mov     dword ptr [rsp+78h+var_50], r8d; char
0x18004250d  mov     [rsp+78h+var_58], r9; __int64
0x180042512  mov     r9, r14
0x180042515  mov     rcx, [r10+10h]; LoggerHandle
0x180042519  call    WPP_SF_qsls
0x18004251e  mov     ecx, r12d; unsigned int
0x180042521  call    ?IsNonClientScrollBarCode@@YA_NI@Z; IsNonClientScrollBarCode(uint)
0x180042526  mov     r13b, al
0x180042529  test    al, al
0x18004252b  jz      short loc_180042561
0x18004252d  test    byte ptr [rbx+0EAh], 4
0x180042534  jz      short loc_180042561
0x180042536  mov     [rsp+78h+arg_10], 20000h
0x180042541  mov     esi, 2
0x180042546  mov     r8d, 271h
0x18004254c  mov     edx, [rsp+78h+arg_10]
0x180042553  lea     rcx, aIxptellmeif; "IXPTellMeIf"
0x18004255a  call    MicrosoftTelemetryAssertTriggeredArgs
0x18004255f  jmp     short loc_180042566
0x180042561  mov     esi, 2
0x180042566  test    r13b, r13b
0x180042569  jz      short loc_1800425A3
0x18004256b  mov     rcx, r14
0x18004256e  call    GetRealWindowOwner
0x180042573  mov     ebx, eax
0x180042575  call    cs:__imp_GetCurrentProcessId
0x18004257b  cmp     eax, ebx
0x18004257d  jz      short loc_1800425A3
0x18004257f  mov     [rsp+78h+arg_10], 20000h
0x18004258a  mov     r8d, 275h
0x180042590  mov     edx, [rsp+78h+arg_10]
0x180042597  lea     rcx, aIxptellmeif; "IXPTellMeIf"
0x18004259e  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800425a3  mov     ecx, r12d
0x1800425a6  test    r12d, r12d
0x1800425a9  jz      short loc_180042619
0x1800425ab  sub     ecx, 1
0x1800425ae  jz      short loc_180042619
0x1800425b0  cmp     ecx, 1
0x1800425b3  jz      short loc_180042601
0x1800425b5  mov     ecx, 57h ; 'W'; LastError
0x1800425ba  call    cs:__imp_RtlSetLastWin32Error
0x1800425c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800425c7  cmp     rcx, r15
0x1800425ca  jz      loc_180042764
0x1800425d0  test    [rcx+1Ch], dil
0x1800425d4  jz      loc_180042764
0x1800425da  cmp     [rcx+19h], sil
0x1800425de  jb      loc_180042764
0x1800425e4  mov     edx, 2Bh ; '+'
0x1800425e9  mov     r9d, r12d
0x1800425ec  lea     r8, WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids
0x1800425f3  mov     rcx, [rcx+10h]
0x1800425f7  call    WPP_SF_d
0x1800425fc  jmp     loc_180042764
0x180042601  xor     r9d, r9d; lParam
0x180042604  xor     r8d, r8d; wParam
0x180042607  mov     edx, 0E1h; Msg
0x18004260c  mov     rcx, r14; hWnd
0x18004260f  call    SendMessageW
0x180042614  jmp     loc_180042766
0x180042619  mov     rcx, r14; HWND
0x18004261c  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180042621  mov     rbx, rax
0x180042624  test    rax, rax
0x180042627  jnz     short loc_180042655
0x180042629  mov     rcx, cs:WPP_GLOBAL_Control
0x180042630  cmp     rcx, r15
0x180042633  jz      loc_180042764
0x180042639  test    [rcx+1Ch], dil
0x18004263d  jz      loc_180042764
0x180042643  cmp     [rcx+19h], sil
0x180042647  jb      loc_180042764
0x18004264d  lea     edx, [rax+27h]
0x180042650  jmp     loc_180042751
0x180042655  call    Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline
0x18004265a  test    eax, eax
0x18004265c  jz      loc_180042704
0x180042662  mov     rcx, rbx; this
0x180042665  call    ?GetPSBInfo@NonClient@Scrollbar@@YAPEAUtagSBINFO@@PEBUtagWND@@@Z; Scrollbar::NonClient::GetPSBInfo(tagWND const *)
0x18004266a  test    rax, rax
0x18004266d  jz      short loc_180042684
0x18004266f  mov     ecx, 10h
0x180042674  cmp     r12d, 1
0x180042678  cmovnz  rdi, rcx
0x18004267c  mov     eax, [rdi+rax]
0x18004267f  jmp     loc_180042766
0x180042684  mov     ecx, 5A7h; LastError
0x180042689  call    cs:__imp_RtlSetLastWin32Error
0x18004268f  mov     rcx, cs:WPP_GLOBAL_Control
0x180042696  cmp     rcx, r15
0x180042699  jz      short loc_1800426BF
0x18004269b  test    [rcx+1Ch], dil
0x18004269f  jz      short loc_1800426BF
0x1800426a1  cmp     [rcx+19h], sil
0x1800426a5  jb      short loc_1800426BF
0x1800426a7  mov     edx, 28h ; '('
0x1800426ac  mov     r9, r14
0x1800426af  lea     r8, WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids
0x1800426b6  mov     rcx, [rcx+10h]
0x1800426ba  call    WPP_SF_q
0x1800426bf  jmp     loc_180042764
0x1800426c4  lea     rax, WPP_GLOBAL_Control
0x1800426cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800426d2  cmp     rcx, rax
0x1800426d5  jz      short loc_180042700
0x1800426d7  test    byte ptr [rcx+1Ch], 20h
0x1800426db  jz      short loc_180042700
0x1800426dd  cmp     byte ptr [rcx+19h], 2
0x1800426e1  jb      short loc_180042700
0x1800426e3  mov     edx, 29h ; ')'
0x1800426e8  mov     r9, [rsp+78h+arg_0]
0x1800426f0  lea     r8, WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids
0x1800426f7  mov     rcx, [rcx+10h]
0x1800426fb  call    WPP_SF_q
0x180042700  xor     eax, eax
0x180042702  jmp     short loc_180042766
0x180042704  mov     rax, [rbx+90h]
0x18004270b  test    rax, rax
0x18004270e  jz      short loc_180042729
0x180042710  mov     ecx, 10h
0x180042715  cmp     r12d, 1
0x180042719  cmovnz  rdi, rcx
0x18004271d  sub     rdi, [rbx+8]
0x180042721  add     rdi, rax
0x180042724  mov     eax, [rdi+rbx]
0x180042727  jmp     short loc_180042766
0x180042729  mov     ecx, 5A7h; LastError
0x18004272e  call    cs:__imp_RtlSetLastWin32Error
0x180042734  mov     rcx, cs:WPP_GLOBAL_Control
0x18004273b  cmp     rcx, r15
0x18004273e  jz      short loc_180042764
0x180042740  test    [rcx+1Ch], dil
0x180042744  jz      short loc_180042764
0x180042746  cmp     [rcx+19h], sil
0x18004274a  jb      short loc_180042764
0x18004274c  mov     edx, 2Ah ; '*'
0x180042751  mov     r9, r14
0x180042754  lea     r8, WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids
0x18004275b  mov     rcx, [rcx+10h]
0x18004275f  call    WPP_SF_q
0x180042764  xor     eax, eax
0x180042766  lea     r11, [rsp+78h+var_28]
0x18004276b  mov     rbx, [r11+38h]
0x18004276f  mov     rsi, [r11+48h]
0x180042773  mov     rsp, r11
0x180042776  pop     r15
0x180042778  pop     r14
0x18004277a  pop     r13
0x18004277c  pop     r12
0x18004277e  pop     rdi
0x18004277f  retn
0x18009795b  push    rbp
0x18009795d  sub     rsp, 40h
0x180097961  mov     rbp, rdx
0x180097964  mov     rax, [rcx]
0x180097967  mov     ecx, [rax]
0x180097969  mov     [rbp+40h], ecx
0x18009796c  mov     ecx, [rbp+40h]
0x18009796f  call    SetLastNtError
0x180097974  mov     dword ptr [rbp+48h], 1
0x18009797b  mov     eax, [rbp+48h]
0x18009797e  add     rsp, 40h
0x180097982  pop     rbp
0x180097983  retn
```
