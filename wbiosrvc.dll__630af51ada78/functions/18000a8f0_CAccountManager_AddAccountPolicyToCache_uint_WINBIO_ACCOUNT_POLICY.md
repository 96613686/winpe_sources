# CAccountManager::AddAccountPolicyToCache(uint,_WINBIO_ACCOUNT_POLICY *)

- ea: `0x18000a8f0`
- end: `0x18000ab66`
- name: `?AddAccountPolicyToCache@CAccountManager@@AEAAJIPEAU_WINBIO_ACCOUNT_POLICY@@@Z`
- size: `630`
- prototype: `int(CAccountManager *__hidden this, unsigned int, struct _WINBIO_ACCOUNT_POLICY *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a794`
- `0x180015744`

## callees

- `0x180008d60`
- `0x18000986c`
- `0x18000a8f0`
- `0x18000b760`
- `0x1800306c4`
- `0x18005742c`
- `0x18006963c`
- `0x180078654`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000ab05`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000ab05`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000ab43`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000ab43`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CAccountManager::AddAccountPolicyToCache(
        CAccountManager *this,
        unsigned int a2,
        struct _WINBIO_ACCOUNT_POLICY *a3)
{
  struct _WINBIO_ACCOUNT_POLICY *v3; // r15
  __int64 result; // rax
  __int64 *v7; // rcx
  __int64 *v8; // rax
  __int64 *v9; // r14
  int v10; // r13d
  __int64 v11; // rax
  __int64 ***v12; // r12
  volatile signed __int32 *v13; // r14
  __int64 v14; // rax
  __int64 *v15; // rdi
  __int64 *i; // rbx
  WINBIO_IDENTITY_TYPE Type; // eax
  __int128 v18; // xmm1
  __int128 v19; // xmm2
  __int128 v20; // xmm3
  __int128 v21; // xmm4
  __int64 **v22; // rdx
  _QWORD *v23; // [rsp+20h] [rbp-68h]
  __int64 ***v24; // [rsp+28h] [rbp-60h]
  volatile signed __int32 *v25; // [rsp+30h] [rbp-58h]
  _BYTE v26[8]; // [rsp+38h] [rbp-50h] BYREF
  std::_Ref_count_base *v27; // [rsp+40h] [rbp-48h]
  unsigned int v28; // [rsp+48h] [rbp-40h] BYREF
  __int64 ***v29; // [rsp+50h] [rbp-38h]
  std::_Ref_count_base *v30; // [rsp+58h] [rbp-30h]

