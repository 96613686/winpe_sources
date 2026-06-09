# SessionConfig::EtwSessionForChannel::GetSessionNameAndGuid(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,_GUID &)

- ea: `0x14000d314`
- end: `0x14000d568`
- name: `?GetSessionNameAndGuid@EtwSessionForChannel@SessionConfig@@SAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@4@AEAU_GUID@@@Z`
- size: `596`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b6d0`
- `0x140013658`
- `0x14002ddb0`

## callees

- `0x140004ae0`
- `0x140005600`
- `0x140006cd0`
- `0x140007db0`
- `0x14000d314`
- `0x14000d6e8`
- `0x14001a9b8`
- `0x140022cec`
- `0x14002c79c`
- `0x14002f6c8`
- `0x140030ecc`
- `0x140031810`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x14000d3f6`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x14000d3f6`

## string_xrefs

- `0x14000d3aa`: `EventLog-Security`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SessionConfig::EtwSessionForChannel::GetSessionNameAndGuid(
        _QWORD *a1,
        wint_t **a2,
        struct _GUID *a3)
{
  const char *v6; // r8
  wint_t *v7; // r10
  wint_t *v8; // rcx
  unsigned __int64 v9; // rdx
  __int64 result; // rax
  __int64 v11; // r10
  wint_t *v12; // rbx
  wint_t *v13; // rdi
  wint_t v14; // ax
  const char *v15; // r8
  int v16; // ebx
  unsigned __int8 *v17[4]; // [rsp+20h] [rbp-58h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+40h] [rbp-38h] BYREF
  int v19; // [rsp+58h] [rbp-20h]
  __int64 v20; // [rsp+5Ch] [rbp-1Ch]
  char v21; // [rsp+64h] [rbp-14h]

  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           a2,
                           L"EventLog-",
                           9)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           a2,
                           *a1,
                           a1[1]) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v6, 1479);
    throw (EvtException *)pExceptionObject;
  }
  v7 = a2[1];
  v8 = *a2;
  if ( v7 - *a2 )
  {
    v9 = 0;
    do
    {
      if ( v8[v9] == 47 || v8[v9] == 92 )
        v8[v9] = 45;
      ++v9;
      v7 = a2[1];
      v8 = *a2;
    }
    while ( v9 < v7 - *a2 );
  }
  if ( (char *)v7 - (char *)v8 != 34
    || (result = utl::_Char16TraitsBase<wchar_t>::compare(v8, L"EventLog-Security", 17), (_DWORD)result) )
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v17);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(v17, v11 >> 1);
    v12 = *a2;
    v13 = a2[1];
    while ( v12 != v13 )
    {
      v14 = towupper(*v12);
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                               v17,
                               v14) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v15, 1505);
        throw (EvtException *)pExceptionObject;
      }
      ++v12;
    }
    v16 = Sha256HashToGuid(v17[0], 2 * (unsigned int)((v17[1] - v17[0]) >> 1), a3);
    if ( v16 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          100,
          &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
          (unsigned int)v16);
      }
      pExceptionObject[0] = word_14003838A;
      pExceptionObject[1] = 0;
      pExceptionObject[2] = 0;
      v19 = v16;
      v20 = -1;
      v21 = 0;
      throw (EvtException *)pExceptionObject;
    }
    return utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v17);
  }
  else
  {
    *a3 = (struct _GUID)AuditLoggerGuid;
  }
  return result;
}

```

## disassembly

