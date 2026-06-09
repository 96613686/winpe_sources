# TdxIssueIoControlRequest

- ea: `0x140010100`
- end: `0x1400105cf`
- name: `TdxIssueIoControlRequest`
- size: `1231`
- prototype: `__int64 __fastcall(__int64, __int64, int *)`
- caller_count: `5`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x14000fe30`
- `0x14000ffc0`
- `0x140010f10`
- `0x140011cb4`
- `0x140012308`

## callees

- `0x140002850`
- `0x140003590`
- `0x1400047d0`
- `0x1400054ec`
- `0x140008620`
- `0x140008ef0`
- `0x14000fcf0`
- `0x140010100`
- `0x140015d78`
- `0x140015de0`
- `0x140015e90`
- `0x140015f64`
- `0x1400184b0`
- `0x140018590`
- `0x140018900`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140010220`
- `ntoskrnl!KeLowerIrql` at `0x140010220`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x14001031f`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x14001031f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010474`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010474`
- `ntoskrnl!KeInitializeEvent` at `0x140010297`
- `ntoskrnl!KeInitializeEvent` at `0x140010297`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010162`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400103d6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010433`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010162`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400103d6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010433`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400101e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001027f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400103fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001044a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400104a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400104ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001054a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400101e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001027f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400103fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001044a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400104a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400104ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001054a`

## pseudocode