  v3 = a3;
  result = winbio::ValidateFactor((winbio *)a2, a2);
  if ( (int)result >= 0 )
  {
    if ( v3 )
    {
      if ( v3->Identity.Type == 1 || v3->Identity.Type == 3 && IsValidSid(v3->Identity.Value.AccountSid.Data) )
      {
        v7 = (__int64 *)*((_QWORD *)this + 2);
        v8 = (__int64 *)v7[1];
        HIDWORD(v29) = 0;
        v9 = v7;
        v10 = 0;
        while ( !*((_BYTE *)v8 + 25) )
        {
          if ( *((_DWORD *)v8 + 8) < a2 )
          {
            v8 = (__int64 *)v8[2];
          }
          else
          {
            v9 = v8;
            v8 = (__int64 *)*v8;
          }
        }
        try
        {
          if ( *((_BYTE *)v9 + 25) || a2 < *((_DWORD *)v9 + 8) || v9 == v7 )
          {
            v23 = operator new(0x10u);
            *v23 = 0;
            v23[1] = 0;
            std::list<_WINBIO_ACCOUNT_POLICY>::_Alloc_sentinel_and_proxy(v23);
            v11 = std::shared_ptr<std::list<_WINBIO_ACCOUNT_POLICY>>::shared_ptr<std::list<_WINBIO_ACCOUNT_POLICY>>(
                    v26,
                    v23);
            v12 = *(__int64 ****)v11;
            v13 = *(volatile signed __int32 **)(v11 + 8);
            *(_QWORD *)v11 = 0;
            *(_QWORD *)(v11 + 8) = 0;
            v24 = v12;
            v25 = v13;
            if ( v27 )
              std::_Ref_count_base::_Decref(v27);
            v28 = a2;
            if ( v13 )
              _InterlockedIncrement(v13 + 2);
            v29 = v12;
            v30 = (std::_Ref_count_base *)v13;
            std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<std::list<_WINBIO_ACCOUNT_POLICY>>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<std::list<_WINBIO_ACCOUNT_POLICY>>>>,0>>::_Emplace<std::pair<unsigned long,std::shared_ptr<std::list<_WINBIO_ACCOUNT_POLICY>>>>(
              (char *)this + 16,
              v26,
              &v28);
            if ( v30 )
              std::_Ref_count_base::_Decref(v30);
          }
          else
          {
            v14 = v9[6];
            if ( v14 )
              _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
            v12 = (__int64 ***)v9[5];
            v24 = v12;
            v13 = (volatile signed __int32 *)v9[6];
            v25 = v13;
          }
        }
        catch ( std::bad_alloc )
        {
          v3 = a3;
          v10 = -2147024882;
          v13 = v25;
          v12 = v24;
        }
        if ( v10 >= 0 )
        {
          v15 = (__int64 *)*v12;
          for ( i = **v12; i != v15; i = (__int64 *)*i )
          {
            Type = v3->Identity.Type;
            if ( *((_DWORD *)i + 4) == v3->Identity.Type
              && (Type == 1 || Type == 3 && EqualSid(v3->Identity.Value.AccountSid.Data, i + 3)) )
            {
              v18 = *(_OWORD *)&v3->Identity.Value.AccountSid.Data[8];
              v19 = *(_OWORD *)&v3->Identity.Value.AccountSid.Data[24];
              v20 = *(_OWORD *)&v3->Identity.Value.AccountSid.Data[40];
              v21 = *(_OWORD *)&v3->Identity.Value.AccountSid.Data[56];
              *((_OWORD *)i + 1) = *(_OWORD *)&v3->Identity.Type;
              *((_OWORD *)i + 2) = v18;
              *((_OWORD *)i + 3) = v19;
              *((_OWORD *)i + 4) = v20;
              *((_OWORD *)i + 5) = v21;
              goto LABEL_30;
            }
          }
          v22 = *v12;
          if ( v3->Identity.Type == 1 )
            std::list<_WINBIO_ACCOUNT_POLICY>::_Emplace<_WINBIO_ACCOUNT_POLICY const &>(v12, *v22, v3);
          else
            std::list<_WINBIO_ACCOUNT_POLICY>::_Emplace<_WINBIO_ACCOUNT_POLICY const &>(v12, v22, v3);
        }
LABEL_30:
        if ( v13 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v13);
        return (unsigned int)v10;
      }
      else
      {
        return 2147942487LL;
      }
    }
    else
    {
      return 2147500035LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a8f0  mov     [rsp+arg_0], rbx
0x18000a8f5  mov     [rsp+arg_10], r8
0x18000a8fa  push    rdi
0x18000a8fb  push    r12
0x18000a8fd  push    r13
0x18000a8ff  push    r14
0x18000a901  push    r15
0x18000a903  sub     rsp, 60h
0x18000a907  mov     r15, r8
0x18000a90a  mov     edi, edx
0x18000a90c  mov     rbx, rcx
0x18000a90f  mov     ecx, edx; this
0x18000a911  call    ?ValidateFactor@winbio@@YAJI@Z; winbio::ValidateFactor(uint)
0x18000a916  test    eax, eax
0x18000a918  js      loc_18000AACA
0x18000a91e  test    r15, r15
0x18000a921  jz      loc_18000AB15
0x18000a927  cmp     dword ptr [r15], 1
0x18000a92b  jnz     loc_18000AAE0
0x18000a931  xorps   xmm0, xmm0
0x18000a934  movdqu  [rsp+88h+var_60], xmm0
0x18000a93a  lea     rax, [rbx+10h]
0x18000a93e  mov     [rsp+88h+arg_18], rax
0x18000a946  mov     rcx, [rax]
0x18000a949  mov     rax, [rcx+8]
0x18000a94d  xor     edx, edx
0x18000a94f  mov     [rsp+88h+var_34], edx
0x18000a953  mov     r14, rcx
0x18000a956  xor     r13d, r13d
0x18000a959  jmp     short loc_18000A95F
0x18000a95b  mov     rax, [rax+10h]
0x18000a95f  cmp     [rax+19h], dl
0x18000a962  jnz     short loc_18000A971
0x18000a964  cmp     [rax+20h], edi
0x18000a967  jb      short loc_18000A95B
0x18000a969  mov     r14, rax
0x18000a96c  mov     rax, [rax]
0x18000a96f  jmp     short loc_18000A95F
0x18000a971  cmp     [r14+19h], dl
0x18000a975  jnz     short loc_18000A981
0x18000a977  cmp     edi, [r14+20h]
0x18000a97b  jnb     loc_18000AA29
0x18000a981  mov     ecx, 10h; Size
0x18000a986  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a98b  mov     rbx, rax
0x18000a98e  mov     [rsp+88h+var_68], rax
0x18000a993  mov     qword ptr [rax], 0
0x18000a99a  mov     qword ptr [rax+8], 0
0x18000a9a2  mov     rcx, rax
0x18000a9a5  call    ?_Alloc_sentinel_and_proxy@?$list@U_WINBIO_ACCOUNT_POLICY@@V?$allocator@U_WINBIO_ACCOUNT_POLICY@@@std@@@std@@AEAAXXZ; std::list<_WINBIO_ACCOUNT_POLICY>::_Alloc_sentinel_and_proxy(void)
0x18000a9aa  nop
0x18000a9ab  mov     rdx, rbx
0x18000a9ae  lea     rcx, [rsp+88h+var_50]
0x18000a9b3  call    ??$?0V?$list@U_WINBIO_ACCOUNT_POLICY@@V?$allocator@U_WINBIO_ACCOUNT_POLICY@@@std@@@std@@$0A@@?$shared_ptr@V?$list@U_WINBIO_ACCOUNT_POLICY@@V?$allocator@U_WINBIO_ACCOUNT_POLICY@@@std@@@std@@@std@@QEAA@PEAV?$list@U_WINBIO_ACCOUNT_POLICY@@V?$allocator@U_WINBIO_ACCOUNT_POLICY@@@std@@@1@@Z; std::shared_ptr<std::list<_WINBIO_ACCOUNT_POLICY>>::shared_ptr<std::list<_WINBIO_ACCOUNT_POLICY>>(std::list<_WINBIO_ACCOUNT_POLICY> *)
0x18000a9b8  mov     r12, [rax]
0x18000a9bb  mov     r14, [rax+8]
0x18000a9bf  mov     qword ptr [rax], 0
0x18000a9c6  mov     qword ptr [rax+8], 0
0x18000a9ce  mov     qword ptr [rsp+88h+var_60], r12
0x18000a9d3  mov     qword ptr [rsp+88h+var_60+8], r14
0x18000a9d8  mov     rcx, [rsp+88h+var_48]; this
0x18000a9dd  test    rcx, rcx
0x18000a9e0  jz      short loc_18000A9E7
0x18000a9e2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a9e7  mov     [rsp+88h+var_40], edi
0x18000a9eb  test    r14, r14
0x18000a9ee  jz      short loc_18000A9F5
0x18000a9f0  lock inc dword ptr [r14+8]
0x18000a9f5  mov     [rsp+50h], r12
0x18000a9fa  mov     [rsp+88h+var_30], r14
0x18000a9ff  lea     r8, [rsp+88h+var_40]
0x18000aa04  lea     rdx, [rsp+88h+var_50]
0x18000aa09  mov     rcx, [rsp+88h+arg_18]
0x18000aa11  call    ??$_Emplace@U?$pair@KV?$shared_ptr@V?$list@U_WINBIO_ACCOUNT_POLICY@@V?$allocator@U_WINBIO_ACCOUNT_POLICY@@@std@@@std@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@V?$list@U_WINBIO_ACCOUNT_POLICY@@V?$allocator@U_WINBIO_ACCOUNT_POLICY@@@std@@@std@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@V?$list@U_WINBIO_ACCOUNT_POLICY@@V?$allocator@U_WINBIO_ACCOUNT_POLICY@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@V?$list@U_WINBIO_ACCOUNT_POLICY@@V?$allocator@U_WINBIO_ACCOUNT_POLICY@@@std@@@std@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@KV?$shared_ptr@V?$list@U_WINBIO_ACCOUNT_POLICY@@V?$allocator@U_WINBIO_ACCOUNT_POLICY@@@std@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<std::list<_WINBIO_ACCOUNT_POLICY>>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<std::list<_WINBIO_ACCOUNT_POLICY>>>>,0>>::_Emplace<std::pair<ulong,std::shared_ptr<std::list<_WINBIO_ACCOUNT_POLICY>>>>(std::pair<ulong,std::shared_ptr<std::list<_WINBIO_ACCOUNT_POLICY>>> &&)
0x18000aa16  nop
0x18000aa17  mov     rcx, [rsp+88h+var_30]; this
0x18000aa1c  test    rcx, rcx
0x18000aa1f  jz      short loc_18000AA27
0x18000aa21  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000aa26  nop
0x18000aa27  jmp     short loc_18000AA51
0x18000aa29  cmp     r14, rcx
0x18000aa2c  jz      loc_18000A981
0x18000aa32  mov     rax, [r14+30h]
0x18000aa36  test    rax, rax
0x18000aa39  jz      short loc_18000AA3F
0x18000aa3b  lock inc dword ptr [rax+8]
0x18000aa3f  mov     r12, [r14+28h]
0x18000aa43  mov     qword ptr [rsp+88h+var_60], r12
0x18000aa48  mov     r14, [r14+30h]
0x18000aa4c  mov     qword ptr [rsp+88h+var_60+8], r14
0x18000aa51  test    r13d, r13d
0x18000aa54  js      short loc_18000AABA
0x18000aa56  mov     rdi, [r12]
0x18000aa5a  mov     rbx, [rdi]
0x18000aa5d  cmp     rbx, rdi
0x18000aa60  jz      short loc_18000AAA1
0x18000aa62  mov     eax, [r15]
0x18000aa65  cmp     [rbx+10h], eax
0x18000aa68  jnz     loc_18000AAF2
0x18000aa6e  cmp     eax, 1
0x18000aa71  jnz     short loc_18000AAED
0x18000aa73  movaps  xmm0, xmmword ptr [r15]
0x18000aa77  movaps  xmm1, xmmword ptr [r15+10h]
0x18000aa7c  movaps  xmm2, xmmword ptr [r15+20h]
0x18000aa81  movaps  xmm3, xmmword ptr [r15+30h]
0x18000aa86  movaps  xmm4, xmmword ptr [r15+40h]
0x18000aa8b  movups  xmmword ptr [rbx+10h], xmm0
0x18000aa8f  movups  xmmword ptr [rbx+20h], xmm1
0x18000aa93  movups  xmmword ptr [rbx+30h], xmm2
0x18000aa97  movups  xmmword ptr [rbx+40h], xmm3
0x18000aa9b  movups  xmmword ptr [rbx+50h], xmm4
0x18000aa9f  jmp     short loc_18000AABA
0x18000aaa1  mov     rdx, [r12]
0x18000aaa5  mov     r8, r15
0x18000aaa8  mov     rcx, r12
0x18000aaab  cmp     dword ptr [r15], 1
0x18000aaaf  jnz     short loc_18000AAFA
0x18000aab1  mov     rdx, [rdx]
0x18000aab4  call    ??$_Emplace@AEBU_WINBIO_ACCOUNT_POLICY@@@?$list@U_WINBIO_ACCOUNT_POLICY@@V?$allocator@U_WINBIO_ACCOUNT_POLICY@@@std@@@std@@QEAAPEAU?$_List_node@U_WINBIO_ACCOUNT_POLICY@@PEAX@1@QEAU21@AEBU_WINBIO_ACCOUNT_POLICY@@@Z; std::list<_WINBIO_ACCOUNT_POLICY>::_Emplace<_WINBIO_ACCOUNT_POLICY const &>(std::_List_node<_WINBIO_ACCOUNT_POLICY,void *> * const,_WINBIO_ACCOUNT_POLICY const &)
0x18000aab9  nop
0x18000aaba  test    r14, r14
0x18000aabd  jz      short loc_18000AAC7
0x18000aabf  mov     rcx, r14; this
0x18000aac2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000aac7  mov     eax, r13d
0x18000aaca  mov     rbx, [rsp+88h+arg_0]
0x18000aad2  add     rsp, 60h
0x18000aad6  pop     r15
0x18000aad8  pop     r14
0x18000aada  pop     r13
0x18000aadc  pop     r12
0x18000aade  pop     rdi
0x18000aadf  retn
0x18000aae0  cmp     dword ptr [r15], 3
0x18000aae4  jz      short loc_18000AB01
0x18000aae6  mov     eax, 80070057h
0x18000aaeb  jmp     short loc_18000AACA
0x18000aaed  cmp     eax, 3
0x18000aaf0  jz      short loc_18000AB3B
0x18000aaf2  mov     rbx, [rbx]
0x18000aaf5  jmp     loc_18000AA5D
0x18000aafa  call    ??$_Emplace@AEBU_WINBIO_ACCOUNT_POLICY@@@?$list@U_WINBIO_ACCOUNT_POLICY@@V?$allocator@U_WINBIO_ACCOUNT_POLICY@@@std@@@std@@QEAAPEAU?$_List_node@U_WINBIO_ACCOUNT_POLICY@@PEAX@1@QEAU21@AEBU_WINBIO_ACCOUNT_POLICY@@@Z; std::list<_WINBIO_ACCOUNT_POLICY>::_Emplace<_WINBIO_ACCOUNT_POLICY const &>(std::_List_node<_WINBIO_ACCOUNT_POLICY,void *> * const,_WINBIO_ACCOUNT_POLICY const &)
0x18000aaff  jmp     short loc_18000AABA
0x18000ab01  lea     rcx, [r15+8]; pSid
0x18000ab05  call    cs:__imp_IsValidSid
0x18000ab0b  test    eax, eax
0x18000ab0d  jnz     loc_18000A931
0x18000ab13  jmp     short loc_18000AAE6
0x18000ab15  mov     eax, 80004003h
0x18000ab1a  jmp     short loc_18000AACA
0x18000ab1c  mov     r15, [rsp+88h+arg_10]
0x18000ab24  mov     r13d, dword ptr [rsp+88h+arg_18]
0x18000ab2c  mov     r14, qword ptr [rsp+88h+var_60+8]
0x18000ab31  mov     r12, qword ptr [rsp+88h+var_60]
0x18000ab36  jmp     loc_18000AA51
0x18000ab3b  lea     rdx, [rbx+18h]; pSid2
0x18000ab3f  lea     rcx, [r15+8]; pSid1
0x18000ab43  call    cs:__imp_EqualSid
0x18000ab49  test    eax, eax
0x18000ab4b  jnz     loc_18000AA73
0x18000ab51  jmp     short loc_18000AAF2
0x18000ab53  mov     r13d, dword ptr [rsp+88h+arg_18]
0x18000ab5b  mov     r14, qword ptr [rsp+88h+var_60+8]
0x18000ab60  jmp     loc_18000AABA
```
