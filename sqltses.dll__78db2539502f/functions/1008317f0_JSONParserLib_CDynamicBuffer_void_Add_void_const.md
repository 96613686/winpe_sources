# JSONParserLib::CDynamicBuffer<void *>::Add(void * const &)

- ea: `0x1008317f0`
- end: `0x1008319f1`
- name: `?Add@?$CDynamicBuffer@PEAX@JSONParserLib@@QEAAKAEBQEAX@Z`
- size: `513`
- prototype: `__int64 __fastcall(__int64, const void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x10082fe90`
- `0x1008303b0`
- `0x100830750`

## callees

- `0x10048b440`
- `0x1008317f0`

## import_xrefs

- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100831905`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100831905`
- `sqldk!??_V@YAXPEAX@Z` at `0x100831983`
- `sqldk!??_V@YAXPEAX@Z` at `0x100831994`
- `sqldk!??_V@YAXPEAX@Z` at `0x10083199e`
- `sqldk!??_V@YAXPEAX@Z` at `0x100831983`
- `sqldk!??_V@YAXPEAX@Z` at `0x100831994`
- `sqldk!??_V@YAXPEAX@Z` at `0x10083199e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10083196a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10083196a`

## string_xrefs

- `0x1008318f3`: `Sql\Ntdbms\storeng\jsonparser\include\JSON_DynamicBuffer.h`

## pseudocode

```c
__int64 __fastcall JSONParserLib::CDynamicBuffer<void *>::Add(__int64 a1, const void *a2)
{
  unsigned int v4; // esi
  unsigned int v5; // eax
  unsigned int v6; // r10d
  unsigned int v7; // r9d
  unsigned int v8; // r8d
  unsigned int v9; // eax
  unsigned int v10; // edx
  unsigned int v11; // ecx
  __int64 v12; // r14
  unsigned __int64 v13; // rax
  void *v14; // rax
  void *v15; // r15
  void *v16; // rbx
  void *v17; // rdi
  void *v18; // rcx

  if ( a2 )
  {
    v4 = 0;
    v5 = *(_DWORD *)(a1 + 28);
    v6 = v5 + 1;
    v7 = v5 + 1;
    if ( v5 + 1 < v5 || v5 == -1 )
    {
      return 3;
    }
    else if ( *(_BYTE *)(a1 + 48) )
    {
      v10 = *(_DWORD *)(a1 + 24);
      if ( v7 <= v10 )
        goto LABEL_19;
      while ( !v4 )
      {
        v11 = v10 >> 1;
        if ( v10 >> 1 <= *(_DWORD *)(a1 + 36) )
          v11 = *(_DWORD *)(a1 + 36);
        if ( v11 + v10 > v10 )
          v10 += v11;
        else
          v4 = 3;
        if ( v10 >= v7 )
        {
          if ( v4 )
            return v4;
          v7 = v10;
          goto LABEL_19;
        }
      }
    }
    else
    {
      v8 = v5 + *(_DWORD *)(a1 + 36) - (v5 + *(_DWORD *)(a1 + 36)) % *(_DWORD *)(a1 + 36);
      v9 = v5 + 1;
      if ( v8 >= v6 )
        v9 = v6 + *(_DWORD *)(a1 + 36) - 1 - (v6 + *(_DWORD *)(a1 + 36) - 1) % *(_DWORD *)(a1 + 36);
      v7 = v9;
      v4 = v8 < v6 ? 3 : 0;
      if ( v8 >= v6 )
      {
LABEL_19:
        v12 = *(unsigned int *)(a1 + 32);
        if ( v7 >= (unsigned int)v12 )
          v12 = v7;
        v4 = 0;
        if ( (unsigned int)v12 <= *(_DWORD *)(a1 + 24) )
          goto LABEL_32;
        _mm_lfence();
        v13 = 8LL * (unsigned int)v12;
        if ( !is_mul_ok((unsigned int)v12, 8u) )
          v13 = -1;
        v14 = operator new[](
                v13,
                *(struct IMemObj **)(a1 + 40),
                1,
                "Sql\\Ntdbms\\storeng\\jsonparser\\include\\JSON_DynamicBuffer.h",
                225,
                6u);
        v15 = v14;
        if ( v14 )
        {
          v16 = *(void **)(a1 + 16);
          *(_QWORD *)(a1 + 16) = 0;
          v17 = v16;
          if ( v16 )
          {
            memcpy_s(v14, 8 * v12, v16, 8LL * *(unsigned int *)(a1 + 28));
            v17 = 0;
            operator delete(v16, 8u);
          }
          v18 = *(void **)(a1 + 16);
          if ( v18 != v15 )
            operator delete[](v18);
          *(_QWORD *)(a1 + 16) = v15;
          *(_DWORD *)(a1 + 24) = v12;
          operator delete[](v17);
        }
        else
        {
          v4 = 1;
        }
        operator delete[](0);
        if ( !v4 )
        {
LABEL_32:
          memcpy_s((void *const)(*(_QWORD *)(a1 + 16) + 8LL * *(unsigned int *)(a1 + 28)), 8u, a2, 8u);
          ++*(_DWORD *)(a1 + 28);
          return v4;
        }
      }
    }
    return v4;
  }
  return 2;
}

```

