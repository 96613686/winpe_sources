# PgmMoveList

- ea: `0x140010a7c`
- end: `0x140010adb`
- name: `PgmMoveList`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000dd10`

## callees

- `0x140010a7c`

## pseudocode

```c
__int64 __fastcall PgmMoveList(_QWORD **a1, _QWORD *a2)
{
  _QWORD *v2; // r8
  __int64 result; // rax

  if ( *(_QWORD **)(*a2 + 8LL) != a2
    || (v2 = (_QWORD *)a2[1], (_QWORD *)*v2 != a2)
    || (_QWORD **)(*a1)[1] != a1
    || (_QWORD **)*a1[1] != a1
    || (*v2 = a1, a2[1] = a1[1], *a1[1] = a2, result = (__int64)*a1, a1[1] = v2, *(_QWORD ***)(result + 8) != a1)
    || (_QWORD **)*v2 != a1 )
  {
    __fastfail(3u);
  }
  *v2 = result;
  *(_QWORD *)(result + 8) = v2;
  a1[1] = a1;
  *a1 = a1;
  return result;
}

```

## disassembly

```asm
0x140010a7c  mov     rax, [rdx]
0x140010a7f  cmp     [rax+8], rdx
0x140010a83  jnz     short loc_140010AD4
0x140010a85  mov     r8, [rdx+8]
0x140010a89  cmp     [r8], rdx
0x140010a8c  jnz     short loc_140010AD4
0x140010a8e  mov     rax, [rcx]
0x140010a91  cmp     [rax+8], rcx
0x140010a95  jnz     short loc_140010AD4
0x140010a97  mov     rax, [rcx+8]
0x140010a9b  cmp     [rax], rcx
0x140010a9e  jnz     short loc_140010AD4
0x140010aa0  mov     [r8], rcx
0x140010aa3  mov     rax, [rcx+8]
0x140010aa7  mov     [rdx+8], rax
0x140010aab  mov     rax, [rcx+8]
0x140010aaf  mov     [rax], rdx
0x140010ab2  mov     rax, [rcx]
0x140010ab5  mov     [rcx+8], r8
0x140010ab9  cmp     [rax+8], rcx
0x140010abd  jnz     short loc_140010AD4
0x140010abf  cmp     [r8], rcx
0x140010ac2  jnz     short loc_140010AD4
0x140010ac4  mov     [r8], rax
0x140010ac7  mov     [rax+8], r8
0x140010acb  mov     [rcx+8], rcx
0x140010acf  mov     [rcx], rcx
0x140010ad2  retn
0x140010ad4  mov     ecx, 3
0x140010ad9  int     29h; Win8: RtlFailFast(ecx)
```
