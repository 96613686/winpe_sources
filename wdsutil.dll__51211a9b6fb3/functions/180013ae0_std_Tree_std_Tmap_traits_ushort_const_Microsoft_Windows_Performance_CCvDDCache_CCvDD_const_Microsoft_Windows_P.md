# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_hint<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)

- ea: `0x180013ae0`
- end: `0x180013d75`
- name: `??$_Insert_hint@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@1@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@@Z`
- size: `661`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015a30`

## callees

- `0x1800133c4`
- `0x180013ae0`
- `0x180013ecc`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180013b3e`
- `msvcrt!_wcsicmp` at `0x180013b88`
- `msvcrt!_wcsicmp` at `0x180013bcd`
- `msvcrt!_wcsicmp` at `0x180013c30`
- `msvcrt!_wcsicmp` at `0x180013c8a`
- `msvcrt!_wcsicmp` at `0x180013cf3`
- `msvcrt!_wcsicmp` at `0x180013b3e`
- `msvcrt!_wcsicmp` at `0x180013b88`
- `msvcrt!_wcsicmp` at `0x180013bcd`
- `msvcrt!_wcsicmp` at `0x180013c30`
- `msvcrt!_wcsicmp` at `0x180013c8a`
- `msvcrt!_wcsicmp` at `0x180013cf3`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_hint<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(
        __int64 ***a1,
        _QWORD *a2,
        __int64 *a3,
        const wchar_t **a4,
        __int64 a5)
{
  __int64 **v9; // rcx
  __int64 v10; // rcx
  int v11; // r8d
  _QWORD *result; // rax
  __int64 *v13; // rdi
  __int64 *i; // rax
  __int64 *v15; // rdi
  __int64 *j; // rax
  __int64 *v17; // rcx
  int v18; // [rsp+20h] [rbp-68h]
  char v19; // [rsp+38h] [rbp-50h] BYREF

  v9 = *a1;
  if ( a1[1] )
  {
    if ( a3 == *v9 )
    {
      if ( _wcsicmp(*a4, (const wchar_t *)a3[4]) < 0 )
      {
        std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(
          a1,
          a2,
          1,
          a3,
          v18,
          a5);
        return a2;
      }
      goto LABEL_43;
    }
    if ( a3 == (__int64 *)v9 )
    {
      if ( _wcsicmp((const wchar_t *)v9[2][4], *a4) < 0 )
      {
        std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(
          a1,
          a2,
          0,
          (*a1)[2],
          v18,
          a5);
        return a2;
      }
      goto LABEL_43;
    }
    if ( _wcsicmp(*a4, (const wchar_t *)a3[4]) < 0 )
    {
      if ( *((_BYTE *)a3 + 25) )
      {
        v13 = (__int64 *)a3[2];
      }
      else
      {
        v13 = (__int64 *)*a3;
        if ( *(_BYTE *)(*a3 + 25) )
        {
          v13 = a3;
          for ( i = (__int64 *)a3[1]; !*((_BYTE *)i + 25) && v13 == (__int64 *)*i; i = (__int64 *)i[1] )
            v13 = i;
          if ( !*((_BYTE *)v13 + 25) )
            v13 = i;
        }
        else
        {
          while ( !*(_BYTE *)(v13[2] + 25) )
            v13 = (__int64 *)v13[2];
        }
      }
      if ( _wcsicmp((const wchar_t *)v13[4], *a4) < 0 )
      {
        if ( *(_BYTE *)(v13[2] + 25) )
          std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(
            a1,
            a2,
            0,
            v13,
            v18,
            a5);
        else
          std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(
            a1,
            a2,
            1,
            a3,
            v18,
            a5);
        return a2;
      }
    }
    if ( _wcsicmp((const wchar_t *)a3[4], *a4) >= 0 )
      goto LABEL_43;
    v15 = a3;
    if ( !*((_BYTE *)a3 + 25) )
    {
      j = (__int64 *)a3[2];
      if ( *((_BYTE *)j + 25) )
      {
        for ( j = (__int64 *)a3[1]; !*((_BYTE *)j + 25) && v15 == (__int64 *)j[2]; j = (__int64 *)j[1] )
          v15 = j;
      }
      else
      {
        v17 = (__int64 *)*j;
        if ( !*(_BYTE *)(*j + 25) )
        {
          do
          {
            v15 = v17;
            v17 = (__int64 *)*v17;
          }
          while ( !*((_BYTE *)v17 + 25) );
          goto LABEL_37;
        }
      }
      v15 = j;
    }
LABEL_37:
    if ( v15 == (__int64 *)*a1 || _wcsicmp(*a4, (const wchar_t *)v15[4]) < 0 )
    {
      if ( *(_BYTE *)(a3[2] + 25) )
        std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(
          a1,
          a2,
          0,
          a3,
          v18,
          a5);
      else
        std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(
          a1,
          a2,
          1,
          v15,
          v18,
          a5);
      return a2;
    }
LABEL_43:
    *a2 = *(_QWORD *)std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_nohint<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(
                       (_DWORD)a1,
                       (unsigned int)&v19,
                       v11,
                       (_DWORD)a4,
                       a5);
    return a2;
  }
  try
  {
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(
      a1,
      a2,
      1,
      v9,
      v18,
      a5);
    result = a2;
  }
  catch ( ... )
  {
    std::_Tree_buy<unsigned short const *>::_Freenode0(v10, a5);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180013ae0  push    rbx
0x180013ae2  push    rsi
0x180013ae3  push    rdi
0x180013ae4  push    r12
0x180013ae6  push    r14
0x180013ae8  push    r15
0x180013aea  sub     rsp, 58h
0x180013aee  mov     [rsp+88h+var_58], 0FFFFFFFFFFFFFFFEh
0x180013af7  mov     r15, r9
0x180013afa  mov     rbx, r8
0x180013afd  mov     rsi, rdx
0x180013b00  mov     r14, rcx
0x180013b03  mov     rcx, [rcx]
0x180013b06  xor     r12d, r12d
0x180013b09  cmp     [r14+8], r12
0x180013b0d  jnz     short loc_180013B32
0x180013b0f  mov     rax, [rsp+88h+arg_20]
0x180013b17  mov     [rsp+88h+var_60], rax
0x180013b1c  mov     r9, rcx
0x180013b1f  mov     r8b, 1
0x180013b22  mov     rcx, r14
0x180013b25  call    ??$_Insert_at@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@1@1@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(bool,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *,std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x180013b2a  mov     rax, rsi
0x180013b2d  jmp     loc_180013D66
0x180013b32  cmp     rbx, [rcx]
0x180013b35  jnz     short loc_180013B78
0x180013b37  mov     rdx, [r8+20h]; String2
0x180013b3b  mov     rcx, [r9]; String1
0x180013b3e  call    cs:__imp__wcsicmp
0x180013b45  nop     dword ptr [rax+rax+00h]
0x180013b4a  test    eax, eax
0x180013b4c  jns     loc_180013D40
0x180013b52  mov     rax, [rsp+88h+arg_20]
0x180013b5a  mov     [rsp+88h+var_60], rax
0x180013b5f  mov     r9, rbx
0x180013b62  mov     r8b, 1
0x180013b65  mov     rdx, rsi
0x180013b68  mov     rcx, r14
0x180013b6b  call    ??$_Insert_at@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@1@1@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(bool,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *,std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x180013b70  mov     rax, rsi
0x180013b73  jmp     loc_180013D66
0x180013b78  cmp     rbx, rcx
0x180013b7b  jnz     short loc_180013BC6
0x180013b7d  mov     rcx, [rcx+10h]
0x180013b81  mov     rdx, [r9]; String2
0x180013b84  mov     rcx, [rcx+20h]; String1
0x180013b88  call    cs:__imp__wcsicmp
0x180013b8f  nop     dword ptr [rax+rax+00h]
0x180013b94  test    eax, eax
0x180013b96  jns     loc_180013D40
0x180013b9c  mov     r9, [r14]
0x180013b9f  mov     rax, [rsp+88h+arg_20]
0x180013ba7  mov     [rsp+88h+var_60], rax
0x180013bac  mov     r9, [r9+10h]
0x180013bb0  xor     r8d, r8d
0x180013bb3  mov     rdx, rsi
0x180013bb6  mov     rcx, r14
0x180013bb9  call    ??$_Insert_at@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@1@1@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(bool,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *,std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x180013bbe  mov     rax, rsi
0x180013bc1  jmp     loc_180013D66
0x180013bc6  mov     rdx, [r8+20h]; String2
0x180013bca  mov     rcx, [r9]; String1
0x180013bcd  call    cs:__imp__wcsicmp
0x180013bd4  nop     dword ptr [rax+rax+00h]
0x180013bd9  test    eax, eax
0x180013bdb  jns     loc_180013C83
0x180013be1  cmp     [rbx+19h], r12b
0x180013be5  jz      short loc_180013BED
0x180013be7  mov     rdi, [rbx+10h]
0x180013beb  jmp     short loc_180013C29
0x180013bed  mov     rdi, [rbx]
0x180013bf0  cmp     [rdi+19h], r12b
0x180013bf4  jz      short loc_180013C03
0x180013bf6  mov     rdi, rbx
0x180013bf9  mov     rax, [rbx+8]
0x180013bfd  jmp     short loc_180013C1B
0x180013bff  mov     rdi, [rdi+10h]
0x180013c03  mov     rax, [rdi+10h]
0x180013c07  cmp     [rax+19h], r12b
0x180013c0b  jz      short loc_180013BFF
0x180013c0d  jmp     short loc_180013C29
0x180013c0f  cmp     rdi, [rax]
0x180013c12  jnz     short loc_180013C21
0x180013c14  mov     rdi, rax
0x180013c17  mov     rax, [rax+8]
0x180013c1b  cmp     [rax+19h], r12b
0x180013c1f  jz      short loc_180013C0F
0x180013c21  cmp     [rdi+19h], r12b
0x180013c25  cmovz   rdi, rax
0x180013c29  mov     rdx, [r15]; String2
0x180013c2c  mov     rcx, [rdi+20h]; String1
0x180013c30  call    cs:__imp__wcsicmp
0x180013c37  nop     dword ptr [rax+rax+00h]
0x180013c3c  test    eax, eax
0x180013c3e  jns     short loc_180013C83
0x180013c40  mov     rax, [rdi+10h]
0x180013c44  mov     rdx, rsi
0x180013c47  mov     rcx, r14
0x180013c4a  cmp     [rax+19h], r12b
0x180013c4e  mov     rax, [rsp+88h+arg_20]
0x180013c56  mov     [rsp+88h+var_60], rax
0x180013c5b  jz      short loc_180013C70
0x180013c5d  mov     r9, rdi
0x180013c60  xor     r8d, r8d
0x180013c63  call    ??$_Insert_at@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@1@1@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(bool,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *,std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x180013c68  mov     rax, rsi
0x180013c6b  jmp     loc_180013D66
0x180013c70  mov     r9, rbx
0x180013c73  mov     r8b, 1
0x180013c76  call    ??$_Insert_at@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@1@1@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(bool,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *,std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x180013c7b  mov     rax, rsi
0x180013c7e  jmp     loc_180013D66
0x180013c83  mov     rdx, [r15]; String2
0x180013c86  mov     rcx, [rbx+20h]; String1
0x180013c8a  call    cs:__imp__wcsicmp
0x180013c91  nop     dword ptr [rax+rax+00h]
0x180013c96  test    eax, eax
0x180013c98  jns     loc_180013D40
0x180013c9e  mov     rdi, rbx
0x180013ca1  cmp     [rbx+19h], r12b
0x180013ca5  jnz     short loc_180013CE7
0x180013ca7  mov     rax, [rbx+10h]
0x180013cab  cmp     [rax+19h], r12b
0x180013caf  jnz     short loc_180013CCB
0x180013cb1  mov     rcx, [rax]
0x180013cb4  cmp     [rcx+19h], r12b
0x180013cb8  jnz     short loc_180013CE4
0x180013cba  mov     rdi, rcx
0x180013cbd  mov     rax, [rcx]
0x180013cc0  mov     rcx, rax
0x180013cc3  cmp     [rax+19h], r12b
0x180013cc7  jz      short loc_180013CBA
0x180013cc9  jmp     short loc_180013CE7
0x180013ccb  mov     rax, [rbx+8]
0x180013ccf  jmp     short loc_180013CDE
0x180013cd1  cmp     rdi, [rax+10h]
0x180013cd5  jnz     short loc_180013CE4
0x180013cd7  mov     rdi, rax
0x180013cda  mov     rax, [rax+8]
0x180013cde  cmp     [rax+19h], r12b
0x180013ce2  jz      short loc_180013CD1
0x180013ce4  mov     rdi, rax
0x180013ce7  cmp     rdi, [r14]
0x180013cea  jz      short loc_180013D03
0x180013cec  mov     rdx, [rdi+20h]; String2
0x180013cf0  mov     rcx, [r15]; String1
0x180013cf3  call    cs:__imp__wcsicmp
0x180013cfa  nop     dword ptr [rax+rax+00h]
0x180013cff  test    eax, eax
0x180013d01  jns     short loc_180013D40
0x180013d03  mov     rax, [rbx+10h]
0x180013d07  mov     rdx, rsi
0x180013d0a  mov     rcx, r14
0x180013d0d  cmp     [rax+19h], r12b
0x180013d11  mov     rax, [rsp+88h+arg_20]
0x180013d19  mov     [rsp+88h+var_60], rax
0x180013d1e  jz      short loc_180013D30
0x180013d20  mov     r9, rbx
0x180013d23  xor     r8d, r8d
0x180013d26  call    ??$_Insert_at@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@1@1@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(bool,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *,std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x180013d2b  mov     rax, rsi
0x180013d2e  jmp     short loc_180013D66
0x180013d30  mov     r9, rdi
0x180013d33  mov     r8b, 1
0x180013d36  call    ??$_Insert_at@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@1@1@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_at<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(bool,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *,std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x180013d3b  mov     rax, rsi
0x180013d3e  jmp     short loc_180013D66
0x180013d40  mov     rax, [rsp+88h+arg_20]
0x180013d48  mov     [rsp+88h+var_68], rax
0x180013d4d  mov     r9, r15
0x180013d50  lea     rdx, [rsp+88h+var_50]
0x180013d55  mov     rcx, r14
0x180013d58  call    ??$_Insert_nohint@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_nohint<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(bool,std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x180013d5d  mov     rcx, [rax]
0x180013d60  mov     [rsi], rcx
0x180013d63  mov     rax, rsi
0x180013d66  add     rsp, 58h
0x180013d6a  pop     r15
0x180013d6c  pop     r14
0x180013d6e  pop     r12
0x180013d70  pop     rdi
0x180013d71  pop     rsi
0x180013d72  pop     rbx
0x180013d73  retn
```
