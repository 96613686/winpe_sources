# CWallpaperCore::_EnableSlideshow(bool,bool)

- ea: `0x18003fba8`
- end: `0x18003fe55`
- name: `?_EnableSlideshow@CWallpaperCore@@AEAAJ_N0@Z`
- size: `685`
- prototype: `__int64 __fastcall(CWallpaperCore *__hidden this, bool, bool)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003cc80`
- `0x18003d0c0`
- `0x18003d730`

## callees

- `0x18003fba8`
- `0x180043148`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fcf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fcf9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fe2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fe2f`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18003fd96`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18003fd96`
- `POWRPROF!PowerReadDCValueIndex` at `0x18003fdca`
- `POWRPROF!PowerReadDCValueIndex` at `0x18003fdca`
- `USER32!SendMessageW` at `0x18003fce5`
- `USER32!SendMessageW` at `0x18003fce5`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003fc10`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003fc4e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003fc89`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003fdf7`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003fc10`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003fc4e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003fc89`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003fdf7`
- `DUI70!StrToID` at `0x18003fbfe`
- `DUI70!StrToID` at `0x18003fc3c`
- `DUI70!StrToID` at `0x18003fc77`
- `DUI70!StrToID` at `0x18003fde5`
- `DUI70!StrToID` at `0x18003fbfe`
- `DUI70!StrToID` at `0x18003fc3c`
- `DUI70!StrToID` at `0x18003fc77`
- `DUI70!StrToID` at `0x18003fde5`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18003fc25`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18003fc60`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18003fc9e`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18003fe1f`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18003fc25`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18003fc60`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18003fc9e`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18003fe1f`
- `DUI70!?GetSelection@Combobox@DirectUI@@QEAAHXZ` at `0x18003fccb`
- `DUI70!?GetSelection@Combobox@DirectUI@@QEAAHXZ` at `0x18003fccb`

## string_xrefs

- `0x18003fbf7`: `ComboBox_Interval`

## pseudocode

```c
__int64 __fastcall CWallpaperCore::_EnableSlideshow(CWallpaperCore *this, bool a2, char a3)
{
  signed int v5; // edi
  DirectUI::Element *v6; // rbx
  unsigned __int16 v7; // ax
  DirectUI::Element *Descendent; // r15
  DirectUI::Element *v9; // rbx
  unsigned __int16 v10; // ax
  DirectUI::Element *v11; // rax
  DirectUI::Element *v12; // rbx
  unsigned __int16 v13; // ax
  struct DirectUI::Element *v14; // r13
  HWND v15; // rbx
  int Selection; // eax
  unsigned int v17; // ebx
  signed int LastError; // eax
  __int64 v19; // rcx
  __int64 v20; // rdx
  DirectUI::Element *v21; // rbx
  unsigned __int16 v22; // ax
  DirectUI::Element *v23; // rbx
  DWORD DcValueIndex; // [rsp+68h] [rbp+38h] BYREF
  GUID *ActivePolicyGuid; // [rsp+78h] [rbp+48h] BYREF

  if ( a2 || a3 )
  {
    v5 = 0;
  }
  else
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 52) + 96LL))(*((_QWORD *)this + 52), 0);
    if ( v5 < 0 )
      return (unsigned int)v5;
  }
  v6 = (DirectUI::Element *)*((_QWORD *)this + 4);
  v7 = StrToID(L"ComboBox_Interval");
  Descendent = DirectUI::Element::FindDescendent(v6, v7);
  DirectUI::Element::SetEnabled(Descendent, a2);
  v9 = (DirectUI::Element *)*((_QWORD *)this + 4);
  v10 = StrToID(L"Slideshow_Interval");
  v11 = DirectUI::Element::FindDescendent(v9, v10);
  DirectUI::Element::SetEnabled(v11, a2);
  v12 = (DirectUI::Element *)*((_QWORD *)this + 4);
  v13 = StrToID(L"CheckBox_Shuffle");
  v14 = DirectUI::Element::FindDescendent(v12, v13);
  DirectUI::Element::SetEnabled(v14, a2);
  if ( a2 )
  {
    v15 = (HWND)(*(__int64 (__fastcall **)(DirectUI::Element *))(*(_QWORD *)Descendent + 360LL))(Descendent);
    Selection = DirectUI::Combobox::GetSelection(Descendent);
    v17 = SendMessageW(v15, 0x150u, Selection, 0);
    if ( v17 == -1 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
    }
    else
    {
      v19 = *((_QWORD *)this + 52);
      DcValueIndex = 0;
      LODWORD(ActivePolicyGuid) = 0;
      if ( (*(int (__fastcall **)(__int64, DWORD *, GUID **))(*(_QWORD *)v19 + 120LL))(
             v19,
             &DcValueIndex,
             &ActivePolicyGuid) >= 0 )
      {
        v20 = DcValueIndex;
        if ( (((unsigned __int8)DcValueIndex ^ (*((_BYTE *)v14 + 148) >> 4)) & 1) != 0 )
        {
          v20 = DcValueIndex ^ 1;
          DcValueIndex ^= 1u;
        }
        v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 52) + 112LL))(
               *((_QWORD *)this + 52),
               v20,
               v17);
      }
    }
  }
  if ( *((_BYTE *)this + 72) )
  {
    ActivePolicyGuid = 0;
    if ( !PowerGetActiveScheme(0, &ActivePolicyGuid) )
    {
      DcValueIndex = 0;
      if ( !PowerReadDCValueIndex(0, ActivePolicyGuid, &SubGroupOfPowerSettingsGuid, &PowerSettingGuid, &DcValueIndex) )
      {
        v21 = (DirectUI::Element *)*((_QWORD *)this + 4);
        v22 = StrToID(L"CheckBox_PauseSlideshow");
        v23 = DirectUI::Element::FindDescendent(v21, v22);
        CWallpaperCore::_SetPaused(this, DcValueIndex != 0);
        if ( v5 >= 0 )
          DirectUI::Element::SetEnabled(v23, a2);
      }
      LocalFree(ActivePolicyGuid);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003fba8  mov     [rsp-28h+arg_0], rbx
0x18003fbad  mov     [rsp-28h+arg_10], rsi
0x18003fbb2  push    rbp
0x18003fbb3  push    rdi
0x18003fbb4  push    r13
0x18003fbb6  push    r14
0x18003fbb8  push    r15
0x18003fbba  mov     rbp, rsp
0x18003fbbd  sub     rsp, 30h
0x18003fbc1  mov     r14b, dl
0x18003fbc4  mov     rsi, rcx
0x18003fbc7  test    dl, dl
0x18003fbc9  jnz     short loc_18003FBF1
0x18003fbcb  test    r8b, r8b
0x18003fbce  jnz     short loc_18003FBF1
0x18003fbd0  mov     rcx, [rcx+1A0h]
0x18003fbd7  xor     edx, edx
0x18003fbd9  mov     rax, [rcx]
0x18003fbdc  mov     rax, [rax+60h]
0x18003fbe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fbe5  mov     edi, eax
0x18003fbe7  test    eax, eax
0x18003fbe9  js      loc_18003FE3B
0x18003fbef  jmp     short loc_18003FBF3
0x18003fbf1  xor     edi, edi
0x18003fbf3  mov     rbx, [rsi+20h]
0x18003fbf7  lea     rcx, aComboboxInterv; "ComboBox_Interval"
0x18003fbfe  call    cs:__imp_StrToID
0x18003fc05  nop     dword ptr [rax+rax+00h]
0x18003fc0a  movzx   edx, ax
0x18003fc0d  mov     rcx, rbx
0x18003fc10  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003fc17  nop     dword ptr [rax+rax+00h]
0x18003fc1c  mov     rcx, rax
0x18003fc1f  mov     dl, r14b
0x18003fc22  mov     r15, rax
0x18003fc25  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18003fc2c  nop     dword ptr [rax+rax+00h]
0x18003fc31  mov     rbx, [rsi+20h]
0x18003fc35  lea     rcx, aSlideshowInter; "Slideshow_Interval"
0x18003fc3c  call    cs:__imp_StrToID
0x18003fc43  nop     dword ptr [rax+rax+00h]
0x18003fc48  movzx   edx, ax
0x18003fc4b  mov     rcx, rbx
0x18003fc4e  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003fc55  nop     dword ptr [rax+rax+00h]
0x18003fc5a  mov     rcx, rax
0x18003fc5d  mov     dl, r14b
0x18003fc60  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18003fc67  nop     dword ptr [rax+rax+00h]
0x18003fc6c  mov     rbx, [rsi+20h]
0x18003fc70  lea     rcx, aCheckboxShuffl_0; "CheckBox_Shuffle"
0x18003fc77  call    cs:__imp_StrToID
0x18003fc7e  nop     dword ptr [rax+rax+00h]
0x18003fc83  movzx   edx, ax
0x18003fc86  mov     rcx, rbx
0x18003fc89  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003fc90  nop     dword ptr [rax+rax+00h]
0x18003fc95  mov     rcx, rax
0x18003fc98  mov     dl, r14b
0x18003fc9b  mov     r13, rax
0x18003fc9e  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18003fca5  nop     dword ptr [rax+rax+00h]
0x18003fcaa  test    r14b, r14b
0x18003fcad  jz      loc_18003FD7E
0x18003fcb3  mov     rcx, [r15]
0x18003fcb6  mov     rax, [rcx+168h]
0x18003fcbd  mov     rcx, r15
0x18003fcc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fcc5  mov     rcx, r15
0x18003fcc8  mov     rbx, rax
0x18003fccb  call    cs:__imp_?GetSelection@Combobox@DirectUI@@QEAAHXZ; DirectUI::Combobox::GetSelection(void)
0x18003fcd2  nop     dword ptr [rax+rax+00h]
0x18003fcd7  movsxd  r8, eax; wParam
0x18003fcda  xor     r9d, r9d; lParam
0x18003fcdd  mov     edx, 150h; Msg
0x18003fce2  mov     rcx, rbx; hWnd
0x18003fce5  call    cs:__imp_SendMessageW
0x18003fcec  nop     dword ptr [rax+rax+00h]
0x18003fcf1  mov     rbx, rax
0x18003fcf4  cmp     eax, 0FFFFFFFFh
0x18003fcf7  jnz     short loc_18003FD20
0x18003fcf9  call    cs:__imp_GetLastError
0x18003fd00  nop     dword ptr [rax+rax+00h]
0x18003fd05  mov     edi, eax
0x18003fd07  test    eax, eax
0x18003fd09  jle     short loc_18003FD14
0x18003fd0b  movzx   edi, ax
0x18003fd0e  or      edi, 80070000h
0x18003fd14  test    edi, edi
0x18003fd16  mov     eax, 80004005h
0x18003fd1b  cmovns  edi, eax
0x18003fd1e  jmp     short loc_18003FD7E
0x18003fd20  mov     rcx, [rsi+1A0h]
0x18003fd27  lea     r8, [rbp+ActivePolicyGuid]
0x18003fd2b  mov     [rbp+arg_8], 0
0x18003fd32  lea     rdx, [rbp+arg_8]
0x18003fd36  mov     dword ptr [rbp+ActivePolicyGuid], 0
0x18003fd3d  mov     rax, [rcx]
0x18003fd40  mov     rax, [rax+78h]
0x18003fd44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd49  test    eax, eax
0x18003fd4b  js      short loc_18003FD7E
0x18003fd4d  mov     al, [r13+94h]
0x18003fd54  mov     edx, [rbp+arg_8]
0x18003fd57  shr     al, 4
0x18003fd5a  xor     al, dl
0x18003fd5c  test    al, 1
0x18003fd5e  jz      short loc_18003FD66
0x18003fd60  xor     edx, 1
0x18003fd63  mov     [rbp+arg_8], edx
0x18003fd66  mov     rcx, [rsi+1A0h]
0x18003fd6d  mov     r8d, ebx
0x18003fd70  mov     rax, [rcx]
0x18003fd73  mov     rax, [rax+70h]
0x18003fd77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd7c  mov     edi, eax
0x18003fd7e  cmp     byte ptr [rsi+48h], 0
0x18003fd82  jz      loc_18003FE3B
0x18003fd88  lea     rdx, [rbp+ActivePolicyGuid]; ActivePolicyGuid
0x18003fd8c  mov     [rbp+ActivePolicyGuid], 0
0x18003fd94  xor     ecx, ecx; UserRootPowerKey
0x18003fd96  call    cs:__imp_PowerGetActiveScheme
0x18003fd9d  nop     dword ptr [rax+rax+00h]
0x18003fda2  test    eax, eax
0x18003fda4  jnz     loc_18003FE3B
0x18003fdaa  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x18003fdae  lea     r9, PowerSettingGuid; PowerSettingGuid
0x18003fdb5  mov     [rbp+arg_8], eax
0x18003fdb8  lea     r8, SubGroupOfPowerSettingsGuid; SubGroupOfPowerSettingsGuid
0x18003fdbf  lea     rax, [rbp+arg_8]
0x18003fdc3  xor     ecx, ecx; RootPowerKey
0x18003fdc5  mov     [rsp+30h+DcValueIndex], rax; DcValueIndex
0x18003fdca  call    cs:__imp_PowerReadDCValueIndex
0x18003fdd1  nop     dword ptr [rax+rax+00h]
0x18003fdd6  test    eax, eax
0x18003fdd8  jnz     short loc_18003FE2B
0x18003fdda  mov     rbx, [rsi+20h]
0x18003fdde  lea     rcx, aCheckboxPauses; "CheckBox_PauseSlideshow"
0x18003fde5  call    cs:__imp_StrToID
0x18003fdec  nop     dword ptr [rax+rax+00h]
0x18003fdf1  movzx   edx, ax
0x18003fdf4  mov     rcx, rbx
0x18003fdf7  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003fdfe  nop     dword ptr [rax+rax+00h]
0x18003fe03  cmp     [rbp+arg_8], 0
0x18003fe07  mov     rcx, rsi; this
0x18003fe0a  mov     rbx, rax
0x18003fe0d  setnz   dl; bool
0x18003fe10  call    ?_SetPaused@CWallpaperCore@@AEAAX_N@Z; CWallpaperCore::_SetPaused(bool)
0x18003fe15  test    edi, edi
0x18003fe17  js      short loc_18003FE2B
0x18003fe19  mov     dl, r14b
0x18003fe1c  mov     rcx, rbx
0x18003fe1f  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18003fe26  nop     dword ptr [rax+rax+00h]
0x18003fe2b  mov     rcx, [rbp+ActivePolicyGuid]; hMem
0x18003fe2f  call    cs:__imp_LocalFree
0x18003fe36  nop     dword ptr [rax+rax+00h]
0x18003fe3b  mov     rbx, [rsp+30h+arg_0]
0x18003fe40  mov     eax, edi
0x18003fe42  mov     rsi, [rsp+30h+arg_10]
0x18003fe47  add     rsp, 30h
0x18003fe4b  pop     r15
0x18003fe4d  pop     r14
0x18003fe4f  pop     r13
0x18003fe51  pop     rdi
0x18003fe52  pop     rbp
0x18003fe53  retn
```
