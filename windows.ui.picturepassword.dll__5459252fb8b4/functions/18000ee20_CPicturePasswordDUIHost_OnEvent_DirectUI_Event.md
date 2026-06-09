# CPicturePasswordDUIHost::OnEvent(DirectUI::Event *)

- ea: `0x18000ee20`
- end: `0x18000f39b`
- name: `?OnEvent@CPicturePasswordDUIHost@@UEAAXPEAUEvent@DirectUI@@@Z`
- size: `1403`
- prototype: `void __fastcall(CPicturePasswordDUIHost *__hidden this, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1800043a4`
- `0x180007dfc`
- `0x18000cbb0`
- `0x18000d404`
- `0x18000e334`
- `0x18000ee20`
- `0x180010d04`
- `0x1800119ec`
- `0x180011b3c`
- `0x180011b74`
- `0x180011e88`
- `0x180012d7c`
- `0x1800189c4`
- `0x18001f010`

## import_xrefs

- `SHCORE!__imp_SHQueueUserWorkItem` at `0x18000f11f`
- `SHCORE!__imp_SHQueueUserWorkItem` at `0x18000f11f`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x18000f297`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x18000f297`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000efc7`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000efc7`
- `DUI70!?GetXOffset@BaseScrollViewer@DirectUI@@QEAAHXZ` at `0x18000f2a3`
- `DUI70!?GetXOffset@BaseScrollViewer@DirectUI@@QEAAHXZ` at `0x18000f2a3`
- `DUI70!?GetYOffset@BaseScrollViewer@DirectUI@@QEAAHXZ` at `0x18000f2b4`
- `DUI70!?GetYOffset@BaseScrollViewer@DirectUI@@QEAAHXZ` at `0x18000f2b4`
- `DUI70!?TriggeredAnimationComplete@PVLAnimation@DirectUI@@SA?AVUID@@XZ` at `0x18000f304`
- `DUI70!?OnEvent@TouchHWNDElement@DirectUI@@UEAAXPEAUEvent@2@@Z` at `0x18000f394`
- `DUI70!?ManipulationCompleted@TouchScrollViewer@DirectUI@@SA?AVUID@@XZ` at `0x18000f215`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000f247`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000f263`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000f247`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000f263`
- `DUI70!StrToID` at `0x18000f23b`
- `DUI70!StrToID` at `0x18000f257`
- `DUI70!StrToID` at `0x18000f23b`
- `DUI70!StrToID` at `0x18000f257`
- `DUI70!?Click@TouchButton@DirectUI@@SA?AVUID@@XZ` at `0x18000ee4d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x18000f1f0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x18000f1f0`

## pseudocode

