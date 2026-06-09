# SleepStudyManager::~SleepStudyManager(void)

- ea: `0x180046208`
- end: `0x1800463ba`
- name: `??1SleepStudyManager@@UEAA@XZ`
- size: `434`
- prototype: `void __fastcall(SleepStudyManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800463c0`

## callees

- `0x18000fe2c`
- `0x18000fe54`
- `0x180046208`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180046379`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180046379`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180046268`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180046268`
- `ntdll!RtlNtStatusToDosError` at `0x1800462b4`
- `ntdll!RtlNtStatusToDosError` at `0x1800462b4`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800462eb`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800462eb`

## pseudocode

```c
void __fastcall SleepStudyManager::~SleepStudyManager(SleepStudyManager *this)
{
  char *v2; // rcx
  int v3; // eax
  NTSTATUS v4; // ebx
  ULONG v5; // eax
  signed int v6; // eax
  signed int v7; // ebx
  __int64 v8; // r9

  *(_QWORD *)this = &SleepStudyManager::`vftable';
  v2 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a64cad8379ea35ae44c45673a4b5eb3c_Traceguids);
    v2 = (char *)WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 1) )
  {
    v3 = RtlUnsubscribeWnfNotificationWaitForCompletion(*((_QWORD *)this + 1));
    v4 = v3;
    if ( v3 >= 0 )
    {
LABEL_14:
      v2 = (char *)WPP_GLOBAL_Control;
      goto LABEL_15;
    }
    v2 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_a64cad8379ea35ae44c45673a4b5eb3c_Traceguids,
          (unsigned int)v3);
        v2 = (char *)WPP_GLOBAL_Control;
      }
      if ( v2 != (char *)&WPP_GLOBAL_Control && v2[28] < 0 )
      {
        v5 = RtlNtStatusToDosError(v4);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_a64cad8379ea35ae44c45673a4b5eb3c_Traceguids, v5);
        goto LABEL_14;
      }
    }
  }
LABEL_15:
  if ( !*((_QWORD *)this + 2) )
    goto LABEL_30;
  v6 = PowerSettingUnregisterNotification(*((HPOWERNOTIFY *)this + 2));
  v7 = v6;
  if ( !v6 )
    goto LABEL_29;
  v2 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v6 > 0 )
        v8 = (unsigned __int16)v6 | 0x80070000;
      else
        v8 = (unsigned int)v6;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a64cad8379ea35ae44c45673a4b5eb3c_Traceguids, v8);
      v2 = (char *)WPP_GLOBAL_Control;
    }
    if ( v2 != (char *)&WPP_GLOBAL_Control && v2[28] < 0 )
    {
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      WPP_SF_d(*((_QWORD *)v2 + 2), 16, WPP_a64cad8379ea35ae44c45673a4b5eb3c_Traceguids, (unsigned int)v7);
LABEL_29:
      v2 = (char *)WPP_GLOBAL_Control;
    }
  }
LABEL_30:
  if ( *((_QWORD *)this + 3) )
  {
    EventUnregister(*((_QWORD *)this + 3));
    *((_QWORD *)this + 3) = 0;
    v2 = (char *)WPP_GLOBAL_Control;
  }
  if ( v2 != (char *)&WPP_GLOBAL_Control && (v2[28] & 4) != 0 && (unsigned __int8)v2[25] >= 6u )
    WPP_SF_(*((_QWORD *)v2 + 2), 17, WPP_a64cad8379ea35ae44c45673a4b5eb3c_Traceguids);
}

