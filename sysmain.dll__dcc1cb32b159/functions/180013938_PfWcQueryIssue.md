# PfWcQueryIssue

- ea: `0x180013938`
- end: `0x180013d9a`
- name: `PfWcQueryIssue`
- size: `1122`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180013410`
- `0x180013728`
- `0x18001437c`

## callees

- `0x18000c000`
- `0x18000ee28`
- `0x180013938`
- `0x180013ee0`
- `0x180014320`
- `0x18002341c`
- `0x180027c64`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x1800139f4`
- `ntdll!NtQueryInformationThread` at `0x1800139f4`
- `ntdll!RtlNtStatusToDosError` at `0x180013bba`
- `ntdll!RtlNtStatusToDosError` at `0x180013d54`
- `ntdll!RtlNtStatusToDosError` at `0x180013bba`
- `ntdll!RtlNtStatusToDosError` at `0x180013d54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013adf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013adf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800139ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800139c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800139d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013a06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013a2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013a4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013aea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013b01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800139ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800139c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800139d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013a06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013a2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013a4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013aea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013b01`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800139b6`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800139b6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800139cf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180013a3a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180013af5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800139cf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180013a3a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180013af5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180013cf4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180013cf4`

## pseudocode

```c
__int64 __fastcall PfWcQueryIssue(__int64 a1, __int64 a2, void *a3)
{
  unsigned int v3; // ebx
  HANDLE v4; // r12
  int v7; // r13d
  unsigned int *v9; // rdi
  HANDLE CurrentThread; // rax
  int ThreadPriority; // esi
  HANDLE v12; // rax
  HANDLE v13; // rax
  int v14; // eax
  HANDLE v15; // rax
  NTSTATUS v16; // eax
  HANDLE v17; // rax
  HANDLE v18; // rax
  int v19; // r10d
  unsigned __int64 v20; // rsi
  __int64 v21; // r9
  __int64 v22; // r8
  __int64 v23; // rcx
  DWORD LastError; // ebx
  HANDLE v25; // rax
  HANDLE v26; // rax
  unsigned int j; // eax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  unsigned __int64 v33; // rcx
  unsigned int i; // edx
  __int64 v35; // rcx
  __int128 v37; // [rsp+48h] [rbp-21h] BYREF
  __int64 v38; // [rsp+58h] [rbp-11h]
  __int128 v39; // [rsp+60h] [rbp-9h] BYREF
  __int128 v40; // [rsp+70h] [rbp+7h]
  int nPriority; // [rsp+D0h] [rbp+67h]
  unsigned int ThreadInformation; // [rsp+D8h] [rbp+6Fh] BYREF
  int v43; // [rsp+E0h] [rbp+77h] BYREF
  unsigned __int8 *v44; // [rsp+E8h] [rbp+7Fh] BYREF

  v3 = 0;
  v44 = 0;
  v43 = 0;
  v4 = a3;
  v7 = 8;
  v39 = 0;
  v40 = 0;
  if ( !a3 )
  {
    v4 = OpenProcess(0x1000u, 0, *(_DWORD *)(a2 + 20));
    if ( !v4 )
    {
      LastError = GetLastError();
      if ( LastError != 87 )
        goto LABEL_23;
      v3 = 0;
      nPriority = 32;
      v9 = (unsigned int *)(a2 + 112);
      for ( i = 0; i < *v9; *(_QWORD *)(v35 + *(_QWORD *)(a2 + 104) + 8) |= 1uLL )
      {
        v35 = i++;
        v35 *= 16;
        *(_QWORD *)(v35 + *(_QWORD *)(a2 + 104) + 8) = 0;
      }
      goto LABEL_9;
    }
  }
  v9 = (unsigned int *)(a2 + 112);
  *((_QWORD *)&v39 + 1) = *(_QWORD *)(a2 + 104);
  *(_QWORD *)&v40 = 16LL * *(unsigned int *)(a2 + 112);
  LODWORD(v39) = 0;
  *((_QWORD *)&v40 + 1) = v4;
  DWORD1(v39) = 2 - (a3 != 0);
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  nPriority = ThreadPriority;
  v12 = GetCurrentThread();
  SetThreadPriority(v12, 15);
  v13 = GetCurrentThread();
  ThreadInformation = 0;
  v14 = NtQueryInformationThread(v13, ThreadPagePriority, &ThreadInformation, 4u, 0);
  if ( v14 < 0 )
    RtlNtStatusToDosError(v14);
  else
    v7 = ThreadInformation;
  v15 = GetCurrentThread();
  PfSetPagePriorityThread(v15);
  v16 = PfsVirtualQuery(&v39);
  if ( v16 >= 0 )
  {
    if ( ThreadPriority != 32 )
    {
      v17 = GetCurrentThread();
      SetThreadPriority(v17, ThreadPriority);
      nPriority = 32;
    }
    if ( v7 != 8 )
    {
      v18 = GetCurrentThread();
      PfSetPagePriorityThread(v18);
      v7 = 8;
    }
LABEL_9:
    v19 = a1 + 8840;
    v37 = 0;
    LODWORD(v37) = 1;
    v38 = 1;
    v20 = 17;
    if ( !a3 )
    {
      if ( *v9 )
      {
        do
        {
          v21 = *(_QWORD *)(a2 + 104);
          v22 = 16LL * v3;
          v23 = *(_QWORD *)(v22 + v21 + 8);
          if ( (v23 & 1) != 0 || (v23 & 0x200000) == 0 && (v23 & 0xC00000) != 0x800000 )
          {
            if ( (*(_QWORD *)(v22 + v21 + 8) & 1LL) != 0 || (ThreadInformation = 3, (v23 & 0xC00000) != 0) )
              ThreadInformation = 1;
            v20 ^= (*(_QWORD *)(v22 + v21) ^ v20) & 0xFFFFFFFFFFFFF000uLL;
            if ( !(unsigned int)BtDbBreakupRange(v19, (int)a2 + 56, v20 >> 12, 0, 1, (__int64)&v43, (__int64)&v44) )
              v44 = (unsigned __int8 *)PfWcRangeRemove(a1, a2, v44, ThreadInformation);
            v19 = a1 + 8840;
          }
          ++v3;
        }
        while ( v3 < *v9 );
      }
LABEL_14:
      LastError = 0;
LABEL_15:
      ThreadPriority = nPriority;
      goto LABEL_16;
    }
    for ( j = 0; ; j = ThreadInformation + 1 )
    {
      ThreadInformation = j;
      if ( j >= *v9 )
        goto LABEL_14;
      v29 = *(_QWORD *)(a2 + 104);
      v30 = 2LL * j;
      v31 = *(_QWORD *)(v29 + 16LL * j + 8);
      if ( (v31 & 1) == 0 && (v31 & 0xC00000) == 0x800000 )
        break;
LABEL_34:
      ;
    }
    v20 = *(_QWORD *)(v29 + 8 * v30) & 0xFFFFFFFFFFFFF000uLL | v20 & 0xFFF;
    *(_QWORD *)&v37 = v20;
    LastError = BtDbBreakupRange(v19, (int)a2 + 56, v20 >> 12, 0, 1, (__int64)&v43, (__int64)&v44);
    if ( LastError )
      goto LABEL_15;
    v32 = (__int64)v44;
    if ( v44 )
    {
      v33 = *v44;
      if ( (v33 & 0x70) != 0 )
      {
        *(_QWORD *)(a1 + 4496) += (v33 >> 4) & 7;
LABEL_43:
        v19 = a1 + 8840;
        goto LABEL_34;
      }
    }
    else
    {
      v32 = PfPdRangeCreateAndRecordAccess(a1, (int)a2 + 56, (unsigned int)&v37, 3, 1);
      v44 = (unsigned __int8 *)v32;
      if ( !v32 )
      {
LABEL_53:
        LastError = 8;
        goto LABEL_15;
      }
      LOWORD(v20) = v37;
      LastError = 1;
    }
    if ( !PfWcRangeAdd(a1, a2 + 56, v32, 0) )
      goto LABEL_53;
    if ( !LastError )
      --*(_QWORD *)(a1 + 128);
    if ( *(_DWORD *)(a1 + 16676) >= *(_DWORD *)(a1 + 16672) )
    {
      LastError = 112;
      goto LABEL_15;
    }
    goto LABEL_43;
  }
  LastError = RtlNtStatusToDosError(v16);
LABEL_16:
  if ( v4 && !a3 )
    CloseHandle(v4);
  if ( ThreadPriority != 32 )
  {
    v25 = GetCurrentThread();
    SetThreadPriority(v25, ThreadPriority);
  }
  if ( v7 != 8 )
  {
    v26 = GetCurrentThread();
    PfSetPagePriorityThread(v26);
  }
LABEL_23:
  *(_DWORD *)(a2 + 112) = 0;
  return LastError;
}

```

