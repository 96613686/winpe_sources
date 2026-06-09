# FExRegisterVWifiMpInternal

- ea: `0x14000745c`
- end: `0x140007cf8`
- name: `FExRegisterVWifiMpInternal`
- size: `2204`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x140006bc0`

## callees

- `0x140003b7c`
- `0x14000745c`
- `0x140007d00`
- `0x140007d58`
- `0x140009270`
- `0x14000c39c`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000ed88`
- `0x14000ede4`
- `0x14000f110`
- `0x14000f500`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140007c18`
- `ntoskrnl!DbgPrint` at `0x140007cb7`
- `ntoskrnl!DbgPrint` at `0x140007c18`
- `ntoskrnl!DbgPrint` at `0x140007cb7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007707`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007707`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400079e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400079e5`
- `NDIS!NdisFreeMemory` at `0x1400077e6`
- `NDIS!NdisFreeMemory` at `0x140007a80`
- `NDIS!NdisFreeMemory` at `0x140007cd1`
- `NDIS!NdisFreeMemory` at `0x1400077e6`
- `NDIS!NdisFreeMemory` at `0x140007a80`
- `NDIS!NdisFreeMemory` at `0x140007cd1`
- `NDIS!NdisFOidRequest` at `0x1400075be`
- `NDIS!NdisFOidRequest` at `0x1400075be`
- `NDIS!NdisInitializeEvent` at `0x140007572`
- `NDIS!NdisInitializeEvent` at `0x140007572`
- `NDIS!NdisWaitEvent` at `0x1400075dc`
- `NDIS!NdisWaitEvent` at `0x1400075dc`

## pseudocode

```c
__int64 __fastcall FExRegisterVWifiMpInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        __int64 *a5,
        __int64 a6,
        __int64 a7)
{
  int v7; // ebx
  unsigned int v10; // r15d
  char *v11; // rsi
  int v12; // ebx
  int v13; // edi
  unsigned int v14; // eax
  _DWORD *v15; // r12
  unsigned int v16; // ebx
  __int64 v17; // rbx
  void *v18; // rcx
  char v19; // di
  unsigned int v20; // eax
  __int64 v21; // r8
  int v22; // ebx
  int v23; // eax
  __int64 v24; // rbx
  _DWORD *v25; // rdi
  __int64 v26; // r8
  __int64 *v27; // r9
  PDEVICE_OBJECT v28; // rcx
  __int64 v30; // r8
  _OWORD **v31; // r15
  _OWORD *v32; // rcx
  _OWORD *v33; // rax
  _QWORD *v34; // rdx
  KIRQL v35; // dl
  int v36; // ebx
  PDEVICE_OBJECT v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rdx
  PVOID VirtualAddress; // [rsp+50h] [rbp-B0h] BYREF
  int v41; // [rsp+58h] [rbp-A8h]
  PVOID v42; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v43; // [rsp+68h] [rbp-98h]
  __int64 v44; // [rsp+70h] [rbp-90h]
  __int64 v45; // [rsp+78h] [rbp-88h]
  __int64 *v46; // [rsp+80h] [rbp-80h]
  _BYTE OidRequest[280]; // [rsp+90h] [rbp-70h] BYREF

  v7 = a3;
  v43 = a5;
  v45 = a6;
  v44 = a7;
  VirtualAddress = 0;
  v10 = 0;
  v41 = 0;
  v11 = 0;
  v42 = 0;
  v46 = a4;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_63d282d22d9e3f2cd53cfde58a2ac431_Traceguids);
  v12 = v7 - 1;
  if ( v12 )
  {
    v36 = v12 - 1;
    if ( v36 )
    {
      if ( v36 == 1 )
        v13 = 20;
      else
        v13 = 100;
    }
    else
    {
      v41 = 1;
      v13 = 4;
    }
  }
  else
  {
    v13 = 12;
  }
  v14 = AllocMem(*(_QWORD *)(a1 + 128), 16, a3, &VirtualAddress);
  v15 = VirtualAddress;
  v16 = v14;
  if ( v14 )
  {
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_75;
    v38 = 16;
    goto LABEL_74;
  }
  *(_OWORD *)VirtualAddress = 0;
  *(_WORD *)v15 = 384;
  v15[1] = v13;
  v17 = *(_QWORD *)(a2 + 8);
  memset(OidRequest, 0, sizeof(OidRequest));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 237, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  memset(OidRequest, 0, 0xF8u);
  NdisInitializeEvent((PNDIS_EVENT)&OidRequest[248]);
  v18 = *(void **)(v17 + 128);
  *(_DWORD *)OidRequest = 15466902;
  *(_DWORD *)&OidRequest[4] = 12;
  *(_DWORD *)&OidRequest[32] = 235143425;
  *(_QWORD *)&OidRequest[52] = 16;
  *(_QWORD *)&OidRequest[40] = v15;
  *(_DWORD *)&OidRequest[48] = 8;
  *(_QWORD *)&OidRequest[16] = 1380341590;
  v16 = NdisFOidRequest(v18, (PNDIS_OID_REQUEST)OidRequest);
  if ( v16 == 259 )
  {
    NdisWaitEvent((PNDIS_EVENT)&OidRequest[248], 0);
    v16 = *(_DWORD *)&OidRequest[272];
  }
  if ( !v16 )
  {
    v10 = *(_DWORD *)&OidRequest[60];
    if ( *(_DWORD *)&OidRequest[60] > 0x10u )
      v10 = 16;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 238, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  if ( v16 )
  {
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_75;
    v38 = 17;
LABEL_74:
    WPP_SF_d(v37->AttachedDevice, v38, WPP_63d282d22d9e3f2cd53cfde58a2ac431_Traceguids);
LABEL_75:
    v19 = 0;
    goto LABEL_28;
  }
  v19 = 1;
  if ( v10 >= 0x10 )
  {
    *(_BYTE *)(a1 + 2712) = 0;
    if ( v44 && *(_BYTE *)(a1 + 2681) )
    {
      LODWORD(VirtualAddress) = 0;
      v20 = filterDoInternalRequest(a1, 0, 234947437, 0, 0, 0);
      v22 = (int)VirtualAddress;
      if ( v20 != -2147483643 && v20 || (unsigned int)VirtualAddress < 0xB8 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          v24 = a2;
          WPP_SF_qddd(
            WPP_GLOBAL_Control->AttachedDevice,
            v20,
            v21,
            a2,
            v15[1],
            v20,
            (_DWORD)VirtualAddress,
            &VirtualAddress);
LABEL_21:
          v25 = (_DWORD *)(a1 + 24);
          if ( *(_DWORD *)(a1 + 24) != 1801678668 )
          {
            DbgPrint("Trying to acquire uninited lock %p, %s, Line %d\n", (const void *)(a1 + 24), "FilterLock", 423);
            __debugbreak();
          }
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 28));
          *(_BYTE *)(a1 + 112) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 104));
          *(_QWORD *)(a1 + 72) = "FilterLock";
          *(_BYTE *)(a1 + 32) = 1;
          *(_DWORD *)(a1 + 80) = 423;
          *(_BYTE *)(v24 + 1) = 1;
          *(_BYTE *)(v24 + 3) = 1;
          *(_DWORD *)(v24 + 104) = v15[1];
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 20, v26, v24, v15[1]);
          }
          v27 = v43;
          *(_WORD *)(a1 + 2388) = 6;
          *(_DWORD *)(a1 + 2390) = v15[2];
          *(_WORD *)(a1 + 2394) = *((_WORD *)v15 + 6);
          *(_DWORD *)(a1 + 2422) = v15[2];
          *(_WORD *)(a1 + 2426) = *((_WORD *)v15 + 6);
          v16 = AllocMem(*(_QWORD *)(a1 + 128), 224, v26, v27);
          if ( v16 )
          {
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_26;
            }
            v39 = 21;
          }
          else
          {
            v16 = CopyMpGeneralAttributes(*(_QWORD *)(a1 + 128), a1 + 2296, *v43);
            if ( v16 )
            {
              v28 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
              {
                goto LABEL_26;
              }
              v39 = 22;
            }
            else
            {
              v31 = (_OWORD **)v45;
              v16 = AllocMem(*(_QWORD *)(a1 + 128), 64, v30, v45);
              if ( !v16 )
              {
                v32 = *v31;
                if ( v41 )
                  v33 = *(_OWORD **)(a1 + 2536);
                else
                  v33 = *(_OWORD **)(a1 + 2520);
                *v32 = *v33;
                v32[1] = v33[1];
                v32[2] = v33[2];
                v32[3] = v33[3];
                if ( v11 )
                {
                  v34 = (_QWORD *)v44;
                  *(_OWORD *)(a1 + 2716) = *(_OWORD *)(v11 + 4);
                  *(_OWORD *)(a1 + 2732) = *(_OWORD *)(v11 + 20);
                  *(_OWORD *)(a1 + 2748) = *(_OWORD *)(v11 + 36);
                  *(_OWORD *)(a1 + 2764) = *(_OWORD *)(v11 + 52);
                  *(_OWORD *)(a1 + 2780) = *(_OWORD *)(v11 + 68);
                  *(_OWORD *)(a1 + 2796) = *(_OWORD *)(v11 + 84);
                  *(_OWORD *)(a1 + 2812) = *(_OWORD *)(v11 + 100);
                  *(_OWORD *)(a1 + 2828) = *(_OWORD *)(v11 + 116);
                  *(_OWORD *)(a1 + 2844) = *(_OWORD *)(v11 + 132);
                  *(_OWORD *)(a1 + 2860) = *(_OWORD *)(v11 + 148);
                  *(_OWORD *)(a1 + 2876) = *(_OWORD *)(v11 + 164);
                  *(_DWORD *)(a1 + 2892) = *((_DWORD *)v11 + 45);
                  *(_BYTE *)(a1 + 2896) = -96;
                  *(_BYTE *)(a1 + 2897) = 1;
                  *(_WORD *)(a1 + 2898) = 40;
                  *(_QWORD *)(a1 + 2912) = a1 + 2716;
                  *(_QWORD *)(a1 + 2904) = a1 + 2716;
                  *(_QWORD *)(a1 + 2920) = 0;
                  *(_QWORD *)(a1 + 2928) = 0;
                  *(_BYTE *)(a1 + 2712) = 1;
                  *v34 = a1 + 2896;
                }
                *v46 = a2;
                if ( *v25 != 1801678668 )
                {
                  DbgPrint("Trying to acquire uninited lock %p, %s, Line %d\n", v25, "FilterUnlock", 430);
                  __debugbreak();
                }
                v35 = *(_BYTE *)(a1 + 112);
                *(_QWORD *)(a1 + 88) = "FilterUnlock";
                *(_DWORD *)(a1 + 96) = 430;
                *(_BYTE *)(a1 + 32) = 0;
                KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 104), v35);
                _InterlockedDecrement((volatile signed __int32 *)(a1 + 28));
                goto LABEL_27;
              }
              v28 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
              {
LABEL_26:
                ReleaseSpinLock(a1 + 24, "FilterUnlock", 430, 0);
LABEL_27:
                v19 = 1;
                goto LABEL_28;
              }
              v39 = 23;
            }
          }
          WPP_SF_d(v28->AttachedDevice, v39, WPP_63d282d22d9e3f2cd53cfde58a2ac431_Traceguids);
          goto LABEL_26;
        }
      }
      else
      {
        v23 = AllocMem(*(_QWORD *)(a1 + 128), (unsigned int)VirtualAddress, v21, &v42);
        if ( v23 || (v11 = (char *)v42) == 0 )
          v11 = 0;
        else
          v23 = filterDoInternalRequest(a1, 0, 234947437, (_DWORD)v42, v22, 0);
        if ( v11 && v23 )
        {
          NdisFreeMemory(v11, 0, 0);
          v11 = 0;
        }
      }
    }
    v24 = a2;
    goto LABEL_21;
  }
  v16 = -1073741823;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_63d282d22d9e3f2cd53cfde58a2ac431_Traceguids);
