# CWsmLogConfig::GetConfig(void)

- ea: `0x14000a980`
- end: `0x14000a9a3`
- name: `?GetConfig@CWsmLogConfig@@UEBAQEAU_WSM_LOG_CONFIG@@XZ`
- size: `35`
- prototype: `struct _WSM_LOG_CONFIG *__fastcall(CWsmLogConfig *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000a9b0`

## callees

- `0x14000a980`

## pseudocode

```c
struct _WSM_LOG_CONFIG *__fastcall CWsmLogConfig::GetConfig(CWsmLogConfig *this)
{
  struct _WSM_LOG_CONFIG *result; // rax

  result = (struct _WSM_LOG_CONFIG *)((*((_QWORD *)this + 5) + 8LL) & -(__int64)(*((_QWORD *)this + 5) != 0));
  if ( (!result || !*(_QWORD *)result)
    && !*(_QWORD *)(((*((_QWORD *)this + 5) + 8LL) & -(__int64)(*((_QWORD *)this + 5) != 0)) + 8) )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000a980  mov     rax, [rcx+28h]
0x14000a984  lea     rcx, [rax+8]
0x14000a988  neg     rax
0x14000a98b  sbb     rax, rax
0x14000a98e  and     rax, rcx
0x14000a991  jz      short loc_14000A999
0x14000a993  cmp     qword ptr [rax], 0
0x14000a997  jnz     short locret_14000A9A2
0x14000a999  cmp     qword ptr [rax+8], 0
0x14000a99e  ja      short locret_14000A9A2
0x14000a9a0  xor     eax, eax
0x14000a9a2  retn
```
