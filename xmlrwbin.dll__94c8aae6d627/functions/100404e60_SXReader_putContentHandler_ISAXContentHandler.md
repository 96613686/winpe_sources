# SXReader::putContentHandler(ISAXContentHandler *)

- ea: `0x100404e60`
- end: `0x100404eb9`
- name: `?putContentHandler@SXReader@@UEAAJPEAUISAXContentHandler@@@Z`
- size: `89`
- prototype: `__int64 __fastcall(SXReader *__hidden this, struct ISAXContentHandler *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x100404e60`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall SXReader::putContentHandler(SXReader *this, struct ISAXContentHandler *a2)
{
  __int64 v2; // rdi

  v2 = *((_QWORD *)this + 3);
  if ( a2 )
    ((void (__fastcall *)(struct ISAXContentHandler *))a2->lpVtbl->AddRef)(a2);
  *((_QWORD *)this + 3) = a2;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  return 0;
}

```

## disassembly

```asm
0x100404e60  mov     [rsp+arg_0], rbx
0x100404e65  mov     [rsp+arg_8], rsi
0x100404e6a  push    rdi
0x100404e6b  sub     rsp, 20h
0x100404e6f  mov     rdi, [rcx+18h]
0x100404e73  mov     rbx, rdx
0x100404e76  mov     rsi, rcx
0x100404e79  test    rdx, rdx
0x100404e7c  jz      short loc_100404E8E
0x100404e7e  mov     rax, [rdx]
0x100404e81  mov     rcx, rdx
0x100404e84  mov     rax, [rax+8]
0x100404e88  call    cs:__guard_dispatch_icall_fptr
0x100404e8e  mov     [rsi+18h], rbx
0x100404e92  test    rdi, rdi
0x100404e95  jz      short loc_100404EA7
0x100404e97  mov     rax, [rdi]
0x100404e9a  mov     rcx, rdi
0x100404e9d  mov     rax, [rax+10h]
0x100404ea1  call    cs:__guard_dispatch_icall_fptr
0x100404ea7  mov     rbx, [rsp+28h+arg_0]
0x100404eac  xor     eax, eax
0x100404eae  mov     rsi, [rsp+28h+arg_8]
0x100404eb3  add     rsp, 20h
0x100404eb7  pop     rdi
0x100404eb8  retn
```
