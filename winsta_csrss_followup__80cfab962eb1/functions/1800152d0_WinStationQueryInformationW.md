# WinStationQueryInformationW

- ea: `0x1800152d0`
- end: `0x1800154c6`
- name: `WinStationQueryInformationW`
- size: `502`
- prototype: `__int64 __usercall@<rax>(CPublicBinding *this@<rcx>, unsigned int@<edx>, int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180002600`

## callees

- `0x180004558`
- `0x180005b40`
- `0x180006740`
- `0x1800096c0`
- `0x1800152d0`
- `0x180023690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001530a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015473`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001530a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015473`

## string_xrefs

- `0x180015372`: `WinStationUserToken failed: 0x%x in %s`
- `0x1800153a6`: `GetUserTokenForSession failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall WinStationQueryInformationW(
        CPublicBinding *this,
        ULONG a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        unsigned int *a6)
{
  ULONG SessionId; // r10d
  __int64 result; // rax
  DWORD v8; // ecx
  int UserTokenForSession; // ebx

  SessionId = a2;
  if ( a2 == -1 )
  {
    if ( this && *(_WORD *)this && !*((_DWORD *)this + 12) )
    {
      _DbgPrintMessage(4, "LOGONID_CURRENT specified for a remote server!");
      SetLastError(0x57u);
      return 0;
    }
    SessionId = NtCurrentPeb()->SessionId;
  }
  switch ( a3 )
  {
    case 1u:
    case 2u:
    case 3u:
    case 4u:
    case 6u:
    case 7u:
    case 8u:
    case 0x14u:
    case 0x19u:
    case 0x1Cu:
    case 0x1Du:
    case 0x27u:
    case 0x28u:
    case 0x29u:
    case 0x2Au:
      result = Public_WinStationQueryInformationW(this, SessionId, a3, (struct _WINSTATIONINFORMATIONW *)a4, a5, a6);
      break;
    case 0xEu:
      if ( a5 < 0x18 )
      {
        _DbgPrintMessage(8, "WinStationUserToken failed: 0x%x in %s", -2147024809, "WinStationQueryInformationW");
        v8 = ConvertHRESULT2WIN32(-2147024809);
        goto LABEL_20;
      }
      UserTokenForSession = GetUserTokenForSession(SessionId, (void **)(a4 + 16));
      if ( UserTokenForSession < 0 )
      {
        _DbgPrintMessage(
          8,
          "GetUserTokenForSession failed: 0x%x in %s",
          (unsigned int)UserTokenForSession,
          "WinStationQueryInformationW");
        goto LABEL_12;
      }
      *a6 = 24;
      result = 1;
      break;
    case 0x25u:
      if ( a5 < 4 )
      {
        _DbgPrintMessage(
          8,
          "WinStationReconnectedFromId failed: 0x%x in %s",
          -2147024809,
          "WinStationQueryInformationW");
        v8 = ConvertHRESULT2WIN32(-2147024809);
        goto LABEL_20;
      }
      UserTokenForSession = GetReconnectedFromId(SessionId, (unsigned int *)a4);
      if ( UserTokenForSession < 0 )
      {
        _DbgPrintMessage(
          8,
          "GetReconnectedFromId failed: 0x%x in %s",
          (unsigned int)UserTokenForSession,
          "WinStationQueryInformationW");
LABEL_12:
        v8 = ConvertHRESULT2WIN32(UserTokenForSession);
        goto LABEL_20;
      }
      *a6 = 4;
      result = 1;
      break;
    default:
      _DbgPrintMessage(4, "!!! Obsolete_WinStationQueryInformationW deprecated");
      v8 = 1;
LABEL_20:
      SetLastError(v8);
      result = 0;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x1800152d0  push    rbx
0x1800152d2  sub     rsp, 30h
0x1800152d6  mov     r10d, edx
0x1800152d9  mov     r11, rcx
0x1800152dc  cmp     edx, 0FFFFFFFFh
0x1800152df  jnz     short loc_180015330
0x1800152e1  test    rcx, rcx
0x1800152e4  jz      short loc_180015320
0x1800152e6  xor     eax, eax
0x1800152e8  cmp     ax, [rcx]
0x1800152eb  jz      short loc_180015320
0x1800152ed  cmp     [rcx+30h], eax
0x1800152f0  jnz     short loc_180015320
0x1800152f2  lea     rdx, aLogonidCurrent; "LOGONID_CURRENT specified for a remote "...
0x1800152f9  mov     ecx, 4; int
0x1800152fe  xor     bl, bl
0x180015300  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015305  mov     ecx, 57h ; 'W'; dwErrCode
0x18001530a  call    cs:__imp_SetLastError
0x180015311  nop     dword ptr [rax+rax+00h]
0x180015316  movzx   eax, bl
0x180015319  add     rsp, 30h
0x18001531d  pop     rbx
0x18001531e  retn
0x180015320  mov     rax, gs:60h
0x180015329  mov     r10d, [rax+2C0h]
0x180015330  lea     eax, [r8-1]; switch 42 cases
0x180015334  cmp     eax, 29h
0x180015337  ja      def_180015358; jumptable 0000000180015358 default case, cases 5,9-13,15-19,21-24,26,27,30-36,38
0x18001533d  lea     rdx, __ImageBase
0x180015344  cdqe
0x180015346  movzx   eax, ds:(byte_18001549C - 180000000h)[rdx+rax]
0x18001534e  mov     ecx, ds:(jpt_180015358 - 180000000h)[rdx+rax*4]
0x180015355  add     rcx, rdx
0x180015358  jmp     rcx; switch jump
0x18001535e  cmp     [rsp+38h+arg_20], 18h; jumptable 0000000180015358 case 14
0x180015363  jnb     short loc_180015394
0x180015365  lea     r9, aWinstationquer_11; "WinStationQueryInformationW"
0x18001536c  mov     r8d, 80070057h
0x180015372  lea     rdx, aWinstationuser_0; "WinStationUserToken failed: 0x%x in %s"
0x180015379  mov     ecx, 8; int
0x18001537e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015383  mov     ecx, 80070057h; int
0x180015388  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18001538d  mov     ecx, eax
0x18001538f  jmp     loc_180015473
0x180015394  lea     rdx, [r9+10h]; void **
0x180015398  mov     ecx, r10d; unsigned int
0x18001539b  call    ?GetUserTokenForSession@@YAJKPEAPEAX@Z; GetUserTokenForSession(ulong,void * *)
0x1800153a0  mov     ebx, eax
0x1800153a2  test    eax, eax
0x1800153a4  jns     short loc_1800153CF
0x1800153a6  lea     rdx, aGetusertokenfo; "GetUserTokenForSession failed: 0x%x in "...
0x1800153ad  mov     r8d, ebx
0x1800153b0  lea     r9, aWinstationquer_11; "WinStationQueryInformationW"
0x1800153b7  mov     ecx, 8; int
0x1800153bc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800153c1  mov     ecx, ebx; int
0x1800153c3  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800153c8  mov     ecx, eax
0x1800153ca  jmp     loc_180015473
0x1800153cf  mov     rax, [rsp+38h+arg_28]
0x1800153d4  mov     bl, 1
0x1800153d6  mov     dword ptr [rax], 18h
0x1800153dc  movzx   eax, bl
0x1800153df  add     rsp, 30h
0x1800153e3  pop     rbx
0x1800153e4  retn
0x1800153e6  mov     edx, r10d; jumptable 0000000180015358 cases 1-4,6-8,20,25,28,29,39-42
0x1800153e9  mov     rcx, r11; this
0x1800153ec  add     rsp, 30h
0x1800153f0  pop     rbx
0x1800153f1  jmp     ?Public_WinStationQueryInformationW@@YAEPEAXKW4_WINSTATIONINFOCLASS@@0KPEAK@Z; Public_WinStationQueryInformationW(void *,ulong,_WINSTATIONINFOCLASS,void *,ulong,ulong *)
0x1800153f6  cmp     [rsp+38h+arg_20], 4; jumptable 0000000180015358 case 37
0x1800153fb  jnb     short loc_180015429
0x1800153fd  lea     r9, aWinstationquer_11; "WinStationQueryInformationW"
0x180015404  mov     r8d, 80070057h
0x18001540a  lea     rdx, aWinstationreco; "WinStationReconnectedFromId failed: 0x%"...
0x180015411  mov     ecx, 8; int
0x180015416  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001541b  mov     ecx, 80070057h; int
0x180015420  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180015425  mov     ecx, eax
0x180015427  jmp     short loc_180015473
0x180015429  mov     rdx, r9; unsigned int *
0x18001542c  mov     ecx, r10d; unsigned int
0x18001542f  call    ?GetReconnectedFromId@@YAJKPEAK@Z; GetReconnectedFromId(ulong,ulong *)
0x180015434  mov     ebx, eax
0x180015436  test    eax, eax
0x180015438  jns     short loc_180015446
0x18001543a  lea     rdx, aGetreconnected; "GetReconnectedFromId failed: 0x%x in %s"
0x180015441  jmp     loc_1800153AD
0x180015446  mov     rax, [rsp+38h+arg_28]
0x18001544b  mov     bl, 1
0x18001544d  mov     dword ptr [rax], 4
0x180015453  movzx   eax, bl
0x180015456  add     rsp, 30h
0x18001545a  pop     rbx
0x18001545b  retn
0x18001545d  lea     rdx, aObsoleteWinsta; jumptable 0000000180015358 default case, cases 5,9-13,15-19,21-24,26,27,30-36,38
0x180015464  mov     ecx, 4; int
0x180015469  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001546e  mov     ecx, 1; dwErrCode
0x180015473  call    cs:__imp_SetLastError
0x18001547a  nop     dword ptr [rax+rax+00h]
0x18001547f  xor     bl, bl
0x180015481  movzx   eax, bl
0x180015484  add     rsp, 30h
0x180015488  pop     rbx
0x180015489  retn
```
