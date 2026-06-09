# StorageService::StorageGrovelerCallback(void)

- ea: `0x18002aeb0`
- end: `0x18002aef1`
- name: `?StorageGrovelerCallback@StorageService@@KAXXZ`
- size: `65`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18002aeb0`

## import_xrefs

- `storageusage!RunStorageGroveler` at `0x18002aed3`
- `storageusage!RunStorageGroveler` at `0x18002aed3`
- `storageusage!CloseFindStorageSearch` at `0x18002aee6`
- `storageusage!CloseFindStorageSearch` at `0x18002aee6`
- `storageusage!OpenStorageTypeSearch` at `0x18002aec2`
- `storageusage!OpenStorageTypeSearch` at `0x18002aec2`

## pseudocode

```c
void StorageService::StorageGrovelerCallback(void)
{
  __int64 v0; // [rsp+30h] [rbp+8h] BYREF

  v0 = 0;
  if ( (int)OpenStorageTypeSearch(&v0) >= 0 )
    RunStorageGroveler(v0, 0);
  if ( v0 )
    CloseFindStorageSearch(&v0);
}

```

## disassembly

```asm
0x18002aeb0  sub     rsp, 28h
0x18002aeb4  lea     rcx, [rsp+28h+arg_0]
0x18002aeb9  mov     [rsp+28h+arg_0], 0
0x18002aec2  call    cs:__imp_OpenStorageTypeSearch
0x18002aec8  test    eax, eax
0x18002aeca  js      short loc_18002AED9
0x18002aecc  mov     rcx, [rsp+28h+arg_0]
0x18002aed1  xor     edx, edx
0x18002aed3  call    cs:__imp_RunStorageGroveler
0x18002aed9  cmp     [rsp+28h+arg_0], 0
0x18002aedf  jz      short loc_18002AEEC
0x18002aee1  lea     rcx, [rsp+28h+arg_0]
0x18002aee6  call    cs:__imp_CloseFindStorageSearch
0x18002aeec  add     rsp, 28h
0x18002aef0  retn
```
