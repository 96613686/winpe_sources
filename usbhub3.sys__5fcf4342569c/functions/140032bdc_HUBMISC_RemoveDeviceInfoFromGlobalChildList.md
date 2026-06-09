# HUBMISC_RemoveDeviceInfoFromGlobalChildList

- ea: `0x140032bdc`
- end: `0x140032c1e`
- name: `HUBMISC_RemoveDeviceInfoFromGlobalChildList`
- size: `66`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400211a0`
- `0x140021230`
- `0x1400232a0`
- `0x1400233a0`
- `0x1400258e0`
- `0x140081bb0`

## callees

- `0x140032bdc`

## import_xrefs

- `USBD!USBD_RemoveDeviceFromGlobalList` at `0x140032c0c`
- `USBD!USBD_RemoveDeviceFromGlobalList` at `0x140032c0c`

## pseudocode

```c
__int64 __fastcall HUBMISC_RemoveDeviceInfoFromGlobalChildList(__int64 a1)
{
  __int64 v1; // rdx
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 2160) )
    return USBD_RemoveDeviceFromGlobalList();
  v1 = *(_QWORD *)(a1 + 8);
  if ( (*(_DWORD *)(v1 + 204) & 0x200) != 0 )
    _InterlockedAnd((volatile signed __int32 *)(v1 + 1336), 0xFFFFFFBF);
  if ( *(_QWORD *)(a1 + 2160) )
    return USBD_RemoveDeviceFromGlobalList();
  return result;
}

```

## disassembly

```asm
0x140032bdc  sub     rsp, 28h
0x140032be0  cmp     qword ptr [rcx+870h], 0
0x140032be8  jnz     short loc_140032C0C
0x140032bea  mov     rdx, [rcx+8]
0x140032bee  test    dword ptr [rdx+0CCh], 200h
0x140032bf8  jz      short loc_140032C02
0x140032bfa  lock and dword ptr [rdx+538h], 0FFFFFFBFh
0x140032c02  cmp     qword ptr [rcx+870h], 0
0x140032c0a  jz      short loc_140032C18
0x140032c0c  call    cs:__imp_USBD_RemoveDeviceFromGlobalList
0x140032c13  nop     dword ptr [rax+rax+00h]
0x140032c18  add     rsp, 28h
0x140032c1c  retn
```
