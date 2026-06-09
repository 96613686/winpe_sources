# ChannelConfigReader::GetLogFilePath(void)

- ea: `0x1400158b4`
- end: `0x140015ab9`
- name: `?GetLogFilePath@ChannelConfigReader@@QEBA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@XZ`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1400073ec`

## callees

- `0x140005600`
- `0x140005620`
- `0x140006cd0`
- `0x1400158b4`
- `0x140016284`
- `0x140022cec`
- `0x14002d1c0`
- `0x14002f6c8`
- `0x140031810`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ChannelConfigReader::GetLogFilePath(_QWORD *a1, __int64 a2)
{
  int *v4; // rax
  int *v5; // rcx
  int *v6; // rdx
  __int64 v7; // r8
  const char *v8; // r8
  unsigned int StringValueNoThrow; // esi
  const char *v10; // r8
  wchar_t *v11; // rcx
  __int64 v12; // rax
  wchar_t *v14[2]; // [rsp+20h] [rbp-50h] BYREF
  __int128 v15; // [rsp+30h] [rbp-40h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+40h] [rbp-30h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(a2);
  if ( *((_BYTE *)a1 + 128) )
  {
    v4 = (int *)(a1 + 8);
    if ( (_QWORD *)a1[10] != a1 + 8 )
    {
      v5 = (int *)(a1 + 8);
      v6 = *(int **)v4;
      do
      {
        if ( v6[6] >= 9 )
        {
          v5 = v6;
          v7 = 2;
        }
        else
        {
          v7 = 4;
        }
        v6 = *(int **)&v6[v7];
      }
      while ( v6 != (int *)&utl::_TreeSentinel );
      if ( v5 != v4 && v5[6] <= 9 && v5 != (int *)-32LL )
      {
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                 a2,
                                 *((_QWORD *)v5 + 4),
                                 (unsigned int)v5[10]) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 14);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v8, 287);
          throw (EvtException *)pExceptionObject;
        }
        return a2;
      }
    }
  }
  StringValueNoThrow = RegReadStringValueNoThrow((HKEY)*a1, 0, L"File", a2);
  if ( StringValueNoThrow == 2 )
  {
    v11 = (wchar_t *)a1[4];
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
LABEL_31:
    v14[0] = v11;
    v15 = 0;
    v14[1] = (wchar_t *)v12;
    GetDefaultLogFilePath(v14, (__int64)&v15, (__int64)v10, a2);
    return a2;
  }
  if ( StringValueNoThrow )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids,
        StringValueNoThrow);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, StringValueNoThrow, v10, 304);
    throw (EvtException *)pExceptionObject;
  }
  if ( *((_BYTE *)a1 + 140) == 1 && (GetDWORDHelper(*a1, 0, L"Flags") & 1) == 0 )
  {
    v11 = (wchar_t *)a1[4];
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    goto LABEL_31;
  }
  return a2;
}

```

## disassembly

