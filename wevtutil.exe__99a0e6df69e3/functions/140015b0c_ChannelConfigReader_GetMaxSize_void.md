# ChannelConfigReader::GetMaxSize(void)

- ea: `0x140015b0c`
- end: `0x140015ca4`
- name: `?GetMaxSize@ChannelConfigReader@@QEBA_KXZ`
- size: `408`
- prototype: `unsigned __int64 __fastcall(ChannelConfigReader *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400073ec`

## callees

- `0x140008870`
- `0x140015b0c`
- `0x140019348`
- `0x14001b5b4`
- `0x140022cec`
- `0x14002f6c8`
- `0x140031810`

## pseudocode

```c
unsigned __int64 __fastcall ChannelConfigReader::GetMaxSize(ChannelConfigReader **this, char *a2)
{
  char *v3; // rax
  char *v4; // rcx
  __int64 v5; // r8
  ChannelConfigReader *v7; // rcx
  unsigned int v8; // ebx
  const wchar_t *v9; // rdx
  const char *v10; // r8
  const wchar_t *v11; // rsi
  __int64 v12; // rdi
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // rax
  const wchar_t *v15; // [rsp+20h] [rbp-40h] BYREF
  __int64 v16; // [rsp+28h] [rbp-38h]
  _BYTE pExceptionObject[48]; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v18; // [rsp+80h] [rbp+20h] BYREF
  unsigned int v19; // [rsp+88h] [rbp+28h] BYREF

  if ( *((_BYTE *)this + 128) )
  {
    v3 = (char *)(this + 8);
    if ( this[10] != (ChannelConfigReader *)(this + 8) )
    {
      a2 = *(char **)v3;
      v4 = (char *)(this + 8);
      do
      {
        if ( *((int *)a2 + 6) >= 8 )
        {
          v4 = a2;
          v5 = 8;
        }
        else
        {
          v5 = 16;
        }
        a2 = *(char **)&a2[v5];
      }
      while ( a2 != (char *)&utl::_TreeSentinel );
      if ( v4 != v3 && *((int *)v4 + 6) <= 8 && v4 != (char *)-32LL )
        return *((_QWORD *)v4 + 4) << 10;
    }
  }
  v7 = *this;
  v19 = 0;
  v18 = 0;
  v8 = RegReadDWORDValueNoThrow((HKEY)v7, (const wchar_t *)a2, L"MaxSize", &v19);
  RegReadDWORDValueNoThrow((HKEY)*this, v9, L"MaxSizeUpper", &v18);
  if ( (v8 & 0xFFFFFFFD) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, v8);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v8, v10, 399);
    throw (EvtException *)pExceptionObject;
  }
  v11 = (const wchar_t *)this[4];
  v12 = (this[5] - (ChannelConfigReader *)v11) >> 1;
  v16 = v12;
  v13 = v19 | ((unsigned __int64)v18 << 32);
  v15 = v11;
  if ( IsSecurityChannel(&v15) )
  {
    if ( !v13 )
      return 41943040;
    v14 = 20971520;
  }
  else
  {
    v15 = v11;
    v16 = v12;
    if ( IsCoreChannel(&v15) )
    {
      if ( !v13 )
        return 20971520;
    }
    else if ( !v13 )
    {
      return 1052672;
    }
    v14 = 1052672;
  }
  if ( v13 < v14 )
    return v14;
  return v13;
}

```

## disassembly

