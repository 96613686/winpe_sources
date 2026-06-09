# CShortcutTF::Parse(CSrTokenDL const *,ulong,ulong,ulong,CSrTokenDL *,ulong *)

- ea: `0x1800d1378`
- end: `0x1800d1645`
- name: `?Parse@CShortcutTF@@QEAAJPEBVCSrTokenDL@@KKKPEAV2@PEAK@Z`
- size: `717`
- prototype: `__int64 __fastcall(CShortcutTF *__hidden this, const struct CSrTokenDL *, unsigned int, unsigned int, unsigned int, struct CSrTokenDL *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800cf4d0`

## callees

- `0x180004312`
- `0x1800d1378`
- `0x1800f6bc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d1428`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d1428`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d15e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d160d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d15e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d160d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d149f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d149f`

## pseudocode

```c
__int64 __fastcall CShortcutTF::Parse(
        CShortcutTF *this,
        const struct CSrTokenDL *a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        struct CSrTokenDL *a6,
        unsigned int *a7)
{
  unsigned int v7; // edi
  int v9; // r10d
  unsigned int v10; // eax
  const struct CSrTokenDL *v11; // r11
  unsigned int v12; // ebp
  unsigned int v13; // r12d
  unsigned int v14; // ecx
  int v15; // ebx
  unsigned int v16; // r14d
  unsigned int v17; // r9d
  unsigned int v18; // esi
  unsigned int v19; // ebp
  __int64 v20; // r15
  __int64 v21; // rbx
  unsigned int v22; // ecx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rax
  _QWORD *v26; // rax
  _QWORD *v27; // rsi
  unsigned int v28; // r15d
  char *v29; // rbp
  __int64 v30; // rax
  __int64 v31; // rcx
  _WORD *v32; // rdx
  __int64 v33; // rax
  size_t v34; // rbx
  const unsigned __int16 *v35; // r8
  char *v36; // rdi
  __int64 result; // rax
  unsigned int v38; // [rsp+30h] [rbp-48h]
  int v39; // [rsp+34h] [rbp-44h]
  unsigned int v40; // [rsp+38h] [rbp-40h]
  unsigned int v41; // [rsp+3Ch] [rbp-3Ch]

  v7 = 0;
  v9 = a4;
  v10 = a3;
  v40 = 0;
  v11 = a2;
  v12 = 0;
  v13 = a3;
  *a7 = 0;
  v14 = a4 + a3;
  v41 = a4 + a3;
  while ( v13 < v14 )
  {
    v15 = 0;
    v16 = 0;
    v17 = 0;
    v39 = 0;
    v18 = 0;
    v38 = 0;
    if ( !*((_DWORD *)this + 4) )
      goto LABEL_20;
    v19 = v10 + v9 - v13;
    while ( 1 )
    {
      v20 = *((_QWORD *)this + 1);
      v21 = 32LL * v18;
      if ( v19 >= *(_DWORD *)(v21 + v20 + 24) )
        break;
LABEL_16:
      if ( ++v18 >= *((_DWORD *)this + 4) )
        goto LABEL_19;
    }
    while ( 1 )
    {
      v22 = *(_DWORD *)(v21 + v20 + 24);
      if ( v7 >= v22 )
        break;
      v23 = _o__wcsicmp(
              *(_QWORD *)(*(_QWORD *)(v21 + v20 + 16) + 8LL * v7),
              *((_QWORD *)v11 + 5 * v7 + 5 * (unsigned __int64)v13));
      v11 = a2;
      if ( v23 )
      {
        v7 = 0;
        goto LABEL_15;
      }
      ++v7;
    }
    v7 = 0;
    if ( !v22 )
    {
LABEL_15:
      v17 = v38;
      goto LABEL_16;
    }
    if ( v16 <= v22 )
    {
      v24 = *((_QWORD *)this + 1);
      v25 = -1;
      do
        ++v25;
      while ( *(_WORD *)(*(_QWORD *)(v21 + v24) + 2 * v25) );
      v16 = *(_DWORD *)(v21 + v20 + 24);
      *(_DWORD *)(v21 + v24 + 28) = 0;
      v17 = v38 + 2 * v25 + 10;
      ++v39;
      v38 = v17;
      goto LABEL_16;
    }
    v17 = v38;
LABEL_19:
    v15 = v39;
LABEL_20:
    v26 = CoTaskMemAlloc(v17);
    v27 = v26;
    if ( !v26 )
      return 2147942414LL;
    v28 = 0;
    v29 = (char *)&v26[v15];
    while ( v7 < *((_DWORD *)this + 4) )
    {
      v30 = *((_QWORD *)this + 1);
      v31 = 32LL * v7;
      if ( !*(_DWORD *)(v31 + v30 + 28) )
      {
        *(_DWORD *)(v31 + v30 + 28) = 1;
        v27[v28] = v29;
        v32 = *(_WORD **)(v31 + *((_QWORD *)this + 1));
        v33 = -1;
        do
          ++v33;
        while ( v32[v33] );
        v34 = 2LL * (unsigned int)(v33 + 1);
        if ( v34 > (unsigned __int64)v27 + v38 - (_QWORD)v29 )
        {
          CoTaskMemFree(v27);
          return 2147942522LL;
        }
        ++v28;
        memcpy_0(v29, v32, v34);
        v29 += v34;
      }
      ++v7;
    }
    v7 = 0;
    if ( v16 )
    {
      v35 = (const unsigned __int16 *)*v27;
      v36 = (char *)a6 + 40 * v40;
      *((_DWORD *)v36 + 9) = 0;
      CSrTokenDL::SetAnyViaCopy(
        (CSrTokenDL *)(5LL * v40),
        (unsigned __int16 **)v36 + 1,
        v35,
        v28,
        a5,
        (unsigned int *)v36 + 9);
      CSrTokenDL::SetAnyViaCopy(
        (CSrTokenDL *)1,
        (unsigned __int16 **)v36,
        *(const unsigned __int16 **)(32LL * v13 + *((_QWORD *)this + 1) + 8),
        1u,
        1u,
        0);
      v12 = ++v40;
      v36[16] = *((_BYTE *)a2 + 40 * v13 + 16);
      *((_DWORD *)v36 + 5) = v13;
      *((_DWORD *)v36 + 6) = v16;
      *((_DWORD *)v36 + 7) = 0;
      *((_DWORD *)v36 + 8) = 1;
      v7 = 0;
    }
    else
    {
      v12 = v40;
      v16 = 1;
    }
    CoTaskMemFree(v27);
    v10 = a3;
    v13 += v16;
    v9 = a4;
    v14 = v41;
    v11 = a2;
  }
  result = 0;
  *a7 = v12;
  return result;
}

```

