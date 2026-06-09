# TetheringService::RemovePeer(uchar (*)[6])

- ea: `0x18001b898`
- end: `0x18001bb25`
- name: `?RemovePeer@TetheringService@@QEAAXPEAY05E@Z`
- size: `653`
- prototype: `void __fastcall(TetheringService *__hidden this, unsigned __int8 (*)[6])`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18001379c`
- `0x18001f740`
- `0x180025394`

## callees

- `0x180002590`
- `0x180003088`
- `0x18000bf4c`
- `0x18000d9dc`
- `0x18001b898`
- `0x18001c184`
- `0x1800200d0`
- `0x180020524`
- `0x180029c10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ba71`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ba71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001baf7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001baf7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b8fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b8fd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001bae3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001bae3`

## pseudocode

```c
void __fastcall TetheringService::RemovePeer(TetheringService *this, unsigned __int8 (*a2)[6])
{
  unsigned __int8 *v4; // rdi
  unsigned __int8 *v5; // rcx
  __int64 v6; // rax
  int v7; // ecx
  int v8; // edx
  int v9; // r8d
  int v10; // r10d
  int v11; // r9d
  __int128 v12; // xmm0
  int v13; // eax
  TetheringServiceTelemetry *v14; // rcx
  __int64 v15; // rdx
  int v16; // [rsp+40h] [rbp-148h]
  int v17; // [rsp+50h] [rbp-138h] BYREF
  _BYTE v18[220]; // [rsp+54h] [rbp-134h] BYREF
  int v19; // [rsp+130h] [rbp-58h] BYREF
  __int128 v20; // [rsp+134h] [rbp-54h]
  int v21; // [rsp+144h] [rbp-44h]
  char v22[16]; // [rsp+148h] [rbp-40h] BYREF
  __int16 v23; // [rsp+158h] [rbp-30h]

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 290, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)this + 34);
  v4 = (unsigned __int8 *)*((_QWORD *)this + 175);
  v5 = 0;
  if ( !v4 )
    goto LABEL_20;
  do
  {
    if ( *(_DWORD *)v4 == *(_DWORD *)a2 && *((_WORD *)v4 + 2) == *(_WORD *)&(*a2)[4] )
      break;
    v5 = v4;
    v4 = (unsigned __int8 *)*((_QWORD *)v4 + 29);
  }
  while ( v4 );
  if ( v4 )
  {
    v6 = *((_QWORD *)v4 + 29);
    if ( v5 )
      *((_QWORD *)v5 + 29) = v6;
    else
      *((_QWORD *)this + 175) = v6;
    --*((_DWORD *)this + 415);
    memset_0(v18, 0, 0xD0u);
    v17 = 4;
    TetheringService::SendNotification(this, (struct _TETHERING_WNF_NOTIFICATION_MSG *)&v17);
    if ( !IsMobile() )
    {
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 291, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
      }
      CSebHelper::PublishWnfEvent((char *)this + 1288, 12);
    }
    v7 = v4[4];
    v8 = v4[3];
    v9 = v4[2];
    v10 = v4[1];
    v11 = *v4;
    v23 = 0;
    v16 = v4[5];
    *(_OWORD *)v22 = 0;
    StringCchPrintfA(v22, 0x12u, "%02x:%02x:%02x:%02x:%02x:%02x", v11, v10, v9, v8, v7, v16);
    v12 = *((_OWORD *)this + 27);
    v13 = *((_DWORD *)this + 112);
    v19 = 25;
    v21 = v13;
    v20 = v12;
    NetworkingTriageScenario::MobileHotspot::TetheringPeerRemoved(
      (const struct NetworkingTriageScenario::MobileHotspot::RequiredFields *)&v19,
      v22,
      (const unsigned __int16 *)v4 + 3);
    free(v4);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v15 = 292;
LABEL_23:
      WPP_SF_(*((_QWORD *)v14 + 2), v15, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    }
  }
  else
  {
LABEL_20:
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v15 = 293;
      goto LABEL_23;
    }
  }
  if ( !*((_QWORD *)this + 175)
    && *((_BYTE *)this + 1568)
    && ChangeTimerQueueTimer(*((HANDLE *)this + 198), *((HANDLE *)this + 197), *((_DWORD *)this + 398), 0xFFFFFFFF) )
  {
    *((_BYTE *)this + 1596) = 1;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 34);
}

```

## disassembly

