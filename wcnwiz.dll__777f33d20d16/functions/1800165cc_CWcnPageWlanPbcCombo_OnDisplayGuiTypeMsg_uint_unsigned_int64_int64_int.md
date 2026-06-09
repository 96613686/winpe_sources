# CWcnPageWlanPbcCombo::OnDisplayGuiTypeMsg(uint,unsigned __int64,__int64,int &)

- ea: `0x1800165cc`
- end: `0x180016800`
- name: `?OnDisplayGuiTypeMsg@CWcnPageWlanPbcCombo@@QEAA_JI_K_JAEAH@Z`
- size: `564`
- prototype: `__int64 __fastcall(CWcnPageWlanPbcCombo *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000bf80`

## callees

- `0x18000d630`
- `0x18000e19c`
- `0x18000fc10`
- `0x1800165cc`
- `0x1800172f8`
- `0x1800173e8`
- `0x1800279ac`
- `0x18002de1c`
- `0x180031010`

## import_xrefs

- `USER32!PostMessageW` at `0x1800166f2`
- `USER32!PostMessageW` at `0x1800166f2`
- `USER32!KillTimer` at `0x180016782`
- `USER32!KillTimer` at `0x180016782`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180016712`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180016770`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180016712`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180016770`

## pseudocode

```c
__int64 __fastcall CWcnPageWlanPbcCombo::OnDisplayGuiTypeMsg(
        CWcnPageWlanPbcCombo *this,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4)
{
  int v4; // edi
  const char *Indent; // rax
  __int64 v7; // r10
  int v8; // esi
  int v9; // ebp
  int v10; // edi
  int v11; // edi
  int v12; // edi
  int v13; // edi
  int v14; // edi
  int NetworkSignatureForProfile; // eax
  HWND *Parent; // rax
  DirectUI::Element *v17; // rcx
  int v18; // edi
  const char *v19; // rax
  __int64 v20; // r10
  __int64 v22; // [rsp+68h] [rbp+20h] BYREF

  v22 = a4;
  v4 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v7 + 16), 21, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids, Indent);
  }
  if ( !*((_BYTE *)this + 506) )
  {
    v8 = 0;
    v9 = 0;
    *((_BYTE *)this + 508) = v4 == 3;
    if ( v4 )
    {
      v10 = v4 - 1;
      if ( !v10 )
        return 0;
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( v14 )
            {
              if ( v14 != 1 )
                return 0;
              NetworkSignatureForProfile = WcnWlanCreateNetworkSignatureForProfile(
                                             (const struct _DOT11_SSID *)(*((_QWORD *)this + 45) + 168LL),
                                             a2,
                                             a3,
                                             (const struct _GUID *)(*((_QWORD *)this + 45) + 152LL),
                                             *(struct _GUID **)(*((_QWORD *)this + 45) + 208LL));
              if ( NetworkSignatureForProfile < 0
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  32,
                  WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids,
                  (unsigned int)NetworkSignatureForProfile);
              }
              Parent = (HWND *)ATL::CWindow::GetParent((char *)this + 152, &v22);
              PostMessageW(*Parent, 0x471u, 1u, 0);
              goto LABEL_29;
            }
            v17 = (DirectUI::Element *)*((_QWORD *)this + 71);
            v18 = 808;
            *((_BYTE *)this + 511) = 1;
            DirectUI::Element::SetEnabled(v17, 1);
          }
          else
          {
            if ( *((_BYTE *)this + 509) )
            {
              v18 = 809;
              v9 = 810;
            }
            else
            {
              v18 = 0;
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 69) + 8LL))(*((_QWORD *)this + 69));
            }
            *((_BYTE *)this + 510) = 1;
            if ( !v18 )
              goto LABEL_29;
          }
        }
        else
        {
          if ( CWcnPageWlanPbcCombo::_ReadPassword(this) )
            *((_BYTE *)this + 509) = 1;
          else
            DirectUI::Element::SetEnabled(*((DirectUI::Element **)this + 71), 0);
          KillTimer(*((HWND *)this + 19), 0x264369Au);
          v18 = 807;
          v8 = 10815;
        }
      }
      else
      {
        v18 = 806;
        v8 = 10801;
      }
      *((_DWORD *)this + 132) = v18;
      *((_DWORD *)this + 133) = v8;
      *((_DWORD *)this + 134) = v9;
    }
LABEL_29:
    CWcnPageWlanPbcCombo::_UpdateDisabledWidgets(this);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v19 = GetIndent(-1);
      WPP_SF_s(*(_QWORD *)(v20 + 16), 22, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids, v19);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800165cc  mov     [rsp+arg_0], rbx
0x1800165d1  mov     [rsp+arg_8], rbp
0x1800165d6  mov     [rsp+arg_18], r9
0x1800165db  push    rsi
0x1800165dc  push    rdi
0x1800165dd  push    r15
0x1800165df  sub     rsp, 30h
0x1800165e3  mov     rdi, r8
0x1800165e6  mov     rbx, rcx
0x1800165e9  mov     r10, cs:WPP_GLOBAL_Control
0x1800165f0  lea     r15, WPP_GLOBAL_Control
0x1800165f7  cmp     r10, r15
0x1800165fa  jz      short loc_180016625
0x1800165fc  cmp     byte ptr [r10+19h], 6
0x180016601  jb      short loc_180016625
0x180016603  mov     ecx, 1; int
0x180016608  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001660d  mov     rcx, [r10+10h]
0x180016611  lea     r8, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids
0x180016618  mov     edx, 15h
0x18001661d  mov     r9, rax
0x180016620  call    WPP_SF_s
0x180016625  cmp     byte ptr [rbx+1FAh], 0
0x18001662c  jnz     loc_1800167EB
0x180016632  xor     esi, esi
0x180016634  xor     ebp, ebp
0x180016636  cmp     edi, 3
0x180016639  setz    al
0x18001663c  mov     [rbx+1FCh], al
0x180016642  test    edi, edi
0x180016644  jz      loc_1800167B0
0x18001664a  sub     edi, 1
0x18001664d  jz      loc_1800167EB
0x180016653  sub     edi, 1
0x180016656  jz      loc_180016794
0x18001665c  sub     edi, 1
0x18001665f  jz      loc_180016752
0x180016665  sub     edi, 1
0x180016668  jz      loc_18001671D
0x18001666e  sub     edi, 1
0x180016671  jz      loc_1800166FD
0x180016677  cmp     edi, 1
0x18001667a  jnz     loc_1800167EB
0x180016680  mov     rax, [rbx+168h]
0x180016687  lea     r9, [rax+98h]; struct _GUID *
0x18001668e  lea     rcx, [rax+0A8h]; struct _DOT11_SSID *
0x180016695  mov     rax, [rax+0D0h]
0x18001669c  mov     [rsp+48h+var_28], rax; struct _GUID *
0x1800166a1  call    ?WcnWlanCreateNetworkSignatureForProfile@@YAJPEBU_DOT11_SSID@@PEBG_NPEBU_GUID@@PEAU2@@Z; WcnWlanCreateNetworkSignatureForProfile(_DOT11_SSID const *,ushort const *,bool,_GUID const *,_GUID *)
0x1800166a6  test    eax, eax
0x1800166a8  jns     short loc_1800166D2
0x1800166aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166b1  cmp     rcx, r15
0x1800166b4  jz      short loc_1800166D2
0x1800166b6  cmp     byte ptr [rcx+19h], 2
0x1800166ba  jb      short loc_1800166D2
0x1800166bc  mov     rcx, [rcx+10h]
0x1800166c0  lea     edx, [rsi+20h]
0x1800166c3  mov     r9d, eax
0x1800166c6  lea     r8, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids
0x1800166cd  call    WPP_SF_d
0x1800166d2  lea     rcx, [rbx+98h]
0x1800166d9  lea     rdx, [rsp+48h+arg_18]
0x1800166de  call    ?GetParent@CWindow@ATL@@QEBA?AV12@XZ; ATL::CWindow::GetParent(void)
0x1800166e3  xor     r9d, r9d; lParam
0x1800166e6  mov     edx, 471h; Msg
0x1800166eb  mov     rcx, [rax]; hWnd
0x1800166ee  lea     r8d, [r9+1]; wParam
0x1800166f2  call    cs:__imp_PostMessageW
0x1800166f8  jmp     loc_1800167B0
0x1800166fd  mov     rcx, [rbx+238h]
0x180016704  mov     dl, 1
0x180016706  mov     edi, 328h
0x18001670b  mov     byte ptr [rbx+1FFh], 1
0x180016712  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180016718  jmp     loc_18001679E
0x18001671d  cmp     [rbx+1FDh], sil
0x180016724  jnz     short loc_18001673D
0x180016726  mov     rcx, [rbx+228h]
0x18001672d  xor     edi, edi
0x18001672f  mov     rax, [rcx]
0x180016732  mov     rax, [rax+8]
0x180016736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001673b  jmp     short loc_180016745
0x18001673d  mov     edi, 329h
0x180016742  lea     ebp, [rdi+1]
0x180016745  mov     byte ptr [rbx+1FEh], 1
0x18001674c  test    edi, edi
0x18001674e  jz      short loc_1800167B0
0x180016750  jmp     short loc_18001679E
0x180016752  mov     rcx, rbx; this
0x180016755  call    ?_ReadPassword@CWcnPageWlanPbcCombo@@AEAA_NXZ; CWcnPageWlanPbcCombo::_ReadPassword(void)
0x18001675a  test    al, al
0x18001675c  jz      short loc_180016767
0x18001675e  mov     byte ptr [rbx+1FDh], 1
0x180016765  jmp     short loc_180016776
0x180016767  mov     rcx, [rbx+238h]
0x18001676e  xor     edx, edx
0x180016770  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180016776  mov     rcx, [rbx+98h]; hWnd
0x18001677d  mov     edx, 264369Ah; uIDEvent
0x180016782  call    cs:__imp_KillTimer
0x180016788  mov     edi, 327h
0x18001678d  mov     esi, 2A3Fh
0x180016792  jmp     short loc_18001679E
0x180016794  mov     edi, 326h
0x180016799  mov     esi, 2A31h
0x18001679e  mov     [rbx+210h], edi
0x1800167a4  mov     [rbx+214h], esi
0x1800167aa  mov     [rbx+218h], ebp
0x1800167b0  mov     rcx, rbx; this
0x1800167b3  call    ?_UpdateDisabledWidgets@CWcnPageWlanPbcCombo@@AEAAXXZ; CWcnPageWlanPbcCombo::_UpdateDisabledWidgets(void)
0x1800167b8  mov     r10, cs:WPP_GLOBAL_Control
0x1800167bf  cmp     r10, r15
0x1800167c2  jz      short loc_1800167EB
0x1800167c4  cmp     byte ptr [r10+19h], 6
0x1800167c9  jb      short loc_1800167EB
0x1800167cb  or      ecx, 0FFFFFFFFh; int
0x1800167ce  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800167d3  mov     rcx, [r10+10h]
0x1800167d7  lea     r8, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids
0x1800167de  mov     edx, 16h
0x1800167e3  mov     r9, rax
0x1800167e6  call    WPP_SF_s
0x1800167eb  mov     rbx, [rsp+48h+arg_0]
0x1800167f0  xor     eax, eax
0x1800167f2  mov     rbp, [rsp+48h+arg_8]
0x1800167f7  add     rsp, 30h
0x1800167fb  pop     r15
0x1800167fd  pop     rdi
0x1800167fe  pop     rsi
0x1800167ff  retn
```
