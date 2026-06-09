# CEventUI::UpdateUIForStateClosing(void)

- ea: `0x1800080d8`
- end: `0x1800083b7`
- name: `?UpdateUIForStateClosing@CEventUI@@AEAAJXZ`
- size: `735`
- prototype: `__int64 __fastcall(CEventUI *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180007e50`

## callees

- `0x180003604`
- `0x180005c20`
- `0x180005c80`
- `0x1800080d8`
- `0x180008f3c`
- `0x180009250`
- `0x180009580`
- `0x1800096a8`
- `0x18000c8a0`

## import_xrefs

- `wer!WerpGetUIParamByIndex` at `0x180008234`
- `wer!WerpGetUIParamByIndex` at `0x180008281`
- `wer!WerpGetUIParamByIndex` at `0x1800082b9`
- `wer!WerpGetUIParamByIndex` at `0x180008234`
- `wer!WerpGetUIParamByIndex` at `0x180008281`
- `wer!WerpGetUIParamByIndex` at `0x1800082b9`
- `wer!WerpGetReportFlags` at `0x180008180`
- `wer!WerpGetReportFlags` at `0x180008180`
- `KERNEL32!WaitForSingleObject` at `0x180008150`
- `KERNEL32!WaitForSingleObject` at `0x180008201`
- `KERNEL32!WaitForSingleObject` at `0x180008150`
- `KERNEL32!WaitForSingleObject` at `0x180008201`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180008345`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180008345`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x1800081eb`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x1800081eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CEventUI::UpdateUIForStateClosing(CEventUI *this)
{
  int ReportFlags; // ebx
  unsigned int v3; // esi
  _DWORD *v4; // rdx
  __int64 v5; // rcx
  int v7; // [rsp+40h] [rbp-79h] BYREF
  __int128 v8; // [rsp+44h] [rbp-75h]
  int v9; // [rsp+54h] [rbp-65h]
  _QWORD v10[4]; // [rsp+58h] [rbp-61h] BYREF
  _QWORD v11[4]; // [rsp+78h] [rbp-41h] BYREF
  _QWORD v12[4]; // [rsp+98h] [rbp-21h] BYREF
  _QWORD v13[4]; // [rsp+B8h] [rbp-1h] BYREF
  _QWORD v14[7]; // [rsp+D8h] [rbp+1Fh] BYREF
  int v15; // [rsp+120h] [rbp+67h] BYREF
  __int64 v16; // [rsp+128h] [rbp+6Fh] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v14);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v12);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v13);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v11);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v10);
  v16 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v15 = 0;
  CEventUI::WaitForUIUptime(this);
  if ( WaitForSingleObject(*((HANDLE *)this + 119), 0) )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
      v14,
      *((_QWORD *)this + 3) + 400LL);
    ReportFlags = WerpGetReportFlags(*((_QWORD *)this + 6), &v15);
    if ( ReportFlags >= 0 )
    {
      v3 = 0;
      SetWindowPos(*((HWND *)this + 13), 0, 0, 0, 0, 0, 0x47u);
      if ( (v15 & 8) != 0 && WaitForSingleObject(*(HANDLE *)(*((_QWORD *)this + 3) + 8LL), 0) )
      {
        v7 = 1005;
        *(_QWORD *)&v8 = 282;
        v3 = 1;
      }
      v16 = 0;
      if ( (int)WerpGetUIParamByIndex(*((_QWORD *)this + 6), 8, &v16) < 0 )
      {
        UtilLoadString(v13, 230);
        tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
          v12,
          v13[0],
          v14[0]);
      }
      else
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          v12,
          v16);
      }
      v16 = 0;
      if ( (int)WerpGetUIParamByIndex(*((_QWORD *)this + 6), 9, &v16) < 0 )
        UtilLoadString(v11, 246);
      else
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          v11,
          v16);
      v16 = 0;
      if ( (int)WerpGetUIParamByIndex(*((_QWORD *)this + 6), 10, &v16) < 0 )
        UtilLoadString(v10, 284);
      else
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          v10,
          v16);
      v4 = (_DWORD *)((char *)this + 792);
      if ( *((_DWORD *)this + 44) != 9 )
        *v4 |= 0x400u;
      v5 = 3LL * v3;
      *(&v7 + v5) = 1112;
      *(_QWORD *)((char *)&v8 + 4 * v5) = v10[0];
      *((_QWORD *)this + 102) = v12[0];
      *((_QWORD *)this + 103) = v11[0];
      *(_QWORD *)((char *)this + 836) = &v7;
      *((_DWORD *)this + 208) = v3 + 1;
      *v4 &= ~0x400u;
      SendMessageW(*((HWND *)this + 13), 0x465u, 0, (LPARAM)this + 772);
      CUIDlgBase::UICallback((char *)this + 8, 22);
      CUIDlgBase::UICallback((char *)this + 8, 7);
      ReportFlags = 0;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids,
        (unsigned int)ReportFlags);
    }
  }
  else
  {
    ReportFlags = -2145681407;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v10);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v11);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v13);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v12);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v14);
  return (unsigned int)ReportFlags;
}

```

