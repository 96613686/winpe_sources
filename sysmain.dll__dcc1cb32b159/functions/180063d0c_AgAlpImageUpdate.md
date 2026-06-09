# AgAlpImageUpdate

- ea: `0x180063d0c`
- end: `0x180063eb0`
- name: `AgAlpImageUpdate`
- size: `420`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18005ee60`
- `0x1800aca00`

## callees

- `0x18002341c`
- `0x180063d0c`
- `0x180078746`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180063d4b`
- `ntdll!NtQueryInformationThread` at `0x180063d4b`
- `ntdll!RtlNtStatusToDosError` at `0x180063d5a`
- `ntdll!RtlNtStatusToDosError` at `0x180063d5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180063d2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180063d66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180063e89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180063d2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180063d66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180063e89`

## pseudocode

```c
__int64 __fastcall AgAlpImageUpdate(__int64 a1, __int64 a2, __int64 *a3)
{
  HANDLE CurrentThread; // rax
  unsigned int v7; // ebp
  int v8; // eax
  int v9; // esi
  HANDLE v10; // rax
  __int64 result; // rax
  unsigned int v12; // r9d
  __int64 *i; // rdx
  __int64 v14; // rcx
  __int64 v15; // r15
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rcx
  HANDLE v19; // rax
  int ThreadInformation; // [rsp+60h] [rbp+8h] BYREF

  CurrentThread = GetCurrentThread();
  v7 = 0;
  ThreadInformation = 0;
  v8 = NtQueryInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u, 0);
  if ( v8 >= 0 )
  {
    v9 = ThreadInformation;
  }
  else
  {
    v9 = 8;
    RtlNtStatusToDosError(v8);
  }
  v10 = GetCurrentThread();
  PfSetPagePriorityThread(v10);
  result = 0;
  *(_QWORD *)a2 = 0;
  *(_BYTE *)a2 = 5;
  *(_DWORD *)(a2 + 4) = 334168;
  *(_OWORD *)(a2 + 12) = *(_OWORD *)(a1 + 2816);
  *(_OWORD *)(a2 + 28) = *(_OWORD *)(a1 + 2832);
  *(_OWORD *)(a2 + 44) = *(_OWORD *)(a1 + 2848);
  *(_OWORD *)(a2 + 60) = *(_OWORD *)(a1 + 2864);
  *(_OWORD *)(a2 + 76) = *(_OWORD *)(a1 + 2880);
  *(_QWORD *)(a2 + 92) = *(_QWORD *)(a1 + 2896);
  if ( *((_DWORD *)a3 + 3) )
  {
    result = *(unsigned __int16 *)(a1 + 2904);
    *(_WORD *)(a2 + 8) = result;
    v12 = 0;
    for ( i = *(__int64 **)(a1 + 2920); i != (__int64 *)(a1 + 2920); i = (__int64 *)*i )
    {
      result = v12;
      v14 = 6LL * v12++;
      *(_OWORD *)(a2 + 8 * v14 + 304) = *((_OWORD *)i - 1);
      *(_OWORD *)(a2 + 8 * v14 + 320) = *(_OWORD *)i;
      *(_OWORD *)(a2 + 8 * v14 + 336) = *((_OWORD *)i + 1);
    }
  }
  if ( *((_DWORD *)a3 + 2) )
  {
    v15 = *a3;
    do
    {
      v16 = 33944LL * v7;
      v17 = *(unsigned int *)(v15 + 4LL * v7);
      v18 = 5 * v17;
      *(_OWORD *)(a2 + 4 * v18 + 100) = *(_OWORD *)(v16 + a1 + 4600);
      *(_DWORD *)(a2 + 4 * v18 + 116) = *(_DWORD *)(v16 + a1 + 4616);
      result = (__int64)memcpy_0((void *)(a2 + 6448 + 32772 * v17), (const void *)(a1 + v16 + 4640), 0x8004u);
      ++v7;
    }
    while ( v7 < *((_DWORD *)a3 + 2) );
  }
  if ( v9 != 8 )
  {
    v19 = GetCurrentThread();
    return PfSetPagePriorityThread(v19);
  }
  return result;
}

```

## disassembly

