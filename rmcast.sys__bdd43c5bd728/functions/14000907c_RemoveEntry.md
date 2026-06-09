# RemoveEntry

- ea: `0x14000907c`
- end: `0x1400090f0`
- name: `RemoveEntry`
- size: `116`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140008868`
- `0x140008fb0`
- `0x140018d80`

## callees

- `0x14000907c`

## pseudocode

```c
__int64 *__fastcall RemoveEntry(__int64 a1, __int64 *a2)
{
  unsigned int v2; // r11d
  int v4; // ecx
  __int64 v5; // r9
  __int64 v6; // r10
  __int64 *result; // rax
  __int64 **v8; // rcx

  v2 = *(_DWORD *)(a1 + 24);
  v4 = *(_DWORD *)(a1 + 20);
  v5 = v2 & (*((_DWORD *)a2 + 4) >> v4);
  if ( a2 == *(__int64 **)(a1 + 8 * v5 + 192) )
  {
    v6 = *a2;
    if ( *a2 == a1 || (v2 & (*(_DWORD *)(v6 + 16) >> v4)) != (_DWORD)v5 )
      *(_QWORD *)(a1 + 8 * v5 + 192) = 0;
    else
      *(_QWORD *)(a1 + 8 * v5 + 192) = v6;
  }
  result = (__int64 *)*a2;
  if ( *(__int64 **)(*a2 + 8) != a2 || (v8 = (__int64 **)a2[1], *v8 != a2) )
    __fastfail(3u);
  *v8 = result;
  result[1] = (__int64)v8;
  a2[1] = (__int64)a2;
  *a2 = (__int64)a2;
  return result;
}

```

## disassembly

```asm
0x14000907c  mov     r11d, [rcx+18h]
0x140009080  mov     r8, rcx
0x140009083  mov     eax, [rdx+10h]
0x140009086  mov     ecx, [rcx+14h]
0x140009089  shr     eax, cl
0x14000908b  and     eax, r11d
0x14000908e  mov     r9d, eax
0x140009091  cmp     rdx, [r8+rax*8+0C0h]
0x140009099  jnz     short loc_1400090C7
0x14000909b  mov     r10, [rdx]
0x14000909e  cmp     r10, r8
0x1400090a1  jz      short loc_1400090BB
0x1400090a3  mov     eax, [r10+10h]
0x1400090a7  shr     eax, cl
0x1400090a9  and     eax, r11d
0x1400090ac  cmp     eax, r9d
0x1400090af  jnz     short loc_1400090BB
0x1400090b1  mov     [r8+r9*8+0C0h], r10
0x1400090b9  jmp     short loc_1400090C7
0x1400090bb  mov     qword ptr [r8+r9*8+0C0h], 0
0x1400090c7  mov     rax, [rdx]
0x1400090ca  cmp     [rax+8], rdx
0x1400090ce  jnz     short loc_1400090E9
0x1400090d0  mov     rcx, [rdx+8]
0x1400090d4  cmp     [rcx], rdx
0x1400090d7  jnz     short loc_1400090E9
0x1400090d9  mov     [rcx], rax
0x1400090dc  mov     [rax+8], rcx
0x1400090e0  mov     [rdx+8], rdx
0x1400090e4  mov     [rdx], rdx
0x1400090e7  retn
0x1400090e9  mov     ecx, 3
0x1400090ee  int     29h; Win8: RtlFailFast(ecx)
```
