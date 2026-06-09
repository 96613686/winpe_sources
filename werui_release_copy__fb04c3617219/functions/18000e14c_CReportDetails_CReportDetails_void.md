# CReportDetails::~CReportDetails(void)

- ea: `0x18000e14c`
- end: `0x18000e184`
- name: `??1CReportDetails@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(CReportDetails *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009ab8`
- `0x18000cae8`

## callees

- `0x18000e14c`

## import_xrefs

- `COMCTL32!__imp_RemoveWindowSubclass` at `0x18000e178`
- `COMCTL32!__imp_RemoveWindowSubclass` at `0x18000e178`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000e158`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000e158`

## pseudocode

```c
void __fastcall CReportDetails::~CReportDetails(HWND *this)
{
  if ( IsWindow(*this) )
  {
    if ( *((_DWORD *)this + 10) )
      RemoveWindowSubclass(*this, (SUBCLASSPROC)CReportDetails::Static_ControlProc, 0xFFEEu);
  }
}

```

## disassembly

```asm
0x18000e14c  push    rbx
0x18000e14e  sub     rsp, 20h
0x18000e152  mov     rbx, rcx
0x18000e155  mov     rcx, [rcx]; hWnd
0x18000e158  call    cs:__imp_IsWindow
0x18000e15e  test    eax, eax
0x18000e160  jz      short loc_18000E17E
0x18000e162  cmp     dword ptr [rbx+28h], 0
0x18000e166  jz      short loc_18000E17E
0x18000e168  mov     rcx, [rbx]; hWnd
0x18000e16b  lea     rdx, ?Static_ControlProc@CReportDetails@@CA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x18000e172  mov     r8d, 0FFEEh; uIdSubclass
0x18000e178  call    cs:__imp_RemoveWindowSubclass
0x18000e17e  add     rsp, 20h
0x18000e182  pop     rbx
0x18000e183  retn
```
