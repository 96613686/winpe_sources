# DVRSourceSink::CreateReaderIdEventName(_GUID *,unsigned __int64,ushort *)

- ea: `0x1800057f4`
- end: `0x18000583c`
- name: `?CreateReaderIdEventName@DVRSourceSink@@YAJPEAU_GUID@@_KPEAG@Z`
- size: `72`
- prototype: `__int64 __fastcall(GUID *rguid, struct _GUID *, unsigned __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000569c`
- `0x180006f20`

## callees

- `0x1800057f4`
- `0x18000774c`

## import_xrefs

- `ole32!StringFromGUID2` at `0x180005825`
- `ole32!StringFromGUID2` at `0x180005825`

## string_xrefs

- `0x180005803`: `Global\SBE.File.Reader.`

## pseudocode

```c
__int64 __fastcall DVRSourceSink::CreateReaderIdEventName(
        GUID *rguid,
        struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  __int64 result; // rax
  __int64 v6; // r11

  result = StringCchCopyW(a3, 0x104u, L"Global\\SBE.File.Reader.");
  if ( (int)result >= 0 )
    return StringFromGUID2(rguid, (LPOLESTR)(v6 + 46), 237) == 0 ? 0x80004005 : 0;
  return result;
}

```

## disassembly

```asm
0x1800057f4  push    rbx
0x1800057f6  sub     rsp, 20h
0x1800057fa  mov     r11, r8
0x1800057fd  mov     rbx, rcx
0x180005800  mov     rcx, r11; unsigned __int16 *
0x180005803  lea     r8, aGlobalSbeFileR; "Global\\SBE.File.Reader."
0x18000580a  mov     edx, 104h; unsigned __int64
0x18000580f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005814  test    eax, eax
0x180005816  js      short loc_180005836
0x180005818  lea     rdx, [r11+2Eh]; lpsz
0x18000581c  mov     r8d, 0EDh; cchMax
0x180005822  mov     rcx, rbx; rguid
0x180005825  call    cs:__imp_StringFromGUID2
0x18000582b  neg     eax
0x18000582d  sbb     eax, eax
0x18000582f  not     eax
0x180005831  and     eax, 80004005h
0x180005836  add     rsp, 20h
0x18000583a  pop     rbx
0x18000583b  retn
```
