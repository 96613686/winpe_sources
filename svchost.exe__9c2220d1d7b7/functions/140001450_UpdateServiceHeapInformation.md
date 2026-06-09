# UpdateServiceHeapInformation

- ea: `0x140001450`
- end: `0x14000149b`
- name: `UpdateServiceHeapInformation`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x140001280`

## callees

- `0x140001450`

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
0x140001450  mov     rax, [rcx+40h]
0x140001454  mov     r9, rdx
0x140001457  test    rax, rax
0x14000145a  jz      short loc_140001496
0x14000145c  lea     rax, [rdx+rax*4]
0x140001460  lea     r8, [rax+rax*4]
0x140001464  mov     rax, 47AE147AE147AE15h
0x14000146e  shl     r8, 2
0x140001472  mul     r8
0x140001475  sub     r8, rdx
0x140001478  shr     r8, 1
0x14000147b  add     r8, rdx
0x14000147e  shr     r8, 6
0x140001482  mov     [rcx+40h], r8
0x140001486  mov     [rcx+48h], r9
0x14000148a  cmp     [rcx+38h], r9
0x14000148e  jnb     short locret_140001494
0x140001490  mov     [rcx+38h], r9
0x140001494  retn
0x140001496  mov     r8, r9
0x140001499  jmp     short loc_140001482
```
