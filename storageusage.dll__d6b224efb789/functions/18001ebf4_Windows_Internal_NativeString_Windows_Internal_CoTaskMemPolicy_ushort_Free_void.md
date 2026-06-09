# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x18001ebf4`
- end: `0x18001ec28`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017b84`
- `0x1800180a0`
- `0x180019674`
- `0x180019edc`

## callees

- `0x18001ebf4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ec05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ec05`

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
0x18001ebf4  push    rbx
0x18001ebf6  sub     rsp, 20h
0x18001ebfa  mov     rbx, rcx
0x18001ebfd  mov     rcx, [rcx]; pv
0x18001ec00  test    rcx, rcx
0x18001ec03  jz      short loc_18001EC12
0x18001ec05  call    cs:__imp_CoTaskMemFree
0x18001ec0b  mov     qword ptr [rbx], 0
0x18001ec12  mov     qword ptr [rbx+8], 0
0x18001ec1a  mov     qword ptr [rbx+10h], 0
0x18001ec22  add     rsp, 20h
0x18001ec26  pop     rbx
0x18001ec27  retn
```
