# SrvNetCloseEndpoint

- ea: `0x1400105e0`
- end: `0x1400109a0`
- name: `SrvNetCloseEndpoint`
- size: `960`
- prototype: ``
- caller_count: `6`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140010b60`
- `0x14001f740`
- `0x140041c44`
- `0x140042524`
- `0x140043178`
- `0x140054c20`

## callees

- `0x140008144`
- `0x14000b360`
- `0x14000b480`
- `0x14000b830`
- `0x14000d800`
- `0x1400105e0`
- `0x140013c50`
- `0x140015790`
- `0x140015c80`
- `0x140015ee4`
- `0x140016c84`
- `0x14001ab70`
- `0x140043178`
- `0x1400456b8`
- `0x140046058`
- `0x140046aa0`
- `0x14004956c`
- `0x140051710`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140010616`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010675`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400108f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010616`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010675`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400108f2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010827`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010827`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010758`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010774`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010758`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010774`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010743`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010743`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400105fc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001089a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400105fc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001089a`
- `ntoskrnl!ExRundownCompleted` at `0x1400106a7`
- `ntoskrnl!ExRundownCompleted` at `0x1400106d4`
- `ntoskrnl!ExRundownCompleted` at `0x1400106a7`
- `ntoskrnl!ExRundownCompleted` at `0x1400106d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010808`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001081b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010808`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001081b`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001068b`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400106c4`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001068b`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400106c4`

## pseudocode

```c
void __fastcall SrvNetCloseEndpoint(__int64 *a1)
{
  KSPIN_LOCK *v1; // rsi
  KIRQL v3; // al
  int v4; // edx
  int v5; // r8d
  __int64 v6; // r14
  struct _EX_RUNDOWN_REF v7; // rcx
  __int64 **v8; // rax
  bool v9; // r15
  __int64 v10; // r8
  __int64 v11; // r9
  KIRQL v12; // r9
  _QWORD *v13; // rdx
  int v14; // ecx
  __int64 v15; // rax
  __int64 v16; // rcx
  void *v17; // rbx
  _QWORD v18[2]; // [rsp+40h] [rbp-10h] BYREF

  v1 = (KSPIN_LOCK *)(a1 + 3);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 3);
  if ( *((_BYTE *)a1 + 145) )
  {
    KeReleaseSpinLock(v1, v3);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids, a1);
    }
  }
  else
  {
    *((_BYTE *)a1 + 145) = 1;
    KeReleaseSpinLock(v1, v3);
    if ( !*((_DWORD *)a1 + 31) )
    {
      ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)a1 + 8);
      v6 = a1[4];
      a1[4] = 0;
      ExRundownCompleted((PEX_RUNDOWN_REF)a1 + 8);
      if ( v6 )
      {
        SrvNetDereferenceHandle(v6);
        ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)a1 + 7);
        ExRundownCompleted((PEX_RUNDOWN_REF)a1 + 7);
      }
    }
    switch ( *((_DWORD *)a1 + 31) )
    {
      case 1:
        SrvNetClearInterfaceEndpoint(a1);
        SrvNetWskCloseListenSocket(a1);
        break;
      case 2:
        if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x80000) != 0 )
          McTemplateK0qqhzr2_EtwWriteTransfer(
            *((_WORD *)a1 + 36) >> 1,
            v4,
            v5,
            0,
            *((_DWORD *)a1 + 12),
            *((_WORD *)a1 + 36) >> 1,
            a1[10]);
        SrvNetRdmaCloseListener(a1);
        break;
      case 4:
        SrvNetQUICListenerClose(a1);
        break;
    }
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(SrvNetDeviceExtension, 1u);
    ExAcquireResourceExclusiveLite((PERESOURCE)((char *)SrvNetDeviceExtension + 288), 1u);
    v7.Count = *a1;
    if ( *(__int64 **)(*a1 + 8) != a1 || (v8 = (__int64 **)a1[1], *v8 != a1) )
LABEL_46:
      __fastfail(3u);
    *v8 = (__int64 *)v7.Count;
    v9 = 0;
    *(_QWORD *)(v7.Count + 8) = v8;
    a1[1] = (__int64)a1;
    *a1 = (__int64)a1;
    *((_BYTE *)a1 + 146) = 1;
    if ( *((_BYTE *)a1 + 121) )
      v9 = _InterlockedAdd((volatile signed __int32 *)&SrvNetDeviceExtension[4].ExclusiveWaiters + 1, 0xFFFFFFFF) == 0;
    if ( *((_BYTE *)a1 + 120) )
    {
      _InterlockedDecrement((volatile signed __int32 *)&SrvNetDeviceExtension[4].ExclusiveWaiters);
      SrvNetClearAndFreeInterfaceTable((PRTL_DYNAMIC_HASH_TABLE)(a1 + 36));
      SrvNetClearAndFreeInterfaceTable((PRTL_DYNAMIC_HASH_TABLE)(a1 + 41));
    }
    ExReleaseResourceLite((PERESOURCE)((char *)SrvNetDeviceExtension + 288));
    ExReleaseResourceLite(SrvNetDeviceExtension);
    KeLeaveCriticalRegion();
    SrvNetDisconnectSelectedEndpointConnections(a1, 0, 0);
    SrvNetNotifyClientsOfEndpoint(a1, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids);
    }
    SrvNetEndpointProcessDisconnects(a1);
    v18[1] = v18;
    v18[0] = v18;
    LOBYTE(v11) = KeAcquireSpinLockRaiseToDpc(v1);
    if ( !*((_DWORD *)a1 + 31) )
      RfsAppendList(v18, a1 + 24, v10, v11);
    RfsAppendList(v18, a1 + 26, v10, v11);
    v13 = (_QWORD *)v18[0];
    v14 = 0;
    while ( v13 != v18 )
    {
      v13 = (_QWORD *)*v13;
      ++v14;
    }
    *((_DWORD *)a1 + 42) -= v14;
    KeReleaseSpinLock(v1, v12);
    while ( 1 )
    {
      v15 = v18[0];
      if ( (_QWORD *)v18[0] == v18 )
        break;
      if ( *(_QWORD **)(v18[0] + 8LL) != v18 )
        goto LABEL_46;
      v16 = *(_QWORD *)v18[0];
      if ( *(_QWORD *)(*(_QWORD *)v18[0] + 8LL) != v18[0] )
        goto LABEL_46;
      v18[0] = *(_QWORD *)v18[0];
      v17 = (void *)(v15 - 512);
      *(_QWORD *)(v16 + 8) = v18;
      if ( !*(_DWORD *)(v15 - 512 + 480) )
        SrvNetTdiCloseConnection(v15 - 512);
      SrvNetFreeConnection(v17);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids);
    }
    SrvNetDereferenceEndpoint(a1);
    if ( v9 )
      SrvNetFreeUniversalAndRdmaEndpoints();
  }
}

```

