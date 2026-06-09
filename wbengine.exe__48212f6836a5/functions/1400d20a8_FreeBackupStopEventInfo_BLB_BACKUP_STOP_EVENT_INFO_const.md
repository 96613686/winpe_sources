# FreeBackupStopEventInfo(_BLB_BACKUP_STOP_EVENT_INFO * const)

- ea: `0x1400d20a8`
- end: `0x1400d2429`
- name: `?FreeBackupStopEventInfo@@YAXQEAU_BLB_BACKUP_STOP_EVENT_INFO@@@Z`
- size: `897`
- prototype: `void __fastcall(struct _BLB_BACKUP_STOP_EVENT_INFO *const)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140031960`

## callees

- `0x1400d20a8`
- `0x14012dd98`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400d20db`
- `ole32!CoTaskMemFree` at `0x1400d20f5`
- `ole32!CoTaskMemFree` at `0x1400d210d`
- `ole32!CoTaskMemFree` at `0x1400d211f`
- `ole32!CoTaskMemFree` at `0x1400d2131`
- `ole32!CoTaskMemFree` at `0x1400d2144`
- `ole32!CoTaskMemFree` at `0x1400d2157`
- `ole32!CoTaskMemFree` at `0x1400d216d`
- `ole32!CoTaskMemFree` at `0x1400d2183`
- `ole32!CoTaskMemFree` at `0x1400d2196`
- `ole32!CoTaskMemFree` at `0x1400d21a9`
- `ole32!CoTaskMemFree` at `0x1400d21bf`
- `ole32!CoTaskMemFree` at `0x1400d21d8`
- `ole32!CoTaskMemFree` at `0x1400d21f1`
- `ole32!CoTaskMemFree` at `0x1400d220a`
- `ole32!CoTaskMemFree` at `0x1400d2223`
- `ole32!CoTaskMemFree` at `0x1400d223c`
- `ole32!CoTaskMemFree` at `0x1400d2255`
- `ole32!CoTaskMemFree` at `0x1400d226e`
- `ole32!CoTaskMemFree` at `0x1400d2287`
- `ole32!CoTaskMemFree` at `0x1400d22a0`
- `ole32!CoTaskMemFree` at `0x1400d22b9`
- `ole32!CoTaskMemFree` at `0x1400d22d2`
- `ole32!CoTaskMemFree` at `0x1400d22eb`
- `ole32!CoTaskMemFree` at `0x1400d2304`
- `ole32!CoTaskMemFree` at `0x1400d231d`
- `ole32!CoTaskMemFree` at `0x1400d2336`
- `ole32!CoTaskMemFree` at `0x1400d234f`
- `ole32!CoTaskMemFree` at `0x1400d2368`
- `ole32!CoTaskMemFree` at `0x1400d2381`
- `ole32!CoTaskMemFree` at `0x1400d2397`
- `ole32!CoTaskMemFree` at `0x1400d23bc`
- `ole32!CoTaskMemFree` at `0x1400d23cf`
- `ole32!CoTaskMemFree` at `0x1400d23e2`
- `ole32!CoTaskMemFree` at `0x1400d23f8`
- `ole32!CoTaskMemFree` at `0x1400d2411`
- `ole32!CoTaskMemFree` at `0x1400d20db`
- `ole32!CoTaskMemFree` at `0x1400d20f5`
- `ole32!CoTaskMemFree` at `0x1400d210d`
- `ole32!CoTaskMemFree` at `0x1400d211f`
- `ole32!CoTaskMemFree` at `0x1400d2131`
- `ole32!CoTaskMemFree` at `0x1400d2144`
- `ole32!CoTaskMemFree` at `0x1400d2157`
- `ole32!CoTaskMemFree` at `0x1400d216d`
- `ole32!CoTaskMemFree` at `0x1400d2183`
- `ole32!CoTaskMemFree` at `0x1400d2196`
- `ole32!CoTaskMemFree` at `0x1400d21a9`
- `ole32!CoTaskMemFree` at `0x1400d21bf`
- `ole32!CoTaskMemFree` at `0x1400d21d8`
- `ole32!CoTaskMemFree` at `0x1400d21f1`
- `ole32!CoTaskMemFree` at `0x1400d220a`
- `ole32!CoTaskMemFree` at `0x1400d2223`
- `ole32!CoTaskMemFree` at `0x1400d223c`
- `ole32!CoTaskMemFree` at `0x1400d2255`
- `ole32!CoTaskMemFree` at `0x1400d226e`
- `ole32!CoTaskMemFree` at `0x1400d2287`
- `ole32!CoTaskMemFree` at `0x1400d22a0`
- `ole32!CoTaskMemFree` at `0x1400d22b9`
- `ole32!CoTaskMemFree` at `0x1400d22d2`
- `ole32!CoTaskMemFree` at `0x1400d22eb`
- `ole32!CoTaskMemFree` at `0x1400d2304`
- `ole32!CoTaskMemFree` at `0x1400d231d`
- `ole32!CoTaskMemFree` at `0x1400d2336`
- `ole32!CoTaskMemFree` at `0x1400d234f`
- `ole32!CoTaskMemFree` at `0x1400d2368`
- `ole32!CoTaskMemFree` at `0x1400d2381`
- `ole32!CoTaskMemFree` at `0x1400d2397`
- `ole32!CoTaskMemFree` at `0x1400d23bc`
- `ole32!CoTaskMemFree` at `0x1400d23cf`
- `ole32!CoTaskMemFree` at `0x1400d23e2`
- `ole32!CoTaskMemFree` at `0x1400d23f8`
- `ole32!CoTaskMemFree` at `0x1400d2411`

## pseudocode

```c
void __fastcall FreeBackupStopEventInfo(struct _BLB_BACKUP_STOP_EVENT_INFO *const a1)
{
  void **v2; // rdi
  unsigned int i; // esi
  void *v4; // rcx
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
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  void *v28; // rcx
  void *v29; // rcx
  void *v30; // rcx
  void *v31; // rcx
  void *v32; // rcx
  void *v33; // rcx
  void *v34; // rcx
  void *v35; // rcx
  void *v36; // rcx
  void *v37; // rcx
  void *v38; // rcx

  if ( *((_QWORD *)a1 + 5) )
  {
    v2 = (void **)((char *)a1 + 48);
    for ( i = 0; i < *((_DWORD *)a1 + 9); ++i )
    {
      v4 = *(void **)(*((_QWORD *)a1 + 5) + 8LL * i);
      if ( v4 )
      {
        CoTaskMemFree(v4);
        *(_QWORD *)(*((_QWORD *)a1 + 5) + 8LL * i) = 0;
      }
      v5 = (void *)*((_QWORD *)*v2 + i);
      if ( v5 )
      {
        CoTaskMemFree(v5);
        *((_QWORD *)*v2 + i) = 0;
      }
    }
    CoTaskMemFree(*((LPVOID *)a1 + 5));
    v6 = *v2;
    *((_QWORD *)a1 + 5) = 0;
    if ( v6 )
    {
      CoTaskMemFree(v6);
      *v2 = 0;
    }
  }
  v7 = (void *)*((_QWORD *)a1 + 15);
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *((_QWORD *)a1 + 15) = 0;
  }
  v8 = (void *)*((_QWORD *)a1 + 7);
  if ( v8 )
  {
    CoTaskMemFree(v8);
    *((_QWORD *)a1 + 7) = 0;
  }
  v9 = (void *)*((_QWORD *)a1 + 8);
  if ( v9 )
  {
    CoTaskMemFree(v9);
    *((_QWORD *)a1 + 8) = 0;
  }
  v10 = (void *)*((_QWORD *)a1 + 17);
  if ( v10 )
  {
    CoTaskMemFree(v10);
    *((_QWORD *)a1 + 17) = 0;
  }
  v11 = (void *)*((_QWORD *)a1 + 9);
  if ( v11 )
  {
    CoTaskMemFree(v11);
    *((_QWORD *)a1 + 9) = 0;
  }
  v12 = (void *)*((_QWORD *)a1 + 12);
  if ( v12 )
  {
    CoTaskMemFree(v12);
    *((_QWORD *)a1 + 12) = 0;
  }
  v13 = (void *)*((_QWORD *)a1 + 10);
  if ( v13 )
  {
    CoTaskMemFree(v13);
    *((_QWORD *)a1 + 10) = 0;
  }
  v14 = (void *)*((_QWORD *)a1 + 16);
  if ( v14 )
  {
    CoTaskMemFree(v14);
    *((_QWORD *)a1 + 16) = 0;
  }
  v15 = (void *)*((_QWORD *)a1 + 18);
  if ( v15 )
  {
    CoTaskMemFree(v15);
    *((_QWORD *)a1 + 18) = 0;
  }
  v16 = (void *)*((_QWORD *)a1 + 19);
  if ( v16 )
  {
    CoTaskMemFree(v16);
    *((_QWORD *)a1 + 19) = 0;
  }
  v17 = (void *)*((_QWORD *)a1 + 20);
  if ( v17 )
  {
    CoTaskMemFree(v17);
    *((_QWORD *)a1 + 20) = 0;
  }
  v18 = (void *)*((_QWORD *)a1 + 21);
  if ( v18 )
  {
    CoTaskMemFree(v18);
    *((_QWORD *)a1 + 21) = 0;
  }
  v19 = (void *)*((_QWORD *)a1 + 22);
  if ( v19 )
  {
    CoTaskMemFree(v19);
    *((_QWORD *)a1 + 22) = 0;
  }
  v20 = (void *)*((_QWORD *)a1 + 23);
  if ( v20 )
  {
    CoTaskMemFree(v20);
    *((_QWORD *)a1 + 23) = 0;
  }
  v21 = (void *)*((_QWORD *)a1 + 32);
  if ( v21 )
  {
    CoTaskMemFree(v21);
    *((_QWORD *)a1 + 32) = 0;
  }
  v22 = (void *)*((_QWORD *)a1 + 33);
  if ( v22 )
  {
    CoTaskMemFree(v22);
    *((_QWORD *)a1 + 33) = 0;
  }
  v23 = (void *)*((_QWORD *)a1 + 34);
  if ( v23 )
  {
    CoTaskMemFree(v23);
    *((_QWORD *)a1 + 34) = 0;
  }
  v24 = (void *)*((_QWORD *)a1 + 35);
  if ( v24 )
  {
    CoTaskMemFree(v24);
    *((_QWORD *)a1 + 35) = 0;
  }
  v25 = (void *)*((_QWORD *)a1 + 36);
  if ( v25 )
  {
    CoTaskMemFree(v25);
    *((_QWORD *)a1 + 36) = 0;
  }
  v26 = (void *)*((_QWORD *)a1 + 37);
  if ( v26 )
  {
    CoTaskMemFree(v26);
    *((_QWORD *)a1 + 37) = 0;
  }
  v27 = (void *)*((_QWORD *)a1 + 38);
  if ( v27 )
  {
    CoTaskMemFree(v27);
    *((_QWORD *)a1 + 38) = 0;
  }
  v28 = (void *)*((_QWORD *)a1 + 39);
  if ( v28 )
  {
    CoTaskMemFree(v28);
    *((_QWORD *)a1 + 39) = 0;
  }
  v29 = (void *)*((_QWORD *)a1 + 42);
  if ( v29 )
  {
    CoTaskMemFree(v29);
    *((_QWORD *)a1 + 42) = 0;
  }
  v30 = (void *)*((_QWORD *)a1 + 43);
  if ( v30 )
  {
    CoTaskMemFree(v30);
    *((_QWORD *)a1 + 43) = 0;
  }
  v31 = (void *)*((_QWORD *)a1 + 45);
  if ( v31 )
  {
    CoTaskMemFree(v31);
    *((_QWORD *)a1 + 45) = 0;
  }
  v32 = (void *)*((_QWORD *)a1 + 46);
  if ( v32 )
  {
    CoTaskMemFree(v32);
    *((_QWORD *)a1 + 46) = 0;
  }
  v33 = (void *)*((_QWORD *)a1 + 3);
  if ( v33 )
  {
    CoTaskMemFree(v33);
    *((_QWORD *)a1 + 3) = 0;
  }
  FreeComponentConsistencyStatus(*((_DWORD *)a1 + 94), *((struct _BLB_COMPONENT_STATUS **)a1 + 48));
  v34 = (void *)*((_QWORD *)a1 + 13);
  if ( v34 )
  {
    CoTaskMemFree(v34);
    *((_QWORD *)a1 + 13) = 0;
  }
  v35 = (void *)*((_QWORD *)a1 + 14);
  if ( v35 )
  {
    CoTaskMemFree(v35);
    *((_QWORD *)a1 + 14) = 0;
  }
  v36 = (void *)*((_QWORD *)a1 + 11);
  if ( v36 )
  {
    CoTaskMemFree(v36);
    *((_QWORD *)a1 + 11) = 0;
  }
  v37 = (void *)*((_QWORD *)a1 + 58);
  if ( v37 )
  {
    CoTaskMemFree(v37);
    *((_QWORD *)a1 + 58) = 0;
  }
  v38 = (void *)*((_QWORD *)a1 + 59);
  if ( v38 )
  {
    CoTaskMemFree(v38);
    *((_QWORD *)a1 + 59) = 0;
  }
}