```asm
0x14000d314  push    rbp
0x14000d316  push    rbx
0x14000d317  push    rsi
0x14000d318  push    rdi
0x14000d319  mov     rbp, rsp
0x14000d31c  sub     rsp, 78h
0x14000d320  mov     rsi, r8
0x14000d323  mov     rdi, rdx
0x14000d326  mov     rbx, rcx
0x14000d329  mov     r8d, 9
0x14000d32f  lea     rdx, aEventlog; "EventLog-"
0x14000d336  mov     rcx, rdi
0x14000d339  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14000d33e  test    al, al
0x14000d340  jz      loc_14000D50C
0x14000d346  mov     r8, [rbx+8]
0x14000d34a  mov     rdx, [rbx]
0x14000d34d  mov     rcx, rdi
0x14000d350  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14000d355  test    al, al
0x14000d357  jz      loc_14000D50C
0x14000d35d  mov     r10, [rdi+8]
0x14000d361  mov     rcx, [rdi]
0x14000d364  mov     rax, r10
0x14000d367  sub     rax, rcx
0x14000d36a  sar     rax, 1
0x14000d36d  jz      short loc_14000D39D
0x14000d36f  xor     edx, edx
0x14000d371  cmp     word ptr [rcx+rdx*2], 2Fh ; '/'
0x14000d376  jz      short loc_14000D37F
0x14000d378  cmp     word ptr [rcx+rdx*2], 5Ch ; '\'
0x14000d37d  jnz     short loc_14000D385
0x14000d37f  mov     word ptr [rcx+rdx*2], 2Dh ; '-'
0x14000d385  inc     rdx
0x14000d388  mov     r10, [rdi+8]
0x14000d38c  mov     rcx, [rdi]
0x14000d38f  mov     rax, r10
0x14000d392  sub     rax, rcx
0x14000d395  sar     rax, 1
0x14000d398  cmp     rdx, rax
0x14000d39b  jb      short loc_14000D371
0x14000d39d  sub     r10, rcx
0x14000d3a0  cmp     r10, 22h ; '"'
0x14000d3a4  jnz     short loc_14000D3CE
0x14000d3a6  lea     r8d, [r10-11h]
0x14000d3aa  lea     rdx, aEventlogSecuri; "EventLog-Security"
0x14000d3b1  call    ?compare@?$_Char16TraitsBase@_W@utl@@SAHPEB_W0_K@Z; utl::_Char16TraitsBase<wchar_t>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x14000d3b6  test    eax, eax
0x14000d3b8  jnz     short loc_14000D3CE
0x14000d3ba  movups  xmm0, cs:AuditLoggerGuid
0x14000d3c1  movdqu  xmmword ptr [rsi], xmm0
0x14000d3c5  add     rsp, 78h
0x14000d3c9  pop     rdi
0x14000d3ca  pop     rsi
0x14000d3cb  pop     rbx
0x14000d3cc  pop     rbp
0x14000d3cd  retn
0x14000d3ce  lea     rcx, [rbp+var_58]
0x14000d3d2  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14000d3d7  nop
0x14000d3d8  sar     r10, 1
0x14000d3db  mov     rdx, r10
0x14000d3de  lea     rcx, [rbp+var_58]
0x14000d3e2  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x14000d3e7  mov     rbx, [rdi]
0x14000d3ea  mov     rdi, [rdi+8]
0x14000d3ee  cmp     rbx, rdi
0x14000d3f1  jz      short loc_14000D46E
0x14000d3f3  movzx   ecx, word ptr [rbx]; C
0x14000d3f6  call    cs:__imp_towupper
0x14000d3fc  movzx   edx, ax
0x14000d3ff  lea     rcx, [rbp+var_58]
0x14000d403  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14000d408  test    al, al
0x14000d40a  jz      short loc_14000D412
0x14000d40c  add     rbx, 2
0x14000d410  jmp     short loc_14000D3EE
0x14000d412  lea     rax, WPP_GLOBAL_Control
0x14000d419  mov     ebx, 0Eh
0x14000d41e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d425  cmp     rcx, rax
0x14000d428  jz      short loc_14000D44C
0x14000d42a  test    byte ptr [rcx+1Ch], 4
0x14000d42e  jz      short loc_14000D44C
0x14000d430  cmp     byte ptr [rcx+19h], 2
0x14000d434  jb      short loc_14000D44C
0x14000d436  lea     edx, [rbx+55h]
0x14000d439  mov     r9d, ebx
0x14000d43c  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x14000d443  mov     rcx, [rcx+10h]
0x14000d447  call    WPP_SF_d
0x14000d44c  mov     r9d, 5E1h; int
0x14000d452  mov     edx, ebx; unsigned int
0x14000d454  lea     rcx, [rbp+pExceptionObject]; this
0x14000d458  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14000d45d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000d464  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000d468  call    _CxxThrowException_0
0x14000d46e  mov     rcx, [rbp+var_58]; unsigned __int8 *
0x14000d472  mov     rdx, [rbp+var_50]
0x14000d476  sub     rdx, rcx
0x14000d479  sar     rdx, 1
0x14000d47c  add     edx, edx; unsigned int
0x14000d47e  mov     r8, rsi; struct _GUID *
0x14000d481  call    ?Sha256HashToGuid@@YAJPEAEKPEAU_GUID@@@Z; Sha256HashToGuid(uchar *,ulong,_GUID *)
0x14000d486  mov     ebx, eax
0x14000d488  test    eax, eax
0x14000d48a  jns     short loc_14000D4FE
0x14000d48c  lea     rax, WPP_GLOBAL_Control
0x14000d493  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d49a  cmp     rcx, rax
0x14000d49d  jz      short loc_14000D4C3
0x14000d49f  test    byte ptr [rcx+1Ch], 4
0x14000d4a3  jz      short loc_14000D4C3
0x14000d4a5  cmp     byte ptr [rcx+19h], 2
0x14000d4a9  jb      short loc_14000D4C3
0x14000d4ab  mov     edx, 64h ; 'd'
0x14000d4b0  mov     r9d, ebx
0x14000d4b3  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x14000d4ba  mov     rcx, [rcx+10h]
0x14000d4be  call    WPP_SF_d
0x14000d4c3  lea     rax, word_14003838A
0x14000d4ca  mov     [rbp+pExceptionObject], rax
0x14000d4ce  mov     [rbp+var_30], 0
0x14000d4d6  mov     [rbp+var_28], 0
0x14000d4de  mov     [rbp+var_20], ebx
0x14000d4e1  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x14000d4e9  mov     [rbp+var_14], 0
0x14000d4ed  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000d4f4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000d4f8  call    _CxxThrowException_0
0x14000d4fe  lea     rcx, [rbp+var_58]
0x14000d502  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14000d507  jmp     loc_14000D3C5
0x14000d50c  lea     rax, WPP_GLOBAL_Control
0x14000d513  mov     ebx, 0Eh
0x14000d518  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d51f  cmp     rcx, rax
0x14000d522  jz      short loc_14000D546
0x14000d524  test    byte ptr [rcx+1Ch], 4
0x14000d528  jz      short loc_14000D546
0x14000d52a  cmp     byte ptr [rcx+19h], 2
0x14000d52e  jb      short loc_14000D546
0x14000d530  lea     edx, [rbx+54h]
0x14000d533  mov     r9d, ebx
0x14000d536  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x14000d53d  mov     rcx, [rcx+10h]
0x14000d541  call    WPP_SF_d
0x14000d546  mov     r9d, 5C7h; int
0x14000d54c  mov     edx, ebx; unsigned int
0x14000d54e  lea     rcx, [rbp+pExceptionObject]; this
0x14000d552  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14000d557  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000d55e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000d562  call    _CxxThrowException_0
```
