# WinNatUpdateIcmpSessionState

- ea: `0x14001b9e0`
- end: `0x14001ba57`
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
- `0x14001b9e0`

## pseudocode

```c
unsigned __int64 __fastcall WinNatUpdateIcmpSessionState(unsigned int *a1, __int64 a2)
{
  unsigned __int64 result; // rax
  char v3; // di

  result = a1[30];
  v3 = a2;
  if ( (_DWORD)result != 1 && (_DWORD)result != 58 )
    result = MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2);
  if ( v3 )
  {
    result = 0x624DD2F1A9FBE77LL * (MEMORY[0xFFFFF78000000008] / 0x2710uLL);
    a1[34] = a1[31] + MEMORY[0xFFFFF78000000008] / 0x2710uLL / 0x3E8;
  }
  return result;
}

```

## disassembly

```asm
0x14001b9e0  mov     [rsp+arg_0], rbx
0x14001b9e5  push    rdi
0x14001b9e6  sub     rsp, 20h
0x14001b9ea  mov     eax, [rcx+78h]
0x14001b9ed  mov     dil, dl
0x14001b9f0  mov     rbx, rcx
0x14001b9f3  cmp     eax, 1
0x14001b9f6  jz      short loc_14001BA02
0x14001b9f8  cmp     eax, 3Ah ; ':'
0x14001b9fb  jz      short loc_14001BA02
0x14001b9fd  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001ba02  test    dil, dil
0x14001ba05  jz      short loc_14001BA4B
0x14001ba07  mov     rcx, 0FFFFF78000000008h
0x14001ba11  mov     rax, 346DC5D63886594Bh
0x14001ba1b  mov     rcx, [rcx]
0x14001ba1e  mul     rcx
0x14001ba21  mov     rax, 624DD2F1A9FBE77h
0x14001ba2b  mov     rcx, rdx
0x14001ba2e  shr     rcx, 0Bh
0x14001ba32  mul     rcx
0x14001ba35  sub     rcx, rdx
0x14001ba38  shr     rcx, 1
0x14001ba3b  add     rcx, rdx
0x14001ba3e  shr     rcx, 9
0x14001ba42  add     ecx, [rbx+7Ch]
0x14001ba45  mov     [rbx+88h], ecx
0x14001ba4b  mov     rbx, [rsp+28h+arg_0]
0x14001ba50  add     rsp, 20h
0x14001ba54  pop     rdi
0x14001ba55  retn
```
