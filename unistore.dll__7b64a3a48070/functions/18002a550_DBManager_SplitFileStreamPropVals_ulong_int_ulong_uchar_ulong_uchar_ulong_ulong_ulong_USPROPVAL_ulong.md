# DBManager::SplitFileStreamPropVals(ulong,int,ulong,uchar *,ulong *,uchar * *,ulong * *,ulong *,ulong *,_USPROPVAL * *,ulong * *)

- ea: `0x18002a550`
- end: `0x18002ac0b`
- name: `?SplitFileStreamPropVals@DBManager@@SAJKHKPEAEPEAKPEAPEAEPEAPEAK11PEAPEAU_USPROPVAL@@3@Z`
- size: `1723`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, int@<edx>, unsigned int@<r8d>, unsigned __int8 *@<r9>, unsigned int *, unsigned __int8 **, unsigned int **, unsigned int *, unsigned int *, struct _USPROPVAL **, unsigned int **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x180029c10`

## callees

- `0x1800068f0`
- `0x180029be0`
- `0x18002a550`
- `0x18004e8f8`
- `0x18006f180`
- `0x180078a40`
- `0x180078a8c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a7e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a962`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a96b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a979`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a987`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a7e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a962`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a96b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a979`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a987`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a656`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a674`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a918`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a934`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002aa5f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a656`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a674`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a918`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a934`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002aa5f`

## string_xrefs

- `0x18002a755`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18002a771`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18002a94c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18002a9ff`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18002aa28`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18002aabd`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18002abd0`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18002abee`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBManager::SplitFileStreamPropVals(
        unsigned int a1,
        int a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int *a5,
        unsigned __int8 **a6,
        unsigned int **a7,
        unsigned int *a8,
        unsigned int *a9,
        struct _USPROPVAL **a10,
        unsigned int **a11)
{
  __int64 v11; // r14
  int v12; // ebx
  __int64 v13; // rdi
  __int64 v14; // rsi
  unsigned int v16; // r13d
  __int64 v17; // r11
  unsigned __int16 **v18; // r12
  int v19; // eax
  __int64 v20; // r12
  unsigned __int8 *v21; // rbx
  unsigned __int8 *v22; // rdi
  __int64 v23; // rcx
  unsigned int *v24; // r15
  struct _USPROPVAL *v25; // rsi
  unsigned int *v26; // r14
  unsigned int v27; // edx
  __int64 v28; // r8
  unsigned int v29; // ebp
  __int64 v30; // r13
  int v31; // r9d
  unsigned __int8 *v32; // r10
  __int64 v33; // rax
  unsigned __int8 *v34; // rcx
  int v36; // eax
  __int64 v37; // r8
  int v38; // r9d
  int i; // edx
  __int64 v40; // r8
  int v41; // r9d
  int j; // eax
  __int64 v43; // rax
  __int64 v44; // r9
  __int64 v45; // r15
  unsigned __int8 *v46; // r9
  __int64 v47; // rdx
  __int64 v48; // rax
  unsigned __int8 *v49; // r15
  unsigned int StreamValidProp; // eax
  unsigned int v51; // eax
  __int64 v52; // rax
  unsigned __int8 *v53; // r15
  unsigned __int8 *v54; // rbp
  unsigned int v55; // eax
  unsigned int v56; // eax
  unsigned int v57; // [rsp+30h] [rbp-68h]
  int v58; // [rsp+34h] [rbp-64h]
  int v59; // [rsp+38h] [rbp-60h]
  unsigned int v60; // [rsp+40h] [rbp-58h]
  int v61; // [rsp+48h] [rbp-50h]
  _DWORD *Block; // [rsp+50h] [rbp-48h]
  unsigned int *v63; // [rsp+58h] [rbp-40h]

  v11 = a1;
  v12 = a2;
  v13 = a3;
  v14 = a3;
  Block = operator new[](saturated_mul(a3, 4u));
  if ( Block )
  {
    v16 = 0;
    v57 = 0;
    if ( (_DWORD)v13 )
    {
      v17 = 0;
      v18 = &(&g_rgTableInfo)[12 * v11];
      if ( v12 )
      {
        do
        {
          if ( (unsigned __int16)*(_DWORD *)&a4[40 * v17] == 100 && (unsigned int)IsFileStreamSupportedInTable(v11) )
          {
            for ( i = 0; i < *((unsigned __int16 *)v18 + 6); ++i )
            {
              if ( v38 == *(_DWORD *)(32LL * i + *(_QWORD *)(v37 + 16) + 4) )
                goto LABEL_5;
            }
            v19 = 0;
          }
          else
          {
LABEL_5:
            ++v16;
            v19 = 1;
          }
          Block[v17] = v19;
          v17 = (unsigned int)(v17 + 1);
        }
        while ( (unsigned int)v17 < (unsigned int)v13 );
      }
      else
      {
        do
        {
          if ( (unsigned __int16)*(_DWORD *)&a4[24 * v17] == 100 && (unsigned int)IsFileStreamSupportedInTable(v11) )
          {
            for ( j = 0; j < *((unsigned __int16 *)v18 + 6); ++j )
            {
              if ( v41 == *(_DWORD *)(32LL * j + *(_QWORD *)(v40 + 16) + 4) )
                goto LABEL_33;
            }
            v36 = 0;
          }
          else
          {
LABEL_33:
            ++v16;
            v36 = 1;
          }
          Block[v17] = v36;
          v17 = (unsigned int)(v17 + 1);
        }
        while ( (unsigned int)v17 < (unsigned int)v13 );
      }
      v12 = a2;
      v57 = v16;
    }
    v20 = (unsigned int)v13 - v16;
    v61 = v13 - v16;
    if ( (_DWORD)v13 == v16 )
    {
      *a5 = v16;
      *a8 = v16;
      *a9 = 0;
    }
    if ( v12 )
    {
      v22 = (unsigned __int8 *)LocalAlloc(0x40u, 40 * v13);
      if ( v22 )
      {
        v21 = 0;
        goto LABEL_13;
      }
      v44 = 2968;
    }
    else
    {
      v21 = (unsigned __int8 *)LocalAlloc(0, 24 * v13);
      if ( v21 )
      {
        v22 = 0;
LABEL_13:
        v63 = (unsigned int *)LocalAlloc(0, 4 * v14);
        v24 = v63;
        if ( v63 )
        {
          v25 = 0;
          v26 = 0;
          if ( !(_DWORD)v20 )
            goto LABEL_15;
          v25 = (struct _USPROPVAL *)LocalAlloc(0, 24 * v20);
          if ( v25 )
          {
            v26 = (unsigned int *)LocalAlloc(0, 4 * v20);
            if ( v26 )
            {
LABEL_15:
              v27 = 0;
              v28 = 0;
              v29 = 0;
              v59 = 0;
              v58 = 0;
              v60 = 0;
              if ( a3 )
              {
                v30 = 0;
                v31 = a2;
                v32 = a4;
                do
                {
                  if ( Block[v30] )
                  {
                    v24[v27] = v29;
                    if ( v31 )
                    {
                      v43 = 5LL * v27;
                      *(_OWORD *)&v22[8 * v43] = *(_OWORD *)&v32[40 * v30];
                      *(_OWORD *)&v22[8 * v43 + 16] = *(_OWORD *)&v32[40 * v30 + 16];
                      *(_QWORD *)&v22[8 * v43 + 32] = *(_QWORD *)&v32[40 * v30 + 32];
                    }
                    else
                    {
                      v32 = a4;
                      v33 = 3LL * v27;
                      *(_OWORD *)&v21[8 * v33] = *(_OWORD *)&a4[24 * v30];
                      *(_QWORD *)&v21[8 * v33 + 16] = *(_QWORD *)&a4[24 * v30 + 16];
                    }
                    v59 = ++v27;
                  }
                  else
                  {
                    v45 = (unsigned int)v28;
                    v26[v28] = v29;
                    if ( v31 )
                    {
                      v46 = a4;
                      v47 = 40 * v30;
                      if ( (*(_WORD *)&a4[40 * v30 + 6] & 0x800) != 0 )
                      {
                        Log_AssertionEvent(
                          2048,
                          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                          3016);
                        LODWORD(v28) = v58;
                        v47 = 40 * v30;
                        v46 = a4;
                      }
                      v48 = 3 * v45;
                      *(_OWORD *)((char *)v25 + 8 * v48) = *(_OWORD *)&v46[v47];
                      *((_QWORD *)v25 + v48 + 2) = *(_QWORD *)&v46[v47 + 16];
                      v49 = &v22[40 * v57 + 40 * (unsigned int)v28];
                      StreamValidProp = GetStreamValidProp(*(_DWORD *)&v46[v47]);
                      v32 = a4;
                      *(_DWORD *)v49 = StreamValidProp;
                      *((_WORD *)v49 + 3) = 0;
                      v51 = *(unsigned __int16 *)&a4[40 * v30 + 6];
                      LOWORD(v51) = ~(_WORD)v51;
                      *((_DWORD *)v49 + 2) = (v51 >> 9) & 1;
                    }
                    else
                    {
                      v52 = 3 * v28;
                      v53 = &a4[24 * v30];
                      *(_OWORD *)((char *)v25 + 8 * v52) = *(_OWORD *)v53;
                      *((_QWORD *)v25 + v52 + 2) = *((_QWORD *)v53 + 2);
                      v54 = &v21[24 * v57 + 24 * (unsigned int)v28];
                      v55 = GetStreamValidProp(*(_DWORD *)v53);
                      v32 = a4;
                      *(_DWORD *)v54 = v55;
                      *((_WORD *)v54 + 3) = 0;
                      v56 = *((unsigned __int16 *)v53 + 3);
                      LOWORD(v56) = ~(_WORD)v56;
                      *((_DWORD *)v54 + 2) = (v56 >> 9) & 1;
                      v29 = v60;
                    }
                    v24 = v63;
                    v28 = (unsigned int)(v58 + 1);
                    v27 = v59;
                    v31 = a2;
                    ++v58;
                  }
                  ++v29;
                  ++v30;
                  v23 = 2048;
                  v60 = v29;
                }
                while ( v29 < a3 );
                LODWORD(v20) = v61;
                v16 = v57;
              }
              if ( v27 != v16 )
              {
                Log_AssertionEvent(
                  v23,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                  3042);
                LODWORD(v28) = v58;
              }
              if ( (_DWORD)v28 != (_DWORD)v20 )
                Log_AssertionEvent(
                  v23,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                  3043);
              *a5 = a3;
              if ( a2 )
              {
                *a6 = v22;
                *a7 = v24;
                *a8 = v16;
                *a9 = v20;
                *a10 = v25;
                *a11 = v26;
                if ( !v21 )
                  goto LABEL_31;
                v34 = v21;
              }
              else
              {
                *a6 = v21;
                *a7 = v24;
                *a8 = v16;
                *a9 = v20;
                *a10 = v25;
                *a11 = v26;
                if ( !v22 )
                {
LABEL_31:
                  operator delete(Block);
                  return 0;
                }
                v34 = v22;
              }
              LocalFree(v34);
              goto LABEL_31;
            }
            Log_UnistoreHREvent_0(
              2147942414LL,
              0,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
              2985);
            LocalFree(v25);
            LocalFree(v63);
            if ( v22 )
              goto LABEL_51;
          }
          else
          {
            Log_UnistoreHREvent_0(
              2147942414LL,
              0,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
              2982);
            LocalFree(v63);
            if ( v22 )
LABEL_51:
              LocalFree(v22);
          }
          if ( v21 )
          {
LABEL_53:
            LocalFree(v21);
            operator delete(Block);
            return 2147942414LL;
          }
          goto LABEL_58;
        }
        Log_UnistoreHREvent_0(
          2147942414LL,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          2977);
        if ( v22 )
          LocalFree(v22);
        if ( v21 )
          goto LABEL_53;
LABEL_58:
        operator delete(Block);
        return 2147942414LL;
      }
      v44 = 2973;
    }
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v44);
    goto LABEL_58;
  }
  Log_UnistoreHREvent_0(
    2147942414LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
    2914);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18002a550  mov     [rsp+arg_18], r9
0x18002a555  mov     [rsp+arg_10], r8d
0x18002a55a  mov     [rsp+arg_8], edx
0x18002a55e  push    rbx
0x18002a55f  push    rbp
0x18002a560  push    rsi
0x18002a561  push    rdi
0x18002a562  push    r14
0x18002a564  push    r15
0x18002a566  sub     rsp, 68h
0x18002a56a  mov     r14d, ecx
0x18002a56d  mov     ebx, edx
0x18002a56f  mov     edi, r8d
0x18002a572  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002a579  mov     eax, 4
0x18002a57e  mov     esi, r8d
0x18002a581  mul     rdi
0x18002a584  mov     r15, r9
0x18002a587  cmovb   rax, rcx
0x18002a58b  mov     rcx, rax; unsigned __int64
0x18002a58e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002a593  mov     [rsp+98h+Block], rax
0x18002a598  mov     rbp, rax
0x18002a59b  test    rax, rax
0x18002a59e  jz      loc_18002ABE8
0x18002a5a4  mov     [rsp+98h+arg_0], r12
0x18002a5ac  mov     [rsp+98h+var_38], r13
0x18002a5b1  xor     r13d, r13d
0x18002a5b4  mov     [rsp+98h+var_68], r13d
0x18002a5b9  test    edi, edi
0x18002a5bb  jz      short loc_18002A613
0x18002a5bd  lea     rax, ?g_rgTableInfo@@3QBUUSTableInfo@@B; USTableInfo const near * const g_rgTableInfo
0x18002a5c4  xor     r11d, r11d
0x18002a5c7  lea     rdx, [r14+r14*2]
0x18002a5cb  shl     rdx, 5
0x18002a5cf  lea     r12, [rdx+rax]
0x18002a5d3  lea     r8, [rdx+rax]
0x18002a5d7  test    ebx, ebx
0x18002a5d9  jz      loc_18002A820
0x18002a5df  lea     rax, [r11+r11*4]
0x18002a5e3  mov     r9d, [r15+rax*8]
0x18002a5e7  cmp     r9w, 64h ; 'd'
0x18002a5ec  jz      loc_18002A849
0x18002a5f2  inc     r13d
0x18002a5f5  mov     eax, 1
0x18002a5fa  mov     [rbp+r11*4+0], eax
0x18002a5ff  inc     r11d
0x18002a602  cmp     r11d, edi
0x18002a605  jb      short loc_18002A5DF
0x18002a607  mov     ebx, [rsp+98h+arg_8]
0x18002a60e  mov     [rsp+98h+var_68], r13d
0x18002a613  mov     r12d, edi
0x18002a616  sub     r12d, r13d
0x18002a619  mov     [rsp+98h+var_50], r12d
0x18002a61e  jnz     short loc_18002A644
0x18002a620  mov     rax, [rsp+98h+arg_20]
0x18002a628  mov     [rax], r13d
0x18002a62b  mov     rax, [rsp+98h+arg_38]
0x18002a633  mov     [rax], r13d
0x18002a636  mov     rax, [rsp+98h+arg_40]
0x18002a63e  mov     dword ptr [rax], 0
0x18002a644  test    ebx, ebx
0x18002a646  jnz     loc_18002AA52
0x18002a64c  lea     rdx, [rdi+rdi*2]
0x18002a650  xor     ecx, ecx; uFlags
0x18002a652  shl     rdx, 3; uBytes
0x18002a656  call    cs:__imp_LocalAlloc
0x18002a65c  mov     rbx, rax
0x18002a65f  test    rax, rax
0x18002a662  jz      loc_18002ABCA
0x18002a668  xor     edi, edi
0x18002a66a  lea     rdx, ds:0[rsi*4]; uBytes
0x18002a672  xor     ecx, ecx; uFlags
0x18002a674  call    cs:__imp_LocalAlloc
0x18002a67a  mov     [rsp+98h+var_40], rax
0x18002a67f  mov     r15, rax
0x18002a682  test    rax, rax
0x18002a685  jz      loc_18002A9F9
0x18002a68b  xor     esi, esi
0x18002a68d  xor     r14d, r14d
0x18002a690  test    r12d, r12d
0x18002a693  jnz     loc_18002A90E
0x18002a699  xor     edx, edx
0x18002a69b  xor     r8d, r8d
0x18002a69e  xor     ebp, ebp
0x18002a6a0  mov     [rsp+98h+var_60], edx
0x18002a6a4  mov     [rsp+98h+var_64], r8d
0x18002a6a9  mov     dword ptr [rsp+98h+var_58], ebp
0x18002a6ad  cmp     [rsp+98h+arg_10], edx
0x18002a6b4  jbe     loc_18002A74A
0x18002a6ba  mov     r12d, [rsp+98h+var_68]
0x18002a6bf  xor     r13d, r13d
0x18002a6c2  mov     r9d, [rsp+98h+arg_8]
0x18002a6ca  mov     ecx, 800h
0x18002a6cf  mov     r10, [rsp+98h+arg_18]
0x18002a6d7  mov     rax, [rsp+98h+Block]
0x18002a6dc  cmp     dword ptr [rax+r13*4], 0
0x18002a6e1  jz      loc_18002AA7F
0x18002a6e7  mov     eax, edx
0x18002a6e9  mov     [r15+rax*4], ebp
0x18002a6ed  test    r9d, r9d
0x18002a6f0  jnz     loc_18002A99F
0x18002a6f6  mov     r10, [rsp+98h+arg_18]
0x18002a6fe  lea     rax, [rax+rax*2]
0x18002a702  lea     rcx, ds:0[r13*2]
0x18002a70a  add     rcx, r13
0x18002a70d  movups  xmm0, xmmword ptr [r10+rcx*8]
0x18002a712  movups  xmmword ptr [rbx+rax*8], xmm0
0x18002a716  movsd   xmm1, qword ptr [r10+rcx*8+10h]
0x18002a71d  movsd   qword ptr [rbx+rax*8+10h], xmm1
0x18002a723  inc     edx
0x18002a725  mov     [rsp+98h+var_60], edx
0x18002a729  inc     ebp
0x18002a72b  inc     r13
0x18002a72e  mov     ecx, 800h
0x18002a733  mov     dword ptr [rsp+98h+var_58], ebp
0x18002a737  cmp     ebp, [rsp+98h+arg_10]
0x18002a73e  jb      short loc_18002A6D7
0x18002a740  mov     r12d, [rsp+98h+var_50]
0x18002a745  mov     r13d, [rsp+98h+var_68]
0x18002a74a  cmp     edx, r13d
0x18002a74d  jz      short loc_18002A766
0x18002a74f  mov     r8d, 0BE2h
0x18002a755  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002a75c  call    Log_AssertionEvent
0x18002a761  mov     r8d, [rsp+98h+var_64]
0x18002a766  cmp     r8d, r12d
0x18002a769  jz      short loc_18002A77D
0x18002a76b  mov     r8d, 0BE3h
0x18002a771  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002a778  call    Log_AssertionEvent
0x18002a77d  cmp     [rsp+98h+arg_8], 0
0x18002a785  mov     rax, [rsp+98h+arg_20]
0x18002a78d  mov     ecx, [rsp+98h+arg_10]
0x18002a794  mov     [rax], ecx
0x18002a796  mov     rax, [rsp+98h+arg_28]
0x18002a79e  jnz     loc_18002A8C3
0x18002a7a4  mov     [rax], rbx
0x18002a7a7  mov     rax, [rsp+98h+arg_30]
0x18002a7af  mov     [rax], r15
0x18002a7b2  mov     rax, [rsp+98h+arg_38]
0x18002a7ba  mov     [rax], r13d
0x18002a7bd  mov     rax, [rsp+98h+arg_40]
0x18002a7c5  mov     [rax], r12d
0x18002a7c8  mov     rax, [rsp+98h+arg_48]
0x18002a7d0  mov     [rax], rsi
0x18002a7d3  mov     rax, [rsp+98h+arg_50]
0x18002a7db  mov     [rax], r14
0x18002a7de  test    rdi, rdi
0x18002a7e1  jz      short loc_18002A7EC
0x18002a7e3  mov     rcx, rdi; hMem
0x18002a7e6  call    cs:__imp_LocalFree
0x18002a7ec  mov     rcx, [rsp+98h+Block]; Block
0x18002a7f1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002a7f6  xor     eax, eax
0x18002a7f8  mov     r12, [rsp+98h+arg_0]
0x18002a800  mov     r13, [rsp+98h+var_38]
0x18002a805  add     rsp, 68h
0x18002a809  pop     r15
0x18002a80b  pop     r14
0x18002a80d  pop     rdi
0x18002a80e  pop     rsi
0x18002a80f  pop     rbp
0x18002a810  pop     rbx
0x18002a811  retn
0x18002a820  lea     rax, [r11+r11*2]
0x18002a824  mov     r9d, [r15+rax*8]
0x18002a828  cmp     r9w, 64h ; 'd'
0x18002a82d  jz      short loc_18002A884
0x18002a82f  inc     r13d
0x18002a832  mov     eax, 1
0x18002a837  mov     [rbp+r11*4+0], eax
0x18002a83c  inc     r11d
0x18002a83f  cmp     r11d, edi
0x18002a842  jb      short loc_18002A820
0x18002a844  jmp     loc_18002A607
0x18002a849  mov     ecx, r14d; unsigned int
0x18002a84c  call    ?IsFileStreamSupportedInTable@@YAHK@Z; IsFileStreamSupportedInTable(ulong)
0x18002a851  test    eax, eax
0x18002a853  jz      loc_18002A5F2
0x18002a859  movzx   r10d, word ptr [r12+0Ch]
0x18002a85f  xor     edx, edx
0x18002a861  cmp     edx, r10d
0x18002a864  jge     loc_18002A9D4
0x18002a86a  mov     rax, [r8+10h]
0x18002a86e  movsxd  rcx, edx
0x18002a871  shl     rcx, 5
0x18002a875  cmp     r9d, [rcx+rax+4]
0x18002a87a  jz      loc_18002A5F2
0x18002a880  inc     edx
0x18002a882  jmp     short loc_18002A861
0x18002a884  mov     ecx, r14d; unsigned int
0x18002a887  call    ?IsFileStreamSupportedInTable@@YAHK@Z; IsFileStreamSupportedInTable(ulong)
0x18002a88c  test    eax, eax
0x18002a88e  jz      short loc_18002A82F
0x18002a890  movzx   r10d, word ptr [r12+0Ch]
0x18002a896  xor     eax, eax
0x18002a898  nop     dword ptr [rax+rax+00000000h]
0x18002a8a0  cmp     eax, r10d
0x18002a8a3  jge     loc_18002A9DB
0x18002a8a9  mov     rcx, [r8+10h]
0x18002a8ad  movsxd  rdx, eax
0x18002a8b0  shl     rdx, 5
0x18002a8b4  cmp     r9d, [rdx+rcx+4]
0x18002a8b9  jz      loc_18002A82F
0x18002a8bf  inc     eax
0x18002a8c1  jmp     short loc_18002A8A0
0x18002a8c3  mov     [rax], rdi
0x18002a8c6  mov     rax, [rsp+98h+arg_30]
0x18002a8ce  mov     [rax], r15
0x18002a8d1  mov     rax, [rsp+98h+arg_38]
0x18002a8d9  mov     [rax], r13d
0x18002a8dc  mov     rax, [rsp+98h+arg_40]
0x18002a8e4  mov     [rax], r12d
0x18002a8e7  mov     rax, [rsp+98h+arg_48]
0x18002a8ef  mov     [rax], rsi
0x18002a8f2  mov     rax, [rsp+98h+arg_50]
0x18002a8fa  mov     [rax], r14
0x18002a8fd  test    rbx, rbx
0x18002a900  jz      loc_18002A7EC
0x18002a906  mov     rcx, rbx
0x18002a909  jmp     loc_18002A7E6
0x18002a90e  lea     rdx, [r12+r12*2]
0x18002a912  xor     ecx, ecx; uFlags
0x18002a914  shl     rdx, 3; uBytes
0x18002a918  call    cs:__imp_LocalAlloc
0x18002a91e  mov     rsi, rax
0x18002a921  test    rax, rax
0x18002a924  jz      loc_18002AA22
0x18002a92a  lea     rdx, ds:0[r12*4]; uBytes
0x18002a932  xor     ecx, ecx; uFlags
0x18002a934  call    cs:__imp_LocalAlloc
0x18002a93a  mov     r14, rax
0x18002a93d  test    rax, rax
0x18002a940  jnz     loc_18002A699
0x18002a946  mov     r9d, 0BA9h
0x18002a94c  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002a953  xor     edx, edx
0x18002a955  mov     ecx, 8007000Eh
0x18002a95a  call    Log_UnistoreHREvent_0
0x18002a95f  mov     rcx, rsi; hMem
0x18002a962  call    cs:__imp_LocalFree
0x18002a968  mov     rcx, r15; hMem
0x18002a96b  call    cs:__imp_LocalFree
0x18002a971  test    rdi, rdi
0x18002a974  jz      short loc_18002A97F
0x18002a976  mov     rcx, rdi; hMem
0x18002a979  call    cs:__imp_LocalFree
0x18002a97f  test    rbx, rbx
0x18002a982  jz      short loc_18002A9E7
0x18002a984  mov     rcx, rbx; hMem
0x18002a987  call    cs:__imp_LocalFree
0x18002a98d  mov     rcx, rbp; Block
0x18002a990  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002a995  mov     eax, 8007000Eh
0x18002a99a  jmp     loc_18002A7F8
0x18002a99f  lea     rax, [rax+rax*4]
0x18002a9a3  lea     rcx, ds:0[r13*4]
0x18002a9ab  add     rcx, r13
0x18002a9ae  movups  xmm0, xmmword ptr [r10+rcx*8]
0x18002a9b3  movups  xmmword ptr [rdi+rax*8], xmm0
0x18002a9b7  movups  xmm1, xmmword ptr [r10+rcx*8+10h]
0x18002a9bd  movups  xmmword ptr [rdi+rax*8+10h], xmm1
0x18002a9c2  movsd   xmm0, qword ptr [r10+rcx*8+20h]
0x18002a9c9  movsd   qword ptr [rdi+rax*8+20h], xmm0
0x18002a9cf  jmp     loc_18002A723
0x18002a9d4  xor     eax, eax
0x18002a9d6  jmp     loc_18002A5FA
0x18002a9db  xor     eax, eax
0x18002a9dd  jmp     loc_18002A837
0x18002a9e2  test    rbx, rbx
0x18002a9e5  jnz     short loc_18002A984
0x18002a9e7  mov     rcx, rbp; Block
0x18002a9ea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002a9ef  mov     eax, 8007000Eh
0x18002a9f4  jmp     loc_18002A7F8
0x18002a9f9  mov     r9d, 0BA1h
0x18002a9ff  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002aa06  xor     edx, edx
0x18002aa08  mov     ecx, 8007000Eh
0x18002aa0d  call    Log_UnistoreHREvent_0
0x18002aa12  test    rdi, rdi
0x18002aa15  jz      short loc_18002A9E2
0x18002aa17  mov     rcx, rdi; hMem
0x18002aa1a  call    cs:__imp_LocalFree
0x18002aa20  jmp     short loc_18002A9E2
0x18002aa22  mov     r9d, 0BA6h
0x18002aa28  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002aa2f  xor     edx, edx
0x18002aa31  mov     ecx, 8007000Eh
0x18002aa36  call    Log_UnistoreHREvent_0
0x18002aa3b  mov     rcx, r15; hMem
0x18002aa3e  call    cs:__imp_LocalFree
0x18002aa44  test    rdi, rdi
0x18002aa47  jz      loc_18002A97F
0x18002aa4d  jmp     loc_18002A976
0x18002aa52  lea     rdx, [rdi+rdi*4]
0x18002aa56  mov     ecx, 40h ; '@'; uFlags
0x18002aa5b  shl     rdx, 3; uBytes
0x18002aa5f  call    cs:__imp_LocalAlloc
  ... truncated ...
```
