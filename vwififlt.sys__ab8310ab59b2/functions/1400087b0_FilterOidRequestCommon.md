# FilterOidRequestCommon

- ea: `0x1400087b0`
- end: `0x140008ce0`
- name: `FilterOidRequestCommon`
- size: `1328`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140007f70`
- `0x140008570`

## callees

- `0x1400087b0`
- `0x140009270`
- `0x14000ada8`
- `0x14000aef0`
- `0x14000cd98`
- `0x14000d8ec`
- `0x14000d91c`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140008b68`
- `ntoskrnl!DbgPrint` at `0x140008bda`
- `ntoskrnl!DbgPrint` at `0x140008c21`
- `ntoskrnl!DbgPrint` at `0x140008c65`
- `ntoskrnl!DbgPrint` at `0x140008b68`
- `ntoskrnl!DbgPrint` at `0x140008bda`
- `ntoskrnl!DbgPrint` at `0x140008c21`
- `ntoskrnl!DbgPrint` at `0x140008c65`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008832`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000894b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008832`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000894b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400088b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400089bb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400088b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400089bb`
- `NDIS!NdisFOidRequest` at `0x1400089db`
- `NDIS!NdisFOidRequest` at `0x1400089db`
- `NDIS!NdisAllocateCloneOidRequest` at `0x1400088db`
- `NDIS!NdisAllocateCloneOidRequest` at `0x1400088db`

## pseudocode

```c
__int64 __fastcall FilterOidRequestCommon(__int64 a1, NDIS_PORT_NUMBER a2, __int64 a3)
{
  unsigned int v3; // esi
  char v5; // r12
  unsigned int v7; // ebp
  __int64 v8; // r14
  volatile signed __int32 *v9; // rbp
  KIRQL v10; // dl
  KIRQL v11; // dl
  PDEVICE_OBJECT v12; // rcx
  __int64 v14; // rdx
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  char v17; // [rsp+80h] [rbp+8h]
  unsigned int v19; // [rsp+90h] [rbp+18h]
  PNDIS_OID_REQUEST ClonedOidRequest; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  ClonedOidRequest = 0;
  v5 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 164, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  v7 = *(_DWORD *)(a3 + 32);
  v19 = v7;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 165, a3, v7, *(_DWORD *)(a1 + 104));
  v8 = *(_QWORD *)(a1 + 8);
  if ( *(_DWORD *)(v8 + 24) != 1801678668 )
  {
    DbgPrint("Trying to acquire uninited lock %p, %s, Line %d\n", (const void *)(v8 + 24), "FilterLock", 423);
    __debugbreak();
  }
  _InterlockedIncrement((volatile signed __int32 *)(v8 + 28));
  *(_BYTE *)(v8 + 112) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 104));
  *(_QWORD *)(v8 + 72) = "FilterLock";
  *(_BYTE *)(v8 + 32) = 1;
  *(_DWORD *)(v8 + 80) = 423;
  if ( *(_BYTE *)(v8 + 2656) )
  {
    if ( v7 == 235208965 )
    {
      v3 = -1073741436;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_33;
      v16 = 166;
      goto LABEL_47;
    }
    if ( v7 != -50265855 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        goto LABEL_33;
      v16 = 167;
      goto LABEL_47;
    }
  }
  if ( !*(_BYTE *)(a1 + 3) )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_33;
    v16 = 168;
