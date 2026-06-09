# std::basic_ifstream<char,std::char_traits<char>>::basic_ifstream<char,std::char_traits<char>>(ushort const *,int,int)

- ea: `0x180058210`
- end: `0x18005839a`
- name: `??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEBGHH@Z`
- size: `394`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180058e50`
- `0x180059970`

## callees

- `0x1800580f4`
- `0x180058210`
- `0x18005a03c`
- `0x180071010`

## import_xrefs

- `msvcp_win!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x18005831a`
- `msvcp_win!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x18005831a`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x1800582dd`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x1800582dd`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x180058292`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x180058292`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x180058305`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x180058305`
- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x1800582ad`
- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x180058335`
- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x1800582ad`
- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x180058335`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x180058246`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x180058246`
- `msvcp_win!??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x180058265`
- `msvcp_win!??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x180058265`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x180058380`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x180058380`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall std::ifstream::ifstream(__int64 a1, const unsigned __int16 *a2)
{
  struct _iobuf *v4; // rax
  __int64 v5; // rax
  std::codecvt_base *v6; // rbx
  void (__fastcall ***v7)(_QWORD, __int64); // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v10; // [rsp+28h] [rbp-10h]

  *(_QWORD *)a1 = &std::ifstream::`vbtable';
  std::ios::ios(a1 + 176);
  std::istream::istream(a1, a1 + 16, 0, 0);
  *(_QWORD *)(*(int *)(*(_QWORD *)a1 + 4LL) + a1) = &std::ifstream::`vftable';
  *(_DWORD *)(*(int *)(*(_QWORD *)a1 + 4LL) + a1 - 4) = *(_DWORD *)(*(_QWORD *)a1 + 4LL) - 176;
  std::streambuf::streambuf(a1 + 16);
  *(_QWORD *)(a1 + 16) = &std::filebuf::`vftable';
  *(_BYTE *)(a1 + 140) = 0;
  *(_BYTE *)(a1 + 129) = 0;
  std::streambuf::_Init(a1 + 16);
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 132) = `std::filebuf::_Init'::`2'::_Stinit;
  *(_QWORD *)(a1 + 120) = 0;
  v4 = std::_Fiopen(a2, 1, 64);
  if ( v4 )
  {
    std::filebuf::_Init(a1 + 16, v4, 1);
    v5 = std::streambuf::getloc(a1 + 16, v9);
    v6 = (std::codecvt_base *)std::use_facet<std::codecvt<char,char,_Mbstatet>>(v5);
    if ( std::codecvt_base::always_noconv(v6) )
    {
      *(_QWORD *)(a1 + 120) = 0;
    }
    else
    {
      *(_QWORD *)(a1 + 120) = v6;
      std::streambuf::_Init(a1 + 16);
    }
    if ( v10 )
    {
      v7 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v7 )
        (**v7)(v7, 1);
    }
  }
  else
  {
    std::ios::setstate(a1 + *(int *)(*(_QWORD *)a1 + 4LL), 2);
  }
  return a1;
}

