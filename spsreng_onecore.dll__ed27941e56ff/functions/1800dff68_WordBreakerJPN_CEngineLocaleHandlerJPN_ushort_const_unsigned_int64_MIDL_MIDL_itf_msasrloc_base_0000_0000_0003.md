# WordBreakerJPN(CEngineLocaleHandlerJPN *,ushort const *,unsigned __int64,__MIDL___MIDL_itf_msasrloc_base_0000_0000_0003 *)

- ea: `0x1800dff68`
- end: `0x1800e022b`
- name: `?WordBreakerJPN@@YAJPEAVCEngineLocaleHandlerJPN@@PEBG_KPEAU__MIDL___MIDL_itf_msasrloc_base_0000_0000_0003@@@Z`
- size: `707`
- prototype: `__int64 __fastcall(struct CEngineLocaleHandlerJPN *, const unsigned __int16 *, unsigned __int64, struct __MIDL___MIDL_itf_msasrloc_base_0000_0000_0003 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800db098`

## callees

- `0x1800060c0`
- `0x1800141c0`
- `0x1800ddd08`
- `0x1800dff68`
- `0x1800e0234`
- `0x1800e0658`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e01b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e0203`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e01b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e0203`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e0079`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e0079`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WordBreakerJPN(
        struct CEngineLocaleHandlerJPN *a1,
        const unsigned __int16 *a2,
        unsigned __int64 a3,
        struct __MIDL___MIDL_itf_msasrloc_base_0000_0000_0003 *a4)
{
  int v5; // eax
  unsigned int v6; // edx
  DLPToken *v7; // rbx
  int v8; // r14d
  int v9; // esi
  unsigned __int64 v10; // r12
  int i; // r8d
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // r15
  unsigned __int64 v16; // r13
  char *v17; // rax
  char *v18; // rax
  unsigned __int16 *v19; // r15
  char *v20; // rax
  int v21; // r13d
  __int64 v22; // r10
  _QWORD *v23; // r11
  __int64 v24; // r9
  __int64 v25; // r8
  __int64 v26; // rcx
  _WORD *v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  int v30; // r15d
  int j; // esi
  void *v32; // rcx
  int v34; // [rsp+40h] [rbp-28h] BYREF
  int v35; // [rsp+44h] [rbp-24h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-20h] BYREF
  DLPToken *v37; // [rsp+50h] [rbp-18h] BYREF

