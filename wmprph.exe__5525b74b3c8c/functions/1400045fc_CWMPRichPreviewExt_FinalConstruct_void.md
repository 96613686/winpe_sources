# CWMPRichPreviewExt::FinalConstruct(void)

- ea: `0x1400045fc`
- end: `0x14000477e`
- name: `?FinalConstruct@CWMPRichPreviewExt@@QEAAJXZ`
- size: `386`
- prototype: `__int64 __fastcall(CWMPRichPreviewExt *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000ac24`
- `0x14000ad2c`

## callees

- `0x140001014`
- `0x140001d26`
- `0x1400045fc`
- `0x1400099e0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000464d`
- `KERNEL32!GetModuleHandleW` at `0x14000464d`
- `KERNEL32!GetLastError` at `0x1400046d5`
- `KERNEL32!GetLastError` at `0x1400046d5`
- `USER32!DefWindowProcW` at `0x140004680`
- `USER32!DefWindowProcW` at `0x14000470c`
- `USER32!RegisterClassExW` at `0x1400046ca`
- `USER32!RegisterClassExW` at `0x1400046ca`
- `USER32!GetClassInfoExW` at `0x140004676`
- `USER32!GetClassInfoExW` at `0x140004676`
- `USER32!LoadCursorW` at `0x1400046ac`
- `USER32!LoadCursorW` at `0x1400046ac`

## pseudocode

```c
__int64 __fastcall CWMPRichPreviewExt::FinalConstruct(CWMPRichPreviewExt *this)
{
  signed int v2; // ebx
  HINSTANCE ModuleHandleW; // rsi
  HCURSOR CursorW; // rax
  signed int LastError; // eax
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  struct tagWNDCLASSEXW wcx; // [rsp+20h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_a1620705688d36e506283508f1a041e6_Traceguids);
  }
  v2 = 0;
  ModuleHandleW = GetModuleHandleW(0);
  memset_0(&wcx, 0, sizeof(wcx));
  if ( GetClassInfoExW(ModuleHandleW, L"RPHInnerParent", &wcx) )
    goto LABEL_10;
  wcx.lpfnWndProc = DefWindowProcW;
  wcx.cbSize = 80;
  wcx.style = 3;
  *(_QWORD *)&wcx.cbClsExtra = 0;
  wcx.hInstance = ModuleHandleW;
  wcx.hIcon = 0;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
  wcx.lpszClassName = L"RPHInnerParent";
  *(_OWORD *)&wcx.hbrBackground = 0;
  wcx.hCursor = CursorW;
  wcx.hIconSm = 0;
  if ( RegisterClassExW(&wcx) )
    goto LABEL_10;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_10:
    v6 = operator new(0x50u);
    v7 = v6;
    if ( v6 )
    {
      v6[1] = 0;
      v6[5] = 0;
      v6[6] = 0;
      v6[7] = DefWindowProcW;
      *v6 = &CWMPRichPreviewAXWindow::`vftable';
      v6[8] = this;
      v6[9] = 0;
    }
    else
    {
      v7 = 0;
    }
    *((_QWORD *)this + 17) = v7;
    if ( !v7 )
      v2 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_a1620705688d36e506283508f1a041e6_Traceguids);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400045fc  push    rbp
