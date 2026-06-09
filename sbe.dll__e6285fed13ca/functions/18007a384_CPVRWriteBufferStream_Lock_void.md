# CPVRWriteBufferStream::Lock(void)

- ea: `0x18007a384`
- end: `0x18007a41b`
- name: `?Lock@CPVRWriteBufferStream@@QEAAHXZ`
- size: `151`
- prototype: `__int64 __fastcall(CPVRWriteBufferStream *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1800787f8`
- `0x180078b14`
- `0x180078fb0`
- `0x18007925c`
- `0x18007935c`
- `0x180079c90`
- `0x18007c1b0`

## callees

- `0x18007a2d8`
- `0x18007a384`
- `0x18007c1f8`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18007a3af`
- `KERNEL32!WaitForSingleObject` at `0x18007a3af`
- `KERNEL32!GetCurrentThreadId` at `0x18007a3d7`
- `KERNEL32!GetCurrentThreadId` at `0x18007a3d7`
- `KERNEL32!LeaveCriticalSection` at `0x18007a3c6`
- `KERNEL32!LeaveCriticalSection` at `0x18007a3c6`
- `KERNEL32!EnterCriticalSection` at `0x18007a39d`
- `KERNEL32!EnterCriticalSection` at `0x18007a39d`

## pseudocode

```c
__int64 __fastcall CPVRWriteBufferStream::Lock(CPVRWriteBufferStream *this)
{
  __int64 v1; // rdi
  DWORD v3; // eax
  DWORD v4; // esi
  unsigned int v5; // ebx

  v1 = *((_QWORD *)this + 1);
  if ( !v1 )
    return 1;
  EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 8));
  if ( *(_DWORD *)v1 )
  {
    v4 = 0;
  }
  else
  {
    v3 = WaitForSingleObject(*(HANDLE *)(v1 + 48), 0xFFFFFFFF);
    v4 = v3;
    if ( v3 && v3 != 128 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 8));
      return 0;
    }
  }
  if ( !*(_DWORD *)v1 )
    *(_DWORD *)(v1 + 56) = GetCurrentThreadId();
  v5 = 1;
  ++*(_DWORD *)v1;
  if ( v4 )
  {
    if ( v4 != 128 )
      return 0;
    v5 = CPVRWriteBufferStream::IsValidWriteCache(this);
    if ( !v5 )
      CPVRWriteBufferStream::Unlock(this);
  }
  return v5;
}

```

## disassembly

```asm
0x18007a384  push    rbx
0x18007a386  push    rbp
0x18007a387  push    rsi
0x18007a388  push    rdi
0x18007a389  sub     rsp, 28h
0x18007a38d  mov     rdi, [rcx+8]
0x18007a391  mov     rbp, rcx
0x18007a394  test    rdi, rdi
0x18007a397  jz      short loc_18007A40B
0x18007a399  lea     rcx, [rdi+8]; lpCriticalSection
0x18007a39d  call    cs:__imp_EnterCriticalSection
0x18007a3a3  cmp     dword ptr [rdi], 0
0x18007a3a6  jnz     short loc_18007A3D0
0x18007a3a8  mov     rcx, [rdi+30h]; hHandle
0x18007a3ac  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007a3af  call    cs:__imp_WaitForSingleObject
0x18007a3b5  mov     esi, eax
0x18007a3b7  test    eax, eax
0x18007a3b9  jz      short loc_18007A3D2
0x18007a3bb  cmp     eax, 80h
0x18007a3c0  jz      short loc_18007A3D2
0x18007a3c2  lea     rcx, [rdi+8]; lpCriticalSection
0x18007a3c6  call    cs:__imp_LeaveCriticalSection
0x18007a3cc  xor     ebx, ebx
0x18007a3ce  jmp     short loc_18007A410
0x18007a3d0  xor     esi, esi
0x18007a3d2  cmp     dword ptr [rdi], 0
0x18007a3d5  jnz     short loc_18007A3E0
0x18007a3d7  call    cs:__imp_GetCurrentThreadId
0x18007a3dd  mov     [rdi+38h], eax
0x18007a3e0  mov     ebx, 1
0x18007a3e5  add     [rdi], ebx
0x18007a3e7  test    esi, esi
0x18007a3e9  jz      short loc_18007A410
0x18007a3eb  cmp     esi, 80h
0x18007a3f1  jnz     short loc_18007A3CC
0x18007a3f3  mov     rcx, rbp; this
0x18007a3f6  call    ?IsValidWriteCache@CPVRWriteBufferStream@@IEAAHXZ; CPVRWriteBufferStream::IsValidWriteCache(void)
0x18007a3fb  mov     ebx, eax
0x18007a3fd  test    eax, eax
0x18007a3ff  jnz     short loc_18007A410
0x18007a401  mov     rcx, rbp; this
0x18007a404  call    ?Unlock@CPVRWriteBufferStream@@QEAAXXZ; CPVRWriteBufferStream::Unlock(void)
0x18007a409  jmp     short loc_18007A410
0x18007a40b  mov     ebx, 1
0x18007a410  mov     eax, ebx
0x18007a412  add     rsp, 28h
0x18007a416  pop     rdi
0x18007a417  pop     rsi
0x18007a418  pop     rbp
0x18007a419  pop     rbx
0x18007a41a  retn
```
