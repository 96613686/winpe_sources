# RtlpCreateFunctionOverrideFixupInfo(gsl::span<uchar const,-1>,ulong,ulong,_RTL_FUNCTION_OVERRIDE_CAPABILITIES const *,_RTL_FUNCTION_OVERRIDE_INFORMATION * *,_RTL_SYSTEM_OVERRIDE_INFORMATION const *)

- ea: `0x1400da5b4`
- end: `0x1400daa05`
- name: `?RtlpCreateFunctionOverrideFixupInfo@@YAJV?$span@$$CBE$0?0@gsl@@KKPEBU_RTL_FUNCTION_OVERRIDE_CAPABILITIES@@PEAPEAU_RTL_FUNCTION_OVERRIDE_INFORMATION@@PEBU_RTL_SYSTEM_OVERRIDE_INFORMATION@@@Z`
- size: `1105`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1400dbb60`
- `0x1400dbcfc`

## callees

- `0x14000f0f0`
- `0x140037e68`
- `0x1400da348`
- `0x1400da5b4`
- `0x1400dafc4`
- `0x1400db154`
- `0x1400db6a8`
- `0x1400db73c`
- `0x1400db778`
- `0x1400dbde0`

## pseudocode

```c
__int64 __fastcall RtlpCreateFunctionOverrideFixupInfo(
        unsigned __int64 *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        struct _RTL_FUNCTION_OVERRIDE_INFORMATION **a5,
        __int64 a6)
{
  unsigned __int64 v6; // r10
  struct _RTL_FUNCTION_OVERRIDE_INFORMATION *v7; // r12
  unsigned int *v9; // rax
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // r14
  struct _RTL_FUNCTION_OVERRIDE_INFORMATION *v13; // rdx
  unsigned int *v14; // r13
  unsigned __int64 v15; // rsi
  __int64 Pool; // rax
  int v17; // ebx
  unsigned __int64 v18; // rdi
  unsigned int *v19; // r15
  unsigned int *v20; // r11
  unsigned int i; // eax
  __int64 v22; // rdx
  __int64 v23; // r11
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rdi
  unsigned int v26; // edx
  __int64 v27; // r11
  unsigned __int64 v28; // rax
  __int64 v29; // r15
  bool v30; // zf
  char *v31; // rax
  __int64 v32; // rdi
  int v33; // eax
  unsigned __int64 v34; // rdi
  unsigned int *v35; // r15
  unsigned int *v36; // rsi
  unsigned __int64 v37; // rdx
  unsigned __int64 v38; // r13
  unsigned __int64 v39; // rax
  unsigned int v40; // eax
  int v41; // r14d
  unsigned int *v42; // rcx
  __int64 v43; // r8
  __int64 v45; // [rsp+48h] [rbp-79h]
  __int64 v46; // [rsp+48h] [rbp-79h]
  unsigned __int64 v47; // [rsp+48h] [rbp-79h]
  unsigned int *v48; // [rsp+50h] [rbp-71h]
  __int64 v49; // [rsp+58h] [rbp-69h] BYREF
  unsigned int *v50; // [rsp+60h] [rbp-61h]
  unsigned __int64 v51; // [rsp+68h] [rbp-59h] BYREF
  char *v52; // [rsp+70h] [rbp-51h]
  __int64 v53; // [rsp+78h] [rbp-49h]
  struct _RTL_FUNCTION_OVERRIDE_INFORMATION *v54[2]; // [rsp+88h] [rbp-39h] BYREF
  __int64 v55; // [rsp+98h] [rbp-29h] BYREF
  unsigned __int64 v56; // [rsp+A0h] [rbp-21h]
  __int64 v57; // [rsp+A8h] [rbp-19h]
  __int128 v58; // [rsp+B0h] [rbp-11h]
  struct _RTL_FUNCTION_OVERRIDE_INFORMATION *v59; // [rsp+C0h] [rbp-1h]
  unsigned int v60; // [rsp+118h] [rbp+57h]
  struct _RTL_FUNCTION_OVERRIDE_INFORMATION *v61; // [rsp+118h] [rbp+57h]

  v6 = *a1;
  v55 = 0;
  v7 = 0;
  v54[0] = 0;
  v53 = 0;
  *a5 = 0;
  v58 = 0;
  if ( v6 >= 4 )
  {
    v9 = (unsigned int *)a1[1];
    v10 = v6 - 4;
    if ( v9 )
    {
      v11 = *v9;
      if ( (_DWORD)v11 )
      {
        v12 = (unsigned int)v11;
        if ( v11 < v10 )
        {
          v13 = (struct _RTL_FUNCTION_OVERRIDE_INFORMATION *)(v10 - v11);
          v14 = v9 + 1;
          v59 = v13;
          if ( v13 == (struct _RTL_FUNCTION_OVERRIDE_INFORMATION *)-1LL || v9 == (unsigned int *)-4LL )
            goto LABEL_62;
          if ( v13 )
          {
            v15 = (unsigned __int64)a2 >> 12;
            Pool = SkAllocatePool(512, 8 * v15);
            v53 = Pool;
            if ( !Pool )
              return (unsigned int)-1073741801;
            if ( v15 <= 2 * v15 )
            {
              LODWORD(v55) = 0;
              v56 = v15;
              v57 = Pool;
              if ( v12 < 0x10 )
              {
                v18 = v12;
                v48 = v14;
                v19 = v14;
                v20 = 0;
              }
              else
              {
                v18 = v12 - 16;
                v19 = v14 + 4;
                v48 = v14 + 4;
                v20 = v14;
              }
              for ( i = 0; ; i = v60 + 1 )
              {
                v60 = i;
                if ( !v20 )
                  break;
                v49 = 1;
                v50 = v20;
                v17 = RtlpValidateRvasWithinImage(a2, a3, &v49);
                if ( v17 < 0 )
                  goto LABEL_64;
                v24 = *(unsigned int *)(v23 + 8);
                if ( !(_DWORD)v24 )
                  goto LABEL_63;
                if ( (v24 & 3) != 0 )
                  goto LABEL_63;
                v45 = *(unsigned int *)(v23 + 8);
                v11 = (unsigned int)v24;
                if ( v24 > v18 )
                  goto LABEL_63;
                if ( !v19 )
                  goto LABEL_62;
                if ( (v24 & 3) != 0 )
                  goto LABEL_62;
                v25 = v18 - (unsigned int)v24;
                v49 = v24 >> 2;
                v50 = v19;
                if ( v25 == -1 )
                  goto LABEL_62;
                v17 = RtlpValidateRvasWithinImage(a2, v22, &v49);
                if ( v17 < 0 )
                  goto LABEL_64;
                v28 = *(unsigned int *)(v27 + 12);
                if ( !(_DWORD)v28 )
                  goto LABEL_63;
                if ( (v28 & 3) != 0 )
                  goto LABEL_63;
                v29 = (unsigned int)v28;
                if ( v28 > v25 )
                  goto LABEL_63;
                v30 = (unsigned int *)((char *)v48 + v45) == 0;
                v31 = (char *)v48 + v45;
                v46 = (__int64)v48 + v45;
                if ( v30 )
                  goto LABEL_62;
                v18 = v25 - v29;
                if ( v18 == -1 )
                  goto LABEL_62;
                v51 = v29;
                v52 = v31;
                v17 = RtlpParseFunctionOverrideRelocations(v11, &v51, v26, &v55);
                if ( v17 < 0 )
                  goto LABEL_64;
                v20 = (unsigned int *)(v29 + v46);
                if ( v18 < 0x10 )
                {
                  v19 = (unsigned int *)(v29 + v46);
                  v48 = v20;
                  v20 = 0;
                }
                else
                {
                  v18 -= 16LL;
                  if ( v18 == -1 )
                    goto LABEL_62;
                  v19 = v20 + 4;
                  v48 = v20 + 4;
                }
              }
              v32 = v53;
              v52 = (char *)v53;
              v51 = v15;
              v33 = RtlpAllocateFunctionOverrideInfo(&v51, i, v54);
              v7 = v54[0];
              v17 = v33;
              if ( v33 >= 0 )
              {
                LODWORD(v55) = 1;
                v57 = v32 + 4 * v15;
                v56 = v15;
                *(struct _RTL_FUNCTION_OVERRIDE_INFORMATION **)&v58 = v54[0];
                DWORD2(v58) = 0;
                if ( v12 < 0x10 )
                {
                  v34 = v12;
                  v35 = v14;
                  v36 = 0;
                }
                else
                {
                  v34 = v12 - 16;
                  v35 = v14 + 4;
                  v36 = v14;
                }
                v61 = (struct _RTL_FUNCTION_OVERRIDE_INFORMATION *)((char *)v14 + v12);
                while ( v36 )
                {
                  v11 = v36[2];
                  if ( v34 < v11 )
                    goto LABEL_62;
                  v37 = v36[3];
                  if ( v34 - v11 < v37 || !v35 && v36[2] )
                    goto LABEL_62;
                  if ( (v11 & 3) != 0 )
                    goto LABEL_62;
                  v38 = v11 >> 2;
                  if ( !v35 )
                  {
                    if ( v38 )
                      goto LABEL_62;
                  }
                  v39 = (unsigned int)(v37 + v11);
                  v47 = v39;
                  if ( v34 < v39 )
                    goto LABEL_62;
                  v34 -= v39;
                  if ( v34 == -1 )
                    goto LABEL_62;
                  v51 = v36[3];
                  v52 = (char *)v35 + v11;
                  v17 = RtlpParseFunctionOverrideRelocations(a2, &v51, a3, &v55);
                  if ( v17 < 0 )
                    goto LABEL_64;
                  v40 = *v36;
                  v41 = DWORD2(v58);
                  v49 = v38;
                  v42 = (unsigned int *)((char *)v7 + 16 * DWORD2(v58) + 40);
                  v50 = v35;
                  *v42 = v40;
                  v43 = v36[1];
                  v54[0] = v59;
                  v54[1] = v61;
                  v17 = RtlpParseBinaryDecisionDiagram(v54, &v49, v43, a4, v42, a6);
                  if ( v17 < 0 )
                    goto LABEL_64;
                  v36 = (unsigned int *)((char *)v35 + v47);
                  if ( v34 < 0x10 )
                  {
                    v35 = (unsigned int *)((char *)v35 + v47);
                    v36 = 0;
                  }
                  else
                  {
                    v34 -= 16LL;
                    if ( v34 == -1 )
                      goto LABEL_62;
                    v35 = v36 + 4;
                  }
                  DWORD2(v58) = v41 + 1;
                }
                v17 = RtlpSortAndValidateRelocations(v7);
                if ( v17 >= 0 )
                  *a5 = v7;
              }
              goto LABEL_64;
            }
LABEL_62:
            `gsl::details::get_terminate_handler'::`2'::handler((gsl::details *)v11);
          }
        }
      }
    }
  }
LABEL_63:
  v17 = -1073741701;
LABEL_64:
  if ( v53 )
    SkFreePool(512, v53);
  if ( v17 < 0 && v7 )
    RtlFreeFunctionOverrideInfo(v7);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1400da5b4  mov     rax, rsp
0x1400da5b7  mov     [rax+20h], r9
0x1400da5bb  mov     [rax+18h], r8d
0x1400da5bf  mov     [rax+10h], edx
0x1400da5c2  push    rbp
0x1400da5c3  push    rbx
0x1400da5c4  push    rsi
0x1400da5c5  push    rdi
0x1400da5c6  push    r12
0x1400da5c8  push    r13
0x1400da5ca  push    r14
0x1400da5cc  push    r15
0x1400da5ce  lea     rbp, [rax-4Fh]
0x1400da5d2  sub     rsp, 0C8h
0x1400da5d9  mov     r10, [rcx]
0x1400da5dc  xor     eax, eax
0x1400da5de  xor     edi, edi
0x1400da5e0  mov     [rbp+47h+var_70], rax
0x1400da5e4  mov     rax, [rbp+47h+arg_20]
0x1400da5e8  xor     r12d, r12d
0x1400da5eb  mov     r8d, edx
0x1400da5ee  xorps   xmm0, xmm0
0x1400da5f1  mov     [rbp+47h+var_80], r12
0x1400da5f5  mov     [rbp+47h+var_90], rdi
0x1400da5f9  mov     [rax], rdi
0x1400da5fc  movups  [rbp+47h+var_58], xmm0
0x1400da600  cmp     r10, 4
0x1400da604  jb      loc_1400DA9C2
0x1400da60a  mov     rax, [rcx+8]
0x1400da60e  lea     rdx, [r10-4]
0x1400da612  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1400da616  jz      loc_1400DA9B5
0x1400da61c  test    rax, rax
0x1400da61f  jz      loc_1400DA9C2
0x1400da625  mov     ecx, [rax]
0x1400da627  test    ecx, ecx
0x1400da629  jz      loc_1400DA9C2
0x1400da62f  mov     r14d, ecx
0x1400da632  cmp     rcx, rdx
0x1400da635  jnb     loc_1400DA9C2
0x1400da63b  sub     rdx, rcx
0x1400da63e  lea     r13, [rax+4]
0x1400da642  mov     [rbp+47h+var_48], rdx
0x1400da646  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1400da64a  jz      loc_1400DA9B5
0x1400da650  test    r13, r13
0x1400da653  jz      loc_1400DA9B5
0x1400da659  test    rdx, rdx
0x1400da65c  jz      loc_1400DA9C2
0x1400da662  mov     esi, r8d
0x1400da665  mov     ecx, 200h
0x1400da66a  shr     rsi, 0Ch
0x1400da66e  mov     r8d, 6F467452h
0x1400da674  lea     rbx, [rsi+rsi]
0x1400da678  lea     rdx, ds:0[rbx*4]
0x1400da680  call    SkAllocatePool
0x1400da685  mov     [rbp+47h+var_90], rax
0x1400da689  test    rax, rax
0x1400da68c  jnz     short loc_1400DA698
0x1400da68e  mov     ebx, 0C0000017h
0x1400da693  jmp     loc_1400DA9EE
0x1400da698  cmp     rsi, rbx
0x1400da69b  ja      loc_1400DA9B5
0x1400da6a1  mov     dword ptr [rbp+47h+var_70], edi
0x1400da6a4  mov     [rbp+47h+var_68], rsi
0x1400da6a8  mov     [rbp+47h+var_60], rax
0x1400da6ac  cmp     r14, 10h
0x1400da6b0  jb      short loc_1400DA6CD
0x1400da6b2  lea     rdi, [r14-10h]
0x1400da6b6  lea     r15, [r13+10h]
0x1400da6ba  mov     [rbp+47h+var_B8], r15
0x1400da6be  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400da6c2  jz      loc_1400DA9B5
0x1400da6c8  mov     r11, r13
0x1400da6cb  jmp     short loc_1400DA6DA
0x1400da6cd  mov     rdi, r14
0x1400da6d0  mov     [rbp+47h+var_B8], r13
0x1400da6d4  mov     r15, r13
0x1400da6d7  xor     r11d, r11d
0x1400da6da  xor     eax, eax
0x1400da6dc  mov     dword ptr [rbp+47h+arg_0], eax
0x1400da6df  test    r11, r11
0x1400da6e2  jz      loc_1400DA80B
0x1400da6e8  mov     edx, [rbp+47h+arg_10]
0x1400da6eb  lea     r8, [rbp+47h+var_B0]
0x1400da6ef  mov     ecx, [rbp+47h+arg_8]
0x1400da6f2  mov     [rbp+47h+var_B0], 1
0x1400da6fa  mov     [rbp+47h+var_A8], r11
0x1400da6fe  call    ?RtlpValidateRvasWithinImage@@YAJKKAEBV?$span@$$CBK$0?0@gsl@@@Z; RtlpValidateRvasWithinImage(ulong,ulong,gsl::span<ulong const,-1> const &)
0x1400da703  mov     ebx, eax
0x1400da705  test    eax, eax
0x1400da707  js      loc_1400DA9C7
0x1400da70d  mov     eax, [r11+8]
0x1400da711  test    eax, eax
0x1400da713  jz      loc_1400DA9C2
0x1400da719  test    al, 3
0x1400da71b  jnz     loc_1400DA9C2
0x1400da721  mov     [rbp+47h+var_C0], rax
0x1400da725  mov     ecx, eax
0x1400da727  cmp     rax, rdi
0x1400da72a  ja      loc_1400DA9C2
0x1400da730  test    r15, r15
0x1400da733  jz      loc_1400DA9B5
0x1400da739  test    cl, 3
0x1400da73c  jnz     loc_1400DA9B5
0x1400da742  shr     rax, 2
0x1400da746  sub     rdi, rcx
0x1400da749  mov     [rbp+47h+var_B0], rax
0x1400da74d  mov     [rbp+47h+var_A8], r15
0x1400da751  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400da755  jz      loc_1400DA9B5
0x1400da75b  mov     ecx, [rbp+47h+arg_8]
0x1400da75e  lea     r8, [rbp+47h+var_B0]
0x1400da762  call    ?RtlpValidateRvasWithinImage@@YAJKKAEBV?$span@$$CBK$0?0@gsl@@@Z; RtlpValidateRvasWithinImage(ulong,ulong,gsl::span<ulong const,-1> const &)
0x1400da767  mov     ebx, eax
0x1400da769  test    eax, eax
0x1400da76b  js      loc_1400DA9C7
0x1400da771  mov     eax, [r11+0Ch]
0x1400da775  test    eax, eax
0x1400da777  jz      loc_1400DA9C2
0x1400da77d  test    al, 3
0x1400da77f  jnz     loc_1400DA9C2
0x1400da785  mov     r15d, eax
0x1400da788  cmp     rax, rdi
0x1400da78b  ja      loc_1400DA9C2
0x1400da791  mov     rax, [rbp+47h+var_C0]
0x1400da795  add     rax, [rbp+47h+var_B8]
0x1400da799  mov     [rbp+47h+var_C0], rax
0x1400da79d  jz      loc_1400DA9B5
0x1400da7a3  sub     rdi, r15
0x1400da7a6  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400da7aa  jz      loc_1400DA9B5
0x1400da7b0  mov     r8d, edx
0x1400da7b3  mov     [rbp+47h+var_A0], r15
0x1400da7b7  lea     rdx, [rbp+47h+var_A0]
0x1400da7bb  mov     [rbp+47h+var_98], rax
0x1400da7bf  lea     r9, [rbp+47h+var_70]
0x1400da7c3  call    ?RtlpParseFunctionOverrideRelocations@@YAJKV?$span@$$CBE$0?0@gsl@@KPEAU_RTLP_PARSE_RELOCATIONS_PACKET@@@Z; RtlpParseFunctionOverrideRelocations(ulong,gsl::span<uchar const,-1>,ulong,_RTLP_PARSE_RELOCATIONS_PACKET *)
0x1400da7c8  mov     ebx, eax
0x1400da7ca  test    eax, eax
0x1400da7cc  js      loc_1400DA9C7
0x1400da7d2  mov     r11, [rbp+47h+var_C0]
0x1400da7d6  add     r11, r15
0x1400da7d9  cmp     rdi, 10h
0x1400da7dd  jb      short loc_1400DA7F7
0x1400da7df  add     rdi, 0FFFFFFFFFFFFFFF0h
0x1400da7e3  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400da7e7  jz      loc_1400DA9B5
0x1400da7ed  lea     r15, [r11+10h]
0x1400da7f1  mov     [rbp+47h+var_B8], r15
0x1400da7f5  jmp     short loc_1400DA801
0x1400da7f7  mov     r15, r11
0x1400da7fa  mov     [rbp+47h+var_B8], r11
0x1400da7fe  xor     r11d, r11d
0x1400da801  mov     eax, dword ptr [rbp+47h+arg_0]
0x1400da804  inc     eax
0x1400da806  jmp     loc_1400DA6DC
0x1400da80b  mov     rdi, [rbp+47h+var_90]
0x1400da80f  lea     r8, [rbp+47h+var_80]
0x1400da813  mov     edx, eax
0x1400da815  mov     [rbp+47h+var_98], rdi
0x1400da819  lea     rcx, [rbp+47h+var_A0]
0x1400da81d  mov     [rbp+47h+var_A0], rsi
0x1400da821  call    ?RtlpAllocateFunctionOverrideInfo@@YAJV?$span@$$CBK$0?0@gsl@@KPEAPEAU_RTL_FUNCTION_OVERRIDE_INFORMATION@@@Z; RtlpAllocateFunctionOverrideInfo(gsl::span<ulong const,-1>,ulong,_RTL_FUNCTION_OVERRIDE_INFORMATION * *)
0x1400da826  mov     r12, [rbp+47h+var_80]
0x1400da82a  mov     ebx, eax
0x1400da82c  test    eax, eax
0x1400da82e  js      loc_1400DA9C7
0x1400da834  mov     dword ptr [rbp+47h+var_70], 1
0x1400da83b  lea     rax, [rdi+rsi*4]
0x1400da83f  mov     [rbp+47h+var_60], rax
0x1400da843  mov     [rbp+47h+var_68], rsi
0x1400da847  mov     qword ptr [rbp+47h+var_58], r12
0x1400da84b  mov     dword ptr [rbp+47h+var_58+8], 0
0x1400da852  cmp     r14, 10h
0x1400da856  jb      short loc_1400DA86F
0x1400da858  lea     rdi, [r14-10h]
0x1400da85c  lea     r15, [r13+10h]
0x1400da860  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400da864  jz      loc_1400DA9B5
0x1400da86a  mov     rsi, r13
0x1400da86d  jmp     short loc_1400DA877
0x1400da86f  mov     rdi, r14
0x1400da872  mov     r15, r13
0x1400da875  xor     esi, esi
0x1400da877  lea     rax, [r14+r13]
0x1400da87b  mov     [rbp+47h+arg_0], rax
0x1400da87f  test    rsi, rsi
0x1400da882  jz      loc_1400DA99E
0x1400da888  mov     ecx, [rsi+8]
0x1400da88b  cmp     rdi, rcx
0x1400da88e  jb      loc_1400DA9B5
0x1400da894  mov     edx, [rsi+0Ch]
0x1400da897  mov     rax, rdi
0x1400da89a  sub     rax, rcx
0x1400da89d  cmp     rax, rdx
0x1400da8a0  jb      loc_1400DA9B5
0x1400da8a6  test    r15, r15
0x1400da8a9  jnz     short loc_1400DA8B4
0x1400da8ab  test    rcx, rcx
0x1400da8ae  jnz     loc_1400DA9B5
0x1400da8b4  test    cl, 3
0x1400da8b7  jnz     loc_1400DA9B5
0x1400da8bd  mov     r13, rcx
0x1400da8c0  shr     r13, 2
0x1400da8c4  test    r15, r15
0x1400da8c7  jnz     short loc_1400DA8D2
0x1400da8c9  test    r13, r13
0x1400da8cc  jnz     loc_1400DA9B5
0x1400da8d2  lea     eax, [rdx+rcx]
0x1400da8d5  mov     [rbp+47h+var_C0], rax
0x1400da8d9  cmp     rdi, rax
0x1400da8dc  jb      loc_1400DA9B5
0x1400da8e2  sub     rdi, rax
0x1400da8e5  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400da8e9  jz      loc_1400DA9B5
0x1400da8ef  mov     r8d, [rbp+47h+arg_10]
0x1400da8f3  lea     rax, [r15+rcx]
0x1400da8f7  mov     ecx, [rbp+47h+arg_8]
0x1400da8fa  lea     r9, [rbp+47h+var_70]
0x1400da8fe  mov     [rbp+47h+var_A0], rdx
0x1400da902  lea     rdx, [rbp+47h+var_A0]
0x1400da906  mov     [rbp+47h+var_98], rax
0x1400da90a  call    ?RtlpParseFunctionOverrideRelocations@@YAJKV?$span@$$CBE$0?0@gsl@@KPEAU_RTLP_PARSE_RELOCATIONS_PACKET@@@Z; RtlpParseFunctionOverrideRelocations(ulong,gsl::span<uchar const,-1>,ulong,_RTLP_PARSE_RELOCATIONS_PACKET *)
0x1400da90f  mov     ebx, eax
0x1400da911  test    eax, eax
0x1400da913  js      loc_1400DA9C7
0x1400da919  mov     eax, [rsi]
0x1400da91b  lea     rdx, [rbp+47h+var_B0]
0x1400da91f  mov     r14d, dword ptr [rbp+47h+var_58+8]
0x1400da923  mov     r9, [rbp+47h+arg_18]
0x1400da927  mov     ecx, r14d
0x1400da92a  shl     rcx, 4
0x1400da92e  add     rcx, 28h ; '('
0x1400da932  mov     [rbp+47h+var_B0], r13
0x1400da936  add     rcx, r12
0x1400da939  mov     [rbp+47h+var_A8], r15
0x1400da93d  mov     [rcx], eax
0x1400da93f  mov     rax, [rbp+47h+var_48]
0x1400da943  mov     r8d, [rsi+4]
0x1400da947  mov     [rbp+47h+var_80], rax
0x1400da94b  mov     rax, [rbp+47h+arg_0]
0x1400da94f  mov     [rbp+47h+var_78], rax
0x1400da953  mov     rax, [rbp+47h+arg_28]
0x1400da957  mov     [rsp+28h], rax
0x1400da95c  mov     [rsp+100h+var_E0], rcx
0x1400da961  lea     rcx, [rbp+47h+var_80]
0x1400da965  call    ?RtlpParseBinaryDecisionDiagram@@YAJV?$span@$$CBE$0?0@gsl@@V?$span@$$CBK$0?0@2@KPEBU_RTL_FUNCTION_OVERRIDE_CAPABILITIES@@PEAU_RTL_FUNCTION_OVERRIDE_ENTRY@@PEBU_RTL_SYSTEM_OVERRIDE_INFORMATION@@K@Z; RtlpParseBinaryDecisionDiagram(gsl::span<uchar const,-1>,gsl::span<ulong const,-1>,ulong,_RTL_FUNCTION_OVERRIDE_CAPABILITIES const *,_RTL_FUNCTION_OVERRIDE_ENTRY *,_RTL_SYSTEM_OVERRIDE_INFORMATION const *,ulong)
0x1400da96a  mov     ebx, eax
0x1400da96c  test    eax, eax
0x1400da96e  js      short loc_1400DA9C7
0x1400da970  mov     rsi, [rbp+47h+var_C0]
0x1400da974  add     rsi, r15
0x1400da977  cmp     rdi, 10h
0x1400da97b  jb      short loc_1400DA98D
0x1400da97d  add     rdi, 0FFFFFFFFFFFFFFF0h
0x1400da981  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400da985  jz      short loc_1400DA9B5
0x1400da987  lea     r15, [rsi+10h]
0x1400da98b  jmp     short loc_1400DA992
0x1400da98d  mov     r15, rsi
0x1400da990  xor     esi, esi
0x1400da992  inc     r14d
0x1400da995  mov     dword ptr [rbp+47h+var_58+8], r14d
0x1400da999  jmp     loc_1400DA87F
0x1400da99e  mov     rcx, r12; struct _RTL_FUNCTION_OVERRIDE_INFORMATION *
0x1400da9a1  call    ?RtlpSortAndValidateRelocations@@YAJPEAU_RTL_FUNCTION_OVERRIDE_INFORMATION@@@Z; RtlpSortAndValidateRelocations(_RTL_FUNCTION_OVERRIDE_INFORMATION *)
0x1400da9a6  mov     ebx, eax
0x1400da9a8  test    eax, eax
0x1400da9aa  js      short loc_1400DA9C7
0x1400da9ac  mov     rax, [rbp+47h+arg_20]
0x1400da9b0  mov     [rax], r12
0x1400da9b3  jmp     short loc_1400DA9C7
0x1400da9b5  mov     rax, cs:?handler@?1??get_terminate_handler@details@gsl@@YAAEAP6AXXZXZ@4P6AXXZEA; void (*`gsl::details::get_terminate_handler(void)'::`2'::handler)(void)
0x1400da9bc  call    rax ; gsl::details::default_terminate_handler(void); gsl::details::default_terminate_handler(void)
0x1400da9c2  mov     ebx, 0C000007Bh
0x1400da9c7  mov     rax, [rbp+47h+var_90]
0x1400da9cb  test    rax, rax
0x1400da9ce  jz      short loc_1400DA9DD
0x1400da9d0  mov     rdx, rax
0x1400da9d3  mov     ecx, 200h
0x1400da9d8  call    SkFreePool
0x1400da9dd  test    ebx, ebx
0x1400da9df  jns     short loc_1400DA9EE
0x1400da9e1  test    r12, r12
0x1400da9e4  jz      short loc_1400DA9EE
0x1400da9e6  mov     rcx, r12
0x1400da9e9  call    RtlFreeFunctionOverrideInfo
0x1400da9ee  mov     eax, ebx
0x1400da9f0  add     rsp, 0C8h
0x1400da9f7  pop     r15
0x1400da9f9  pop     r14
0x1400da9fb  pop     r13
0x1400da9fd  pop     r12
0x1400da9ff  pop     rdi
0x1400daa00  pop     rsi
0x1400daa01  pop     rbx
0x1400daa02  pop     rbp
0x1400daa03  retn
```
