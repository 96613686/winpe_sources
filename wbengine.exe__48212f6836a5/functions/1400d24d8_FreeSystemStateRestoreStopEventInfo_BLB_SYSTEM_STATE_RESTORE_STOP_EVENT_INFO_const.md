# FreeSystemStateRestoreStopEventInfo(_BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO * const)

- ea: `0x1400d24d8`
- end: `0x1400d265c`
- name: `?FreeSystemStateRestoreStopEventInfo@@YAXQEAU_BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO@@@Z`
- size: `388`
- prototype: `void __fastcall(struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *const)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140077a78`

## callees

- `0x1400d24d8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400d2502`
- `ole32!CoTaskMemFree` at `0x1400d251b`
- `ole32!CoTaskMemFree` at `0x1400d2541`
- `ole32!CoTaskMemFree` at `0x1400d255a`
- `ole32!CoTaskMemFree` at `0x1400d256d`
- `ole32!CoTaskMemFree` at `0x1400d2580`
- `ole32!CoTaskMemFree` at `0x1400d2593`
- `ole32!CoTaskMemFree` at `0x1400d25a6`
- `ole32!CoTaskMemFree` at `0x1400d25b9`
- `ole32!CoTaskMemFree` at `0x1400d25cc`
- `ole32!CoTaskMemFree` at `0x1400d25e2`
- `ole32!CoTaskMemFree` at `0x1400d25fb`
- `ole32!CoTaskMemFree` at `0x1400d2614`
- `ole32!CoTaskMemFree` at `0x1400d262d`
- `ole32!CoTaskMemFree` at `0x1400d2646`
- `ole32!CoTaskMemFree` at `0x1400d2502`
- `ole32!CoTaskMemFree` at `0x1400d251b`
- `ole32!CoTaskMemFree` at `0x1400d2541`
- `ole32!CoTaskMemFree` at `0x1400d255a`
- `ole32!CoTaskMemFree` at `0x1400d256d`
- `ole32!CoTaskMemFree` at `0x1400d2580`
- `ole32!CoTaskMemFree` at `0x1400d2593`
- `ole32!CoTaskMemFree` at `0x1400d25a6`
- `ole32!CoTaskMemFree` at `0x1400d25b9`
- `ole32!CoTaskMemFree` at `0x1400d25cc`
- `ole32!CoTaskMemFree` at `0x1400d25e2`
- `ole32!CoTaskMemFree` at `0x1400d25fb`
- `ole32!CoTaskMemFree` at `0x1400d2614`
- `ole32!CoTaskMemFree` at `0x1400d262d`
- `ole32!CoTaskMemFree` at `0x1400d2646`

## pseudocode

