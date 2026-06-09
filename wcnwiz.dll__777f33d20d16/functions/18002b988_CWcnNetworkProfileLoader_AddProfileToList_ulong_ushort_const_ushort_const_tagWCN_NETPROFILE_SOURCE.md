# CWcnNetworkProfileLoader::AddProfileToList(ulong,ushort const *,ushort const *,tagWCN_NETPROFILE_SOURCE)

- ea: `0x18002b988`
- end: `0x18002bde2`
- name: `?AddProfileToList@CWcnNetworkProfileLoader@@IEAAJKPEBG0W4tagWCN_NETPROFILE_SOURCE@@@Z`
- size: `1114`
- prototype: `__int64 __fastcall(_QWORD *, __int16, unsigned __int16 *, _BYTE *, int)`
- caller_count: `4`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18002bfb8`
- `0x18002c708`
- `0x18002cec0`
- `0x18002d050`

## callees

- `0x180001820`
- `0x180002294`
- `0x1800028a0`
- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x180010940`
- `0x18001acd4`
- `0x180029424`
- `0x1800295ec`
- `0x1800296a4`
- `0x18002b150`
- `0x18002b874`
- `0x18002b988`
- `0x18002de1c`
- `0x180031010`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x18002bcad`
- `KERNEL32!lstrcmpW` at `0x18002bcad`
- `wlanapi!WFDFreeMemoryInt` at `0x18002bd60`
- `wlanapi!WFDFreeMemoryInt` at `0x18002bd60`

## string_xrefs

- `0x18002ba2c`: `wszProfileXml`

## pseudocode

```c
__int64 __fastcall CWcnNetworkProfileLoader::AddProfileToList(
        _QWORD *a1,
        __int16 a2,
        unsigned __int16 *a3,
        _BYTE *a4,
        int a5)
{
  __int64 v9; // rsi
  _BYTE *v10; // r10
  const char *Indent; // rax
  __int64 v12; // r10
  __int64 v13; // rdx
  const char *v14; // r9
  int v16; // eax
  __int64 *v17; // rdx
  int v18; // ebx
  _QWORD *v19; // r10
  __int64 v20; // rdx
  unsigned __int16 **v21; // rax
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rbx
  __int64 v26; // rax
  int v27; // r12d
  _QWORD *v28; // r15
  unsigned __int16 **v29; // r13
  unsigned __int16 **v30; // rax
  unsigned int v31; // eax
  __int64 v32; // r10
  __int64 v33; // rax
  __int64 v34; // [rsp+0h] [rbp-578h] BYREF
  unsigned __int16 *v35; // [rsp+30h] [rbp-548h]
  struct _WFD_PROFILE *v36; // [rsp+38h] [rbp-540h] BYREF
  __int64 v37; // [rsp+40h] [rbp-538h] BYREF
  unsigned __int16 **v38; // [rsp+48h] [rbp-530h]
  LPCWSTR lpString1; // [rsp+50h] [rbp-528h]
  std::bad_alloc *v40; // [rsp+58h] [rbp-520h] BYREF
  _BYTE v41[32]; // [rsp+60h] [rbp-518h] BYREF
  char v42[32]; // [rsp+80h] [rbp-4F8h] BYREF
  _BYTE v43[656]; // [rsp+A0h] [rbp-4D8h] BYREF
  _BYTE v44[512]; // [rsp+330h] [rbp-248h] BYREF

  v35 = a3;
  v9 = 0;
  memset_0(v43, 0, 0x288u);
  v36 = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v12 + 16), 43, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids, Indent);
    v10 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || v10[25] < 2u )
      return 2147500035LL;
    v13 = 44;
    v14 = "wszProfileXml";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v10 + 2), v13, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids, v14);
    return 2147500035LL;
  }
  if ( !a4 )
  {
    if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || v10[25] < 2u )
      return 2147500035LL;
    v13 = 45;
    v14 = "wszDisplayDescription";
    goto LABEL_12;
  }
  v16 = WcnNetworkProfileParse(a3, a2, (struct tagWCN_NETPROFILE_SETTINGS *)v43, &v36);
  v18 = v16;
  if ( v16 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_58;
    v20 = 46;
    goto LABEL_18;
  }
  if ( (a2 & 0x10) != 0 )
  {
    v16 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _BYTE *))(*a1 + 24LL))(a1, 256, v43);
    v18 = v16;
    if ( v16 < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_58;
      v20 = 47;
      goto LABEL_18;
    }
  }
  if ( (a2 & 0x20) != 0 )
  {
    v16 = (*(__int64 (__fastcall **)(_QWORD *, _BYTE *, __int64, _BYTE *))(*a1 + 16LL))(a1, v43, 256, v44);
    v18 = v16;
    if ( v16 < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_58;
      v20 = 48;
      goto LABEL_18;
    }
    a4 = v44;
  }
  v21 = (unsigned __int16 **)operator new(0x2F0u, (const struct std::nothrow_t *)std::nothrow);
  v38 = v21;
  if ( !v21
    || (std::wstring::wstring(v21 + 2, v17, v21),
        std::wstring::wstring(v22 + 48, v23, v22),
        *(_WORD *)(v24 + 80) = 0,
        *(_BYTE *)(v24 + 82) = 0,
        *(_QWORD *)(v24 + 744) = 0,
        v9 = v24,
        (v37 = v24) == 0) )
  {
    v18 = -2147024882;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_58;
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids, "pNewProfile");
    goto LABEL_57;
  }
  v38 = (unsigned __int16 **)v41;
  v25 = std::wstring::wstring(v41, a4);
  v26 = std::wstring::wstring(v42, v35);
  v16 = CWcnNetworkProfile::Init(v9, v26, v43, v25);
  v18 = v16;
  if ( v16 >= 0 )
  {
    *(_DWORD *)(v9 + 736) = a5;
    if ( a5 == 3 )
    {
      *(_QWORD *)(v9 + 744) = v36;
      v36 = 0;
    }
    if ( (a2 & 2) != 0 )
      *(_BYTE *)(v9 + 80) = 1;
    v27 = a2 & 0x40;
    if ( v27 )
      *(_BYTE *)(v9 + 81) = 1;
    v28 = a1 + 2;
    v29 = (unsigned __int16 **)a1[2];
    v30 = (unsigned __int16 **)v28[1];
    v38 = v30;
    while ( v29 != v30 )
    {
      v35 = *v29;
      lpString1 = v35 + 44;
      if ( (unsigned __int8)tagWCN_NETPROFILE_SETTINGS::operator==(v35 + 44, v43) )
      {
        if ( v27 )
          *((_BYTE *)v35 + 81) = 1;
        goto LABEL_57;
      }
      if ( !lstrcmpW(lpString1, (LPCWSTR)(v9 + 88)) )
      {
        *((_BYTE *)v35 + 80) = 1;
        *(_BYTE *)(v9 + 80) = 1;
      }
      ++v29;
      v30 = v38;
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v17 = (__int64 *)v28[1];
      if ( v17 == (__int64 *)v28[2] )
      {
        std::vector<CWcnNetworkProfile *>::_Emplace_reallocate<CWcnNetworkProfile * const &>(v28, v17, &v37);
      }
      else
      {
        *v17 = v9;
        v28[1] += 8LL;
      }
      v9 = 0;
      v37 = 0;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', &v40) )
      {
        v17 = &v34;
        LODWORD(v35) = -2147024882;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v33 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v40 + 8LL))(v40);
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids, v33);
        }
        v18 = (int)v35;
        v9 = v37;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18002BD09);
      }
    }
    goto LABEL_57;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    goto LABEL_58;
  v20 = 50;
