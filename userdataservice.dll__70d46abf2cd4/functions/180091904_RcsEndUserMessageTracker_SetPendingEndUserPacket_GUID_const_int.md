# RcsEndUserMessageTracker::_SetPendingEndUserPacket(_GUID const &,int *)

- ea: `0x180091904`
- end: `0x180091c0d`
- name: `?_SetPendingEndUserPacket@RcsEndUserMessageTracker@@AEAAJAEBU_GUID@@PEAH@Z`
- size: `777`
- prototype: `__int64 __fastcall(RcsEndUserMessageTracker *__hidden this, const struct _GUID *, int *)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180091c20`
- `0x1800f0c08`
- `0x1800f1028`

## callees

- `0x180008ee8`
- `0x1800234d4`
- `0x180035c40`
- `0x180068c60`
- `0x18007d240`
- `0x180091904`
- `0x180091df4`
- `0x180097db8`
- `0x18009e71c`
- `0x1800f0338`
- `0x1800f03f4`
- `0x1800f0ab4`
- `0x1800f1264`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009195a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800919db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091b5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009195a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800919db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091b5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091996`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800919b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091a47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091a55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091bb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091996`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800919b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091a47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091a55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091bb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091b3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091bcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091b3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091bcb`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180091af2`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180091af2`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180091aba`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180091aba`

## pseudocode

```c
__int64 __fastcall RcsEndUserMessageTracker::_SetPendingEndUserPacket(
        RcsEndUserMessageTracker *this,
        const struct _GUID *a2,
        int *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r14
  char *v7; // r12
  __int64 v8; // r8
  unsigned int v9; // ebx
  struct _RTL_CRITICAL_SECTION *v11; // rdi
  void **v12; // rbx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r9
  int v17; // eax
  _OWORD *v18; // rax
  struct IUnknown **v19; // rdi
  HRESULT v20; // eax
  __int64 v21; // r8
  void **v22; // rax
  HRESULT v23; // eax
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r9
  __int64 v27; // rcx
  char *v28; // rax
  char *v29; // rbx
  struct _GUID v30; // xmm0
  __int64 v31; // r8
  void *v32; // rcx
  int v33; // [rsp+30h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-48h] BYREF
  struct IUnknown **v35; // [rsp+40h] [rbp-40h] BYREF
  struct IUnknown *v36; // [rsp+48h] [rbp-38h] BYREF
  void **v37[2]; // [rsp+50h] [rbp-30h] BYREF
  GUID pguid; // [rsp+60h] [rbp-20h] BYREF

  if ( *((_DWORD *)this + 14) )
    Log_AssertionEvent_26(this, a2, 335);
  if ( a3 )
    *a3 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v7 = (char *)this + 168;
  utl::_Tree<_GUID,utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserMessageInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserMessageInfo>>>,GuidComparator,utl::allocator<utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserMessageInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserMessageInfo>>>>,0>::find<void>(
    (__int64)this + 168,
    v37,
    a2);
  if ( (char *)this + 168 == (char *)v37[0] )
  {
    v9 = -2147024809;
    Log_HREvent_48(2147942487LL, 0, v8, 347);
    LeaveCriticalSection(v6);
    return v9;
  }
  if ( **((_QWORD **)v37[0] + 5) )
    *a3 = 1;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( !*a3 )
  {
    v11 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
    v36 = 0;
    v33 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v12 = (void **)((char *)this + 136);
    utl::_Tree<_GUID,utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserMessageInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserMessageInfo>>>,GuidComparator,utl::allocator<utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserMessageInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserMessageInfo>>>>,0>::find<void>(
      (__int64)v12,
      v37,
      a2);
    if ( v12 == v37[0] )
    {
      v9 = -2147023728;
      v14 = 0;
      v15 = 2147943568LL;
      v16 = 368;
LABEL_15:
      Log_HREvent_48(v15, v14, v13, v16);
      LeaveCriticalSection(v11);
LABEL_31:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v36);
      return v9;
    }
    v17 = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown **, int *))(***((_QWORD ***)v37[0] + 5) + 32LL))(
            **((_QWORD **)v37[0] + 5),
            &v36,
            &v33);
    v9 = v17;
    if ( v17 < 0 )
    {
      v14 = 1;
      v16 = 369;
      v15 = (unsigned int)v17;
      goto LABEL_15;
    }
    LeaveCriticalSection(v11);
    if ( v33 )
    {
      v18 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v18 )
      {
        *v18 = 0;
        v18[1] = 0;
        *((_QWORD *)v18 + 4) = 0;
        v19 = (struct IUnknown **)RcsEndUserMessageTracker::RcsEndUserPacketInfo::RcsEndUserPacketInfo((RcsEndUserMessageTracker::RcsEndUserPacketInfo *)v18);
      }
      else
      {
        v19 = 0;
      }
      v35 = v19;
      if ( *v19 != v36 )
        ATL::AtlComPtrAssign(v19, v36);
      pguid = 0;
      v20 = CoCreateGuid(&pguid);
      v9 = v20;
      if ( v20 < 0 )
      {
        Log_HREvent_48((unsigned int)v20, 1, v21, 379);
LABEL_30:
        utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserPacketInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserPacketInfo>>::~unique_ptr<RcsEndUserMessageTracker::RcsEndUserPacketInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserPacketInfo>>(&v35);
        goto LABEL_31;
      }
      pv = 0;
      v22 = tlx::replace<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),0>(&pv);
      v23 = StringFromCLSID(&pguid, (LPOLESTR *)v22);
      v9 = v23;
      if ( v23 < 0 )
      {
        v25 = 1;
        v26 = 382;
        v27 = (unsigned int)v23;
        goto LABEL_28;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               v19 + 1,
                               pv) )
      {
        v9 = -2147024882;
        v25 = 0;
        v27 = 2147942414LL;
        v26 = 383;
LABEL_28:
        Log_HREvent_48(v27, v25, v24, v26);
        if ( pv )
          CoTaskMemFree(pv);
        goto LABEL_30;
      }
      EnterCriticalSection(v6);
      v28 = (char *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
      v37[0] = (void **)v28;
      v29 = v28;
      if ( v28 )
      {
        v30 = *a2;
        v35 = 0;
        v37[0] = 0;
        *(struct _GUID *)(v28 + 24) = v30;
        *((_QWORD *)v28 + 5) = v19;
      }
      utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserMessageInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserMessageInfo>>>>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserMessageInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserMessageInfo>>>>>>(v37);
      utl::_Tree<_GUID,utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserPacketInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserPacketInfo>>>,GuidComparator,utl::allocator<utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserPacketInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserPacketInfo>>>>,0>::_EmplaceImpl(
        v7,
        v37,
        v31,
        v29);
      LeaveCriticalSection(v6);
      v32 = pv;
      *a3 = 1;
      if ( v32 )
        CoTaskMemFree(v32);
      utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserPacketInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserPacketInfo>>::~unique_ptr<RcsEndUserMessageTracker::RcsEndUserPacketInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserPacketInfo>>(&v35);
    }
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v36);
  }
  return 0;
}

