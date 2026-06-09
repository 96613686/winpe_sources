# RealGetScrollInfo(HWND__ *,int,tagSCROLLINFO *)

- ea: `0x180042e90`
- end: `0x1800432bf`
- name: `?RealGetScrollInfo@@YAHPEAUHWND__@@HPEAUtagSCROLLINFO@@@Z`
- size: `1071`
- prototype: `__int64 __fastcall(HWND, struct tagWND *, LPARAM lParam)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000cf20`
- `0x18000d210`
- `0x180020e80`
- `0x180042e90`
- `0x1800432d0`
- `0x180043794`
- `0x1800437c4`
- `0x18004389c`
- `0x18004397c`
- `0x18004acf8`
- `0x18005b678`
- `0x18006c5d8`
- `0x180074ef0`
- `0x18008a158`
- `0x18008b0ac`

## import_xrefs

- `win32u!NtUserSBGetParms` at `0x1800432a9`
- `win32u!NtUserSBGetParms` at `0x1800432a9`
- `ntdll!RtlSetLastWin32Error` at `0x180043040`
- `ntdll!RtlSetLastWin32Error` at `0x180043192`
- `ntdll!RtlSetLastWin32Error` at `0x180043249`
- `ntdll!RtlSetLastWin32Error` at `0x180043040`
- `ntdll!RtlSetLastWin32Error` at `0x180043192`
- `ntdll!RtlSetLastWin32Error` at `0x180043249`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043129`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004316e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043129`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004316e`

## pseudocode

```c
__int64 __fastcall RealGetScrollInfo(HWND a1, struct tagWND *a2, struct tagSBDATA *lParam)
{
  unsigned int v4; // r12d
  Scrollbar *v6; // rax
  const struct tagWND *v7; // rdx
  Scrollbar *v8; // r8
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  PVOID *v11; // r10
  const char *FnidString; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 ScrollbarTypeString; // rax
  __int64 v16; // r8
  __int64 v17; // r10
  __int64 v18; // r9
  __int64 v19; // r9
  struct tagWND *v21; // rax
  Scrollbar::NonClient *v22; // r15
  int RealWindowOwner; // ebx
  int v24; // ebx
  const struct tagWND *v25; // rdx
  char *v26; // r8
  struct tagSBINFO *PSBInfo; // rax
  int v28; // r8d
  __int64 v29; // rax
  __int64 v30; // r8
  struct tagSCROLLINFO *v31; // [rsp+20h] [rbp-68h]

  v4 = (unsigned int)a2;
  v6 = ValidateHwnd(a1);
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
    v10 = 23;
LABEL_58:
    WPP_SF_q(v9[2], v10, &WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids, a1);
    return 0;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    FnidString = Scrollbar::GetFnidString(v6, v7);
    ScrollbarTypeString = GetScrollbarTypeString(v4, v13, v14, FnidString);
    WPP_SF_qsls(*(_QWORD *)(v17 + 16), v18, (*(_BYTE *)(v16 + 234) & 4) != 0, ScrollbarTypeString);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)lParam != 28 )
  {
    if ( *(_DWORD *)lParam != 24 )
    {
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x20) != 0 && *((_BYTE *)v11 + 25) >= 2u )
        WPP_SF_DD(v11[2], 25, v8, *(unsigned int *)lParam);
      return 0;
    }
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x20) != 0 && *((_BYTE *)v11 + 25) >= 3u )
    {
      LODWORD(v31) = 28;
      WPP_SF_DD(v11[2], 26, v8, 24);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v19 = *((unsigned int *)lParam + 1);
  if ( (v19 & 0xFFFF8FE0) != 0 )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x20) != 0 && *((_BYTE *)v11 + 25) >= 2u )
      WPP_SF_d(v11[2], 27, &WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids, v19);
    return 0;
  }
  if ( v4 >= 2 )
  {
    if ( v4 == 2 )
    {
      SendMessageW(a1, 0xEAu, 0, (LPARAM)lParam);
      return 1;
    }
    RtlSetLastWin32Error(0x57u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids, v4);
    }
    return 0;
  }
  v21 = ValidateHwnd(a1);
  v22 = v21;
  if ( !v21 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v10 = 28;
    goto LABEL_58;
  }
  if ( (*((_BYTE *)v21 + 234) & 4) != 0 )
    MicrosoftTelemetryAssertTriggeredArgs("IXPTellMeIf", 0x20000, 453);
  RealWindowOwner = GetRealWindowOwner(a1);
  if ( GetCurrentProcessId() != RealWindowOwner )
    MicrosoftTelemetryAssertTriggeredArgs("IXPTellMeIf", 0x20000, 457);
  if ( !(unsigned int)Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline() )
  {
    v29 = *((_QWORD *)v22 + 18);
    if ( !v29 )
    {
      RtlSetLastWin32Error(0x5A7u);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 0;
      }
      v10 = 31;
      goto LABEL_58;
    }
    v30 = 20;
    if ( v4 != 1 )
      v30 = 4;
    v26 = (char *)v22 + v29 + v30 - *((_QWORD *)v22 + 1);
    return NtUserSBGetParms(a1, v4, v26, lParam);
  }
  v24 = GetRealWindowOwner(a1);
  if ( GetCurrentProcessId() != v24 )
  {
    v26 = 0;
    return NtUserSBGetParms(a1, v4, v26, lParam);
  }
  PSBInfo = Scrollbar::NonClient::GetPSBInfo(v22, v25);
  if ( PSBInfo )
  {
    v28 = 20;
    if ( v4 != 1 )
      v28 = 4;
    return Scrollbar::GetScrollBarParameters(v22, (struct tagWND *)v4, (int)PSBInfo + v28, lParam, v31);
  }
  else
  {
    RtlSetLastWin32Error(0x5A7u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids, a1);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180042e90  mov     [rsp+arg_10], r8
0x180042e95  mov     [rsp+arg_0], rcx
0x180042e9a  push    rbx
0x180042e9b  push    rsi
0x180042e9c  push    rdi
0x180042e9d  push    r12
0x180042e9f  push    r13
0x180042ea1  push    r14
0x180042ea3  push    r15
0x180042ea5  sub     rsp, 50h
0x180042ea9  mov     rbx, r8
0x180042eac  mov     r12d, edx
0x180042eaf  mov     r14, rcx
0x180042eb2  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180042eb7  mov     r8, rax
0x180042eba  test    rax, rax
0x180042ebd  jnz     short loc_180042EF5
0x180042ebf  lea     rsi, WPP_GLOBAL_Control
0x180042ec6  mov     rcx, cs:WPP_GLOBAL_Control
0x180042ecd  cmp     rcx, rsi
0x180042ed0  jz      loc_18004327F
0x180042ed6  test    byte ptr [rcx+1Ch], 20h
0x180042eda  jz      loc_18004327F
0x180042ee0  lea     edi, [rax+2]
0x180042ee3  cmp     [rcx+19h], dil
0x180042ee7  jb      loc_18004327F
0x180042eed  lea     edx, [rax+17h]
0x180042ef0  jmp     loc_18004326C
0x180042ef5  lea     rsi, WPP_GLOBAL_Control
0x180042efc  mov     r10, cs:WPP_GLOBAL_Control
0x180042f03  mov     r13d, 4
0x180042f09  cmp     r10, rsi
0x180042f0c  jz      short loc_180042F64
0x180042f0e  test    byte ptr [r10+1Ch], 20h
0x180042f13  jz      short loc_180042F64
0x180042f15  cmp     [r10+19h], r13b
0x180042f19  jb      short loc_180042F64
0x180042f1b  mov     rcx, r8; this
0x180042f1e  call    ?GetFnidString@Scrollbar@@YAPEBDPEBUtagWND@@@Z; Scrollbar::GetFnidString(tagWND const *)
0x180042f23  mov     r9, rax
0x180042f26  mov     ecx, r12d
0x180042f29  call    GetScrollbarTypeString
0x180042f2e  movzx   r8d, byte ptr [r8+0EAh]
0x180042f36  shr     r8d, 2
0x180042f3a  and     r8d, 1
0x180042f3e  lea     edx, [r13+14h]
0x180042f42  mov     [rsp+88h+var_58], rax; __int64
0x180042f47  mov     dword ptr [rsp+88h+var_60], r8d; char
0x180042f4c  mov     [rsp+88h+var_68], r9; __int64
0x180042f51  mov     r9, r14
0x180042f54  mov     rcx, [r10+10h]; LoggerHandle
0x180042f58  call    WPP_SF_qsls
0x180042f5d  mov     r10, cs:WPP_GLOBAL_Control
0x180042f64  cmp     dword ptr [rbx], 1Ch
0x180042f67  jz      short loc_180042FE1
0x180042f69  cmp     dword ptr [rbx], 18h
0x180042f6c  jz      short loc_180042FAD
0x180042f6e  cmp     r10, rsi
0x180042f71  jz      loc_18004327F
0x180042f77  test    byte ptr [r10+1Ch], 20h
0x180042f7c  jz      loc_18004327F
0x180042f82  mov     edi, 2
0x180042f87  cmp     [r10+19h], dil
0x180042f8b  jb      loc_18004327F
0x180042f91  lea     edx, [rdi+17h]
0x180042f94  mov     dword ptr [rsp+88h+var_68], 18h
0x180042f9c  mov     r9d, [rbx]
0x180042f9f  mov     rcx, [r10+10h]
0x180042fa3  call    WPP_SF_DD
0x180042fa8  jmp     loc_18004327F
0x180042fad  cmp     r10, rsi
0x180042fb0  jz      short loc_180042FE1
0x180042fb2  test    byte ptr [r10+1Ch], 20h
0x180042fb7  jz      short loc_180042FE1
0x180042fb9  cmp     byte ptr [r10+19h], 3
0x180042fbe  jb      short loc_180042FE1
0x180042fc0  mov     edx, 1Ah
0x180042fc5  mov     dword ptr [rsp+88h+var_68], 1Ch; struct tagSCROLLINFO *
0x180042fcd  lea     r9d, [rdx-2]
0x180042fd1  mov     rcx, [r10+10h]
0x180042fd5  call    WPP_SF_DD
0x180042fda  mov     r10, cs:WPP_GLOBAL_Control
0x180042fe1  mov     r9d, [rbx+4]
0x180042fe5  test    r9d, 0FFFF8FE0h
0x180042fec  jz      short loc_180043029
0x180042fee  cmp     r10, rsi
0x180042ff1  jz      loc_18004327F
0x180042ff7  test    byte ptr [r10+1Ch], 20h
0x180042ffc  jz      loc_18004327F
0x180043002  mov     edi, 2
0x180043007  cmp     [r10+19h], dil
0x18004300b  jb      loc_18004327F
0x180043011  lea     edx, [rdi+19h]
0x180043014  lea     r8, WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids
0x18004301b  mov     rcx, [r10+10h]
0x18004301f  call    WPP_SF_d
0x180043024  jmp     loc_18004327F
0x180043029  mov     ecx, r12d
0x18004302c  test    r12d, r12d
0x18004302f  jz      short loc_1800430A7
0x180043031  sub     ecx, 1
0x180043034  jz      short loc_1800430A7
0x180043036  cmp     ecx, 1
0x180043039  jz      short loc_18004308A
0x18004303b  mov     ecx, 57h ; 'W'; LastError
0x180043040  call    cs:__imp_RtlSetLastWin32Error
0x180043046  mov     rcx, cs:WPP_GLOBAL_Control
0x18004304d  cmp     rcx, rsi
0x180043050  jz      loc_18004327F
0x180043056  test    byte ptr [rcx+1Ch], 20h
0x18004305a  jz      loc_18004327F
0x180043060  mov     edi, 2
0x180043065  cmp     [rcx+19h], dil
0x180043069  jb      loc_18004327F
0x18004306f  lea     edx, [rdi+1Eh]
0x180043072  mov     r9d, r12d
0x180043075  lea     r8, WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids
0x18004307c  mov     rcx, [rcx+10h]
0x180043080  call    WPP_SF_d
0x180043085  jmp     loc_18004327F
0x18004308a  mov     r9, rbx; lParam
0x18004308d  xor     r8d, r8d; wParam
0x180043090  mov     edx, 0EAh; Msg
0x180043095  mov     rcx, r14; hWnd
0x180043098  call    SendMessageW
0x18004309d  mov     eax, 1
0x1800430a2  jmp     loc_1800432AF
0x1800430a7  mov     rcx, r14; HWND
0x1800430aa  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x1800430af  mov     r15, rax
0x1800430b2  test    rax, rax
0x1800430b5  jnz     short loc_1800430E6
0x1800430b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800430be  cmp     rcx, rsi
0x1800430c1  jz      loc_18004327F
0x1800430c7  test    byte ptr [rcx+1Ch], 20h
0x1800430cb  jz      loc_18004327F
0x1800430d1  lea     edi, [rax+2]
0x1800430d4  cmp     [rcx+19h], dil
0x1800430d8  jb      loc_18004327F
0x1800430de  lea     edx, [rax+1Ch]
0x1800430e1  jmp     loc_18004326C
0x1800430e6  test    [rax+0EAh], r13b
0x1800430ed  jz      short loc_18004311A
0x1800430ef  mov     [rsp+88h+arg_18], 20000h
0x1800430fa  mov     edi, 2
0x1800430ff  mov     r8d, 1C5h
0x180043105  mov     edx, [rsp+88h+arg_18]
0x18004310c  lea     rcx, aIxptellmeif; "IXPTellMeIf"
0x180043113  call    MicrosoftTelemetryAssertTriggeredArgs
0x180043118  jmp     short loc_18004311F
0x18004311a  mov     edi, 2
0x18004311f  mov     rcx, r14
0x180043122  call    GetRealWindowOwner
0x180043127  mov     ebx, eax
0x180043129  call    cs:__imp_GetCurrentProcessId
0x18004312f  cmp     eax, ebx
0x180043131  jz      short loc_180043157
0x180043133  mov     [rsp+88h+arg_18], 20000h
0x18004313e  mov     r8d, 1C9h
0x180043144  mov     edx, [rsp+88h+arg_18]
0x18004314b  lea     rcx, aIxptellmeif; "IXPTellMeIf"
0x180043152  call    MicrosoftTelemetryAssertTriggeredArgs
0x180043157  call    Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline
0x18004315c  test    eax, eax
0x18004315e  jz      loc_180043238
0x180043164  mov     rcx, r14
0x180043167  call    GetRealWindowOwner
0x18004316c  mov     ebx, eax
0x18004316e  call    cs:__imp_GetCurrentProcessId
0x180043174  cmp     eax, ebx
0x180043176  jz      short loc_180043180
0x180043178  xor     r8d, r8d
0x18004317b  jmp     loc_18004329B
0x180043180  mov     rcx, r15; this
0x180043183  call    ?GetPSBInfo@NonClient@Scrollbar@@YAPEAUtagSBINFO@@PEBUtagWND@@@Z; Scrollbar::NonClient::GetPSBInfo(tagWND const *)
0x180043188  test    rax, rax
0x18004318b  jnz     short loc_1800431CF
0x18004318d  mov     ecx, 5A7h; LastError
0x180043192  call    cs:__imp_RtlSetLastWin32Error
0x180043198  mov     rcx, cs:WPP_GLOBAL_Control
0x18004319f  cmp     rcx, rsi
0x1800431a2  jz      short loc_1800431C8
0x1800431a4  test    byte ptr [rcx+1Ch], 20h
0x1800431a8  jz      short loc_1800431C8
0x1800431aa  cmp     [rcx+19h], dil
0x1800431ae  jb      short loc_1800431C8
0x1800431b0  mov     edx, 1Dh
0x1800431b5  mov     r9, r14
0x1800431b8  lea     r8, WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids
0x1800431bf  mov     rcx, [rcx+10h]
0x1800431c3  call    WPP_SF_q
0x1800431c8  xor     eax, eax
0x1800431ca  jmp     loc_1800432AF
0x1800431cf  mov     r8d, 14h
0x1800431d5  cmp     r12d, 1
0x1800431d9  cmovnz  r8, r13
0x1800431dd  add     r8, rax; int
0x1800431e0  mov     r9, [rsp+88h+arg_10]; struct tagSBDATA *
0x1800431e8  mov     edx, r12d; struct tagWND *
0x1800431eb  mov     rcx, r15; this
0x1800431ee  call    ?GetScrollBarParameters@Scrollbar@@YAHPEAUtagWND@@HPEAUtagSBDATA@@PEAUtagSCROLLINFO@@@Z; Scrollbar::GetScrollBarParameters(tagWND *,int,tagSBDATA *,tagSCROLLINFO *)
0x1800431f3  jmp     loc_1800432AF
0x1800431f8  lea     rax, WPP_GLOBAL_Control
0x1800431ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180043206  cmp     rcx, rax
0x180043209  jz      short loc_180043234
0x18004320b  test    byte ptr [rcx+1Ch], 20h
0x18004320f  jz      short loc_180043234
0x180043211  cmp     byte ptr [rcx+19h], 2
0x180043215  jb      short loc_180043234
0x180043217  mov     edx, 1Eh
0x18004321c  mov     r9, [rsp+88h+arg_0]
0x180043224  lea     r8, WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids
0x18004322b  mov     rcx, [rcx+10h]
0x18004322f  call    WPP_SF_q
0x180043234  xor     eax, eax
0x180043236  jmp     short loc_1800432AF
0x180043238  mov     rax, [r15+90h]
0x18004323f  test    rax, rax
0x180043242  jnz     short loc_180043283
0x180043244  mov     ecx, 5A7h; LastError
0x180043249  call    cs:__imp_RtlSetLastWin32Error
0x18004324f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043256  cmp     rcx, rsi
0x180043259  jz      short loc_18004327F
0x18004325b  test    byte ptr [rcx+1Ch], 20h
0x18004325f  jz      short loc_18004327F
0x180043261  cmp     [rcx+19h], dil
0x180043265  jb      short loc_18004327F
0x180043267  mov     edx, 1Fh
0x18004326c  mov     r9, r14
0x18004326f  lea     r8, WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids
0x180043276  mov     rcx, [rcx+10h]
0x18004327a  call    WPP_SF_q
0x18004327f  xor     eax, eax
0x180043281  jmp     short loc_1800432AF
0x180043283  mov     r8d, 14h
0x180043289  cmp     r12d, 1
0x18004328d  cmovnz  r8, r13
0x180043291  sub     r8, [r15+8]
0x180043295  add     r8, rax
0x180043298  add     r8, r15
0x18004329b  mov     r9, [rsp+88h+arg_10]
0x1800432a3  mov     edx, r12d
0x1800432a6  mov     rcx, r14
0x1800432a9  call    cs:__imp_NtUserSBGetParms
0x1800432af  add     rsp, 50h
0x1800432b3  pop     r15
0x1800432b5  pop     r14
0x1800432b7  pop     r13
0x1800432b9  pop     r12
0x1800432bb  pop     rdi
0x1800432bc  pop     rsi
0x1800432bd  pop     rbx
0x1800432be  retn
0x1800979bb  push    rbp
0x1800979bd  sub     rsp, 40h
0x1800979c1  mov     rbp, rdx
0x1800979c4  mov     rax, [rcx]
0x1800979c7  mov     ecx, [rax]
0x1800979c9  mov     [rbp+40h], ecx
0x1800979cc  mov     ecx, [rbp+40h]
0x1800979cf  call    SetLastNtError
0x1800979d4  mov     dword ptr [rbp+48h], 1
0x1800979db  mov     eax, [rbp+48h]
0x1800979de  add     rsp, 40h
0x1800979e2  pop     rbp
0x1800979e3  retn
```
