# BinXmlHandler::CommonTriggerFields(_TASK_TRIGGER &)

- ea: `0x18000d338`
- end: `0x18000d556`
- name: `?CommonTriggerFields@BinXmlHandler@@AEAAJAEAU_TASK_TRIGGER@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(BinXmlHandler *__hidden this, struct _TASK_TRIGGER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d600`

## callees

- `0x18000d2ac`
- `0x18000d2d8`
- `0x18000d308`
- `0x18000d338`
- `0x18000e434`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3fa`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000d3ea`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000d49e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000d3ea`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000d49e`

## pseudocode

```c
signed int __fastcall BinXmlHandler::CommonTriggerFields(BinXmlHandler *this, struct _TASK_TRIGGER *a2)
{
  TSTime *v2; // rsi
  bool v5; // dl
  WORD wMinute; // ax
  signed int result; // eax
  WORD wDay; // ax
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  struct _SYSTEMTIME LocalTime; // [rsp+20h] [rbp-30h] BYREF
  SYSTEMTIME UniversalTime; // [rsp+30h] [rbp-20h] BYREF

  LOBYTE(LocalTime.wYear) = 0;
  *(_OWORD *)&a2->cbTriggerSize = 0;
  v2 = (BinXmlHandler *)((char *)this + 296);
  *(_OWORD *)&a2->wStartHour = 0;
  *(_OWORD *)&a2->TriggerType = 0;
  a2->cbTriggerSize = 48;
  *(_QWORD *)&LocalTime.wHour = 0;
  if ( (unsigned __int8)TSTime::operator==((char *)this + 296, &LocalTime) )
  {
    TSTime::TSTime((TSTime *)&LocalTime, v5);
    *(struct _SYSTEMTIME *)v2 = LocalTime;
  }
  TSTime::ToSYSTEMTIME(v2, &UniversalTime);
  if ( *(_BYTE *)v2 )
  {
    a2->wBeginYear = UniversalTime.wYear;
    a2->wBeginMonth = UniversalTime.wMonth;
    a2->wBeginDay = UniversalTime.wDay;
    a2->wStartHour = UniversalTime.wHour;
    wMinute = UniversalTime.wMinute;
  }
  else
  {
    LocalTime = 0;
    if ( !SystemTimeToTzSpecificLocalTime(0, &UniversalTime, &LocalTime) )
      goto LABEL_6;
    a2->wBeginYear = LocalTime.wYear;
    a2->wBeginMonth = LocalTime.wMonth;
    a2->wBeginDay = LocalTime.wDay;
    a2->wStartHour = LocalTime.wHour;
    wMinute = LocalTime.wMinute;
  }
  a2->wStartMinute = wMinute;
  LOBYTE(LocalTime.wYear) = 0;
  *(_QWORD *)&LocalTime.wHour = -1;
  if ( !(unsigned __int8)TSTime::operator!=((char *)this + 312, &LocalTime) )
  {
LABEL_15:
    v9 = *((_DWORD *)this + 64);
    if ( v9 )
    {
      a2->MinutesInterval = v9 / 0x3C;
      if ( !(v9 / 0x3C) )
        a2->MinutesInterval = 1;
      v10 = *((_DWORD *)this + 65);
      if ( v10 )
      {
        a2->MinutesDuration = v10 / 0x3C;
        if ( !(v10 / 0x3C) )
          a2->MinutesDuration = 1;
      }
      else
      {
        a2->MinutesDuration = -1;
      }
      if ( *((_BYTE *)this + 280) )
        a2->rgFlags |= 2u;
    }
    if ( !*((_BYTE *)this + 128) )
      a2->rgFlags |= 4u;
    return 0;
  }
  TSTime::ToSYSTEMTIME((BinXmlHandler *)((char *)this + 312), &LocalTime);
  if ( *((_BYTE *)this + 312) )
  {
    a2->wEndYear = LocalTime.wYear;
    a2->wEndMonth = LocalTime.wMonth;
    wDay = LocalTime.wDay;
LABEL_14:
    a2->rgFlags |= 1u;
    a2->wEndDay = wDay;
    goto LABEL_15;
  }
  UniversalTime = 0;
  if ( SystemTimeToTzSpecificLocalTime(0, &LocalTime, &UniversalTime) )
  {
    a2->wEndYear = UniversalTime.wYear;
    a2->wEndMonth = UniversalTime.wMonth;
    wDay = UniversalTime.wDay;
    goto LABEL_14;
  }
LABEL_6:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000d338  mov     [rsp-18h+arg_10], rbx
0x18000d33d  push    rbp
0x18000d33e  push    rsi
0x18000d33f  push    rdi
0x18000d340  mov     rbp, rsp
0x18000d343  sub     rsp, 50h
0x18000d347  mov     rax, cs:__security_cookie
0x18000d34e  xor     rax, rsp
0x18000d351  mov     [rbp+var_10], rax
0x18000d355  xorps   xmm0, xmm0
0x18000d358  mov     byte ptr [rbp+LocalTime.wYear], 0
0x18000d35c  movups  xmmword ptr [rdx], xmm0
0x18000d35f  lea     rsi, [rcx+128h]
0x18000d366  mov     rbx, rdx
0x18000d369  movups  xmmword ptr [rdx+10h], xmm0
0x18000d36d  mov     rdi, rcx
0x18000d370  mov     rcx, rsi
0x18000d373  movups  xmmword ptr [rdx+20h], xmm0
0x18000d377  mov     word ptr [rdx], 30h ; '0'
0x18000d37c  lea     rdx, [rbp+LocalTime]
0x18000d380  mov     qword ptr [rbp+LocalTime.wHour], 0
0x18000d388  call    ??8TSTime@@QEBA_NAEBV0@@Z; TSTime::operator==(TSTime const &)
0x18000d38d  test    al, al
0x18000d38f  jz      short loc_18000D3A2
0x18000d391  lea     rcx, [rbp+LocalTime]; this
0x18000d395  call    ??0TSTime@@QEAA@_N@Z; TSTime::TSTime(bool)
0x18000d39a  movups  xmm0, xmmword ptr [rbp+LocalTime.wYear]
0x18000d39e  movdqu  xmmword ptr [rsi], xmm0
0x18000d3a2  lea     rdx, [rbp+UniversalTime]; retstr
0x18000d3a6  mov     rcx, rsi; this
0x18000d3a9  call    ?ToSYSTEMTIME@TSTime@@QEBA?AU_SYSTEMTIME@@XZ; TSTime::ToSYSTEMTIME(void)
0x18000d3ae  cmp     byte ptr [rsi], 0
0x18000d3b1  jz      short loc_18000D3D9
0x18000d3b3  movzx   eax, [rbp+UniversalTime.wYear]
0x18000d3b7  mov     [rbx+4], ax
0x18000d3bb  movzx   eax, [rbp+UniversalTime.wMonth]
0x18000d3bf  mov     [rbx+6], ax
0x18000d3c3  movzx   eax, [rbp+UniversalTime.wDay]
0x18000d3c7  mov     [rbx+8], ax
0x18000d3cb  movzx   eax, [rbp+UniversalTime.wHour]
0x18000d3cf  mov     [rbx+10h], ax
0x18000d3d3  movzx   eax, [rbp+UniversalTime.wMinute]
0x18000d3d7  jmp     short loc_18000D43F
0x18000d3d9  xorps   xmm0, xmm0
0x18000d3dc  lea     r8, [rbp+LocalTime]; lpLocalTime
0x18000d3e0  lea     rdx, [rbp+UniversalTime]; lpUniversalTime
0x18000d3e4  xor     ecx, ecx; lpTimeZoneInformation
0x18000d3e6  movups  xmmword ptr [rbp+LocalTime.wYear], xmm0
0x18000d3ea  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x18000d3f1  nop     dword ptr [rax+rax+00h]
0x18000d3f6  test    eax, eax
0x18000d3f8  jnz     short loc_18000D41B
0x18000d3fa  call    cs:__imp_GetLastError
0x18000d401  nop     dword ptr [rax+rax+00h]
0x18000d406  test    eax, eax
0x18000d408  jle     loc_18000D539
0x18000d40e  movzx   eax, ax
0x18000d411  or      eax, 80070000h
0x18000d416  jmp     loc_18000D539
0x18000d41b  movzx   eax, [rbp+LocalTime.wYear]
0x18000d41f  mov     [rbx+4], ax
0x18000d423  movzx   eax, [rbp+LocalTime.wMonth]
0x18000d427  mov     [rbx+6], ax
0x18000d42b  movzx   eax, [rbp+LocalTime.wDay]
0x18000d42f  mov     [rbx+8], ax
0x18000d433  movzx   eax, [rbp+LocalTime.wHour]
0x18000d437  mov     [rbx+10h], ax
0x18000d43b  movzx   eax, [rbp+LocalTime.wMinute]
0x18000d43f  lea     rsi, [rdi+138h]
0x18000d446  mov     [rbx+12h], ax
0x18000d44a  mov     rcx, rsi
0x18000d44d  mov     byte ptr [rbp+LocalTime.wYear], 0
0x18000d451  lea     rdx, [rbp+LocalTime]
0x18000d455  mov     qword ptr [rbp+LocalTime.wHour], 0FFFFFFFFFFFFFFFFh
0x18000d45d  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x18000d462  test    al, al
0x18000d464  jz      short loc_18000D4CE
0x18000d466  lea     rdx, [rbp+LocalTime]; retstr
0x18000d46a  mov     rcx, rsi; this
0x18000d46d  call    ?ToSYSTEMTIME@TSTime@@QEBA?AU_SYSTEMTIME@@XZ; TSTime::ToSYSTEMTIME(void)
0x18000d472  cmp     byte ptr [rsi], 0
0x18000d475  jz      short loc_18000D48D
0x18000d477  movzx   eax, [rbp+LocalTime.wYear]
0x18000d47b  mov     [rbx+0Ah], ax
0x18000d47f  movzx   eax, [rbp+LocalTime.wMonth]
0x18000d483  mov     [rbx+0Ch], ax
0x18000d487  movzx   eax, [rbp+LocalTime.wDay]
0x18000d48b  jmp     short loc_18000D4C6
0x18000d48d  xorps   xmm0, xmm0
0x18000d490  lea     r8, [rbp+UniversalTime]; lpLocalTime
0x18000d494  lea     rdx, [rbp+LocalTime]; lpUniversalTime
0x18000d498  xor     ecx, ecx; lpTimeZoneInformation
0x18000d49a  movups  xmmword ptr [rbp+UniversalTime.wYear], xmm0
0x18000d49e  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x18000d4a5  nop     dword ptr [rax+rax+00h]
0x18000d4aa  test    eax, eax
0x18000d4ac  jz      loc_18000D3FA
0x18000d4b2  movzx   eax, [rbp+UniversalTime.wYear]
0x18000d4b6  mov     [rbx+0Ah], ax
0x18000d4ba  movzx   eax, [rbp+UniversalTime.wMonth]
0x18000d4be  mov     [rbx+0Ch], ax
0x18000d4c2  movzx   eax, [rbp+UniversalTime.wDay]
0x18000d4c6  or      dword ptr [rbx+1Ch], 1
0x18000d4ca  mov     [rbx+0Eh], ax
0x18000d4ce  mov     ecx, [rdi+100h]
0x18000d4d4  test    ecx, ecx
0x18000d4d6  jz      short loc_18000D52A
0x18000d4d8  mov     r8d, 88888889h
0x18000d4de  mov     eax, r8d
0x18000d4e1  mul     ecx
0x18000d4e3  shr     edx, 5
0x18000d4e6  mov     [rbx+18h], edx
0x18000d4e9  test    edx, edx
0x18000d4eb  jnz     short loc_18000D4F4
0x18000d4ed  mov     dword ptr [rbx+18h], 1
0x18000d4f4  mov     ecx, [rdi+104h]
0x18000d4fa  test    ecx, ecx
0x18000d4fc  jz      short loc_18000D516
0x18000d4fe  mov     eax, r8d
0x18000d501  mul     ecx
0x18000d503  shr     edx, 5
0x18000d506  mov     [rbx+14h], edx
0x18000d509  test    edx, edx
0x18000d50b  jnz     short loc_18000D51D
0x18000d50d  mov     dword ptr [rbx+14h], 1
0x18000d514  jmp     short loc_18000D51D
0x18000d516  mov     dword ptr [rbx+14h], 0FFFFFFFFh
0x18000d51d  cmp     byte ptr [rdi+118h], 0
0x18000d524  jz      short loc_18000D52A
0x18000d526  or      dword ptr [rbx+1Ch], 2
0x18000d52a  cmp     byte ptr [rdi+80h], 0
0x18000d531  jnz     short loc_18000D537
0x18000d533  or      dword ptr [rbx+1Ch], 4
0x18000d537  xor     eax, eax
0x18000d539  mov     rcx, [rbp+var_10]
0x18000d53d  xor     rcx, rsp; StackCookie
0x18000d540  call    __security_check_cookie
0x18000d545  mov     rbx, [rsp+50h+arg_10]
0x18000d54d  add     rsp, 50h
0x18000d551  pop     rdi
0x18000d552  pop     rsi
0x18000d553  pop     rbp
0x18000d554  retn
```
