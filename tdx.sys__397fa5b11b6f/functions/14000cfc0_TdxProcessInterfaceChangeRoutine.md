# TdxProcessInterfaceChangeRoutine

- ea: `0x14000cfc0`
- end: `0x14000d788`
- name: `TdxProcessInterfaceChangeRoutine`
- size: `1992`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x14000cfc0`
- `0x14000daa0`
- `0x14000db08`
- `0x14000f364`
- `0x140010608`
- `0x140010998`
- `0x140012b8c`
- `0x140012e90`
- `0x140013bf8`
- `0x1400151d0`
- `0x1400184b0`
- `0x140018600`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14000d14c`
- `ntoskrnl!KeReleaseMutex` at `0x14000d2e7`
- `ntoskrnl!KeReleaseMutex` at `0x14000d38a`
- `ntoskrnl!KeReleaseMutex` at `0x14000d4cc`
- `ntoskrnl!KeReleaseMutex` at `0x14000d5ac`
- `ntoskrnl!KeReleaseMutex` at `0x14000d14c`
- `ntoskrnl!KeReleaseMutex` at `0x14000d2e7`
- `ntoskrnl!KeReleaseMutex` at `0x14000d38a`
- `ntoskrnl!KeReleaseMutex` at `0x14000d4cc`
- `ntoskrnl!KeReleaseMutex` at `0x14000d5ac`
- `ntoskrnl!RtlCompareMemory` at `0x14000d117`
- `ntoskrnl!RtlCompareMemory` at `0x14000d287`
- `ntoskrnl!RtlCompareMemory` at `0x14000d117`
- `ntoskrnl!RtlCompareMemory` at `0x14000d287`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d16a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d16a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d0c6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d23f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d582`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d0c6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d23f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d582`
- `NETIO!NsiGetParameter` at `0x14000d3e3`
- `NETIO!NsiGetParameter` at `0x14000d6a2`
- `NETIO!NsiGetParameter` at `0x14000d3e3`
- `NETIO!NsiGetParameter` at `0x14000d6a2`
- `NETIO!NsiGetAllParameters` at `0x14000d218`
- `NETIO!NsiGetAllParameters` at `0x14000d218`
- `TDI!TdiDeregisterDeviceObject` at `0x14000d2fb`
- `TDI!TdiDeregisterDeviceObject` at `0x14000d2fb`

## pseudocode

