# CUniqueIdMap::AcquireId(ulong *)

- ea: `0x1800179a0`
- end: `0x180018006`
- name: `?AcquireId@CUniqueIdMap@@QEAAJPEAK@Z`
- size: `1638`
- prototype: `__int64 __fastcall(CUniqueIdMap *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180045c60`

## callees

- `0x1800179a0`
- `0x1800321f0`
- `0x18003269c`
- `0x180032724`
- `0x180033070`
- `0x18003c3b0`
- `0x18004eb58`
- `0x18004ee24`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017e23`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017e23`
- `ntdll!EtwEventWriteTransfer` at `0x180017af5`
- `ntdll!EtwEventWriteTransfer` at `0x180017d74`
- `ntdll!EtwEventWriteTransfer` at `0x180017af5`
- `ntdll!EtwEventWriteTransfer` at `0x180017d74`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800179f5`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800179f5`
- `ntdll!RtlReleaseResource` at `0x180017fbf`
- `ntdll!RtlReleaseResource` at `0x180017fbf`

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
    if ( (unsigned int)dword_180128170 > 5 )
    {
      v50 = v3;
      v67 = &v50;
      v68 = 4;
      v65 = "AcquireId: Using Id from AvailableIdsList";
      v66 = 42;
      v53 = 0x50B000000LL;
      v54 = 0;
      v59 = (char *)off_180128178;
      v60 = *(unsigned __int16 *)off_180128178;
      v61 = 2;
      v62 = word_1801078BA;
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
    if ( (unsigned int)dword_180128170 > 5 )
    {
      v52 = v3;
      v67 = &v52;
      v68 = 4;
      v65 = "AcquireId: Generating new Id";
      v66 = 29;
      v53 = 0x50B000000LL;
      v54 = 0;
      v59 = (char *)off_180128178;
      v60 = *(unsigned __int16 *)off_180128178;
      v61 = 2;
      v62 = (__int16 *)qword_1801078E0;
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
0x1800179a0  mov     [rsp+arg_10], rbx
0x1800179a5  mov     [rsp+arg_18], rsi
0x1800179aa  push    rdi
0x1800179ab  push    r12
0x1800179ad  push    r13
0x1800179af  push    r14
0x1800179b1  push    r15
0x1800179b3  sub     rsp, 0C0h
0x1800179ba  mov     rax, cs:__security_cookie
0x1800179c1  xor     rax, rsp
0x1800179c4  mov     [rsp+0E8h+var_38], rax
0x1800179cc  mov     [rsp+0E8h+var_90], rdx
0x1800179d1  mov     rdi, rcx
0x1800179d4  mov     [rsp+0E8h+var_98], rcx
0x1800179d9  lea     rax, [rcx+8]
0x1800179dd  mov     [rsp+0E8h+var_88], rax
0x1800179e2  mov     [rsp+0E8h+var_80], 1
0x1800179ea  cmp     dword ptr [rax+60h], 0
0x1800179ee  jz      short loc_1800179FC
0x1800179f0  mov     dl, 1; Wait
0x1800179f2  mov     rcx, rax; Resource
0x1800179f5  call    cs:__imp_RtlAcquireResourceExclusive
0x1800179fb  nop
0x1800179fc  cmp     qword ptr [rdi+78h], 0
0x180017a01  jnz     loc_180017B07
0x180017a07  mov     r13d, [rdi+4]
0x180017a0b  mov     [rsp+0E8h+var_B4], r13d
0x180017a10  lea     eax, [r13+1]
0x180017a14  mov     [rdi+4], eax
0x180017a17  mov     eax, cs:dword_180128170
0x180017a1d  cmp     eax, 5
0x180017a20  jbe     loc_180017B00
0x180017a26  mov     [rsp+0E8h+var_B0], r13d
0x180017a2b  lea     rax, [rsp+0E8h+var_B0]
0x180017a30  mov     [rsp+0E8h+var_48], rax
0x180017a38  mov     [rsp+0E8h+var_40], 4
0x180017a44  xor     ebx, ebx
0x180017a46  lea     rax, aAcquireidGener; "AcquireId: Generating new Id"
0x180017a4d  mov     [rsp+0E8h+var_58], rax
0x180017a55  mov     [rsp+0E8h+var_50], 1Dh
0x180017a61  mov     dword ptr [rsp+0E8h+var_A8], 0B000000h
0x180017a69  movzx   eax, cs:word_1801078D6
0x180017a70  mov     dword ptr [rsp+0E8h+var_A8+4], eax
0x180017a74  mov     [rsp+0E8h+var_A0], rbx
0x180017a79  mov     rax, cs:off_180128178
0x180017a80  mov     [rsp+0E8h+var_78], rax
0x180017a85  movzx   eax, word ptr [rax]
0x180017a88  mov     [rsp+0E8h+var_70], eax
0x180017a8c  mov     [rsp+0E8h+var_6C], 2
0x180017a94  lea     rax, qword_1801078E0
0x180017a9b  mov     [rsp+0E8h+var_68], rax
0x180017aa3  mov     [rsp+0E8h+var_60], 1Ah
0x180017aae  mov     [rsp+0E8h+var_5C], 1
0x180017ab9  lea     rax, _TraceLoggingMetadataEnd
0x180017ac0  lea     rcx, _TraceLoggingMetadata
0x180017ac7  sub     eax, ecx
0x180017ac9  mov     [rsp+0E8h+var_B8], eax
0x180017acd  mov     eax, [rsp+0E8h+var_B8]
0x180017ad1  lea     rax, [rsp+0E8h+var_78]
0x180017ad6  mov     [rsp+0E8h+var_C0], rax
0x180017adb  mov     [rsp+0E8h+var_C8], 4
0x180017ae3  xor     r9d, r9d
0x180017ae6  xor     r8d, r8d
0x180017ae9  lea     rdx, [rsp+0E8h+var_A8]
0x180017aee  mov     rcx, cs:RegHandle
0x180017af5  call    cs:__imp_EtwEventWriteTransfer
0x180017afb  jmp     loc_180017D7F
0x180017b00  xor     ebx, ebx
0x180017b02  jmp     loc_180017D7F
0x180017b07  lea     rsi, [rdi+70h]
0x180017b0b  mov     rbx, [rsi]
0x180017b0e  mov     rdx, [rbx]
0x180017b11  mov     r13d, [rdx+1Ch]
0x180017b15  mov     [rsp+0E8h+var_B4], r13d
0x180017b1a  mov     rax, [rbx+8]
0x180017b1e  mov     rdi, rbx
0x180017b21  cmp     byte ptr [rax+19h], 0
0x180017b25  jnz     short loc_180017B53
0x180017b27  mov     ecx, [rax+1Ch]
0x180017b2a  cmp     ecx, r13d
0x180017b2d  jnb     short loc_180017B35
0x180017b2f  mov     rax, [rax+10h]
0x180017b33  jmp     short loc_180017B48
0x180017b35  cmp     byte ptr [rdi+19h], 0
0x180017b39  jz      short loc_180017B42
0x180017b3b  cmp     r13d, ecx
0x180017b3e  cmovb   rdi, rax
0x180017b42  mov     rbx, rax
0x180017b45  mov     rax, [rax]
0x180017b48  cmp     byte ptr [rax+19h], 0
0x180017b4c  jz      short loc_180017B27
0x180017b4e  mov     rax, [rsi]
0x180017b51  jmp     short loc_180017B56
0x180017b53  mov     rax, rbx
0x180017b56  add     rax, 8
0x180017b5a  cmp     byte ptr [rdi+19h], 0
0x180017b5e  cmovz   rax, rdi
0x180017b62  mov     rcx, [rax]
0x180017b65  cmp     byte ptr [rcx+19h], 0
0x180017b69  jnz     short loc_180017B88
0x180017b6b  nop     dword ptr [rax+rax+00h]
0x180017b70  cmp     r13d, [rcx+1Ch]
0x180017b74  jnb     short loc_180017B7E
0x180017b76  mov     rdi, rcx
0x180017b79  mov     rcx, [rcx]
0x180017b7c  jmp     short loc_180017B82
0x180017b7e  mov     rcx, [rcx+10h]
0x180017b82  cmp     byte ptr [rcx+19h], 0
0x180017b86  jz      short loc_180017B70
0x180017b88  cmp     rbx, rdx
0x180017b8b  jnz     short loc_180017BE0
0x180017b8d  cmp     byte ptr [rdi+19h], 0
0x180017b91  jz      short loc_180017BE0
0x180017b93  mov     rdi, [rsi]
0x180017b96  mov     rbx, [rdi+8]
0x180017b9a  cmp     byte ptr [rbx+19h], 0
0x180017b9e  jnz     short loc_180017BC5
0x180017ba0  mov     r8, [rbx+10h]
0x180017ba4  mov     rdx, rsi
0x180017ba7  mov     rcx, rsi
0x180017baa  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@KPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@KPEAX@std@@@1@PEAU?$_Tree_node@KPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<ulong>>::_Erase_tree<std::allocator<std::_Tree_node<ulong,void *>>>(std::allocator<std::_Tree_node<ulong,void *>> &,std::_Tree_node<ulong,void *> *)
0x180017baf  mov     rcx, rbx; Block
0x180017bb2  mov     rbx, [rbx]
0x180017bb5  mov     edx, 20h ; ' '
0x180017bba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017bbf  cmp     byte ptr [rbx+19h], 0
0x180017bc3  jz      short loc_180017BA0
0x180017bc5  mov     [rdi+8], rdi
0x180017bc9  mov     [rdi], rdi
0x180017bcc  mov     [rdi+10h], rdi
0x180017bd0  xor     ebx, ebx
0x180017bd2  mov     [rsi+8], rbx
0x180017bd6  jmp     loc_180017C98
0x180017be0  cmp     rbx, rdi
0x180017be3  jz      loc_180017C96
0x180017be9  mov     rdx, rbx
0x180017bec  mov     r8, [rbx+10h]
0x180017bf0  cmp     byte ptr [r8+19h], 0
0x180017bf5  jz      short loc_180017C46
0x180017bf7  mov     rax, rbx
0x180017bfa  lea     r8, [rbx+8]
0x180017bfe  mov     rcx, [r8]
0x180017c01  cmp     byte ptr [rcx+19h], 0
0x180017c05  jnz     short loc_180017C1A
0x180017c07  cmp     rbx, [rcx+10h]
0x180017c0b  jnz     short loc_180017C1A
0x180017c0d  mov     rbx, rcx
0x180017c10  mov     rcx, [rcx+8]
0x180017c14  cmp     byte ptr [rcx+19h], 0
0x180017c18  jz      short loc_180017C07
0x180017c1a  mov     rbx, rcx
0x180017c1d  mov     r8, [r8]
0x180017c20  mov     r9, rsi
0x180017c23  cmp     byte ptr [r8+19h], 0
0x180017c28  jnz     short loc_180017C7C
0x180017c2a  nop     word ptr [rax+rax+00h]
0x180017c30  cmp     rax, [r8+10h]
0x180017c34  jnz     short loc_180017C7C
0x180017c36  mov     rax, r8
0x180017c39  mov     r8, [r8+8]
0x180017c3d  cmp     byte ptr [r8+19h], 0
0x180017c42  jz      short loc_180017C30
0x180017c44  jmp     short loc_180017C7C
0x180017c46  mov     rcx, [r8]
0x180017c49  cmp     byte ptr [rcx+19h], 0
0x180017c4d  jnz     short loc_180017C61
0x180017c4f  nop
0x180017c50  mov     rbx, rcx
0x180017c53  mov     rax, [rcx]
0x180017c56  mov     rcx, rax
0x180017c59  cmp     byte ptr [rax+19h], 0
0x180017c5d  jz      short loc_180017C50
0x180017c5f  jmp     short loc_180017C64
0x180017c61  mov     rbx, r8
0x180017c64  mov     r9, rsi
0x180017c67  mov     rcx, [r8]
0x180017c6a  cmp     byte ptr [rcx+19h], 0
0x180017c6e  jnz     short loc_180017C7C
0x180017c70  mov     rax, [rcx]
0x180017c73  mov     rcx, rax
0x180017c76  cmp     byte ptr [rax+19h], 0
0x180017c7a  jz      short loc_180017C70
0x180017c7c  mov     rcx, r9
0x180017c7f  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$SmartPtr@VCRemoteDisplayDeviceContext@@@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$SmartPtr@VCRemoteDisplayDeviceContext@@@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$SmartPtr@VCRemoteDisplayDeviceContext@@@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,SmartPtr<CRemoteDisplayDeviceContext>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,SmartPtr<CRemoteDisplayDeviceContext>>>>,std::_Iterator_base0>)
0x180017c84  mov     edx, 20h ; ' '
0x180017c89  mov     rcx, rax; Block
0x180017c8c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017c91  jmp     loc_180017BE0
0x180017c96  xor     ebx, ebx
0x180017c98  mov     eax, cs:dword_180128170
0x180017c9e  cmp     eax, 5
0x180017ca1  jbe     loc_180017D7A
0x180017ca7  mov     [rsp+0E8h+var_B8], r13d
0x180017cac  lea     rax, [rsp+0E8h+var_B8]
0x180017cb1  mov     [rsp+0E8h+var_48], rax
0x180017cb9  mov     [rsp+0E8h+var_40], 4
0x180017cc5  lea     rax, aAcquireidUsing; "AcquireId: Using Id from AvailableIdsLi"...
0x180017ccc  mov     [rsp+0E8h+var_58], rax
0x180017cd4  mov     [rsp+0E8h+var_50], 2Ah ; '*'
0x180017ce0  mov     dword ptr [rsp+0E8h+var_A8], 0B000000h
0x180017ce8  movzx   eax, cs:word_1801078B0
0x180017cef  mov     dword ptr [rsp+0E8h+var_A8+4], eax
0x180017cf3  mov     [rsp+0E8h+var_A0], rbx
0x180017cf8  mov     rax, cs:off_180128178
0x180017cff  mov     [rsp+0E8h+var_78], rax
0x180017d04  movzx   eax, word ptr [rax]
0x180017d07  mov     [rsp+0E8h+var_70], eax
0x180017d0b  mov     [rsp+0E8h+var_6C], 2
0x180017d13  lea     rax, word_1801078BA
0x180017d1a  mov     [rsp+0E8h+var_68], rax
0x180017d22  mov     [rsp+0E8h+var_60], 1Ah
0x180017d2d  mov     [rsp+0E8h+var_5C], 1
0x180017d38  lea     rax, _TraceLoggingMetadataEnd
0x180017d3f  lea     rcx, _TraceLoggingMetadata
0x180017d46  sub     eax, ecx
0x180017d48  mov     [rsp+0E8h+var_B0], eax
0x180017d4c  mov     eax, [rsp+0E8h+var_B0]
0x180017d50  lea     rax, [rsp+0E8h+var_78]
0x180017d55  mov     [rsp+0E8h+var_C0], rax
0x180017d5a  mov     [rsp+0E8h+var_C8], 4
0x180017d62  xor     r9d, r9d
0x180017d65  xor     r8d, r8d
0x180017d68  lea     rdx, [rsp+0E8h+var_A8]
0x180017d6d  mov     rcx, cs:RegHandle
0x180017d74  call    cs:__imp_EtwEventWriteTransfer
0x180017d7a  mov     rdi, [rsp+0E8h+var_98]
0x180017d7f  lea     r15, [rdi+80h]
0x180017d86  lfence
0x180017d89  movzx   esi, r13b
0x180017d8d  mov     rax, 0CBF29CE484222325h
0x180017d97  xor     rsi, rax
0x180017d9a  mov     rcx, 100000001B3h
0x180017da4  imul    rsi, rcx
0x180017da8  movzx   eax, byte ptr [rsp+0E8h+var_B4+1]
0x180017dad  xor     rsi, rax
0x180017db0  imul    rsi, rcx
0x180017db4  movzx   eax, byte ptr [rsp+0E8h+var_B4+2]
0x180017db9  xor     rsi, rax
0x180017dbc  imul    rsi, rcx
0x180017dc0  movzx   eax, byte ptr [rsp+0E8h+var_B4+3]
0x180017dc5  xor     rsi, rax
0x180017dc8  imul    rsi, rcx
0x180017dcc  mov     rdx, rsi
0x180017dcf  and     rdx, [r15+30h]
0x180017dd3  mov     r8, [r15+18h]
0x180017dd7  mov     rax, rdx
0x180017dda  add     rax, rax
0x180017ddd  mov     rcx, [r8+rax*8+8]
0x180017de2  lea     r12, [r15+8]
0x180017de6  mov     r14, [r12]
0x180017dea  cmp     rcx, r14
0x180017ded  jz      short loc_180017E0C
0x180017def  add     rdx, rdx
0x180017df2  mov     rax, [r8+rdx*8]
0x180017df6  cmp     r13d, [rcx+10h]
0x180017dfa  jz      loc_180017FAB
0x180017e00  cmp     rcx, rax
0x180017e03  jnz     loc_180017FFB
0x180017e09  mov     r14, rcx
0x180017e0c  mov     rax, 0AAAAAAAAAAAAAAAh
0x180017e16  cmp     [r15+10h], rax
0x180017e1a  jnz     short loc_180017E29
0x180017e1c  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180017e23  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180017e29  mov     [rsp+0E8h+var_A8], r12
0x180017e2e  mov     [rsp+0E8h+var_A0], rbx
0x180017e33  mov     ecx, 18h; Size
0x180017e38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017e3d  mov     rdi, rax
0x180017e40  mov     [rsp+0E8h+var_A0], rax
0x180017e45  mov     [rax+10h], r13d
0x180017e49  mov     rcx, [r15+10h]
0x180017e4d  add     rcx, 1
0x180017e51  xorps   xmm0, xmm0
0x180017e54  js      short loc_180017E5D
0x180017e56  cvtsi2ss xmm0, rcx
0x180017e5b  jmp     short loc_180017E72
0x180017e5d  mov     rax, rcx
0x180017e60  shr     rax, 1
0x180017e63  and     ecx, 1
0x180017e66  or      rax, rcx
0x180017e69  cvtsi2ss xmm0, rax
0x180017e6e  addss   xmm0, xmm0
0x180017e72  mov     rbx, [r15+38h]
0x180017e76  movss   xmm3, dword ptr [r15]
0x180017e7b  xorps   xmm2, xmm2
0x180017e7e  test    rbx, rbx
0x180017e81  js      short loc_180017E8A
0x180017e83  cvtsi2ss xmm2, rbx
0x180017e88  jmp     short loc_180017EA2
0x180017e8a  mov     rcx, rbx
0x180017e8d  shr     rcx, 1
0x180017e90  mov     rax, rbx
0x180017e93  and     eax, 1
0x180017e96  or      rcx, rax
0x180017e99  cvtsi2ss xmm2, rcx
0x180017e9e  addss   xmm2, xmm2
0x180017ea2  movaps  xmm1, xmm0
0x180017ea5  divss   xmm1, xmm2
0x180017ea9  comiss  xmm1, xmm3
  ... truncated ...
```
