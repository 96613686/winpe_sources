# QueryLogCommand::PrintEventRenderedXml(void *,void *)

- ea: `0x14000b8e8`
- end: `0x14000bbc9`
- name: `?PrintEventRenderedXml@QueryLogCommand@@AEAAXPEAX0@Z`
- size: `737`
- prototype: `void(QueryLogCommand *__hidden this, void *, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c928`

## callees

- `0x14000b8e8`
- `0x14000cabc`
- `0x14000cfbc`
- `0x14000d144`
- `0x140010450`
- `0x1400163cc`
- `0x14001c0a8`
- `0x140021b00`
- `0x140022cec`
- `0x140027780`
- `0x1400293bc`
- `0x140031810`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall QueryLogCommand::PrintEventRenderedXml(QueryLogCommand *this, void *a2, void *a3)
{
  _QWORD *v5; // rbx
  unsigned int v6; // eax
  unsigned int v7; // esi
  const WCHAR *v8; // r9
  EVT_HANDLE v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // esi
  _BYTE *v12; // rdx
  _BYTE *v13; // rdx
  __int64 v14; // rax
  const char *v15; // [rsp+20h] [rbp-59h]
  int v16; // [rsp+20h] [rbp-59h]
  const char *v17; // [rsp+20h] [rbp-59h]
  _BYTE v18[4]; // [rsp+40h] [rbp-39h] BYREF
  DWORD v19[3]; // [rsp+44h] [rbp-35h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-29h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+60h] [rbp-19h] BYREF
  _OWORD v22[2]; // [rsp+88h] [rbp+Fh] BYREF

  v19[0] = 0;
  v5 = (_QWORD *)((char *)this + 200);
  v6 = RenderEvent(a3, a2, 0, v19);
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids, v6);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v7, 0, 0, v15, 395, 0x1Bu, 0);
    throw (EvtException *)pExceptionObject;
  }
  if ( v19[0] != 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids, 13);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, 0, 0, v15, 400, 0x1Bu, 0);
    throw (EvtException *)pExceptionObject;
  }
  v22[0] = 0;
  v22[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v22[0]) = 0;
  if ( *(_DWORD *)(*v5 + 12LL) == 1 && *(_QWORD *)*v5 )
    std::wstring::assign(v22);
  if ( *((_BYTE *)this + 256) )
  {
    v8 = (const WCHAR *)((char *)this + 40);
    if ( *((_QWORD *)this + 8) > 7u )
      v8 = *(const WCHAR **)v8;
  }
  else
  {
    v8 = 0;
  }
  v9 = QueryLogCommand::PublisherCache::Open(
         (_QWORD *)this + 28,
         *((void **)this + 3),
         (__int64)v22,
         v8,
         *((_DWORD *)this + 62));
  v10 = RenderMessage(v9, a2, 0xFFFFFFFF, v16, 9u, (__int64)v5);
  v11 = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids, v10);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v11, 0, 0, v17, 421, 0x1Bu, 0);
    throw (EvtException *)pExceptionObject;
  }
  v18[0] = 13;
  v12 = (_BYTE *)v5[1];
  if ( v12 == (_BYTE *)v5[2] )
  {
    std::vector<unsigned char>::_Emplace_reallocate<unsigned char>(v5, v12, v18);
  }
  else
  {
    *v12 = 13;
    ++v5[1];
  }
  v18[0] = 10;
  v13 = (_BYTE *)v5[1];
  if ( v13 == (_BYTE *)v5[2] )
  {
    std::vector<unsigned char>::_Emplace_reallocate<unsigned char>(v5, v13, v18);
  }
  else
  {
    *v13 = 10;
    ++v5[1];
  }
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(*v5 + 2 * v14) );
  v20[0] = *v5;
  v20[1] = v14;
  FilePuts(*((HANDLE *)this + 2), v20);
  std::wstring::_Tidy_deallocate(v22);
}