```c
__int64 __fastcall TdxIssueIoControlRequest(__int64 a1, __int64 a2, int *a3)
{
  KIRQL v6; // r14
  __int64 result; // rax
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rsi
  char v11; // r12
  KSPIN_LOCK *v12; // rcx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  __int64 v16; // r8
  int v17; // r9d
  unsigned int v18; // ebx
  KIRQL v19; // dl
  KSPIN_LOCK *v20; // rcx
  __int64 v21; // rax
  KIRQL v22; // al
  KSPIN_LOCK *v23; // rcx
  struct _KEVENT Event; // [rsp+50h] [rbp-89h] BYREF
  _QWORD v25[10]; // [rsp+70h] [rbp-69h] BYREF
  __int128 v26; // [rsp+C0h] [rbp-19h] BYREF
  __int128 v27; // [rsp+D0h] [rbp-9h]
  _DWORD v28[4]; // [rsp+E0h] [rbp+7h] BYREF

  memset(&Event, 0, sizeof(Event));
  v26 = 0;
  v27 = 0;
  memset(v25, 0, sizeof(v25));
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  if ( *(_DWORD *)(a1 + 4) != 2 )
  {
    if ( (*(_DWORD *)a1 & 4) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_sqddDs(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          (_DWORD)WPP_GLOBAL_Control,
          (unsigned int)"TdxIssueIoControlRequest",
          a1,
          a3[1],
          a3[2]);
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v6);
      return 3221225485LL;
    }
    DbgTdxReferenceTransportAddress(a1, "minio\\netio\\session\\tdi\\request.c", 935);
    LOBYTE(v8) = 1;
    v9 = TdxSelectTlRequestTransportAddress(a1, v8);
    v10 = v9;
    if ( !v9 )
    {
      KeLowerIrql(v6);
      return 3221225793LL;
    }
    v11 = 0;
    v12 = (KSPIN_LOCK *)(v9 + 8);
LABEL_14:
    KeReleaseSpinLock(v12, v6);
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    v13 = *a3;
    *(_QWORD *)&v26 = &Event;
    v25[0] = TdxSynchronousTlIoRequestComplete;
    v25[1] = &v26;
    LODWORD(v25[2]) = v13;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( !v14 || (v15 = v14 - 1) == 0 )
      {
        v16 = (unsigned int)a3[1];
        v17 = a3[2];
        HIDWORD(v25[2]) = a3[1];
        LODWORD(v25[3]) = v17;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          WPP_SF_qdd(WPP_GLOBAL_Control->AttachedDevice, WPP_GLOBAL_Control, v16, a1, v16, v17);
        }
LABEL_28:
        v25[4] = *((_QWORD *)a3 + 2);
        v25[5] = (unsigned int)a3[6];
        v25[6] = *((_QWORD *)a3 + 4);
        v25[7] = (unsigned int)a3[10];
        if ( v11 )
        {
          v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)(a1 + 264) + 8LL))(*(_QWORD *)(a1 + 288), v25);
          TdxDecrementTlEndpointReference(a1, 0, 0);
        }
        else
        {
          v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v10 + 8));
          v20 = (KSPIN_LOCK *)(v10 + 8);
          if ( (*(_DWORD *)v10 & 0x14) != 4 )
          {
            KeReleaseSpinLock(v20, v19);
            v18 = -2147483631;
            goto LABEL_39;
          }
          ++*(_DWORD *)(v10 + 544);
          KeReleaseSpinLock(v20, v19);
          v21 = *(_QWORD *)(v10 + 328);
          if ( !v21 )
            v21 = *(_QWORD *)(v10 + 336);
          v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(v21 + 8))(*(_QWORD *)(v10 + 320), v25);
          v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v10 + 8));
          --*(_DWORD *)(v10 + 544);
          KeReleaseSpinLock((PKSPIN_LOCK)(v10 + 8), v22);
        }
        if ( v18 == 259 )
        {
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
          v18 = DWORD2(v26);
          v25[9] = v27;
        }
        if ( v11 )
        {
          DbgTdxDereferenceConnection(a1, "TdxIssueIoControlRequest", 1050);
LABEL_40:
          *(_QWORD *)(a2 + 56) = v25[9];
          result = v18;
          *(_DWORD *)(a2 + 48) = v18;
          return result;
        }
LABEL_39:
        DbgTdxDereferenceTransportAddress(v10, "minio\\netio\\session\\tdi\\request.c", 1052);
        goto LABEL_40;
      }
      if ( v15 == 1 && *(_BYTE *)(a2 + 64) )
      {
        if ( a3[2] == -2013265894 )
          return 3221225659LL;
        if ( a3[2] == -2013265909 )
        {
          v28[0] = 56847937;
          v28[1] = 1;
          v28[2] = -1073741637;
          RtlLogUnexpectedCodepath(v28);
          return 3221225659LL;
        }
      }
    }
    LODWORD(v25[3]) = a3[2];
    goto LABEL_28;
  }
  if ( *(_QWORD *)(a1 + 264) && (*(_DWORD *)a1 & 0x80u) == 0 )
  {
    v11 = 1;
    v10 = 0;
    TdxIncrementTlEndpointReference(a1);
    DbgTdxReferenceConnection(a1, "TdxIssueIoControlRequest", 894);
    v12 = (KSPIN_LOCK *)(a1 + 8);
    goto LABEL_14;
  }
  v23 = (KSPIN_LOCK *)(a1 + 8);
  if ( (*(_DWORD *)a1 & 0x1000) != 0 )
  {
    KeReleaseSpinLock(v23, v6);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_sqdd(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        (_DWORD)WPP_GLOBAL_Control,
        (unsigned int)"TdxIssueIoControlRequest",
        a1,
        a3[1],
        a3[2]);
    }
    return 0;
  }
  else
  {
    KeReleaseSpinLock(v23, v6);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_sqddD(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        (_DWORD)WPP_GLOBAL_Control,
        (unsigned int)"TdxIssueIoControlRequest",
        a1,
        a3[1],
        a3[2]);
    }
    return 3221225488LL;
  }
}

```

## disassembly

