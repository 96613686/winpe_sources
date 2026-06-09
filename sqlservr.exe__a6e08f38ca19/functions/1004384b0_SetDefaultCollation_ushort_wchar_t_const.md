# SetDefaultCollation(ushort,wchar_t const *)

- ea: `0x1004384b0`
- end: `0x10043894b`
- name: `?SetDefaultCollation@@YAXGPEB_W@Z`
- size: `1179`
- prototype: `void __fastcall(unsigned __int16, const wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1004369a0`

## callees

- `0x100401580`
- `0x1004384b0`
- `0x100439960`
- `0x100439c60`
- `0x100439ec0`
- `0x100440460`
- `0x10045283c`
- `0x100452b78`
- `0x100452be0`

## import_xrefs

- `sqlmin!?RecollateServer@@YAXKVContextHandle@@@Z` at `0x1004388d1`
- `sqlmin!?RecollateServer@@YAXKVContextHandle@@@Z` at `0x1004388d1`
- `sqlTsEs!?FResolveCollation@@YAHPEB_WHPEAK@Z` at `0x1004387a7`
- `sqlTsEs!?FResolveCollation@@YAHPEB_WHPEAK@Z` at `0x1004387a7`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x1004387d8`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x1004387d8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100438810`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100438852`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100438882`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1004388c4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100438810`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100438852`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100438882`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1004388c4`
- `sqldk!?WaitForDone@SOS_Task@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z` at `0x100438827`
- `sqldk!?WaitForDone@SOS_Task@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z` at `0x100438899`
- `sqldk!?WaitForDone@SOS_Task@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z` at `0x100438827`
- `sqldk!?WaitForDone@SOS_Task@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z` at `0x100438899`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10043890f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10043890f`
- `sqldk!??2@YAPEAX_K@Z` at `0x1004385fb`
- `sqldk!??2@YAPEAX_K@Z` at `0x100438688`
- `sqldk!??2@YAPEAX_K@Z` at `0x1004385fb`
- `sqldk!??2@YAPEAX_K@Z` at `0x100438688`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x1004387d1`
- `MSVCP140!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1004388e0`
- `MSVCP140!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1004388e0`

## string_xrefs

