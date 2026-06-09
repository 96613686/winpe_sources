# TdxIssueListenRequest

- ea: `0x1400157cc`
- end: `0x1400159e0`
- name: `TdxIssueListenRequest`
- size: `532`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140005fe0`
- `0x1400126e4`

## callees

- `0x140002850`
- `0x14000ccfc`
- `0x14000ced0`
- `0x1400106c0`
- `0x1400157cc`
- `0x1400184b0`
- `0x140018590`
- `0x140018900`

## import_xrefs

- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x140015937`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x140015937`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400158f1`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400158f1`
- `ntoskrnl!KeInitializeEvent` at `0x140015866`
- `ntoskrnl!KeInitializeEvent` at `0x140015866`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015901`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015901`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015839`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400158d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015965`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015839`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400158d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015965`

## pseudocode

```c
__int64 __fastcall TdxIssueListenRequest(KSPIN_LOCK *a1, KIRQL a2)
{
  __int64 locked; // rsi
  int v5; // edi
  int v6; // ecx
  unsigned int v7; // eax
  unsigned int v8; // r12d
  char v9; // r15
  __int64 result; // rax
  union _LARGE_INTEGER Interval; // [rsp+20h] [rbp-79h] BYREF
  struct _KEVENT Event; // [rsp+28h] [rbp-71h] BYREF
  _QWORD v13[14]; // [rsp+40h] [rbp-59h] BYREF
  int v14; // [rsp+B0h] [rbp+17h] BYREF
  __int64 v15; // [rsp+B4h] [rbp+1Bh]

  memset(v13, 0, 0x68u);
  DbgTdxReferenceTransportAddress(a1, "minio\\netio\\session\\tdi\\request.c", 173);
  locked = TdxLockedObjectHeaderToTransport(a1);
  if ( !locked )
  {
    KeReleaseSpinLock(a1 + 1, a2);
    v5 = -1073741808;
    return TdxListenRequestComplete((int)a1, v5, v13[10], v13[12]);
  }
  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v6 = *(_DWORD *)a1;
  v13[0] = TdxListenRequestComplete;
  v7 = 0x80000000;
  v13[1] = a1;
  if ( (v6 & 0x20) != 0 )
    v7 = -2147483647;
  LODWORD(v13[2]) = v7;
  v13[3] = a1[40];
  v13[9] = a1;
  v13[8] = a1 + 24;
  v13[11] = TdxTransportAddressListenDispatch;
  v8 = 0;
  v9 = 0;
  if ( *((_DWORD *)a1 + 136) )
  {
    do
    {
      KeReleaseSpinLock(a1 + 1, a2);
      Interval.QuadPart = -10000;
      KeDelayExecutionThread(0, 0, &Interval);
      ++v8;
      a2 = KeAcquireSpinLockRaiseToDpc(a1 + 1);
      if ( v8 >= 0x2710 && !v9 )
      {
        v14 = 60624589;
        v9 = 1;
        v15 = 1;
        RtlLogUnexpectedCodepath(&v14);
      }
    }
    while ( *((_DWORD *)a1 + 136) );
    v6 = *(_DWORD *)a1;
  }
  a1[40] = 0;
  *(_DWORD *)a1 = v6 | 0x10;
  KeReleaseSpinLock(a1 + 1, a2);
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)(locked + 80) + 32LL))(*(_QWORD *)(locked + 72), v13);
  result = DbgTdxDereferenceTransport(locked, "minio\\netio\\session\\tdi\\request.c", 231);
  if ( v5 != 259 )
    return TdxListenRequestComplete((int)a1, v5, v13[10], v13[12]);
  return result;
}