```

## disassembly

```asm
0x180046208  push    rbx
0x18004620a  push    rbp
0x18004620b  push    rdi
0x18004620c  push    r14
0x18004620e  sub     rsp, 28h
0x180046212  lea     rax, ??_7SleepStudyManager@@6B@; const SleepStudyManager::`vftable'
0x180046219  mov     rdi, rcx
0x18004621c  mov     [rcx], rax
0x18004621f  mov     rcx, cs:WPP_GLOBAL_Control
0x180046226  lea     rbp, WPP_GLOBAL_Control
0x18004622d  lea     r14, WPP_a64cad8379ea35ae44c45673a4b5eb3c_Traceguids
0x180046234  cmp     rcx, rbp
0x180046237  jz      short loc_18004625D
0x180046239  test    byte ptr [rcx+1Ch], 4
0x18004623d  jz      short loc_18004625D
0x18004623f  cmp     byte ptr [rcx+19h], 6
0x180046243  jb      short loc_18004625D
0x180046245  mov     rcx, [rcx+10h]
0x180046249  mov     edx, 0Ch
0x18004624e  mov     r8, r14
0x180046251  call    WPP_SF_
0x180046256  mov     rcx, cs:WPP_GLOBAL_Control
0x18004625d  cmp     qword ptr [rdi+8], 0
0x180046262  jz      short loc_1800462DC
0x180046264  mov     rcx, [rdi+8]
0x180046268  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18004626e  mov     ebx, eax
0x180046270  test    eax, eax
0x180046272  jns     short loc_1800462D5
0x180046274  mov     rcx, cs:WPP_GLOBAL_Control
0x18004627b  cmp     rcx, rbp
0x18004627e  jz      short loc_1800462DC
0x180046280  test    byte ptr [rcx+1Ch], 4
0x180046284  jz      short loc_1800462A7
0x180046286  cmp     byte ptr [rcx+19h], 2
0x18004628a  jb      short loc_1800462A7
0x18004628c  mov     rcx, [rcx+10h]
0x180046290  mov     edx, 0Dh
0x180046295  mov     r9d, eax
0x180046298  mov     r8, r14
0x18004629b  call    WPP_SF_d
0x1800462a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800462a7  cmp     rcx, rbp
0x1800462aa  jz      short loc_1800462DC
0x1800462ac  test    byte ptr [rcx+1Ch], 80h
0x1800462b0  jz      short loc_1800462DC
0x1800462b2  mov     ecx, ebx; Status
0x1800462b4  call    cs:__imp_RtlNtStatusToDosError
0x1800462ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800462c1  mov     edx, 0Eh
0x1800462c6  mov     r9d, eax
0x1800462c9  mov     r8, r14
0x1800462cc  mov     rcx, [rcx+10h]
0x1800462d0  call    WPP_SF_d
0x1800462d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800462dc  cmp     qword ptr [rdi+10h], 0
0x1800462e1  jz      loc_18004636E
0x1800462e7  mov     rcx, [rdi+10h]; RegistrationHandle
0x1800462eb  call    cs:__imp_PowerSettingUnregisterNotification
0x1800462f1  mov     ebx, eax
0x1800462f3  test    eax, eax
0x1800462f5  jz      short loc_180046367
0x1800462f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800462fe  cmp     rcx, rbp
0x180046301  jz      short loc_18004636E
0x180046303  test    byte ptr [rcx+1Ch], 4
0x180046307  jz      short loc_18004633B
0x180046309  cmp     byte ptr [rcx+19h], 2
0x18004630d  jb      short loc_18004633B
0x18004630f  test    eax, eax
0x180046311  jg      short loc_180046318
0x180046313  mov     r9d, eax
0x180046316  jmp     short loc_180046323
0x180046318  movzx   r9d, bx
0x18004631c  or      r9d, 80070000h
0x180046323  mov     rcx, [rcx+10h]
0x180046327  mov     edx, 0Fh
0x18004632c  mov     r8, r14
0x18004632f  call    WPP_SF_d
0x180046334  mov     rcx, cs:WPP_GLOBAL_Control
0x18004633b  cmp     rcx, rbp
0x18004633e  jz      short loc_18004636E
0x180046340  test    byte ptr [rcx+1Ch], 80h
0x180046344  jz      short loc_18004636E
0x180046346  test    ebx, ebx
0x180046348  jle     short loc_180046353
0x18004634a  movzx   ebx, bx
0x18004634d  or      ebx, 80070000h
0x180046353  mov     rcx, [rcx+10h]
0x180046357  mov     edx, 10h
0x18004635c  mov     r9d, ebx
0x18004635f  mov     r8, r14
0x180046362  call    WPP_SF_d
0x180046367  mov     rcx, cs:WPP_GLOBAL_Control
0x18004636e  cmp     qword ptr [rdi+18h], 0
0x180046373  jz      short loc_18004638E
0x180046375  mov     rcx, [rdi+18h]; RegHandle
0x180046379  call    cs:__imp_EventUnregister
0x18004637f  mov     qword ptr [rdi+18h], 0
0x180046387  mov     rcx, cs:WPP_GLOBAL_Control
0x18004638e  cmp     rcx, rbp
0x180046391  jz      short loc_1800463B0
0x180046393  test    byte ptr [rcx+1Ch], 4
0x180046397  jz      short loc_1800463B0
0x180046399  cmp     byte ptr [rcx+19h], 6
0x18004639d  jb      short loc_1800463B0
0x18004639f  mov     rcx, [rcx+10h]
0x1800463a3  mov     edx, 11h
0x1800463a8  mov     r8, r14
0x1800463ab  call    WPP_SF_
0x1800463b0  add     rsp, 28h
0x1800463b4  pop     r14
0x1800463b6  pop     rdi
0x1800463b7  pop     rbp
0x1800463b8  pop     rbx
0x1800463b9  retn
```
