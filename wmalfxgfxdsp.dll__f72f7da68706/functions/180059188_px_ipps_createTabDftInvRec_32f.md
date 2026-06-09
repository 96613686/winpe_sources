# px_ipps_createTabDftInvRec_32f

- ea: `0x180059188`
- end: `0x1800591e1`
- name: `px_ipps_createTabDftInvRec_32f`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001cbe0`

## callees

- `0x18001f910`
- `0x180059188`

## pseudocode

```c
__int64 __fastcall px_ipps_createTabDftInvRec_32f(int a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 result; // rax
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  __int64 v7; // rbx

  v3 = (a1 + 3) / 4;
  result = px_ippsMalloc_8u((unsigned int)(8 * ((a1 + 3) / 4)));
  if ( result )
  {
    v5 = v3;
    if ( (int)v3 > 0 )
    {
      v6 = (_QWORD *)result;
      v7 = a2 - result;
      do
      {
        *v6 = *(_QWORD *)((char *)v6 + v7);
        ++v6;
        --v5;
      }
      while ( v5 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x180059188  mov     [rsp+arg_0], rbx
0x18005918d  push    rdi
0x18005918e  sub     rsp, 20h
0x180059192  lea     eax, [rcx+3]
0x180059195  mov     rbx, rdx
0x180059198  cdq
0x180059199  and     edx, 3
0x18005919c  add     eax, edx
0x18005919e  sar     eax, 2
0x1800591a1  movsxd  rdi, eax
0x1800591a4  mov     ecx, edi
0x1800591a6  shl     ecx, 3
0x1800591a9  call    px_ippsMalloc_8u
0x1800591ae  mov     r8, rax
0x1800591b1  test    rax, rax
0x1800591b4  jz      short loc_1800591D6
0x1800591b6  mov     rdx, rdi
0x1800591b9  test    edi, edi
0x1800591bb  jle     short loc_1800591D3
0x1800591bd  mov     rcx, rax
0x1800591c0  sub     rbx, rax
0x1800591c3  mov     rax, [rbx+rcx]
0x1800591c7  mov     [rcx], rax
0x1800591ca  lea     rcx, [rcx+8]
0x1800591ce  dec     rdx
0x1800591d1  jnz     short loc_1800591C3
0x1800591d3  mov     rax, r8
0x1800591d6  mov     rbx, [rsp+28h+arg_0]
0x1800591db  add     rsp, 20h
0x1800591df  pop     rdi
0x1800591e0  retn
```