```asm
0x140015b0c  mov     [rsp-18h+arg_10], rbx
0x140015b11  push    rbp
0x140015b12  push    rsi
0x140015b13  push    rdi
0x140015b14  mov     rbp, rsp
0x140015b17  sub     rsp, 60h
0x140015b1b  cmp     byte ptr [rcx+80h], 0
0x140015b22  mov     rdi, rcx
0x140015b25  jz      short loc_140015B7E
0x140015b27  lea     rax, [rcx+40h]
0x140015b2b  cmp     [rax+10h], rax
0x140015b2f  jz      short loc_140015B7E
0x140015b31  mov     rdx, [rax]
0x140015b34  mov     rcx, rax
0x140015b37  cmp     dword ptr [rdx+18h], 8
0x140015b3b  jge     short loc_140015B45
0x140015b3d  mov     r8d, 10h
0x140015b43  jmp     short loc_140015B4E
0x140015b45  mov     rcx, rdx
0x140015b48  mov     r8d, 8
0x140015b4e  mov     rdx, [r8+rdx]; wchar_t *
0x140015b52  lea     r8, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140015b59  cmp     rdx, r8
0x140015b5c  jnz     short loc_140015B37
0x140015b5e  cmp     rcx, rax
0x140015b61  jz      short loc_140015B7E
0x140015b63  cmp     dword ptr [rcx+18h], 8
0x140015b67  jg      short loc_140015B7E
0x140015b69  lea     rax, [rcx+20h]
0x140015b6d  test    rax, rax
0x140015b70  jz      short loc_140015B7E
0x140015b72  mov     rax, [rax]
0x140015b75  shl     rax, 0Ah
0x140015b79  jmp     loc_140015C94
0x140015b7e  mov     rcx, [rdi]; HKEY
0x140015b81  lea     r9, [rbp+arg_8]; unsigned int *
0x140015b85  lea     r8, aMaxsize_0; "MaxSize"
0x140015b8c  mov     [rbp+arg_8], 0
0x140015b93  mov     [rbp+arg_0], 0
0x140015b9a  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x140015b9f  mov     rcx, [rdi]; HKEY
0x140015ba2  lea     r9, [rbp+arg_0]; unsigned int *
0x140015ba6  lea     r8, aMaxsizeupper; "MaxSizeUpper"
0x140015bad  mov     ebx, eax
0x140015baf  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x140015bb4  test    ebx, 0FFFFFFFDh
0x140015bba  jz      short loc_140015C15
0x140015bbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140015bc3  lea     rax, WPP_GLOBAL_Control
0x140015bca  cmp     rcx, rax
0x140015bcd  jz      short loc_140015BF3
0x140015bcf  test    byte ptr [rcx+1Ch], 4
0x140015bd3  jz      short loc_140015BF3
0x140015bd5  cmp     byte ptr [rcx+19h], 2
0x140015bd9  jb      short loc_140015BF3
0x140015bdb  mov     rcx, [rcx+10h]
0x140015bdf  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x140015be6  mov     edx, 22h ; '"'
0x140015beb  mov     r9d, ebx
0x140015bee  call    WPP_SF_d
0x140015bf3  mov     r9d, 18Fh; int
0x140015bf9  lea     rcx, [rbp+pExceptionObject]; this
0x140015bfd  mov     edx, ebx; unsigned int
0x140015bff  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140015c04  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140015c0b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140015c0f  call    _CxxThrowException_0
0x140015c15  mov     rsi, [rdi+20h]
0x140015c19  lea     rcx, [rbp+var_40]
0x140015c1d  mov     rdi, [rdi+28h]
0x140015c21  mov     eax, [rbp+arg_8]
0x140015c24  sub     rdi, rsi
0x140015c27  mov     ebx, [rbp+arg_0]
0x140015c2a  sar     rdi, 1
0x140015c2d  shl     rbx, 20h
0x140015c31  mov     [rbp+var_38], rdi
0x140015c35  or      rbx, rax
0x140015c38  mov     [rbp+var_40], rsi
0x140015c3c  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x140015c41  test    al, al
0x140015c43  jz      short loc_140015C58
0x140015c45  test    rbx, rbx
0x140015c48  jnz     short loc_140015C51
0x140015c4a  mov     eax, 2800000h
0x140015c4f  jmp     short loc_140015C94
0x140015c51  mov     eax, 1400000h
0x140015c56  jmp     short loc_140015C8A
0x140015c58  lea     rcx, [rbp+var_40]
0x140015c5c  mov     [rbp+var_40], rsi
0x140015c60  mov     [rbp+var_38], rdi
0x140015c64  call    ?IsCoreChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsCoreChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x140015c69  test    al, al
0x140015c6b  jz      short loc_140015C79
0x140015c6d  test    rbx, rbx
0x140015c70  jnz     short loc_140015C85
0x140015c72  mov     eax, 1400000h
0x140015c77  jmp     short loc_140015C94
0x140015c79  test    rbx, rbx
0x140015c7c  jnz     short loc_140015C85
0x140015c7e  mov     eax, 101000h
0x140015c83  jmp     short loc_140015C94
0x140015c85  mov     eax, 101000h
0x140015c8a  cmp     rbx, rax
0x140015c8d  cmovb   rbx, rax
0x140015c91  mov     rax, rbx
0x140015c94  mov     rbx, [rsp+60h+arg_10]
0x140015c9c  add     rsp, 60h
0x140015ca0  pop     rdi
0x140015ca1  pop     rsi
0x140015ca2  pop     rbp
0x140015ca3  retn
```