```c
const NPI_MODULEID *__fastcall TdxProcessInterfaceChangeRoutine(unsigned int *P)
{
  struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C v1; // rsi
  unsigned int *v2; // r15
  unsigned int v3; // r12d
  const NPI_MODULEID *result; // rax
  const NPI_MODULEID *v5; // rbx
  unsigned int v6; // edi
  __int64 *v7; // r14
  int v8; // edi
  struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C v9; // rbx
  void *v10; // rcx
  int AllParameters; // eax
  __int64 *v12; // rbx
  int v13; // r14d
  __int64 v14; // rcx
  struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C v15; // rbx
  int v16; // ecx
  void *v17; // rbx
  int v18; // eax
  __int64 v19; // r9
  int v20; // edx
  const char *v21; // r8
  size_t v22; // r8
  __int64 v23; // r8
  int v24; // edx
  unsigned int Timeout; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C v27; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+78h] [rbp-88h] BYREF
  __int64 Source2; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v31[2]; // [rsp+88h] [rbp-78h]
  _OWORD v32[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v33; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v34; // [rsp+C0h] [rbp-40h]
  __int128 v35; // [rsp+D0h] [rbp-30h]
  __int128 v36; // [rsp+E0h] [rbp-20h]
  __int128 v37; // [rsp+F0h] [rbp-10h]
  __int64 v38; // [rsp+100h] [rbp+0h]

  v1 = 0;
  v27 = 0;
  v38 = 0;
  v2 = P;
  v29 = 0;
  v3 = 0;
  v33 = 0;
  v28 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  memset(v32, 0, sizeof(v32));
  result = (const NPI_MODULEID *)&WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    result = (const NPI_MODULEID *)WPP_SF_qq(
                                     WPP_GLOBAL_Control->AttachedDevice,
                                     34,
                                     WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids,
                                     P,
                                     P);
  }
  if ( v2 )
  {
    while ( 1 )
    {
      v5 = (const NPI_MODULEID *)*((_QWORD *)v2 + 1);
      if ( v5 == &NPI_MS_IPV4_MODULEID )
      {
        v6 = 0;
      }
      else
      {
        v6 = 256;
        if ( v5 == &NPI_MS_IPV6_MODULEID )
          v6 = 41;
      }
      v7 = (__int64 *)*((_QWORD *)v2 + 2);
      if ( !v7 )
      {
        if ( (int)TdxGetAllParameters(3, 1, (_DWORD)v5, 7, (__int64)&v29, 8, 0, 0, 0, 0, (__int64)v32, 32) >= 0 )
        {
          do
          {
            if ( DWORD1(v32[0]) != 24 )
            {
              KeWaitForSingleObject(&WPP_MAIN_CB.Dpc.DpcListEntry, Executive, 0, 0, 0);
              TdxCreateAndRegisterDeviceObject(&v29, v6, v32, &v27);
              KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
            }
            ++v3;
          }
          while ( (int)TdxGetAllParameters(3, 2, (_DWORD)v5, 7, (__int64)&v29, 8, 0, 0, 0, 0, (__int64)v32, 32) >= 0 );
          v28 = v3;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 35, v23, v3);
        }
        TdxDecrementNotReadyInterfaceCount(1624);
        goto LABEL_19;
      }
      if ( v5 == &NPI_MS_NDIS_MODULEID )
      {
        v31[1] = 41;
        v26 = 0;
        v31[0] = 0;
        KeWaitForSingleObject(&WPP_MAIN_CB.Dpc.DpcListEntry, Executive, 0, 0, 0);
        do
        {
          v8 = v31[*(_QWORD *)&v1];
          v9 = WPP_MAIN_CB.DeviceQueue.1;
          Source2 = *v7;
          while ( *(struct _DEVICE_OBJECT **)&v9 != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.Busy )
          {
            if ( *(_DWORD *)(*(_QWORD *)&v9 + 20LL) == v8
              && (*(_DWORD *)(*(_QWORD *)&v9 + 304LL) & 8) == 0
              && RtlCompareMemory((const void *)(*(_QWORD *)&v9 + 24LL), &Source2, 8u) == 8 )
            {
              if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)&v9 + 288LL) - 1) > 1
                && (*(_DWORD *)(*(_QWORD *)&v9 + 304LL) & 4) == 0 )
              {
                if ( (int)NsiGetParameter(3, &NPI_MS_NDIS_MODULEID, 0, *((_QWORD *)v2 + 2), v2[6], 1, &v26, 4, 8) >= 0 )
                {
                  v24 = v26;
                  if ( v26 == 2 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
                    {
                      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_q)(
                        WPP_GLOBAL_Control->AttachedDevice,
                        33,
                        WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids,
                        v9);
                      v24 = v26;
                    }
                    *(_DWORD *)(*(_QWORD *)&v9 + 304LL) |= 4u;
                    *(_DWORD *)(*(_QWORD *)&v9 + 288LL) = v24;
                    TdxDecrementNotReadyInterfaceCount(1523);
                    TdxNaTryToOverlapDelayedBinds("TdxProcessIfMediaStateChangeRoutine", 1524);
                  }
                }
                else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                       && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
                {
                  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_q)(
                    WPP_GLOBAL_Control->AttachedDevice,
                    32,
                    WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids,
                    v9);
                }
              }
              break;
            }
            v9 = **(struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C **)&v9;
          }
          ++*(_QWORD *)&v1;
        }
        while ( v1 != 2 );
        KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
        v3 = v28;
        goto LABEL_18;
      }
      AllParameters = NsiGetAllParameters(3, v5, 7, v7, v2[6], 0, 0, &v33, 88, v32, 32);
      v12 = (__int64 *)*((_QWORD *)v2 + 2);
      v13 = AllParameters;
      KeWaitForSingleObject(&WPP_MAIN_CB.Dpc.DpcListEntry, Executive, 0, 0, 0);
      v14 = *v12;
      v15 = WPP_MAIN_CB.DeviceQueue.1;
      Source2 = v14;
      while ( *(struct _DEVICE_OBJECT **)&v15 != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.Busy )
      {
        if ( *(_DWORD *)(*(_QWORD *)&v15 + 20LL) == v6
          && (*(_DWORD *)(*(_QWORD *)&v15 + 304LL) & 8) == 0
          && RtlCompareMemory((const void *)(*(_QWORD *)&v15 + 24LL), &Source2, 8u) == 8 )
        {
          v1 = v15;
          break;
        }
        v15 = **(struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C **)&v15;
      }
      v27 = v1;
      if ( v1 )
        break;
      if ( !v13 )
        goto LABEL_55;
LABEL_58:
      KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
LABEL_18:
      v1 = 0;
LABEL_19:
      v10 = v2;
      v2 = *(unsigned int **)v2;
      ExFreePoolWithTag(v10, 0x20786454u);
      result = &NPI_MS_IPV4_MODULEID;
      if ( !v2 )
        return result;
    }
    v16 = *(_DWORD *)(*(_QWORD *)&v1 + 304LL);
    if ( v13 == -1073741275 )
    {
      v17 = 0;
      if ( (v16 & 8) == 0 )
      {
        *(_DWORD *)(*(_QWORD *)&v1 + 304LL) = v16 | 8;
        v17 = (void *)((__int64 (__fastcall *)(_QWORD))TdxDereferenceDeviceObjectContext)(v27);
      }
      KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
      if ( v17 )
        TdiDeregisterDeviceObject(v17);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_q)(
          WPP_GLOBAL_Control->AttachedDevice,
          37,
          WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids,
          v27);
      }
      goto LABEL_18;
    }
    if ( (v16 & 8) == 0 )
    {
      v18 = *(_DWORD *)(*(_QWORD *)&v1 + 288LL);
      if ( v18 )
      {
        if ( v18 == 2 )
          goto LABEL_44;
LABEL_46:
        v1 = 0;
        if ( (v16 & 4) == 0 )
        {
          v19 = *((_QWORD *)v2 + 2);
          Timeout = v2[6];
          v26 = 0;
          NsiGetParameter(3, &NPI_MS_NDIS_MODULEID, 0, v19, Timeout, 1, &v26, 4, 8);
          v20 = v26;
          if ( v26 == 2 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
            {
              v21 = "MediaConnectStateUnknown";
              if ( *(_DWORD *)(*(_QWORD *)&v27 + 288LL) )
                v21 = "MediaConnectStateConnected";
              WPP_SF_qs(
                WPP_GLOBAL_Control->AttachedDevice,
                36,
                (unsigned int)WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids,
                *(_DWORD *)&v27,
                (__int64)v21);
              v20 = v26;
            }
            *(_DWORD *)(*(_QWORD *)&v27 + 288LL) = v20;
            *(_DWORD *)(*(_QWORD *)&v27 + 304LL) |= 4u;
            TdxDecrementNotReadyInterfaceCount(1717);
            TdxNaTryToOverlapDelayedBinds("TdxProcessInterfaceChangeRoutine", 1718);
          }
        }
      }
      else
      {
        if ( !(_DWORD)v34 )
          goto LABEL_46;
        *(_DWORD *)(*(_QWORD *)&v1 + 288LL) = 1;
LABEL_44:
        v1 = 0;
      }
      KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
      goto LABEL_19;
    }
LABEL_55:
    if ( v2[6] < 8 )
      v22 = v2[6];
    else
      v22 = 8;
    memmove(&v29, *((const void **)v2 + 2), v22);
    TdxCreateAndRegisterDeviceObject(&v29, v6, v32, &v27);
    goto LABEL_58;
  }
  return result;
}

```

