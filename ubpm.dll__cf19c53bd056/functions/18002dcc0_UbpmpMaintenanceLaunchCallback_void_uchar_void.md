# UbpmpMaintenanceLaunchCallback(void *,uchar,void *)

- ea: `0x18002dcc0`
- end: `0x18002e0c1`
- name: `?UbpmpMaintenanceLaunchCallback@@YAXPEAXE0@Z`
- size: `1025`
- prototype: `void __fastcall(void *, unsigned __int8, void *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001d70`
- `0x180001db8`
- `0x180003f80`
- `0x18000a500`
- `0x18000a6e0`
- `0x18000aba0`
- `0x18000f9a0`
- `0x180015e10`
- `0x180018538`
- `0x180019d90`
- `0x180024600`
- `0x180029854`
- `0x18002dcc0`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18002de01`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002de62`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002de6b`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002df16`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002de01`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002de62`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002de6b`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002df16`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002dded`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002de3a`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002dded`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002de3a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002dd76`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002ddc0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002dd76`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002ddc0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002dd9a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002dd9a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e082`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e082`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002e094`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002e094`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002de8a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002de8a`

## pseudocode

```c
void __fastcall UbpmpMaintenanceLaunchCallback(void *a1, unsigned __int8 a2, void *a3)
{
  unsigned __int8 v3; // bl
  __int64 v4; // rcx
  int v5; // r12d
  char v6; // r13
  int v7; // esi
  _UNKNOWN **v8; // r15
  const FILETIME *v9; // r14
  const FILETIME **v10; // rax
  const FILETIME **v11; // rdi
  _QWORD *v12; // rsi
  const FILETIME *i; // rbx
  const FILETIME ***v14; // rax
  __int128 *v15; // rsi
  __int64 **v16; // rax
  __int128 *v17; // rcx
  __int128 **v18; // r8
  __int128 **v19; // rdx
  __int128 *v20; // rax
  __int128 *v21; // rbx
  __int128 *v22; // rdi
  __int128 *v23; // rcx
  __int128 **v24; // r8
  __int128 **v25; // rdx
  __int128 *v26; // rax
  __int128 *v27; // rbx
  DWORD v28; // ebx
  __int16 v29; // [rsp+30h] [rbp-D0h] BYREF
  int v30; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v31; // [rsp+38h] [rbp-C8h] BYREF
  int v32; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v33[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+70h] [rbp-90h]
  _BYTE v35[144]; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v36; // [rsp+110h] [rbp+10h] BYREF
  __int16 *v37; // [rsp+130h] [rbp+30h]
  __int64 v38; // [rsp+138h] [rbp+38h]
  int *v39; // [rsp+140h] [rbp+40h]
  __int64 v40; // [rsp+148h] [rbp+48h]
  int *v41; // [rsp+150h] [rbp+50h]
  __int64 v42; // [rsp+158h] [rbp+58h]

  v3 = a2;
  LOBYTE(v29) = a2;
  memset_0(v35, 0, 0x88u);
  v5 = 0;
  v34 = 0;
  v30 = 0;
  v31 = 0;
  memset(v33, 0, sizeof(v33));
  if ( (unsigned int)dword_18004C0F0 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v4,
      (unsigned __int8 *)byte_180043FCB);
  *((_QWORD *)&v31 + 1) = &v31;
  *(_QWORD *)&v31 = &v31;
  if ( (v3 & 4) != 0 )
  {
    v6 = 0;
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_MaintenanceLaunchLock);
    byte_18004CB33 = 0;
    dword_18004CEE8 = 0;
    RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
    v7 = 1235;
  }
  else
  {
    v6 = 1;
    UbpmUtilsStartLockTracking((struct _CEM_LOCK_TRACKER *)v35);
    Sleep(0x3E8u);
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_MaintenanceLaunchLock);
    byte_18004CB33 = 0;
    dword_18004CEE8 = 0;
    RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
    UbpmpAcquireListLockShared();
    v8 = (_UNKNOWN **)g_leConsumerListHead;
    if ( g_leConsumerListHead != (_UNKNOWN *)&g_leConsumerListHead )
    {
      while ( 1 )
      {
        v9 = (const FILETIME *)(v8 - 1);
        RtlAcquireSRWLockShared(v8 + 5);
        if ( !*((_QWORD *)v8[2] + 6) || (unsigned int)UbpmpTakeConsumerReference(v8 - 1) )
        {
          RtlReleaseSRWLockShared(v8 + 5);
        }
        else
        {
          v10 = (const FILETIME **)UbpmAlloc(0x20u);
          v11 = v10;
          if ( !v10 )
          {
            v7 = 14;
            RtlReleaseSRWLockShared(v8 + 5);
            UbpmpReleaseListLockShared();
            v5 = v30;
            goto LABEL_31;
          }
          v10[2] = v9;
          RtlAcquireSRWLockShared(&v9[26]);
          v12 = v11 + 3;
          if ( !(unsigned int)UbpmStatsOperation((__int64)(v8 - 1), 0, v33) )
            *v12 = *(_QWORD *)((char *)v33 + 12);
          RtlReleaseSRWLockShared(&v9[26]);
          RtlReleaseSRWLockShared(v8 + 5);
          if ( *((_DWORD *)v11 + 7) && *(_DWORD *)v12 )
          {
            for ( i = (const FILETIME *)v31; ; i = (const FILETIME *)*i )
            {
              if ( i == (const FILETIME *)&v31 )
                goto LABEL_18;
              if ( CompareFileTime((const FILETIME *)v11 + 3, i + 3) < 0 )
                break;
            }
            v16 = (__int64 **)i[1];
            if ( *v16 != (__int64 *)i )
LABEL_45:
              __fastfail(3u);
            *v11 = i;
            v11[1] = (const FILETIME *)v16;
            *v16 = (__int64 *)v11;
            i[1] = (const FILETIME)v11;
          }
          else
          {
LABEL_18:
            v14 = (const FILETIME ***)*((_QWORD *)&v31 + 1);
            if ( **((__int128 ***)&v31 + 1) != &v31 )
              goto LABEL_45;
            v11[1] = (const FILETIME *)*((_QWORD *)&v31 + 1);
            *v11 = (const FILETIME *)&v31;
            *v14 = v11;
            *((_QWORD *)&v31 + 1) = v11;
          }
        }
        v8 = (_UNKNOWN **)*v8;
        if ( v8 == &g_leConsumerListHead )
        {
          v5 = v30;
          break;
        }
      }
    }
    UbpmpReleaseListLockShared();
    v15 = (__int128 *)v31;
    while ( v15 != &v31 )
    {
      v17 = *(__int128 **)v15;
      if ( *(__int128 **)(*(_QWORD *)v15 + 8LL) != v15 )
        goto LABEL_45;
      v18 = (__int128 **)v15 + 1;
      v19 = (__int128 **)*((_QWORD *)v15 + 1);
      if ( *v19 != v15 )
        goto LABEL_45;
      *v19 = v17;
      v20 = v15;
      *((_QWORD *)v17 + 1) = v19;
      v21 = v15;
      *v18 = v15;
      v15 = v17;
      LOBYTE(v18) = 1;
      *(_QWORD *)v20 = v20;
      UbpmRunConsumerQueuedActions(*((_QWORD *)v20 + 2), 3, v18);
      UbpmpCloseTriggerConsumer(*((_QWORD *)v21 + 2));
      UBPM_MIDL_user_free(v21);
      ++v5;
    }
    v7 = 0;
LABEL_31:
    v3 = v29;
  }
  if ( (unsigned int)dword_18004C0F0 > 4 )
  {
    v29 = v3;
    v30 = v7;
    v41 = &v30;
    v32 = v5;
    v39 = &v32;
    v42 = 4;
    v37 = &v29;
    v40 = 4;
    v38 = 2;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18004C0F0, (unsigned __int8 *)byte_18004404B, 0, 0, 5u, &v36);
  }
  v22 = (__int128 *)v31;
  while ( v22 != &v31 )
  {
    v23 = *(__int128 **)v22;
    if ( *(__int128 **)(*(_QWORD *)v22 + 8LL) != v22 )
      goto LABEL_45;
    v24 = (__int128 **)v22 + 1;
    v25 = (__int128 **)*((_QWORD *)v22 + 1);
    if ( *v25 != v22 )
      goto LABEL_45;
    v26 = v22;
    *v25 = v23;
    *((_QWORD *)v23 + 1) = v25;
    v27 = v22;
    v22 = v23;
    *v24 = v26;
    *(_QWORD *)v26 = v26;
    UbpmpCloseTriggerConsumer(*((_QWORD *)v26 + 2));
    UBPM_MIDL_user_free(v27);
  }
  if ( v6 )
  {
    v28 = UbpmpLockTrackerId;
    if ( UbpmpLockTrackerId != -1 )
    {
      if ( *(_QWORD *)TlsGetValue(UbpmpLockTrackerId) )
        __int2c();
      TlsSetValue(v28, 0);
    }
  }
}

```

