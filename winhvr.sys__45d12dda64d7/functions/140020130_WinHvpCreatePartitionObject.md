# WinHvpCreatePartitionObject

- ea: `0x140020130`
- end: `0x1400202c6`
- name: `WinHvpCreatePartitionObject`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001f2d0`

## callees

- `0x1400024d0`
- `0x14000b008`
- `0x140020130`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400201c9`
- `ntoskrnl!KeInitializeEvent` at `0x1400201fe`
- `ntoskrnl!KeInitializeEvent` at `0x1400201c9`
- `ntoskrnl!KeInitializeEvent` at `0x1400201fe`
- `ntoskrnl!KeInitializeDpc` at `0x1400201b0`
- `ntoskrnl!KeInitializeDpc` at `0x1400201b0`

## pseudocode

```c
__int64 __fastcall WinHvpCreatePartitionObject(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char a7,
        char a8,
        __int64 *a9)
{
  unsigned int v13; // edi
  __int64 Pool; // rax
  __int64 v15; // rbx
  _QWORD *v16; // rax
  __int64 v17; // rax

  v13 = -1073741670;
  Pool = WinHvpAllocatePool(64, 264, 1215711319);
  v15 = Pool;
  if ( Pool )
  {
    *(_QWORD *)(Pool + 16) = a1;
    *(_QWORD *)(Pool + 24) = a3;
    *(_QWORD *)(Pool + 32) = a4;
    *(_QWORD *)Pool = 1;
    *(_DWORD *)(Pool + 40) = a2;
    *(_QWORD *)(Pool + 48) = a5;
    *(_QWORD *)(Pool + 56) = a6;
    KeInitializeDpc((PRKDPC)(Pool + 96), WinHvpOnCallCompletionDpcRoutine, 0);
    KeInitializeEvent((PRKEVENT)(v15 + 160), SynchronizationEvent, 0);
    *(_DWORD *)(v15 + 184) = 1;
    *(_QWORD *)(v15 + 192) = 0;
    *(_DWORD *)(v15 + 200) = 0;
    KeInitializeEvent((PRKEVENT)(v15 + 208), SynchronizationEvent, 0);
    if ( WinHvpRootSchedulerActive )
    {
      *(_BYTE *)(v15 + 8) = WinHvpDfssEnabled;
      if ( (a8 & 1) != 0 )
        *(_BYTE *)(v15 + 8) = 0;
      if ( (a8 & 2) != 0 )
        *(_WORD *)(v15 + 8) = 256;
      if ( a7 < 0 )
      {
        v16 = (_QWORD *)WinHvpAllocatePool(256, 16, 1517701207);
        *(_QWORD *)(v15 + 88) = v16;
        if ( !v16 )
          goto LABEL_15;
        *v16 = 1;
      }
      *(_DWORD *)(v15 + 72) = 2048;
      v17 = WinHvpAllocatePool(64, 0x4000, 1316374615);
      *(_QWORD *)(v15 + 64) = v17;
      if ( v17 )
      {
LABEL_11:
        v13 = 0;
        *a9 = v15;
        return v13;
      }
    }
    else
    {
      if ( (a8 & 2) == 0 )
        goto LABEL_11;
      v13 = -1073741811;
    }
LABEL_15:
    WinHvpDereferencePartition(v15);
  }
  return v13;
}

```

## disassembly

