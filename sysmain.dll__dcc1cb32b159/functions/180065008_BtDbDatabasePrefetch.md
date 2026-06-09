# BtDbDatabasePrefetch

- ea: `0x180065008`
- end: `0x180065161`
- name: `BtDbDatabasePrefetch`
- size: `345`
- prototype: `__int64 __fastcall(struct _BTDB_ITERATOR *, struct _PREFETCH_INTERNAL_PARAMS *)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180011090`
- `0x18002afe0`
- `0x18005e4c0`
- `0x180064e5c`

## callees

- `0x180011f34`
- `0x18002341c`
- `0x180052bdc`
- `0x1800531e8`
- `0x180065008`
- `0x180078746`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18006505f`
- `ntdll!NtQueryInformationThread` at `0x18006505f`
- `ntdll!RtlNtStatusToDosError` at `0x18006506b`
- `ntdll!RtlNtStatusToDosError` at `0x18006506b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180065043`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180065077`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006513d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180065043`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180065077`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006513d`

## pseudocode

```c
__int64 __fastcall BtDbDatabasePrefetch(struct _BTDB_ITERATOR *a1, struct _PREFETCH_INTERNAL_PARAMS *a2)
{
  int v2; // r13d
  __int64 v3; // rsi
  unsigned int v4; // r12d
  bool v5; // zf
  struct _BTDB_ITERATOR *v7; // rdi
  int v8; // r14d
  HANDLE CurrentThread; // rax
  int v10; // eax
  HANDLE v11; // rax
  unsigned int v12; // edi
  unsigned int v13; // edi
  char v14; // al
  HANDLE v15; // rax
  _QWORD v17[3]; // [rsp+30h] [rbp-18h] BYREF
  int ThreadInformation; // [rsp+98h] [rbp+50h] BYREF
  unsigned int v20; // [rsp+A0h] [rbp+58h] BYREF
  int v21; // [rsp+A8h] [rbp+60h] BYREF

  v2 = *((_DWORD *)a2 + 1);
  v3 = 0;
  v4 = 0;
  v17[0] = 0;
  v5 = (*((_BYTE *)a2 + 56) & 4) == 0;
  v7 = a1;
  v21 = 0;
  v8 = 8;
  v20 = 0;
  if ( v5 )
  {
    CurrentThread = GetCurrentThread();
    ThreadInformation = 0;
    v10 = NtQueryInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u, 0);
    if ( v10 >= 0 )
      v8 = ThreadInformation;
    else
      RtlNtStatusToDosError(v10);
    v11 = GetCurrentThread();
    PfSetPagePriorityThread(v11);
  }
  if ( *(_DWORD *)a2 == 7 )
  {
    PrefetchParamsResetErrorData(a2);
    *(_OWORD *)((char *)a2 + 8) = 0;
    *(_OWORD *)((char *)a2 + 24) = 0;
    *(_OWORD *)((char *)a2 + 36) = 0;
    while ( !v20 )
    {
      v12 = BtDbDatabasePrefetchPerform(v7, a2, &v20);
      if ( v12 )
        goto LABEL_18;
      if ( (v2 & 4) != 0 )
      {
        v13 = *((_DWORD *)a2 + 12);
        if ( v13 )
        {
          if ( *((_QWORD *)a2 + 9) )
          {
            v14 = PfArrayGrow(v13 + v4 - 1, 8, &v21, v17);
            v3 = v17[0];
            if ( v14 )
            {
              memcpy_0((void *)(v17[0] + 8LL * v4), *((const void **)a2 + 9), 8LL * v13);
              v4 += v13;
            }
          }
        }
      }
      v7 = a1;
    }
    v12 = 0;
  }
  else
  {
    v12 = 87;
  }
LABEL_18:
  if ( (v2 & 4) != 0 )
  {
    PrefetchParamsResetErrorData(a2);
    *((_QWORD *)a2 + 9) = v3;
    *((_DWORD *)a2 + 12) = v4;
  }
  if ( v8 != 8 )
  {
    v15 = GetCurrentThread();
    PfSetPagePriorityThread(v15);
  }
  return v12;
}