## disassembly

```asm
0x1800d1378  mov     rax, rsp
0x1800d137b  mov     [rax+8], rbx
0x1800d137f  mov     [rax+20h], r9d
0x1800d1383  mov     [rax+18h], r8d
0x1800d1387  mov     [rax+10h], rdx
0x1800d138b  push    rbp
0x1800d138c  push    rsi
0x1800d138d  push    rdi
0x1800d138e  push    r12
0x1800d1390  push    r13
0x1800d1392  push    r14
0x1800d1394  push    r15
0x1800d1396  sub     rsp, 40h
0x1800d139a  xor     edi, edi
0x1800d139c  mov     r13, rcx
0x1800d139f  mov     rcx, [rsp+78h+arg_30]
0x1800d13a7  mov     r10d, r9d
0x1800d13aa  mov     eax, r8d
0x1800d13ad  mov     [rsp+78h+var_40], edi
0x1800d13b1  mov     r11, rdx
0x1800d13b4  mov     ebp, edi
0x1800d13b6  mov     r12d, r8d
0x1800d13b9  mov     [rcx], edi
0x1800d13bb  lea     ecx, [r9+r8]
0x1800d13bf  mov     [rsp+78h+var_3C], ecx
0x1800d13c3  cmp     r12d, ecx
0x1800d13c6  jnb     loc_1800D1621
0x1800d13cc  mov     ebx, edi
0x1800d13ce  mov     r14d, edi
0x1800d13d1  mov     r9d, edi
0x1800d13d4  mov     [rsp+78h+var_44], ebx
0x1800d13d8  mov     esi, edi
0x1800d13da  mov     [rsp+78h+var_48], edi
0x1800d13de  cmp     [r13+10h], edi
0x1800d13e2  jbe     loc_1800D149C
0x1800d13e8  mov     ebp, r10d
0x1800d13eb  sub     ebp, r12d
0x1800d13ee  add     ebp, eax
0x1800d13f0  mov     r15, [r13+8]
0x1800d13f4  mov     ebx, esi
0x1800d13f6  shl     rbx, 5
0x1800d13fa  cmp     ebp, [rbx+r15+18h]
0x1800d13ff  jb      loc_1800D1485
0x1800d1405  mov     ecx, [rbx+r15+18h]
0x1800d140a  cmp     edi, ecx
0x1800d140c  jnb     short loc_1800D143E
0x1800d140e  mov     rcx, [rbx+r15+10h]
0x1800d1413  mov     r8d, edi
0x1800d1416  mov     eax, r12d
0x1800d1419  add     rax, r8
0x1800d141c  mov     rcx, [rcx+r8*8]
0x1800d1420  lea     rdx, [rax+rax*4]
0x1800d1424  mov     rdx, [r11+rdx*8]
0x1800d1428  call    cs:__imp__o__wcsicmp
0x1800d142e  mov     r11, [rsp+78h+arg_8]
0x1800d1436  test    eax, eax
0x1800d1438  jnz     short loc_1800D147E
0x1800d143a  inc     edi
0x1800d143c  jmp     short loc_1800D1405
0x1800d143e  xor     edi, edi
0x1800d1440  test    ecx, ecx
0x1800d1442  jz      short loc_1800D1480
0x1800d1444  cmp     r14d, ecx
0x1800d1447  ja      short loc_1800D1493
0x1800d1449  mov     rdx, [r13+8]
0x1800d144d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d1451  mov     r8, [rbx+rdx]
0x1800d1455  inc     rax
0x1800d1458  cmp     [r8+rax*2], di
0x1800d145d  jnz     short loc_1800D1455
0x1800d145f  mov     r9d, [rsp+78h+var_48]
0x1800d1464  mov     r14d, ecx
0x1800d1467  mov     [rbx+rdx+1Ch], edi
0x1800d146b  lea     r9d, [r9+rax*2]
0x1800d146f  add     r9d, 0Ah
0x1800d1473  inc     [rsp+78h+var_44]
0x1800d1477  mov     [rsp+78h+var_48], r9d
0x1800d147c  jmp     short loc_1800D1485
0x1800d147e  xor     edi, edi
0x1800d1480  mov     r9d, [rsp+78h+var_48]
0x1800d1485  inc     esi
0x1800d1487  cmp     esi, [r13+10h]
0x1800d148b  jb      loc_1800D13F0
0x1800d1491  jmp     short loc_1800D1498
0x1800d1493  mov     r9d, [rsp+78h+var_48]
0x1800d1498  mov     ebx, [rsp+78h+var_44]
0x1800d149c  mov     ecx, r9d; cb
0x1800d149f  call    cs:__imp_CoTaskMemAlloc
0x1800d14a5  mov     rsi, rax
0x1800d14a8  test    rax, rax
0x1800d14ab  jz      loc_1800D161A
0x1800d14b1  mov     ecx, ebx
0x1800d14b3  mov     r15d, edi
0x1800d14b6  lea     rbp, [rax+rcx*8]
0x1800d14ba  cmp     edi, [r13+10h]
0x1800d14be  jnb     short loc_1800D1527
0x1800d14c0  mov     rax, [r13+8]
0x1800d14c4  xor     r8d, r8d
0x1800d14c7  mov     ecx, edi
0x1800d14c9  shl     rcx, 5
0x1800d14cd  cmp     [rcx+rax+1Ch], r8d
0x1800d14d2  jnz     short loc_1800D1523
0x1800d14d4  mov     dword ptr [rcx+rax+1Ch], 1
0x1800d14dc  mov     eax, r15d
0x1800d14df  mov     [rsi+rax*8], rbp
0x1800d14e3  mov     rax, [r13+8]
0x1800d14e7  mov     rdx, [rcx+rax]; Src
0x1800d14eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d14ef  inc     rax
0x1800d14f2  cmp     [rdx+rax*2], r8w
0x1800d14f7  jnz     short loc_1800D14EF
0x1800d14f9  lea     ebx, [rax+1]
0x1800d14fc  mov     eax, [rsp+78h+var_48]
0x1800d1500  sub     rax, rbp
0x1800d1503  add     rbx, rbx
0x1800d1506  add     rax, rsi
0x1800d1509  cmp     rbx, rax
0x1800d150c  ja      loc_1800D160A
0x1800d1512  mov     r8, rbx; Size
0x1800d1515  mov     rcx, rbp; void *
0x1800d1518  inc     r15d
0x1800d151b  call    memcpy_0
0x1800d1520  add     rbp, rbx
0x1800d1523  inc     edi
0x1800d1525  jmp     short loc_1800D14BA
0x1800d1527  xor     edi, edi
0x1800d1529  test    r14d, r14d
0x1800d152c  jz      loc_1800D15D4
0x1800d1532  mov     ebp, [rsp+78h+var_40]
0x1800d1536  mov     r9d, r15d; unsigned int
0x1800d1539  mov     rax, [rsp+78h+arg_28]
0x1800d1541  mov     r8, [rsi]; unsigned __int16 *
0x1800d1544  lea     rcx, ds:0[rbp*4]
0x1800d154c  add     rcx, rbp; this
0x1800d154f  lea     rdi, [rax+rcx*8]
0x1800d1553  lea     rax, [rdi+24h]
0x1800d1557  mov     [rsp+78h+var_50], rax; unsigned int *
0x1800d155c  lea     rdx, [rdi+8]; unsigned __int16 **
0x1800d1560  mov     dword ptr [rax], 0
0x1800d1566  mov     eax, [rsp+78h+arg_20]
0x1800d156d  mov     [rsp+78h+var_58], eax; unsigned int
0x1800d1571  call    ?SetAnyViaCopy@CSrTokenDL@@QEAAJPEAPEAGPEBGKKPEAK@Z; CSrTokenDL::SetAnyViaCopy(ushort * *,ushort const *,ulong,ulong,ulong *)
0x1800d1576  mov     r8, [r13+8]
0x1800d157a  xor     r15d, r15d
0x1800d157d  mov     eax, r12d
0x1800d1580  mov     rdx, rdi; unsigned __int16 **
0x1800d1583  shl     rax, 5
0x1800d1587  mov     [rsp+78h+var_50], r15; unsigned int *
0x1800d158c  lea     ecx, [r15+1]; this
0x1800d1590  mov     ebx, r12d
0x1800d1593  mov     r9d, ecx; unsigned int
0x1800d1596  mov     [rsp+78h+var_58], ecx; unsigned int
0x1800d159a  mov     r8, [rax+r8+8]; unsigned __int16 *
0x1800d159f  call    ?SetAnyViaCopy@CSrTokenDL@@QEAAJPEAPEAGPEBGKKPEAK@Z; CSrTokenDL::SetAnyViaCopy(ushort * *,ushort const *,ulong,ulong,ulong *)
0x1800d15a4  mov     rcx, [rsp+78h+arg_8]
0x1800d15ac  lea     rax, [rbx+rbx*4]
0x1800d15b0  inc     ebp
0x1800d15b2  mov     [rsp+78h+var_40], ebp
0x1800d15b6  mov     cl, [rcx+rax*8+10h]
0x1800d15ba  mov     [rdi+10h], cl
0x1800d15bd  mov     [rdi+14h], r12d
0x1800d15c1  mov     [rdi+18h], r14d
0x1800d15c5  mov     [rdi+1Ch], r15d
0x1800d15c9  mov     dword ptr [rdi+20h], 1
0x1800d15d0  xor     edi, edi
0x1800d15d2  jmp     short loc_1800D15DE
0x1800d15d4  mov     ebp, [rsp+78h+var_40]
0x1800d15d8  mov     r14d, 1
0x1800d15de  mov     rcx, rsi; pv
0x1800d15e1  call    cs:__imp_CoTaskMemFree
0x1800d15e7  mov     eax, [rsp+78h+arg_10]
0x1800d15ee  add     r12d, r14d
0x1800d15f1  mov     r10d, [rsp+78h+arg_18]
0x1800d15f9  mov     ecx, [rsp+78h+var_3C]
0x1800d15fd  mov     r11, [rsp+78h+arg_8]
0x1800d1605  jmp     loc_1800D13C3
0x1800d160a  mov     rcx, rsi; pv
0x1800d160d  call    cs:__imp_CoTaskMemFree
0x1800d1613  mov     eax, 8007007Ah
0x1800d1618  jmp     short loc_1800D162D
0x1800d161a  mov     eax, 8007000Eh
0x1800d161f  jmp     short loc_1800D162D
0x1800d1621  mov     rcx, [rsp+78h+arg_30]
0x1800d1629  mov     eax, edi
0x1800d162b  mov     [rcx], ebp
0x1800d162d  mov     rbx, [rsp+78h+arg_0]
0x1800d1635  add     rsp, 40h
0x1800d1639  pop     r15
0x1800d163b  pop     r14
0x1800d163d  pop     r13
0x1800d163f  pop     r12
0x1800d1641  pop     rdi
0x1800d1642  pop     rsi
0x1800d1643  pop     rbp
0x1800d1644  retn
```
