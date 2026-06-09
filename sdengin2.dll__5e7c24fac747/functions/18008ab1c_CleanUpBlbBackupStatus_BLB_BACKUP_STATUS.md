# CleanUpBlbBackupStatus(_BLB_BACKUP_STATUS *)

- ea: `0x18008ab1c`
- end: `0x18008acbd`
- name: `?CleanUpBlbBackupStatus@@YAXPEAU_BLB_BACKUP_STATUS@@@Z`
- size: `417`
- prototype: `void __fastcall(struct _BLB_BACKUP_STATUS *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180043328`

## callees

- `0x18008ab1c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18008ab3d`
- `ole32!CoTaskMemFree` at `0x18008ab4b`
- `ole32!CoTaskMemFree` at `0x18008ab59`
- `ole32!CoTaskMemFree` at `0x18008ab67`
- `ole32!CoTaskMemFree` at `0x18008ab85`
- `ole32!CoTaskMemFree` at `0x18008ab9c`
- `ole32!CoTaskMemFree` at `0x18008abc6`
- `ole32!CoTaskMemFree` at `0x18008abd6`
- `ole32!CoTaskMemFree` at `0x18008abe6`
- `ole32!CoTaskMemFree` at `0x18008ac28`
- `ole32!CoTaskMemFree` at `0x18008ac53`
- `ole32!CoTaskMemFree` at `0x18008ac61`
- `ole32!CoTaskMemFree` at `0x18008ac77`
- `ole32!CoTaskMemFree` at `0x18008ac8f`
- `ole32!CoTaskMemFree` at `0x18008ab3d`
- `ole32!CoTaskMemFree` at `0x18008ab4b`
- `ole32!CoTaskMemFree` at `0x18008ab59`
- `ole32!CoTaskMemFree` at `0x18008ab67`
- `ole32!CoTaskMemFree` at `0x18008ab85`
- `ole32!CoTaskMemFree` at `0x18008ab9c`
- `ole32!CoTaskMemFree` at `0x18008abc6`
- `ole32!CoTaskMemFree` at `0x18008abd6`
- `ole32!CoTaskMemFree` at `0x18008abe6`
- `ole32!CoTaskMemFree` at `0x18008ac28`
- `ole32!CoTaskMemFree` at `0x18008ac53`
- `ole32!CoTaskMemFree` at `0x18008ac61`
- `ole32!CoTaskMemFree` at `0x18008ac77`
- `ole32!CoTaskMemFree` at `0x18008ac8f`

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
0x18008ab1c  test    rcx, rcx
0x18008ab1f  jz      locret_18008ACBC
0x18008ab25  push    rbx
0x18008ab26  push    rbp
0x18008ab27  push    rsi
0x18008ab28  push    rdi
0x18008ab29  push    r12
0x18008ab2b  push    r14
0x18008ab2d  push    r15
0x18008ab2f  sub     rsp, 20h
0x18008ab33  mov     rsi, rcx
0x18008ab36  xor     r12d, r12d
0x18008ab39  mov     rcx, [rcx+38h]; pv
0x18008ab3d  call    cs:__imp_CoTaskMemFree
0x18008ab43  mov     rcx, [rsi+30h]; pv
0x18008ab47  mov     [rsi+38h], r12
0x18008ab4b  call    cs:__imp_CoTaskMemFree
0x18008ab51  mov     rcx, [rsi+50h]; pv
0x18008ab55  mov     [rsi+30h], r12
0x18008ab59  call    cs:__imp_CoTaskMemFree
0x18008ab5f  mov     rcx, [rsi+10h]; pv
0x18008ab63  mov     [rsi+50h], r12
0x18008ab67  call    cs:__imp_CoTaskMemFree
0x18008ab6d  lea     rbx, [rsi+40h]
0x18008ab71  mov     [rsi+10h], r12
0x18008ab75  mov     edi, r12d
0x18008ab78  cmp     [rsi+2Ch], r12d
0x18008ab7c  jbe     short loc_18008AB99
0x18008ab7e  mov     rcx, [rbx]
0x18008ab81  mov     rcx, [rcx+40h]; pv
0x18008ab85  call    cs:__imp_CoTaskMemFree
0x18008ab8b  mov     rax, [rbx]
0x18008ab8e  inc     edi
0x18008ab90  mov     [rax+40h], r12
0x18008ab94  cmp     edi, [rsi+2Ch]
0x18008ab97  jb      short loc_18008AB7E
0x18008ab99  mov     rcx, [rbx]; pv
0x18008ab9c  call    cs:__imp_CoTaskMemFree
0x18008aba2  mov     [rbx], r12
0x18008aba5  cmp     [rsi+60h], r12
0x18008aba9  jz      short loc_18008ABF8
0x18008abab  mov     ebp, r12d
0x18008abae  cmp     [rsi+58h], r12d
0x18008abb2  jbe     short loc_18008ABF8
0x18008abb4  mov     rbx, [rsi+60h]
0x18008abb8  mov     eax, ebp
0x18008abba  lea     rdi, [rax+rax*4]
0x18008abbe  add     rdi, rdi
0x18008abc1  mov     rcx, [rbx+rdi*8+20h]; pv
0x18008abc6  call    cs:__imp_CoTaskMemFree
0x18008abcc  mov     rcx, [rbx+rdi*8+28h]; pv
0x18008abd1  mov     [rbx+rdi*8+20h], r12
0x18008abd6  call    cs:__imp_CoTaskMemFree
0x18008abdc  mov     rcx, [rbx+rdi*8+38h]; pv
0x18008abe1  mov     [rbx+rdi*8+28h], r12
0x18008abe6  call    cs:__imp_CoTaskMemFree
0x18008abec  inc     ebp
0x18008abee  mov     [rbx+rdi*8+38h], r12
0x18008abf3  cmp     ebp, [rsi+58h]
0x18008abf6  jb      short loc_18008ABB4
0x18008abf8  mov     rdx, [rsi+70h]
0x18008abfc  test    rdx, rdx
0x18008abff  jz      loc_18008AC9D
0x18008ac05  cmp     [rdx+50h], r12
0x18008ac09  jz      loc_18008AC9D
0x18008ac0f  cmp     [rdx+38h], r12d
0x18008ac13  jbe     short loc_18008AC8B
0x18008ac15  mov     ebp, r12d
0x18008ac18  mov     eax, ebp
0x18008ac1a  imul    rdi, rax, 58h ; 'X'
0x18008ac1e  add     rdi, [rdx+50h]
0x18008ac22  jz      short loc_18008AC80
0x18008ac24  mov     rcx, [rdi+40h]; pv
0x18008ac28  call    cs:__imp_CoTaskMemFree
0x18008ac2e  lea     rbx, [rdi+50h]
0x18008ac32  mov     [rdi+40h], r12
0x18008ac36  mov     r14d, r12d
0x18008ac39  cmp     [rdi+48h], r12d
0x18008ac3d  jbe     short loc_18008AC74
0x18008ac3f  mov     eax, r14d
0x18008ac42  lea     r15, [rax+rax*8]
0x18008ac46  shl     r15, 4
0x18008ac4a  add     r15, [rbx]
0x18008ac4d  jz      short loc_18008AC6B
0x18008ac4f  mov     rcx, [r15+70h]; pv
0x18008ac53  call    cs:__imp_CoTaskMemFree
0x18008ac59  mov     rcx, [r15+78h]; pv
0x18008ac5d  mov     [r15+70h], r12
0x18008ac61  call    cs:__imp_CoTaskMemFree
0x18008ac67  mov     [r15+78h], r12
0x18008ac6b  inc     r14d
0x18008ac6e  cmp     r14d, [rdi+48h]
0x18008ac72  jb      short loc_18008AC3F
0x18008ac74  mov     rcx, [rbx]; pv
0x18008ac77  call    cs:__imp_CoTaskMemFree
0x18008ac7d  mov     [rbx], r12
0x18008ac80  mov     rdx, [rsi+70h]
0x18008ac84  inc     ebp
0x18008ac86  cmp     ebp, [rdx+38h]
0x18008ac89  jb      short loc_18008AC18
0x18008ac8b  mov     rcx, [rdx+50h]; pv
0x18008ac8f  call    cs:__imp_CoTaskMemFree
0x18008ac95  mov     rax, [rsi+70h]
0x18008ac99  mov     [rax+50h], r12
0x18008ac9d  mov     eax, 0A8h
0x18008aca2  mov     [rsi], r12b
0x18008aca5  inc     rsi
0x18008aca8  sub     rax, 1
0x18008acac  jnz     short loc_18008ACA2
0x18008acae  add     rsp, 20h
0x18008acb2  pop     r15
0x18008acb4  pop     r14
0x18008acb6  pop     r12
0x18008acb8  pop     rdi
0x18008acb9  pop     rsi
0x18008acba  pop     rbp
0x18008acbb  pop     rbx
0x18008acbc  retn
```