  v35 = 0;
  v34 = 0;
  v37 = 0;
  pv = 0;
  v5 = WordBreakerJPNToDLPTokens(a1, a2, a3, &v35, &v34, &v37, (struct tagMORRSLT **)&pv);
  v7 = v37;
  v8 = v5;
  if ( v5 >= 0 )
  {
    if ( v37 )
    {
      v9 = v34;
      if ( v34 > 0 )
      {
        v10 = 5 * v34;
        for ( i = 0; i < v34; ++i )
        {
          v12 = -1;
          do
            ++v12;
          while ( *(_WORD *)(*((_QWORD *)v37 + 6 * i + 2) + 2 * v12) );
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)(*((_QWORD *)v37 + 6 * i + 3) + 2 * v13) );
          v14 = -1;
          do
            ++v14;
          while ( *(_WORD *)(*((_QWORD *)v37 + 6 * i + 4) + 2 * v14) );
          v10 += v14 + v12 + v13;
        }
        v37 = (DLPToken *)(8LL * v34);
        v15 = (2LL * v34 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        v16 = (2 * v10 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        v17 = (char *)CoTaskMemAlloc((SIZE_T)v37 + v15 + ((12LL * v34 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + v16);
        v6 = 0;
        if ( v17 )
        {
          *((_QWORD *)a4 + 5) = v17;
          *((_QWORD *)a4 + 3) = v17;
          v18 = &v17[v15];
          v19 = (unsigned __int16 *)((char *)v37 + (_QWORD)v18);
          *((_QWORD *)a4 + 2) = v18;
          *(_DWORD *)a4 = v9;
          *((_QWORD *)a4 + 1) = v19;
          v20 = (char *)v19 + v16;
          v21 = 0;
          *((_QWORD *)a4 + 4) = v20;
          while ( v21 < v9 )
          {
            v22 = *((_QWORD *)a4 + 4);
            v23 = pv;
            v24 = 3LL * v21;
            v25 = 48LL * v21;
            *(_WORD *)(*((_QWORD *)a4 + 3) + 2LL * v21) = *(_WORD *)((char *)v7 + v25 + 40);
            *(_QWORD *)(v22 + 4 * v24) = *(_QWORD *)((char *)v7 + v25);
            *(_DWORD *)(v22 + 4 * v24 + 8) = *(_DWORD *)((char *)v7 + v25 + 8);
            v26 = v23[3];
            if ( v26 )
            {
              *(_DWORD *)(v22 + 12LL * v21) = *(unsigned __int16 *)(v26 + 2LL * *(unsigned int *)((char *)v7 + v25));
              *(_WORD *)(v22 + 12LL * v21 + 4) = *(_WORD *)(v23[3]
                                                          + 2LL
                                                          * (*(_DWORD *)((char *)v7 + v25)
                                                           + (unsigned int)*(unsigned __int16 *)((char *)v7 + v25 + 4)))
                                               - *(_WORD *)(v22 + 12LL * v21);
            }
            *(_QWORD *)(*((_QWORD *)a4 + 2) + 8LL * v21) = v19;
            v27 = *(_WORD **)((char *)v7 + v25 + 24);
            v28 = *v27
                ? StringCchPrintfW(
                    v19,
                    v10,
                    L"/%s/%s/%s;",
                    *(_QWORD *)((char *)v7 + v25 + 16),
                    v27,
                    *(_QWORD *)((char *)v7 + v25 + 32))
                : StringCchCopyW(v19, v10, *(const unsigned __int16 **)((char *)v7 + v25 + 16));
            v6 = 0;
            v8 = v28;
            if ( v28 < 0 )
              break;
            v29 = -1;
            do
              ++v29;
            while ( v19[v29] );
            v10 += -1 - v29;
            v19 += v29 + 1;
            ++v21;
          }
        }
        else
        {
          v8 = -2147024882;
        }
      }
    }
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v7 )
  {
    v30 = v35;
    for ( j = 0; j < v30; ++j )
      DLPToken::clean((DLPToken *)((char *)v7 + 48 * j));
    DLPToken::`vector deleting destructor'(v7, v6);
  }
  if ( v8 < 0 )
  {
    v32 = (void *)*((_QWORD *)a4 + 5);
    if ( v32 )
      CoTaskMemFree(v32);
    *(_OWORD *)a4 = 0;
    *((_OWORD *)a4 + 1) = 0;
    *((_OWORD *)a4 + 2) = 0;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800dff68  push    rbp
0x1800dff6a  push    rbx
0x1800dff6b  push    rsi
0x1800dff6c  push    rdi
0x1800dff6d  push    r12
0x1800dff6f  push    r13
0x1800dff71  push    r14
0x1800dff73  push    r15
0x1800dff75  mov     rbp, rsp
0x1800dff78  sub     rsp, 68h
0x1800dff7c  xor     r13d, r13d
0x1800dff7f  lea     rax, [rbp+pv]
0x1800dff83  mov     [rsp+68h+var_38], rax; struct tagMORRSLT **
0x1800dff88  mov     rdi, r9
0x1800dff8b  lea     rax, [rbp+var_18]
0x1800dff8f  mov     [rbp+var_24], r13d
0x1800dff93  mov     [rsp+68h+var_40], rax; struct DLPToken **
0x1800dff98  lea     r9, [rbp+var_24]; int *
0x1800dff9c  lea     rax, [rbp+var_28]
0x1800dffa0  mov     [rbp+var_28], r13d
0x1800dffa4  mov     [rsp+68h+var_48], rax; int *
0x1800dffa9  mov     [rbp+var_18], r13
0x1800dffad  mov     [rbp+pv], r13
0x1800dffb1  call    ?WordBreakerJPNToDLPTokens@@YAJPEAVCEngineLocaleHandlerJPN@@PEBG_KPEAH3PEAPEAVDLPToken@@PEAPEAUtagMORRSLT@@@Z; WordBreakerJPNToDLPTokens(CEngineLocaleHandlerJPN *,ushort const *,unsigned __int64,int *,int *,DLPToken * *,tagMORRSLT * *)
0x1800dffb6  mov     rbx, [rbp+var_18]
0x1800dffba  mov     r14d, eax
0x1800dffbd  test    eax, eax
0x1800dffbf  js      loc_1800E01AB
0x1800dffc5  test    rbx, rbx
0x1800dffc8  jz      loc_1800E01AB
0x1800dffce  movsxd  rsi, [rbp+var_28]
0x1800dffd2  test    esi, esi
0x1800dffd4  jle     loc_1800E01AB
0x1800dffda  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800dffde  lea     eax, [rsi+rsi*4]
0x1800dffe1  movsxd  r12, eax
0x1800dffe4  mov     r8d, r13d
0x1800dffe7  test    esi, esi
0x1800dffe9  jle     short loc_1800E003C
0x1800dffeb  movsxd  rax, r8d
0x1800dffee  mov     rdx, r10
0x1800dfff1  lea     rcx, [rax+rax*2]
0x1800dfff5  add     rcx, rcx
0x1800dfff8  mov     rax, [rbx+rcx*8+10h]
0x1800dfffd  inc     rdx
0x1800e0000  cmp     [rax+rdx*2], r13w
0x1800e0005  jnz     short loc_1800DFFFD
0x1800e0007  mov     r9, [rbx+rcx*8+18h]
0x1800e000c  mov     rax, r10
0x1800e000f  inc     rax
0x1800e0012  cmp     [r9+rax*2], r13w
0x1800e0017  jnz     short loc_1800E000F
0x1800e0019  mov     r9, [rbx+rcx*8+20h]
0x1800e001e  mov     rcx, r10
0x1800e0021  inc     rcx
0x1800e0024  cmp     [r9+rcx*2], r13w
0x1800e0029  jnz     short loc_1800E0021
0x1800e002b  add     rax, rdx
0x1800e002e  inc     r8d
0x1800e0031  add     rax, rcx
0x1800e0034  add     r12, rax
0x1800e0037  cmp     r8d, esi
0x1800e003a  jl      short loc_1800DFFEB
0x1800e003c  lea     rdx, ds:0[rsi*8]
0x1800e0044  lea     rax, [rsi+rsi*2]
0x1800e0048  mov     [rbp+var_18], rdx
0x1800e004c  lea     rcx, ds:7[rax*4]
0x1800e0054  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800e0058  lea     r15, ds:7[rsi*2]
0x1800e0060  and     r15, 0FFFFFFFFFFFFFFF8h
0x1800e0064  lea     r13, ds:7[r12*2]
0x1800e006c  add     rcx, r15
0x1800e006f  and     r13, 0FFFFFFFFFFFFFFF8h
0x1800e0073  add     rcx, rdx
0x1800e0076  add     rcx, r13; cb
0x1800e0079  call    cs:__imp_CoTaskMemAlloc
0x1800e007f  xor     edx, edx
0x1800e0081  test    rax, rax
0x1800e0084  jz      loc_1800E01A2
0x1800e008a  mov     [rdi+28h], rax
0x1800e008e  mov     [rdi+18h], rax
0x1800e0092  add     rax, r15
0x1800e0095  mov     r15, [rbp+var_18]
0x1800e0099  add     r15, rax
0x1800e009c  mov     [rdi+10h], rax
0x1800e00a0  mov     [rdi], esi
0x1800e00a2  mov     [rdi+8], r15
0x1800e00a6  lea     rax, [r15+r13]
0x1800e00aa  mov     r13d, edx
0x1800e00ad  mov     [rdi+20h], rax
0x1800e00b1  cmp     r13d, esi
0x1800e00b4  jge     loc_1800E01A8
0x1800e00ba  mov     rcx, [rdi+18h]
0x1800e00be  xor     r14d, r14d
0x1800e00c1  mov     r10, [rdi+20h]
0x1800e00c5  mov     r11, [rbp+pv]
0x1800e00c9  movsxd  rdx, r13d
0x1800e00cc  lea     r9, [rdx+rdx*2]
0x1800e00d0  lea     r8, [rdx+rdx*2]
0x1800e00d4  shl     r8, 4
0x1800e00d8  movzx   eax, word ptr [r8+rbx+28h]
0x1800e00de  mov     [rcx+rdx*2], ax
0x1800e00e2  movsd   xmm0, qword ptr [r8+rbx]
0x1800e00e8  movsd   qword ptr [r10+r9*4], xmm0
0x1800e00ee  mov     eax, [r8+rbx+8]
0x1800e00f3  mov     [r10+r9*4+8], eax
0x1800e00f8  mov     rcx, [r11+18h]
0x1800e00fc  test    rcx, rcx
0x1800e00ff  jz      short loc_1800E012A
0x1800e0101  mov     eax, [r8+rbx]
0x1800e0105  movzx   ecx, word ptr [rcx+rax*2]
0x1800e0109  mov     [r10+r9*4], ecx
0x1800e010d  movzx   ecx, word ptr [r8+rbx+4]
0x1800e0113  add     ecx, [r8+rbx]
0x1800e0117  mov     rax, [r11+18h]
0x1800e011b  movzx   ecx, word ptr [rax+rcx*2]
0x1800e011f  sub     cx, [r10+r9*4]
0x1800e0124  mov     [r10+r9*4+4], cx
0x1800e012a  mov     rax, [rdi+10h]
0x1800e012e  mov     [rax+rdx*8], r15
0x1800e0132  mov     rdx, r12; unsigned __int64
0x1800e0135  mov     rcx, [r8+rbx+18h]
0x1800e013a  cmp     [rcx], r14w
0x1800e013e  jz      short loc_1800E0165
0x1800e0140  mov     rax, [r8+rbx+20h]
0x1800e0145  mov     r9, [r8+rbx+10h]
0x1800e014a  lea     r8, aSSS; "/%s/%s/%s;"
0x1800e0151  mov     [rsp+68h+var_40], rax
0x1800e0156  mov     [rsp+68h+var_48], rcx
0x1800e015b  mov     rcx, r15; unsigned __int16 *
0x1800e015e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e0163  jmp     short loc_1800E0172
0x1800e0165  mov     r8, [r8+rbx+10h]; unsigned __int16 *
0x1800e016a  mov     rcx, r15; unsigned __int16 *
0x1800e016d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800e0172  xor     edx, edx
0x1800e0174  mov     r14d, eax
0x1800e0177  test    eax, eax
0x1800e0179  js      short loc_1800E01A8
0x1800e017b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e017f  mov     rcx, rax
0x1800e0182  inc     rcx
0x1800e0185  cmp     [r15+rcx*2], dx
0x1800e018a  jnz     short loc_1800E0182
0x1800e018c  sub     rax, rcx
0x1800e018f  lea     r15, [r15+rcx*2]
0x1800e0193  add     r12, rax
0x1800e0196  add     r15, 2
0x1800e019a  inc     r13d
0x1800e019d  jmp     loc_1800E00B1
0x1800e01a2  mov     r14d, 8007000Eh
0x1800e01a8  xor     r13d, r13d
0x1800e01ab  mov     rax, [rbp+pv]
0x1800e01af  test    rax, rax
0x1800e01b2  jz      short loc_1800E01BD
0x1800e01b4  mov     rcx, rax; pv
0x1800e01b7  call    cs:__imp_CoTaskMemFree
0x1800e01bd  test    rbx, rbx
0x1800e01c0  jz      short loc_1800E01F5
0x1800e01c2  mov     r15d, [rbp+var_24]
0x1800e01c6  mov     esi, r13d
0x1800e01c9  test    r15d, r15d
0x1800e01cc  jle     short loc_1800E01E8
0x1800e01ce  movsxd  rax, esi
0x1800e01d1  lea     rcx, [rax+rax*2]
0x1800e01d5  shl     rcx, 4
0x1800e01d9  add     rcx, rbx; this
0x1800e01dc  call    ?clean@DLPToken@@QEAAXXZ; DLPToken::clean(void)
0x1800e01e1  inc     esi
0x1800e01e3  cmp     esi, r15d
0x1800e01e6  jl      short loc_1800E01CE
0x1800e01e8  test    rbx, rbx
0x1800e01eb  jz      short loc_1800E01F5
0x1800e01ed  mov     rcx, rbx; this
0x1800e01f0  call    ??_EDLPToken@@QEAAPEAXI@Z; DLPToken::`vector deleting destructor'(uint)
0x1800e01f5  test    r14d, r14d
0x1800e01f8  jns     short loc_1800E0217
0x1800e01fa  mov     rcx, [rdi+28h]; pv
0x1800e01fe  test    rcx, rcx
0x1800e0201  jz      short loc_1800E0209
0x1800e0203  call    cs:__imp_CoTaskMemFree
0x1800e0209  xorps   xmm0, xmm0
0x1800e020c  movups  xmmword ptr [rdi], xmm0
0x1800e020f  movups  xmmword ptr [rdi+10h], xmm0
0x1800e0213  movups  xmmword ptr [rdi+20h], xmm0
0x1800e0217  mov     eax, r14d
0x1800e021a  add     rsp, 68h
0x1800e021e  pop     r15
0x1800e0220  pop     r14
0x1800e0222  pop     r13
0x1800e0224  pop     r12
0x1800e0226  pop     rdi
0x1800e0227  pop     rsi
0x1800e0228  pop     rbx
0x1800e0229  pop     rbp
0x1800e022a  retn
```