```

## disassembly

```asm
0x14000b8e8  mov     [rsp-8+arg_18], rbx
0x14000b8ed  push    rbp
0x14000b8ee  push    rsi
0x14000b8ef  push    rdi
0x14000b8f0  push    r14
0x14000b8f2  push    r15
0x14000b8f4  lea     rbp, [rsp-37h]
0x14000b8f9  sub     rsp, 0B0h
0x14000b900  mov     rax, cs:__security_cookie
0x14000b907  xor     rax, rsp
0x14000b90a  mov     [rbp+57h+var_28], rax
0x14000b90e  mov     rax, r8
0x14000b911  mov     r14, rdx
0x14000b914  mov     rdi, rcx
0x14000b917  xor     r15d, r15d
0x14000b91a  mov     [rbp+57h+var_8C], r15d
0x14000b91e  lea     rbx, [rcx+0C8h]
0x14000b925  lea     rcx, [rbp+57h+var_8C]
0x14000b929  mov     [rsp+0D0h+var_B0], rcx; char *
0x14000b92e  mov     r9, rbx
0x14000b931  xor     r8d, r8d; Flags
0x14000b934  mov     rcx, rax; Context
0x14000b937  call    ?RenderEvent@@YAKPEAX0KAEAV?$vector@EV?$allocator@E@std@@@std@@AEAK@Z; RenderEvent(void *,void *,ulong,std::vector<uchar> &,ulong &)
0x14000b93c  mov     esi, eax
0x14000b93e  test    eax, eax
0x14000b940  jz      short loc_14000B9B4
0x14000b942  lea     rcx, WPP_GLOBAL_Control
0x14000b949  mov     r10, cs:WPP_GLOBAL_Control
0x14000b950  cmp     r10, rcx
0x14000b953  jz      short loc_14000B97D
0x14000b955  test    dword ptr [r10+1Ch], 400000h
0x14000b95d  jz      short loc_14000B97D
0x14000b95f  cmp     byte ptr [r10+19h], 2
0x14000b964  jb      short loc_14000B97D
0x14000b966  lea     edx, [r15+1Bh]
0x14000b96a  mov     r9d, eax
0x14000b96d  lea     r8, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids
0x14000b974  mov     rcx, [r10+10h]
0x14000b978  call    WPP_SF_d
0x14000b97d  mov     [rsp+0D0h+Src], r15; Src
0x14000b982  mov     [rsp+0D0h+var_A0], 1Bh; unsigned int
0x14000b98a  mov     [rsp+0D0h+var_A8], 18Bh; int
0x14000b992  xor     r9d, r9d; unsigned int
0x14000b995  xor     r8d, r8d; unsigned int
0x14000b998  mov     edx, esi; unsigned int
0x14000b99a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14000b99e  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000b9a3  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000b9aa  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000b9ae  call    _CxxThrowException_0
0x14000b9b4  cmp     [rbp+57h+var_8C], 1
0x14000b9b8  jz      short loc_14000BA2E
0x14000b9ba  lea     rcx, WPP_GLOBAL_Control
0x14000b9c1  mov     rax, cs:WPP_GLOBAL_Control
0x14000b9c8  cmp     rax, rcx
0x14000b9cb  jz      short loc_14000B9F5
0x14000b9cd  test    dword ptr [rax+1Ch], 400000h
0x14000b9d4  jz      short loc_14000B9F5
0x14000b9d6  cmp     byte ptr [rax+19h], 2
0x14000b9da  jb      short loc_14000B9F5
0x14000b9dc  mov     edx, 1Ch
0x14000b9e1  lea     r9d, [rdx-0Fh]
0x14000b9e5  lea     r8, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids
0x14000b9ec  mov     rcx, [rax+10h]
0x14000b9f0  call    WPP_SF_d
0x14000b9f5  mov     [rsp+0D0h+Src], r15; Src
0x14000b9fa  mov     [rsp+0D0h+var_A0], 1Bh; unsigned int
0x14000ba02  mov     [rsp+0D0h+var_A8], 190h; int
0x14000ba0a  xor     r9d, r9d; unsigned int
0x14000ba0d  xor     r8d, r8d; unsigned int
0x14000ba10  lea     edx, [r9+0Dh]; unsigned int
0x14000ba14  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14000ba18  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000ba1d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000ba24  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000ba28  call    _CxxThrowException_0
0x14000ba2e  xorps   xmm0, xmm0
0x14000ba31  movups  [rbp+57h+var_48], xmm0
0x14000ba35  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14000ba3d  movdqu  [rbp+57h+var_38], xmm1
0x14000ba42  mov     word ptr [rbp+57h+var_48], r15w
0x14000ba47  mov     rdx, [rbx]
0x14000ba4a  cmp     dword ptr [rdx+0Ch], 1
0x14000ba4e  jnz     short loc_14000BA61
0x14000ba50  mov     rdx, [rdx]
0x14000ba53  test    rdx, rdx
0x14000ba56  jz      short loc_14000BA61
0x14000ba58  lea     rcx, [rbp+57h+var_48]
0x14000ba5c  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x14000ba61  mov     eax, [rdi+0F8h]
0x14000ba67  cmp     [rdi+100h], r15b
0x14000ba6e  jz      short loc_14000BA80
0x14000ba70  lea     r9, [rdi+28h]
0x14000ba74  cmp     qword ptr [r9+18h], 7
0x14000ba79  jbe     short loc_14000BA83
0x14000ba7b  mov     r9, [r9]
0x14000ba7e  jmp     short loc_14000BA83
0x14000ba80  mov     r9, r15
0x14000ba83  lea     rcx, [rdi+0E0h]
0x14000ba8a  mov     dword ptr [rsp+0D0h+var_B0], eax; char *
0x14000ba8e  lea     r8, [rbp+57h+var_48]
0x14000ba92  mov     rdx, [rdi+18h]
0x14000ba96  call    ?Open@PublisherCache@QueryLogCommand@@QEAAPEAXPEAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WK@Z; QueryLogCommand::PublisherCache::Open(void *,std::wstring const &,wchar_t const *,ulong)
0x14000ba9b  mov     qword ptr [rsp+0D0h+var_A0], rbx; __int64
0x14000baa0  mov     [rsp+0D0h+var_A8], 9; DWORD
0x14000baa8  or      r8d, 0FFFFFFFFh; MessageId
0x14000baac  mov     rdx, r14; Event
0x14000baaf  mov     rcx, rax; PublisherMetadata
0x14000bab2  call    ?RenderMessage@@YAKPEAX0KKPEAU_EVT_VARIANT@@KAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; RenderMessage(void *,void *,ulong,ulong,_EVT_VARIANT *,ulong,std::vector<uchar> &)
0x14000bab7  mov     esi, eax
0x14000bab9  test    eax, eax
0x14000babb  jz      short loc_14000BB30
0x14000babd  lea     rcx, WPP_GLOBAL_Control
0x14000bac4  mov     r10, cs:WPP_GLOBAL_Control
0x14000bacb  cmp     r10, rcx
0x14000bace  jz      short loc_14000BAF9
0x14000bad0  test    dword ptr [r10+1Ch], 400000h
0x14000bad8  jz      short loc_14000BAF9
0x14000bada  cmp     byte ptr [r10+19h], 2
0x14000badf  jb      short loc_14000BAF9
0x14000bae1  mov     edx, 1Dh
0x14000bae6  mov     r9d, eax
0x14000bae9  lea     r8, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids
0x14000baf0  mov     rcx, [r10+10h]
0x14000baf4  call    WPP_SF_d
0x14000baf9  mov     [rsp+0D0h+Src], r15; Src
0x14000bafe  mov     [rsp+0D0h+var_A0], 1Bh; unsigned int
0x14000bb06  mov     [rsp+0D0h+var_A8], 1A5h; int
0x14000bb0e  xor     r9d, r9d; unsigned int
0x14000bb11  xor     r8d, r8d; unsigned int
0x14000bb14  mov     edx, esi; unsigned int
0x14000bb16  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14000bb1a  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000bb1f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000bb26  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000bb2a  call    _CxxThrowException_0
0x14000bb30  mov     [rbp+57h+var_90], 0Dh
0x14000bb34  mov     rdx, [rbx+8]
0x14000bb38  cmp     rdx, [rbx+10h]
0x14000bb3c  jz      short loc_14000BB47
0x14000bb3e  mov     byte ptr [rdx], 0Dh
0x14000bb41  inc     qword ptr [rbx+8]
0x14000bb45  jmp     short loc_14000BB53
0x14000bb47  lea     r8, [rbp+57h+var_90]
0x14000bb4b  mov     rcx, rbx
0x14000bb4e  call    ??$_Emplace_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAE$$QEAE@Z; std::vector<uchar>::_Emplace_reallocate<uchar>(uchar * const,uchar &&)
0x14000bb53  mov     [rbp+57h+var_90], 0Ah
0x14000bb57  mov     rdx, [rbx+8]
0x14000bb5b  cmp     rdx, [rbx+10h]
0x14000bb5f  jz      short loc_14000BB6A
0x14000bb61  mov     byte ptr [rdx], 0Ah
0x14000bb64  inc     qword ptr [rbx+8]
0x14000bb68  jmp     short loc_14000BB76
0x14000bb6a  lea     r8, [rbp+57h+var_90]
0x14000bb6e  mov     rcx, rbx
0x14000bb71  call    ??$_Emplace_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAE$$QEAE@Z; std::vector<uchar>::_Emplace_reallocate<uchar>(uchar * const,uchar &&)
0x14000bb76  mov     rcx, [rbx]
0x14000bb79  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000bb7d  inc     rax
0x14000bb80  cmp     [rcx+rax*2], r15w
0x14000bb85  jnz     short loc_14000BB7D
0x14000bb87  mov     [rbp+57h+var_80], rcx
0x14000bb8b  mov     [rbp+57h+var_78], rax
0x14000bb8f  lea     rdx, [rbp+57h+var_80]
0x14000bb93  mov     rcx, [rdi+10h]; hFile
0x14000bb97  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x14000bb9c  nop
0x14000bb9d  lea     rcx, [rbp+57h+var_48]
0x14000bba1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000bba6  mov     rcx, [rbp+57h+var_28]
0x14000bbaa  xor     rcx, rsp; StackCookie
0x14000bbad  call    __security_check_cookie
0x14000bbb2  mov     rbx, [rsp+0D0h+arg_18]
0x14000bbba  add     rsp, 0B0h
0x14000bbc1  pop     r15
0x14000bbc3  pop     r14
0x14000bbc5  pop     rdi
0x14000bbc6  pop     rsi
0x14000bbc7  pop     rbp
0x14000bbc8  retn
```
