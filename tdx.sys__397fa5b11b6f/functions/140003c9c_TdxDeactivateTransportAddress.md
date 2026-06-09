# TdxDeactivateTransportAddress

- ea: `0x140003c9c`
- end: `0x1400042ce`
- name: `TdxDeactivateTransportAddress`
- size: `1586`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400042e0`
- `0x140017ad0`

## callees

- `0x140003590`
- `0x140003c9c`
- `0x1400047d0`
- `0x1400054ec`
- `0x140008620`
- `0x1400087a0`
- `0x14000f4f0`
- `0x14000fc90`
- `0x140012a8c`
- `0x140012b8c`
- `0x14001303c`
- `0x1400184b0`
- `0x140018590`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140004016`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140004016`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140004006`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140004006`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x140003daa`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x140003daa`
- `ntoskrnl!KeDelayExecutionThread` at `0x140003d6a`
- `ntoskrnl!KeDelayExecutionThread` at `0x140003d6a`
- `ntoskrnl!IofCompleteRequest` at `0x140004055`
- `ntoskrnl!IofCompleteRequest` at `0x1400041e2`
- `ntoskrnl!IofCompleteRequest` at `0x14000424f`
- `ntoskrnl!IofCompleteRequest` at `0x140004055`
- `ntoskrnl!IofCompleteRequest` at `0x1400041e2`
- `ntoskrnl!IofCompleteRequest` at `0x14000424f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003f48`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003f48`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140003e1c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004025`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400040c5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140003e1c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004025`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400040c5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003e0c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003ff5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400040e9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003e0c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003ff5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400040e9`
- `ntoskrnl!KeInitializeEvent` at `0x140003e89`
- `ntoskrnl!KeInitializeEvent` at `0x140003e89`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003cee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003d79`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003f61`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004095`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400041f3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000425e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003cee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003d79`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003f61`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004095`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400041f3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000425e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003d1e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003d4e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003dfe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003e3d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004036`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000422f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000427c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003d1e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003d4e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003dfe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003e3d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004036`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000422f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000427c`

## pseudocode

