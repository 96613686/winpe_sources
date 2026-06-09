# UdfDeleteInternalStream

- ea: `0x140058aac`
- end: `0x140058c4e`
- name: `UdfDeleteInternalStream`
- size: `418`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14004e020`
- `0x140052864`
- `0x1400537b0`
- `0x140058898`

## callees

- `0x140058aac`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140058b76`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140058b76`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140058bfc`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140058bfc`
- `ntoskrnl!ExAcquireFastMutex` at `0x140058ada`
- `ntoskrnl!ExAcquireFastMutex` at `0x140058ada`
- `ntoskrnl!ExReleaseFastMutex` at `0x140058b3e`
- `ntoskrnl!ExReleaseFastMutex` at `0x140058b3e`
- `ntoskrnl!ObfDereferenceObject` at `0x140058c36`
- `ntoskrnl!ObfDereferenceObject` at `0x140058c36`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140058c19`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140058c19`

## pseudocode

```c
void __fastcall UdfDeleteInternalStream(__int64 a1, __int64 a2)
{
  struct _KTHREAD *CurrentThread; // rdi
  __int64 v4; // rcx
  __int64 v5; // rax
  struct _FILE_OBJECT *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax

  CurrentThread = KeGetCurrentThread();
  v4 = *(_QWORD *)(a2 + 136);
  if ( CurrentThread != *(struct _KTHREAD **)(v4 + 64) )
  {
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v4 + 80) + 216LL));
    *(_QWORD *)(*(_QWORD *)(a2 + 136) + 64LL) = CurrentThread;
  }
  ++*(_DWORD *)(*(_QWORD *)(a2 + 136) + 72LL);
  v5 = *(_QWORD *)(a2 + 136);
  v6 = *(struct _FILE_OBJECT **)(a2 + 504);
  *(_QWORD *)(a2 + 504) = 0;
  --*(_DWORD *)(v5 + 72);
  v7 = *(_QWORD *)(a2 + 136);
  if ( !*(_DWORD *)(v7 + 72) )
  {
    *(_QWORD *)(v7 + 64) = 0;
    ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 80LL) + 216LL));
  }
  if ( v6 )
  {
    if ( (*(_DWORD *)(a2 + 212) & 0x8000000) != 0 )
    {
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL) + 1584LL));
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL) + 1640LL) = KeGetCurrentThread();
      v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL) + 320LL);
      --*(_DWORD *)(v8 + 204);
      v9 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL) + 320LL) + 136LL) + 8LL);
      --*(_DWORD *)(v9 + 256);
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL) + 1640LL) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL) + 1584LL));
    }
    else
    {
      if ( v6->PrivateCacheMap )
        CcUninitializeCacheMap(v6, 0, 0);
      v6->FileName.Buffer = 0;
      v6->FileName.Length = 0;
      ObfDereferenceObject(v6);
    }
  }
}

```

## disassembly

```asm
0x140058aac  mov     [rsp+arg_8], rbx
0x140058ab1  push    rdi
0x140058ab2  sub     rsp, 20h
0x140058ab6  mov     rdi, gs:188h
0x140058abf  mov     rbx, rdx
0x140058ac2  mov     rcx, [rdx+88h]
0x140058ac9  cmp     rdi, [rcx+40h]
0x140058acd  jz      short loc_140058AF1
0x140058acf  mov     rcx, [rcx+50h]
0x140058ad3  add     rcx, 0D8h; FastMutex
0x140058ada  call    cs:__imp_ExAcquireFastMutex
0x140058ae1  nop     dword ptr [rax+rax+00h]
0x140058ae6  mov     rax, [rbx+88h]
0x140058aed  mov     [rax+40h], rdi
0x140058af1  mov     rax, [rbx+88h]
0x140058af8  inc     dword ptr [rax+48h]
0x140058afb  mov     rax, [rbx+88h]
0x140058b02  mov     rdi, [rbx+1F8h]
0x140058b09  mov     qword ptr [rbx+1F8h], 0
0x140058b14  dec     dword ptr [rax+48h]
0x140058b17  mov     rax, [rbx+88h]
0x140058b1e  cmp     dword ptr [rax+48h], 0
0x140058b22  jnz     short loc_140058B4A
0x140058b24  mov     qword ptr [rax+40h], 0
0x140058b2c  mov     rax, [rbx+88h]
0x140058b33  mov     rcx, [rax+50h]
0x140058b37  add     rcx, 0D8h; FastMutex
0x140058b3e  call    cs:__imp_ExReleaseFastMutex
0x140058b45  nop     dword ptr [rax+rax+00h]
0x140058b4a  test    rdi, rdi
0x140058b4d  jz      loc_140058C42
0x140058b53  test    dword ptr [rbx+0D4h], 8000000h
0x140058b5d  jz      loc_140058C0A
0x140058b63  mov     rax, [rbx+88h]
0x140058b6a  mov     edi, 630h
0x140058b6f  mov     rcx, [rax+8]
0x140058b73  add     rcx, rdi; FastMutex
0x140058b76  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140058b7d  nop     dword ptr [rax+rax+00h]
0x140058b82  mov     rdx, gs:188h
0x140058b8b  mov     rax, [rbx+88h]
0x140058b92  mov     rcx, [rax+8]
0x140058b96  mov     [rcx+668h], rdx
0x140058b9d  mov     rax, [rbx+88h]
0x140058ba4  mov     rcx, [rax+8]
0x140058ba8  mov     rax, [rcx+140h]
0x140058baf  dec     dword ptr [rax+0CCh]
0x140058bb5  mov     rax, [rbx+88h]
0x140058bbc  mov     rcx, [rax+8]
0x140058bc0  mov     rax, [rcx+140h]
0x140058bc7  mov     rcx, [rax+88h]
0x140058bce  mov     rax, [rcx+8]
0x140058bd2  dec     dword ptr [rax+100h]
0x140058bd8  mov     rax, [rbx+88h]
0x140058bdf  mov     rcx, [rax+8]
0x140058be3  mov     qword ptr [rcx+668h], 0
0x140058bee  mov     rax, [rbx+88h]
0x140058bf5  mov     rcx, [rax+8]
0x140058bf9  add     rcx, rdi; FastMutex
0x140058bfc  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140058c03  nop     dword ptr [rax+rax+00h]
0x140058c08  jmp     short loc_140058C42
0x140058c0a  cmp     qword ptr [rdi+30h], 0
0x140058c0f  jz      short loc_140058C25
0x140058c11  xor     r8d, r8d; UninitializeEvent
0x140058c14  xor     edx, edx; TruncateSize
0x140058c16  mov     rcx, rdi; FileObject
0x140058c19  call    cs:__imp_CcUninitializeCacheMap
0x140058c20  nop     dword ptr [rax+rax+00h]
0x140058c25  xor     eax, eax
0x140058c27  mov     qword ptr [rdi+60h], 0
0x140058c2f  mov     rcx, rdi; Object
0x140058c32  mov     [rdi+58h], ax
0x140058c36  call    cs:__imp_ObfDereferenceObject
0x140058c3d  nop     dword ptr [rax+rax+00h]
0x140058c42  mov     rbx, [rsp+28h+arg_8]
0x140058c47  add     rsp, 20h
0x140058c4b  pop     rdi
0x140058c4c  retn
```