```

## disassembly

```asm
0x1400157cc  mov     [rsp-8+arg_10], rbx
0x1400157d1  mov     [rsp-8+arg_18], rsi
0x1400157d6  push    rbp
0x1400157d7  push    rdi
0x1400157d8  push    r12
0x1400157da  push    r14
0x1400157dc  push    r15
0x1400157de  lea     rbp, [rsp-37h]
0x1400157e3  sub     rsp, 0D0h
0x1400157ea  mov     rax, cs:__security_cookie
0x1400157f1  xor     rax, rsp
0x1400157f4  mov     [rbp+57h+var_30], rax
0x1400157f8  mov     dil, dl
0x1400157fb  mov     rbx, rcx
0x1400157fe  xor     edx, edx; Val
0x140015800  lea     rcx, [rbp+57h+var_B0]; void *
0x140015804  lea     r8d, [rdx+68h]; Size
0x140015808  call    memset
0x14001580d  mov     r8d, 0ADh
0x140015813  lea     rdx, aMinioNetioSess_0; "minio\\netio\\session\\tdi\\request.c"
0x14001581a  mov     rcx, rbx
0x14001581d  call    DbgTdxReferenceTransportAddress
0x140015822  mov     rcx, rbx
0x140015825  call    TdxLockedObjectHeaderToTransport
0x14001582a  mov     rsi, rax
0x14001582d  test    rax, rax
0x140015830  jnz     short loc_14001584F
0x140015832  lea     rcx, [rbx+8]; SpinLock
0x140015836  mov     dl, dil; NewIrql
0x140015839  call    cs:__imp_KeReleaseSpinLock
0x140015840  nop     dword ptr [rax+rax+00h]
0x140015845  mov     edi, 0C0000010h
0x14001584a  jmp     loc_1400159A5
0x14001584f  xor     eax, eax
0x140015851  lea     rcx, [rbp+57h+Event]; Event
0x140015855  xorps   xmm0, xmm0
0x140015858  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x14001585c  xor     r8d, r8d; State
0x14001585f  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x140015863  lea     edx, [rax+1]; Type
0x140015866  call    cs:__imp_KeInitializeEvent
0x14001586d  nop     dword ptr [rax+rax+00h]
0x140015872  mov     ecx, [rbx]
0x140015874  lea     rax, TdxListenRequestComplete
0x14001587b  mov     [rbp+57h+var_B0], rax
0x14001587f  test    cl, 20h
0x140015882  mov     eax, 80000000h
0x140015887  mov     [rbp+57h+var_A8], rbx
0x14001588b  mov     edx, 80000001h
0x140015890  cmovnz  eax, edx
0x140015893  mov     [rbp+57h+var_A0], eax
0x140015896  mov     rax, [rbx+140h]
0x14001589d  mov     [rbp+57h+var_98], rax
0x1400158a1  lea     rax, [rbx+0C0h]
0x1400158a8  mov     [rbp+57h+var_68], rbx
0x1400158ac  mov     [rbp+57h+var_70], rax
0x1400158b0  lea     rax, TdxTransportAddressListenDispatch
0x1400158b7  mov     [rbp+57h+var_58], rax
0x1400158bb  xor     r12d, r12d
0x1400158be  xor     r15b, r15b
0x1400158c1  cmp     [rbx+220h], r12d
0x1400158c8  jbe     loc_14001594E
0x1400158ce  mov     dl, dil; NewIrql
0x1400158d1  lea     rcx, [rbx+8]; SpinLock
0x1400158d5  call    cs:__imp_KeReleaseSpinLock
0x1400158dc  nop     dword ptr [rax+rax+00h]
0x1400158e1  lea     r8, [rbp+57h+Interval]; Interval
0x1400158e5  mov     qword ptr [rbp+57h+Interval], 0FFFFFFFFFFFFD8F0h
0x1400158ed  xor     edx, edx; Alertable
0x1400158ef  xor     ecx, ecx; WaitMode
0x1400158f1  call    cs:__imp_KeDelayExecutionThread
0x1400158f8  nop     dword ptr [rax+rax+00h]
0x1400158fd  lea     rcx, [rbx+8]; SpinLock
0x140015901  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015908  nop     dword ptr [rax+rax+00h]
0x14001590d  inc     r12d
0x140015910  mov     dil, al
0x140015913  cmp     r12d, 2710h
0x14001591a  jb      short loc_140015943
0x14001591c  test    r15b, r15b
0x14001591f  jnz     short loc_140015943
0x140015921  lea     rcx, [rbp+57h+var_40]
0x140015925  mov     [rbp+57h+var_40], 39D0ECDh
0x14001592c  mov     r15b, 1
0x14001592f  mov     [rbp+57h+var_3C], 1
0x140015937  call    cs:__imp_RtlLogUnexpectedCodepath
0x14001593e  nop     dword ptr [rax+rax+00h]
0x140015943  cmp     dword ptr [rbx+220h], 0
0x14001594a  ja      short loc_1400158CE
0x14001594c  mov     ecx, [rbx]
0x14001594e  or      ecx, 10h
0x140015951  mov     qword ptr [rbx+140h], 0
0x14001595c  mov     [rbx], ecx
0x14001595e  mov     dl, dil; NewIrql
0x140015961  lea     rcx, [rbx+8]; SpinLock
0x140015965  call    cs:__imp_KeReleaseSpinLock
0x14001596c  nop     dword ptr [rax+rax+00h]
0x140015971  mov     rax, [rsi+50h]
0x140015975  lea     rdx, [rbp+57h+var_B0]
0x140015979  mov     rcx, [rsi+48h]
0x14001597d  mov     rax, [rax+20h]
0x140015981  call    _guard_dispatch_icall
0x140015986  mov     r8d, 0E7h
0x14001598c  lea     rdx, aMinioNetioSess_0; "minio\\netio\\session\\tdi\\request.c"
0x140015993  mov     rcx, rsi
0x140015996  mov     edi, eax
0x140015998  call    DbgTdxDereferenceTransport
0x14001599d  cmp     edi, 103h
0x1400159a3  jz      short loc_1400159B7
0x1400159a5  mov     r9, qword ptr [rbp+57h+var_50]; int
0x1400159a9  mov     edx, edi; int
0x1400159ab  mov     r8, qword ptr [rbp+57h+var_60]; int
0x1400159af  mov     rcx, rbx; int
0x1400159b2  call    TdxListenRequestComplete
0x1400159b7  mov     rcx, [rbp+57h+var_30]
0x1400159bb  xor     rcx, rsp; StackCookie
0x1400159be  call    __security_check_cookie
0x1400159c3  lea     r11, [rsp+0F0h+var_20]
0x1400159cb  mov     rbx, [r11+40h]
0x1400159cf  mov     rsi, [r11+48h]
0x1400159d3  mov     rsp, r11
0x1400159d6  pop     r15
0x1400159d8  pop     r14
0x1400159da  pop     r12
0x1400159dc  pop     rdi
0x1400159dd  pop     rbp
0x1400159de  retn
```