```c
void __fastcall TdxDeactivateTransportAddress(int *a1)
{
  KSPIN_LOCK *v1; // rsi
  KIRQL v3; // al
  IRP *v4; // r12
  int v5; // ecx
  KIRQL v6; // r15
  unsigned int v7; // r14d
  char v8; // bl
  KSPIN_LOCK *v9; // r14
  __int64 v10; // r9
  __int64 v11; // rcx
  unsigned int (__fastcall **v12)(__int64, __int128 *); // rax
  KIRQL v13; // al
  _QWORD *v14; // rcx
  char v15; // r8
  _QWORD *v16; // rdx
  KIRQL v17; // bl
  _QWORD *v18; // r10
  bool v19; // zf
  _QWORD *v20; // r9
  _QWORD *v21; // rax
  __int128 *v22; // rbx
  IRP *v23; // rcx
  KIRQL v24; // al
  _QWORD *v25; // r14
  _QWORD *v26; // rcx
  KIRQL v27; // r15
  _QWORD *v28; // rbx
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rax
  IRP *v33; // rcx
  _QWORD **v34; // r14
  _QWORD *v35; // rbx
  _QWORD *v36; // rax
  _QWORD *v37; // rcx
  KIRQL Irql[8]; // [rsp+30h] [rbp-89h] BYREF
  __int128 v39; // [rsp+38h] [rbp-81h] BYREF
  _QWORD v40[2]; // [rsp+48h] [rbp-71h] BYREF
  __int128 v41; // [rsp+58h] [rbp-61h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+68h] [rbp-51h] BYREF
  IRP *v43; // [rsp+70h] [rbp-49h]
  struct _KEVENT Event; // [rsp+78h] [rbp-41h] BYREF
  PVOID Object[2]; // [rsp+90h] [rbp-29h] BYREF
  __int128 v46; // [rsp+A0h] [rbp-19h]
  int v47; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v48; // [rsp+B4h] [rbp-5h]

  v1 = (KSPIN_LOCK *)(a1 + 2);
  v41 = 0;
  memset(&Event, 0, sizeof(Event));
  *(_OWORD *)Object = 0;
  v46 = 0;
  v39 = 0;
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 1);
  v4 = (IRP *)*((_QWORD *)a1 + 67);
  v5 = *a1;
  v6 = v3;
  v43 = v4;
  *((_QWORD *)a1 + 67) = 0;
  if ( (v5 & 4) == 0 )
  {
    KeReleaseSpinLock(v1, v3);
    return;
  }
  v7 = 0;
  v8 = 0;
  if ( a1[136] )
  {
    do
    {
      KeReleaseSpinLock(v1, v6);
      Interval.QuadPart = -10000;
      KeDelayExecutionThread(0, 0, &Interval);
      ++v7;
      v6 = KeAcquireSpinLockRaiseToDpc(v1);
      if ( v7 >= 0x2710 && !v8 )
      {
        v47 = 60534448;
        v8 = 1;
        v48 = 1;
        RtlLogUnexpectedCodepath(&v47);
      }
    }
    while ( a1[136] );
    v4 = v43;
  }
  *a1 &= ~4u;
  if ( (*a1 & 0x20) != 0 )
  {
    v9 = (KSPIN_LOCK *)*((_QWORD *)a1 + 63);
  }
  else if ( (*a1 & 0x40) != 0 )
  {
    v9 = (KSPIN_LOCK *)*((_QWORD *)a1 + 64);
  }
  else
  {
    v9 = 0;
  }
  *((_QWORD *)a1 + 63) = 0;
  *((_QWORD *)a1 + 64) = 0;
  if ( v9 )
  {
    KeReleaseSpinLockFromDpcLevel(v1);
    KeAcquireSpinLockAtDpcLevel(v9 + 1);
    v9[63] = 0;
    v9[64] = 0;
    KeReleaseSpinLock(v9 + 1, v6);
    DbgTdxDereferenceTransportAddress(v9, "minio\\netio\\session\\tdi\\address.c", 1158);
    DbgTdxDereferenceTransportAddress(a1, "minio\\netio\\session\\tdi\\address.c", 1159);
  }
  else
  {
    KeReleaseSpinLock(v1, v6);
  }
  Object[0] = &Event;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v10 = *((_QWORD *)a1 + 40);
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids, v10);
    }
    *(_QWORD *)&v41 = TdxSynchronousTlRequestComplete;
    *((_QWORD *)&v41 + 1) = Object;
    if ( (*a1 & 2) != 0 )
    {
      v11 = *((_QWORD *)a1 + 40);
LABEL_27:
      v12 = (unsigned int (__fastcall **)(__int64, __int128 *))*((_QWORD *)a1 + 41);
LABEL_28:
      if ( (*v12)(v11, &v41) == 259 )
        KeWaitForSingleObject(Object[0], Executive, 0, 0, 0);
      goto LABEL_30;
    }
    if ( (*a1 & 0x20) == 0 || *((_QWORD *)a1 + 42) )
    {
      v12 = (unsigned int (__fastcall **)(__int64, __int128 *))*((_QWORD *)a1 + 42);
      v11 = *((_QWORD *)a1 + 40);
      if ( v12 )
        goto LABEL_28;
      goto LABEL_27;
    }
  }
LABEL_30:
  if ( (*a1 & 2) != 0 )
  {
    v13 = KeAcquireSpinLockRaiseToDpc(v1);
    v14 = a1 + 84;
    v15 = 0;
    v16 = (_QWORD *)*((_QWORD *)a1 + 42);
    v17 = v13;
    *((_QWORD *)&v39 + 1) = &v39;
    *(_QWORD *)&v39 = &v39;
    while ( v16 != v14 )
    {
      v18 = (_QWORD *)*v16;
      v19 = _InterlockedExchange64(v16 - 8, 0) == 0;
      *((_DWORD *)v16 - 30) = -1073741536;
      *(v16 - 14) = 0;
      v20 = (_QWORD *)*((_QWORD *)&v39 + 1);
      if ( v19 )
        v15 = 1;
      if ( **((__int128 ***)&v39 + 1) != &v39 )
        goto LABEL_64;
      v21 = v16;
      v16 = v18;
      *v21 = &v39;
      v21[1] = v20;
      *v20 = v21;
      *((_QWORD *)&v39 + 1) = v21;
    }
    *((_QWORD *)a1 + 43) = a1 + 84;
    *v14 = v14;
    if ( v15 )
    {
      Irql[0] = 0;
      KeReleaseSpinLockFromDpcLevel(v1);
      IoAcquireCancelSpinLock(Irql);
      IoReleaseCancelSpinLock(Irql[0]);
      KeAcquireSpinLockAtDpcLevel(v1);
    }
    KeReleaseSpinLock(v1, v17);
    v22 = (__int128 *)v39;
    while ( v22 != &v39 )
    {
      v23 = (IRP *)((char *)v22 - 168);
      v22 = *(__int128 **)v22;
      IofCompleteRequest(v23, 2);
      DbgTdxDereferenceTransportAddress(a1, "minio\\netio\\session\\tdi\\address.c", 1268);
    }
  }
  else
  {
    v40[1] = v40;
    v40[0] = v40;
    v24 = KeAcquireSpinLockRaiseToDpc(v1);
    v25 = a1 + 94;
    while ( 1 )
    {
      v26 = (_QWORD *)*v25;
      v27 = v24;
      if ( (_QWORD *)*v25 == v25 )
        break;
      v28 = v26 - 34;
      KeAcquireSpinLockAtDpcLevel(v26 - 33);
      DbgTdxReferenceConnection(v28, "TdxDeactivateTransportAddress", 1296);
      KeReleaseSpinLockFromDpcLevel(v1);
      TdxTraceConnectionRoutine(v28, "TdxDeactivateTransportAddress");
      v30 = 512;
      if ( (*(_DWORD *)v28 & 0x200) != 0 || !v28[36] )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          WPP_SF_sq(
            WPP_GLOBAL_Control->AttachedDevice,
            23,
            (unsigned int)WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids,
            (unsigned int)"TdxDeactivateTransportAddress",
            (char)v28);
        }
        LOBYTE(v30) = v27;
        TdxShutdownEndpointConnection(v28, v30);
      }
      else
      {
        LOBYTE(v29) = 1;
        LOBYTE(v30) = v27;
        *(_DWORD *)v28 |= 0x200u;
        TdxDecrementTlEndpointReference(v28, v30, v29);
      }
      TdxDisassociateConnectionFromTransportAddress(a1, v28, v40);
      DbgTdxDereferenceConnection(v28, "TdxDeactivateTransportAddress", 1319);
      while ( 1 )
      {
        v31 = v40[0];
        if ( (_QWORD *)v40[0] == v40 )
          break;
        if ( *(_QWORD **)(v40[0] + 8LL) != v40 )
          goto LABEL_64;
        v32 = *(_QWORD *)v40[0];
        if ( *(_QWORD *)(*(_QWORD *)v40[0] + 8LL) != v40[0] )
          goto LABEL_64;
        v40[0] = *(_QWORD *)v40[0];
        *(_QWORD *)(v32 + 8) = v40;
        v33 = (IRP *)(v31 - 168);
        v33->IoStatus.Status = -1073741536;
        v33->IoStatus.Information = 0;
        IofCompleteRequest(v33, 2);
      }
      v24 = KeAcquireSpinLockRaiseToDpc(v1);
    }
    v34 = (_QWORD **)(a1 + 86);
    while ( 1 )
    {
      v35 = *v34;
      if ( *v34 == v34 )
        break;
      if ( (_QWORD **)v35[1] != v34 || (v36 = (_QWORD *)*v35, *(_QWORD **)(*v35 + 8LL) != v35) )
LABEL_64:
        __fastfail(3u);
      *v34 = v36;
      v36[1] = v34;
      KeReleaseSpinLock(v1, v27);
      v37 = v35 - 21;
      *((_DWORD *)v37 + 12) = -1073741536;
      v37[7] = 0;
      IofCompleteRequest((PIRP)(v35 - 21), 2);
      v27 = KeAcquireSpinLockRaiseToDpc(v1);
    }
    KeReleaseSpinLock(v1, v27);
  }
  if ( v4 )
    TdxReissueConnectWhileListenRequests(v4);
  DbgTdxDereferenceTransportAddress(a1, "minio\\netio\\session\\tdi\\address.c", 1369);
}

```

