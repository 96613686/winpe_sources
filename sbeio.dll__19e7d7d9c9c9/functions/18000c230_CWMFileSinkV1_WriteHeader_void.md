# CWMFileSinkV1::WriteHeader(void)

- ea: `0x18000c230`
- end: `0x18000c294`
- name: `?WriteHeader@CWMFileSinkV1@@IEAAJXZ`
- size: `100`
- prototype: `__int64 __fastcall(CWMFileSinkV1 *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009630`
- `0x18000b124`

## callees

- `0x18000c230`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CWMFileSinkV1::WriteHeader(CWMFileSinkV1 *this)
{
  __int64 v1; // rax
  __int64 v2; // r8
  __int64 v4; // rdx
  int v5; // ecx
  __int64 result; // rax
  unsigned int v7; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_QWORD *)this;
  v2 = *((unsigned int *)this + 56);
  v4 = *((_QWORD *)this + 29);
  v7 = 0;
  v5 = (*(__int64 (__fastcall **)(CWMFileSinkV1 *, __int64, __int64, unsigned int *))(v1 + 208))(this, v4, v2, &v7);
  if ( v5 >= 0 )
  {
    *((_QWORD *)this + 33) += v7;
    result = (unsigned int)v5;
    *((_DWORD *)this + 6) = 1;
  }
  else
  {
    *((_DWORD *)this + 2314) = 1;
    return 3222077464LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000c230  push    rbx
0x18000c232  sub     rsp, 30h
0x18000c236  mov     rax, [rcx]
0x18000c239  lea     r9, [rsp+38h+arg_0]
0x18000c23e  mov     r8d, [rcx+0E0h]
0x18000c245  mov     rbx, rcx
0x18000c248  mov     rdx, [rcx+0E8h]
0x18000c24f  mov     [rsp+38h+arg_0], 0
0x18000c257  mov     rax, [rax+0D0h]
0x18000c25e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c263  mov     ecx, eax
0x18000c265  test    eax, eax
0x18000c267  jns     short loc_18000C27A
0x18000c269  mov     dword ptr [rbx+2428h], 1
0x18000c273  mov     eax, 0C00D0018h
0x18000c278  jmp     short loc_18000C28E
0x18000c27a  mov     eax, [rsp+38h+arg_0]
0x18000c27e  add     [rbx+108h], rax
0x18000c285  mov     eax, ecx
0x18000c287  mov     dword ptr [rbx+18h], 1
0x18000c28e  add     rsp, 30h
0x18000c292  pop     rbx
0x18000c293  retn
```
