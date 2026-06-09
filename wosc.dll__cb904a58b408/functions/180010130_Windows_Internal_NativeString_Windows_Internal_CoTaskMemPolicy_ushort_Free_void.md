# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x180010130`
- end: `0x180010164`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `35`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009e7c`
- `0x18000a2e8`
- `0x180016b40`
- `0x180016ca0`
- `0x180016e00`
- `0x180016f60`
- `0x1800170c0`
- `0x180017220`
- `0x180019d84`
- `0x180022738`
- `0x180022a8c`
- `0x18002612c`
- `0x180026518`
- `0x180028f90`
- `0x1800290ac`
- `0x18002bb50`
- `0x180040c4c`
- `0x180049318`
- `0x18004f93c`
- `0x18004fbd8`
- `0x180050000`
- `0x1800501b0`
- `0x1800505d0`
- `0x1800506e0`
- `0x180050850`
- `0x18005138c`
- `0x1800514e8`
- `0x1800515a4`
- `0x180051950`
- `0x180051efc`
- `0x180052094`
- `0x1800521a8`
- `0x180052280`
- `0x180052570`
- `0x180056cc9`

## callees

- `0x180010130`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010141`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010141`

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
0x180010130  push    rbx
0x180010132  sub     rsp, 20h
0x180010136  mov     rbx, rcx
0x180010139  mov     rcx, [rcx]; pv
0x18001013c  test    rcx, rcx
0x18001013f  jz      short loc_18001014E
0x180010141  call    cs:__imp_CoTaskMemFree
0x180010147  mov     qword ptr [rbx], 0
0x18001014e  mov     qword ptr [rbx+8], 0
0x180010156  mov     qword ptr [rbx+10h], 0
0x18001015e  add     rsp, 20h
0x180010162  pop     rbx
0x180010163  retn
```
