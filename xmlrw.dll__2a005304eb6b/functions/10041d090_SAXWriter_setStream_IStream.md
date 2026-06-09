# SAXWriter::setStream(IStream *)

- ea: `0x10041d090`
- end: `0x10041d11c`
- name: `?setStream@SAXWriter@@QEAAXPEAUIStream@@@Z`
- size: `140`
- prototype: `void __fastcall(SAXWriter *__hidden this, struct IStream *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x10041d270`
- `0x10041da70`

## callees

- `0x10041d090`
- `0x100439df0`

## pseudocode

```c
void __fastcall SAXWriter::setStream(SAXWriter *this, struct IStream *a2)
{
  __int64 v4; // rsi

  if ( *((_QWORD *)this + 13) )
    (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)this + 184LL))(this);
  v4 = *((_QWORD *)this + 12);
  if ( a2 )
    ((void (__fastcall *)(struct IStream *))a2->lpVtbl->AddRef)(a2);
  *((_QWORD *)this + 12) = a2;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( *((_QWORD *)this + 13) )
    (*(void (__fastcall **)(SAXWriter *, _QWORD))(*(_QWORD *)this + 208LL))(this, *((_QWORD *)this + 12));
}

```

## disassembly

```asm
0x10041d090  mov     [rsp+arg_0], rbx
0x10041d095  mov     [rsp+arg_8], rsi
0x10041d09a  push    rdi
0x10041d09b  sub     rsp, 20h
0x10041d09f  cmp     qword ptr [rcx+68h], 0
0x10041d0a4  mov     rdi, rdx
0x10041d0a7  mov     rbx, rcx
0x10041d0aa  jz      short loc_10041D0BC
0x10041d0ac  mov     rax, [rcx]
0x10041d0af  mov     rax, [rax+0B8h]
0x10041d0b6  call    cs:__guard_dispatch_icall_fptr
0x10041d0bc  mov     rsi, [rbx+60h]
0x10041d0c0  test    rdi, rdi
0x10041d0c3  jz      short loc_10041D0D5
0x10041d0c5  mov     rax, [rdi]
0x10041d0c8  mov     rcx, rdi
0x10041d0cb  mov     rax, [rax+8]
0x10041d0cf  call    cs:__guard_dispatch_icall_fptr
0x10041d0d5  mov     [rbx+60h], rdi
0x10041d0d9  test    rsi, rsi
0x10041d0dc  jz      short loc_10041D0EE
0x10041d0de  mov     rax, [rsi]
0x10041d0e1  mov     rcx, rsi
0x10041d0e4  mov     rax, [rax+10h]
0x10041d0e8  call    cs:__guard_dispatch_icall_fptr
0x10041d0ee  cmp     qword ptr [rbx+68h], 0
0x10041d0f3  jz      short loc_10041D10C
0x10041d0f5  mov     rax, [rbx]
0x10041d0f8  mov     rcx, rbx
0x10041d0fb  mov     rdx, [rbx+60h]
0x10041d0ff  mov     rax, [rax+0D0h]
0x10041d106  call    cs:__guard_dispatch_icall_fptr
0x10041d10c  mov     rbx, [rsp+28h+arg_0]
0x10041d111  mov     rsi, [rsp+28h+arg_8]
0x10041d116  add     rsp, 20h
0x10041d11a  pop     rdi
0x10041d11b  retn
```