- `0x100438876`: `g_taskInitSqlAgentUser != nullptr`
- `0x100438804`: `g_taskInitCrossPlatTelemetryAndClustering != nullptr`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall SetDefaultCollation(unsigned __int16 a1, const wchar_t *a2)
{
  _QWORD *v4; // rax
  __int16 *v5; // rdi
  __int64 v6; // r15
  _QWORD *v7; // r12
  __int64 v8; // rax
  _OWORD *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // r8
  char v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rdi
  unsigned int v16; // edi
  struct SOS_Task *v17; // rcx
  struct SOS_Task *v18; // rcx
  unsigned int v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v20; // [rsp+38h] [rbp-C8h]
  _OWORD *v21; // [rsp+40h] [rbp-C0h]
  int v22; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h]
  __int64 v24; // [rsp+58h] [rbp-A8h]
  __int64 v25; // [rsp+60h] [rbp-A0h]
  __int64 v26; // [rsp+68h] [rbp-98h]
  __int64 v27; // [rsp+70h] [rbp-90h]
  __int128 v28; // [rsp+78h] [rbp-88h]
  __int128 v29; // [rsp+90h] [rbp-70h] BYREF
  __int64 v30; // [rsp+B0h] [rbp-50h]
  _BYTE v31[24]; // [rsp+B8h] [rbp-48h] BYREF
  __int16 v32; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v33; // [rsp+D8h] [rbp-28h]
  __int16 v34; // [rsp+E0h] [rbp-20h]
  const wchar_t *v35; // [rsp+E8h] [rbp-18h]
  __int16 v36; // [rsp+F0h] [rbp-10h]
  const wchar_t *v37; // [rsp+F8h] [rbp-8h]
  __int16 v38; // [rsp+100h] [rbp+0h]
  const wchar_t *v39; // [rsp+108h] [rbp+8h]
  __int16 v40; // [rsp+110h] [rbp+10h]
  const wchar_t *v41; // [rsp+118h] [rbp+18h]
  __int16 v42; // [rsp+120h] [rbp+20h]
  const wchar_t *v43; // [rsp+128h] [rbp+28h]
  __int16 v44; // [rsp+130h] [rbp+30h]
  const wchar_t *v45; // [rsp+138h] [rbp+38h]
  __int16 v46; // [rsp+140h] [rbp+40h]
  const wchar_t *v47; // [rsp+148h] [rbp+48h]
  __int16 v48; // [rsp+150h] [rbp+50h]
  const wchar_t *v49; // [rsp+158h] [rbp+58h]
  __int16 v50; // [rsp+160h] [rbp+60h]
  const wchar_t *v51; // [rsp+168h] [rbp+68h]
  __int64 v52; // [rsp+170h] [rbp+70h] BYREF

  v27 = -2;
  if ( dword_1004D48A8 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&dword_1004D48A8);
    if ( dword_1004D48A8 == -1 )
    {
      v32 = 2052;
      v33 = L"Chinese_PRC_CI_AS";
      v34 = 1028;
      v35 = L"Chinese_Taiwan_Stroke_CI_AS";
      v36 = 1031;
      v37 = L"Latin1_General_CI_AS";
      v38 = 3082;
      v39 = L"Modern_Spanish_CI_AS";
      v40 = 1036;
      v41 = L"French_CI_AS";
      v42 = 1040;
      v43 = L"Latin1_General_CI_AS";
      v44 = 1041;
      v45 = L"Japanese_CI_AS";
      v46 = 1042;
      v47 = L"Korean_Wansung_CI_AS";
      v48 = 1046;
      v49 = L"Latin1_General_CI_AS";
      v50 = 1049;
      v51 = L"Cyrillic_General_CI_AS";
      qword_1004D48B0 = 0;
      qword_1004D48B8 = 0;
      _mm_lfence();
      v4 = operator new(0x30u);
      *v4 = v4;
      v4[1] = v4;
      v4[2] = v4;
      *((_WORD *)v4 + 12) = 257;
      qword_1004D48B0 = (__int64)v4;
      v5 = &v32;
      v6 = (__int64)v4;
      v7 = v4;
      do
      {
        v8 = std::_Tree<std::_Tmap_traits<unsigned short,wchar_t const *,std::less<unsigned short>,std::allocator<std::pair<unsigned short const,wchar_t const *>>,0>>::_Find_hint<unsigned short>(
               &qword_1004D48B0,
               v31,
               v7,
               v5);
        v28 = *(_OWORD *)v8;
        v30 = *(_QWORD *)(v8 + 16);
        if ( !(_BYTE)v30 )
        {
          if ( qword_1004D48B8 == 0x555555555555555LL )
            std::_Throw_tree_length_error();
          v20 = &qword_1004D48B0;
          _mm_lfence();
          v9 = operator new(0x30u);
          v21 = v9;
          v9[2] = *(_OWORD *)v5;
          *(_QWORD *)v9 = v6;
          *((_QWORD *)v9 + 1) = v6;
          *((_QWORD *)v9 + 2) = v6;
          *((_WORD *)v9 + 12) = 0;
          v21 = 0;
          v29 = v28;
          std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const,wchar_t const *>>>::_Insert_node(
            &qword_1004D48B0,
            &v29,
            v9);
          v6 = qword_1004D48B0;
        }
        v5 += 8;
      }
      while ( v5 != (__int16 *)&v52 );
      atexit(SetDefaultCollation_::_2_::_dynamic_atexit_destructor_for__x_defaultCollations__);
      Init_thread_footer(&dword_1004D48A8);
    }
  }
  if ( a2 )
    goto LABEL_26;
  v10 = qword_1004D48B0;
  v11 = *(_QWORD *)(qword_1004D48B0 + 8);
  v12 = qword_1004D48B0;
  v13 = *(_BYTE *)(v11 + 25);
  if ( !v13 )
  {
    v14 = *(_QWORD *)(qword_1004D48B0 + 8);
    do
    {
      if ( *(_WORD *)(v14 + 32) >= a1 )
      {
        v12 = v14;
        v14 = *(_QWORD *)v14;
      }
      else
      {
        v14 = *(_QWORD *)(v14 + 16);
      }
    }
    while ( !*(_BYTE *)(v14 + 25) );
  }
  if ( !*(_BYTE *)(v12 + 25) && a1 >= *(_WORD *)(v12 + 32) )
  {
    if ( !v13 )
    {
      do
      {
        if ( *(_WORD *)(v11 + 32) >= a1 )
        {
          v10 = v11;
          v11 = *(_QWORD *)v11;
        }
        else
        {
          v11 = *(_QWORD *)(v11 + 16);
        }
      }
      while ( !*(_BYTE *)(v11 + 25) );
    }
    if ( *(_BYTE *)(v10 + 25) || a1 < *(_WORD *)(v10 + 32) )
    {
      std::_Xout_of_range("invalid map<K, T> key");
      __debugbreak();
    }
    a2 = *(const wchar_t **)(v10 + 40);
LABEL_26:
    v15 = -1;
    do
      ++v15;
    while ( a2[v15] );
    v16 = 2 * v15;
    if ( FResolveCollation(a2, v16, &v19) )
    {
      v22 = 4195111;
      v23 = 0;
      v25 = 0;
      v24 = 0;
      v26 = 0;
      if ( OsInfo::IsXPlatInstance(SOS_OS_OsInfo) )
      {
        v17 = g_taskInitCrossPlatTelemetryAndClustering;
        if ( !g_taskInitCrossPlatTelemetryAndClustering )
        {
          utassert_fail(1u, "g_taskInitCrossPlatTelemetryAndClustering != nullptr", "setup.cpp", 790, 0);
          v17 = g_taskInitCrossPlatTelemetryAndClustering;
        }
        if ( (unsigned int)SOS_Task::WaitForDone(v17, 0xFFFFFFFFLL, &v22) == 0x80000000 )
          utassert_fail(1u, "result != SOS_FAIL", "setup.cpp", 793, 0);
        v18 = g_taskInitSqlAgentUser;
        if ( !g_taskInitSqlAgentUser )
        {
          utassert_fail(1u, "g_taskInitSqlAgentUser != nullptr", "setup.cpp", 796, 0);
          v18 = g_taskInitSqlAgentUser;
        }
        if ( (unsigned int)SOS_Task::WaitForDone(v18, 0xFFFFFFFFLL, &v22) == 0x80000000 )
          utassert_fail(1u, "result != SOS_FAIL", "setup.cpp", 799, 0);
      }
      RecollateServer(v19, 0);
    }
    else
    {
      WriteConsoleMessage(0xC327u, v16, a2);
      ex_raise(4, 48, 16, 3, v16, a2);
    }
  }
}

