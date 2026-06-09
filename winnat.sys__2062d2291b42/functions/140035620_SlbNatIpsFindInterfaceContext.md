# SlbNatIpsFindInterfaceContext

- ea: `0x140035620`
- end: `0x140035699`
- name: `SlbNatIpsFindInterfaceContext`
- size: `121`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000820c`
- `0x140008928`
- `0x14002f220`
- `0x14002f324`
- `0x140032228`
- `0x140034644`
- `0x1400346bc`

## callees

- `0x14000caa0`
- `0x14002e400`
- `0x140035620`

## pseudocode

```c
PVOID *__fastcall SlbNatIpsFindInterfaceContext(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // edi
  PVOID *i; // rbx

  v3 = a1;
  if ( !(_DWORD)a1 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  for ( i = (PVOID *)qword_140027848; i != &qword_140027848; i = (PVOID *)*i )
  {
    if ( *((_DWORD *)i + 7) == v3 )
    {
      if ( (xmmword_1400272E0 & 4) != 0 )
        WPP_SF_qd(a1, 13, a3, i, v3);
      return i;
    }
  }
  if ( (xmmword_1400272E0 & 4) != 0 )
    WPP_SF_qd(a1, 14, a3, 0, v3);
  return 0;
}

```

## disassembly

```asm
0x140035620  mov     [rsp+arg_0], rbx
0x140035625  push    rdi
0x140035626  sub     rsp, 30h
0x14003562a  mov     edi, ecx
0x14003562c  test    ecx, ecx
0x14003562e  jnz     short loc_140035635
0x140035630  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140035635  mov     rbx, cs:qword_140027848
0x14003563c  lea     rax, qword_140027848
0x140035643  cmp     rbx, rax
0x140035646  jz      short loc_140035671
0x140035648  cmp     [rbx+1Ch], edi
0x14003564b  jz      short loc_140035652
0x14003564d  mov     rbx, [rbx]
0x140035650  jmp     short loc_14003563C
0x140035652  test    byte ptr cs:xmmword_1400272E0, 4
0x140035659  jz      short loc_14003566C
0x14003565b  mov     edx, 0Dh
0x140035660  mov     [rsp+38h+var_18], edi
0x140035664  mov     r9, rbx
0x140035667  call    WPP_SF_qd
0x14003566c  mov     rax, rbx
0x14003566f  jmp     short loc_14003568D
0x140035671  test    byte ptr cs:xmmword_1400272E0, 4
0x140035678  jz      short loc_14003568B
0x14003567a  mov     edx, 0Eh
0x14003567f  mov     [rsp+38h+var_18], edi
0x140035683  xor     r9d, r9d
0x140035686  call    WPP_SF_qd
0x14003568b  xor     eax, eax
0x14003568d  mov     rbx, [rsp+38h+arg_0]
0x140035692  add     rsp, 30h
0x140035696  pop     rdi
0x140035697  retn
```