LABEL_47:
    WPP_SF_(v15->AttachedDevice, v16, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
LABEL_33:
    v17 = 0;
    ReleaseSpinLock(v8 + 24, "FilterUnlock", 430, 0);
    v9 = (volatile signed __int32 *)(a1 + 132);
    goto LABEL_23;
  }
  v9 = (volatile signed __int32 *)(a1 + 132);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 132));
  v17 = 1;
  if ( *(_DWORD *)(v8 + 24) != 1801678668 )
  {
    DbgPrint("Trying to acquire uninited lock %p, %s, Line %d\n", (const void *)(v8 + 24), "FilterUnlock", 430);
    __debugbreak();
  }
  v10 = *(_BYTE *)(v8 + 112);
  *(_QWORD *)(v8 + 88) = "FilterUnlock";
  *(_DWORD *)(v8 + 96) = 430;
  *(_BYTE *)(v8 + 32) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)(v8 + 104), v10);
  _InterlockedDecrement((volatile signed __int32 *)(v8 + 28));
  v3 = NdisAllocateCloneOidRequest(*(NDIS_HANDLE *)(v8 + 128), (PNDIS_OID_REQUEST)a3, 0x646E5756u, &ClonedOidRequest);
  if ( v3 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_23;
    v14 = 169;
LABEL_49:
    WPP_SF_d(v12->AttachedDevice, v14, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    goto LABEL_23;
  }
  v5 = 1;
  *(_QWORD *)ClonedOidRequest->SourceReserved = a3;
  ClonedOidRequest->RequestId = *(PVOID *)(a3 + 16);
  ClonedOidRequest->PortNumber = a2;
  *(_QWORD *)&ClonedOidRequest->SourceReserved[8] = a1;
  if ( *(_DWORD *)(v8 + 24) != 1801678668 )
  {
    DbgPrint("Trying to acquire uninited lock %p, %s, Line %d\n", (const void *)(v8 + 24), "FilterLock", 423);
    __debugbreak();
  }
  _InterlockedIncrement((volatile signed __int32 *)(v8 + 28));
  *(_BYTE *)(v8 + 112) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 104));
  *(_QWORD *)(v8 + 72) = "FilterLock";
  *(_BYTE *)(v8 + 32) = 1;
  *(_DWORD *)(v8 + 80) = 423;
  if ( *(_QWORD *)(a1 + 112) )
    TraceAssert("!pFilterMpCtx->PendingOidRequest", "onecoreuap\\net\\vwifi\\filter\\filter.c", 2731);
  *(_QWORD *)(a1 + 112) = ClonedOidRequest;
  *(_DWORD *)(a1 + 120) = v19;
  if ( *(_DWORD *)(v8 + 24) != 1801678668 )
  {
    DbgPrint("Trying to acquire uninited lock %p, %s, Line %d\n", (const void *)(v8 + 24), "FilterUnlock", 430);
    __debugbreak();
  }
  v11 = *(_BYTE *)(v8 + 112);
  *(_QWORD *)(v8 + 88) = "FilterUnlock";
  *(_DWORD *)(v8 + 96) = 430;
  *(_BYTE *)(v8 + 32) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)(v8 + 104), v11);
  _InterlockedDecrement((volatile signed __int32 *)(v8 + 28));
  v3 = NdisFOidRequest(*(NDIS_HANDLE *)(v8 + 128), ClonedOidRequest);
  if ( v3 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v14 = 170;
      goto LABEL_49;
    }
  }
