# SlbNatIpsCreateInterfaceContext

- ea: `0x14002e008`
- end: `0x14002e0b9`
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
- `0x14002d008`
- `0x14002e008`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002e048`
- `ntoskrnl!ExAllocatePool2` at `0x14002e048`

## pseudocode

```c
__int64 __fastcall SlbNatIpsCreateInterfaceContext(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // ebx
  __int64 result; // rax
  __int64 *v6; // rcx

  v4 = a1;
  if ( !(_DWORD)a1 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
  if ( (xmmword_1400262E0 & 4) != 0 )
    WPP_SF_d(1026, 15, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, v4);
  result = ExAllocatePool2(64, 64, 1667845715);
  if ( result )
  {
    *(_DWORD *)(result + 56) = 0;
    *(_DWORD *)(result + 28) = v4;
    v6 = (__int64 *)qword_140026850;
    if ( *(PVOID **)qword_140026850 != &qword_140026848 )
      __fastfail(3u);
    *(_QWORD *)result = &qword_140026848;
    *(_QWORD *)(result + 8) = v6;
    *v6 = result;
    qword_140026850 = result;
  }
  else
  {
    if ( (xmmword_1400262D0 & 4) != 0 )
      WPP_SF_d(514, 16, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, v4);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14002e008  push    rbx
0x14002e00a  sub     rsp, 20h
0x14002e00e  mov     ebx, ecx
0x14002e010  test    ecx, ecx
0x14002e012  jnz     short loc_14002E019
0x14002e014  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002e019  test    byte ptr cs:xmmword_1400262E0, 4
0x14002e020  jz      short loc_14002E03B
0x14002e022  mov     edx, 0Fh
0x14002e027  lea     r8, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids
0x14002e02e  mov     ecx, 402h
0x14002e033  mov     r9d, ebx
0x14002e036  call    WPP_SF_d
0x14002e03b  mov     ecx, 40h ; '@'
0x14002e040  mov     r8d, 63694E53h
0x14002e046  mov     edx, ecx
0x14002e048  call    cs:__imp_ExAllocatePool2
0x14002e04f  nop     dword ptr [rax+rax+00h]
0x14002e054  test    rax, rax
0x14002e057  jnz     short loc_14002E07D
0x14002e059  test    byte ptr cs:xmmword_1400262D0, 4
0x14002e060  jz      short loc_14002E079
0x14002e062  lea     edx, [rax+10h]
0x14002e065  mov     ecx, 202h
0x14002e06a  mov     r9d, ebx
0x14002e06d  lea     r8, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids
0x14002e074  call    WPP_SF_d
0x14002e079  xor     eax, eax
0x14002e07b  jmp     short loc_14002E0B2
0x14002e07d  mov     dword ptr [rax+38h], 0
0x14002e084  lea     rdx, qword_140026848
0x14002e08b  mov     [rax+1Ch], ebx
0x14002e08e  mov     rcx, cs:qword_140026850
0x14002e095  cmp     [rcx], rdx
0x14002e098  jz      short loc_14002E0A1
0x14002e09a  mov     ecx, 3
0x14002e09f  int     29h; Win8: RtlFailFast(ecx)
0x14002e0a1  mov     [rax], rdx
0x14002e0a4  mov     [rax+8], rcx
0x14002e0a8  mov     [rcx], rax
0x14002e0ab  mov     cs:qword_140026850, rax
0x14002e0b2  add     rsp, 20h
0x14002e0b6  pop     rbx
0x14002e0b7  retn
```
