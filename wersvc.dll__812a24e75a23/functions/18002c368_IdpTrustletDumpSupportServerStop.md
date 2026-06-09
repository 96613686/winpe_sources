# IdpTrustletDumpSupportServerStop

- ea: `0x18002c368`
- end: `0x18002c3f4`
- name: `IdpTrustletDumpSupportServerStop`
- size: `140`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002c778`

## callees

- `0x18002c368`

## import_xrefs

- `ntdll!NtClose` at `0x18002c379`
- `ntdll!NtClose` at `0x18002c3b2`
- `ntdll!NtClose` at `0x18002c379`
- `ntdll!NtClose` at `0x18002c3b2`
- `ntdll!NtTerminateThread` at `0x18002c3a8`
- `ntdll!NtTerminateThread` at `0x18002c3a8`
- `ntdll!RtlFreeHeap` at `0x18002c3d0`
- `ntdll!RtlFreeHeap` at `0x18002c3d0`
- `ntdll!RtlFreeHeap` at `0x18002c3ed`
- `ntdll!NtWaitForSingleObject` at `0x18002c398`
- `ntdll!NtWaitForSingleObject` at `0x18002c398`

## pseudocode

```c
BOOLEAN __fastcall IdpTrustletDumpSupportServerStop(void *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // r8
  union _LARGE_INTEGER Timeout; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(void **)a1;
  if ( v2 )
    NtClose(v2);
  v3 = (void *)*((_QWORD *)a1 + 4);
  if ( v3 )
  {
    Timeout.QuadPart = -100000000;
    if ( NtWaitForSingleObject(v3, 0, &Timeout) )
      NtTerminateThread(*((HANDLE *)a1 + 4), 0);
    NtClose(*((HANDLE *)a1 + 4));
  }
  v4 = (void *)*((_QWORD *)a1 + 3);
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x18002c368  push    rbx
0x18002c36a  sub     rsp, 20h
0x18002c36e  mov     rbx, rcx
0x18002c371  mov     rcx, [rcx]; Handle
0x18002c374  test    rcx, rcx
0x18002c377  jz      short loc_18002C37F
0x18002c379  call    cs:__imp_NtClose
0x18002c37f  mov     rcx, [rbx+20h]; Handle
0x18002c383  test    rcx, rcx
0x18002c386  jz      short loc_18002C3B8
0x18002c388  lea     r8, [rsp+28h+Timeout]; Timeout
0x18002c38d  mov     qword ptr [rsp+28h+Timeout], 0FFFFFFFFFA0A1F00h
0x18002c396  xor     edx, edx; Alertable
0x18002c398  call    cs:__imp_NtWaitForSingleObject
0x18002c39e  test    eax, eax
0x18002c3a0  jz      short loc_18002C3AE
0x18002c3a2  mov     rcx, [rbx+20h]; ThreadHandle
0x18002c3a6  xor     edx, edx; ExitStatus
0x18002c3a8  call    cs:__imp_NtTerminateThread
0x18002c3ae  mov     rcx, [rbx+20h]; Handle
0x18002c3b2  call    cs:__imp_NtClose
0x18002c3b8  mov     r8, [rbx+18h]; P
0x18002c3bc  test    r8, r8
0x18002c3bf  jz      short loc_18002C3D6
0x18002c3c1  mov     rcx, gs:60h
0x18002c3ca  xor     edx, edx; Flags
0x18002c3cc  mov     rcx, [rcx+30h]; HeapHandle
0x18002c3d0  call    cs:__imp_RtlFreeHeap
0x18002c3d6  mov     rcx, gs:60h
0x18002c3df  mov     r8, rbx
0x18002c3e2  xor     edx, edx
0x18002c3e4  mov     rcx, [rcx+30h]
0x18002c3e8  add     rsp, 20h
0x18002c3ec  pop     rbx
0x18002c3ed  jmp     cs:__imp_RtlFreeHeap
```