## disassembly

```asm
0x14000cfc0  push    rbp
0x14000cfc2  push    rsi
0x14000cfc3  push    r12
0x14000cfc5  push    r15
0x14000cfc7  lea     rbp, [rsp-28h]
0x14000cfcc  sub     rsp, 128h
0x14000cfd3  mov     rax, cs:__security_cookie
0x14000cfda  xor     rax, rsp
0x14000cfdd  mov     [rbp+40h+var_30], rax
0x14000cfe1  xorps   xmm0, xmm0
0x14000cfe4  xor     esi, esi
0x14000cfe6  xor     eax, eax
0x14000cfe8  mov     [rsp+140h+var_D8], rsi
0x14000cfed  mov     [rbp+40h+var_40], rax
0x14000cff1  mov     r15, rcx
0x14000cff4  mov     [rsp+140h+var_C8], rsi
0x14000cff9  mov     r12d, esi
0x14000cffc  movups  [rbp+40h+var_90], xmm0
0x14000d000  mov     [rsp+140h+var_D0], esi
0x14000d004  movups  [rbp+40h+var_80], xmm0
0x14000d008  movups  [rbp+40h+var_70], xmm0
0x14000d00c  movups  [rbp+40h+var_60], xmm0
0x14000d010  movups  [rbp+40h+var_50], xmm0
0x14000d014  movups  [rbp+40h+var_B0], xmm0
0x14000d018  movups  [rbp+40h+var_A0], xmm0
0x14000d01c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d023  lea     rax, WPP_GLOBAL_Control
0x14000d02a  cmp     rcx, rax
0x14000d02d  jz      short loc_14000D039
0x14000d02f  cmp     byte ptr [rcx+29h], 3
0x14000d033  jnb     loc_14000D4E4
0x14000d039  test    r15, r15
0x14000d03c  jz      loc_14000D1B9
0x14000d042  mov     [rsp+140h+arg_8], rbx
0x14000d04a  lea     rax, NPI_MS_IPV4_MODULEID
0x14000d051  mov     [rsp+140h+arg_10], rdi
0x14000d059  lea     r8, NPI_MS_IPV6_MODULEID
0x14000d060  mov     [rsp+140h+arg_18], r13
0x14000d068  lea     rcx, NPI_MS_NDIS_MODULEID
0x14000d06f  mov     [rsp+140h+var_20], r14
0x14000d077  lea     r13, WPP_MAIN_CB.DeviceQueue.20h
0x14000d07e  mov     edx, 29h ; ')'
0x14000d083  mov     rbx, [r15+8]
0x14000d087  cmp     rbx, rax
0x14000d08a  jnz     loc_14000D354
0x14000d090  mov     edi, esi
0x14000d092  mov     r14, [r15+10h]
0x14000d096  test    r14, r14
0x14000d099  jz      loc_14000D513
0x14000d09f  cmp     rbx, rcx
0x14000d0a2  jnz     loc_14000D1D4
0x14000d0a8  mov     [rbp+40h+var_B4], edx
0x14000d0ab  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Object
0x14000d0b2  xor     edx, edx; WaitReason
0x14000d0b4  mov     [rsp+140h+var_E0], esi
0x14000d0b8  xor     r9d, r9d; Alertable
0x14000d0bb  mov     [rbp+40h+var_B8], esi
0x14000d0be  xor     r8d, r8d; WaitMode
0x14000d0c1  mov     [rsp+140h+Timeout], rsi; Timeout
0x14000d0c6  call    cs:__imp_KeWaitForSingleObject
0x14000d0cd  nop     dword ptr [rax+rax+00h]
0x14000d0d2  lea     r12, WPP_GLOBAL_Control
0x14000d0d9  mov     rax, [r14]
0x14000d0dc  mov     edi, [rbp+rsi*4+40h+var_B8]
0x14000d0e0  mov     rbx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x14000d0e7  mov     [rbp+40h+Source2], rax
0x14000d0eb  nop     dword ptr [rax+rax+00h]
0x14000d0f0  cmp     rbx, r13
0x14000d0f3  jz      short loc_14000D13A
0x14000d0f5  cmp     [rbx+14h], edi
0x14000d0f8  jnz     short loc_14000D104
0x14000d0fa  mov     eax, [rbx+130h]
0x14000d100  test    al, 8
0x14000d102  jz      short loc_14000D109
0x14000d104  mov     rbx, [rbx]
0x14000d107  jmp     short loc_14000D0F0
0x14000d109  lea     rcx, [rbx+18h]; Source1
0x14000d10d  mov     r8d, 8; Length
0x14000d113  lea     rdx, [rbp+40h+Source2]; Source2
0x14000d117  call    cs:__imp_RtlCompareMemory
0x14000d11e  nop     dword ptr [rax+rax+00h]
0x14000d123  cmp     rax, 8
0x14000d127  jnz     short loc_14000D104
0x14000d129  mov     eax, [rbx+120h]
0x14000d12f  dec     eax
0x14000d131  cmp     eax, 1
0x14000d134  ja      loc_14000D657
0x14000d13a  inc     rsi
0x14000d13d  cmp     rsi, 2
0x14000d141  jnz     short loc_14000D0D9
0x14000d143  xor     edx, edx; Wait
0x14000d145  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Mutex
0x14000d14c  call    cs:__imp_KeReleaseMutex
0x14000d153  nop     dword ptr [rax+rax+00h]
0x14000d158  mov     r12d, [rsp+140h+var_D0]
0x14000d15d  xor     esi, esi
0x14000d15f  mov     rcx, r15; P
0x14000d162  mov     edx, 20786454h; Tag
0x14000d167  mov     r15, [r15]
0x14000d16a  call    cs:__imp_ExFreePoolWithTag
0x14000d171  nop     dword ptr [rax+rax+00h]
0x14000d176  lea     rax, NPI_MS_IPV4_MODULEID
0x14000d17d  mov     edx, 29h ; ')'
0x14000d182  lea     rcx, NPI_MS_NDIS_MODULEID
0x14000d189  lea     r8, NPI_MS_IPV6_MODULEID
0x14000d190  test    r15, r15
0x14000d193  jnz     loc_14000D083
0x14000d199  mov     r14, [rsp+140h+var_20]
0x14000d1a1  mov     r13, [rsp+140h+arg_18]
0x14000d1a9  mov     rdi, [rsp+140h+arg_10]
0x14000d1b1  mov     rbx, [rsp+140h+arg_8]
0x14000d1b9  mov     rcx, [rbp+40h+var_30]
0x14000d1bd  xor     rcx, rsp; StackCookie
0x14000d1c0  call    __security_check_cookie
0x14000d1c5  add     rsp, 128h
0x14000d1cc  pop     r15
0x14000d1ce  pop     r12
0x14000d1d0  pop     rsi
0x14000d1d1  pop     rbp
0x14000d1d2  retn
0x14000d1d4  mov     dword ptr [rsp+140h+var_F0], 20h ; ' '
0x14000d1dc  lea     rax, [rbp+40h+var_B0]
0x14000d1e0  mov     [rsp+140h+var_F8], rax
0x14000d1e5  mov     r9, r14
0x14000d1e8  mov     dword ptr [rsp+140h+var_100], 58h ; 'X'
0x14000d1f0  lea     rax, [rbp+40h+var_90]
0x14000d1f4  mov     [rsp+140h+var_108], rax
0x14000d1f9  mov     r8d, 7
0x14000d1ff  mov     eax, [r15+18h]
0x14000d203  mov     rdx, rbx
0x14000d206  mov     dword ptr [rsp+140h+var_110], esi
0x14000d20a  mov     ecx, 3
0x14000d20f  mov     [rsp+140h+var_118], rsi
0x14000d214  mov     dword ptr [rsp+140h+Timeout], eax
0x14000d218  call    cs:__imp_NsiGetAllParameters
0x14000d21f  nop     dword ptr [rax+rax+00h]
0x14000d224  mov     rbx, [r15+10h]
0x14000d228  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Object
0x14000d22f  xor     r9d, r9d; Alertable
0x14000d232  mov     [rsp+140h+Timeout], rsi; Timeout
0x14000d237  xor     r8d, r8d; WaitMode
0x14000d23a  xor     edx, edx; WaitReason
0x14000d23c  mov     r14d, eax
0x14000d23f  call    cs:__imp_KeWaitForSingleObject
0x14000d246  nop     dword ptr [rax+rax+00h]
0x14000d24b  mov     rcx, [rbx]
0x14000d24e  mov     rbx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x14000d255  mov     [rbp+40h+Source2], rcx
0x14000d259  nop     dword ptr [rax+00000000h]
0x14000d260  cmp     rbx, r13
0x14000d263  jz      short loc_14000D29C
0x14000d265  cmp     [rbx+14h], edi
0x14000d268  jnz     short loc_14000D274
0x14000d26a  mov     eax, [rbx+130h]
0x14000d270  test    al, 8
0x14000d272  jz      short loc_14000D279
0x14000d274  mov     rbx, [rbx]
0x14000d277  jmp     short loc_14000D260
0x14000d279  lea     rcx, [rbx+18h]; Source1
0x14000d27d  mov     r8d, 8; Length
0x14000d283  lea     rdx, [rbp+40h+Source2]; Source2
0x14000d287  call    cs:__imp_RtlCompareMemory
0x14000d28e  nop     dword ptr [rax+rax+00h]
0x14000d293  cmp     rax, 8
0x14000d297  jnz     short loc_14000D274
0x14000d299  mov     rsi, rbx
0x14000d29c  mov     [rsp+140h+var_D8], rsi
0x14000d2a1  test    rsi, rsi
0x14000d2a4  jz      loc_14000D4DD
0x14000d2aa  mov     ecx, [rsi+130h]
0x14000d2b0  mov     eax, ecx
0x14000d2b2  and     eax, 8
0x14000d2b5  cmp     r14d, 0C0000225h
0x14000d2bc  jnz     loc_14000D364
0x14000d2c2  xor     ebx, ebx
0x14000d2c4  test    eax, eax
0x14000d2c6  jnz     short loc_14000D2DE
0x14000d2c8  or      ecx, 8
0x14000d2cb  mov     [rsi+130h], ecx
0x14000d2d1  mov     rcx, [rsp+140h+var_D8]
0x14000d2d6  call    TdxDereferenceDeviceObjectContext
0x14000d2db  mov     rbx, rax
0x14000d2de  xor     edx, edx; Wait
0x14000d2e0  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Mutex
0x14000d2e7  call    cs:__imp_KeReleaseMutex
0x14000d2ee  nop     dword ptr [rax+rax+00h]
0x14000d2f3  test    rbx, rbx
0x14000d2f6  jz      short loc_14000D307
0x14000d2f8  mov     rcx, rbx; RegistrationHandle
0x14000d2fb  call    cs:__imp_TdiDeregisterDeviceObject
0x14000d302  nop     dword ptr [rax+rax+00h]
0x14000d307  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d30e  lea     rax, WPP_GLOBAL_Control
0x14000d315  cmp     rcx, rax
0x14000d318  jz      loc_14000D15D
0x14000d31e  cmp     byte ptr [rcx+29h], 3
0x14000d322  jb      loc_14000D15D
0x14000d328  test    dword ptr [rcx+2Ch], 200h
0x14000d32f  jz      loc_14000D15D
0x14000d335  mov     r9, [rsp+140h+var_D8]
0x14000d33a  lea     r8, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids
0x14000d341  mov     rcx, [rcx+18h]
0x14000d345  mov     edx, 25h ; '%'
0x14000d34a  call    WPP_SF_q
0x14000d34f  jmp     loc_14000D15D
0x14000d354  cmp     rbx, r8
0x14000d357  mov     edi, 100h
0x14000d35c  cmovz   edi, edx
0x14000d35f  jmp     loc_14000D092
0x14000d364  test    eax, eax
0x14000d366  jnz     loc_14000D48D
0x14000d36c  mov     eax, [rsi+120h]
0x14000d372  test    eax, eax
0x14000d374  jz      loc_14000D767
0x14000d37a  cmp     eax, 2
0x14000d37d  jnz     short loc_14000D39B
0x14000d37f  xor     esi, esi
0x14000d381  xor     edx, edx; Wait
0x14000d383  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Mutex
0x14000d38a  call    cs:__imp_KeReleaseMutex
0x14000d391  nop     dword ptr [rax+rax+00h]
0x14000d396  jmp     loc_14000D15F
0x14000d39b  xor     esi, esi
0x14000d39d  test    cl, 4
0x14000d3a0  jnz     short loc_14000D381
0x14000d3a2  mov     r9, [r15+10h]
0x14000d3a6  lea     rax, [rsp+140h+var_E0]
0x14000d3ab  mov     dword ptr [rsp+140h+var_100], 8
0x14000d3b3  lea     rdx, NPI_MS_NDIS_MODULEID
0x14000d3ba  mov     dword ptr [rsp+140h+var_108], 4
0x14000d3c2  xor     r8d, r8d
0x14000d3c5  mov     [rsp+140h+var_110], rax
0x14000d3ca  mov     ecx, 3
0x14000d3cf  mov     eax, [r15+18h]
0x14000d3d3  mov     dword ptr [rsp+140h+var_118], 1
0x14000d3db  mov     dword ptr [rsp+140h+Timeout], eax
0x14000d3df  mov     [rsp+140h+var_E0], esi
0x14000d3e3  call    cs:__imp_NsiGetParameter
0x14000d3ea  nop     dword ptr [rax+rax+00h]
0x14000d3ef  mov     edx, [rsp+140h+var_E0]
0x14000d3f3  cmp     edx, 2
0x14000d3f6  jnz     short loc_14000D381
0x14000d3f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d3ff  lea     rax, WPP_GLOBAL_Control
0x14000d406  cmp     rcx, rax
0x14000d409  jz      short loc_14000D456
0x14000d40b  cmp     byte ptr [rcx+29h], 3
0x14000d40f  jb      short loc_14000D456
0x14000d411  test    dword ptr [rcx+2Ch], 200h
0x14000d418  jz      short loc_14000D456
0x14000d41a  mov     r9, [rsp+140h+var_D8]
0x14000d41f  lea     rax, aMediaconnectst; "MediaConnectStateConnected"
0x14000d426  mov     rcx, [rcx+18h]
0x14000d42a  lea     r8, aMediaconnectst_0; "MediaConnectStateUnknown"
0x14000d431  mov     edx, 24h ; '$'
0x14000d436  cmp     [r9+120h], esi
0x14000d43d  cmovnz  r8, rax
0x14000d441  mov     [rsp+140h+Timeout], r8
0x14000d446  lea     r8, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids
0x14000d44d  call    WPP_SF_qs
0x14000d452  mov     edx, [rsp+140h+var_E0]
0x14000d456  mov     rax, [rsp+140h+var_D8]
0x14000d45b  mov     ecx, 6B5h
0x14000d460  mov     [rax+120h], edx
0x14000d466  mov     rax, [rsp+140h+var_D8]
0x14000d46b  or      dword ptr [rax+130h], 4
0x14000d472  call    TdxDecrementNotReadyInterfaceCount
0x14000d477  mov     edx, 6B6h
0x14000d47c  lea     rcx, aTdxprocessinte; "TdxProcessInterfaceChangeRoutine"
0x14000d483  call    TdxNaTryToOverlapDelayedBinds
0x14000d488  jmp     loc_14000D381
0x14000d48d  mov     eax, [r15+18h]
0x14000d491  cmp     eax, 8
0x14000d494  jb      loc_14000D780
0x14000d49a  mov     r8d, 8; Size
0x14000d4a0  mov     rdx, [r15+10h]; Src
0x14000d4a4  lea     rcx, [rsp+140h+var_C8]; void *
0x14000d4a9  call    memmove
0x14000d4ae  lea     r9, [rsp+140h+var_D8]
0x14000d4b3  mov     edx, edi
0x14000d4b5  lea     r8, [rbp+40h+var_B0]
0x14000d4b9  lea     rcx, [rsp+140h+var_C8]
0x14000d4be  call    TdxCreateAndRegisterDeviceObject
0x14000d4c3  xor     edx, edx; Wait
0x14000d4c5  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Mutex
0x14000d4cc  call    cs:__imp_KeReleaseMutex
0x14000d4d3  nop     dword ptr [rax+rax+00h]
0x14000d4d8  jmp     loc_14000D15D
0x14000d4dd  test    r14d, r14d
0x14000d4e0  jnz     short loc_14000D4C3
0x14000d4e2  jmp     short loc_14000D48D
0x14000d4e4  test    dword ptr [rcx+2Ch], 200h
0x14000d4eb  jz      loc_14000D039
0x14000d4f1  mov     rcx, [rcx+18h]
0x14000d4f5  lea     r8, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids
0x14000d4fc  mov     edx, 22h ; '"'
0x14000d501  mov     [rsp+140h+Timeout], r15
0x14000d506  mov     r9, r15
0x14000d509  call    WPP_SF_qq
0x14000d50e  jmp     loc_14000D039
  ... truncated ...
```
