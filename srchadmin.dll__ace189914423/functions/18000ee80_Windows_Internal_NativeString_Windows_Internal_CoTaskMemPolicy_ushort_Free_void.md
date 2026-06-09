# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x18000ee80`
- end: `0x18000eeb4`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000eebc`

## callees

- `0x18000ee80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ee91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ee91`

## pseudocode

```c
void __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x18000ee80  push    rbx
0x18000ee82  sub     rsp, 20h
0x18000ee86  mov     rbx, rcx
0x18000ee89  mov     rcx, [rcx]; pv
0x18000ee8c  test    rcx, rcx
0x18000ee8f  jz      short loc_18000EE9E
0x18000ee91  call    cs:__imp_CoTaskMemFree
0x18000ee97  mov     qword ptr [rbx], 0
0x18000ee9e  mov     qword ptr [rbx+8], 0
0x18000eea6  mov     qword ptr [rbx+10h], 0
0x18000eeae  add     rsp, 20h
0x18000eeb2  pop     rbx
0x18000eeb3  retn
```
