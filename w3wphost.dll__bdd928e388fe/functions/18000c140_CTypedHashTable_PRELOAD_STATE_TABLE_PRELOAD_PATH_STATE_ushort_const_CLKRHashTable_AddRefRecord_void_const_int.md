# CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)

- ea: `0x18000c140`
- end: `0x18000c160`
- name: `?_AddRefRecord@?$CTypedHashTable@VPRELOAD_STATE_TABLE@@VPRELOAD_PATH_STATE@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000b444`
- `0x18000c140`

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
0x18000c140  sub     rsp, 28h
0x18000c144  cmp     edx, 1
0x18000c147  jnz     short loc_18000C151
0x18000c149  lock inc dword ptr [rcx]
0x18000c14c  add     rsp, 28h
0x18000c150  retn
0x18000c151  cmp     edx, 0FFFFFFFFh
0x18000c154  jnz     short loc_18000C15B
0x18000c156  call    ?DereferencePreloadState@PRELOAD_PATH_STATE@@QEAAXXZ; PRELOAD_PATH_STATE::DereferencePreloadState(void)
0x18000c15b  add     rsp, 28h
0x18000c15f  retn
```