## disassembly

```asm
0x1800080d8  mov     [rsp-8+arg_10], rbx
0x1800080dd  push    rbp
0x1800080de  push    rsi
0x1800080df  push    rdi
0x1800080e0  lea     rbp, [rsp-47h]
0x1800080e5  sub     rsp, 100h
0x1800080ec  mov     rdi, rcx
0x1800080ef  lea     rcx, [rbp+57h+var_38]; void *
0x1800080f3  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x1800080f8  nop
0x1800080f9  lea     rcx, [rbp+57h+var_78]; void *
0x1800080fd  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180008102  nop
0x180008103  lea     rcx, [rbp+57h+var_58]; void *
0x180008107  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x18000810c  nop
0x18000810d  lea     rcx, [rbp+57h+var_98]; void *
0x180008111  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180008116  nop
0x180008117  lea     rcx, [rbp+57h+var_B8]; void *
0x18000811b  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180008120  nop
0x180008121  mov     [rbp+57h+arg_8], 0
0x180008129  mov     [rbp+57h+var_D0], 0
0x180008130  xorps   xmm0, xmm0
0x180008133  xor     eax, eax
0x180008135  movups  [rbp+57h+var_CC], xmm0
0x180008139  mov     [rbp+57h+var_BC], eax
0x18000813c  mov     [rbp+57h+arg_0], eax
0x18000813f  mov     rcx, rdi; this
0x180008142  call    ?WaitForUIUptime@CEventUI@@AEAAXXZ; CEventUI::WaitForUIUptime(void)
0x180008147  xor     edx, edx; dwMilliseconds
0x180008149  mov     rcx, [rdi+3B8h]; hHandle
0x180008150  call    cs:__imp_WaitForSingleObject
0x180008156  test    eax, eax
0x180008158  jnz     short loc_180008164
0x18000815a  mov     ebx, 801B8001h
0x18000815f  jmp     loc_180008371
0x180008164  mov     rdx, [rdi+18h]
0x180008168  add     rdx, 190h
0x18000816f  lea     rcx, [rbp+57h+var_38]
0x180008173  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180008178  lea     rdx, [rbp+57h+arg_0]
0x18000817c  mov     rcx, [rdi+30h]
0x180008180  call    cs:__imp_WerpGetReportFlags
0x180008186  mov     ebx, eax
0x180008188  test    eax, eax
0x18000818a  jns     short loc_1800081CD
0x18000818c  lea     rax, WPP_GLOBAL_Control
0x180008193  mov     rcx, cs:WPP_GLOBAL_Control
0x18000819a  cmp     rcx, rax
0x18000819d  jz      loc_180008371
0x1800081a3  mov     esi, 1
0x1800081a8  test    [rcx+1Ch], sil
0x1800081ac  jz      loc_180008371
0x1800081b2  lea     edx, [rsi+29h]
0x1800081b5  mov     r9d, ebx
0x1800081b8  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x1800081bf  mov     rcx, [rcx+10h]
0x1800081c3  call    WPP_SF_d
0x1800081c8  jmp     loc_180008371
0x1800081cd  xor     esi, esi
0x1800081cf  mov     [rsp+110h+uFlags], 47h ; 'G'; uFlags
0x1800081d7  mov     [rsp+110h+cy], esi; cy
0x1800081db  mov     [rsp+110h+var_F0], esi; cx
0x1800081df  xor     r9d, r9d; Y
0x1800081e2  xor     r8d, r8d; X
0x1800081e5  xor     edx, edx; hWndInsertAfter
0x1800081e7  mov     rcx, [rdi+68h]; hWnd
0x1800081eb  call    cs:__imp_SetWindowPos
0x1800081f1  test    byte ptr [rbp+57h+arg_0], 8
0x1800081f5  jz      short loc_18000821F
0x1800081f7  mov     rcx, [rdi+18h]
0x1800081fb  xor     edx, edx; dwMilliseconds
0x1800081fd  mov     rcx, [rcx+8]; hHandle
0x180008201  call    cs:__imp_WaitForSingleObject
0x180008207  test    eax, eax
0x180008209  jz      short loc_18000821F
0x18000820b  mov     [rbp+57h+var_D0], 3EDh
0x180008212  mov     qword ptr [rbp+57h+var_CC], 11Ah
0x18000821a  mov     esi, 1
0x18000821f  mov     [rbp+57h+arg_8], 0
0x180008227  lea     r8, [rbp+57h+arg_8]
0x18000822b  mov     edx, 8
0x180008230  mov     rcx, [rdi+30h]
0x180008234  call    cs:__imp_WerpGetUIParamByIndex
0x18000823a  test    eax, eax
0x18000823c  js      short loc_18000824D
0x18000823e  mov     rdx, [rbp+57h+arg_8]
0x180008242  lea     rcx, [rbp+57h+var_78]
0x180008246  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000824b  jmp     short loc_18000826C
0x18000824d  mov     edx, 0E6h
0x180008252  lea     rcx, [rbp+57h+var_58]
0x180008256  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x18000825b  mov     r8, [rbp+57h+var_38]
0x18000825f  mov     rdx, [rbp+57h+var_58]
0x180008263  lea     rcx, [rbp+57h+var_78]
0x180008267  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x18000826c  mov     [rbp+57h+arg_8], 0
0x180008274  lea     r8, [rbp+57h+arg_8]
0x180008278  mov     edx, 9
0x18000827d  mov     rcx, [rdi+30h]
0x180008281  call    cs:__imp_WerpGetUIParamByIndex
0x180008287  lea     rcx, [rbp+57h+var_98]
0x18000828b  test    eax, eax
0x18000828d  js      short loc_18000829A
0x18000828f  mov     rdx, [rbp+57h+arg_8]
0x180008293  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180008298  jmp     short loc_1800082A4
0x18000829a  mov     edx, 0F6h
0x18000829f  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x1800082a4  mov     [rbp+57h+arg_8], 0
0x1800082ac  lea     r8, [rbp+57h+arg_8]
0x1800082b0  mov     edx, 0Ah
0x1800082b5  mov     rcx, [rdi+30h]
0x1800082b9  call    cs:__imp_WerpGetUIParamByIndex
0x1800082bf  lea     rcx, [rbp+57h+var_B8]
0x1800082c3  test    eax, eax
0x1800082c5  js      short loc_1800082D2
0x1800082c7  mov     rdx, [rbp+57h+arg_8]
0x1800082cb  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800082d0  jmp     short loc_1800082DC
0x1800082d2  mov     edx, 11Ch
0x1800082d7  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x1800082dc  lea     rdx, [rdi+318h]
0x1800082e3  cmp     dword ptr [rdi+0B0h], 9
0x1800082ea  jz      short loc_1800082F0
0x1800082ec  bts     dword ptr [rdx], 0Ah
0x1800082f0  mov     eax, esi
0x1800082f2  lea     rcx, [rax+rax*2]
0x1800082f6  mov     [rbp+rcx*4+57h+var_D0], 458h
0x1800082fe  mov     rax, [rbp+57h+var_B8]
0x180008302  mov     qword ptr [rbp+rcx*4+57h+var_CC], rax
0x180008307  lea     r9, [rdi+304h]; lParam
0x18000830e  mov     rax, [rbp+57h+var_78]
0x180008312  mov     [r9+2Ch], rax
0x180008316  mov     rax, [rbp+57h+var_98]
0x18000831a  mov     [rdi+338h], rax
0x180008321  lea     rax, [rbp+57h+var_D0]
0x180008325  mov     [rdi+344h], rax
0x18000832c  lea     eax, [rsi+1]
0x18000832f  mov     [rdi+340h], eax
0x180008335  btr     dword ptr [rdx], 0Ah
0x180008339  xor     r8d, r8d; wParam
0x18000833c  mov     edx, 465h; Msg
0x180008341  mov     rcx, [rdi+68h]; hWnd
0x180008345  call    cs:__imp_SendMessageW
0x18000834b  mov     r8, [rdi+68h]
0x18000834f  mov     edx, 16h
0x180008354  lea     rcx, [rdi+8]
0x180008358  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x18000835d  mov     r8, [rdi+68h]
0x180008361  mov     edx, 7
0x180008366  lea     rcx, [rdi+8]
0x18000836a  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x18000836f  xor     ebx, ebx
0x180008371  lea     rcx, [rbp+57h+var_B8]
0x180008375  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000837a  nop
0x18000837b  lea     rcx, [rbp+57h+var_98]
0x18000837f  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180008384  nop
0x180008385  lea     rcx, [rbp+57h+var_58]
0x180008389  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000838e  nop
0x18000838f  lea     rcx, [rbp+57h+var_78]
0x180008393  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180008398  nop
0x180008399  lea     rcx, [rbp+57h+var_38]
0x18000839d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800083a2  mov     eax, ebx
0x1800083a4  mov     rbx, [rsp+110h+arg_10]
0x1800083ac  add     rsp, 100h
0x1800083b3  pop     rdi
0x1800083b4  pop     rsi
0x1800083b5  pop     rbp
0x1800083b6  retn
```
