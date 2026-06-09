# SXReader::getContentHandler(ISAXContentHandler * *)

- ea: `0x100404e20`
- end: `0x100404e50`
- name: `?getContentHandler@SXReader@@UEAAJPEAPEAUISAXContentHandler@@@Z`
- size: `48`
- prototype: `__int64 __fastcall(SXReader *__hidden this, struct ISAXContentHandler **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x100404e20`
- `0x100424580`

## pseudocode

```c
struct ISAXContentHandler *__fastcall SXReader::getContentHandler(SXReader *this, struct ISAXContentHandler **a2)
{
  struct ISAXContentHandler *result; // rax

  result = (struct ISAXContentHandler *)*((_QWORD *)this + 3);
  if ( result )
  {
    *a2 = result;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 8LL))(*((_QWORD *)this + 3));
    return 0;
  }
  else
  {
    *a2 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x100404e20  sub     rsp, 28h
0x100404e24  mov     rax, [rcx+18h]
0x100404e28  test    rax, rax
0x100404e2b  jnz     short loc_100404E35
0x100404e2d  mov     [rdx], rax
0x100404e30  add     rsp, 28h
0x100404e34  retn
0x100404e35  mov     [rdx], rax
0x100404e38  mov     rcx, [rcx+18h]
0x100404e3c  mov     rax, [rcx]
0x100404e3f  mov     rax, [rax+8]
0x100404e43  call    cs:__guard_dispatch_icall_fptr
0x100404e49  xor     eax, eax
0x100404e4b  add     rsp, 28h
0x100404e4f  retn
```
