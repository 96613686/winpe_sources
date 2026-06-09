# SessionConfig::DeleteChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,void *)

- ea: `0x14002ddb0`
- end: `0x14002e00f`
- name: `?DeleteChannel@SessionConfig@@SAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAX@Z`
- size: `607`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, installer_update`

## callers

- `0x14001d828`

## callees

- `0x140002bd0`
- `0x140004ae0`
- `0x140005600`
- `0x140006008`
- `0x1400073ec`
- `0x1400098cc`
- `0x14000b6d0`
- `0x14000d314`
- `0x140014960`
- `0x140014988`
- `0x140019348`
- `0x140021b00`
- `0x140022cec`
- `0x14002d880`
- `0x14002ddb0`
- `0x14002e0cc`
- `0x14002efbc`
- `0x14002f6c8`
- `0x140031810`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SessionConfig::DeleteChannel(struct _GUID *a1, void *a2)
{
  void *v2; // rdi
  struct _GUID *v3; // rsi
  const char *v4; // r8
  void *v5; // rax
  __int64 v6; // rbx
  struct _GUID v8; // [rsp+20h] [rbp-138h] BYREF
  __int64 v9; // [rsp+30h] [rbp-128h] BYREF
  struct _GUID v10; // [rsp+40h] [rbp-118h] BYREF
  struct _GUID *v11; // [rsp+50h] [rbp-108h]
  void *v12; // [rsp+60h] [rbp-F8h]
  wchar_t *v13[4]; // [rsp+68h] [rbp-F0h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+88h] [rbp-D0h] BYREF
  wchar_t *v15[8]; // [rsp+B0h] [rbp-A8h] BYREF
  struct _GUID v16; // [rsp+F0h] [rbp-68h]

  v2 = a2;
  v3 = a1;
  v11 = a1;
  v12 = a2;
  v8 = *a1;
  if ( IsCoreChannel((const wchar_t **)&v8) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, 4317);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0x10DDu, v4, 794);
    throw (EvtException *)pExceptionObject;
  }
  try
  {
    v9 = 0;
    v8 = *v3;
    ChannelConfigReader::ChannelConfigReader((__int64)v15, (__int128 *)&v8, (__int64)v2);
    v5 = operator new(0x100u);
    *(_QWORD *)&v8.Data1 = v5;
    if ( v5 )
    {
      v10 = 0;
      v6 = ChannelConfigSnapshot::ChannelConfigSnapshot(v5, v15, &v10);
    }
    else
    {
      v6 = 0;
    }
    v9 = v6;
    ChannelConfigReader::~ChannelConfigReader((ChannelConfigReader *)v15);
  }
  catch ( EvtException )
  {
    v6 = v9;
    v3 = v11;
    v2 = v12;
  }
  if ( v6 )
  {
    if ( ChannelConfigSnapshot::IsOwnerOfEtwSession((ChannelConfigSnapshot *)v6) )
    {
      *(_QWORD *)&v8.Data1 = *(_QWORD *)(v6 + 200);
      *(_QWORD *)v8.Data4 = (__int64)(*(_QWORD *)(v6 + 208) - *(_QWORD *)&v8.Data1) >> 1;
      SessionConfig::EtwSessionForChannel::EtwSessionForChannel(
        (__int64)v15,
        &v8,
        *(unsigned __int8 *)(v6 + 249),
        *(unsigned __int8 *)(v6 + 248));
      v10 = v16;
      SessionConfig::DeleteSession(v15[0], &v10, v2);
      SessionConfig::EtwSessionForChannel::~EtwSessionForChannel((SessionConfig::EtwSessionForChannel *)v15);
    }
    else
    {
      SessionConfig::UpdateProvidersForChannel((const struct ChannelConfigSnapshot *)v6, 0, v2);
    }
  }
  else
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v13);
    v8 = 0;
    v10 = *v3;
    SessionConfig::EtwSessionForChannel::GetSessionNameAndGuid(&v10, v13, &v8);
    v10 = v8;
    SessionConfig::DeleteSession(v13[0], &v10, v2);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v13);
  }
  return utl::unique_ptr<ChannelConfigSnapshot,utl::default_delete<ChannelConfigSnapshot>>::~unique_ptr<ChannelConfigSnapshot,utl::default_delete<ChannelConfigSnapshot>>(&v9);
}

```

## disassembly

