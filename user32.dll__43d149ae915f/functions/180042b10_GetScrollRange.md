# GetScrollRange

- ea: `0x180042b10`
- end: `0x180042e83`
- name: `GetScrollRange`
- size: `883`
- prototype: `BOOL __stdcall(HWND hWnd, int nBar, LPINT lpMinPos, LPINT lpMaxPos)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000cf20`
- `0x18000d210`
- `0x180020e80`
- `0x180042b10`
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

- `ntdll!RtlSetLastWin32Error` at `0x180042c78`
- `ntdll!RtlSetLastWin32Error` at `0x180042d70`
- `ntdll!RtlSetLastWin32Error` at `0x180042e2e`
- `ntdll!RtlSetLastWin32Error` at `0x180042c78`
- `ntdll!RtlSetLastWin32Error` at `0x180042d70`
- `ntdll!RtlSetLastWin32Error` at `0x180042e2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180042c39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180042c39`

## pseudocode

```c
BOOL __stdcall GetScrollRange(HWND hWnd, int nBar, LPINT lpMinPos, LPINT lpMaxPos)
{
  Scrollbar *v7; // rax
  const struct tagWND *v8; // rdx
  Scrollbar *v9; // rbx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  const char *FnidString; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 ScrollbarTypeString; // rax
  __int64 v16; // r10
  __int64 v17; // r9
  bool v18; // al
  int RealWindowOwner; // ebx
  struct tagWND *v20; // rbx
  const struct tagWND *v22; // rdx
  struct tagSBINFO *PSBInfo; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  char *v26; // rcx
  __int64 v27; // rdx
  bool v28; // [rsp+40h] [rbp-48h]

  v7 = ValidateHwnd(hWnd);
  v9 = v7;
  if ( !v7 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v11 = 44;
LABEL_28:
    WPP_SF_q(v10[2], v11, &WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids, hWnd);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    FnidString = Scrollbar::GetFnidString(v7, v8);
    ScrollbarTypeString = GetScrollbarTypeString((unsigned int)nBar, v13, v14, FnidString);
    WPP_SF_qsls(*(_QWORD *)(v16 + 16), v17, (*((_BYTE *)v9 + 234) & 4) != 0, ScrollbarTypeString);
  }
  v18 = IsNonClientScrollBarCode(nBar);
  v28 = v18;
  if ( v18 && (*((_BYTE *)v9 + 234) & 4) != 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs("IXPTellMeIf", 0x20000, 724);
    v18 = v28;
  }
  if ( v18 )
  {
    RealWindowOwner = GetRealWindowOwner(hWnd);
    if ( GetCurrentProcessId() != RealWindowOwner )
      MicrosoftTelemetryAssertTriggeredArgs("IXPTellMeIf", 0x20000, 728);
  }
  if ( (unsigned int)nBar < 2 )
  {
    v20 = ValidateHwnd(hWnd);
    if ( !v20 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 0;
      }
      v11 = 46;
      goto LABEL_28;
    }
    *lpMinPos = 0;
    *lpMaxPos = 0;
    if ( (unsigned int)Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline() )
    {
      PSBInfo = Scrollbar::NonClient::GetPSBInfo(v20, v22);
      if ( PSBInfo )
      {
        v24 = 20;
        if ( nBar != 1 )
          v24 = 4;
        *lpMinPos = *(_DWORD *)((char *)PSBInfo + v24);
        *lpMaxPos = *(_DWORD *)((char *)PSBInfo + v24 + 4);
      }
      else
      {
        RtlSetLastWin32Error(0x5A7u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids, hWnd);
        }
      }
    }
    else
    {
      v25 = *((_QWORD *)v20 + 18);
      if ( v25 && (v26 = (char *)v20 + v25 - *((_QWORD *)v20 + 1)) != 0 )
      {
        v27 = 20;
        if ( nBar != 1 )
          v27 = 4;
        *lpMinPos = *(_DWORD *)&v26[v27];
        *lpMaxPos = *(_DWORD *)&v26[v27 + 4];
      }
      else
      {
        RtlSetLastWin32Error(0x5A7u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids, hWnd);
        }
      }
    }
  }
  else
  {
    if ( nBar != 2 )
    {
      RtlSetLastWin32Error(0x57u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          &WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids,
          (unsigned int)nBar);
      }
      return 0;
    }
    SendMessageW(hWnd, 0xE3u, (WPARAM)lpMinPos, (LPARAM)lpMaxPos);
  }
  return 1;
}

```