```asm
0x140020130  push    rbx
0x140020132  push    rbp
0x140020133  push    rsi
0x140020134  push    rdi
0x140020135  push    r13
0x140020137  push    r14
0x140020139  push    r15
0x14002013b  sub     rsp, 20h
0x14002013f  mov     rbp, r8
0x140020142  mov     r14d, edx
0x140020145  mov     r15, rcx
0x140020148  mov     edx, 108h
0x14002014d  mov     ecx, 40h ; '@'
0x140020152  mov     r8d, 48764857h
0x140020158  mov     rsi, r9
0x14002015b  mov     edi, 0C000009Ah
0x140020160  call    WinHvpAllocatePool
0x140020165  mov     rbx, rax
0x140020168  test    rax, rax
0x14002016b  jz      loc_14002029B
0x140020171  mov     [rax+10h], r15
0x140020175  lea     rcx, [rbx+60h]; Dpc
0x140020179  mov     [rax+18h], rbp
0x14002017d  lea     rdx, WinHvpOnCallCompletionDpcRoutine; DeferredRoutine
0x140020184  mov     [rax+20h], rsi
0x140020188  mov     r13d, 1
0x14002018e  mov     [rax], r13
0x140020191  xor     r8d, r8d; DeferredContext
0x140020194  mov     [rax+28h], r14d
0x140020198  mov     rax, [rsp+58h+arg_20]
0x1400201a0  mov     [rbx+30h], rax
0x1400201a4  mov     rax, [rsp+58h+arg_28]
0x1400201ac  mov     [rbx+38h], rax
0x1400201b0  call    cs:__imp_KeInitializeDpc
0x1400201b7  nop     dword ptr [rax+rax+00h]
0x1400201bc  lea     rcx, [rbx+0A0h]; Event
0x1400201c3  xor     r8d, r8d; State
0x1400201c6  mov     edx, r13d; Type
0x1400201c9  call    cs:__imp_KeInitializeEvent
0x1400201d0  nop     dword ptr [rax+rax+00h]
0x1400201d5  lea     rcx, [rbx+0D0h]; Event
0x1400201dc  mov     [rbx+0B8h], r13d
0x1400201e3  xor     r8d, r8d; State
0x1400201e6  mov     qword ptr [rbx+0C0h], 0
0x1400201f1  mov     edx, r13d; Type
0x1400201f4  mov     dword ptr [rbx+0C8h], 0
0x1400201fe  call    cs:__imp_KeInitializeEvent
0x140020205  nop     dword ptr [rax+rax+00h]
0x14002020a  cmp     cs:WinHvpRootSchedulerActive, 0
0x140020211  jz      loc_1400202AD
0x140020217  mov     al, cs:WinHvpDfssEnabled
0x14002021d  mov     [rbx+8], al
0x140020220  test    [rsp+58h+arg_38], r13b
0x140020228  jz      short loc_14002022E
0x14002022a  mov     byte ptr [rbx+8], 0
0x14002022e  test    [rsp+58h+arg_38], 2
0x140020236  jz      short loc_14002023E
0x140020238  mov     word ptr [rbx+8], 100h
0x14002023e  test    [rsp+58h+arg_30], 80h
0x140020246  jz      short loc_140020269
0x140020248  mov     edx, 10h
0x14002024d  mov     ecx, 100h
0x140020252  mov     r8d, 5A764857h
0x140020258  call    WinHvpAllocatePool
0x14002025d  mov     [rbx+58h], rax
0x140020261  test    rax, rax
0x140020264  jz      short loc_1400202BC
0x140020266  mov     [rax], r13
0x140020269  mov     edx, 4000h
0x14002026e  mov     dword ptr [rbx+48h], 800h
0x140020275  mov     ecx, 40h ; '@'
0x14002027a  mov     r8d, 4E764857h
0x140020280  call    WinHvpAllocatePool
0x140020285  mov     [rbx+40h], rax
0x140020289  test    rax, rax
0x14002028c  jz      short loc_1400202BC
0x14002028e  mov     rax, [rsp+58h+arg_40]
0x140020296  xor     edi, edi
0x140020298  mov     [rax], rbx
0x14002029b  mov     eax, edi
0x14002029d  add     rsp, 20h
0x1400202a1  pop     r15
0x1400202a3  pop     r14
0x1400202a5  pop     r13
0x1400202a7  pop     rdi
0x1400202a8  pop     rsi
0x1400202a9  pop     rbp
0x1400202aa  pop     rbx
0x1400202ab  retn
0x1400202ad  test    [rsp+58h+arg_38], 2
0x1400202b5  jz      short loc_14002028E
0x1400202b7  mov     edi, 0C000000Dh
0x1400202bc  mov     rcx, rbx
0x1400202bf  call    WinHvpDereferencePartition
0x1400202c4  jmp     short loc_14002029B
```
