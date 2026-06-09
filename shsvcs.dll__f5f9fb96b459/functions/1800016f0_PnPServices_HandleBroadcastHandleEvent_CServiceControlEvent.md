# PnPServices::_HandleBroadcastHandleEvent(CServiceControlEvent *)

- ea: `0x1800016f0`
- end: `0x180001a27`
- name: `?_HandleBroadcastHandleEvent@PnPServices@@YAJPEAVCServiceControlEvent@@@Z`
- size: `823`
- prototype: `__int64 __fastcall(PnPServices *__hidden this, struct CServiceControlEvent *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800015f0`

## callees

- `0x1800016f0`
- `0x180002e70`
- `0x180003570`
- `0x180014bd0`
- `0x18001b404`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800018f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800018f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000193f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000193f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800018ae`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800018ae`

## pseudocode

```c
__int64 __fastcall PnPServices::_HandleBroadcastHandleEvent(PnPServices *this, struct CServiceControlEvent *a2)
{
  int v3; // eax
  __int64 v4; // rdi
  unsigned int v5; // edx
  _QWORD *v6; // r8
  __int64 v7; // rax
  char *v8; // rax
  char *v9; // rbx
  BOOL v10; // edx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int128 v13; // xmm0
  _DWORD *v14; // rdi
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  __int64 v16; // rcx
  struct _RTL_CRITICAL_SECTION *v17; // rcx
  __int64 result; // rax
  unsigned int v19; // edi
  int v20; // eax
  int v21; // eax
  char *v22; // rax
  __int64 v23; // rcx
  struct PnPServices::CPnPDeviceEvent *v24; // rdi
  unsigned int v25; // ebx
  _OWORD v26[16]; // [rsp+30h] [rbp-108h] BYREF

  v3 = *((_DWORD *)this + 7);
  if ( v3 == 32774 )
  {
    v4 = *((_QWORD *)this + 4);
    v5 = 0;
    v26[0] = GUID_IO_DEVICE_BECOMING_READY;
    v26[1] = GUID_IO_VOLUME_MOUNT;
    v26[2] = GUID_IO_VOLUME_DISMOUNT;
    v26[3] = GUID_IO_VOLUME_DISMOUNT_FAILED;
    v26[4] = GUID_IO_VOLUME_LOCK;
    v26[5] = GUID_IO_VOLUME_UNLOCK;
    v26[6] = GUID_IO_VOLUME_LOCK_FAILED;
    v26[7] = GUID_IO_MEDIA_ARRIVAL;
    v26[8] = GUID_IO_MEDIA_REMOVAL;
    v26[9] = GUID_IO_VOLUME_CHANGE;
    v26[10] = GUID_IO_VOLUME_NAME_CHANGE;
    v26[11] = GUID_IO_VOLUME_PREPARING_EJECT;
    v26[12] = GUID_IO_VOLUME_BACKGROUND_FORMAT;
    v26[13] = GUID_IO_VOLUME_FVE_STATUS_CHANGE;
    v26[14] = GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE;
    while ( v5 < 0xF )
    {
      v6 = &v26[v5];
      v7 = *v6 - *(_QWORD *)(v4 + 32);
      if ( *v6 == *(_QWORD *)(v4 + 32) )
        v7 = v6[1] - *(_QWORD *)(v4 + 40);
      if ( !v7 )
      {
        v8 = (char *)operator new(0x38u);
        v9 = v8;
        if ( !v8 )
          return 2147942414LL;
        v10 = 0;
        *(_QWORD *)(v8 + 12) = 0;
        *(_QWORD *)(v8 + 20) = 0;
        *(_QWORD *)(v8 + 28) = 0;
        *(_QWORD *)(v8 + 36) = 0;
        *(_QWORD *)(v8 + 44) = 0;
        *((_DWORD *)v8 + 13) = 0;
        *((_DWORD *)v8 + 2) = 1;
        *(_QWORD *)v8 = &PnPServices::CPnPInterfaceEvent::`vftable';
        v11 = *(_QWORD *)&GUID_IO_VOLUME_MOUNT.Data1 - *(_QWORD *)(v4 + 32);
        if ( *(_QWORD *)&GUID_IO_VOLUME_MOUNT.Data1 == *(_QWORD *)(v4 + 32) )
          v11 = *(_QWORD *)GUID_IO_VOLUME_MOUNT.Data4 - *(_QWORD *)(v4 + 40);
        if ( !v11 && *(_DWORD *)v4 >= 0x48u && *(_DWORD *)(v4 + 52) == 1 )
          v10 = CompareStringOrdinal(
                  (LPCWCH)(v4 + 52 + *(unsigned int *)(v4 + 64)),
                  *(_DWORD *)(v4 + 60) >> 1,
                  L"RAW",
                  -1,
                  0) == 2;
        v12 = *(_QWORD *)(v4 + 24);
        *((_DWORD *)v9 + 4) = *((_DWORD *)this + 7);
        v13 = *(_OWORD *)(v4 + 32);
        *((_QWORD *)v9 + 5) = v12;
        *((_DWORD *)v9 + 12) = v10;
        *(_OWORD *)(v9 + 20) = v13;
        v14 = PnPServices::g_pmrePnPDeviceEvents;
        _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
        v15 = (struct _RTL_CRITICAL_SECTION *)(v14 + 44);
        if ( v14 == (_DWORD *)-168LL )
          v15 = 0;
        EnterCriticalSection(v15);
        v16 = *(_QWORD *)&v14[2 * *v14 + 2];
        if ( v16 && _InterlockedExchangeAdd((volatile signed __int32 *)(v16 + 8), 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(__int64, __int64))v16)(v16, 1);
        *(_QWORD *)&v14[2 * (*v14)++ + 2] = v9;
        if ( *v14 == 20 )
          *v14 = 0;
        v17 = 0;
        if ( v14 != (_DWORD *)-168LL )
          v17 = (struct _RTL_CRITICAL_SECTION *)(v14 + 44);
        LeaveCriticalSection(v17);
        result = PnPServices::CHandleNotif::HandleBroadcastHandleEvent((struct PnPServices::CPnPDeviceEvent *)v9);
        v19 = result;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(char *, __int64))v9)(v9, 1);
          return v19;
        }
        return result;
      }
      ++v5;
    }
    return 0;
  }
  v20 = v3 - 32769;
  if ( v20 )
  {
    v21 = v20 - 1;
    if ( v21 )
    {
      if ( (unsigned int)(v21 - 1) > 1 )
        return 0;
    }
  }
  v22 = (char *)operator new(0x38u);
  v24 = (struct PnPServices::CPnPDeviceEvent *)v22;
  if ( !v22 )
    return 2147942414LL;
  *(_QWORD *)(v22 + 12) = 0;
  *(_QWORD *)(v22 + 20) = 0;
  *(_QWORD *)(v22 + 28) = 0;
  *(_QWORD *)(v22 + 36) = 0;
  *(_QWORD *)(v22 + 44) = 0;
  *((_DWORD *)v22 + 13) = 0;
  *((_DWORD *)v22 + 2) = 1;
  *(_QWORD *)v22 = &PnPServices::CPnPInterfaceEvent::`vftable';
  *((_DWORD *)v22 + 4) = *((_DWORD *)this + 7);
  *(GUID *)(v22 + 20) = guidInvalid;
  CMostRecentEvents<PnPServices::CPnPDeviceEvent,20>::Add(v23, v22);
  v25 = PnPServices::CHandleNotif::HandleBroadcastHandleEvent(v24);
  CRefCounted::Release(v24);
  return v25;
}

```

