# OncRpcDrcpTableEntryRemove

- ea: `0x1400115f4`
- end: `0x140011637`
- name: `OncRpcDrcpTableEntryRemove`
- size: `67`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140010904`
- `0x140011184`
- `0x140011280`

## callees

- `0x1400115f4`

## pseudocode

```c
_QWORD *__fastcall OncRpcDrcpTableEntryRemove(__int64 a1, _QWORD *a2)
{
  __int64 v2; // r8
  _QWORD *v3; // rcx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  _QWORD *result; // rax

  v2 = a2[3];
  if ( *(_QWORD **)(v2 + 8) != a2 + 3
    || (v3 = (_QWORD *)a2[4], (_QWORD *)*v3 != a2 + 3)
    || (*v3 = v2, *(_QWORD *)(v2 + 8) = v3, v4 = a2 + 5, v5 = a2[5], *(_QWORD **)(v5 + 8) != v4)
    || (result = (_QWORD *)v4[1], (_QWORD *)*result != v4) )
  {
    __fastfail(3u);
  }
  *result = v5;
  *(_QWORD *)(v5 + 8) = result;
  return result;
}

```

## disassembly

```asm
0x1400115f4  lea     rax, [rdx+18h]
0x1400115f8  mov     r8, [rax]
0x1400115fb  cmp     [r8+8], rax
0x1400115ff  jnz     short loc_140011630
0x140011601  mov     rcx, [rax+8]
0x140011605  cmp     [rcx], rax
0x140011608  jnz     short loc_140011630
0x14001160a  mov     [rcx], r8
0x14001160d  mov     [r8+8], rcx
0x140011611  lea     rcx, [rdx+28h]
0x140011615  mov     rdx, [rcx]
0x140011618  cmp     [rdx+8], rcx
0x14001161c  jnz     short loc_140011630
0x14001161e  mov     rax, [rcx+8]
0x140011622  cmp     [rax], rcx
0x140011625  jnz     short loc_140011630
0x140011627  mov     [rax], rdx
0x14001162a  mov     [rdx+8], rax
0x14001162e  retn
0x140011630  mov     ecx, 3
0x140011635  int     29h; Win8: RtlFailFast(ecx)
```
