# CEventUI::UpdateUIForStateCabbingData(void)

- ea: `0x18000801c`
- end: `0x1800080d0`
- name: `?UpdateUIForStateCabbingData@CEventUI@@AEAAJXZ`
- size: `180`
- prototype: `__int64 __fastcall(CEventUI *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180007e50`

## callees

- `0x180003604`
- `0x180004874`
- `0x180005fec`
- `0x18000801c`
- `0x18000c8a0`
- `0x180018010`

## import_xrefs

- `wer!WerpGetReportFlags` at `0x18000803a`
- `wer!WerpGetReportFlags` at `0x18000803a`

## pseudocode

```c
__int64 __fastcall CEventUI::UpdateUIForStateCabbingData(CEventUI *this)
{
  int ReportFlags; // edi
  int v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  ReportFlags = WerpGetReportFlags(*((_QWORD *)this + 6), &v4);
  if ( ReportFlags >= 0 )
  {
    if ( (v4 & 0x40) != 0 )
      CUIDlgBase::UICallback((char *)this + 8, 3);
    CEventUI::AddUploadNotifyIcon(this);
    if ( (v4 & 0x40) != 0 )
    {
      UINotifyGhostWindowAndHide(*((HWND *)this + 13), *((enum _WER_REPORT_TYPE *)this + 2));
      return 0;
    }
    else
    {
      return (*(__int64 (__fastcall **)(CEventUI *, __int64))(*(_QWORD *)this + 16LL))(this, 9);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids,
        (unsigned int)ReportFlags);
    return (unsigned int)ReportFlags;
  }
}

```

## disassembly

```asm
0x18000801c  mov     [rsp+arg_8], rbx
0x180008021  push    rdi
0x180008022  sub     rsp, 20h
0x180008026  mov     rbx, rcx
0x180008029  mov     [rsp+28h+arg_0], 0
0x180008031  mov     rcx, [rcx+30h]
0x180008035  lea     rdx, [rsp+28h+arg_0]
0x18000803a  call    cs:__imp_WerpGetReportFlags
0x180008040  mov     edi, eax
0x180008042  test    eax, eax
0x180008044  jns     short loc_18000807B
0x180008046  mov     rcx, cs:WPP_GLOBAL_Control
0x18000804d  lea     rax, WPP_GLOBAL_Control
0x180008054  cmp     rcx, rax
0x180008057  jz      short loc_180008077
0x180008059  test    byte ptr [rcx+1Ch], 1
0x18000805d  jz      short loc_180008077
0x18000805f  mov     rcx, [rcx+10h]
0x180008063  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x18000806a  mov     edx, 29h ; ')'
0x18000806f  mov     r9d, edi
0x180008072  call    WPP_SF_d
0x180008077  mov     eax, edi
0x180008079  jmp     short loc_1800080C5
0x18000807b  test    byte ptr [rsp+28h+arg_0], 40h
0x180008080  jz      short loc_180008092
0x180008082  xor     r8d, r8d
0x180008085  lea     rcx, [rbx+8]
0x180008089  lea     edx, [r8+3]
0x18000808d  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x180008092  mov     rcx, rbx; this
0x180008095  call    ?AddUploadNotifyIcon@CEventUI@@AEAAJXZ; CEventUI::AddUploadNotifyIcon(void)
0x18000809a  test    byte ptr [rsp+28h+arg_0], 40h
0x18000809f  jnz     short loc_1800080B7
0x1800080a1  mov     rax, [rbx]
0x1800080a4  mov     edx, 9
0x1800080a9  mov     rcx, rbx
0x1800080ac  mov     rax, [rax+10h]
0x1800080b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080b5  jmp     short loc_1800080C5
0x1800080b7  mov     edx, [rbx+8]; enum _WER_REPORT_TYPE
0x1800080ba  mov     rcx, [rbx+68h]; hWndChild
0x1800080be  call    ?UINotifyGhostWindowAndHide@@YAJPEAUHWND__@@W4_WER_REPORT_TYPE@@@Z; UINotifyGhostWindowAndHide(HWND__ *,_WER_REPORT_TYPE)
0x1800080c3  xor     eax, eax
0x1800080c5  mov     rbx, [rsp+28h+arg_8]
0x1800080ca  add     rsp, 20h
0x1800080ce  pop     rdi
0x1800080cf  retn
```
