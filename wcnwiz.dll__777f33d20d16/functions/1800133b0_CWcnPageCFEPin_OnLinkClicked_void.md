# CWcnPageCFEPin::_OnLinkClicked(void)

- ea: `0x1800133b0`
- end: `0x180013476`
- name: `?_OnLinkClicked@CWcnPageCFEPin@@AEAAXXZ`
- size: `198`
- prototype: `void __fastcall(CWcnPageCFEPin *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180012c20`
- `0x180012cf0`

## callees

- `0x18000d630`
- `0x18000fc10`
- `0x1800133b0`
- `0x18002de1c`

## import_xrefs

- `USER32!SendMessageW` at `0x180013435`
- `USER32!SendMessageW` at `0x180013435`

## pseudocode

```c
void __fastcall CWcnPageCFEPin::_OnLinkClicked(CWcnPageCFEPin *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  __int64 v4; // rax
  HWND *Parent; // rax
  const char *v6; // rax
  __int64 v7; // r10
  char v8; // [rsp+30h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 23, WPP_ec3d56dcd870365e094116459b5f4c14_Traceguids, Indent);
  }
  v4 = *((_QWORD *)this + 45);
  *((_BYTE *)this + 386) = 1;
  *(_DWORD *)(v4 + 888) |= 2u;
  Parent = (HWND *)ATL::CWindow::GetParent((char *)this + 152, &v8);
  SendMessageW(*Parent, 0x465u, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)&qword_180036950);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v6 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v7 + 16), 24, WPP_ec3d56dcd870365e094116459b5f4c14_Traceguids, v6);
  }
}

```

## disassembly

```asm
0x1800133b0  mov     [rsp+arg_8], rbx
0x1800133b5  push    rdi
0x1800133b6  sub     rsp, 20h
0x1800133ba  mov     rbx, rcx
0x1800133bd  mov     r10, cs:WPP_GLOBAL_Control
0x1800133c4  lea     rdi, WPP_GLOBAL_Control
0x1800133cb  cmp     r10, rdi
0x1800133ce  jz      short loc_1800133F9
0x1800133d0  cmp     byte ptr [r10+19h], 6
0x1800133d5  jb      short loc_1800133F9
0x1800133d7  mov     ecx, 1; int
0x1800133dc  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800133e1  mov     rcx, [r10+10h]
0x1800133e5  lea     r8, WPP_ec3d56dcd870365e094116459b5f4c14_Traceguids
0x1800133ec  mov     edx, 17h
0x1800133f1  mov     r9, rax
0x1800133f4  call    WPP_SF_s
0x1800133f9  mov     rax, [rbx+168h]
0x180013400  lea     rcx, [rbx+98h]
0x180013407  mov     byte ptr [rbx+182h], 1
0x18001340e  lea     rdx, [rsp+28h+arg_0]
0x180013413  or      dword ptr [rax+378h], 2
0x18001341a  call    ?GetParent@CWindow@ATL@@QEBA?AV12@XZ; ATL::CWindow::GetParent(void)
0x18001341f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180013423  lea     r9, qword_180036950; lParam
0x18001342a  mov     r8, rbx; wParam
0x18001342d  mov     edx, 465h; Msg
0x180013432  mov     rcx, [rax]; hWnd
0x180013435  call    cs:__imp_SendMessageW
0x18001343b  mov     r10, cs:WPP_GLOBAL_Control
0x180013442  cmp     r10, rdi
0x180013445  jz      short loc_18001346B
0x180013447  cmp     byte ptr [r10+19h], 6
0x18001344c  jb      short loc_18001346B
0x18001344e  mov     ecx, ebx; int
0x180013450  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180013455  mov     rcx, [r10+10h]
0x180013459  lea     edx, [rbx+19h]
0x18001345c  mov     r9, rax
0x18001345f  lea     r8, WPP_ec3d56dcd870365e094116459b5f4c14_Traceguids
0x180013466  call    WPP_SF_s
0x18001346b  mov     rbx, [rsp+28h+arg_8]
0x180013470  add     rsp, 20h
0x180013474  pop     rdi
0x180013475  retn
```
