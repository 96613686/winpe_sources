# SlbNatIpsCleanupDataPathState

- ea: `0x1400343cc`
- end: `0x1400344bc`
- name: `SlbNatIpsCleanupDataPathState`
- size: `240`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140031088`
- `0x1400344fc`
- `0x140036af8`

## callees

- `0x14000caa0`
- `0x1400343cc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140034418`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034429`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003447d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003449b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034418`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034429`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003447d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003449b`

## pseudocode

```c
void __fastcall SlbNatIpsCleanupDataPathState(void *a1, __int64 a2, __int64 a3)
{
  _DWORD *v3; // rbx
  __int64 v4; // rax
  void *v5; // rcx
  unsigned int v6; // edi
  __int64 i; // rbx
  _QWORD *v8; // rbp

  while ( 1 )
  {
    v3 = qword_140027848;
    if ( qword_140027848 == &qword_140027848 )
      break;
    if ( *((PVOID **)qword_140027848 + 1) != &qword_140027848
      || (v4 = *(_QWORD *)qword_140027848, *(PVOID *)(*(_QWORD *)qword_140027848 + 8LL) != qword_140027848) )
    {
      __fastfail(3u);
    }
    qword_140027848 = *(PVOID *)qword_140027848;
    *(_QWORD *)(v4 + 8) = &qword_140027848;
    if ( v3[10] )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
    v5 = (void *)*((_QWORD *)v3 + 6);
    if ( v5 )
      ExFreePoolWithTag(v5, 0);
    ExFreePoolWithTag(v3, 0);
  }
  if ( qword_140027858 )
  {
    v6 = dword_140027B60;
    for ( i = 0; (unsigned int)i < v6; i = (unsigned int)(i + 1) )
    {
      v8 = qword_140027858;
      if ( (*((_BYTE *)qword_140027858 + 96 * i) & 1) != 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
      a1 = (void *)v8[12 * i + 1];
      if ( a1 )
        ExFreePoolWithTag(a1, 0x636A4E53u);
    }
    ExFreePoolWithTag(qword_140027858, 0x63704E53u);
    qword_140027858 = 0;
  }
}

```

## disassembly

```asm
0x1400343cc  push    rbx
0x1400343ce  push    rbp
0x1400343cf  push    rsi
0x1400343d0  push    rdi
0x1400343d1  sub     rsp, 28h
0x1400343d5  lea     rdi, qword_140027848
0x1400343dc  mov     rbx, cs:qword_140027848
0x1400343e3  cmp     rbx, rdi
0x1400343e6  jz      short loc_14003443E
0x1400343e8  cmp     [rbx+8], rdi
0x1400343ec  jnz     short loc_140034437
0x1400343ee  mov     rax, [rbx]
0x1400343f1  cmp     [rax+8], rbx
0x1400343f5  jnz     short loc_140034437
0x1400343f7  mov     cs:qword_140027848, rax
0x1400343fe  mov     [rax+8], rdi
0x140034402  cmp     dword ptr [rbx+28h], 0
0x140034406  jz      short loc_14003440D
0x140034408  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003440d  mov     rcx, [rbx+30h]; P
0x140034411  test    rcx, rcx
0x140034414  jz      short loc_140034424
0x140034416  xor     edx, edx; Tag
0x140034418  call    cs:__imp_ExFreePoolWithTag
0x14003441f  nop     dword ptr [rax+rax+00h]
0x140034424  xor     edx, edx; Tag
0x140034426  mov     rcx, rbx; P
0x140034429  call    cs:__imp_ExFreePoolWithTag
0x140034430  nop     dword ptr [rax+rax+00h]
0x140034435  jmp     short loc_1400343DC
0x140034437  mov     ecx, 3
0x14003443c  int     29h; Win8: RtlFailFast(ecx)
0x14003443e  cmp     cs:qword_140027858, 0
0x140034446  jz      short loc_1400344B2
0x140034448  mov     edi, cs:dword_140027B60
0x14003444e  xor     ebx, ebx
0x140034450  test    edi, edi
0x140034452  jz      short loc_14003448F
0x140034454  mov     rbp, cs:qword_140027858
0x14003445b  lea     rsi, [rbx+rbx*2]
0x14003445f  shl     rsi, 5
0x140034463  test    byte ptr [rsi+rbp], 1
0x140034467  jz      short loc_14003446E
0x140034469  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003446e  mov     rcx, [rsi+rbp+8]; P
0x140034473  test    rcx, rcx
0x140034476  jz      short loc_140034489
0x140034478  mov     edx, 636A4E53h; Tag
0x14003447d  call    cs:__imp_ExFreePoolWithTag
0x140034484  nop     dword ptr [rax+rax+00h]
0x140034489  inc     ebx
0x14003448b  cmp     ebx, edi
0x14003448d  jb      short loc_140034454
0x14003448f  mov     rcx, cs:qword_140027858; P
0x140034496  mov     edx, 63704E53h; Tag
0x14003449b  call    cs:__imp_ExFreePoolWithTag
0x1400344a2  nop     dword ptr [rax+rax+00h]
0x1400344a7  mov     cs:qword_140027858, 0
0x1400344b2  add     rsp, 28h
0x1400344b6  pop     rdi
0x1400344b7  pop     rsi
0x1400344b8  pop     rbp
0x1400344b9  pop     rbx
0x1400344ba  retn
```
