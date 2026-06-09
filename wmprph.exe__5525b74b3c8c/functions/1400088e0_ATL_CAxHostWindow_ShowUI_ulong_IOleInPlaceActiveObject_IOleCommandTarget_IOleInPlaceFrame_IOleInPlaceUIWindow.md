# ATL::CAxHostWindow::ShowUI(ulong,IOleInPlaceActiveObject *,IOleCommandTarget *,IOleInPlaceFrame *,IOleInPlaceUIWindow *)

- ea: `0x1400088e0`
- end: `0x140008932`
- name: `?ShowUI@CAxHostWindow@ATL@@UEAAJKPEAUIOleInPlaceActiveObject@@PEAUIOleCommandTarget@@PEAUIOleInPlaceFrame@@PEAUIOleInPlaceUIWindow@@@Z`
- size: `82`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, unsigned int, struct IOleInPlaceActiveObject *, struct IOleCommandTarget *, struct IOleInPlaceFrame *, struct IOleInPlaceUIWindow *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400088e0`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::ShowUI(
        ATL::CAxHostWindow *this,
        __int64 a2,
        struct IOleInPlaceActiveObject *a3,
        struct IOleCommandTarget *a4,
        struct IOleInPlaceFrame *a5,
        struct IOleInPlaceUIWindow *a6)
{
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 result; // rax
  unsigned int v9; // [rsp+50h] [rbp+8h] BYREF

  v6 = *((_DWORD *)this + 39);
  v7 = *((_QWORD *)this + 10);
  result = (v6 >> 6) & 1;
  v9 = result;
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64, __int64, struct IOleInPlaceActiveObject *, struct IOleCommandTarget *, struct IOleInPlaceFrame *, struct IOleInPlaceUIWindow *, unsigned int *))(*(_QWORD *)v7 + 72LL))(
      v7,
      a2,
      a3,
      a4,
      a5,
      a6,
      &v9);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x1400088e0  mov     r11, rsp
0x1400088e3  sub     rsp, 48h
0x1400088e7  mov     eax, [rcx+9Ch]
0x1400088ed  mov     rcx, [rcx+50h]
0x1400088f1  shr     eax, 6
0x1400088f4  and     eax, 1
0x1400088f7  mov     [rsp+48h+arg_0], eax
0x1400088fb  test    rcx, rcx
0x1400088fe  jz      short loc_14000892D
0x140008900  mov     rax, [rcx]
0x140008903  mov     r10, [rax+48h]
0x140008907  lea     rax, [r11+8]
0x14000890b  mov     [r11-18h], rax
0x14000890f  mov     rax, [rsp+48h+arg_28]
0x140008914  mov     [r11-20h], rax
0x140008918  mov     rax, [rsp+48h+arg_20]
0x14000891d  mov     [r11-28h], rax
0x140008921  mov     rax, r10
0x140008924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008929  mov     eax, [rsp+48h+arg_0]
0x14000892d  add     rsp, 48h
0x140008931  retn
```
