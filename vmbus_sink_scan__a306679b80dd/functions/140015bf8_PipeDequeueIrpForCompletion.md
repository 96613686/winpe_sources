# PipeDequeueIrpForCompletion

- ea: `0x140015bf8`
- end: `0x140015c3c`
- name: `PipeDequeueIrpForCompletion`
- size: `68`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400019c0`
- `0x140002c50`
- `0x14001661c`

## callees

- `0x140015bf8`

## pseudocode

```c
char __fastcall PipeDequeueIrpForCompletion(__int64 a1, int a2)
{
  _QWORD *v2; // rdx
  __int64 v3; // r8
  _QWORD *v4; // rax
  char result; // al

  *(_DWORD *)(a1 + 48) = a2;
  v2 = (_QWORD *)(a1 + 136);
  v3 = *(_QWORD *)(a1 + 136);
  if ( *(_QWORD *)(v3 + 8) != a1 + 136 || (v4 = *(_QWORD **)(a1 + 144), (_QWORD *)*v4 != v2) )
    __fastfail(3u);
  *v4 = v3;
  *(_QWORD *)(v3 + 8) = v4;
  if ( _InterlockedExchange64((volatile __int64 *)(a1 + 104), 0) )
    return 1;
  *(_QWORD *)(a1 + 144) = a1 + 136;
  result = 0;
  *v2 = v2;
  return result;
}

```

## disassembly

```asm
0x140015bf8  mov     [rcx+30h], edx
0x140015bfb  lea     rdx, [rcx+88h]
0x140015c02  mov     r8, [rdx]
0x140015c05  cmp     [r8+8], rdx
0x140015c09  jnz     short loc_140015C35
0x140015c0b  mov     rax, [rdx+8]
0x140015c0f  cmp     [rax], rdx
0x140015c12  jnz     short loc_140015C35
0x140015c14  mov     [rax], r8
0x140015c17  mov     [r8+8], rax
0x140015c1b  xor     eax, eax
0x140015c1d  xchg    rax, [rcx+68h]
0x140015c21  test    rax, rax
0x140015c24  jz      short loc_140015C2A
0x140015c26  mov     al, 1
0x140015c28  retn
0x140015c2a  mov     [rdx+8], rdx
0x140015c2e  xor     al, al
0x140015c30  mov     [rdx], rdx
0x140015c33  retn
0x140015c35  mov     ecx, 3
0x140015c3a  int     29h; Win8: RtlFailFast(ecx)
```