```

## disassembly

```asm
0x1004384b0  mov     rax, rsp
0x1004384b3  push    rbp
0x1004384b4  push    r12
0x1004384b6  push    r13
0x1004384b8  push    r14
0x1004384ba  push    r15
0x1004384bc  lea     rbp, [rsp-80h]
0x1004384c1  sub     rsp, 180h
0x1004384c8  mov     [rsp+1A0h+var_130], 0FFFFFFFFFFFFFFFEh
0x1004384d1  mov     [rax+8], rbx
0x1004384d5  mov     [rax+18h], rsi
0x1004384d9  mov     [rax+20h], rdi
0x1004384dd  mov     rax, cs:__security_cookie
0x1004384e4  xor     rax, rsp
0x1004384e7  mov     [rbp+0A0h+var_30], rax
0x1004384eb  mov     r14, rdx
0x1004384ee  movzx   esi, cx
0x1004384f1  mov     rax, gs:58h
0x1004384fa  mov     ecx, 4
0x1004384ff  mov     r8, [rax]
0x100438502  xor     ebx, ebx
0x100438504  mov     eax, [rcx+r8]
0x100438508  cmp     cs:dword_1004D48A8, eax
0x10043850e  jle     loc_1004386F9
0x100438514  lea     rcx, dword_1004D48A8
0x10043851b  call    _Init_thread_header
0x100438520  cmp     cs:dword_1004D48A8, 0FFFFFFFFh
0x100438527  jnz     loc_1004386F9
0x10043852d  mov     eax, 804h
0x100438532  mov     [rbp+0A0h+var_D0], ax
0x100438536  lea     rax, aChinesePrcCiAs; "Chinese_PRC_CI_AS"
0x10043853d  mov     [rbp+0A0h+var_C8], rax
0x100438541  mov     eax, 404h
0x100438546  mov     [rbp+0A0h+var_C0], ax
0x10043854a  lea     rax, aChineseTaiwanS; "Chinese_Taiwan_Stroke_CI_AS"
0x100438551  mov     [rbp+0A0h+var_B8], rax
0x100438555  mov     eax, 407h
0x10043855a  mov     [rbp+0A0h+var_B0], ax
0x10043855e  lea     rcx, aLatin1GeneralC; "Latin1_General_CI_AS"
0x100438565  mov     [rbp+0A0h+var_A8], rcx
0x100438569  mov     eax, 0C0Ah
0x10043856e  mov     [rbp+0A0h+var_A0], ax
0x100438572  lea     rax, aModernSpanishC; "Modern_Spanish_CI_AS"
0x100438579  mov     [rbp+0A0h+var_98], rax
0x10043857d  mov     eax, 40Ch
0x100438582  mov     [rbp+0A0h+var_90], ax
0x100438586  lea     rax, aFrenchCiAs; "French_CI_AS"
0x10043858d  mov     [rbp+0A0h+var_88], rax
0x100438591  mov     eax, 410h
0x100438596  mov     [rbp+0A0h+var_80], ax
0x10043859a  mov     [rbp+0A0h+var_78], rcx
0x10043859e  mov     eax, 411h
0x1004385a3  mov     [rbp+0A0h+var_70], ax
0x1004385a7  lea     rax, aJapaneseCiAs; "Japanese_CI_AS"
0x1004385ae  mov     [rbp+0A0h+var_68], rax
0x1004385b2  mov     eax, 412h
0x1004385b7  mov     [rbp+0A0h+var_60], ax
0x1004385bb  lea     rax, aKoreanWansungC; "Korean_Wansung_CI_AS"
0x1004385c2  mov     [rbp+0A0h+var_58], rax
0x1004385c6  mov     eax, 416h
0x1004385cb  mov     [rbp+0A0h+var_50], ax
0x1004385cf  mov     [rbp+0A0h+var_48], rcx
0x1004385d3  mov     eax, 419h
0x1004385d8  mov     [rbp+0A0h+var_40], ax
0x1004385dc  lea     rax, aCyrillicGenera; "Cyrillic_General_CI_AS"
0x1004385e3  mov     [rbp+0A0h+var_38], rax
0x1004385e7  mov     cs:qword_1004D48B0, rbx
0x1004385ee  mov     cs:qword_1004D48B8, rbx
0x1004385f5  lfence
0x1004385f8  lea     ecx, [rbx+30h]
0x1004385fb  call    cs:__imp_??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x100438601  mov     [rax], rax
0x100438604  mov     [rax+8], rax
0x100438608  mov     [rax+10h], rax
0x10043860c  mov     word ptr [rax+18h], 101h
0x100438612  mov     cs:qword_1004D48B0, rax
0x100438619  lea     rdi, [rbp+0A0h+var_D0]
0x10043861d  mov     r15, cs:qword_1004D48B0
0x100438624  mov     r12, r15
0x100438627  lea     r13, qword_1004D48B0
0x10043862e  xchg    ax, ax
0x100438630  mov     r9, rdi
0x100438633  mov     r8, r12
0x100438636  lea     rdx, [rbp+0A0h+var_E8]
0x10043863a  mov     rcx, r13
0x10043863d  call    ??$_Find_hint@G@?$_Tree@V?$_Tmap_traits@GPEB_WU?$less@G@std@@V?$allocator@U?$pair@$$CBGPEB_W@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_hint_result@PEAU?$_Tree_node@U?$pair@$$CBGPEB_W@std@@PEAX@std@@@1@QEAU?$_Tree_node@U?$pair@$$CBGPEB_W@std@@PEAX@1@AEBG@Z; std::_Tree<std::_Tmap_traits<ushort,wchar_t const *,std::less<ushort>,std::allocator<std::pair<ushort const,wchar_t const *>>,0>>::_Find_hint<ushort>(std::_Tree_node<std::pair<ushort const,wchar_t const *>,void *> * const,ushort const &)
0x100438642  movups  xmm0, xmmword ptr [rax]
0x100438645  movups  [rsp+1A0h+var_128], xmm0
0x10043864a  movsd   xmm0, qword ptr [rax+10h]
0x10043864f  movsd   [rbp+0A0h+var_F0], xmm0
0x100438654  cmp     byte ptr [rbp+0A0h+var_F0], 0
0x100438658  jnz     short loc_1004386CF
0x10043865a  mov     rax, 555555555555555h
0x100438664  cmp     cs:qword_1004D48B8, rax
0x10043866b  jz      loc_100438942
0x100438671  mov     [rsp+1A0h+var_168], r13
0x100438676  mov     [rsp+1A0h+var_160], rbx
0x10043867b  mov     [rsp+1A0h+var_160], rbx
0x100438680  lfence
0x100438683  mov     ecx, 30h ; '0'
0x100438688  call    cs:__imp_??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x10043868e  mov     [rsp+1A0h+var_160], rax
0x100438693  movups  xmm0, xmmword ptr [rdi]
0x100438696  movups  xmmword ptr [rax+20h], xmm0
0x10043869a  mov     [rax], r15
0x10043869d  mov     [rax+8], r15
0x1004386a1  mov     [rax+10h], r15
0x1004386a5  mov     word ptr [rax+18h], 0
0x1004386ab  mov     [rsp+1A0h+var_160], rbx
0x1004386b0  movups  xmm0, [rsp+1A0h+var_128]
0x1004386b5  movaps  [rbp+0A0h+var_110], xmm0
0x1004386b9  mov     r8, rax
0x1004386bc  lea     rdx, [rbp+0A0h+var_110]
0x1004386c0  mov     rcx, r13
0x1004386c3  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBGPEB_W@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBGPEB_W@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBGPEB_W@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const,wchar_t const *>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ushort const,wchar_t const *>,void *> *>,std::_Tree_node<std::pair<ushort const,wchar_t const *>,void *> * const)
0x1004386c8  mov     r15, cs:qword_1004D48B0
0x1004386cf  add     rdi, 10h
0x1004386d3  lea     rax, [rbp+0A0h+var_30]
0x1004386d7  cmp     rdi, rax
0x1004386da  jnz     loc_100438630
0x1004386e0  lea     rcx, _SetDefaultCollation____2____dynamic_atexit_destructor_for__x_defaultCollations__; void (__cdecl *)()
0x1004386e7  call    atexit
0x1004386ec  nop
0x1004386ed  lea     rcx, dword_1004D48A8
0x1004386f4  call    _Init_thread_footer
0x1004386f9  test    r14, r14
0x1004386fc  jnz     loc_100438783
0x100438702  mov     rdx, cs:qword_1004D48B0
0x100438709  mov     rax, [rdx+8]
0x10043870d  mov     r8, rdx
0x100438710  movzx   r9d, byte ptr [rax+19h]
0x100438715  test    r9b, r9b
0x100438718  jnz     short loc_100438738
0x10043871a  mov     rcx, rax
0x10043871d  nop     dword ptr [rax]
0x100438720  cmp     [rcx+20h], si
0x100438724  jnb     short loc_10043872C
0x100438726  mov     rcx, [rcx+10h]
0x10043872a  jmp     short loc_100438732
0x10043872c  mov     r8, rcx
0x10043872f  mov     rcx, [rcx]
0x100438732  cmp     byte ptr [rcx+19h], 0
0x100438736  jz      short loc_100438720
0x100438738  cmp     byte ptr [r8+19h], 0
0x10043873d  jnz     loc_100438915
0x100438743  cmp     si, [r8+20h]
0x100438748  jb      loc_100438915
0x10043874e  test    r9b, r9b
0x100438751  jnz     short loc_10043876B
0x100438753  cmp     [rax+20h], si
0x100438757  jnb     short loc_10043875F
0x100438759  mov     rax, [rax+10h]
0x10043875d  jmp     short loc_100438765
0x10043875f  mov     rdx, rax
0x100438762  mov     rax, [rax]
0x100438765  cmp     byte ptr [rax+19h], 0
0x100438769  jz      short loc_100438753
0x10043876b  cmp     byte ptr [rdx+19h], 0
0x10043876f  jnz     loc_1004388D9
0x100438775  cmp     si, [rdx+20h]
0x100438779  jb      loc_1004388D9
0x10043877f  mov     r14, [rdx+28h]
0x100438783  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x10043878a  nop     word ptr [rax+rax+00h]
0x100438790  inc     rdi
0x100438793  cmp     word ptr [r14+rdi*2], 0
0x100438799  jnz     short loc_100438790
0x10043879b  add     edi, edi
0x10043879d  lea     r8, [rsp+1A0h+var_170]
0x1004387a2  mov     edx, edi
0x1004387a4  mov     rcx, r14
0x1004387a7  call    cs:__imp_?FResolveCollation@@YAHPEB_WHPEAK@Z; FResolveCollation(wchar_t const *,int,ulong *)
0x1004387ad  test    eax, eax
0x1004387af  jz      loc_1004388E7
0x1004387b5  mov     [rsp+1A0h+var_158], 400327h
0x1004387bd  mov     [rsp+1A0h+var_150], rbx
0x1004387c2  mov     [rsp+1A0h+var_140], rbx
0x1004387c7  mov     [rsp+1A0h+var_148], rbx
0x1004387cc  mov     [rsp+1A0h+var_138], rbx
0x1004387d1  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x1004387d8  call    cs:__imp_?IsXPlatInstance@OsInfo@@QEBA?B_NXZ; OsInfo::IsXPlatInstance(void)
0x1004387de  test    al, al
0x1004387e0  jz      loc_1004388CA
0x1004387e6  mov     rcx, cs:?g_taskInitCrossPlatTelemetryAndClustering@@3PEAVSOS_Task@@EA; SOS_Task * g_taskInitCrossPlatTelemetryAndClustering
0x1004387ed  test    rcx, rcx
0x1004387f0  jnz     short loc_10043881D
0x1004387f2  mov     [rsp+1A0h+var_180], rbx
0x1004387f7  mov     r9d, 316h
0x1004387fd  lea     r8, aSetupCpp; "setup.cpp"
0x100438804  lea     rdx, aGTaskinitcross; "g_taskInitCrossPlatTelemetryAndClusteri"...
0x10043880b  mov     ecx, 1
0x100438810  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100438816  mov     rcx, cs:?g_taskInitCrossPlatTelemetryAndClustering@@3PEAVSOS_Task@@EA; SOS_Task * g_taskInitCrossPlatTelemetryAndClustering
0x10043881d  lea     r8, [rsp+1A0h+var_158]
0x100438822  mov     edx, 0FFFFFFFFh
0x100438827  call    cs:__imp_?WaitForDone@SOS_Task@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z; SOS_Task::WaitForDone(ulong,SOS_WaitInfo const *)
0x10043882d  cmp     eax, 80000000h
0x100438832  jnz     short loc_100438858
0x100438834  mov     [rsp+1A0h+var_180], rbx
0x100438839  mov     r9d, 319h
0x10043883f  lea     r8, aSetupCpp; "setup.cpp"
0x100438846  lea     rdx, aResultSosFail; "result != SOS_FAIL"
0x10043884d  mov     ecx, 1
0x100438852  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100438858  mov     rcx, cs:?g_taskInitSqlAgentUser@@3PEAVSOS_Task@@EA; SOS_Task * g_taskInitSqlAgentUser
0x10043885f  test    rcx, rcx
0x100438862  jnz     short loc_10043888F
0x100438864  mov     [rsp+1A0h+var_180], rbx
0x100438869  mov     r9d, 31Ch
0x10043886f  lea     r8, aSetupCpp; "setup.cpp"
0x100438876  lea     rdx, aGTaskinitsqlag; "g_taskInitSqlAgentUser != nullptr"
0x10043887d  mov     ecx, 1
0x100438882  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100438888  mov     rcx, cs:?g_taskInitSqlAgentUser@@3PEAVSOS_Task@@EA; SOS_Task * g_taskInitSqlAgentUser
0x10043888f  lea     r8, [rsp+1A0h+var_158]
0x100438894  mov     edx, 0FFFFFFFFh
0x100438899  call    cs:__imp_?WaitForDone@SOS_Task@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z; SOS_Task::WaitForDone(ulong,SOS_WaitInfo const *)
0x10043889f  cmp     eax, 80000000h
0x1004388a4  jnz     short loc_1004388CA
0x1004388a6  mov     [rsp+1A0h+var_180], rbx
0x1004388ab  mov     r9d, 31Fh
0x1004388b1  lea     r8, aSetupCpp; "setup.cpp"
0x1004388b8  lea     rdx, aResultSosFail; "result != SOS_FAIL"
0x1004388bf  mov     ecx, 1
0x1004388c4  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1004388ca  mov     rdx, rbx
0x1004388cd  mov     ecx, [rsp+1A0h+var_170]
0x1004388d1  call    cs:__imp_?RecollateServer@@YAXKVContextHandle@@@Z; RecollateServer(ulong,ContextHandle)
0x1004388d7  jmp     short loc_100438915
0x1004388d9  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x1004388e0  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1004388e6  int     3; Trap to Debugger
0x1004388e7  mov     r8, r14
0x1004388ea  mov     edx, edi
0x1004388ec  mov     ecx, 0C327h; unsigned int
0x1004388f1  call    ?WriteConsoleMessage@@YAXKZZ; WriteConsoleMessage(ulong,...)
0x1004388f6  mov     [rsp+1A0h+var_178], r14
0x1004388fb  mov     dword ptr [rsp+1A0h+var_180], edi
0x1004388ff  mov     edx, 30h ; '0'
0x100438904  lea     ecx, [rdx-2Ch]
0x100438907  lea     r9d, [rdx-2Dh]
0x10043890b  lea     r8d, [rdx-20h]
0x10043890f  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100438915  mov     rcx, [rbp+0A0h+var_30]
0x100438919  xor     rcx, rsp; StackCookie
0x10043891c  call    __security_check_cookie
0x100438921  lea     r11, [rsp+1A0h+var_20]
0x100438929  mov     rbx, [r11+30h]
0x10043892d  mov     rsi, [r11+40h]
0x100438931  mov     rdi, [r11+48h]
0x100438935  mov     rsp, r11
0x100438938  pop     r15
0x10043893a  pop     r14
0x10043893c  pop     r13
0x10043893e  pop     r12
0x100438940  pop     rbp
0x100438941  retn
0x100438942  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
0x100438948  jmp     short $+2
0x10043894a  nop
```
