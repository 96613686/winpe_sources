# CreateDefaultSchedule(SUBSCRIPTIONSCHEDULE,_GUID *)

- ea: `0x18000b208`
- end: `0x18000b36e`
- name: `?CreateDefaultSchedule@@YAJW4SUBSCRIPTIONSCHEDULE@@PEAU_GUID@@@Z`
- size: `358`
- prototype: `int(enum SUBSCRIPTIONSCHEDULE, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000afb4`

## callees

- `0x18000b208`
- `0x18000b3fc`
- `0x18000d580`
- `0x18001d038`
- `0x180029280`

## import_xrefs

- `USER32!LoadStringW` at `0x18000b313`
- `USER32!LoadStringW` at `0x18000b313`

## pseudocode

```c
__int64 __fastcall CreateDefaultSchedule(enum SUBSCRIPTIONSCHEDULE a1, struct _GUID *a2)
{
  int v3; // ecx
  struct _GUID v4; // xmm0
  UINT v5; // r14d
  unsigned int v6; // esi
  int v7; // eax
  _TASK_TRIGGER v9; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  *(_OWORD *)&v9.cbTriggerSize = 0;
  *a2 = GUID_NULL;
  memset(&v9.wStartHour, 0, 32);
  if ( a1 == SUBSSCHED_AUTO )
    return (unsigned int)-2147467259;
  v3 = a1 - 1;
  if ( !v3 )
  {
    v4 = (struct _GUID)NOTFCOOKIE_SCHEDULE_GROUP_DAILY;
    v5 = 8044;
    v9.TriggerType = TASK_TIME_TRIGGER_DAILY;
    v9.Type.Daily.DaysInterval = 1;
    goto LABEL_6;
  }
  if ( v3 != 1 )
    return (unsigned int)-2147467259;
  v4 = (struct _GUID)NOTFCOOKIE_SCHEDULE_GROUP_WEEKLY;
  v9.Type.MonthlyDate.rgfDays = 131073;
  v9.TriggerType = TASK_TIME_TRIGGER_WEEKLY;
  v5 = 8210;
LABEL_6:
  v6 = 0;
  *a2 = v4;
  if ( !ScheduleCookieExists(a2) )
  {
    v7 = Random(11);
    v9.rgFlags = 0;
    v9.cbTriggerSize = 48;
    v9.wRandomMinutesInterval = 30;
    v9.wStartHour = 30 * v7 / 0x3Cu;
    v9.wStartMinute = 30 * v7 % 0x3Cu;
    LoadStringW(g_hinstMUI, v5, Buffer, 260);
    v6 = CreateSchedule(Buffer, 0, a2, &v9, 1);
    if ( v6 == -2147220991 )
      return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18000b208  mov     [rsp-8+arg_0], rbx
0x18000b20d  mov     [rsp-8+arg_10], rsi
0x18000b212  push    rbp
0x18000b213  push    rdi
0x18000b214  push    r14
0x18000b216  lea     rbp, [rsp-180h]
0x18000b21e  sub     rsp, 280h
0x18000b225  mov     rax, cs:__security_cookie
0x18000b22c  xor     rax, rsp
0x18000b22f  mov     [rbp+190h+var_20], rax
0x18000b236  xorps   xmm1, xmm1
0x18000b239  mov     rdi, rdx
0x18000b23c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000b243  movups  xmmword ptr [rsp+290h+var_260.cbTriggerSize], xmm1
0x18000b248  movdqu  xmmword ptr [rdx], xmm0
0x18000b24c  movups  xmmword ptr [rsp+290h+var_260.wStartHour], xmm1
0x18000b251  movups  xmmword ptr [rsp+290h+var_260.TriggerType], xmm1
0x18000b256  test    ecx, ecx
0x18000b258  jz      loc_18000B340
0x18000b25e  sub     ecx, 1
0x18000b261  jz      short loc_18000B28D
0x18000b263  sub     ecx, 1
0x18000b266  jnz     loc_18000B340
0x18000b26c  movups  xmm0, cs:NOTFCOOKIE_SCHEDULE_GROUP_WEEKLY
0x18000b273  lea     eax, [rcx+2]
0x18000b276  mov     dword ptr [rsp+290h+var_260.Type], 20001h
0x18000b27e  mov     [rsp+290h+var_260.TriggerType], eax
0x18000b282  lea     ebx, [rcx+1]
0x18000b285  mov     r14d, 2012h
0x18000b28b  jmp     short loc_18000B2A8
0x18000b28d  movups  xmm0, cs:NOTFCOOKIE_SCHEDULE_GROUP_DAILY
0x18000b294  mov     ebx, 1
0x18000b299  mov     r14d, 1F6Ch
0x18000b29f  mov     [rsp+290h+var_260.TriggerType], ebx
0x18000b2a3  mov     word ptr [rsp+290h+var_260.Type], bx
0x18000b2a8  mov     rcx, rdi; struct _GUID *
0x18000b2ab  xor     esi, esi
0x18000b2ad  movdqu  xmmword ptr [rdx], xmm0
0x18000b2b1  call    ?ScheduleCookieExists@@YAHPEAU_GUID@@@Z; ScheduleCookieExists(_GUID *)
0x18000b2b6  test    eax, eax
0x18000b2b8  jnz     loc_18000B345
0x18000b2be  lea     ecx, [rsi+0Bh]
0x18000b2c1  call    Random
0x18000b2c6  imul    r9d, eax, 1Eh
0x18000b2ca  lea     r8, [rsp+290h+Buffer]; lpBuffer
0x18000b2cf  lea     eax, [rsi+30h]
0x18000b2d2  mov     [rsp+290h+var_260.rgFlags], esi
0x18000b2d6  mov     [rsp+290h+var_260.cbTriggerSize], ax
0x18000b2db  lea     eax, [rsi+1Eh]
0x18000b2de  mov     [rsp+290h+var_260.wRandomMinutesInterval], ax
0x18000b2e3  mov     eax, 88888889h
0x18000b2e8  mul     r9d
0x18000b2eb  shr     edx, 5
0x18000b2ee  movzx   eax, dx
0x18000b2f1  imul    ecx, eax, 3Ch ; '<'
0x18000b2f4  mov     [rsp+290h+var_260.wStartHour], dx
0x18000b2f9  mov     edx, r14d; uID
0x18000b2fc  sub     r9w, cx
0x18000b300  mov     rcx, cs:g_hinstMUI; hInstance
0x18000b307  mov     [rsp+290h+var_260.wStartMinute], r9w
0x18000b30d  mov     r9d, 104h; cchBufferMax
0x18000b313  call    cs:__imp_LoadStringW
0x18000b319  lea     r9, [rsp+290h+var_260]; struct _TASK_TRIGGER *
0x18000b31e  mov     [rsp+290h+var_270], ebx; int
0x18000b322  mov     r8, rdi; struct _GUID *
0x18000b325  lea     rcx, [rsp+290h+Buffer]; unsigned __int16 *
0x18000b32a  xor     edx, edx; unsigned int
0x18000b32c  call    ?CreateSchedule@@YAJPEBGKPEAU_GUID@@PEAU_TASK_TRIGGER@@H@Z; CreateSchedule(ushort const *,ulong,_GUID *,_TASK_TRIGGER *,int)
0x18000b331  mov     esi, eax
0x18000b333  xor     eax, eax
0x18000b335  cmp     esi, 80040201h
0x18000b33b  cmovz   esi, eax
0x18000b33e  jmp     short loc_18000B345
0x18000b340  mov     esi, 80004005h
0x18000b345  mov     eax, esi
0x18000b347  mov     rcx, [rbp+190h+var_20]
0x18000b34e  xor     rcx, rsp; StackCookie
0x18000b351  call    __security_check_cookie
0x18000b356  lea     r11, [rsp+290h+var_10]
0x18000b35e  mov     rbx, [r11+20h]
0x18000b362  mov     rsi, [r11+30h]
0x18000b366  mov     rsp, r11
0x18000b369  pop     r14
0x18000b36b  pop     rdi
0x18000b36c  pop     rbp
0x18000b36d  retn
```
