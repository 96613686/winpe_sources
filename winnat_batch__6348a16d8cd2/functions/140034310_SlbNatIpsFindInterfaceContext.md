# SlbNatIpsFindInterfaceContext

- ea: `0x140034310`
- end: `0x140034389`
- name: `SlbNatIpsFindInterfaceContext`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000820c`
- `0x140008928`
- `0x14002e220`
- `0x14002e324`
- `0x1400310f8`
- `0x140033514`
- `0x14003358c`

## callees

- `0x14000caa0`
- `0x14002d400`
- `0x140034310`

## pseudocode

```c
PVOID *__fastcall SlbNatIpsFindInterfaceContext(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // edi
  PVOID *i; // rbx

  v3 = a1;
  if ( !(_DWORD)a1 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  for ( i = (PVOID *)qword_140026848; i != &qword_140026848; i = (PVOID *)*i )
  {
    if ( *((_DWORD *)i + 7) == v3 )
    {
      if ( (xmmword_1400262E0 & 4) != 0 )
        WPP_SF_qd(a1, 13, a3, i, v3);
      return i;
    }
  }
  if ( (xmmword_1400262E0 & 4) != 0 )
    WPP_SF_qd(a1, 14, a3, 0, v3);
  return 0;
}

```

## disassembly

```asm
0x140034310  mov     [rsp+arg_0], rbx
0x140034315  push    rdi
0x140034316  sub     rsp, 30h
0x14003431a  mov     edi, ecx
0x14003431c  test    ecx, ecx
0x14003431e  jnz     short loc_140034325
0x140034320  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140034325  mov     rbx, cs:qword_140026848
0x14003432c  lea     rax, qword_140026848
0x140034333  cmp     rbx, rax
0x140034336  jz      short loc_140034361
0x140034338  cmp     [rbx+1Ch], edi
0x14003433b  jz      short loc_140034342
0x14003433d  mov     rbx, [rbx]
0x140034340  jmp     short loc_14003432C
0x140034342  test    byte ptr cs:xmmword_1400262E0, 4
0x140034349  jz      short loc_14003435C
0x14003434b  mov     edx, 0Dh
0x140034350  mov     [rsp+38h+var_18], edi
0x140034354  mov     r9, rbx
0x140034357  call    WPP_SF_qd
0x14003435c  mov     rax, rbx
0x14003435f  jmp     short loc_14003437D
0x140034361  test    byte ptr cs:xmmword_1400262E0, 4
0x140034368  jz      short loc_14003437B
0x14003436a  mov     edx, 0Eh
0x14003436f  mov     [rsp+38h+var_18], edi
0x140034373  xor     r9d, r9d
0x140034376  call    WPP_SF_qd
0x14003437b  xor     eax, eax
0x14003437d  mov     rbx, [rsp+38h+arg_0]
0x140034382  add     rsp, 30h
0x140034386  pop     rdi
0x140034387  retn
```
