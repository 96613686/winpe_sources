# SmpReleaseControlBlock

- ea: `0x140004ec0`
- end: `0x140005029`
- name: `SmpReleaseControlBlock`
- size: `361`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140001880`
- `0x140001f60`
- `0x1400031b0`
- `0x1400036d0`
- `0x140005ac4`

## callees

- `0x140004ec0`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtClose` at `0x140004f2d`
- `ntdll!NtClose` at `0x140004f37`
- `ntdll!NtClose` at `0x140004f52`
- `ntdll!NtClose` at `0x14000501e`
- `ntdll!NtClose` at `0x140004f2d`
- `ntdll!NtClose` at `0x140004f37`
- `ntdll!NtClose` at `0x140004f52`
- `ntdll!NtClose` at `0x14000501e`
- `ntdll!RtlFreeHeap` at `0x140004f6a`
- `ntdll!RtlFreeHeap` at `0x140004f6a`
- `ntdll!NtUnmapViewOfSection` at `0x140004f48`
- `ntdll!NtUnmapViewOfSection` at `0x140004f48`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140004ff7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140004ff7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140005015`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140005015`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x140004fea`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x140004fea`
- `ntdll!RtlDeleteNoSplay` at `0x140005008`
- `ntdll!RtlDeleteNoSplay` at `0x140005008`

## pseudocode

```c
BOOLEAN __fastcall SmpReleaseControlBlock(char *BaseAddress)
{
  signed __int32 v2; // eax
  bool v3; // cc
  BOOLEAN result; // al
  void *v5; // rdi
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  _OWORD v8[2]; // [rsp+40h] [rbp-168h] BYREF
  __int64 v9; // [rsp+60h] [rbp-148h]
  int v10; // [rsp+68h] [rbp-140h]
  int v11; // [rsp+6Ch] [rbp-13Ch]
  int v12; // [rsp+70h] [rbp-138h]

  memset_0(v8, 0, 0x148u);
  v2 = _InterlockedExchangeAdd((volatile signed __int32 *)BaseAddress + 1, 0xFFFFFFFF);
  v3 = v2 <= 1;
  result = v2 - 1;
  if ( v3 )
  {
    v5 = (void *)*((_QWORD *)BaseAddress + 6);
    if ( v5 )
    {
      if ( (*BaseAddress & 1) == 0 && *((_QWORD *)BaseAddress + 9) != SmpUniqueProcessId )
      {
        v6 = *((_OWORD *)BaseAddress + 4);
        v7 = *((_OWORD *)BaseAddress + 5);
        v12 = *((_DWORD *)BaseAddress + 2);
        v8[0] = v6;
        v9 = *((_QWORD *)BaseAddress + 12);
        v8[1] = v7;
        v10 = 5;
        v11 = -1073741823;
        ((void (__fastcall *)(__int64, __int64, _OWORD *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))NtAlpcSendWaitReceivePort)(
          SmpApiConnectionPort,
          0x10000,
          v8,
          0,
          0,
          0,
          0,
          0);
      }
      RtlAcquireSRWLockExclusive(&SmpControlLock);
      RtlDeleteNoSplay((PRTL_SPLAY_LINKS)(BaseAddress + 104), &SmpControlBlockRoot);
      RtlReleaseSRWLockExclusive(&SmpControlLock);
      NtClose(v5);
    }
    NtClose(*((HANDLE *)BaseAddress + 4));
    NtClose(*((HANDLE *)BaseAddress + 5));
    NtUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, *((PVOID *)BaseAddress + 2));
    NtClose(*((HANDLE *)BaseAddress + 3));
    return RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, BaseAddress);
  }
  return result;
}

```

## disassembly

