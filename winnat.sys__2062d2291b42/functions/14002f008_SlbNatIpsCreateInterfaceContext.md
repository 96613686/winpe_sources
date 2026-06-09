# SlbNatIpsCreateInterfaceContext

- ea: `0x14002f008`
- end: `0x14002f0b9`
- name: `SlbNatIpsCreateInterfaceContext`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000820c`

## callees

- `0x14000caa0`
- `0x14002e008`
- `0x14002f008`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002f048`
- `ntoskrnl!ExAllocatePool2` at `0x14002f048`

## pseudocode

```c
__int64 __fastcall SlbNatIpsCreateInterfaceContext(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  __int64 result; // rax
  __int64 *v5; // rcx

  v3 = a1;
  if ( !(_DWORD)a1 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  if ( (xmmword_1400272E0 & 4) != 0 )
    WPP_SF_d(1026, 15, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, v3);
  result = ExAllocatePool2(64, 64, 1667845715);
  if ( result )
  {
    *(_DWORD *)(result + 56) = 0;
    *(_DWORD *)(result + 28) = v3;
    v5 = (__int64 *)qword_140027850;
    if ( *(PVOID **)qword_140027850 != &qword_140027848 )
      __fastfail(3u);
    *(_QWORD *)result = &qword_140027848;
    *(_QWORD *)(result + 8) = v5;
    *v5 = result;
    qword_140027850 = result;
  }
  else
  {
    if ( (xmmword_1400272D0 & 4) != 0 )
      WPP_SF_d(514, 16, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, v3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14002f008  push    rbx
0x14002f00a  sub     rsp, 20h
0x14002f00e  mov     ebx, ecx
0x14002f010  test    ecx, ecx
0x14002f012  jnz     short loc_14002F019
0x14002f014  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002f019  test    byte ptr cs:xmmword_1400272E0, 4
0x14002f020  jz      short loc_14002F03B
0x14002f022  mov     edx, 0Fh
0x14002f027  lea     r8, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids
0x14002f02e  mov     ecx, 402h
0x14002f033  mov     r9d, ebx
0x14002f036  call    WPP_SF_d
0x14002f03b  mov     ecx, 40h ; '@'
0x14002f040  mov     r8d, 63694E53h
0x14002f046  mov     edx, ecx
0x14002f048  call    cs:__imp_ExAllocatePool2
0x14002f04f  nop     dword ptr [rax+rax+00h]
0x14002f054  test    rax, rax
0x14002f057  jnz     short loc_14002F07D
0x14002f059  test    byte ptr cs:xmmword_1400272D0, 4
0x14002f060  jz      short loc_14002F079
0x14002f062  lea     edx, [rax+10h]
0x14002f065  mov     ecx, 202h
0x14002f06a  mov     r9d, ebx
0x14002f06d  lea     r8, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids
0x14002f074  call    WPP_SF_d
0x14002f079  xor     eax, eax
0x14002f07b  jmp     short loc_14002F0B2
0x14002f07d  mov     dword ptr [rax+38h], 0
0x14002f084  lea     rdx, qword_140027848
0x14002f08b  mov     [rax+1Ch], ebx
0x14002f08e  mov     rcx, cs:qword_140027850
0x14002f095  cmp     [rcx], rdx
0x14002f098  jz      short loc_14002F0A1
0x14002f09a  mov     ecx, 3
0x14002f09f  int     29h; Win8: RtlFailFast(ecx)
0x14002f0a1  mov     [rax], rdx
0x14002f0a4  mov     [rax+8], rcx
0x14002f0a8  mov     [rcx], rax
0x14002f0ab  mov     cs:qword_140027850, rax
0x14002f0b2  add     rsp, 20h
0x14002f0b6  pop     rbx
0x14002f0b7  retn
```
