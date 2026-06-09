# CClientUtils::ReadRegistryEntry(UT_REGREAD_LOCATION,ushort const *,ushort const *,uchar *,int,long,ulong *,int)

- ea: `0x180008e40`
- end: `0x180008e99`
- name: `?ReadRegistryEntry@CClientUtils@@UEAAHW4UT_REGREAD_LOCATION@@PEBG1PEAEHJPEAKH@Z`
- size: `89`
- prototype: `int __high(enum UT_REGREAD_LOCATION, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, int, int, unsigned int *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180008bc0`

## pseudocode

```c
__int64 __fastcall CClientUtils::ReadRegistryEntry(
        __int64 a1,
        int a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        BYTE *lpData,
        DWORD a6,
        int a7,
        unsigned int *a8,
        int a9)
{
  return CClientUtils::ReadRegistryEntry((HKEY)((a2 != 0) - 0x7FFFFFFFLL), a3, a4, lpData, a6, a7, a8, a9);
}

```

## disassembly

```asm
0x180008e40  sub     rsp, 48h
0x180008e44  mov     eax, [rsp+48h+arg_40]
0x180008e4b  neg     edx
0x180008e4d  mov     [rsp+48h+var_10], eax; int
0x180008e51  mov     r10, r9
0x180008e54  mov     rax, [rsp+48h+arg_38]
0x180008e5c  sbb     rcx, rcx
0x180008e5f  mov     r9, [rsp+48h+lpData]; lpData
0x180008e64  mov     r11, r8
0x180008e67  mov     [rsp+48h+var_18], rax; unsigned int *
0x180008e6c  neg     rcx
0x180008e6f  mov     eax, dword ptr [rsp+48h+arg_30]
0x180008e76  add     rcx, 0FFFFFFFF80000001h; hKey
0x180008e7d  mov     dword ptr [rsp+48h+var_20], eax; char
0x180008e81  mov     r8, r10; unsigned __int16 *
0x180008e84  mov     eax, [rsp+48h+arg_28]
0x180008e88  mov     rdx, r11; unsigned __int16 *
0x180008e8b  mov     [rsp+48h+var_28], eax; int
0x180008e8f  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x180008e94  add     rsp, 48h
0x180008e98  retn
```
