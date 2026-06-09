# RealSetScrollInfo(HWND__ *,int,tagSCROLLINFO const *,int)

- ea: `0x1800435a0`
- end: `0x18004378b`
- name: `?RealSetScrollInfo@@YAHPEAUHWND__@@HPEBUtagSCROLLINFO@@H@Z`
- size: `491`
- prototype: `__int64 __fastcall(HWND, int, const struct tagSCROLLINFO *, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000cf20`
- `0x18000d210`
- `0x1800432d0`
- `0x1800435a0`
- `0x180043794`
- `0x1800437c4`
- `0x18004397c`
- `0x1800439b8`
- `0x1800592f0`
- `0x18005b678`
- `0x18006bbac`
- `0x180074ef0`
- `0x18008b88c`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserSetScrollInfo` at `0x18004362c`
- `win32u!NtUserSetScrollInfo` at `0x18004362c`
- `ntdll!RtlSetLastWin32Error` at `0x180043745`
- `ntdll!RtlSetLastWin32Error` at `0x180043745`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009ddca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009ddca`

## pseudocode

```c
int __fastcall RealSetScrollInfo(HWND a1, unsigned int a2, const struct tagSCROLLINFO *a3, int a4)
{
  WPARAM v4; // r12
  Scrollbar *v8; // rax
  const struct tagWND *v9; // rdx
  Scrollbar *v10; // rbx
  __int128 v12; // xmm1
  const char *FnidString; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 ScrollbarTypeString; // rax
  __int64 v17; // r10
  __int64 v18; // r9
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  Scrollbar::NonClient *v21; // rbx
  int RealWindowOwner; // ebx
  __int128 v23; // xmm1
  int v24; // [rsp+20h] [rbp-88h]
  int v25; // [rsp+28h] [rbp-80h]
  _BYTE lParam[28]; // [rsp+48h] [rbp-60h] BYREF

  v4 = a4;
  v8 = ValidateHwnd(a1);
  v10 = v8;
  if ( !v8 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v20 = 20;
LABEL_27:
    WPP_SF_q(v19[2], v20, &WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids, a1);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    FnidString = Scrollbar::GetFnidString(v8, v9);
    ScrollbarTypeString = GetScrollbarTypeString(a2, v14, v15, FnidString);
    WPP_SF_qslsl(*(_QWORD *)(v17 + 16), v18, (*((_BYTE *)v10 + 234) & 4) != 0, ScrollbarTypeString, v4);
  }
  if ( IsNonClientScrollBarCode(a2) )
  {
    if ( (*((_BYTE *)v10 + 234) & 4) != 0 )
      MicrosoftTelemetryAssertTriggeredArgs("IXPTellMeIf", 0x20000, 303);
    RealWindowOwner = GetRealWindowOwner(a1);
    if ( GetCurrentProcessId() != RealWindowOwner )
      MicrosoftTelemetryAssertTriggeredArgs("IXPTellMeIf", 0x20000, 307);
  }
  if ( a2 == 2 )
  {
    if ( a3 )
    {
      v12 = *(_OWORD *)&a3->nMax;
      *(_OWORD *)lParam = *(_OWORD *)&a3->cbSize;
      *(_OWORD *)&lParam[12] = v12;
      return SendMessageW(a1, 0xE9u, v4, (LPARAM)lParam);
    }
    goto LABEL_18;
  }
  if ( !(unsigned int)Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline() )
    return NtUserSetScrollInfo(a1, a2, a3, (unsigned int)v4);
  v21 = ValidateHwnd(a1);
  if ( !v21 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v20 = 22;
    goto LABEL_27;
  }
  if ( !VerifyScrollBarCode(a2, "SetScrollInfo") )
    return 0;
  if ( !a3 )
  {
LABEL_18:
    RtlSetLastWin32Error(0x3E6u);
    return 0;
  }
  v23 = *(_OWORD *)&a3->nMax;
  *(_OWORD *)lParam = *(_OWORD *)&a3->cbSize;
  *(_OWORD *)&lParam[12] = v23;
  return Scrollbar::NonClient::SetScrollBar(
           v21,
           (struct tagWND *)a2,
           (int)lParam,
           (struct tagSCROLLINFO *)(unsigned int)v4,
           v24,
           v25);
}

```

## disassembly

