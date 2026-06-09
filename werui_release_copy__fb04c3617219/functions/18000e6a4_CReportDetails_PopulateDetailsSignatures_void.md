# CReportDetails::PopulateDetailsSignatures(void)

- ea: `0x18000e6a4`
- end: `0x18000ea83`
- name: `?PopulateDetailsSignatures@CReportDetails@@AEAAJXZ`
- size: `991`
- prototype: `__int64 __fastcall(CReportDetails *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000e348`

## callees

- `0x180003604`
- `0x180005c80`
- `0x180008f3c`
- `0x180009580`
- `0x1800095a8`
- `0x1800095d0`
- `0x1800096a8`
- `0x18000979c`
- `0x18000e6a4`
- `0x180016c1e`
- `0x180016c50`

## import_xrefs

- `wer!WerpGetDynamicParameter` at `0x18000e961`
- `wer!WerpGetDynamicParameter` at `0x18000e961`
- `wer!WerpGetNumSigParams` at `0x18000e71a`
- `wer!WerpGetNumSigParams` at `0x18000e71a`
- `wer!WerpGetSigParamByIndex` at `0x18000e8b0`
- `wer!WerpGetSigParamByIndex` at `0x18000e8b0`
- `wer!WerpGetEventType` at `0x18000e830`
- `wer!WerpGetEventType` at `0x18000e830`
- `USER32!GetSysColor` at `0x18000e78d`
- `USER32!GetSysColor` at `0x18000ea16`
- `USER32!GetSysColor` at `0x18000e78d`
- `USER32!GetSysColor` at `0x18000ea16`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000e7a5`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000e7ba`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000ea2e`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000ea43`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000e7a5`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000e7ba`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000ea2e`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000ea43`

## pseudocode

```c
__int64 __fastcall CReportDetails::PopulateDetailsSignatures(CReportDetails *this)
{
  int NumSigParams; // edi
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  DWORD SysColor; // eax
  HWND v6; // rcx
  unsigned int i; // edi
  __int64 v8; // rcx
  unsigned int j; // edi
  __int64 v10; // rcx
  DWORD v11; // eax
  HWND v12; // rcx
  unsigned int v14; // [rsp+20h] [rbp-89h] BYREF
  __int64 v15; // [rsp+28h] [rbp-81h] BYREF
  __int64 v16; // [rsp+30h] [rbp-79h] BYREF
  LPARAM v17[4]; // [rsp+38h] [rbp-71h] BYREF
  __int64 v18; // [rsp+58h] [rbp-51h] BYREF
  __int64 v19; // [rsp+60h] [rbp-49h]
  __int64 v20; // [rsp+78h] [rbp-31h] BYREF
  _BYTE lParam[12]; // [rsp+80h] [rbp-29h] BYREF
  DWORD v22; // [rsp+94h] [rbp-15h]

  memset_0(lParam, 0, 0x5Cu);
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v20 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v17);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&v18);
  NumSigParams = WerpGetNumSigParams(*((_QWORD *)this + 4), &v14);
  if ( NumSigParams >= 0 )
  {
    UtilLoadString(v17, 216);
    *(_QWORD *)lParam = 0x400000010000005CLL;
    *(_DWORD *)&lParam[8] = 1;
    SysColor = GetSysColor(26);
    v6 = *(HWND *)this;
    v22 = SysColor;
    SendMessageW(v6, 0x444u, 1u, (LPARAM)lParam);
    SendMessageW(*(HWND *)this, 0xC2u, 0, v17[0]);
    v17[1] = v17[0];
    *(_WORD *)v17[0] = 0;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
      v17,
      L"  ",
      2);
    UtilLoadString(&v18, 268);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(
      &v18,
      58);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
      &v18,
      L"\t",
      1);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
      v17,
      v18,
      (v19 - v18) >> 1);
    NumSigParams = WerpGetEventType(*((_QWORD *)this + 4), &v20);
    if ( NumSigParams >= 0 )
    {
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
        v17,
        v20);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
        v17,
        L"\r\n",
        2);
      for ( i = 0; i < v14; ++i )
      {
        v8 = *((_QWORD *)this + 4);
        v16 = 0;
        v15 = 0;
        if ( (int)WerpGetSigParamByIndex(v8, i, &v16, &v15) >= 0 )
        {
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
            v17,
            L"  ",
            2);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
            &v18,
            v15);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(
            &v18,
            58);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
            &v18,
            L"\t",
            1);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
            v17,
            v18,
            (v19 - v18) >> 1);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
            v17,
            v16);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
            v17,
            L"\r\n",
            2);
        }
      }
      for ( j = 0; j < 0x36; ++j )
      {
        v10 = *((_QWORD *)this + 4);
        v16 = 0;
        v15 = 0;
        if ( (int)WerpGetDynamicParameter(v10, j, &v15, &v16) >= 0 )
        {
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
            v17,
            L"  ",
            2);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
            &v18,
            v15);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(
            &v18,
            58);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
            &v18,
            L"\t",
            1);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
            v17,
            v18,
            (v19 - v18) >> 1);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
            v17,
            v16);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
            v17,
            L"\r\n",
            2);
        }
      }
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
        v17,
        L"\r\n",
        2);
      *(_DWORD *)lParam = 92;
      *(_QWORD *)&lParam[4] = 1073741825;
      v11 = GetSysColor(8);
      v12 = *(HWND *)this;
      v22 = v11;
      SendMessageW(v12, 0x444u, 1u, (LPARAM)lParam);
      SendMessageW(*(HWND *)this, 0xC2u, 0, v17[0]);
      NumSigParams = 0;
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 16;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 15;
LABEL_5:
      WPP_SF_d(v3[2], v4, &WPP_d630dad542cd30ddeb64ab72592d0c50_Traceguids, (unsigned int)NumSigParams);
    }
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v18);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v17);
  return (unsigned int)NumSigParams;
}

```

