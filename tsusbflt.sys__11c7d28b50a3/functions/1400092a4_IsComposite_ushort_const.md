# IsComposite(ushort const *)

- ea: `0x1400092a4`
- end: `0x1400092c0`
- name: `?IsComposite@@YAEPEBG@Z`
- size: `28`
- prototype: `unsigned __int8 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140012010`

## callees

- `0x14000a86c`

## pseudocode

```c
unsigned __int8 __fastcall IsComposite(wchar_t *a1, __int64 a2, __int64 a3, unsigned int *a4)
{
  return IsAnyStringInMultiSzOnStringTable(a1, (const unsigned __int16 **const)&g_CompositeDeviceIdList, 1u, a4);
}

```

## disassembly

```asm
0x1400092a4  sub     rsp, 28h
0x1400092a8  mov     r8d, 1; unsigned int
0x1400092ae  lea     rdx, ?g_CompositeDeviceIdList@@3PAPEBGA; unsigned __int16 **
0x1400092b5  call    ?IsAnyStringInMultiSzOnStringTable@@YAEPEBGQEAPEBGKPEAK@Z; IsAnyStringInMultiSzOnStringTable(ushort const *,ushort const * * const,ulong,ulong *)
0x1400092ba  add     rsp, 28h
0x1400092be  retn
```
