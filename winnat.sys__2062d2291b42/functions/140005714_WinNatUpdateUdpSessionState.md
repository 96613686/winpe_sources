# WinNatUpdateUdpSessionState

- ea: `0x140005714`
- end: `0x14000579d`
- name: `WinNatUpdateUdpSessionState`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140004ed0`

## callees

- `0x140005714`
- `0x14000caa0`

## pseudocode

```c
unsigned __int64 __fastcall WinNatUpdateUdpSessionState(__int64 a1, __int64 a2, __int64 a3)
{
  char v3; // di
  unsigned __int64 result; // rax

  v3 = a2;
  if ( *(_DWORD *)(a1 + 120) != 17 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  if ( v3 || (result = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 72LL) + 112LL), *(_BYTE *)(result + 388)) )
  {
    result = 0x624DD2F1A9FBE77LL * (MEMORY[0xFFFFF78000000008] / 0x2710uLL);
    *(_DWORD *)(a1 + 136) = *(_DWORD *)(a1 + 124) + MEMORY[0xFFFFF78000000008] / 0x2710uLL / 0x3E8;
  }
  return result;
}

```

## disassembly

```asm
0x140005714  mov     [rsp+arg_0], rbx
0x140005719  push    rdi
0x14000571a  sub     rsp, 20h
0x14000571e  cmp     dword ptr [rcx+78h], 11h
0x140005722  mov     dil, dl
0x140005725  mov     rbx, rcx
0x140005728  jnz     short loc_140005796
0x14000572a  test    dil, dil
0x14000572d  jnz     short loc_140005750
0x14000572f  mov     rax, [rbx+50h]
0x140005733  mov     rdx, [rax+48h]
0x140005737  mov     rax, [rdx+70h]
0x14000573b  cmp     [rax+184h], dil
0x140005742  jnz     short loc_140005750
0x140005744  mov     rbx, [rsp+28h+arg_0]
0x140005749  add     rsp, 20h
0x14000574d  pop     rdi
0x14000574e  retn
0x140005750  mov     rcx, 0FFFFF78000000008h
0x14000575a  mov     rax, 346DC5D63886594Bh
0x140005764  mov     rcx, [rcx]
0x140005767  mul     rcx
0x14000576a  mov     rax, 624DD2F1A9FBE77h
0x140005774  mov     rcx, rdx
0x140005777  shr     rcx, 0Bh
0x14000577b  mul     rcx
0x14000577e  sub     rcx, rdx
0x140005781  shr     rcx, 1
0x140005784  add     rcx, rdx
0x140005787  shr     rcx, 9
0x14000578b  add     ecx, [rbx+7Ch]
0x14000578e  mov     [rbx+88h], ecx
0x140005794  jmp     short loc_140005744
0x140005796  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000579b  jmp     short loc_14000572A
```
