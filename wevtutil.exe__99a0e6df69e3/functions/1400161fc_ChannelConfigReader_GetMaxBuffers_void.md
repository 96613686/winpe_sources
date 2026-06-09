# ChannelConfigReader::GetMaxBuffers(void)

- ea: `0x1400161fc`
- end: `0x14001627e`
- name: `?GetMaxBuffers@ChannelConfigReader@@QEBAKXZ`
- size: `130`
- prototype: `unsigned int __fastcall(ChannelConfigReader *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000750c`

## callees

- `0x1400161fc`
- `0x140016284`
- `0x14001b580`
- `0x14001b5b4`

## pseudocode

```c
__int64 __fastcall ChannelConfigReader::GetMaxBuffers(ChannelConfigReader *this)
{
  unsigned int v2; // ebx
  __int64 v3; // rbp
  __int64 v4; // rsi
  __int64 v5; // rsi
  __int64 v7; // [rsp+20h] [rbp-38h] BYREF
  __int64 v8; // [rsp+28h] [rbp-30h]

  if ( (unsigned int)(*((_DWORD *)this + 34) - 2) > 1 )
  {
    v3 = *((_QWORD *)this + 4);
    v4 = *((_QWORD *)this + 5);
    v7 = v3;
    v5 = (v4 - v3) >> 1;
    v8 = v5;
    if ( (unsigned __int8)IsSystemChannel(&v7) || (v7 = v3, v2 = 64, v8 = v5, IsSecurityChannel(&v7)) )
      v2 = 16;
  }
  else
  {
    v2 = 10;
  }
  return GetDWORDHelper(*(_QWORD *)this, v2, L"MaxBuffers");
}

```

## disassembly

```asm
0x1400161fc  push    rbx
0x1400161fe  push    rbp
0x1400161ff  push    rsi
0x140016200  push    rdi
0x140016201  sub     rsp, 38h
0x140016205  mov     eax, [rcx+88h]
0x14001620b  mov     rdi, rcx
0x14001620e  sub     eax, 2
0x140016211  cmp     eax, 1
0x140016214  ja      short loc_14001621D
0x140016216  mov     ebx, 0Ah
0x14001621b  jmp     short loc_140016265
0x14001621d  mov     rbp, [rcx+20h]
0x140016221  mov     rsi, [rcx+28h]
0x140016225  lea     rcx, [rsp+58h+var_38]
0x14001622a  sub     rsi, rbp
0x14001622d  mov     [rsp+58h+var_38], rbp
0x140016232  sar     rsi, 1
0x140016235  mov     [rsp+58h+var_30], rsi
0x14001623a  call    ?IsSystemChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSystemChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14001623f  test    al, al
0x140016241  jnz     short loc_140016260
0x140016243  lea     rcx, [rsp+58h+var_38]
0x140016248  mov     [rsp+58h+var_38], rbp
0x14001624d  mov     ebx, 40h ; '@'
0x140016252  mov     [rsp+58h+var_30], rsi
0x140016257  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14001625c  test    al, al
0x14001625e  jz      short loc_140016265
0x140016260  mov     ebx, 10h
0x140016265  mov     rcx, [rdi]
0x140016268  lea     r8, aMaxbuffers_0; "MaxBuffers"
0x14001626f  mov     edx, ebx
0x140016271  add     rsp, 38h
0x140016275  pop     rdi
0x140016276  pop     rsi
0x140016277  pop     rbp
0x140016278  pop     rbx
0x140016279  jmp     GetDWORDHelper
```
