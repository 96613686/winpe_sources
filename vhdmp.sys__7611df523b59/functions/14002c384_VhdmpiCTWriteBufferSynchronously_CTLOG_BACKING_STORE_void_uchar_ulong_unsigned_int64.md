# VhdmpiCTWriteBufferSynchronously(_CTLOG_BACKING_STORE *,void *,uchar,ulong *,unsigned __int64 *)

- ea: `0x14002c384`
- end: `0x14002c59c`
- name: `?VhdmpiCTWriteBufferSynchronously@@YAJPEAU_CTLOG_BACKING_STORE@@PEAXEPEAKPEA_K@Z`
- size: `536`
- prototype: `__int64 __fastcall(struct _CTLOG_BACKING_STORE *, void *, __int64, unsigned int *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14002ad78`
- `0x14002b2d0`

## callees

- `0x140023560`
- `0x14002b9b8`
- `0x14002c2b4`
- `0x14002c384`
- `0x140035e94`
- `0x14005da00`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x14002c4a2`
- `ntoskrnl!KeResetEvent` at `0x14002c4a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c486`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c486`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c4b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c4b4`

## string_xrefs

- `0x14002c553`: `VhdmpiCTWriteBufferSynchronously: ERROR!   Status=0x%x (VirtualDisk = %p) (BackingStore = %p)`
- `0x14002c454`: `VhdmpiCTWriteBufferSynchronously: currently free buffer is not available (VirtualDisk = %p) (BackingStore = %p)`
- `0x14002c438`: `VhdmpiCTWriteBufferSynchronously`
- `0x14002c55f`: `VhdmpiCTWriteBufferSynchronously`

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
  int v12; // r8d
  int v13; // ebx
  KIRQL v14; // bl
  __int64 v15; // rsi
  __int64 v16; // rcx
  int v17; // r8d

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
        if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
          TraceEvents(
            (int)"VhdmpiCTWriteBufferSynchronously",
            1423,
            v12,
            4096,
            "VhdmpiCTWriteBufferSynchronously: currently free buffer is not available (VirtualDisk = %p) (BackingStore = %p)",
            *((_QWORD *)a1 + 9));
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
  if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
    TraceEvents(
      (int)"VhdmpiCTWriteBufferSynchronously",
      1504,
      v17,
      4096,
      "VhdmpiCTWriteBufferSynchronously: ERROR!   Status=0x%x (VirtualDisk = %p) (BackingStore = %p)",
      v13);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14002c384  push    rbx
0x14002c386  push    rbp
0x14002c387  push    rsi
0x14002c388  push    rdi
0x14002c389  push    r12
0x14002c38b  push    r13
0x14002c38d  push    r14
0x14002c38f  push    r15
0x14002c391  sub     rsp, 48h
0x14002c395  mov     r15, [rsp+88h+arg_20]
0x14002c39d  mov     r14, r9
0x14002c3a0  mov     r12, rdx
0x14002c3a3  mov     rdi, rcx
0x14002c3a6  test    r15, r15
0x14002c3a9  jz      short loc_14002C3B2
0x14002c3ab  mov     qword ptr [r15], 0
0x14002c3b2  test    rdi, rdi
0x14002c3b5  jz      loc_14002C516
0x14002c3bb  test    r14, r14
0x14002c3be  jz      loc_14002C516
0x14002c3c4  test    r12, r12
0x14002c3c7  jz      loc_14002C516
0x14002c3cd  mov     rcx, [rcx+1120h]; struct _CTLOG_BUFFER *
0x14002c3d4  xor     ebp, ebp
0x14002c3d6  mov     r13d, [r9]
0x14002c3d9  test    rcx, rcx
0x14002c3dc  jz      short loc_14002C3EB
0x14002c3de  mov     eax, [rcx+20h]
0x14002c3e1  cmp     [rcx+24h], eax
0x14002c3e4  jnz     short loc_14002C3EB
0x14002c3e6  call    ?VhdmpiCTAddToDirtyBufferList@@YAXPEAU_CTLOG_BUFFER@@@Z; VhdmpiCTAddToDirtyBufferList(_CTLOG_BUFFER *)
0x14002c3eb  cmp     [rdi+1120h], rbp
0x14002c3f2  jnz     loc_14002C4C0
0x14002c3f8  mov     rcx, [rdi+48h]
0x14002c3fc  add     rcx, 778h; SpinLock
0x14002c403  call    ?VhdmpiCTGetNewBuffer@@YAPEAU_CTLOG_BUFFER@@PEAU_CTLOG_BUFFER_MANAGER@@@Z; VhdmpiCTGetNewBuffer(_CTLOG_BUFFER_MANAGER *)
0x14002c408  mov     rsi, rax
0x14002c40b  test    rax, rax
0x14002c40e  jnz     short loc_14002C46F
0x14002c410  mov     eax, cs:dword_140087708
0x14002c416  lea     r8d, [rsi+4]
0x14002c41a  cmp     eax, r8d
0x14002c41d  jbe     short loc_14002C465
0x14002c41f  mov     edx, 1000h
0x14002c424  lea     rcx, dword_140087708
0x14002c42b  call    _tlgKeywordOn
0x14002c430  test    al, al
0x14002c432  jz      short loc_14002C465
0x14002c434  mov     rax, [rdi+48h]
0x14002c438  lea     rcx, aVhdmpictwriteb_0; "VhdmpiCTWriteBufferSynchronously"
0x14002c43f  mov     [rsp+88h+var_58], rdi
0x14002c444  mov     edx, 58Fh; int
0x14002c449  mov     qword ptr [rsp+88h+var_60], rax; char
0x14002c44e  mov     r9d, 1000h; int
0x14002c454  lea     rax, aVhdmpictwriteb_1; "VhdmpiCTWriteBufferSynchronously: curre"...
0x14002c45b  mov     [rsp+88h+var_68], rax; char *
0x14002c460  call    TraceEvents
0x14002c465  mov     ebx, 103h
0x14002c46a  jmp     loc_14002C522
0x14002c46f  mov     rax, [rdi+38h]
0x14002c473  mov     [rsi+28h], rax
0x14002c477  mov     [rsi+10h], rdi
0x14002c47b  mov     [rdi+1120h], rsi
0x14002c482  mov     rcx, [rsi+30h]; SpinLock
0x14002c486  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002c48d  nop     dword ptr [rax+rax+00h]
0x14002c492  mov     bl, al
0x14002c494  lock inc dword ptr [rdi+1128h]
0x14002c49b  lea     rcx, [rdi+1130h]; Event
0x14002c4a2  call    cs:__imp_KeResetEvent
0x14002c4a9  nop     dword ptr [rax+rax+00h]
0x14002c4ae  mov     rcx, [rsi+30h]; SpinLock
0x14002c4b2  mov     dl, bl; NewIrql
0x14002c4b4  call    cs:__imp_KeReleaseSpinLock
0x14002c4bb  nop     dword ptr [rax+rax+00h]
0x14002c4c0  mov     rsi, [rdi+1120h]
0x14002c4c7  test    rsi, rsi
0x14002c4ca  jz      short loc_14002C465
0x14002c4cc  mov     ecx, [rsi+24h]
0x14002c4cf  xor     ebx, ebx
0x14002c4d1  mov     eax, [rsi+20h]
0x14002c4d4  mov     ebp, r13d
0x14002c4d7  sub     eax, ecx
0x14002c4d9  mov     rdx, r12; Src
0x14002c4dc  cmp     r13d, eax
0x14002c4df  cmova   ebp, eax
0x14002c4e2  add     rcx, [rsi+18h]; void *
0x14002c4e6  mov     r8d, ebp; Size
0x14002c4e9  call    memmove
0x14002c4ee  test    r15, r15
0x14002c4f1  jz      short loc_14002C4FD
0x14002c4f3  mov     eax, [rsi+24h]
0x14002c4f6  add     rax, [rsi+28h]
0x14002c4fa  mov     [r15], rax
0x14002c4fd  add     [rsi+24h], ebp
0x14002c500  mov     eax, [rsi+24h]
0x14002c503  cmp     eax, [rsi+20h]
0x14002c506  jnz     short loc_14002C522
0x14002c508  mov     rcx, [rdi+1120h]; struct _CTLOG_BUFFER *
0x14002c50f  call    ?VhdmpiCTAddToDirtyBufferList@@YAXPEAU_CTLOG_BUFFER@@@Z; VhdmpiCTAddToDirtyBufferList(_CTLOG_BUFFER *)
0x14002c514  jmp     short loc_14002C522
0x14002c516  mov     ebx, 0C000000Dh
0x14002c51b  test    r14, r14
0x14002c51e  jz      short loc_14002C529
0x14002c520  xor     ebp, ebp
0x14002c522  mov     [r14], ebp
0x14002c525  test    ebx, ebx
0x14002c527  jns     short loc_14002C588
0x14002c529  mov     eax, cs:dword_140087708
0x14002c52f  mov     r8d, 2
0x14002c535  cmp     eax, r8d
0x14002c538  jbe     short loc_14002C588
0x14002c53a  mov     edx, 1000h
0x14002c53f  lea     rcx, dword_140087708
0x14002c546  call    _tlgKeywordOn
0x14002c54b  test    al, al
0x14002c54d  jz      short loc_14002C588
0x14002c54f  mov     rdx, [rdi+48h]
0x14002c553  lea     rax, aVhdmpictwriteb; "VhdmpiCTWriteBufferSynchronously: ERROR"...
0x14002c55a  mov     [rsp+88h+var_50], rdi
0x14002c55f  lea     rcx, aVhdmpictwriteb_0; "VhdmpiCTWriteBufferSynchronously"
0x14002c566  mov     [rsp+88h+var_58], rdx
0x14002c56b  mov     r10d, 5E0h
0x14002c571  mov     dword ptr [rsp+88h+var_60], ebx; char
0x14002c575  mov     edx, r10d; int
0x14002c578  mov     r9d, 1000h; int
0x14002c57e  mov     [rsp+88h+var_68], rax; char *
0x14002c583  call    TraceEvents
0x14002c588  mov     eax, ebx
0x14002c58a  add     rsp, 48h
0x14002c58e  pop     r15
0x14002c590  pop     r14
0x14002c592  pop     r13
0x14002c594  pop     r12
0x14002c596  pop     rdi
0x14002c597  pop     rsi
0x14002c598  pop     rbp
0x14002c599  pop     rbx
0x14002c59a  retn
```
