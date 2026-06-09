# FreeRecoveryStatus(_BLB_RESTORE_SYSTEM_STATE_STATUS &)

- ea: `0x14012e498`
- end: `0x14012e5aa`
- name: `?FreeRecoveryStatus@@YAXAEAU_BLB_RESTORE_SYSTEM_STATE_STATUS@@@Z`
- size: `274`
- prototype: `void __fastcall(struct _BLB_RESTORE_SYSTEM_STATE_STATUS *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140078030`

## callees

- `0x14012e498`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14012e4d3`
- `ole32!CoTaskMemFree` at `0x14012e503`
- `ole32!CoTaskMemFree` at `0x14012e517`
- `ole32!CoTaskMemFree` at `0x14012e52b`
- `ole32!CoTaskMemFree` at `0x14012e549`
- `ole32!CoTaskMemFree` at `0x14012e569`
- `ole32!CoTaskMemFree` at `0x14012e57b`
- `ole32!CoTaskMemFree` at `0x14012e58d`
- `ole32!CoTaskMemFree` at `0x14012e4d3`
- `ole32!CoTaskMemFree` at `0x14012e503`
- `ole32!CoTaskMemFree` at `0x14012e517`
- `ole32!CoTaskMemFree` at `0x14012e52b`
- `ole32!CoTaskMemFree` at `0x14012e549`
- `ole32!CoTaskMemFree` at `0x14012e569`
- `ole32!CoTaskMemFree` at `0x14012e57b`
- `ole32!CoTaskMemFree` at `0x14012e58d`

## pseudocode

```c
void __fastcall FreeRecoveryStatus(struct _BLB_RESTORE_SYSTEM_STATE_STATUS *a1)
{
  __int64 i; // r15
  __int64 v3; // r14
  __int64 v4; // rbp
  int v5; // eax
  unsigned int v6; // r12d
  __int64 v7; // rbx
  __int64 v8; // rdi
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx

  if ( *((_QWORD *)a1 + 15) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 26); *(_QWORD *)(v3 + v4 + 88) = 0 )
    {
      v3 = *((_QWORD *)a1 + 15);
      v4 = 96 * i;
      CoTaskMemFree(*(LPVOID *)(v3 + 96 * i + 72));
      v5 = *(_DWORD *)(v3 + 96 * i + 80);
      *(_QWORD *)(v3 + 96 * i + 72) = 0;
      if ( v5 )
      {
        v6 = 0;
        do
        {
          v7 = *(_QWORD *)(v3 + v4 + 88);
          v8 = 88LL * v6;
          CoTaskMemFree(*(LPVOID *)(v8 + v7 + 64));
          v9 = *(void **)(v8 + v7 + 72);
          *(_QWORD *)(v8 + v7 + 64) = 0;
          CoTaskMemFree(v9);
          v10 = *(void **)(v8 + v7 + 80);
          *(_QWORD *)(v8 + v7 + 72) = 0;
          CoTaskMemFree(v10);
          ++v6;
          *(_QWORD *)(v8 + v7 + 80) = 0;
        }
        while ( v6 < *(_DWORD *)(v3 + v4 + 80) );
      }
      CoTaskMemFree(*(LPVOID *)(v3 + v4 + 88));
      i = (unsigned int)(i + 1);
    }
    CoTaskMemFree(*((LPVOID *)a1 + 15));
    *((_QWORD *)a1 + 15) = 0;
  }
  CoTaskMemFree(*((LPVOID *)a1 + 11));
  v11 = (void *)*((_QWORD *)a1 + 12);
  *((_QWORD *)a1 + 11) = 0;
  CoTaskMemFree(v11);
  *((_QWORD *)a1 + 12) = 0;
}

```

## disassembly

```asm
0x14012e498  push    rbx
0x14012e49a  push    rbp
0x14012e49b  push    rsi
0x14012e49c  push    rdi
0x14012e49d  push    r12
0x14012e49f  push    r14
0x14012e4a1  push    r15
0x14012e4a3  sub     rsp, 20h
0x14012e4a7  cmp     qword ptr [rcx+78h], 0
0x14012e4ac  mov     rsi, rcx
0x14012e4af  jz      loc_14012E577
0x14012e4b5  xor     r15d, r15d
0x14012e4b8  cmp     [rcx+68h], r15d
0x14012e4bc  jbe     loc_14012E565
0x14012e4c2  mov     r14, [rsi+78h]
0x14012e4c6  lea     rbp, [r15+r15*2]
0x14012e4ca  shl     rbp, 5
0x14012e4ce  mov     rcx, [r14+rbp+48h]; pv
0x14012e4d3  call    cs:__imp_CoTaskMemFree
0x14012e4d9  mov     eax, [r14+rbp+50h]
0x14012e4de  mov     qword ptr [r14+rbp+48h], 0
0x14012e4e7  test    eax, eax
0x14012e4e9  jz      short loc_14012E544
0x14012e4eb  xor     r12d, r12d
0x14012e4ee  test    eax, eax
0x14012e4f0  jz      short loc_14012E544
0x14012e4f2  mov     rbx, [r14+rbp+58h]
0x14012e4f7  mov     eax, r12d
0x14012e4fa  imul    rdi, rax, 58h ; 'X'
0x14012e4fe  mov     rcx, [rdi+rbx+40h]; pv
0x14012e503  call    cs:__imp_CoTaskMemFree
0x14012e509  mov     rcx, [rdi+rbx+48h]; pv
0x14012e50e  mov     qword ptr [rdi+rbx+40h], 0
0x14012e517  call    cs:__imp_CoTaskMemFree
0x14012e51d  mov     rcx, [rdi+rbx+50h]; pv
0x14012e522  mov     qword ptr [rdi+rbx+48h], 0
0x14012e52b  call    cs:__imp_CoTaskMemFree
0x14012e531  inc     r12d
0x14012e534  mov     qword ptr [rdi+rbx+50h], 0
0x14012e53d  cmp     r12d, [r14+rbp+50h]
0x14012e542  jb      short loc_14012E4F2
0x14012e544  mov     rcx, [r14+rbp+58h]; pv
0x14012e549  call    cs:__imp_CoTaskMemFree
0x14012e54f  inc     r15d
0x14012e552  mov     qword ptr [r14+rbp+58h], 0
0x14012e55b  cmp     r15d, [rsi+68h]
0x14012e55f  jb      loc_14012E4C2
0x14012e565  mov     rcx, [rsi+78h]; pv
0x14012e569  call    cs:__imp_CoTaskMemFree
0x14012e56f  mov     qword ptr [rsi+78h], 0
0x14012e577  mov     rcx, [rsi+58h]; pv
0x14012e57b  call    cs:__imp_CoTaskMemFree
0x14012e581  mov     rcx, [rsi+60h]; pv
0x14012e585  mov     qword ptr [rsi+58h], 0
0x14012e58d  call    cs:__imp_CoTaskMemFree
0x14012e593  mov     qword ptr [rsi+60h], 0
0x14012e59b  add     rsp, 20h
0x14012e59f  pop     r15
0x14012e5a1  pop     r14
0x14012e5a3  pop     r12
0x14012e5a5  pop     rdi
0x14012e5a6  pop     rsi
0x14012e5a7  pop     rbp
0x14012e5a8  pop     rbx
0x14012e5a9  retn
```
