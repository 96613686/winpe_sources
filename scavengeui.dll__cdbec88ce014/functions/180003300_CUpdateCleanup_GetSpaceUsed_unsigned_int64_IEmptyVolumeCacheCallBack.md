# CUpdateCleanup::GetSpaceUsed(unsigned __int64 *,IEmptyVolumeCacheCallBack *)

- ea: `0x180003300`
- end: `0x180003615`
- name: `?GetSpaceUsed@CUpdateCleanup@@UEAAJPEA_KPEAUIEmptyVolumeCacheCallBack@@@Z`
- size: `789`
- prototype: `__int64 __fastcall(CUpdateCleanup *__hidden this, unsigned __int64 *, struct IEmptyVolumeCacheCallBack *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180002fcc`
- `0x180003128`
- `0x180003300`
- `0x180003798`
- `0x180005010`

## import_xrefs

- `DismApi!DismDelete` at `0x1800035a4`
- `DismApi!DismDelete` at `0x1800035cf`
- `DismApi!DismDelete` at `0x1800035f6`
- `DismApi!DismDelete` at `0x1800035a4`
- `DismApi!DismDelete` at `0x1800035cf`
- `DismApi!DismDelete` at `0x1800035f6`
- `DismApi!DismGetPackages` at `0x1800034c7`
- `DismApi!DismGetPackages` at `0x1800034c7`

## pseudocode

```c
__int64 __fastcall CUpdateCleanup::GetSpaceUsed(
        CUpdateCleanup *this,
        unsigned __int64 *a2,
        struct IEmptyVolumeCacheCallBack *a3)
{
  int v6; // r8d
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  __int64 v13; // rax
  int Packages; // esi
  __int64 v15; // rsi
  __int64 v16; // rax
  __int64 v17; // r9
  __int64 *v18; // rcx
  __int64 *v19; // rdx
  int v20; // eax
  unsigned int i; // r14d
  unsigned __int64 v22; // rax
  _QWORD v23[2]; // [rsp+30h] [rbp-48h] BYREF
  void **v24; // [rsp+40h] [rbp-38h] BYREF
  __int64 v25; // [rsp+48h] [rbp-30h]
  _BYTE v26[16]; // [rsp+50h] [rbp-28h] BYREF
  unsigned int v27; // [rsp+80h] [rbp+8h] BYREF
  int v28; // [rsp+88h] [rbp+10h] BYREF

  *((_DWORD *)this + 136) = 0;
  if ( !a2 )
    return 2147942487LL;
  v25 = 0;
  v24 = &RAII::CAutoDismDelete<_DismPackage *>::`vftable';
  v27 = 0;
  v23[1] = 0;
  v23[0] = ((__int64 (__fastcall *)(CUpdateCleanup *, unsigned __int64 *, struct IEmptyVolumeCacheCallBack *))std::_Tree_alloc<0,std::_Tree_base_types<enum _DismReleaseType>>::_Buyheadnode)(
             this,
             a2,
             a3);
  v28 = 0;
  std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::_Insert_nohint<enum _DismReleaseType,std::_Nil>(
    (__int64 *)(unsigned int)v23,
    (unsigned int)v26,
    v6,
    (int *)(unsigned int)&v28,
    byte_18000A8DC);
  v28 = 3;
  std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::_Insert_nohint<enum _DismReleaseType,std::_Nil>(
    (__int64 *)(unsigned int)v23,
    (unsigned int)v26,
    v7,
    (int *)(unsigned int)&v28,
    byte_18000A8DC);
  v28 = 4;
  std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::_Insert_nohint<enum _DismReleaseType,std::_Nil>(
    (__int64 *)(unsigned int)v23,
    (unsigned int)v26,
    v8,
    (int *)(unsigned int)&v28,
    byte_18000A8DC);
  v28 = 5;
  std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::_Insert_nohint<enum _DismReleaseType,std::_Nil>(
    (__int64 *)(unsigned int)v23,
    (unsigned int)v26,
    v9,
    (int *)(unsigned int)&v28,
    byte_18000A8DC);
  v28 = 6;
  std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::_Insert_nohint<enum _DismReleaseType,std::_Nil>(
    (__int64 *)(unsigned int)v23,
    (unsigned int)v26,
    v10,
    (int *)(unsigned int)&v28,
    byte_18000A8DC);
  v28 = 7;
  std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::_Insert_nohint<enum _DismReleaseType,std::_Nil>(
    (__int64 *)(unsigned int)v23,
    (unsigned int)v26,
    v11,
    (int *)(unsigned int)&v28,
    byte_18000A8DC);
  v28 = 10;
  std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::_Insert_nohint<enum _DismReleaseType,std::_Nil>(
    (__int64 *)(unsigned int)v23,
    (unsigned int)v26,
    v12,
    (int *)(unsigned int)&v28,
    byte_18000A8DC);
  v13 = ((__int64 (__fastcall *)(void ***))v24[1])(&v24);
  Packages = DismGetPackages(*((unsigned int *)this + 156), v13, &v27);
  if ( Packages < 0 )
  {
    std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::~_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>((void **)v23);
    v24 = &RAII::CAutoDismDelete<_DismPackage *>::`vftable';
    if ( v25 )
      DismDelete();
    return (unsigned int)Packages;
  }
  else
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      for ( i = 0; i < v27; ++i )
      {
        v15 = 32LL * i;
        if ( *(_DWORD *)(v15 + ((__int64 (__fastcall *)(void ***))v24[4])(&v24) + 8) == 6 )
        {
          v16 = ((__int64 (__fastcall *)(void ***))v24[4])(&v24);
          v17 = v16;
          v18 = *(__int64 **)(v23[0] + 8LL);
          v19 = (__int64 *)v23[0];
          if ( !*((_BYTE *)v18 + 25) )
          {
            v20 = *(_DWORD *)(v15 + v16 + 12);
            do
            {
              if ( *((_DWORD *)v18 + 7) >= v20 )
              {
                v19 = v18;
                v18 = (__int64 *)*v18;
              }
              else
              {
                v18 = (__int64 *)v18[2];
              }
            }
            while ( !*((_BYTE *)v18 + 25) );
          }
          if ( v19 == (__int64 *)v23[0] || *(_DWORD *)(v15 + v17 + 12) < *((_DWORD *)v19 + 7) )
            v19 = (__int64 *)v23[0];
          if ( v19 != (__int64 *)v23[0] )
            *((_DWORD *)this + 136) += 190;
        }
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
      {
        __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_1800035AE);
        std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::~_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>((void **)v23);
        v24 = &RAII::CAutoDismDelete<_DismPackage *>::`vftable';
        if ( v25 )
          DismDelete();
        return 2147549183LL;
      }
    }
    v22 = (unsigned __int64)*((unsigned int *)this + 136) << 20;
    *a2 = v22;
    *((_QWORD *)this + 69) = v22;
    std::_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>::~_Tree<std::_Tset_traits<enum _DismReleaseType,std::less<enum _DismReleaseType>,std::allocator<enum _DismReleaseType>,0>>((void **)v23);
    v24 = &RAII::CAutoDismDelete<_DismPackage *>::`vftable';
    if ( v25 )
      DismDelete();
    return 0;
  }
}

```

