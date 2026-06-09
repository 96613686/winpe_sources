# CShareEnumerator::QueryCCHSharePath(void)

- ea: `0x18000fc64`
- end: `0x18000fc95`
- name: `?QueryCCHSharePath@CShareEnumerator@@QEAAKXZ`
- size: `49`
- prototype: `__int64 __fastcall(CShareEnumerator *this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fa10`
- `0x180010320`
- `0x1800103b0`
- `0x180010d6c`

## callees

- `0x18000fc64`

## pseudocode

```c
__int64 __fastcall CShareEnumerator::QueryCCHSharePath(CShareEnumerator *this)
{
  __int64 result; // rax

  result = *((unsigned int *)this + 147);
  if ( (_DWORD)result == -1 )
  {
    result = -1;
    do
      ++result;
    while ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 72LL * *((unsigned int *)this + 12) + 40) + 2 * result) );
    *((_DWORD *)this + 147) = result;
  }
  return result;
}

```

## disassembly

```asm
0x18000fc64  mov     eax, [rcx+24Ch]
0x18000fc6a  cmp     eax, 0FFFFFFFFh
0x18000fc6d  jnz     short locret_18000FC94
0x18000fc6f  mov     eax, [rcx+30h]
0x18000fc72  lea     rdx, [rax+rax*8]
0x18000fc76  mov     rax, [rcx+38h]
0x18000fc7a  mov     r8, [rax+rdx*8+28h]
0x18000fc7f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fc83  inc     rax
0x18000fc86  cmp     word ptr [r8+rax*2], 0
0x18000fc8c  jnz     short loc_18000FC83
0x18000fc8e  mov     [rcx+24Ch], eax
0x18000fc94  retn
```
