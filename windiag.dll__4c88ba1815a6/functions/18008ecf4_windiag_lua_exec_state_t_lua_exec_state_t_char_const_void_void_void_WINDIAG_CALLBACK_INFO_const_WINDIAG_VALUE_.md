# windiag::lua_exec_state_t::lua_exec_state_t(char const *,void *,void *,void (*)(_WINDIAG_CALLBACK_INFO const *,_WINDIAG_VALUE *),void *,void *)

- ea: `0x18008ecf4`
- end: `0x18008ef3a`
- name: `??0lua_exec_state_t@windiag@@QEAA@PEBDPEAX1P6AXPEBU_WINDIAG_CALLBACK_INFO@@PEAU_WINDIAG_VALUE@@@Z11@Z`
- size: `582`
- prototype: `LARGE_INTEGER *__fastcall(LARGE_INTEGER *this, const char *, LARGE_INTEGER, LARGE_INTEGER, LARGE_INTEGER Frequency, LARGE_INTEGER PerformanceCount, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180090780`

## callees

- `0x18000491c`
- `0x18003a52c`
- `0x18003d4b0`
- `0x18003d708`
- `0x18008ecf4`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18008ef19`
- `msvcp_win!_Mtx_unlock` at `0x18008ef19`
- `msvcp_win!_Mtx_lock` at `0x18008ee2f`
- `msvcp_win!_Mtx_lock` at `0x18008ee2f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008ee3e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008ee5f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008ee3e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008ee5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008ed51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008ed51`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18008ed62`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18008ed62`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18008ed94`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18008ed94`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18008edaf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18008edaf`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
LARGE_INTEGER *__fastcall windiag::lua_exec_state_t::lua_exec_state_t(
        LARGE_INTEGER *this,
        const char *a2,
        LARGE_INTEGER a3,
        LARGE_INTEGER a4,
        LARGE_INTEGER Frequency,
        LARGE_INTEGER PerformanceCount,
        void *a7)
{
  size_t v10; // r8
  LONG HighPart; // ecx
  _QWORD *v12; // rax
  void *v13; // rbx
  _QWORD *v14; // rax
  int v15; // esi
  _BYTE *v16; // rcx
  _QWORD *v17; // r14
  _QWORD *v18; // rax
  _QWORD *v20; // [rsp+20h] [rbp-18h] BYREF
  int v21; // [rsp+28h] [rbp-10h]
  DWORD LowPart; // [rsp+2Ch] [rbp-Ch]

  *(_OWORD *)&this->LowPart = 0;
  this[2].QuadPart = 0;
  this[3].QuadPart = 0;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  std::string::_Construct<1,char const *>(this, a2, v10);
  this[4] = a3;
  this[5] = a4;
  this[6] = Frequency;
  this[7] = PerformanceCount;
  this[8].LowPart = GetCurrentThreadId();
  Frequency.QuadPart = 0;
  GetSystemTimePreciseAsFileTime(&Frequency);
  HighPart = Frequency.HighPart;
  this[9].LowPart = Frequency.LowPart;
  this[9].HighPart = HighPart;
  this[10].QuadPart = (LONGLONG)a7;
  this[11].QuadPart = 0;
  this[12].QuadPart = 1000000000;
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  if ( QueryPerformanceFrequency(&Frequency) )
  {
    if ( Frequency.QuadPart > 0 )
    {
      this[12] = Frequency;
      if ( QueryPerformanceCounter(&PerformanceCount) )
        this[11] = PerformanceCount;
    }
  }
  this[13].QuadPart = 0;
  this[14].QuadPart = 0;
  this[15].QuadPart = 0;
  this[16].QuadPart = 0;
  this[17].QuadPart = 0;
  LOBYTE(this[18].LowPart) = 0;
  this[19].QuadPart = 0;
  this[20].QuadPart = 0;
  this[21].QuadPart = 0;
  this[22].QuadPart = 0;
  this[23].QuadPart = 0;
  v12 = operator new(0x10u);
  v12[1] = 0;
  this[19].QuadPart = (LONGLONG)v12;
  *v12 = this + 19;
  this[24].QuadPart = 0;
  this[25].QuadPart = 1000000;
  PerformanceCount.QuadPart = (LONGLONG)&windiag::lua_exec_state_t::exec_states_mtx;
  if ( _Mtx_lock((_Mtx_t)&windiag::lua_exec_state_t::exec_states_mtx) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( dword_1800BE3DC == 0x7FFFFFFF )
  {
    dword_1800BE3DC = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v13 = windiag::lua_exec_state_t::exec_states;
  v14 = (_QWORD *)*((_QWORD *)windiag::lua_exec_state_t::exec_states + 1);
  v15 = 0;
  Frequency.QuadPart = 0;
  v16 = windiag::lua_exec_state_t::exec_states;
  if ( *((_BYTE *)v14 + 25) )
  {
    v17 = v14;
  }
  else
  {
    do
    {
      v17 = v14;
      if ( v14[4] >= (unsigned __int64)this )
      {
        v15 = 1;
        v16 = v14;
        v14 = (_QWORD *)*v14;
      }
      else
      {
        v15 = 0;
        v14 = (_QWORD *)v14[2];
      }
    }
    while ( !*((_BYTE *)v14 + 25) );
  }
  if ( v16[25] || (unsigned __int64)this < *((_QWORD *)v16 + 4) )
  {
    if ( qword_1800BEE38 == 0x666666666666666LL )
      std::_Throw_tree_length_error();
    v18 = operator new(0x28u);
    v18[4] = this;
    *v18 = v13;
    v18[1] = v13;
    v18[2] = v13;
    *((_WORD *)v18 + 12) = 0;
    v20 = v17;
    v21 = v15;
    LowPart = Frequency.LowPart;
    std::_Tree_val<std::_Tree_simple_types<unsigned short>>::_Insert_node(&windiag::lua_exec_state_t::exec_states, &v20);
  }
  _Mtx_unlock((_Mtx_t)&windiag::lua_exec_state_t::exec_states_mtx);
  return this;
}

```

## disassembly

```asm
0x18008ecf4  mov     [rsp-40h+arg_0], rcx
0x18008ecf9  push    rbp
0x18008ecfa  push    rbx
0x18008ecfb  push    rsi
0x18008ecfc  push    rdi
0x18008ecfd  push    r12
0x18008ecff  push    r13
0x18008ed01  push    r14
0x18008ed03  push    r15
0x18008ed05  mov     rbp, rsp
0x18008ed08  sub     rsp, 38h
0x18008ed0c  mov     rbx, r9
0x18008ed0f  mov     rsi, r8
0x18008ed12  mov     rdi, rcx
0x18008ed15  xorps   xmm0, xmm0
0x18008ed18  movups  xmmword ptr [rcx], xmm0
0x18008ed1b  xor     r12d, r12d
0x18008ed1e  mov     [rcx+10h], r12
0x18008ed22  mov     [rcx+18h], r12
0x18008ed26  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008ed2a  inc     r8
0x18008ed2d  cmp     [rdx+r8], r12b
0x18008ed31  jnz     short loc_18008ED2A
0x18008ed33  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18008ed38  nop
0x18008ed39  mov     [rdi+20h], rsi
0x18008ed3d  mov     [rdi+28h], rbx
0x18008ed41  mov     rax, qword ptr [rbp+Frequency]
0x18008ed45  mov     [rdi+30h], rax
0x18008ed49  mov     rax, qword ptr [rbp+PerformanceCount]
0x18008ed4d  mov     [rdi+38h], rax
0x18008ed51  call    cs:__imp_GetCurrentThreadId
0x18008ed57  mov     [rdi+40h], eax
0x18008ed5a  mov     qword ptr [rbp+Frequency], r12
0x18008ed5e  lea     rcx, [rbp+Frequency]
0x18008ed62  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x18008ed68  mov     eax, dword ptr [rbp+Frequency]
0x18008ed6b  mov     ecx, dword ptr [rbp+Frequency+4]
0x18008ed6e  mov     [rdi+48h], eax
0x18008ed71  mov     [rdi+4Ch], ecx
0x18008ed74  mov     rax, [rbp+arg_30]
0x18008ed78  mov     [rdi+50h], rax
0x18008ed7c  mov     [rdi+58h], r12
0x18008ed80  mov     qword ptr [rdi+60h], 3B9ACA00h
0x18008ed88  mov     qword ptr [rbp+Frequency], r12
0x18008ed8c  mov     qword ptr [rbp+PerformanceCount], r12
0x18008ed90  lea     rcx, [rbp+Frequency]; lpFrequency
0x18008ed94  call    cs:__imp_QueryPerformanceFrequency
0x18008ed9a  test    eax, eax
0x18008ed9c  jz      short loc_18008EDC1
0x18008ed9e  mov     rax, qword ptr [rbp+Frequency]
0x18008eda2  test    rax, rax
0x18008eda5  jle     short loc_18008EDC1
0x18008eda7  mov     [rdi+60h], rax
0x18008edab  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18008edaf  call    cs:__imp_QueryPerformanceCounter
0x18008edb5  test    eax, eax
0x18008edb7  jz      short loc_18008EDC1
0x18008edb9  mov     rax, qword ptr [rbp+PerformanceCount]
0x18008edbd  mov     [rdi+58h], rax
0x18008edc1  xor     eax, eax
0x18008edc3  mov     [rdi+68h], rax
0x18008edc7  mov     [rdi+70h], rax
0x18008edcb  mov     [rdi+78h], rax
0x18008edcf  mov     [rdi+80h], rax
0x18008edd6  mov     [rdi+88h], rax
0x18008eddd  mov     [rdi+90h], al
0x18008ede3  lea     rbx, [rdi+98h]
0x18008edea  mov     [rbx], r12
0x18008eded  mov     [rbx+8], r12
0x18008edf1  mov     [rbx+10h], r12
0x18008edf5  mov     [rbx+18h], r12
0x18008edf9  mov     [rbx+20h], r12
0x18008edfd  lea     ecx, [rax+10h]; Size
0x18008ee00  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008ee05  mov     [rax+8], r12
0x18008ee09  mov     [rbx], rax
0x18008ee0c  mov     [rax], rbx
0x18008ee0f  mov     [rdi+0C0h], r12
0x18008ee16  mov     qword ptr [rdi+0C8h], 0F4240h
0x18008ee21  lea     r13, ?exec_states_mtx@lua_exec_state_t@windiag@@0Vmutex@std@@A; std::mutex windiag::lua_exec_state_t::exec_states_mtx
0x18008ee28  mov     qword ptr [rbp+PerformanceCount], r13
0x18008ee2c  mov     rcx, r13; _Mtx_t
0x18008ee2f  call    cs:__imp__Mtx_lock
0x18008ee35  test    eax, eax
0x18008ee37  jz      short loc_18008EE45
0x18008ee39  mov     ecx, 5
0x18008ee3e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18008ee44  int     3; Trap to Debugger
0x18008ee45  mov     eax, cs:dword_1800BE3DC
0x18008ee4b  cmp     eax, 7FFFFFFFh
0x18008ee50  jnz     short loc_18008EE66
0x18008ee52  dec     eax
0x18008ee54  mov     cs:dword_1800BE3DC, eax
0x18008ee5a  mov     ecx, 6
0x18008ee5f  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18008ee65  nop
0x18008ee66  mov     rbx, cs:?exec_states@lua_exec_state_t@windiag@@0V?$set@PEBUlua_exec_state_t@windiag@@U?$less@PEBUlua_exec_state_t@windiag@@@std@@V?$allocator@PEBUlua_exec_state_t@windiag@@@4@@std@@A; std::set<windiag::lua_exec_state_t const *> windiag::lua_exec_state_t::exec_states
0x18008ee6d  mov     rax, [rbx+8]
0x18008ee71  mov     esi, r12d
0x18008ee74  xor     ecx, ecx
0x18008ee76  mov     qword ptr [rbp+Frequency], rcx
0x18008ee7a  mov     rcx, rbx
0x18008ee7d  cmp     [rax+19h], r12b
0x18008ee81  jnz     short loc_18008EEA8
0x18008ee83  mov     r14, rax
0x18008ee86  cmp     [rax+20h], rdi
0x18008ee8a  jnb     short loc_18008EE95
0x18008ee8c  mov     esi, r12d
0x18008ee8f  mov     rax, [rax+10h]
0x18008ee93  jmp     short loc_18008EEA0
0x18008ee95  mov     esi, 1
0x18008ee9a  mov     rcx, rax
0x18008ee9d  mov     rax, [rax]
0x18008eea0  cmp     [rax+19h], r12b
0x18008eea4  jz      short loc_18008EE83
0x18008eea6  jmp     short loc_18008EEAB
0x18008eea8  mov     r14, rax
0x18008eeab  cmp     [rcx+19h], r12b
0x18008eeaf  jnz     short loc_18008EEB7
0x18008eeb1  cmp     rdi, [rcx+20h]
0x18008eeb5  jnb     short loc_18008EF16
0x18008eeb7  mov     rax, 666666666666666h
0x18008eec1  cmp     cs:qword_1800BEE38, rax
0x18008eec8  jz      short loc_18008EF34
0x18008eeca  lea     r15, ?exec_states@lua_exec_state_t@windiag@@0V?$set@PEBUlua_exec_state_t@windiag@@U?$less@PEBUlua_exec_state_t@windiag@@@std@@V?$allocator@PEBUlua_exec_state_t@windiag@@@4@@std@@A; std::set<windiag::lua_exec_state_t const *> windiag::lua_exec_state_t::exec_states
0x18008eed1  mov     [rbp+var_18], r15
0x18008eed5  mov     qword ptr [rbp+var_10], r12
0x18008eed9  mov     ecx, 28h ; '('; Size
0x18008eede  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008eee3  nop
0x18008eee4  mov     [rax+20h], rdi
0x18008eee8  mov     [rax], rbx
0x18008eeeb  mov     [rax+8], rbx
0x18008eeef  mov     [rax+10h], rbx
0x18008eef3  mov     [rax+18h], r12w
0x18008eef8  mov     [rbp+var_18], r14
0x18008eefc  mov     [rbp+var_10], esi
0x18008eeff  mov     rcx, qword ptr [rbp+Frequency]
0x18008ef03  mov     [rbp+var_10+4], ecx
0x18008ef06  mov     r8, rax
0x18008ef09  lea     rdx, [rbp+var_18]
0x18008ef0d  mov     rcx, r15
0x18008ef10  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@G@std@@@std@@QEAAPEAU?$_Tree_node@GPEAX@2@U?$_Tree_id@PEAU?$_Tree_node@GPEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<ushort>>::_Insert_node(std::_Tree_id<std::_Tree_node<ushort,void *> *>,std::_Tree_node<ushort,void *> * const)
0x18008ef15  nop
0x18008ef16  mov     rcx, r13; _Mtx_t
0x18008ef19  call    cs:__imp__Mtx_unlock
0x18008ef1f  nop
0x18008ef20  mov     rax, rdi
0x18008ef23  add     rsp, 38h
0x18008ef27  pop     r15
0x18008ef29  pop     r14
0x18008ef2b  pop     r13
0x18008ef2d  pop     r12
0x18008ef2f  pop     rdi
0x18008ef30  pop     rsi
0x18008ef31  pop     rbx
0x18008ef32  pop     rbp
0x18008ef33  retn
0x18008ef34  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
