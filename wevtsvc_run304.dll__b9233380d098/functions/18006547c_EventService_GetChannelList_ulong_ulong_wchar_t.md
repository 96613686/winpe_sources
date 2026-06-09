# EventService::GetChannelList(ulong,ulong &,wchar_t * * &)

- ea: `0x18006547c`
- end: `0x180065824`
- name: `?GetChannelList@EventService@@QEAAXKAEAKAEAPEAPEA_W@Z`
- size: `936`
- prototype: `void __fastcall(EventService *__hidden this, unsigned int, unsigned int *, wchar_t ***)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, service_task`

## callers

- `0x1800a8750`

## callees

- `0x180006fb0`
- `0x18000bf10`
- `0x180017128`
- `0x180017b98`
- `0x18001c320`
- `0x18002de70`
- `0x18006547c`
- `0x18006582c`
- `0x180070498`
- `0x180083d50`
- `0x1800916a0`
- `0x180092008`
- `0x1800929b4`
- `0x18009aee0`
- `0x18009bb88`
- `0x1800a19d8`
- `0x1800c173c`
- `0x1800d334c`
- `0x1800d3370`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800654c9`
- `RPCRT4!RpcImpersonateClient` at `0x1800654c9`
- `RPCRT4!RpcRevertToSelf` at `0x1800656b0`
- `RPCRT4!RpcRevertToSelf` at `0x1800656b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall EventService::GetChannelList(RTL_SRWLOCK *this, __int64 a2, unsigned int *a3, wchar_t ***a4)
{
  unsigned int v6; // r14d
  unsigned int v7; // eax
  unsigned int v8; // ebx
  char *v9; // rdi
  __int64 v10; // r13
  void *v11; // rax
  int v12; // r14d
  void *v13; // rcx
  char v14; // al
  char v15; // bl
  __int64 v16; // rcx
  wchar_t *v17; // rbx
  unsigned __int64 v18; // rdi
  wchar_t **v19; // r8
  unsigned int i; // edx
  wchar_t *v21; // rax
  void *v22; // [rsp+20h] [rbp-E0h] BYREF
  int v23; // [rsp+28h] [rbp-D8h]
  const wchar_t *pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  char *v25; // [rsp+38h] [rbp-C8h]
  char *v26; // [rsp+40h] [rbp-C0h]
  unsigned int v27; // [rsp+48h] [rbp-B8h]
  int v28; // [rsp+4Ch] [rbp-B4h]
  int v29; // [rsp+50h] [rbp-B0h]
  char v30; // [rsp+54h] [rbp-ACh]
  __int128 v31; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h]
  int v33; // [rsp+70h] [rbp-90h]
  int v34; // [rsp+74h] [rbp-8Ch]
  int v35; // [rsp+78h] [rbp-88h]
  void *Src; // [rsp+80h] [rbp-80h]
  __m128i si128; // [rsp+90h] [rbp-70h] BYREF
  WCHAR *v38; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[512]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v42; // [rsp+2B8h] [rbp+1B8h]
  char v43; // [rsp+2C0h] [rbp+1C0h]

  v6 = 0;
  v23 = 0;
  EventService::WaitForInit(this);
  *a3 = 0;
  *a4 = 0;
  v7 = RpcImpersonateClient(0);
  v8 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v7);
    }
    pExceptionObject = &word_1800EC961;
    v25 = 0;
    v26 = 0;
    v27 = v8;
    v28 = -1;
    v29 = -1;
    v30 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  BYTE1(v23) = 1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffff0000000000000000);
  v38 = (WCHAR *)&pszFormat;
  v39 = 0;
  v40 = 0;
  memset_0(v41, 0, sizeof(v41));
  v42 = -1;
  v43 = 0;
  if ( ChannelConfigEnumerator::MoveFirstLegacy((ChannelConfigEnumerator *)&si128)
    || ChannelConfigEnumerator::MoveFirstGlobal((ChannelConfigEnumerator *)&si128) )
  {
    utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(&pExceptionObject);
    v9 = v25;
    while ( 1 )
    {
      Src = v38;
      v10 = v39;
      v11 = MIDL_user_allocate(saturated_mul(v39 + 1, 2u));
      v22 = v11;
      v12 = v6 | 1;
      if ( v9 == v26 )
      {
        v14 = utl::vector<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,utl::allocator<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>>::_PushBackOne2<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>(
                &pExceptionObject,
                &v22);
        v9 = v25;
        v13 = v22;
        if ( !v14 )
          goto LABEL_15;
      }
      else
      {
        v13 = 0;
        *(_QWORD *)v9 = v11;
        v9 += 8;
        v25 = v9;
      }
      if ( !*((_QWORD *)v9 - 1) )
      {
LABEL_15:
        v15 = 1;
        goto LABEL_16;
      }
      v15 = 0;
LABEL_16:
      v6 = v12 & 0xFFFFFFFE;
      if ( v13 )
        operator delete(v13);
      if ( v15 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
        }
        v31 = 0;
        v32 = 0;
        v33 = 14;
        v34 = -1;
        v35 = 2227;
        throw (EvtException *)&v31;
      }
      memcpy_0(*((void **)v9 - 1), Src, 2 * v10);
      *(_WORD *)(2 * v10 + *((_QWORD *)v9 - 1)) = 0;
      if ( !ChannelConfigEnumerator::MoveNext((ChannelConfigEnumerator *)&si128) )
      {
        v17 = (wchar_t *)pExceptionObject;
        if ( pExceptionObject == (const wchar_t *)v9 )
        {
          if ( pExceptionObject != (const wchar_t *)-1LL )
          {
            utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>>(
              v16,
              pExceptionObject,
              (v9 - (char *)pExceptionObject) >> 3);
            operator delete(v17);
          }
        }
        else
        {
          v18 = (v9 - (char *)pExceptionObject) >> 3;
          utl::make_unique_for_overwrite<wchar_t * [0],0>(&v22, v18);
          v19 = (wchar_t **)v22;
          if ( !v22 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
            }
            v31 = 0;
            v32 = 0;
            v33 = 14;
            v34 = -1;
            v35 = 2245;
            throw (EvtException *)&v31;
          }
          for ( i = 0; i < v18; ++i )
          {
            v21 = *(wchar_t **)&v17[4 * i];
            *(_QWORD *)&v17[4 * i] = 0;
            v19[i] = v21;
          }
          v22 = 0;
          *a4 = v19;
          *a3 = v18;
          utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v22);
          utl::vector<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,utl::allocator<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>>::_Uninit(&pExceptionObject);
        }
        break;
      }
    }
  }
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&si128);
  RpcRevertToSelf();
}

