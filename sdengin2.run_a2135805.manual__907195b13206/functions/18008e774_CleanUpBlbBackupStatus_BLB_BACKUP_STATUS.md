# CleanUpBlbBackupStatus(_BLB_BACKUP_STATUS *)

- ea: `0x18008e774`
- end: `0x18008e972`
- name: `?CleanUpBlbBackupStatus@@YAXPEAU_BLB_BACKUP_STATUS@@@Z`
- size: `510`
- prototype: `void __fastcall(struct _BLB_BACKUP_STATUS *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180044bfc`

## callees

- `0x18008e774`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18008e795`
- `ole32!CoTaskMemFree` at `0x18008e7a9`
- `ole32!CoTaskMemFree` at `0x18008e7bd`
- `ole32!CoTaskMemFree` at `0x18008e7d1`
- `ole32!CoTaskMemFree` at `0x18008e7f5`
- `ole32!CoTaskMemFree` at `0x18008e812`
- `ole32!CoTaskMemFree` at `0x18008e842`
- `ole32!CoTaskMemFree` at `0x18008e858`
- `ole32!CoTaskMemFree` at `0x18008e86e`
- `ole32!CoTaskMemFree` at `0x18008e8ba`
- `ole32!CoTaskMemFree` at `0x18008e8eb`
- `ole32!CoTaskMemFree` at `0x18008e8ff`
- `ole32!CoTaskMemFree` at `0x18008e91b`
- `ole32!CoTaskMemFree` at `0x18008e93d`
- `ole32!CoTaskMemFree` at `0x18008e795`
- `ole32!CoTaskMemFree` at `0x18008e7a9`
- `ole32!CoTaskMemFree` at `0x18008e7bd`
- `ole32!CoTaskMemFree` at `0x18008e7d1`
- `ole32!CoTaskMemFree` at `0x18008e7f5`
- `ole32!CoTaskMemFree` at `0x18008e812`
- `ole32!CoTaskMemFree` at `0x18008e842`
- `ole32!CoTaskMemFree` at `0x18008e858`
- `ole32!CoTaskMemFree` at `0x18008e86e`
- `ole32!CoTaskMemFree` at `0x18008e8ba`
- `ole32!CoTaskMemFree` at `0x18008e8eb`
- `ole32!CoTaskMemFree` at `0x18008e8ff`
- `ole32!CoTaskMemFree` at `0x18008e91b`
- `ole32!CoTaskMemFree` at `0x18008e93d`

## pseudocode

```c
void __fastcall CleanUpBlbBackupStatus(LPVOID *a1)
{
  LPVOID *v1; // rsi
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  LPVOID *v5; // rbx
  unsigned int i; // edi
  unsigned int j; // ebp
  _QWORD *v8; // rbx
  __int64 v9; // rdi
  void *v10; // rcx
  void *v11; // rcx
  LPVOID v12; // rdx
  unsigned int v13; // ebp
  __int64 v14; // rdi
  LPVOID *v15; // rbx
  unsigned int k; // r14d
  __int64 v17; // r15
  void *v18; // rcx
  __int64 v19; // rax

  if ( a1 )
  {
    v1 = a1;
    CoTaskMemFree(a1[7]);
    v2 = v1[6];
    v1[7] = 0;
    CoTaskMemFree(v2);
    v3 = v1[10];
    v1[6] = 0;
    CoTaskMemFree(v3);
    v4 = v1[2];
    v1[10] = 0;
    CoTaskMemFree(v4);
    v5 = v1 + 8;
    v1[2] = 0;
    for ( i = 0; i < *((_DWORD *)v1 + 11); *((_QWORD *)*v5 + 8) = 0 )
    {
      CoTaskMemFree(*((LPVOID *)*v5 + 8));
      ++i;
    }
    CoTaskMemFree(*v5);
    *v5 = 0;
    if ( v1[12] )
    {
      for ( j = 0; j < *((_DWORD *)v1 + 22); v8[v9 + 7] = 0 )
      {
        v8 = v1[12];
        v9 = 10LL * j;
        CoTaskMemFree((LPVOID)v8[10 * j + 4]);
        v10 = (void *)v8[10 * j + 5];
        v8[10 * j + 4] = 0;
        CoTaskMemFree(v10);
        v11 = (void *)v8[10 * j + 7];
        v8[10 * j + 5] = 0;
        CoTaskMemFree(v11);
        ++j;
      }
    }
    v12 = v1[14];
    if ( v12 && *((_QWORD *)v12 + 10) )
    {
      if ( *((_DWORD *)v12 + 14) )
      {
        v13 = 0;
        do
        {
          v14 = *((_QWORD *)v12 + 10) + 88LL * v13;
          if ( v14 )
          {
            CoTaskMemFree(*(LPVOID *)(v14 + 64));
            v15 = (LPVOID *)(v14 + 80);
            *(_QWORD *)(v14 + 64) = 0;
            for ( k = 0; k < *(_DWORD *)(v14 + 72); ++k )
            {
              v17 = (__int64)*v15 + 144 * k;
              if ( v17 )
              {
                CoTaskMemFree(*(LPVOID *)(v17 + 112));
                v18 = *(void **)(v17 + 120);
                *(_QWORD *)(v17 + 112) = 0;
                CoTaskMemFree(v18);
                *(_QWORD *)(v17 + 120) = 0;
              }
            }
            CoTaskMemFree(*v15);
            *v15 = 0;
          }
          v12 = v1[14];
          ++v13;
        }
        while ( v13 < *((_DWORD *)v12 + 14) );
      }
      CoTaskMemFree(*((LPVOID *)v12 + 10));
      *((_QWORD *)v1[14] + 10) = 0;
    }
    v19 = 168;
    do
    {
      *(_BYTE *)v1 = 0;
      v1 = (LPVOID *)((char *)v1 + 1);
      --v19;
    }
    while ( v19 );
  }
}

