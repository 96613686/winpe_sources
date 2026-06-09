# ChannelConfigReader::GetIsolation(void)

- ea: `0x14001aec0`
- end: `0x14001af44`
- name: `?GetIsolation@ChannelConfigReader@@QEBA?AW4_EVT_CHANNEL_ISOLATION_TYPE@@XZ`
- size: `132`
- prototype: `enum _EVT_CHANNEL_ISOLATION_TYPE __fastcall(ChannelConfigReader *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140006de0`
- `0x1400073ec`

## callees

- `0x140008b40`
- `0x140016284`
- `0x14001aec0`
- `0x14001b5b4`

## pseudocode

```c
__int64 __fastcall ChannelConfigReader::GetIsolation(ChannelConfigReader *this)
{
  __int64 v1; // rdi
  __int64 v3; // rbx
  int v4; // r8d
  _QWORD v6[3]; // [rsp+20h] [rbp-18h] BYREF

  v1 = *((_QWORD *)this + 4);
  v3 = (*((_QWORD *)this + 5) - v1) >> 1;
  if ( v3 == 6
    && !(unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(v1, (__int64)L"System", 6) )
  {
    return (unsigned int)(v4 - 5);
  }
  v6[0] = v1;
  v6[1] = v3;
  if ( IsSecurityChannel(v6) )
    return 2;
  else
    return GetDWORDHelper(*(_QWORD *)this, 0, L"Isolation");
}

```

## disassembly

```asm
0x14001aec0  mov     [rsp+arg_0], rbx
0x14001aec5  mov     [rsp+arg_8], rsi
0x14001aeca  push    rdi
0x14001aecb  sub     rsp, 30h
0x14001aecf  mov     rdi, [rcx+20h]
0x14001aed3  mov     r8d, 6
0x14001aed9  mov     rbx, [rcx+28h]
0x14001aedd  mov     rsi, rcx
0x14001aee0  sub     rbx, rdi
0x14001aee3  sar     rbx, 1
0x14001aee6  cmp     rbx, r8
0x14001aee9  jnz     short loc_14001AF04
0x14001aeeb  lea     rdx, aSystem; "System"
0x14001aef2  mov     rcx, rdi
0x14001aef5  call    ?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x14001aefa  test    eax, eax
0x14001aefc  jnz     short loc_14001AF04
0x14001aefe  lea     eax, [r8-5]
0x14001af02  jmp     short loc_14001AF34
0x14001af04  lea     rcx, [rsp+38h+var_18]
0x14001af09  mov     [rsp+38h+var_18], rdi
0x14001af0e  mov     [rsp+38h+var_10], rbx
0x14001af13  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14001af18  test    al, al
0x14001af1a  jz      short loc_14001AF23
0x14001af1c  mov     eax, 2
0x14001af21  jmp     short loc_14001AF34
0x14001af23  mov     rcx, [rsi]
0x14001af26  lea     r8, aIsolation; "Isolation"
0x14001af2d  xor     edx, edx
0x14001af2f  call    GetDWORDHelper
0x14001af34  mov     rbx, [rsp+38h+arg_0]
0x14001af39  mov     rsi, [rsp+38h+arg_8]
0x14001af3e  add     rsp, 30h
0x14001af42  pop     rdi
0x14001af43  retn
```