```asm
0x140004ec0  push    rbx
0x140004ec2  sub     rsp, 1A0h
0x140004ec9  mov     rax, cs:__security_cookie
0x140004ed0  xor     rax, rsp
0x140004ed3  mov     [rsp+1A8h+var_18], rax
0x140004edb  mov     rbx, rcx
0x140004ede  xor     edx, edx; Val
0x140004ee0  lea     rcx, [rsp+1A8h+var_168]; void *
0x140004ee5  mov     r8d, 148h; Size
0x140004eeb  call    memset_0
0x140004ef0  mov     eax, 0FFFFFFFFh
0x140004ef5  lock xadd [rbx+4], eax
0x140004efa  sub     eax, 1
0x140004efd  jle     short loc_140004F18
0x140004eff  mov     rcx, [rsp+1A8h+var_18]
0x140004f07  xor     rcx, rsp; StackCookie
0x140004f0a  call    __security_check_cookie
0x140004f0f  add     rsp, 1A0h
0x140004f16  pop     rbx
0x140004f17  retn
0x140004f18  mov     [rsp+1A8h+arg_8], rdi
0x140004f20  mov     rdi, [rbx+30h]
0x140004f24  test    rdi, rdi
0x140004f27  jnz     short loc_140004F7A
0x140004f29  mov     rcx, [rbx+20h]; Handle
0x140004f2d  call    cs:__imp_NtClose
0x140004f33  mov     rcx, [rbx+28h]; Handle
0x140004f37  call    cs:__imp_NtClose
0x140004f3d  mov     rdx, [rbx+10h]; BaseAddress
0x140004f41  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140004f48  call    cs:__imp_NtUnmapViewOfSection
0x140004f4e  mov     rcx, [rbx+18h]; Handle
0x140004f52  call    cs:__imp_NtClose
0x140004f58  mov     rcx, gs:60h
0x140004f61  mov     r8, rbx; BaseAddress
0x140004f64  xor     edx, edx; Flags
0x140004f66  mov     rcx, [rcx+30h]; HeapHandle
0x140004f6a  call    cs:__imp_RtlFreeHeap
0x140004f70  mov     rdi, [rsp+1A8h+arg_8]
0x140004f78  jmp     short loc_140004EFF
0x140004f7a  test    byte ptr [rbx], 1
0x140004f7d  jnz     short loc_140004FF0
0x140004f7f  mov     rax, cs:SmpUniqueProcessId
0x140004f86  cmp     [rbx+48h], rax
0x140004f8a  jz      short loc_140004FF0
0x140004f8c  movups  xmm0, xmmword ptr [rbx+40h]
0x140004f90  mov     eax, [rbx+8]
0x140004f93  lea     r8, [rsp+1A8h+var_168]
0x140004f98  movups  xmm1, xmmword ptr [rbx+50h]
0x140004f9c  mov     rcx, cs:SmpApiConnectionPort
0x140004fa3  xor     r9d, r9d
0x140004fa6  mov     [rsp+1A8h+var_138], eax
0x140004faa  mov     edx, 10000h
0x140004faf  xor     eax, eax
0x140004fb1  movaps  [rsp+1A8h+var_168], xmm0
0x140004fb6  movsd   xmm0, qword ptr [rbx+60h]
0x140004fbb  mov     [rsp+1A8h+var_170], rax
0x140004fc0  mov     [rsp+1A8h+var_178], rax
0x140004fc5  mov     [rsp+1A8h+var_180], rax
0x140004fca  movsd   [rsp+1A8h+var_148], xmm0
0x140004fd0  mov     [rsp+1A8h+var_188], rax
0x140004fd5  movaps  [rsp+1A8h+var_158], xmm1
0x140004fda  mov     [rsp+1A8h+var_140], 5
0x140004fe2  mov     [rsp+1A8h+var_13C], 0C0000001h
0x140004fea  call    cs:__imp_NtAlpcSendWaitReceivePort
0x140004ff0  lea     rcx, SmpControlLock
0x140004ff7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x140004ffd  lea     rcx, [rbx+68h]; Links
0x140005001  lea     rdx, SmpControlBlockRoot; Root
0x140005008  call    cs:__imp_RtlDeleteNoSplay
0x14000500e  lea     rcx, SmpControlLock
0x140005015  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14000501b  mov     rcx, rdi; Handle
0x14000501e  call    cs:__imp_NtClose
0x140005024  jmp     loc_140004F29
```