```

## disassembly

```asm
0x18008e774  test    rcx, rcx
0x18008e777  jz      locret_18008E970
0x18008e77d  push    rbx
0x18008e77e  push    rbp
0x18008e77f  push    rsi
0x18008e780  push    rdi
0x18008e781  push    r12
0x18008e783  push    r14
0x18008e785  push    r15
0x18008e787  sub     rsp, 20h
0x18008e78b  mov     rsi, rcx
0x18008e78e  xor     r12d, r12d
0x18008e791  mov     rcx, [rcx+38h]; pv
0x18008e795  call    cs:__imp_CoTaskMemFree
0x18008e79c  nop     dword ptr [rax+rax+00h]
0x18008e7a1  mov     rcx, [rsi+30h]; pv
0x18008e7a5  mov     [rsi+38h], r12
0x18008e7a9  call    cs:__imp_CoTaskMemFree
0x18008e7b0  nop     dword ptr [rax+rax+00h]
0x18008e7b5  mov     rcx, [rsi+50h]; pv
0x18008e7b9  mov     [rsi+30h], r12
0x18008e7bd  call    cs:__imp_CoTaskMemFree
0x18008e7c4  nop     dword ptr [rax+rax+00h]
0x18008e7c9  mov     rcx, [rsi+10h]; pv
0x18008e7cd  mov     [rsi+50h], r12
0x18008e7d1  call    cs:__imp_CoTaskMemFree
0x18008e7d8  nop     dword ptr [rax+rax+00h]
0x18008e7dd  lea     rbx, [rsi+40h]
0x18008e7e1  mov     [rsi+10h], r12
0x18008e7e5  mov     edi, r12d
0x18008e7e8  cmp     [rsi+2Ch], r12d
0x18008e7ec  jbe     short loc_18008E80F
0x18008e7ee  mov     rcx, [rbx]
0x18008e7f1  mov     rcx, [rcx+40h]; pv
0x18008e7f5  call    cs:__imp_CoTaskMemFree
0x18008e7fc  nop     dword ptr [rax+rax+00h]
0x18008e801  mov     rax, [rbx]
0x18008e804  inc     edi
0x18008e806  mov     [rax+40h], r12
0x18008e80a  cmp     edi, [rsi+2Ch]
0x18008e80d  jb      short loc_18008E7EE
0x18008e80f  mov     rcx, [rbx]; pv
0x18008e812  call    cs:__imp_CoTaskMemFree
0x18008e819  nop     dword ptr [rax+rax+00h]
0x18008e81e  mov     [rbx], r12
0x18008e821  cmp     [rsi+60h], r12
0x18008e825  jz      short loc_18008E886
0x18008e827  mov     ebp, r12d
0x18008e82a  cmp     [rsi+58h], r12d
0x18008e82e  jbe     short loc_18008E886
0x18008e830  mov     rbx, [rsi+60h]
0x18008e834  mov     eax, ebp
0x18008e836  lea     rdi, [rax+rax*4]
0x18008e83a  add     rdi, rdi
0x18008e83d  mov     rcx, [rbx+rdi*8+20h]; pv
0x18008e842  call    cs:__imp_CoTaskMemFree
0x18008e849  nop     dword ptr [rax+rax+00h]
0x18008e84e  mov     rcx, [rbx+rdi*8+28h]; pv
0x18008e853  mov     [rbx+rdi*8+20h], r12
0x18008e858  call    cs:__imp_CoTaskMemFree
0x18008e85f  nop     dword ptr [rax+rax+00h]
0x18008e864  mov     rcx, [rbx+rdi*8+38h]; pv
0x18008e869  mov     [rbx+rdi*8+28h], r12
0x18008e86e  call    cs:__imp_CoTaskMemFree
0x18008e875  nop     dword ptr [rax+rax+00h]
0x18008e87a  inc     ebp
0x18008e87c  mov     [rbx+rdi*8+38h], r12
0x18008e881  cmp     ebp, [rsi+58h]
0x18008e884  jb      short loc_18008E830
0x18008e886  mov     rdx, [rsi+70h]
0x18008e88a  test    rdx, rdx
0x18008e88d  jz      loc_18008E951
0x18008e893  cmp     [rdx+50h], r12
0x18008e897  jz      loc_18008E951
0x18008e89d  cmp     [rdx+38h], r12d
0x18008e8a1  jbe     loc_18008E939
0x18008e8a7  mov     ebp, r12d
0x18008e8aa  mov     eax, ebp
0x18008e8ac  imul    rdi, rax, 58h ; 'X'
0x18008e8b0  add     rdi, [rdx+50h]
0x18008e8b4  jz      short loc_18008E92A
0x18008e8b6  mov     rcx, [rdi+40h]; pv
0x18008e8ba  call    cs:__imp_CoTaskMemFree
0x18008e8c1  nop     dword ptr [rax+rax+00h]
0x18008e8c6  lea     rbx, [rdi+50h]
0x18008e8ca  mov     [rdi+40h], r12
0x18008e8ce  mov     r14d, r12d
0x18008e8d1  cmp     [rdi+48h], r12d
0x18008e8d5  jbe     short loc_18008E918
0x18008e8d7  mov     eax, r14d
0x18008e8da  lea     r15, [rax+rax*8]
0x18008e8de  shl     r15, 4
0x18008e8e2  add     r15, [rbx]
0x18008e8e5  jz      short loc_18008E90F
0x18008e8e7  mov     rcx, [r15+70h]; pv
0x18008e8eb  call    cs:__imp_CoTaskMemFree
0x18008e8f2  nop     dword ptr [rax+rax+00h]
0x18008e8f7  mov     rcx, [r15+78h]; pv
0x18008e8fb  mov     [r15+70h], r12
0x18008e8ff  call    cs:__imp_CoTaskMemFree
0x18008e906  nop     dword ptr [rax+rax+00h]
0x18008e90b  mov     [r15+78h], r12
0x18008e90f  inc     r14d
0x18008e912  cmp     r14d, [rdi+48h]
0x18008e916  jb      short loc_18008E8D7
0x18008e918  mov     rcx, [rbx]; pv
0x18008e91b  call    cs:__imp_CoTaskMemFree
0x18008e922  nop     dword ptr [rax+rax+00h]
0x18008e927  mov     [rbx], r12
0x18008e92a  mov     rdx, [rsi+70h]
0x18008e92e  inc     ebp
0x18008e930  cmp     ebp, [rdx+38h]
0x18008e933  jb      loc_18008E8AA
0x18008e939  mov     rcx, [rdx+50h]; pv
0x18008e93d  call    cs:__imp_CoTaskMemFree
0x18008e944  nop     dword ptr [rax+rax+00h]
0x18008e949  mov     rax, [rsi+70h]
0x18008e94d  mov     [rax+50h], r12
0x18008e951  mov     eax, 0A8h
0x18008e956  mov     [rsi], r12b
0x18008e959  inc     rsi
0x18008e95c  sub     rax, 1
0x18008e960  jnz     short loc_18008E956
0x18008e962  add     rsp, 20h
0x18008e966  pop     r15
0x18008e968  pop     r14
0x18008e96a  pop     r12
0x18008e96c  pop     rdi
0x18008e96d  pop     rsi
0x18008e96e  pop     rbp
0x18008e96f  pop     rbx
0x18008e970  retn
```
