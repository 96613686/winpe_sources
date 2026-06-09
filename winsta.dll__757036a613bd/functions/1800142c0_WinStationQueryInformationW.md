# WinStationQueryInformationW

- ea: `0x1800142c0`
- end: `0x1800144ca`
- name: `WinStationQueryInformationW`
- size: `522`
- prototype: `__int64 __usercall@<rax>(CPublicBinding *this@<rcx>, unsigned int@<edx>, int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180004bb0`

## callees

- `0x180005fcc`
- `0x180007890`
- `0x1800083b0`
- `0x18000c820`
- `0x1800142c0`
- `0x180021de8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800142fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014374`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800143bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014423`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001447d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800142fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014374`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800143bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014423`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001447d`

## string_xrefs

- `0x180014357`: `WinStationUserToken failed: 0x%x in %s`
- `0x180014397`: `GetUserTokenForSession failed: 0x%x in %s`

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
  DWORD v8; // eax
  int UserTokenForSession; // ebx
  DWORD v10; // eax
  DWORD v11; // eax

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
      if ( a5 >= 0x18 )
      {
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
      }
      else
      {
        _DbgPrintMessage(8, "WinStationUserToken failed: 0x%x in %s", -2147024809, "WinStationQueryInformationW");
        v8 = ConvertHRESULT2WIN32(-2147024809);
        SetLastError(v8);
        result = 0;
      }
      break;
    case 0x25u:
      if ( a5 >= 4 )
      {
        UserTokenForSession = GetReconnectedFromId(SessionId, (unsigned int *)a4);
        if ( UserTokenForSession >= 0 )
        {
          *a6 = 4;
          result = 1;
        }
        else
        {
          _DbgPrintMessage(
            8,
            "GetReconnectedFromId failed: 0x%x in %s",
            (unsigned int)UserTokenForSession,
            "WinStationQueryInformationW");
LABEL_12:
          v10 = ConvertHRESULT2WIN32(UserTokenForSession);
          SetLastError(v10);
          result = 0;
        }
      }
      else
      {
        _DbgPrintMessage(
          8,
          "WinStationReconnectedFromId failed: 0x%x in %s",
          -2147024809,
          "WinStationQueryInformationW");
        v11 = ConvertHRESULT2WIN32(-2147024809);
        SetLastError(v11);
        result = 0;
      }
      break;
    default:
      _DbgPrintMessage(4, "!!! Obsolete_WinStationQueryInformationW deprecated");
      SetLastError(1u);
      result = 0;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x1800142c0  push    rbx