## disassembly

```asm
0x140003c9c  push    rbp
0x140003c9e  push    rbx
0x140003c9f  push    rsi
0x140003ca0  push    rdi
0x140003ca1  push    r12
0x140003ca3  push    r13
0x140003ca5  push    r14
0x140003ca7  push    r15
0x140003ca9  lea     rbp, [rsp-1Fh]
0x140003cae  sub     rsp, 0D8h
0x140003cb5  mov     rax, cs:__security_cookie
0x140003cbc  xor     rax, rsp
0x140003cbf  mov     [rbp+57h+var_50], rax
0x140003cc3  xorps   xmm0, xmm0
0x140003cc6  lea     rsi, [rcx+8]
0x140003cca  mov     rdi, rcx
0x140003ccd  xorps   xmm1, xmm1
0x140003cd0  xor     eax, eax
0x140003cd2  mov     rcx, rsi; SpinLock
0x140003cd5  movups  [rbp+57h+var_B8], xmm0
0x140003cd9  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x140003cdd  movups  xmmword ptr [rbp+57h+Event.Header], xmm1
0x140003ce1  movups  xmmword ptr [rbp+57h+Object], xmm0
0x140003ce5  movups  [rbp+57h+var_70], xmm0
0x140003ce9  movups  [rsp+110h+var_D8], xmm0
0x140003cee  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003cf5  nop     dword ptr [rax+rax+00h]
0x140003cfa  mov     r12, [rdi+218h]
0x140003d01  xor     r13d, r13d
0x140003d04  mov     ecx, [rdi]
0x140003d06  mov     r15b, al
0x140003d09  mov     [rbp+57h+var_A0], r12
0x140003d0d  mov     [rdi+218h], r13
0x140003d14  test    cl, 4
0x140003d17  jnz     short loc_140003D2F
0x140003d19  mov     dl, al; NewIrql
0x140003d1b  mov     rcx, rsi; SpinLock
0x140003d1e  call    cs:__imp_KeReleaseSpinLock
0x140003d25  nop     dword ptr [rax+rax+00h]
0x140003d2a  jmp     loc_1400042AD
0x140003d2f  mov     r14d, r13d
0x140003d32  mov     bl, r13b
0x140003d35  cmp     [rdi+220h], r13d
0x140003d3c  jbe     loc_140003DC3
0x140003d42  mov     r12d, 1
0x140003d48  mov     dl, r15b; NewIrql
0x140003d4b  mov     rcx, rsi; SpinLock
0x140003d4e  call    cs:__imp_KeReleaseSpinLock
0x140003d55  nop     dword ptr [rax+rax+00h]
0x140003d5a  lea     r8, [rbp+57h+Interval]; Interval
0x140003d5e  mov     qword ptr [rbp+57h+Interval], 0FFFFFFFFFFFFD8F0h
0x140003d66  xor     edx, edx; Alertable
0x140003d68  xor     ecx, ecx; WaitMode
0x140003d6a  call    cs:__imp_KeDelayExecutionThread
0x140003d71  nop     dword ptr [rax+rax+00h]
0x140003d76  mov     rcx, rsi; SpinLock
0x140003d79  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003d80  nop     dword ptr [rax+rax+00h]
0x140003d85  add     r14d, r12d
0x140003d88  mov     r15b, al
0x140003d8b  cmp     r14d, 2710h
0x140003d92  jb      short loc_140003DB6
0x140003d94  test    bl, bl
0x140003d96  jnz     short loc_140003DB6
0x140003d98  lea     rcx, [rbp+57h+var_60]
0x140003d9c  mov     [rbp+57h+var_60], 39BAEB0h
0x140003da3  mov     bl, r12b
0x140003da6  mov     [rbp+57h+var_5C], r12
0x140003daa  call    cs:__imp_RtlLogUnexpectedCodepath
0x140003db1  nop     dword ptr [rax+rax+00h]
0x140003db6  cmp     [rdi+220h], r13d
0x140003dbd  ja      short loc_140003D48
0x140003dbf  mov     r12, [rbp+57h+var_A0]
0x140003dc3  and     dword ptr [rdi], 0FFFFFFFBh
0x140003dc6  mov     eax, [rdi]
0x140003dc8  test    al, 20h
0x140003dca  jz      short loc_140003DD5
0x140003dcc  mov     r14, [rdi+1F8h]
0x140003dd3  jmp     short loc_140003DE5
0x140003dd5  test    al, 40h
0x140003dd7  jz      short loc_140003DE2
0x140003dd9  mov     r14, [rdi+200h]
0x140003de0  jmp     short loc_140003DE5
0x140003de2  mov     r14, r13
0x140003de5  mov     [rdi+1F8h], r13
0x140003dec  mov     rcx, rsi; SpinLock
0x140003def  mov     [rdi+200h], r13
0x140003df6  test    r14, r14
0x140003df9  jnz     short loc_140003E0C
0x140003dfb  mov     dl, r15b; NewIrql
0x140003dfe  call    cs:__imp_KeReleaseSpinLock
0x140003e05  nop     dword ptr [rax+rax+00h]
0x140003e0a  jmp     short loc_140003E73
0x140003e0c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140003e13  nop     dword ptr [rax+rax+00h]
0x140003e18  lea     rcx, [r14+8]; SpinLock
0x140003e1c  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140003e23  nop     dword ptr [rax+rax+00h]
0x140003e28  mov     dl, r15b; NewIrql
0x140003e2b  mov     [r14+1F8h], r13
0x140003e32  lea     rcx, [r14+8]; SpinLock
0x140003e36  mov     [r14+200h], r13
0x140003e3d  call    cs:__imp_KeReleaseSpinLock
0x140003e44  nop     dword ptr [rax+rax+00h]
0x140003e49  mov     r8d, 486h
0x140003e4f  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140003e56  mov     rcx, r14
0x140003e59  call    DbgTdxDereferenceTransportAddress
0x140003e5e  mov     r8d, 487h
0x140003e64  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140003e6b  mov     rcx, rdi
0x140003e6e  call    DbgTdxDereferenceTransportAddress
0x140003e73  xor     r8d, r8d; State
0x140003e76  lea     rax, [rbp+57h+Event]
0x140003e7a  lea     rcx, [rbp+57h+Event]; Event
0x140003e7e  mov     [rbp+57h+Object], rax
0x140003e82  lea     r14d, [r8+1]
0x140003e86  mov     edx, r14d; Type
0x140003e89  call    cs:__imp_KeInitializeEvent
0x140003e90  nop     dword ptr [rax+rax+00h]
0x140003e95  mov     r9, [rdi+140h]
0x140003e9c  lea     rax, WPP_GLOBAL_Control
0x140003ea3  test    r9, r9
0x140003ea6  jz      loc_140003F54
0x140003eac  mov     rcx, cs:WPP_GLOBAL_Control
0x140003eb3  cmp     rcx, rax
0x140003eb6  jz      short loc_140003EDB
0x140003eb8  cmp     byte ptr [rcx+29h], 4
0x140003ebc  jb      short loc_140003EDB
0x140003ebe  test    dword ptr [rcx+2Ch], 200h
0x140003ec5  jz      short loc_140003EDB
0x140003ec7  mov     rcx, [rcx+18h]
0x140003ecb  lea     edx, [r14+15h]
0x140003ecf  lea     r8, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids
0x140003ed6  call    WPP_SF_q
0x140003edb  lea     rax, TdxSynchronousTlRequestComplete
0x140003ee2  mov     qword ptr [rbp+57h+var_B8], rax
0x140003ee6  lea     rax, [rbp+57h+Object]
0x140003eea  mov     qword ptr [rbp+57h+var_B8+8], rax
0x140003eee  mov     eax, [rdi]
0x140003ef0  test    al, 2
0x140003ef2  jz      short loc_140003EFD
0x140003ef4  mov     rcx, [rdi+140h]
0x140003efb  jmp     short loc_140003F1D
0x140003efd  test    al, 20h
0x140003eff  jz      short loc_140003F0A
0x140003f01  cmp     [rdi+150h], r13
0x140003f08  jz      short loc_140003F54
0x140003f0a  mov     rax, [rdi+150h]
0x140003f11  mov     rcx, [rdi+140h]
0x140003f18  test    rax, rax
0x140003f1b  jnz     short loc_140003F24
0x140003f1d  mov     rax, [rdi+148h]
0x140003f24  mov     rax, [rax]
0x140003f27  lea     rdx, [rbp+57h+var_B8]
0x140003f2b  call    _guard_dispatch_icall
0x140003f30  cmp     eax, 103h
0x140003f35  jnz     short loc_140003F54
0x140003f37  mov     rcx, [rbp+57h+Object]; Object
0x140003f3b  xor     r9d, r9d; Alertable
0x140003f3e  xor     r8d, r8d; WaitMode
0x140003f41  mov     [rsp+110h+Timeout], r13; Timeout
0x140003f46  xor     edx, edx; WaitReason
0x140003f48  call    cs:__imp_KeWaitForSingleObject
0x140003f4f  nop     dword ptr [rax+rax+00h]
0x140003f54  mov     eax, [rdi]
0x140003f56  mov     rcx, rsi; SpinLock
0x140003f59  test    al, 2
0x140003f5b  jz      loc_140004085
0x140003f61  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003f68  nop     dword ptr [rax+rax+00h]
0x140003f6d  lea     rcx, [rdi+150h]
0x140003f74  mov     r8b, r13b
0x140003f77  mov     rdx, [rcx]
0x140003f7a  mov     bl, al
0x140003f7c  lea     rax, [rsp+110h+var_D8]
0x140003f81  mov     qword ptr [rbp+57h+var_D8+8], rax
0x140003f85  lea     rax, [rsp+110h+var_D8]
0x140003f8a  mov     qword ptr [rsp+110h+var_D8], rax
0x140003f8f  jmp     short loc_140003FDC
0x140003f91  mov     r10, [rdx]
0x140003f94  mov     rax, r13
0x140003f97  xchg    rax, [rdx-40h]
0x140003f9b  test    rax, rax
0x140003f9e  mov     dword ptr [rdx-78h], 0C0000120h
0x140003fa5  mov     [rdx-70h], r13
0x140003fa9  lea     rax, [rsp+110h+var_D8]
0x140003fae  mov     r9, qword ptr [rbp+57h+var_D8+8]
0x140003fb2  movzx   r8d, r8b
0x140003fb6  cmovz   r8d, r14d
0x140003fba  cmp     [r9], rax
0x140003fbd  jnz     loc_14000426F
0x140003fc3  mov     rax, rdx
0x140003fc6  mov     rdx, r10
0x140003fc9  lea     r10, [rsp+110h+var_D8]
0x140003fce  mov     [rax], r10
0x140003fd1  mov     [rax+8], r9
0x140003fd5  mov     [r9], rax
0x140003fd8  mov     qword ptr [rbp+57h+var_D8+8], rax
0x140003fdc  cmp     rdx, rcx
0x140003fdf  jnz     short loc_140003F91
0x140003fe1  mov     [rcx+8], rcx
0x140003fe5  mov     [rcx], rcx
0x140003fe8  test    r8b, r8b
0x140003feb  jz      short loc_140004031
0x140003fed  mov     rcx, rsi; SpinLock
0x140003ff0  mov     [rsp+110h+Irql], r13b
0x140003ff5  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140003ffc  nop     dword ptr [rax+rax+00h]
0x140004001  lea     rcx, [rsp+110h+Irql]; Irql
0x140004006  call    cs:__imp_IoAcquireCancelSpinLock
0x14000400d  nop     dword ptr [rax+rax+00h]
0x140004012  mov     cl, [rsp+110h+Irql]; Irql
0x140004016  call    cs:__imp_IoReleaseCancelSpinLock
0x14000401d  nop     dword ptr [rax+rax+00h]
0x140004022  mov     rcx, rsi; SpinLock
0x140004025  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000402c  nop     dword ptr [rax+rax+00h]
0x140004031  mov     dl, bl; NewIrql
0x140004033  mov     rcx, rsi; SpinLock
0x140004036  call    cs:__imp_KeReleaseSpinLock
0x14000403d  nop     dword ptr [rax+rax+00h]
0x140004042  mov     rbx, qword ptr [rsp+110h+var_D8]
0x140004047  jmp     short loc_140004076
0x140004049  lea     rcx, [rbx-0A8h]; Irp
0x140004050  mov     dl, 2; PriorityBoost
0x140004052  mov     rbx, [rbx]
0x140004055  call    cs:__imp_IofCompleteRequest
0x14000405c  nop     dword ptr [rax+rax+00h]
0x140004061  mov     r8d, 4F4h
0x140004067  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x14000406e  mov     rcx, rdi
0x140004071  call    DbgTdxDereferenceTransportAddress
0x140004076  lea     rax, [rsp+110h+var_D8]
0x14000407b  cmp     rbx, rax
0x14000407e  jnz     short loc_140004049
0x140004080  jmp     loc_140004288
0x140004085  lea     rax, [rbp+57h+var_C8]
0x140004089  mov     [rbp+57h+var_C0], rax
0x14000408d  lea     rax, [rbp+57h+var_C8]
0x140004091  mov     [rbp+57h+var_C8], rax
0x140004095  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000409c  nop     dword ptr [rax+rax+00h]
0x1400040a1  lea     r14, [rdi+178h]
0x1400040a8  mov     rcx, [r14]
0x1400040ab  mov     r15b, al
0x1400040ae  cmp     rcx, r14
0x1400040b1  jz      loc_140004204
0x1400040b7  lea     rbx, [rcx-110h]
0x1400040be  add     rcx, 0FFFFFFFFFFFFFEF8h; SpinLock
0x1400040c5  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400040cc  nop     dword ptr [rax+rax+00h]
0x1400040d1  mov     r8d, 510h
0x1400040d7  lea     rdx, aTdxdeactivatet_0; "TdxDeactivateTransportAddress"
0x1400040de  mov     rcx, rbx
0x1400040e1  call    DbgTdxReferenceConnection
0x1400040e6  mov     rcx, rsi; SpinLock
0x1400040e9  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400040f0  nop     dword ptr [rax+rax+00h]
0x1400040f5  lea     rdx, aTdxdeactivatet_0; "TdxDeactivateTransportAddress"
0x1400040fc  mov     rcx, rbx
0x1400040ff  call    TdxTraceConnectionRoutine
0x140004104  mov     eax, [rbx]
0x140004106  mov     edx, 200h
0x14000410b  test    edx, eax
0x14000410d  jnz     short loc_14000412C
0x14000410f  cmp     [rbx+120h], r13
0x140004116  jz      short loc_14000412C
0x140004118  or      eax, edx
0x14000411a  mov     r8b, 1
0x14000411d  mov     dl, r15b
0x140004120  mov     [rbx], eax
0x140004122  mov     rcx, rbx
0x140004125  call    TdxDecrementTlEndpointReference
0x14000412a  jmp     short loc_140004176
0x14000412c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004133  lea     rax, WPP_GLOBAL_Control
0x14000413a  cmp     rcx, rax
0x14000413d  jz      short loc_14000416B
0x14000413f  cmp     byte ptr [rcx+29h], 4
0x140004143  jb      short loc_14000416B
0x140004145  test    [rcx+2Ch], edx
0x140004148  jz      short loc_14000416B
0x14000414a  mov     rcx, [rcx+18h]
0x14000414e  lea     r9, aTdxdeactivatet_0; "TdxDeactivateTransportAddress"
0x140004155  mov     edx, 17h
0x14000415a  mov     [rsp+110h+Timeout], rbx
0x14000415f  lea     r8, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids
0x140004166  call    WPP_SF_sq
0x14000416b  mov     dl, r15b
0x14000416e  mov     rcx, rbx
0x140004171  call    TdxShutdownEndpointConnection
0x140004176  lea     r8, [rbp+57h+var_C8]
0x14000417a  mov     rdx, rbx
0x14000417d  mov     rcx, rdi
0x140004180  call    TdxDisassociateConnectionFromTransportAddress
0x140004185  mov     r8d, 527h
0x14000418b  lea     rdx, aTdxdeactivatet_0; "TdxDeactivateTransportAddress"
0x140004192  mov     rcx, rbx
0x140004195  call    DbgTdxDereferenceConnection
  ... truncated ...
```
