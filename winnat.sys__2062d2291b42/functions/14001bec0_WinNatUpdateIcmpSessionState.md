# WinNatUpdateIcmpSessionState

- ea: `0x14001bec0`
- end: `0x14001bf37`
- name: `WinNatUpdateIcmpSessionState`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140004ed0`

## callees

- `0x14000caa0`
- `0x14001bec0`

## pseudocode

```c
unsigned __int64 __fastcall WinNatUpdateIcmpSessionState(unsigned int *a1, __int64 a2, __int64 a3)
{
  unsigned __int64 result; // rax
  char v4; // di

  result = a1[30];
  v4 = a2;
  if ( (_DWORD)result != 1 && (_DWORD)result != 58 )
    result = MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  if ( v4 )
  {
    result = 0x624DD2F1A9FBE77LL * (MEMORY[0xFFFFF78000000008] / 0x2710uLL);
    a1[34] = a1[31] + MEMORY[0xFFFFF78000000008] / 0x2710uLL / 0x3E8;
  }
  return result;
}

```

## disassembly

```asm
0x14001bec0  mov     [rsp+arg_0], rbx
0x14001bec5  push    rdi
0x14001bec6  sub     rsp, 20h
0x14001beca  mov     eax, [rcx+78h]
0x14001becd  mov     dil, dl
0x14001bed0  mov     rbx, rcx
0x14001bed3  cmp     eax, 1
0x14001bed6  jz      short loc_14001BEE2
0x14001bed8  cmp     eax, 3Ah ; ':'
0x14001bedb  jz      short loc_14001BEE2
0x14001bedd  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001bee2  test    dil, dil
0x14001bee5  jz      short loc_14001BF2B
0x14001bee7  mov     rcx, 0FFFFF78000000008h
0x14001bef1  mov     rax, 346DC5D63886594Bh
0x14001befb  mov     rcx, [rcx]
0x14001befe  mul     rcx
0x14001bf01  mov     rax, 624DD2F1A9FBE77h
0x14001bf0b  mov     rcx, rdx
0x14001bf0e  shr     rcx, 0Bh
0x14001bf12  mul     rcx
0x14001bf15  sub     rcx, rdx
0x14001bf18  shr     rcx, 1
0x14001bf1b  add     rcx, rdx
0x14001bf1e  shr     rcx, 9
0x14001bf22  add     ecx, [rbx+7Ch]
0x14001bf25  mov     [rbx+88h], ecx
0x14001bf2b  mov     rbx, [rsp+28h+arg_0]
0x14001bf30  add     rsp, 20h
0x14001bf34  pop     rdi
0x14001bf35  retn
```
