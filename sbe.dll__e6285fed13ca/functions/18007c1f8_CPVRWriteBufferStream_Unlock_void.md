# CPVRWriteBufferStream::Unlock(void)

- ea: `0x18007c1f8`
- end: `0x18007c238`
- name: `?Unlock@CPVRWriteBufferStream@@QEAAXXZ`
- size: `64`
- prototype: `void __fastcall(CPVRWriteBufferStream *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800787f8`
- `0x180078b14`
- `0x180078fb0`
- `0x18007925c`
- `0x18007935c`
- `0x180079c90`
- `0x18007a384`
- `0x18007c1b0`

## callees

- `0x18007c1f8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007c207`
- `KERNEL32!GetCurrentThreadId` at `0x18007c207`
- `KERNEL32!LeaveCriticalSection` at `0x18007c22c`
- `KERNEL32!LeaveCriticalSection` at `0x18007c22c`
- `KERNEL32!ReleaseMutex` at `0x18007c21b`
- `KERNEL32!ReleaseMutex` at `0x18007c21b`

## pseudocode

```c
void __fastcall CPVRWriteBufferStream::Unlock(CPVRWriteBufferStream *this)
{
  __int64 v1; // rbx

  v1 = *((_QWORD *)this + 1);
  if ( v1 && *(_DWORD *)(v1 + 56) == GetCurrentThreadId() )
  {
    if ( (*(_DWORD *)v1)-- == 1 )
    {
      ReleaseMutex(*(HANDLE *)(v1 + 48));
      *(_DWORD *)(v1 + 56) = -1;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 8));
  }
}

```

## disassembly

```asm
0x18007c1f8  push    rbx
0x18007c1fa  sub     rsp, 20h
0x18007c1fe  mov     rbx, [rcx+8]
0x18007c202  test    rbx, rbx
0x18007c205  jz      short loc_18007C232
0x18007c207  call    cs:__imp_GetCurrentThreadId
0x18007c20d  cmp     [rbx+38h], eax
0x18007c210  jnz     short loc_18007C232
0x18007c212  sub     dword ptr [rbx], 1
0x18007c215  jnz     short loc_18007C228
0x18007c217  mov     rcx, [rbx+30h]; hMutex
0x18007c21b  call    cs:__imp_ReleaseMutex
0x18007c221  mov     dword ptr [rbx+38h], 0FFFFFFFFh
0x18007c228  lea     rcx, [rbx+8]; lpCriticalSection
0x18007c22c  call    cs:__imp_LeaveCriticalSection
0x18007c232  add     rsp, 20h
0x18007c236  pop     rbx
0x18007c237  retn
```
