# WimFSFLockSystemBackingVolume

- ea: `0x14002d7f4`
- end: `0x14002d939`
- name: `WimFSFLockSystemBackingVolume`
- size: `325`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400263f0`
- `0x14002dcc0`

## callees

- `0x14000edcc`
- `0x14002d7f4`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14002d857`
- `ntoskrnl!KeDelayExecutionThread` at `0x14002d857`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002d8c2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002d8f2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002d8c2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002d8f2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002d8b0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002d8e0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002d8b0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002d8e0`
- `FLTMGR!FltObjectDereference` at `0x14002d889`
- `FLTMGR!FltObjectDereference` at `0x14002d889`
- `FLTMGR!FltReleaseContext` at `0x14002d8d1`
- `FLTMGR!FltReleaseContext` at `0x14002d90c`
- `FLTMGR!FltReleaseContext` at `0x14002d8d1`
- `FLTMGR!FltReleaseContext` at `0x14002d90c`

## pseudocode

```c
__int64 __fastcall WimFSFLockSystemBackingVolume(struct _UNICODE_STRING *a1, struct _FAST_MUTEX **a2)
{
  unsigned int v2; // r14d
  struct _FAST_MUTEX *v3; // rdi
  char *v4; // rsi
  int AttachVolumeFromPathName; // ebx
  struct _FAST_MUTEX *v8; // rbx
  char *v9; // rbp
  __int64 result; // rax
  PFAST_MUTEX FastMutex[7]; // [rsp+20h] [rbp-38h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+70h] [rbp+18h] BYREF
  PVOID FltObject; // [rsp+78h] [rbp+20h] BYREF

  v2 = 0;
  FltObject = 0;
  v3 = 0;
  FastMutex[0] = 0;
  v4 = 0;
  while ( 1 )
  {
    do
    {
      AttachVolumeFromPathName = WofGetAttachVolumeFromPathName(a1, 0, &FltObject, FastMutex);
      if ( (unsigned int)(AttachVolumeFromPathName + 2147483632) <= 1 )
      {
        Interval.QuadPart = -1000000;
        KeDelayExecutionThread(0, 0, &Interval);
        ++v2;
        if ( AttachVolumeFromPathName == -2147483632 )
          continue;
      }
      if ( AttachVolumeFromPathName != -2147483631 )
        break;
    }
    while ( v2 < 0x28 );
    if ( AttachVolumeFromPathName < 0 )
      break;
    FltObjectDereference(FltObject);
    v8 = FastMutex[0];
    v9 = (char *)FastMutex[0] + (unsigned int)dword_14001A2FC;
    if ( v4 == v9 )
    {
      FltReleaseContext(v3);
      result = 0;
      *a2 = v3;
      return result;
    }
    if ( v4 )
    {
      ExAcquireFastMutexUnsafe(v3);
      --*((_DWORD *)v4 + 1);
      ExReleaseFastMutexUnsafe(v3);
      FltReleaseContext(v3);
    }
    ExAcquireFastMutexUnsafe(v8);
    ++*((_DWORD *)v9 + 1);
    ExReleaseFastMutexUnsafe(v8);
    v4 = v9;
    v3 = v8;
  }
  return (unsigned int)AttachVolumeFromPathName;
}

