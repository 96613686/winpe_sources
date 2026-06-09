# UusComponent::CheckAllCapabilities(std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent>>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::optional<std::filesystem::path>,std::optional<UusVersion>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180035160`
- end: `0x180035608`
- name: `?CheckAllCapabilities@UusComponent@@SA_NAEBV?$map@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@U?$less@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@V?$optional@Vpath@filesystem@std@@@3@V?$optional@VUusVersion@@@3@1@Z`
- size: `1192`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800393d4`

## callees

- `0x180009c38`
- `0x18000f84c`
- `0x18001b030`
- `0x180028728`
- `0x1800293d4`
- `0x180029644`
- `0x180034914`
- `0x180035160`
- `0x18003a910`
- `0x18003b228`
- `0x1800427d0`
- `0x180042bc4`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
char __fastcall UusComponent::CheckAllCapabilities(__int64 ***a1, _BYTE *a2, __int64 a3, __int64 a4, char *a5)
{
  __int64 v5; // r15
  int v7; // r14d
  __int64 v9; // r13
  _QWORD *v10; // rax
  __int64 *j; // rcx
  __int64 *v12; // rbx
  int *v13; // rdi
  int *v14; // r13
  _QWORD *v15; // rsi
  int v16; // r14d
  __int64 *v17; // rax
  _QWORD *v18; // rcx
  __int64 v19; // rax
  __int64 *i; // rax
  char v21; // di
  __int64 *v22; // rbx
  int v23; // esi
  __int64 *k; // rax
  _QWORD *v25; // rbx
  void *v26; // rcx
  __int128 v28; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v29; // [rsp+40h] [rbp-C8h]
  char v30; // [rsp+48h] [rbp-C0h]
  _BYTE *v31; // [rsp+58h] [rbp-B0h]
  char *v32; // [rsp+60h] [rbp-A8h]
  char *v33; // [rsp+68h] [rbp-A0h]
  __int64 v34; // [rsp+70h] [rbp-98h]
  void **v35; // [rsp+78h] [rbp-90h]
  __int64 v36; // [rsp+80h] [rbp-88h]
  _QWORD v37[2]; // [rsp+88h] [rbp-80h] BYREF
  char v38; // [rsp+98h] [rbp-70h]
  _BYTE v39[32]; // [rsp+A0h] [rbp-68h] BYREF
  char v40; // [rsp+C0h] [rbp-48h]
  _BYTE v41[32]; // [rsp+C8h] [rbp-40h] BYREF
  int *v42; // [rsp+E8h] [rbp-20h] BYREF
  int *v43; // [rsp+F0h] [rbp-18h]
  int v44; // [rsp+100h] [rbp-8h]
  __int64 v45; // [rsp+108h] [rbp+0h]
  _BYTE v46[32]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v47[32]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v48[24]; // [rsp+158h] [rbp+50h] BYREF
  int v49; // [rsp+170h] [rbp+68h]
  __int64 v50; // [rsp+178h] [rbp+70h]
  __int64 v51; // [rsp+188h] [rbp+80h]
  __int64 v52; // [rsp+190h] [rbp+88h]
  void *v53[2]; // [rsp+198h] [rbp+90h] BYREF

  v5 = a4;
  v34 = a4;
  v7 = (int)a2;
  v31 = a2;
  v51 = a3;
  v52 = a4;
  v9 = (__int64)a5;
  v32 = a5;
  v53[1] = 0;
  v10 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(32);
  *v10 = v10;
  v10[1] = v10;
  v10[2] = v10;
  *((_WORD *)v10 + 12) = 257;
  v53[0] = v10;
  v12 = **a1;
  if ( !*((_BYTE *)v12 + 25) )
  {
    v33 = v47;
    do
    {
      std::wstring::wstring(v46, v12 + 4);
      std::wstring::wstring(v47, v12 + 8);
      std::vector<enum UusCapability>::vector<enum UusCapability>(v48, v12 + 12);
      v49 = *((_DWORD *)v12 + 30);
      v50 = v12[16];
      std::wstring::wstring(v41, v47);
      std::vector<enum UusCapability>::vector<enum UusCapability>(&v42, v48);
      v44 = v49;
      v45 = v50;
      v13 = v42;
      v14 = v43;
      if ( v42 != v43 )
      {
        v15 = v53[0];
        do
        {
          v16 = *v13;
          v17 = (__int64 *)v15[1];
          *((_QWORD *)&v28 + 1) = v17;
          v29 = 0;
          v18 = v15;
          while ( !*((_BYTE *)v17 + 25) )
          {
            *((_QWORD *)&v28 + 1) = v17;
            if ( *((_DWORD *)v17 + 7) >= v16 )
            {
              LODWORD(v29) = 1;
              v18 = v17;
            }
            else
            {
              LODWORD(v29) = 0;
              v17 += 2;
            }
            v17 = (__int64 *)*v17;
          }
          if ( *((_BYTE *)v18 + 25) || v16 < *((_DWORD *)v18 + 7) )
          {
            if ( v53[1] == (void *)0x7FFFFFFFFFFFFFFLL )
              std::_Throw_tree_length_error();
            v35 = v53;
            v36 = 0;
            v19 = std::_Allocate<16,std::_Default_allocate_traits>(32);
            *(_DWORD *)(v19 + 28) = v16;
            *(_QWORD *)v19 = v15;
            *(_QWORD *)(v19 + 8) = v15;
            *(_QWORD *)(v19 + 16) = v15;
            *(_WORD *)(v19 + 24) = 0;
            v36 = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Insert_node(
              v53,
              (char *)&v28 + 8,
              v19);
            v15 = v53[0];
          }
          ++v13;
        }
        while ( v13 != v14 );
      }
      std::vector<enum UusCapability>::~vector<enum UusCapability>(&v42);
      std::wstring::_Tidy_deallocate(v41);
      std::vector<enum UusCapability>::~vector<enum UusCapability>(v48);
      std::wstring::_Tidy_deallocate(v47);
      std::wstring::_Tidy_deallocate(v46);
      j = (__int64 *)v12[2];
      if ( *((_BYTE *)j + 25) )
      {
        for ( i = (__int64 *)v12[1]; !*((_BYTE *)i + 25) && v12 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v12 = i;
        v12 = i;
      }
      else
      {
        v12 = (__int64 *)v12[2];
        for ( j = (__int64 *)*j; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v12 = j;
      }
    }
    while ( !*((_BYTE *)v12 + 25) );
    v7 = (int)v31;
    v9 = (__int64)v32;
  }
  v33 = (char *)&v28 + 8;
  v30 = 0;
  if ( *(_BYTE *)(v5 + 16) )
  {
    *((_QWORD *)&v28 + 1) = &UusVersion::`vftable';
    v29 = *(_QWORD *)(v5 + 8);
    v30 = 1;
  }
  v32 = (char *)&v28 + 8;
  v31 = v39;
  LOBYTE(j) = 0;
  v40 = 0;
  if ( *(_BYTE *)(a3 + 32) )
  {
    std::wstring::wstring(v39, a3);
    LOBYTE(j) = 1;
    v40 = 1;
  }
  v33 = v39;
  v21 = 1;
  v22 = *(__int64 **)v53[0];
  if ( !*(_BYTE *)(*(_QWORD *)v53[0] + 25LL) )
  {
    do
    {
      v23 = *((_DWORD *)v22 + 7);
      v31 = v37;
      v38 = 0;
      if ( v30 )
      {
        v37[0] = &UusVersion::`vftable';
        v37[1] = v29;
        v38 = 1;
      }
      v35 = (void **)v41;
      LOBYTE(v42) = 0;
      if ( (_BYTE)j )
      {
        std::wstring::wstring(v41, v39);
        LOBYTE(v42) = 1;
      }
      v21 = (unsigned __int8)UusCapabilities::Check((_DWORD)j, v23, v7, (unsigned int)v41, (__int64)v37, v9) != 0
          ? v21
          : 0;
      j = (__int64 *)v22[2];
      if ( *((_BYTE *)j + 25) )
      {
        for ( k = (__int64 *)v22[1]; !*((_BYTE *)k + 25) && v22 == (__int64 *)k[2]; k = (__int64 *)k[1] )
          v22 = k;
        v22 = k;
      }
      else
      {
        v22 = (__int64 *)v22[2];
        for ( j = (__int64 *)*j; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v22 = j;
      }
      LOBYTE(j) = v40;
    }
    while ( !*((_BYTE *)v22 + 25) );
    v5 = v34;
  }
  if ( (_BYTE)j )
    std::wstring::_Tidy_deallocate(v39);
  if ( v30 )
    (**((void (__fastcall ***)(char *, _QWORD))&v28 + 1))((char *)&v28 + 8, 0);
  v25 = (_QWORD *)*((_QWORD *)v53[0] + 1);
  while ( !*((_BYTE *)v25 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<enum UusCapability>>::_Erase_tree<std::allocator<std::_Tree_node<enum UusCapability,void *>>>(
      v53,
      v53,
      v25[2]);
    v26 = v25;
    v25 = (_QWORD *)*v25;
    operator delete(v26);
  }
  operator delete(v53[0]);
  if ( *(_BYTE *)(a3 + 32) )
    std::wstring::_Tidy_deallocate(a3);
  if ( *(_BYTE *)(v5 + 16) )
    (**(void (__fastcall ***)(__int64, _QWORD))v5)(v5, 0);
  return v21;
}

```

## disassembly

```asm
0x180035160  mov     rax, rsp
0x180035163  mov     [rax+8], rbx
0x180035167  mov     [rax+20h], r9
0x18003516b  mov     [rax+18h], r8
0x18003516f  push    rbp
0x180035170  push    rsi
0x180035171  push    rdi
0x180035172  push    r12
0x180035174  push    r13
0x180035176  push    r14
0x180035178  push    r15
0x18003517a  lea     rbp, [rax-0E8h]
0x180035181  sub     rsp, 1B0h
0x180035188  mov     rax, cs:__security_cookie
0x18003518f  xor     rax, rsp
0x180035192  mov     [rbp+0E0h+var_40], rax
0x180035199  mov     r15, r9
0x18003519c  mov     [rsp+1E0h+var_178], r9
0x1800351a1  mov     r12, r8
0x1800351a4  mov     r14, rdx
0x1800351a7  mov     [rsp+1E0h+var_190], rdx
0x1800351ac  mov     rbx, rcx
0x1800351af  mov     [rbp+0E0h+var_60], r8
0x1800351b6  mov     [rbp+0E0h+var_58], r9
0x1800351bd  mov     r13, [rbp+0E0h+arg_20]
0x1800351c4  mov     [rsp+1E0h+var_188], r13
0x1800351c9  xorps   xmm0, xmm0
0x1800351cc  movups  xmmword ptr [rbp+0E0h+var_50], xmm0
0x1800351d3  xor     esi, esi
0x1800351d5  mov     [rbp+0E0h+var_50], rsi
0x1800351dc  mov     [rbp+0E0h+var_50+8], rsi
0x1800351e3  lea     ecx, [rsi+20h]
0x1800351e6  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800351eb  mov     [rax], rax
0x1800351ee  mov     [rax+8], rax
0x1800351f2  mov     [rax+10h], rax
0x1800351f6  mov     word ptr [rax+18h], 101h
0x1800351fc  mov     [rbp+0E0h+var_50], rax
0x180035203  mov     rbx, [rbx]
0x180035206  mov     rbx, [rbx]
0x180035209  cmp     [rbx+19h], sil
0x18003520d  jnz     loc_1800353EF
0x180035213  lea     rax, [rbp+0E0h+var_B0]
0x180035217  mov     [rsp+1E0h+var_180], rax
0x18003521c  lea     rdx, [rbx+20h]
0x180035220  lea     rcx, [rbp+0E0h+var_D0]
0x180035224  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180035229  nop
0x18003522a  lea     rdx, [rbx+40h]
0x18003522e  lea     rcx, [rbp+0E0h+var_B0]
0x180035232  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180035237  nop
0x180035238  lea     rdx, [rbx+60h]
0x18003523c  lea     rcx, [rbp+0E0h+var_90]
0x180035240  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x180035245  mov     eax, [rbx+78h]
0x180035248  mov     [rbp+0E0h+var_78], eax
0x18003524b  mov     rax, [rbx+80h]
0x180035252  mov     [rbp+0E0h+var_70], rax
0x180035256  lea     rdx, [rbp+0E0h+var_B0]
0x18003525a  lea     rcx, [rbp+0E0h+var_120]
0x18003525e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180035263  nop
0x180035264  lea     rdx, [rbp+0E0h+var_90]
0x180035268  lea     rcx, [rbp+0E0h+var_100]
0x18003526c  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x180035271  mov     eax, [rbp+0E0h+var_78]
0x180035274  mov     [rbp+0E0h+var_E8], eax
0x180035277  mov     rax, [rbp+0E0h+var_70]
0x18003527b  mov     [rbp+0E0h+var_E0], rax
0x18003527f  mov     rdi, [rbp+0E0h+var_100]
0x180035283  mov     r13, [rbp+0E0h+var_F8]
0x180035287  cmp     rdi, r13
0x18003528a  jz      loc_18003536A
0x180035290  mov     rsi, [rbp+0E0h+var_50]
0x180035297  xor     edx, edx
0x180035299  mov     r14d, [rdi]
0x18003529c  mov     rax, [rsi+8]
0x1800352a0  mov     qword ptr [rsp+1E0h+var_1B8+8], rax
0x1800352a5  mov     [rsp+1E0h+var_1A8], 0
0x1800352ae  mov     rcx, rsi
0x1800352b1  jmp     short loc_1800352D6
0x1800352b3  mov     qword ptr [rsp+1E0h+var_1B8+8], rax
0x1800352b8  cmp     [rax+1Ch], r14d
0x1800352bc  jge     short loc_1800352C8
0x1800352be  mov     dword ptr [rsp+1E0h+var_1A8], edx
0x1800352c2  add     rax, 10h
0x1800352c6  jmp     short loc_1800352D3
0x1800352c8  mov     dword ptr [rsp+1E0h+var_1A8], 1
0x1800352d0  mov     rcx, rax
0x1800352d3  mov     rax, [rax]
0x1800352d6  cmp     [rax+19h], dl
0x1800352d9  jz      short loc_1800352B3
0x1800352db  cmp     [rcx+19h], dl
0x1800352de  jnz     short loc_1800352E6
0x1800352e0  cmp     r14d, [rcx+1Ch]
0x1800352e4  jge     short loc_18003535B
0x1800352e6  mov     rax, 7FFFFFFFFFFFFFFh
0x1800352f0  cmp     [rbp+0E0h+var_50+8], rax
0x1800352f7  jz      loc_180035602
0x1800352fd  lea     rax, [rbp+0E0h+var_50]
0x180035304  mov     [rsp+1E0h+var_170], rax
0x180035309  mov     [rsp+1E0h+var_168], rdx
0x18003530e  mov     ecx, 20h ; ' '
0x180035313  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180035318  nop
0x180035319  mov     [rax+1Ch], r14d
0x18003531d  mov     [rax], rsi
0x180035320  mov     [rax+8], rsi
0x180035324  mov     [rax+10h], rsi
0x180035328  xor     edx, edx
0x18003532a  mov     [rax+18h], dx
0x18003532e  mov     [rsp+1E0h+var_168], rdx
0x180035333  movups  xmm0, [rsp+1E0h+var_1B8+8]
0x180035338  movdqu  [rsp+1E0h+var_1B8+8], xmm0
0x18003533e  mov     r8, rax
0x180035341  lea     rdx, [rsp+1E0h+var_1B8+8]
0x180035346  lea     rcx, [rbp+0E0h+var_50]
0x18003534d  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *>,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> * const)
0x180035352  mov     rsi, [rbp+0E0h+var_50]
0x180035359  xor     edx, edx
0x18003535b  add     rdi, 4
0x18003535f  cmp     rdi, r13
0x180035362  jnz     loc_180035299
0x180035368  xor     esi, esi
0x18003536a  lea     rcx, [rbp+0E0h+var_100]
0x18003536e  call    ??1?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@XZ; std::vector<UusCapability>::~vector<UusCapability>(void)
0x180035373  lea     rcx, [rbp+0E0h+var_120]
0x180035377  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003537c  nop
0x18003537d  lea     rcx, [rbp+0E0h+var_90]
0x180035381  call    ??1?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@XZ; std::vector<UusCapability>::~vector<UusCapability>(void)
0x180035386  lea     rcx, [rbp+0E0h+var_B0]
0x18003538a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003538f  lea     rcx, [rbp+0E0h+var_D0]
0x180035393  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035398  mov     rcx, [rbx+10h]
0x18003539c  cmp     [rcx+19h], sil
0x1800353a0  jz      short loc_1800353C0
0x1800353a2  mov     rax, [rbx+8]
0x1800353a6  jmp     short loc_1800353B5
0x1800353a8  cmp     rbx, [rax+10h]
0x1800353ac  jnz     short loc_1800353BB
0x1800353ae  mov     rbx, rax
0x1800353b1  mov     rax, [rax+8]
0x1800353b5  cmp     [rax+19h], sil
0x1800353b9  jz      short loc_1800353A8
0x1800353bb  mov     rbx, rax
0x1800353be  jmp     short loc_1800353DB
0x1800353c0  mov     rbx, rcx
0x1800353c3  mov     rcx, [rcx]
0x1800353c6  cmp     [rcx+19h], sil
0x1800353ca  jnz     short loc_1800353DB
0x1800353cc  mov     rbx, rcx
0x1800353cf  mov     rax, [rcx]
0x1800353d2  mov     rcx, rax
0x1800353d5  cmp     [rax+19h], sil
0x1800353d9  jz      short loc_1800353CC
0x1800353db  cmp     [rbx+19h], sil
0x1800353df  jz      loc_18003521C
0x1800353e5  mov     r14, [rsp+1E0h+var_190]
0x1800353ea  mov     r13, [rsp+1E0h+var_188]
0x1800353ef  lea     rax, [rsp+1E0h+var_1B8+8]
0x1800353f4  mov     [rsp+1E0h+var_180], rax
0x1800353f9  mov     [rsp+1E0h+var_1A0], sil
0x1800353fe  lea     rax, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x180035405  cmp     [r15+10h], sil
0x180035409  jz      short loc_18003541E
0x18003540b  mov     qword ptr [rsp+1E0h+var_1B8+8], rax
0x180035410  mov     rax, [r15+8]
0x180035414  mov     [rsp+1E0h+var_1A8], rax
0x180035419  mov     [rsp+1E0h+var_1A0], 1
0x18003541e  lea     rax, [rsp+1E0h+var_1B8+8]
0x180035423  mov     [rsp+1E0h+var_188], rax
0x180035428  lea     rax, [rbp+0E0h+var_148]
0x18003542c  mov     [rsp+1E0h+var_190], rax
0x180035431  mov     cl, sil
0x180035434  mov     [rbp+0E0h+var_128], cl
0x180035437  cmp     [r12+20h], sil
0x18003543c  jz      short loc_18003544F
0x18003543e  mov     rdx, r12
0x180035441  lea     rcx, [rbp+0E0h+var_148]
0x180035445  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003544a  mov     cl, 1
0x18003544c  mov     [rbp+0E0h+var_128], cl
0x18003544f  lea     rax, [rbp+0E0h+var_148]
0x180035453  mov     [rsp+1E0h+var_180], rax
0x180035458  mov     dil, 1
0x18003545b  mov     rbx, [rbp+0E0h+var_50]
0x180035462  mov     rbx, [rbx]
0x180035465  cmp     [rbx+19h], sil
0x180035469  jnz     loc_180035539
0x18003546f  lea     r15, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x180035476  mov     esi, [rbx+1Ch]
0x180035479  lea     rax, [rbp+0E0h+var_160]
0x18003547d  mov     [rsp+1E0h+var_190], rax
0x180035482  xor     edx, edx
0x180035484  mov     [rbp+0E0h+var_150], dl
0x180035487  cmp     [rsp+1E0h+var_1A0], dl
0x18003548b  jz      short loc_18003549E
0x18003548d  mov     [rbp+0E0h+var_160], r15
0x180035491  mov     rax, [rsp+1E0h+var_1A8]
0x180035496  mov     [rbp+0E0h+var_158], rax
0x18003549a  mov     [rbp+0E0h+var_150], 1
0x18003549e  lea     rax, [rbp+0E0h+var_120]
0x1800354a2  mov     [rsp+1E0h+var_170], rax
0x1800354a7  mov     byte ptr [rbp+0E0h+var_100], dl
0x1800354aa  test    cl, cl
0x1800354ac  jz      short loc_1800354BF
0x1800354ae  lea     rdx, [rbp+0E0h+var_148]
0x1800354b2  lea     rcx, [rbp+0E0h+var_120]
0x1800354b6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800354bb  mov     byte ptr [rbp+0E0h+var_100], 1
0x1800354bf  mov     qword ptr [rsp+1E0h+var_1B8], r13
0x1800354c4  lea     rax, [rbp+0E0h+var_160]
0x1800354c8  mov     [rsp+1E0h+var_1C0], rax
0x1800354cd  lea     r9, [rbp+0E0h+var_120]
0x1800354d1  mov     r8, r14
0x1800354d4  mov     edx, esi
0x1800354d6  call    ?Check@UusCapabilities@@QEAA_NW4UusCapability@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@Vpath@filesystem@std@@@4@V?$optional@VUusVersion@@@4@1@Z; UusCapabilities::Check(UusCapability,std::wstring const &,std::optional<std::filesystem::path>,std::optional<UusVersion>,std::wstring const &)
0x1800354db  neg     al
0x1800354dd  sbb     cl, cl
0x1800354df  and     dil, cl
0x1800354e2  mov     rcx, [rbx+10h]
0x1800354e6  xor     esi, esi
0x1800354e8  cmp     [rcx+19h], sil
0x1800354ec  jz      short loc_18003550C
0x1800354ee  mov     rax, [rbx+8]
0x1800354f2  jmp     short loc_180035501
0x1800354f4  cmp     rbx, [rax+10h]
0x1800354f8  jnz     short loc_180035507
0x1800354fa  mov     rbx, rax
0x1800354fd  mov     rax, [rax+8]
0x180035501  cmp     [rax+19h], sil
0x180035505  jz      short loc_1800354F4
0x180035507  mov     rbx, rax
0x18003550a  jmp     short loc_180035527
0x18003550c  mov     rbx, rcx
0x18003550f  mov     rcx, [rcx]
0x180035512  cmp     [rcx+19h], sil
0x180035516  jnz     short loc_180035527
0x180035518  mov     rbx, rcx
0x18003551b  mov     rax, [rcx]
0x18003551e  mov     rcx, rax
0x180035521  cmp     [rax+19h], sil
0x180035525  jz      short loc_180035518
0x180035527  mov     cl, [rbp+0E0h+var_128]
0x18003552a  cmp     [rbx+19h], sil
0x18003552e  jz      loc_180035476
0x180035534  mov     r15, [rsp+1E0h+var_178]
0x180035539  test    cl, cl
0x18003553b  jz      short loc_180035547
0x18003553d  lea     rcx, [rbp+0E0h+var_148]
0x180035541  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035546  nop
0x180035547  cmp     [rsp+1E0h+var_1A0], sil
0x18003554c  jz      short loc_180035563
0x18003554e  mov     rax, qword ptr [rsp+1E0h+var_1B8+8]
0x180035553  xor     edx, edx
0x180035555  lea     rcx, [rsp+1E0h+var_1B8+8]
0x18003555a  mov     rax, [rax]
0x18003555d  call    _guard_dispatch_icall
0x180035562  nop
0x180035563  mov     rax, [rbp+0E0h+var_50]
0x18003556a  mov     rbx, [rax+8]
0x18003556e  jmp     short loc_180035597
0x180035570  mov     r8, [rbx+10h]
0x180035574  lea     rdx, [rbp+0E0h+var_50]
0x18003557b  lea     rcx, [rbp+0E0h+var_50]
0x180035582  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@W4UusCapability@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@W4UusCapability@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@W4UusCapability@@PEAX@std@@@1@PEAU?$_Tree_node@W4UusCapability@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<UusCapability>>::_Erase_tree<std::allocator<std::_Tree_node<UusCapability,void *>>>(std::allocator<std::_Tree_node<UusCapability,void *>> &,std::_Tree_node<UusCapability,void *> *)
0x180035587  mov     rcx, rbx; void *
0x18003558a  mov     rbx, [rbx]
0x18003558d  mov     edx, 20h ; ' '; unsigned __int64
0x180035592  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180035597  cmp     [rbx+19h], sil
0x18003559b  jz      short loc_180035570
0x18003559d  mov     edx, 20h ; ' '; unsigned __int64
0x1800355a2  mov     rcx, [rbp+0E0h+var_50]; void *
0x1800355a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800355ae  nop
0x1800355af  cmp     [r12+20h], sil
0x1800355b4  jz      short loc_1800355BF
0x1800355b6  mov     rcx, r12
0x1800355b9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800355be  nop
0x1800355bf  cmp     [r15+10h], sil
0x1800355c3  jz      short loc_1800355D5
0x1800355c5  mov     rdx, [r15]
0x1800355c8  mov     rax, [rdx]
0x1800355cb  xor     edx, edx
0x1800355cd  mov     rcx, r15
0x1800355d0  call    _guard_dispatch_icall
0x1800355d5  mov     al, dil
0x1800355d8  mov     rcx, [rbp+0E0h+var_40]
0x1800355df  xor     rcx, rsp; StackCookie
0x1800355e2  call    __security_check_cookie
0x1800355e7  mov     rbx, [rsp+1E0h+arg_0]
0x1800355ef  add     rsp, 1B0h
0x1800355f6  pop     r15
0x1800355f8  pop     r14
  ... truncated ...
```