```asm
0x1400158b4  mov     [rsp-18h+arg_10], rbx
0x1400158b9  mov     [rsp-18h+arg_18], rsi
0x1400158be  mov     [rsp-18h+arg_8], rdx
0x1400158c3  push    rbp
0x1400158c4  push    rdi
0x1400158c5  push    r14
0x1400158c7  mov     rbp, rsp
0x1400158ca  sub     rsp, 70h
0x1400158ce  mov     rdi, rdx
0x1400158d1  mov     rbx, rcx
0x1400158d4  mov     [rbp+arg_0], 1
0x1400158db  mov     rcx, rdx
0x1400158de  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400158e3  nop
0x1400158e4  mov     [rbp+arg_0], 1
0x1400158eb  xor     r14d, r14d
0x1400158ee  cmp     [rbx+80h], r14b
0x1400158f5  jz      loc_1400159C1
0x1400158fb  lea     rax, [rbx+40h]
0x1400158ff  cmp     [rax+10h], rax
0x140015903  jz      loc_1400159C1
0x140015909  mov     rcx, rax
0x14001590c  mov     rdx, [rax]
0x14001590f  cmp     dword ptr [rdx+18h], 9
0x140015913  jge     short loc_14001591D
0x140015915  mov     r8d, 10h
0x14001591b  jmp     short loc_140015926
0x14001591d  mov     rcx, rdx
0x140015920  mov     r8d, 8
0x140015926  mov     rdx, [r8+rdx]
0x14001592a  lea     r8, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140015931  cmp     rdx, r8
0x140015934  jnz     short loc_14001590F
0x140015936  cmp     rcx, rax
0x140015939  jz      loc_1400159C1
0x14001593f  cmp     dword ptr [rcx+18h], 9
0x140015943  jg      short loc_1400159C1
0x140015945  lea     rdx, [rcx+20h]
0x140015949  test    rdx, rdx
0x14001594c  jz      short loc_1400159C1
0x14001594e  mov     r8d, [rdx+8]
0x140015952  mov     rdx, [rdx]
0x140015955  mov     rcx, rdi
0x140015958  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14001595d  test    al, al
0x14001595f  jnz     loc_140015AA1
0x140015965  lea     rax, WPP_GLOBAL_Control
0x14001596c  mov     ebx, 0Eh
0x140015971  mov     rcx, cs:WPP_GLOBAL_Control
0x140015978  cmp     rcx, rax
0x14001597b  jz      short loc_14001599F
0x14001597d  test    byte ptr [rcx+1Ch], 4
0x140015981  jz      short loc_14001599F
0x140015983  cmp     byte ptr [rcx+19h], 2
0x140015987  jb      short loc_14001599F
0x140015989  lea     edx, [rbx+11h]
0x14001598c  mov     r9d, ebx
0x14001598f  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x140015996  mov     rcx, [rcx+10h]
0x14001599a  call    WPP_SF_d
0x14001599f  mov     r9d, 11Fh; int
0x1400159a5  mov     edx, ebx; unsigned int
0x1400159a7  lea     rcx, [rbp+pExceptionObject]; this
0x1400159ab  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x1400159b0  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400159b7  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400159bb  call    _CxxThrowException_0
0x1400159c1  mov     r9, rdi
0x1400159c4  lea     r8, aFile; "File"
0x1400159cb  xor     edx, edx
0x1400159cd  mov     rcx, [rbx]; hKey
0x1400159d0  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1400159d5  mov     esi, eax
0x1400159d7  cmp     eax, 2
0x1400159da  jnz     short loc_1400159F3
0x1400159dc  mov     rcx, [rbx+20h]
0x1400159e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400159e4  inc     rax
0x1400159e7  cmp     [rcx+rax*2], r14w
0x1400159ec  jnz     short loc_1400159E4
0x1400159ee  jmp     loc_140015A80
0x1400159f3  test    esi, esi
0x1400159f5  jz      short loc_140015A50
0x1400159f7  lea     rax, WPP_GLOBAL_Control
0x1400159fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140015a05  cmp     rcx, rax
0x140015a08  jz      short loc_140015A2E
0x140015a0a  test    byte ptr [rcx+1Ch], 4
0x140015a0e  jz      short loc_140015A2E
0x140015a10  cmp     byte ptr [rcx+19h], 2
0x140015a14  jb      short loc_140015A2E
0x140015a16  mov     edx, 20h ; ' '
0x140015a1b  mov     r9d, esi
0x140015a1e  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x140015a25  mov     rcx, [rcx+10h]
0x140015a29  call    WPP_SF_d
0x140015a2e  mov     r9d, 130h; int
0x140015a34  mov     edx, esi; unsigned int
0x140015a36  lea     rcx, [rbp+pExceptionObject]; this
0x140015a3a  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140015a3f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140015a46  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140015a4a  call    _CxxThrowException_0
0x140015a50  cmp     byte ptr [rbx+8Ch], 1
0x140015a57  jnz     short loc_140015AA1
0x140015a59  lea     r8, aFlags; "Flags"
0x140015a60  xor     edx, edx
0x140015a62  mov     rcx, [rbx]
0x140015a65  call    GetDWORDHelper
0x140015a6a  test    al, 1
0x140015a6c  jnz     short loc_140015AA1
0x140015a6e  mov     rcx, [rbx+20h]
0x140015a72  or      rax, 0FFFFFFFFFFFFFFFFh
0x140015a76  inc     rax
0x140015a79  cmp     [rcx+rax*2], r14w
0x140015a7e  jnz     short loc_140015A76
0x140015a80  xorps   xmm0, xmm0
0x140015a83  mov     [rbp+var_50], rcx
0x140015a87  movdqa  [rbp+var_40], xmm0
0x140015a8c  mov     [rbp+var_48], rax
0x140015a90  mov     r9, rdi
0x140015a93  lea     rdx, [rbp+var_40]
0x140015a97  lea     rcx, [rbp+var_50]
0x140015a9b  call    ?GetDefaultLogFilePath@@YAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0W4_EVT_CHANNEL_TYPE@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@2@@Z; GetDefaultLogFilePath(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_EVT_CHANNEL_TYPE,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x140015aa0  nop
0x140015aa1  mov     rax, rdi
0x140015aa4  lea     r11, [rsp+70h+var_s0]
0x140015aa9  mov     rbx, [r11+30h]
0x140015aad  mov     rsi, [r11+38h]
0x140015ab1  mov     rsp, r11
0x140015ab4  pop     r14
0x140015ab6  pop     rdi
0x140015ab7  pop     rbp
0x140015ab8  retn
```