## disassembly

```asm
0x18002dcc0  push    rbp
0x18002dcc2  push    rbx
0x18002dcc3  push    rsi
0x18002dcc4  push    rdi
0x18002dcc5  push    r12
0x18002dcc7  push    r13
0x18002dcc9  push    r14
0x18002dccb  push    r15
0x18002dccd  lea     rbp, [rsp-78h]
0x18002dcd2  sub     rsp, 178h
0x18002dcd9  mov     rax, cs:__security_cookie
0x18002dce0  xor     rax, rsp
0x18002dce3  mov     [rbp+0B0h+var_50], rax
0x18002dce7  mov     bl, dl
0x18002dce9  mov     byte ptr [rsp+1B0h+var_180], dl
0x18002dced  xor     edx, edx; Val
0x18002dcef  lea     rcx, [rbp+0B0h+var_130]; void *
0x18002dcf3  mov     r8d, 88h; Size
0x18002dcf9  call    memset_0
0x18002dcfe  xor     eax, eax
0x18002dd00  xor     r12d, r12d
0x18002dd03  xorps   xmm1, xmm1
0x18002dd06  mov     [rsp+1B0h+var_140], eax
0x18002dd0a  mov     eax, cs:dword_18004C0F0
0x18002dd10  xor     edi, edi
0x18002dd12  mov     [rsp+1B0h+var_17C], r12d
0x18002dd17  xorps   xmm0, xmm0
0x18002dd1a  movups  [rsp+1B0h+var_178], xmm0
0x18002dd1f  movups  [rsp+1B0h+var_160], xmm1
0x18002dd24  movups  [rsp+1B0h+var_150], xmm1
0x18002dd29  cmp     eax, 4
0x18002dd2c  jbe     short loc_18002DD3A
0x18002dd2e  lea     rdx, byte_180043FCB
0x18002dd35  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18002dd3a  lea     rax, [rsp+1B0h+var_178]
0x18002dd3f  mov     qword ptr [rsp+1B0h+var_178+8], rax
0x18002dd44  lea     rax, [rsp+1B0h+var_178]
0x18002dd49  mov     qword ptr [rsp+1B0h+var_178], rax
0x18002dd4e  test    bl, 4
0x18002dd51  jz      short loc_18002DD86
0x18002dd53  lea     rcx, g_MaintenanceLaunchLock; struct _UBPM_SRWLOCK *
0x18002dd5a  xor     r13b, r13b
0x18002dd5d  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18002dd62  lea     rcx, g_MaintenanceLaunchLock
0x18002dd69  mov     cs:byte_18004CB33, dil
0x18002dd70  mov     cs:dword_18004CEE8, edi
0x18002dd76  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002dd7c  mov     esi, 4D3h
0x18002dd81  jmp     loc_18002DF90
0x18002dd86  lea     rcx, [rbp+0B0h+var_130]; lpTlsValue
0x18002dd8a  mov     r13d, 1
0x18002dd90  call    ?UbpmUtilsStartLockTracking@@YAXPEAU_CEM_LOCK_TRACKER@@@Z; UbpmUtilsStartLockTracking(_CEM_LOCK_TRACKER *)
0x18002dd95  mov     ecx, 3E8h; dwMilliseconds
0x18002dd9a  call    cs:__imp_Sleep
0x18002dda0  lea     rcx, g_MaintenanceLaunchLock; struct _UBPM_SRWLOCK *
0x18002dda7  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18002ddac  lea     rcx, g_MaintenanceLaunchLock
0x18002ddb3  mov     cs:byte_18004CB33, dil
0x18002ddba  mov     cs:dword_18004CEE8, edi
0x18002ddc0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002ddc6  call    UbpmpAcquireListLockShared
0x18002ddcb  mov     r15, cs:g_leConsumerListHead
0x18002ddd2  lea     rax, g_leConsumerListHead
0x18002ddd9  cmp     r15, rax
0x18002dddc  jz      loc_18002DEE2
0x18002dde2  lea     r14, [r15-8]
0x18002dde6  lea     rbx, [r14+30h]
0x18002ddea  mov     rcx, rbx
0x18002dded  call    cs:__imp_RtlAcquireSRWLockShared
0x18002ddf3  mov     rax, [r14+18h]
0x18002ddf7  cmp     qword ptr [rax+30h], 0
0x18002ddfc  jnz     short loc_18002DE0C
0x18002ddfe  mov     rcx, rbx
0x18002de01  call    cs:__imp_RtlReleaseSRWLockShared
0x18002de07  jmp     loc_18002DECA
0x18002de0c  mov     rcx, r14
0x18002de0f  call    UbpmpTakeConsumerReference
0x18002de14  test    eax, eax
0x18002de16  jnz     short loc_18002DDFE
0x18002de18  lea     ecx, [rax+20h]; Size
0x18002de1b  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002de20  mov     rdi, rax
0x18002de23  test    rax, rax
0x18002de26  jz      loc_18002DF0E
0x18002de2c  lea     r12, [r14+0D0h]
0x18002de33  mov     [rax+10h], r14
0x18002de37  mov     rcx, r12
0x18002de3a  call    cs:__imp_RtlAcquireSRWLockShared
0x18002de40  lea     r8, [rsp+1B0h+var_160]
0x18002de45  xor     edx, edx
0x18002de47  mov     rcx, r14
0x18002de4a  lea     rsi, [rdi+18h]
0x18002de4e  call    UbpmStatsOperation
0x18002de53  test    eax, eax
0x18002de55  jnz     short loc_18002DE5F
0x18002de57  mov     rax, qword ptr [rsp+1B0h+var_160+0Ch]
0x18002de5c  mov     [rsi], rax
0x18002de5f  mov     rcx, r12
0x18002de62  call    cs:__imp_RtlReleaseSRWLockShared
0x18002de68  mov     rcx, rbx
0x18002de6b  call    cs:__imp_RtlReleaseSRWLockShared
0x18002de71  cmp     dword ptr [rsi+4], 0
0x18002de75  jz      short loc_18002DEA1
0x18002de77  cmp     dword ptr [rsi], 0
0x18002de7a  jz      short loc_18002DEA1
0x18002de7c  mov     rbx, qword ptr [rsp+1B0h+var_178]
0x18002de81  jmp     short loc_18002DE97
0x18002de83  lea     rdx, [rbx+18h]; lpFileTime2
0x18002de87  mov     rcx, rsi; lpFileTime1
0x18002de8a  call    cs:__imp_CompareFileTime
0x18002de90  test    eax, eax
0x18002de92  js      short loc_18002DEF1
0x18002de94  mov     rbx, [rbx]
0x18002de97  lea     rax, [rsp+1B0h+var_178]
0x18002de9c  cmp     rbx, rax
0x18002de9f  jnz     short loc_18002DE83
0x18002dea1  mov     rax, qword ptr [rsp+1B0h+var_178+8]
0x18002dea6  lea     rcx, [rsp+1B0h+var_178]
0x18002deab  cmp     [rax], rcx
0x18002deae  jnz     loc_18002E0BA
0x18002deb4  mov     [rdi+8], rax
0x18002deb8  lea     rcx, [rsp+1B0h+var_178]
0x18002debd  mov     [rdi], rcx
0x18002dec0  mov     [rax], rdi
0x18002dec3  mov     qword ptr [rsp+1B0h+var_178+8], rdi
0x18002dec8  xor     edi, edi
0x18002deca  mov     r15, [r15]
0x18002decd  lea     rax, g_leConsumerListHead
0x18002ded4  cmp     r15, rax
0x18002ded7  jnz     loc_18002DDE2
0x18002dedd  mov     r12d, [rsp+1B0h+var_17C]
0x18002dee2  call    UbpmpReleaseListLockShared
0x18002dee7  mov     rsi, qword ptr [rsp+1B0h+var_178]
0x18002deec  jmp     loc_18002DF80
0x18002def1  mov     rax, [rbx+8]
0x18002def5  cmp     [rax], rbx
0x18002def8  jnz     loc_18002E0BA
0x18002defe  mov     [rdi], rbx
0x18002df01  mov     [rdi+8], rax
0x18002df05  mov     [rax], rdi
0x18002df08  mov     [rbx+8], rdi
0x18002df0c  jmp     short loc_18002DEC8
0x18002df0e  mov     rcx, rbx
0x18002df11  mov     esi, 0Eh
0x18002df16  call    cs:__imp_RtlReleaseSRWLockShared
0x18002df1c  call    UbpmpReleaseListLockShared
0x18002df21  mov     r12d, [rsp+1B0h+var_17C]
0x18002df26  jmp     short loc_18002DF8C
0x18002df28  mov     rcx, [rsi]
0x18002df2b  cmp     [rcx+8], rsi
0x18002df2f  jnz     loc_18002E0BA
0x18002df35  lea     r8, [rsi+8]
0x18002df39  mov     rdx, [r8]
0x18002df3c  cmp     [rdx], rsi
0x18002df3f  jnz     loc_18002E0BA
0x18002df45  mov     [rdx], rcx
0x18002df48  mov     rax, rsi
0x18002df4b  mov     [rcx+8], rdx
0x18002df4f  mov     rbx, rsi
0x18002df52  mov     [r8], rax
0x18002df55  mov     rsi, rcx
0x18002df58  mov     r8b, r13b
0x18002df5b  mov     edx, 3
0x18002df60  mov     [rax], rax
0x18002df63  mov     rcx, [rax+10h]
0x18002df67  call    UbpmRunConsumerQueuedActions
0x18002df6c  mov     rcx, [rbx+10h]
0x18002df70  call    UbpmpCloseTriggerConsumer
0x18002df75  mov     rcx, rbx
0x18002df78  call    UBPM_MIDL_user_free
0x18002df7d  add     r12d, r13d
0x18002df80  lea     rax, [rsp+1B0h+var_178]
0x18002df85  cmp     rsi, rax
0x18002df88  jnz     short loc_18002DF28
0x18002df8a  xor     esi, esi
0x18002df8c  mov     bl, byte ptr [rsp+1B0h+var_180]
0x18002df90  mov     eax, cs:dword_18004C0F0
0x18002df96  cmp     eax, 4
0x18002df99  jbe     short loc_18002E009
0x18002df9b  movzx   eax, bl
0x18002df9e  lea     rdx, byte_18004404B
0x18002dfa5  mov     [rsp+1B0h+var_180], ax
0x18002dfaa  lea     rcx, dword_18004C0F0
0x18002dfb1  lea     rax, [rsp+1B0h+var_17C]
0x18002dfb6  mov     [rsp+1B0h+var_17C], esi
0x18002dfba  mov     [rbp+0B0h+var_60], rax
0x18002dfbe  xor     r9d, r9d
0x18002dfc1  lea     rax, [rsp+1B0h+var_168]
0x18002dfc6  mov     [rsp+1B0h+var_168], r12d
0x18002dfcb  mov     [rbp+0B0h+var_70], rax
0x18002dfcf  xor     r8d, r8d
0x18002dfd2  lea     rax, [rsp+1B0h+var_180]
0x18002dfd7  mov     [rbp+0B0h+var_58], 4
0x18002dfdf  mov     [rbp+0B0h+var_80], rax
0x18002dfe3  lea     rax, [rbp+0B0h+var_A0]
0x18002dfe7  mov     [rsp+1B0h+var_188], rax
0x18002dfec  mov     [rsp+1B0h+var_190], 5
0x18002dff4  mov     [rbp+0B0h+var_68], 4
0x18002dffc  mov     [rbp+0B0h+var_78], 2
0x18002e004  call    _tlgWriteTransfer_EventWriteTransfer
0x18002e009  test    rdi, rdi
0x18002e00c  jz      short loc_18002E01F
0x18002e00e  mov     rcx, [rdi+10h]
0x18002e012  call    UbpmpCloseTriggerConsumer
0x18002e017  mov     rcx, rdi
0x18002e01a  call    UBPM_MIDL_user_free
0x18002e01f  mov     rdi, qword ptr [rsp+1B0h+var_178]
0x18002e024  jmp     short loc_18002E066
0x18002e026  mov     rcx, [rdi]
0x18002e029  cmp     [rcx+8], rdi
0x18002e02d  jnz     loc_18002E0BA
0x18002e033  lea     r8, [rdi+8]
0x18002e037  mov     rdx, [r8]
0x18002e03a  cmp     [rdx], rdi
0x18002e03d  jnz     short loc_18002E0BA
0x18002e03f  mov     rax, rdi
0x18002e042  mov     [rdx], rcx
0x18002e045  mov     [rcx+8], rdx
0x18002e049  mov     rbx, rdi
0x18002e04c  mov     rdi, rcx
0x18002e04f  mov     [r8], rax
0x18002e052  mov     [rax], rax
0x18002e055  mov     rcx, [rax+10h]
0x18002e059  call    UbpmpCloseTriggerConsumer
0x18002e05e  mov     rcx, rbx
0x18002e061  call    UBPM_MIDL_user_free
0x18002e066  lea     rax, [rsp+1B0h+var_178]
0x18002e06b  cmp     rdi, rax
0x18002e06e  jnz     short loc_18002E026
0x18002e070  test    r13b, r13b
0x18002e073  jz      short loc_18002E09A
0x18002e075  mov     ebx, cs:UbpmpLockTrackerId
0x18002e07b  cmp     ebx, 0FFFFFFFFh
0x18002e07e  jz      short loc_18002E09A
0x18002e080  mov     ecx, ebx; dwTlsIndex
0x18002e082  call    cs:__imp_TlsGetValue
0x18002e088  cmp     qword ptr [rax], 0
0x18002e08c  jz      short loc_18002E090
0x18002e08e  int     2Ch; Windows NT - assertion failure
0x18002e090  xor     edx, edx; lpTlsValue
0x18002e092  mov     ecx, ebx; dwTlsIndex
0x18002e094  call    cs:__imp_TlsSetValue
0x18002e09a  mov     rcx, [rbp+0B0h+var_50]
0x18002e09e  xor     rcx, rsp; StackCookie
0x18002e0a1  call    __security_check_cookie
0x18002e0a6  add     rsp, 178h
0x18002e0ad  pop     r15
0x18002e0af  pop     r14
0x18002e0b1  pop     r13
0x18002e0b3  pop     r12
0x18002e0b5  pop     rdi
0x18002e0b6  pop     rsi
0x18002e0b7  pop     rbx
0x18002e0b8  pop     rbp
0x18002e0b9  retn
0x18002e0ba  mov     ecx, 3
0x18002e0bf  int     29h; Win8: RtlFailFast(ecx)
```
