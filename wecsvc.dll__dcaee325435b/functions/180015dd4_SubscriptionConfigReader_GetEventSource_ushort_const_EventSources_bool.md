# SubscriptionConfigReader::GetEventSource(ushort const *,_EventSources &,bool)

- ea: `0x180015dd4`
- end: `0x180015f71`
- name: `?GetEventSource@SubscriptionConfigReader@@QEBA_NPEBGAEAU_EventSources@@_N@Z`
- size: `413`
- prototype: `bool __fastcall(HKEY *this, const unsigned __int16 *, struct _EventSources *, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180004760`
- `0x18001483c`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003e6c`
- `0x1800062d4`
- `0x1800064e0`
- `0x18000669c`
- `0x180015c30`
- `0x180015dd4`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015e64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015e64`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall SubscriptionConfigReader::GetEventSource(
        HKEY *this,
        const unsigned __int16 *a2,
        struct _EventSources *a3,
        bool a4)
{
  const WCHAR *v8; // rdx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  bool EventSource; // bl
  __int64 v13; // rdx
  HKEY phkResult; // [rsp+30h] [rbp-39h] BYREF
  void **pExceptionObject; // [rsp+38h] [rbp-31h] BYREF
  char v16; // [rsp+40h] [rbp-29h]
  const char *v17; // [rsp+48h] [rbp-21h]
  __int64 v18; // [rsp+50h] [rbp-19h]
  __int64 v19; // [rsp+58h] [rbp-11h]
  unsigned int v20; // [rsp+60h] [rbp-9h]
  int v21; // [rsp+64h] [rbp-5h]
  int v22; // [rsp+68h] [rbp-1h]
  LPCWSTR lpSubKey[3]; // [rsp+70h] [rbp+7h] BYREF
  unsigned __int64 v24; // [rsp+88h] [rbp+1Fh]

  v24 = 7;
  lpSubKey[2] = 0;
  LOWORD(lpSubKey[0]) = 0;
  std::wstring::assign(lpSubKey, L"EventSources\\");
  std::wstring::append(lpSubKey, a2);
  phkResult = 0;
  v8 = (const WCHAR *)lpSubKey;
  if ( v24 >= 8 )
    v8 = lpSubKey[0];
  v9 = RegOpenKeyExW(this[2], v8, 0, 0x20019u, &phkResult);
  if ( v9 == 2 )
  {
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
    LOBYTE(v10) = 1;
    std::wstring::_Tidy(lpSubKey, v10, 0);
    return 0;
  }
  else
  {
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, v9);
      }
      v16 = 0;
      v17 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v18 = 0;
      v19 = 0;
      v20 = v9;
      v21 = -1;
      v22 = 271;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    EventSource = SubscriptionConfigReader::GetEventSource((SubscriptionConfigReader *)this, phkResult, a2, a3, a4);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
    LOBYTE(v13) = 1;
    std::wstring::_Tidy(lpSubKey, v13, 0);
    return EventSource;
  }
}

