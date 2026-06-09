# CFciPropertiesShellExt::DialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180007290`
- end: `0x180007867`
- name: `?DialogProc@CFciPropertiesShellExt@@QEAA_JPEAUHWND__@@I_K_J@Z`
- size: `1495`
- prototype: `__int64 __fastcall(HANDLE *this, HWND, int, __int64, HWND)`
- caller_count: `1`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007870`

## callees

- `0x180007290`
- `0x180009090`
- `0x18000a87c`
- `0x18000ace8`
- `0x18000b328`
- `0x18000b410`
- `0x18000b4f8`
- `0x18000b668`
- `0x18000b95c`
- `0x18000ba34`
- `0x18000baf0`
- `0x18000bc10`
- `0x18000be1c`
- `0x18000c2cc`
- `0x18000c398`
- `0x18000c4a4`
- `0x18000c588`
- `0x18000d880`
- `0x18000db28`
- `0x18000e224`
- `0x18000fa8c`
- `0x18001b3ee`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000775a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000775a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000781f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000781f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000780d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000780d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180007835`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180007835`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007847`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007847`
- `USER32!SendDlgItemMessageW` at `0x1800074dd`
- `USER32!SendDlgItemMessageW` at `0x1800074dd`
- `USER32!LoadImageW` at `0x1800077e9`
- `USER32!LoadImageW` at `0x1800077e9`
- `USER32!SetCursor` at `0x1800077f2`
- `USER32!SetCursor` at `0x1800077f2`
- `USER32!GetDlgItem` at `0x180007486`
- `USER32!GetDlgItem` at `0x1800074b5`
- `USER32!GetDlgItem` at `0x180007486`
- `USER32!GetDlgItem` at `0x1800074b5`
- `USER32!CheckRadioButton` at `0x180007404`
- `USER32!CheckRadioButton` at `0x180007404`
- `USER32!SendMessageW` at `0x18000764b`
- `USER32!SendMessageW` at `0x18000767e`
- `USER32!SendMessageW` at `0x1800076bf`
- `USER32!SendMessageW` at `0x18000764b`
- `USER32!SendMessageW` at `0x18000767e`
- `USER32!SendMessageW` at `0x1800076bf`
- `USER32!EnableWindow` at `0x180007491`
- `USER32!EnableWindow` at `0x180007491`

## pseudocode

```c
__int64 __fastcall CFciPropertiesShellExt::DialogProc(HANDLE *this, HWND a2, int a3, __int64 a4, HWND a5)
{
  HWND v5; // r15
  HANDLE *v6; // rsi
  __int64 v7; // rbx
  int v8; // r8d
  int v9; // r8d
  const struct _PSHNOTIFY *v10; // r8
  int v11; // r8d
  unsigned __int64 v12; // r8
  struct CFciPropertiesShellExt::PropertyInfo *v14; // rax
  int v15; // edi
  struct CFciPropertiesShellExt::PropertyInfo *v16; // rax
  struct CFciPropertiesShellExt::PropertyInfo *v17; // rbx
  _WORD *v18; // rcx
  HWND v19; // rax
  __int64 v20; // r9
  struct CFciPropertiesShellExt::PropertyInfo *v21; // r8
  HWND DlgItem; // rax
  int v23; // eax
  struct CFciPropertiesShellExt::PropertyInfo *SelectedProperty; // rax
  HWND v25; // rsi
  WPARAM v26; // r15
  __int64 v27; // rdx
  OLECHAR *v28; // rcx
  BSTR v29; // r8
  __int64 v30; // rax
  OLECHAR *v31; // rdi
  OLECHAR v32; // r9
  OLECHAR *v33; // rdx
  HCURSOR ImageW; // rax
  HANDLE v35; // rcx
  BSTR bstrString[2]; // [rsp+30h] [rbp-91h] BYREF
  LPARAM v38; // [rsp+40h] [rbp-81h] BYREF
  int v39; // [rsp+48h] [rbp-79h]
  __int64 v40; // [rsp+58h] [rbp-69h]
  int v41; // [rsp+60h] [rbp-61h]
  __int64 v42; // [rsp+68h] [rbp-59h]

  v5 = a2;
  v6 = this;
  v7 = 0;
  v8 = a3 - 2;
  if ( !v8 )
  {
    if ( this[17] )
    {
      SetEvent(this[19]);
      if ( WaitForSingleObject(v6[17], 0x2710u) )
        TerminateThread(v6[17], 0x80004005);
      v35 = v6[17];
      if ( v35 )
        CloseHandle(v35);
      v6[17] = 0;
    }
    return v7;
  }
  v9 = v8 - 30;
  if ( !v9 )
  {
    if ( !WORD1(a5) || !this[17] )
      return v7;
    ImageW = (HCURSOR)LoadImageW(0, (LPCWSTR)0x7F8A, 2u, 0, 0, 0x8000u);
    SetCursor(ImageW);
    return 1;
  }
  v10 = (const struct _PSHNOTIFY *)(unsigned int)(v9 - 46);
  if ( !(_DWORD)v10 )
  {
    v23 = *((_DWORD *)a5 + 4);
    switch ( v23 )
    {
      case -759:
        if ( *((_QWORD *)a5 + 1) != 10010 )
          return v7;
        return CFciPropertiesShellExt::OnDateChange(
                 (CFciPropertiesShellExt *)this,
                 a2,
                 (const struct tagNMDATETIMECHANGE *)a5);
      case -722:
        if ( *((_QWORD *)a5 + 1) != 10006 )
          return v7;
        return CFciPropertiesShellExt::OnIntDeltaPos((CFciPropertiesShellExt *)this, a2, (const struct _NM_UPDOWN *)a5);
      case -202:
        return CFciPropertiesShellExt::OnApply((CFciPropertiesShellExt *)this, a2, v10);
      case -200:
        return CFciPropertiesShellExt::OnSetActive((CFciPropertiesShellExt *)this, a2, v10);
      case -187:
        if ( *((_QWORD *)a5 + 1) != 1001 )
          return v7;
        bstrString[0] = 0;
        CSrmComBSTR::LoadStringW((CSrmComBSTR *)bstrString, off_18002B230, *((_DWORD *)this + 55));
        *((_DWORD *)a5 + 6) = 1;
        v27 = 2147483646;
        v28 = bstrString[0];
        v29 = bstrString[0];
        v30 = 2084;
        v31 = (OLECHAR *)(a5 + 7);
        do
        {
          if ( !v27 )
            break;
          v32 = *v29;
          if ( !*v29 )
            break;
          ++v29;
          *v31++ = v32;
          --v27;
          --v30;
        }
        while ( v30 );
        v33 = v31 - 1;
        if ( v30 )
          v33 = v31;
        *v33 = 0;
        SysFreeString(v28);
        return 1;
      case -184:
        v25 = *(HWND *)a5;
        v26 = *((int *)a5 + 1077);
        if ( (unsigned int)SendMessageW(*(HWND *)a5, 0x105Cu, v26, 1) )
        {
          memset_0(&v38, 0, 0x98u);
          v42 = 1;
        }
        else
        {
          memset_0(&v38, 0, 0x98u);
          v42 = 0x100000001LL;
        }
        v38 = 0x400000098LL;
        SendMessageW(v25, 0x1093u, v26, (LPARAM)&v38);
        return v7;
      case -158:
        if ( *((_QWORD *)a5 + 1) == 1001 )
          return CFciPropertiesShellExt::OnPropertyGetInfoTip(
                   (CFciPropertiesShellExt *)this,
                   a2,
                   (const struct tagNMLVGETINFOTIPW *)a5);
        if ( *((_QWORD *)a5 + 1) != 10001 )
        {
          if ( *((_QWORD *)a5 + 1) == 10002 )
          {
            SelectedProperty = CFciPropertiesShellExt::GetSelectedProperty(a2);
            if ( !SelectedProperty || *((_DWORD *)SelectedProperty + 20) != 2 )
              return v7;
            memset_0(&v38, 0, 0x58u);
            v39 = 1;
            v41 = *((_DWORD *)a5 + 10);
            v40 = *((_QWORD *)a5 + 4);
            SendMessageW(*(HWND *)a5, 0x1073u, *((int *)a5 + 11), (LPARAM)&v38);
            return 1;
          }
          if ( *((_QWORD *)a5 + 1) != 10014 )
            return v7;
        }
        return CFciPropertiesShellExt::OnSingleSelectionGetInfoTip(
                 (CFciPropertiesShellExt *)this,
                 a2,
                 (const struct tagNMLVGETINFOTIPW *)a5);
    }
    if ( v23 != -101 )
      return v7;
    if ( *((_QWORD *)a5 + 1) != 1001 )
    {
      if ( *((_QWORD *)a5 + 1) != 10001 )
      {
        if ( *((_QWORD *)a5 + 1) == 10002 )
          return CFciPropertiesShellExt::OnMultiChoiceItemChanged(
                   (CFciPropertiesShellExt *)this,
                   a2,
                   (const struct tagNMLISTVIEW *)a5);
        if ( *((_QWORD *)a5 + 1) != 10014 )
          return v7;
      }
      return CFciPropertiesShellExt::OnSingleSelectionItemChanged(
               (CFciPropertiesShellExt *)this,
               a2,
               (const struct tagNMLISTVIEW *)a5);
    }
    if ( ((_BYTE)a5[10] & 8) == 0 )
      return v7;
    if ( ((_BYTE)a5[8] & 2) != 0 )
    {
      if ( ((_BYTE)a5[9] & 2) != 0 )
        return v7;
      v21 = (struct CFciPropertiesShellExt::PropertyInfo *)*((_QWORD *)a5 + 7);
      if ( !v21 )
        return v7;
    }
    else
    {
      if ( ((_BYTE)a5[9] & 2) == 0 )
        return v7;
      v21 = 0;
    }
    v20 = 0;
    goto LABEL_39;
  }
  v11 = (_DWORD)v10 - 194;
  if ( !v11 )
  {
    DlgItem = GetDlgItem(a2, 1001);
    CFciPropertiesShellExt::SetupPropertiesListView(DlgItem);
    SendDlgItemMessageW(v5, 1007, 0x160Cu, 0, 1);
    return 1;
  }
  v12 = (unsigned int)(v11 - 1);
  if ( !(_DWORD)v12 )
  {
    if ( WORD1(a4) )
    {
      if ( WORD1(a4) != 256 && WORD1(a4) != 512 )
      {
        if ( WORD1(a4) != 768 )
          return v7;
        if ( (unsigned __int16)a4 == 10003 )
          return CFciPropertiesShellExt::OnEditStringChange((CFciPropertiesShellExt *)this, a2, a5);
        if ( (unsigned __int16)a4 == 10004 )
          return CFciPropertiesShellExt::OnEditMultiStringChange((CFciPropertiesShellExt *)this, a2, a5);
        if ( (unsigned __int16)a4 != 10005 )
          return v7;
        return CFciPropertiesShellExt::OnEditIntChange((CFciPropertiesShellExt *)this, a2, a5);
      }
      if ( (unsigned __int16)a4 != 10003 && (unsigned int)(unsigned __int16)a4 - 10004 > 1 )
        return v7;
      v14 = CFciPropertiesShellExt::GetSelectedProperty(a2);
      if ( !v14 || *((_DWORD *)v14 + 20) != 4 && (unsigned int)(*((_DWORD *)v14 + 20) - 5) > 1 )
        return v7;
      CFciPropertiesShellExt::SetTextValue((CFciPropertiesShellExt *)v6, a5, v14);
      return 1;
    }
    v15 = (unsigned __int16)a4;
    if ( (unsigned __int16)a4 != 1006 )
    {
      if ( (unsigned __int16)a4 != 1007 )
      {
        if ( (unsigned __int16)a4 == 1012 )
          return CFciPropertiesShellExt::OnClickContinue((CFciPropertiesShellExt *)this, a2, (HWND)v12);
        if ( (unsigned __int16)a4 == 10007 || (unsigned int)(unsigned __int16)a4 - 10008 <= 1 )
        {
          CheckRadioButton(a2, 10007, 10009, (unsigned __int16)a4);
          return CFciPropertiesShellExt::OnBoolChange((CFciPropertiesShellExt *)v6, v5, v15);
        }
        return v7;
      }
      CFciPropertiesShellExt::ShowElevated((CFciPropertiesShellExt *)this, a2);
      return 1;
    }
    v16 = CFciPropertiesShellExt::GetSelectedProperty(a2);
    v17 = v16;
    if ( !v16 )
      return 0;
    *((_DWORD *)v16 + 52) = 4;
    if ( *((_QWORD *)v16 + 24) < 8u )
      v18 = (_WORD *)((char *)v16 + 168);
    else
      v18 = (_WORD *)*((_QWORD *)v16 + 21);
    *((_QWORD *)v16 + 23) = 0;
    *v18 = 0;
    v19 = GetDlgItem(v5, 1006);
    EnableWindow(v19, 0);
    v20 = 1;
    v21 = v17;
    a2 = v5;
    this = v6;
LABEL_39:
    CFciPropertiesShellExt::UpdatePage(this, a2, v21, v20);
    return 1;
  }
  if ( (_DWORD)v12 == 32495 )
    return CFciPropertiesShellExt::OnFciPropsInitDone((CFciPropertiesShellExt *)this, a2, v12, a4);
  return v7;
}

