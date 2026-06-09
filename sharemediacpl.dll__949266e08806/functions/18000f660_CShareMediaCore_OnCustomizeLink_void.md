# CShareMediaCore::_OnCustomizeLink(void)

- ea: `0x18000f660`
- end: `0x18000f844`
- name: `?_OnCustomizeLink@CShareMediaCore@@AEAAJXZ`
- size: `484`
- prototype: `__int64 __fastcall(CShareMediaCore *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000b78c`

## callees

- `0x180001914`
- `0x180003860`
- `0x180003888`
- `0x180003d8c`
- `0x180003e3c`
- `0x1800069d4`
- `0x180006b3c`
- `0x18000a5ec`
- `0x18000f660`
- `0x18001e010`

## import_xrefs

- `USER32!DialogBoxParamW` at `0x18000f7b0`
- `USER32!DialogBoxParamW` at `0x18000f7b0`

## pseudocode

```c
__int64 __fastcall CShareMediaCore::_OnCustomizeLink(CShareMediaCore *this)
{
  CDeviceSettings *v2; // rax
  CDeviceSettings *v3; // rax
  struct CDeviceSettings *v4; // rdi
  int v5; // ebx
  CLibrarySharingFilterDlg *v6; // rax
  CLibrarySharingFilterDlg *dwInitParam; // rsi
  _QWORD *v8; // rcx
  HWND ParentWindow; // rbp

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  v2 = (CDeviceSettings *)operator new(0x70u);
  if ( v2 && (v3 = CDeviceSettings::CDeviceSettings(v2), (v4 = v3) != 0) )
  {
    v5 = CDeviceSettings::SetID(v3, L"Default");
    if ( v5 >= 0 )
    {
      v6 = (CLibrarySharingFilterDlg *)operator new(0x48u);
      dwInitParam = v6;
      if ( v6 )
      {
        CLibrarySharingFilterDlg::CLibrarySharingFilterDlg(v6);
        *(_QWORD *)dwInitParam = &CLibrarySharingDefaultsDlg::`vftable';
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
            v8 = WPP_GLOBAL_Control;
          }
          if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x20) != 0 )
            WPP_SF_(v8[2], 91, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
        }
        v5 = CLibrarySharingFilterDlg::SetDeviceSettings(dwInitParam, v4);
        if ( v5 >= 0 )
        {
          ParentWindow = CShareMediaCore::GetParentWindow(this);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
          }
          DialogBoxParamW(
            g_hinst,
            (LPCWSTR)0x13D,
            ParentWindow,
            CLibrarySharingDefaultsDlg::s_DialogProc,
            (LPARAM)dwInitParam);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
          }
        }
        (**(void (__fastcall ***)(CLibrarySharingFilterDlg *, __int64))dwInitParam)(dwInitParam, 1);
      }
      else
      {
        v5 = -2147024882;
      }
    }
    (*(void (__fastcall **)(struct CDeviceSettings *))(*(_QWORD *)v4 + 16LL))(v4);
  }
  else
  {
    v5 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      61,
      &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids,
      (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f660  push    rbx
0x18000f662  push    rbp
0x18000f663  push    rsi
0x18000f664  push    rdi
0x18000f665  push    r15
0x18000f667  sub     rsp, 30h
0x18000f66b  mov     rbp, rcx
0x18000f66e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f675  lea     r15, WPP_GLOBAL_Control
0x18000f67c  cmp     rcx, r15
0x18000f67f  jz      short loc_18000F69C
0x18000f681  test    byte ptr [rcx+1Ch], 20h
0x18000f685  jz      short loc_18000F69C
0x18000f687  mov     rcx, [rcx+10h]
0x18000f68b  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000f692  mov     edx, 3Ch ; '<'
0x18000f697  call    WPP_SF_
0x18000f69c  mov     ecx, 70h ; 'p'; Size
0x18000f6a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f6a6  test    rax, rax
0x18000f6a9  jz      loc_18000F808
0x18000f6af  mov     rcx, rax; this
0x18000f6b2  call    ??0CDeviceSettings@@QEAA@XZ; CDeviceSettings::CDeviceSettings(void)
0x18000f6b7  mov     rdi, rax
0x18000f6ba  test    rax, rax
0x18000f6bd  jz      loc_18000F808
0x18000f6c3  lea     rdx, aDefault; "Default"
0x18000f6ca  mov     rcx, rax; this
0x18000f6cd  call    ?SetID@CDeviceSettings@@QEAAJPEBG@Z; CDeviceSettings::SetID(ushort const *)
0x18000f6d2  mov     ebx, eax
0x18000f6d4  test    eax, eax
0x18000f6d6  js      loc_18000F7F7
0x18000f6dc  mov     ecx, 48h ; 'H'; Size
0x18000f6e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f6e6  mov     rsi, rax
0x18000f6e9  test    rax, rax
0x18000f6ec  jz      loc_18000F7F2
0x18000f6f2  mov     rcx, rax; this
0x18000f6f5  call    ??0CLibrarySharingFilterDlg@@QEAA@XZ; CLibrarySharingFilterDlg::CLibrarySharingFilterDlg(void)
0x18000f6fa  lea     rax, ??_7CLibrarySharingDefaultsDlg@@6B@; const CLibrarySharingDefaultsDlg::`vftable'
0x18000f701  mov     [rsi], rax
0x18000f704  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f70b  cmp     rcx, r15
0x18000f70e  jz      short loc_18000F752
0x18000f710  test    byte ptr [rcx+1Ch], 20h
0x18000f714  jz      short loc_18000F732
0x18000f716  mov     rcx, [rcx+10h]
0x18000f71a  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x18000f721  mov     edx, 5Ah ; 'Z'
0x18000f726  call    WPP_SF_
0x18000f72b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f732  cmp     rcx, r15
0x18000f735  jz      short loc_18000F752
0x18000f737  test    byte ptr [rcx+1Ch], 20h
0x18000f73b  jz      short loc_18000F752
0x18000f73d  mov     rcx, [rcx+10h]
0x18000f741  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x18000f748  mov     edx, 5Bh ; '['
0x18000f74d  call    WPP_SF_
0x18000f752  mov     rdx, rdi; struct CDeviceSettings *
0x18000f755  mov     rcx, rsi; this
0x18000f758  call    ?SetDeviceSettings@CLibrarySharingFilterDlg@@QEAAJPEAVCDeviceSettings@@@Z; CLibrarySharingFilterDlg::SetDeviceSettings(CDeviceSettings *)
0x18000f75d  mov     ebx, eax
0x18000f75f  test    eax, eax
0x18000f761  js      short loc_18000F7DD
0x18000f763  mov     rcx, rbp; this
0x18000f766  call    ?GetParentWindow@CShareMediaCore@@QEAAPEAUHWND__@@XZ; CShareMediaCore::GetParentWindow(void)
0x18000f76b  mov     rbp, rax
0x18000f76e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f775  cmp     rcx, r15
0x18000f778  jz      short loc_18000F795
0x18000f77a  test    byte ptr [rcx+1Ch], 20h
0x18000f77e  jz      short loc_18000F795
0x18000f780  mov     rcx, [rcx+10h]
0x18000f784  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x18000f78b  mov     edx, 5Eh ; '^'
0x18000f790  call    WPP_SF_
0x18000f795  mov     rcx, cs:g_hinst; hInstance
0x18000f79c  lea     r9, ?s_DialogProc@CLibrarySharingDefaultsDlg@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18000f7a3  mov     r8, rbp; hWndParent
0x18000f7a6  mov     [rsp+58h+dwInitParam], rsi; dwInitParam
0x18000f7ab  mov     edx, 13Dh; lpTemplateName
0x18000f7b0  call    cs:__imp_DialogBoxParamW
0x18000f7b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7bd  cmp     rcx, r15
0x18000f7c0  jz      short loc_18000F7DD
0x18000f7c2  test    byte ptr [rcx+1Ch], 20h
0x18000f7c6  jz      short loc_18000F7DD
0x18000f7c8  mov     rcx, [rcx+10h]
0x18000f7cc  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x18000f7d3  mov     edx, 5Fh ; '_'
0x18000f7d8  call    WPP_SF_
0x18000f7dd  mov     rax, [rsi]
0x18000f7e0  mov     edx, 1
0x18000f7e5  mov     rcx, rsi
0x18000f7e8  mov     rax, [rax]
0x18000f7eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7f0  jmp     short loc_18000F7F7
0x18000f7f2  mov     ebx, 8007000Eh
0x18000f7f7  mov     rax, [rdi]
0x18000f7fa  mov     rcx, rdi
0x18000f7fd  mov     rax, [rax+10h]
0x18000f801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f806  jmp     short loc_18000F80D
0x18000f808  mov     ebx, 8007000Eh
0x18000f80d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f814  cmp     rcx, r15
0x18000f817  jz      short loc_18000F837
0x18000f819  test    byte ptr [rcx+1Ch], 20h
0x18000f81d  jz      short loc_18000F837
0x18000f81f  mov     rcx, [rcx+10h]
0x18000f823  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000f82a  mov     edx, 3Dh ; '='
0x18000f82f  mov     r9d, ebx
0x18000f832  call    WPP_SF_d
0x18000f837  mov     eax, ebx
0x18000f839  add     rsp, 30h
0x18000f83d  pop     r15
0x18000f83f  pop     rdi
0x18000f840  pop     rsi
0x18000f841  pop     rbp
0x18000f842  pop     rbx
0x18000f843  retn
```