## disassembly

```asm
0x1800016f0  mov     r11, rsp
0x1800016f3  mov     [r11+20h], rbx
0x1800016f7  push    rbp
0x1800016f8  push    rdi
0x1800016f9  push    r15
0x1800016fb  sub     rsp, 120h
0x180001702  mov     rbp, rcx
0x180001705  xor     r15d, r15d
0x180001708  mov     ecx, r15d
0x18000170b  mov     eax, [rbp+1Ch]
0x18000170e  cmp     eax, 8006h
0x180001713  jnz     loc_18000198E
0x180001719  movups  xmm0, xmmword ptr cs:GUID_IO_DEVICE_BECOMING_READY.Data1
0x180001720  mov     rdi, [rbp+20h]
0x180001724  mov     edx, r15d
0x180001727  movups  xmm1, xmmword ptr cs:GUID_IO_VOLUME_MOUNT.Data1
0x18000172e  movaps  [rsp+138h+var_108], xmm0
0x180001733  movups  xmm0, xmmword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data1
0x18000173a  movaps  [rsp+138h+var_F8], xmm1
0x18000173f  movups  xmm1, xmmword ptr cs:GUID_IO_VOLUME_DISMOUNT_FAILED.Data1
0x180001746  movaps  [rsp+138h+var_E8], xmm0
0x18000174b  movups  xmm0, xmmword ptr cs:GUID_IO_VOLUME_LOCK.Data1
0x180001752  movaps  [rsp+138h+var_D8], xmm1
0x180001757  movups  xmm1, xmmword ptr cs:GUID_IO_VOLUME_UNLOCK.Data1
0x18000175e  movaps  [rsp+138h+var_C8], xmm0
0x180001763  movups  xmm0, xmmword ptr cs:GUID_IO_VOLUME_LOCK_FAILED.Data1
0x18000176a  movaps  [rsp+138h+var_B8], xmm1
0x180001772  movups  xmm1, xmmword ptr cs:GUID_IO_MEDIA_ARRIVAL.Data1
0x180001779  movaps  [rsp+138h+var_A8], xmm0
0x180001781  movups  xmm0, xmmword ptr cs:GUID_IO_MEDIA_REMOVAL.Data1
0x180001788  movaps  [rsp+138h+var_98], xmm1
0x180001790  movups  xmm1, xmmword ptr cs:GUID_IO_VOLUME_CHANGE.Data1
0x180001797  movaps  [rsp+138h+var_88], xmm0
0x18000179f  movups  xmm0, xmmword ptr cs:GUID_IO_VOLUME_NAME_CHANGE.Data1
0x1800017a6  movaps  xmmword ptr [r11-78h], xmm1
0x1800017ab  movups  xmm1, xmmword ptr cs:GUID_IO_VOLUME_PREPARING_EJECT.Data1
0x1800017b2  movaps  xmmword ptr [r11-68h], xmm0
0x1800017b7  movups  xmm0, xmmword ptr cs:GUID_IO_VOLUME_BACKGROUND_FORMAT.Data1
0x1800017be  movaps  xmmword ptr [r11-58h], xmm1
0x1800017c3  movups  xmm1, xmmword ptr cs:GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data1
0x1800017ca  movaps  xmmword ptr [r11-48h], xmm0
0x1800017cf  movups  xmm0, xmmword ptr cs:GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE.Data1
0x1800017d6  movaps  xmmword ptr [r11-38h], xmm1
0x1800017db  movaps  xmmword ptr [r11-28h], xmm0
0x1800017e0  cmp     edx, 0Fh
0x1800017e3  jnb     loc_180001987
0x1800017e9  mov     eax, edx
0x1800017eb  lea     r8, [rsp+138h+var_108]
0x1800017f0  shl     rax, 4
0x1800017f4  add     r8, rax
0x1800017f7  mov     rax, [r8]
0x1800017fa  sub     rax, [rdi+20h]
0x1800017fe  jnz     short loc_180001808
0x180001800  mov     rax, [r8+8]
0x180001804  sub     rax, [rdi+28h]
0x180001808  test    rax, rax
0x18000180b  jz      short loc_180001811
0x18000180d  inc     edx
0x18000180f  jmp     short loc_1800017E0
0x180001811  mov     ecx, 38h ; '8'; Size
0x180001816  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000181b  mov     rbx, rax
0x18000181e  test    rax, rax
0x180001821  jz      loc_180001A0E
0x180001827  mov     [rsp+138h+arg_8], rsi
0x18000182f  mov     edx, r15d
0x180001832  mov     [rsp+138h+arg_10], r14
0x18000183a  mov     [rax+0Ch], r15
0x18000183e  mov     [rax+14h], r15
0x180001842  mov     [rax+1Ch], r15
0x180001846  mov     [rax+24h], r15
0x18000184a  mov     [rax+2Ch], r15
0x18000184e  mov     [rax+34h], r15d
0x180001852  mov     dword ptr [rax+8], 1
0x180001859  lea     rax, ??_7CPnPInterfaceEvent@PnPServices@@6B@; const PnPServices::CPnPInterfaceEvent::`vftable'
0x180001860  mov     [rbx], rax
0x180001863  mov     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data1
0x18000186a  sub     rax, [rdi+20h]
0x18000186e  jnz     short loc_18000187B
0x180001870  mov     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data4
0x180001877  sub     rax, [rdi+28h]
0x18000187b  mov     esi, 0FFFFFFFFh
0x180001880  test    rax, rax
0x180001883  jnz     short loc_1800018BD
0x180001885  cmp     dword ptr [rdi], 48h ; 'H'
0x180001888  jb      short loc_1800018BD
0x18000188a  cmp     dword ptr [rdi+34h], 1
0x18000188e  lea     rax, [rdi+34h]
0x180001892  jnz     short loc_1800018BD
0x180001894  mov     edx, [rax+8]
0x180001897  lea     r8, String2; "RAW"
0x18000189e  mov     ecx, [rax+0Ch]
0x1800018a1  mov     r9d, esi; cchCount2
0x1800018a4  shr     edx, 1; cchCount1
0x1800018a6  add     rcx, rax; lpString1
0x1800018a9  mov     [rsp+138h+bIgnoreCase], r15d; bIgnoreCase
0x1800018ae  call    cs:__imp_CompareStringOrdinal
0x1800018b4  cmp     eax, 2
0x1800018b7  mov     edx, r15d
0x1800018ba  setz    dl
0x1800018bd  mov     rcx, [rdi+18h]
0x1800018c1  mov     eax, [rbp+1Ch]
0x1800018c4  mov     [rbx+10h], eax
0x1800018c7  movups  xmm0, xmmword ptr [rdi+20h]
0x1800018cb  mov     [rbx+28h], rcx
0x1800018cf  mov     [rbx+30h], edx
0x1800018d2  movups  xmmword ptr [rbx+14h], xmm0
0x1800018d6  mov     rdi, cs:?g_pmrePnPDeviceEvents@PnPServices@@3PEAV?$CMostRecentEvents@VCPnPDeviceEvent@PnPServices@@$0BE@@@EA; CMostRecentEvents<PnPServices::CPnPDeviceEvent,20> * PnPServices::g_pmrePnPDeviceEvents
0x1800018dd  lock inc dword ptr [rbx+8]
0x1800018e1  lea     rbp, [rdi+0A8h]
0x1800018e8  lea     r14, [rbp+8]
0x1800018ec  test    rbp, rbp
0x1800018ef  mov     rcx, r14
0x1800018f2  cmovz   rcx, r15; lpCriticalSection
0x1800018f6  call    cs:__imp_EnterCriticalSection
0x1800018fc  mov     eax, [rdi]
0x1800018fe  mov     rcx, [rdi+rax*8+8]
0x180001903  test    rcx, rcx
0x180001906  jz      short loc_180001924
0x180001908  mov     eax, esi
0x18000190a  lock xadd [rcx+8], eax
0x18000190f  cmp     eax, 1
0x180001912  jnz     short loc_180001924
0x180001914  mov     rax, [rcx]
0x180001917  mov     edx, 1
0x18000191c  mov     rax, [rax]
0x18000191f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001924  mov     eax, [rdi]
0x180001926  mov     [rdi+rax*8+8], rbx
0x18000192b  inc     dword ptr [rdi]
0x18000192d  cmp     dword ptr [rdi], 14h
0x180001930  jnz     short loc_180001935
0x180001932  mov     [rdi], r15d
0x180001935  test    rbp, rbp
0x180001938  mov     rcx, r15
0x18000193b  cmovnz  rcx, r14; lpCriticalSection
0x18000193f  call    cs:__imp_LeaveCriticalSection
0x180001945  mov     rcx, rbx; struct PnPServices::CPnPDeviceEvent *
0x180001948  call    ?HandleBroadcastHandleEvent@CHandleNotif@PnPServices@@SAJPEAVCPnPDeviceEvent@2@@Z; PnPServices::CHandleNotif::HandleBroadcastHandleEvent(PnPServices::CPnPDeviceEvent *)
0x18000194d  mov     edi, eax
0x18000194f  lock xadd [rbx+8], esi
0x180001954  mov     r14, [rsp+138h+arg_10]
0x18000195c  cmp     esi, 1
0x18000195f  mov     rsi, [rsp+138h+arg_8]
0x180001967  jnz     loc_180001A13
0x18000196d  mov     rcx, [rbx]
0x180001970  mov     edx, 1
0x180001975  mov     rax, [rcx]
0x180001978  mov     rcx, rbx
0x18000197b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001980  mov     eax, edi
0x180001982  jmp     loc_180001A13
0x180001987  mov     eax, ecx
0x180001989  jmp     loc_180001A13
0x18000198e  sub     eax, 8001h
0x180001993  jz      short loc_1800019A4
0x180001995  sub     eax, 1
0x180001998  jz      short loc_1800019A4
0x18000199a  sub     eax, 1
0x18000199d  jz      short loc_1800019A4
0x18000199f  cmp     eax, 1
0x1800019a2  jnz     short loc_180001987
0x1800019a4  mov     ecx, 38h ; '8'; Size
0x1800019a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800019ae  mov     rdi, rax
0x1800019b1  test    rax, rax
0x1800019b4  jz      short loc_180001A0E
0x1800019b6  mov     [rax+0Ch], r15
0x1800019ba  mov     rdx, rdi
0x1800019bd  mov     [rax+14h], r15
0x1800019c1  mov     [rax+1Ch], r15
0x1800019c5  mov     [rax+24h], r15
0x1800019c9  mov     [rax+2Ch], r15
0x1800019cd  mov     [rax+34h], r15d
0x1800019d1  mov     dword ptr [rax+8], 1
0x1800019d8  lea     rax, ??_7CPnPInterfaceEvent@PnPServices@@6B@; const PnPServices::CPnPInterfaceEvent::`vftable'
0x1800019df  mov     [rdi], rax
0x1800019e2  mov     eax, [rbp+1Ch]
0x1800019e5  mov     [rdi+10h], eax
0x1800019e8  movups  xmm0, xmmword ptr cs:?guidInvalid@@3U_GUID@@B.Data1; _GUID const guidInvalid ...
0x1800019ef  movups  xmmword ptr [rdi+14h], xmm0
0x1800019f3  call    ?Add@?$CMostRecentEvents@VCPnPDeviceEvent@PnPServices@@$0BE@@@QEAAJPEAVCPnPDeviceEvent@PnPServices@@@Z; CMostRecentEvents<PnPServices::CPnPDeviceEvent,20>::Add(PnPServices::CPnPDeviceEvent *)
0x1800019f8  mov     rcx, rdi; struct PnPServices::CPnPDeviceEvent *
0x1800019fb  call    ?HandleBroadcastHandleEvent@CHandleNotif@PnPServices@@SAJPEAVCPnPDeviceEvent@2@@Z; PnPServices::CHandleNotif::HandleBroadcastHandleEvent(PnPServices::CPnPDeviceEvent *)
0x180001a00  mov     rcx, rdi; this
0x180001a03  mov     ebx, eax
0x180001a05  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180001a0a  mov     eax, ebx
0x180001a0c  jmp     short loc_180001A13
0x180001a0e  mov     eax, 8007000Eh
0x180001a13  mov     rbx, [rsp+138h+arg_18]
0x180001a1b  add     rsp, 120h
0x180001a22  pop     r15
0x180001a24  pop     rdi
0x180001a25  pop     rbp
0x180001a26  retn
```