```

## disassembly

```asm
0x180015dd4  mov     [rsp-8+arg_18], rbx
0x180015dd9  push    rbp
0x180015dda  push    rsi
0x180015ddb  push    rdi
0x180015ddc  push    r14
0x180015dde  push    r15
0x180015de0  lea     rbp, [rsp-37h]
0x180015de5  sub     rsp, 0A0h
0x180015dec  mov     rax, cs:__security_cookie
0x180015df3  xor     rax, rsp
0x180015df6  mov     [rbp+57h+var_30], rax
0x180015dfa  mov     r14b, r9b
0x180015dfd  mov     r15, r8
0x180015e00  mov     rsi, rdx
0x180015e03  mov     rdi, rcx
0x180015e06  mov     [rbp+57h+var_38], 7
0x180015e0e  mov     [rbp+57h+var_40], 0
0x180015e16  xor     eax, eax
0x180015e18  mov     word ptr [rbp+57h+lpSubKey], ax
0x180015e1c  lea     rdx, aEventsources_1; "EventSources\\"
0x180015e23  lea     rcx, [rbp+57h+lpSubKey]
0x180015e27  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180015e2c  mov     rdx, rsi
0x180015e2f  lea     rcx, [rbp+57h+lpSubKey]
0x180015e33  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180015e38  mov     [rbp+57h+var_90], 0
0x180015e40  lea     rdx, [rbp+57h+lpSubKey]
0x180015e44  cmp     [rbp+57h+var_38], 8
0x180015e49  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180015e4e  lea     rax, [rbp+57h+var_90]
0x180015e52  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180015e57  mov     r9d, 20019h; samDesired
0x180015e5d  xor     r8d, r8d; ulOptions
0x180015e60  mov     rcx, [rdi+10h]; hKey
0x180015e64  call    cs:__imp_RegOpenKeyExW
0x180015e6a  mov     ebx, eax
0x180015e6c  cmp     eax, 2
0x180015e6f  jnz     short loc_180015E90
0x180015e71  lea     rcx, [rbp+57h+var_90]; this
0x180015e75  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180015e7a  nop
0x180015e7b  xor     r8d, r8d
0x180015e7e  mov     dl, 1
0x180015e80  lea     rcx, [rbp+57h+lpSubKey]
0x180015e84  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015e89  xor     al, al
0x180015e8b  jmp     loc_180015F4E
0x180015e90  test    ebx, ebx
0x180015e92  jz      loc_180015F1B
0x180015e98  lea     rax, WPP_GLOBAL_Control
0x180015e9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ea6  cmp     rcx, rax
0x180015ea9  jz      short loc_180015ECF
0x180015eab  test    byte ptr [rcx+1Ch], 40h
0x180015eaf  jz      short loc_180015ECF
0x180015eb1  cmp     byte ptr [rcx+19h], 2
0x180015eb5  jb      short loc_180015ECF
0x180015eb7  mov     edx, 14h
0x180015ebc  mov     r9d, ebx
0x180015ebf  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x180015ec6  mov     rcx, [rcx+10h]
0x180015eca  call    WPP_SF_D
0x180015ecf  mov     [rbp+57h+var_80], 0
0x180015ed3  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x180015eda  mov     [rbp+57h+var_78], rax
0x180015ede  mov     [rbp+57h+var_70], 0
0x180015ee6  mov     [rbp+57h+var_68], 0
0x180015eee  mov     [rbp+57h+var_60], ebx
0x180015ef1  mov     [rbp+57h+var_5C], 0FFFFFFFFh
0x180015ef8  mov     [rbp+57h+var_58], 10Fh
0x180015eff  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180015f06  mov     [rbp+57h+pExceptionObject], rax
0x180015f0a  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180015f11  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180015f15  call    _CxxThrowException_0
0x180015f1b  mov     byte ptr [rsp+0C0h+phkResult], r14b; bool
0x180015f20  mov     r9, r15; struct _EventSources *
0x180015f23  mov     r8, rsi; unsigned __int16 *
0x180015f26  mov     rdx, [rbp+57h+var_90]; HKEY
0x180015f2a  mov     rcx, rdi; this
0x180015f2d  call    ?GetEventSource@SubscriptionConfigReader@@QEBA_NPEAUHKEY__@@PEBGAEAU_EventSources@@_N@Z; SubscriptionConfigReader::GetEventSource(HKEY__ *,ushort const *,_EventSources &,bool)
0x180015f32  mov     bl, al
0x180015f34  lea     rcx, [rbp+57h+var_90]; this
0x180015f38  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180015f3d  nop
0x180015f3e  xor     r8d, r8d
0x180015f41  mov     dl, 1
0x180015f43  lea     rcx, [rbp+57h+lpSubKey]
0x180015f47  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015f4c  mov     al, bl
0x180015f4e  mov     rcx, [rbp+57h+var_30]
0x180015f52  xor     rcx, rsp; StackCookie
0x180015f55  call    __security_check_cookie
0x180015f5a  mov     rbx, [rsp+0C0h+arg_18]
0x180015f62  add     rsp, 0A0h
0x180015f69  pop     r15
0x180015f6b  pop     r14
0x180015f6d  pop     rdi
0x180015f6e  pop     rsi
0x180015f6f  pop     rbp
0x180015f70  retn
```