```asm
0x140010100  mov     [rsp-8+arg_18], rbx
0x140010105  push    rbp
0x140010106  push    rsi
0x140010107  push    rdi
0x140010108  push    r12
0x14001010a  push    r13
0x14001010c  push    r14
0x14001010e  push    r15
0x140010110  lea     rbp, [rsp-27h]
0x140010115  sub     rsp, 100h
0x14001011c  mov     rax, cs:__security_cookie
0x140010123  xor     rax, rsp
0x140010126  mov     [rbp+57h+var_40], rax
0x14001012a  xor     eax, eax
0x14001012c  xorps   xmm1, xmm1
0x14001012f  mov     rbx, r8
0x140010132  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x140010136  mov     r13, rdx
0x140010139  mov     rdi, rcx
0x14001013c  xorps   xmm0, xmm0
0x14001013f  lea     rcx, [rbp+57h+var_C0]; void *
0x140010143  lea     r8d, [rax+50h]; Size
0x140010147  xor     edx, edx; Val
0x140010149  movups  xmmword ptr [rsp+130h+Event.Header], xmm0
0x14001014e  movups  [rbp+57h+var_70], xmm1
0x140010152  movups  [rbp+57h+var_60], xmm1
0x140010156  call    memset
0x14001015b  lea     r15, [rdi+8]
0x14001015f  mov     rcx, r15; SpinLock
0x140010162  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010169  nop     dword ptr [rax+rax+00h]
0x14001016e  cmp     dword ptr [rdi+4], 2
0x140010172  mov     r14b, al
0x140010175  jz      loc_14001023F
0x14001017b  mov     ecx, [rdi]
0x14001017d  test    cl, 4
0x140010180  jnz     short loc_1400101F6
0x140010182  mov     r8, cs:WPP_GLOBAL_Control
0x140010189  lea     rcx, WPP_GLOBAL_Control
0x140010190  cmp     r8, rcx
0x140010193  jz      short loc_1400101DA
0x140010195  cmp     byte ptr [r8+29h], 5
0x14001019a  jb      short loc_1400101DA
0x14001019c  test    dword ptr [r8+2Ch], 200h
0x1400101a4  jz      short loc_1400101DA
0x1400101a6  mov     rcx, [r8+18h]
0x1400101aa  lea     rax, aFalse; "FALSE"
0x1400101b1  mov     [rsp+130h+var_F0], rax
0x1400101b6  lea     r9, aTdxissueiocont; "TdxIssueIoControlRequest"
0x1400101bd  mov     eax, [rbx+8]
0x1400101c0  mov     edx, 0Bh
0x1400101c5  mov     [rsp+130h+var_100], eax
0x1400101c9  mov     eax, [rbx+4]
0x1400101cc  mov     [rsp+130h+var_108], eax
0x1400101d0  mov     [rsp+130h+Timeout], rdi
0x1400101d5  call    WPP_SF_sqddDs
0x1400101da  mov     dl, r14b; NewIrql
0x1400101dd  mov     rcx, r15; SpinLock
0x1400101e0  call    cs:__imp_KeReleaseSpinLock
0x1400101e7  nop     dword ptr [rax+rax+00h]
0x1400101ec  mov     eax, 0C000000Dh
0x1400101f1  jmp     loc_1400105A7
0x1400101f6  mov     r8d, 3A7h
0x1400101fc  lea     rdx, aMinioNetioSess_0; "minio\\netio\\session\\tdi\\request.c"
0x140010203  mov     rcx, rdi
0x140010206  call    DbgTdxReferenceTransportAddress
0x14001020b  mov     dl, 1
0x14001020d  mov     rcx, rdi
0x140010210  call    TdxSelectTlRequestTransportAddress
0x140010215  mov     rsi, rax
0x140010218  test    rax, rax
0x14001021b  jnz     short loc_140010236
0x14001021d  mov     cl, r14b; NewIrql
0x140010220  call    cs:__imp_KeLowerIrql
0x140010227  nop     dword ptr [rax+rax+00h]
0x14001022c  mov     eax, 0C0000141h
0x140010231  jmp     loc_1400105A7
0x140010236  xor     r12b, r12b
0x140010239  lea     rcx, [rax+8]
0x14001023d  jmp     short loc_14001027C
0x14001023f  cmp     qword ptr [rdi+108h], 0
0x140010247  jz      loc_1400104E0
0x14001024d  mov     eax, [rdi]
0x14001024f  test    al, al
0x140010251  js      loc_1400104E0
0x140010257  mov     rcx, rdi
0x14001025a  mov     r12b, 1
0x14001025d  xor     esi, esi
0x14001025f  call    TdxIncrementTlEndpointReference
0x140010264  mov     r8d, 37Eh
0x14001026a  lea     rdx, aTdxissueiocont; "TdxIssueIoControlRequest"
0x140010271  mov     rcx, rdi
0x140010274  call    DbgTdxReferenceConnection
0x140010279  mov     rcx, r15; SpinLock
0x14001027c  mov     dl, r14b; NewIrql
0x14001027f  call    cs:__imp_KeReleaseSpinLock
0x140010286  nop     dword ptr [rax+rax+00h]
0x14001028b  xor     r8d, r8d; State
0x14001028e  lea     rcx, [rsp+130h+Event]; Event
0x140010293  lea     edx, [r8+1]; Type
0x140010297  call    cs:__imp_KeInitializeEvent
0x14001029e  nop     dword ptr [rax+rax+00h]
0x1400102a3  mov     ecx, [rbx]
0x1400102a5  lea     rax, [rsp+130h+Event]
0x1400102aa  mov     qword ptr [rbp+57h+var_70], rax
0x1400102ae  lea     rax, TdxSynchronousTlIoRequestComplete
0x1400102b5  mov     [rbp+57h+var_C0], rax
0x1400102b9  lea     rax, [rbp+57h+var_70]
0x1400102bd  mov     [rbp+57h+var_B8], rax
0x1400102c1  mov     [rbp+57h+var_B0], ecx
0x1400102c4  test    ecx, ecx
0x1400102c6  jz      loc_140010377
0x1400102cc  sub     ecx, 1
0x1400102cf  jz      short loc_14001032D
0x1400102d1  sub     ecx, 1
0x1400102d4  jz      short loc_14001032D
0x1400102d6  cmp     ecx, 1
0x1400102d9  jnz     loc_140010377
0x1400102df  cmp     byte ptr [r13+40h], 0
0x1400102e4  jz      loc_140010377
0x1400102ea  cmp     dword ptr [rbx+8], 8800001Ah
0x1400102f1  jnz     short loc_1400102FD
0x1400102f3  mov     eax, 0C00000BBh
0x1400102f8  jmp     loc_1400105A7
0x1400102fd  cmp     dword ptr [rbx+8], 8800000Bh
0x140010304  jnz     short loc_140010377
0x140010306  lea     rcx, [rbp+57h+var_50]
0x14001030a  mov     [rbp+57h+var_50], 3636E41h
0x140010311  mov     [rbp+57h+var_4C], 1
0x140010318  mov     [rbp+57h+var_48], 0C00000BBh
0x14001031f  call    cs:__imp_RtlLogUnexpectedCodepath
0x140010326  nop     dword ptr [rax+rax+00h]
0x14001032b  jmp     short loc_1400102F3
0x14001032d  mov     r8d, [rbx+4]
0x140010331  mov     r9d, [rbx+8]
0x140010335  mov     [rbp+57h+var_AC], r8d
0x140010339  mov     [rbp+57h+var_A8], r9d
0x14001033d  mov     rdx, cs:WPP_GLOBAL_Control
0x140010344  lea     rcx, WPP_GLOBAL_Control
0x14001034b  cmp     rdx, rcx
0x14001034e  jz      short loc_14001037D
0x140010350  cmp     byte ptr [rdx+29h], 5
0x140010354  jb      short loc_14001037D
0x140010356  test    dword ptr [rdx+2Ch], 200h
0x14001035d  jz      short loc_14001037D
0x14001035f  mov     rcx, [rdx+18h]
0x140010363  mov     [rsp+130h+var_108], r9d
0x140010368  mov     r9, rdi
0x14001036b  mov     dword ptr [rsp+130h+Timeout], r8d
0x140010370  call    WPP_SF_qdd
0x140010375  jmp     short loc_14001037D
0x140010377  mov     eax, [rbx+8]
0x14001037a  mov     [rbp+57h+var_A8], eax
0x14001037d  mov     rax, [rbx+10h]
0x140010381  mov     [rbp+57h+var_A0], rax
0x140010385  mov     eax, [rbx+18h]
0x140010388  mov     [rbp+57h+var_98], rax
0x14001038c  mov     rax, [rbx+20h]
0x140010390  mov     [rbp+57h+var_90], rax
0x140010394  mov     eax, [rbx+28h]
0x140010397  mov     [rbp+57h+var_88], rax
0x14001039b  test    r12b, r12b
0x14001039e  jz      short loc_1400103CF
0x1400103a0  mov     rax, [rdi+108h]
0x1400103a7  lea     rdx, [rbp+57h+var_C0]
0x1400103ab  mov     rcx, [rdi+120h]
0x1400103b2  mov     rax, [rax+8]
0x1400103b6  call    _guard_dispatch_icall
0x1400103bb  xor     r8d, r8d
0x1400103be  xor     edx, edx
0x1400103c0  mov     rcx, rdi
0x1400103c3  mov     ebx, eax
0x1400103c5  call    TdxDecrementTlEndpointReference
0x1400103ca  jmp     loc_140010456
0x1400103cf  lea     r14, [rsi+8]
0x1400103d3  mov     rcx, r14; SpinLock
0x1400103d6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400103dd  nop     dword ptr [rax+rax+00h]
0x1400103e2  mov     ecx, [rsi]
0x1400103e4  mov     dl, al; NewIrql
0x1400103e6  and     cl, 14h
0x1400103e9  cmp     cl, 4
0x1400103ec  mov     rcx, r14; SpinLock
0x1400103ef  jnz     loc_1400104A7
0x1400103f5  inc     dword ptr [rsi+220h]
0x1400103fb  call    cs:__imp_KeReleaseSpinLock
0x140010402  nop     dword ptr [rax+rax+00h]
0x140010407  mov     rax, [rsi+148h]
0x14001040e  lea     rdx, [rbp+57h+var_C0]
0x140010412  mov     rcx, [rsi+140h]
0x140010419  test    rax, rax
0x14001041c  jnz     short loc_140010425
0x14001041e  mov     rax, [rsi+150h]
0x140010425  mov     rax, [rax+8]
0x140010429  call    _guard_dispatch_icall
0x14001042e  mov     rcx, r14; SpinLock
0x140010431  mov     ebx, eax
0x140010433  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001043a  nop     dword ptr [rax+rax+00h]
0x14001043f  dec     dword ptr [rsi+220h]
0x140010445  mov     rcx, r14; SpinLock
0x140010448  mov     dl, al; NewIrql
0x14001044a  call    cs:__imp_KeReleaseSpinLock
0x140010451  nop     dword ptr [rax+rax+00h]
0x140010456  cmp     ebx, 103h
0x14001045c  jnz     short loc_14001048B
0x14001045e  xor     r9d, r9d; Alertable
0x140010461  mov     [rsp+130h+Timeout], 0; Timeout
0x14001046a  xor     r8d, r8d; WaitMode
0x14001046d  lea     rcx, [rsp+130h+Event]; Object
0x140010472  xor     edx, edx; WaitReason
0x140010474  call    cs:__imp_KeWaitForSingleObject
0x14001047b  nop     dword ptr [rax+rax+00h]
0x140010480  mov     rax, qword ptr [rbp+57h+var_60]
0x140010484  mov     ebx, dword ptr [rbp+57h+var_70+8]
0x140010487  mov     [rbp+57h+var_78], rax
0x14001048b  test    r12b, r12b
0x14001048e  jz      short loc_1400104B8
0x140010490  mov     r8d, 41Ah
0x140010496  lea     rdx, aTdxissueiocont; "TdxIssueIoControlRequest"
0x14001049d  mov     rcx, rdi
0x1400104a0  call    DbgTdxDereferenceConnection
0x1400104a5  jmp     short loc_1400104CD
0x1400104a7  call    cs:__imp_KeReleaseSpinLock
0x1400104ae  nop     dword ptr [rax+rax+00h]
0x1400104b3  mov     ebx, 80000011h
0x1400104b8  mov     r8d, 41Ch
0x1400104be  lea     rdx, aMinioNetioSess_0; "minio\\netio\\session\\tdi\\request.c"
0x1400104c5  mov     rcx, rsi
0x1400104c8  call    DbgTdxDereferenceTransportAddress
0x1400104cd  mov     rax, [rbp+57h+var_78]
0x1400104d1  mov     [r13+38h], rax
0x1400104d5  mov     eax, ebx
0x1400104d7  mov     [r13+30h], ebx
0x1400104db  jmp     loc_1400105A7
0x1400104e0  test    dword ptr [rdi], 1000h
0x1400104e6  mov     dl, r14b; NewIrql
0x1400104e9  mov     rcx, r15; SpinLock
0x1400104ec  jz      short loc_14001054A
0x1400104ee  call    cs:__imp_KeReleaseSpinLock
0x1400104f5  nop     dword ptr [rax+rax+00h]
0x1400104fa  mov     r8, cs:WPP_GLOBAL_Control
0x140010501  lea     rcx, WPP_GLOBAL_Control
0x140010508  cmp     r8, rcx
0x14001050b  jz      short loc_140010546
0x14001050d  cmp     byte ptr [r8+29h], 5
0x140010512  jb      short loc_140010546
0x140010514  test    dword ptr [r8+2Ch], 200h
0x14001051c  jz      short loc_140010546
0x14001051e  mov     eax, [rbx+8]
0x140010521  lea     r9, aTdxissueiocont; "TdxIssueIoControlRequest"
0x140010528  mov     rcx, [r8+18h]
0x14001052c  mov     edx, 0Ch
0x140010531  mov     [rsp+130h+var_100], eax
0x140010535  mov     eax, [rbx+4]
0x140010538  mov     [rsp+130h+var_108], eax
0x14001053c  mov     [rsp+130h+Timeout], rdi
0x140010541  call    WPP_SF_sqdd
0x140010546  xor     eax, eax
0x140010548  jmp     short loc_1400105A7
0x14001054a  call    cs:__imp_KeReleaseSpinLock
0x140010551  nop     dword ptr [rax+rax+00h]
0x140010556  mov     r8, cs:WPP_GLOBAL_Control
0x14001055d  lea     rcx, WPP_GLOBAL_Control
0x140010564  cmp     r8, rcx
0x140010567  jz      short loc_1400105A2
0x140010569  cmp     byte ptr [r8+29h], 5
0x14001056e  jb      short loc_1400105A2
0x140010570  test    dword ptr [r8+2Ch], 200h
0x140010578  jz      short loc_1400105A2
0x14001057a  mov     eax, [rbx+8]
0x14001057d  lea     r9, aTdxissueiocont; "TdxIssueIoControlRequest"
0x140010584  mov     rcx, [r8+18h]
0x140010588  mov     edx, 0Dh
0x14001058d  mov     [rsp+130h+var_100], eax
0x140010591  mov     eax, [rbx+4]
0x140010594  mov     [rsp+130h+var_108], eax
0x140010598  mov     [rsp+130h+Timeout], rdi
0x14001059d  call    WPP_SF_sqddD
0x1400105a2  mov     eax, 0C0000010h
0x1400105a7  mov     rcx, [rbp+57h+var_40]
0x1400105ab  xor     rcx, rsp; StackCookie
0x1400105ae  call    __security_check_cookie
0x1400105b3  mov     rbx, [rsp+130h+arg_18]
0x1400105bb  add     rsp, 100h
0x1400105c2  pop     r15
0x1400105c4  pop     r14
0x1400105c6  pop     r13
0x1400105c8  pop     r12
0x1400105ca  pop     rdi
0x1400105cb  pop     rsi
0x1400105cc  pop     rbp
0x1400105cd  retn
```
