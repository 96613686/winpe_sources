# CWcnPageCFETransferFailed::_OnLinkClicked(void)

- ea: `0x180012700`
- end: `0x1800127bf`
- name: `?_OnLinkClicked@CWcnPageCFETransferFailed@@AEAAXXZ`
- size: `191`
- prototype: `void __fastcall(CWcnPageCFETransferFailed *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800120c0`
- `0x180012140`

## callees

- `0x18000d630`
- `0x18000fc10`
- `0x180012700`
- `0x18002de1c`

## import_xrefs

- `USER32!SendMessageW` at `0x18001277e`
- `USER32!SendMessageW` at `0x18001277e`

## pseudocode

```c
void __fastcall CWcnPageCFETransferFailed::_OnLinkClicked(CWcnPageCFETransferFailed *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  HWND *Parent; // rax
  const char *v5; // rax
  __int64 v6; // r10
  char v7; // [rsp+30h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 13, WPP_3613e1472a6e3da556a8797fe79ad568_Traceguids, Indent);
  }
  *(_DWORD *)(*((_QWORD *)this + 45) + 888LL) |= 2u;
  Parent = (HWND *)ATL::CWindow::GetParent((char *)this + 152, &v7);
  SendMessageW(*Parent, 0x465u, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)&lParam);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v5 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 14, WPP_3613e1472a6e3da556a8797fe79ad568_Traceguids, v5);
  }
}

```

## disassembly

```asm
0x180012700  mov     [rsp+arg_8], rbx
0x180012705  push    rdi
0x180012706  sub     rsp, 20h
0x18001270a  mov     rbx, rcx
0x18001270d  mov     r10, cs:WPP_GLOBAL_Control
0x180012714  lea     rdi, WPP_GLOBAL_Control
0x18001271b  cmp     r10, rdi
0x18001271e  jz      short loc_180012749
0x180012720  cmp     byte ptr [r10+19h], 6
0x180012725  jb      short loc_180012749
0x180012727  mov     ecx, 1; int
0x18001272c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180012731  mov     rcx, [r10+10h]
0x180012735  lea     r8, WPP_3613e1472a6e3da556a8797fe79ad568_Traceguids
0x18001273c  mov     edx, 0Dh
0x180012741  mov     r9, rax
0x180012744  call    WPP_SF_s
0x180012749  mov     rax, [rbx+168h]
0x180012750  lea     rcx, [rbx+98h]
0x180012757  lea     rdx, [rsp+28h+arg_0]
0x18001275c  or      dword ptr [rax+378h], 2
0x180012763  call    ?GetParent@CWindow@ATL@@QEBA?AV12@XZ; ATL::CWindow::GetParent(void)
0x180012768  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001276c  lea     r9, lParam; lParam
0x180012773  mov     r8, rbx; wParam
0x180012776  mov     edx, 465h; Msg
0x18001277b  mov     rcx, [rax]; hWnd
0x18001277e  call    cs:__imp_SendMessageW
0x180012784  mov     r10, cs:WPP_GLOBAL_Control
0x18001278b  cmp     r10, rdi
0x18001278e  jz      short loc_1800127B4
0x180012790  cmp     byte ptr [r10+19h], 6
0x180012795  jb      short loc_1800127B4
0x180012797  mov     ecx, ebx; int
0x180012799  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001279e  mov     rcx, [r10+10h]
0x1800127a2  lea     edx, [rbx+0Fh]
0x1800127a5  mov     r9, rax
0x1800127a8  lea     r8, WPP_3613e1472a6e3da556a8797fe79ad568_Traceguids
0x1800127af  call    WPP_SF_s
0x1800127b4  mov     rbx, [rsp+28h+arg_8]
0x1800127b9  add     rsp, 20h
0x1800127bd  pop     rdi
0x1800127be  retn
```