```c
void __fastcall FreeSystemStateRestoreStopEventInfo(struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *const a1)
{
  unsigned int i; // edi
  void *v3; // rcx
  unsigned int j; // edi
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx

  if ( *((_QWORD *)a1 + 7) )
  {
    for ( i = 0; i < *((_DWORD *)a1 + 12); ++i )
    {
      v3 = *(void **)(*((_QWORD *)a1 + 7) + 8LL * i);
      if ( v3 )
      {
        CoTaskMemFree(v3);
        *(_QWORD *)(*((_QWORD *)a1 + 7) + 8LL * i) = 0;
      }
    }
    CoTaskMemFree(*((LPVOID *)a1 + 7));
    *((_QWORD *)a1 + 7) = 0;
  }
  if ( *((_QWORD *)a1 + 9) )
  {
    for ( j = 0; j < *((_DWORD *)a1 + 16); ++j )
    {
      v5 = *(void **)(*((_QWORD *)a1 + 9) + 8LL * j);
      if ( v5 )
      {
        CoTaskMemFree(v5);
        *(_QWORD *)(*((_QWORD *)a1 + 9) + 8LL * j) = 0;
      }
    }
    CoTaskMemFree(*((LPVOID *)a1 + 9));
    *((_QWORD *)a1 + 9) = 0;
  }
  v6 = (void *)*((_QWORD *)a1 + 10);
  if ( v6 )
  {
    CoTaskMemFree(v6);
    *((_QWORD *)a1 + 10) = 0;
  }
  v7 = (void *)*((_QWORD *)a1 + 11);
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *((_QWORD *)a1 + 11) = 0;
  }
  v8 = (void *)*((_QWORD *)a1 + 12);
  if ( v8 )
  {
    CoTaskMemFree(v8);
    *((_QWORD *)a1 + 12) = 0;
  }
  v9 = (void *)*((_QWORD *)a1 + 13);
  if ( v9 )
  {
    CoTaskMemFree(v9);
    *((_QWORD *)a1 + 13) = 0;
  }
  v10 = (void *)*((_QWORD *)a1 + 14);
  if ( v10 )
  {
    CoTaskMemFree(v10);
    *((_QWORD *)a1 + 14) = 0;
  }
  v11 = (void *)*((_QWORD *)a1 + 15);
  if ( v11 )
  {
    CoTaskMemFree(v11);
    *((_QWORD *)a1 + 15) = 0;
  }
  v12 = (void *)*((_QWORD *)a1 + 26);
  if ( v12 )
  {
    CoTaskMemFree(v12);
    *((_QWORD *)a1 + 26) = 0;
  }
  v13 = (void *)*((_QWORD *)a1 + 27);
  if ( v13 )
  {
    CoTaskMemFree(v13);
    *((_QWORD *)a1 + 27) = 0;
  }
  v14 = (void *)*((_QWORD *)a1 + 28);
  if ( v14 )
  {
    CoTaskMemFree(v14);
    *((_QWORD *)a1 + 28) = 0;
  }
  v15 = (void *)*((_QWORD *)a1 + 29);
  if ( v15 )
  {
    CoTaskMemFree(v15);
    *((_QWORD *)a1 + 29) = 0;
  }
  v16 = (void *)*((_QWORD *)a1 + 30);
  if ( v16 )
  {
    CoTaskMemFree(v16);
    *((_QWORD *)a1 + 30) = 0;
  }
}

```

## disassembly

