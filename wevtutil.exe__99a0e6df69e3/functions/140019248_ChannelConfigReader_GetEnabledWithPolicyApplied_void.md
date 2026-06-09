# ChannelConfigReader::GetEnabledWithPolicyApplied(void)

- ea: `0x140019248`
- end: `0x140019342`
- name: `?GetEnabledWithPolicyApplied@ChannelConfigReader@@QEBA_NXZ`
- size: `250`
- prototype: `bool __fastcall(ChannelConfigReader *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400073ec`

## callees

- `0x140008870`
- `0x140019248`
- `0x140019348`
- `0x14001b1f8`
- `0x140022cec`
- `0x14002f6c8`
- `0x140031810`

## pseudocode

```c
bool __fastcall ChannelConfigReader::GetEnabledWithPolicyApplied(ChannelConfigReader *this)
{
  __int64 v2; // rdx
  const wchar_t *v3; // rdx
  const struct _EVT_VARIANT *Property; // rax
  bool v5; // zf
  HKEY v7; // rcx
  unsigned int v8; // ebx
  const char *v9; // r8
  const wchar_t *v10[2]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v12; // [rsp+70h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 5);
  v10[0] = *((const wchar_t **)this + 4);
  v10[1] = (const wchar_t *)((signed __int64)(v2 - (unsigned __int64)v10[0]) >> 1);
  if ( IsCoreChannel(v10) )
    return 1;
  if ( *((_BYTE *)this + 128) )
  {
    Property = ChannelPolicy::GetProperty((ChannelConfigReader *)((char *)this + 64), EvtChannelConfigEnabled);
    if ( Property )
    {
      v5 = Property->BooleanVal == (_DWORD)v3;
      return !v5;
    }
  }
  if ( *((_BYTE *)this + 140) == 1 )
    return 1;
  v7 = *(HKEY *)this;
  v12 = 0;
  v8 = RegReadDWORDValueNoThrow(v7, v3, L"Enabled", &v12);
  if ( v8 != 2 )
  {
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, v8);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, v8, v9, 371);
      throw (EvtException *)pExceptionObject;
    }
    v5 = v12 == 0;
    return !v5;
  }
  return 0;
}

```

## disassembly

```asm
0x140019248  push    rbx
0x14001924a  sub     rsp, 60h
0x14001924e  mov     rax, [rcx+20h]
0x140019252  mov     rbx, rcx
0x140019255  mov     rdx, [rcx+28h]
0x140019259  lea     rcx, [rsp+68h+var_48]
0x14001925e  sub     rdx, rax
0x140019261  mov     [rsp+68h+var_48], rax
0x140019266  sar     rdx, 1
0x140019269  mov     [rsp+68h+var_40], rdx
0x14001926e  call    ?IsCoreChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsCoreChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x140019273  test    al, al
0x140019275  jnz     loc_14001933A
0x14001927b  cmp     [rbx+80h], al
0x140019281  jz      short loc_14001929D
0x140019283  lea     rcx, [rbx+40h]; this
0x140019287  xor     edx, edx; enum _EVT_CHANNEL_CONFIG_PROPERTY_ID
0x140019289  call    ?GetProperty@ChannelPolicy@@QEBAPEBU_EVT_VARIANT@@W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z; ChannelPolicy::GetProperty(_EVT_CHANNEL_CONFIG_PROPERTY_ID)
0x14001928e  test    rax, rax
0x140019291  jz      short loc_14001929D
0x140019293  cmp     [rax], edx
0x140019295  setnz   al
0x140019298  jmp     loc_14001933C
0x14001929d  cmp     byte ptr [rbx+8Ch], 1
0x1400192a4  jz      loc_14001933A
0x1400192aa  mov     rcx, [rbx]; HKEY
0x1400192ad  lea     r9, [rsp+68h+arg_0]; unsigned int *
0x1400192b2  lea     r8, aEnabled; "Enabled"
0x1400192b9  mov     [rsp+68h+arg_0], 0
0x1400192c1  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x1400192c6  mov     ebx, eax
0x1400192c8  cmp     eax, 2
0x1400192cb  jnz     short loc_1400192D1
0x1400192cd  xor     al, al
0x1400192cf  jmp     short loc_14001933C
0x1400192d1  test    ebx, ebx
0x1400192d3  jz      short loc_140019330
0x1400192d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400192dc  lea     rax, WPP_GLOBAL_Control
0x1400192e3  cmp     rcx, rax
0x1400192e6  jz      short loc_14001930C
0x1400192e8  test    byte ptr [rcx+1Ch], 4
0x1400192ec  jz      short loc_14001930C
0x1400192ee  cmp     byte ptr [rcx+19h], 2
0x1400192f2  jb      short loc_14001930C
0x1400192f4  mov     rcx, [rcx+10h]
0x1400192f8  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x1400192ff  mov     edx, 21h ; '!'
0x140019304  mov     r9d, ebx
0x140019307  call    WPP_SF_d
0x14001930c  mov     r9d, 173h; int
0x140019312  lea     rcx, [rsp+68h+pExceptionObject]; this
0x140019317  mov     edx, ebx; unsigned int
0x140019319  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14001931e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140019325  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x14001932a  call    _CxxThrowException_0
0x140019330  cmp     [rsp+68h+arg_0], 0
0x140019335  jmp     loc_140019295
0x14001933a  mov     al, 1
0x14001933c  add     rsp, 60h
0x140019340  pop     rbx
0x140019341  retn
```
