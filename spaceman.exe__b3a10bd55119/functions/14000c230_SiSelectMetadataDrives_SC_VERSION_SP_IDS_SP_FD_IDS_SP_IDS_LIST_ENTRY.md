# SiSelectMetadataDrives(_SC_VERSION,_SP_IDS *,_SP_FD_IDS *,_SP_IDS *,_LIST_ENTRY *)

- ea: `0x14000c230`
- end: `0x14000c689`
- name: `?SiSelectMetadataDrives@@YAHW4_SC_VERSION@@PEAU_SP_IDS@@PEAU_SP_FD_IDS@@1PEAU_LIST_ENTRY@@@Z`
- size: `1113`
- prototype: `__int64 __fastcall(unsigned int, __int64, int *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000c868`

## callees

- `0x14000ba1c`
- `0x14000c230`
- `0x14000ce68`
- `0x14000d1be`
- `0x14000d1f0`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x14000c4a4`
- `bcrypt!BCryptGenRandom` at `0x14000c4a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c33b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c563`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c33b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c563`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000c32b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000c32b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000c5d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000c5d6`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14000c51a`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14000c5c8`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14000c51a`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14000c5c8`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x14000c4bd`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x14000c4bd`
- `ntdll!RtlInitializeGenericTableAvl` at `0x14000c44c`
- `ntdll!RtlInitializeGenericTableAvl` at `0x14000c44c`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x14000c53c`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x14000c5b3`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x14000c53c`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x14000c5b3`

## pseudocode

```c
__int64 __fastcall SiSelectMetadataDrives(unsigned int a1, __int64 a2, int *a3, __int64 a4, __int64 *a5)
{
  unsigned int v8; // edx
  __int64 v9; // rcx
  int v10; // r12d
  __int64 *k; // rax
  _DWORD *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rcx
  _QWORD *v15; // rax
  int v16; // r14d
  int v17; // ebx
  _QWORD **v18; // rsi
  _QWORD *v19; // rax
  unsigned int v20; // ecx
  unsigned int v21; // r15d
  struct _RTL_AVL_TABLE *v22; // r14
  struct _RTL_AVL_TABLE *Parent; // rsi
  _QWORD **v24; // r13
  _QWORD *i; // rbx
  _QWORD *v26; // rdx
  int LeftChild; // eax
  int v28; // esi
  signed int v29; // r13d
  struct _RTL_AVL_TABLE *j; // rbx
  DWORD v31; // ecx
  _QWORD *v32; // rax
  BOOLEAN v33; // al
  _QWORD **v34; // rbx
  _QWORD *v35; // rax
  __int64 v36; // rcx
  _QWORD *v37; // rdx
  _QWORD *v38; // r14
  struct _RTL_AVL_TABLE *v39; // rsi
  PVOID v40; // rax
  __int64 *v41; // rcx
  __int64 *v42; // rax
  __int64 v43; // rax
  unsigned __int8 NewElement[4]; // [rsp+30h] [rbp-91h] BYREF
  __int64 v46; // [rsp+38h] [rbp-89h] BYREF
  __int64 *v47; // [rsp+40h] [rbp-81h]
  _QWORD *Buffer; // [rsp+48h] [rbp-79h] BYREF
  PVOID v49; // [rsp+50h] [rbp-71h] BYREF
  PVOID RestartKey; // [rsp+58h] [rbp-69h] BYREF
  __int64 v51; // [rsp+60h] [rbp-61h] BYREF
  _QWORD v52[11]; // [rsp+68h] [rbp-59h] BYREF
  _QWORD v53[2]; // [rsp+C0h] [rbp-1h] BYREF

  v51 = 0;
  memset_0(v52, 0, 0x68u);
  Buffer = 0;
  v47 = &v46;
  v8 = 0;
  RestartKey = 0;
  v46 = (__int64)&v46;
  *(_DWORD *)NewElement = 1;
  do
  {
    v9 = 2LL * (int)v8++;
    v52[v9] = &v52[v9 - 1];
    v52[v9 - 1] = &v52[v9 - 1];
  }
  while ( v8 < 7 );
  v10 = 6;
  if ( a1 > 8 )
  {
    *(_DWORD *)NewElement = SiIncludeDrivesForMetadata(a1, a2, a3);
    if ( *(_DWORD *)NewElement && (__int64 *)v46 != &v46 )
    {
      v12 = LocalAlloc(0x40u, 0xD8u);
      if ( v12 )
      {
        *v12 = 6;
        v14 = v53[0];
        if ( *(_QWORD **)(v53[0] + 8LL) != v53 )
          goto LABEL_63;
        v15 = v12 + 50;
        v16 = 6;
        *v15 = v53[0];
        v15[1] = v53;
        *(_QWORD *)(v14 + 8) = v15;
        v53[0] = v15;
        if ( !a3 || (v17 = *a3, v17 <= 1) )
          v17 = 5;
        while ( 1 )
        {
          v18 = (_QWORD **)&v52[2 * (unsigned int)v17 - 1];
          *(_DWORD *)NewElement = SiGetFaultDomains(&v46, (unsigned int)v17, v13, v18);
          if ( !*(_DWORD *)NewElement )
            break;
          if ( v17 != 1 )
          {
            v19 = *v18;
            v20 = 0;
            if ( *v18 == v18 )
            {
LABEL_24:
              v16 = v17;
            }
            else
            {
              v13 = *(_QWORD *)&GUID_NULL.Data1;
              while ( *(_QWORD *)((char *)v19 - 196) != *(_QWORD *)&GUID_NULL.Data1
                   || *(_QWORD *)((char *)v19 - 188) != *(_QWORD *)GUID_NULL.Data4 )
              {
                v19 = (_QWORD *)*v19;
                ++v20;
                if ( v19 == v18 )
                {
                  if ( v20 >= 5 )
                    goto LABEL_26;
                  goto LABEL_24;
                }
              }
            }
            if ( --v17 > 0 )
              continue;
          }
LABEL_26:
          v21 = 0;
          v22 = (struct _RTL_AVL_TABLE *)&v52[2 * v16 - 1];
          Parent = (struct _RTL_AVL_TABLE *)v22->BalancedRoot.Parent;
          if ( (struct _RTL_AVL_TABLE *)v22->BalancedRoot.Parent != v22 )
          {
            v24 = (_QWORD **)&v52[2 * v17 - 1];
            while ( 2 )
            {
              RtlInitializeGenericTableAvl(
                Parent - 1,
                (PRTL_AVL_COMPARE_ROUTINE)SiFdTableCompareRoutine,
                SiTableAllocateRoutine,
                SiTableFreeRoutine,
                0);
              for ( i = *v24; i != v24; i = (_QWORD *)*i )
              {
                v26 = i - 25;
                Buffer = i - 25;
                LeftChild = (int)Parent[-2].BalancedRoot.LeftChild;
                if ( LeftChild == 6
                  || *(struct _RTL_BALANCED_LINKS **)((char *)&v26[2 * (unsigned int)(LeftChild - 2) + 2] + 4) == *(struct _RTL_BALANCED_LINKS **)((char *)&Parent[-2].BalancedRoot.LeftChild + 4)
                  && *(struct _RTL_BALANCED_LINKS **)((char *)&v26[2 * (unsigned int)(LeftChild - 2) + 3] + 4) == *(struct _RTL_BALANCED_LINKS **)((char *)&Parent[-2].BalancedRoot.RightChild + 4) )
                {
                  BCryptGenRandom(0, (PUCHAR)(v26[11] + 16LL), 4u, 2u);
                  RtlInsertElementGenericTableAvl(Parent - 1, &Buffer, 8u, NewElement);
                  if ( !*(_DWORD *)NewElement )
                  {
                    v31 = 5010;
LABEL_46:
                    SetLastError(v31);
                    goto LABEL_47;
                  }
                }
              }
              Parent = (struct _RTL_AVL_TABLE *)Parent->BalancedRoot.Parent;
              ++v21;
              if ( Parent != v22 )
                continue;
              break;
            }
          }
          v28 = 0;
          v29 = (v21 + 4 - (v21 + 4) % v21) / v21;
          if ( v29 > 0 )
          {
            while ( 2 )
            {
              for ( j = (struct _RTL_AVL_TABLE *)v22->BalancedRoot.Parent;
                    j != v22;
                    j = (struct _RTL_AVL_TABLE *)j->BalancedRoot.Parent )
              {
                RestartKey = 0;
                v32 = RtlEnumerateGenericTableWithoutSplayingAvl(j - 1, &RestartKey);
                if ( v32 )
                {
                  Buffer = (_QWORD *)*v32;
                  *(_DWORD *)(Buffer[11] + 20LL) |= 4u;
                  v33 = RtlDeleteElementGenericTableAvl(j - 1, v32);
                  *(_DWORD *)NewElement = v33;
                  if ( !v33 )
                  {
                    v31 = 1168;
                    goto LABEL_46;
                  }
                }
              }
              if ( ++v28 < v29 )
                continue;
              break;
            }
          }
          goto LABEL_47;
        }
      }
      else
      {
        SetLastError(0x5AAu);
        *(_DWORD *)NewElement = 0;
      }
    }
  }
  else
  {
    for ( k = (__int64 *)*a5; k != a5; k = (__int64 *)*k )
      *((_DWORD *)k + 5) |= 4u;
  }
  do
  {
LABEL_47:
    v34 = (_QWORD **)&v52[2 * (unsigned int)v10 - 1];
    while ( 1 )
    {
      v35 = *v34;
      if ( *v34 == v34 )
        break;
      v36 = *v35;
      if ( *(_QWORD **)(*v35 + 8LL) != v35 )
        goto LABEL_63;
      v37 = (_QWORD *)v35[1];
      if ( (_QWORD *)*v37 != v35 )
        goto LABEL_63;
      v38 = v35 - 25;
      *v37 = v36;
      v39 = (struct _RTL_AVL_TABLE *)(v35 - 13);
      *(_QWORD *)(v36 + 8) = v37;
      while ( 1 )
      {
        v49 = 0;
        v40 = RtlEnumerateGenericTableWithoutSplayingAvl(v39, &v49);
        if ( !v40 )
          break;
        RtlDeleteElementGenericTableAvl(v39, v40);
      }
      LocalFree(v38);
    }
    --v10;
  }
  while ( v10 >= 0 );
  if ( *(__int64 **)(*a5 + 8) != a5
    || (v41 = (__int64 *)a5[1], (__int64 *)*v41 != a5)
    || *(__int64 **)(v46 + 8) != &v46
    || (__int64 *)*v47 != &v46
    || (*v41 = (__int64)&v46,
        v42 = v47,
        a5[1] = (__int64)v47,
        *v42 = (__int64)a5,
        v43 = v46,
        v47 = v41,
        *(__int64 **)(v46 + 8) != &v46)
    || (__int64 *)*v41 != &v46 )
  {
LABEL_63:
    __fastfail(3u);
  }
  *v41 = v46;
  *(_QWORD *)(v43 + 8) = v41;
  return *(unsigned int *)NewElement;
}

