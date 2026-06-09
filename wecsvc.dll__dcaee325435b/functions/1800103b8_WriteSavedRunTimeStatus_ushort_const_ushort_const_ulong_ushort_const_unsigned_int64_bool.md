# WriteSavedRunTimeStatus(ushort const *,ushort const *,ulong,ushort const *,unsigned __int64,bool)

- ea: `0x1800103b8`
- end: `0x180010506`
- name: `?WriteSavedRunTimeStatus@@YAXPEBG0K0_K_N@Z`
- size: `334`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned __int64, char)`
- caller_count: `10`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180008828`
- `0x180009170`
- `0x180009a10`
- `0x18000cef8`
- `0x18000cfa0`
- `0x18000dda4`
- `0x18000e2f8`
- `0x180021149`
- `0x18002120d`
- `0x1800213a1`

## callees

- `0x180003e6c`
- `0x1800062d4`
- `0x18000669c`
- `0x18000ef44`
- `0x1800103b8`
- `0x1800129f0`
- `0x180012ac0`
- `0x180012b94`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800104a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800104b6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800104c6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800104a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800104b6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800104c6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010403`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010403`

## pseudocode

```c
void __fastcall WriteSavedRunTimeStatus(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned __int64 a5,
        char a6)
{
  unsigned __int64 v10; // rdi
  HKEY v11; // rbx
  __int64 v12; // rdx
  char v13; // al
  int v14; // r8d
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-78h] BYREF
  const unsigned __int16 *v16; // [rsp+38h] [rbp-70h]
  const unsigned __int16 *v17; // [rsp+40h] [rbp-68h]
  wmi::Exception *v18; // [rsp+48h] [rbp-60h] BYREF
  _WORD v19[8]; // [rsp+50h] [rbp-58h] BYREF
  __int64 v20; // [rsp+60h] [rbp-48h]
  __int64 v21; // [rsp+68h] [rbp-40h]

  v17 = a1;
  v16 = a2;
  v10 = a5;
  if ( !a5 )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v10 = (unsigned __int64)SystemTimeAsFileTime;
  }
  try
  {
    v11 = OpenSubscriptionEventSourceKey((__int64)a1, (__int64)a2, 0x20006u, a6);
    SystemTimeAsFileTime = (struct _FILETIME)v11;
    RegWriteDWORDValue(v11, L"LastError", a3);
    v21 = 7;
    v20 = 0;
    v19[0] = 0;
    if ( a4 )
      std::wstring::assign(v19, a4);
    RegWriteStringValue(v11, L"LastFaultMessage", v19);
    RegWriteQWORDValue(v11, L"LastErrorTime", v10);
    RegDeleteValueW(v11, L"LastHeartbeatTime");
    RegDeleteValueW(v11, L"BatchEventsDropped");
    RegDeleteValueW(v11, L"BatchEventsProcessed");
    LOBYTE(v12) = 1;
    std::wstring::_Tidy(v19, v12, 0);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&SystemTimeAsFileTime);
  }
  catch ( wmi::Exception *v18 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = (**(__int64 (__fastcall ***)(wmi::Exception *))v18)(v18);
      WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v14, (_DWORD)v17, (__int64)v16, v13);
    }
  }
}

```

## disassembly

