# CWcnPageProfileCreateNew::OnKillActiveForward(void)

- ea: `0x180014da0`
- end: `0x180014fe0`
- name: `?OnKillActiveForward@CWcnPageProfileCreateNew@@QEAA_NXZ`
- size: `576`
- prototype: `bool __fastcall(CWcnPageProfileCreateNew *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180009be4`

## callees

- `0x180001844`
- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x1800116cc`
- `0x1800143ac`
- `0x180014da0`
- `0x180027bac`
- `0x18002de1c`

## import_xrefs

- `USER32!SendMessageW` at `0x180014e64`
- `USER32!SendMessageW` at `0x180014f91`
- `USER32!SendMessageW` at `0x180014e64`
- `USER32!SendMessageW` at `0x180014f91`
- `USER32!GetDlgItem` at `0x180014e50`
- `USER32!GetDlgItem` at `0x180014e50`
- `USER32!GetWindowTextW` at `0x180014e3e`
- `USER32!GetWindowTextW` at `0x180014e3e`

## pseudocode

```c
char __fastcall CWcnPageProfileCreateNew::OnKillActiveForward(CWcnPageProfileCreateNew *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  CWcnPageProfileCreateNew *v4; // rcx
  unsigned int v5; // esi
  unsigned int v6; // ebx
  HWND DlgItem; // rax
  bool v8; // al
  int NetworkProfile; // eax
  void *v10; // rsi
  int v11; // edi
  _BYTE *v12; // r10
  char *v13; // rbx
  int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // r10
  void *Block; // [rsp+70h] [rbp+8h] BYREF

  Block = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 26, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, Indent);
  }
  v4 = (CWcnPageProfileCreateNew *)(28LL * CWcnPageProfileCreateNew::GetSelectedItemHelper(this, *((HWND *)this + 41)));
  v5 = *(_DWORD *)&byte_1800369E0[(_QWORD)v4];
  v6 = *(_DWORD *)&byte_1800369E0[28 * CWcnPageProfileCreateNew::GetSelectedItemHelper(v4, *((HWND *)this + 43)) + 4];
  GetWindowTextW(*((HWND *)this + 37), (LPWSTR)this + 184, 64);
  DlgItem = GetDlgItem(*((HWND *)this + 21), 2304);
  v8 = (unsigned int)SendMessageW(DlgItem, 0xF0u, 0, 0) == 1;
  *((_BYTE *)this + 361) = v8;
  NetworkProfile = WcnWlanGenerateNetworkProfile(
                     (const unsigned __int16 *)this + 184,
                     v5,
                     v6,
                     (const unsigned __int16 *)this + 248,
                     v8,
                     (unsigned __int16 **)&Block);
  v10 = Block;
  v11 = NetworkProfile;
  if ( NetworkProfile >= 0 )
  {
    v13 = (char *)this + 192;
    v14 = tagWCNWIZ_DATA::SetProfile(
            *((tagWCNWIZ_DATA **)this + 24),
            (unsigned __int16 *)Block,
            (const unsigned __int16 *)this + 248);
    v11 = v14;
    if ( v14 >= 0 )
    {
      *(_DWORD *)(*(_QWORD *)v13 + 888LL) |= 8u;
      if ( *((_BYTE *)this + 216) )
        *((_BYTE *)this + 216) = 0;
      else
        *(_DWORD *)(*(_QWORD *)v13 + 888LL) &= ~4u;
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_17;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids,
        (unsigned int)v14);
    }
    v12 = WPP_GLOBAL_Control;
    goto LABEL_17;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids,
      (unsigned int)NetworkProfile);
    v12 = WPP_GLOBAL_Control;
  }
  v13 = (char *)this + 192;
LABEL_17:
  if ( v10 )
  {
    operator delete(v10);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v11 < 0 )
  {
    *(_DWORD *)(*(_QWORD *)v13 + 8LL) = v11;
    SendMessageW(*((HWND *)this + 20), 0x465u, 0xFFFFFFFFFFFFFFFFuLL, *(_QWORD *)v13 + 892LL);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v12 != (_BYTE *)&WPP_GLOBAL_Control && (v11 < 0 || v12[25] >= 6u) )
  {
    v15 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v16 + 16), 29, (unsigned int)WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, v15, v11);
  }
  return 1;
}

