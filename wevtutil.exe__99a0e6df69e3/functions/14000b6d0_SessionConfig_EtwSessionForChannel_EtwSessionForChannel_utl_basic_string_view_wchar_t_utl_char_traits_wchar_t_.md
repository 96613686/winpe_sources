# SessionConfig::EtwSessionForChannel::EtwSessionForChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_EVT_CHANNEL_TYPE,_EVT_CHANNEL_ISOLATION_TYPE)

- ea: `0x14000b6d0`
- end: `0x14000b8e0`
- name: `??0EtwSessionForChannel@SessionConfig@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4_EVT_CHANNEL_TYPE@@W4_EVT_CHANNEL_ISOLATION_TYPE@@@Z`
- size: `528`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001291c`
- `0x140013658`
- `0x1400151ec`
- `0x14002d8e4`
- `0x14002ddb0`
- `0x14002e0cc`

## callees

- `0x140005600`
- `0x140005a80`
- `0x140008b40`
- `0x14000b6d0`
- `0x14000d314`
- `0x14001b580`
- `0x14001b5b4`
- `0x140022cec`
- `0x14002f6c8`
- `0x140031810`

## string_xrefs

- `0x14000b77f`: `Security`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SessionConfig::EtwSessionForChannel::EtwSessionForChannel(__int64 a1, _QWORD *a2, int a3, int a4)
{
  __int64 v8; // rcx
  __int128 v9; // xmm0
  const char *v10; // r8
  __int64 v11; // r8
  int v12; // edi
  __int128 v14; // [rsp+20h] [rbp-40h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+30h] [rbp-30h] BYREF
  int v16; // [rsp+48h] [rbp-18h]
  __int64 v17; // [rsp+4Ch] [rbp-14h]
  char v18; // [rsp+54h] [rbp-Ch]

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(a1);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v8 + 32);
  if ( a2[1] == 11
    && !(unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(*a2, L"Application", 11) )
  {
    goto LABEL_3;
  }
  v9 = *(_OWORD *)a2;
  v14 = *(_OWORD *)a2;
  if ( (unsigned __int8)IsSystemChannel(&v14) )
  {
    *(_QWORD *)&v14 = L"System";
    *((_QWORD *)&v14 + 1) = 6;
  }
  else
  {
    v14 = v9;
    if ( (unsigned __int8)IsSecurityChannel(&v14) )
    {
      *(_QWORD *)&v14 = L"Security";
      *((_QWORD *)&v14 + 1) = 8;
    }
    else if ( a4 == 2 || (unsigned int)(a3 - 2) <= 1 )
    {
      v14 = v9;
    }
    else
    {
      if ( !a4 )
      {
LABEL_3:
        *(_QWORD *)&v14 = L"Application";
        *((_QWORD *)&v14 + 1) = 11;
        goto LABEL_19;
      }
      if ( a4 != 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, 87);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, v10, 1450);
        throw (EvtException *)pExceptionObject;
      }
      *(_QWORD *)&v14 = L"System";
      *((_QWORD *)&v14 + 1) = 6;
    }
  }
LABEL_19:
  SessionConfig::EtwSessionForChannel::GetSessionNameAndGuid(&v14, a1, a1 + 64);
  LOBYTE(v11) = 1;
  v12 = tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(a1 + 32, a1 + 64, v11);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        97,
        &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
        (unsigned int)v12);
    }
    pExceptionObject[0] = word_14003838A;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v16 = v12;
    v17 = -1;
    v18 = 0;
    throw (EvtException *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x14000b6d0  mov     [rsp-28h+arg_8], rbx
0x14000b6d5  mov     [rsp-28h+arg_10], rsi
0x14000b6da  mov     [rsp-28h+arg_0], rcx
0x14000b6df  push    rbp
0x14000b6e0  push    rdi
0x14000b6e1  push    r13
0x14000b6e3  push    r14
0x14000b6e5  push    r15
0x14000b6e7  mov     rbp, rsp
0x14000b6ea  sub     rsp, 60h
0x14000b6ee  mov     edi, r9d
0x14000b6f1  mov     r14d, r8d
0x14000b6f4  mov     rsi, rdx
0x14000b6f7  mov     rbx, rcx
0x14000b6fa  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14000b6ff  nop
0x14000b700  add     rcx, 20h ; ' '
0x14000b704  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14000b709  nop
0x14000b70a  mov     r13d, 0Bh
0x14000b710  cmp     [rsi+8], r13
0x14000b714  jnz     short loc_14000B740
0x14000b716  mov     r8d, r13d
0x14000b719  lea     rdx, aApplication; "Application"
0x14000b720  mov     rcx, [rsi]
0x14000b723  call    ?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x14000b728  test    eax, eax
0x14000b72a  jnz     short loc_14000B740
0x14000b72c  lea     rax, aApplication; "Application"
0x14000b733  mov     qword ptr [rbp+var_40], rax
0x14000b737  mov     qword ptr [rbp+var_40+8], r13
0x14000b73b  jmp     loc_14000B82C
0x14000b740  movaps  xmm0, xmmword ptr [rsi]
0x14000b743  movdqa  [rbp+var_40], xmm0
0x14000b748  lea     rcx, [rbp+var_40]
0x14000b74c  call    ?IsSystemChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSystemChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14000b751  lea     rcx, [rbp+var_40]
0x14000b755  test    al, al
0x14000b757  jz      short loc_14000B771
0x14000b759  lea     rax, aSystem; "System"
0x14000b760  mov     qword ptr [rbp+var_40], rax
0x14000b764  mov     qword ptr [rbp+var_40+8], 6
0x14000b76c  jmp     loc_14000B830
0x14000b771  movdqa  [rbp+var_40], xmm0
0x14000b776  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14000b77b  test    al, al
0x14000b77d  jz      short loc_14000B797
0x14000b77f  lea     rax, aSecurity; "Security"
0x14000b786  mov     qword ptr [rbp+var_40], rax
0x14000b78a  mov     qword ptr [rbp+var_40+8], 8
0x14000b792  jmp     loc_14000B82C
0x14000b797  cmp     edi, 2
0x14000b79a  jz      loc_14000B827
0x14000b7a0  lea     eax, [r14-2]
0x14000b7a4  cmp     eax, 1
0x14000b7a7  jbe     short loc_14000B827
0x14000b7a9  test    edi, edi
0x14000b7ab  jz      loc_14000B72C
0x14000b7b1  cmp     edi, 1
0x14000b7b4  jnz     short loc_14000B7CB
0x14000b7b6  lea     rax, aSystem; "System"
0x14000b7bd  mov     qword ptr [rbp+var_40], rax
0x14000b7c1  mov     qword ptr [rbp+var_40+8], 6
0x14000b7c9  jmp     short loc_14000B82C
0x14000b7cb  lea     rax, WPP_GLOBAL_Control
0x14000b7d2  mov     ebx, 57h ; 'W'
0x14000b7d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b7de  cmp     rcx, rax
0x14000b7e1  jz      short loc_14000B805
0x14000b7e3  test    byte ptr [rcx+1Ch], 4
0x14000b7e7  jz      short loc_14000B805
0x14000b7e9  cmp     byte ptr [rcx+19h], 2
0x14000b7ed  jb      short loc_14000B805
0x14000b7ef  lea     edx, [rbx+9]
0x14000b7f2  mov     r9d, ebx
0x14000b7f5  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x14000b7fc  mov     rcx, [rcx+10h]
0x14000b800  call    WPP_SF_d
0x14000b805  mov     r9d, 5AAh; int
0x14000b80b  mov     edx, ebx; unsigned int
0x14000b80d  lea     rcx, [rbp+pExceptionObject]; this
0x14000b811  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14000b816  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000b81d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000b821  call    _CxxThrowException_0
0x14000b827  movdqa  [rbp+var_40], xmm0
0x14000b82c  lea     rcx, [rbp+var_40]
0x14000b830  lea     r8, [rbx+40h]
0x14000b834  mov     rdx, rbx
0x14000b837  call    ?GetSessionNameAndGuid@EtwSessionForChannel@SessionConfig@@SAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@4@AEAU_GUID@@@Z; SessionConfig::EtwSessionForChannel::GetSessionNameAndGuid(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,_GUID &)
0x14000b83c  lea     rdx, [rbx+40h]
0x14000b840  mov     r8b, 1
0x14000b843  lea     rcx, [rbx+20h]
0x14000b847  call    ??$assign_guid@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBU_GUID@@_N@Z; tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,_GUID const &,bool)
0x14000b84c  mov     edi, eax
0x14000b84e  test    eax, eax
0x14000b850  jns     short loc_14000B8C4
0x14000b852  lea     rax, WPP_GLOBAL_Control
0x14000b859  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b860  cmp     rcx, rax
0x14000b863  jz      short loc_14000B889
0x14000b865  test    byte ptr [rcx+1Ch], 4
0x14000b869  jz      short loc_14000B889
0x14000b86b  cmp     byte ptr [rcx+19h], 2
0x14000b86f  jb      short loc_14000B889
0x14000b871  mov     edx, 61h ; 'a'
0x14000b876  mov     r9d, edi
0x14000b879  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x14000b880  mov     rcx, [rcx+10h]
0x14000b884  call    WPP_SF_d
0x14000b889  lea     rax, word_14003838A
0x14000b890  mov     [rbp+pExceptionObject], rax
0x14000b894  mov     [rbp+var_28], 0
0x14000b89c  mov     [rbp+var_20], 0
0x14000b8a4  mov     [rbp+var_18], edi
0x14000b8a7  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x14000b8af  mov     [rbp+var_C], 0
0x14000b8b3  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000b8ba  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000b8be  call    _CxxThrowException_0
0x14000b8c4  mov     rax, rbx
0x14000b8c7  lea     r11, [rsp+60h+var_s0]
0x14000b8cc  mov     rbx, [r11+38h]
0x14000b8d0  mov     rsi, [r11+40h]
0x14000b8d4  mov     rsp, r11
0x14000b8d7  pop     r15
0x14000b8d9  pop     r14
0x14000b8db  pop     r13
0x14000b8dd  pop     rdi
0x14000b8de  pop     rbp
0x14000b8df  retn
```
