# _RegOpenKey(HKEY__ *,ushort const *,ulong,HKEY__ * *)

- ea: `0x180016580`
- end: `0x1800165b0`
- name: `?_RegOpenKey@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z`
- size: `48`
- prototype: `LSTATUS __fastcall(HKEY, const unsigned __int16 *, __int64, HKEY *phkResult)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180013858`
- `0x1800139b0`
- `0x18002daf4`
- `0x1800329f0`

## callees

- `0x180016580`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016599`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016599`

## pseudocode

```c
LSTATUS __fastcall _RegOpenKey(HKEY a1, const unsigned __int16 *a2, __int64 a3, HKEY *phkResult)
{
  LSTATUS result; // eax

  *phkResult = 0;
  result = RegOpenKeyExW(a1, a2, 0, 1u, phkResult);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180016580  sub     rsp, 38h
0x180016584  mov     qword ptr [r9], 0
0x18001658b  xor     r8d, r8d; ulOptions
0x18001658e  mov     [rsp+38h+phkResult], r9; phkResult
0x180016593  mov     r9d, 1; samDesired
0x180016599  call    cs:__imp_RegOpenKeyExW
0x18001659f  test    eax, eax
0x1800165a1  jle     short loc_1800165AB
0x1800165a3  movzx   eax, ax
0x1800165a6  or      eax, 80070000h
0x1800165ab  add     rsp, 38h
0x1800165af  retn
```