```

## disassembly

```asm
0x14000c230  mov     [rsp-8+arg_18], rbx
0x14000c235  push    rbp
0x14000c236  push    rsi
0x14000c237  push    rdi
0x14000c238  push    r12
0x14000c23a  push    r13
0x14000c23c  push    r14
0x14000c23e  push    r15
0x14000c240  lea     rbp, [rsp-1Fh]
0x14000c245  sub     rsp, 0E0h
0x14000c24c  mov     rax, cs:__security_cookie
0x14000c253  xor     rax, rsp
0x14000c256  mov     [rbp+4Fh+var_40], rax
0x14000c25a  mov     rdi, [rbp+4Fh+arg_20]
0x14000c25e  mov     r14, rdx
0x14000c261  xor     edx, edx; Val
0x14000c263  mov     [rbp+4Fh+var_B0], 0
0x14000c26b  mov     rbx, r8
0x14000c26e  mov     esi, ecx
0x14000c270  lea     rcx, [rbp+4Fh+var_A8]; void *
0x14000c274  lea     r8d, [rdx+68h]; Size
0x14000c278  call    memset_0
0x14000c27d  lea     rax, [rsp+110h+var_D8]
0x14000c282  mov     [rbp+4Fh+Buffer], 0
0x14000c28a  mov     [rsp+110h+var_D0], rax
0x14000c28f  xor     edx, edx
0x14000c291  lea     rax, [rsp+110h+var_D8]
0x14000c296  mov     [rbp+4Fh+RestartKey], 0
0x14000c29e  mov     [rsp+110h+var_D8], rax
0x14000c2a3  mov     dword ptr [rsp+110h+NewElement], 1
0x14000c2ab  movsxd  rcx, edx
0x14000c2ae  lea     rax, [rbp+4Fh+var_B0]
0x14000c2b2  shl     rcx, 4
0x14000c2b6  inc     edx
0x14000c2b8  add     rax, rcx
0x14000c2bb  mov     [rbp+rcx+4Fh+var_A8], rax
0x14000c2c0  mov     [rax], rax
0x14000c2c3  cmp     edx, 7
0x14000c2c6  jb      short loc_14000C2AB
0x14000c2c8  mov     r12d, 6
0x14000c2ce  cmp     esi, 8
0x14000c2d1  ja      short loc_14000C2E9
0x14000c2d3  mov     rax, [rdi]
0x14000c2d6  jmp     short loc_14000C2DF
0x14000c2d8  or      dword ptr [rax+14h], 4
0x14000c2dc  mov     rax, [rax]
0x14000c2df  cmp     rax, rdi
0x14000c2e2  jnz     short loc_14000C2D8
0x14000c2e4  jmp     loc_14000C569
0x14000c2e9  lea     rax, [rsp+110h+var_D8]
0x14000c2ee  mov     r8, rbx
0x14000c2f1  mov     [rsp+110h+var_E8], rax
0x14000c2f6  mov     rdx, r14
0x14000c2f9  mov     ecx, esi
0x14000c2fb  mov     [rsp+110h+TableContext], rdi
0x14000c300  call    ?SiIncludeDrivesForMetadata@@YAHW4_SC_VERSION@@PEAU_SP_IDS@@PEAU_SP_FD_IDS@@1PEAU_LIST_ENTRY@@3@Z; SiIncludeDrivesForMetadata(_SC_VERSION,_SP_IDS *,_SP_FD_IDS *,_SP_IDS *,_LIST_ENTRY *,_LIST_ENTRY *)
0x14000c305  mov     dword ptr [rsp+110h+NewElement], eax
0x14000c309  test    eax, eax
0x14000c30b  jz      loc_14000C569
0x14000c311  lea     rax, [rsp+110h+var_D8]
0x14000c316  cmp     [rsp+110h+var_D8], rax
0x14000c31b  jz      loc_14000C569
0x14000c321  mov     edx, 0D8h; uBytes
0x14000c326  mov     ecx, 40h ; '@'; uFlags
0x14000c32b  call    cs:__imp_LocalAlloc
0x14000c331  test    rax, rax
0x14000c334  jnz     short loc_14000C34E
0x14000c336  mov     ecx, 5AAh; dwErrCode
0x14000c33b  call    cs:__imp_SetLastError
0x14000c341  mov     dword ptr [rsp+110h+NewElement], 0
0x14000c349  jmp     loc_14000C569
0x14000c34e  mov     [rax], r12d
0x14000c351  lea     rdx, [rbp+4Fh+var_50]
0x14000c355  mov     rcx, [rbp+4Fh+var_50]
0x14000c359  cmp     [rcx+8], rdx
0x14000c35d  jnz     loc_14000C682
0x14000c363  add     rax, 0C8h
0x14000c369  lea     rdx, [rbp+4Fh+var_50]
0x14000c36d  mov     r14d, r12d
0x14000c370  mov     [rax], rcx
0x14000c373  mov     [rax+8], rdx
0x14000c377  mov     [rcx+8], rax
0x14000c37b  mov     [rbp+4Fh+var_50], rax
0x14000c37f  test    rbx, rbx
0x14000c382  jz      short loc_14000C38B
0x14000c384  mov     ebx, [rbx]
0x14000c386  cmp     ebx, 1
0x14000c389  jg      short loc_14000C390
0x14000c38b  mov     ebx, 5
0x14000c390  mov     eax, ebx
0x14000c392  lea     rsi, [rbp+4Fh+var_B0]
0x14000c396  shl     rax, 4
0x14000c39a  lea     rcx, [rsp+110h+var_D8]
0x14000c39f  add     rsi, rax
0x14000c3a2  mov     edx, ebx
0x14000c3a4  mov     r9, rsi
0x14000c3a7  call    ?SiGetFaultDomains@@YAHPEAU_LIST_ENTRY@@W4_SC_FD_TYPE@@H0@Z; SiGetFaultDomains(_LIST_ENTRY *,_SC_FD_TYPE,int,_LIST_ENTRY *)
0x14000c3ac  mov     dword ptr [rsp+110h+NewElement], eax
0x14000c3b0  test    eax, eax
0x14000c3b2  jz      loc_14000C569
0x14000c3b8  cmp     ebx, 1
0x14000c3bb  jz      short loc_14000C3FF
0x14000c3bd  mov     rax, [rsi]
0x14000c3c0  xor     ecx, ecx
0x14000c3c2  cmp     rax, rsi
0x14000c3c5  jz      short loc_14000C3F6
0x14000c3c7  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x14000c3ce  mov     r8, qword ptr cs:GUID_NULL.Data1
0x14000c3d5  cmp     [rax-0C4h], r8
0x14000c3dc  jnz     short loc_14000C3E7
0x14000c3de  cmp     [rax-0BCh], rdx
0x14000c3e5  jz      short loc_14000C3F9
0x14000c3e7  mov     rax, [rax]
0x14000c3ea  inc     ecx
0x14000c3ec  cmp     rax, rsi
0x14000c3ef  jnz     short loc_14000C3D5
0x14000c3f1  cmp     ecx, 5
0x14000c3f4  jnb     short loc_14000C3FF
0x14000c3f6  mov     r14d, ebx
0x14000c3f9  dec     ebx
0x14000c3fb  test    ebx, ebx
0x14000c3fd  jg      short loc_14000C390
0x14000c3ff  movsxd  rax, r14d
0x14000c402  xor     r15d, r15d
0x14000c405  shl     rax, 4
0x14000c409  lea     r14, [rbp+4Fh+var_B0]
0x14000c40d  add     r14, rax
0x14000c410  mov     rsi, [r14]
0x14000c413  cmp     rsi, r14
0x14000c416  jz      loc_14000C4E1
0x14000c41c  movsxd  rax, ebx
0x14000c41f  lea     r13, [rbp+4Fh+var_B0]
0x14000c423  shl     rax, 4
0x14000c427  add     r13, rax
0x14000c42a  lea     rcx, [rsi-68h]; Table
0x14000c42e  mov     [rsp+110h+TableContext], 0; TableContext
0x14000c437  lea     r9, ?SiTableFreeRoutine@@YAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x14000c43e  lea     r8, ?SiTableAllocateRoutine@@YAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x14000c445  lea     rdx, ?SiFdTableCompareRoutine@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x14000c44c  call    cs:__imp_RtlInitializeGenericTableAvl
0x14000c452  mov     rbx, [r13+0]
0x14000c456  jmp     short loc_14000C4CD
0x14000c458  lea     rdx, [rbx-0C8h]
0x14000c45f  mov     [rbp+4Fh+Buffer], rdx
0x14000c463  mov     eax, [rsi-0C8h]
0x14000c469  cmp     eax, r12d
0x14000c46c  jz      short loc_14000C492
0x14000c46e  add     eax, 0FFFFFFFEh
0x14000c471  mov     ecx, eax
0x14000c473  add     rcx, rcx
0x14000c476  mov     rax, [rdx+rcx*8+14h]
0x14000c47b  cmp     rax, [rsi-0C4h]
0x14000c482  jnz     short loc_14000C4CA
0x14000c484  mov     rax, [rdx+rcx*8+1Ch]
0x14000c489  cmp     rax, [rsi-0BCh]
0x14000c490  jnz     short loc_14000C4CA
0x14000c492  mov     rdx, [rdx+58h]
0x14000c496  xor     ecx, ecx; hAlgorithm
0x14000c498  add     rdx, 10h; pbBuffer
0x14000c49c  lea     r9d, [rcx+2]; dwFlags
0x14000c4a0  lea     r8d, [rcx+4]; cbBuffer
0x14000c4a4  call    cs:__imp_BCryptGenRandom
0x14000c4aa  lea     r9, [rsp+110h+NewElement]; NewElement
0x14000c4af  mov     r8d, 8; BufferSize
0x14000c4b5  lea     rdx, [rbp+4Fh+Buffer]; Buffer
0x14000c4b9  lea     rcx, [rsi-68h]; Table
0x14000c4bd  call    cs:__imp_RtlInsertElementGenericTableAvl
0x14000c4c3  cmp     dword ptr [rsp+110h+NewElement], 0
0x14000c4c8  jz      short loc_14000C503
0x14000c4ca  mov     rbx, [rbx]
0x14000c4cd  cmp     rbx, r13
0x14000c4d0  jnz     short loc_14000C458
0x14000c4d2  mov     rsi, [rsi]
0x14000c4d5  inc     r15d
0x14000c4d8  cmp     rsi, r14
0x14000c4db  jnz     loc_14000C42A
0x14000c4e1  xor     edx, edx
0x14000c4e3  lea     ecx, [r15+4]
0x14000c4e7  mov     eax, ecx
0x14000c4e9  xor     esi, esi
0x14000c4eb  div     r15d
0x14000c4ee  sub     ecx, edx
0x14000c4f0  xor     edx, edx
0x14000c4f2  mov     eax, ecx
0x14000c4f4  div     r15d
0x14000c4f7  mov     r13d, eax
0x14000c4fa  test    eax, eax
0x14000c4fc  jle     short loc_14000C569
0x14000c4fe  mov     rbx, [r14]
0x14000c501  jmp     short loc_14000C550
0x14000c503  mov     ecx, 1392h
0x14000c508  jmp     short loc_14000C563
0x14000c50a  lea     rdx, [rbp+4Fh+RestartKey]; RestartKey
0x14000c50e  mov     [rbp+4Fh+RestartKey], 0
0x14000c516  lea     rcx, [rbx-68h]; Table
0x14000c51a  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x14000c520  test    rax, rax
0x14000c523  jz      short loc_14000C54D
0x14000c525  mov     rdx, [rax]
0x14000c528  lea     rcx, [rbx-68h]; Table
0x14000c52c  mov     [rbp+4Fh+Buffer], rdx
0x14000c530  mov     r8, [rdx+58h]
0x14000c534  mov     rdx, rax; Buffer
0x14000c537  or      dword ptr [r8+14h], 4
0x14000c53c  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14000c542  movzx   eax, al
0x14000c545  mov     dword ptr [rsp+110h+NewElement], eax
0x14000c549  test    eax, eax
0x14000c54b  jz      short loc_14000C55E
0x14000c54d  mov     rbx, [rbx]
0x14000c550  cmp     rbx, r14
0x14000c553  jnz     short loc_14000C50A
0x14000c555  inc     esi
0x14000c557  cmp     esi, r13d
0x14000c55a  jl      short loc_14000C4FE
0x14000c55c  jmp     short loc_14000C569
0x14000c55e  mov     ecx, 490h; dwErrCode
0x14000c563  call    cs:__imp_SetLastError
0x14000c569  mov     eax, r12d
0x14000c56c  lea     rbx, [rbp+4Fh+var_B0]
0x14000c570  shl     rax, 4
0x14000c574  add     rbx, rax
0x14000c577  mov     rax, [rbx]
0x14000c57a  cmp     rax, rbx
0x14000c57d  jz      short loc_14000C5DE
0x14000c57f  mov     rcx, [rax]
0x14000c582  cmp     [rcx+8], rax
0x14000c586  jnz     loc_14000C682
0x14000c58c  mov     rdx, [rax+8]
0x14000c590  cmp     [rdx], rax
0x14000c593  jnz     loc_14000C682
0x14000c599  lea     r14, [rax-0C8h]
0x14000c5a0  mov     [rdx], rcx
0x14000c5a3  lea     rsi, [r14+60h]
0x14000c5a7  mov     [rcx+8], rdx
0x14000c5ab  jmp     short loc_14000C5B9
0x14000c5ad  mov     rdx, rax; Buffer
0x14000c5b0  mov     rcx, rsi; Table
0x14000c5b3  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14000c5b9  lea     rdx, [rbp+4Fh+var_C0]; RestartKey
0x14000c5bd  mov     [rbp+4Fh+var_C0], 0
0x14000c5c5  mov     rcx, rsi; Table
0x14000c5c8  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x14000c5ce  test    rax, rax
0x14000c5d1  jnz     short loc_14000C5AD
0x14000c5d3  mov     rcx, r14; hMem
0x14000c5d6  call    cs:__imp_LocalFree
0x14000c5dc  jmp     short loc_14000C577
0x14000c5de  sub     r12d, 1
0x14000c5e2  jns     short loc_14000C569
0x14000c5e4  mov     rax, [rdi]
0x14000c5e7  cmp     [rax+8], rdi
0x14000c5eb  jnz     loc_14000C682
0x14000c5f1  mov     rcx, [rdi+8]
0x14000c5f5  cmp     [rcx], rdi
0x14000c5f8  jnz     loc_14000C682
0x14000c5fe  mov     rax, [rsp+110h+var_D8]
0x14000c603  lea     rdx, [rsp+110h+var_D8]
0x14000c608  cmp     [rax+8], rdx
0x14000c60c  jnz     short loc_14000C682
0x14000c60e  mov     rax, [rsp+110h+var_D0]
0x14000c613  lea     rdx, [rsp+110h+var_D8]
0x14000c618  cmp     [rax], rdx
0x14000c61b  jnz     short loc_14000C682
0x14000c61d  lea     rax, [rsp+110h+var_D8]
0x14000c622  mov     [rcx], rax
0x14000c625  lea     rdx, [rsp+110h+var_D8]
0x14000c62a  mov     rax, [rsp+110h+var_D0]
0x14000c62f  mov     [rdi+8], rax
0x14000c633  mov     [rax], rdi
0x14000c636  mov     rax, [rsp+110h+var_D8]
0x14000c63b  mov     [rsp+110h+var_D0], rcx
0x14000c640  cmp     [rax+8], rdx
0x14000c644  jnz     short loc_14000C682
0x14000c646  lea     rdx, [rsp+110h+var_D8]
0x14000c64b  cmp     [rcx], rdx
0x14000c64e  jnz     short loc_14000C682
0x14000c650  mov     [rcx], rax
0x14000c653  mov     [rax+8], rcx
0x14000c657  mov     eax, dword ptr [rsp+110h+NewElement]
0x14000c65b  mov     rcx, [rbp+4Fh+var_40]
0x14000c65f  xor     rcx, rsp; StackCookie
0x14000c662  call    __security_check_cookie
0x14000c667  mov     rbx, [rsp+110h+arg_18]
0x14000c66f  add     rsp, 0E0h
0x14000c676  pop     r15
0x14000c678  pop     r14
0x14000c67a  pop     r13
0x14000c67c  pop     r12
0x14000c67e  pop     rdi
0x14000c67f  pop     rsi
0x14000c680  pop     rbp
0x14000c681  retn
0x14000c682  mov     ecx, 3
0x14000c687  int     29h; Win8: RtlFailFast(ecx)
```