```asm
0x180063d0c  mov     [rsp+arg_8], rbx
0x180063d11  mov     [rsp+arg_10], rbp
0x180063d16  push    rsi
0x180063d17  push    rdi
0x180063d18  push    r12
0x180063d1a  push    r14
0x180063d1c  push    r15
0x180063d1e  sub     rsp, 30h
0x180063d22  mov     r14, r8
0x180063d25  mov     rbx, rdx
0x180063d28  mov     rdi, rcx
0x180063d2b  call    cs:__imp_GetCurrentThread
0x180063d31  xor     ebp, ebp
0x180063d33  lea     r8, [rsp+58h+ThreadInformation]; ThreadInformation
0x180063d38  mov     rcx, rax; ThreadHandle
0x180063d3b  mov     [rsp+58h+ThreadInformation], ebp
0x180063d3f  mov     [rsp+58h+ReturnLength], rbp; ReturnLength
0x180063d44  lea     r9d, [rbp+4]; ThreadInformationLength
0x180063d48  lea     edx, [rbp+18h]; ThreadInformationClass
0x180063d4b  call    cs:__imp_NtQueryInformationThread
0x180063d51  test    eax, eax
0x180063d53  jns     short loc_180063D62
0x180063d55  mov     ecx, eax; Status
0x180063d57  lea     esi, [rbp+8]
0x180063d5a  call    cs:__imp_RtlNtStatusToDosError
0x180063d60  jmp     short loc_180063D66
0x180063d62  mov     esi, [rsp+58h+ThreadInformation]
0x180063d66  call    cs:__imp_GetCurrentThread
0x180063d6c  mov     rcx, rax; ThreadHandle
0x180063d6f  mov     edx, 1
0x180063d74  call    PfSetPagePriorityThread
0x180063d79  xor     eax, eax
0x180063d7b  mov     [rbx], rax
0x180063d7e  mov     byte ptr [rbx], 5
0x180063d81  mov     dword ptr [rbx+4], 51958h
0x180063d88  movups  xmm0, xmmword ptr [rdi+0B00h]
0x180063d8f  movups  xmmword ptr [rbx+0Ch], xmm0
0x180063d93  movups  xmm1, xmmword ptr [rdi+0B10h]
0x180063d9a  movups  xmmword ptr [rbx+1Ch], xmm1
0x180063d9e  movups  xmm0, xmmword ptr [rdi+0B20h]
0x180063da5  movups  xmmword ptr [rbx+2Ch], xmm0
0x180063da9  movups  xmm1, xmmword ptr [rdi+0B30h]
0x180063db0  movups  xmmword ptr [rbx+3Ch], xmm1
0x180063db4  movups  xmm0, xmmword ptr [rdi+0B40h]
0x180063dbb  movups  xmmword ptr [rbx+4Ch], xmm0
0x180063dbf  movsd   xmm1, qword ptr [rdi+0B50h]
0x180063dc7  movsd   qword ptr [rbx+5Ch], xmm1
0x180063dcc  cmp     [r14+0Ch], ebp
0x180063dd0  jz      short loc_180063E24
0x180063dd2  movzx   eax, word ptr [rdi+0B58h]
0x180063dd9  lea     r8, [rdi+0B68h]
0x180063de0  mov     [rbx+8], ax
0x180063de4  mov     r9d, ebp
0x180063de7  mov     rdx, [r8]
0x180063dea  jmp     short loc_180063E1F
0x180063dec  movups  xmm0, xmmword ptr [rdx-10h]
0x180063df0  mov     eax, r9d
0x180063df3  lea     rcx, [rax+rax*2]
0x180063df7  add     rcx, rcx
0x180063dfa  inc     r9d
0x180063dfd  movups  xmmword ptr [rbx+rcx*8+130h], xmm0
0x180063e05  movups  xmm1, xmmword ptr [rdx]
0x180063e08  movups  xmmword ptr [rbx+rcx*8+140h], xmm1
0x180063e10  movups  xmm0, xmmword ptr [rdx+10h]
0x180063e14  movups  xmmword ptr [rbx+rcx*8+150h], xmm0
0x180063e1c  mov     rdx, [rdx]
0x180063e1f  cmp     rdx, r8
0x180063e22  jnz     short loc_180063DEC
0x180063e24  cmp     [r14+8], ebp
0x180063e28  jbe     short loc_180063E84
0x180063e2a  mov     r15, [r14]
0x180063e2d  lea     r12, [rbx+1930h]
0x180063e34  mov     eax, ebp
0x180063e36  imul    rdx, rax, 8498h
0x180063e3d  mov     r8d, [r15+rax*4]
0x180063e41  movups  xmm0, xmmword ptr [rdx+rdi+11F8h]
0x180063e49  lea     rcx, [r8+r8*4]
0x180063e4d  movups  xmmword ptr [rbx+rcx*4+64h], xmm0
0x180063e52  mov     eax, [rdx+rdi+1208h]
0x180063e59  add     rdx, 1220h
0x180063e60  mov     [rbx+rcx*4+74h], eax
0x180063e64  add     rdx, rdi; Src
0x180063e67  imul    rcx, r8, 8004h
0x180063e6e  mov     r8d, 8004h; Size
0x180063e74  add     rcx, r12; void *
0x180063e77  call    memcpy_0
0x180063e7c  inc     ebp
0x180063e7e  cmp     ebp, [r14+8]
0x180063e82  jb      short loc_180063E34
0x180063e84  cmp     esi, 8
0x180063e87  jz      short loc_180063E99
0x180063e89  call    cs:__imp_GetCurrentThread
0x180063e8f  mov     rcx, rax; ThreadHandle
0x180063e92  mov     edx, esi
0x180063e94  call    PfSetPagePriorityThread
0x180063e99  mov     rbx, [rsp+58h+arg_8]
0x180063e9e  mov     rbp, [rsp+58h+arg_10]
0x180063ea3  add     rsp, 30h
0x180063ea7  pop     r15
0x180063ea9  pop     r14
0x180063eab  pop     r12
0x180063ead  pop     rdi
0x180063eae  pop     rsi
0x180063eaf  retn
```
