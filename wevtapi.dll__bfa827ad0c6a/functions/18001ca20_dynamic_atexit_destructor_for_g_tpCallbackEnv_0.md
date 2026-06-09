# _dynamic_atexit_destructor_for__g_tpCallbackEnv___0

- ea: `0x18001ca20`
- end: `0x18001ca76`
- name: `_dynamic_atexit_destructor_for__g_tpCallbackEnv___0`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001ca20`
- `0x18001ca80`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001ca47`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001ca47`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001ca65`

## pseudocode

```c
int dynamic_atexit_destructor_for__g_tpCallbackEnv___0()
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v2; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  v2 = 0;
  InitOnceBeginInitialize(&stru_18004B748, 0, &v1, &v2);
  if ( v2 )
    return wil_StagingConfig_LogFeatureProcessUsage();
  else
    return InitOnceComplete(&stru_18004B748, 0, 0);
}

```

## disassembly

```asm
0x18001ca20  mov     rax, rsp
0x18001ca23  sub     rsp, 28h
0x18001ca27  lea     r9, [rax+10h]; lpContext
0x18001ca2b  mov     dword ptr [rax+8], 0
0x18001ca32  lea     r8, [rax+8]; fPending
0x18001ca36  mov     qword ptr [rax+10h], 0
0x18001ca3e  xor     edx, edx; dwFlags
0x18001ca40  lea     rcx, stru_18004B748; lpInitOnce
0x18001ca47  call    cs:__imp_InitOnceBeginInitialize
0x18001ca4d  cmp     [rsp+28h+arg_8], 0
0x18001ca53  jnz     short loc_18001CA6C
0x18001ca55  xor     r8d, r8d
0x18001ca58  lea     rcx, stru_18004B748
0x18001ca5f  xor     edx, edx
0x18001ca61  add     rsp, 28h
0x18001ca65  jmp     cs:__imp_InitOnceComplete
0x18001ca6c  call    wil_StagingConfig_LogFeatureProcessUsage
0x18001ca71  add     rsp, 28h
0x18001ca75  retn
```