```asm
0x1800103b8  push    rbx
0x1800103ba  push    rsi
0x1800103bb  push    rdi
0x1800103bc  push    r14
0x1800103be  push    r15
0x1800103c0  sub     rsp, 80h
0x1800103c7  mov     rax, cs:__security_cookie
0x1800103ce  xor     rax, rsp
0x1800103d1  mov     [rsp+0A8h+var_38], rax
0x1800103d6  mov     rsi, r9
0x1800103d9  mov     r15d, r8d
0x1800103dc  mov     r14, rdx
0x1800103df  mov     rbx, rcx
0x1800103e2  mov     [rsp+0A8h+var_68], rcx
0x1800103e7  mov     [rsp+0A8h+var_70], rdx
0x1800103ec  mov     rdi, [rsp+0A8h+arg_20]
0x1800103f4  test    rdi, rdi
0x1800103f7  jnz     short loc_180010418
0x1800103f9  mov     qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x1800103fe  lea     rcx, [rsp+0A8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010403  call    cs:__imp_GetSystemTimeAsFileTime
0x180010409  mov     edi, [rsp+0A8h+SystemTimeAsFileTime.dwHighDateTime]
0x18001040d  shl     rdi, 20h
0x180010411  mov     eax, [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime]
0x180010415  or      rdi, rax
0x180010418  mov     r9b, [rsp+0A8h+arg_28]
0x180010420  mov     r8d, 20006h
0x180010426  mov     rdx, r14
0x180010429  mov     rcx, rbx
0x18001042c  call    OpenSubscriptionEventSourceKey
0x180010431  mov     rbx, rax
0x180010434  mov     qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180010439  mov     r8d, r15d; unsigned int
0x18001043c  lea     rdx, aLasterror; "LastError"
0x180010443  mov     rcx, rax; HKEY
0x180010446  call    ?RegWriteDWORDValue@@YAXPEAUHKEY__@@PEBGK@Z; RegWriteDWORDValue(HKEY__ *,ushort const *,ulong)
0x18001044b  mov     [rsp+0A8h+var_40], 7
0x180010454  mov     [rsp+0A8h+var_48], 0
0x18001045d  xor     eax, eax
0x18001045f  mov     [rsp+0A8h+var_58], ax
0x180010464  test    rsi, rsi
0x180010467  jz      short loc_180010476
0x180010469  mov     rdx, rsi
0x18001046c  lea     rcx, [rsp+0A8h+var_58]
0x180010471  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180010476  lea     r8, [rsp+0A8h+var_58]
0x18001047b  lea     rdx, aLastfaultmessa; "LastFaultMessage"
0x180010482  mov     rcx, rbx
0x180010485  call    ?RegWriteStringValue@@YAXPEAUHKEY__@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegWriteStringValue(HKEY__ *,ushort const *,std::wstring const &)
0x18001048a  mov     r8, rdi; unsigned __int64
0x18001048d  lea     rdx, aLasterrortime; "LastErrorTime"
0x180010494  mov     rcx, rbx; HKEY
0x180010497  call    ?RegWriteQWORDValue@@YAXPEAUHKEY__@@PEBG_K@Z; RegWriteQWORDValue(HKEY__ *,ushort const *,unsigned __int64)
0x18001049c  lea     rdx, aLastheartbeatt; "LastHeartbeatTime"
0x1800104a3  mov     rcx, rbx; hKey
0x1800104a6  call    cs:__imp_RegDeleteValueW
0x1800104ac  lea     rdx, aBatcheventsdro; "BatchEventsDropped"
0x1800104b3  mov     rcx, rbx; hKey
0x1800104b6  call    cs:__imp_RegDeleteValueW
0x1800104bc  lea     rdx, aBatcheventspro; "BatchEventsProcessed"
0x1800104c3  mov     rcx, rbx; hKey
0x1800104c6  call    cs:__imp_RegDeleteValueW
0x1800104cc  nop
0x1800104cd  xor     r8d, r8d
0x1800104d0  mov     dl, 1
0x1800104d2  lea     rcx, [rsp+0A8h+var_58]
0x1800104d7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800104dc  nop
0x1800104dd  lea     rcx, [rsp+0A8h+SystemTimeAsFileTime]; this
0x1800104e2  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800104e7  nop
0x1800104e8  jmp     short $+2
0x1800104ea  mov     rcx, [rsp+0A8h+var_38]
0x1800104ef  xor     rcx, rsp; StackCookie
0x1800104f2  call    __security_check_cookie
0x1800104f7  add     rsp, 80h
0x1800104fe  pop     r15
0x180010500  pop     r14
0x180010502  pop     rdi
0x180010503  pop     rsi
0x180010504  pop     rbx
0x180010505  retn
```
