# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_nohint<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(bool,std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)

- ea: `0x180013ecc`
- end: `0x180014040`
- name: `??$_Insert_nohint@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@@Z`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013ae0`

## callees

- `0x1800133c4`
- `0x180013ecc`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180013f04`
- `msvcrt!_wcsicmp` at `0x180013fd1`
- `msvcrt!_wcsicmp` at `0x180013f04`
- `msvcrt!_wcsicmp` at `0x180013fd1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001401b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001401b`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_nohint<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(
        __int64 **a1,
        __int64 a2,
        __int64 a3,
        const wchar_t **a4,
        void *a5)
{
  __int64 *v8; // rbx
  __int64 *v9; // rsi
  int v10; // eax
  unsigned int v11; // r14d
  __int64 *v12; // rsi
  __int64 v13; // rcx
  __int64 result; // rax
  __int64 j; // rax
  __int64 *i; // rax
  int v17; // [rsp+20h] [rbp-58h]
  __int64 v18; // [rsp+80h] [rbp+8h] BYREF

  try
  {
    v8 = *a1;
    v9 = (__int64 *)(*a1)[1];
    if ( *((_BYTE *)v9 + 25) )
    {
      LOBYTE(v11) = 1;
      v12 = *a1;
    }
    else
    {
      do
      {
        v8 = v9;
        v10 = _wcsicmp(*a4, (const wchar_t *)v9[4]);
        v11 = (unsigned int)v10 >> 31;
        if ( v10 >= 0 )
          v9 = (__int64 *)v9[2];
        else
          v9 = (__int64 *)*v9;
      }
      while ( !*((_BYTE *)v9 + 25) );
      v12 = v8;
      if ( v10 >= 0 )
        goto LABEL_25;
    }
    if ( v12 != (__int64 *)**a1 )
    {
      if ( *((_BYTE *)v12 + 25) )
      {
        v8 = (__int64 *)v12[2];
      }
      else if ( *(_BYTE *)(*v12 + 25) )
      {
        for ( i = (__int64 *)v12[1]; !*((_BYTE *)i + 25) && v8 == (__int64 *)*i; i = (__int64 *)i[1] )
          v8 = i;
        if ( !*((_BYTE *)v8 + 25) )
          v8 = i;
      }
      else
      {
        v8 = (__int64 *)*v12;
        for ( j = *(_QWORD *)(*v12 + 16); !*(_BYTE *)(j + 25); j = v8[2] )
          v8 = (__int64 *)v8[2];
      }
LABEL_25:
      if ( _wcsicmp((const wchar_t *)v8[4], *a4) >= 0 )
      {
        operator delete(a5);
        *(_QWORD *)a2 = v8;
        *(_BYTE *)(a2 + 8) = 0;
      }
      else
      {
        *(_QWORD *)a2 = *std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(
                           a1,
                           &v18,
                           v11,
                           v12,
                           v17,
                           (__int64)a5);
        *(_BYTE *)(a2 + 8) = 1;
      }
      return a2;
    }
    *(_QWORD *)a2 = *std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(
                       a1,
                       &v18,
                       1,
                       v12,
                       v17,
                       (__int64)a5);
    *(_BYTE *)(a2 + 8) = 1;
    result = a2;
  }
  catch ( ... )
  {
    std::_Tree_buy<unsigned short const *>::_Freenode0(v13, a5);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180013ecc  push    rbx
0x180013ece  push    rsi
0x180013ecf  push    rdi
0x180013ed0  push    r12
0x180013ed2  push    r14
0x180013ed4  push    r15
0x180013ed6  sub     rsp, 48h
0x180013eda  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x180013ee3  mov     r12, r9
0x180013ee6  mov     rdi, rdx
0x180013ee9  mov     r15, rcx
0x180013eec  mov     rbx, [rcx]
0x180013eef  mov     rsi, [rbx+8]
0x180013ef3  cmp     byte ptr [rsi+19h], 0
0x180013ef7  jnz     short loc_180013F38
0x180013ef9  mov     rbx, rsi
0x180013efc  mov     rdx, [rsi+20h]; String2
0x180013f00  mov     rcx, [r12]; String1
0x180013f04  call    cs:__imp__wcsicmp
0x180013f0b  nop     dword ptr [rax+rax+00h]
0x180013f10  mov     r14d, eax
0x180013f13  shr     r14d, 1Fh
0x180013f17  test    r14b, r14b
0x180013f1a  jz      short loc_180013F21
0x180013f1c  mov     rsi, [rsi]
0x180013f1f  jmp     short loc_180013F25
0x180013f21  mov     rsi, [rsi+10h]
0x180013f25  cmp     byte ptr [rsi+19h], 0
0x180013f29  jz      short loc_180013EF9
0x180013f2b  mov     rsi, rbx
0x180013f2e  test    r14b, r14b
0x180013f31  jnz     short loc_180013F3E
0x180013f33  jmp     loc_180013FC9
0x180013f38  mov     r14b, 1
0x180013f3b  mov     rsi, rbx
0x180013f3e  mov     rax, [r15]
0x180013f41  cmp     rsi, [rax]
0x180013f44  jnz     short loc_180013F7B
0x180013f46  mov     rax, [rsp+78h+arg_20]
0x180013f4e  mov     [rsp+78h+var_50], rax
0x180013f53  mov     r9, rsi
0x180013f56  mov     r8b, 1
0x180013f59  lea     rdx, [rsp+78h+arg_0]
0x180013f61  mov     rcx, r15
0x180013f64  call    ??$_Insert_at@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@1@1@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(bool,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *,std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x180013f69  mov     rax, [rax]
0x180013f6c  mov     [rdi], rax
0x180013f6f  mov     byte ptr [rdi+8], 1
0x180013f73  mov     rax, rdi
0x180013f76  jmp     loc_180014031
0x180013f7b  cmp     byte ptr [rsi+19h], 0
0x180013f7f  jz      short loc_180013F87
0x180013f81  mov     rbx, [rsi+10h]
0x180013f85  jmp     short loc_180013FC9
0x180013f87  mov     rax, [rsi]
0x180013f8a  cmp     byte ptr [rax+19h], 0
0x180013f8e  jnz     short loc_180013FA9
0x180013f90  mov     rbx, rax
0x180013f93  mov     rax, [rax+10h]
0x180013f97  jmp     short loc_180013FA1
0x180013f99  mov     rbx, [rbx+10h]
0x180013f9d  mov     rax, [rbx+10h]
0x180013fa1  cmp     byte ptr [rax+19h], 0
0x180013fa5  jz      short loc_180013F99
0x180013fa7  jmp     short loc_180013FC9
0x180013fa9  mov     rax, [rsi+8]
0x180013fad  jmp     short loc_180013FBB
0x180013faf  cmp     rbx, [rax]
0x180013fb2  jnz     short loc_180013FC1
0x180013fb4  mov     rbx, rax
0x180013fb7  mov     rax, [rax+8]
0x180013fbb  cmp     byte ptr [rax+19h], 0
0x180013fbf  jz      short loc_180013FAF
0x180013fc1  cmp     byte ptr [rbx+19h], 0
0x180013fc5  cmovz   rbx, rax
0x180013fc9  mov     rdx, [r12]; String2
0x180013fcd  mov     rcx, [rbx+20h]; String1
0x180013fd1  call    cs:__imp__wcsicmp
0x180013fd8  nop     dword ptr [rax+rax+00h]
0x180013fdd  test    eax, eax
0x180013fdf  jns     short loc_180014013
0x180013fe1  mov     rax, [rsp+78h+arg_20]
0x180013fe9  mov     [rsp+78h+var_50], rax
0x180013fee  mov     r9, rsi
0x180013ff1  mov     r8b, r14b
0x180013ff4  lea     rdx, [rsp+78h+arg_0]
0x180013ffc  mov     rcx, r15
0x180013fff  call    ??$_Insert_at@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@1@1@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(bool,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *,std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x180014004  mov     rax, [rax]
0x180014007  mov     [rdi], rax
0x18001400a  mov     byte ptr [rdi+8], 1
0x18001400e  mov     rax, rdi
0x180014011  jmp     short loc_180014031
0x180014013  mov     rcx, [rsp+78h+arg_20]
0x18001401b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014022  nop     dword ptr [rax+rax+00h]
0x180014027  mov     [rdi], rbx
0x18001402a  mov     byte ptr [rdi+8], 0
0x18001402e  mov     rax, rdi
0x180014031  add     rsp, 48h
0x180014035  pop     r15
0x180014037  pop     r14
0x180014039  pop     r12
0x18001403b  pop     rdi
0x18001403c  pop     rsi
0x18001403d  pop     rbx
0x18001403e  retn
```
