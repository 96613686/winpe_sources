# AslTelemetryDelete

- ea: `0x14000c3e8`
- end: `0x14000c537`
- name: `AslTelemetryDelete`
- size: `335`
- prototype: `char __fastcall(char *P)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000320c`
- `0x14000c1a0`
- `0x14002ec10`

## callees

- `0x14000c3e8`
- `0x14000c540`
- `0x14000d854`

## import_xrefs

- `ADVAPI32!EventUnregister` at `0x14000c430`
- `ADVAPI32!EventUnregister` at `0x14000c430`
- `ntdll!RtlDeleteCriticalSection` at `0x14000c509`
- `ntdll!RtlDeleteCriticalSection` at `0x14000c509`
- `ntdll!RtlFreeHeap` at `0x14000c4ab`
- `ntdll!RtlFreeHeap` at `0x14000c4de`
- `ntdll!RtlFreeHeap` at `0x14000c521`
- `ntdll!RtlFreeHeap` at `0x14000c4ab`
- `ntdll!RtlFreeHeap` at `0x14000c4de`
- `ntdll!RtlFreeHeap` at `0x14000c521`

## pseudocode

```c
char __fastcall AslTelemetryDelete(char *P)
{
  signed __int32 v2; // eax
  REGHANDLE v3; // rcx
  unsigned __int64 v4; // rcx
  unsigned int i; // esi
  __int64 v6; // rdi
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  void *v9; // r8
  void *v10; // r8

  if ( P )
    AslTelemetryFlush();
  v2 = _InterlockedExchangeAdd(&dword_140042B10, 0xFFFFFFFF);
  if ( v2 == 1 )
  {
    v3 = RegHandle;
    dword_140042000 = 0;
    RegHandle = 0;
    LOBYTE(v2) = EventUnregister(v3);
  }
  if ( P )
  {
    v4 = *((_QWORD *)P + 24);
    if ( v4 )
    {
      for ( i = 0; i < v4; ++i )
      {
        v6 = 0;
        if ( i < v4 )
        {
          v7 = *((_QWORD *)P + 23) * i;
          if ( !is_mul_ok(*((_QWORD *)P + 23), i) || (v8 = *((_QWORD *)P + 27), v6 = v8 + v7, v8 + v7 < v8) )
            v6 = 0;
        }
        AslAnsiStringFree(v6 + 8);
        AslAnsiStringFree(v6 + 24);
        v4 = *((_QWORD *)P + 24);
      }
    }
    v9 = (void *)*((_QWORD *)P + 27);
    if ( v9 )
      RtlFreeHeap(*((HANDLE *)P + 22), 0, v9);
    *((_OWORD *)P + 11) = 0;
    *((_OWORD *)P + 12) = 0;
    *((_OWORD *)P + 13) = 0;
    v10 = (void *)*((_QWORD *)P + 21);
    if ( v10 )
      RtlFreeHeap(*((HANDLE *)P + 16), 0, v10);
    *((_OWORD *)P + 8) = 0;
    *((_OWORD *)P + 9) = 0;
    *((_OWORD *)P + 10) = 0;
    AslAnsiStringFree(P + 72);
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(P + 88));
    LOBYTE(v2) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return v2;
}

```

## disassembly

```asm
0x14000c3e8  mov     [rsp+arg_8], rbx
0x14000c3ed  mov     [rsp+arg_10], rsi
0x14000c3f2  push    rdi
0x14000c3f3  sub     rsp, 20h
0x14000c3f7  mov     rbx, rcx
0x14000c3fa  test    rcx, rcx
0x14000c3fd  jz      short loc_14000C404
0x14000c3ff  call    AslTelemetryFlush
0x14000c404  or      eax, 0FFFFFFFFh
0x14000c407  lock xadd cs:dword_140042B10, eax
0x14000c40f  cmp     eax, 1
0x14000c412  jnz     short loc_14000C436
0x14000c414  mov     rcx, cs:RegHandle; RegHandle
0x14000c41b  mov     cs:dword_140042000, 0
0x14000c425  mov     cs:RegHandle, 0
0x14000c430  call    cs:__imp_EventUnregister
0x14000c436  test    rbx, rbx
0x14000c439  jz      loc_14000C527
0x14000c43f  mov     rcx, [rbx+0C0h]
0x14000c446  test    rcx, rcx
0x14000c449  jz      short loc_14000C496
0x14000c44b  xor     esi, esi
0x14000c44d  xor     edi, edi
0x14000c44f  mov     eax, esi
0x14000c451  cmp     rax, rcx
0x14000c454  jnb     short loc_14000C474
0x14000c456  mul     qword ptr [rbx+0B8h]
0x14000c45d  test    rdx, rdx
0x14000c460  jnz     short loc_14000C472
0x14000c462  mov     rcx, [rbx+0D8h]
0x14000c469  lea     rdi, [rcx+rax]
0x14000c46d  cmp     rdi, rcx
0x14000c470  jnb     short loc_14000C474
0x14000c472  xor     edi, edi
0x14000c474  lea     rcx, [rdi+8]
0x14000c478  call    AslAnsiStringFree
0x14000c47d  lea     rcx, [rdi+18h]
0x14000c481  call    AslAnsiStringFree
0x14000c486  mov     rcx, [rbx+0C0h]
0x14000c48d  inc     esi
0x14000c48f  mov     eax, esi
0x14000c491  cmp     rax, rcx
0x14000c494  jb      short loc_14000C44D
0x14000c496  mov     r8, [rbx+0D8h]; P
0x14000c49d  test    r8, r8
0x14000c4a0  jz      short loc_14000C4B1
0x14000c4a2  mov     rcx, [rbx+0B0h]; HeapHandle
0x14000c4a9  xor     edx, edx; Flags
0x14000c4ab  call    cs:__imp_RtlFreeHeap
0x14000c4b1  xorps   xmm0, xmm0
0x14000c4b4  movups  xmmword ptr [rbx+0B0h], xmm0
0x14000c4bb  movups  xmmword ptr [rbx+0C0h], xmm0
0x14000c4c2  movups  xmmword ptr [rbx+0D0h], xmm0
0x14000c4c9  mov     r8, [rbx+0A8h]; P
0x14000c4d0  test    r8, r8
0x14000c4d3  jz      short loc_14000C4E4
0x14000c4d5  mov     rcx, [rbx+80h]; HeapHandle
0x14000c4dc  xor     edx, edx; Flags
0x14000c4de  call    cs:__imp_RtlFreeHeap
0x14000c4e4  xorps   xmm0, xmm0
0x14000c4e7  lea     rcx, [rbx+48h]
0x14000c4eb  movups  xmmword ptr [rbx+80h], xmm0
0x14000c4f2  movups  xmmword ptr [rbx+90h], xmm0
0x14000c4f9  movups  xmmword ptr [rbx+0A0h], xmm0
0x14000c500  call    AslAnsiStringFree
0x14000c505  lea     rcx, [rbx+58h]; CriticalSection
0x14000c509  call    cs:__imp_RtlDeleteCriticalSection
0x14000c50f  mov     rcx, gs:60h
0x14000c518  mov     r8, rbx; P
0x14000c51b  xor     edx, edx; Flags
0x14000c51d  mov     rcx, [rcx+30h]; HeapHandle
0x14000c521  call    cs:__imp_RtlFreeHeap
0x14000c527  mov     rbx, [rsp+28h+arg_8]
0x14000c52c  mov     rsi, [rsp+28h+arg_10]
0x14000c531  add     rsp, 20h
0x14000c535  pop     rdi
0x14000c536  retn
```
