# McTryEnable(void)

- ea: `0x180034860`
- end: `0x1800348a7`
- name: `?McTryEnable@@YAXXZ`
- size: `71`
- prototype: `void __fastcall(HKEY)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1800343b8`
- `0x180034640`
- `0x180034860`

## string_xrefs

- `0x180034878`: `SYSTEM\CurrentControlSet\Control\MCUpdate`
- `0x180034896`: `SYSTEM\CurrentControlSet\Control\MCUpdate`

## pseudocode

```c
void __fastcall McTryEnable(HKEY a1)
{
  HKEY v1; // rcx
  unsigned int v2; // r9d
  unsigned int v3; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0;
  if ( !VelocityGetRegDword(a1, L"SYSTEM\\CurrentControlSet\\Control\\MCUpdate", L"SelfHost", &v3) || v3 )
    VelocitySetRegDword(v1, L"SYSTEM\\CurrentControlSet\\Control\\MCUpdate", L"SelfHost", v2);
}

```

## disassembly

```asm
0x180034860  sub     rsp, 28h
0x180034864  lea     r9, [rsp+28h+arg_0]; unsigned int *
0x180034869  mov     [rsp+28h+arg_0], 0
0x180034871  lea     r8, aSelfhost; "SelfHost"
0x180034878  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\MCU"...
0x18003487f  call    ?VelocityGetRegDword@@YAHPEAUHKEY__@@PEBG1PEAK@Z; VelocityGetRegDword(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180034884  test    eax, eax
0x180034886  jz      short loc_18003488F
0x180034888  cmp     [rsp+28h+arg_0], 0
0x18003488d  jz      short loc_1800348A2
0x18003488f  lea     r8, aSelfhost; "SelfHost"
0x180034896  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\MCU"...
0x18003489d  call    ?VelocitySetRegDword@@YAHPEAUHKEY__@@PEBG1K@Z; VelocitySetRegDword(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800348a2  add     rsp, 28h
0x1800348a6  retn
```
