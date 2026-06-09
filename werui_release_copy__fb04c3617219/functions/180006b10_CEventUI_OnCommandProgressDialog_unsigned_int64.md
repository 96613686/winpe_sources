# CEventUI::OnCommandProgressDialog(unsigned __int64)

- ea: `0x180006b10`
- end: `0x180006bd5`
- name: `?OnCommandProgressDialog@CEventUI@@AEAAJ_K@Z`
- size: `197`
- prototype: `__int64 __fastcall(CEventUI *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007bd0`

## callees

- `0x1800035dc`
- `0x180004874`
- `0x180006870`
- `0x180006b10`
- `0x18000c8a0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180006b94`
- `KERNEL32!SetEvent` at `0x180006bbf`
- `KERNEL32!SetEvent` at `0x180006b94`
- `KERNEL32!SetEvent` at `0x180006bbf`

## pseudocode

```c
__int64 __fastcall CEventUI::OnCommandProgressDialog(CEventUI *this, __int64 a2)
{
  __int64 v3; // rdx
  __int64 v4; // rdx
  enum _WER_REPORT_TYPE v5; // edx

  v3 = a2 - 2;
  if ( !v3 )
    goto LABEL_5;
  v4 = v3 - 1003;
  if ( !v4 )
  {
    v5 = *((_DWORD *)this + 2);
    *((_DWORD *)this + 52) = 5;
    UINotifyGhostWindowAndHide(*((HWND *)this + 13), v5);
    SetEvent(*((HANDLE *)this + 119));
LABEL_11:
    SetEvent(*((HANDLE *)this + 24));
    return 1;
  }
  if ( v4 == 107 )
  {
LABEL_5:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids);
    if ( *((_DWORD *)this + 44) == 9 )
    {
      UINotifyGhostWindowAndHide(*((HWND *)this + 13), *((enum _WER_REPORT_TYPE *)this + 2));
      CUIDlgBase::UICallback((char *)this + 8, 3);
    }
    else
    {
      CEventUI::HandleUICancellation(this);
    }
    goto LABEL_11;
  }
  return 1;
}

```

## disassembly

```asm
0x180006b10  mov     [rsp+arg_0], rbx
0x180006b15  push    rdi
0x180006b16  sub     rsp, 20h
0x180006b1a  mov     rdi, rcx
0x180006b1d  sub     rdx, 2
0x180006b21  jz      short loc_180006B36
0x180006b23  sub     rdx, 3EBh
0x180006b2a  jz      short loc_180006B77
0x180006b2c  cmp     rdx, 6Bh ; 'k'
0x180006b30  jnz     loc_180006BC5
0x180006b36  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b3d  lea     rax, WPP_GLOBAL_Control
0x180006b44  cmp     rcx, rax
0x180006b47  jz      short loc_180006B64
0x180006b49  test    byte ptr [rcx+1Ch], 4
0x180006b4d  jz      short loc_180006B64
0x180006b4f  mov     rcx, [rcx+10h]
0x180006b53  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x180006b5a  mov     edx, 20h ; ' '
0x180006b5f  call    WPP_SF_
0x180006b64  cmp     dword ptr [rdi+0B0h], 9
0x180006b6b  jz      short loc_180006B9C
0x180006b6d  mov     rcx, rdi; this
0x180006b70  call    ?HandleUICancellation@CEventUI@@AEAAJXZ; CEventUI::HandleUICancellation(void)
0x180006b75  jmp     short loc_180006BB8
0x180006b77  mov     edx, [rcx+8]; enum _WER_REPORT_TYPE
0x180006b7a  mov     dword ptr [rcx+0D0h], 5
0x180006b84  mov     rcx, [rcx+68h]; hWndChild
0x180006b88  call    ?UINotifyGhostWindowAndHide@@YAJPEAUHWND__@@W4_WER_REPORT_TYPE@@@Z; UINotifyGhostWindowAndHide(HWND__ *,_WER_REPORT_TYPE)
0x180006b8d  mov     rcx, [rdi+3B8h]; hEvent
0x180006b94  call    cs:__imp_SetEvent
0x180006b9a  jmp     short loc_180006BB8
0x180006b9c  mov     edx, [rdi+8]; enum _WER_REPORT_TYPE
0x180006b9f  mov     rcx, [rdi+68h]; hWndChild
0x180006ba3  call    ?UINotifyGhostWindowAndHide@@YAJPEAUHWND__@@W4_WER_REPORT_TYPE@@@Z; UINotifyGhostWindowAndHide(HWND__ *,_WER_REPORT_TYPE)
0x180006ba8  xor     r8d, r8d
0x180006bab  lea     rcx, [rdi+8]
0x180006baf  lea     edx, [r8+3]
0x180006bb3  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x180006bb8  mov     rcx, [rdi+0C0h]; hEvent
0x180006bbf  call    cs:__imp_SetEvent
0x180006bc5  mov     rbx, [rsp+28h+arg_0]
0x180006bca  mov     eax, 1
0x180006bcf  add     rsp, 20h
0x180006bd3  pop     rdi
0x180006bd4  retn
```
