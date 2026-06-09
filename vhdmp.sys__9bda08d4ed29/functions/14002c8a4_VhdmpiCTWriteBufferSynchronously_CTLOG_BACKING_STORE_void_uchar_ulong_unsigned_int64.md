# VhdmpiCTWriteBufferSynchronously(_CTLOG_BACKING_STORE *,void *,uchar,ulong *,unsigned __int64 *)

- ea: `0x14002c8a4`
- end: `0x14002cabc`
- name: `?VhdmpiCTWriteBufferSynchronously@@YAJPEAU_CTLOG_BACKING_STORE@@PEAXEPEAKPEA_K@Z`
- size: `536`
- prototype: `int(struct _CTLOG_BACKING_STORE *, void *, unsigned __int8, unsigned int *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14002b298`
- `0x14002b7f0`

## callees

- `0x140023980`
- `0x14002bed8`
- `0x14002c7d4`
- `0x14002c8a4`
- `0x140036284`
- `0x14005de00`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x14002c9c2`
- `ntoskrnl!KeResetEvent` at `0x14002c9c2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c9a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c9a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c9d4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c9d4`

## string_xrefs

- `0x14002c974`: `VhdmpiCTWriteBufferSynchronously: currently free buffer is not available (VirtualDisk = %p) (BackingStore = %p)`
- `0x14002c958`: `VhdmpiCTWriteBufferSynchronously`
- `0x14002ca7f`: `VhdmpiCTWriteBufferSynchronously`
- `0x14002ca73`: `VhdmpiCTWriteBufferSynchronously: ERROR!   Status=0x%x (VirtualDisk = %p) (BackingStore = %p)`

## pseudocode

```c
__int64 __fastcall VhdmpiCTWriteBufferSynchronously(
        struct _CTLOG_BACKING_STORE *a1,
        void *a2,
        __int64 a3,
        unsigned int *a4,
        unsigned __int64 *a5)
{
  __int64 v8; // rcx
  unsigned int v9; // ebp
  unsigned int v10; // r13d
  struct _CTLOG_BUFFER *v11; // rsi
  unsigned __int8 v12; // r8
  int v13; // ebx
  KIRQL v14; // bl
  __int64 v15; // rsi
  __int64 v16; // rcx
  unsigned __int8 v17; // r8

  if ( a5 )
    *a5 = 0;
  if ( a1 && a4 && a2 )
  {
    v8 = *((_QWORD *)a1 + 548);
    v9 = 0;
    v10 = *a4;
    if ( v8 && *(_DWORD *)(v8 + 36) == *(_DWORD *)(v8 + 32) )
      VhdmpiCTAddToDirtyBufferList((struct _CTLOG_BUFFER *)v8);
    if ( !*((_QWORD *)a1 + 548) )
    {
      v11 = VhdmpiCTGetNewBuffer((PKSPIN_LOCK)(*((_QWORD *)a1 + 9) + 1912LL));
      if ( !v11 )
      {
        if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
          TraceEvents(
            "VhdmpiCTWriteBufferSynchronously",
            0x58Fu,
            v12,
            0x1000u,
            "VhdmpiCTWriteBufferSynchronously: currently free buffer is not available (VirtualDisk = %p) (BackingStore = %p)",
            *((const void **)a1 + 9),
            a1);
        goto LABEL_14;
      }
      *((_QWORD *)v11 + 5) = *((_QWORD *)a1 + 7);
      *((_QWORD *)v11 + 2) = a1;
      *((_QWORD *)a1 + 548) = v11;
      v14 = KeAcquireSpinLockRaiseToDpc(*((PKSPIN_LOCK *)v11 + 6));
      _InterlockedIncrement((volatile signed __int32 *)a1 + 1098);
      KeResetEvent((PRKEVENT)((char *)a1 + 4400));
      KeReleaseSpinLock(*((PKSPIN_LOCK *)v11 + 6), v14);
    }
    v15 = *((_QWORD *)a1 + 548);
    if ( !v15 )
    {
LABEL_14:
      v13 = 259;
      goto LABEL_25;
    }
    v16 = *(unsigned int *)(v15 + 36);
    v13 = 0;
    v9 = v10;
    if ( v10 > *(_DWORD *)(v15 + 32) - (int)v16 )
      v9 = *(_DWORD *)(v15 + 32) - v16;
    memmove((void *)(*(_QWORD *)(v15 + 24) + v16), a2, v9);
    if ( a5 )
      *a5 = *(_QWORD *)(v15 + 40) + *(unsigned int *)(v15 + 36);
    *(_DWORD *)(v15 + 36) += v9;
    if ( *(_DWORD *)(v15 + 36) == *(_DWORD *)(v15 + 32) )
      VhdmpiCTAddToDirtyBufferList(*((struct _CTLOG_BUFFER **)a1 + 548));
LABEL_25:
    *a4 = v9;
    if ( v13 >= 0 )
      return (unsigned int)v13;
    goto LABEL_26;
  }
  v13 = -1073741811;
  if ( a4 )
  {
    v9 = 0;
    goto LABEL_25;
  }
LABEL_26:
  if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
    TraceEvents(
      "VhdmpiCTWriteBufferSynchronously",
      0x5E0u,
      v17,
      0x1000u,
      "VhdmpiCTWriteBufferSynchronously: ERROR!   Status=0x%x (VirtualDisk = %p) (BackingStore = %p)",
      v13,
      *((const void **)a1 + 9),
      a1);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14002c8a4  push    rbx
0x14002c8a6  push    rbp
0x14002c8a7  push    rsi
0x14002c8a8  push    rdi
0x14002c8a9  push    r12
0x14002c8ab  push    r13
0x14002c8ad  push    r14
0x14002c8af  push    r15
0x14002c8b1  sub     rsp, 48h
0x14002c8b5  mov     r15, [rsp+88h+arg_20]
0x14002c8bd  mov     r14, r9
0x14002c8c0  mov     r12, rdx
0x14002c8c3  mov     rdi, rcx
0x14002c8c6  test    r15, r15
0x14002c8c9  jz      short loc_14002C8D2
0x14002c8cb  mov     qword ptr [r15], 0
0x14002c8d2  test    rdi, rdi
0x14002c8d5  jz      loc_14002CA36
0x14002c8db  test    r14, r14
0x14002c8de  jz      loc_14002CA36
0x14002c8e4  test    r12, r12
0x14002c8e7  jz      loc_14002CA36
0x14002c8ed  mov     rcx, [rcx+1120h]; struct _CTLOG_BUFFER *
0x14002c8f4  xor     ebp, ebp
0x14002c8f6  mov     r13d, [r9]
0x14002c8f9  test    rcx, rcx
0x14002c8fc  jz      short loc_14002C90B
0x14002c8fe  mov     eax, [rcx+20h]
0x14002c901  cmp     [rcx+24h], eax
0x14002c904  jnz     short loc_14002C90B
0x14002c906  call    ?VhdmpiCTAddToDirtyBufferList@@YAXPEAU_CTLOG_BUFFER@@@Z; VhdmpiCTAddToDirtyBufferList(_CTLOG_BUFFER *)
0x14002c90b  cmp     [rdi+1120h], rbp
0x14002c912  jnz     loc_14002C9E0
0x14002c918  mov     rcx, [rdi+48h]
0x14002c91c  add     rcx, 778h; SpinLock
0x14002c923  call    ?VhdmpiCTGetNewBuffer@@YAPEAU_CTLOG_BUFFER@@PEAU_CTLOG_BUFFER_MANAGER@@@Z; VhdmpiCTGetNewBuffer(_CTLOG_BUFFER_MANAGER *)
0x14002c928  mov     rsi, rax
0x14002c92b  test    rax, rax
0x14002c92e  jnz     short loc_14002C98F
0x14002c930  mov     eax, cs:dword_1400876D0
0x14002c936  lea     r8d, [rsi+4]
0x14002c93a  cmp     eax, r8d
0x14002c93d  jbe     short loc_14002C985
0x14002c93f  mov     edx, 1000h
0x14002c944  lea     rcx, dword_1400876D0
0x14002c94b  call    _tlgKeywordOn
0x14002c950  test    al, al
0x14002c952  jz      short loc_14002C985
0x14002c954  mov     rax, [rdi+48h]
0x14002c958  lea     rcx, aVhdmpictwriteb_0; "VhdmpiCTWriteBufferSynchronously"
0x14002c95f  mov     [rsp+88h+var_58], rdi
0x14002c964  mov     edx, 58Fh; int
0x14002c969  mov     qword ptr [rsp+88h+var_60], rax; char
0x14002c96e  mov     r9d, 1000h; int
0x14002c974  lea     rax, aVhdmpictwriteb_1; "VhdmpiCTWriteBufferSynchronously: curre"...
0x14002c97b  mov     [rsp+88h+var_68], rax; char *
0x14002c980  call    TraceEvents
0x14002c985  mov     ebx, 103h
0x14002c98a  jmp     loc_14002CA42
0x14002c98f  mov     rax, [rdi+38h]
0x14002c993  mov     [rsi+28h], rax
0x14002c997  mov     [rsi+10h], rdi
0x14002c99b  mov     [rdi+1120h], rsi
0x14002c9a2  mov     rcx, [rsi+30h]; SpinLock
0x14002c9a6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002c9ad  nop     dword ptr [rax+rax+00h]
0x14002c9b2  mov     bl, al
0x14002c9b4  lock inc dword ptr [rdi+1128h]
0x14002c9bb  lea     rcx, [rdi+1130h]; Event
0x14002c9c2  call    cs:__imp_KeResetEvent
0x14002c9c9  nop     dword ptr [rax+rax+00h]
0x14002c9ce  mov     rcx, [rsi+30h]; SpinLock
0x14002c9d2  mov     dl, bl; NewIrql
0x14002c9d4  call    cs:__imp_KeReleaseSpinLock
0x14002c9db  nop     dword ptr [rax+rax+00h]
0x14002c9e0  mov     rsi, [rdi+1120h]
0x14002c9e7  test    rsi, rsi
0x14002c9ea  jz      short loc_14002C985
0x14002c9ec  mov     ecx, [rsi+24h]
0x14002c9ef  xor     ebx, ebx
0x14002c9f1  mov     eax, [rsi+20h]
0x14002c9f4  mov     ebp, r13d
0x14002c9f7  sub     eax, ecx
0x14002c9f9  mov     rdx, r12; Src
0x14002c9fc  cmp     r13d, eax
0x14002c9ff  cmova   ebp, eax
0x14002ca02  add     rcx, [rsi+18h]; void *
0x14002ca06  mov     r8d, ebp; Size
0x14002ca09  call    memmove
0x14002ca0e  test    r15, r15
0x14002ca11  jz      short loc_14002CA1D
0x14002ca13  mov     eax, [rsi+24h]
0x14002ca16  add     rax, [rsi+28h]
0x14002ca1a  mov     [r15], rax
0x14002ca1d  add     [rsi+24h], ebp
0x14002ca20  mov     eax, [rsi+24h]
0x14002ca23  cmp     eax, [rsi+20h]
0x14002ca26  jnz     short loc_14002CA42
0x14002ca28  mov     rcx, [rdi+1120h]; struct _CTLOG_BUFFER *
0x14002ca2f  call    ?VhdmpiCTAddToDirtyBufferList@@YAXPEAU_CTLOG_BUFFER@@@Z; VhdmpiCTAddToDirtyBufferList(_CTLOG_BUFFER *)
0x14002ca34  jmp     short loc_14002CA42
0x14002ca36  mov     ebx, 0C000000Dh
0x14002ca3b  test    r14, r14
0x14002ca3e  jz      short loc_14002CA49
0x14002ca40  xor     ebp, ebp
0x14002ca42  mov     [r14], ebp
0x14002ca45  test    ebx, ebx
0x14002ca47  jns     short loc_14002CAA8
0x14002ca49  mov     eax, cs:dword_1400876D0
0x14002ca4f  mov     r8d, 2
0x14002ca55  cmp     eax, r8d
0x14002ca58  jbe     short loc_14002CAA8
0x14002ca5a  mov     edx, 1000h
0x14002ca5f  lea     rcx, dword_1400876D0
0x14002ca66  call    _tlgKeywordOn
0x14002ca6b  test    al, al
0x14002ca6d  jz      short loc_14002CAA8
0x14002ca6f  mov     rdx, [rdi+48h]
0x14002ca73  lea     rax, aVhdmpictwriteb; "VhdmpiCTWriteBufferSynchronously: ERROR"...
0x14002ca7a  mov     [rsp+88h+var_50], rdi
0x14002ca7f  lea     rcx, aVhdmpictwriteb_0; "VhdmpiCTWriteBufferSynchronously"
0x14002ca86  mov     [rsp+88h+var_58], rdx
0x14002ca8b  mov     r10d, 5E0h
0x14002ca91  mov     dword ptr [rsp+88h+var_60], ebx; char
0x14002ca95  mov     edx, r10d; int
0x14002ca98  mov     r9d, 1000h; int
0x14002ca9e  mov     [rsp+88h+var_68], rax; char *
0x14002caa3  call    TraceEvents
0x14002caa8  mov     eax, ebx
0x14002caaa  add     rsp, 48h
0x14002caae  pop     r15
0x14002cab0  pop     r14
0x14002cab2  pop     r13
0x14002cab4  pop     r12
0x14002cab6  pop     rdi
0x14002cab7  pop     rsi
0x14002cab8  pop     rbp
0x14002cab9  pop     rbx
0x14002caba  retn
```
