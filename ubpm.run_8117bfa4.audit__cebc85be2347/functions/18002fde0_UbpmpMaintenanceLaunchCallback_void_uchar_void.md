# UbpmpMaintenanceLaunchCallback(void *,uchar,void *)

- ea: `0x18002fde0`
- end: `0x18003022e`
- name: `?UbpmpMaintenanceLaunchCallback@@YAXPEAXE0@Z`
- size: `1102`
- prototype: `void __fastcall(void *, unsigned __int8, void *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002c70`
- `0x180002cc4`
- `0x180004410`
- `0x18000e0a8`
- `0x18000fbf0`
- `0x1800101a0`
- `0x1800103c0`
- `0x180012950`
- `0x1800150c0`
- `0x1800182a0`
- `0x180025d50`
- `0x18002b854`
- `0x18002fde0`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18002ff39`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002ffa6`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002ffb5`
- `ntdll!RtlReleaseSRWLockShared` at `0x18003006c`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002ff39`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002ffa6`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002ffb5`
- `ntdll!RtlReleaseSRWLockShared` at `0x18003006c`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002ff1f`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002ff78`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002ff1f`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002ff78`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002fe96`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002feec`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002fe96`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002feec`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002fec0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002fec0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800301e2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800301e2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800301fa`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800301fa`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002ffda`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002ffda`

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
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int128 *v25; // rdi
  __int128 *v26; // rcx
  __int128 **v27; // r8
  __int128 **v28; // rdx
  __int128 *v29; // rax
  __int128 *v30; // rbx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  DWORD v34; // ebx
  __int16 v35; // [rsp+30h] [rbp-D0h] BYREF
  int v36; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v37; // [rsp+38h] [rbp-C8h] BYREF
  int v38; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v39[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v40; // [rsp+70h] [rbp-90h]
  _BYTE v41[144]; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v42; // [rsp+110h] [rbp+10h] BYREF
  __int16 *v43; // [rsp+130h] [rbp+30h]
  __int64 v44; // [rsp+138h] [rbp+38h]
  int *v45; // [rsp+140h] [rbp+40h]
  __int64 v46; // [rsp+148h] [rbp+48h]
  int *v47; // [rsp+150h] [rbp+50h]
  __int64 v48; // [rsp+158h] [rbp+58h]

  v3 = a2;
  LOBYTE(v35) = a2;
  memset_0(v41, 0, 0x88u);
  v5 = 0;
  v40 = 0;
  v36 = 0;
  v37 = 0;
  memset(v39, 0, sizeof(v39));
  if ( (unsigned int)dword_18004F0F0 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v4,
      (unsigned __int8 *)byte_180047033);
  *((_QWORD *)&v37 + 1) = &v37;
  *(_QWORD *)&v37 = &v37;
  if ( (v3 & 4) != 0 )
  {
    v6 = 0;
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_MaintenanceLaunchLock);
    byte_18004FC33 = 0;
    dword_18004FFE8 = 0;
    RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
    v7 = 1235;
  }
  else
  {
    v6 = 1;
    UbpmUtilsStartLockTracking((struct _CEM_LOCK_TRACKER *)v41);
    Sleep(0x3E8u);
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_MaintenanceLaunchLock);
    byte_18004FC33 = 0;
    dword_18004FFE8 = 0;
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
            v5 = v36;
            goto LABEL_31;
          }
          v10[2] = v9;
          RtlAcquireSRWLockShared(&v9[26]);
          v12 = v11 + 3;
          if ( !(unsigned int)UbpmStatsOperation((__int64)(v8 - 1), 0, v39) )
            *v12 = *(_QWORD *)((char *)v39 + 12);
          RtlReleaseSRWLockShared(&v9[26]);
          RtlReleaseSRWLockShared(v8 + 5);
          if ( *((_DWORD *)v11 + 7) && *(_DWORD *)v12 )
          {
            for ( i = (const FILETIME *)v37; ; i = (const FILETIME *)*i )
            {
              if ( i == (const FILETIME *)&v37 )
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
            v14 = (const FILETIME ***)*((_QWORD *)&v37 + 1);
            if ( **((__int128 ***)&v37 + 1) != &v37 )
              goto LABEL_45;
            v11[1] = (const FILETIME *)*((_QWORD *)&v37 + 1);
            *v11 = (const FILETIME *)&v37;
            *v14 = v11;
            *((_QWORD *)&v37 + 1) = v11;
          }
        }
        v8 = (_UNKNOWN **)*v8;
        if ( v8 == &g_leConsumerListHead )
        {
          v5 = v36;
          break;
        }
      }
    }
    UbpmpReleaseListLockShared();
    v15 = (__int128 *)v37;
    while ( v15 != &v37 )
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
      UBPM_MIDL_user_free(v21, v22, v23, v24);
      ++v5;
    }
    v7 = 0;
