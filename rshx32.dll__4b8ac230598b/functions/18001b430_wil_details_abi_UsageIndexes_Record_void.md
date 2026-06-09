# wil::details_abi::UsageIndexes::Record(void)

- ea: `0x18001b430`
- end: `0x18001b535`
- name: `?Record@UsageIndexes@details_abi@wil@@QEAAXXZ`
- size: `261`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *this, __int64, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180019cf0`
- `0x18001b6f0`
- `0x18001c090`

## callees

- `0x18001b430`
- `0x18001bcbc`
- `0x18001d370`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexes::Record(
        wil::details_abi::UsageIndexes *this,
        __int64 a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  __int64 v5; // [rsp+20h] [rbp-40h] BYREF
  __int64 v6; // [rsp+28h] [rbp-38h]
  __int64 v7; // [rsp+30h] [rbp-30h]
  __int64 v8; // [rsp+38h] [rbp-28h]
  __int64 v9; // [rsp+40h] [rbp-20h]
  __int64 v10; // [rsp+48h] [rbp-18h]

  if ( *((_BYTE *)this + 56) )
  {
    v5 = __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_1;
    v6 = __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_2;
    v7 = __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_3;
    wil::details_abi::RecordWnfUsageIndex(
      (wil::details_abi *)&v5,
      (const struct __WIL__WNF_STATE_NAME *)3,
      (unsigned __int64)this,
      a4);
  }
  if ( *((_BYTE *)this + 120) )
  {
    v5 = __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_1;
    v6 = __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_2;
    v7 = __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_3;
    wil::details_abi::RecordWnfUsageIndex(
      (wil::details_abi *)&v5,
      (const struct __WIL__WNF_STATE_NAME *)3,
      (unsigned __int64)this + 64,
      a4);
  }
  if ( *((_BYTE *)this + 184) )
  {
    v5 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_1;
    v6 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_2;
    v7 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_3;
    v8 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_4;
    v9 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_5;
    v10 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_6;
    wil::details_abi::RecordWnfUsageIndex(
      (wil::details_abi *)&v5,
      (const struct __WIL__WNF_STATE_NAME *)6,
      (unsigned __int64)this + 128,
      a4);
  }
}

```

## disassembly

```asm
0x18001b430  mov     [rsp-8+arg_8], rbx
0x18001b435  push    rbp
0x18001b436  mov     rbp, rsp
0x18001b439  sub     rsp, 60h
0x18001b43d  mov     rax, cs:__security_cookie
0x18001b444  xor     rax, rsp
0x18001b447  mov     [rbp+var_10], rax
0x18001b44b  cmp     byte ptr [rcx+38h], 0
0x18001b44f  mov     rbx, rcx
0x18001b452  jz      short loc_18001B486
0x18001b454  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_1@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_1
0x18001b45b  mov     r8, rcx; unsigned __int64
0x18001b45e  mov     [rbp+var_40], rax
0x18001b462  lea     rcx, [rbp+var_40]; this
0x18001b466  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_2@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_2
0x18001b46d  mov     edx, 3; struct __WIL__WNF_STATE_NAME *
0x18001b472  mov     [rbp+var_38], rax
0x18001b476  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_3@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_3
0x18001b47d  mov     [rbp+var_30], rax
0x18001b481  call    ?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z; wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)
0x18001b486  lea     r8, [rbx+40h]; unsigned __int64
0x18001b48a  cmp     byte ptr [r8+38h], 0
0x18001b48f  jz      short loc_18001B4C0
0x18001b491  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_USAGE_TRACKING_1@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_1
0x18001b498  lea     rcx, [rbp+var_40]; this
0x18001b49c  mov     [rbp+var_40], rax
0x18001b4a0  mov     edx, 3; struct __WIL__WNF_STATE_NAME *
0x18001b4a5  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_USAGE_TRACKING_2@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_2
0x18001b4ac  mov     [rbp+var_38], rax
0x18001b4b0  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_USAGE_TRACKING_3@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_3
0x18001b4b7  mov     [rbp+var_30], rax
0x18001b4bb  call    ?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z; wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)
0x18001b4c0  lea     r8, [rbx+80h]; unsigned __int64
0x18001b4c7  cmp     byte ptr [r8+38h], 0
0x18001b4cc  jz      short loc_18001B51E
0x18001b4ce  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_1@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_1
0x18001b4d5  lea     rcx, [rbp+var_40]; this
0x18001b4d9  mov     [rbp+var_40], rax
0x18001b4dd  mov     edx, 6; struct __WIL__WNF_STATE_NAME *
0x18001b4e2  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_2@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_2
0x18001b4e9  mov     [rbp+var_38], rax
0x18001b4ed  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_3@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_3
0x18001b4f4  mov     [rbp+var_30], rax
0x18001b4f8  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_4@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_4
0x18001b4ff  mov     [rbp+var_28], rax
0x18001b503  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_5@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_5
0x18001b50a  mov     [rbp+var_20], rax
0x18001b50e  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_6@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_6
0x18001b515  mov     [rbp+var_18], rax
0x18001b519  call    ?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z; wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)
0x18001b51e  mov     rcx, [rbp+var_10]
0x18001b522  xor     rcx, rsp; StackCookie
0x18001b525  call    __security_check_cookie
0x18001b52a  mov     rbx, [rsp+60h+arg_8]
0x18001b52f  add     rsp, 60h
0x18001b533  pop     rbp
0x18001b534  retn
```
