# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x180031454`
- end: `0x180031488`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: ``
- caller_count: `17`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d678`
- `0x18002d494`
- `0x18002d900`
- `0x18002da1c`
- `0x18002dafc`
- `0x18002eacc`
- `0x18002f100`
- `0x1800301f0`
- `0x180031d0c`
- `0x180031fac`
- `0x180032030`
- `0x180032564`
- `0x180032948`
- `0x180032de0`
- `0x180032ff0`
- `0x180033840`
- `0x1800338d0`

## callees

- `0x180031454`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031465`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031465`

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
0x180031454  push    rbx
0x180031456  sub     rsp, 20h
0x18003145a  mov     rbx, rcx
0x18003145d  mov     rcx, [rcx]; pv
0x180031460  test    rcx, rcx
0x180031463  jz      short loc_180031472
0x180031465  call    cs:__imp_CoTaskMemFree
0x18003146b  mov     qword ptr [rbx], 0
0x180031472  mov     qword ptr [rbx+8], 0
0x18003147a  mov     qword ptr [rbx+10h], 0
0x180031482  add     rsp, 20h
0x180031486  pop     rbx
0x180031487  retn
```
