# CUniqueIdMap::AcquireId(ulong *)

- ea: `0x1800185b0`
- end: `0x180018c3d`
- name: `?AcquireId@CUniqueIdMap@@QEAAJPEAK@Z`
- size: `1677`
- prototype: `__int64 __fastcall(CUniqueIdMap *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180048060`

## callees

- `0x1800185b0`
- `0x180033f60`
- `0x18003440c`
- `0x180034494`
- `0x180034e10`
- `0x18003e538`
- `0x1800511f0`
- `0x1800514bc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018a4d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018a4d`
- `ntdll!EtwEventWriteTransfer` at `0x18001870b`
- `ntdll!EtwEventWriteTransfer` at `0x180018994`
- `ntdll!EtwEventWriteTransfer` at `0x18001870b`
- `ntdll!EtwEventWriteTransfer` at `0x180018994`
- `ntdll!RtlAcquireResourceExclusive` at `0x180018605`
- `ntdll!RtlAcquireResourceExclusive` at `0x180018605`
- `ntdll!RtlReleaseResource` at `0x180018bef`
- `ntdll!RtlReleaseResource` at `0x180018bef`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CUniqueIdMap::AcquireId(CUniqueIdMap *this, unsigned int *a2)
{
  CUniqueIdMap *v2; // rdi
  unsigned int v3; // r13d
  _QWORD *v4; // rsi
  _QWORD *v5; // rbx
  _QWORD *v6; // rdx
  __int64 *v7; // rax
  _QWORD *v8; // rdi
  unsigned int v9; // ecx
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  __int64 *v12; // rcx
  _QWORD *v13; // rdi
  _QWORD *v14; // rbx
  void *v15; // rcx
  _QWORD *v16; // rdx
  _BYTE *v17; // r8
  _QWORD *v18; // rax
  __int64 *v19; // r8
  __int64 i; // rcx
  __int64 v21; // r8
  _QWORD *j; // r9
  __int64 *v23; // rcx
  __int64 *v24; // rcx
  void *v25; // rax
  char *v26; // r15
  unsigned __int64 v27; // rsi
  __int64 v28; // r8
  __int64 *v29; // rcx
  __int64 **v30; // r12
  __int64 *v31; // r14
  _DWORD *v32; // rdi
  __int64 v33; // rcx
  float v34; // xmm0_4
  unsigned __int64 v35; // rbx
  float v36; // xmm3_4
  float v37; // xmm2_4
  __int64 v38; // rcx
  float v39; // xmm0_4
  unsigned __int64 v40; // rcx
  unsigned __int64 v41; // rax
  unsigned __int64 v42; // rcx
  __int64 v43; // r8
  __int64 *v44; // rcx
  _QWORD *v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rsi
  __int64 *v48; // rdx
  unsigned int v50; // [rsp+30h] [rbp-B8h] BYREF
  unsigned int v51; // [rsp+34h] [rbp-B4h]
  unsigned int v52; // [rsp+38h] [rbp-B0h] BYREF
  __int64 v53; // [rsp+40h] [rbp-A8h] BYREF
  _DWORD *v54; // [rsp+48h] [rbp-A0h]
  CUniqueIdMap *v55; // [rsp+50h] [rbp-98h]
  unsigned int *v56; // [rsp+58h] [rbp-90h]
  char *v57; // [rsp+60h] [rbp-88h]
  int v58; // [rsp+68h] [rbp-80h]
  char *v59; // [rsp+70h] [rbp-78h] BYREF
  int v60; // [rsp+78h] [rbp-70h]
  int v61; // [rsp+7Ch] [rbp-6Ch]
  __int16 *v62; // [rsp+80h] [rbp-68h]
  int v63; // [rsp+88h] [rbp-60h]
  int v64; // [rsp+8Ch] [rbp-5Ch]
  const char *v65; // [rsp+90h] [rbp-58h]
  __int64 v66; // [rsp+98h] [rbp-50h]
  unsigned int *v67; // [rsp+A0h] [rbp-48h]
  __int64 v68; // [rsp+A8h] [rbp-40h]

  v56 = a2;
  v2 = this;
  v55 = this;
  v57 = (char *)this + 8;
  v58 = 1;
  if ( *((_DWORD *)this + 26) )
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 8), 1u);
  if ( *((_QWORD *)v2 + 15) )
  {
    v4 = (_QWORD *)((char *)v2 + 112);
    v5 = (_QWORD *)*((_QWORD *)v2 + 14);
    v6 = (_QWORD *)*v5;
    v3 = *(_DWORD *)(*v5 + 28LL);
    v51 = v3;
    v7 = (__int64 *)v5[1];
    v8 = v5;
    if ( *((_BYTE *)v7 + 25) )
    {
      v10 = v5;
    }
    else
    {
      do
      {
        v9 = *((_DWORD *)v7 + 7);
        if ( v9 >= v3 )
        {
          if ( *((_BYTE *)v8 + 25) && v3 < v9 )
            v8 = v7;
          v5 = v7;
          v7 = (__int64 *)*v7;
        }
        else
        {
          v7 = (__int64 *)v7[2];
        }
      }
      while ( !*((_BYTE *)v7 + 25) );
      v10 = (_QWORD *)*v4;
    }
    v11 = v10 + 1;
    if ( !*((_BYTE *)v8 + 25) )
      v11 = v8;
    v12 = (__int64 *)*v11;
    if ( !*(_BYTE *)(*v11 + 25LL) )
    {
      do
      {
        if ( v3 >= *((_DWORD *)v12 + 7) )
        {
          v12 = (__int64 *)v12[2];
        }
        else
        {
          v8 = v12;
          v12 = (__int64 *)*v12;
        }
      }
      while ( !*((_BYTE *)v12 + 25) );
    }
    if ( v5 == v6 && *((_BYTE *)v8 + 25) )
    {
      v13 = (_QWORD *)*v4;
      v14 = *(_QWORD **)(*v4 + 8LL);
      while ( !*((_BYTE *)v14 + 25) )
      {
        std::_Tree_val<std::_Tree_simple_types<unsigned long>>::_Erase_tree<std::allocator<std::_Tree_node<unsigned long,void *>>>(
          v4,
          v4,
          v14[2]);
        v15 = v14;
        v14 = (_QWORD *)*v14;
        operator delete(v15);
      }
      v13[1] = v13;
      *v13 = v13;
      v13[2] = v13;
      v4[1] = 0;
    }
    else
    {
      while ( v5 != v8 )
      {
        v16 = v5;
        v17 = (_BYTE *)v5[2];
        if ( v17[25] )
        {
          v18 = v5;
          v19 = v5 + 1;
          for ( i = v5[1]; !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
          {
            if ( v5 != *(_QWORD **)(i + 16) )
              break;
            v5 = (_QWORD *)i;
          }
          v5 = (_QWORD *)i;
          v21 = *v19;
          for ( j = v4; !*(_BYTE *)(v21 + 25); v21 = *(_QWORD *)(v21 + 8) )
          {
            if ( v18 != *(_QWORD **)(v21 + 16) )
              break;
            v18 = (_QWORD *)v21;
          }
        }
        else
        {
          v23 = *(__int64 **)v17;
          if ( *(_BYTE *)(*(_QWORD *)v17 + 25LL) )
          {
            v5 = (_QWORD *)v5[2];
          }
          else
          {
            do
            {
              v5 = v23;
              v23 = (__int64 *)*v23;
            }
            while ( !*((_BYTE *)v23 + 25) );
          }
          j = v4;
          v24 = *(__int64 **)v17;
          if ( !*(_BYTE *)(*(_QWORD *)v17 + 25LL) )
          {
            do
              v24 = (__int64 *)*v24;
            while ( !*((_BYTE *)v24 + 25) );
          }
        }
        v25 = (void *)std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,SmartPtr<CRemoteDisplayDeviceContext>>>>::_Extract(
                        j,
                        v16);
        operator delete(v25);
      }
    }
    if ( (unsigned int)dword_18012E170 > 5 )
    {
      v50 = v3;
      v67 = &v50;
      v68 = 4;
      v65 = "AcquireId: Using Id from AvailableIdsList";
      v66 = 42;
      v53 = 0x50B000000LL;
      v54 = 0;
      v59 = (char *)off_18012E178;
      v60 = *(unsigned __int16 *)off_18012E178;
      v61 = 2;
      v62 = word_18010D93A;
      v63 = 26;
      v64 = 1;
      v52 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(RegHandle, &v53, 0, 0, 4, &v59);
    }
    v2 = v55;
  }
  else
  {
    v3 = *((_DWORD *)v2 + 1);
    v51 = v3;
    *((_DWORD *)v2 + 1) = v3 + 1;
    if ( (unsigned int)dword_18012E170 > 5 )
    {
      v52 = v3;
      v67 = &v52;
      v68 = 4;
      v65 = "AcquireId: Generating new Id";
      v66 = 29;
      v53 = 0x50B000000LL;
      v54 = 0;
      v59 = (char *)off_18012E178;
      v60 = *(unsigned __int16 *)off_18012E178;
      v61 = 2;
      v62 = (__int16 *)qword_18010D960;
      v63 = 26;
      v64 = 1;
      v50 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(RegHandle, &v53, 0, 0, 4, &v59);
    }
  }
  v26 = (char *)v2 + 128;
  _mm_lfence();
  v27 = 0x100000001B3LL
      * (HIBYTE(v51)
       ^ (0x100000001B3LL
        * (BYTE2(v51)
         ^ (0x100000001B3LL * (BYTE1(v51) ^ (0x100000001B3LL * ((unsigned __int8)v3 ^ 0xCBF29CE484222325uLL)))))));
  v28 = *((_QWORD *)v2 + 19);
  v29 = *(__int64 **)(v28 + 16 * (*((_QWORD *)v2 + 22) & v27) + 8);
  v30 = (__int64 **)((char *)v2 + 136);
  v31 = (__int64 *)*((_QWORD *)v2 + 17);
  if ( v29 == v31 )
  {
LABEL_51:
    if ( *((_QWORD *)v2 + 18) == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("unordered_map/set too long");
    v53 = (__int64)v2 + 136;
    v54 = 0;
    v32 = operator new(0x18u);
    v54 = v32;
    v32[4] = v3;
    v33 = *((_QWORD *)v26 + 2) + 1LL;
    if ( v33 < 0 )
      v34 = (float)(v33 & 1 | (unsigned int)((unsigned __int64)v33 >> 1))
          + (float)(v33 & 1 | (unsigned int)((unsigned __int64)v33 >> 1));
    else
      v34 = (float)(int)v33;
    v35 = *((_QWORD *)v26 + 7);
    v36 = *(float *)v26;
    if ( (v35 & 0x8000000000000000uLL) != 0LL )
    {
      v38 = *((_QWORD *)v26 + 7) & 1LL | (v35 >> 1);
      v37 = (float)(int)v38 + (float)(int)v38;
    }
    else
    {
      v37 = (float)(int)v35;
    }
    if ( (float)(v34 / v37) > v36 )
    {
      v39 = o_ceilf_0(v34 / v36);
      v40 = 0;
      if ( v39 >= 9.223372e18 )
      {
        v39 = v39 - 9.223372e18;
        if ( v39 < 9.223372e18 )
          v40 = 0x8000000000000000uLL;
      }
      v41 = v40 + (unsigned int)(int)v39;
      v42 = 8;
      if ( v41 > 8 )
        v42 = v41;
      if ( v35 < v42 )
      {
        if ( v35 >= 0x200 || (v35 *= 8LL, v35 < v42) )
          v35 = v42;
      }
      std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::_Forced_rehash(
        v26,
        v35);
      v43 = *((_QWORD *)v26 + 3);
      v44 = *(__int64 **)(v43 + 16 * (*((_QWORD *)v26 + 6) & v27) + 8);
      v31 = *v30;
      if ( v44 != *v30 )
      {
        while ( v32[4] != *((_DWORD *)v44 + 4) )
        {
          if ( v44 == *(__int64 **)(v43 + 16 * (*((_QWORD *)v26 + 6) & v27)) )
          {
            v31 = v44;
            goto LABEL_75;
          }
          v44 = (__int64 *)v44[1];
        }
        v31 = (__int64 *)*v44;
      }
    }
LABEL_75:
    v45 = (_QWORD *)v31[1];
    ++*((_QWORD *)v26 + 2);
    *(_QWORD *)v32 = v31;
    *((_QWORD *)v32 + 1) = v45;
    *v45 = v32;
    v31[1] = (__int64)v32;
    v46 = *((_QWORD *)v26 + 3);
    v47 = 2 * (*((_QWORD *)v26 + 6) & v27);
    v48 = *(__int64 **)(v46 + 8 * v47);
    if ( v48 == *v30 )
    {
      *(_QWORD *)(v46 + 8 * v47) = v32;
LABEL_80:
      *(_QWORD *)(v46 + 8 * v47 + 8) = v32;
      goto LABEL_81;
    }
    if ( v48 == v31 )
    {
      *(_QWORD *)(v46 + 8 * v47) = v32;
    }
    else if ( *(_QWORD **)(v46 + 8 * v47 + 8) == v45 )
    {
      goto LABEL_80;
    }
LABEL_81:
    v2 = v55;
    goto LABEL_82;
  }
  while ( v3 != *((_DWORD *)v29 + 4) )
  {
    if ( v29 == *(__int64 **)(v28
                            + 16
                            * (*((_QWORD *)v2 + 22)
                             & (0x100000001B3LL
                              * (HIBYTE(v51)
                               ^ (0x100000001B3LL
                                * (BYTE2(v51)
                                 ^ (0x100000001B3LL
                                  * (BYTE1(v51) ^ (0x100000001B3LL * ((unsigned __int8)v3 ^ 0xCBF29CE484222325uLL)))))))))) )
    {
      v31 = v29;
      goto LABEL_51;
    }
    v29 = (__int64 *)v29[1];
  }
LABEL_82:
  ++*(_DWORD *)v2;
  *v56 = v3;
  if ( *((_DWORD *)v2 + 26) )
    RtlReleaseResource((PRTL_RESOURCE)((char *)v2 + 8));
  return 0;
}

```

## disassembly

```asm
0x1800185b0  mov     [rsp+arg_10], rbx
0x1800185b5  mov     [rsp+arg_18], rsi
0x1800185ba  push    rdi
0x1800185bb  push    r12
0x1800185bd  push    r13
0x1800185bf  push    r14
0x1800185c1  push    r15
0x1800185c3  sub     rsp, 0C0h
0x1800185ca  mov     rax, cs:__security_cookie
0x1800185d1  xor     rax, rsp
0x1800185d4  mov     [rsp+0E8h+var_38], rax
0x1800185dc  mov     [rsp+0E8h+var_90], rdx
0x1800185e1  mov     rdi, rcx
0x1800185e4  mov     [rsp+0E8h+var_98], rcx
0x1800185e9  lea     rax, [rcx+8]
0x1800185ed  mov     [rsp+0E8h+var_88], rax
0x1800185f2  mov     [rsp+0E8h+var_80], 1
0x1800185fa  cmp     dword ptr [rax+60h], 0
0x1800185fe  jz      short loc_180018612
0x180018600  mov     dl, 1; Wait
0x180018602  mov     rcx, rax; Resource
0x180018605  call    cs:__imp_RtlAcquireResourceExclusive
0x18001860c  nop     dword ptr [rax+rax+00h]
0x180018611  nop
0x180018612  cmp     qword ptr [rdi+78h], 0
0x180018617  jnz     loc_180018723
0x18001861d  mov     r13d, [rdi+4]
0x180018621  mov     [rsp+0E8h+var_B4], r13d
0x180018626  lea     eax, [r13+1]
0x18001862a  mov     [rdi+4], eax
0x18001862d  mov     eax, cs:dword_18012E170
0x180018633  cmp     eax, 5
0x180018636  jbe     loc_18001871C
0x18001863c  mov     [rsp+0E8h+var_B0], r13d
0x180018641  lea     rax, [rsp+0E8h+var_B0]
0x180018646  mov     [rsp+0E8h+var_48], rax
0x18001864e  mov     [rsp+0E8h+var_40], 4
0x18001865a  xor     ebx, ebx
0x18001865c  lea     rax, aAcquireidGener; "AcquireId: Generating new Id"
0x180018663  mov     [rsp+0E8h+var_58], rax
0x18001866b  mov     [rsp+0E8h+var_50], 1Dh
0x180018677  mov     dword ptr [rsp+0E8h+var_A8], 0B000000h
0x18001867f  movzx   eax, cs:word_18010D956
0x180018686  mov     dword ptr [rsp+0E8h+var_A8+4], eax
0x18001868a  mov     [rsp+0E8h+var_A0], rbx
0x18001868f  mov     rax, cs:off_18012E178
0x180018696  mov     [rsp+0E8h+var_78], rax
0x18001869b  movzx   eax, word ptr [rax]
0x18001869e  mov     [rsp+0E8h+var_70], eax
0x1800186a2  mov     [rsp+0E8h+var_6C], 2
0x1800186aa  lea     rax, qword_18010D960
0x1800186b1  mov     [rsp+0E8h+var_68], rax
0x1800186b9  mov     [rsp+0E8h+var_60], 1Ah
0x1800186c4  mov     [rsp+0E8h+var_5C], 1
0x1800186cf  lea     rax, _TraceLoggingMetadataEnd
0x1800186d6  lea     rcx, _TraceLoggingMetadata
0x1800186dd  sub     eax, ecx
0x1800186df  mov     [rsp+0E8h+var_B8], eax
0x1800186e3  mov     eax, [rsp+0E8h+var_B8]
0x1800186e7  lea     rax, [rsp+0E8h+var_78]
0x1800186ec  mov     [rsp+0E8h+var_C0], rax
0x1800186f1  mov     [rsp+0E8h+var_C8], 4
0x1800186f9  xor     r9d, r9d
0x1800186fc  xor     r8d, r8d
0x1800186ff  lea     rdx, [rsp+0E8h+var_A8]
0x180018704  mov     rcx, cs:RegHandle
0x18001870b  call    cs:__imp_EtwEventWriteTransfer
0x180018712  nop     dword ptr [rax+rax+00h]
0x180018717  jmp     loc_1800189A5
0x18001871c  xor     ebx, ebx
0x18001871e  jmp     loc_1800189A5
0x180018723  lea     rsi, [rdi+70h]
0x180018727  mov     rbx, [rsi]
0x18001872a  mov     rdx, [rbx]
0x18001872d  mov     r13d, [rdx+1Ch]
0x180018731  mov     [rsp+0E8h+var_B4], r13d
0x180018736  mov     rax, [rbx+8]
0x18001873a  mov     rdi, rbx
0x18001873d  cmp     byte ptr [rax+19h], 0
0x180018741  jnz     short loc_18001876F
0x180018743  mov     ecx, [rax+1Ch]
0x180018746  cmp     ecx, r13d
0x180018749  jnb     short loc_180018751
0x18001874b  mov     rax, [rax+10h]
0x18001874f  jmp     short loc_180018764
0x180018751  cmp     byte ptr [rdi+19h], 0
0x180018755  jz      short loc_18001875E
0x180018757  cmp     r13d, ecx
0x18001875a  cmovb   rdi, rax
0x18001875e  mov     rbx, rax
0x180018761  mov     rax, [rax]
0x180018764  cmp     byte ptr [rax+19h], 0
0x180018768  jz      short loc_180018743
0x18001876a  mov     rax, [rsi]
0x18001876d  jmp     short loc_180018772
0x18001876f  mov     rax, rbx
0x180018772  add     rax, 8
0x180018776  cmp     byte ptr [rdi+19h], 0
0x18001877a  cmovz   rax, rdi
0x18001877e  mov     rcx, [rax]
0x180018781  cmp     byte ptr [rcx+19h], 0
0x180018785  jnz     short loc_1800187A0
0x180018787  cmp     r13d, [rcx+1Ch]
0x18001878b  jnb     short loc_180018795
0x18001878d  mov     rdi, rcx
0x180018790  mov     rcx, [rcx]
0x180018793  jmp     short loc_180018799
0x180018795  mov     rcx, [rcx+10h]
0x180018799  cmp     byte ptr [rcx+19h], 0
0x18001879d  jz      short loc_180018787
0x18001879f  nop
0x1800187a0  cmp     rbx, rdx
0x1800187a3  jnz     short loc_180018800
0x1800187a5  cmp     byte ptr [rdi+19h], 0
0x1800187a9  jz      short loc_180018800
0x1800187ab  mov     rdi, [rsi]
0x1800187ae  mov     rbx, [rdi+8]
0x1800187b2  cmp     byte ptr [rbx+19h], 0
0x1800187b6  jnz     short loc_1800187E5
0x1800187b8  nop     dword ptr [rax+rax+00000000h]
0x1800187c0  mov     r8, [rbx+10h]
0x1800187c4  mov     rdx, rsi
0x1800187c7  mov     rcx, rsi
0x1800187ca  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@KPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@KPEAX@std@@@1@PEAU?$_Tree_node@KPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<ulong>>::_Erase_tree<std::allocator<std::_Tree_node<ulong,void *>>>(std::allocator<std::_Tree_node<ulong,void *>> &,std::_Tree_node<ulong,void *> *)
0x1800187cf  mov     rcx, rbx; Block
0x1800187d2  mov     rbx, [rbx]
0x1800187d5  mov     edx, 20h ; ' '
0x1800187da  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800187df  cmp     byte ptr [rbx+19h], 0
0x1800187e3  jz      short loc_1800187C0
0x1800187e5  mov     [rdi+8], rdi
0x1800187e9  mov     [rdi], rdi
0x1800187ec  mov     [rdi+10h], rdi
0x1800187f0  xor     ebx, ebx
0x1800187f2  mov     [rsi+8], rbx
0x1800187f6  jmp     loc_1800188B8
0x180018800  cmp     rbx, rdi
0x180018803  jz      loc_1800188B6
0x180018809  mov     rdx, rbx
0x18001880c  mov     r8, [rbx+10h]
0x180018810  cmp     byte ptr [r8+19h], 0
0x180018815  jz      short loc_180018866
0x180018817  mov     rax, rbx
0x18001881a  lea     r8, [rbx+8]
0x18001881e  mov     rcx, [r8]
0x180018821  cmp     byte ptr [rcx+19h], 0
0x180018825  jnz     short loc_18001883A
0x180018827  cmp     rbx, [rcx+10h]
0x18001882b  jnz     short loc_18001883A
0x18001882d  mov     rbx, rcx
0x180018830  mov     rcx, [rcx+8]
0x180018834  cmp     byte ptr [rcx+19h], 0
0x180018838  jz      short loc_180018827
0x18001883a  mov     rbx, rcx
0x18001883d  mov     r8, [r8]
0x180018840  mov     r9, rsi
0x180018843  cmp     byte ptr [r8+19h], 0
0x180018848  jnz     short loc_18001889C
0x18001884a  nop     word ptr [rax+rax+00h]
0x180018850  cmp     rax, [r8+10h]
0x180018854  jnz     short loc_18001889C
0x180018856  mov     rax, r8
0x180018859  mov     r8, [r8+8]
0x18001885d  cmp     byte ptr [r8+19h], 0
0x180018862  jz      short loc_180018850
0x180018864  jmp     short loc_18001889C
0x180018866  mov     rcx, [r8]
0x180018869  cmp     byte ptr [rcx+19h], 0
0x18001886d  jnz     short loc_180018881
0x18001886f  nop
0x180018870  mov     rbx, rcx
0x180018873  mov     rax, [rcx]
0x180018876  mov     rcx, rax
0x180018879  cmp     byte ptr [rax+19h], 0
0x18001887d  jz      short loc_180018870
0x18001887f  jmp     short loc_180018884
0x180018881  mov     rbx, r8
0x180018884  mov     r9, rsi
0x180018887  mov     rcx, [r8]
0x18001888a  cmp     byte ptr [rcx+19h], 0
0x18001888e  jnz     short loc_18001889C
0x180018890  mov     rax, [rcx]
0x180018893  mov     rcx, rax
0x180018896  cmp     byte ptr [rax+19h], 0
0x18001889a  jz      short loc_180018890
0x18001889c  mov     rcx, r9
0x18001889f  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$SmartPtr@VCRemoteDisplayDeviceContext@@@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$SmartPtr@VCRemoteDisplayDeviceContext@@@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$SmartPtr@VCRemoteDisplayDeviceContext@@@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,SmartPtr<CRemoteDisplayDeviceContext>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,SmartPtr<CRemoteDisplayDeviceContext>>>>,std::_Iterator_base0>)
0x1800188a4  mov     edx, 20h ; ' '
0x1800188a9  mov     rcx, rax; Block
0x1800188ac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800188b1  jmp     loc_180018800
0x1800188b6  xor     ebx, ebx
0x1800188b8  mov     eax, cs:dword_18012E170
0x1800188be  cmp     eax, 5
0x1800188c1  jbe     loc_1800189A0
0x1800188c7  mov     [rsp+0E8h+var_B8], r13d
0x1800188cc  lea     rax, [rsp+0E8h+var_B8]
0x1800188d1  mov     [rsp+0E8h+var_48], rax
0x1800188d9  mov     [rsp+0E8h+var_40], 4
0x1800188e5  lea     rax, aAcquireidUsing; "AcquireId: Using Id from AvailableIdsLi"...
0x1800188ec  mov     [rsp+0E8h+var_58], rax
0x1800188f4  mov     [rsp+0E8h+var_50], 2Ah ; '*'
0x180018900  mov     dword ptr [rsp+0E8h+var_A8], 0B000000h
0x180018908  movzx   eax, cs:word_18010D930
0x18001890f  mov     dword ptr [rsp+0E8h+var_A8+4], eax
0x180018913  mov     [rsp+0E8h+var_A0], rbx
0x180018918  mov     rax, cs:off_18012E178
0x18001891f  mov     [rsp+0E8h+var_78], rax
0x180018924  movzx   eax, word ptr [rax]
0x180018927  mov     [rsp+0E8h+var_70], eax
0x18001892b  mov     [rsp+0E8h+var_6C], 2
0x180018933  lea     rax, word_18010D93A
0x18001893a  mov     [rsp+0E8h+var_68], rax
0x180018942  mov     [rsp+0E8h+var_60], 1Ah
0x18001894d  mov     [rsp+0E8h+var_5C], 1
0x180018958  lea     rax, _TraceLoggingMetadataEnd
0x18001895f  lea     rcx, _TraceLoggingMetadata
0x180018966  sub     eax, ecx
0x180018968  mov     [rsp+0E8h+var_B0], eax
0x18001896c  mov     eax, [rsp+0E8h+var_B0]
0x180018970  lea     rax, [rsp+0E8h+var_78]
0x180018975  mov     [rsp+0E8h+var_C0], rax
0x18001897a  mov     [rsp+0E8h+var_C8], 4
0x180018982  xor     r9d, r9d
0x180018985  xor     r8d, r8d
0x180018988  lea     rdx, [rsp+0E8h+var_A8]
0x18001898d  mov     rcx, cs:RegHandle
0x180018994  call    cs:__imp_EtwEventWriteTransfer
0x18001899b  nop     dword ptr [rax+rax+00h]
0x1800189a0  mov     rdi, [rsp+0E8h+var_98]
0x1800189a5  lea     r15, [rdi+80h]
0x1800189ac  lfence
0x1800189af  movzx   esi, r13b
0x1800189b3  mov     rax, 0CBF29CE484222325h
0x1800189bd  xor     rsi, rax
0x1800189c0  mov     rcx, 100000001B3h
0x1800189ca  imul    rsi, rcx
0x1800189ce  movzx   eax, byte ptr [rsp+0E8h+var_B4+1]
0x1800189d3  xor     rsi, rax
0x1800189d6  imul    rsi, rcx
0x1800189da  movzx   eax, byte ptr [rsp+0E8h+var_B4+2]
0x1800189df  xor     rsi, rax
0x1800189e2  imul    rsi, rcx
0x1800189e6  movzx   eax, byte ptr [rsp+0E8h+var_B4+3]
0x1800189eb  xor     rsi, rax
0x1800189ee  imul    rsi, rcx
0x1800189f2  mov     rdx, rsi
0x1800189f5  and     rdx, [r15+30h]
0x1800189f9  mov     r8, [r15+18h]
0x1800189fd  mov     rax, rdx
0x180018a00  add     rax, rax
0x180018a03  mov     rcx, [r8+rax*8+8]
0x180018a08  lea     r12, [r15+8]
0x180018a0c  mov     r14, [r12]
0x180018a10  cmp     rcx, r14
0x180018a13  jz      short loc_180018A36
0x180018a15  add     rdx, rdx
0x180018a18  mov     rax, [r8+rdx*8]
0x180018a1c  nop     dword ptr [rax+00h]
0x180018a20  cmp     r13d, [rcx+10h]
0x180018a24  jz      loc_180018BDB
0x180018a2a  cmp     rcx, rax
0x180018a2d  jnz     loc_180018C32
0x180018a33  mov     r14, rcx
0x180018a36  mov     rax, 0AAAAAAAAAAAAAAAh
0x180018a40  cmp     [r15+10h], rax
0x180018a44  jnz     short loc_180018A59
0x180018a46  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180018a4d  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180018a59  mov     [rsp+0E8h+var_A8], r12
0x180018a5e  mov     [rsp+0E8h+var_A0], rbx
0x180018a63  mov     ecx, 18h; Size
0x180018a68  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018a6d  mov     rdi, rax
0x180018a70  mov     [rsp+0E8h+var_A0], rax
0x180018a75  mov     [rax+10h], r13d
0x180018a79  mov     rcx, [r15+10h]
0x180018a7d  add     rcx, 1
0x180018a81  xorps   xmm0, xmm0
0x180018a84  js      short loc_180018A8D
0x180018a86  cvtsi2ss xmm0, rcx
0x180018a8b  jmp     short loc_180018AA2
0x180018a8d  mov     rax, rcx
0x180018a90  shr     rax, 1
0x180018a93  and     ecx, 1
0x180018a96  or      rax, rcx
0x180018a99  cvtsi2ss xmm0, rax
0x180018a9e  addss   xmm0, xmm0
0x180018aa2  mov     rbx, [r15+38h]
0x180018aa6  movss   xmm3, dword ptr [r15]
0x180018aab  xorps   xmm2, xmm2
0x180018aae  test    rbx, rbx
0x180018ab1  js      short loc_180018ABA
0x180018ab3  cvtsi2ss xmm2, rbx
0x180018ab8  jmp     short loc_180018AD2
0x180018aba  mov     rcx, rbx
0x180018abd  shr     rcx, 1
0x180018ac0  mov     rax, rbx
0x180018ac3  and     eax, 1
0x180018ac6  or      rcx, rax
  ... truncated ...
```