```

## disassembly

```asm
0x180058210  mov     rax, rsp
0x180058213  mov     [rax+10h], rbx
0x180058217  mov     [rax+18h], rsi
0x18005821b  mov     [rax+20h], r9d
0x18005821f  mov     [rax+8], rcx
0x180058223  push    rdi
0x180058224  sub     rsp, 30h
0x180058228  mov     rbx, rdx
0x18005822b  mov     rsi, rcx
0x18005822e  mov     dword ptr [rax+20h], 0
0x180058235  lea     rax, ??_8?$basic_ifstream@DU?$char_traits@D@std@@@std@@7B@; const std::ifstream::`vbtable'
0x18005823c  mov     [rcx], rax
0x18005823f  add     rcx, 0B0h
0x180058246  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x18005824c  nop
0x18005824d  mov     [rsp+38h+arg_18], 1
0x180058255  lea     rdi, [rsi+10h]
0x180058259  xor     r9d, r9d
0x18005825c  xor     r8d, r8d
0x18005825f  mov     rdx, rdi
0x180058262  mov     rcx, rsi
0x180058265  call    cs:__imp_??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z; std::istream::istream(std::streambuf *,bool)
0x18005826b  nop
0x18005826c  mov     rax, [rsi]
0x18005826f  movsxd  rcx, dword ptr [rax+4]
0x180058273  lea     rax, ??_7?$basic_ifstream@DU?$char_traits@D@std@@@std@@6B@; const std::ifstream::`vftable'
0x18005827a  mov     [rcx+rsi], rax
0x18005827e  mov     rax, [rsi]
0x180058281  movsxd  rcx, dword ptr [rax+4]
0x180058285  lea     edx, [rcx-0B0h]
0x18005828b  mov     [rcx+rsi-4], edx
0x18005828f  mov     rcx, rdi
0x180058292  call    cs:__imp_??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::streambuf::streambuf(void)
0x180058298  lea     rax, ??_7?$basic_filebuf@DU?$char_traits@D@std@@@std@@6B@; const std::filebuf::`vftable'
0x18005829f  mov     [rdi], rax
0x1800582a2  mov     byte ptr [rdi+7Ch], 0
0x1800582a6  mov     byte ptr [rdi+71h], 0
0x1800582aa  mov     rcx, rdi
0x1800582ad  call    cs:__imp_?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ; std::streambuf::_Init(void)
0x1800582b3  mov     qword ptr [rdi+80h], 0
0x1800582be  mov     rax, cs:?_Stinit@?1??_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@23@@Z@4U_Mbstatet@@A; _Mbstatet `std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)'::`2'::_Stinit
0x1800582c5  mov     [rdi+74h], rax
0x1800582c9  mov     qword ptr [rdi+68h], 0
0x1800582d1  mov     edx, 1
0x1800582d6  lea     r8d, [rdx+3Fh]
0x1800582da  mov     rcx, rbx
0x1800582dd  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z; std::_Fiopen(ushort const *,int,int)
0x1800582e3  test    rax, rax
0x1800582e6  jz      loc_18005836F
0x1800582ec  mov     r8d, 1
0x1800582f2  mov     rdx, rax
0x1800582f5  mov     rcx, rdi
0x1800582f8  call    ?_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)
0x1800582fd  lea     rdx, [rsp+38h+var_18]
0x180058302  mov     rcx, rdi
0x180058305  call    cs:__imp_?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ; std::streambuf::getloc(void)
0x18005830b  nop
0x18005830c  mov     rcx, rax
0x18005830f  call    ??$use_facet@V?$codecvt@DDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@DDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<char,char,_Mbstatet>>(std::locale const &)
0x180058314  mov     rbx, rax
0x180058317  mov     rcx, rax
0x18005831a  call    cs:__imp_?always_noconv@codecvt_base@std@@QEBA_NXZ; std::codecvt_base::always_noconv(void)
0x180058320  test    al, al
0x180058322  jz      short loc_18005832E
0x180058324  mov     qword ptr [rdi+68h], 0
0x18005832c  jmp     short loc_18005833C
0x18005832e  mov     [rdi+68h], rbx
0x180058332  mov     rcx, rdi
0x180058335  call    cs:__imp_?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ; std::streambuf::_Init(void)
0x18005833b  nop
0x18005833c  mov     rcx, [rsp+38h+var_10]
0x180058341  test    rcx, rcx
0x180058344  jz      short loc_180058387
0x180058346  mov     rax, [rcx]
0x180058349  mov     rax, [rax+10h]
0x18005834d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058352  mov     r8, rax
0x180058355  test    rax, rax
0x180058358  jz      short loc_180058387
0x18005835a  mov     rcx, [rax]
0x18005835d  mov     rax, [rcx]
0x180058360  mov     edx, 1
0x180058365  mov     rcx, r8
0x180058368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005836d  jmp     short loc_180058387
0x18005836f  mov     rax, [rsi]
0x180058372  movsxd  rcx, dword ptr [rax+4]
0x180058376  add     rcx, rsi
0x180058379  xor     r8d, r8d
0x18005837c  lea     edx, [r8+2]
0x180058380  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x180058386  nop
0x180058387  mov     rax, rsi
0x18005838a  mov     rbx, [rsp+38h+arg_8]
0x18005838f  mov     rsi, [rsp+38h+arg_10]
0x180058394  add     rsp, 30h
0x180058398  pop     rdi
0x180058399  retn
```