LABEL_23:
  if ( v3 != 259 )
  {
    if ( ClonedOidRequest )
    {
      FilterOidRequestCompleteCommon(v8, (__int64)ClonedOidRequest, v3, 0);
    }
    else if ( v17 )
    {
      _InterlockedDecrement(v9);
    }
  }
  if ( !v5 )
  {
    if ( *(_DWORD *)(a3 + 4) == 12 )
    {
      *(_QWORD *)(a3 + 64) = 0;
      *(_DWORD *)(a3 + 60) = 0;
    }
    else
    {
      *(_QWORD *)(a3 + 52) = 0;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 171, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x1400087b0  mov     [rsp+arg_8], edx
0x1400087b4  push    rbx
0x1400087b5  push    rbp
0x1400087b6  push    rsi
0x1400087b7  push    rdi
0x1400087b8  push    r12
0x1400087ba  push    r13
0x1400087bc  push    r14
0x1400087be  push    r15
0x1400087c0  sub     rsp, 38h
0x1400087c4  xor     esi, esi
0x1400087c6  mov     r15, r8
0x1400087c9  mov     [rsp+78h+ClonedOidRequest], rsi
0x1400087d1  xor     r12b, r12b
0x1400087d4  mov     rdi, rcx
0x1400087d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400087de  lea     r13, WPP_GLOBAL_Control
0x1400087e5  cmp     rcx, r13
0x1400087e8  jz      short loc_1400087F5
0x1400087ea  mov     eax, [rcx+2Ch]
0x1400087ed  test    al, 20h
0x1400087ef  jnz     loc_140008B19
0x1400087f5  mov     ebp, [r15+20h]
0x1400087f9  mov     [rsp+78h+arg_10], ebp
0x140008800  mov     rcx, cs:WPP_GLOBAL_Control
0x140008807  cmp     rcx, r13
0x14000880a  jz      short loc_140008817
0x14000880c  mov     eax, [rcx+2Ch]
0x14000880f  test    al, 4
0x140008811  jnz     loc_140008B33
0x140008817  mov     r14, [rdi+8]
0x14000881b  cmp     dword ptr [r14+18h], 6B636F4Ch
0x140008823  jnz     loc_140008B50
0x140008829  lock inc dword ptr [r14+1Ch]
0x14000882e  lea     rcx, [r14+68h]; SpinLock
0x140008832  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008839  nop     dword ptr [rax+rax+00h]
0x14000883e  mov     [r14+70h], al
0x140008842  lea     rax, aFilterlock; "FilterLock"
0x140008849  mov     [r14+48h], rax
0x14000884d  mov     byte ptr [r14+20h], 1
0x140008852  mov     dword ptr [r14+50h], 1A7h
0x14000885a  cmp     [r14+0A60h], sil
0x140008861  jnz     loc_140008ABC
0x140008867  cmp     [rdi+3], sil
0x14000886b  jz      loc_140008A78
0x140008871  lea     rbp, [rdi+84h]
0x140008878  lock inc dword ptr [rbp+0]
0x14000887c  cmp     dword ptr [r14+18h], 6B636F4Ch
0x140008884  lea     r13, aFilterunlock; "FilterUnlock"
0x14000888b  mov     [rsp+78h+arg_0], 1
0x140008893  jnz     loc_140008BC6
0x140008899  movzx   edx, byte ptr [r14+70h]; NewIrql
0x14000889e  lea     rcx, [r14+68h]; SpinLock
0x1400088a2  mov     [r14+58h], r13
0x1400088a6  mov     dword ptr [r14+60h], 1AEh
0x1400088ae  mov     [r14+20h], sil
0x1400088b2  call    cs:__imp_KeReleaseSpinLock
0x1400088b9  nop     dword ptr [rax+rax+00h]
0x1400088be  lock dec dword ptr [r14+1Ch]
0x1400088c3  lea     r9, [rsp+78h+ClonedOidRequest]; ClonedOidRequest
0x1400088cb  mov     rcx, [r14+80h]; SourceHandle
0x1400088d2  mov     r8d, 646E5756h; PoolTag
0x1400088d8  mov     rdx, r15; OidRequest
0x1400088db  call    cs:__imp_NdisAllocateCloneOidRequest
0x1400088e2  nop     dword ptr [rax+rax+00h]
0x1400088e7  mov     esi, eax
0x1400088e9  test    eax, eax
0x1400088eb  jnz     loc_140008A50
0x1400088f1  mov     rax, [rsp+78h+ClonedOidRequest]
0x1400088f9  mov     r12b, 1
0x1400088fc  mov     [rax+0D8h], r15
0x140008903  mov     rax, [rsp+78h+ClonedOidRequest]
0x14000890b  mov     rcx, [r15+10h]
0x14000890f  mov     [rax+10h], rcx
0x140008913  mov     rax, [rsp+78h+ClonedOidRequest]
0x14000891b  mov     ecx, [rsp+78h+arg_8]
0x140008922  mov     [rax+8], ecx
0x140008925  mov     rax, [rsp+78h+ClonedOidRequest]
0x14000892d  mov     [rax+0E0h], rdi
0x140008934  cmp     dword ptr [r14+18h], 6B636F4Ch
0x14000893c  jnz     loc_140008C09
0x140008942  lock inc dword ptr [r14+1Ch]
0x140008947  lea     rcx, [r14+68h]; SpinLock
0x14000894b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008952  nop     dword ptr [rax+rax+00h]
0x140008957  mov     [r14+70h], al
0x14000895b  lea     rax, aFilterlock; "FilterLock"
0x140008962  mov     [r14+48h], rax
0x140008966  mov     [r14+20h], r12b
0x14000896a  mov     dword ptr [r14+50h], 1A7h
0x140008972  cmp     qword ptr [rdi+70h], 0
0x140008977  jnz     loc_140008C33
0x14000897d  mov     rax, [rsp+78h+ClonedOidRequest]
0x140008985  mov     [rdi+70h], rax
0x140008989  mov     eax, [rsp+78h+arg_10]
0x140008990  mov     [rdi+78h], eax
0x140008993  cmp     dword ptr [r14+18h], 6B636F4Ch
0x14000899b  jnz     loc_140008C51
0x1400089a1  movzx   edx, byte ptr [r14+70h]; NewIrql
0x1400089a6  lea     rcx, [r14+68h]; SpinLock
0x1400089aa  mov     [r14+58h], r13
0x1400089ae  mov     dword ptr [r14+60h], 1AEh
0x1400089b6  mov     byte ptr [r14+20h], 0
0x1400089bb  call    cs:__imp_KeReleaseSpinLock
0x1400089c2  nop     dword ptr [rax+rax+00h]
0x1400089c7  lock dec dword ptr [r14+1Ch]
0x1400089cc  mov     rdx, [rsp+78h+ClonedOidRequest]; OidRequest
0x1400089d4  mov     rcx, [r14+80h]; NdisFilterHandle
0x1400089db  call    cs:__imp_NdisFOidRequest
0x1400089e2  nop     dword ptr [rax+rax+00h]
0x1400089e7  mov     esi, eax
0x1400089e9  test    eax, eax
0x1400089eb  jz      loc_140008AB0
0x1400089f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400089f8  lea     rbx, WPP_GLOBAL_Control
0x1400089ff  cmp     rcx, rbx
0x140008a02  jz      short loc_140008A10
0x140008a04  mov     eax, [rcx+2Ch]
0x140008a07  test    r12b, al
0x140008a0a  jnz     loc_140008BEC
0x140008a10  cmp     esi, 103h
0x140008a16  jnz     loc_140008C77
0x140008a1c  test    r12b, r12b
0x140008a1f  jz      loc_140008AF1
0x140008a25  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a2c  cmp     rcx, rbx
0x140008a2f  jz      short loc_140008A3C
0x140008a31  mov     eax, [rcx+2Ch]
0x140008a34  test    al, 20h
0x140008a36  jnz     loc_140008CC3
0x140008a3c  mov     eax, esi
0x140008a3e  add     rsp, 38h
0x140008a42  pop     r15
0x140008a44  pop     r14
0x140008a46  pop     r13
0x140008a48  pop     r12
0x140008a4a  pop     rdi
0x140008a4b  pop     rsi
0x140008a4c  pop     rbp
0x140008a4d  pop     rbx
0x140008a4e  retn
0x140008a50  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a57  lea     rbx, WPP_GLOBAL_Control
0x140008a5e  cmp     rcx, rbx
0x140008a61  jz      short loc_140008A10
0x140008a63  mov     edx, [rcx+2Ch]
0x140008a66  test    dl, 1
0x140008a69  jz      short loc_140008A10
0x140008a6b  mov     edx, 0A9h
0x140008a70  mov     r9d, eax
0x140008a73  jmp     loc_140008BF4
0x140008a78  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a7f  cmp     rcx, r13
0x140008a82  jnz     loc_140008BA1
0x140008a88  xor     r9d, r9d
0x140008a8b  mov     [rsp+78h+arg_0], r12b
0x140008a93  mov     r8d, 1AEh
0x140008a99  lea     rdx, aFilterunlock; "FilterUnlock"
0x140008aa0  lea     rcx, [r14+18h]
0x140008aa4  call    ReleaseSpinLock
0x140008aa9  lea     rbp, [rdi+84h]
0x140008ab0  lea     rbx, WPP_GLOBAL_Control
0x140008ab7  jmp     loc_140008A10
0x140008abc  cmp     ebp, 0E050105h
0x140008ac2  jz      loc_140008B7A
0x140008ac8  cmp     ebp, 0FD010101h
0x140008ace  jz      loc_140008867
0x140008ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x140008adb  cmp     rcx, r13
0x140008ade  jz      short loc_140008A88
0x140008ae0  mov     eax, [rcx+2Ch]
0x140008ae3  test    al, 4
0x140008ae5  jz      short loc_140008A88
0x140008ae7  mov     edx, 0A7h
0x140008aec  jmp     loc_140008BB1
0x140008af1  mov     ecx, [r15+4]
0x140008af5  test    ecx, ecx
0x140008af7  jz      short loc_140008B0C
0x140008af9  sub     ecx, 1
0x140008afc  jz      short loc_140008B0C
0x140008afe  sub     ecx, 1
0x140008b01  jz      short loc_140008B0C
0x140008b03  cmp     ecx, 0Ah
0x140008b06  jz      loc_140008CAE
0x140008b0c  mov     qword ptr [r15+34h], 0
0x140008b14  jmp     loc_140008A25
0x140008b19  mov     rcx, [rcx+18h]
0x140008b1d  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140008b24  mov     edx, 0A4h
0x140008b29  call    WPP_SF_
0x140008b2e  jmp     loc_1400087F5
0x140008b33  mov     eax, [rdi+68h]
0x140008b36  mov     edx, 0A5h
0x140008b3b  mov     rcx, [rcx+18h]
0x140008b3f  mov     r9d, ebp
0x140008b42  mov     [rsp+78h+var_58], eax
0x140008b46  call    WPP_SF_Dd
0x140008b4b  jmp     loc_140008817
0x140008b50  mov     r9d, 1A7h
0x140008b56  lea     r8, aFilterlock; "FilterLock"
0x140008b5d  lea     rdx, [r14+18h]
0x140008b61  lea     rcx, Format; "Trying to acquire uninited lock %p, %s,"...
0x140008b68  call    cs:__imp_DbgPrint
0x140008b6f  nop     dword ptr [rax+rax+00h]
0x140008b74  int     3; Trap to Debugger
0x140008b75  jmp     loc_140008829
0x140008b7a  mov     esi, 0C0000184h
0x140008b7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b86  cmp     rcx, r13
0x140008b89  jz      loc_140008A88
0x140008b8f  mov     eax, [rcx+2Ch]
0x140008b92  test    al, 1
0x140008b94  jz      loc_140008A88
0x140008b9a  mov     edx, 0A6h
0x140008b9f  jmp     short loc_140008BB1
0x140008ba1  mov     eax, [rcx+2Ch]
0x140008ba4  test    al, 4
0x140008ba6  jz      loc_140008A88
0x140008bac  mov     edx, 0A8h
0x140008bb1  mov     rcx, [rcx+18h]
0x140008bb5  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140008bbc  call    WPP_SF_
0x140008bc1  jmp     loc_140008A88
0x140008bc6  mov     r9d, 1AEh
0x140008bcc  lea     rdx, [r14+18h]
0x140008bd0  mov     r8, r13
0x140008bd3  lea     rcx, Format; "Trying to acquire uninited lock %p, %s,"...
0x140008bda  call    cs:__imp_DbgPrint
0x140008be1  nop     dword ptr [rax+rax+00h]
0x140008be6  int     3; Trap to Debugger
0x140008be7  jmp     loc_140008899
0x140008bec  mov     edx, 0AAh
0x140008bf1  mov     r9d, esi
0x140008bf4  mov     rcx, [rcx+18h]
0x140008bf8  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140008bff  call    WPP_SF_d
0x140008c04  jmp     loc_140008A10
0x140008c09  mov     r9d, 1A7h
0x140008c0f  lea     r8, aFilterlock; "FilterLock"
0x140008c16  lea     rdx, [r14+18h]
0x140008c1a  lea     rcx, Format; "Trying to acquire uninited lock %p, %s,"...
0x140008c21  call    cs:__imp_DbgPrint
0x140008c28  nop     dword ptr [rax+rax+00h]
0x140008c2d  int     3; Trap to Debugger
0x140008c2e  jmp     loc_140008942
0x140008c33  mov     r8d, 0AABh
0x140008c39  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x140008c40  lea     rcx, aPfiltermpctxPe; "!pFilterMpCtx->PendingOidRequest"
0x140008c47  call    TraceAssert
0x140008c4c  jmp     loc_14000897D
0x140008c51  mov     r9d, 1AEh
0x140008c57  lea     rdx, [r14+18h]
0x140008c5b  mov     r8, r13
0x140008c5e  lea     rcx, Format; "Trying to acquire uninited lock %p, %s,"...
0x140008c65  call    cs:__imp_DbgPrint
0x140008c6c  nop     dword ptr [rax+rax+00h]
0x140008c71  int     3; Trap to Debugger
0x140008c72  jmp     loc_1400089A1
0x140008c77  mov     rdx, [rsp+78h+ClonedOidRequest]
0x140008c7f  test    rdx, rdx
0x140008c82  jz      short loc_140008C97
0x140008c84  xor     r9d, r9d
0x140008c87  mov     r8d, esi
0x140008c8a  mov     rcx, r14
0x140008c8d  call    FilterOidRequestCompleteCommon
0x140008c92  jmp     loc_140008A1C
0x140008c97  cmp     [rsp+78h+arg_0], 0
0x140008c9f  jz      loc_140008A1C
0x140008ca5  lock dec dword ptr [rbp+0]
0x140008ca9  jmp     loc_140008A1C
0x140008cae  mov     qword ptr [r15+40h], 0
0x140008cb6  mov     dword ptr [r15+3Ch], 0
0x140008cbe  jmp     loc_140008A25
0x140008cc3  mov     rcx, [rcx+18h]
0x140008cc7  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140008cce  mov     edx, 0ABh
0x140008cd3  mov     r9d, esi
0x140008cd6  call    WPP_SF_d
0x140008cdb  jmp     loc_140008A3C
```
