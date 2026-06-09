# ATL::CAxHostWindow::GetWindowContext(IOleInPlaceFrame * *,IOleInPlaceUIWindow * *,tagRECT *,tagRECT *,tagOIFI *)

- ea: `0x180016920`
- end: `0x180016ad5`
- name: `?GetWindowContext@CAxHostWindow@ATL@@UEAAJPEAPEAUIOleInPlaceFrame@@PEAPEAUIOleInPlaceUIWindow@@PEAUtagRECT@@2PEAUtagOIFI@@@Z`
- size: `437`
- prototype: `int(ATL::CAxHostWindow *__hidden this, struct IOleInPlaceFrame **, struct IOleInPlaceUIWindow **, struct tagRECT *, struct tagRECT *, struct tagOIFI *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800156cc`
- `0x180015794`
- `0x180016920`
- `0x180063010`

## import_xrefs

- `USER32!CreateAcceleratorTableW` at `0x180016a6c`
- `USER32!CreateAcceleratorTableW` at `0x180016a6c`
- `USER32!GetParent` at `0x180016a9a`
- `USER32!GetParent` at `0x180016a9a`
- `USER32!GetClientRect` at `0x180016a33`
- `USER32!GetClientRect` at `0x180016a45`
- `USER32!GetClientRect` at `0x180016a33`
- `USER32!GetClientRect` at `0x180016a45`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAxHostWindow::GetWindowContext(
        ATL::CAxHostWindow *this,
        struct IOleInPlaceFrame **a2,
        struct IOleInPlaceUIWindow **a3,
        struct tagRECT *a4,
        struct tagRECT *lpRect,
        struct tagOIFI *a6)
{
  _QWORD *v10; // r15
  _QWORD *v11; // r14
  struct tagOIFI *v12; // rbx
  __int64 paccel; // [rsp+68h] [rbp+10h] BYREF

  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a2 || !a3 || !a4 || !lpRect )
    return 2147500035LL;
  v10 = (_QWORD *)((char *)this + 120);
  if ( !*((_QWORD *)this + 15) )
  {
    paccel = 0;
    ATL::CComObject<ATL::CAxFrameWindow>::CreateInstance(&paccel);
    (**(void (__fastcall ***)(__int64, GUID *, _QWORD *))(paccel + 72))(
      paccel + 72,
      &GUID_00000116_0000_0000_c000_000000000046,
      v10);
  }
  v11 = (_QWORD *)((char *)this + 128);
  if ( !*((_QWORD *)this + 16) )
  {
    paccel = 0;
    ATL::CComObject<ATL::CAxUIWindow>::CreateInstance(&paccel);
    (**(void (__fastcall ***)(__int64, GUID *, char *))(paccel + 72))(
      paccel + 72,
      &GUID_00000115_0000_0000_c000_000000000046,
      (char *)this + 128);
  }
  *a2 = (struct IOleInPlaceFrame *)*v10;
  if ( *v10 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
  *a3 = (struct IOleInPlaceUIWindow *)*v11;
  if ( *v11 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
  GetClientRect(*((HWND *)this - 10), a4);
  GetClientRect(*((HWND *)this - 10), lpRect);
  if ( !*((_QWORD *)this + 30) )
  {
    LODWORD(paccel) = 0;
    WORD2(paccel) = 0;
    *((_QWORD *)this + 30) = CreateAcceleratorTableW((LPACCEL)&paccel, 1);
  }
  v12 = a6;
  a6->cb = 32;
  v12->fMDIApp = (*((_DWORD *)this + 48) >> 2) & 1;
  v12->hwndFrame = GetParent(*((HWND *)this - 10));
  v12->haccel = (HACCEL)*((_QWORD *)this + 30);
  v12->cAccelEntries = *((_QWORD *)this + 30) != 0;
  return 0;
}

```

## disassembly

```asm
0x180016920  push    rbx
0x180016922  push    rsi
0x180016923  push    rdi
0x180016924  push    r12
0x180016926  push    r14
0x180016928  push    r15
0x18001692a  sub     rsp, 28h
0x18001692e  mov     r12, r9
0x180016931  mov     rbx, r8
0x180016934  mov     rsi, rdx
0x180016937  mov     rdi, rcx
0x18001693a  test    rdx, rdx
0x18001693d  jz      short loc_180016946
0x18001693f  mov     qword ptr [rdx], 0
0x180016946  test    rbx, rbx
0x180016949  jz      short loc_180016952
0x18001694b  mov     qword ptr [r8], 0
0x180016952  test    rsi, rsi
0x180016955  jz      loc_180016AC2
0x18001695b  test    rbx, rbx
0x18001695e  jz      loc_180016AC2
0x180016964  test    r12, r12
0x180016967  jz      loc_180016AC2
0x18001696d  cmp     [rsp+58h+lpRect], 0
0x180016976  jz      loc_180016AC2
0x18001697c  lea     r15, [rcx+78h]
0x180016980  cmp     qword ptr [r15], 0
0x180016984  jnz     short loc_1800169B7
0x180016986  mov     [rsp+58h+paccel], 0
0x18001698f  lea     rcx, [rsp+58h+paccel]
0x180016994  call    ?CreateInstance@?$CComObject@VCAxFrameWindow@ATL@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<ATL::CAxFrameWindow>::CreateInstance(ATL::CComObject<ATL::CAxFrameWindow> * *)
0x180016999  mov     rcx, [rsp+58h+paccel]
0x18001699e  add     rcx, 48h ; 'H'
0x1800169a2  mov     rax, [rcx]
0x1800169a5  mov     r8, r15
0x1800169a8  lea     rdx, _GUID_00000116_0000_0000_c000_000000000046
0x1800169af  mov     rax, [rax]
0x1800169b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169b7  lea     r14, [rdi+80h]
0x1800169be  cmp     qword ptr [r14], 0
0x1800169c2  jnz     short loc_1800169F6
0x1800169c4  mov     [rsp+58h+paccel], 0
0x1800169cd  lea     rcx, [rsp+58h+paccel]
0x1800169d2  call    ?CreateInstance@?$CComObject@VCAxUIWindow@ATL@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<ATL::CAxUIWindow>::CreateInstance(ATL::CComObject<ATL::CAxUIWindow> * *)
0x1800169d7  mov     rcx, [rsp+58h+paccel]
0x1800169dc  add     rcx, 48h ; 'H'
0x1800169e0  mov     rax, [rcx]
0x1800169e3  mov     r8, r14
0x1800169e6  lea     rdx, _GUID_00000115_0000_0000_c000_000000000046
0x1800169ed  mov     rax, [rax]
0x1800169f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169f5  nop
0x1800169f6  mov     rax, [r15]
0x1800169f9  mov     [rsi], rax
0x1800169fc  mov     rcx, [r15]
0x1800169ff  test    rcx, rcx
0x180016a02  jz      short loc_180016A11
0x180016a04  mov     rax, [rcx]
0x180016a07  mov     rax, [rax+8]
0x180016a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a10  nop
0x180016a11  mov     rax, [r14]
0x180016a14  mov     [rbx], rax
0x180016a17  mov     rcx, [r14]
0x180016a1a  test    rcx, rcx
0x180016a1d  jz      short loc_180016A2C
0x180016a1f  mov     rax, [rcx]
0x180016a22  mov     rax, [rax+8]
0x180016a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a2b  nop
0x180016a2c  mov     rdx, r12; lpRect
0x180016a2f  mov     rcx, [rdi-50h]; hWnd
0x180016a33  call    cs:__imp_GetClientRect
0x180016a39  mov     rdx, [rsp+58h+lpRect]; lpRect
0x180016a41  mov     rcx, [rdi-50h]; hWnd
0x180016a45  call    cs:__imp_GetClientRect
0x180016a4b  cmp     qword ptr [rdi+0F0h], 0
0x180016a53  jnz     short loc_180016A79
0x180016a55  mov     dword ptr [rsp+58h+paccel], 0
0x180016a5d  xor     eax, eax
0x180016a5f  mov     word ptr [rsp+58h+paccel+4], ax
0x180016a64  lea     edx, [rax+1]; cAccel
0x180016a67  lea     rcx, [rsp+58h+paccel]; paccel
0x180016a6c  call    cs:__imp_CreateAcceleratorTableW
0x180016a72  mov     [rdi+0F0h], rax
0x180016a79  mov     rbx, [rsp+58h+arg_28]
0x180016a81  mov     dword ptr [rbx], 20h ; ' '
0x180016a87  mov     eax, [rdi+0C0h]
0x180016a8d  shr     eax, 2
0x180016a90  and     eax, 1
0x180016a93  mov     [rbx+4], eax
0x180016a96  mov     rcx, [rdi-50h]; hWnd
0x180016a9a  call    cs:__imp_GetParent
0x180016aa0  mov     [rbx+8], rax
0x180016aa4  mov     rax, [rdi+0F0h]
0x180016aab  mov     [rbx+10h], rax
0x180016aaf  xor     eax, eax
0x180016ab1  cmp     [rdi+0F0h], rax
0x180016ab8  setnz   al
0x180016abb  mov     [rbx+18h], eax
0x180016abe  xor     eax, eax
0x180016ac0  jmp     short loc_180016AC7
0x180016ac2  mov     eax, 80004003h
0x180016ac7  add     rsp, 28h
0x180016acb  pop     r15
0x180016acd  pop     r14
0x180016acf  pop     r12
0x180016ad1  pop     rdi
0x180016ad2  pop     rsi
0x180016ad3  pop     rbx
0x180016ad4  retn
```
