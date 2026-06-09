# SaveBookmarkAndOrHeartbeatTime(ushort const *,ushort const *,ushort const *,bool,ulong,ulong,bool)

- ea: `0x18000fd88`
- end: `0x18000ff35`
- name: `?SaveBookmarkAndOrHeartbeatTime@@YAXPEBG00_NKK1@Z`
- size: `429`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, char, unsigned int, unsigned int, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000e2f8`
- `0x18000fc80`

## callees

- `0x180003810`
- `0x180003e6c`
- `0x1800062d4`
- `0x18000ef44`
- `0x18000fd88`
- `0x18001274c`
- `0x1800129f0`
- `0x180012ac0`
- `0x180012b94`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fe33`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fe89`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fe99`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fea9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000feb9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fec9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fed9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fe33`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fe89`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fe99`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fea9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000feb9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fec9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fed9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fdce`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fdce`

## pseudocode

```c
void __fastcall SaveBookmarkAndOrHeartbeatTime(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4,
        unsigned int a5,
        unsigned int a6,
        bool a7)
{
  HKEY v8; // rbx
  unsigned __int64 v9; // rdi
  __int64 v10; // rdx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-40h] BYREF
  unsigned __int64 v12; // [rsp+28h] [rbp-38h] BYREF
  HKEY v13; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v14[32]; // [rsp+38h] [rbp-28h] BYREF

  v8 = OpenSubscriptionEventSourceKey((__int64)a1, (__int64)a2, 0x2001Fu, a4);
  v13 = v8;
  v12 = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v9 = (unsigned __int64)SystemTimeAsFileTime;
  if ( a7 )
  {
    RegReadQWORDValue(v8, L"LastHeartbeatTime", &v12);
    RegWriteDWORDValue(v8, L"BatchEventsProcessingTime", (v9 - v12) / 0x3E8);
  }
  else
  {
    RegDeleteValueW(v8, L"BatchEventsProcessingTime");
  }
  RegWriteQWORDValue(v8, L"LastHeartbeatTime", v9);
  if ( a3 )
  {
    std::wstring::wstring(v14, a3);
    RegWriteStringValue(v8, L"Bookmark", v14);
    LOBYTE(v10) = 1;
    std::wstring::_Tidy(v14, v10, 0);
    RegDeleteValueW(v8, L"LastError");
    RegDeleteValueW(v8, L"LastErrorCount");
    RegDeleteValueW(v8, L"LastFaultMessage");
    RegDeleteValueW(v8, L"LastErrorTime");
  }
  RegDeleteValueW(v8, L"BatchEventsDropped");
  RegDeleteValueW(v8, L"BatchEventsProcessed");
  if ( a5 )
    RegWriteDWORDValue(v8, L"BatchEventsDropped", a5);
  if ( a6 )
    RegWriteDWORDValue(v8, L"BatchEventsProcessed", a6);
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&v13);
}