0x1400045fe  push    rbx
0x1400045ff  push    rsi
0x140004600  push    rdi
0x140004601  push    r13
0x140004603  push    r14
0x140004605  push    r15
0x140004607  mov     rbp, rsp
0x14000460a  sub     rsp, 70h
0x14000460e  mov     rdi, rcx
0x140004611  mov     rcx, cs:WPP_GLOBAL_Control
0x140004618  lea     r15, WPP_GLOBAL_Control
0x14000461f  cmp     rcx, r15
0x140004622  jz      short loc_140004645
0x140004624  test    byte ptr [rcx+1Ch], 1
0x140004628  jz      short loc_140004645
0x14000462a  cmp     byte ptr [rcx+19h], 5
0x14000462e  jb      short loc_140004645
0x140004630  mov     rcx, [rcx+10h]
0x140004634  lea     r8, WPP_a1620705688d36e506283508f1a041e6_Traceguids
0x14000463b  mov     edx, 0Eh
0x140004640  call    WPP_SF_
0x140004645  xor     r14d, r14d
0x140004648  xor     ecx, ecx; lpModuleName
0x14000464a  mov     ebx, r14d
0x14000464d  call    cs:__imp_GetModuleHandleW
0x140004653  xor     edx, edx; Val
0x140004655  lea     r8d, [r14+50h]; Size
0x140004659  lea     rcx, [rbp+wcx]; void *
0x14000465d  mov     rsi, rax
0x140004660  call    memset_0
0x140004665  lea     r13, szClass; "RPHInnerParent"
0x14000466c  mov     rcx, rsi; hInstance
0x14000466f  mov     rdx, r13; lpszClass
0x140004672  lea     r8, [rbp+wcx]; lpwcx
0x140004676  call    cs:__imp_GetClassInfoExW
0x14000467c  test    eax, eax
0x14000467e  jnz     short loc_1400046EE
0x140004680  mov     rax, cs:__imp_DefWindowProcW
0x140004687  mov     edx, 7F00h; lpCursorName
0x14000468c  xor     ecx, ecx; hInstance
0x14000468e  mov     [rbp+wcx.lpfnWndProc], rax
0x140004692  mov     [rbp+wcx.cbSize], 50h ; 'P'
0x140004699  mov     [rbp+wcx.style], 3
0x1400046a0  mov     qword ptr [rbp+wcx.cbClsExtra], r14
0x1400046a4  mov     [rbp+wcx.hInstance], rsi
0x1400046a8  mov     [rbp+wcx.hIcon], r14
0x1400046ac  call    cs:__imp_LoadCursorW
0x1400046b2  xorps   xmm0, xmm0
0x1400046b5  mov     [rbp+wcx.lpszClassName], r13
0x1400046b9  lea     rcx, [rbp+wcx]; WNDCLASSEXW *
0x1400046bd  movdqa  xmmword ptr [rbp+wcx.hbrBackground], xmm0
0x1400046c2  mov     [rbp+wcx.hCursor], rax
0x1400046c6  mov     [rbp+wcx.hIconSm], r14
0x1400046ca  call    cs:__imp_RegisterClassExW
0x1400046d0  test    ax, ax
0x1400046d3  jnz     short loc_1400046EE
0x1400046d5  call    cs:__imp_GetLastError
0x1400046db  mov     ebx, eax
0x1400046dd  test    eax, eax
0x1400046df  jle     short loc_1400046EA
0x1400046e1  movzx   ebx, ax
0x1400046e4  or      ebx, 80070000h
0x1400046ea  test    ebx, ebx
0x1400046ec  js      short loc_140004740
0x1400046ee  mov     ecx, 50h ; 'P'; Size
0x1400046f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400046f8  mov     rcx, rax
0x1400046fb  test    rax, rax
0x1400046fe  jz      short loc_14000472B
0x140004700  mov     [rax+8], r14
0x140004704  mov     [rax+28h], r14
0x140004708  mov     [rax+30h], r14
0x14000470c  mov     rax, cs:__imp_DefWindowProcW
0x140004713  mov     [rcx+38h], rax
0x140004717  lea     rax, ??_7CWMPRichPreviewAXWindow@@6B@; const CWMPRichPreviewAXWindow::`vftable'
0x14000471e  mov     [rcx], rax
0x140004721  mov     [rcx+40h], rdi
0x140004725  mov     [rcx+48h], r14
0x140004729  jmp     short loc_14000472E
0x14000472b  mov     rcx, r14
0x14000472e  test    rcx, rcx
0x140004731  mov     [rdi+88h], rcx
0x140004738  mov     eax, 8007000Eh
0x14000473d  cmovz   ebx, eax
0x140004740  mov     rcx, cs:WPP_GLOBAL_Control
0x140004747  cmp     rcx, r15
0x14000474a  jz      short loc_14000476D
0x14000474c  test    byte ptr [rcx+1Ch], 1
0x140004750  jz      short loc_14000476D
0x140004752  cmp     byte ptr [rcx+19h], 5
0x140004756  jb      short loc_14000476D
0x140004758  mov     rcx, [rcx+10h]
0x14000475c  lea     r8, WPP_a1620705688d36e506283508f1a041e6_Traceguids
0x140004763  mov     edx, 0Fh
0x140004768  call    WPP_SF_
0x14000476d  mov     eax, ebx
0x14000476f  add     rsp, 70h
0x140004773  pop     r15
0x140004775  pop     r14
0x140004777  pop     r13
0x140004779  pop     rdi
0x14000477a  pop     rsi
0x14000477b  pop     rbx
0x14000477c  pop     rbp
0x14000477d  retn
```
