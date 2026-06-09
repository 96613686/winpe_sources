# InitWSManConnectionOptions(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,_WSMAN_CONNECTION_OPTIONS &)

- ea: `0x18000dc4c`
- end: `0x18000dd9d`
- name: `?InitWSManConnectionOptions@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_WSMAN_CONNECTION_OPTIONS@@@Z`
- size: `337`
- prototype: `void __fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180008828`
- `0x180009a10`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18000669c`
- `0x18000dc4c`
- `0x18001fe13`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcbc`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000dc9a`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000dc9a`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18000dcae`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18000dcae`

## string_xrefs

- `0x18000dd05`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall InitWSManConnectionOptions(_QWORD *a1, __int64 a2)
{
  _QWORD *v3; // rbx
  LCID ThreadLocale; // eax
  DWORD LastError; // ebx
  void **pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  char v7; // [rsp+28h] [rbp-D8h]
  const char *v8; // [rsp+30h] [rbp-D0h]
  __int64 v9; // [rsp+38h] [rbp-C8h]
  __int64 v10; // [rsp+40h] [rbp-C0h]
  DWORD v11; // [rsp+48h] [rbp-B8h]
  int v12; // [rsp+4Ch] [rbp-B4h]
  int v13; // [rsp+50h] [rbp-B0h]
  WCHAR Name[88]; // [rsp+60h] [rbp-A0h] BYREF

  *(_DWORD *)a2 = 24;
  v3 = a1;
  if ( !a1[2] )
  {
    memset_0(Name, 0, 0xAAu);
    ThreadLocale = GetThreadLocale();
    if ( !LCIDToLocaleName(ThreadLocale, Name, 85, 0) )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, LastError);
      }
      v7 = 0;
      v8 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
      v9 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v10 = 0;
      v11 = LastError;
      v12 = -1;
      v13 = 674;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    std::wstring::assign((__int64)v3, (__int64)Name);
  }
  if ( v3[2] )
  {
    if ( v3[3] >= 8u )
      v3 = (_QWORD *)*v3;
    *(_QWORD *)(a2 + 16) = v3;
  }
}

```

## disassembly

```asm
0x18000dc4c  mov     [rsp-8+arg_10], rbx
0x18000dc51  mov     [rsp-8+arg_18], rdi
0x18000dc56  push    rbp
0x18000dc57  lea     rbp, [rsp-20h]
0x18000dc5c  sub     rsp, 120h
0x18000dc63  mov     rax, cs:__security_cookie
0x18000dc6a  xor     rax, rsp
0x18000dc6d  mov     [rbp+20h+var_10], rax
0x18000dc71  mov     dword ptr [rdx], 18h
0x18000dc77  mov     rdi, rdx
0x18000dc7a  cmp     qword ptr [rcx+10h], 0
0x18000dc7f  mov     rbx, rcx
0x18000dc82  jnz     loc_18000DD67
0x18000dc88  xor     edx, edx; Val
0x18000dc8a  lea     rcx, [rsp+120h+Name]; void *
0x18000dc8f  mov     r8d, 0AAh; Size
0x18000dc95  call    memset_0
0x18000dc9a  call    cs:__imp_GetThreadLocale
0x18000dca0  xor     r9d, r9d; dwFlags
0x18000dca3  lea     rdx, [rsp+120h+Name]; lpName
0x18000dca8  mov     ecx, eax; Locale
0x18000dcaa  lea     r8d, [r9+55h]; cchName
0x18000dcae  call    cs:__imp_LCIDToLocaleName
0x18000dcb4  test    eax, eax
0x18000dcb6  jnz     loc_18000DD5A
0x18000dcbc  call    cs:__imp_GetLastError
0x18000dcc2  mov     ebx, eax
0x18000dcc4  mov     eax, 507h
0x18000dcc9  test    ebx, ebx
0x18000dccb  cmovz   ebx, eax
0x18000dcce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcd5  lea     rax, WPP_GLOBAL_Control
0x18000dcdc  cmp     rcx, rax
0x18000dcdf  jz      short loc_18000DD05
0x18000dce1  test    byte ptr [rcx+1Ch], 10h
0x18000dce5  jz      short loc_18000DD05
0x18000dce7  cmp     byte ptr [rcx+19h], 2
0x18000dceb  jb      short loc_18000DD05
0x18000dced  mov     rcx, [rcx+10h]
0x18000dcf1  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000dcf8  mov     edx, 18h
0x18000dcfd  mov     r9d, ebx
0x18000dd00  call    WPP_SF_D
0x18000dd05  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000dd0c  mov     [rsp+120h+var_F8], 0
0x18000dd11  mov     [rsp+120h+var_F0], rax
0x18000dd16  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000dd1d  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000dd24  mov     [rsp+120h+var_E8], 0
0x18000dd2d  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18000dd32  mov     [rsp+120h+pExceptionObject], rax
0x18000dd37  mov     [rsp+120h+var_E0], 0
0x18000dd40  mov     [rsp+120h+var_D8], ebx
0x18000dd44  mov     [rsp+120h+var_D4], 0FFFFFFFFh
0x18000dd4c  mov     [rsp+120h+var_D0], 2A2h
0x18000dd54  call    _CxxThrowException_0
0x18000dd5a  lea     rdx, [rsp+120h+Name]
0x18000dd5f  mov     rcx, rbx
0x18000dd62  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000dd67  cmp     qword ptr [rbx+10h], 0
0x18000dd6c  jbe     short loc_18000DD7C
0x18000dd6e  cmp     qword ptr [rbx+18h], 8
0x18000dd73  jb      short loc_18000DD78
0x18000dd75  mov     rbx, [rbx]
0x18000dd78  mov     [rdi+10h], rbx
0x18000dd7c  mov     rcx, [rbp+20h+var_10]
0x18000dd80  xor     rcx, rsp; StackCookie
0x18000dd83  call    __security_check_cookie
0x18000dd88  lea     r11, [rsp+120h+var_s0]
0x18000dd90  mov     rbx, [r11+20h]
0x18000dd94  mov     rdi, [r11+28h]
0x18000dd98  mov     rsp, r11
0x18000dd9b  pop     rbp
0x18000dd9c  retn
```