```c
void __fastcall CPicturePasswordDUIHost::OnEvent(CPicturePasswordDUIHost *this, struct DirectUI::Event *a2)
{
  char *v2; // rbx
  struct DirectUI::Element *PageElement; // rbx
  struct DirectUI::Element *v6; // rsi
  struct DirectUI::Element *v7; // r14
  struct DirectUI::Element *v8; // r15
  DirectUI::Element *v9; // rdi
  CPicturePasswordDUIHost *v10; // rcx
  bool v11; // r8
  unsigned int v12; // edx
  bool v13; // cf
  CPicturePasswordDUIHost *v14; // rcx
  struct IStream *v15; // rbx
  bool v16; // zf
  unsigned __int64 v17; // rbx
  unsigned __int8 *v18; // rdi
  unsigned __int64 v19; // rsi
  struct GESTURE_SIGNATURE *v20; // r14
  struct CPrivateNotificationWindow *v21; // r15
  HWND v22; // rax
  struct CGestureSubmissionJobData *v23; // rbx
  unsigned __int16 v24; // ax
  DirectUI::Element *Descendent; // rbx
  unsigned __int16 v26; // ax
  struct DirectUI::Element *v27; // rax
  DirectUI::BaseScrollViewer *v28; // rdi
  const struct tagSIZE *Extent; // rbx
  int YOffset; // eax
  int v31; // ecx
  bool v32; // r8
  unsigned int v33; // edx
  struct IStream *v34; // [rsp+98h] [rbp+48h] BYREF
  struct CGestureSubmissionJobData *v35; // [rsp+A0h] [rbp+50h] BYREF
  struct DirectUI::Element *v36; // [rsp+A8h] [rbp+58h]

  v2 = (char *)a2 + 8;
  if ( *((_DWORD *)a2 + 5) == 2
    && (v34 = (struct IStream *)DirectUI::TouchButton::Click, (unsigned __int8)operator==(v2, &v34)) )
  {
    PageElement = CPicturePasswordDUIHost::_GetPageElement(this, L"selectBgButton");
    v6 = CPicturePasswordDUIHost::_GetPageElement(this, L"reselectBgButton");
    v7 = CPicturePasswordDUIHost::_GetPageElement(this, L"acceptBgButton");
    v8 = CPicturePasswordDUIHost::_GetPageElement(this, L"reviewButton");
    v34 = CPicturePasswordDUIHost::_GetPageElement(this, L"startOverButton");
    v9 = CPicturePasswordDUIHost::_GetPageElement(this, L"okButton");
    v35 = CPicturePasswordDUIHost::_GetPageElement(this, L"cancelButton");
    v36 = CPicturePasswordDUIHost::_GetPageElement(this, L"tryAgainButton");
    v10 = CPicturePasswordDUIHost::_GetPageElement(this, L"syncedBgButton");
    if ( *(struct DirectUI::Element **)a2 == PageElement || *(struct DirectUI::Element **)a2 == v6 )
    {
      CPicturePasswordDUIHost::_InvokePicker(this);
      goto LABEL_39;
    }
    if ( *(struct DirectUI::Element **)a2 == v7 )
    {
      CPrivateNotificationWindow::PostNotification(*((CPrivateNotificationWindow **)this + 91), 0x403u, 0, 0);
LABEL_39:
      *((_BYTE *)a2 + 16) = 1;
      goto LABEL_51;
    }
    if ( *(struct DirectUI::Element **)a2 == v8 )
    {
      *((_BYTE *)this + 881) = 1;
      v12 = 3;
LABEL_11:
      CPicturePasswordDUIHost::_SwitchToPage((__int64)this, v12, v11);
      goto LABEL_39;
    }
    if ( *(struct IStream **)a2 == v34 )
    {
      _FadeElement(*((struct DirectUI::Element **)this + 107));
      v13 = *((_BYTE *)this + 881) != 0;
      *((_BYTE *)this + 880) = 0;
      v12 = 4 - v13;
      goto LABEL_11;
    }
    if ( *(DirectUI::Element **)a2 == v9 && *((_DWORD *)this + 180) == 6 && !*((_BYTE *)this + 881) )
    {
      DirectUI::Element::SetEnabled(v9, 0);
      if ( *((_BYTE *)this + 865) )
      {
        v34 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v34);
        if ( (int)CPicturePasswordDUIHost::_LoadImage(v14, L"Cloud.jpg", &v34) >= 0 )
        {
          v15 = v34;
          if ( *((struct IStream **)this + 92) != v34 )
          {
            v35 = v34;
            Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream>::InternalAddRef((__int64 *)&v35);
            v35 = (struct CGestureSubmissionJobData *)*((_QWORD *)this + 92);
            *((_QWORD *)this + 92) = v15;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v35);
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v34);
      }
      v16 = *((_BYTE *)this + 864) == 0;
      v35 = 0;
      if ( v16 )
        v34 = 0;
      else
        v34 = (struct IStream *)*((_QWORD *)this + 92);
      v17 = *((_QWORD *)this + 58);
      v18 = (unsigned __int8 *)*((_QWORD *)this + 57);
      v19 = *((_QWORD *)this + 86);
      v20 = (struct GESTURE_SIGNATURE *)*((_QWORD *)this + 85);
      v21 = (struct CPrivateNotificationWindow *)*((_QWORD *)this + 91);
      v22 = (HWND)(*(__int64 (__fastcall **)(CPicturePasswordDUIHost *))(*(_QWORD *)this + 360LL))(this);
      if ( (int)CGestureSubmissionJobData::CreateInstance(
                  v22,
                  v21,
                  v20,
                  v19,
                  v18,
                  v17,
                  v34,
                  (const struct tagRECT *)((char *)this + 744),
                  (const struct tagSIZE *)this + 95,
                  &v35) >= 0 )
      {
        v23 = v35;
        if ( (unsigned int)SHQueueUserWorkItem(
                             CPicturePasswordDUIHost::s_SubmitGestureDataToSystem,
                             v35,
                             0,
                             0,
                             0,
                             0,
                             16) )
          v23 = 0;
        if ( v23 )
          (**(void (__fastcall ***)(struct CGestureSubmissionJobData *, __int64))v23)(v23, 1);
      }
      goto LABEL_39;
    }
    if ( *(struct CGestureSubmissionJobData **)a2 == v35 || *(DirectUI::Element **)a2 == v9 )
    {
      PostMessageW(*((HWND *)this + 109), 0x10u, 0, 0);
      goto LABEL_39;
    }
    if ( *(struct DirectUI::Element **)a2 == v36 )
    {
      CPicturePasswordDUIHost::_SwitchToPage((__int64)this, 3u, v11);
    }
    else if ( *(CPicturePasswordDUIHost **)a2 == v10 )
    {
      v34 = 0;
      if ( (int)CPicturePasswordDUIHost::_LoadImage(v10, L"Sanitized.jpg", &v34) >= 0 )
      {
        if ( CPrivateNotificationWindow::PostNotification(
               *((CPrivateNotificationWindow **)this + 91),
               0x402u,
               0,
               (__int64)v34) )
        {
          *((_BYTE *)this + 865) = 1;
        }
        else
        {
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v34 + 16LL))(v34);
        }
      }
      goto LABEL_39;
    }
  }
  else if ( *((_DWORD *)a2 + 5) == 2
         && (v34 = (struct IStream *)DirectUI::TouchScrollViewer::ManipulationCompleted,
             (unsigned __int8)operator==(v2, &v34)) )
  {
    v24 = StrToID(L"clientPanel");
    Descendent = DirectUI::Element::FindDescendent(this, v24);
    v26 = StrToID(L"bgViewer");
    v27 = DirectUI::Element::FindDescendent(Descendent, v26);
    v28 = (DirectUI::BaseScrollViewer *)element_cast<DirectUI::TouchScrollViewer>((__int64)v27);
    if ( v28 == *(DirectUI::BaseScrollViewer **)a2 && !*((_BYTE *)this + 976) )
    {
      v34 = 0;
      Extent = DirectUI::Element::GetExtent(Descendent, &v34);
      *((_DWORD *)this + 186) = DirectUI::BaseScrollViewer::GetXOffset(v28);
      YOffset = DirectUI::BaseScrollViewer::GetYOffset(v28);
      v31 = *((_DWORD *)this + 186);
      *((_DWORD *)this + 187) = YOffset;
      *((_DWORD *)this + 188) = Extent->cx + v31;
      *((_DWORD *)this + 189) = Extent->cy + YOffset;
      *(_OWORD *)((char *)this + 892) = *(_OWORD *)((char *)this + 744);
      CValuePtr::Release((CValuePtr *)&v34);
    }
  }
  else if ( *((_DWORD *)a2 + 5) == 4 )
  {
    v34 = (struct IStream *)DirectUI::PVLAnimation::TriggeredAnimationComplete;
    if ( (unsigned __int8)operator==(v2, &v34) )
    {
      if ( *((_DWORD *)this + 241) == *((_DWORD *)a2 + 9) )
      {
        *((_BYTE *)this + 960) = 0;
        *((_DWORD *)this + 241) = 0;
        if ( *((_BYTE *)this + 968) )
        {
          v33 = *((_DWORD *)this + 243);
          *((_BYTE *)this + 968) = 0;
          CPicturePasswordDUIHost::_SwitchToPage((__int64)this, v33, v32);
        }
        CPrivateNotificationWindow::PostNotification(*((CPrivateNotificationWindow **)this + 91), 0x40Au, 0, 0);
      }
    }
  }
LABEL_51:
  DirectUI::TouchHWNDElement::OnEvent(this, a2);
}

```

