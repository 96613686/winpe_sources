# InitializeThreadFromPool(void)

- ea: `0x180003c80`
- end: `0x180003cbe`
- name: `?InitializeThreadFromPool@@YA?AUSThreadFromPoolState@@XZ`
- size: `62`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003c00`
- `0x1800053b0`
- `0x18000f150`
- `0x18000f1b0`

## callees

- `0x180003c80`
- `0x180004850`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x180003c96`
- `ntdll!RtlSetThreadErrorMode` at `0x180003c96`
- `RPCRT4!RpcMgmtSetCancelTimeout` at `0x180003c9e`
- `RPCRT4!RpcMgmtSetCancelTimeout` at `0x180003c9e`

## pseudocode

```c
__int64 InitializeThreadFromPool()
{
  CActiveThreadList *v0; // rcx
  ULONG OldMode; // [rsp+30h] [rbp+8h] BYREF

  OldMode = 0;
  RtlSetThreadErrorMode(0x10u, &OldMode);
  RpcMgmtSetCancelTimeout(0);
  if ( g_pActiveThreadList )
    CActiveThreadList::AddCurrent(v0);
  return OldMode;
}

```

## disassembly

```asm
0x180003c80  sub     rsp, 28h
0x180003c84  lea     rdx, [rsp+28h+OldMode]; OldMode
0x180003c89  mov     [rsp+28h+OldMode], 0
0x180003c91  mov     ecx, 10h; NewMode
0x180003c96  call    cs:__imp_RtlSetThreadErrorMode
0x180003c9c  xor     ecx, ecx; Timeout
0x180003c9e  call    cs:__imp_RpcMgmtSetCancelTimeout
0x180003ca4  cmp     cs:g_pActiveThreadList, 0
0x180003cac  jnz     short loc_180003CB7
0x180003cae  mov     eax, [rsp+28h+OldMode]
0x180003cb2  add     rsp, 28h
0x180003cb6  retn
0x180003cb7  call    ?AddCurrent@CActiveThreadList@@QEAAJXZ; CActiveThreadList::AddCurrent(void)
0x180003cbc  jmp     short loc_180003CAE
```