## disassembly

```asm
0x180013938  push    rbp
0x18001393a  push    rbx
0x18001393b  push    rsi
0x18001393c  push    rdi
0x18001393d  push    r12
0x18001393f  push    r13
0x180013941  push    r14
0x180013943  push    r15
0x180013945  lea     rbp, [rsp-1Fh]
0x18001394a  sub     rsp, 88h
0x180013951  xor     ebx, ebx
0x180013953  mov     [rbp+57h+var_80], r8
0x180013957  mov     [rbp+57h+arg_18], rbx
0x18001395b  xorps   xmm0, xmm0
0x18001395e  mov     [rbp+57h+arg_10], ebx
0x180013961  mov     r12, r8
0x180013964  mov     r14, rdx
0x180013967  mov     r15, rcx
0x18001396a  lea     r13d, [rbx+8]
0x18001396e  mov     rsi, r8
0x180013971  movups  [rbp+57h+var_60], xmm0
0x180013975  movups  [rbp+57h+var_50], xmm0
0x180013979  test    r8, r8
0x18001397c  jz      loc_180013CE9
0x180013982  mov     rax, [r14+68h]
0x180013986  lea     rdi, [r14+70h]
0x18001398a  mov     qword ptr [rbp+57h+var_60+8], rax
0x18001398e  mov     eax, [rdi]
0x180013990  shl     rax, 4
0x180013994  mov     qword ptr [rbp+57h+var_50], rax
0x180013998  mov     rax, rsi
0x18001399b  neg     rax
0x18001399e  mov     dword ptr [rbp+57h+var_60], ebx
0x1800139a1  mov     qword ptr [rbp+57h+var_50+8], r12
0x1800139a5  sbb     ecx, ecx
0x1800139a7  add     ecx, 2
0x1800139aa  mov     dword ptr [rbp+57h+var_60+4], ecx
0x1800139ad  call    cs:__imp_GetCurrentThread
0x1800139b3  mov     rcx, rax; hThread
0x1800139b6  call    cs:__imp_GetThreadPriority
0x1800139bc  mov     esi, eax
0x1800139be  mov     [rbp+57h+nPriority], eax
0x1800139c1  call    cs:__imp_GetCurrentThread
0x1800139c7  mov     rcx, rax; hThread
0x1800139ca  mov     edx, 0Fh; nPriority
0x1800139cf  call    cs:__imp_SetThreadPriority
0x1800139d5  call    cs:__imp_GetCurrentThread
0x1800139db  mov     r9d, 4; ThreadInformationLength
0x1800139e1  mov     [rbp+57h+ThreadInformation], ebx
0x1800139e4  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x1800139e8  mov     [rsp+0C0h+ReturnLength], rbx; ReturnLength
0x1800139ed  mov     rcx, rax; ThreadHandle
0x1800139f0  lea     edx, [r9+14h]; ThreadInformationClass
0x1800139f4  call    cs:__imp_NtQueryInformationThread
0x1800139fa  test    eax, eax
0x1800139fc  js      loc_180013BB8
0x180013a02  mov     r13d, [rbp+57h+ThreadInformation]
0x180013a06  call    cs:__imp_GetCurrentThread
0x180013a0c  mov     rcx, rax; ThreadHandle
0x180013a0f  mov     edx, 1
0x180013a14  call    PfSetPagePriorityThread
0x180013a19  lea     rcx, [rbp+57h+var_60]
0x180013a1d  call    PfsVirtualQuery
0x180013a22  test    eax, eax
0x180013a24  js      loc_180013D52
0x180013a2a  cmp     esi, 20h ; ' '
0x180013a2d  jz      short loc_180013A47
0x180013a2f  call    cs:__imp_GetCurrentThread
0x180013a35  mov     rcx, rax; hThread
0x180013a38  mov     edx, esi; nPriority
0x180013a3a  call    cs:__imp_SetThreadPriority
0x180013a40  mov     [rbp+57h+nPriority], 20h ; ' '
0x180013a47  cmp     r13d, 8
0x180013a4b  jz      short loc_180013A64
0x180013a4d  call    cs:__imp_GetCurrentThread
0x180013a53  mov     rcx, rax; ThreadHandle
0x180013a56  mov     edx, r13d
0x180013a59  call    PfSetPagePriorityThread
0x180013a5e  mov     r13d, 8
0x180013a64  xor     eax, eax
0x180013a66  lea     r10, [r15+2288h]
0x180013a6d  xorps   xmm0, xmm0
0x180013a70  mov     [rbp+57h+var_68], rax
0x180013a74  movups  [rbp+57h+var_78], xmm0
0x180013a78  mov     dword ptr [rbp+57h+var_78], 1
0x180013a7f  mov     rsi, qword ptr [rbp+57h+var_78]
0x180013a83  and     esi, 0FE7h
0x180013a89  mov     dword ptr [rbp+57h+var_68], 1
0x180013a90  or      rsi, 10h
0x180013a94  cmp     [rbp+57h+var_80], rbx
0x180013a98  jnz     loc_180013BC5
0x180013a9e  cmp     [rdi], eax
0x180013aa0  jbe     short loc_180013ACB
0x180013aa2  mov     r9, [r14+68h]
0x180013aa6  mov     r8d, ebx
0x180013aa9  shl     r8, 4
0x180013aad  mov     rcx, [r8+r9+8]
0x180013ab2  mov     rdx, rcx
0x180013ab5  and     edx, 1
0x180013ab8  jnz     loc_180013B40
0x180013abe  bt      rcx, 15h
0x180013ac3  jnb     short loc_180013B30
0x180013ac5  inc     ebx
0x180013ac7  cmp     ebx, [rdi]
0x180013ac9  jb      short loc_180013AA2
0x180013acb  xor     ebx, ebx
0x180013acd  mov     esi, [rbp+57h+nPriority]
0x180013ad0  test    r12, r12
0x180013ad3  jz      short loc_180013AE5
0x180013ad5  cmp     [rbp+57h+var_80], 0
0x180013ada  jnz     short loc_180013AE5
0x180013adc  mov     rcx, r12; hObject
0x180013adf  call    cs:__imp_CloseHandle
0x180013ae5  cmp     esi, 20h ; ' '
0x180013ae8  jz      short loc_180013AFB
0x180013aea  call    cs:__imp_GetCurrentThread
0x180013af0  mov     rcx, rax; hThread
0x180013af3  mov     edx, esi; nPriority
0x180013af5  call    cs:__imp_SetThreadPriority
0x180013afb  cmp     r13d, 8
0x180013aff  jz      short loc_180013B12
0x180013b01  call    cs:__imp_GetCurrentThread
0x180013b07  mov     rcx, rax; ThreadHandle
0x180013b0a  mov     edx, r13d
0x180013b0d  call    PfSetPagePriorityThread
0x180013b12  mov     dword ptr [r14+70h], 0
0x180013b1a  mov     eax, ebx
0x180013b1c  add     rsp, 88h
0x180013b23  pop     r15
0x180013b25  pop     r14
0x180013b27  pop     r13
0x180013b29  pop     r12
0x180013b2b  pop     rdi
0x180013b2c  pop     rsi
0x180013b2d  pop     rbx
0x180013b2e  pop     rbp
0x180013b2f  retn
0x180013b30  mov     rax, rcx
0x180013b33  and     eax, 0C00000h
0x180013b38  cmp     rax, 800000h
0x180013b3e  jz      short loc_180013AC5
0x180013b40  mov     rax, rsi
0x180013b43  test    rdx, rdx
0x180013b46  jz      loc_180013D81
0x180013b4c  mov     [rbp+57h+ThreadInformation], 1
0x180013b53  xor     rsi, [r8+r9]
0x180013b57  lea     rdx, [r14+38h]
0x180013b5b  and     rsi, 0FFFFFFFFFFFFF000h
0x180013b62  xor     r9d, r9d
0x180013b65  xor     rsi, rax
0x180013b68  mov     rcx, r10
0x180013b6b  lea     rax, [rbp+57h+arg_18]
0x180013b6f  mov     r8, rsi
0x180013b72  mov     [rsp+0C0h+var_90], rax
0x180013b77  lea     rax, [rbp+57h+arg_10]
0x180013b7b  mov     [rsp+0C0h+var_98], rax
0x180013b80  shr     r8, 0Ch
0x180013b84  mov     dword ptr [rsp+0C0h+ReturnLength], 1
0x180013b8c  call    BtDbBreakupRange
0x180013b91  test    eax, eax
0x180013b93  jnz     short loc_180013BAC
0x180013b95  mov     r9d, [rbp+57h+ThreadInformation]
0x180013b99  mov     rdx, r14
0x180013b9c  mov     r8, [rbp+57h+arg_18]
0x180013ba0  mov     rcx, r15
0x180013ba3  call    PfWcRangeRemove
0x180013ba8  mov     [rbp+57h+arg_18], rax
0x180013bac  lea     r10, [r15+2288h]
0x180013bb3  jmp     loc_180013AC5
0x180013bb8  mov     ecx, eax; Status
0x180013bba  call    cs:__imp_RtlNtStatusToDosError
0x180013bc0  jmp     loc_180013A06
0x180013bc5  mov     eax, ebx
0x180013bc7  mov     [rbp+57h+ThreadInformation], eax
0x180013bca  cmp     eax, [rdi]
0x180013bcc  jnb     loc_180013ACB
0x180013bd2  mov     rdx, [r14+68h]
0x180013bd6  mov     ecx, eax
0x180013bd8  add     rcx, rcx
0x180013bdb  mov     rax, [rdx+rcx*8+8]
0x180013be0  test    al, 1
0x180013be2  jz      short loc_180013BEB
0x180013be4  mov     eax, [rbp+57h+ThreadInformation]
0x180013be7  inc     eax
0x180013be9  jmp     short loc_180013BC7
0x180013beb  and     eax, 0C00000h
0x180013bf0  cmp     rax, 800000h
0x180013bf6  jnz     short loc_180013BE4
0x180013bf8  mov     rax, [rdx+rcx*8]
0x180013bfc  and     esi, 0FFFh
0x180013c02  and     rax, 0FFFFFFFFFFFFF000h
0x180013c08  lea     rcx, [rbp+57h+arg_18]
0x180013c0c  mov     [rsp+0C0h+var_90], rcx
0x180013c11  lea     rdx, [r14+38h]
0x180013c15  or      rsi, rax
0x180013c18  lea     rcx, [rbp+57h+arg_10]
0x180013c1c  mov     [rsp+0C0h+var_98], rcx
0x180013c21  mov     r8, rsi
0x180013c24  shr     r8, 0Ch
0x180013c28  xor     r9d, r9d
0x180013c2b  mov     rcx, r10
0x180013c2e  mov     qword ptr [rbp+57h+var_78], rsi
0x180013c32  mov     dword ptr [rsp+0C0h+ReturnLength], 1
0x180013c3a  call    BtDbBreakupRange
0x180013c3f  mov     ebx, eax
0x180013c41  test    eax, eax
0x180013c43  jnz     loc_180013ACD
0x180013c49  mov     rax, [rbp+57h+arg_18]
0x180013c4d  test    rax, rax
0x180013c50  jz      short loc_180013CB0
0x180013c52  movzx   ecx, byte ptr [rax]
0x180013c55  test    cl, 70h
0x180013c58  jnz     short loc_180013C9D
0x180013c5a  xor     r9d, r9d
0x180013c5d  lea     rdx, [r14+38h]
0x180013c61  mov     r8, rax
0x180013c64  mov     rcx, r15
0x180013c67  call    PfWcRangeAdd
0x180013c6c  test    rax, rax
0x180013c6f  jz      loc_180013D6D
0x180013c75  test    ebx, ebx
0x180013c77  jz      loc_180013D61
0x180013c7d  mov     eax, [r15+4120h]
0x180013c84  cmp     [r15+4124h], eax
0x180013c8b  jnb     loc_180013D77
0x180013c91  lea     r10, [r15+2288h]
0x180013c98  jmp     loc_180013BE4
0x180013c9d  mov     rax, rcx
0x180013ca0  shr     rax, 4
0x180013ca4  and     eax, 7
0x180013ca7  add     [r15+1190h], rax
0x180013cae  jmp     short loc_180013C91
0x180013cb0  mov     r9d, 3
0x180013cb6  mov     dword ptr [rsp+0C0h+ReturnLength], 1
0x180013cbe  lea     r8, [rbp+57h+var_78]
0x180013cc2  mov     rcx, r15
0x180013cc5  lea     rdx, [r14+38h]
0x180013cc9  call    PfPdRangeCreateAndRecordAccess
0x180013cce  mov     [rbp+57h+arg_18], rax
0x180013cd2  test    rax, rax
0x180013cd5  jz      loc_180013D6D
0x180013cdb  mov     rsi, qword ptr [rbp+57h+var_78]
0x180013cdf  mov     ebx, 1
0x180013ce4  jmp     loc_180013C5A
0x180013ce9  mov     r8d, [rdx+14h]; dwProcessId
0x180013ced  mov     ecx, 1000h; dwDesiredAccess
0x180013cf2  xor     edx, edx; bInheritHandle
0x180013cf4  call    cs:__imp_OpenProcess
0x180013cfa  mov     r12, rax
0x180013cfd  test    rax, rax
0x180013d00  jnz     loc_180013982
0x180013d06  call    cs:__imp_GetLastError
0x180013d0c  mov     ebx, eax
0x180013d0e  cmp     eax, 57h ; 'W'
0x180013d11  jnz     loc_180013B12
0x180013d17  xor     ebx, ebx
0x180013d19  mov     [rbp+57h+nPriority], 20h ; ' '
0x180013d20  lea     rdi, [r14+70h]
0x180013d24  mov     edx, ebx
0x180013d26  cmp     [rdi], ebx
0x180013d28  jbe     loc_180013A64
0x180013d2e  mov     rax, [r14+68h]
0x180013d32  mov     ecx, edx
0x180013d34  inc     edx
0x180013d36  shl     rcx, 4
0x180013d3a  mov     [rcx+rax+8], rbx
0x180013d3f  mov     rax, [r14+68h]
0x180013d43  or      qword ptr [rcx+rax+8], 1
0x180013d49  cmp     edx, [rdi]
0x180013d4b  jb      short loc_180013D2E
0x180013d4d  jmp     loc_180013A64
0x180013d52  mov     ecx, eax; Status
0x180013d54  call    cs:__imp_RtlNtStatusToDosError
0x180013d5a  mov     ebx, eax
0x180013d5c  jmp     loc_180013AD0
0x180013d61  dec     qword ptr [r15+80h]
0x180013d68  jmp     loc_180013C7D
0x180013d6d  mov     ebx, 8
0x180013d72  jmp     loc_180013ACD
0x180013d77  mov     ebx, 70h ; 'p'
0x180013d7c  jmp     loc_180013ACD
0x180013d81  mov     [rbp+57h+ThreadInformation], 3
0x180013d88  test    rcx, 0C00000h
0x180013d8f  jz      loc_180013B53
0x180013d95  jmp     loc_180013B4C
```