## disassembly

```asm
0x180003300  mov     [rsp+arg_10], rsi
0x180003305  mov     [rsp+arg_18], rdi
0x18000330a  push    r12
0x18000330c  push    r14
0x18000330e  push    r15
0x180003310  sub     rsp, 60h
0x180003314  mov     r12, rdx
0x180003317  mov     rdi, rcx
0x18000331a  mov     dword ptr [rcx+220h], 0
0x180003324  test    rdx, rdx
0x180003327  jnz     short loc_180003333
0x180003329  mov     eax, 80070057h
0x18000332e  jmp     loc_1800035FE
0x180003333  mov     [rsp+78h+var_30], 0
0x18000333c  lea     r15, ??_7?$CAutoDismDelete@PEAU_DismPackage@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismPackage *>::`vftable'
0x180003343  mov     [rsp+78h+var_38], r15
0x180003348  mov     [rsp+78h+arg_0], 0
0x180003353  mov     [rsp+78h+var_48], 0
0x18000335c  mov     [rsp+78h+var_40], 0
0x180003365  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@W4_DismReleaseType@@V?$allocator@W4_DismReleaseType@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@W4_DismReleaseType@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<_DismReleaseType>>::_Buyheadnode(void)
0x18000336a  mov     [rsp+78h+var_48], rax
0x18000336f  mov     [rsp+78h+arg_8], 0
0x18000337a  mov     al, cs:byte_18000A8DC
0x180003380  mov     [rsp+78h+var_58], al
0x180003384  lea     r9, [rsp+78h+arg_8]
0x18000338c  lea     rdx, [rsp+78h+var_28]
0x180003391  lea     rcx, [rsp+78h+var_48]
0x180003396  call    ??$_Insert_nohint@W4_DismReleaseType@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@W4_DismReleaseType@@@std@@@std@@@std@@_N@1@_N$$QEAW4_DismReleaseType@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::_Insert_nohint<_DismReleaseType,std::_Nil>(bool,_DismReleaseType &&,std::_Nil)
0x18000339b  mov     [rsp+78h+arg_8], 3
0x1800033a6  mov     al, cs:byte_18000A8DC
0x1800033ac  mov     [rsp+78h+var_58], al
0x1800033b0  lea     r9, [rsp+78h+arg_8]
0x1800033b8  lea     rdx, [rsp+78h+var_28]
0x1800033bd  lea     rcx, [rsp+78h+var_48]
0x1800033c2  call    ??$_Insert_nohint@W4_DismReleaseType@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@W4_DismReleaseType@@@std@@@std@@@std@@_N@1@_N$$QEAW4_DismReleaseType@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::_Insert_nohint<_DismReleaseType,std::_Nil>(bool,_DismReleaseType &&,std::_Nil)
0x1800033c7  mov     [rsp+78h+arg_8], 4
0x1800033d2  mov     al, cs:byte_18000A8DC
0x1800033d8  mov     [rsp+78h+var_58], al
0x1800033dc  lea     r9, [rsp+78h+arg_8]
0x1800033e4  lea     rdx, [rsp+78h+var_28]
0x1800033e9  lea     rcx, [rsp+78h+var_48]
0x1800033ee  call    ??$_Insert_nohint@W4_DismReleaseType@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@W4_DismReleaseType@@@std@@@std@@@std@@_N@1@_N$$QEAW4_DismReleaseType@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::_Insert_nohint<_DismReleaseType,std::_Nil>(bool,_DismReleaseType &&,std::_Nil)
0x1800033f3  mov     [rsp+78h+arg_8], 5
0x1800033fe  mov     al, cs:byte_18000A8DC
0x180003404  mov     [rsp+78h+var_58], al
0x180003408  lea     r9, [rsp+78h+arg_8]
0x180003410  lea     rdx, [rsp+78h+var_28]
0x180003415  lea     rcx, [rsp+78h+var_48]
0x18000341a  call    ??$_Insert_nohint@W4_DismReleaseType@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@W4_DismReleaseType@@@std@@@std@@@std@@_N@1@_N$$QEAW4_DismReleaseType@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::_Insert_nohint<_DismReleaseType,std::_Nil>(bool,_DismReleaseType &&,std::_Nil)
0x18000341f  mov     [rsp+78h+arg_8], 6
0x18000342a  mov     al, cs:byte_18000A8DC
0x180003430  mov     [rsp+78h+var_58], al
0x180003434  lea     r9, [rsp+78h+arg_8]
0x18000343c  lea     rdx, [rsp+78h+var_28]
0x180003441  lea     rcx, [rsp+78h+var_48]
0x180003446  call    ??$_Insert_nohint@W4_DismReleaseType@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@W4_DismReleaseType@@@std@@@std@@@std@@_N@1@_N$$QEAW4_DismReleaseType@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::_Insert_nohint<_DismReleaseType,std::_Nil>(bool,_DismReleaseType &&,std::_Nil)
0x18000344b  mov     [rsp+78h+arg_8], 7
0x180003456  mov     al, cs:byte_18000A8DC
0x18000345c  mov     [rsp+78h+var_58], al
0x180003460  lea     r9, [rsp+78h+arg_8]
0x180003468  lea     rdx, [rsp+78h+var_28]
0x18000346d  lea     rcx, [rsp+78h+var_48]
0x180003472  call    ??$_Insert_nohint@W4_DismReleaseType@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@W4_DismReleaseType@@@std@@@std@@@std@@_N@1@_N$$QEAW4_DismReleaseType@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::_Insert_nohint<_DismReleaseType,std::_Nil>(bool,_DismReleaseType &&,std::_Nil)
0x180003477  mov     [rsp+78h+arg_8], 0Ah
0x180003482  mov     al, cs:byte_18000A8DC
0x180003488  mov     [rsp+78h+var_58], al
0x18000348c  lea     r9, [rsp+78h+arg_8]
0x180003494  lea     rdx, [rsp+78h+var_28]
0x180003499  lea     rcx, [rsp+78h+var_48]
0x18000349e  call    ??$_Insert_nohint@W4_DismReleaseType@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@W4_DismReleaseType@@@std@@@std@@@std@@_N@1@_N$$QEAW4_DismReleaseType@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::_Insert_nohint<_DismReleaseType,std::_Nil>(bool,_DismReleaseType &&,std::_Nil)
0x1800034a3  mov     rax, [rsp+78h+var_38]
0x1800034a8  lea     rcx, [rsp+78h+var_38]
0x1800034ad  mov     rax, [rax+8]
0x1800034b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034b6  lea     r8, [rsp+78h+arg_0]
0x1800034be  mov     rdx, rax
0x1800034c1  mov     ecx, [rdi+270h]
0x1800034c7  call    cs:__imp_DismGetPackages
0x1800034cd  mov     esi, eax
0x1800034cf  test    eax, eax
0x1800034d1  js      loc_1800035DC
0x1800034d7  xor     r14d, r14d
0x1800034da  cmp     r14d, [rsp+78h+arg_0]
0x1800034e2  jnb     loc_180003575
0x1800034e8  mov     rax, [rsp+78h+var_38]
0x1800034ed  lea     rcx, [rsp+78h+var_38]
0x1800034f2  mov     rax, [rax+20h]
0x1800034f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034fb  mov     esi, r14d
0x1800034fe  shl     rsi, 5
0x180003502  cmp     dword ptr [rsi+rax+8], 6
0x180003507  jnz     short loc_18000356D
0x180003509  mov     rax, [rsp+78h+var_38]
0x18000350e  lea     rcx, [rsp+78h+var_38]
0x180003513  mov     rax, [rax+20h]
0x180003517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000351c  mov     r9, rax
0x18000351f  mov     r8, [rsp+78h+var_48]
0x180003524  mov     rcx, [r8+8]
0x180003528  mov     rdx, r8
0x18000352b  cmp     byte ptr [rcx+19h], 0
0x18000352f  jnz     short loc_18000354C
0x180003531  mov     eax, [rsi+rax+0Ch]
0x180003535  cmp     [rcx+1Ch], eax
0x180003538  jge     short loc_180003540
0x18000353a  mov     rcx, [rcx+10h]
0x18000353e  jmp     short loc_180003546
0x180003540  mov     rdx, rcx
0x180003543  mov     rcx, [rcx]
0x180003546  cmp     byte ptr [rcx+19h], 0
0x18000354a  jz      short loc_180003535
0x18000354c  cmp     rdx, r8
0x18000354f  jz      short loc_18000355B
0x180003551  mov     eax, [rdx+1Ch]
0x180003554  cmp     [rsi+r9+0Ch], eax
0x180003559  jge     short loc_18000355E
0x18000355b  mov     rdx, r8
0x18000355e  cmp     rdx, r8
0x180003561  jz      short loc_18000356D
0x180003563  add     dword ptr [rdi+220h], 0BEh
0x18000356d  inc     r14d
0x180003570  jmp     loc_1800034DA
0x180003575  mov     eax, [rdi+220h]
0x18000357b  shl     rax, 14h
0x18000357f  mov     [r12], rax
0x180003583  mov     [rdi+228h], rax
0x18000358a  lea     rcx, [rsp+78h+var_48]
0x18000358f  call    ??1?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::~_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>(void)
0x180003594  nop
0x180003595  mov     [rsp+78h+var_38], r15
0x18000359a  mov     rcx, [rsp+78h+var_30]
0x18000359f  test    rcx, rcx
0x1800035a2  jz      short loc_1800035AA
0x1800035a4  call    cs:__imp_DismDelete
0x1800035aa  xor     eax, eax
0x1800035ac  jmp     short loc_1800035FE
0x1800035ae  lea     rcx, [rsp+78h+var_48]
0x1800035b3  call    ??1?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::~_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>(void)
0x1800035b8  nop
0x1800035b9  lea     r15, ??_7?$CAutoDismDelete@PEAU_DismPackage@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismPackage *>::`vftable'
0x1800035c0  mov     [rsp+78h+var_38], r15
0x1800035c5  mov     rcx, [rsp+78h+var_30]
0x1800035ca  test    rcx, rcx
0x1800035cd  jz      short loc_1800035D5
0x1800035cf  call    cs:__imp_DismDelete
0x1800035d5  mov     eax, 8000FFFFh
0x1800035da  jmp     short loc_1800035FE
0x1800035dc  lea     rcx, [rsp+78h+var_48]
0x1800035e1  call    ??1?$_Tree@V?$_Tset_traits@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>::~_Tree<std::_Tset_traits<_DismReleaseType,std::less<_DismReleaseType>,std::allocator<_DismReleaseType>,0>>(void)
0x1800035e6  nop
0x1800035e7  mov     [rsp+78h+var_38], r15
0x1800035ec  mov     rcx, [rsp+78h+var_30]
0x1800035f1  test    rcx, rcx
0x1800035f4  jz      short loc_1800035FC
0x1800035f6  call    cs:__imp_DismDelete
0x1800035fc  mov     eax, esi
0x1800035fe  lea     r11, [rsp+78h+var_18]
0x180003603  mov     rsi, [r11+30h]
0x180003607  mov     rdi, [r11+38h]
0x18000360b  mov     rsp, r11
0x18000360e  pop     r15
0x180003610  pop     r14
0x180003612  pop     r12
0x180003614  retn
```
