# ATL::CComControlBase::~CComControlBase(void)

- ea: `0x1800028c8`
- end: `0x180002967`
- name: `??1CComControlBase@ATL@@UEAA@XZ`
- size: `159`
- prototype: `void __fastcall(ATL::CComControlBase *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002970`

## callees

- `0x1800028c8`
- `0x180015010`

## import_xrefs

- `USER32!DestroyWindow` at `0x1800028dd`
- `USER32!DestroyWindow` at `0x1800028dd`

## pseudocode

```c
void __fastcall ATL::CComControlBase::~CComControlBase(ATL::CComControlBase *this)
{
  HWND v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx

  v2 = (HWND)**((_QWORD **)this + 11);
  if ( v2 )
    DestroyWindow(v2);
  v3 = *((_QWORD *)this + 6);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 5);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 4);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)this + 2);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = *((_QWORD *)this + 1);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
}

```

## disassembly

```asm
0x1800028c8  push    rbx
0x1800028ca  sub     rsp, 20h
0x1800028ce  mov     rax, [rcx+58h]
0x1800028d2  mov     rbx, rcx
0x1800028d5  mov     rcx, [rax]; hWnd
0x1800028d8  test    rcx, rcx
0x1800028db  jz      short loc_1800028E3
0x1800028dd  call    cs:__imp_DestroyWindow
0x1800028e3  mov     rcx, [rbx+30h]
0x1800028e7  test    rcx, rcx
0x1800028ea  jz      short loc_1800028F8
0x1800028ec  mov     rax, [rcx]
0x1800028ef  mov     rax, [rax+10h]
0x1800028f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028f8  mov     rcx, [rbx+28h]
0x1800028fc  test    rcx, rcx
0x1800028ff  jz      short loc_18000290D
0x180002901  mov     rax, [rcx]
0x180002904  mov     rax, [rax+10h]
0x180002908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000290d  mov     rcx, [rbx+20h]
0x180002911  test    rcx, rcx
0x180002914  jz      short loc_180002922
0x180002916  mov     rax, [rcx]
0x180002919  mov     rax, [rax+10h]
0x18000291d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002922  mov     rcx, [rbx+18h]
0x180002926  test    rcx, rcx
0x180002929  jz      short loc_180002937
0x18000292b  mov     rax, [rcx]
0x18000292e  mov     rax, [rax+10h]
0x180002932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002937  mov     rcx, [rbx+10h]
0x18000293b  test    rcx, rcx
0x18000293e  jz      short loc_18000294C
0x180002940  mov     rax, [rcx]
0x180002943  mov     rax, [rax+10h]
0x180002947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000294c  mov     rcx, [rbx+8]
0x180002950  test    rcx, rcx
0x180002953  jz      short loc_180002961
0x180002955  mov     rax, [rcx]
0x180002958  mov     rax, [rax+10h]
0x18000295c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002961  add     rsp, 20h
0x180002965  pop     rbx
0x180002966  retn
```