```

## disassembly

```asm
0x18000fd88  mov     [rsp-18h+arg_18], rbx
0x18000fd8d  push    rbp
0x18000fd8e  push    rsi
0x18000fd8f  push    rdi
0x18000fd90  mov     rbp, rsp
0x18000fd93  sub     rsp, 60h
0x18000fd97  mov     rax, cs:__security_cookie
0x18000fd9e  xor     rax, rsp
0x18000fda1  mov     [rbp+var_8], rax
0x18000fda5  mov     rsi, r8
0x18000fda8  mov     r8d, 2001Fh
0x18000fdae  call    OpenSubscriptionEventSourceKey
0x18000fdb3  mov     rbx, rax
0x18000fdb6  mov     [rbp+var_30], rax
0x18000fdba  mov     [rbp+var_38], 0
0x18000fdc2  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000fdca  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000fdce  call    cs:__imp_GetSystemTimeAsFileTime
0x18000fdd4  mov     edi, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x18000fdd7  shl     rdi, 20h
0x18000fddb  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000fdde  or      rdi, rax
0x18000fde1  mov     rcx, rbx; HKEY
0x18000fde4  cmp     [rbp+arg_30], 0
0x18000fde8  jz      short loc_18000FE2C
0x18000fdea  lea     r8, [rbp+var_38]; unsigned __int64 *
0x18000fdee  lea     rdx, aLastheartbeatt; "LastHeartbeatTime"
0x18000fdf5  call    ?RegReadQWORDValue@@YA_NPEAUHKEY__@@PEBGAEA_K@Z; RegReadQWORDValue(HKEY__ *,ushort const *,unsigned __int64 &)
0x18000fdfa  mov     r8, rdi
0x18000fdfd  sub     r8, [rbp+var_38]
0x18000fe01  mov     rax, 624DD2F1A9FBE77h
0x18000fe0b  mul     r8
0x18000fe0e  sub     r8, rdx
0x18000fe11  shr     r8, 1
0x18000fe14  add     r8, rdx
0x18000fe17  shr     r8, 9; unsigned int
0x18000fe1b  lea     rdx, aBatcheventspro_0; "BatchEventsProcessingTime"
0x18000fe22  mov     rcx, rbx; HKEY
0x18000fe25  call    ?RegWriteDWORDValue@@YAXPEAUHKEY__@@PEBGK@Z; RegWriteDWORDValue(HKEY__ *,ushort const *,ulong)
0x18000fe2a  jmp     short loc_18000FE39
0x18000fe2c  lea     rdx, aBatcheventspro_0; "BatchEventsProcessingTime"
0x18000fe33  call    cs:__imp_RegDeleteValueW
0x18000fe39  mov     r8, rdi; unsigned __int64
0x18000fe3c  lea     rdx, aLastheartbeatt; "LastHeartbeatTime"
0x18000fe43  mov     rcx, rbx; HKEY
0x18000fe46  call    ?RegWriteQWORDValue@@YAXPEAUHKEY__@@PEBG_K@Z; RegWriteQWORDValue(HKEY__ *,ushort const *,unsigned __int64)
0x18000fe4b  test    rsi, rsi
0x18000fe4e  jz      short loc_18000FEBF
0x18000fe50  mov     rdx, rsi
0x18000fe53  lea     rcx, [rbp+var_28]
0x18000fe57  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000fe5c  nop
0x18000fe5d  lea     r8, [rbp+var_28]
0x18000fe61  lea     rdx, aBookmark; "Bookmark"
0x18000fe68  mov     rcx, rbx
0x18000fe6b  call    ?RegWriteStringValue@@YAXPEAUHKEY__@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegWriteStringValue(HKEY__ *,ushort const *,std::wstring const &)
0x18000fe70  nop
0x18000fe71  xor     r8d, r8d
0x18000fe74  mov     dl, 1
0x18000fe76  lea     rcx, [rbp+var_28]
0x18000fe7a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000fe7f  lea     rdx, aLasterror; "LastError"
0x18000fe86  mov     rcx, rbx; hKey
0x18000fe89  call    cs:__imp_RegDeleteValueW
0x18000fe8f  lea     rdx, aLasterrorcount; "LastErrorCount"
0x18000fe96  mov     rcx, rbx; hKey
0x18000fe99  call    cs:__imp_RegDeleteValueW
0x18000fe9f  lea     rdx, aLastfaultmessa; "LastFaultMessage"
0x18000fea6  mov     rcx, rbx; hKey
0x18000fea9  call    cs:__imp_RegDeleteValueW
0x18000feaf  lea     rdx, aLasterrortime; "LastErrorTime"
0x18000feb6  mov     rcx, rbx; hKey
0x18000feb9  call    cs:__imp_RegDeleteValueW
0x18000febf  lea     rdx, aBatcheventsdro; "BatchEventsDropped"
0x18000fec6  mov     rcx, rbx; hKey
0x18000fec9  call    cs:__imp_RegDeleteValueW
0x18000fecf  lea     rdx, aBatcheventspro; "BatchEventsProcessed"
0x18000fed6  mov     rcx, rbx; hKey
0x18000fed9  call    cs:__imp_RegDeleteValueW
0x18000fedf  mov     r8d, [rbp+arg_20]; unsigned int
0x18000fee3  test    r8d, r8d
0x18000fee6  jz      short loc_18000FEF7
0x18000fee8  lea     rdx, aBatcheventsdro; "BatchEventsDropped"
0x18000feef  mov     rcx, rbx; HKEY
0x18000fef2  call    ?RegWriteDWORDValue@@YAXPEAUHKEY__@@PEBGK@Z; RegWriteDWORDValue(HKEY__ *,ushort const *,ulong)
0x18000fef7  mov     r8d, [rbp+arg_28]; unsigned int
0x18000fefb  test    r8d, r8d
0x18000fefe  jz      short loc_18000FF10
0x18000ff00  lea     rdx, aBatcheventspro; "BatchEventsProcessed"
0x18000ff07  mov     rcx, rbx; HKEY
0x18000ff0a  call    ?RegWriteDWORDValue@@YAXPEAUHKEY__@@PEBGK@Z; RegWriteDWORDValue(HKEY__ *,ushort const *,ulong)
0x18000ff0f  nop
0x18000ff10  lea     rcx, [rbp+var_30]; this
0x18000ff14  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18000ff19  mov     rcx, [rbp+var_8]
0x18000ff1d  xor     rcx, rsp; StackCookie
0x18000ff20  call    __security_check_cookie
0x18000ff25  mov     rbx, [rsp+60h+arg_18]
0x18000ff2d  add     rsp, 60h
0x18000ff31  pop     rdi
0x18000ff32  pop     rsi
0x18000ff33  pop     rbp
0x18000ff34  retn
```
