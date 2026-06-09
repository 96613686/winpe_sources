# UpdateServiceHeapInformation

- ea: `0x140001430`
- end: `0x14000147a`
- name: `UpdateServiceHeapInformation`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x140001250`

## callees

- `0x140001430`

## pseudocode

```c
unsigned __int64 __fastcall UpdateServiceHeapInformation(_QWORD *a1, unsigned __int64 a2)
{
  unsigned __int64 result; // rax
  unsigned __int64 v3; // r8
  unsigned __int64 v4; // r8

  result = a1[8];
  if ( result )
  {
    v3 = 20 * (a2 + 4 * result);
    result = 0x99999999999999A4uLL * (a2 + 4 * result);
    v4 = v3 / 0x64;
  }
  else
  {
    v4 = a2;
  }
  a1[8] = v4;
  a1[9] = a2;
  if ( a1[7] < a2 )
    a1[7] = a2;
  return result;
}

```

## disassembly

```asm
0x140001430  mov     rax, [rcx+40h]
0x140001434  mov     r9, rdx
0x140001437  test    rax, rax
0x14000143a  jz      short loc_140001475
0x14000143c  lea     rax, [rdx+rax*4]
0x140001440  lea     r8, [rax+rax*4]
0x140001444  mov     rax, 47AE147AE147AE15h
0x14000144e  shl     r8, 2
0x140001452  mul     r8
0x140001455  sub     r8, rdx
0x140001458  shr     r8, 1
0x14000145b  add     r8, rdx
0x14000145e  shr     r8, 6
0x140001462  mov     [rcx+40h], r8
0x140001466  mov     [rcx+48h], r9
0x14000146a  cmp     [rcx+38h], r9
0x14000146e  jnb     short locret_140001474
0x140001470  mov     [rcx+38h], r9
0x140001474  retn
0x140001475  mov     r8, r9
0x140001478  jmp     short loc_140001462
```