```

## disassembly

```asm
0x180065008  mov     [rsp-40h+arg_0], rcx
0x18006500d  push    rbp
0x18006500e  push    rbx
0x18006500f  push    rsi
0x180065010  push    rdi
0x180065011  push    r12
0x180065013  push    r13
0x180065015  push    r14
0x180065017  push    r15
0x180065019  mov     rbp, rsp
0x18006501c  sub     rsp, 48h
0x180065020  mov     r13d, [rdx+4]
0x180065024  xor     esi, esi
0x180065026  xor     r12d, r12d
0x180065029  mov     [rbp+var_18], rsi
0x18006502d  test    byte ptr [rdx+38h], 4
0x180065031  mov     rbx, rdx
0x180065034  mov     rdi, rcx
0x180065037  mov     [rbp+arg_18], esi
0x18006503a  lea     r14d, [rsi+8]
0x18006503e  mov     [rbp+arg_10], esi
0x180065041  jnz     short loc_18006508A
0x180065043  call    cs:__imp_GetCurrentThread
0x180065049  lea     r9d, [rsi+4]; ThreadInformationLength
0x18006504d  mov     [rbp+ThreadInformation], esi
0x180065050  mov     rcx, rax; ThreadHandle
0x180065053  mov     [rsp+48h+ReturnLength], rsi; ReturnLength
0x180065058  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x18006505c  lea     edx, [rsi+18h]; ThreadInformationClass
0x18006505f  call    cs:__imp_NtQueryInformationThread
0x180065065  test    eax, eax
0x180065067  jns     short loc_180065073
0x180065069  mov     ecx, eax; Status
0x18006506b  call    cs:__imp_RtlNtStatusToDosError
0x180065071  jmp     short loc_180065077
0x180065073  mov     r14d, [rbp+ThreadInformation]
0x180065077  call    cs:__imp_GetCurrentThread
0x18006507d  mov     rcx, rax; ThreadHandle
0x180065080  mov     edx, 1
0x180065085  call    PfSetPagePriorityThread
0x18006508a  cmp     dword ptr [rbx], 7
0x18006508d  jz      short loc_180065099
0x18006508f  mov     edi, 57h ; 'W'
0x180065094  jmp     loc_180065121
0x180065099  mov     rcx, rbx
0x18006509c  call    PrefetchParamsResetErrorData
0x1800650a1  xorps   xmm0, xmm0
0x1800650a4  movups  xmmword ptr [rbx+8], xmm0
0x1800650a8  movups  xmmword ptr [rbx+18h], xmm0
0x1800650ac  movups  xmmword ptr [rbx+24h], xmm0
0x1800650b0  cmp     [rbp+arg_10], 0
0x1800650b4  jnz     short loc_18006511F
0x1800650b6  lea     r8, [rbp+arg_10]; unsigned int *
0x1800650ba  mov     rdx, rbx; struct _PREFETCH_INTERNAL_PARAMS *
0x1800650bd  mov     rcx, rdi; struct _BTDB_ITERATOR *
0x1800650c0  call    ?BtDbDatabasePrefetchPerform@@YAKPEAU_BTDB_ITERATOR@@PEAU_PREFETCH_INTERNAL_PARAMS@@PEAK@Z; BtDbDatabasePrefetchPerform(_BTDB_ITERATOR *,_PREFETCH_INTERNAL_PARAMS *,ulong *)
0x1800650c5  mov     edi, eax
0x1800650c7  test    eax, eax
0x1800650c9  jnz     short loc_180065121
0x1800650cb  test    r13b, 4
0x1800650cf  jz      short loc_180065119
0x1800650d1  mov     edi, [rbx+30h]
0x1800650d4  test    edi, edi
0x1800650d6  jz      short loc_180065119
0x1800650d8  cmp     qword ptr [rbx+48h], 0
0x1800650dd  jz      short loc_180065119
0x1800650df  lea     r15d, [rdi+r12]
0x1800650e3  lea     ecx, [r15-1]
0x1800650e7  lea     r9, [rbp+var_18]
0x1800650eb  lea     r8, [rbp+arg_18]
0x1800650ef  lea     edx, [rax+8]
0x1800650f2  call    PfArrayGrow
0x1800650f7  mov     rsi, [rbp+var_18]
0x1800650fb  test    al, al
0x1800650fd  jz      short loc_180065119
0x1800650ff  mov     rdx, [rbx+48h]; Src
0x180065103  mov     r8d, edi
0x180065106  mov     eax, r12d
0x180065109  shl     r8, 3; Size
0x18006510d  lea     rcx, [rsi+rax*8]; void *
0x180065111  call    memcpy_0
0x180065116  mov     r12d, r15d
0x180065119  mov     rdi, [rbp+arg_0]
0x18006511d  jmp     short loc_1800650B0
0x18006511f  xor     edi, edi
0x180065121  test    r13b, 4
0x180065125  jz      short loc_180065137
0x180065127  mov     rcx, rbx
0x18006512a  call    PrefetchParamsResetErrorData
0x18006512f  mov     [rbx+48h], rsi
0x180065133  mov     [rbx+30h], r12d
0x180065137  cmp     r14d, 8
0x18006513b  jz      short loc_18006514E
0x18006513d  call    cs:__imp_GetCurrentThread
0x180065143  mov     rcx, rax; ThreadHandle
0x180065146  mov     edx, r14d
0x180065149  call    PfSetPagePriorityThread
0x18006514e  mov     eax, edi
0x180065150  add     rsp, 48h
0x180065154  pop     r15
0x180065156  pop     r14
0x180065158  pop     r13
0x18006515a  pop     r12
0x18006515c  pop     rdi
0x18006515d  pop     rsi
0x18006515e  pop     rbx
0x18006515f  pop     rbp
0x180065160  retn
```
