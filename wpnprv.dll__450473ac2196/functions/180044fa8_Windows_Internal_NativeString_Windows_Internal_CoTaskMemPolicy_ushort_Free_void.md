# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x180044fa8`
- end: `0x180044fdc`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180032b64`
- `0x180033718`
- `0x18004245c`
- `0x180043ee0`
- `0x18006a800`
- `0x18007d52c`
- `0x18007e4b8`
- `0x18007ead0`
- `0x1800812c4`
- `0x1800860f0`

## callees

- `0x180044fa8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044fb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044fb9`

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
0x180044fa8  push    rbx
0x180044faa  sub     rsp, 20h
0x180044fae  mov     rbx, rcx
0x180044fb1  mov     rcx, [rcx]; pv
0x180044fb4  test    rcx, rcx
0x180044fb7  jz      short loc_180044FC6
0x180044fb9  call    cs:__imp_CoTaskMemFree
0x180044fbf  mov     qword ptr [rbx], 0
0x180044fc6  mov     qword ptr [rbx+8], 0
0x180044fce  mov     qword ptr [rbx+10h], 0
0x180044fd6  add     rsp, 20h
0x180044fda  pop     rbx
0x180044fdb  retn
```
