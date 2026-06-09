# PfsDecompressBuffer

- ea: `0x1800236e8`
- end: `0x18002380c`
- name: `PfsDecompressBuffer`
- size: `292`
- prototype: `__int64 __usercall@<rax>(PUCHAR Buffer@<rcx>, __int64)`
- caller_count: `15`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180023e88`
- `0x180031818`
- `0x1800319b8`
- `0x180038d1c`
- `0x18004b918`
- `0x180054330`
- `0x180054874`
- `0x180054960`
- `0x180059ce0`
- `0x18008a24c`
- `0x18008bdf4`
- `0x180092f40`
- `0x18009675c`
- `0x1800a9a3c`
- `0x1800b4988`

## callees

- `0x18002341c`
- `0x1800236e8`
- `0x1800474bc`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180023727`
- `ntdll!NtQueryInformationThread` at `0x180023727`
- `ntdll!NtSetInformationThread` at `0x180023759`
- `ntdll!NtSetInformationThread` at `0x180023759`
- `ntdll!RtlNtStatusToDosError` at `0x1800237cc`
- `ntdll!RtlNtStatusToDosError` at `0x1800237db`
- `ntdll!RtlNtStatusToDosError` at `0x1800237f6`
- `ntdll!RtlNtStatusToDosError` at `0x1800237cc`
- `ntdll!RtlNtStatusToDosError` at `0x1800237db`
- `ntdll!RtlNtStatusToDosError` at `0x1800237f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800236fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023741`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800237ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800236fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023741`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800237ad`

## pseudocode

```c
__int64 __fastcall PfsDecompressBuffer(PUCHAR Buffer, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  HANDLE CurrentThread; // rax
  int v7; // eax
  int v8; // edi
  HANDLE v9; // rax
  int v10; // eax
  NTSTATUS v11; // eax
  ULONG v12; // ebx
  HANDLE v13; // rax
  int ThreadInformation; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16[8]; // [rsp+38h] [rbp-40h] BYREF

  CurrentThread = GetCurrentThread();
  ThreadInformation = 0;
  v7 = NtQueryInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u, 0);
  if ( v7 < 0 )
  {
    v8 = 8;
    RtlNtStatusToDosError(v7);
  }
  else
  {
    v8 = ThreadInformation;
  }
  ThreadInformation = 1;
  v9 = GetCurrentThread();
  v10 = NtSetInformationThread(v9, ThreadPagePriority, &ThreadInformation, 4u);
  if ( v10 < 0 )
    RtlNtStatusToDosError(v10);
  v16[0] = (__int64)PfsCompressAlloc;
  v16[1] = (__int64)PfsCompressFree;
  v11 = SmDecompressBuffer(Buffer, a5, (__int64)v16);
  if ( v11 < 0 )
  {
    if ( v11 == -1073741672 )
    {
      v12 = 605;
    }
    else
    {
      v12 = RtlNtStatusToDosError(v11);
      if ( v12 == 605 )
        v12 = 11;
    }
  }
  else
  {
    v12 = 0;
  }
  if ( v8 != 8 )
  {
    v13 = GetCurrentThread();
    PfSetPagePriorityThread(v13);
  }
  return v12;
}

```

## disassembly

```asm
0x1800236e8  push    rbx
0x1800236ea  push    rbp
0x1800236eb  push    rsi
0x1800236ec  push    rdi
0x1800236ed  push    r14
0x1800236ef  sub     rsp, 50h
0x1800236f3  mov     rbx, r9
0x1800236f6  mov     rsi, r8
0x1800236f9  mov     ebp, edx
0x1800236fb  mov     r14, rcx
0x1800236fe  call    cs:__imp_GetCurrentThread
0x180023704  mov     r9d, 4; ThreadInformationLength
0x18002370a  mov     [rsp+78h+ThreadInformation], 0
0x180023712  lea     r8, [rsp+78h+ThreadInformation]; ThreadInformation
0x180023717  mov     [rsp+78h+ReturnLength], 0; ReturnLength
0x180023720  mov     rcx, rax; ThreadHandle
0x180023723  lea     edx, [r9+14h]; ThreadInformationClass
0x180023727  call    cs:__imp_NtQueryInformationThread
0x18002372d  test    eax, eax
0x18002372f  js      loc_1800237D4
0x180023735  mov     edi, [rsp+78h+ThreadInformation]
0x180023739  mov     [rsp+78h+ThreadInformation], 1
0x180023741  call    cs:__imp_GetCurrentThread
0x180023747  mov     r9d, 4; ThreadInformationLength
0x18002374d  lea     r8, [rsp+78h+ThreadInformation]; ThreadInformation
0x180023752  mov     rcx, rax; ThreadHandle
0x180023755  lea     edx, [r9+14h]; ThreadInformationClass
0x180023759  call    cs:__imp_NtSetInformationThread
0x18002375f  test    eax, eax
0x180023761  js      short loc_1800237CA
0x180023763  lea     rax, PfsCompressAlloc
0x18002376a  mov     r9, rbx
0x18002376d  mov     [rsp+78h+var_40], rax
0x180023772  mov     r8, rsi
0x180023775  lea     rax, PfsCompressFree
0x18002377c  mov     edx, ebp
0x18002377e  mov     [rsp+78h+var_38], rax
0x180023783  mov     rcx, r14; Buffer
0x180023786  lea     rax, [rsp+78h+var_40]
0x18002378b  mov     [rsp+78h+var_50], rax; __int64
0x180023790  mov     rax, [rsp+78h+arg_20]
0x180023798  mov     [rsp+78h+ReturnLength], rax; __int64
0x18002379d  call    SmDecompressBuffer
0x1800237a2  test    eax, eax
0x1800237a4  js      short loc_1800237E6
0x1800237a6  xor     ebx, ebx
0x1800237a8  cmp     edi, 8
0x1800237ab  jz      short loc_1800237BD
0x1800237ad  call    cs:__imp_GetCurrentThread
0x1800237b3  mov     rcx, rax; ThreadHandle
0x1800237b6  mov     edx, edi
0x1800237b8  call    PfSetPagePriorityThread
0x1800237bd  mov     eax, ebx
0x1800237bf  add     rsp, 50h
0x1800237c3  pop     r14
0x1800237c5  pop     rdi
0x1800237c6  pop     rsi
0x1800237c7  pop     rbp
0x1800237c8  pop     rbx
0x1800237c9  retn
0x1800237ca  mov     ecx, eax; Status
0x1800237cc  call    cs:__imp_RtlNtStatusToDosError
0x1800237d2  jmp     short loc_180023763
0x1800237d4  mov     ecx, eax; Status
0x1800237d6  mov     edi, 8
0x1800237db  call    cs:__imp_RtlNtStatusToDosError
0x1800237e1  jmp     loc_180023739
0x1800237e6  cmp     eax, 0C0000098h
0x1800237eb  jnz     short loc_1800237F4
0x1800237ed  mov     ebx, 25Dh
0x1800237f2  jmp     short loc_1800237A8
0x1800237f4  mov     ecx, eax; Status
0x1800237f6  call    cs:__imp_RtlNtStatusToDosError
0x1800237fc  mov     ebx, eax
0x1800237fe  cmp     eax, 25Dh
0x180023803  jnz     short loc_1800237A8
0x180023805  mov     ebx, 0Bh
0x18002380a  jmp     short loc_1800237A8
```
