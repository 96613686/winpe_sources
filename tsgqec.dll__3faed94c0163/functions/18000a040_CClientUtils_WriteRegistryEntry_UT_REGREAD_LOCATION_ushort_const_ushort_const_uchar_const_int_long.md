# CClientUtils::WriteRegistryEntry(UT_REGREAD_LOCATION,ushort const *,ushort const *,uchar * const,int,long)

- ea: `0x18000a040`
- end: `0x18000a07e`
- name: `?WriteRegistryEntry@CClientUtils@@UEAAHW4UT_REGREAD_LOCATION@@PEBG1QEAEHJ@Z`
- size: `62`
- prototype: `int __high(enum UT_REGREAD_LOCATION, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *const, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180009d6c`

## pseudocode

```c
__int64 __fastcall CClientUtils::WriteRegistryEntry(
        __int64 a1,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        BYTE *lpData,
        DWORD cbData,
        DWORD dwType)
{
  return CClientUtils::WriteRegistryEntry((HKEY)((a2 != 0) - 0x7FFFFFFFLL), a3, a4, lpData, cbData, dwType);
}

```

## disassembly

```asm
0x18000a040  sub     rsp, 38h
0x18000a044  mov     eax, [rsp+38h+arg_30]
0x18000a048  neg     edx
0x18000a04a  mov     r10, r9
0x18000a04d  mov     [rsp+38h+dwType], eax; dwType
0x18000a051  mov     eax, [rsp+38h+arg_28]
0x18000a055  sbb     rcx, rcx
0x18000a058  mov     r9, [rsp+38h+lpData]; lpData
0x18000a05d  mov     r11, r8
0x18000a060  neg     rcx
0x18000a063  mov     [rsp+38h+cbData], eax; cbData
0x18000a067  add     rcx, 0FFFFFFFF80000001h; hKey
0x18000a06e  mov     r8, r10; unsigned __int16 *
0x18000a071  mov     rdx, r11; unsigned __int16 *
0x18000a074  call    ?WriteRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1QEAEHJ@Z; CClientUtils::WriteRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar * const,int,long)
0x18000a079  add     rsp, 38h
0x18000a07d  retn
```