```

## disassembly

```asm
0x180091904  mov     [rsp-28h+arg_8], rbx
0x180091909  mov     [rsp-28h+arg_18], rsi
0x18009190e  push    rbp
0x18009190f  push    rdi
0x180091910  push    r12
0x180091912  push    r14
0x180091914  push    r15
0x180091916  mov     rbp, rsp
0x180091919  sub     rsp, 80h
0x180091920  mov     rax, cs:__security_cookie
0x180091927  xor     rax, rsp
0x18009192a  mov     [rbp+var_10], rax
0x18009192e  cmp     dword ptr [rcx+38h], 0
0x180091932  mov     rsi, r8
0x180091935  mov     r15, rdx
0x180091938  mov     rbx, rcx
0x18009193b  jz      short loc_180091948
0x18009193d  mov     r8d, 14Fh
0x180091943  call    Log_AssertionEvent_26
0x180091948  test    rsi, rsi
0x18009194b  jz      short loc_180091953
0x18009194d  mov     dword ptr [rsi], 0
0x180091953  lea     r14, [rbx+58h]
0x180091957  mov     rcx, r14; lpCriticalSection
0x18009195a  call    cs:__imp_EnterCriticalSection
0x180091960  lea     r12, [rbx+0A8h]
0x180091967  mov     r8, r15
0x18009196a  mov     rcx, r12
0x18009196d  lea     rdx, [rbp+var_30]
0x180091971  call    ??$find@X@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$unique_ptr@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@U?$default_delete@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@@utl@@@utl@@@utl@@UGuidComparator@@V?$allocator@U?$pair@$$CBU_GUID@@V?$unique_ptr@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@U?$default_delete@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@@utl@@@utl@@@utl@@@3@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBU_GUID@@V?$unique_ptr@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@U?$default_delete@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@@utl@@@utl@@@utl@@@1@AEBU_GUID@@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserMessageInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserMessageInfo>>>,GuidComparator,utl::allocator<utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserMessageInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserMessageInfo>>>>,0>::find<void>(_GUID const &)
0x180091976  mov     rax, [rbp+var_30]
0x18009197a  cmp     r12, rax
0x18009197d  jnz     short loc_1800919A3
0x18009197f  mov     ebx, 80070057h
0x180091984  xor     edx, edx
0x180091986  mov     ecx, ebx
0x180091988  mov     r9d, 15Bh
0x18009198e  call    Log_HREvent_48
0x180091993  mov     rcx, r14; lpCriticalSection
0x180091996  call    cs:__imp_LeaveCriticalSection
0x18009199c  mov     eax, ebx
0x18009199e  jmp     loc_180091BE5
0x1800919a3  mov     rcx, [rax+28h]
0x1800919a7  cmp     qword ptr [rcx], 0
0x1800919ab  jz      short loc_1800919B3
0x1800919ad  mov     dword ptr [rsi], 1
0x1800919b3  mov     rcx, r14; lpCriticalSection
0x1800919b6  call    cs:__imp_LeaveCriticalSection
0x1800919bc  cmp     dword ptr [rsi], 0
0x1800919bf  jnz     loc_180091BE3
0x1800919c5  lea     rdi, [rbx+10h]
0x1800919c9  mov     [rbp+var_38], 0
0x1800919d1  mov     rcx, rdi; lpCriticalSection
0x1800919d4  mov     [rbp+var_50], 0
0x1800919db  call    cs:__imp_EnterCriticalSection
0x1800919e1  add     rbx, 88h
0x1800919e8  lea     rdx, [rbp+var_30]
0x1800919ec  mov     rcx, rbx
0x1800919ef  mov     r8, r15
0x1800919f2  call    ??$find@X@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$unique_ptr@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@U?$default_delete@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@@utl@@@utl@@@utl@@UGuidComparator@@V?$allocator@U?$pair@$$CBU_GUID@@V?$unique_ptr@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@U?$default_delete@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@@utl@@@utl@@@utl@@@3@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBU_GUID@@V?$unique_ptr@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@U?$default_delete@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@@utl@@@utl@@@utl@@@1@AEBU_GUID@@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserMessageInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserMessageInfo>>>,GuidComparator,utl::allocator<utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserMessageInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserMessageInfo>>>>,0>::find<void>(_GUID const &)
0x1800919f7  mov     rax, [rbp+var_30]
0x1800919fb  cmp     rbx, rax
0x1800919fe  jnz     short loc_180091A11
0x180091a00  mov     ebx, 80070490h
0x180091a05  xor     edx, edx
0x180091a07  mov     ecx, ebx
0x180091a09  mov     r9d, 170h
0x180091a0f  jmp     short loc_180091A3F
0x180091a11  mov     rcx, [rax+28h]
0x180091a15  lea     r8, [rbp+var_50]
0x180091a19  lea     rdx, [rbp+var_38]
0x180091a1d  mov     rcx, [rcx]
0x180091a20  mov     rax, [rcx]
0x180091a23  mov     rax, [rax+20h]
0x180091a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091a2c  mov     ebx, eax
0x180091a2e  test    eax, eax
0x180091a30  jns     short loc_180091A52
0x180091a32  mov     edx, 1
0x180091a37  mov     r9d, 171h
0x180091a3d  mov     ecx, eax
0x180091a3f  call    Log_HREvent_48
0x180091a44  mov     rcx, rdi; lpCriticalSection
0x180091a47  call    cs:__imp_LeaveCriticalSection
0x180091a4d  jmp     loc_180091B4A
0x180091a52  mov     rcx, rdi; lpCriticalSection
0x180091a55  call    cs:__imp_LeaveCriticalSection
0x180091a5b  cmp     [rbp+var_50], 0
0x180091a5f  jz      loc_180091BDA
0x180091a65  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180091a6c  mov     ecx, 28h ; '('; unsigned __int64
0x180091a71  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180091a76  test    rax, rax
0x180091a79  jz      short loc_180091A98
0x180091a7b  xorps   xmm0, xmm0
0x180091a7e  xor     ecx, ecx
0x180091a80  movups  xmmword ptr [rax], xmm0
0x180091a83  movups  xmmword ptr [rax+10h], xmm0
0x180091a87  mov     [rax+20h], rcx
0x180091a8b  mov     rcx, rax; this
0x180091a8e  call    ??0RcsEndUserPacketInfo@RcsEndUserMessageTracker@@QEAA@XZ; RcsEndUserMessageTracker::RcsEndUserPacketInfo::RcsEndUserPacketInfo(void)
0x180091a93  mov     rdi, rax
0x180091a96  jmp     short loc_180091A9A
0x180091a98  xor     edi, edi
0x180091a9a  mov     rdx, [rbp+var_38]; struct IUnknown *
0x180091a9e  mov     [rbp+var_40], rdi
0x180091aa2  cmp     [rdi], rdx
0x180091aa5  jz      short loc_180091AAF
0x180091aa7  mov     rcx, rdi; struct IUnknown **
0x180091aaa  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180091aaf  xorps   xmm0, xmm0
0x180091ab2  lea     rcx, [rbp+pguid]; pguid
0x180091ab6  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x180091aba  call    cs:__imp_CoCreateGuid
0x180091ac0  mov     ebx, eax
0x180091ac2  test    eax, eax
0x180091ac4  jns     short loc_180091ADA
0x180091ac6  mov     edx, 1
0x180091acb  mov     r9d, 17Bh
0x180091ad1  mov     ecx, eax
0x180091ad3  call    Log_HREvent_48
0x180091ad8  jmp     short loc_180091B41
0x180091ada  lea     rcx, [rbp+pv]
0x180091ade  mov     [rbp+pv], 0
0x180091ae6  call    ??$replace@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(void *),&CoTaskMemFree(void *),0>(tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0> &)
0x180091aeb  mov     rdx, rax; lplpsz
0x180091aee  lea     rcx, [rbp+pguid]; rclsid
0x180091af2  call    cs:__imp_StringFromCLSID
0x180091af8  mov     ebx, eax
0x180091afa  test    eax, eax
0x180091afc  jns     short loc_180091B0D
0x180091afe  mov     edx, 1
0x180091b03  mov     r9d, 17Eh
0x180091b09  mov     ecx, eax
0x180091b0b  jmp     short loc_180091B2D
0x180091b0d  mov     rdx, [rbp+pv]
0x180091b11  lea     rcx, [rdi+8]
0x180091b15  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180091b1a  test    al, al
0x180091b1c  jnz     short loc_180091B58
0x180091b1e  mov     ebx, 8007000Eh
0x180091b23  xor     edx, edx
0x180091b25  mov     ecx, ebx
0x180091b27  mov     r9d, 17Fh
0x180091b2d  call    Log_HREvent_48
0x180091b32  mov     rcx, [rbp+pv]; pv
0x180091b36  test    rcx, rcx
0x180091b39  jz      short loc_180091B41
0x180091b3b  call    cs:__imp_CoTaskMemFree
0x180091b41  lea     rcx, [rbp+var_40]
0x180091b45  call    ??1?$unique_ptr@URcsEndUserPacketInfo@RcsEndUserMessageTracker@@U?$default_delete@URcsEndUserPacketInfo@RcsEndUserMessageTracker@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserPacketInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserPacketInfo>>::~unique_ptr<RcsEndUserMessageTracker::RcsEndUserPacketInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserPacketInfo>>(void)
0x180091b4a  lea     rcx, [rbp+var_38]
0x180091b4e  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180091b53  jmp     loc_18009199C
0x180091b58  mov     rcx, r14; lpCriticalSection
0x180091b5b  call    cs:__imp_EnterCriticalSection
0x180091b61  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180091b68  mov     ecx, 30h ; '0'; unsigned __int64
0x180091b6d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180091b72  mov     [rbp+var_30], rax
0x180091b76  mov     rbx, rax
0x180091b79  test    rax, rax
0x180091b7c  jz      short loc_180091B9B
0x180091b7e  movups  xmm0, xmmword ptr [r15]
0x180091b82  mov     [rbp+var_40], 0
0x180091b8a  mov     [rbp+var_30], 0
0x180091b92  movdqu  xmmword ptr [rax+18h], xmm0
0x180091b97  mov     [rax+28h], rdi
0x180091b9b  lea     rcx, [rbp+var_30]
0x180091b9f  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@U?$pair@$$CBU_GUID@@V?$unique_ptr@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@U?$default_delete@URcsEndUserMessageInfo@RcsEndUserMessageTracker@@@utl@@@utl@@@utl@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserMessageInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserMessageInfo>>>>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserMessageInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserMessageInfo>>>>>>(void)
0x180091ba4  mov     r9, rbx
0x180091ba7  lea     rdx, [rbp+var_30]
0x180091bab  mov     rcx, r12
0x180091bae  call    ?_EmplaceImpl@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$unique_ptr@URcsEndUserPacketInfo@RcsEndUserMessageTracker@@U?$default_delete@URcsEndUserPacketInfo@RcsEndUserMessageTracker@@@utl@@@utl@@@utl@@UGuidComparator@@V?$allocator@U?$pair@$$CBU_GUID@@V?$unique_ptr@URcsEndUserPacketInfo@RcsEndUserMessageTracker@@U?$default_delete@URcsEndUserPacketInfo@RcsEndUserMessageTracker@@@utl@@@utl@@@utl@@@3@$0A@@utl@@AEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBU_GUID@@V?$unique_ptr@URcsEndUserPacketInfo@RcsEndUserMessageTracker@@U?$default_delete@URcsEndUserPacketInfo@RcsEndUserMessageTracker@@@utl@@@utl@@@utl@@@utl@@_N@2@PEAU?$_TreeNode@U?$pair@$$CBU_GUID@@V?$unique_ptr@URcsEndUserPacketInfo@RcsEndUserMessageTracker@@U?$default_delete@URcsEndUserPacketInfo@RcsEndUserMessageTracker@@@utl@@@utl@@@utl@@@2@0@Z; utl::_Tree<_GUID,utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserPacketInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserPacketInfo>>>,GuidComparator,utl::allocator<utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserPacketInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserPacketInfo>>>>,0>::_EmplaceImpl(utl::_TreeNode<utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserPacketInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserPacketInfo>>>> *,utl::_TreeNode<utl::pair<_GUID const,utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserPacketInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserPacketInfo>>>> *)
0x180091bb3  mov     rcx, r14; lpCriticalSection
0x180091bb6  call    cs:__imp_LeaveCriticalSection
0x180091bbc  mov     rcx, [rbp+pv]; pv
0x180091bc0  mov     dword ptr [rsi], 1
0x180091bc6  test    rcx, rcx
0x180091bc9  jz      short loc_180091BD1
0x180091bcb  call    cs:__imp_CoTaskMemFree
0x180091bd1  lea     rcx, [rbp+var_40]
0x180091bd5  call    ??1?$unique_ptr@URcsEndUserPacketInfo@RcsEndUserMessageTracker@@U?$default_delete@URcsEndUserPacketInfo@RcsEndUserMessageTracker@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<RcsEndUserMessageTracker::RcsEndUserPacketInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserPacketInfo>>::~unique_ptr<RcsEndUserMessageTracker::RcsEndUserPacketInfo,utl::default_delete<RcsEndUserMessageTracker::RcsEndUserPacketInfo>>(void)
0x180091bda  lea     rcx, [rbp+var_38]
0x180091bde  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180091be3  xor     eax, eax
0x180091be5  mov     rcx, [rbp+var_10]
0x180091be9  xor     rcx, rsp; StackCookie
0x180091bec  call    __security_check_cookie
0x180091bf1  lea     r11, [rsp+80h+var_s0]
0x180091bf9  mov     rbx, [r11+38h]
0x180091bfd  mov     rsi, [r11+48h]
0x180091c01  mov     rsp, r11
0x180091c04  pop     r15
0x180091c06  pop     r14
0x180091c08  pop     r12
0x180091c0a  pop     rdi
0x180091c0b  pop     rbp
0x180091c0c  retn
```