```asm
0x18001b898  mov     [rsp+arg_8], rbx
0x18001b89d  mov     [rsp+arg_10], rbp
0x18001b8a2  push    rsi
0x18001b8a3  push    rdi
0x18001b8a4  push    r15
0x18001b8a6  sub     rsp, 170h
0x18001b8ad  mov     rax, cs:__security_cookie
0x18001b8b4  xor     rax, rsp
0x18001b8b7  mov     [rsp+188h+var_28], rax
0x18001b8bf  mov     rsi, rdx
0x18001b8c2  mov     rbx, rcx
0x18001b8c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8cc  lea     r15, WPP_GLOBAL_Control
0x18001b8d3  cmp     rcx, r15
0x18001b8d6  jz      short loc_18001B8F3
0x18001b8d8  test    byte ptr [rcx+1Ch], 8
0x18001b8dc  jz      short loc_18001B8F3
0x18001b8de  mov     rcx, [rcx+10h]
0x18001b8e2  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001b8e9  mov     edx, 122h
0x18001b8ee  call    WPP_SF_
0x18001b8f3  lea     rbp, [rbx+550h]
0x18001b8fa  mov     rcx, rbp; lpCriticalSection
0x18001b8fd  call    cs:__imp_EnterCriticalSection
0x18001b903  mov     rdi, [rbx+578h]
0x18001b90a  xor     ecx, ecx
0x18001b90c  test    rdi, rdi
0x18001b90f  jz      loc_18001BA90
0x18001b915  mov     eax, [rdi]
0x18001b917  cmp     eax, [rsi]
0x18001b919  jnz     short loc_18001B925
0x18001b91b  movzx   eax, word ptr [rdi+4]
0x18001b91f  cmp     ax, [rsi+4]
0x18001b923  jz      short loc_18001B934
0x18001b925  mov     rcx, rdi
0x18001b928  mov     rdi, [rdi+0E8h]
0x18001b92f  test    rdi, rdi
0x18001b932  jnz     short loc_18001B915
0x18001b934  test    rdi, rdi
0x18001b937  jz      loc_18001BA90
0x18001b93d  mov     rax, [rdi+0E8h]
0x18001b944  test    rcx, rcx
0x18001b947  jnz     short loc_18001B952
0x18001b949  mov     [rbx+578h], rax
0x18001b950  jmp     short loc_18001B959
0x18001b952  mov     [rcx+0E8h], rax
0x18001b959  mov     eax, [rbx+67Ch]
0x18001b95f  lea     rcx, [rsp+188h+var_134]; void *
0x18001b964  dec     eax
0x18001b966  xor     edx, edx; Val
0x18001b968  mov     r8d, 0D0h; Size
0x18001b96e  mov     [rbx+67Ch], eax
0x18001b974  call    memset_0
0x18001b979  lea     rdx, [rsp+188h+var_138]; struct _TETHERING_WNF_NOTIFICATION_MSG *
0x18001b97e  mov     [rsp+188h+var_138], 4
0x18001b986  mov     rcx, rbx; this
0x18001b989  call    ?SendNotification@TetheringService@@AEAAXPEAU_TETHERING_WNF_NOTIFICATION_MSG@@@Z; TetheringService::SendNotification(_TETHERING_WNF_NOTIFICATION_MSG *)
0x18001b98e  call    ?IsMobile@@YA_NXZ; IsMobile(void)
0x18001b993  test    al, al
0x18001b995  jnz     short loc_18001B9CF
0x18001b997  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b99e  cmp     rcx, r15
0x18001b9a1  jz      short loc_18001B9BE
0x18001b9a3  test    byte ptr [rcx+1Ch], 4
0x18001b9a7  jz      short loc_18001B9BE
0x18001b9a9  mov     rcx, [rcx+10h]
0x18001b9ad  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001b9b4  mov     edx, 123h
0x18001b9b9  call    WPP_SF_
0x18001b9be  lea     rcx, [rbx+508h]
0x18001b9c5  mov     edx, 0Ch
0x18001b9ca  call    ?PublishWnfEvent@CSebHelper@@SAJAEBU_GUID@@W4NotificationMessageType@@I@Z; CSebHelper::PublishWnfEvent(_GUID const &,NotificationMessageType,uint)
0x18001b9cf  movzx   ecx, byte ptr [rdi+4]
0x18001b9d3  xor     eax, eax
0x18001b9d5  movzx   edx, byte ptr [rdi+3]
0x18001b9d9  xorps   xmm0, xmm0
0x18001b9dc  movzx   r8d, byte ptr [rdi+2]
0x18001b9e1  movzx   r10d, byte ptr [rdi+1]
0x18001b9e6  movzx   r9d, byte ptr [rdi]
0x18001b9ea  mov     [rsp+188h+var_30], ax
0x18001b9f2  movzx   eax, byte ptr [rdi+5]
0x18001b9f6  mov     [rsp+188h+var_148], eax
0x18001b9fa  mov     [rsp+188h+var_150], ecx
0x18001b9fe  lea     rcx, [rsp+188h+var_40]; char *
0x18001ba06  mov     [rsp+188h+var_158], edx
0x18001ba0a  mov     edx, 12h; unsigned __int64
0x18001ba0f  mov     [rsp+188h+var_160], r8d
0x18001ba14  lea     r8, a02x02x02x02x02; "%02x:%02x:%02x:%02x:%02x:%02x"
0x18001ba1b  movups  xmmword ptr [rsp+188h+var_40], xmm0
0x18001ba23  mov     [rsp+188h+var_168], r10d
0x18001ba28  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001ba2d  movups  xmm0, xmmword ptr [rbx+1B0h]
0x18001ba34  mov     eax, [rbx+1C0h]
0x18001ba3a  lea     r8, [rdi+6]; unsigned __int16 *
0x18001ba3e  lea     rdx, [rsp+188h+var_40]; char *
0x18001ba46  mov     [rsp+188h+var_58], 19h
0x18001ba51  lea     rcx, [rsp+188h+var_58]; struct NetworkingTriageScenario::MobileHotspot::RequiredFields *
0x18001ba59  mov     [rsp+188h+var_44], eax
0x18001ba60  movdqu  [rsp+188h+var_54], xmm0
0x18001ba69  call    ?TetheringPeerRemoved@MobileHotspot@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBDPEBG@Z; NetworkingTriageScenario::MobileHotspot::TetheringPeerRemoved(NetworkingTriageScenario::MobileHotspot::RequiredFields const &,char const *,ushort const *)
0x18001ba6e  mov     rcx, rdi; Block
0x18001ba71  call    cs:__imp_free
0x18001ba77  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba7e  cmp     rcx, r15
0x18001ba81  jz      short loc_18001BAB7
0x18001ba83  test    byte ptr [rcx+1Ch], 4
0x18001ba87  jz      short loc_18001BAB7
0x18001ba89  mov     edx, 124h
0x18001ba8e  jmp     short loc_18001BAA7
0x18001ba90  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba97  cmp     rcx, r15
0x18001ba9a  jz      short loc_18001BAB7
0x18001ba9c  test    byte ptr [rcx+1Ch], 2
0x18001baa0  jz      short loc_18001BAB7
0x18001baa2  mov     edx, 125h
0x18001baa7  mov     rcx, [rcx+10h]
0x18001baab  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001bab2  call    WPP_SF_
0x18001bab7  cmp     qword ptr [rbx+578h], 0
0x18001babf  jnz     short loc_18001BAF4
0x18001bac1  cmp     byte ptr [rbx+620h], 0
0x18001bac8  jz      short loc_18001BAF4
0x18001baca  mov     r8d, [rbx+638h]; DueTime
0x18001bad1  or      r9d, 0FFFFFFFFh; Period
0x18001bad5  mov     rdx, [rbx+628h]; Timer
0x18001badc  mov     rcx, [rbx+630h]; TimerQueue
0x18001bae3  call    cs:__imp_ChangeTimerQueueTimer
0x18001bae9  test    eax, eax
0x18001baeb  jz      short loc_18001BAF4
0x18001baed  mov     byte ptr [rbx+63Ch], 1
0x18001baf4  mov     rcx, rbp; lpCriticalSection
0x18001baf7  call    cs:__imp_LeaveCriticalSection
0x18001bafd  mov     rcx, [rsp+188h+var_28]
0x18001bb05  xor     rcx, rsp; StackCookie
0x18001bb08  call    __security_check_cookie
0x18001bb0d  lea     r11, [rsp+188h+var_18]
0x18001bb15  mov     rbx, [r11+28h]
0x18001bb19  mov     rbp, [r11+30h]
0x18001bb1d  mov     rsp, r11
0x18001bb20  pop     r15
0x18001bb22  pop     rdi
0x18001bb23  pop     rsi
0x18001bb24  retn
```