```asm
0x14002ddb0  mov     [rsp+arg_10], rbx
0x14002ddb5  mov     [rsp+arg_18], rsi
0x14002ddba  push    rdi
0x14002ddbb  sub     rsp, 150h
0x14002ddc2  mov     rax, cs:__security_cookie
0x14002ddc9  xor     rax, rsp
0x14002ddcc  mov     [rsp+158h+var_18], rax
0x14002ddd4  mov     rdi, rdx
0x14002ddd7  mov     rsi, rcx
0x14002ddda  mov     [rsp+158h+var_108], rcx
0x14002dddf  mov     [rsp+158h+var_F8], rdx
0x14002dde4  mov     rax, [rcx]
0x14002dde7  mov     qword ptr [rsp+158h+var_138], rax
0x14002ddec  mov     rax, [rcx+8]
0x14002ddf0  mov     qword ptr [rsp+158h+var_138+8], rax
0x14002ddf5  lea     rcx, [rsp+158h+var_138]
0x14002ddfa  call    ?IsCoreChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsCoreChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14002ddff  test    al, al
0x14002de01  jz      short loc_14002DE6A
0x14002de03  lea     rax, WPP_GLOBAL_Control
0x14002de0a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002de11  cmp     rcx, rax
0x14002de14  jz      short loc_14002DE3D
0x14002de16  test    byte ptr [rcx+1Ch], 4
0x14002de1a  jz      short loc_14002DE3D
0x14002de1c  cmp     byte ptr [rcx+19h], 2
0x14002de20  jb      short loc_14002DE3D
0x14002de22  mov     edx, 31h ; '1'
0x14002de27  mov     r9d, 10DDh
0x14002de2d  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x14002de34  mov     rcx, [rcx+10h]
0x14002de38  call    WPP_SF_d
0x14002de3d  mov     edx, 10DDh; unsigned int
0x14002de42  mov     r9d, 31Ah; int
0x14002de48  lea     rcx, [rsp+158h+pExceptionObject]; this
0x14002de50  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002de55  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002de5c  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x14002de64  call    _CxxThrowException_0
0x14002de6a  mov     [rsp+158h+var_128], 0
0x14002de73  movaps  xmm0, xmmword ptr [rsi]
0x14002de76  movdqa  [rsp+158h+var_138], xmm0
0x14002de7c  mov     r8, rdi
0x14002de7f  lea     rdx, [rsp+158h+var_138]
0x14002de84  lea     rcx, [rsp+158h+var_A8]
0x14002de8c  call    ??0ChannelConfigReader@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAX@Z; ChannelConfigReader::ChannelConfigReader(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,void *)
0x14002de91  nop
0x14002de92  mov     ecx, 100h; dwBytes
0x14002de97  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002de9c  mov     qword ptr [rsp+158h+var_138], rax
0x14002dea1  test    rax, rax
0x14002dea4  jz      short loc_14002DEC9
0x14002dea6  xorps   xmm0, xmm0
0x14002dea9  movdqa  xmmword ptr [rsp+158h+var_118.Data1], xmm0
0x14002deaf  lea     r8, [rsp+158h+var_118]
0x14002deb4  lea     rdx, [rsp+158h+var_A8]
0x14002debc  mov     rcx, rax
0x14002debf  call    ??0ChannelConfigSnapshot@@QEAA@AEBVChannelConfigReader@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; ChannelConfigSnapshot::ChannelConfigSnapshot(ChannelConfigReader const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14002dec4  mov     rbx, rax
0x14002dec7  jmp     short loc_14002DECB
0x14002dec9  xor     ebx, ebx
0x14002decb  mov     [rsp+158h+var_128], rbx
0x14002ded0  lea     rcx, [rsp+158h+var_A8]; this
0x14002ded8  call    ??1ChannelConfigReader@@QEAA@XZ; ChannelConfigReader::~ChannelConfigReader(void)
0x14002dedd  nop
0x14002dede  jmp     short loc_14002DEEF
0x14002dee0  mov     rbx, [rsp+158h+var_128]
0x14002dee5  mov     rsi, [rsp+158h+var_108]
0x14002deea  mov     rdi, [rsp+158h+var_F8]
0x14002deef  test    rbx, rbx
0x14002def2  jz      loc_14002DF87
0x14002def8  mov     rcx, rbx; this
0x14002defb  call    ?IsOwnerOfEtwSession@ChannelConfigSnapshot@@QEBA_NXZ; ChannelConfigSnapshot::IsOwnerOfEtwSession(void)
0x14002df00  test    al, al
0x14002df02  jz      short loc_14002DF78
0x14002df04  mov     rax, [rbx+0C8h]
0x14002df0b  mov     qword ptr [rsp+158h+var_138], rax
0x14002df10  mov     rcx, [rbx+0D0h]
0x14002df17  sub     rcx, rax
0x14002df1a  sar     rcx, 1
0x14002df1d  mov     qword ptr [rsp+158h+var_138+8], rcx
0x14002df22  movzx   r9d, byte ptr [rbx+0F8h]
0x14002df2a  movzx   r8d, byte ptr [rbx+0F9h]
0x14002df32  lea     rdx, [rsp+158h+var_138]
0x14002df37  lea     rcx, [rsp+158h+var_A8]
0x14002df3f  call    ??0EtwSessionForChannel@SessionConfig@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4_EVT_CHANNEL_TYPE@@W4_EVT_CHANNEL_ISOLATION_TYPE@@@Z; SessionConfig::EtwSessionForChannel::EtwSessionForChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_EVT_CHANNEL_TYPE,_EVT_CHANNEL_ISOLATION_TYPE)
0x14002df44  nop
0x14002df45  movaps  xmm0, [rsp+158h+var_68]
0x14002df4d  movdqu  xmmword ptr [rsp+158h+var_118.Data1], xmm0
0x14002df53  mov     r8, rdi; void *
0x14002df56  lea     rdx, [rsp+158h+var_118]; struct _GUID
0x14002df5b  mov     rcx, [rsp+158h+var_A8]; wchar_t *
0x14002df63  call    ?DeleteSession@SessionConfig@@CAXPEB_WU_GUID@@PEAX@Z; SessionConfig::DeleteSession(wchar_t const *,_GUID,void *)
0x14002df68  nop
0x14002df69  lea     rcx, [rsp+158h+var_A8]; this
0x14002df71  call    ??1EtwSessionForChannel@SessionConfig@@QEAA@XZ; SessionConfig::EtwSessionForChannel::~EtwSessionForChannel(void)
0x14002df76  jmp     short loc_14002DFE0
0x14002df78  mov     r8, rdi; void *
0x14002df7b  xor     edx, edx; bool
0x14002df7d  mov     rcx, rbx; struct ChannelConfigSnapshot *
0x14002df80  call    ?UpdateProvidersForChannel@SessionConfig@@CAXAEBVChannelConfigSnapshot@@_NPEAX@Z; SessionConfig::UpdateProvidersForChannel(ChannelConfigSnapshot const &,bool,void *)
0x14002df85  jmp     short loc_14002DFE0
0x14002df87  lea     rcx, [rsp+158h+var_F0]
0x14002df8c  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002df91  nop
0x14002df92  xorps   xmm0, xmm0
0x14002df95  movups  [rsp+158h+var_138], xmm0
0x14002df9a  movaps  xmm1, xmmword ptr [rsi]
0x14002df9d  movdqa  xmmword ptr [rsp+158h+var_118.Data1], xmm1
0x14002dfa3  lea     r8, [rsp+158h+var_138]
0x14002dfa8  lea     rdx, [rsp+158h+var_F0]
0x14002dfad  lea     rcx, [rsp+158h+var_118]
0x14002dfb2  call    ?GetSessionNameAndGuid@EtwSessionForChannel@SessionConfig@@SAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@4@AEAU_GUID@@@Z; SessionConfig::EtwSessionForChannel::GetSessionNameAndGuid(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,_GUID &)
0x14002dfb7  movaps  xmm0, [rsp+158h+var_138]
0x14002dfbc  movdqa  xmmword ptr [rsp+158h+var_118.Data1], xmm0
0x14002dfc2  mov     r8, rdi; void *
0x14002dfc5  lea     rdx, [rsp+158h+var_118]; struct _GUID
0x14002dfca  mov     rcx, [rsp+158h+var_F0]; wchar_t *
0x14002dfcf  call    ?DeleteSession@SessionConfig@@CAXPEB_WU_GUID@@PEAX@Z; SessionConfig::DeleteSession(wchar_t const *,_GUID,void *)
0x14002dfd4  nop
0x14002dfd5  lea     rcx, [rsp+158h+var_F0]
0x14002dfda  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002dfdf  nop
0x14002dfe0  lea     rcx, [rsp+158h+var_128]
0x14002dfe5  call    ??1?$unique_ptr@VChannelConfigSnapshot@@U?$default_delete@VChannelConfigSnapshot@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ChannelConfigSnapshot,utl::default_delete<ChannelConfigSnapshot>>::~unique_ptr<ChannelConfigSnapshot,utl::default_delete<ChannelConfigSnapshot>>(void)
0x14002dfea  mov     rcx, [rsp+158h+var_18]
0x14002dff2  xor     rcx, rsp; StackCookie
0x14002dff5  call    __security_check_cookie
0x14002dffa  lea     r11, [rsp+158h+var_8]
0x14002e002  mov     rbx, [r11+20h]
0x14002e006  mov     rsi, [r11+28h]
0x14002e00a  mov     rsp, r11
0x14002e00d  pop     rdi
0x14002e00e  retn
```