```

## disassembly

```asm
0x1400d20a8  push    rbx
0x1400d20aa  push    rbp
0x1400d20ab  push    rsi
0x1400d20ac  push    rdi
0x1400d20ad  push    r14
0x1400d20af  sub     rsp, 20h
0x1400d20b3  xor     r14d, r14d
0x1400d20b6  mov     rbx, rcx
0x1400d20b9  cmp     [rcx+28h], r14
0x1400d20bd  jz      short loc_1400D2128
0x1400d20bf  lea     rdi, [rcx+30h]
0x1400d20c3  mov     esi, r14d
0x1400d20c6  cmp     [rcx+24h], r14d
0x1400d20ca  jbe     short loc_1400D2109
0x1400d20cc  mov     rax, [rbx+28h]
0x1400d20d0  mov     ebp, esi
0x1400d20d2  mov     rcx, [rax+rbp*8]; pv
0x1400d20d6  test    rcx, rcx
0x1400d20d9  jz      short loc_1400D20E9
0x1400d20db  call    cs:__imp_CoTaskMemFree
0x1400d20e1  mov     rax, [rbx+28h]
0x1400d20e5  mov     [rax+rbp*8], r14
0x1400d20e9  mov     rax, [rdi]
0x1400d20ec  mov     rcx, [rax+rbp*8]; pv
0x1400d20f0  test    rcx, rcx
0x1400d20f3  jz      short loc_1400D2102
0x1400d20f5  call    cs:__imp_CoTaskMemFree
0x1400d20fb  mov     rax, [rdi]
0x1400d20fe  mov     [rax+rbp*8], r14
0x1400d2102  inc     esi
0x1400d2104  cmp     esi, [rbx+24h]
0x1400d2107  jb      short loc_1400D20CC
0x1400d2109  mov     rcx, [rbx+28h]; pv
0x1400d210d  call    cs:__imp_CoTaskMemFree
0x1400d2113  mov     rcx, [rdi]; pv
0x1400d2116  mov     [rbx+28h], r14
0x1400d211a  test    rcx, rcx
0x1400d211d  jz      short loc_1400D2128
0x1400d211f  call    cs:__imp_CoTaskMemFree
0x1400d2125  mov     [rdi], r14
0x1400d2128  mov     rcx, [rbx+78h]; pv
0x1400d212c  test    rcx, rcx
0x1400d212f  jz      short loc_1400D213B
0x1400d2131  call    cs:__imp_CoTaskMemFree
0x1400d2137  mov     [rbx+78h], r14
0x1400d213b  mov     rcx, [rbx+38h]; pv
0x1400d213f  test    rcx, rcx
0x1400d2142  jz      short loc_1400D214E
0x1400d2144  call    cs:__imp_CoTaskMemFree
0x1400d214a  mov     [rbx+38h], r14
0x1400d214e  mov     rcx, [rbx+40h]; pv
0x1400d2152  test    rcx, rcx
0x1400d2155  jz      short loc_1400D2161
0x1400d2157  call    cs:__imp_CoTaskMemFree
0x1400d215d  mov     [rbx+40h], r14
0x1400d2161  mov     rcx, [rbx+88h]; pv
0x1400d2168  test    rcx, rcx
0x1400d216b  jz      short loc_1400D217A
0x1400d216d  call    cs:__imp_CoTaskMemFree
0x1400d2173  mov     [rbx+88h], r14
0x1400d217a  mov     rcx, [rbx+48h]; pv
0x1400d217e  test    rcx, rcx
0x1400d2181  jz      short loc_1400D218D
0x1400d2183  call    cs:__imp_CoTaskMemFree
0x1400d2189  mov     [rbx+48h], r14
0x1400d218d  mov     rcx, [rbx+60h]; pv
0x1400d2191  test    rcx, rcx
0x1400d2194  jz      short loc_1400D21A0
0x1400d2196  call    cs:__imp_CoTaskMemFree
0x1400d219c  mov     [rbx+60h], r14
0x1400d21a0  mov     rcx, [rbx+50h]; pv
0x1400d21a4  test    rcx, rcx
0x1400d21a7  jz      short loc_1400D21B3
0x1400d21a9  call    cs:__imp_CoTaskMemFree
0x1400d21af  mov     [rbx+50h], r14
0x1400d21b3  mov     rcx, [rbx+80h]; pv
0x1400d21ba  test    rcx, rcx
0x1400d21bd  jz      short loc_1400D21CC
0x1400d21bf  call    cs:__imp_CoTaskMemFree
0x1400d21c5  mov     [rbx+80h], r14
0x1400d21cc  mov     rcx, [rbx+90h]; pv
0x1400d21d3  test    rcx, rcx
0x1400d21d6  jz      short loc_1400D21E5
0x1400d21d8  call    cs:__imp_CoTaskMemFree
0x1400d21de  mov     [rbx+90h], r14
0x1400d21e5  mov     rcx, [rbx+98h]; pv
0x1400d21ec  test    rcx, rcx
0x1400d21ef  jz      short loc_1400D21FE
0x1400d21f1  call    cs:__imp_CoTaskMemFree
0x1400d21f7  mov     [rbx+98h], r14
0x1400d21fe  mov     rcx, [rbx+0A0h]; pv
0x1400d2205  test    rcx, rcx
0x1400d2208  jz      short loc_1400D2217
0x1400d220a  call    cs:__imp_CoTaskMemFree
0x1400d2210  mov     [rbx+0A0h], r14
0x1400d2217  mov     rcx, [rbx+0A8h]; pv
0x1400d221e  test    rcx, rcx
0x1400d2221  jz      short loc_1400D2230
0x1400d2223  call    cs:__imp_CoTaskMemFree
0x1400d2229  mov     [rbx+0A8h], r14
0x1400d2230  mov     rcx, [rbx+0B0h]; pv
0x1400d2237  test    rcx, rcx
0x1400d223a  jz      short loc_1400D2249
0x1400d223c  call    cs:__imp_CoTaskMemFree
0x1400d2242  mov     [rbx+0B0h], r14
0x1400d2249  mov     rcx, [rbx+0B8h]; pv
0x1400d2250  test    rcx, rcx
0x1400d2253  jz      short loc_1400D2262
0x1400d2255  call    cs:__imp_CoTaskMemFree
0x1400d225b  mov     [rbx+0B8h], r14
0x1400d2262  mov     rcx, [rbx+100h]; pv
0x1400d2269  test    rcx, rcx
0x1400d226c  jz      short loc_1400D227B
0x1400d226e  call    cs:__imp_CoTaskMemFree
0x1400d2274  mov     [rbx+100h], r14
0x1400d227b  mov     rcx, [rbx+108h]; pv
0x1400d2282  test    rcx, rcx
0x1400d2285  jz      short loc_1400D2294
0x1400d2287  call    cs:__imp_CoTaskMemFree
0x1400d228d  mov     [rbx+108h], r14
0x1400d2294  mov     rcx, [rbx+110h]; pv
0x1400d229b  test    rcx, rcx
0x1400d229e  jz      short loc_1400D22AD
0x1400d22a0  call    cs:__imp_CoTaskMemFree
0x1400d22a6  mov     [rbx+110h], r14
0x1400d22ad  mov     rcx, [rbx+118h]; pv
0x1400d22b4  test    rcx, rcx
0x1400d22b7  jz      short loc_1400D22C6
0x1400d22b9  call    cs:__imp_CoTaskMemFree
0x1400d22bf  mov     [rbx+118h], r14
0x1400d22c6  mov     rcx, [rbx+120h]; pv
0x1400d22cd  test    rcx, rcx
0x1400d22d0  jz      short loc_1400D22DF
0x1400d22d2  call    cs:__imp_CoTaskMemFree
0x1400d22d8  mov     [rbx+120h], r14
0x1400d22df  mov     rcx, [rbx+128h]; pv
0x1400d22e6  test    rcx, rcx
0x1400d22e9  jz      short loc_1400D22F8
0x1400d22eb  call    cs:__imp_CoTaskMemFree
0x1400d22f1  mov     [rbx+128h], r14
0x1400d22f8  mov     rcx, [rbx+130h]; pv
0x1400d22ff  test    rcx, rcx
0x1400d2302  jz      short loc_1400D2311
0x1400d2304  call    cs:__imp_CoTaskMemFree
0x1400d230a  mov     [rbx+130h], r14
0x1400d2311  mov     rcx, [rbx+138h]; pv
0x1400d2318  test    rcx, rcx
0x1400d231b  jz      short loc_1400D232A
0x1400d231d  call    cs:__imp_CoTaskMemFree
0x1400d2323  mov     [rbx+138h], r14
0x1400d232a  mov     rcx, [rbx+150h]; pv
0x1400d2331  test    rcx, rcx
0x1400d2334  jz      short loc_1400D2343
0x1400d2336  call    cs:__imp_CoTaskMemFree
0x1400d233c  mov     [rbx+150h], r14
0x1400d2343  mov     rcx, [rbx+158h]; pv
0x1400d234a  test    rcx, rcx
0x1400d234d  jz      short loc_1400D235C
0x1400d234f  call    cs:__imp_CoTaskMemFree
0x1400d2355  mov     [rbx+158h], r14
0x1400d235c  mov     rcx, [rbx+168h]; pv
0x1400d2363  test    rcx, rcx
0x1400d2366  jz      short loc_1400D2375
0x1400d2368  call    cs:__imp_CoTaskMemFree
0x1400d236e  mov     [rbx+168h], r14
0x1400d2375  mov     rcx, [rbx+170h]; pv
0x1400d237c  test    rcx, rcx
0x1400d237f  jz      short loc_1400D238E
0x1400d2381  call    cs:__imp_CoTaskMemFree
0x1400d2387  mov     [rbx+170h], r14
0x1400d238e  mov     rcx, [rbx+18h]; pv
0x1400d2392  test    rcx, rcx
0x1400d2395  jz      short loc_1400D23A1
0x1400d2397  call    cs:__imp_CoTaskMemFree
0x1400d239d  mov     [rbx+18h], r14
0x1400d23a1  mov     rdx, [rbx+180h]; struct _BLB_COMPONENT_STATUS *
0x1400d23a8  mov     ecx, [rbx+178h]; unsigned int
0x1400d23ae  call    ?FreeComponentConsistencyStatus@@YAXKPEAU_BLB_COMPONENT_STATUS@@@Z; FreeComponentConsistencyStatus(ulong,_BLB_COMPONENT_STATUS *)
0x1400d23b3  mov     rcx, [rbx+68h]; pv
0x1400d23b7  test    rcx, rcx
0x1400d23ba  jz      short loc_1400D23C6
0x1400d23bc  call    cs:__imp_CoTaskMemFree
0x1400d23c2  mov     [rbx+68h], r14
0x1400d23c6  mov     rcx, [rbx+70h]; pv
0x1400d23ca  test    rcx, rcx
0x1400d23cd  jz      short loc_1400D23D9
0x1400d23cf  call    cs:__imp_CoTaskMemFree
0x1400d23d5  mov     [rbx+70h], r14
0x1400d23d9  mov     rcx, [rbx+58h]; pv
0x1400d23dd  test    rcx, rcx
0x1400d23e0  jz      short loc_1400D23EC
0x1400d23e2  call    cs:__imp_CoTaskMemFree
0x1400d23e8  mov     [rbx+58h], r14
0x1400d23ec  mov     rcx, [rbx+1D0h]; pv
0x1400d23f3  test    rcx, rcx
0x1400d23f6  jz      short loc_1400D2405
0x1400d23f8  call    cs:__imp_CoTaskMemFree
0x1400d23fe  mov     [rbx+1D0h], r14
0x1400d2405  mov     rcx, [rbx+1D8h]; pv
0x1400d240c  test    rcx, rcx
0x1400d240f  jz      short loc_1400D241E
0x1400d2411  call    cs:__imp_CoTaskMemFree
0x1400d2417  mov     [rbx+1D8h], r14
0x1400d241e  add     rsp, 20h
0x1400d2422  pop     r14
0x1400d2424  pop     rdi
0x1400d2425  pop     rsi
0x1400d2426  pop     rbp
0x1400d2427  pop     rbx
0x1400d2428  retn
```