```asm
0x1400d24d8  push    rbx
0x1400d24da  push    rbp
0x1400d24db  push    rsi
0x1400d24dc  push    rdi
0x1400d24dd  sub     rsp, 28h
0x1400d24e1  xor     ebp, ebp
0x1400d24e3  mov     rbx, rcx
0x1400d24e6  cmp     [rcx+38h], rbp
0x1400d24ea  jz      short loc_1400D2525
0x1400d24ec  mov     edi, ebp
0x1400d24ee  cmp     [rcx+30h], ebp
0x1400d24f1  jbe     short loc_1400D2517
0x1400d24f3  mov     rax, [rbx+38h]
0x1400d24f7  mov     esi, edi
0x1400d24f9  mov     rcx, [rax+rsi*8]; pv
0x1400d24fd  test    rcx, rcx
0x1400d2500  jz      short loc_1400D2510
0x1400d2502  call    cs:__imp_CoTaskMemFree
0x1400d2508  mov     rax, [rbx+38h]
0x1400d250c  mov     [rax+rsi*8], rbp
0x1400d2510  inc     edi
0x1400d2512  cmp     edi, [rbx+30h]
0x1400d2515  jb      short loc_1400D24F3
0x1400d2517  mov     rcx, [rbx+38h]; pv
0x1400d251b  call    cs:__imp_CoTaskMemFree
0x1400d2521  mov     [rbx+38h], rbp
0x1400d2525  cmp     [rbx+48h], rbp
0x1400d2529  jz      short loc_1400D2564
0x1400d252b  mov     edi, ebp
0x1400d252d  cmp     [rbx+40h], ebp
0x1400d2530  jbe     short loc_1400D2556
0x1400d2532  mov     rax, [rbx+48h]
0x1400d2536  mov     esi, edi
0x1400d2538  mov     rcx, [rax+rsi*8]; pv
0x1400d253c  test    rcx, rcx
0x1400d253f  jz      short loc_1400D254F
0x1400d2541  call    cs:__imp_CoTaskMemFree
0x1400d2547  mov     rax, [rbx+48h]
0x1400d254b  mov     [rax+rsi*8], rbp
0x1400d254f  inc     edi
0x1400d2551  cmp     edi, [rbx+40h]
0x1400d2554  jb      short loc_1400D2532
0x1400d2556  mov     rcx, [rbx+48h]; pv
0x1400d255a  call    cs:__imp_CoTaskMemFree
0x1400d2560  mov     [rbx+48h], rbp
0x1400d2564  mov     rcx, [rbx+50h]; pv
0x1400d2568  test    rcx, rcx
0x1400d256b  jz      short loc_1400D2577
0x1400d256d  call    cs:__imp_CoTaskMemFree
0x1400d2573  mov     [rbx+50h], rbp
0x1400d2577  mov     rcx, [rbx+58h]; pv
0x1400d257b  test    rcx, rcx
0x1400d257e  jz      short loc_1400D258A
0x1400d2580  call    cs:__imp_CoTaskMemFree
0x1400d2586  mov     [rbx+58h], rbp
0x1400d258a  mov     rcx, [rbx+60h]; pv
0x1400d258e  test    rcx, rcx
0x1400d2591  jz      short loc_1400D259D
0x1400d2593  call    cs:__imp_CoTaskMemFree
0x1400d2599  mov     [rbx+60h], rbp
0x1400d259d  mov     rcx, [rbx+68h]; pv
0x1400d25a1  test    rcx, rcx
0x1400d25a4  jz      short loc_1400D25B0
0x1400d25a6  call    cs:__imp_CoTaskMemFree
0x1400d25ac  mov     [rbx+68h], rbp
0x1400d25b0  mov     rcx, [rbx+70h]; pv
0x1400d25b4  test    rcx, rcx
0x1400d25b7  jz      short loc_1400D25C3
0x1400d25b9  call    cs:__imp_CoTaskMemFree
0x1400d25bf  mov     [rbx+70h], rbp
0x1400d25c3  mov     rcx, [rbx+78h]; pv
0x1400d25c7  test    rcx, rcx
0x1400d25ca  jz      short loc_1400D25D6
0x1400d25cc  call    cs:__imp_CoTaskMemFree
0x1400d25d2  mov     [rbx+78h], rbp
0x1400d25d6  mov     rcx, [rbx+0D0h]; pv
0x1400d25dd  test    rcx, rcx
0x1400d25e0  jz      short loc_1400D25EF
0x1400d25e2  call    cs:__imp_CoTaskMemFree
0x1400d25e8  mov     [rbx+0D0h], rbp
0x1400d25ef  mov     rcx, [rbx+0D8h]; pv
0x1400d25f6  test    rcx, rcx
0x1400d25f9  jz      short loc_1400D2608
0x1400d25fb  call    cs:__imp_CoTaskMemFree
0x1400d2601  mov     [rbx+0D8h], rbp
0x1400d2608  mov     rcx, [rbx+0E0h]; pv
0x1400d260f  test    rcx, rcx
0x1400d2612  jz      short loc_1400D2621
0x1400d2614  call    cs:__imp_CoTaskMemFree
0x1400d261a  mov     [rbx+0E0h], rbp
0x1400d2621  mov     rcx, [rbx+0E8h]; pv
0x1400d2628  test    rcx, rcx
0x1400d262b  jz      short loc_1400D263A
0x1400d262d  call    cs:__imp_CoTaskMemFree
0x1400d2633  mov     [rbx+0E8h], rbp
0x1400d263a  mov     rcx, [rbx+0F0h]; pv
0x1400d2641  test    rcx, rcx
0x1400d2644  jz      short loc_1400D2653
0x1400d2646  call    cs:__imp_CoTaskMemFree
0x1400d264c  mov     [rbx+0F0h], rbp
0x1400d2653  add     rsp, 28h
0x1400d2657  pop     rdi
0x1400d2658  pop     rsi
0x1400d2659  pop     rbp
0x1400d265a  pop     rbx
0x1400d265b  retn
```