```asm
0x1800435a0  push    rbx
0x1800435a2  push    rbp
0x1800435a3  push    rsi
0x1800435a4  push    rdi
0x1800435a5  push    r12
0x1800435a7  push    r14
0x1800435a9  push    r15
0x1800435ab  sub     rsp, 70h
0x1800435af  mov     rax, cs:__security_cookie
0x1800435b6  xor     rax, rsp
0x1800435b9  mov     [rsp+0A8h+var_40], rax
0x1800435be  movsxd  r12, r9d
0x1800435c1  mov     rsi, r8
0x1800435c4  mov     r15d, edx
0x1800435c7  mov     rbp, rcx
0x1800435ca  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x1800435cf  mov     rbx, rax
0x1800435d2  test    rax, rax
0x1800435d5  jz      loc_1800436D7
0x1800435db  mov     r10, cs:WPP_GLOBAL_Control
0x1800435e2  lea     r14, WPP_GLOBAL_Control
0x1800435e9  cmp     r10, r14
0x1800435ec  jz      short loc_1800435F9
0x1800435ee  test    byte ptr [r10+1Ch], 20h
0x1800435f3  jnz     loc_18004367F
0x1800435f9  mov     ecx, r15d; unsigned int
0x1800435fc  call    ?IsNonClientScrollBarCode@@YA_NI@Z; IsNonClientScrollBarCode(uint)
0x180043601  mov     edi, 2
0x180043606  test    al, al
0x180043608  jnz     loc_18004370F
0x18004360e  cmp     r15d, edi
0x180043611  jz      short loc_18004364E
0x180043613  call    Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline
0x180043618  mov     rcx, rbp; HWND
0x18004361b  test    eax, eax
0x18004361d  jnz     loc_180043751
0x180043623  mov     r9d, r12d
0x180043626  mov     r8, rsi
0x180043629  mov     edx, r15d
0x18004362c  call    cs:__imp_NtUserSetScrollInfo
0x180043632  mov     rcx, [rsp+0A8h+var_40]
0x180043637  xor     rcx, rsp; StackCookie
0x18004363a  call    __security_check_cookie
0x18004363f  add     rsp, 70h
0x180043643  pop     r15
0x180043645  pop     r14
0x180043647  pop     r12
0x180043649  pop     rdi
0x18004364a  pop     rsi
0x18004364b  pop     rbp
0x18004364c  pop     rbx
0x18004364d  retn
0x18004364e  test    rsi, rsi
0x180043651  jz      loc_180043740
0x180043657  movups  xmm0, xmmword ptr [rsi]
0x18004365a  mov     r8, r12; wParam
0x18004365d  lea     r9, [rsp+0A8h+lParam]; lParam
0x180043662  movups  xmm1, xmmword ptr [rsi+0Ch]
0x180043666  mov     edx, 0E9h; Msg
0x18004366b  mov     rcx, rbp; hWnd
0x18004366e  movups  xmmword ptr [rsp+0A8h+lParam], xmm0
0x180043673  movups  xmmword ptr [rsp+0A8h+lParam+0Ch], xmm1
0x180043678  call    SendMessageW
0x18004367d  jmp     short loc_180043632
0x18004367f  cmp     byte ptr [r10+19h], 4
0x180043684  jb      loc_1800435F9
0x18004368a  mov     rcx, rbx; this
0x18004368d  call    ?GetFnidString@Scrollbar@@YAPEBDPEBUtagWND@@@Z; Scrollbar::GetFnidString(tagWND const *)
0x180043692  mov     ecx, r15d
0x180043695  mov     r9, rax
0x180043698  call    GetScrollbarTypeString
0x18004369d  movzx   r8d, byte ptr [rbx+0EAh]
0x1800436a5  mov     edx, 15h
0x1800436aa  mov     rcx, [r10+10h]; LoggerHandle
0x1800436ae  mov     dword ptr [rsp+0A8h+var_70], r12d; char
0x1800436b3  mov     [rsp+0A8h+var_78], rax; __int64
0x1800436b8  shr     r8d, 2
0x1800436bc  and     r8d, 1
0x1800436c0  mov     dword ptr [rsp+0A8h+var_80], r8d; char
0x1800436c5  mov     [rsp+0A8h+var_88], r9; __int64
0x1800436ca  mov     r9, rbp
0x1800436cd  call    WPP_SF_qslsl
0x1800436d2  jmp     loc_1800435F9
0x1800436d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800436de  lea     r14, WPP_GLOBAL_Control
0x1800436e5  cmp     rcx, r14
0x1800436e8  jz      loc_18009DE14
0x1800436ee  test    byte ptr [rcx+1Ch], 20h
0x1800436f2  jz      loc_18009DE14
0x1800436f8  mov     edi, 2
0x1800436fd  cmp     [rcx+19h], dil
0x180043701  jb      loc_18009DE14
0x180043707  lea     edx, [rdi+12h]
0x18004370a  jmp     loc_18009DE01
0x18004370f  test    byte ptr [rbx+0EAh], 4
0x180043716  jz      loc_18009DDC0
0x18004371c  mov     [rsp+0A8h+var_68], 20000h
0x180043724  lea     rcx, aIxptellmeif; "IXPTellMeIf"
0x18004372b  mov     edx, [rsp+0A8h+var_68]
0x18004372f  mov     r8d, 12Fh
0x180043735  call    MicrosoftTelemetryAssertTriggeredArgs
0x18004373a  nop
0x18004373b  jmp     loc_18009DDC0
0x180043740  mov     ecx, 3E6h; LastError
0x180043745  call    cs:__imp_RtlSetLastWin32Error
0x18004374b  nop
0x18004374c  jmp     loc_18009DE14
0x180043751  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180043756  mov     rbx, rax
0x180043759  test    rax, rax
0x18004375c  jnz     loc_18009DE1B
0x180043762  mov     rcx, cs:WPP_GLOBAL_Control
0x180043769  cmp     rcx, r14
0x18004376c  jz      loc_18009DE14
0x180043772  test    byte ptr [rcx+1Ch], 20h
0x180043776  jz      loc_18009DE14
0x18004377c  cmp     [rcx+19h], dil
0x180043780  jnb     loc_18009DDFC
0x180043786  jmp     loc_18009DE14
0x18009ddc0  mov     rcx, rbp
0x18009ddc3  call    GetRealWindowOwner
0x18009ddc8  mov     ebx, eax
0x18009ddca  call    cs:__imp_GetCurrentProcessId
0x18009ddd0  cmp     eax, ebx
0x18009ddd2  jz      loc_18004360E
0x18009ddd8  mov     [rsp+0A8h+var_68], 20000h
0x18009dde0  lea     rcx, aIxptellmeif; "IXPTellMeIf"
0x18009dde7  mov     edx, [rsp+0A8h+var_68]
0x18009ddeb  mov     r8d, 133h
0x18009ddf1  call    MicrosoftTelemetryAssertTriggeredArgs
0x18009ddf6  nop
0x18009ddf7  jmp     loc_18004360E
0x18009ddfc  mov     edx, 16h
0x18009de01  mov     rcx, [rcx+10h]
0x18009de05  lea     r8, WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids
0x18009de0c  mov     r9, rbp
0x18009de0f  call    WPP_SF_q
0x18009de14  xor     eax, eax
0x18009de16  jmp     loc_180043632
0x18009de1b  lea     rdx, aSetscrollinfo_0; "SetScrollInfo"
0x18009de22  mov     ecx, r15d; int
0x18009de25  call    ?VerifyScrollBarCode@@YA_NHQEBD@Z; VerifyScrollBarCode(int,char const * const)
0x18009de2a  test    al, al
0x18009de2c  jz      short loc_18009DE14
0x18009de2e  test    rsi, rsi
0x18009de31  jz      loc_180043740
0x18009de37  movups  xmm0, xmmword ptr [rsi]
0x18009de3a  mov     r9d, r12d; struct tagSCROLLINFO *
0x18009de3d  lea     r8, [rsp+0A8h+lParam]; int
0x18009de42  movups  xmm1, xmmword ptr [rsi+0Ch]
0x18009de46  mov     edx, r15d; struct tagWND *
0x18009de49  mov     rcx, rbx; this
0x18009de4c  movups  xmmword ptr [rsp+0A8h+lParam], xmm0
0x18009de51  movups  xmmword ptr [rsp+0A8h+lParam+0Ch], xmm1
0x18009de56  call    ?SetScrollBar@NonClient@Scrollbar@@YAJPEAUtagWND@@HPEAUtagSCROLLINFO@@HH@Z; Scrollbar::NonClient::SetScrollBar(tagWND *,int,tagSCROLLINFO *,int,int)
0x18009de5b  nop
0x18009de5c  jmp     loc_180043632
```
