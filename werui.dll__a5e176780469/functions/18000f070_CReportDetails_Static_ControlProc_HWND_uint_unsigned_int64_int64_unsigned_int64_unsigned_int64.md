# CReportDetails::Static_ControlProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)

- ea: `0x18000f070`
- end: `0x18000f0fd`
- name: `?Static_ControlProc@CReportDetails@@CA_JPEAUHWND__@@I_K_J11@Z`
- size: `141`
- prototype: `LRESULT __stdcall(HWND hWnd, UINT uMsg, WPARAM wParam, LPARAM lParam, UINT_PTR uIdSubclass, DWORD_PTR dwRefData)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000ee10`
- `0x18000ee6c`
- `0x18000f070`

## import_xrefs

- `COMCTL32!__imp_RemoveWindowSubclass` at `0x18000f0dd`
- `COMCTL32!__imp_RemoveWindowSubclass` at `0x18000f0dd`
- `COMCTL32!__imp_DefSubclassProc` at `0x18000f0f6`

## pseudocode

```c
LRESULT __fastcall CReportDetails::Static_ControlProc(
        HWND hWnd,
        UINT uMsg,
        WPARAM wParam,
        struct tagNMHDR *lParam,
        UINT_PTR uIdSubclass,
        CReportDetails *dwRefData)
{
  if ( uIdSubclass != 65518 )
    return DefSubclassProc(hWnd, uMsg, wParam, (LPARAM)lParam);
  if ( !dwRefData )
    goto LABEL_8;
  if ( uMsg != 78 )
  {
    if ( uMsg == 123 )
    {
      CReportDetails::ShowContextMenu(dwRefData, (unsigned __int16)lParam, WORD1(lParam));
      return DefSubclassProc(hWnd, uMsg, wParam, (LPARAM)lParam);
    }
LABEL_8:
    if ( uMsg == 2 )
      RemoveWindowSubclass(hWnd, CReportDetails::Static_ControlProc, 0xFFEEu);
    return DefSubclassProc(hWnd, uMsg, wParam, (LPARAM)lParam);
  }
  if ( lParam->code == 1803 )
    CReportDetails::ProcessNotification(dwRefData, lParam);
  return DefSubclassProc(hWnd, uMsg, wParam, (LPARAM)lParam);
}

```

## disassembly

```asm
0x18000f070  push    rbx
0x18000f072  push    rbp
0x18000f073  push    rsi
0x18000f074  push    rdi
0x18000f075  sub     rsp, 28h
0x18000f079  mov     rbp, r8
0x18000f07c  mov     rbx, r9
0x18000f07f  mov     r8d, 0FFEEh; uIdSubclass
0x18000f085  mov     edi, edx
0x18000f087  mov     rsi, rcx
0x18000f08a  cmp     [rsp+48h+uIdSubclass], r8
0x18000f08f  jnz     short loc_18000F0E3
0x18000f091  mov     rcx, [rsp+48h+dwRefData]; this
0x18000f096  test    rcx, rcx
0x18000f099  jz      short loc_18000F0CE
0x18000f09b  cmp     edx, 4Eh ; 'N'
0x18000f09e  jz      short loc_18000F0BA
0x18000f0a0  cmp     edx, 7Bh ; '{'
0x18000f0a3  jnz     short loc_18000F0CE
0x18000f0a5  mov     rax, rbx
0x18000f0a8  movzx   edx, bx; int
0x18000f0ab  shr     rax, 10h
0x18000f0af  movzx   r8d, ax; int
0x18000f0b3  call    ?ShowContextMenu@CReportDetails@@AEAAJHH@Z; CReportDetails::ShowContextMenu(int,int)
0x18000f0b8  jmp     short loc_18000F0E3
0x18000f0ba  cmp     dword ptr [r9+10h], 70Bh
0x18000f0c2  jnz     short loc_18000F0E3
0x18000f0c4  mov     rdx, rbx; struct tagNMHDR *
0x18000f0c7  call    ?ProcessNotification@CReportDetails@@QEAA_JPEAUtagNMHDR@@@Z; CReportDetails::ProcessNotification(tagNMHDR *)
0x18000f0cc  jmp     short loc_18000F0E3
0x18000f0ce  cmp     edi, 2
0x18000f0d1  jnz     short loc_18000F0E3
0x18000f0d3  lea     rdx, ?Static_ControlProc@CReportDetails@@CA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x18000f0da  mov     rcx, rsi; hWnd
0x18000f0dd  call    cs:__imp_RemoveWindowSubclass
0x18000f0e3  mov     r9, rbx
0x18000f0e6  mov     r8, rbp
0x18000f0e9  mov     edx, edi
0x18000f0eb  mov     rcx, rsi
0x18000f0ee  add     rsp, 28h
0x18000f0f2  pop     rdi
0x18000f0f3  pop     rsi
0x18000f0f4  pop     rbp
0x18000f0f5  pop     rbx
0x18000f0f6  jmp     cs:__imp_DefSubclassProc
```
