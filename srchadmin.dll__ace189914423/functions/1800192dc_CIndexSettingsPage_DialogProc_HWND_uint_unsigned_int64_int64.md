# CIndexSettingsPage::_DialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800192dc`
- end: `0x1800193c1`
- name: `?_DialogProc@CIndexSettingsPage@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `229`
- prototype: `__int64 __fastcall(CIndexSettingsPage *__hidden this, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a0b0`

## callees

- `0x180004360`
- `0x180018b7c`
- `0x180019048`
- `0x1800192dc`
- `0x1800198d4`
- `0x180019c7c`
- `0x180019dcc`
- `0x18001d004`
- `0x18001d104`

## import_xrefs

- `USER32!SetCursor` at `0x1800193a5`
- `USER32!SetCursor` at `0x1800193a5`

## string_xrefs

- `0x180019381`: `AdvIdxCplLink`

## pseudocode

```c
__int64 __fastcall CIndexSettingsPage::_DialogProc(HCURSOR *this, HWND a2, int a3, int a4, __int64 a5)
{
  __int64 result; // rax
  int v6; // r8d
  int v7; // r8d
  int v8; // r8d
  HWND v9; // r8
  int v10; // eax

  result = 0;
  v6 = a3 - 26;
  if ( !v6 )
    return CIndexSettingsPage::_RefreshData((CIndexSettingsPage *)this);
  v7 = v6 - 6;
  if ( v7 )
  {
    v8 = v7 - 46;
    if ( v8 )
    {
      v9 = (HWND)(unsigned int)(v8 - 194);
      if ( (_DWORD)v9 )
      {
        if ( (_DWORD)v9 == 1 )
          return CIndexSettingsPage::_OnCommand((CIndexSettingsPage *)this, (unsigned __int16)a4, v9, HIWORD(a4));
      }
      else
      {
        return CIndexSettingsPage::_OnInitDialog((CIndexSettingsPage *)this);
      }
    }
    else
    {
      v10 = *(_DWORD *)(a5 + 16);
      if ( v10 == -202 )
      {
        CIndexSettingsPage::_OnApply((WCHAR *)this);
      }
      else if ( v10 != -201 && (v10 == -4 || v10 == -2) )
      {
        if ( *(_QWORD *)(a5 + 8) == 912 )
        {
          SearchOptionsTelemetry::AdvancedIndexingHelpClicked();
          LaunchHSC(L"7ef664a7-395c-4cb3-9178-deb08ed4df2c");
        }
        if ( *(_QWORD *)(a5 + 8) == 916 )
        {
          SearchOptionsTelemetry::TroubleshootIndexingClicked();
          LaunchIndexingTroubleshooter(L"AdvIdxCplLink");
        }
      }
      return 0;
    }
  }
  else if ( *((_DWORD *)this + 4) )
  {
    SetCursor(this[3]);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800192dc  push    rbx
0x1800192de  sub     rsp, 20h
0x1800192e2  xor     eax, eax
0x1800192e4  mov     r10, r9
0x1800192e7  sub     r8d, 1Ah
0x1800192eb  jz      loc_1800193B6
0x1800192f1  sub     r8d, 6
0x1800192f5  jz      loc_18001939C
0x1800192fb  sub     r8d, 2Eh ; '.'
0x1800192ff  jz      short loc_180019337
0x180019301  sub     r8d, 0C2h; HWND
0x180019308  jz      short loc_18001932D
0x18001930a  cmp     r8d, 1
0x18001930e  jnz     loc_1800193BB
0x180019314  mov     rax, r9
0x180019317  movzx   edx, r10w; unsigned int
0x18001931b  shr     rax, 10h
0x18001931f  movzx   r9d, ax; unsigned int
0x180019323  add     rsp, 20h
0x180019327  pop     rbx
0x180019328  jmp     ?_OnCommand@CIndexSettingsPage@@AEAA_JIPEAUHWND__@@I@Z; CIndexSettingsPage::_OnCommand(uint,HWND__ *,uint)
0x18001932d  add     rsp, 20h
0x180019331  pop     rbx
0x180019332  jmp     ?_OnInitDialog@CIndexSettingsPage@@AEAA_JXZ; CIndexSettingsPage::_OnInitDialog(void)
0x180019337  mov     rbx, [rsp+28h+arg_20]
0x18001933c  mov     eax, [rbx+10h]
0x18001933f  cmp     eax, 0FFFFFF36h
0x180019344  jz      short loc_18001938F
0x180019346  cmp     eax, 0FFFFFF37h
0x18001934b  jz      short loc_180019394
0x18001934d  cmp     eax, 0FFFFFFFCh
0x180019350  jz      short loc_180019357
0x180019352  cmp     eax, 0FFFFFFFEh
0x180019355  jnz     short loc_180019394
0x180019357  cmp     qword ptr [rbx+8], 390h
0x18001935f  jnz     short loc_180019372
0x180019361  call    ?AdvancedIndexingHelpClicked@SearchOptionsTelemetry@@SAXXZ; SearchOptionsTelemetry::AdvancedIndexingHelpClicked(void)
0x180019366  lea     rcx, a7ef664a7395c4c; "7ef664a7-395c-4cb3-9178-deb08ed4df2c"
0x18001936d  call    ?LaunchHSC@@YAJPEBG@Z; LaunchHSC(ushort const *)
0x180019372  cmp     qword ptr [rbx+8], 394h
0x18001937a  jnz     short loc_180019394
0x18001937c  call    ?TroubleshootIndexingClicked@SearchOptionsTelemetry@@SAXXZ; SearchOptionsTelemetry::TroubleshootIndexingClicked(void)
0x180019381  lea     rcx, String; "AdvIdxCplLink"
0x180019388  call    ?LaunchIndexingTroubleshooter@@YAJPEBG@Z; LaunchIndexingTroubleshooter(ushort const *)
0x18001938d  jmp     short loc_180019394
0x18001938f  call    ?_OnApply@CIndexSettingsPage@@AEAAJXZ; CIndexSettingsPage::_OnApply(void)
0x180019394  xor     eax, eax
0x180019396  add     rsp, 20h
0x18001939a  pop     rbx
0x18001939b  retn
0x18001939c  cmp     [rcx+10h], eax
0x18001939f  jz      short loc_1800193BB
0x1800193a1  mov     rcx, [rcx+18h]; hCursor
0x1800193a5  call    cs:__imp_SetCursor
0x1800193ab  mov     eax, 1
0x1800193b0  add     rsp, 20h
0x1800193b4  pop     rbx
0x1800193b5  retn
0x1800193b6  call    ?_RefreshData@CIndexSettingsPage@@AEAA_JXZ; CIndexSettingsPage::_RefreshData(void)
0x1800193bb  add     rsp, 20h
0x1800193bf  pop     rbx
0x1800193c0  retn
```
