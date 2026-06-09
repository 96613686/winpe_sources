# SIPolicyStateDeletePolicy

- ea: `0x18001cc4c`
- end: `0x18001cca2`
- name: `SIPolicyStateDeletePolicy`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001c380`

## callees

- `0x18001cc4c`

## pseudocode

```c
__int64 __fastcall SIPolicyStateDeletePolicy(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rax
  __int64 v3; // r9
  _QWORD *v4; // r8
  __int64 *v5; // rcx
  __int64 v6; // r8
  __int64 result; // rax

  v2 = (_QWORD *)(a2 + 832);
  v3 = *(_QWORD *)(a2 + 832);
  if ( *(_QWORD *)(v3 + 8) != a2 + 832
    || (v4 = *(_QWORD **)(a2 + 840), (_QWORD *)*v4 != v2)
    || (*v4 = v3, v5 = (__int64 *)(a1 + 32), *(_QWORD *)(v3 + 8) = v4, v6 = *v5, *(__int64 **)(*v5 + 8) != v5) )
  {
    __fastfail(3u);
  }
  *v2 = v6;
  *(_QWORD *)(a2 + 840) = v5;
  *(_QWORD *)(v6 + 8) = v2;
  *v5 = (__int64)v2;
  result = *(_DWORD *)(a2 + 672) & 0xFFFFFFCF | 0x10;
  *(_DWORD *)(a2 + 672) = result;
  return result;
}

```

## disassembly

```asm
0x18001cc4c  lea     rax, [rdx+340h]
0x18001cc53  mov     r9, [rax]
0x18001cc56  cmp     [r9+8], rax
0x18001cc5a  jnz     short loc_18001CC9B
0x18001cc5c  mov     r8, [rax+8]
0x18001cc60  cmp     [r8], rax
0x18001cc63  jnz     short loc_18001CC9B
0x18001cc65  mov     [r8], r9
0x18001cc68  add     rcx, 20h ; ' '
0x18001cc6c  mov     [r9+8], r8
0x18001cc70  mov     r8, [rcx]
0x18001cc73  cmp     [r8+8], rcx
0x18001cc77  jnz     short loc_18001CC9B
0x18001cc79  mov     [rax], r8
0x18001cc7c  mov     [rax+8], rcx
0x18001cc80  mov     [r8+8], rax
0x18001cc84  mov     [rcx], rax
0x18001cc87  mov     eax, [rdx+2A0h]
0x18001cc8d  and     eax, 0FFFFFFDFh
0x18001cc90  or      eax, 10h
0x18001cc93  mov     [rdx+2A0h], eax
0x18001cc99  retn
0x18001cc9b  mov     ecx, 3
0x18001cca0  int     29h; Win8: RtlFailFast(ecx)
```