```

## disassembly

```asm
0x180014da0  push    rbx
0x180014da2  push    rbp
0x180014da3  push    rsi
0x180014da4  push    rdi
0x180014da5  push    r12
0x180014da7  push    r14
0x180014da9  sub     rsp, 38h
0x180014dad  mov     rbp, rcx
0x180014db0  mov     [rsp+68h+Block], 0
0x180014db9  mov     r10, cs:WPP_GLOBAL_Control
0x180014dc0  lea     r12, WPP_GLOBAL_Control
0x180014dc7  cmp     r10, r12
0x180014dca  jz      short loc_180014DF5
0x180014dcc  cmp     byte ptr [r10+19h], 6
0x180014dd1  jb      short loc_180014DF5
0x180014dd3  mov     ecx, 1; int
0x180014dd8  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180014ddd  mov     rcx, [r10+10h]
0x180014de1  lea     r8, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x180014de8  mov     edx, 1Ah
0x180014ded  mov     r9, rax
0x180014df0  call    WPP_SF_s
0x180014df5  mov     rdx, [rbp+148h]; HWND
0x180014dfc  call    ?GetSelectedItemHelper@CWcnPageProfileCreateNew@@AEBAIPEAUHWND__@@@Z; CWcnPageProfileCreateNew::GetSelectedItemHelper(HWND__ *)
0x180014e01  mov     rdx, [rbp+158h]; HWND
0x180014e08  lea     rbx, byte_1800369E0
0x180014e0f  mov     eax, eax
0x180014e11  imul    rcx, rax, 1Ch; this
0x180014e15  mov     esi, [rcx+rbx]
0x180014e18  call    ?GetSelectedItemHelper@CWcnPageProfileCreateNew@@AEBAIPEAUHWND__@@@Z; CWcnPageProfileCreateNew::GetSelectedItemHelper(HWND__ *)
0x180014e1d  mov     eax, eax
0x180014e1f  lea     rdi, [rbp+170h]
0x180014e26  imul    rcx, rax, 1Ch
0x180014e2a  mov     r8d, 40h ; '@'; nMaxCount
0x180014e30  mov     rdx, rdi; lpString
0x180014e33  mov     ebx, [rcx+rbx+4]
0x180014e37  mov     rcx, [rbp+128h]; hWnd
0x180014e3e  call    cs:__imp_GetWindowTextW
0x180014e44  mov     rcx, [rbp+0A8h]; hDlg
0x180014e4b  mov     edx, 900h; nIDDlgItem
0x180014e50  call    cs:__imp_GetDlgItem
0x180014e56  xor     r9d, r9d; lParam
0x180014e59  xor     r8d, r8d; wParam
0x180014e5c  mov     rcx, rax; hWnd
0x180014e5f  mov     edx, 0F0h; Msg
0x180014e64  call    cs:__imp_SendMessageW
0x180014e6a  lea     rcx, [rsp+68h+Block]
0x180014e6f  mov     r8d, ebx; unsigned int
0x180014e72  mov     [rsp+68h+var_40], rcx; unsigned __int16 **
0x180014e77  lea     r14, [rbp+1F0h]
0x180014e7e  cmp     eax, 1
0x180014e81  mov     r9, r14; unsigned __int16 *
0x180014e84  mov     edx, esi; unsigned int
0x180014e86  mov     rcx, rdi; unsigned __int16 *
0x180014e89  setz    al
0x180014e8c  mov     [rbp+169h], al
0x180014e92  mov     [rsp+68h+var_48], al; bool
0x180014e96  call    ?WcnWlanGenerateNetworkProfile@@YAJPEBGII0_NPEAPEAG@Z; WcnWlanGenerateNetworkProfile(ushort const *,uint,uint,ushort const *,bool,ushort * *)
0x180014e9b  mov     rsi, [rsp+68h+Block]
0x180014ea0  mov     edi, eax
0x180014ea2  test    eax, eax
0x180014ea4  jns     short loc_180014EE1
0x180014ea6  mov     r10, cs:WPP_GLOBAL_Control
0x180014ead  cmp     r10, r12
0x180014eb0  jz      short loc_180014ED8
0x180014eb2  cmp     byte ptr [r10+19h], 2
0x180014eb7  jb      short loc_180014ED8
0x180014eb9  mov     rcx, [r10+10h]
0x180014ebd  lea     r8, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x180014ec4  mov     edx, 1Bh
0x180014ec9  mov     r9d, eax
0x180014ecc  call    WPP_SF_d
0x180014ed1  mov     r10, cs:WPP_GLOBAL_Control
0x180014ed8  lea     rbx, [rbp+0C0h]
0x180014edf  jmp     short loc_180014F56
0x180014ee1  lea     rbx, [rbp+0C0h]
0x180014ee8  mov     r8, r14; unsigned __int16 *
0x180014eeb  mov     rcx, [rbx]; this
0x180014eee  mov     rdx, rsi; unsigned __int16 *
0x180014ef1  call    ?SetProfile@tagWCNWIZ_DATA@@QEAAJPEBG0@Z; tagWCNWIZ_DATA::SetProfile(ushort const *,ushort const *)
0x180014ef6  mov     edi, eax
0x180014ef8  test    eax, eax
0x180014efa  jns     short loc_180014F29
0x180014efc  mov     r10, cs:WPP_GLOBAL_Control
0x180014f03  cmp     r10, r12
0x180014f06  jz      short loc_180014F56
0x180014f08  cmp     byte ptr [r10+19h], 2
0x180014f0d  jb      short loc_180014F56
0x180014f0f  mov     rcx, [r10+10h]
0x180014f13  lea     r8, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x180014f1a  mov     edx, 1Ch
0x180014f1f  mov     r9d, eax
0x180014f22  call    WPP_SF_d
0x180014f27  jmp     short loc_180014F4F
0x180014f29  mov     rax, [rbx]
0x180014f2c  or      dword ptr [rax+378h], 8
0x180014f33  cmp     byte ptr [rbp+0D8h], 0
0x180014f3a  jz      short loc_180014F45
0x180014f3c  mov     byte ptr [rbp+0D8h], 0
0x180014f43  jmp     short loc_180014F4F
0x180014f45  mov     rax, [rbx]
0x180014f48  and     dword ptr [rax+378h], 0FFFFFFFBh
0x180014f4f  mov     r10, cs:WPP_GLOBAL_Control
0x180014f56  test    rsi, rsi
0x180014f59  jz      short loc_180014F6A
0x180014f5b  mov     rcx, rsi; Block
0x180014f5e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014f63  mov     r10, cs:WPP_GLOBAL_Control
0x180014f6a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180014f6e  test    edi, edi
0x180014f70  jns     short loc_180014F9E
0x180014f72  mov     rax, [rbx]
0x180014f75  mov     r8, rsi; wParam
0x180014f78  mov     edx, 465h; Msg
0x180014f7d  mov     [rax+8], edi
0x180014f80  mov     r9, [rbx]
0x180014f83  mov     rcx, [rbp+0A0h]; hWnd
0x180014f8a  add     r9, 37Ch; lParam
0x180014f91  call    cs:__imp_SendMessageW
0x180014f97  mov     r10, cs:WPP_GLOBAL_Control
0x180014f9e  cmp     r10, r12
0x180014fa1  jz      short loc_180014FD1
0x180014fa3  test    edi, edi
0x180014fa5  js      short loc_180014FAE
0x180014fa7  cmp     byte ptr [r10+19h], 6
0x180014fac  jb      short loc_180014FD1
0x180014fae  mov     ecx, esi; int
0x180014fb0  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180014fb5  mov     rcx, [r10+10h]
0x180014fb9  lea     r8, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x180014fc0  mov     edx, 1Dh
0x180014fc5  mov     dword ptr [rsp+68h+var_48], edi
0x180014fc9  mov     r9, rax
0x180014fcc  call    WPP_SF_sd
0x180014fd1  mov     al, 1
0x180014fd3  add     rsp, 38h
0x180014fd7  pop     r14
0x180014fd9  pop     r12
0x180014fdb  pop     rdi
0x180014fdc  pop     rsi
0x180014fdd  pop     rbp
0x180014fde  pop     rbx
0x180014fdf  retn
```
