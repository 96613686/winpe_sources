# GetEffectiveOffset(_TIME_DYNAMIC_ZONE_INFORMATION const &,int *)

- ea: `0x180013c4c`
- end: `0x180013d6d`
- name: `?GetEffectiveOffset@@YAJAEBU_TIME_DYNAMIC_ZONE_INFORMATION@@PEAH@Z`
- size: `289`
- prototype: `__int64 __fastcall(const struct _TIME_DYNAMIC_ZONE_INFORMATION *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013aa0`

## callees

- `0x18000883c`
- `0x18000885c`
- `0x180013c4c`
- `0x180013d74`
- `0x18001b150`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTimeEx` at `0x180013c98`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTimeEx` at `0x180013c98`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180013c80`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180013c80`

## string_xrefs

- `0x180013ca6`: `onecore\base\win32\winnls\tzautoupdate\nitzfinder.cpp`
- `0x180013ce7`: `onecore\base\win32\winnls\tzautoupdate\nitzfinder.cpp`

## pseudocode

```c
__int64 __fastcall GetEffectiveOffset(const struct _TIME_DYNAMIC_ZONE_INFORMATION *a1, int *a2)
{
  const char *v4; // r9
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // [rsp+20h] [rbp-60h] BYREF
  struct _SYSTEMTIME v9; // [rsp+30h] [rbp-50h] BYREF
  struct _SYSTEMTIME v10; // [rsp+40h] [rbp-40h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-30h] BYREF
  struct _SYSTEMTIME v12; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  SystemTime = 0;
  GetSystemTime(&SystemTime);
  v12 = 0;
  if ( !(unsigned int)SystemTimeToTzSpecificLocalTimeEx(a1, &SystemTime, &v12) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xF,
             (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\nitzfinder.cpp",
             v4);
  v9 = SystemTime;
  v8 = 0;
  v6 = RoSystemTimeToDateTime(&v9, (struct Windows::Foundation::DateTime *)&v8);
  if ( v6 < 0 )
  {
    v7 = 18;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\nitzfinder.cpp",
      (const char *)(unsigned int)v6,
      v8);
    return (unsigned int)v6;
  }
  v10 = v12;
  *(_QWORD *)&v9.wYear = 0;
  v6 = RoSystemTimeToDateTime(&v10, (struct Windows::Foundation::DateTime *)&v9);
  if ( v6 < 0 )
  {
    v7 = 21;
    goto LABEL_5;
  }
  *a2 = (*(_QWORD *)&v9.wYear - v8) / 600000000;
  return 0;
}

```

## disassembly

```asm
0x180013c4c  mov     [rsp-8+arg_10], rbx
0x180013c51  mov     [rsp-8+arg_18], rdi
0x180013c56  push    rbp
0x180013c57  mov     rbp, rsp
0x180013c5a  sub     rsp, 80h
0x180013c61  mov     rax, cs:__security_cookie
0x180013c68  xor     rax, rsp
0x180013c6b  mov     [rbp+var_10], rax
0x180013c6f  mov     rbx, rcx
0x180013c72  xorps   xmm0, xmm0
0x180013c75  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180013c79  mov     rdi, rdx
0x180013c7c  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180013c80  call    cs:__imp_GetSystemTime
0x180013c86  xorps   xmm0, xmm0
0x180013c89  lea     r8, [rbp+var_20]
0x180013c8d  lea     rdx, [rbp+SystemTime]
0x180013c91  mov     rcx, rbx
0x180013c94  movups  [rbp+var_20], xmm0
0x180013c98  call    cs:__imp_SystemTimeToTzSpecificLocalTimeEx
0x180013c9e  test    eax, eax
0x180013ca0  jnz     short loc_180013CBA
0x180013ca2  mov     rcx, [rbp+8]; this
0x180013ca6  lea     r8, aOnecoreBaseWin; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x180013cad  lea     edx, [rax+0Fh]; void *
0x180013cb0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013cb5  jmp     loc_180013D4C
0x180013cba  movaps  xmm0, xmmword ptr [rbp+SystemTime.wYear]
0x180013cbe  lea     rdx, [rbp+var_60]; struct Windows::Foundation::DateTime *
0x180013cc2  lea     rcx, [rbp+var_50]; struct _SYSTEMTIME
0x180013cc6  movdqa  xmmword ptr [rbp+var_50.wYear], xmm0
0x180013ccb  mov     [rbp+var_60], 0
0x180013cd3  call    ?RoSystemTimeToDateTime@@YAJU_SYSTEMTIME@@PEAUDateTime@Foundation@Windows@@@Z; RoSystemTimeToDateTime(_SYSTEMTIME,Windows::Foundation::DateTime *)
0x180013cd8  mov     ebx, eax
0x180013cda  test    eax, eax
0x180013cdc  jns     short loc_180013CFA
0x180013cde  mov     edx, 12h; void *
0x180013ce3  mov     rcx, [rbp+8]; this
0x180013ce7  lea     r8, aOnecoreBaseWin; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x180013cee  mov     r9d, ebx; char *
0x180013cf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013cf6  mov     eax, ebx
0x180013cf8  jmp     short loc_180013D4C
0x180013cfa  movaps  xmm0, [rbp+var_20]
0x180013cfe  lea     rdx, [rbp+var_50]; struct Windows::Foundation::DateTime *
0x180013d02  lea     rcx, [rbp+var_40]; struct _SYSTEMTIME
0x180013d06  movdqa  xmmword ptr [rbp+var_40.wYear], xmm0
0x180013d0b  mov     qword ptr [rbp+var_50.wYear], 0
0x180013d13  call    ?RoSystemTimeToDateTime@@YAJU_SYSTEMTIME@@PEAUDateTime@Foundation@Windows@@@Z; RoSystemTimeToDateTime(_SYSTEMTIME,Windows::Foundation::DateTime *)
0x180013d18  mov     ebx, eax
0x180013d1a  test    eax, eax
0x180013d1c  jns     short loc_180013D25
0x180013d1e  mov     edx, 15h
0x180013d23  jmp     short loc_180013CE3
0x180013d25  mov     rcx, qword ptr [rbp+var_50.wYear]
0x180013d29  mov     rax, 1CA213D840BAF7D5h
0x180013d33  sub     rcx, [rbp+var_60]
0x180013d37  imul    rcx
0x180013d3a  sar     rdx, 1Ah
0x180013d3e  mov     rax, rdx
0x180013d41  shr     rax, 3Fh
0x180013d45  add     rdx, rax
0x180013d48  mov     [rdi], edx
0x180013d4a  xor     eax, eax
0x180013d4c  mov     rcx, [rbp+var_10]
0x180013d50  xor     rcx, rsp; StackCookie
0x180013d53  call    __security_check_cookie
0x180013d58  lea     r11, [rsp+80h+var_s0]
0x180013d60  mov     rbx, [r11+20h]
0x180013d64  mov     rdi, [r11+28h]
0x180013d68  mov     rsp, r11
0x180013d6b  pop     rbp
0x180013d6c  retn
```