0x1800142c2  sub     rsp, 30h
0x1800142c6  mov     r10d, edx
0x1800142c9  mov     r11, rcx
0x1800142cc  cmp     edx, 0FFFFFFFFh
0x1800142cf  jnz     short loc_180014319
0x1800142d1  test    rcx, rcx
0x1800142d4  jz      short loc_180014309
0x1800142d6  xor     eax, eax
0x1800142d8  cmp     ax, [rcx]
0x1800142db  jz      short loc_180014309
0x1800142dd  cmp     [rcx+30h], eax
0x1800142e0  jnz     short loc_180014309
0x1800142e2  lea     rdx, aLogonidCurrent
0x1800142e9  mov     ecx, 4; int
0x1800142ee  xor     bl, bl
0x1800142f0  call    ?_DbgPrintMessage@@YAXHPEBDZZ
0x1800142f5  mov     ecx, 57h ; 'W'; dwErrCode
0x1800142fa  call    cs:__imp_SetLastError
0x180014300  movzx   eax, bl
0x180014303  add     rsp, 30h
0x180014307  pop     rbx
0x180014308  retn
0x180014309  mov     rax, gs:60h
0x180014312  mov     r10d, [rax+2C0h]
0x180014319  lea     eax, [r8-1]; switch 42 cases
0x18001431d  cmp     eax, 29h
0x180014320  ja      def_180014341; jumptable 0000000180014341 default case, cases 5,9-13,15-19,21-24,26,27,30-36,38
0x180014326  lea     rdx, __ImageBase
0x18001432d  cdqe
0x18001432f  movzx   eax, ds:(byte_1800144A0 - 180000000h)[rdx+rax]
0x180014337  mov     ecx, ds:(jpt_180014341 - 180000000h)[rdx+rax*4]
0x18001433e  add     rcx, rdx
0x180014341  jmp     rcx; switch jump
0x180014343  cmp     [rsp+38h+arg_20], 18h; jumptable 0000000180014341 case 14
0x180014348  jnb     short loc_180014385
0x18001434a  lea     r9, aWinstationquer_11
0x180014351  mov     r8d, 80070057h
0x180014357  lea     rdx, aWinstationuser_0
0x18001435e  mov     ecx, 8; int
0x180014363  call    ?_DbgPrintMessage@@YAXHPEBDZZ
0x180014368  mov     ecx, 80070057h; int
0x18001436d  call    ?ConvertHRESULT2WIN32@@YAKJ@Z
0x180014372  mov     ecx, eax; dwErrCode
0x180014374  call    cs:__imp_SetLastError
0x18001437a  xor     bl, bl
0x18001437c  movzx   eax, bl
0x18001437f  add     rsp, 30h
0x180014383  pop     rbx
0x180014384  retn
0x180014385  lea     rdx, [r9+10h]; void **
0x180014389  mov     ecx, r10d; unsigned int
0x18001438c  call    ?GetUserTokenForSession@@YAJKPEAPEAX@Z
0x180014391  mov     ebx, eax
0x180014393  test    eax, eax
0x180014395  jns     short loc_1800143CC
0x180014397  lea     rdx, aGetusertokenfo
0x18001439e  mov     r8d, ebx
0x1800143a1  lea     r9, aWinstationquer_11
0x1800143a8  mov     ecx, 8; int
0x1800143ad  call    ?_DbgPrintMessage@@YAXHPEBDZZ
0x1800143b2  mov     ecx, ebx; int
0x1800143b4  call    ?ConvertHRESULT2WIN32@@YAKJ@Z
0x1800143b9  mov     ecx, eax; dwErrCode
0x1800143bb  call    cs:__imp_SetLastError
0x1800143c1  xor     bl, bl
0x1800143c3  movzx   eax, bl
0x1800143c6  add     rsp, 30h
0x1800143ca  pop     rbx
0x1800143cb  retn
0x1800143cc  mov     rax, [rsp+38h+arg_28]
0x1800143d1  mov     bl, 1
0x1800143d3  mov     dword ptr [rax], 18h
0x1800143d9  movzx   eax, bl
0x1800143dc  add     rsp, 30h
0x1800143e0  pop     rbx
0x1800143e1  retn
0x1800143e2  mov     edx, r10d; jumptable 0000000180014341 cases 1-4,6-8,20,25,28,29,39-42
0x1800143e5  mov     rcx, r11; this
0x1800143e8  add     rsp, 30h
0x1800143ec  pop     rbx
0x1800143ed  jmp     ?Public_WinStationQueryInformationW@@YAEPEAXKW4_WINSTATIONINFOCLASS@@0KPEAK@Z
0x1800143f2  cmp     [rsp+38h+arg_20], 4; jumptable 0000000180014341 case 37
0x1800143f7  jnb     short loc_180014434
0x1800143f9  lea     r9, aWinstationquer_11
0x180014400  mov     r8d, 80070057h
0x180014406  lea     rdx, aWinstationreco
0x18001440d  mov     ecx, 8; int
0x180014412  call    ?_DbgPrintMessage@@YAXHPEBDZZ
0x180014417  mov     ecx, 80070057h; int
0x18001441c  call    ?ConvertHRESULT2WIN32@@YAKJ@Z
0x180014421  mov     ecx, eax; dwErrCode
0x180014423  call    cs:__imp_SetLastError
0x180014429  xor     bl, bl
0x18001442b  movzx   eax, bl
0x18001442e  add     rsp, 30h
0x180014432  pop     rbx
0x180014433  retn
0x180014434  mov     rdx, r9; unsigned int *
0x180014437  mov     ecx, r10d; unsigned int
0x18001443a  call    ?GetReconnectedFromId@@YAJKPEAK@Z
0x18001443f  mov     ebx, eax
0x180014441  test    eax, eax
0x180014443  jns     short loc_180014451
0x180014445  lea     rdx, aGetreconnected
0x18001444c  jmp     loc_18001439E
0x180014451  mov     rax, [rsp+38h+arg_28]
0x180014456  mov     bl, 1
0x180014458  mov     dword ptr [rax], 4
0x18001445e  movzx   eax, bl
0x180014461  add     rsp, 30h
0x180014465  pop     rbx
0x180014466  retn
0x180014467  lea     rdx, aObsoleteWinsta; jumptable 0000000180014341 default case, cases 5,9-13,15-19,21-24,26,27,30-36,38
0x18001446e  mov     ecx, 4; int
0x180014473  call    ?_DbgPrintMessage@@YAXHPEBDZZ
0x180014478  mov     ecx, 1; dwErrCode
0x18001447d  call    cs:__imp_SetLastError
0x180014483  xor     bl, bl
0x180014485  movzx   eax, bl
0x180014488  add     rsp, 30h
0x18001448c  pop     rbx
0x18001448d  retn
```