LABEL_31:
    v3 = v35;
  }
  if ( (unsigned int)dword_18004F0F0 > 4 )
  {
    v35 = v3;
    v36 = v7;
    v47 = &v36;
    v38 = v5;
    v45 = &v38;
    v48 = 4;
    v43 = &v35;
    v46 = 4;
    v44 = 2;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18004F0F0, (unsigned __int8 *)byte_1800470B3, 0, 0, 5u, &v42);
  }
  v25 = (__int128 *)v37;
  while ( v25 != &v37 )
  {
    v26 = *(__int128 **)v25;
    if ( *(__int128 **)(*(_QWORD *)v25 + 8LL) != v25 )
      goto LABEL_45;
    v27 = (__int128 **)v25 + 1;
    v28 = (__int128 **)*((_QWORD *)v25 + 1);
    if ( *v28 != v25 )
      goto LABEL_45;
    v29 = v25;
    *v28 = v26;
    *((_QWORD *)v26 + 1) = v28;
    v30 = v25;
    v25 = v26;
    *v27 = v29;
    *(_QWORD *)v29 = v29;
    UbpmpCloseTriggerConsumer(*((_QWORD *)v29 + 2));
    UBPM_MIDL_user_free(v30, v31, v32, v33);
  }
  if ( v6 )
  {
    v34 = UbpmpLockTrackerId;
    if ( UbpmpLockTrackerId != -1 )
    {
      if ( *(_QWORD *)TlsGetValue(UbpmpLockTrackerId) )
        __int2c();
      TlsSetValue(v34, 0);
    }
  }
}

