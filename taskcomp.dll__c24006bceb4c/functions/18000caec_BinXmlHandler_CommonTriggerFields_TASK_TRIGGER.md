# BinXmlHandler::CommonTriggerFields(_TASK_TRIGGER &)

- ea: `0x18000caec`
- end: `0x18000ccf7`
- name: `?CommonTriggerFields@BinXmlHandler@@AEAAJAEAU_TASK_TRIGGER@@@Z`
- size: `523`
- prototype: `signed int __fastcall(BinXmlHandler *this, struct _TASK_TRIGGER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000cd80`

## callees

- `0x18000ca64`
- `0x18000ca8c`
- `0x18000cabc`
- `0x18000caec`
- `0x18000db5c`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cba8`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000cb9e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000cc46`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000cb9e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000cc46`

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
0x18000caec  mov     [rsp-18h+arg_10], rbx
0x18000caf1  push    rbp
0x18000caf2  push    rsi
0x18000caf3  push    rdi
0x18000caf4  mov     rbp, rsp
0x18000caf7  sub     rsp, 50h
0x18000cafb  mov     rax, cs:__security_cookie
0x18000cb02  xor     rax, rsp
0x18000cb05  mov     [rbp+var_10], rax
0x18000cb09  xorps   xmm0, xmm0
0x18000cb0c  mov     byte ptr [rbp+LocalTime.wYear], 0
0x18000cb10  movups  xmmword ptr [rdx], xmm0
0x18000cb13  lea     rsi, [rcx+128h]
0x18000cb1a  mov     rbx, rdx
0x18000cb1d  movups  xmmword ptr [rdx+10h], xmm0
0x18000cb21  mov     rdi, rcx
0x18000cb24  mov     rcx, rsi
0x18000cb27  movups  xmmword ptr [rdx+20h], xmm0
0x18000cb2b  mov     word ptr [rdx], 30h ; '0'
0x18000cb30  lea     rdx, [rbp+LocalTime]
0x18000cb34  mov     qword ptr [rbp+LocalTime.wHour], 0
0x18000cb3c  call    ??8TSTime@@QEBA_NAEBV0@@Z; TSTime::operator==(TSTime const &)
0x18000cb41  test    al, al
0x18000cb43  jz      short loc_18000CB56
0x18000cb45  lea     rcx, [rbp+LocalTime]; this
0x18000cb49  call    ??0TSTime@@QEAA@_N@Z; TSTime::TSTime(bool)
0x18000cb4e  movups  xmm0, xmmword ptr [rbp+LocalTime.wYear]
0x18000cb52  movdqu  xmmword ptr [rsi], xmm0
0x18000cb56  lea     rdx, [rbp+UniversalTime]; retstr
0x18000cb5a  mov     rcx, rsi; this
0x18000cb5d  call    ?ToSYSTEMTIME@TSTime@@QEBA?AU_SYSTEMTIME@@XZ; TSTime::ToSYSTEMTIME(void)
0x18000cb62  cmp     byte ptr [rsi], 0
0x18000cb65  jz      short loc_18000CB8D
0x18000cb67  movzx   eax, [rbp+UniversalTime.wYear]
0x18000cb6b  mov     [rbx+4], ax
0x18000cb6f  movzx   eax, [rbp+UniversalTime.wMonth]
0x18000cb73  mov     [rbx+6], ax
0x18000cb77  movzx   eax, [rbp+UniversalTime.wDay]
0x18000cb7b  mov     [rbx+8], ax
0x18000cb7f  movzx   eax, [rbp+UniversalTime.wHour]
0x18000cb83  mov     [rbx+10h], ax
0x18000cb87  movzx   eax, [rbp+UniversalTime.wMinute]
0x18000cb8b  jmp     short loc_18000CBE7
0x18000cb8d  xorps   xmm0, xmm0
0x18000cb90  lea     r8, [rbp+LocalTime]; lpLocalTime
0x18000cb94  lea     rdx, [rbp+UniversalTime]; lpUniversalTime
0x18000cb98  xor     ecx, ecx; lpTimeZoneInformation
0x18000cb9a  movups  xmmword ptr [rbp+LocalTime.wYear], xmm0
0x18000cb9e  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x18000cba4  test    eax, eax
0x18000cba6  jnz     short loc_18000CBC3
0x18000cba8  call    cs:__imp_GetLastError
0x18000cbae  test    eax, eax
0x18000cbb0  jle     loc_18000CCDB
0x18000cbb6  movzx   eax, ax
0x18000cbb9  or      eax, 80070000h
0x18000cbbe  jmp     loc_18000CCDB
0x18000cbc3  movzx   eax, [rbp+LocalTime.wYear]
0x18000cbc7  mov     [rbx+4], ax
0x18000cbcb  movzx   eax, [rbp+LocalTime.wMonth]
0x18000cbcf  mov     [rbx+6], ax
0x18000cbd3  movzx   eax, [rbp+LocalTime.wDay]
0x18000cbd7  mov     [rbx+8], ax
0x18000cbdb  movzx   eax, [rbp+LocalTime.wHour]
0x18000cbdf  mov     [rbx+10h], ax
0x18000cbe3  movzx   eax, [rbp+LocalTime.wMinute]
0x18000cbe7  lea     rsi, [rdi+138h]
0x18000cbee  mov     [rbx+12h], ax
0x18000cbf2  mov     rcx, rsi
0x18000cbf5  mov     byte ptr [rbp+LocalTime.wYear], 0
0x18000cbf9  lea     rdx, [rbp+LocalTime]
0x18000cbfd  mov     qword ptr [rbp+LocalTime.wHour], 0FFFFFFFFFFFFFFFFh
0x18000cc05  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x18000cc0a  test    al, al
0x18000cc0c  jz      short loc_18000CC70
0x18000cc0e  lea     rdx, [rbp+LocalTime]; retstr
0x18000cc12  mov     rcx, rsi; this
0x18000cc15  call    ?ToSYSTEMTIME@TSTime@@QEBA?AU_SYSTEMTIME@@XZ; TSTime::ToSYSTEMTIME(void)
0x18000cc1a  cmp     byte ptr [rsi], 0
0x18000cc1d  jz      short loc_18000CC35
0x18000cc1f  movzx   eax, [rbp+LocalTime.wYear]
0x18000cc23  mov     [rbx+0Ah], ax
0x18000cc27  movzx   eax, [rbp+LocalTime.wMonth]
0x18000cc2b  mov     [rbx+0Ch], ax
0x18000cc2f  movzx   eax, [rbp+LocalTime.wDay]
0x18000cc33  jmp     short loc_18000CC68
0x18000cc35  xorps   xmm0, xmm0
0x18000cc38  lea     r8, [rbp+UniversalTime]; lpLocalTime
0x18000cc3c  lea     rdx, [rbp+LocalTime]; lpUniversalTime
0x18000cc40  xor     ecx, ecx; lpTimeZoneInformation
0x18000cc42  movups  xmmword ptr [rbp+UniversalTime.wYear], xmm0
0x18000cc46  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x18000cc4c  test    eax, eax
0x18000cc4e  jz      loc_18000CBA8
0x18000cc54  movzx   eax, [rbp+UniversalTime.wYear]
0x18000cc58  mov     [rbx+0Ah], ax
0x18000cc5c  movzx   eax, [rbp+UniversalTime.wMonth]
0x18000cc60  mov     [rbx+0Ch], ax
0x18000cc64  movzx   eax, [rbp+UniversalTime.wDay]
0x18000cc68  or      dword ptr [rbx+1Ch], 1
0x18000cc6c  mov     [rbx+0Eh], ax
0x18000cc70  mov     ecx, [rdi+100h]
0x18000cc76  test    ecx, ecx
0x18000cc78  jz      short loc_18000CCCC
0x18000cc7a  mov     r8d, 88888889h
0x18000cc80  mov     eax, r8d
0x18000cc83  mul     ecx
0x18000cc85  shr     edx, 5
0x18000cc88  mov     [rbx+18h], edx
0x18000cc8b  test    edx, edx
0x18000cc8d  jnz     short loc_18000CC96
0x18000cc8f  mov     dword ptr [rbx+18h], 1
0x18000cc96  mov     ecx, [rdi+104h]
0x18000cc9c  test    ecx, ecx
0x18000cc9e  jz      short loc_18000CCB8
0x18000cca0  mov     eax, r8d
0x18000cca3  mul     ecx
0x18000cca5  shr     edx, 5
0x18000cca8  mov     [rbx+14h], edx
0x18000ccab  test    edx, edx
0x18000ccad  jnz     short loc_18000CCBF
0x18000ccaf  mov     dword ptr [rbx+14h], 1
0x18000ccb6  jmp     short loc_18000CCBF
0x18000ccb8  mov     dword ptr [rbx+14h], 0FFFFFFFFh
0x18000ccbf  cmp     byte ptr [rdi+118h], 0
0x18000ccc6  jz      short loc_18000CCCC
0x18000ccc8  or      dword ptr [rbx+1Ch], 2
0x18000cccc  cmp     byte ptr [rdi+80h], 0
0x18000ccd3  jnz     short loc_18000CCD9
0x18000ccd5  or      dword ptr [rbx+1Ch], 4
0x18000ccd9  xor     eax, eax
0x18000ccdb  mov     rcx, [rbp+var_10]
0x18000ccdf  xor     rcx, rsp; StackCookie
0x18000cce2  call    __security_check_cookie
0x18000cce7  mov     rbx, [rsp+50h+arg_10]
0x18000ccef  add     rsp, 50h
0x18000ccf3  pop     rdi
0x18000ccf4  pop     rsi
0x18000ccf5  pop     rbp
0x18000ccf6  retn
```