## disassembly

```asm
0x18000ee20  mov     [rsp-38h+arg_0], rbx
0x18000ee25  push    rbp
0x18000ee26  push    rsi
0x18000ee27  push    rdi
0x18000ee28  push    r12
0x18000ee2a  push    r13
0x18000ee2c  push    r14
0x18000ee2e  push    r15
0x18000ee30  mov     rbp, rsp
0x18000ee33  sub     rsp, 50h
0x18000ee37  xor     esi, esi
0x18000ee39  lea     rbx, [rdx+8]
0x18000ee3d  cmp     dword ptr [rdx+14h], 2
0x18000ee41  mov     r13, rdx
0x18000ee44  mov     r12, rcx
0x18000ee47  jnz     loc_18000F20A
0x18000ee4d  mov     rax, cs:__imp_?Click@TouchButton@DirectUI@@SA?AVUID@@XZ; DirectUI::TouchButton::Click(void)
0x18000ee54  lea     rdx, [rbp+arg_8]
0x18000ee58  mov     rcx, rbx
0x18000ee5b  mov     [rbp+arg_8], rax
0x18000ee5f  call    ??8@YA_NAEBVUID@@AEBQ6A?AV0@XZ@Z; operator==(UID const &,UID (*const &)(void))
0x18000ee64  test    al, al
0x18000ee66  jz      loc_18000F20A
0x18000ee6c  lea     rdx, aSelectbgbutton; "selectBgButton"
0x18000ee73  mov     rcx, r12; this
0x18000ee76  call    ?_GetPageElement@CPicturePasswordDUIHost@@IEAAPEAVElement@DirectUI@@PEBG@Z; CPicturePasswordDUIHost::_GetPageElement(ushort const *)
0x18000ee7b  lea     rdx, aReselectbgbutt; "reselectBgButton"
0x18000ee82  mov     rcx, r12; this
0x18000ee85  mov     rbx, rax
0x18000ee88  call    ?_GetPageElement@CPicturePasswordDUIHost@@IEAAPEAVElement@DirectUI@@PEBG@Z; CPicturePasswordDUIHost::_GetPageElement(ushort const *)
0x18000ee8d  lea     rdx, aAcceptbgbutton; "acceptBgButton"
0x18000ee94  mov     rcx, r12; this
0x18000ee97  mov     rsi, rax
0x18000ee9a  call    ?_GetPageElement@CPicturePasswordDUIHost@@IEAAPEAVElement@DirectUI@@PEBG@Z; CPicturePasswordDUIHost::_GetPageElement(ushort const *)
0x18000ee9f  lea     rdx, aReviewbutton; "reviewButton"
0x18000eea6  mov     rcx, r12; this
0x18000eea9  mov     r14, rax
0x18000eeac  call    ?_GetPageElement@CPicturePasswordDUIHost@@IEAAPEAVElement@DirectUI@@PEBG@Z; CPicturePasswordDUIHost::_GetPageElement(ushort const *)
0x18000eeb1  lea     rdx, aStartoverbutto; "startOverButton"
0x18000eeb8  mov     rcx, r12; this
0x18000eebb  mov     r15, rax
0x18000eebe  call    ?_GetPageElement@CPicturePasswordDUIHost@@IEAAPEAVElement@DirectUI@@PEBG@Z; CPicturePasswordDUIHost::_GetPageElement(ushort const *)
0x18000eec3  lea     rdx, aOkbutton; "okButton"
0x18000eeca  mov     [rbp+arg_8], rax
0x18000eece  mov     rcx, r12; this
0x18000eed1  call    ?_GetPageElement@CPicturePasswordDUIHost@@IEAAPEAVElement@DirectUI@@PEBG@Z; CPicturePasswordDUIHost::_GetPageElement(ushort const *)
0x18000eed6  lea     rdx, aCancelbutton; "cancelButton"
0x18000eedd  mov     rcx, r12; this
0x18000eee0  mov     rdi, rax
0x18000eee3  call    ?_GetPageElement@CPicturePasswordDUIHost@@IEAAPEAVElement@DirectUI@@PEBG@Z; CPicturePasswordDUIHost::_GetPageElement(ushort const *)
0x18000eee8  lea     rdx, aTryagainbutton; "tryAgainButton"
0x18000eeef  mov     [rbp+arg_10], rax
0x18000eef3  mov     rcx, r12; this
0x18000eef6  call    ?_GetPageElement@CPicturePasswordDUIHost@@IEAAPEAVElement@DirectUI@@PEBG@Z; CPicturePasswordDUIHost::_GetPageElement(ushort const *)
0x18000eefb  lea     rdx, aSyncedbgbutton; "syncedBgButton"
0x18000ef02  mov     [rbp+arg_18], rax
0x18000ef06  mov     rcx, r12; this
0x18000ef09  call    ?_GetPageElement@CPicturePasswordDUIHost@@IEAAPEAVElement@DirectUI@@PEBG@Z; CPicturePasswordDUIHost::_GetPageElement(ushort const *)
0x18000ef0e  mov     rcx, rax; this
0x18000ef11  cmp     [r13+0], rbx
0x18000ef15  jz      loc_18000F1F8
0x18000ef1b  cmp     [r13+0], rsi
0x18000ef1f  jz      loc_18000F1F8
0x18000ef25  cmp     [r13+0], r14
0x18000ef29  jnz     short loc_18000EF48
0x18000ef2b  mov     rcx, [r12+2D8h]; this
0x18000ef33  xor     r9d, r9d; __int64
0x18000ef36  xor     r8d, r8d; unsigned __int64
0x18000ef39  mov     edx, 403h; unsigned int
0x18000ef3e  call    ?PostNotification@CPrivateNotificationWindow@@QEAA_NI_K_J@Z; CPrivateNotificationWindow::PostNotification(uint,unsigned __int64,__int64)
0x18000ef43  jmp     loc_18000F200
0x18000ef48  cmp     [r13+0], r15
0x18000ef4c  jnz     short loc_18000EF5E
0x18000ef4e  mov     byte ptr [r12+371h], 1
0x18000ef57  mov     edx, 3
0x18000ef5c  jmp     short loc_18000EF8D
0x18000ef5e  mov     rax, [rbp+arg_8]
0x18000ef62  cmp     [r13+0], rax
0x18000ef66  jnz     short loc_18000EF9A
0x18000ef68  mov     rcx, [r12+358h]; struct DirectUI::Element *
0x18000ef70  call    ?_FadeElement@@YAXPEAVElement@DirectUI@@@Z; _FadeElement(DirectUI::Element *)
0x18000ef75  mov     al, [r12+371h]
0x18000ef7d  neg     al
0x18000ef7f  mov     byte ptr [r12+370h], 0
0x18000ef88  sbb     edx, edx
0x18000ef8a  add     edx, 4
0x18000ef8d  mov     rcx, r12
0x18000ef90  call    ?_SwitchToPage@CPicturePasswordDUIHost@@IEAAJW4PICTURE_PASSWORD_ENROLLMENT_PAGE@@@Z; CPicturePasswordDUIHost::_SwitchToPage(PICTURE_PASSWORD_ENROLLMENT_PAGE)
0x18000ef95  jmp     loc_18000F200
0x18000ef9a  cmp     [r13+0], rdi
0x18000ef9e  jnz     loc_18000F14E
0x18000efa4  cmp     dword ptr [r12+2D0h], 6
0x18000efad  jnz     loc_18000F14E
0x18000efb3  cmp     byte ptr [r12+371h], 0
0x18000efbc  jnz     loc_18000F14E
0x18000efc2  xor     edx, edx
0x18000efc4  mov     rcx, rdi
0x18000efc7  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18000efcd  cmp     byte ptr [r12+361h], 0
0x18000efd6  jz      short loc_18000F03E
0x18000efd8  lea     rcx, [rbp+arg_8]
0x18000efdc  mov     [rbp+arg_8], 0
0x18000efe4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000efe9  lea     r8, [rbp+arg_8]; struct IStream **
0x18000efed  lea     rdx, aCloudJpg; "Cloud.jpg"
0x18000eff4  call    ?_LoadImage@CPicturePasswordDUIHost@@IEAAJPEBGPEAPEAUIStream@@@Z; CPicturePasswordDUIHost::_LoadImage(ushort const *,IStream * *)
0x18000eff9  test    eax, eax
0x18000effb  js      short loc_18000F035
0x18000effd  mov     rbx, [rbp+arg_8]
0x18000f001  cmp     [r12+2E0h], rbx
0x18000f009  jz      short loc_18000F035
0x18000f00b  lea     rcx, [rbp+arg_10]
0x18000f00f  mov     [rbp+arg_10], rbx
0x18000f013  call    ?InternalAddRef@?$ComPtr@VCMarshalStream@CMarshaledInterface@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream>::InternalAddRef(void)
0x18000f018  mov     rax, [r12+2E0h]
0x18000f020  lea     rcx, [rbp+arg_10]
0x18000f024  mov     [rbp+arg_10], rax
0x18000f028  mov     [r12+2E0h], rbx
0x18000f030  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f035  lea     rcx, [rbp+arg_8]
0x18000f039  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f03e  cmp     byte ptr [r12+360h], 0
0x18000f047  mov     [rbp+arg_10], 0
0x18000f04f  jz      short loc_18000F05F
0x18000f051  mov     rax, [r12+2E0h]
0x18000f059  mov     [rbp+arg_8], rax
0x18000f05d  jmp     short loc_18000F067
0x18000f05f  mov     [rbp+arg_8], 0
0x18000f067  mov     rax, [r12]
0x18000f06b  mov     rcx, r12
0x18000f06e  mov     rbx, [r12+1D0h]
0x18000f076  mov     rdi, [r12+1C8h]
0x18000f07e  mov     rsi, [r12+2B0h]
0x18000f086  mov     rax, [rax+168h]
0x18000f08d  mov     r14, [r12+2A8h]
0x18000f095  mov     r15, [r12+2D8h]
0x18000f09d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0a2  lea     rdx, [rbp+arg_10]
0x18000f0a6  mov     r9, rsi; unsigned __int64
0x18000f0a9  mov     [rsp+50h+var_8], rdx; struct CGestureSubmissionJobData **
0x18000f0ae  lea     rcx, [r12+2F8h]
0x18000f0b6  mov     [rsp+50h+var_10], rcx; struct tagSIZE *
0x18000f0bb  lea     r10, [r12+2E8h]
0x18000f0c3  mov     rcx, [rbp+arg_8]
0x18000f0c7  mov     r8, r14; struct GESTURE_SIGNATURE *
0x18000f0ca  mov     [rsp+50h+var_18], r10; struct tagRECT *
0x18000f0cf  mov     rdx, r15; struct CPrivateNotificationWindow *
0x18000f0d2  mov     [rsp+50h+var_20], rcx; struct IStream *
0x18000f0d7  mov     rcx, rax; HWND
0x18000f0da  mov     [rsp+50h+var_28], rbx; unsigned __int64
0x18000f0df  mov     [rsp+50h+var_30], rdi; unsigned __int8 *
0x18000f0e4  call    ?CreateInstance@CGestureSubmissionJobData@@SAJPEAUHWND__@@PEAVCPrivateNotificationWindow@@PEAUGESTURE_SIGNATURE@@_KPEAE3PEAUIStream@@AEBUtagRECT@@AEBUtagSIZE@@PEAPEAV1@@Z; CGestureSubmissionJobData::CreateInstance(HWND__ *,CPrivateNotificationWindow *,GESTURE_SIGNATURE *,unsigned __int64,uchar *,unsigned __int64,IStream *,tagRECT const &,tagSIZE const &,CGestureSubmissionJobData * *)
0x18000f0e9  test    eax, eax
0x18000f0eb  js      loc_18000F200
0x18000f0f1  mov     rbx, [rbp+arg_10]
0x18000f0f5  lea     rcx, ?s_SubmitGestureDataToSystem@CPicturePasswordDUIHost@@KAKPEAX@Z; CPicturePasswordDUIHost::s_SubmitGestureDataToSystem(void *)
0x18000f0fc  mov     dword ptr [rsp+50h+var_20], 10h
0x18000f104  mov     rdx, rbx
0x18000f107  mov     [rsp+50h+var_28], 0
0x18000f110  xor     r9d, r9d
0x18000f113  xor     r8d, r8d
0x18000f116  mov     [rsp+50h+var_30], 0
0x18000f11f  call    cs:__imp_SHQueueUserWorkItem
0x18000f125  xor     edx, edx
0x18000f127  test    eax, eax
0x18000f129  cmovnz  rbx, rdx
0x18000f12d  test    rbx, rbx
0x18000f130  jz      loc_18000F200
0x18000f136  mov     rax, [rbx]
0x18000f139  mov     edx, 1
0x18000f13e  mov     rcx, rbx
0x18000f141  mov     rax, [rax]
0x18000f144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f149  jmp     loc_18000F200
0x18000f14e  mov     rax, [rbp+arg_10]
0x18000f152  cmp     [r13+0], rax
0x18000f156  jz      loc_18000F1DE
0x18000f15c  cmp     [r13+0], rdi
0x18000f160  jz      short loc_18000F1DE
0x18000f162  mov     rax, [rbp+arg_18]
0x18000f166  cmp     [r13+0], rax
0x18000f16a  jnz     short loc_18000F17E
0x18000f16c  mov     edx, 3
0x18000f171  mov     rcx, r12
0x18000f174  call    ?_SwitchToPage@CPicturePasswordDUIHost@@IEAAJW4PICTURE_PASSWORD_ENROLLMENT_PAGE@@@Z; CPicturePasswordDUIHost::_SwitchToPage(PICTURE_PASSWORD_ENROLLMENT_PAGE)
0x18000f179  jmp     loc_18000F377
0x18000f17e  cmp     [r13+0], rcx
0x18000f182  jnz     loc_18000F377
0x18000f188  lea     r8, [rbp+arg_8]; struct IStream **
0x18000f18c  mov     [rbp+arg_8], 0
0x18000f194  lea     rdx, aSanitizedJpg; "Sanitized.jpg"
0x18000f19b  call    ?_LoadImage@CPicturePasswordDUIHost@@IEAAJPEBGPEAPEAUIStream@@@Z; CPicturePasswordDUIHost::_LoadImage(ushort const *,IStream * *)
0x18000f1a0  test    eax, eax
0x18000f1a2  js      short loc_18000F200
0x18000f1a4  mov     r9, [rbp+arg_8]; __int64
0x18000f1a8  xor     r8d, r8d; unsigned __int64
0x18000f1ab  mov     rcx, [r12+2D8h]; this
0x18000f1b3  mov     edx, 402h; unsigned int
0x18000f1b8  call    ?PostNotification@CPrivateNotificationWindow@@QEAA_NI_K_J@Z; CPrivateNotificationWindow::PostNotification(uint,unsigned __int64,__int64)
0x18000f1bd  test    al, al
0x18000f1bf  jnz     short loc_18000F1D3
0x18000f1c1  mov     rcx, [rbp+arg_8]
0x18000f1c5  mov     rax, [rcx]
0x18000f1c8  mov     rax, [rax+10h]
0x18000f1cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1d1  jmp     short loc_18000F200
0x18000f1d3  mov     byte ptr [r12+361h], 1
0x18000f1dc  jmp     short loc_18000F200
0x18000f1de  mov     rcx, [r12+368h]; hWnd
0x18000f1e6  xor     r9d, r9d; lParam
0x18000f1e9  xor     r8d, r8d; wParam
0x18000f1ec  lea     edx, [r9+10h]; Msg
0x18000f1f0  call    cs:__imp_PostMessageW
0x18000f1f6  jmp     short loc_18000F200
0x18000f1f8  mov     rcx, r12; this
0x18000f1fb  call    ?_InvokePicker@CPicturePasswordDUIHost@@IEAAXXZ; CPicturePasswordDUIHost::_InvokePicker(void)
0x18000f200  mov     byte ptr [r13+10h], 1
0x18000f205  jmp     loc_18000F377
0x18000f20a  cmp     dword ptr [r13+14h], 2
0x18000f20f  jnz     loc_18000F2FD
0x18000f215  mov     rax, cs:__imp_?ManipulationCompleted@TouchScrollViewer@DirectUI@@SA?AVUID@@XZ; DirectUI::TouchScrollViewer::ManipulationCompleted(void)
0x18000f21c  lea     rdx, [rbp+arg_8]
0x18000f220  mov     rcx, rbx
0x18000f223  mov     [rbp+arg_8], rax
0x18000f227  call    ??8@YA_NAEBVUID@@AEBQ6A?AV0@XZ@Z; operator==(UID const &,UID (*const &)(void))
0x18000f22c  test    al, al
0x18000f22e  jz      loc_18000F2FD
0x18000f234  lea     rcx, aClientpanel; "clientPanel"
0x18000f23b  call    cs:__imp_StrToID
0x18000f241  movzx   edx, ax
0x18000f244  mov     rcx, r12
0x18000f247  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000f24d  lea     rcx, aBgviewer; "bgViewer"
0x18000f254  mov     rbx, rax
0x18000f257  call    cs:__imp_StrToID
0x18000f25d  movzx   edx, ax
0x18000f260  mov     rcx, rbx
0x18000f263  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000f269  mov     rcx, rax
0x18000f26c  call    ??$element_cast@VTouchScrollViewer@DirectUI@@@@YAPEAVTouchScrollViewer@DirectUI@@PEAVElement@1@@Z; element_cast<DirectUI::TouchScrollViewer>(DirectUI::Element *)
0x18000f271  mov     rdi, rax
0x18000f274  cmp     rax, [r13+0]
0x18000f278  jnz     loc_18000F377
0x18000f27e  cmp     [r12+3D0h], sil
0x18000f286  jnz     loc_18000F377
0x18000f28c  lea     rdx, [rbp+arg_8]
0x18000f290  mov     [rbp+arg_8], rsi
0x18000f294  mov     rcx, rbx
0x18000f297  call    cs:__imp_?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetExtent(DirectUI::Value * *)
0x18000f29d  mov     rcx, rdi
0x18000f2a0  mov     rbx, rax
0x18000f2a3  call    cs:__imp_?GetXOffset@BaseScrollViewer@DirectUI@@QEAAHXZ; DirectUI::BaseScrollViewer::GetXOffset(void)
0x18000f2a9  mov     rcx, rdi
0x18000f2ac  mov     [r12+2E8h], eax
0x18000f2b4  call    cs:__imp_?GetYOffset@BaseScrollViewer@DirectUI@@QEAAHXZ; DirectUI::BaseScrollViewer::GetYOffset(void)
0x18000f2ba  mov     ecx, [r12+2E8h]
0x18000f2c2  mov     [r12+2ECh], eax
0x18000f2ca  add     ecx, [rbx]
0x18000f2cc  mov     [r12+2F0h], ecx
0x18000f2d4  lea     rcx, [rbp+arg_8]; this
0x18000f2d8  add     eax, [rbx+4]
0x18000f2db  mov     [r12+2F4h], eax
0x18000f2e3  movups  xmm0, xmmword ptr [r12+2E8h]
0x18000f2ec  movdqu  xmmword ptr [r12+37Ch], xmm0
0x18000f2f6  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x18000f2fb  jmp     short loc_18000F377
0x18000f2fd  cmp     dword ptr [r13+14h], 4
0x18000f302  jnz     short loc_18000F377
0x18000f304  mov     rax, cs:__imp_?TriggeredAnimationComplete@PVLAnimation@DirectUI@@SA?AVUID@@XZ; DirectUI::PVLAnimation::TriggeredAnimationComplete(void)
0x18000f30b  lea     rdx, [rbp+arg_8]
0x18000f30f  mov     rcx, rbx
0x18000f312  mov     [rbp+arg_8], rax
0x18000f316  call    ??8@YA_NAEBVUID@@AEBQ6A?AV0@XZ@Z; operator==(UID const &,UID (*const &)(void))
0x18000f31b  test    al, al
0x18000f31d  jz      short loc_18000F377
0x18000f31f  mov     eax, [r13+24h]
0x18000f323  cmp     [r12+3C4h], eax
0x18000f32b  jnz     short loc_18000F377
0x18000f32d  mov     [r12+3C0h], sil
0x18000f335  mov     [r12+3C4h], esi
0x18000f33d  cmp     [r12+3C8h], sil
0x18000f345  jz      short loc_18000F35F
0x18000f347  mov     edx, [r12+3CCh]
0x18000f34f  mov     rcx, r12
0x18000f352  mov     [r12+3C8h], sil
0x18000f35a  call    ?_SwitchToPage@CPicturePasswordDUIHost@@IEAAJW4PICTURE_PASSWORD_ENROLLMENT_PAGE@@@Z; CPicturePasswordDUIHost::_SwitchToPage(PICTURE_PASSWORD_ENROLLMENT_PAGE)
0x18000f35f  mov     rcx, [r12+2D8h]; this
0x18000f367  xor     r9d, r9d; __int64
0x18000f36a  xor     r8d, r8d; unsigned __int64
0x18000f36d  mov     edx, 40Ah; unsigned int
0x18000f372  call    ?PostNotification@CPrivateNotificationWindow@@QEAA_NI_K_J@Z; CPrivateNotificationWindow::PostNotification(uint,unsigned __int64,__int64)
0x18000f377  mov     rdx, r13
0x18000f37a  mov     rcx, r12
0x18000f37d  mov     rbx, [rsp+50h+arg_0]
0x18000f385  add     rsp, 50h
0x18000f389  pop     r15
0x18000f38b  pop     r14
0x18000f38d  pop     r13
0x18000f38f  pop     r12
0x18000f391  pop     rdi
  ... truncated ...
```
