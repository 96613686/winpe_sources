# ChannelConfigReader::GetControlGuid(void)

- ea: `0x1400076b4`
- end: `0x140007830`
- name: `?GetControlGuid@ChannelConfigReader@@QEBA?AU_GUID@@XZ`
- size: `380`
- prototype: `struct _GUID *__fastcall(ChannelConfigReader *__hidden this, struct _GUID *__return_ptr __struct_ptr retstr)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x14000750c`

## callees

- `0x1400039a0`
- `0x140004ae0`
- `0x140005600`
- `0x140005620`
- `0x1400076b4`
- `0x140021b00`
- `0x140022cec`
- `0x14002a328`
- `0x14002f6c8`
- `0x140031810`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _GUID *__fastcall ChannelConfigReader::GetControlGuid(
        ChannelConfigReader *this,
        struct _GUID *__return_ptr retstr)
{
  HKEY *v3; // r10
  unsigned int StringValueNoThrow; // edi
  const char *v5; // r8
  const char *v6; // r8
  void *v8[2]; // [rsp+20h] [rbp-60h] BYREF
  char v9; // [rsp+30h] [rbp-50h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+40h] [rbp-40h] BYREF
  struct _GUID v11; // [rsp+68h] [rbp-18h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v8);
  StringValueNoThrow = RegReadStringValueNoThrow(*v3, 0, L"ControlGuid", (__int64)v8);
  if ( StringValueNoThrow == 2 )
  {
    *retstr = GUID_NULL;
    if ( v8[0] != &v9 )
      operator delete(v8[0]);
  }
  else
  {
    if ( StringValueNoThrow )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids,
          StringValueNoThrow);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, StringValueNoThrow, v5, 207);
      throw (EvtException *)pExceptionObject;
    }
    v11 = 0;
    if ( !tlx::string_to_guid<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(&v11, v8) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, v6, 213);
      throw (EvtException *)pExceptionObject;
    }
    *retstr = v11;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v8);
  }
  return retstr;
}

```

## disassembly

```asm
0x1400076b4  mov     [rsp-8+arg_10], rbx
0x1400076b9  mov     [rsp-8+arg_18], rdi
0x1400076be  push    rbp
0x1400076bf  mov     rbp, rsp
0x1400076c2  sub     rsp, 80h
0x1400076c9  mov     rax, cs:__security_cookie
0x1400076d0  xor     rax, rsp
0x1400076d3  mov     [rbp+var_8], rax
0x1400076d7  mov     rbx, rdx
0x1400076da  mov     r10, rcx
0x1400076dd  lea     rcx, [rbp+var_60]
0x1400076e1  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400076e6  nop
0x1400076e7  lea     r9, [rbp+var_60]
0x1400076eb  lea     r8, aControlguid; "ControlGuid"
0x1400076f2  xor     edx, edx
0x1400076f4  mov     rcx, [r10]; hKey
0x1400076f7  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1400076fc  mov     edi, eax
0x1400076fe  cmp     eax, 2
0x140007701  jnz     short loc_140007729
0x140007703  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14000770a  movdqu  xmmword ptr [rbx], xmm0
0x14000770e  lea     rax, [rbp+var_50]
0x140007712  mov     rcx, [rbp+var_60]; void *
0x140007716  cmp     rcx, rax
0x140007719  jz      loc_14000780C
0x14000771f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140007724  jmp     loc_14000780C
0x140007729  test    edi, edi
0x14000772b  jz      short loc_140007786
0x14000772d  lea     rax, WPP_GLOBAL_Control
0x140007734  mov     rcx, cs:WPP_GLOBAL_Control
0x14000773b  cmp     rcx, rax
0x14000773e  jz      short loc_140007764
0x140007740  test    byte ptr [rcx+1Ch], 4
0x140007744  jz      short loc_140007764
0x140007746  cmp     byte ptr [rcx+19h], 2
0x14000774a  jb      short loc_140007764
0x14000774c  mov     edx, 1Ch
0x140007751  mov     r9d, edi
0x140007754  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x14000775b  mov     rcx, [rcx+10h]
0x14000775f  call    WPP_SF_d
0x140007764  mov     r9d, 0CFh; int
0x14000776a  mov     edx, edi; unsigned int
0x14000776c  lea     rcx, [rbp+pExceptionObject]; this
0x140007770  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140007775  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000777c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140007780  call    _CxxThrowException_0
0x140007786  xorps   xmm0, xmm0
0x140007789  movups  [rbp+var_18], xmm0
0x14000778d  lea     rdx, [rbp+var_60]
0x140007791  lea     rcx, [rbp+var_18]
0x140007795  call    ??$string_to_guid@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@tlx@@YAPEB_WPEAU_GUID@@AEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; tlx::string_to_guid<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(_GUID *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x14000779a  test    rax, rax
0x14000779d  jnz     short loc_1400077FB
0x14000779f  lea     rax, WPP_GLOBAL_Control
0x1400077a6  mov     ebx, 0Dh
0x1400077ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400077b2  cmp     rcx, rax
0x1400077b5  jz      short loc_1400077D9
0x1400077b7  test    byte ptr [rcx+1Ch], 4
0x1400077bb  jz      short loc_1400077D9
0x1400077bd  cmp     byte ptr [rcx+19h], 2
0x1400077c1  jb      short loc_1400077D9
0x1400077c3  lea     edx, [rbx+10h]
0x1400077c6  mov     r9d, ebx
0x1400077c9  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x1400077d0  mov     rcx, [rcx+10h]
0x1400077d4  call    WPP_SF_d
0x1400077d9  mov     r9d, 0D5h; int
0x1400077df  mov     edx, ebx; unsigned int
0x1400077e1  lea     rcx, [rbp+pExceptionObject]; this
0x1400077e5  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x1400077ea  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400077f1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400077f5  call    _CxxThrowException_0
0x1400077fb  movups  xmm0, [rbp+var_18]
0x1400077ff  movdqu  xmmword ptr [rbx], xmm0
0x140007803  lea     rcx, [rbp+var_60]
0x140007807  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14000780c  mov     rax, rbx
0x14000780f  mov     rcx, [rbp+var_8]
0x140007813  xor     rcx, rsp; StackCookie
0x140007816  call    __security_check_cookie
0x14000781b  lea     r11, [rsp+80h+var_s0]
0x140007823  mov     rbx, [r11+20h]
0x140007827  mov     rdi, [r11+28h]
0x14000782b  mov     rsp, r11
0x14000782e  pop     rbp
0x14000782f  retn
```