## disassembly

```asm
0x1400105e0  push    rbp
0x1400105e2  push    rbx
0x1400105e3  push    rsi
0x1400105e4  push    rdi
0x1400105e5  push    r12
0x1400105e7  push    r14
0x1400105e9  push    r15
0x1400105eb  mov     rbp, rsp
0x1400105ee  sub     rsp, 50h
0x1400105f2  lea     rsi, [rcx+18h]
0x1400105f6  mov     rdi, rcx
0x1400105f9  mov     rcx, rsi; SpinLock
0x1400105fc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010603  nop     dword ptr [rax+rax+00h]
0x140010608  cmp     byte ptr [rdi+91h], 0
0x14001060f  mov     rcx, rsi; SpinLock
0x140010612  mov     dl, al; NewIrql
0x140010614  jz      short loc_14001066A
0x140010616  call    cs:__imp_KeReleaseSpinLock
0x14001061d  nop     dword ptr [rax+rax+00h]
0x140010622  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140010629  lea     r12, WPP_GLOBAL_Control
0x140010630  cmp     rcx, r12
0x140010633  jz      short loc_14001065A
0x140010635  bt      dword ptr [rcx+2Ch], 8
0x14001063a  jnb     short loc_14001065A
0x14001063c  cmp     byte ptr [rcx+29h], 2
0x140010640  jb      short loc_14001065A
0x140010642  mov     rcx, [rcx+18h]
0x140010646  lea     r8, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids
0x14001064d  mov     edx, 32h ; '2'
0x140010652  mov     r9, rdi
0x140010655  call    WPP_SF_q
0x14001065a  add     rsp, 50h
0x14001065e  pop     r15
0x140010660  pop     r14
0x140010662  pop     r12
0x140010664  pop     rdi
0x140010665  pop     rsi
0x140010666  pop     rbx
0x140010667  pop     rbp
0x140010668  retn
0x14001066a  mov     ebx, 1
0x14001066f  mov     [rdi+91h], bl
0x140010675  call    cs:__imp_KeReleaseSpinLock
0x14001067c  nop     dword ptr [rax+rax+00h]
0x140010681  cmp     dword ptr [rdi+7Ch], 0
0x140010685  jnz     short loc_1400106E0
0x140010687  lea     rcx, [rdi+40h]; RunRef
0x14001068b  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140010692  nop     dword ptr [rax+rax+00h]
0x140010697  mov     r14, [rdi+20h]
0x14001069b  lea     rcx, [rdi+40h]; RunRef
0x14001069f  mov     qword ptr [rdi+20h], 0
0x1400106a7  call    cs:__imp_ExRundownCompleted
0x1400106ae  nop     dword ptr [rax+rax+00h]
0x1400106b3  test    r14, r14
0x1400106b6  jz      short loc_1400106E0
0x1400106b8  mov     rcx, r14
0x1400106bb  call    SrvNetDereferenceHandle
0x1400106c0  lea     rcx, [rdi+38h]; RunRef
0x1400106c4  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400106cb  nop     dword ptr [rax+rax+00h]
0x1400106d0  lea     rcx, [rdi+38h]; RunRef
0x1400106d4  call    cs:__imp_ExRundownCompleted
0x1400106db  nop     dword ptr [rax+rax+00h]
0x1400106e0  mov     ecx, [rdi+7Ch]
0x1400106e3  sub     ecx, 1
0x1400106e6  jz      short loc_140010733
0x1400106e8  sub     ecx, 1
0x1400106eb  jz      short loc_1400106FC
0x1400106ed  cmp     ecx, 2
0x1400106f0  jnz     short loc_140010743
0x1400106f2  mov     rcx, rdi
0x1400106f5  call    SrvNetQUICListenerClose
0x1400106fa  jmp     short loc_140010743
0x1400106fc  test    byte ptr cs:WPP_MAIN_CB.Queue+12h, 8
0x140010703  jz      short loc_140010729
0x140010705  mov     rax, [rdi+50h]
0x140010709  xor     r9d, r9d
0x14001070c  movzx   ecx, word ptr [rdi+48h]
0x140010710  mov     [rsp+50h+var_20], rax
0x140010715  mov     eax, [rdi+30h]
0x140010718  shr     cx, 1
0x14001071b  mov     [rsp+50h+var_28], cx
0x140010720  mov     [rsp+50h+var_30], eax
0x140010724  call    McTemplateK0qqhzr2_EtwWriteTransfer
0x140010729  mov     rcx, rdi
0x14001072c  call    SrvNetRdmaCloseListener
0x140010731  jmp     short loc_140010743
0x140010733  mov     rcx, rdi
0x140010736  call    SrvNetClearInterfaceEndpoint
0x14001073b  mov     rcx, rdi
0x14001073e  call    SrvNetWskCloseListenSocket
0x140010743  call    cs:__imp_KeEnterCriticalRegion
0x14001074a  nop     dword ptr [rax+rax+00h]
0x14001074f  mov     rcx, cs:SrvNetDeviceExtension; Resource
0x140010756  mov     dl, bl; Wait
0x140010758  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001075f  nop     dword ptr [rax+rax+00h]
0x140010764  mov     rcx, cs:SrvNetDeviceExtension
0x14001076b  mov     dl, bl; Wait
0x14001076d  add     rcx, 120h; Resource
0x140010774  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001077b  nop     dword ptr [rax+rax+00h]
0x140010780  mov     rcx, [rdi]
0x140010783  cmp     [rcx+8], rdi
0x140010787  jnz     loc_140010999
0x14001078d  mov     rax, [rdi+8]
0x140010791  cmp     [rax], rdi
0x140010794  jnz     loc_140010999
0x14001079a  mov     [rax], rcx
0x14001079d  xor     r15b, r15b
0x1400107a0  mov     [rcx+8], rax
0x1400107a4  mov     [rdi+8], rdi
0x1400107a8  mov     [rdi], rdi
0x1400107ab  mov     [rdi+92h], bl
0x1400107b1  cmp     [rdi+79h], r15b
0x1400107b5  jz      short loc_1400107CE
0x1400107b7  mov     rcx, cs:SrvNetDeviceExtension
0x1400107be  lock add dword ptr [rcx+1CCh], 0FFFFFFFFh
0x1400107c6  movzx   r15d, r15b
0x1400107ca  cmovz   r15d, ebx
0x1400107ce  cmp     byte ptr [rdi+78h], 0
0x1400107d2  jz      short loc_1400107FA
0x1400107d4  mov     rax, cs:SrvNetDeviceExtension
0x1400107db  lea     rcx, [rdi+120h]; HashTable
0x1400107e2  lock dec dword ptr [rax+1C8h]
0x1400107e9  call    SrvNetClearAndFreeInterfaceTable
0x1400107ee  lea     rcx, [rdi+148h]; HashTable
0x1400107f5  call    SrvNetClearAndFreeInterfaceTable
0x1400107fa  mov     rcx, cs:SrvNetDeviceExtension
0x140010801  add     rcx, 120h; Resource
0x140010808  call    cs:__imp_ExReleaseResourceLite
0x14001080f  nop     dword ptr [rax+rax+00h]
0x140010814  mov     rcx, cs:SrvNetDeviceExtension; Resource
0x14001081b  call    cs:__imp_ExReleaseResourceLite
0x140010822  nop     dword ptr [rax+rax+00h]
0x140010827  call    cs:__imp_KeLeaveCriticalRegion
0x14001082e  nop     dword ptr [rax+rax+00h]
0x140010833  xor     r8d, r8d
0x140010836  xor     edx, edx
0x140010838  mov     rcx, rdi
0x14001083b  call    SrvNetDisconnectSelectedEndpointConnections
0x140010840  xor     edx, edx
0x140010842  mov     rcx, rdi
0x140010845  call    SrvNetNotifyClientsOfEndpoint
0x14001084a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140010851  lea     r12, WPP_GLOBAL_Control
0x140010858  cmp     rcx, r12
0x14001085b  jz      short loc_14001087F
0x14001085d  bt      dword ptr [rcx+2Ch], 8
0x140010862  jnb     short loc_14001087F
0x140010864  cmp     byte ptr [rcx+29h], 2
0x140010868  jb      short loc_14001087F
0x14001086a  mov     rcx, [rcx+18h]
0x14001086e  lea     r8, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids
0x140010875  mov     edx, 33h ; '3'
0x14001087a  call    WPP_SF_
0x14001087f  mov     rcx, rdi
0x140010882  call    SrvNetEndpointProcessDisconnects
0x140010887  lea     rax, [rbp+var_10]
0x14001088b  mov     rcx, rsi; SpinLock
0x14001088e  mov     [rbp+var_8], rax
0x140010892  lea     rax, [rbp+var_10]
0x140010896  mov     [rbp+var_10], rax
0x14001089a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400108a1  nop     dword ptr [rax+rax+00h]
0x1400108a6  cmp     dword ptr [rdi+7Ch], 0
0x1400108aa  mov     r9b, al
0x1400108ad  jnz     short loc_1400108BF
0x1400108af  lea     rdx, [rdi+0C0h]
0x1400108b6  lea     rcx, [rbp+var_10]
0x1400108ba  call    RfsAppendList
0x1400108bf  lea     rdx, [rdi+0D0h]
0x1400108c6  lea     rcx, [rbp+var_10]
0x1400108ca  call    RfsAppendList
0x1400108cf  mov     rdx, [rbp+var_10]
0x1400108d3  xor     ecx, ecx
0x1400108d5  jmp     short loc_1400108DD
0x1400108d7  mov     rdx, [rdx]
0x1400108da  add     rcx, rbx
0x1400108dd  lea     rax, [rbp+var_10]
0x1400108e1  cmp     rdx, rax
0x1400108e4  jnz     short loc_1400108D7
0x1400108e6  sub     [rdi+0A8h], ecx
0x1400108ec  mov     dl, r9b; NewIrql
0x1400108ef  mov     rcx, rsi; SpinLock
0x1400108f2  call    cs:__imp_KeReleaseSpinLock
0x1400108f9  nop     dword ptr [rax+rax+00h]
0x1400108fe  mov     rax, [rbp+var_10]
0x140010902  lea     rcx, [rbp+var_10]
0x140010906  cmp     rax, rcx
0x140010909  jz      short loc_140010950
0x14001090b  lea     rcx, [rbp+var_10]
0x14001090f  cmp     [rax+8], rcx
0x140010913  jnz     loc_140010999
0x140010919  mov     rcx, [rax]
0x14001091c  cmp     [rcx+8], rax
0x140010920  jnz     short loc_140010999
0x140010922  mov     [rbp+var_10], rcx
0x140010926  lea     rdx, [rbp+var_10]
0x14001092a  lea     rbx, [rax-200h]
0x140010931  mov     [rcx+8], rdx
0x140010935  cmp     dword ptr [rbx+1E0h], 0
0x14001093c  jnz     short loc_140010946
0x14001093e  mov     rcx, rbx
0x140010941  call    SrvNetTdiCloseConnection
0x140010946  mov     rcx, rbx; P
0x140010949  call    SrvNetFreeConnection
0x14001094e  jmp     short loc_1400108FE
0x140010950  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140010957  cmp     rcx, r12
0x14001095a  jz      short loc_14001097E
0x14001095c  bt      dword ptr [rcx+2Ch], 8
0x140010961  jnb     short loc_14001097E
0x140010963  cmp     byte ptr [rcx+29h], 2
0x140010967  jb      short loc_14001097E
0x140010969  mov     rcx, [rcx+18h]
0x14001096d  lea     r8, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids
0x140010974  mov     edx, 34h ; '4'
0x140010979  call    WPP_SF_
0x14001097e  mov     rcx, rdi
0x140010981  call    SrvNetDereferenceEndpoint
0x140010986  test    r15b, r15b
0x140010989  jz      loc_14001065A
0x14001098f  call    SrvNetFreeUniversalAndRdmaEndpoints
0x140010994  jmp     loc_14001065A
0x140010999  mov     ecx, 3
0x14001099e  int     29h; Win8: RtlFailFast(ecx)
```
