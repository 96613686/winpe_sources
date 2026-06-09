# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x1800074d0`
- end: `0x1800074fe`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `46`
- prototype: ``
- caller_count: `25`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005860`
- `0x180005a00`
- `0x180005f10`
- `0x1800061f0`
- `0x1800064c0`
- `0x180007760`
- `0x180007b40`
- `0x180007d34`
- `0x18000bbf0`
- `0x18001ecb0`
- `0x18001f044`
- `0x180025040`
- `0x180030da0`
- `0x180030de0`
- `0x180030f00`
- `0x180030f12`
- `0x180030f36`
- `0x180030f90`
- `0x1800310e0`
- `0x1800311c0`
- `0x180031220`
- `0x180031280`
- `0x1800314ec`
- `0x180031778`
- `0x18003178a`

## callees

- `0x1800074d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800074e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800074e1`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(
        __int64 a1)
{
  void *v2; // rcx
  __int64 result; // rax

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    result = 0;
    *(_QWORD *)a1 = 0;
  }
  else
  {
    result = 0;
  }
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x1800074d0  push    rbx
0x1800074d2  sub     rsp, 20h
0x1800074d6  mov     rbx, rcx
0x1800074d9  mov     rcx, [rcx]; pv
0x1800074dc  test    rcx, rcx
0x1800074df  jz      short loc_1800074FA
0x1800074e1  call    cs:__imp_CoTaskMemFree
0x1800074e7  xor     eax, eax
0x1800074e9  mov     [rbx], rax
0x1800074ec  mov     [rbx+10h], rax
0x1800074f0  mov     [rbx+8], rax
0x1800074f4  add     rsp, 20h
0x1800074f8  pop     rbx
0x1800074f9  retn
0x1800074fa  xor     eax, eax
0x1800074fc  jmp     short loc_1800074EC
```