LABEL_28:
  if ( v15 )
    NdisFreeMemory(v15, 0, 0);
  if ( v11 )
    NdisFreeMemory(v11, 0, 0);
  if ( v16 && v19 )
    FilterDeleteVirtualMac(a2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_63d282d22d9e3f2cd53cfde58a2ac431_Traceguids);
  return v16;
}

```

## disassembly

```asm
0x14000745c  mov     [rsp-8+arg_10], rbx
0x140007461  push    rbp
0x140007462  push    rsi
0x140007463  push    rdi
0x140007464  push    r12
0x140007466  push    r13
0x140007468  push    r14
0x14000746a  push    r15
0x14000746c  lea     rbp, [rsp-0C0h]
0x140007474  sub     rsp, 1C0h
0x14000747b  mov     rax, cs:__security_cookie
0x140007482  xor     rax, rsp
0x140007485  mov     [rbp+0F0h+var_40], rax
0x14000748c  mov     rax, [rbp+0F0h+arg_20]
0x140007493  mov     ebx, r8d
0x140007496  mov     [rsp+1F0h+var_188], rax
0x14000749b  mov     r13, rdx
0x14000749e  mov     rax, [rbp+0F0h+arg_28]
0x1400074a5  mov     r14, rcx
0x1400074a8  mov     [rsp+1F0h+var_178], rax
0x1400074ad  mov     rax, [rbp+0F0h+arg_30]
0x1400074b4  mov     [rsp+1F0h+var_180], rax
0x1400074b9  xor     eax, eax
0x1400074bb  mov     [rsp+1F0h+VirtualAddress], rax
0x1400074c0  mov     r15d, eax
0x1400074c3  mov     [rsp+1F0h+var_198], eax
0x1400074c7  mov     esi, eax
0x1400074c9  mov     [rsp+1F0h+var_190], rax
0x1400074ce  mov     [rbp+0F0h+var_170], r9
0x1400074d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400074d9  lea     rax, WPP_GLOBAL_Control
0x1400074e0  cmp     rcx, rax
0x1400074e3  jnz     loc_140007AFA
0x1400074e9  sub     ebx, 1
0x1400074ec  jnz     loc_140007B1F
0x1400074f2  lea     edi, [rbx+0Ch]
0x1400074f5  mov     rcx, [r14+80h]
0x1400074fc  lea     r9, [rsp+1F0h+VirtualAddress]
0x140007501  mov     edx, 10h
0x140007506  call    AllocMem
0x14000750b  mov     r12, [rsp+1F0h+VirtualAddress]
0x140007510  mov     ebx, eax
0x140007512  test    eax, eax
0x140007514  jnz     loc_140007B4F
0x14000751a  xorps   xmm0, xmm0
0x14000751d  lea     rcx, [rbp+0F0h+OidRequest]; void *
0x140007521  movups  xmmword ptr [r12], xmm0
0x140007526  mov     word ptr [r12], 180h
0x14000752d  xor     edx, edx; Val
0x14000752f  mov     [r12+4], edi
0x140007534  mov     r8d, 118h; Size
0x14000753a  mov     rbx, [r13+8]
0x14000753e  call    memset
0x140007543  mov     rcx, cs:WPP_GLOBAL_Control
0x14000754a  lea     rax, WPP_GLOBAL_Control
0x140007551  cmp     rcx, rax
0x140007554  jnz     loc_140007847
0x14000755a  xor     edx, edx; Val
0x14000755c  lea     rcx, [rbp+0F0h+OidRequest]; void *
0x140007560  mov     r8d, 0F8h; Size
0x140007566  call    memset
0x14000756b  lea     rcx, [rbp+0F0h+Event]; Event
0x140007572  call    cs:__imp_NdisInitializeEvent
0x140007579  nop     dword ptr [rax+rax+00h]
0x14000757e  mov     rcx, [rbx+80h]; NdisFilterHandle
0x140007585  lea     rdx, [rbp+0F0h+OidRequest]; OidRequest
0x140007589  mov     dword ptr [rbp+0F0h+OidRequest.Header.Type], 0EC0196h
0x140007590  mov     edi, 10h
0x140007595  mov     [rbp+0F0h+OidRequest.RequestType], 0Ch
0x14000759c  mov     dword ptr [rbp+0F0h+OidRequest.DATA], 0E040101h
0x1400075a3  mov     qword ptr [rbp+0F0h+OidRequest.DATA+14h], 10h
0x1400075ab  mov     qword ptr [rbp+0F0h+OidRequest.DATA+8], r12
0x1400075af  mov     dword ptr [rbp+0F0h+OidRequest.DATA+10h], 8
0x1400075b6  mov     [rbp+0F0h+OidRequest.RequestId], 52465756h
0x1400075be  call    cs:__imp_NdisFOidRequest
0x1400075c5  nop     dword ptr [rax+rax+00h]
0x1400075ca  mov     ebx, eax
0x1400075cc  cmp     eax, 103h
0x1400075d1  jnz     short loc_1400075EE
0x1400075d3  xor     edx, edx; MsToWait
0x1400075d5  lea     rcx, [rbp+0F0h+Event]; Event
0x1400075dc  call    cs:__imp_NdisWaitEvent
0x1400075e3  nop     dword ptr [rax+rax+00h]
0x1400075e8  mov     ebx, [rbp+0F0h+var_50]
0x1400075ee  test    ebx, ebx
0x1400075f0  jz      loc_140007A60
0x1400075f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400075fd  lea     rax, WPP_GLOBAL_Control
0x140007604  cmp     rcx, rax
0x140007607  jnz     loc_140007A49
0x14000760d  test    ebx, ebx
0x14000760f  jnz     loc_140007BAE
0x140007615  mov     dil, 1
0x140007618  mov     [rsp+1F0h+var_1B0], dil
0x14000761d  cmp     r15d, 10h
0x140007621  jb      loc_140007BC3
0x140007627  xor     edi, edi
0x140007629  mov     [r14+0A98h], dil
0x140007630  cmp     [rsp+1F0h+var_180], rdi
0x140007635  jz      loc_1400076E5
0x14000763b  cmp     [r14+0A79h], dil
0x140007642  jz      loc_1400076E5
0x140007648  lea     rax, [rsp+1F0h+VirtualAddress]
0x14000764d  mov     dword ptr [rsp+1F0h+VirtualAddress], edi
0x140007651  mov     [rsp+1F0h+var_1B8], rax
0x140007656  mov     r15d, 0E01036Dh
0x14000765c  mov     [rsp+1F0h+var_1C8], edi
0x140007660  xor     r9d, r9d
0x140007663  mov     r8d, r15d
0x140007666  mov     [rsp+1F0h+var_1D0], edi
0x14000766a  xor     edx, edx
0x14000766c  mov     rcx, r14
0x14000766f  call    filterDoInternalRequest
0x140007674  mov     ebx, dword ptr [rsp+1F0h+VirtualAddress]
0x140007678  mov     edx, eax
0x14000767a  cmp     eax, 80000005h
0x14000767f  jnz     loc_1400079FA
0x140007685  cmp     ebx, 0B8h
0x14000768b  jb      loc_140007A02
0x140007691  mov     rcx, [r14+80h]
0x140007698  lea     r9, [rsp+1F0h+var_190]
0x14000769d  mov     edx, ebx
0x14000769f  call    AllocMem
0x1400076a4  test    eax, eax
0x1400076a6  jnz     loc_140007AE6
0x1400076ac  mov     rsi, [rsp+1F0h+var_190]
0x1400076b1  test    rsi, rsi
0x1400076b4  jz      loc_140007AE6
0x1400076ba  lea     rax, [rsp+1F0h+VirtualAddress]
0x1400076bf  mov     r9, rsi
0x1400076c2  mov     [rsp+1F0h+var_1B8], rax
0x1400076c7  mov     r8d, r15d
0x1400076ca  mov     [rsp+1F0h+var_1C8], edi
0x1400076ce  xor     edx, edx
0x1400076d0  mov     rcx, r14
0x1400076d3  mov     [rsp+1F0h+var_1D0], ebx
0x1400076d7  call    filterDoInternalRequest
0x1400076dc  test    rsi, rsi
0x1400076df  jnz     loc_140007A70
0x1400076e5  lea     r15, WPP_GLOBAL_Control
0x1400076ec  mov     rbx, r13
0x1400076ef  lea     rdi, [r14+18h]
0x1400076f3  cmp     dword ptr [rdi], 6B636F4Ch
0x1400076f9  jnz     loc_140007C01
0x1400076ff  lock inc dword ptr [rdi+4]
0x140007703  lea     rcx, [rdi+50h]; SpinLock
0x140007707  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000770e  nop     dword ptr [rax+rax+00h]
0x140007713  mov     [rdi+58h], al
0x140007716  lea     rax, aFilterlock; "FilterLock"
0x14000771d  mov     [rdi+30h], rax
0x140007721  mov     byte ptr [rdi+8], 1
0x140007725  mov     dword ptr [rdi+38h], 1A7h
0x14000772c  mov     byte ptr [rbx+1], 1
0x140007730  mov     byte ptr [rbx+3], 1
0x140007734  mov     eax, [r12+4]
0x140007739  mov     [rbx+68h], eax
0x14000773c  mov     rcx, cs:WPP_GLOBAL_Control
0x140007743  cmp     rcx, r15
0x140007746  jnz     loc_140007A94
0x14000774c  mov     r9, [rsp+1F0h+var_188]
0x140007751  lea     r15, [r14+8F8h]
0x140007758  mov     word ptr [r15+5Ch], 6
0x14000775f  mov     edx, 0E0h
0x140007764  mov     eax, [r12+8]
0x140007769  mov     [r15+5Eh], eax
0x14000776d  movzx   eax, word ptr [r12+0Ch]
0x140007773  mov     [r15+62h], ax
0x140007778  mov     eax, [r12+8]
0x14000777d  mov     [r15+7Eh], eax
0x140007781  movzx   eax, word ptr [r12+0Ch]
0x140007787  mov     [r15+82h], ax
0x14000778f  mov     rcx, [r14+80h]
0x140007796  call    AllocMem
0x14000779b  mov     ebx, eax
0x14000779d  test    eax, eax
0x14000779f  jz      loc_14000786C
0x1400077a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400077ac  lea     rax, WPP_GLOBAL_Control
0x1400077b3  cmp     rcx, rax
0x1400077b6  jnz     loc_140007C2A
0x1400077bc  xor     r9d, r9d
0x1400077bf  lea     rdx, aFilterunlock; "FilterUnlock"
0x1400077c6  mov     r8d, 1AEh
0x1400077cc  mov     rcx, rdi
0x1400077cf  call    ReleaseSpinLock
0x1400077d4  mov     dil, [rsp+1F0h+var_1B0]
0x1400077d9  test    r12, r12
0x1400077dc  jz      short loc_1400077F2
0x1400077de  xor     r8d, r8d; MemoryFlags
0x1400077e1  xor     edx, edx; Length
0x1400077e3  mov     rcx, r12; VirtualAddress
0x1400077e6  call    cs:__imp_NdisFreeMemory
0x1400077ed  nop     dword ptr [rax+rax+00h]
0x1400077f2  test    rsi, rsi
0x1400077f5  jnz     loc_140007CC9
0x1400077fb  test    ebx, ebx
0x1400077fd  jnz     loc_140007CE2
0x140007803  mov     rcx, cs:WPP_GLOBAL_Control
0x14000780a  lea     rax, WPP_GLOBAL_Control
0x140007811  cmp     rcx, rax
0x140007814  jnz     loc_140007ABE
0x14000781a  mov     eax, ebx
0x14000781c  mov     rcx, [rbp+0F0h+var_40]
0x140007823  xor     rcx, rsp; StackCookie
0x140007826  call    __security_check_cookie
0x14000782b  mov     rbx, [rsp+1F0h+arg_10]
0x140007833  add     rsp, 1C0h
0x14000783a  pop     r15
0x14000783c  pop     r14
0x14000783e  pop     r13
0x140007840  pop     r12
0x140007842  pop     rdi
0x140007843  pop     rsi
0x140007844  pop     rbp
0x140007845  retn
0x140007847  mov     eax, [rcx+2Ch]
0x14000784a  test    al, 20h
0x14000784c  jz      loc_14000755A
0x140007852  mov     rcx, [rcx+18h]
0x140007856  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000785d  mov     edx, 0EDh
0x140007862  call    WPP_SF_
0x140007867  jmp     loc_14000755A
0x14000786c  mov     rax, [rsp+1F0h+var_188]
0x140007871  mov     rdx, r15
0x140007874  mov     rcx, [r14+80h]
0x14000787b  mov     r8, [rax]
0x14000787e  call    CopyMpGeneralAttributes
0x140007883  mov     ebx, eax
0x140007885  test    eax, eax
0x140007887  jnz     loc_140007C3C
0x14000788d  mov     r15, [rsp+1F0h+var_178]
0x140007892  lea     edx, [rax+40h]
0x140007895  mov     rcx, [r14+80h]
0x14000789c  mov     r9, r15
0x14000789f  call    AllocMem
0x1400078a4  mov     ebx, eax
0x1400078a6  test    eax, eax
0x1400078a8  jnz     loc_140007C65
0x1400078ae  mov     rcx, [r15]
0x1400078b1  cmp     [rsp+1F0h+var_198], eax
0x1400078b5  jnz     loc_140007AEE
0x1400078bb  mov     rax, [r14+9D8h]
0x1400078c2  movups  xmm0, xmmword ptr [rax]
0x1400078c5  movups  xmmword ptr [rcx], xmm0
0x1400078c8  movups  xmm1, xmmword ptr [rax+10h]
0x1400078cc  movups  xmmword ptr [rcx+10h], xmm1
0x1400078d0  movups  xmm0, xmmword ptr [rax+20h]
0x1400078d4  movups  xmmword ptr [rcx+20h], xmm0
0x1400078d8  movups  xmm1, xmmword ptr [rax+30h]
0x1400078dc  movups  xmmword ptr [rcx+30h], xmm1
0x1400078e0  test    rsi, rsi
0x1400078e3  jz      loc_1400079B5
0x1400078e9  movups  xmm0, xmmword ptr [rsi+4]
0x1400078ed  mov     rdx, [rsp+1F0h+var_180]
0x1400078f2  lea     rcx, [r14+0A9Ch]
0x1400078f9  movups  xmmword ptr [rcx], xmm0
0x1400078fc  movups  xmm1, xmmword ptr [rsi+14h]
0x140007900  movups  xmmword ptr [rcx+10h], xmm1
0x140007904  movups  xmm0, xmmword ptr [rsi+24h]
0x140007908  movups  xmmword ptr [rcx+20h], xmm0
0x14000790c  movups  xmm1, xmmword ptr [rsi+34h]
0x140007910  movups  xmmword ptr [rcx+30h], xmm1
0x140007914  movups  xmm0, xmmword ptr [rsi+44h]
0x140007918  movups  xmmword ptr [rcx+40h], xmm0
0x14000791c  movups  xmm1, xmmword ptr [rsi+54h]
0x140007920  movups  xmmword ptr [rcx+50h], xmm1
0x140007924  movups  xmm0, xmmword ptr [rsi+64h]
0x140007928  movups  xmmword ptr [rcx+60h], xmm0
0x14000792c  movups  xmm1, xmmword ptr [rsi+74h]
0x140007930  movups  xmmword ptr [rcx+70h], xmm1
0x140007934  movups  xmm0, xmmword ptr [rsi+84h]
0x14000793b  movups  xmmword ptr [rcx+80h], xmm0
0x140007942  movups  xmm1, xmmword ptr [rsi+94h]
0x140007949  movups  xmmword ptr [rcx+90h], xmm1
0x140007950  movups  xmm0, xmmword ptr [rsi+0A4h]
0x140007957  movups  xmmword ptr [rcx+0A0h], xmm0
0x14000795e  mov     eax, [rsi+0B4h]
0x140007964  mov     [rcx+0B0h], eax
0x14000796a  lea     rax, [r14+0B50h]
0x140007971  mov     byte ptr [rax], 0A0h
0x140007974  mov     byte ptr [r14+0B51h], 1
0x14000797c  mov     word ptr [r14+0B52h], 28h ; '('
0x140007986  mov     [r14+0B60h], rcx
0x14000798d  mov     [r14+0B58h], rcx
0x140007994  mov     qword ptr [r14+0B68h], 0
0x14000799f  mov     qword ptr [r14+0B70h], 0
0x1400079aa  mov     byte ptr [r14+0A98h], 1
0x1400079b2  mov     [rdx], rax
0x1400079b5  mov     rdx, [rbp+0F0h+var_170]
0x1400079b9  lea     r14, aFilterunlock; "FilterUnlock"
0x1400079c0  mov     [rdx], r13
0x1400079c3  cmp     dword ptr [rdi], 6B636F4Ch
0x1400079c9  jnz     loc_140007CA4
0x1400079cf  mov     dl, [rdi+58h]; NewIrql
0x1400079d2  lea     rcx, [rdi+50h]; SpinLock
0x1400079d6  mov     [rdi+40h], r14
0x1400079da  mov     dword ptr [rdi+48h], 1AEh
0x1400079e1  mov     byte ptr [rdi+8], 0
  ... truncated ...
```
