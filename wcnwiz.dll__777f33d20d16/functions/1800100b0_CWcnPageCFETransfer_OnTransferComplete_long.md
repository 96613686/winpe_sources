# CWcnPageCFETransfer::OnTransferComplete(long)

- ea: `0x1800100b0`
- end: `0x18001037e`
- name: `?OnTransferComplete@CWcnPageCFETransfer@@QEAAXJ@Z`
- size: `718`
- prototype: `void __fastcall(CWcnPageCFETransfer *__hidden this, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001d130`
- `0x18001d210`

## callees

- `0x180003abc`
- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x18000fc10`
- `0x1800100b0`
- `0x18001044c`
- `0x1800279ac`
- `0x180028b30`
- `0x18002de1c`
- `0x180031010`

## import_xrefs

- `USER32!PostMessageW` at `0x18001032d`
- `USER32!PostMessageW` at `0x18001032d`
- `USER32!SendMessageW` at `0x180010305`
- `USER32!SendMessageW` at `0x180010305`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWcnPageCFETransfer::OnTransferComplete(CWcnPageCFETransfer *this, int a2)
{
  _BYTE *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  unsigned int v7; // eax
  __int64 v8; // r10
  char *v9; // rdi
  const char *v10; // rax
  __int64 v11; // r10
  int NetworkSignatureForProfile; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // r10
  int v17; // eax
  const unsigned __int16 *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rbx
  HWND *v21; // rax
  HWND *Parent; // rax
  const char *v23; // rax
  __int64 v24; // r10
  __int64 v25; // [rsp+70h] [rbp+18h] BYREF
  char v26; // [rsp+78h] [rbp+20h] BYREF

  v25 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 19, WPP_34b38f0394953bd436a7d3abf2cefb9a_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a2 < 0 )
  {
    if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && v4[25] >= 2u )
    {
      v7 = (unsigned int)GetIndent(0);
      WPP_SF_sd(*(_QWORD *)(v8 + 16), 20, (unsigned int)WPP_34b38f0394953bd436a7d3abf2cefb9a_Traceguids, v7, a2);
    }
    v9 = (char *)this + 360;
    goto LABEL_32;
  }
  if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && v4[25] >= 4u )
  {
    v10 = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 21, WPP_34b38f0394953bd436a7d3abf2cefb9a_Traceguids, v10);
  }
  v9 = (char *)this + 360;
  *(_DWORD *)(*((_QWORD *)this + 45) + 8LL) = a2;
  NetworkSignatureForProfile = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(*((_QWORD *)this + 45) + 32LL))(
                                 *(_QWORD *)(*((_QWORD *)this + 45) + 32LL),
                                 &GUID_c100bebd_d33a_4a4b_bf23_bbef4663d017,
                                 &v25);
  a2 = NetworkSignatureForProfile;
  if ( NetworkSignatureForProfile < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_32;
    v14 = 22;
    goto LABEL_31;
  }
  NetworkSignatureForProfile = (*(__int64 (__fastcall **)(__int64, __int64, __int64, WCHAR *))(*(_QWORD *)v25 + 24LL))(
                                 v25,
                                 1,
                                 2096,
                                 &strProfileXml);
  a2 = NetworkSignatureForProfile;
  if ( NetworkSignatureForProfile < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_32;
    v14 = 23;
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v15 = (unsigned int)GetIndent(0);
    WPP_SF_sS(
      *(_QWORD *)(v16 + 16),
      24,
      (unsigned int)WPP_34b38f0394953bd436a7d3abf2cefb9a_Traceguids,
      v15,
      (__int64)&strProfileXml);
  }
  v17 = WcnNetworkProfileSave(&strProfileXml, (struct _GUID *)(*(_QWORD *)v9 + 152LL));
  if ( v17 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      WPP_34b38f0394953bd436a7d3abf2cefb9a_Traceguids,
      (unsigned int)v17);
  NetworkSignatureForProfile = WcnWlanCreateNetworkSignatureForProfile(
                                 (const struct _DOT11_SSID *)(*(_QWORD *)v9 + 168LL),
                                 v18,
                                 v19,
                                 (const struct _GUID *)(*(_QWORD *)v9 + 152LL),
                                 *(struct _GUID **)(*(_QWORD *)v9 + 208LL));
  a2 = NetworkSignatureForProfile;
  if ( NetworkSignatureForProfile >= 0 )
  {
    Parent = (HWND *)ATL::CWindow::GetParent((char *)this + 152, &v26);
    PostMessageW(*Parent, 0x471u, 1u, 0);
    goto LABEL_34;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = 26;
LABEL_31:
    WPP_SF_d(v13[2], v14, WPP_34b38f0394953bd436a7d3abf2cefb9a_Traceguids, (unsigned int)NetworkSignatureForProfile);
  }
LABEL_32:
  *(_DWORD *)(*(_QWORD *)v9 + 8LL) = a2;
  v20 = *(_QWORD *)v9;
  v21 = (HWND *)ATL::CWindow::GetParent((char *)this + 152, &v26);
  SendMessageW(*v21, 0x465u, 0xFFFFFFFFFFFFFFFFuLL, v20 + 892);
LABEL_34:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v23 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v24 + 16), 27, WPP_34b38f0394953bd436a7d3abf2cefb9a_Traceguids, v23);
  }
  ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(&v25);
}

```

