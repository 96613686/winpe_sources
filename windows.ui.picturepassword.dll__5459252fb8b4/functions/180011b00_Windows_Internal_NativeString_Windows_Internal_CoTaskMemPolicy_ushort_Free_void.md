# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x180011b00`
- end: `0x180011b34`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011534`
- `0x180011e88`
- `0x180013860`
- `0x180013b88`
- `0x180013cc0`

## callees

- `0x180011b00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011b11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011b11`

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
0x180011b00  push    rbx
0x180011b02  sub     rsp, 20h
0x180011b06  mov     rbx, rcx
0x180011b09  mov     rcx, [rcx]; pv
0x180011b0c  test    rcx, rcx
0x180011b0f  jz      short loc_180011B1E
0x180011b11  call    cs:__imp_CoTaskMemFree
0x180011b17  mov     qword ptr [rbx], 0
0x180011b1e  mov     qword ptr [rbx+8], 0
0x180011b26  mov     qword ptr [rbx+10h], 0
0x180011b2e  add     rsp, 20h
0x180011b32  pop     rbx
0x180011b33  retn
```
