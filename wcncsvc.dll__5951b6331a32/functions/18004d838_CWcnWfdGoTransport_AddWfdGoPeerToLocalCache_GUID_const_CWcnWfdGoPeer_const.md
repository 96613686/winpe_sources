# CWcnWfdGoTransport::AddWfdGoPeerToLocalCache(_GUID const *,CWcnWfdGoPeer const *)

- ea: `0x18004d838`
- end: `0x18004da80`
- name: `?AddWfdGoPeerToLocalCache@CWcnWfdGoTransport@@AEAAJPEBU_GUID@@PEBVCWcnWfdGoPeer@@@Z`
- size: `584`
- prototype: `__int64 __fastcall(CWcnWfdGoTransport *this, const struct _GUID *, const struct CWcnWfdGoPeer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004e048`

## callees

- `0x180004fb8`
- `0x180005014`
- `0x18000cecc`
- `0x18000d1c0`
- `0x18004d838`
- `0x180053004`
- `0x180056de6`
- `0x180056e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d8f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d8f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004da1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004da1e`

## pseudocode

```c
__int64 __fastcall CWcnWfdGoTransport::AddWfdGoPeerToLocalCache(
        CWcnWfdGoTransport *this,
        const struct _GUID *a2,
        const struct CWcnWfdGoPeer *a3)
{
  _QWORD *v5; // r10
  const char *Indent; // rax
  __int64 v7; // r10
  int v9; // r14d
  __int64 *v10; // r13
  __int64 *v11; // rbx
  __int64 *v12; // r15
  __int64 **v13; // r13
  __int64 *v14; // rsi
  __int64 *v15; // r15
  __int64 ***v16; // rbx
  __int64 v17; // rax
  unsigned int v18; // eax
  __int64 v19; // r10
  __int64 v20; // rax
  __int64 ***v21; // [rsp+30h] [rbp-78h] BYREF
  const struct CWcnWfdGoPeer *v22; // [rsp+38h] [rbp-70h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp-68h]
  std::bad_alloc *v24; // [rsp+48h] [rbp-60h] BYREF
  __int128 v25; // [rsp+50h] [rbp-58h] BYREF
  __int64 v26; // [rsp+60h] [rbp-48h]

  v22 = a3;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v7 + 16), 55, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, Indent);
    v5 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v5 != &WPP_GLOBAL_Control && *((_BYTE *)v5 + 25) >= 2u )
      WPP_SF_s(v5[2], 56, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, "pWfdGoPeerGuid");
    return 2147500035LL;
  }
  v9 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 328);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 328));
  v21 = (__int64 ***)((char *)this + 368);
  v10 = (__int64 *)*((_QWORD *)this + 46);
  v11 = (__int64 *)v10[1];
  v12 = v10;
  if ( *((_BYTE *)v11 + 25) )
    goto LABEL_17;
  do
  {
    if ( memcmp_0(v11 + 4, a2, 0x10u) >= 0 )
    {
      v12 = v11;
      v11 = (__int64 *)*v11;
    }
    else
    {
      v11 = (__int64 *)v11[2];
    }
  }
  while ( !*((_BYTE *)v11 + 25) );
  if ( v12 == v10 || memcmp_0(a2, v12 + 4, 0x10u) < 0 )
  {
LABEL_17:
    v13 = *v21;
    v14 = (*v21)[1];
    v15 = (__int64 *)*v21;
    if ( *((_BYTE *)v14 + 25) )
      goto LABEL_34;
    do
    {
      if ( memcmp_0(v14 + 4, a2, 0x10u) >= 0 )
      {
        v15 = v14;
        v14 = (__int64 *)*v14;
      }
      else
      {
        v14 = (__int64 *)v14[2];
      }
      v16 = (__int64 ***)v15;
    }
    while ( !*((_BYTE *)v14 + 25) );
    if ( v15 == (__int64 *)v13 || memcmp_0(a2, v15 + 4, 0x10u) < 0 )
    {
LABEL_34:
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        v25 = (__int128)*a2;
        v26 = 0;
        v17 = std::_Tree_buy<std::pair<_GUID const,CWcnWfdGoPeer const *>>::_Buynode<std::pair<_GUID,CWcnWfdGoPeer const *>>(
                v21,
                &v25);
        std::_Tree<std::_Tmap_traits<_GUID,CWcnPeer *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeer *>>,0>>::_Insert_hint<std::pair<_GUID const,CWcnPeer *> &,std::_Tree_node<std::pair<_GUID const,CWcnPeer *>,void *> *>(
          v21,
          &v21,
          v15,
          (const void *)(v17 + 32),
          v17);
        v16 = v21;
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', &v24) )
        {
          LODWORD(v21) = -2147024882;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v20 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v24 + 8LL))(v24);
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, v20);
          }
          v9 = (int)v21;
          __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18004DA0D);
          goto LABEL_25;
        }
      }
    }
    v16[6] = (__int64 **)v22;
  }
  else
  {
    v9 = -2147024713;
  }
LABEL_25:
  LeaveCriticalSection(lpCriticalSection);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v9 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v18 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v19 + 16), 58, (unsigned int)WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids, v18, v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004d838  push    rbx
0x18004d83a  push    rsi
0x18004d83b  push    r12
0x18004d83d  push    r13
0x18004d83f  push    r14
0x18004d841  push    r15
0x18004d843  sub     rsp, 78h
0x18004d847  mov     rax, cs:__security_cookie
0x18004d84e  xor     rax, rsp
0x18004d851  mov     [rsp+0A8h+var_40], rax
0x18004d856  mov     [rsp+0A8h+var_70], r8
0x18004d85b  mov     r12, rdx
0x18004d85e  mov     rbx, rcx
0x18004d861  lea     rax, WPP_GLOBAL_Control
0x18004d868  mov     r10, cs:WPP_GLOBAL_Control
0x18004d86f  cmp     r10, rax
0x18004d872  jz      short loc_18004D8AB
0x18004d874  cmp     byte ptr [r10+19h], 6
0x18004d879  jb      short loc_18004D8AB
0x18004d87b  mov     ecx, 1; int
0x18004d880  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004d885  mov     edx, 37h ; '7'
0x18004d88a  mov     r9, rax
0x18004d88d  lea     r8, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004d894  mov     rcx, [r10+10h]
0x18004d898  call    WPP_SF_s
0x18004d89d  mov     r10, cs:WPP_GLOBAL_Control
0x18004d8a4  lea     rax, WPP_GLOBAL_Control
0x18004d8ab  test    r12, r12
0x18004d8ae  jnz     short loc_18004D8E2
0x18004d8b0  cmp     r10, rax
0x18004d8b3  jz      short loc_18004D8D8
0x18004d8b5  cmp     byte ptr [r10+19h], 2
0x18004d8ba  jb      short loc_18004D8D8
0x18004d8bc  lea     edx, [r12+38h]
0x18004d8c1  lea     r9, aPwfdgopeerguid; "pWfdGoPeerGuid"
0x18004d8c8  lea     r8, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004d8cf  mov     rcx, [r10+10h]
0x18004d8d3  call    WPP_SF_s
0x18004d8d8  mov     eax, 80004003h
0x18004d8dd  jmp     loc_18004DA64
0x18004d8e2  xor     r14d, r14d
0x18004d8e5  lea     rax, [rbx+148h]
0x18004d8ec  mov     [rsp+0A8h+lpCriticalSection], rax
0x18004d8f1  mov     rcx, rax; lpCriticalSection
0x18004d8f4  call    cs:__imp_EnterCriticalSection
0x18004d8fa  add     rbx, 170h
0x18004d901  mov     [rsp+0A8h+var_78], rbx
0x18004d906  mov     r13, [rbx]
0x18004d909  mov     rbx, [r13+8]
0x18004d90d  mov     r15, r13
0x18004d910  cmp     [rbx+19h], r14b
0x18004d914  jnz     short loc_18004D962
0x18004d916  lea     esi, [r14+10h]
0x18004d91a  lea     rcx, [rbx+20h]; Buf1
0x18004d91e  mov     r8, rsi; Size
0x18004d921  mov     rdx, r12; Buf2
0x18004d924  call    memcmp_0
0x18004d929  test    eax, eax
0x18004d92b  jns     short loc_18004D933
0x18004d92d  mov     rbx, [rbx+10h]
0x18004d931  jmp     short loc_18004D939
0x18004d933  mov     r15, rbx
0x18004d936  mov     rbx, [rbx]
0x18004d939  cmp     [rbx+19h], r14b
0x18004d93d  jz      short loc_18004D91A
0x18004d93f  cmp     r15, r13
0x18004d942  jz      short loc_18004D962
0x18004d944  lea     rdx, [r15+20h]; Buf2
0x18004d948  mov     r8, rsi; Size
0x18004d94b  mov     rcx, r12; Buf1
0x18004d94e  call    memcmp_0
0x18004d953  test    eax, eax
0x18004d955  js      short loc_18004D962
0x18004d957  mov     r14d, 800700B7h
0x18004d95d  jmp     loc_18004DA12
0x18004d962  mov     r13, [rsp+0A8h+var_78]
0x18004d967  mov     r13, [r13+0]
0x18004d96b  mov     rsi, [r13+8]
0x18004d96f  mov     r15, r13
0x18004d972  cmp     byte ptr [rsi+19h], 0
0x18004d976  jnz     short loc_18004D9BE
0x18004d978  lea     rcx, [rsi+20h]; Buf1
0x18004d97c  mov     r8d, 10h; Size
0x18004d982  mov     rdx, r12; Buf2
0x18004d985  call    memcmp_0
0x18004d98a  test    eax, eax
0x18004d98c  jns     short loc_18004D994
0x18004d98e  mov     rsi, [rsi+10h]
0x18004d992  jmp     short loc_18004D99A
0x18004d994  mov     r15, rsi
0x18004d997  mov     rsi, [rsi]
0x18004d99a  mov     rbx, r15
0x18004d99d  cmp     byte ptr [rsi+19h], 0
0x18004d9a1  jz      short loc_18004D978
0x18004d9a3  cmp     rbx, r13
0x18004d9a6  jz      short loc_18004D9BE
0x18004d9a8  lea     rdx, [r15+20h]; Buf2
0x18004d9ac  mov     r8d, 10h; Size
0x18004d9b2  mov     rcx, r12; Buf1
0x18004d9b5  call    memcmp_0
0x18004d9ba  test    eax, eax
0x18004d9bc  jns     short loc_18004DA02
0x18004d9be  movups  xmm0, xmmword ptr [r12]
0x18004d9c3  movdqu  [rsp+0A8h+var_58], xmm0
0x18004d9c9  mov     [rsp+0A8h+var_48], 0
0x18004d9d2  lea     rdx, [rsp+0A8h+var_58]
0x18004d9d7  mov     rsi, [rsp+0A8h+var_78]
0x18004d9dc  mov     rcx, rsi
0x18004d9df  call    ??$_Buynode@U?$pair@U_GUID@@PEBVCWcnWfdGoPeer@@@std@@@?$_Tree_buy@U?$pair@$$CBU_GUID@@PEBVCWcnWfdGoPeer@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEBVCWcnWfdGoPeer@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEBVCWcnWfdGoPeer@@@std@@PEAX@1@$$QEAU?$pair@U_GUID@@PEBVCWcnWfdGoPeer@@@1@@Z; std::_Tree_buy<std::pair<_GUID const,CWcnWfdGoPeer const *>>::_Buynode<std::pair<_GUID,CWcnWfdGoPeer const *>>(std::pair<_GUID,CWcnWfdGoPeer const *> &&)
0x18004d9e4  lea     r9, [rax+20h]
0x18004d9e8  mov     [rsp+0A8h+var_88], rax
0x18004d9ed  mov     r8, r15
0x18004d9f0  lea     rdx, [rsp+0A8h+var_78]
0x18004d9f5  mov     rcx, rsi
0x18004d9f8  call    ??$_Insert_hint@AEAU?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVCWcnPeer@@UGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@@std@@@std@@@1@AEAU?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<_GUID,CWcnPeer *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeer *>>,0>>::_Insert_hint<std::pair<_GUID const,CWcnPeer *> &,std::_Tree_node<std::pair<_GUID const,CWcnPeer *>,void *> *>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CWcnPeer *>>>>,std::pair<_GUID const,CWcnPeer *> &,std::_Tree_node<std::pair<_GUID const,CWcnPeer *>,void *> *)
0x18004d9fd  mov     rbx, [rsp+0A8h+var_78]
0x18004da02  mov     rax, [rsp+0A8h+var_70]
0x18004da07  mov     [rbx+30h], rax
0x18004da0b  jmp     short loc_18004DA12
0x18004da0d  mov     r14d, dword ptr [rsp+0A8h+var_78]
0x18004da12  lea     rbx, WPP_GLOBAL_Control
0x18004da19  mov     rcx, [rsp+0A8h+lpCriticalSection]; lpCriticalSection
0x18004da1e  call    cs:__imp_LeaveCriticalSection
0x18004da24  mov     r10, cs:WPP_GLOBAL_Control
0x18004da2b  cmp     r10, rbx
0x18004da2e  jz      short loc_18004DA61
0x18004da30  test    r14d, r14d
0x18004da33  js      short loc_18004DA3C
0x18004da35  cmp     byte ptr [r10+19h], 6
0x18004da3a  jb      short loc_18004DA61
0x18004da3c  or      ecx, 0FFFFFFFFh; int
0x18004da3f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004da44  mov     edx, 3Ah ; ':'
0x18004da49  mov     dword ptr [rsp+0A8h+var_88], r14d
0x18004da4e  mov     r9, rax
0x18004da51  lea     r8, WPP_0760218a09c13eb2b769c5baf1c35c65_Traceguids
0x18004da58  mov     rcx, [r10+10h]
0x18004da5c  call    WPP_SF_sd
0x18004da61  mov     eax, r14d
0x18004da64  mov     rcx, [rsp+0A8h+var_40]
0x18004da69  xor     rcx, rsp; StackCookie
0x18004da6c  call    __security_check_cookie
0x18004da71  add     rsp, 78h
0x18004da75  pop     r15
0x18004da77  pop     r14
0x18004da79  pop     r13
0x18004da7b  pop     r12
0x18004da7d  pop     rsi
0x18004da7e  pop     rbx
0x18004da7f  retn
```
