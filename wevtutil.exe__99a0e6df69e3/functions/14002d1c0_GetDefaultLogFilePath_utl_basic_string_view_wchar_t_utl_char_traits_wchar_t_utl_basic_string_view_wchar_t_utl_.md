# GetDefaultLogFilePath(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_EVT_CHANNEL_TYPE,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x14002d1c0`
- end: `0x14002d5f0`
- name: `?GetDefaultLogFilePath@@YAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0W4_EVT_CHANNEL_TYPE@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@2@@Z`
- size: `1072`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1400158b4`

## callees

- `0x140007310`
- `0x140007db0`
- `0x14000d6e8`
- `0x14001a9b8`
- `0x140022cec`
- `0x14002d1c0`
- `0x14002d5f8`
- `0x14002f6c8`
- `0x140031810`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14002d24d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14002d3f6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14002d24d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14002d3f6`

## pseudocode

```c
__int64 __fastcall GetDefaultLogFilePath(wchar_t **a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r12
  wchar_t *v6; // rdi
  __int64 *v9; // rax
  __int64 v10; // rcx
  const char *v11; // r8
  wchar_t *v12; // rbx
  wchar_t *v13; // rdi
  wchar_t v14; // r15
  wchar_t *v15; // r14
  const char *v16; // r8
  const char *v17; // r8
  const char *v18; // r8
  wchar_t *v19; // rbx
  __int64 v20; // rdi
  wchar_t v21; // r15
  wchar_t *v22; // r14
  const char *v23; // r8
  const char *v24; // r8
  __int64 result; // rax
  const char *v26; // r8
  __int128 v27; // [rsp+20h] [rbp-48h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF

  v4 = *(_QWORD *)(a2 + 8);
  v6 = a1[1];
  v9 = tlx::_LazyImpl<RegistryDefaultLogFolder,tlx::lazy_construct<RegistryDefaultLogFolder>,tlx::static_lazy<RegistryDefaultLogFolder,0,tlx::lazy_construct<RegistryDefaultLogFolder>>>::get((__int64)a1);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(
                           a4,
                           (char *)v6 + v9[5] + v4 + 7)
    || (v27 = *((_OWORD *)tlx::_LazyImpl<RegistryDefaultLogFolder,tlx::lazy_construct<RegistryDefaultLogFolder>,tlx::static_lazy<RegistryDefaultLogFolder,0,tlx::lazy_construct<RegistryDefaultLogFolder>>>::get(v10)
              + 2),
        !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a4, &v27)) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_e943c25bf51636622b146f078f7404e1_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v11, 173);
    throw (EvtException *)pExceptionObject;
  }
  v12 = *a1;
  v13 = &v12[(_QWORD)v6];
  while ( v12 != v13 )
  {
    v14 = *v12;
    v15 = wcschr(L"<>:\"/\\|%*?", *v12);
    if ( v15 )
    {
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                               a4,
                               37)
        || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                               a4,
                               (unsigned int)(v15 - L"<>:\"/\\|%*?") + 48) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_e943c25bf51636622b146f078f7404e1_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v17, 192);
        throw (EvtException *)pExceptionObject;
      }
    }
    else if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                  a4,
                                  v14) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_e943c25bf51636622b146f078f7404e1_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v16, 183);
      throw (EvtException *)pExceptionObject;
    }
    ++v12;
  }
  if ( v4 )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             a4,
                             95) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_e943c25bf51636622b146f078f7404e1_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v18, 201);
      throw (EvtException *)pExceptionObject;
    }
    v19 = *(wchar_t **)a2;
    v20 = *(_QWORD *)a2 + 2 * v4;
    while ( v19 != (wchar_t *)v20 )
    {
      v21 = *v19;
      if ( *v19 )
      {
        v22 = wcschr(L"<>:\"/\\|%*?", v21);
        if ( v22 )
        {
          if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                   a4,
                                   37)
            || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                   a4,
                                   (unsigned int)(v22 - L"<>:\"/\\|%*?") + 48) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_e943c25bf51636622b146f078f7404e1_Traceguids, 14);
            }
            EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v24, 225);
            throw (EvtException *)pExceptionObject;
          }
        }
        else if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                      a4,
                                      v21) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_e943c25bf51636622b146f078f7404e1_Traceguids, 14);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v23, 216);
          throw (EvtException *)pExceptionObject;
        }
      }
      ++v19;
    }
  }
  result = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(a4, L".evtx", 5);
  if ( !(_BYTE)result )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_e943c25bf51636622b146f078f7404e1_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v26, 242);
    throw (EvtException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x14002d1c0  push    rbp
0x14002d1c2  push    rbx
0x14002d1c3  push    rsi
0x14002d1c4  push    rdi
0x14002d1c5  push    r12
0x14002d1c7  push    r13
0x14002d1c9  push    r14
0x14002d1cb  push    r15
0x14002d1cd  mov     rbp, rsp
0x14002d1d0  sub     rsp, 68h
0x14002d1d4  mov     r12, [rdx+8]
0x14002d1d8  mov     rsi, r9
0x14002d1db  mov     rdi, [rcx+8]
0x14002d1df  mov     r13, rdx
0x14002d1e2  mov     rbx, rcx
0x14002d1e5  call    ?get@?$_LazyImpl@VRegistryDefaultLogFolder@@V?$lazy_construct@VRegistryDefaultLogFolder@@@tlx@@V?$static_lazy@VRegistryDefaultLogFolder@@$0A@V?$lazy_construct@VRegistryDefaultLogFolder@@@tlx@@@3@@tlx@@QEAAAEAVRegistryDefaultLogFolder@@XZ; tlx::_LazyImpl<RegistryDefaultLogFolder,tlx::lazy_construct<RegistryDefaultLogFolder>,tlx::static_lazy<RegistryDefaultLogFolder,0,tlx::lazy_construct<RegistryDefaultLogFolder>>>::get(void)
0x14002d1ea  lea     rdx, [r12+7]
0x14002d1ef  mov     rcx, rsi
0x14002d1f2  mov     r8, [rax+28h]
0x14002d1f6  add     r8, rdi
0x14002d1f9  add     rdx, r8
0x14002d1fc  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x14002d201  test    al, al
0x14002d203  jz      loc_14002D583
0x14002d209  call    ?get@?$_LazyImpl@VRegistryDefaultLogFolder@@V?$lazy_construct@VRegistryDefaultLogFolder@@@tlx@@V?$static_lazy@VRegistryDefaultLogFolder@@$0A@V?$lazy_construct@VRegistryDefaultLogFolder@@@tlx@@@3@@tlx@@QEAAAEAVRegistryDefaultLogFolder@@XZ; tlx::_LazyImpl<RegistryDefaultLogFolder,tlx::lazy_construct<RegistryDefaultLogFolder>,tlx::static_lazy<RegistryDefaultLogFolder,0,tlx::lazy_construct<RegistryDefaultLogFolder>>>::get(void)
0x14002d20e  lea     rdx, [rbp+var_48]
0x14002d212  mov     rcx, rsi
0x14002d215  movups  xmm0, xmmword ptr [rax+20h]
0x14002d219  movdqu  [rbp+var_48], xmm0
0x14002d21e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14002d223  test    al, al
0x14002d225  jz      loc_14002D583
0x14002d22b  mov     rbx, [rbx]
0x14002d22e  lea     rdi, [rbx+rdi*2]
0x14002d232  lea     r14, Str; "<>:\"/\\|%*?"
0x14002d239  cmp     rbx, rdi
0x14002d23c  jz      loc_14002D35A
0x14002d242  movzx   r15d, word ptr [rbx]
0x14002d246  mov     rcx, r14; Str
0x14002d249  movzx   edx, r15w; Ch
0x14002d24d  call    cs:__imp_wcschr
0x14002d253  mov     r14, rax
0x14002d256  mov     rcx, rsi
0x14002d259  test    rax, rax
0x14002d25c  jnz     short loc_14002D2CA
0x14002d25e  movzx   edx, r15w
0x14002d262  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14002d267  test    al, al
0x14002d269  jnz     loc_14002D2F5
0x14002d26f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d276  lea     rax, WPP_GLOBAL_Control
0x14002d27d  lea     ebx, [r14+0Eh]
0x14002d281  cmp     rcx, rax
0x14002d284  jz      short loc_14002D2A8
0x14002d286  test    byte ptr [rcx+1Ch], 4
0x14002d28a  jz      short loc_14002D2A8
0x14002d28c  cmp     byte ptr [rcx+19h], 2
0x14002d290  jb      short loc_14002D2A8
0x14002d292  mov     rcx, [rcx+10h]
0x14002d296  lea     edx, [rbx+6]
0x14002d299  mov     r9d, ebx
0x14002d29c  lea     r8, WPP_e943c25bf51636622b146f078f7404e1_Traceguids
0x14002d2a3  call    WPP_SF_d
0x14002d2a8  mov     r9d, 0B7h; int
0x14002d2ae  lea     rcx, [rbp+pExceptionObject]; this
0x14002d2b2  mov     edx, ebx; unsigned int
0x14002d2b4  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002d2b9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002d2c0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14002d2c4  call    _CxxThrowException_0
0x14002d2ca  mov     edx, 25h ; '%'
0x14002d2cf  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14002d2d4  test    al, al
0x14002d2d6  jz      short loc_14002D2FE
0x14002d2d8  lea     rax, Str; "<>:\"/\\|%*?"
0x14002d2df  mov     rcx, rsi
0x14002d2e2  sub     r14, rax
0x14002d2e5  sar     r14, 1
0x14002d2e8  lea     edx, [r14+30h]
0x14002d2ec  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14002d2f1  test    al, al
0x14002d2f3  jz      short loc_14002D2FE
0x14002d2f5  add     rbx, 2
0x14002d2f9  jmp     loc_14002D232
0x14002d2fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d305  lea     rax, WPP_GLOBAL_Control
0x14002d30c  mov     ebx, 0Eh
0x14002d311  cmp     rcx, rax
0x14002d314  jz      short loc_14002D338
0x14002d316  test    byte ptr [rcx+1Ch], 4
0x14002d31a  jz      short loc_14002D338
0x14002d31c  cmp     byte ptr [rcx+19h], 2
0x14002d320  jb      short loc_14002D338
0x14002d322  mov     rcx, [rcx+10h]
0x14002d326  lea     edx, [rbx+7]
0x14002d329  mov     r9d, ebx
0x14002d32c  lea     r8, WPP_e943c25bf51636622b146f078f7404e1_Traceguids
0x14002d333  call    WPP_SF_d
0x14002d338  mov     r9d, 0C0h; int
0x14002d33e  lea     rcx, [rbp+pExceptionObject]; this
0x14002d342  mov     edx, ebx; unsigned int
0x14002d344  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002d349  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002d350  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14002d354  call    _CxxThrowException_0
0x14002d35a  test    r12, r12
0x14002d35d  jz      loc_14002D50A
0x14002d363  mov     edx, 5Fh ; '_'
0x14002d368  mov     rcx, rsi
0x14002d36b  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14002d370  test    al, al
0x14002d372  jnz     short loc_14002D3D0
0x14002d374  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d37b  lea     rax, WPP_GLOBAL_Control
0x14002d382  mov     ebx, 0Eh
0x14002d387  cmp     rcx, rax
0x14002d38a  jz      short loc_14002D3AE
0x14002d38c  test    byte ptr [rcx+1Ch], 4
0x14002d390  jz      short loc_14002D3AE
0x14002d392  cmp     byte ptr [rcx+19h], 2
0x14002d396  jb      short loc_14002D3AE
0x14002d398  mov     rcx, [rcx+10h]
0x14002d39c  lea     edx, [rbx+8]
0x14002d39f  mov     r9d, ebx
0x14002d3a2  lea     r8, WPP_e943c25bf51636622b146f078f7404e1_Traceguids
0x14002d3a9  call    WPP_SF_d
0x14002d3ae  mov     r9d, 0C9h; int
0x14002d3b4  lea     rcx, [rbp+pExceptionObject]; this
0x14002d3b8  mov     edx, ebx; unsigned int
0x14002d3ba  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002d3bf  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002d3c6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14002d3ca  call    _CxxThrowException_0
0x14002d3d0  mov     rbx, [r13+0]
0x14002d3d4  lea     rdi, [rbx+r12*2]
0x14002d3d8  cmp     rbx, rdi
0x14002d3db  jz      loc_14002D50A
0x14002d3e1  movzx   r15d, word ptr [rbx]
0x14002d3e5  test    r15w, r15w
0x14002d3e9  jz      loc_14002D4A5
0x14002d3ef  movzx   edx, r15w; Ch
0x14002d3f3  mov     rcx, r14; Str
0x14002d3f6  call    cs:__imp_wcschr
0x14002d3fc  mov     r14, rax
0x14002d3ff  mov     rcx, rsi
0x14002d402  test    rax, rax
0x14002d405  jnz     short loc_14002D473
0x14002d407  movzx   edx, r15w
0x14002d40b  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14002d410  test    al, al
0x14002d412  jnz     loc_14002D49E
0x14002d418  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d41f  lea     rax, WPP_GLOBAL_Control
0x14002d426  lea     ebx, [r14+0Eh]
0x14002d42a  cmp     rcx, rax
0x14002d42d  jz      short loc_14002D451
0x14002d42f  test    byte ptr [rcx+1Ch], 4
0x14002d433  jz      short loc_14002D451
0x14002d435  cmp     byte ptr [rcx+19h], 2
0x14002d439  jb      short loc_14002D451
0x14002d43b  mov     rcx, [rcx+10h]
0x14002d43f  lea     edx, [rbx+9]
0x14002d442  mov     r9d, ebx
0x14002d445  lea     r8, WPP_e943c25bf51636622b146f078f7404e1_Traceguids
0x14002d44c  call    WPP_SF_d
0x14002d451  mov     r9d, 0D8h; int
0x14002d457  lea     rcx, [rbp+pExceptionObject]; this
0x14002d45b  mov     edx, ebx; unsigned int
0x14002d45d  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002d462  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002d469  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14002d46d  call    _CxxThrowException_0
0x14002d473  mov     edx, 25h ; '%'
0x14002d478  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14002d47d  test    al, al
0x14002d47f  jz      short loc_14002D4AE
0x14002d481  lea     rax, Str; "<>:\"/\\|%*?"
0x14002d488  mov     rcx, rsi
0x14002d48b  sub     r14, rax
0x14002d48e  sar     r14, 1
0x14002d491  lea     edx, [r14+30h]
0x14002d495  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14002d49a  test    al, al
0x14002d49c  jz      short loc_14002D4AE
0x14002d49e  lea     r14, Str; "<>:\"/\\|%*?"
0x14002d4a5  add     rbx, 2
0x14002d4a9  jmp     loc_14002D3D8
0x14002d4ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d4b5  lea     rax, WPP_GLOBAL_Control
0x14002d4bc  mov     ebx, 0Eh
0x14002d4c1  cmp     rcx, rax
0x14002d4c4  jz      short loc_14002D4E8
0x14002d4c6  test    byte ptr [rcx+1Ch], 4
0x14002d4ca  jz      short loc_14002D4E8
0x14002d4cc  cmp     byte ptr [rcx+19h], 2
0x14002d4d0  jb      short loc_14002D4E8
0x14002d4d2  mov     rcx, [rcx+10h]
0x14002d4d6  lea     edx, [rbx+0Ah]
0x14002d4d9  mov     r9d, ebx
0x14002d4dc  lea     r8, WPP_e943c25bf51636622b146f078f7404e1_Traceguids
0x14002d4e3  call    WPP_SF_d
0x14002d4e8  mov     r9d, 0E1h; int
0x14002d4ee  lea     rcx, [rbp+pExceptionObject]; this
0x14002d4f2  mov     edx, ebx; unsigned int
0x14002d4f4  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002d4f9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002d500  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14002d504  call    _CxxThrowException_0
0x14002d50a  mov     r8d, 5
0x14002d510  lea     rdx, aEvtx; ".evtx"
0x14002d517  mov     rcx, rsi
0x14002d51a  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14002d51f  test    al, al
0x14002d521  jnz     loc_14002D5DF
0x14002d527  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d52e  lea     rax, WPP_GLOBAL_Control
0x14002d535  mov     ebx, 0Eh
0x14002d53a  cmp     rcx, rax
0x14002d53d  jz      short loc_14002D561
0x14002d53f  test    byte ptr [rcx+1Ch], 4
0x14002d543  jz      short loc_14002D561
0x14002d545  cmp     byte ptr [rcx+19h], 2
0x14002d549  jb      short loc_14002D561
0x14002d54b  mov     rcx, [rcx+10h]
0x14002d54f  lea     edx, [rbx+0Ch]
0x14002d552  mov     r9d, ebx
0x14002d555  lea     r8, WPP_e943c25bf51636622b146f078f7404e1_Traceguids
0x14002d55c  call    WPP_SF_d
0x14002d561  mov     r9d, 0F2h; int
0x14002d567  lea     rcx, [rbp+pExceptionObject]; this
0x14002d56b  mov     edx, ebx; unsigned int
0x14002d56d  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002d572  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002d579  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14002d57d  call    _CxxThrowException_0
0x14002d583  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d58a  lea     rax, WPP_GLOBAL_Control
0x14002d591  mov     ebx, 0Eh
0x14002d596  cmp     rcx, rax
0x14002d599  jz      short loc_14002D5BD
0x14002d59b  test    byte ptr [rcx+1Ch], 4
0x14002d59f  jz      short loc_14002D5BD
0x14002d5a1  cmp     byte ptr [rcx+19h], 2
0x14002d5a5  jb      short loc_14002D5BD
0x14002d5a7  mov     rcx, [rcx+10h]
0x14002d5ab  lea     edx, [rbx+5]
0x14002d5ae  mov     r9d, ebx
0x14002d5b1  lea     r8, WPP_e943c25bf51636622b146f078f7404e1_Traceguids
0x14002d5b8  call    WPP_SF_d
0x14002d5bd  mov     r9d, 0ADh; int
0x14002d5c3  lea     rcx, [rbp+pExceptionObject]; this
0x14002d5c7  mov     edx, ebx; unsigned int
0x14002d5c9  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002d5ce  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002d5d5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14002d5d9  call    _CxxThrowException_0
0x14002d5df  add     rsp, 68h
0x14002d5e3  pop     r15
0x14002d5e5  pop     r14
0x14002d5e7  pop     r13
0x14002d5e9  pop     r12
0x14002d5eb  pop     rdi
0x14002d5ec  pop     rsi
0x14002d5ed  pop     rbx
0x14002d5ee  pop     rbp
0x14002d5ef  retn
```
