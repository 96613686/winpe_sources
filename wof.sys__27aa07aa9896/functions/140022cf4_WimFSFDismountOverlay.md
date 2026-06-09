# WimFSFDismountOverlay

- ea: `0x140022cf4`
- end: `0x140022e24`
- name: `WimFSFDismountOverlay`
- size: `304`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140026940`
- `0x140026c00`
- `0x140027410`
- `0x1400277c0`
- `0x14002df00`

## callees

- `0x1400104d8`
- `0x140022cf4`
- `0x140022e2c`

## import_xrefs

- `ntoskrnl!ExRundownCompleted` at `0x140022df0`
- `ntoskrnl!ExRundownCompleted` at `0x140022df0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022d99`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022de0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022e00`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022d99`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022de0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022e00`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140022d49`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140022d49`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022d39`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022d64`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022dc2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022d39`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022d64`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022dc2`

## pseudocode

```c
void __fastcall WimFSFDismountOverlay(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // edi
  PFAST_MUTEX *v5; // rdi
  __int64 v6; // rdx
  _QWORD *v7; // rcx
  __int64 v8; // rdi
  struct _FAST_MUTEX *v9; // rdi

  v3 = a2;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_qi(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a1, *(_QWORD *)(a1 + 88));
  _InterlockedOr((volatile signed __int32 *)(a1 + 40), v3);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 112));
  ExWaitForRundownProtectionRelease(*(PEX_RUNDOWN_REF *)(a1 + 96));
  v5 = (PFAST_MUTEX *)_InterlockedExchange64((volatile __int64 *)(a1 + 104), 0);
  if ( v5 )
  {
    ExAcquireFastMutexUnsafe(v5[5]);
    v6 = *(_QWORD *)(a1 + 16);
    if ( *(_QWORD *)(v6 + 8) != a1 + 16 || (v7 = *(_QWORD **)(a1 + 24), *v7 != a1 + 16) )
      __fastfail(3u);
    *v7 = v6;
    *(_QWORD *)(v6 + 8) = v7;
    ExReleaseFastMutexUnsafe(v5[5]);
    WimFSFDereferenceBackingFile(v5);
  }
  v8 = *(_QWORD *)(a1 + 32);
  if ( v8 )
  {
    v9 = (struct _FAST_MUTEX *)(v8 - (unsigned int)dword_14001A2FC);
    ExAcquireFastMutexUnsafe(v9);
    --*(_DWORD *)(*(_QWORD *)(a1 + 32) + 4LL);
    *(_QWORD *)(a1 + 32) = 0;
    ExReleaseFastMutexUnsafe(v9);
  }
  ExRundownCompleted(*(PEX_RUNDOWN_REF *)(a1 + 96));
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 112));
}

```

## disassembly

```asm
0x140022cf4  mov     [rsp+arg_0], rbx
0x140022cf9  mov     [rsp+arg_8], rsi
0x140022cfe  push    rdi
0x140022cff  sub     rsp, 30h
0x140022d03  mov     edi, edx
0x140022d05  mov     rbx, rcx
0x140022d08  mov     rcx, cs:WPP_GLOBAL_Control
0x140022d0f  mov     eax, [rcx+2Ch]
0x140022d12  test    al, 8
0x140022d14  jz      short loc_140022D31
0x140022d16  cmp     byte ptr [rcx+29h], 4
0x140022d1a  jb      short loc_140022D31
0x140022d1c  mov     rax, [rbx+58h]
0x140022d20  mov     r9, rbx
0x140022d23  mov     rcx, [rcx+18h]
0x140022d27  mov     [rsp+38h+var_18], rax
0x140022d2c  call    WPP_SF_qi
0x140022d31  lock or [rbx+28h], edi
0x140022d35  lea     rcx, [rbx+70h]; FastMutex
0x140022d39  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140022d40  nop     dword ptr [rax+rax+00h]
0x140022d45  mov     rcx, [rbx+60h]; RunRef
0x140022d49  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140022d50  nop     dword ptr [rax+rax+00h]
0x140022d55  xor     edi, edi
0x140022d57  xchg    rdi, [rbx+68h]
0x140022d5b  test    rdi, rdi
0x140022d5e  jz      short loc_140022DAD
0x140022d60  mov     rcx, [rdi+28h]; FastMutex
0x140022d64  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140022d6b  nop     dword ptr [rax+rax+00h]
0x140022d70  lea     rax, [rbx+10h]
0x140022d74  mov     rdx, [rax]
0x140022d77  cmp     [rdx+8], rax
0x140022d7b  jnz     loc_140022E1D
0x140022d81  mov     rcx, [rax+8]
0x140022d85  cmp     [rcx], rax
0x140022d88  jnz     loc_140022E1D
0x140022d8e  mov     [rcx], rdx
0x140022d91  mov     [rdx+8], rcx
0x140022d95  mov     rcx, [rdi+28h]; FastMutex
0x140022d99  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140022da0  nop     dword ptr [rax+rax+00h]
0x140022da5  mov     rcx, rdi; P
0x140022da8  call    WimFSFDereferenceBackingFile
0x140022dad  mov     rdi, [rbx+20h]
0x140022db1  test    rdi, rdi
0x140022db4  jz      short loc_140022DEC
0x140022db6  mov     eax, cs:dword_14001A2FC
0x140022dbc  sub     rdi, rax
0x140022dbf  mov     rcx, rdi; FastMutex
0x140022dc2  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140022dc9  nop     dword ptr [rax+rax+00h]
0x140022dce  mov     rax, [rbx+20h]
0x140022dd2  mov     rcx, rdi; FastMutex
0x140022dd5  dec     dword ptr [rax+4]
0x140022dd8  mov     qword ptr [rbx+20h], 0
0x140022de0  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140022de7  nop     dword ptr [rax+rax+00h]
0x140022dec  mov     rcx, [rbx+60h]; RunRef
0x140022df0  call    cs:__imp_ExRundownCompleted
0x140022df7  nop     dword ptr [rax+rax+00h]
0x140022dfc  lea     rcx, [rbx+70h]; FastMutex
0x140022e00  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140022e07  nop     dword ptr [rax+rax+00h]
0x140022e0c  mov     rbx, [rsp+38h+arg_0]
0x140022e11  mov     rsi, [rsp+38h+arg_8]
0x140022e16  add     rsp, 30h
0x140022e1a  pop     rdi
0x140022e1b  retn
0x140022e1d  mov     ecx, 3
0x140022e22  int     29h; Win8: RtlFailFast(ecx)
```