```

## disassembly

```asm
0x14002d7f4  mov     rax, rsp
0x14002d7f7  mov     [rax+8], rbx
0x14002d7fb  mov     [rax+10h], rbp
0x14002d7ff  push    rsi
0x14002d800  push    rdi
0x14002d801  push    r12
0x14002d803  push    r14
0x14002d805  push    r15
0x14002d807  sub     rsp, 30h
0x14002d80b  xor     r14d, r14d
0x14002d80e  mov     qword ptr [rax+20h], 0
0x14002d816  xor     edi, edi
0x14002d818  mov     [rax-38h], r14
0x14002d81c  xor     esi, esi
0x14002d81e  mov     r15, rdx
0x14002d821  mov     r12, rcx
0x14002d824  lea     r9, [rsp+58h+FastMutex]
0x14002d829  xor     edx, edx
0x14002d82b  lea     r8, [rsp+58h+FltObject]
0x14002d830  mov     rcx, r12
0x14002d833  call    WofGetAttachVolumeFromPathName
0x14002d838  mov     ebx, eax
0x14002d83a  lea     ecx, [rax+7FFFFFF0h]
0x14002d840  cmp     ecx, 1
0x14002d843  ja      short loc_14002D86E
0x14002d845  lea     r8, [rsp+58h+Interval]; Interval
0x14002d84a  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFF0BDC0h
0x14002d853  xor     edx, edx; Alertable
0x14002d855  xor     ecx, ecx; WaitMode
0x14002d857  call    cs:__imp_KeDelayExecutionThread
0x14002d85e  nop     dword ptr [rax+rax+00h]
0x14002d863  inc     r14d
0x14002d866  cmp     ebx, 80000010h
0x14002d86c  jz      short loc_14002D876
0x14002d86e  cmp     ebx, 80000011h
0x14002d874  jnz     short loc_14002D87C
0x14002d876  cmp     r14d, 28h ; '('
0x14002d87a  jb      short loc_14002D824
0x14002d87c  test    ebx, ebx
0x14002d87e  js      loc_14002D91F
0x14002d884  mov     rcx, [rsp+58h+FltObject]; FltObject
0x14002d889  call    cs:__imp_FltObjectDereference
0x14002d890  nop     dword ptr [rax+rax+00h]
0x14002d895  mov     ebp, cs:dword_14001A2FC
0x14002d89b  mov     rbx, [rsp+58h+FastMutex]
0x14002d8a0  add     rbp, rbx
0x14002d8a3  cmp     rsi, rbp
0x14002d8a6  jz      short loc_14002D909
0x14002d8a8  test    rsi, rsi
0x14002d8ab  jz      short loc_14002D8DD
0x14002d8ad  mov     rcx, rdi; FastMutex
0x14002d8b0  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002d8b7  nop     dword ptr [rax+rax+00h]
0x14002d8bc  dec     dword ptr [rsi+4]
0x14002d8bf  mov     rcx, rdi; FastMutex
0x14002d8c2  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002d8c9  nop     dword ptr [rax+rax+00h]
0x14002d8ce  mov     rcx, rdi; Context
0x14002d8d1  call    cs:__imp_FltReleaseContext
0x14002d8d8  nop     dword ptr [rax+rax+00h]
0x14002d8dd  mov     rcx, rbx; FastMutex
0x14002d8e0  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002d8e7  nop     dword ptr [rax+rax+00h]
0x14002d8ec  inc     dword ptr [rbp+4]
0x14002d8ef  mov     rcx, rbx; FastMutex
0x14002d8f2  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002d8f9  nop     dword ptr [rax+rax+00h]
0x14002d8fe  mov     rsi, rbp
0x14002d901  mov     rdi, rbx
0x14002d904  jmp     loc_14002D824
0x14002d909  mov     rcx, rdi; Context
0x14002d90c  call    cs:__imp_FltReleaseContext
0x14002d913  nop     dword ptr [rax+rax+00h]
0x14002d918  xor     eax, eax
0x14002d91a  mov     [r15], rdi
0x14002d91d  jmp     short loc_14002D921
0x14002d91f  mov     eax, ebx
0x14002d921  mov     rbx, [rsp+58h+arg_0]
0x14002d926  mov     rbp, [rsp+58h+arg_8]
0x14002d92b  add     rsp, 30h
0x14002d92f  pop     r15
0x14002d931  pop     r14
0x14002d933  pop     r12
0x14002d935  pop     rdi
0x14002d936  pop     rsi
0x14002d937  retn
```
