# PlugPlayServiceStop

- ea: `0x1800160dc`
- end: `0x18001610a`
- name: `PlugPlayServiceStop`
- size: `46`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x18000e750`
- `0x180015f80`

## callees

- `0x180016050`

## pseudocode

```c
__int64 __fastcall PlugPlayServiceStop(__int64 a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  PlugPlayServiceStatusUpdate(a1, 3u, 0);
  PlugPlayServiceStatusUpdate(v1, 1u, 0);
  result = 0;
  PlugPlayServiceStatusHandle = 0;
  return result;
}

```

## disassembly

```asm
0x1800160dc  sub     rsp, 28h
0x1800160e0  xor     r8d, r8d
0x1800160e3  lea     edx, [r8+3]
0x1800160e7  call    PlugPlayServiceStatusUpdate
0x1800160ec  xor     r8d, r8d
0x1800160ef  lea     edx, [r8+1]
0x1800160f3  call    PlugPlayServiceStatusUpdate
0x1800160f8  xor     eax, eax
0x1800160fa  mov     cs:PlugPlayServiceStatusHandle, 0
0x180016105  add     rsp, 28h
0x180016109  retn
```