## disassembly

```asm
0x1008317f0  push    rbp
0x1008317f2  push    rsi
0x1008317f3  push    rdi
0x1008317f4  push    r12
0x1008317f6  push    r13
0x1008317f8  push    r14
0x1008317fa  push    r15
0x1008317fc  sub     rsp, 40h
0x100831800  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x100831809  mov     [rsp+78h+arg_0], rbx
0x100831811  mov     r12, rdx
0x100831814  mov     rbp, rcx
0x100831817  test    rdx, rdx
0x10083181a  jz      loc_1008319D4
0x100831820  xor     esi, esi
0x100831822  mov     eax, [rcx+1Ch]
0x100831825  lea     r10d, [rax+1]
0x100831829  mov     r9d, r10d
0x10083182c  cmp     r10d, eax
0x10083182f  jb      loc_1008319CB
0x100831835  cmp     r10d, 1
0x100831839  jb      loc_1008319CB
0x10083183f  cmp     [rcx+30h], sil
0x100831843  jnz     short loc_100831879
0x100831845  mov     ecx, [rcx+24h]
0x100831848  lea     r8d, [rcx-1]
0x10083184c  add     r8d, r10d
0x10083184f  xor     edx, edx
0x100831851  mov     eax, r8d
0x100831854  div     ecx
0x100831856  sub     r8d, edx
0x100831859  mov     eax, r10d
0x10083185c  cmp     r8d, r10d
0x10083185f  cmovnb  eax, r8d
0x100831863  mov     r9d, eax
0x100831866  cmp     r8d, r10d
0x100831869  sbb     esi, esi
0x10083186b  and     esi, 3
0x10083186e  cmp     r8d, r10d
0x100831871  jb      loc_1008319D0
0x100831877  jmp     short loc_1008318B6
0x100831879  mov     edx, [rcx+18h]
0x10083187c  cmp     r9d, edx
0x10083187f  jbe     short loc_1008318B6
0x100831881  mov     r10d, 3
0x100831887  test    esi, esi
0x100831889  jnz     loc_1008319D0
0x10083188f  mov     ecx, edx
0x100831891  shr     ecx, 1
0x100831893  cmp     ecx, [rbp+24h]
0x100831896  cmovbe  ecx, [rbp+24h]
0x10083189a  lea     eax, [rcx+rdx]
0x10083189d  cmp     eax, edx
0x10083189f  cmovbe  esi, r10d
0x1008318a3  cmova   edx, eax
0x1008318a6  cmp     edx, r9d
0x1008318a9  jb      short loc_100831887
0x1008318ab  test    esi, esi
0x1008318ad  jnz     loc_1008319D0
0x1008318b3  mov     r9d, edx
0x1008318b6  mov     r14d, [rbp+20h]
0x1008318ba  cmp     r9d, r14d
0x1008318bd  cmovnb  r14d, r9d
0x1008318c1  xor     esi, esi
0x1008318c3  cmp     r14d, [rbp+18h]
0x1008318c7  jbe     loc_1008319A8
0x1008318cd  lfence
0x1008318d0  mov     r13d, r14d
0x1008318d3  mov     eax, 8
0x1008318d8  mul     r13
0x1008318db  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1008318e2  cmovo   rax, rcx
0x1008318e6  mov     [rsp+78h+var_50], 6
0x1008318eb  mov     [rsp+78h+var_58], 0E1h
0x1008318f3  lea     r9, aSqlNtdbmsStore_3; "Sql\\Ntdbms\\storeng\\jsonparser\\inclu"...
0x1008318fa  lea     r8d, [rsi+1]
0x1008318fe  mov     rdx, [rbp+28h]
0x100831902  mov     rcx, rax
0x100831905  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10083190b  mov     r15, rax
0x10083190e  mov     rbx, rax
0x100831911  mov     [rsp+78h+arg_10], rax
0x100831919  test    rax, rax
0x10083191c  jnz     short loc_100831923
0x10083191e  lea     esi, [rax+1]
0x100831921  jmp     short loc_10083199B
0x100831923  mov     rbx, [rbp+10h]
0x100831927  mov     qword ptr [rbp+10h], 0
0x10083192f  mov     rdi, rbx
0x100831932  mov     [rsp+78h+arg_8], rbx
0x10083193a  test    rbx, rbx
0x10083193d  jz      short loc_100831970
0x10083193f  mov     r9d, [rbp+1Ch]
0x100831943  shl     r9, 3; SourceSize
0x100831947  lea     rdx, ds:0[r14*8]; DestinationSize
0x10083194f  mov     r8, rbx; Source
0x100831952  mov     rcx, r15; Destination
0x100831955  call    memcpy_s
0x10083195a  xor     edi, edi
0x10083195c  mov     [rsp+78h+arg_8], rdi
0x100831964  lea     edx, [rdi+8]
0x100831967  mov     rcx, rbx
0x10083196a  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100831970  xor     ebx, ebx
0x100831972  mov     [rsp+78h+arg_10], rbx
0x10083197a  mov     rcx, [rbp+10h]
0x10083197e  cmp     rcx, r15
0x100831981  jz      short loc_100831989
0x100831983  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100831989  mov     [rbp+10h], r15
0x10083198d  mov     [rbp+18h], r14d
0x100831991  mov     rcx, rdi
0x100831994  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10083199a  nop
0x10083199b  mov     rcx, rbx
0x10083199e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1008319a4  test    esi, esi
0x1008319a6  jnz     short loc_1008319D0
0x1008319a8  mov     ecx, [rbp+1Ch]
0x1008319ab  mov     rax, [rbp+10h]
0x1008319af  lea     rcx, [rax+rcx*8]; Destination
0x1008319b3  mov     r9d, 8; SourceSize
0x1008319b9  mov     r8, r12; Source
0x1008319bc  mov     edx, r9d; DestinationSize
0x1008319bf  call    memcpy_s
0x1008319c4  inc     dword ptr [rbp+1Ch]
0x1008319c7  mov     eax, esi
0x1008319c9  jmp     short loc_1008319D9
0x1008319cb  mov     esi, 3
0x1008319d0  mov     eax, esi
0x1008319d2  jmp     short loc_1008319D9
0x1008319d4  mov     eax, 2
0x1008319d9  mov     rbx, [rsp+78h+arg_0]
0x1008319e1  add     rsp, 40h
0x1008319e5  pop     r15
0x1008319e7  pop     r14
0x1008319e9  pop     r13
0x1008319eb  pop     r12
0x1008319ed  pop     rdi
0x1008319ee  pop     rsi
0x1008319ef  pop     rbp
0x1008319f0  retn
```
