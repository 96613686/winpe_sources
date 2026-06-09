# CWsmTrackingConfig::GetConfig(void)

- ea: `0x14000a9c0`
- end: `0x14000a9e9`
- name: `?GetConfig@CWsmTrackingConfig@@UEBAQEAU_WSM_TRACKING_CONFIG@@XZ`
- size: `41`
- prototype: `struct _WSM_TRACKING_CONFIG *__fastcall(CWsmTrackingConfig *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000a9f0`

## callees

- `0x14000a9c0`

## pseudocode

```c
struct _WSM_TRACKING_CONFIG *__fastcall CWsmTrackingConfig::GetConfig(CWsmTrackingConfig *this)
{
  struct _WSM_TRACKING_CONFIG *result; // rax

  result = (struct _WSM_TRACKING_CONFIG *)((*((_QWORD *)this + 5) + 88LL) & -(__int64)(*((_QWORD *)this + 5) != 0));
  if ( !result
    || !*(_QWORD *)result
    && !*(_QWORD *)(((*((_QWORD *)this + 5) + 88LL) & -(__int64)(*((_QWORD *)this + 5) != 0)) + 8)
    && !*(_DWORD *)(((*((_QWORD *)this + 5) + 88LL) & -(__int64)(*((_QWORD *)this + 5) != 0)) + 0x10) )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000a9c0  mov     rax, [rcx+28h]
0x14000a9c4  lea     rcx, [rax+58h]
0x14000a9c8  neg     rax
0x14000a9cb  sbb     rax, rax
0x14000a9ce  xor     edx, edx
0x14000a9d0  and     rax, rcx
0x14000a9d3  jz      short loc_14000A9E5
0x14000a9d5  cmp     [rax], rdx
0x14000a9d8  jnz     short locret_14000A9E8
0x14000a9da  cmp     [rax+8], rdx
0x14000a9de  jnz     short locret_14000A9E8
0x14000a9e0  cmp     [rax+10h], edx
0x14000a9e3  jnz     short locret_14000A9E8
0x14000a9e5  mov     rax, rdx
0x14000a9e8  retn
```
