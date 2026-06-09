# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x1800291d4`
- end: `0x180029208`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007390`
- `0x1800228e8`
- `0x1800291c8`

## callees

- `0x1800291d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800291e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800291e5`

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
0x1800291d4  push    rbx
0x1800291d6  sub     rsp, 20h
0x1800291da  mov     rbx, rcx
0x1800291dd  mov     rcx, [rcx]; pv
0x1800291e0  test    rcx, rcx
0x1800291e3  jz      short loc_1800291F2
0x1800291e5  call    cs:__imp_CoTaskMemFree
0x1800291eb  mov     qword ptr [rbx], 0
0x1800291f2  mov     qword ptr [rbx+8], 0
0x1800291fa  mov     qword ptr [rbx+10h], 0
0x180029202  add     rsp, 20h
0x180029206  pop     rbx
0x180029207  retn
```
