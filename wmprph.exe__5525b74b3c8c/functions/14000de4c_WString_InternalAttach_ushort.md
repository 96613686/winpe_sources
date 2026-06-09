# WString::InternalAttach(ushort *)

- ea: `0x14000de4c`
- end: `0x14000de99`
- name: `?InternalAttach@WString@@IEAAXPEAG@Z`
- size: `77`
- prototype: `void __fastcall(WString *__hidden this, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000dcf8`
- `0x14000dee0`
- `0x14000e078`

## callees

- `0x14000d978`
- `0x14000de4c`

## pseudocode

```c
void __fastcall WString::InternalAttach(unsigned __int16 **this, unsigned __int16 *a2)
{
  if ( (*((_BYTE *)this + 12) & 4) != 0 )
  {
    WString::DeleteString(this);
    *((_WORD *)this + 6) = *((_WORD *)this + 6) & 0xFF8F | 0x40;
  }
  else
  {
    WString::DeleteString(this);
    *((_WORD *)this + 6) &= 0xFF8Fu;
  }
  *this = a2;
}

```

## disassembly

```asm
0x14000de4c  mov     [rsp+arg_0], rbx
0x14000de51  push    rdi
0x14000de52  sub     rsp, 20h
0x14000de56  test    byte ptr [rcx+0Ch], 4
0x14000de5a  mov     rdi, rdx
0x14000de5d  mov     rbx, rcx
0x14000de60  jz      short loc_14000DE7D
0x14000de62  call    ?DeleteString@WString@@QEAAXXZ; WString::DeleteString(void)
0x14000de67  movzx   eax, word ptr [rbx+0Ch]
0x14000de6b  mov     ecx, 0FFCFh; this
0x14000de70  and     ax, cx
0x14000de73  or      ax, 40h
0x14000de77  mov     [rbx+0Ch], ax
0x14000de7b  jmp     short loc_14000DE8B
0x14000de7d  call    ?DeleteString@WString@@QEAAXXZ; WString::DeleteString(void)
0x14000de82  mov     eax, 0FF8Fh
0x14000de87  and     [rbx+0Ch], ax
0x14000de8b  mov     [rbx], rdi
0x14000de8e  mov     rbx, [rsp+28h+arg_0]
0x14000de93  add     rsp, 20h
0x14000de97  pop     rdi
0x14000de98  retn
```
