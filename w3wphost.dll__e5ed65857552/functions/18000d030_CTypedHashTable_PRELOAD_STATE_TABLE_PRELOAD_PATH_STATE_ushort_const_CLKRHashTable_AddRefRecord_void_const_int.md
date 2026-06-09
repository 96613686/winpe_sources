# CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)

- ea: `0x18000d030`
- end: `0x18000d052`
- name: `?_AddRefRecord@?$CTypedHashTable@VPRELOAD_STATE_TABLE@@VPRELOAD_PATH_STATE@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c248`
- `0x18000d030`

## pseudocode

```c
void __fastcall CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,unsigned short const *,CLKRHashTable>::_AddRefRecord(
        volatile signed __int32 *a1,
        int a2)
{
  if ( a2 == 1 )
  {
    _InterlockedIncrement(a1);
  }
  else if ( a2 == -1 )
  {
    PRELOAD_PATH_STATE::DereferencePreloadState((PRELOAD_PATH_STATE *)a1);
  }
}

```

## disassembly

```asm
0x18000d030  sub     rsp, 28h
0x18000d034  cmp     edx, 1
0x18000d037  jnz     short loc_18000D042
0x18000d039  lock inc dword ptr [rcx]
0x18000d03c  add     rsp, 28h
0x18000d040  retn
0x18000d042  cmp     edx, 0FFFFFFFFh
0x18000d045  jnz     short loc_18000D04C
0x18000d047  call    ?DereferencePreloadState@PRELOAD_PATH_STATE@@QEAAXXZ; PRELOAD_PATH_STATE::DereferencePreloadState(void)
0x18000d04c  add     rsp, 28h
0x18000d050  retn
```
