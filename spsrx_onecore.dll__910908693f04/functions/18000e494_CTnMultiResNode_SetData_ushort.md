# CTnMultiResNode::SetData(ushort *)

- ea: `0x18000e494`
- end: `0x18000e4ed`
- name: `?SetData@CTnMultiResNode@@QEAAJPEAG@Z`
- size: `89`
- prototype: `__int64 __fastcall(CTnMultiResNode *__hidden this, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180009930`
- `0x18000a14c`
- `0x18000a4c8`
- `0x18000b208`
- `0x18000d1c0`

## callees

- `0x18000e494`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18000e4c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18000e4c6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e4b4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e4b4`

## pseudocode

```c
__int64 __fastcall CTnMultiResNode::SetData(CTnMultiResNode *this, unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  void *v4; // rcx
  __int64 v6; // rax

  v3 = 0;
  v4 = (void *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 7) = 0;
  }
  if ( a2 )
  {
    v6 = _o__wcsdup(a2);
    *((_QWORD *)this + 7) = v6;
    if ( !v6 )
      return (unsigned int)-2147024882;
  }
  return v3;
}

```

## disassembly

```asm
0x18000e494  mov     [rsp+arg_0], rbx
0x18000e499  mov     [rsp+arg_8], rsi
0x18000e49e  push    rdi
0x18000e49f  sub     rsp, 20h
0x18000e4a3  mov     rdi, rcx
0x18000e4a6  xor     ebx, ebx
0x18000e4a8  mov     rcx, [rcx+38h]; Block
0x18000e4ac  mov     rsi, rdx
0x18000e4af  test    rcx, rcx
0x18000e4b2  jz      short loc_18000E4BE
0x18000e4b4  call    cs:__imp_free
0x18000e4ba  mov     [rdi+38h], rbx
0x18000e4be  test    rsi, rsi
0x18000e4c1  jz      short loc_18000E4DB
0x18000e4c3  mov     rcx, rsi
0x18000e4c6  call    cs:__imp__o__wcsdup
0x18000e4cc  test    rax, rax
0x18000e4cf  mov     [rdi+38h], rax
0x18000e4d3  mov     ecx, 8007000Eh
0x18000e4d8  cmovz   ebx, ecx
0x18000e4db  mov     rsi, [rsp+28h+arg_8]
0x18000e4e0  mov     eax, ebx
0x18000e4e2  mov     rbx, [rsp+28h+arg_0]
0x18000e4e7  add     rsp, 20h
0x18000e4eb  pop     rdi
0x18000e4ec  retn
```