## disassembly

```asm
0x18000e6a4  mov     [rsp-8+arg_8], rbx
0x18000e6a9  mov     [rsp-8+arg_10], rsi
0x18000e6ae  push    rbp
0x18000e6af  push    rdi
0x18000e6b0  push    r15
0x18000e6b2  lea     rbp, [rsp-47h]
0x18000e6b7  sub     rsp, 0F0h
0x18000e6be  mov     rax, cs:__security_cookie
0x18000e6c5  xor     rax, rsp
0x18000e6c8  mov     [rbp+57h+var_20], rax
0x18000e6cc  xor     edx, edx; Val
0x18000e6ce  mov     rsi, rcx
0x18000e6d1  lea     rcx, [rbp+57h+lParam]; void *
0x18000e6d5  lea     r8d, [rdx+5Ch]; Size
0x18000e6d9  call    memset_0
0x18000e6de  lea     rcx, [rbp+57h+var_C8]; void *
0x18000e6e2  mov     [rsp+100h+var_E0], 0
0x18000e6ea  mov     [rsp+100h+var_D8], 0
0x18000e6f3  mov     [rbp+57h+var_D0], 0
0x18000e6fb  mov     [rbp+57h+var_88], 0
0x18000e703  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x18000e708  lea     rcx, [rbp+57h+var_A8]; void *
0x18000e70c  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x18000e711  mov     rcx, [rsi+20h]
0x18000e715  lea     rdx, [rsp+100h+var_E0]
0x18000e71a  call    cs:__imp_WerpGetNumSigParams
0x18000e720  mov     edi, eax
0x18000e722  test    eax, eax
0x18000e724  jns     short loc_18000E766
0x18000e726  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e72d  lea     rax, WPP_GLOBAL_Control
0x18000e734  cmp     rcx, rax
0x18000e737  jz      loc_18000EA4B
0x18000e73d  mov     ebx, 1
0x18000e742  test    [rcx+1Ch], bl
0x18000e745  jz      loc_18000EA4B
0x18000e74b  lea     edx, [rbx+0Eh]
0x18000e74e  mov     rcx, [rcx+10h]
0x18000e752  lea     r8, WPP_d630dad542cd30ddeb64ab72592d0c50_Traceguids
0x18000e759  mov     r9d, edi
0x18000e75c  call    WPP_SF_d
0x18000e761  jmp     loc_18000EA4B
0x18000e766  mov     edx, 0D8h
0x18000e76b  lea     rcx, [rbp+57h+var_C8]
0x18000e76f  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x18000e774  mov     ebx, 1
0x18000e779  mov     dword ptr [rbp+57h+lParam], 5Ch ; '\'
0x18000e780  mov     dword ptr [rbp+57h+lParam+4], 40000001h
0x18000e787  mov     [rbp-21h], ebx
0x18000e78a  lea     ecx, [rbx+19h]; nIndex
0x18000e78d  call    cs:__imp_GetSysColor
0x18000e793  mov     rcx, [rsi]; hWnd
0x18000e796  lea     r9, [rbp+57h+lParam]; lParam
0x18000e79a  mov     r8d, ebx; wParam
0x18000e79d  mov     [rbp+57h+var_6C], eax
0x18000e7a0  mov     edx, 444h; Msg
0x18000e7a5  call    cs:__imp_SendMessageW
0x18000e7ab  mov     r9, [rbp+57h+var_C8]; lParam
0x18000e7af  xor     r8d, r8d; wParam
0x18000e7b2  mov     rcx, [rsi]; hWnd
0x18000e7b5  mov     edx, 0C2h; Msg
0x18000e7ba  call    cs:__imp_SendMessageW
0x18000e7c0  mov     rcx, [rbp+57h+var_C8]
0x18000e7c4  lea     r15d, [rbx+1]
0x18000e7c8  mov     [rbp+57h+var_C0], rcx
0x18000e7cc  lea     rdx, asc_18001B348; "  "
0x18000e7d3  xor     eax, eax
0x18000e7d5  mov     r8d, r15d
0x18000e7d8  mov     [rcx], ax
0x18000e7db  lea     rcx, [rbp+57h+var_C8]
0x18000e7df  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000e7e4  mov     edx, 10Ch
0x18000e7e9  lea     rcx, [rbp+57h+var_A8]
0x18000e7ed  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x18000e7f2  lea     edx, [rbx+39h]
0x18000e7f5  lea     rcx, [rbp+57h+var_A8]
0x18000e7f9  call    ?push_back@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::push_back(ushort)
0x18000e7fe  mov     r8d, ebx
0x18000e801  lea     rdx, asc_18001B364; "\t"
0x18000e808  lea     rcx, [rbp+57h+var_A8]
0x18000e80c  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000e811  mov     r8, [rbp+57h+var_A0]
0x18000e815  lea     rcx, [rbp+57h+var_C8]
0x18000e819  mov     rdx, [rbp+57h+var_A8]
0x18000e81d  sub     r8, rdx
0x18000e820  sar     r8, 1
0x18000e823  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000e828  mov     rcx, [rsi+20h]
0x18000e82c  lea     rdx, [rbp+57h+var_88]
0x18000e830  call    cs:__imp_WerpGetEventType
0x18000e836  mov     edi, eax
0x18000e838  test    eax, eax
0x18000e83a  jns     short loc_18000E864
0x18000e83c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e843  lea     rax, WPP_GLOBAL_Control
0x18000e84a  cmp     rcx, rax
0x18000e84d  jz      loc_18000EA4B
0x18000e853  test    [rcx+1Ch], bl
0x18000e856  jz      loc_18000EA4B
0x18000e85c  lea     edx, [rbx+0Fh]
0x18000e85f  jmp     loc_18000E74E
0x18000e864  mov     rdx, [rbp+57h+var_88]
0x18000e868  lea     rcx, [rbp+57h+var_C8]
0x18000e86c  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18000e871  mov     r8, r15
0x18000e874  lea     rdx, asc_18001B350; "\r\n"
0x18000e87b  lea     rcx, [rbp+57h+var_C8]
0x18000e87f  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000e884  xor     edi, edi
0x18000e886  cmp     [rsp+100h+var_E0], edi
0x18000e88a  jbe     loc_18000E93F
0x18000e890  mov     rcx, [rsi+20h]
0x18000e894  lea     r9, [rsp+100h+var_D8]
0x18000e899  lea     r8, [rbp+57h+var_D0]
0x18000e89d  mov     [rbp+57h+var_D0], 0
0x18000e8a5  mov     edx, edi
0x18000e8a7  mov     [rsp+100h+var_D8], 0
0x18000e8b0  call    cs:__imp_WerpGetSigParamByIndex
0x18000e8b6  test    eax, eax
0x18000e8b8  js      short loc_18000E933
0x18000e8ba  mov     r8, r15
0x18000e8bd  lea     rdx, asc_18001B348; "  "
0x18000e8c4  lea     rcx, [rbp+57h+var_C8]
0x18000e8c8  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000e8cd  mov     rdx, [rsp+100h+var_D8]
0x18000e8d2  lea     rcx, [rbp+57h+var_A8]
0x18000e8d6  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000e8db  mov     edx, 3Ah ; ':'
0x18000e8e0  lea     rcx, [rbp+57h+var_A8]
0x18000e8e4  call    ?push_back@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::push_back(ushort)
0x18000e8e9  mov     r8, rbx
0x18000e8ec  lea     rdx, asc_18001B364; "\t"
0x18000e8f3  lea     rcx, [rbp+57h+var_A8]
0x18000e8f7  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000e8fc  mov     r8, [rbp+57h+var_A0]
0x18000e900  lea     rcx, [rbp+57h+var_C8]
0x18000e904  mov     rdx, [rbp+57h+var_A8]
0x18000e908  sub     r8, rdx
0x18000e90b  sar     r8, 1
0x18000e90e  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000e913  mov     rdx, [rbp+57h+var_D0]
0x18000e917  lea     rcx, [rbp+57h+var_C8]
0x18000e91b  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18000e920  mov     r8, r15
0x18000e923  lea     rdx, asc_18001B350; "\r\n"
0x18000e92a  lea     rcx, [rbp+57h+var_C8]
0x18000e92e  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000e933  add     edi, ebx
0x18000e935  cmp     edi, [rsp+100h+var_E0]
0x18000e939  jb      loc_18000E890
0x18000e93f  xor     edi, edi
0x18000e941  mov     rcx, [rsi+20h]
0x18000e945  lea     r9, [rbp+57h+var_D0]
0x18000e949  lea     r8, [rsp+100h+var_D8]
0x18000e94e  mov     [rbp+57h+var_D0], 0
0x18000e956  mov     edx, edi
0x18000e958  mov     [rsp+100h+var_D8], 0
0x18000e961  call    cs:__imp_WerpGetDynamicParameter
0x18000e967  test    eax, eax
0x18000e969  js      short loc_18000E9E4
0x18000e96b  mov     r8, r15
0x18000e96e  lea     rdx, asc_18001B348; "  "
0x18000e975  lea     rcx, [rbp+57h+var_C8]
0x18000e979  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000e97e  mov     rdx, [rsp+100h+var_D8]
0x18000e983  lea     rcx, [rbp+57h+var_A8]
0x18000e987  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000e98c  mov     edx, 3Ah ; ':'
0x18000e991  lea     rcx, [rbp+57h+var_A8]
0x18000e995  call    ?push_back@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::push_back(ushort)
0x18000e99a  mov     r8, rbx
0x18000e99d  lea     rdx, asc_18001B364; "\t"
0x18000e9a4  lea     rcx, [rbp+57h+var_A8]
0x18000e9a8  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000e9ad  mov     r8, [rbp+57h+var_A0]
0x18000e9b1  lea     rcx, [rbp+57h+var_C8]
0x18000e9b5  mov     rdx, [rbp+57h+var_A8]
0x18000e9b9  sub     r8, rdx
0x18000e9bc  sar     r8, 1
0x18000e9bf  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000e9c4  mov     rdx, [rbp+57h+var_D0]
0x18000e9c8  lea     rcx, [rbp+57h+var_C8]
0x18000e9cc  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18000e9d1  mov     r8, r15
0x18000e9d4  lea     rdx, asc_18001B350; "\r\n"
0x18000e9db  lea     rcx, [rbp+57h+var_C8]
0x18000e9df  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000e9e4  add     edi, ebx
0x18000e9e6  cmp     edi, 36h ; '6'
0x18000e9e9  jb      loc_18000E941
0x18000e9ef  mov     r8, r15
0x18000e9f2  lea     rdx, asc_18001B350; "\r\n"
0x18000e9f9  lea     rcx, [rbp+57h+var_C8]
0x18000e9fd  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000ea02  mov     ecx, 8; nIndex
0x18000ea07  mov     dword ptr [rbp+57h+lParam], 5Ch ; '\'
0x18000ea0e  mov     [rbp+57h+lParam+4], 40000001h
0x18000ea16  call    cs:__imp_GetSysColor
0x18000ea1c  mov     rcx, [rsi]; hWnd
0x18000ea1f  lea     r9, [rbp+57h+lParam]; lParam
0x18000ea23  mov     r8, rbx; wParam
0x18000ea26  mov     [rbp+57h+var_6C], eax
0x18000ea29  mov     edx, 444h; Msg
0x18000ea2e  call    cs:__imp_SendMessageW
0x18000ea34  mov     r9, [rbp+57h+var_C8]; lParam
0x18000ea38  xor     r8d, r8d; wParam
0x18000ea3b  mov     rcx, [rsi]; hWnd
0x18000ea3e  mov     edx, 0C2h; Msg
0x18000ea43  call    cs:__imp_SendMessageW
0x18000ea49  xor     edi, edi
0x18000ea4b  lea     rcx, [rbp+57h+var_A8]
0x18000ea4f  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000ea54  lea     rcx, [rbp+57h+var_C8]
0x18000ea58  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000ea5d  mov     eax, edi
0x18000ea5f  mov     rcx, [rbp+57h+var_20]
0x18000ea63  xor     rcx, rsp; StackCookie
0x18000ea66  call    __security_check_cookie
0x18000ea6b  lea     r11, [rsp+100h+var_10]
0x18000ea73  mov     rbx, [r11+28h]
0x18000ea77  mov     rsi, [r11+30h]
0x18000ea7b  mov     rsp, r11
0x18000ea7e  pop     r15
0x18000ea80  pop     rdi
0x18000ea81  pop     rbp
0x18000ea82  retn
```
