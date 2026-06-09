# SlbNatIpsCleanupDataPathState

- ea: `0x14003329c`
- end: `0x14003338c`
- name: `SlbNatIpsCleanupDataPathState`
- size: `240`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002ff58`
- `0x1400333cc`
- `0x140035af8`

## callees

- `0x14000caa0`
- `0x14003329c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400332e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400332f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003334d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003336b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400332e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400332f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003334d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003336b`

## pseudocode

```c
void __fastcall SlbNatIpsCleanupDataPathState(void *a1, __int64 a2, __int64 a3, __int64 a4)
{
  _DWORD *v4; // rbx
  __int64 v5; // rax
  void *v6; // rcx
  unsigned int v7; // edi
  __int64 i; // rbx
  _QWORD *v9; // rbp

  while ( 1 )
  {
    v4 = qword_140026848;
    if ( qword_140026848 == &qword_140026848 )
      break;
    if ( *((PVOID **)qword_140026848 + 1) != &qword_140026848
      || (v5 = *(_QWORD *)qword_140026848, *(PVOID *)(*(_QWORD *)qword_140026848 + 8LL) != qword_140026848) )
    {
      __fastfail(3u);
    }
    qword_140026848 = *(PVOID *)qword_140026848;
    *(_QWORD *)(v5 + 8) = &qword_140026848;
    if ( v4[10] )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
    v6 = (void *)*((_QWORD *)v4 + 6);
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
    ExFreePoolWithTag(v4, 0);
  }
  if ( qword_140026858 )
  {
    v7 = dword_140026B60;
    for ( i = 0; (unsigned int)i < v7; i = (unsigned int)(i + 1) )
    {
      v9 = qword_140026858;
      if ( (*((_BYTE *)qword_140026858 + 96 * i) & 1) != 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
      a1 = (void *)v9[12 * i + 1];
      if ( a1 )
        ExFreePoolWithTag(a1, 0x636A4E53u);
    }
    ExFreePoolWithTag(qword_140026858, 0x63704E53u);
    qword_140026858 = 0;
  }
}

```

## disassembly

```asm
0x14003329c  push    rbx
0x14003329e  push    rbp
0x14003329f  push    rsi
0x1400332a0  push    rdi
0x1400332a1  sub     rsp, 28h
0x1400332a5  lea     rdi, qword_140026848
0x1400332ac  mov     rbx, cs:qword_140026848
0x1400332b3  cmp     rbx, rdi
0x1400332b6  jz      short loc_14003330E
0x1400332b8  cmp     [rbx+8], rdi
0x1400332bc  jnz     short loc_140033307
0x1400332be  mov     rax, [rbx]
0x1400332c1  cmp     [rax+8], rbx
0x1400332c5  jnz     short loc_140033307
0x1400332c7  mov     cs:qword_140026848, rax
0x1400332ce  mov     [rax+8], rdi
0x1400332d2  cmp     dword ptr [rbx+28h], 0
0x1400332d6  jz      short loc_1400332DD
0x1400332d8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400332dd  mov     rcx, [rbx+30h]; P
0x1400332e1  test    rcx, rcx
0x1400332e4  jz      short loc_1400332F4
0x1400332e6  xor     edx, edx; Tag
0x1400332e8  call    cs:__imp_ExFreePoolWithTag
0x1400332ef  nop     dword ptr [rax+rax+00h]
0x1400332f4  xor     edx, edx; Tag
0x1400332f6  mov     rcx, rbx; P
0x1400332f9  call    cs:__imp_ExFreePoolWithTag
0x140033300  nop     dword ptr [rax+rax+00h]
0x140033305  jmp     short loc_1400332AC
0x140033307  mov     ecx, 3
0x14003330c  int     29h; Win8: RtlFailFast(ecx)
0x14003330e  cmp     cs:qword_140026858, 0
0x140033316  jz      short loc_140033382
0x140033318  mov     edi, cs:dword_140026B60
0x14003331e  xor     ebx, ebx
0x140033320  test    edi, edi
0x140033322  jz      short loc_14003335F
0x140033324  mov     rbp, cs:qword_140026858
0x14003332b  lea     rsi, [rbx+rbx*2]
0x14003332f  shl     rsi, 5
0x140033333  test    byte ptr [rsi+rbp], 1
0x140033337  jz      short loc_14003333E
0x140033339  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003333e  mov     rcx, [rsi+rbp+8]; P
0x140033343  test    rcx, rcx
0x140033346  jz      short loc_140033359
0x140033348  mov     edx, 636A4E53h; Tag
0x14003334d  call    cs:__imp_ExFreePoolWithTag
0x140033354  nop     dword ptr [rax+rax+00h]
0x140033359  inc     ebx
0x14003335b  cmp     ebx, edi
0x14003335d  jb      short loc_140033324
0x14003335f  mov     rcx, cs:qword_140026858; P
0x140033366  mov     edx, 63704E53h; Tag
0x14003336b  call    cs:__imp_ExFreePoolWithTag
0x140033372  nop     dword ptr [rax+rax+00h]
0x140033377  mov     cs:qword_140026858, 0
0x140033382  add     rsp, 28h
0x140033386  pop     rdi
0x140033387  pop     rsi
0x140033388  pop     rbp
0x140033389  pop     rbx
0x14003338a  retn
```