## disassembly

```asm
0x1800100b0  mov     [rsp+arg_0], rbx
0x1800100b5  push    rbp
0x1800100b6  push    rsi
0x1800100b7  push    rdi
0x1800100b8  push    r14
0x1800100ba  push    r15
0x1800100bc  sub     rsp, 30h
0x1800100c0  mov     ebx, edx
0x1800100c2  mov     rsi, rcx
0x1800100c5  mov     [rsp+58h+arg_10], 0
0x1800100ce  lea     rbp, WPP_GLOBAL_Control
0x1800100d5  lea     r14, WPP_34b38f0394953bd436a7d3abf2cefb9a_Traceguids
0x1800100dc  mov     r10, cs:WPP_GLOBAL_Control
0x1800100e3  cmp     r10, rbp
0x1800100e6  jz      short loc_180010114
0x1800100e8  cmp     byte ptr [r10+19h], 6
0x1800100ed  jb      short loc_180010114
0x1800100ef  mov     ecx, 1; int
0x1800100f4  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800100f9  mov     edx, 13h
0x1800100fe  mov     r9, rax
0x180010101  mov     r8, r14
0x180010104  mov     rcx, [r10+10h]
0x180010108  call    WPP_SF_s
0x18001010d  mov     r10, cs:WPP_GLOBAL_Control
0x180010114  test    ebx, ebx
0x180010116  jns     short loc_18001014F
0x180010118  cmp     r10, rbp
0x18001011b  jz      short loc_180010143
0x18001011d  cmp     byte ptr [r10+19h], 2
0x180010122  jb      short loc_180010143
0x180010124  xor     ecx, ecx; int
0x180010126  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001012b  mov     edx, 14h
0x180010130  mov     dword ptr [rsp+58h+var_38], ebx
0x180010134  mov     r9, rax
0x180010137  mov     r8, r14
0x18001013a  mov     rcx, [r10+10h]
0x18001013e  call    WPP_SF_sd
0x180010143  lea     rdi, [rsi+168h]
0x18001014a  jmp     loc_1800102D8
0x18001014f  cmp     r10, rbp
0x180010152  jz      short loc_180010176
0x180010154  cmp     byte ptr [r10+19h], 4
0x180010159  jb      short loc_180010176
0x18001015b  xor     ecx, ecx; int
0x18001015d  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180010162  mov     edx, 15h
0x180010167  mov     r9, rax
0x18001016a  mov     r8, r14
0x18001016d  mov     rcx, [r10+10h]
0x180010171  call    WPP_SF_s
0x180010176  lea     rdi, [rsi+168h]
0x18001017d  mov     rax, [rdi]
0x180010180  mov     [rax+8], ebx
0x180010183  mov     rax, [rdi]
0x180010186  mov     rcx, [rax+20h]
0x18001018a  mov     rax, [rcx]
0x18001018d  lea     r8, [rsp+58h+arg_10]
0x180010192  lea     rdx, _GUID_c100bebd_d33a_4a4b_bf23_bbef4663d017
0x180010199  mov     rax, [rax]
0x18001019c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101a1  mov     ebx, eax
0x1800101a3  test    eax, eax
0x1800101a5  jns     short loc_1800101CB
0x1800101a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101ae  cmp     rcx, rbp
0x1800101b1  jz      loc_1800102D8
0x1800101b7  cmp     byte ptr [rcx+19h], 2
0x1800101bb  jb      loc_1800102D8
0x1800101c1  mov     edx, 16h
0x1800101c6  jmp     loc_1800102C9
0x1800101cb  mov     rcx, [rsp+58h+arg_10]
0x1800101d0  mov     rax, [rcx]
0x1800101d3  lea     r15, strProfileXml
0x1800101da  mov     r9, r15
0x1800101dd  mov     edx, 1
0x1800101e2  mov     r8d, 830h
0x1800101e8  mov     rax, [rax+18h]
0x1800101ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101f1  mov     ebx, eax
0x1800101f3  test    eax, eax
0x1800101f5  jns     short loc_18001021B
0x1800101f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101fe  cmp     rcx, rbp
0x180010201  jz      loc_1800102D8
0x180010207  cmp     byte ptr [rcx+19h], 2
0x18001020b  jb      loc_1800102D8
0x180010211  mov     edx, 17h
0x180010216  jmp     loc_1800102C9
0x18001021b  mov     r10, cs:WPP_GLOBAL_Control
0x180010222  cmp     r10, rbp
0x180010225  jz      short loc_18001024E
0x180010227  cmp     byte ptr [r10+19h], 4
0x18001022c  jb      short loc_18001024E
0x18001022e  xor     ecx, ecx; int
0x180010230  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180010235  mov     edx, 18h
0x18001023a  mov     [rsp+58h+var_38], r15
0x18001023f  mov     r9, rax
0x180010242  mov     r8, r14
0x180010245  mov     rcx, [r10+10h]
0x180010249  call    WPP_SF_sS
0x18001024e  mov     rdx, [rdi]
0x180010251  add     rdx, 98h; struct _GUID *
0x180010258  mov     rcx, r15; strProfileXml
0x18001025b  call    ?WcnNetworkProfileSave@@YAJPEBGPEAU_GUID@@@Z; WcnNetworkProfileSave(ushort const *,_GUID *)
0x180010260  test    eax, eax
0x180010262  jns     short loc_18001028A
0x180010264  mov     rcx, cs:WPP_GLOBAL_Control
0x18001026b  cmp     rcx, rbp
0x18001026e  jz      short loc_18001028A
0x180010270  cmp     byte ptr [rcx+19h], 3
0x180010274  jb      short loc_18001028A
0x180010276  mov     edx, 19h
0x18001027b  mov     r9d, eax
0x18001027e  mov     r8, r14
0x180010281  mov     rcx, [rcx+10h]
0x180010285  call    WPP_SF_d
0x18001028a  mov     rax, [rdi]
0x18001028d  lea     r9, [rax+98h]; struct _GUID *
0x180010294  lea     rcx, [rax+0A8h]; struct _DOT11_SSID *
0x18001029b  mov     rax, [rax+0D0h]
0x1800102a2  mov     [rsp+58h+var_38], rax; struct _GUID *
0x1800102a7  call    ?WcnWlanCreateNetworkSignatureForProfile@@YAJPEBU_DOT11_SSID@@PEBG_NPEBU_GUID@@PEAU2@@Z; WcnWlanCreateNetworkSignatureForProfile(_DOT11_SSID const *,ushort const *,bool,_GUID const *,_GUID *)
0x1800102ac  mov     ebx, eax
0x1800102ae  test    eax, eax
0x1800102b0  jns     short loc_18001030D
0x1800102b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102b9  cmp     rcx, rbp
0x1800102bc  jz      short loc_1800102D8
0x1800102be  cmp     byte ptr [rcx+19h], 2
0x1800102c2  jb      short loc_1800102D8
0x1800102c4  mov     edx, 1Ah
0x1800102c9  mov     r9d, eax
0x1800102cc  mov     r8, r14
0x1800102cf  mov     rcx, [rcx+10h]
0x1800102d3  call    WPP_SF_d
0x1800102d8  lea     rcx, [rsi+98h]
0x1800102df  mov     rax, [rdi]
0x1800102e2  mov     [rax+8], ebx
0x1800102e5  mov     rbx, [rdi]
0x1800102e8  lea     rdx, [rsp+58h+arg_18]
0x1800102ed  call    ?GetParent@CWindow@ATL@@QEBA?AV12@XZ; ATL::CWindow::GetParent(void)
0x1800102f2  lea     r9, [rbx+37Ch]; lParam
0x1800102f9  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x1800102fd  mov     edx, 465h; Msg
0x180010302  mov     rcx, [rax]; hWnd
0x180010305  call    cs:__imp_SendMessageW
0x18001030b  jmp     short loc_180010333
0x18001030d  lea     rcx, [rsi+98h]
0x180010314  lea     rdx, [rsp+58h+arg_18]
0x180010319  call    ?GetParent@CWindow@ATL@@QEBA?AV12@XZ; ATL::CWindow::GetParent(void)
0x18001031e  xor     r9d, r9d; lParam
0x180010321  mov     edx, 471h; Msg
0x180010326  lea     r8d, [r9+1]; wParam
0x18001032a  mov     rcx, [rax]; hWnd
0x18001032d  call    cs:__imp_PostMessageW
0x180010333  mov     r10, cs:WPP_GLOBAL_Control
0x18001033a  cmp     r10, rbp
0x18001033d  jz      short loc_180010363
0x18001033f  cmp     byte ptr [r10+19h], 6
0x180010344  jb      short loc_180010363
0x180010346  or      ecx, 0FFFFFFFFh; int
0x180010349  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001034e  mov     edx, 1Bh
0x180010353  mov     r9, rax
0x180010356  mov     r8, r14
0x180010359  mov     rcx, [r10+10h]
0x18001035d  call    WPP_SF_s
0x180010362  nop
0x180010363  lea     rcx, [rsp+58h+arg_10]
0x180010368  call    ??1?$CComPtrBase@UIWCNDevicePrivate@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(void)
0x18001036d  mov     rbx, [rsp+58h+arg_0]
0x180010372  add     rsp, 30h
0x180010376  pop     r15
0x180010378  pop     r14
0x18001037a  pop     rdi
0x18001037b  pop     rsi
0x18001037c  pop     rbp
0x18001037d  retn
```
