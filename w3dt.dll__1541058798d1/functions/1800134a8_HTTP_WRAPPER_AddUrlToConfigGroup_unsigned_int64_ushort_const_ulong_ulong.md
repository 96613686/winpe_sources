# HTTP_WRAPPER::AddUrlToConfigGroup(unsigned __int64,ushort const *,ulong,ulong)

- ea: `0x1800134a8`
- end: `0x1800134d5`
- name: `?AddUrlToConfigGroup@HTTP_WRAPPER@@QEAAK_KPEBGKK@Z`
- size: `45`
- prototype: `unsigned int __fastcall(HTTP_WRAPPER *__hidden this, unsigned __int64, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012530`
- `0x180012b5c`

## import_xrefs

- `HTTPAPI!HttpAddUrlToUrlGroup` at `0x1800134ce`

## pseudocode

```c
ULONG __fastcall HTTP_WRAPPER::AddUrlToConfigGroup(
        HTTP_WRAPPER *this,
        HTTP_URL_GROUP_ID a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5)
{
  return HttpAddUrlToUrlGroup(a2, a3, __PAIR64__(a4, a5), 0);
}

```

## disassembly

```asm
0x1800134a8  sub     rsp, 38h
0x1800134ac  mov     eax, [rsp+38h+arg_20]
0x1800134b0  mov     r10, r8
0x1800134b3  mov     dword ptr [rsp+38h+var_18+4], r9d
0x1800134b8  mov     rcx, rdx
0x1800134bb  mov     dword ptr [rsp+38h+var_18], eax
0x1800134bf  xor     r9d, r9d
0x1800134c2  mov     r8, [rsp+38h+var_18]
0x1800134c7  mov     rdx, r10
0x1800134ca  add     rsp, 38h
0x1800134ce  jmp     cs:__imp_HttpAddUrlToUrlGroup
```