```

## disassembly

```asm
0x180007290  push    rbp
0x180007292  push    rbx
0x180007293  push    rsi
0x180007294  push    rdi
0x180007295  push    r12
0x180007297  push    r15
0x180007299  lea     rbp, [rsp-27h]
0x18000729e  sub     rsp, 0E8h
0x1800072a5  mov     r15, rdx
0x1800072a8  mov     rsi, rcx
0x1800072ab  xor     r12d, r12d
0x1800072ae  mov     ebx, r12d
0x1800072b1  sub     r8d, 2
0x1800072b5  jz      loc_1800077FD
0x1800072bb  sub     r8d, 1Eh
0x1800072bf  jz      loc_1800077AF
0x1800072c5  sub     r8d, 2Eh ; '.'; struct _PSHNOTIFY *
0x1800072c9  jz      loc_1800074ED
0x1800072cf  sub     r8d, 0C2h
0x1800072d6  jz      loc_1800074AD
0x1800072dc  sub     r8d, 1; HWND
0x1800072e0  jz      short loc_1800072FC
0x1800072e2  cmp     r8d, 7EEFh
0x1800072e9  jnz     loc_180007854
0x1800072ef  call    ?OnFciPropsInitDone@CFciPropertiesShellExt@@AEAA_JPEAUHWND__@@_K_J@Z; CFciPropertiesShellExt::OnFciPropsInitDone(HWND__ *,unsigned __int64,__int64)
0x1800072f4  mov     rbx, rax
0x1800072f7  jmp     loc_180007854
0x1800072fc  mov     rax, r9
0x1800072ff  shr     rax, 10h
0x180007303  test    ax, ax
0x180007306  jz      loc_1800073C7
0x18000730c  mov     ecx, 100h
0x180007311  cmp     ax, cx
0x180007314  jz      short loc_180007372
0x180007316  mov     ecx, 200h
0x18000731b  cmp     ax, cx
0x18000731e  jz      short loc_180007372
0x180007320  mov     ecx, 300h
0x180007325  cmp     ax, cx
0x180007328  jnz     loc_180007854
0x18000732e  movzx   ecx, r9w
0x180007332  sub     ecx, 2713h
0x180007338  jz      short loc_180007364
0x18000733a  sub     ecx, 1
0x18000733d  jz      short loc_180007356
0x18000733f  cmp     ecx, 1
0x180007342  jnz     loc_180007854
0x180007348  mov     r8, [rbp+4Fh+arg_20]; HWND
0x18000734c  mov     rcx, rsi; this
0x18000734f  call    ?OnEditIntChange@CFciPropertiesShellExt@@AEAA_JPEAUHWND__@@0@Z; CFciPropertiesShellExt::OnEditIntChange(HWND__ *,HWND__ *)
0x180007354  jmp     short loc_1800072F4
0x180007356  mov     r8, [rbp+4Fh+arg_20]; HWND
0x18000735a  mov     rcx, rsi; this
0x18000735d  call    ?OnEditMultiStringChange@CFciPropertiesShellExt@@AEAA_JPEAUHWND__@@0@Z; CFciPropertiesShellExt::OnEditMultiStringChange(HWND__ *,HWND__ *)
0x180007362  jmp     short loc_1800072F4
0x180007364  mov     r8, [rbp+4Fh+arg_20]; HWND
0x180007368  mov     rcx, rsi; this
0x18000736b  call    ?OnEditStringChange@CFciPropertiesShellExt@@AEAA_JPEAUHWND__@@0@Z; CFciPropertiesShellExt::OnEditStringChange(HWND__ *,HWND__ *)
0x180007370  jmp     short loc_1800072F4
0x180007372  movzx   ecx, r9w
0x180007376  sub     ecx, 2713h
0x18000737c  jz      short loc_18000738C
0x18000737e  sub     ecx, 1
0x180007381  jz      short loc_18000738C
0x180007383  cmp     ecx, 1
0x180007386  jnz     loc_180007854
0x18000738c  mov     rcx, r15; HWND
0x18000738f  call    ?GetSelectedProperty@CFciPropertiesShellExt@@CAPEAUPropertyInfo@1@PEAUHWND__@@@Z; CFciPropertiesShellExt::GetSelectedProperty(HWND__ *)
0x180007394  test    rax, rax
0x180007397  mov     r8, rax; struct CFciPropertiesShellExt::PropertyInfo *
0x18000739a  jz      loc_180007854
0x1800073a0  mov     ecx, [rax+50h]
0x1800073a3  sub     ecx, 4
0x1800073a6  jz      short loc_1800073B6
0x1800073a8  sub     ecx, 1
0x1800073ab  jz      short loc_1800073B6
0x1800073ad  cmp     ecx, 1
0x1800073b0  jnz     loc_180007854
0x1800073b6  mov     rdx, [rbp+4Fh+arg_20]; HWND
0x1800073ba  mov     rcx, rsi; this
0x1800073bd  call    ?SetTextValue@CFciPropertiesShellExt@@AEAAXPEAUHWND__@@AEBUPropertyInfo@1@@Z; CFciPropertiesShellExt::SetTextValue(HWND__ *,CFciPropertiesShellExt::PropertyInfo const &)
0x1800073c2  jmp     loc_1800074E3
0x1800073c7  movzx   edi, r9w
0x1800073cb  mov     ecx, edi
0x1800073cd  sub     ecx, 3EEh
0x1800073d3  jz      short loc_180007437
0x1800073d5  sub     ecx, 1
0x1800073d8  jz      short loc_18000742A
0x1800073da  sub     ecx, 5
0x1800073dd  jz      short loc_18000741D
0x1800073df  sub     ecx, 2323h
0x1800073e5  jz      short loc_1800073F5
0x1800073e7  sub     ecx, 1
0x1800073ea  jz      short loc_1800073F5
0x1800073ec  cmp     ecx, 1
0x1800073ef  jnz     loc_180007854
0x1800073f5  mov     r9d, edi; nIDCheckButton
0x1800073f8  mov     edx, 2717h; nIDFirstButton
0x1800073fd  lea     r8d, [rdx+2]; nIDLastButton
0x180007401  mov     rcx, r15; hDlg
0x180007404  call    cs:__imp_CheckRadioButton
0x18000740a  mov     r8d, edi; int
0x18000740d  mov     rdx, r15; HWND
0x180007410  mov     rcx, rsi; this
0x180007413  call    ?OnBoolChange@CFciPropertiesShellExt@@AEAA_JPEAUHWND__@@H@Z; CFciPropertiesShellExt::OnBoolChange(HWND__ *,int)
0x180007418  jmp     loc_1800072F4
0x18000741d  mov     rcx, rsi; this
0x180007420  call    ?OnClickContinue@CFciPropertiesShellExt@@AEAA_JPEAUHWND__@@0@Z; CFciPropertiesShellExt::OnClickContinue(HWND__ *,HWND__ *)
0x180007425  jmp     loc_1800072F4
0x18000742a  mov     rcx, rsi; this
0x18000742d  call    ?ShowElevated@CFciPropertiesShellExt@@AEAA_NPEAUHWND__@@@Z; CFciPropertiesShellExt::ShowElevated(HWND__ *)
0x180007432  jmp     loc_1800074E3
0x180007437  mov     rcx, r15; HWND
0x18000743a  call    ?GetSelectedProperty@CFciPropertiesShellExt@@CAPEAUPropertyInfo@1@PEAUHWND__@@@Z; CFciPropertiesShellExt::GetSelectedProperty(HWND__ *)
0x18000743f  mov     rbx, rax
0x180007442  test    rax, rax
0x180007445  jnz     short loc_18000744F
0x180007447  mov     rbx, r12
0x18000744a  jmp     loc_180007854
0x18000744f  mov     dword ptr [rax+0D0h], 4
0x180007459  cmp     qword ptr [rax+0C0h], 8
0x180007461  jb      short loc_18000746C
0x180007463  mov     rcx, [rax+0A8h]
0x18000746a  jmp     short loc_180007473
0x18000746c  lea     rcx, [rax+0A8h]
0x180007473  mov     [rax+0B8h], r12
0x18000747a  mov     [rcx], r12w
0x18000747e  mov     edx, 3EEh; nIDDlgItem
0x180007483  mov     rcx, r15; hDlg
0x180007486  call    cs:__imp_GetDlgItem
0x18000748c  xor     edx, edx; bEnable
0x18000748e  mov     rcx, rax; hWnd
0x180007491  call    cs:__imp_EnableWindow
0x180007497  mov     r9d, 1
0x18000749d  mov     r8, rbx
0x1800074a0  mov     rdx, r15
0x1800074a3  mov     rcx, rsi
0x1800074a6  call    ?UpdatePage@CFciPropertiesShellExt@@AEAAXPEAUHWND__@@PEBUPropertyInfo@1@W4UpdatePageReason@1@@Z; CFciPropertiesShellExt::UpdatePage(HWND__ *,CFciPropertiesShellExt::PropertyInfo const *,CFciPropertiesShellExt::UpdatePageReason)
0x1800074ab  jmp     short loc_1800074E3
0x1800074ad  mov     edx, 3E9h; nIDDlgItem
0x1800074b2  mov     rcx, r15; hDlg
0x1800074b5  call    cs:__imp_GetDlgItem
0x1800074bb  mov     rcx, rax; hWnd
0x1800074be  call    ?SetupPropertiesListView@CFciPropertiesShellExt@@CAXPEAUHWND__@@@Z; CFciPropertiesShellExt::SetupPropertiesListView(HWND__ *)
0x1800074c3  mov     [rsp+110h+lParam], 1; lParam
0x1800074cc  xor     r9d, r9d; wParam
0x1800074cf  mov     edx, 3EFh; nIDDlgItem
0x1800074d4  mov     r8d, 160Ch; Msg
0x1800074da  mov     rcx, r15; hDlg
0x1800074dd  call    cs:__imp_SendDlgItemMessageW
0x1800074e3  mov     ebx, 1
0x1800074e8  jmp     loc_180007854
0x1800074ed  mov     rdi, [rbp+4Fh+arg_20]
0x1800074f1  mov     eax, [rdi+10h]
0x1800074f4  cmp     eax, 0FFFFFD09h
0x1800074f9  jz      loc_180007794
0x1800074ff  cmp     eax, 0FFFFFD2Eh
0x180007504  jz      loc_180007779
0x18000750a  cmp     eax, 0FFFFFF36h
0x18000750f  jz      loc_18000776F
0x180007515  cmp     eax, 0FFFFFF38h
0x18000751a  jz      loc_180007765
0x180007520  cmp     eax, 0FFFFFF45h
0x180007525  jz      loc_1800076DF
0x18000752b  cmp     eax, 0FFFFFF48h
0x180007530  jz      loc_180007663
0x180007536  cmp     eax, 0FFFFFF62h
0x18000753b  jz      loc_1800075C5
0x180007541  cmp     eax, 0FFFFFF9Bh
0x180007544  jnz     loc_180007854
0x18000754a  mov     rax, [rdi+8]
0x18000754e  sub     rax, 3E9h
0x180007554  jz      short loc_180007588
0x180007556  sub     rax, 2328h
0x18000755c  jz      short loc_18000756E
0x18000755e  sub     rax, 1
0x180007562  jz      short loc_18000757B
0x180007564  cmp     rax, 0Ch
0x180007568  jnz     loc_180007854
0x18000756e  mov     r8, rdi; struct tagNMLISTVIEW *
0x180007571  call    ?OnSingleSelectionItemChanged@CFciPropertiesShellExt@@AEAA_JPEAUHWND__@@PEBUtagNMLISTVIEW@@@Z; CFciPropertiesShellExt::OnSingleSelectionItemChanged(HWND__ *,tagNMLISTVIEW const *)
0x180007576  jmp     loc_1800072F4
0x18000757b  mov     r8, rdi; struct tagNMLISTVIEW *
0x18000757e  call    ?OnMultiChoiceItemChanged@CFciPropertiesShellExt@@AEAA_JPEAUHWND__@@PEBUtagNMLISTVIEW@@@Z; CFciPropertiesShellExt::OnMultiChoiceItemChanged(HWND__ *,tagNMLISTVIEW const *)
0x180007583  jmp     loc_1800072F4
0x180007588  test    byte ptr [rdi+28h], 8
0x18000758c  jz      loc_180007854
0x180007592  test    byte ptr [rdi+20h], 2
0x180007596  jz      short loc_1800075B0
0x180007598  test    byte ptr [rdi+24h], 2
0x18000759c  jnz     loc_180007854
0x1800075a2  mov     r8, [rdi+38h]
0x1800075a6  test    r8, r8
0x1800075a9  jnz     short loc_1800075BD
0x1800075ab  jmp     loc_180007854
0x1800075b0  test    byte ptr [rdi+24h], 2
0x1800075b4  jz      loc_180007854
0x1800075ba  mov     r8, r12
0x1800075bd  xor     r9d, r9d
0x1800075c0  jmp     loc_1800074A6
0x1800075c5  mov     rax, [rdi+8]
0x1800075c9  sub     rax, 3E9h
0x1800075cf  jz      loc_180007656
0x1800075d5  sub     rax, 2328h
0x1800075db  jz      short loc_1800075ED
0x1800075dd  sub     rax, 1
0x1800075e1  jz      short loc_1800075FA
0x1800075e3  cmp     rax, 0Ch
0x1800075e7  jnz     loc_180007854
0x1800075ed  mov     r8, rdi; struct tagNMLVGETINFOTIPW *
0x1800075f0  call    ?OnSingleSelectionGetInfoTip@CFciPropertiesShellExt@@AEAA_JPEAUHWND__@@PEBUtagNMLVGETINFOTIPW@@@Z; CFciPropertiesShellExt::OnSingleSelectionGetInfoTip(HWND__ *,tagNMLVGETINFOTIPW const *)
0x1800075f5  jmp     loc_1800072F4
0x1800075fa  mov     rcx, r15; HWND
0x1800075fd  call    ?GetSelectedProperty@CFciPropertiesShellExt@@CAPEAUPropertyInfo@1@PEAUHWND__@@@Z; CFciPropertiesShellExt::GetSelectedProperty(HWND__ *)
0x180007602  test    rax, rax
0x180007605  jz      loc_180007854
0x18000760b  cmp     dword ptr [rax+50h], 2
0x18000760f  jnz     loc_180007854
0x180007615  xor     edx, edx; Val
0x180007617  lea     r8d, [rdx+58h]; Size
0x18000761b  lea     rcx, [rsp+110h+var_D0]; void *
0x180007620  call    memset_0
0x180007625  mov     [rbp+4Fh+var_C8], 1
0x18000762c  mov     eax, [rdi+28h]
0x18000762f  mov     [rbp+4Fh+var_B0], eax
0x180007632  mov     rax, [rdi+20h]
0x180007636  mov     [rbp+4Fh+var_B8], rax
0x18000763a  movsxd  r8, dword ptr [rdi+2Ch]; wParam
0x18000763e  lea     r9, [rsp+110h+var_D0]; lParam
0x180007643  mov     edx, 1073h; Msg
0x180007648  mov     rcx, [rdi]; hWnd
0x18000764b  call    cs:__imp_SendMessageW
0x180007651  jmp     loc_1800074E3
0x180007656  mov     r8, rdi; struct tagNMLVGETINFOTIPW *
0x180007659  call    ?OnPropertyGetInfoTip@CFciPropertiesShellExt@@AEAA_JPEAUHWND__@@PEBUtagNMLVGETINFOTIPW@@@Z; CFciPropertiesShellExt::OnPropertyGetInfoTip(HWND__ *,tagNMLVGETINFOTIPW const *)
0x18000765e  jmp     loc_1800072F4
0x180007663  mov     rsi, [rdi]
0x180007666  movsxd  r15, dword ptr [rdi+10D4h]
0x18000766d  mov     r9d, 1; lParam
0x180007673  mov     r8, r15; wParam
0x180007676  mov     edx, 105Ch; Msg
0x18000767b  mov     rcx, rsi; hWnd
0x18000767e  call    cs:__imp_SendMessageW
0x180007684  mov     edi, 98h
0x180007689  xor     edx, edx; Val
0x18000768b  lea     rcx, [rsp+110h+var_D0]; void *
0x180007690  mov     r8d, edi; Size
0x180007693  test    eax, eax
0x180007695  jz      short loc_1800076CA
0x180007697  call    memset_0
0x18000769c  mov     [rbp+4Fh+var_A8], 1
0x1800076a4  mov     dword ptr [rbp+4Fh+var_D0+4], 4
0x1800076ab  mov     dword ptr [rsp+110h+var_D0], edi
0x1800076af  lea     r9, [rsp+110h+var_D0]; lParam
0x1800076b4  mov     r8, r15; wParam
0x1800076b7  mov     edx, 1093h; Msg
0x1800076bc  mov     rcx, rsi; hWnd
0x1800076bf  call    cs:__imp_SendMessageW
0x1800076c5  jmp     loc_180007854
0x1800076ca  call    memset_0
0x1800076cf  mov     dword ptr [rbp+4Fh+var_A8], 1
0x1800076d6  mov     dword ptr [rbp+4Fh+var_A8+4], 1
0x1800076dd  jmp     short loc_1800076A4
0x1800076df  cmp     qword ptr [rdi+8], 3E9h
0x1800076e7  jnz     loc_180007854
0x1800076ed  mov     [rsp+110h+bstrString], r12
0x1800076f2  mov     r8d, [rcx+0DCh]; unsigned int
0x1800076f9  mov     rdx, cs:off_18002B230; HINSTANCE
0x180007700  lea     rcx, [rsp+110h+bstrString]; this
0x180007705  call    ?LoadStringW@CSrmComBSTR@@QEAA_NPEAUHINSTANCE__@@I@Z; CSrmComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x18000770a  mov     dword ptr [rdi+18h], 1
0x180007711  mov     edx, 7FFFFFFEh
0x180007716  mov     rcx, [rsp+110h+bstrString]; bstrString
0x18000771b  mov     r8, rcx
0x18000771e  mov     eax, 824h
0x180007723  add     rdi, 1Ch
0x180007727  test    rdx, rdx
0x18000772a  jz      short loc_18000774B
0x18000772c  movzx   r9d, word ptr [r8]
0x180007730  test    r9w, r9w
0x180007734  jz      short loc_18000774B
0x180007736  add     r8, 2
0x18000773a  mov     [rdi], r9w
0x18000773e  add     rdi, 2
0x180007742  dec     rdx
0x180007745  sub     rax, 1
0x180007749  jnz     short loc_180007727
0x18000774b  lea     rdx, [rdi-2]
0x18000774f  test    rax, rax
0x180007752  cmovnz  rdx, rdi
0x180007756  mov     [rdx], r12w
0x18000775a  call    cs:__imp_SysFreeString
0x180007760  jmp     loc_1800074E3
0x180007765  call    ?OnSetActive@CFciPropertiesShellExt@@AEAA_JPEAUHWND__@@PEBU_PSHNOTIFY@@@Z; CFciPropertiesShellExt::OnSetActive(HWND__ *,_PSHNOTIFY const *)
0x18000776a  jmp     loc_1800072F4
0x18000776f  call    ?OnApply@CFciPropertiesShellExt@@AEAA_JPEAUHWND__@@PEBU_PSHNOTIFY@@@Z; CFciPropertiesShellExt::OnApply(HWND__ *,_PSHNOTIFY const *)
0x180007774  jmp     loc_1800072F4
0x180007779  cmp     qword ptr [rdi+8], 2716h
0x180007781  jnz     loc_180007854
0x180007787  mov     r8, rdi; struct _NM_UPDOWN *
  ... truncated ...
```