```

## disassembly

```asm
0x18002fde0  push    rbp
0x18002fde2  push    rbx
0x18002fde3  push    rsi
0x18002fde4  push    rdi
0x18002fde5  push    r12
0x18002fde7  push    r13
0x18002fde9  push    r14
0x18002fdeb  push    r15
0x18002fded  lea     rbp, [rsp-78h]
0x18002fdf2  sub     rsp, 178h
0x18002fdf9  mov     rax, cs:__security_cookie
0x18002fe00  xor     rax, rsp
0x18002fe03  mov     [rbp+0B0h+var_50], rax
0x18002fe07  mov     bl, dl
0x18002fe09  mov     byte ptr [rsp+1B0h+var_180], dl
0x18002fe0d  xor     edx, edx; Val
0x18002fe0f  lea     rcx, [rbp+0B0h+var_130]; void *
0x18002fe13  mov     r8d, 88h; Size
0x18002fe19  call    memset_0
0x18002fe1e  xor     eax, eax
0x18002fe20  xor     r12d, r12d
0x18002fe23  xorps   xmm1, xmm1
0x18002fe26  mov     [rsp+1B0h+var_140], eax
0x18002fe2a  mov     eax, cs:dword_18004F0F0
0x18002fe30  xor     edi, edi
0x18002fe32  mov     [rsp+1B0h+var_17C], r12d
0x18002fe37  xorps   xmm0, xmm0
0x18002fe3a  movups  [rsp+1B0h+var_178], xmm0
0x18002fe3f  movups  [rsp+1B0h+var_160], xmm1
0x18002fe44  movups  [rsp+1B0h+var_150], xmm1
0x18002fe49  cmp     eax, 4
0x18002fe4c  jbe     short loc_18002FE5A
0x18002fe4e  lea     rdx, byte_180047033
0x18002fe55  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18002fe5a  lea     rax, [rsp+1B0h+var_178]
0x18002fe5f  mov     qword ptr [rsp+1B0h+var_178+8], rax
0x18002fe64  lea     rax, [rsp+1B0h+var_178]
0x18002fe69  mov     qword ptr [rsp+1B0h+var_178], rax
0x18002fe6e  test    bl, 4
0x18002fe71  jz      short loc_18002FEAC
0x18002fe73  lea     rcx, g_MaintenanceLaunchLock; struct _UBPM_SRWLOCK *
0x18002fe7a  xor     r13b, r13b
0x18002fe7d  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18002fe82  lea     rcx, g_MaintenanceLaunchLock
0x18002fe89  mov     cs:byte_18004FC33, dil
0x18002fe90  mov     cs:dword_18004FFE8, edi
0x18002fe96  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002fe9d  nop     dword ptr [rax+rax+00h]
0x18002fea2  mov     esi, 4D3h
0x18002fea7  jmp     loc_1800300EC
0x18002feac  lea     rcx, [rbp+0B0h+var_130]; lpTlsValue
0x18002feb0  mov     r13d, 1
0x18002feb6  call    ?UbpmUtilsStartLockTracking@@YAXPEAU_CEM_LOCK_TRACKER@@@Z; UbpmUtilsStartLockTracking(_CEM_LOCK_TRACKER *)
0x18002febb  mov     ecx, 3E8h; dwMilliseconds
0x18002fec0  call    cs:__imp_Sleep
0x18002fec7  nop     dword ptr [rax+rax+00h]
0x18002fecc  lea     rcx, g_MaintenanceLaunchLock; struct _UBPM_SRWLOCK *
0x18002fed3  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18002fed8  lea     rcx, g_MaintenanceLaunchLock
0x18002fedf  mov     cs:byte_18004FC33, dil
0x18002fee6  mov     cs:dword_18004FFE8, edi
0x18002feec  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002fef3  nop     dword ptr [rax+rax+00h]
0x18002fef8  call    UbpmpAcquireListLockShared
0x18002fefd  mov     r15, cs:g_leConsumerListHead
0x18002ff04  lea     rax, g_leConsumerListHead
0x18002ff0b  cmp     r15, rax
0x18002ff0e  jz      loc_180030038
0x18002ff14  lea     r14, [r15-8]
0x18002ff18  lea     rbx, [r14+30h]
0x18002ff1c  mov     rcx, rbx
0x18002ff1f  call    cs:__imp_RtlAcquireSRWLockShared
0x18002ff26  nop     dword ptr [rax+rax+00h]
0x18002ff2b  mov     rax, [r14+18h]
0x18002ff2f  cmp     qword ptr [rax+30h], 0
0x18002ff34  jnz     short loc_18002FF4A
0x18002ff36  mov     rcx, rbx
0x18002ff39  call    cs:__imp_RtlReleaseSRWLockShared
0x18002ff40  nop     dword ptr [rax+rax+00h]
0x18002ff45  jmp     loc_180030020
0x18002ff4a  mov     rcx, r14
0x18002ff4d  call    UbpmpTakeConsumerReference
0x18002ff52  test    eax, eax
0x18002ff54  jnz     short loc_18002FF36
0x18002ff56  lea     ecx, [rax+20h]; Size
0x18002ff59  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002ff5e  mov     rdi, rax
0x18002ff61  test    rax, rax
0x18002ff64  jz      loc_180030064
0x18002ff6a  lea     r12, [r14+0D0h]
0x18002ff71  mov     [rax+10h], r14
0x18002ff75  mov     rcx, r12
0x18002ff78  call    cs:__imp_RtlAcquireSRWLockShared
0x18002ff7f  nop     dword ptr [rax+rax+00h]
0x18002ff84  lea     r8, [rsp+1B0h+var_160]
0x18002ff89  xor     edx, edx
0x18002ff8b  mov     rcx, r14
0x18002ff8e  lea     rsi, [rdi+18h]
0x18002ff92  call    UbpmStatsOperation
0x18002ff97  test    eax, eax
0x18002ff99  jnz     short loc_18002FFA3
0x18002ff9b  mov     rax, qword ptr [rsp+1B0h+var_160+0Ch]
0x18002ffa0  mov     [rsi], rax
0x18002ffa3  mov     rcx, r12
0x18002ffa6  call    cs:__imp_RtlReleaseSRWLockShared
0x18002ffad  nop     dword ptr [rax+rax+00h]
0x18002ffb2  mov     rcx, rbx
0x18002ffb5  call    cs:__imp_RtlReleaseSRWLockShared
0x18002ffbc  nop     dword ptr [rax+rax+00h]
0x18002ffc1  cmp     dword ptr [rsi+4], 0
0x18002ffc5  jz      short loc_18002FFF7
0x18002ffc7  cmp     dword ptr [rsi], 0
0x18002ffca  jz      short loc_18002FFF7
0x18002ffcc  mov     rbx, qword ptr [rsp+1B0h+var_178]
0x18002ffd1  jmp     short loc_18002FFED
0x18002ffd3  lea     rdx, [rbx+18h]; lpFileTime2
0x18002ffd7  mov     rcx, rsi; lpFileTime1
0x18002ffda  call    cs:__imp_CompareFileTime
0x18002ffe1  nop     dword ptr [rax+rax+00h]
0x18002ffe6  test    eax, eax
0x18002ffe8  js      short loc_180030047
0x18002ffea  mov     rbx, [rbx]
0x18002ffed  lea     rax, [rsp+1B0h+var_178]
0x18002fff2  cmp     rbx, rax
0x18002fff5  jnz     short loc_18002FFD3
0x18002fff7  mov     rax, qword ptr [rsp+1B0h+var_178+8]
0x18002fffc  lea     rcx, [rsp+1B0h+var_178]
0x180030001  cmp     [rax], rcx
0x180030004  jnz     loc_180030227
0x18003000a  mov     [rdi+8], rax
0x18003000e  lea     rcx, [rsp+1B0h+var_178]
0x180030013  mov     [rdi], rcx
0x180030016  mov     [rax], rdi
0x180030019  mov     qword ptr [rsp+1B0h+var_178+8], rdi
0x18003001e  xor     edi, edi
0x180030020  mov     r15, [r15]
0x180030023  lea     rax, g_leConsumerListHead
0x18003002a  cmp     r15, rax
0x18003002d  jnz     loc_18002FF14
0x180030033  mov     r12d, [rsp+1B0h+var_17C]
0x180030038  call    UbpmpReleaseListLockShared
0x18003003d  mov     rsi, qword ptr [rsp+1B0h+var_178]
0x180030042  jmp     loc_1800300DC
0x180030047  mov     rax, [rbx+8]
0x18003004b  cmp     [rax], rbx
0x18003004e  jnz     loc_180030227
0x180030054  mov     [rdi], rbx
0x180030057  mov     [rdi+8], rax
0x18003005b  mov     [rax], rdi
0x18003005e  mov     [rbx+8], rdi
0x180030062  jmp     short loc_18003001E
0x180030064  mov     rcx, rbx
0x180030067  mov     esi, 0Eh
0x18003006c  call    cs:__imp_RtlReleaseSRWLockShared
0x180030073  nop     dword ptr [rax+rax+00h]
0x180030078  call    UbpmpReleaseListLockShared
0x18003007d  mov     r12d, [rsp+1B0h+var_17C]
0x180030082  jmp     short loc_1800300E8
0x180030084  mov     rcx, [rsi]
0x180030087  cmp     [rcx+8], rsi
0x18003008b  jnz     loc_180030227
0x180030091  lea     r8, [rsi+8]
0x180030095  mov     rdx, [r8]
0x180030098  cmp     [rdx], rsi
0x18003009b  jnz     loc_180030227
0x1800300a1  mov     [rdx], rcx
0x1800300a4  mov     rax, rsi
0x1800300a7  mov     [rcx+8], rdx
0x1800300ab  mov     rbx, rsi
0x1800300ae  mov     [r8], rax
0x1800300b1  mov     rsi, rcx
0x1800300b4  mov     r8b, r13b
0x1800300b7  mov     edx, 3
0x1800300bc  mov     [rax], rax
0x1800300bf  mov     rcx, [rax+10h]
0x1800300c3  call    UbpmRunConsumerQueuedActions
0x1800300c8  mov     rcx, [rbx+10h]
0x1800300cc  call    UbpmpCloseTriggerConsumer
0x1800300d1  mov     rcx, rbx
0x1800300d4  call    UBPM_MIDL_user_free
0x1800300d9  add     r12d, r13d
0x1800300dc  lea     rax, [rsp+1B0h+var_178]
0x1800300e1  cmp     rsi, rax
0x1800300e4  jnz     short loc_180030084
0x1800300e6  xor     esi, esi
0x1800300e8  mov     bl, byte ptr [rsp+1B0h+var_180]
0x1800300ec  mov     eax, cs:dword_18004F0F0
0x1800300f2  cmp     eax, 4
0x1800300f5  jbe     short loc_180030165
0x1800300f7  movzx   eax, bl
0x1800300fa  lea     rdx, byte_1800470B3
0x180030101  mov     [rsp+1B0h+var_180], ax
0x180030106  lea     rcx, dword_18004F0F0
0x18003010d  lea     rax, [rsp+1B0h+var_17C]
0x180030112  mov     [rsp+1B0h+var_17C], esi
0x180030116  mov     [rbp+0B0h+var_60], rax
0x18003011a  xor     r9d, r9d
0x18003011d  lea     rax, [rsp+1B0h+var_168]
0x180030122  mov     [rsp+1B0h+var_168], r12d
0x180030127  mov     [rbp+0B0h+var_70], rax
0x18003012b  xor     r8d, r8d
0x18003012e  lea     rax, [rsp+1B0h+var_180]
0x180030133  mov     [rbp+0B0h+var_58], 4
0x18003013b  mov     [rbp+0B0h+var_80], rax
0x18003013f  lea     rax, [rbp+0B0h+var_A0]
0x180030143  mov     [rsp+1B0h+var_188], rax
0x180030148  mov     [rsp+1B0h+var_190], 5
0x180030150  mov     [rbp+0B0h+var_68], 4
0x180030158  mov     [rbp+0B0h+var_78], 2
0x180030160  call    _tlgWriteTransfer_EventWriteTransfer
0x180030165  test    rdi, rdi
0x180030168  jz      short loc_18003017B
0x18003016a  mov     rcx, [rdi+10h]
0x18003016e  call    UbpmpCloseTriggerConsumer
0x180030173  mov     rcx, rdi
0x180030176  call    UBPM_MIDL_user_free
0x18003017b  mov     rdi, qword ptr [rsp+1B0h+var_178]
0x180030180  jmp     short loc_1800301C6
0x180030182  mov     rcx, [rdi]
0x180030185  cmp     [rcx+8], rdi
0x180030189  jnz     loc_180030227
0x18003018f  lea     r8, [rdi+8]
0x180030193  mov     rdx, [r8]
0x180030196  cmp     [rdx], rdi
0x180030199  jnz     loc_180030227
0x18003019f  mov     rax, rdi
0x1800301a2  mov     [rdx], rcx
0x1800301a5  mov     [rcx+8], rdx
0x1800301a9  mov     rbx, rdi
0x1800301ac  mov     rdi, rcx
0x1800301af  mov     [r8], rax
0x1800301b2  mov     [rax], rax
0x1800301b5  mov     rcx, [rax+10h]
0x1800301b9  call    UbpmpCloseTriggerConsumer
0x1800301be  mov     rcx, rbx
0x1800301c1  call    UBPM_MIDL_user_free
0x1800301c6  lea     rax, [rsp+1B0h+var_178]
0x1800301cb  cmp     rdi, rax
0x1800301ce  jnz     short loc_180030182
0x1800301d0  test    r13b, r13b
0x1800301d3  jz      short loc_180030206
0x1800301d5  mov     ebx, cs:UbpmpLockTrackerId
0x1800301db  cmp     ebx, 0FFFFFFFFh
0x1800301de  jz      short loc_180030206
0x1800301e0  mov     ecx, ebx; dwTlsIndex
0x1800301e2  call    cs:__imp_TlsGetValue
0x1800301e9  nop     dword ptr [rax+rax+00h]
0x1800301ee  cmp     qword ptr [rax], 0
0x1800301f2  jz      short loc_1800301F6
0x1800301f4  int     2Ch; Windows NT - assertion failure
0x1800301f6  xor     edx, edx; lpTlsValue
0x1800301f8  mov     ecx, ebx; dwTlsIndex
0x1800301fa  call    cs:__imp_TlsSetValue
0x180030201  nop     dword ptr [rax+rax+00h]
0x180030206  mov     rcx, [rbp+0B0h+var_50]
0x18003020a  xor     rcx, rsp; StackCookie
0x18003020d  call    __security_check_cookie
0x180030212  add     rsp, 178h
0x180030219  pop     r15
0x18003021b  pop     r14
0x18003021d  pop     r13
0x18003021f  pop     r12
0x180030221  pop     rdi
0x180030222  pop     rsi
0x180030223  pop     rbx
0x180030224  pop     rbp
0x180030225  retn
0x180030227  mov     ecx, 3
0x18003022c  int     29h; Win8: RtlFailFast(ecx)
```
