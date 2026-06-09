# Microsoft::Windows::Performance::CCvDDCache::Add(ushort const *,ulong,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,EMBEDDED_PDB_INFORMATION *,bool,ushort const *,bool *)

- ea: `0x180015e34`
- end: `0x180016163`
- name: `?Add@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKKPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKPEAUEMBEDDED_PDB_INFORMATION@@_N0PEA_N@Z`
- size: `815`
- prototype: `int(Microsoft::Windows::Performance::CCvDDCache *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, const union _CVDD *, const unsigned int *, const struct CODEVIEW_INFORMATION_1 *, unsigned int, unsigned int, struct EMBEDDED_PDB_INFORMATION *, bool, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016698`

## callees

- `0x180001540`
- `0x180012cbc`
- `0x180012f80`
- `0x180014048`
- `0x180014584`
- `0x1800153c4`
- `0x180015950`
- `0x180015a30`
- `0x180015e34`
- `0x1800319f0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180016033`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016074`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016033`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016074`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Performance::CCvDDCache::Add(
        Microsoft::Windows::Performance::CCvDDCache *this,
        unsigned __int16 *a2,
        int a3,
        int a4,
        const union _CVDD *a5,
        const unsigned int *a6,
        const struct CODEVIEW_INFORMATION_1 *a7,
        unsigned int a8,
        unsigned int a9,
        struct EMBEDDED_PDB_INFORMATION *a10,
        char a11,
        unsigned __int16 *Src,
        bool *a13)
{
  __int64 v17; // rbx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rax
  const union _CVDD *v24; // rbx
  __int64 v25; // rax
  const union _CVDD *v26; // rcx
  const union _CVDD *v27; // rax
  int v28; // r8d
  __int64 result; // rax
  const union _CVDD *v30; // [rsp+68h] [rbp-150h] BYREF
  unsigned int v31; // [rsp+70h] [rbp-148h]
  unsigned int v32; // [rsp+74h] [rbp-144h]
  int v33; // [rsp+78h] [rbp-140h] BYREF
  const struct CODEVIEW_INFORMATION_1 *v34; // [rsp+80h] [rbp-138h]
  const unsigned int *v35; // [rsp+88h] [rbp-130h] BYREF
  bool v36; // [rsp+90h] [rbp-128h]
  __int64 v37; // [rsp+98h] [rbp-120h]
  void *v38[2]; // [rsp+A0h] [rbp-118h] BYREF
  __int64 v39; // [rsp+B0h] [rbp-108h]
  unsigned __int64 v40; // [rsp+B8h] [rbp-100h]
  void *v41[3]; // [rsp+C0h] [rbp-F8h] BYREF
  unsigned __int64 v42; // [rsp+D8h] [rbp-E0h]
  _BYTE v43[144]; // [rsp+E0h] [rbp-D8h] BYREF

  v37 = -2;
  v33 = a3;
  v30 = a5;
  v35 = a6;
  v34 = a7;
  v32 = a8;
  v31 = a9;
  v42 = 7;
  v41[2] = 0;
  LOWORD(v41[0]) = 0;
  v17 = -1;
  if ( *Src )
  {
    v18 = -1;
    do
      ++v18;
    while ( Src[v18] );
  }
  try
  {
    std::wstring::assign(v41, Src);
    v40 = 7;
    v39 = 0;
    LOWORD(v38[0]) = 0;
    if ( *a2 )
    {
      do
        ++v17;
      while ( a2[v17] );
    }
    std::wstring::assign(v38, a2);
    v19 = Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
            (unsigned int)v43,
            (unsigned int)v38,
            (unsigned int)v41,
            a4,
            (__int64)v30,
            (__int64)v35,
            (__int64)v34,
            a3,
            v32,
            v31,
            (__int64)a10,
            a11);
    v20 = *(_QWORD *)this;
    v22 = std::_List_buy<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Buynode<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(
            v21,
            *(_QWORD *)this,
            *(_QWORD *)(*(_QWORD *)this + 8LL),
            v19);
    v23 = *((_QWORD *)this + 1);
    if ( v23 == 0x199999999999998LL )
      std::_Xlength_error("list<T> too long");
    *((_QWORD *)this + 1) = v23 + 1;
    *(_QWORD *)(v20 + 8) = v22;
    **(_QWORD **)(v22 + 8) = v22;
    Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD((Microsoft::Windows::Performance::CCvDDCache::CCvDD *)v43);
    if ( v40 >= 8 )
      operator delete(v38[0]);
    v40 = 7;
    v39 = 0;
    LOWORD(v38[0]) = 0;
    if ( v42 >= 8 )
      operator delete(v41[0]);
    v24 = (const union _CVDD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 16LL);
    v25 = std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](
            (char *)this + 16,
            &v33);
    if ( *((_QWORD *)v24 + 3) < 8u )
      v26 = v24;
    else
      v26 = *(const union _CVDD **)v24;
    v30 = v26;
    *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
                 v25,
                 &v30) = v24;
    if ( *((_QWORD *)v24 + 3) < 8u )
      v27 = v24;
    else
      v27 = *(const union _CVDD **)v24;
    v30 = v27;
    *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
                 (char *)this + 32,
                 &v30) = v24;
    if ( a13 )
    {
      v30 = v24;
      std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Insert_nohint<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,std::_Nil>(
        (_DWORD)this + 48,
        (unsigned int)&v35,
        v28,
        (unsigned int)&v30,
        byte_18004D348);
      *a13 = v36;
    }
    if ( a10 && *(_DWORD *)a10 )
      *((_QWORD *)a10 + 1) = *((_QWORD *)v24 + 12);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180015e34  push    rbx
0x180015e36  push    rsi
0x180015e37  push    rdi
0x180015e38  push    r12
0x180015e3a  push    r13
0x180015e3c  push    r14
0x180015e3e  push    r15
0x180015e40  sub     rsp, 180h
0x180015e47  mov     [rsp+1B8h+var_120], 0FFFFFFFFFFFFFFFEh
0x180015e53  mov     rax, cs:__security_cookie
0x180015e5a  xor     rax, rsp
0x180015e5d  mov     [rsp+1B8h+var_48], rax
0x180015e65  mov     r13d, r9d
0x180015e68  mov     r12d, r8d
0x180015e6b  mov     r14, rdx
0x180015e6e  mov     rdi, rcx
0x180015e71  mov     rsi, [rsp+1B8h+arg_48]
0x180015e79  mov     [rsp+1B8h+var_140], r8d
0x180015e7e  mov     rax, [rsp+1B8h+arg_20]
0x180015e86  mov     [rsp+1B8h+var_150], rax
0x180015e8b  mov     rax, [rsp+1B8h+arg_28]
0x180015e93  mov     [rsp+1B8h+var_130], rax
0x180015e9b  mov     rax, [rsp+1B8h+arg_30]
0x180015ea3  mov     [rsp+1B8h+var_138], rax
0x180015eab  mov     eax, [rsp+1B8h+arg_38]
0x180015eb2  mov     [rsp+1B8h+var_144], eax
0x180015eb6  mov     eax, [rsp+1B8h+arg_40]
0x180015ebd  mov     [rsp+1B8h+var_148], eax
0x180015ec1  mov     al, [rsp+1B8h+arg_50]
0x180015ec8  mov     [rsp+1B8h+var_158], al
0x180015ecc  mov     rdx, [rsp+1B8h+Src]; Src
0x180015ed4  mov     r15, [rsp+1B8h+arg_60]
0x180015edc  mov     [rsp+1B8h+var_E0], 7
0x180015ee8  xor     ecx, ecx
0x180015eea  mov     [rsp+1B8h+var_E8], rcx
0x180015ef2  mov     word ptr [rsp+1B8h+var_F8], cx
0x180015efa  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015efe  cmp     [rdx], cx
0x180015f01  jnz     short loc_180015F08
0x180015f03  mov     r8d, ecx
0x180015f06  jmp     short loc_180015F15
0x180015f08  mov     r8, rbx
0x180015f0b  inc     r8
0x180015f0e  cmp     [rdx+r8*2], cx
0x180015f13  jnz     short loc_180015F0B
0x180015f15  lea     rcx, [rsp+1B8h+var_F8]; void *
0x180015f1d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180015f22  nop
0x180015f23  mov     [rsp+1B8h+var_100], 7
0x180015f2f  xor     ecx, ecx
0x180015f31  mov     [rsp+1B8h+var_108], rcx
0x180015f39  mov     word ptr [rsp+1B8h+var_118], cx
0x180015f41  cmp     [r14], cx
0x180015f45  jnz     short loc_180015F4B
0x180015f47  mov     ebx, ecx
0x180015f49  jmp     short loc_180015F55
0x180015f4b  inc     rbx
0x180015f4e  cmp     [r14+rbx*2], cx
0x180015f53  jnz     short loc_180015F4B
0x180015f55  mov     r8, rbx
0x180015f58  mov     rdx, r14; Src
0x180015f5b  lea     rcx, [rsp+1B8h+var_118]; void *
0x180015f63  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180015f68  nop
0x180015f69  mov     al, [rsp+1B8h+var_158]
0x180015f6d  mov     [rsp+1B8h+var_160], al
0x180015f71  mov     [rsp+1B8h+var_168], rsi
0x180015f76  mov     eax, [rsp+1B8h+var_148]
0x180015f7a  mov     [rsp+1B8h+var_170], eax
0x180015f7e  mov     eax, [rsp+1B8h+var_144]
0x180015f82  mov     [rsp+1B8h+var_178], eax
0x180015f86  mov     [rsp+1B8h+var_180], r12d
0x180015f8b  mov     rax, [rsp+1B8h+var_138]
0x180015f93  mov     [rsp+1B8h+var_188], rax
0x180015f98  mov     rax, [rsp+1B8h+var_130]
0x180015fa0  mov     [rsp+1B8h+var_190], rax
0x180015fa5  mov     rax, [rsp+1B8h+var_150]
0x180015faa  mov     [rsp+1B8h+var_198], rax
0x180015faf  mov     r9d, r13d
0x180015fb2  lea     r8, [rsp+1B8h+var_F8]
0x180015fba  lea     rdx, [rsp+1B8h+var_118]
0x180015fc2  lea     rcx, [rsp+1B8h+var_D8]
0x180015fca  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::wstring const &,std::wstring const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)
0x180015fcf  nop
0x180015fd0  mov     rbx, [rdi]
0x180015fd3  mov     r9, rax
0x180015fd6  mov     r8, [rbx+8]
0x180015fda  mov     rdx, rbx
0x180015fdd  call    ??$_Buynode@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@?$_List_buy@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAPEAU?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@1@PEAU21@0$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::_List_buy<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Buynode<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *> *,std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *> *,Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)
0x180015fe2  mov     rdx, rax
0x180015fe5  mov     rax, [rdi+8]
0x180015fe9  mov     rcx, 199999999999998h
0x180015ff3  sub     rcx, rax
0x180015ff6  cmp     rcx, 1
0x180015ffa  jb      loc_180016155
0x180016000  inc     rax
0x180016003  mov     [rdi+8], rax
0x180016007  mov     [rbx+8], rdx
0x18001600b  mov     rax, [rdx+8]
0x18001600f  mov     [rax], rdx
0x180016012  lea     rcx, [rsp+1B8h+var_D8]; this
0x18001601a  call    ??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)
0x18001601f  nop
0x180016020  cmp     [rsp+1B8h+var_100], 8
0x180016029  jb      short loc_18001603F
0x18001602b  mov     rcx, [rsp+1B8h+var_118]
0x180016033  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001603a  nop     dword ptr [rax+rax+00h]
0x18001603f  mov     [rsp+1B8h+var_100], 7
0x18001604b  mov     [rsp+1B8h+var_108], 0
0x180016057  xor     eax, eax
0x180016059  mov     word ptr [rsp+1B8h+var_118], ax
0x180016061  cmp     [rsp+1B8h+var_E0], 8
0x18001606a  jb      short loc_180016080
0x18001606c  mov     rcx, [rsp+1B8h+var_F8]
0x180016074  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001607b  nop     dword ptr [rax+rax+00h]
0x180016080  mov     rax, [rdi]
0x180016083  mov     rbx, [rax+8]
0x180016087  add     rbx, 10h
0x18001608b  lea     rcx, [rdi+10h]
0x18001608f  lea     rdx, [rsp+1B8h+var_140]
0x180016094  call    ??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](ulong const &)
0x180016099  cmp     qword ptr [rbx+18h], 8
0x18001609e  jb      short loc_1800160A5
0x1800160a0  mov     rcx, [rbx]
0x1800160a3  jmp     short loc_1800160A8
0x1800160a5  mov     rcx, rbx
0x1800160a8  mov     [rsp+1B8h+var_150], rcx
0x1800160ad  lea     rdx, [rsp+1B8h+var_150]
0x1800160b2  mov     rcx, rax
0x1800160b5  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x1800160ba  mov     [rax], rbx
0x1800160bd  cmp     qword ptr [rbx+18h], 8
0x1800160c2  jb      short loc_1800160C9
0x1800160c4  mov     rax, [rbx]
0x1800160c7  jmp     short loc_1800160CC
0x1800160c9  mov     rax, rbx
0x1800160cc  mov     [rsp+1B8h+var_150], rax
0x1800160d1  lea     rcx, [rdi+20h]
0x1800160d5  lea     rdx, [rsp+1B8h+var_150]
0x1800160da  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x1800160df  mov     [rax], rbx
0x1800160e2  test    r15, r15
0x1800160e5  jz      short loc_180016116
0x1800160e7  mov     [rsp+1B8h+var_150], rbx
0x1800160ec  mov     al, cs:byte_18004D348
0x1800160f2  lea     rcx, [rdi+30h]
0x1800160f6  mov     byte ptr [rsp+1B8h+var_198], al
0x1800160fa  lea     r9, [rsp+1B8h+var_150]
0x1800160ff  lea     rdx, [rsp+1B8h+var_130]
0x180016107  call    ??$_Insert_nohint@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@_N@1@_N$$QEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Insert_nohint<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,std::_Nil>(bool,Microsoft::Windows::Performance::CCvDDCache::CCvDD const * &&,std::_Nil)
0x18001610c  mov     al, [rsp+1B8h+var_128]
0x180016113  mov     [r15], al
0x180016116  test    rsi, rsi
0x180016119  jz      short loc_180016128
0x18001611b  cmp     dword ptr [rsi], 0
0x18001611e  jz      short loc_180016128
0x180016120  mov     rax, [rbx+60h]
0x180016124  mov     [rsi+8], rax
0x180016128  xor     eax, eax
0x18001612a  jmp     short loc_180016131
0x18001612c  mov     eax, 8007000Eh
0x180016131  mov     rcx, [rsp+1B8h+var_48]
0x180016139  xor     rcx, rsp; StackCookie
0x18001613c  call    __security_check_cookie
0x180016141  add     rsp, 180h
0x180016148  pop     r15
0x18001614a  pop     r14
0x18001614c  pop     r13
0x18001614e  pop     r12
0x180016150  pop     rdi
0x180016151  pop     rsi
0x180016152  pop     rbx
0x180016153  retn
0x180016155  lea     rcx, aListTTooLong; "list<T> too long"
0x18001615c  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