## disassembly

```asm
0x180042b10  mov     rax, rsp
0x180042b13  mov     [rax+10h], rbx
0x180042b17  mov     [rax+20h], rsi
0x180042b1b  mov     [rax+18h], r8
0x180042b1f  mov     [rax+8], rcx
0x180042b23  push    rdi
0x180042b24  push    r12
0x180042b26  push    r13
0x180042b28  push    r14
0x180042b2a  push    r15
0x180042b2c  sub     rsp, 60h
0x180042b30  mov     r13, r9
0x180042b33  mov     r12d, edx
0x180042b36  mov     rsi, rcx
0x180042b39  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180042b3e  mov     rbx, rax
0x180042b41  test    rax, rax
0x180042b44  jnz     short loc_180042B7C
0x180042b46  lea     r14, WPP_GLOBAL_Control
0x180042b4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180042b54  cmp     rcx, r14
0x180042b57  jz      loc_180042D0F
0x180042b5d  test    byte ptr [rcx+1Ch], 20h
0x180042b61  jz      loc_180042D0F
0x180042b67  lea     edi, [rax+2]
0x180042b6a  cmp     [rcx+19h], dil
0x180042b6e  jb      loc_180042D0F
0x180042b74  lea     edx, [rax+2Ch]
0x180042b77  jmp     loc_180042CFC
0x180042b7c  lea     r14, WPP_GLOBAL_Control
0x180042b83  mov     r10, cs:WPP_GLOBAL_Control
0x180042b8a  mov     r15d, 4
0x180042b90  cmp     r10, r14
0x180042b93  jz      short loc_180042BE4
0x180042b95  test    byte ptr [r10+1Ch], 20h
0x180042b9a  jz      short loc_180042BE4
0x180042b9c  cmp     [r10+19h], r15b
0x180042ba0  jb      short loc_180042BE4
0x180042ba2  mov     rcx, rbx; this
0x180042ba5  call    ?GetFnidString@Scrollbar@@YAPEBDPEBUtagWND@@@Z; Scrollbar::GetFnidString(tagWND const *)
0x180042baa  mov     r9, rax
0x180042bad  mov     ecx, r12d
0x180042bb0  call    GetScrollbarTypeString
0x180042bb5  movzx   r8d, byte ptr [rbx+0EAh]
0x180042bbd  shr     r8d, 2
0x180042bc1  and     r8d, 1
0x180042bc5  lea     edx, [r15+29h]
0x180042bc9  mov     [rsp+88h+var_58], rax; __int64
0x180042bce  mov     dword ptr [rsp+88h+var_60], r8d; char
0x180042bd3  mov     [rsp+88h+var_68], r9; __int64
0x180042bd8  mov     r9, rsi
0x180042bdb  mov     rcx, [r10+10h]; LoggerHandle
0x180042bdf  call    WPP_SF_qsls
0x180042be4  mov     ecx, r12d; unsigned int
0x180042be7  call    ?IsNonClientScrollBarCode@@YA_NI@Z; IsNonClientScrollBarCode(uint)
0x180042bec  mov     [rsp+88h+var_48], al
0x180042bf0  test    al, al
0x180042bf2  jz      short loc_180042C26
0x180042bf4  test    [rbx+0EAh], r15b
0x180042bfb  jz      short loc_180042C26
0x180042bfd  mov     [rsp+88h+var_44], 20000h
0x180042c05  mov     edi, 2
0x180042c0a  mov     r8d, 2D4h
0x180042c10  mov     edx, [rsp+88h+var_44]
0x180042c14  lea     rcx, aIxptellmeif; "IXPTellMeIf"
0x180042c1b  call    MicrosoftTelemetryAssertTriggeredArgs
0x180042c20  mov     al, [rsp+88h+var_48]
0x180042c24  jmp     short loc_180042C2B
0x180042c26  mov     edi, 2
0x180042c2b  test    al, al
0x180042c2d  jz      short loc_180042C61
0x180042c2f  mov     rcx, rsi
0x180042c32  call    GetRealWindowOwner
0x180042c37  mov     ebx, eax
0x180042c39  call    cs:__imp_GetCurrentProcessId
0x180042c3f  cmp     eax, ebx
0x180042c41  jz      short loc_180042C61
0x180042c43  mov     [rsp+88h+var_44], 20000h
0x180042c4b  mov     r8d, 2D8h
0x180042c51  mov     edx, [rsp+88h+var_44]
0x180042c55  lea     rcx, aIxptellmeif; "IXPTellMeIf"
0x180042c5c  call    MicrosoftTelemetryAssertTriggeredArgs
0x180042c61  mov     ecx, r12d
0x180042c64  test    r12d, r12d
0x180042c67  jz      short loc_180042CD1
0x180042c69  sub     ecx, 1
0x180042c6c  jz      short loc_180042CD1
0x180042c6e  cmp     ecx, 1
0x180042c71  jz      short loc_180042CB4
0x180042c73  mov     ecx, 57h ; 'W'; LastError
0x180042c78  call    cs:__imp_RtlSetLastWin32Error
0x180042c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180042c85  cmp     rcx, r14
0x180042c88  jz      loc_180042D0F
0x180042c8e  test    byte ptr [rcx+1Ch], 20h
0x180042c92  jz      short loc_180042D0F
0x180042c94  cmp     [rcx+19h], dil
0x180042c98  jb      short loc_180042D0F
0x180042c9a  mov     edx, 32h ; '2'
0x180042c9f  mov     r9d, r12d
0x180042ca2  lea     r8, WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids
0x180042ca9  mov     rcx, [rcx+10h]
0x180042cad  call    WPP_SF_d
0x180042cb2  jmp     short loc_180042D0F
0x180042cb4  mov     r9, r13; lParam
0x180042cb7  mov     r8, [rsp+88h+wParam]; wParam
0x180042cbf  mov     edx, 0E3h; Msg
0x180042cc4  mov     rcx, rsi; hWnd
0x180042cc7  call    SendMessageW
0x180042ccc  jmp     loc_180042E64
0x180042cd1  mov     rcx, rsi; HWND
0x180042cd4  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180042cd9  mov     rbx, rax
0x180042cdc  test    rax, rax
0x180042cdf  jnz     short loc_180042D16
0x180042ce1  mov     rcx, cs:WPP_GLOBAL_Control
0x180042ce8  cmp     rcx, r14
0x180042ceb  jz      short loc_180042D0F
0x180042ced  test    byte ptr [rcx+1Ch], 20h
0x180042cf1  jz      short loc_180042D0F
0x180042cf3  cmp     [rcx+19h], dil
0x180042cf7  jb      short loc_180042D0F
0x180042cf9  lea     edx, [rax+2Eh]
0x180042cfc  mov     r9, rsi
0x180042cff  lea     r8, WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids
0x180042d06  mov     rcx, [rcx+10h]
0x180042d0a  call    WPP_SF_q
0x180042d0f  xor     eax, eax
0x180042d11  jmp     loc_180042E69
0x180042d16  mov     rax, [rsp+88h+wParam]
0x180042d1e  mov     dword ptr [rax], 0
0x180042d24  mov     dword ptr [r13+0], 0
0x180042d2c  call    Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline
0x180042d31  test    eax, eax
0x180042d33  jz      loc_180042DEB
0x180042d39  mov     rcx, rbx; this
0x180042d3c  call    ?GetPSBInfo@NonClient@Scrollbar@@YAPEAUtagSBINFO@@PEBUtagWND@@@Z; Scrollbar::NonClient::GetPSBInfo(tagWND const *)
0x180042d41  test    rax, rax
0x180042d44  jz      short loc_180042D6B
0x180042d46  mov     edx, 14h
0x180042d4b  cmp     r12d, 1
0x180042d4f  cmovnz  rdx, r15
0x180042d53  mov     ecx, [rdx+rax]
0x180042d56  mov     r8, [rsp+88h+wParam]
0x180042d5e  mov     [r8], ecx
0x180042d61  mov     eax, [rdx+rax+4]
0x180042d65  mov     [r13+0], eax
0x180042d69  jmp     short loc_180042DA6
0x180042d6b  mov     ecx, 5A7h; LastError
0x180042d70  call    cs:__imp_RtlSetLastWin32Error
0x180042d76  mov     rcx, cs:WPP_GLOBAL_Control
0x180042d7d  cmp     rcx, r14
0x180042d80  jz      short loc_180042DA6
0x180042d82  test    byte ptr [rcx+1Ch], 20h
0x180042d86  jz      short loc_180042DA6
0x180042d88  cmp     [rcx+19h], dil
0x180042d8c  jb      short loc_180042DA6
0x180042d8e  mov     edx, 2Fh ; '/'
0x180042d93  mov     r9, rsi
0x180042d96  lea     r8, WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids
0x180042d9d  mov     rcx, [rcx+10h]
0x180042da1  call    WPP_SF_q
0x180042da6  jmp     loc_180042E64
0x180042dab  lea     rax, WPP_GLOBAL_Control
0x180042db2  mov     rcx, cs:WPP_GLOBAL_Control
0x180042db9  cmp     rcx, rax
0x180042dbc  jz      short loc_180042DE7
0x180042dbe  test    byte ptr [rcx+1Ch], 20h
0x180042dc2  jz      short loc_180042DE7
0x180042dc4  cmp     byte ptr [rcx+19h], 2
0x180042dc8  jb      short loc_180042DE7
0x180042dca  mov     edx, 30h ; '0'
0x180042dcf  mov     r9, [rsp+88h+arg_0]
0x180042dd7  lea     r8, WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids
0x180042dde  mov     rcx, [rcx+10h]
0x180042de2  call    WPP_SF_q
0x180042de7  xor     eax, eax
0x180042de9  jmp     short loc_180042E69
0x180042deb  mov     rax, [rbx+90h]
0x180042df2  test    rax, rax
0x180042df5  jz      short loc_180042E29
0x180042df7  sub     rax, [rbx+8]
0x180042dfb  lea     rcx, [rax+rbx]
0x180042dff  test    rcx, rcx
0x180042e02  jz      short loc_180042E29
0x180042e04  mov     edx, 14h
0x180042e09  cmp     r12d, 1
0x180042e0d  cmovnz  rdx, r15
0x180042e11  mov     eax, [rdx+rcx]
0x180042e14  mov     r8, [rsp+88h+wParam]
0x180042e1c  mov     [r8], eax
0x180042e1f  mov     eax, [rdx+rcx+4]
0x180042e23  mov     [r13+0], eax
0x180042e27  jmp     short loc_180042E64
0x180042e29  mov     ecx, 5A7h; LastError
0x180042e2e  call    cs:__imp_RtlSetLastWin32Error
0x180042e34  mov     rcx, cs:WPP_GLOBAL_Control
0x180042e3b  cmp     rcx, r14
0x180042e3e  jz      short loc_180042E64
0x180042e40  test    byte ptr [rcx+1Ch], 20h
0x180042e44  jz      short loc_180042E64
0x180042e46  cmp     [rcx+19h], dil
0x180042e4a  jb      short loc_180042E64
0x180042e4c  mov     edx, 31h ; '1'
0x180042e51  mov     r9, rsi
0x180042e54  lea     r8, WPP_f04d849a7eb636d9296ede92ea79381a_Traceguids
0x180042e5b  mov     rcx, [rcx+10h]
0x180042e5f  call    WPP_SF_q
0x180042e64  mov     eax, 1
0x180042e69  lea     r11, [rsp+88h+var_28]
0x180042e6e  mov     rbx, [r11+38h]
0x180042e72  mov     rsi, [r11+48h]
0x180042e76  mov     rsp, r11
0x180042e79  pop     r15
0x180042e7b  pop     r14
0x180042e7d  pop     r13
0x180042e7f  pop     r12
0x180042e81  pop     rdi
0x180042e82  retn
0x18009798b  push    rbp
0x18009798d  sub     rsp, 40h
0x180097991  mov     rbp, rdx
0x180097994  mov     rax, [rcx]
0x180097997  mov     ecx, [rax]
0x180097999  mov     [rbp+48h], ecx
0x18009799c  mov     ecx, [rbp+48h]
0x18009799f  call    SetLastNtError
0x1800979a4  mov     dword ptr [rbp+50h], 1
0x1800979ab  mov     eax, [rbp+50h]
0x1800979ae  add     rsp, 40h
0x1800979b2  pop     rbp
0x1800979b3  retn
```