```

## disassembly

```asm
0x18006547c  mov     [rsp-8+arg_8], rbx
0x180065481  push    rbp
0x180065482  push    rsi
0x180065483  push    rdi
0x180065484  push    r12
0x180065486  push    r13
0x180065488  push    r14
0x18006548a  push    r15
0x18006548c  lea     rbp, [rsp-1E0h]
0x180065494  sub     rsp, 2E0h
0x18006549b  mov     rax, cs:__security_cookie
0x1800654a2  xor     rax, rsp
0x1800654a5  mov     [rbp+210h+var_40], rax
0x1800654ac  mov     r12, r9
0x1800654af  mov     r15, r8
0x1800654b2  xor     edi, edi
0x1800654b4  mov     r14d, edi
0x1800654b7  mov     [rsp+310h+var_2E8], edi
0x1800654bb  call    ?WaitForInit@EventService@@AEAAXXZ; EventService::WaitForInit(void)
0x1800654c0  mov     [r15], edi
0x1800654c3  mov     [r12], rdi
0x1800654c7  xor     ecx, ecx; BindingHandle
0x1800654c9  call    cs:__imp_RpcImpersonateClient
0x1800654cf  mov     ebx, eax
0x1800654d1  test    eax, eax
0x1800654d3  jz      short loc_18006554D
0x1800654d5  lea     rcx, WPP_GLOBAL_Control
0x1800654dc  mov     r10, cs:WPP_GLOBAL_Control
0x1800654e3  cmp     r10, rcx
0x1800654e6  jz      short loc_18006550C
0x1800654e8  test    byte ptr [r10+1Ch], 8
0x1800654ed  jz      short loc_18006550C
0x1800654ef  cmp     byte ptr [r10+19h], 2
0x1800654f4  jb      short loc_18006550C
0x1800654f6  lea     edx, [rdi+67h]
0x1800654f9  mov     r9d, eax
0x1800654fc  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180065503  mov     rcx, [r10+10h]
0x180065507  call    WPP_SF_d
0x18006550c  lea     rax, word_1800EC961
0x180065513  mov     [rsp+310h+pExceptionObject], rax
0x180065518  mov     [rsp+310h+var_2D8], rdi
0x18006551d  mov     [rsp+310h+var_2D0], rdi
0x180065522  mov     [rsp+310h+var_2C8], ebx
0x180065526  mov     [rsp+310h+var_2C4], 0FFFFFFFFh
0x18006552e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180065532  mov     [rsp+310h+var_2C0], esi
0x180065536  mov     [rsp+310h+var_2BC], dil
0x18006553b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180065542  lea     rcx, [rsp+310h+pExceptionObject]; pExceptionObject
0x180065547  call    _CxxThrowException_0
0x18006554d  mov     byte ptr [rsp+310h+var_2E8+1], 1
0x180065552  movdqa  xmm0, cs:__xmm@ffffffffffffffff0000000000000000
0x18006555a  movdqa  [rbp+210h+var_280], xmm0
0x18006555f  lea     rax, pszFormat
0x180065566  mov     [rbp+210h+var_270], rax
0x18006556a  mov     [rbp+210h+var_268], rdi
0x18006556e  mov     [rbp+210h+var_260], rdi
0x180065572  xor     edx, edx; Val
0x180065574  mov     r8d, 200h; Size
0x18006557a  lea     rcx, [rbp+210h+var_258]; void *
0x18006557e  call    memset_0
0x180065583  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180065587  mov     [rbp+210h+var_58], rsi
0x18006558e  mov     [rbp+210h+var_50], dil
0x180065595  lea     rcx, [rbp+210h+var_280]; this
0x180065599  call    ?MoveFirstLegacy@ChannelConfigEnumerator@@AEAA_NXZ; ChannelConfigEnumerator::MoveFirstLegacy(void)
0x18006559e  test    al, al
0x1800655a0  jnz     short loc_1800655B3
0x1800655a2  lea     rcx, [rbp+210h+var_280]; this
0x1800655a6  call    ?MoveFirstGlobal@ChannelConfigEnumerator@@AEAA_NXZ; ChannelConfigEnumerator::MoveFirstGlobal(void)
0x1800655ab  test    al, al
0x1800655ad  jz      loc_1800656A6
0x1800655b3  lea     rcx, [rsp+310h+pExceptionObject]; void *
0x1800655b8  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x1800655bd  nop
0x1800655be  mov     rdi, [rsp+310h+var_2D8]
0x1800655c3  mov     rax, [rbp+210h+var_270]
0x1800655c7  mov     [rbp+210h+Src], rax
0x1800655cb  mov     r13, [rbp+210h+var_268]
0x1800655cf  lea     rcx, [r13+1]
0x1800655d3  mov     eax, 2
0x1800655d8  mul     rcx
0x1800655db  cmovb   rax, rsi
0x1800655df  mov     rcx, rax; size
0x1800655e2  call    MIDL_user_allocate
0x1800655e7  mov     [rsp+310h+var_2F0], rax
0x1800655ec  or      r14d, 1
0x1800655f0  cmp     rdi, [rsp+310h+var_2D0]
0x1800655f5  jz      short loc_180065607
0x1800655f7  xor     ecx, ecx
0x1800655f9  mov     [rdi], rax
0x1800655fc  add     rdi, 8
0x180065600  mov     [rsp+310h+var_2D8], rdi
0x180065605  jmp     short loc_180065624
0x180065607  lea     rdx, [rsp+310h+var_2F0]
0x18006560c  lea     rcx, [rsp+310h+pExceptionObject]
0x180065611  call    ??$_PushBackOne2@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@?$vector@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@V?$allocator@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@2@@utl@@AEAA_N$$QEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@1@@Z; utl::vector<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,utl::allocator<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>>::_PushBackOne2<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&)
0x180065616  mov     rdi, [rsp+310h+var_2D8]
0x18006561b  mov     rcx, [rsp+310h+var_2F0]; void *
0x180065620  test    al, al
0x180065622  jz      short loc_18006562F
0x180065624  cmp     qword ptr [rdi-8], 0
0x180065629  jz      short loc_18006562F
0x18006562b  xor     bl, bl
0x18006562d  jmp     short loc_180065631
0x18006562f  mov     bl, 1
0x180065631  and     r14d, 0FFFFFFFEh
0x180065635  test    rcx, rcx
0x180065638  jz      short loc_18006563F
0x18006563a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006563f  test    bl, bl
0x180065641  jnz     loc_1800657B2
0x180065647  lea     rbx, ds:0[r13*2]
0x18006564f  mov     r8, rbx; Size
0x180065652  mov     rdx, [rbp+210h+Src]; Src
0x180065656  mov     rcx, [rdi-8]; void *
0x18006565a  call    memcpy_0
0x18006565f  mov     rcx, [rdi-8]
0x180065663  xor     r13d, r13d
0x180065666  mov     [rbx+rcx], r13w
0x18006566b  lea     rcx, [rbp+210h+var_280]; this
0x18006566f  call    ?MoveNext@ChannelConfigEnumerator@@QEAA_NXZ; ChannelConfigEnumerator::MoveNext(void)
0x180065674  test    al, al
0x180065676  jnz     loc_1800655C3
0x18006567c  mov     rbx, [rsp+310h+pExceptionObject]
0x180065681  cmp     rbx, rdi
0x180065684  jnz     short loc_1800656E0
0x180065686  cmp     rbx, rsi
0x180065689  jz      short loc_1800656A6
0x18006568b  sub     rdi, rbx
0x18006568e  sar     rdi, 3
0x180065692  mov     r8, rdi
0x180065695  mov     rdx, rbx
0x180065698  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@0@PEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>>(utl::allocator<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>> &,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,unsigned __int64)
0x18006569d  mov     rcx, rbx; void *
0x1800656a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800656a5  nop
0x1800656a6  lea     rcx, [rbp+210h+var_280]
0x1800656aa  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800656af  nop
0x1800656b0  call    cs:__imp_RpcRevertToSelf
0x1800656b6  mov     rcx, [rbp+210h+var_40]
0x1800656bd  xor     rcx, rsp; StackCookie
0x1800656c0  call    __security_check_cookie
0x1800656c5  mov     rbx, [rsp+310h+arg_8]
0x1800656cd  add     rsp, 2E0h
0x1800656d4  pop     r15
0x1800656d6  pop     r14
0x1800656d8  pop     r13
0x1800656da  pop     r12
0x1800656dc  pop     rdi
0x1800656dd  pop     rsi
0x1800656de  pop     rbp
0x1800656df  retn
0x1800656e0  sub     rdi, rbx
0x1800656e3  sar     rdi, 3
0x1800656e7  mov     rdx, rdi
0x1800656ea  lea     rcx, [rsp+310h+var_2F0]
0x1800656ef  call    ??$make_unique_for_overwrite@$$BY0A@PEA_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@PEA_WU?$default_delete@$$BY0A@PEA_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t * [0],0>(unsigned __int64)
0x1800656f4  nop
0x1800656f5  mov     r8, [rsp+310h+var_2F0]
0x1800656fa  test    r8, r8
0x1800656fd  jz      short loc_180065744
0x1800656ff  mov     edx, r13d
0x180065702  test    rdi, rdi
0x180065705  jz      short loc_18006571E
0x180065707  mov     ecx, edx
0x180065709  mov     rax, [rbx+rcx*8]
0x18006570d  mov     [rbx+rcx*8], r13
0x180065711  mov     [r8+rcx*8], rax
0x180065715  inc     edx
0x180065717  mov     eax, edx
0x180065719  cmp     rax, rdi
0x18006571c  jb      short loc_180065707
0x18006571e  mov     [rsp+310h+var_2F0], r13
0x180065723  mov     [r12], r8
0x180065727  mov     [r15], edi
0x18006572a  lea     rcx, [rsp+310h+var_2F0]
0x18006572f  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x180065734  nop
0x180065735  lea     rcx, [rsp+310h+pExceptionObject]
0x18006573a  call    ?_Uninit@?$vector@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@V?$allocator@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,utl::allocator<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>>>::_Uninit(void)
0x18006573f  jmp     loc_1800656A6
0x180065744  lea     rcx, WPP_GLOBAL_Control
0x18006574b  mov     ebx, 0Eh
0x180065750  mov     rax, cs:WPP_GLOBAL_Control
0x180065757  cmp     rax, rcx
0x18006575a  jz      short loc_18006577E
0x18006575c  test    byte ptr [rax+1Ch], 8
0x180065760  jz      short loc_18006577E
0x180065762  cmp     byte ptr [rax+19h], 2
0x180065766  jb      short loc_18006577E
0x180065768  lea     edx, [rbx+5Bh]
0x18006576b  mov     r9d, ebx
0x18006576e  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180065775  mov     rcx, [rax+10h]
0x180065779  call    WPP_SF_d
0x18006577e  xorps   xmm0, xmm0
0x180065781  movdqu  [rsp+310h+var_2B8], xmm0
0x180065787  mov     [rsp+310h+var_2A8], r13
0x18006578c  mov     [rsp+310h+var_2A0], ebx
0x180065790  mov     [rsp+310h+var_29C], 0FFFFFFFFh
0x180065798  mov     [rsp+310h+var_298], 8C5h
0x1800657a0  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800657a7  lea     rcx, [rsp+310h+var_2B8]; pExceptionObject
0x1800657ac  call    _CxxThrowException_0
0x1800657b2  lea     rcx, WPP_GLOBAL_Control
0x1800657b9  mov     ebx, 0Eh
0x1800657be  mov     rax, cs:WPP_GLOBAL_Control
0x1800657c5  cmp     rax, rcx
0x1800657c8  jz      short loc_1800657EC
0x1800657ca  test    byte ptr [rax+1Ch], 8
0x1800657ce  jz      short loc_1800657EC
0x1800657d0  cmp     byte ptr [rax+19h], 2
0x1800657d4  jb      short loc_1800657EC
0x1800657d6  lea     edx, [rbx+5Ah]
0x1800657d9  mov     r9d, ebx
0x1800657dc  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x1800657e3  mov     rcx, [rax+10h]
0x1800657e7  call    WPP_SF_d
0x1800657ec  xorps   xmm0, xmm0
0x1800657ef  movdqu  [rsp+310h+var_2B8], xmm0
0x1800657f5  mov     [rsp+310h+var_2A8], 0
0x1800657fe  mov     [rsp+310h+var_2A0], ebx
0x180065802  mov     [rsp+310h+var_29C], 0FFFFFFFFh
0x18006580a  mov     [rsp+310h+var_298], 8B3h
0x180065812  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180065819  lea     rcx, [rsp+310h+var_2B8]; pExceptionObject
0x18006581e  call    _CxxThrowException_0
```