LABEL_18:
  WPP_SF_d(v19[2], v20, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids, (unsigned int)v16);
LABEL_57:
  v19 = WPP_GLOBAL_Control;
LABEL_58:
  if ( v36 )
  {
    WFDFreeMemoryInt(v36);
    v36 = 0;
    v19 = WPP_GLOBAL_Control;
  }
  if ( v9 )
  {
    CWcnNetworkProfile::`scalar deleting destructor'((CWcnNetworkProfile *)v9, (unsigned int)v17);
    v19 = WPP_GLOBAL_Control;
  }
  if ( v19 != &WPP_GLOBAL_Control && (v18 < 0 || *((_BYTE *)v19 + 25) >= 6u) )
  {
    v31 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v32 + 16), 52, (unsigned int)WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids, v31, v18);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18002b988  push    rbx
0x18002b98a  push    rsi
0x18002b98b  push    r12
0x18002b98d  push    r13
0x18002b98f  push    r14
0x18002b991  push    r15
0x18002b993  sub     rsp, 548h
0x18002b99a  mov     rax, cs:__security_cookie
0x18002b9a1  xor     rax, rsp
0x18002b9a4  mov     [rsp+578h+var_48], rax
0x18002b9ac  mov     r15, r9
0x18002b9af  mov     rbx, r8
0x18002b9b2  mov     [rsp+578h+var_548], rbx
0x18002b9b7  mov     r12d, edx
0x18002b9ba  mov     r13, rcx
0x18002b9bd  xor     esi, esi
0x18002b9bf  xor     edx, edx; Val
0x18002b9c1  mov     r8d, 288h; Size
0x18002b9c7  lea     rcx, [rsp+578h+var_4D8]; void *
0x18002b9cf  call    memset_0
0x18002b9d4  mov     [rsp+578h+var_540], rsi
0x18002b9d9  lea     r14, WPP_GLOBAL_Control
0x18002b9e0  mov     r10, cs:WPP_GLOBAL_Control
0x18002b9e7  cmp     r10, r14
0x18002b9ea  jz      short loc_18002BA18
0x18002b9ec  cmp     byte ptr [r10+19h], 6
0x18002b9f1  jb      short loc_18002BA18
0x18002b9f3  lea     ecx, [rsi+1]; int
0x18002b9f6  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002b9fb  lea     edx, [rsi+2Bh]
0x18002b9fe  mov     r9, rax
0x18002ba01  lea     r8, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids
0x18002ba08  mov     rcx, [r10+10h]
0x18002ba0c  call    WPP_SF_s
0x18002ba11  mov     r10, cs:WPP_GLOBAL_Control
0x18002ba18  test    rbx, rbx
0x18002ba1b  jnz     short loc_18002BA35
0x18002ba1d  cmp     r10, r14
0x18002ba20  jz      short loc_18002BA61
0x18002ba22  cmp     byte ptr [r10+19h], 2
0x18002ba27  jb      short loc_18002BA61
0x18002ba29  lea     edx, [rbx+2Ch]
0x18002ba2c  lea     r9, aWszprofilexml; "wszProfileXml"
0x18002ba33  jmp     short loc_18002BA51
0x18002ba35  test    r15, r15
0x18002ba38  jnz     short loc_18002BA6B
0x18002ba3a  cmp     r10, r14
0x18002ba3d  jz      short loc_18002BA61
0x18002ba3f  cmp     byte ptr [r10+19h], 2
0x18002ba44  jb      short loc_18002BA61
0x18002ba46  lea     edx, [r15+2Dh]
0x18002ba4a  lea     r9, aWszdisplaydesc; "wszDisplayDescription"
0x18002ba51  lea     r8, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids
0x18002ba58  mov     rcx, [r10+10h]
0x18002ba5c  call    WPP_SF_s
0x18002ba61  mov     eax, 80004003h
0x18002ba66  jmp     loc_18002BDC0
0x18002ba6b  lea     r9, [rsp+578h+var_540]; struct _WFD_PROFILE **
0x18002ba70  lea     r8, [rsp+578h+var_4D8]; struct tagWCN_NETPROFILE_SETTINGS *
0x18002ba78  mov     edx, r12d; unsigned int
0x18002ba7b  mov     rcx, rbx; unsigned __int16 *
0x18002ba7e  call    ?WcnNetworkProfileParse@@YAJPEBGKPEAUtagWCN_NETPROFILE_SETTINGS@@PEAPEAU_WFD_PROFILE@@@Z; WcnNetworkProfileParse(ushort const *,ulong,tagWCN_NETPROFILE_SETTINGS *,_WFD_PROFILE * *)
0x18002ba83  mov     ebx, eax
0x18002ba85  test    eax, eax
0x18002ba87  jns     short loc_18002BAC1
0x18002ba89  mov     r10, cs:WPP_GLOBAL_Control
0x18002ba90  cmp     r10, r14
0x18002ba93  jz      loc_18002BD56
0x18002ba99  cmp     byte ptr [r10+19h], 2
0x18002ba9e  jb      loc_18002BD56
0x18002baa4  mov     edx, 2Eh ; '.'
0x18002baa9  mov     r9d, eax
0x18002baac  lea     r8, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids
0x18002bab3  mov     rcx, [r10+10h]
0x18002bab7  call    WPP_SF_d
0x18002babc  jmp     loc_18002BD4F
0x18002bac1  test    r12b, 10h
0x18002bac5  jz      short loc_18002BB0C
0x18002bac7  mov     rax, [r13+0]
0x18002bacb  lea     r8, [rsp+578h+var_4D8]
0x18002bad3  mov     edx, 100h
0x18002bad8  mov     rcx, r13
0x18002badb  mov     rax, [rax+18h]
0x18002badf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bae4  mov     ebx, eax
0x18002bae6  test    eax, eax
0x18002bae8  jns     short loc_18002BB0C
0x18002baea  mov     r10, cs:WPP_GLOBAL_Control
0x18002baf1  cmp     r10, r14
0x18002baf4  jz      loc_18002BD56
0x18002bafa  cmp     byte ptr [r10+19h], 2
0x18002baff  jb      loc_18002BD56
0x18002bb05  mov     edx, 2Fh ; '/'
0x18002bb0a  jmp     short loc_18002BAA9
0x18002bb0c  test    r12b, 20h
0x18002bb10  jz      short loc_18002BB6B
0x18002bb12  mov     rax, [r13+0]
0x18002bb16  lea     r9, [rsp+578h+var_248]
0x18002bb1e  mov     r8d, 100h
0x18002bb24  lea     rdx, [rsp+578h+var_4D8]
0x18002bb2c  mov     rcx, r13
0x18002bb2f  mov     rax, [rax+10h]
0x18002bb33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb38  mov     ebx, eax
0x18002bb3a  test    eax, eax
0x18002bb3c  jns     short loc_18002BB63
0x18002bb3e  mov     r10, cs:WPP_GLOBAL_Control
0x18002bb45  cmp     r10, r14
0x18002bb48  jz      loc_18002BD56
0x18002bb4e  cmp     byte ptr [r10+19h], 2
0x18002bb53  jb      loc_18002BD56
0x18002bb59  mov     edx, 30h ; '0'
0x18002bb5e  jmp     loc_18002BAA9
0x18002bb63  lea     r15, [rsp+578h+var_248]
0x18002bb6b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002bb72  mov     ecx, 2F0h; unsigned __int64
0x18002bb77  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002bb7c  mov     r8, rax
0x18002bb7f  mov     [rsp+578h+var_530], rax
0x18002bb84  test    rax, rax
0x18002bb87  jz      loc_18002BD1B
0x18002bb8d  lea     rcx, [rax+10h]
0x18002bb91  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002bb96  lea     rcx, [r8+30h]
0x18002bb9a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002bb9f  mov     [r8+50h], si
0x18002bba4  mov     [r8+52h], sil
0x18002bba8  mov     [r8+2E8h], rsi
0x18002bbaf  mov     rsi, r8
0x18002bbb2  mov     [rsp+578h+var_538], r8
0x18002bbb7  test    r8, r8
0x18002bbba  jz      loc_18002BD1B
0x18002bbc0  lea     rax, [rsp+578h+var_518]
0x18002bbc5  mov     [rsp+578h+var_530], rax
0x18002bbca  mov     rdx, r15
0x18002bbcd  lea     rcx, [rsp+578h+var_518]
0x18002bbd2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002bbd7  mov     rbx, rax
0x18002bbda  mov     rdx, [rsp+578h+var_548]
0x18002bbdf  lea     rcx, [rsp+578h+var_4F8]
0x18002bbe7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002bbec  nop
0x18002bbed  mov     r9, rbx
0x18002bbf0  lea     r8, [rsp+578h+var_4D8]
0x18002bbf8  mov     rdx, rax
0x18002bbfb  mov     rcx, rsi
0x18002bbfe  call    ?Init@CWcnNetworkProfile@@IEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBUtagWCN_NETPROFILE_SETTINGS@@0@Z; CWcnNetworkProfile::Init(std::wstring,tagWCN_NETPROFILE_SETTINGS const *,std::wstring)
0x18002bc03  mov     ebx, eax
0x18002bc05  test    eax, eax
0x18002bc07  jns     short loc_18002BC2E
0x18002bc09  mov     r10, cs:WPP_GLOBAL_Control
0x18002bc10  cmp     r10, r14
0x18002bc13  jz      loc_18002BD56
0x18002bc19  cmp     byte ptr [r10+19h], 2
0x18002bc1e  jb      loc_18002BD56
0x18002bc24  mov     edx, 32h ; '2'
0x18002bc29  jmp     loc_18002BAA9
0x18002bc2e  mov     eax, [rsp+578h+arg_20]
0x18002bc35  mov     [rsi+2E0h], eax
0x18002bc3b  cmp     eax, 3
0x18002bc3e  jnz     short loc_18002BC55
0x18002bc40  mov     rax, [rsp+578h+var_540]
0x18002bc45  mov     [rsi+2E8h], rax
0x18002bc4c  mov     [rsp+578h+var_540], 0
0x18002bc55  test    r12b, 2
0x18002bc59  jz      short loc_18002BC5F
0x18002bc5b  mov     byte ptr [rsi+50h], 1
0x18002bc5f  and     r12d, 40h
0x18002bc63  jz      short loc_18002BC69
0x18002bc65  mov     byte ptr [rsi+51h], 1
0x18002bc69  lea     r15, [r13+10h]
0x18002bc6d  mov     r13, [r15]
0x18002bc70  mov     rax, [r15+8]
0x18002bc74  mov     [rsp+578h+var_530], rax
0x18002bc79  cmp     r13, rax
0x18002bc7c  jz      short loc_18002BCDF
0x18002bc7e  mov     rax, [r13+0]
0x18002bc82  mov     [rsp+578h+var_548], rax
0x18002bc87  add     rax, 58h ; 'X'
0x18002bc8b  mov     [rsp+578h+lpString1], rax
0x18002bc90  lea     rdx, [rsp+578h+var_4D8]
0x18002bc98  mov     rcx, rax
0x18002bc9b  call    ??8tagWCN_NETPROFILE_SETTINGS@@QEBA_NAEBU0@@Z; tagWCN_NETPROFILE_SETTINGS::operator==(tagWCN_NETPROFILE_SETTINGS const &)
0x18002bca0  test    al, al
0x18002bca2  jnz     short loc_18002BCCF
0x18002bca4  lea     rdx, [rsi+58h]; lpString2
0x18002bca8  mov     rcx, [rsp+578h+lpString1]; lpString1
0x18002bcad  call    cs:__imp_lstrcmpW
0x18002bcb3  test    eax, eax
0x18002bcb5  jnz     short loc_18002BCC4
0x18002bcb7  mov     rax, [rsp+578h+var_548]
0x18002bcbc  mov     byte ptr [rax+50h], 1
0x18002bcc0  mov     byte ptr [rsi+50h], 1
0x18002bcc4  add     r13, 8
0x18002bcc8  mov     rax, [rsp+578h+var_530]
0x18002bccd  jmp     short loc_18002BC79
0x18002bccf  test    r12d, r12d
0x18002bcd2  jz      short loc_18002BD4F
0x18002bcd4  mov     rax, [rsp+578h+var_548]
0x18002bcd9  mov     byte ptr [rax+51h], 1
0x18002bcdd  jmp     short loc_18002BD4F
0x18002bcdf  mov     rdx, [r15+8]
0x18002bce3  cmp     rdx, [r15+10h]
0x18002bce7  jz      short loc_18002BCF3
0x18002bce9  mov     [rdx], rsi
0x18002bcec  add     qword ptr [r15+8], 8
0x18002bcf1  jmp     short loc_18002BD00
0x18002bcf3  lea     r8, [rsp+578h+var_538]
0x18002bcf8  mov     rcx, r15
0x18002bcfb  call    ??$_Emplace_reallocate@AEBQEAVCWcnNetworkProfile@@@?$vector@PEAVCWcnNetworkProfile@@V?$allocator@PEAVCWcnNetworkProfile@@@std@@@std@@AEAAPEAPEAVCWcnNetworkProfile@@QEAPEAV2@AEBQEAV2@@Z; std::vector<CWcnNetworkProfile *>::_Emplace_reallocate<CWcnNetworkProfile * const &>(CWcnNetworkProfile * * const,CWcnNetworkProfile * const &)
0x18002bd00  xor     esi, esi
0x18002bd02  mov     [rsp+578h+var_538], rsi
0x18002bd07  jmp     short loc_18002BD4F
0x18002bd09  lea     r14, WPP_GLOBAL_Control
0x18002bd10  mov     ebx, dword ptr [rsp+578h+var_548]
0x18002bd14  mov     rsi, [rsp+578h+var_538]
0x18002bd19  jmp     short loc_18002BD4F
0x18002bd1b  mov     ebx, 8007000Eh
0x18002bd20  mov     r10, cs:WPP_GLOBAL_Control
0x18002bd27  cmp     r10, r14
0x18002bd2a  jz      short loc_18002BD56
0x18002bd2c  cmp     byte ptr [r10+19h], 2
0x18002bd31  jb      short loc_18002BD56
0x18002bd33  mov     edx, 31h ; '1'
0x18002bd38  lea     r9, aPnewprofile; "pNewProfile"
0x18002bd3f  lea     r8, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids
0x18002bd46  mov     rcx, [r10+10h]
0x18002bd4a  call    WPP_SF_s
0x18002bd4f  mov     r10, cs:WPP_GLOBAL_Control
0x18002bd56  mov     rcx, [rsp+578h+var_540]
0x18002bd5b  test    rcx, rcx
0x18002bd5e  jz      short loc_18002BD76
0x18002bd60  call    cs:__imp_WFDFreeMemoryInt
0x18002bd66  mov     [rsp+578h+var_540], 0
0x18002bd6f  mov     r10, cs:WPP_GLOBAL_Control
0x18002bd76  test    rsi, rsi
0x18002bd79  jz      short loc_18002BD8A
0x18002bd7b  mov     rcx, rsi; this
0x18002bd7e  call    ??_GCWcnNetworkProfile@@QEAAPEAXI@Z; CWcnNetworkProfile::`scalar deleting destructor'(uint)
0x18002bd83  mov     r10, cs:WPP_GLOBAL_Control
0x18002bd8a  cmp     r10, r14
0x18002bd8d  jz      short loc_18002BDBE
0x18002bd8f  test    ebx, ebx
0x18002bd91  js      short loc_18002BD9A
0x18002bd93  cmp     byte ptr [r10+19h], 6
0x18002bd98  jb      short loc_18002BDBE
0x18002bd9a  or      ecx, 0FFFFFFFFh; int
0x18002bd9d  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002bda2  mov     edx, 34h ; '4'
0x18002bda7  mov     [rsp+578h+var_558], ebx
0x18002bdab  mov     r9, rax
0x18002bdae  lea     r8, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids
0x18002bdb5  mov     rcx, [r10+10h]
0x18002bdb9  call    WPP_SF_sd
0x18002bdbe  mov     eax, ebx
0x18002bdc0  mov     rcx, [rsp+578h+var_48]
0x18002bdc8  xor     rcx, rsp; StackCookie
0x18002bdcb  call    __security_check_cookie
0x18002bdd0  add     rsp, 548h
0x18002bdd7  pop     r15
0x18002bdd9  pop     r14
0x18002bddb  pop     r13
0x18002bddd  pop     r12
0x18002bddf  pop     rsi
0x18002bde0  pop     rbx
0x18002bde1  retn
```
