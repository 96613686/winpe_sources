# SlbNatUpdateExternalPrefixInstanceInterfaces

- ea: `0x14002e0c0`
- end: `0x14002e1d0`
- name: `SlbNatUpdateExternalPrefixInstanceInterfaces`
- size: `272`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002e560`
- `0x140033c98`

## callees

- `0x14000c7a0`
- `0x14000caa0`
- `0x14002e0c0`
- `0x14002f9fc`

## pseudocode

```c
__int64 __fastcall SlbNatUpdateExternalPrefixInstanceInterfaces(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  __int16 v7; // bp
  unsigned int v10; // r14d
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r15
  unsigned int v14; // esi

  v7 = a2;
  if ( !*(_BYTE *)(a1 + 182) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2);
  if ( v7 != *(_WORD *)(a1 + 180) )
    return 0;
  v10 = 0;
  v11 = 32;
  if ( v7 != 2 )
    v11 = 128;
  if ( *(unsigned __int8 *)(a1 + 182) > (unsigned int)v11 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v11, a2);
  if ( a3 )
  {
    if ( a4 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v11, a2);
    if ( *(_DWORD *)(a1 + 272)
      || !SlbNatIPPrefixMatch((const void *)(a3 + 8), (const void *)(a1 + 184), *(unsigned __int8 *)(a1 + 182)) )
    {
      return v10;
    }
    v12 = a3;
    goto LABEL_25;
  }
  v13 = 16;
  if ( v7 != 2 )
    v13 = 24;
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v11, a2);
  v14 = 0;
  if ( a5 )
  {
    while ( !SlbNatIPPrefixMatch((const void *)(a4 + 8), (const void *)(a1 + 184), *(unsigned __int8 *)(a1 + 182)) )
    {
      ++v14;
      a4 += v13;
      if ( v14 >= a5 )
        goto LABEL_22;
    }
    v12 = a4;
LABEL_25:
    SlbNatChangeInstanceExternalInterface(a1, v12);
    return v10;
  }
LABEL_22:
  SlbNatChangeInstanceExternalInterface(a1, 0);
  return (unsigned int)-1073741198;
}

```

## disassembly

```asm
0x14002e0c0  push    rbx
0x14002e0c2  push    rbp
0x14002e0c3  push    rsi
0x14002e0c4  push    rdi
0x14002e0c5  push    r12
0x14002e0c7  push    r14
0x14002e0c9  push    r15
0x14002e0cb  sub     rsp, 20h
0x14002e0cf  cmp     byte ptr [rcx+0B6h], 0
0x14002e0d6  mov     rdi, r9
0x14002e0d9  mov     rsi, r8
0x14002e0dc  movzx   ebp, dx
0x14002e0df  mov     rbx, rcx
0x14002e0e2  ja      short loc_14002E0E9
0x14002e0e4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002e0e9  cmp     bp, [rbx+0B4h]
0x14002e0f0  jz      short loc_14002E0F9
0x14002e0f2  xor     eax, eax
0x14002e0f4  jmp     loc_14002E1B3
0x14002e0f9  xor     r14d, r14d
0x14002e0fc  cmp     bp, 2
0x14002e100  lea     ecx, [r14+20h]
0x14002e104  lea     eax, [rcx+60h]
0x14002e107  cmovnz  ecx, eax
0x14002e10a  movzx   eax, byte ptr [rbx+0B6h]
0x14002e111  cmp     eax, ecx
0x14002e113  jbe     short loc_14002E11A
0x14002e115  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002e11a  test    rsi, rsi
0x14002e11d  jz      short loc_14002E153
0x14002e11f  test    rdi, rdi
0x14002e122  jz      short loc_14002E129
0x14002e124  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002e129  cmp     [rbx+110h], r14d
0x14002e130  jnz     short loc_14002E1B0
0x14002e132  movzx   r8d, byte ptr [rbx+0B6h]
0x14002e13a  lea     rdx, [rbx+0B8h]
0x14002e141  lea     rcx, [rsi+8]
0x14002e145  call    SlbNatIPPrefixMatch
0x14002e14a  test    al, al
0x14002e14c  jz      short loc_14002E1B0
0x14002e14e  mov     rdx, rsi
0x14002e151  jmp     short loc_14002E1C6
0x14002e153  mov     eax, 18h
0x14002e158  cmp     bp, 2
0x14002e15c  lea     r15d, [rax-8]
0x14002e160  cmovnz  r15d, eax
0x14002e164  test    rdi, rdi
0x14002e167  jnz     short loc_14002E16E
0x14002e169  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002e16e  mov     ebp, [rsp+58h+arg_20]
0x14002e175  xor     esi, esi
0x14002e177  test    ebp, ebp
0x14002e179  jz      short loc_14002E1A0
0x14002e17b  movzx   r8d, byte ptr [rbx+0B6h]
0x14002e183  lea     rcx, [rdi+8]
0x14002e187  lea     rdx, [rbx+0B8h]
0x14002e18e  call    SlbNatIPPrefixMatch
0x14002e193  test    al, al
0x14002e195  jnz     short loc_14002E1C3
0x14002e197  inc     esi
0x14002e199  add     rdi, r15
0x14002e19c  cmp     esi, ebp
0x14002e19e  jb      short loc_14002E17B
0x14002e1a0  xor     edx, edx
0x14002e1a2  mov     rcx, rbx
0x14002e1a5  call    SlbNatChangeInstanceExternalInterface
0x14002e1aa  mov     r14d, 0C0000272h
0x14002e1b0  mov     eax, r14d
0x14002e1b3  add     rsp, 20h
0x14002e1b7  pop     r15
0x14002e1b9  pop     r14
0x14002e1bb  pop     r12
0x14002e1bd  pop     rdi
0x14002e1be  pop     rsi
0x14002e1bf  pop     rbp
0x14002e1c0  pop     rbx
0x14002e1c1  retn
0x14002e1c3  mov     rdx, rdi
0x14002e1c6  mov     rcx, rbx
0x14002e1c9  call    SlbNatChangeInstanceExternalInterface
0x14002e1ce  jmp     short loc_14002E1B0
```
