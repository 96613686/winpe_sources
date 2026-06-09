# Microsoft::Windows::Performance::CCvDDCache::AddFailure(ushort const *,ulong)

- ea: `0x180016248`
- end: `0x18001646f`
- name: `?AddFailure@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGK@Z`
- size: `551`
- prototype: `int(Microsoft::Windows::Performance::CCvDDCache *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016698`

## callees

- `0x180001540`
- `0x180012cbc`
- `0x180012f80`
- `0x180014584`
- `0x1800153c4`
- `0x180015950`
- `0x180015a30`
- `0x180016248`
- `0x1800319f0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001639a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800163cf`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001639a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800163cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Performance::CCvDDCache::AddFailure(
        Microsoft::Windows::Performance::CCvDDCache *this,
        unsigned __int16 *a2,
        int a3)
{
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  _QWORD *v12; // rbx
  __int64 v13; // rax
  _QWORD *v14; // rcx
  __int64 result; // rax
  _QWORD v16[2]; // [rsp+60h] [rbp-118h] BYREF
  void *v17[2]; // [rsp+70h] [rbp-108h] BYREF
  __int64 v18; // [rsp+80h] [rbp-F8h]
  unsigned __int64 v19; // [rsp+88h] [rbp-F0h]
  void *v20[3]; // [rsp+90h] [rbp-E8h] BYREF
  unsigned __int64 v21; // [rsp+A8h] [rbp-D0h]
  _BYTE v22[144]; // [rsp+B0h] [rbp-C8h] BYREF

  v16[1] = -2;
  LODWORD(v16[0]) = a3;
  v21 = 7;
  v20[2] = 0;
  LOWORD(v20[0]) = 0;
  try
  {
    std::wstring::assign(v20, (void *)&Src);
    v19 = 7;
    v18 = 0;
    LOWORD(v17[0]) = 0;
    if ( *a2 )
    {
      v6 = -1;
      do
        ++v6;
      while ( a2[v6] );
    }
    std::wstring::assign(v17, a2);
    v7 = Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
           (__int64)v22,
           (__int64)v17,
           (__int64)v20,
           0,
           0,
           0,
           0,
           a3,
           0,
           0,
           0,
           0);
    v8 = *(_QWORD *)this;
    v10 = std::_List_buy<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Buynode<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(
            v9,
            *(_QWORD *)this,
            *(_QWORD *)(*(_QWORD *)this + 8LL),
            v7);
    v11 = *((_QWORD *)this + 1);
    if ( v11 == 0x199999999999998LL )
      std::_Xlength_error("list<T> too long");
    *((_QWORD *)this + 1) = v11 + 1;
    *(_QWORD *)(v8 + 8) = v10;
    **(_QWORD **)(v10 + 8) = v10;
    Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD((Microsoft::Windows::Performance::CCvDDCache::CCvDD *)v22);
    if ( v19 >= 8 )
      operator delete(v17[0]);
    v19 = 7;
    v18 = 0;
    LOWORD(v17[0]) = 0;
    if ( v21 >= 8 )
      operator delete(v20[0]);
    v12 = (_QWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 16LL);
    v13 = std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](
            (char *)this + 16,
            v16);
    if ( v12[3] < 8u )
      v14 = v12;
    else
      v14 = (_QWORD *)*v12;
    v16[0] = v14;
    *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
                 v13,
                 v16) = 0;
    if ( v12[3] >= 8u )
      v12 = (_QWORD *)*v12;
    v16[0] = v12;
    *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
                 (char *)this + 32,
                 v16) = 0;
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
0x180016248  mov     r11, rsp
0x18001624b  push    rbx
0x18001624c  push    rsi
0x18001624d  push    rdi
0x18001624e  push    r14
0x180016250  push    r15
0x180016252  sub     rsp, 150h
0x180016259  mov     [rsp+178h+var_110], 0FFFFFFFFFFFFFFFEh
0x180016262  mov     rax, cs:__security_cookie
0x180016269  xor     rax, rsp
0x18001626c  mov     [rsp+178h+var_38], rax
0x180016274  mov     esi, r8d
0x180016277  mov     rbx, rdx
0x18001627a  mov     rdi, rcx
0x18001627d  mov     dword ptr [rsp+178h+var_118], r8d
0x180016282  mov     r15d, 7
0x180016288  mov     [r11-0D0h], r15
0x18001628f  xor     r14d, r14d
0x180016292  mov     [r11-0D8h], r14
0x180016299  mov     [r11-0E8h], r14w
0x1800162a1  xor     r8d, r8d
0x1800162a4  lea     rdx, Src; Src
0x1800162ab  lea     rcx, [r11-0E8h]; void *
0x1800162b2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800162b7  nop
0x1800162b8  mov     [rsp+178h+var_F0], r15
0x1800162c0  mov     [rsp+178h+var_F8], r14
0x1800162c8  mov     word ptr [rsp+178h+var_108], r14w
0x1800162ce  cmp     [rbx], r14w
0x1800162d2  jnz     short loc_1800162D9
0x1800162d4  mov     r8d, r14d
0x1800162d7  jmp     short loc_1800162E7
0x1800162d9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800162dd  inc     r8
0x1800162e0  cmp     [rbx+r8*2], r14w
0x1800162e5  jnz     short loc_1800162DD
0x1800162e7  mov     rdx, rbx; Src
0x1800162ea  lea     rcx, [rsp+178h+var_108]; void *
0x1800162ef  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800162f4  nop
0x1800162f5  mov     [rsp+178h+var_120], r14b
0x1800162fa  mov     [rsp+178h+var_128], r14
0x1800162ff  mov     [rsp+178h+var_130], r14d
0x180016304  mov     [rsp+178h+var_138], r14d
0x180016309  mov     [rsp+178h+var_140], esi
0x18001630d  mov     [rsp+178h+var_148], r14
0x180016312  mov     [rsp+178h+var_150], r14
0x180016317  mov     [rsp+178h+var_158], r14
0x18001631c  xor     r9d, r9d
0x18001631f  lea     r8, [rsp+178h+var_E8]
0x180016327  lea     rdx, [rsp+178h+var_108]
0x18001632c  lea     rcx, [rsp+178h+var_C8]
0x180016334  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::wstring const &,std::wstring const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)
0x180016339  nop
0x18001633a  mov     rbx, [rdi]
0x18001633d  mov     r9, rax
0x180016340  mov     r8, [rbx+8]
0x180016344  mov     rdx, rbx
0x180016347  call    ??$_Buynode@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@?$_List_buy@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAPEAU?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@1@PEAU21@0$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::_List_buy<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Buynode<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *> *,std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *> *,Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)
0x18001634c  mov     rdx, rax
0x18001634f  mov     rax, [rdi+8]
0x180016353  mov     rcx, 199999999999998h
0x18001635d  sub     rcx, rax
0x180016360  cmp     rcx, 1
0x180016364  jb      loc_180016461
0x18001636a  inc     rax
0x18001636d  mov     [rdi+8], rax
0x180016371  mov     [rbx+8], rdx
0x180016375  mov     rax, [rdx+8]
0x180016379  mov     [rax], rdx
0x18001637c  lea     rcx, [rsp+178h+var_C8]; this
0x180016384  call    ??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)
0x180016389  nop
0x18001638a  cmp     [rsp+178h+var_F0], 8
0x180016393  jb      short loc_1800163A6
0x180016395  mov     rcx, [rsp+178h+var_108]
0x18001639a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800163a1  nop     dword ptr [rax+rax+00h]
0x1800163a6  mov     [rsp+178h+var_F0], r15
0x1800163ae  mov     [rsp+178h+var_F8], r14
0x1800163b6  mov     word ptr [rsp+178h+var_108], r14w
0x1800163bc  cmp     [rsp+178h+var_D0], 8
0x1800163c5  jb      short loc_1800163DB
0x1800163c7  mov     rcx, [rsp+178h+var_E8]
0x1800163cf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800163d6  nop     dword ptr [rax+rax+00h]
0x1800163db  mov     rax, [rdi]
0x1800163de  mov     rbx, [rax+8]
0x1800163e2  add     rbx, 10h
0x1800163e6  lea     rcx, [rdi+10h]
0x1800163ea  lea     rdx, [rsp+178h+var_118]
0x1800163ef  call    ??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](ulong const &)
0x1800163f4  cmp     qword ptr [rbx+18h], 8
0x1800163f9  jb      short loc_180016400
0x1800163fb  mov     rcx, [rbx]
0x1800163fe  jmp     short loc_180016403
0x180016400  mov     rcx, rbx
0x180016403  mov     [rsp+178h+var_118], rcx
0x180016408  lea     rdx, [rsp+178h+var_118]
0x18001640d  mov     rcx, rax
0x180016410  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x180016415  mov     [rax], r14
0x180016418  cmp     qword ptr [rbx+18h], 8
0x18001641d  jb      short loc_180016422
0x18001641f  mov     rbx, [rbx]
0x180016422  mov     [rsp+178h+var_118], rbx
0x180016427  lea     rcx, [rdi+20h]
0x18001642b  lea     rdx, [rsp+178h+var_118]
0x180016430  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x180016435  mov     [rax], r14
0x180016438  xor     eax, eax
0x18001643a  jmp     short loc_180016441
0x18001643c  mov     eax, 8007000Eh
0x180016441  mov     rcx, [rsp+178h+var_38]
0x180016449  xor     rcx, rsp; StackCookie
0x18001644c  call    __security_check_cookie
0x180016451  add     rsp, 150h
0x180016458  pop     r15
0x18001645a  pop     r14
0x18001645c  pop     rdi
0x18001645d  pop     rsi
0x18001645e  pop     rbx
0x18001645f  retn
0x180016461  lea     rcx, aListTTooLong; "list<T> too long"
0x180016468  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
