# ATL::CComControlBase::OnDraw(ATL_DRAWINFO &)

- ea: `0x180007c30`
- end: `0x180007c8d`
- name: `?OnDraw@CComControlBase@ATL@@UEAAJAEAUATL_DRAWINFO@@@Z`
- size: `93`
- prototype: `__int64 __fastcall(ATL::CComControlBase *__hidden this, struct ATL_DRAWINFO *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `GDI32!SetTextAlign` at `0x180007c42`
- `GDI32!SetTextAlign` at `0x180007c42`
- `GDI32!TextOutA` at `0x180007c7f`
- `GDI32!TextOutA` at `0x180007c7f`

## pseudocode

```c
__int64 __fastcall ATL::CComControlBase::OnDraw(ATL::CComControlBase *this, HDC *a2)
{
  _DWORD *v3; // rcx

  SetTextAlign(a2[4], 0x1Eu);
  v3 = a2[5];
  TextOutA(a2[4], *v3 + (v3[2] - *v3) / 2, v3[1] + (v3[3] - v3[1]) / 2, "ATL 8.0", 7);
  return 0;
}

```

## disassembly

```asm
0x180007c30  push    rbx
0x180007c32  sub     rsp, 30h
0x180007c36  mov     rbx, rdx
0x180007c39  mov     edx, 1Eh; align
0x180007c3e  mov     rcx, [rbx+20h]; hdc
0x180007c42  call    cs:__imp_SetTextAlign
0x180007c48  mov     rcx, [rbx+28h]
0x180007c4c  lea     r9, String; "ATL 8.0"
0x180007c53  mov     [rsp+38h+c], 7; c
0x180007c5b  mov     eax, [rcx+0Ch]
0x180007c5e  sub     eax, [rcx+4]
0x180007c61  cdq
0x180007c62  sub     eax, edx
0x180007c64  sar     eax, 1
0x180007c66  mov     r8d, eax
0x180007c69  mov     eax, [rcx+8]
0x180007c6c  sub     eax, [rcx]
0x180007c6e  add     r8d, [rcx+4]; y
0x180007c72  cdq
0x180007c73  sub     eax, edx
0x180007c75  sar     eax, 1
0x180007c77  add     eax, [rcx]
0x180007c79  mov     rcx, [rbx+20h]; hdc
0x180007c7d  mov     edx, eax; x
0x180007c7f  call    cs:__imp_TextOutA
0x180007c85  xor     eax, eax
0x180007c87  add     rsp, 30h
0x180007c8b  pop     rbx
0x180007c8c  retn
```
