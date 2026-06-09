# SubscriptionConfigEnumerator::SubscriptionConfigEnumerator(HKEY__ *,ushort const *)

- ea: `0x180014310`
- end: `0x1800143ef`
- name: `??0SubscriptionConfigEnumerator@@QEAA@PEAUHKEY__@@PEBG@Z`
- size: `223`
- prototype: `SubscriptionConfigEnumerator *__fastcall(SubscriptionConfigEnumerator *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004434`
- `0x180005ad0`

## callees

- `0x180003810`
- `0x1800062d4`
- `0x1800064e0`
- `0x180011c60`
- `0x180012c6c`
- `0x180013eac`
- `0x18001fe50`

## pseudocode

```c
SubscriptionConfigEnumerator *__fastcall SubscriptionConfigEnumerator::SubscriptionConfigEnumerator(
        SubscriptionConfigEnumerator *this,
        HKEY a2,
        const unsigned __int16 *a3)
{
  const WCHAR *v4; // r8
  __int64 v5; // rdx
  LPCWSTR lpSubKey[4]; // [rsp+30h] [rbp-38h] BYREF

  *(_QWORD *)this = &wmi::RefBase::`vftable';
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &ConfigEnumerator::`vftable';
  RegistryKeyEnumerator::RegistryKeyEnumerator((SubscriptionConfigEnumerator *)((char *)this + 16), a2, a3);
  *((_QWORD *)this + 9) = -2147483646;
  std::wstring::wstring((__int64)this + 80, (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector");
  *(_QWORD *)this = &ConfigEnumerator::`vftable';
  std::operator+<unsigned short>(lpSubKey, (char *)this + 80);
  std::wstring::append(lpSubKey, L"Subscriptions");
  v4 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] >= (LPCWSTR)8 )
    v4 = lpSubKey[0];
  RegistryKeyEnumerator::Reset((SubscriptionConfigEnumerator *)((char *)this + 16), *((HKEY *)this + 9), v4);
  LOBYTE(v5) = 1;
  std::wstring::_Tidy(lpSubKey, v5, 0);
  return this;
}

```

## disassembly

```asm
0x180014310  mov     [rsp+arg_8], rbx
0x180014315  mov     [rsp+arg_10], rsi
0x18001431a  push    rdi
0x18001431b  sub     rsp, 60h
0x18001431f  mov     rax, cs:__security_cookie
0x180014326  xor     rax, rsp
0x180014329  mov     [rsp+68h+var_18], rax
0x18001432e  mov     rsi, rcx
0x180014331  mov     [rsp+68h+var_48], rcx
0x180014336  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x18001433d  mov     [rcx], rax
0x180014340  mov     dword ptr [rcx+8], 0
0x180014347  lea     rax, ??_7ConfigEnumerator@@6B@; const ConfigEnumerator::`vftable'
0x18001434e  mov     [rcx], rax
0x180014351  add     rcx, 10h; this
0x180014355  call    ??0RegistryKeyEnumerator@@QEAA@PEAUHKEY__@@PEBG@Z; RegistryKeyEnumerator::RegistryKeyEnumerator(HKEY__ *,ushort const *)
0x18001435a  nop
0x18001435b  mov     qword ptr [rsi+48h], 0FFFFFFFF80000002h
0x180014363  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001436a  lea     rcx, [rsi+50h]
0x18001436e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180014373  nop
0x180014374  lea     rax, ??_7ConfigEnumerator@@6B@; const ConfigEnumerator::`vftable'
0x18001437b  mov     [rsi], rax
0x18001437e  lea     rdx, [rsi+50h]
0x180014382  lea     rcx, [rsp+68h+lpSubKey]
0x180014387  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@G@Z; std::operator+<ushort>(std::wstring const &,ushort)
0x18001438c  nop
0x18001438d  lea     rdx, aSubscriptions_0; "Subscriptions"
0x180014394  lea     rcx, [rsp+68h+lpSubKey]
0x180014399  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18001439e  lea     r8, [rsp+68h+lpSubKey]
0x1800143a3  cmp     [rsp+68h+var_20], 8
0x1800143a9  cmovnb  r8, [rsp+68h+lpSubKey]; lpSubKey
0x1800143af  mov     rdx, [rsi+48h]; hKey
0x1800143b3  lea     rcx, [rsi+10h]; this
0x1800143b7  call    ?Reset@RegistryKeyEnumerator@@QEAAXPEAUHKEY__@@PEBG@Z; RegistryKeyEnumerator::Reset(HKEY__ *,ushort const *)
0x1800143bc  nop
0x1800143bd  xor     r8d, r8d
0x1800143c0  mov     dl, 1
0x1800143c2  lea     rcx, [rsp+68h+lpSubKey]
0x1800143c7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800143cc  nop
0x1800143cd  mov     rax, rsi
0x1800143d0  mov     rcx, [rsp+68h+var_18]
0x1800143d5  xor     rcx, rsp; StackCookie
0x1800143d8  call    __security_check_cookie
0x1800143dd  lea     r11, [rsp+68h+var_8]
0x1800143e2  mov     rbx, [r11+18h]
0x1800143e6  mov     rsi, [r11+20h]
0x1800143ea  mov     rsp, r11
0x1800143ed  pop     rdi
0x1800143ee  retn
```
