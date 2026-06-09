# FilterDirectOidRequestCommon

- ea: `0x1400097e4`
- end: `0x140009be5`
- name: `FilterDirectOidRequestCommon`
- size: `1025`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140009740`
- `0x14000e960`

## callees

- `0x140009270`
- `0x1400097e4`
- `0x140009bec`
- `0x14000ada8`
- `0x14000cd98`
- `0x14000d8ec`
- `0x14000d91c`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140009ab1`
- `ntoskrnl!DbgPrint` at `0x140009b21`
- `ntoskrnl!DbgPrint` at `0x140009ab1`
- `ntoskrnl!DbgPrint` at `0x140009b21`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009848`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009848`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400098bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400098bc`
- `NDIS!NdisFDirectOidRequest` at `0x14000994b`
- `NDIS!NdisFDirectOidRequest` at `0x14000994b`
- `NDIS!NdisAllocateCloneOidRequest` at `0x1400098e4`
- `NDIS!NdisAllocateCloneOidRequest` at `0x1400098e4`

## pseudocode

```c
__int64 __fastcall FilterDirectOidRequestCommon(__int64 a1, NDIS_PORT_NUMBER a2, __int64 a3)
{
  __int64 v5; // r13
  char v6; // r14
  volatile signed __int32 *v7; // rbx
  KIRQL v8; // dl
  unsigned int v9; // esi
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  char v15; // [rsp+70h] [rbp+8h]
  PNDIS_OID_REQUEST ClonedOidRequest; // [rsp+80h] [rbp+18h] BYREF

  ClonedOidRequest = 0;
  v15 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 189, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 190, a3, *(unsigned int *)(a3 + 32), *(_DWORD *)(a1 + 104));
  }
  v5 = *(_QWORD *)(a1 + 8);
  if ( *(_DWORD *)(v5 + 24) != 1801678668 )
  {
    DbgPrint("Trying to acquire uninited lock %p, %s, Line %d\n", (const void *)(v5 + 24), "FilterLock", 423);
    __debugbreak();
  }
  v6 = 1;
  _InterlockedAdd((volatile signed __int32 *)(v5 + 28), 1u);
  *(_BYTE *)(v5 + 112) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 104));
  *(_QWORD *)(v5 + 72) = "FilterLock";
  *(_BYTE *)(v5 + 32) = 1;
  *(_DWORD *)(v5 + 80) = 423;
  if ( *(_BYTE *)(v5 + 2656) )
  {
    TraceAssert("!pFilter->fLowPower", "onecoreuap\\net\\vwifi\\filter\\filter.c", 3026);
    if ( *(_BYTE *)(v5 + 2656) )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        goto LABEL_19;
      v12 = 191;
      goto LABEL_27;
    }
  }
  if ( *(_BYTE *)(a1 + 3) )
  {
    v7 = (volatile signed __int32 *)(a1 + 136);
    _InterlockedAdd((volatile signed __int32 *)(a1 + 136), 1u);
    if ( *(_DWORD *)(v5 + 24) != 1801678668 )
    {
      DbgPrint("Trying to acquire uninited lock %p, %s, Line %d\n", (const void *)(v5 + 24), "FilterUnlock", 430);
      __debugbreak();
    }
    v8 = *(_BYTE *)(v5 + 112);
    *(_QWORD *)(v5 + 88) = "FilterUnlock";
    *(_BYTE *)(v5 + 32) = 0;
    *(_DWORD *)(v5 + 96) = 430;
    KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 104), v8);
    _InterlockedDecrement((volatile signed __int32 *)(v5 + 28));
    v9 = NdisAllocateCloneOidRequest(*(NDIS_HANDLE *)(v5 + 128), (PNDIS_OID_REQUEST)a3, 0x646E5756u, &ClonedOidRequest);
    if ( v9 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v14 = 193;
LABEL_38:
        WPP_SF_d(v13->AttachedDevice, v14, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
      }
    }
    else
    {
      v15 = 1;
      *(_QWORD *)ClonedOidRequest->SourceReserved = a3;
      ClonedOidRequest->RequestId = *(PVOID *)(a3 + 16);
      ClonedOidRequest->PortNumber = a2;
      *(_QWORD *)&ClonedOidRequest->SourceReserved[8] = a1;
      v9 = NdisFDirectOidRequest(*(NDIS_HANDLE *)(v5 + 128), ClonedOidRequest);
      if ( v9 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v14 = 194;
          goto LABEL_38;
        }
      }
    }
    if ( v9 == 259 )
      goto LABEL_13;
    goto LABEL_11;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
    goto LABEL_19;
  v12 = 192;
LABEL_27:
  WPP_SF_(v11->AttachedDevice, v12, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
LABEL_19:
  v9 = 0;
  v6 = 0;
  ReleaseSpinLock(v5 + 24, "FilterUnlock", 430, 0);
  v7 = (volatile signed __int32 *)(a1 + 136);
LABEL_11:
  if ( ClonedOidRequest )
  {
    FilterDirectOidRequestCompleteCommon(v5, ClonedOidRequest, v9, 0);
  }
  else if ( v6 )
  {
    _InterlockedDecrement(v7);
  }
LABEL_13:
  if ( !v15 )
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
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 195, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  return v9;
}

```

## disassembly

```asm
0x1400097e4  mov     rax, rsp
0x1400097e7  mov     [rax+20h], rbx
0x1400097eb  mov     [rax+10h], edx
0x1400097ee  push    rbp
0x1400097ef  push    rsi
0x1400097f0  push    rdi
0x1400097f1  push    r12
0x1400097f3  push    r13
0x1400097f5  push    r14
0x1400097f7  push    r15
0x1400097f9  sub     rsp, 30h
0x1400097fd  xor     ebx, ebx
0x1400097ff  mov     rdi, r8
0x140009802  mov     [rax+18h], rbx
0x140009806  mov     r15, rcx
0x140009809  mov     [rsp+68h+arg_0], bl
0x14000980d  mov     rcx, cs:WPP_GLOBAL_Control
0x140009814  lea     r12, WPP_GLOBAL_Control
0x14000981b  cmp     rcx, r12
0x14000981e  jnz     loc_140009A21
0x140009824  mov     r13, [r15+8]
0x140009828  lea     rbp, [r13+18h]
0x14000982c  cmp     dword ptr [rbp+0], 6B636F4Ch
0x140009833  jnz     loc_140009A9A
0x140009839  mov     r14d, 1
0x14000983f  lock add [rbp+4], r14d
0x140009844  lea     rcx, [rbp+50h]; SpinLock
0x140009848  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000984f  nop     dword ptr [rax+rax+00h]
0x140009854  mov     [rbp+58h], al
0x140009857  lea     rax, aFilterlock; "FilterLock"
0x14000985e  mov     [rbp+30h], rax
0x140009862  mov     [rbp+8], r14b
0x140009866  mov     dword ptr [rbp+38h], 1A7h
0x14000986d  cmp     [r13+0A60h], bl
0x140009874  jnz     loc_140009AC3
0x14000987a  cmp     [r15+3], bl
0x14000987e  jz      loc_1400099E2
0x140009884  lea     rbx, [r15+88h]
0x14000988b  lock add [rbx], r14d
0x14000988f  cmp     dword ptr [rbp+0], 6B636F4Ch
0x140009896  lea     r12, aFilterunlock; "FilterUnlock"
0x14000989d  jnz     loc_140009B0E
0x1400098a3  mov     dl, [rbp+58h]; NewIrql
0x1400098a6  lea     rcx, [rbp+50h]; SpinLock
0x1400098aa  mov     [rbp+40h], r12
0x1400098ae  xor     r12d, r12d
0x1400098b1  mov     [rbp+8], r12b
0x1400098b5  mov     dword ptr [rbp+48h], 1AEh
0x1400098bc  call    cs:__imp_KeReleaseSpinLock
0x1400098c3  nop     dword ptr [rax+rax+00h]
0x1400098c8  lock dec dword ptr [rbp+4]
0x1400098cc  lea     r9, [rsp+68h+ClonedOidRequest]; ClonedOidRequest
0x1400098d4  mov     rcx, [r13+80h]; SourceHandle
0x1400098db  mov     r8d, 646E5756h; PoolTag
0x1400098e1  mov     rdx, rdi; OidRequest
0x1400098e4  call    cs:__imp_NdisAllocateCloneOidRequest
0x1400098eb  nop     dword ptr [rax+rax+00h]
0x1400098f0  mov     esi, eax
0x1400098f2  test    eax, eax
0x1400098f4  jnz     loc_140009B33
0x1400098fa  mov     rax, [rsp+68h+ClonedOidRequest]
0x140009902  mov     [rsp+68h+arg_0], r14b
0x140009907  mov     [rax+0D8h], rdi
0x14000990e  mov     rcx, [rdi+10h]
0x140009912  mov     rax, [rsp+68h+ClonedOidRequest]
0x14000991a  mov     [rax+10h], rcx
0x14000991e  mov     rax, [rsp+68h+ClonedOidRequest]
0x140009926  mov     ecx, [rsp+68h+arg_8]
0x14000992a  mov     [rax+8], ecx
0x14000992d  mov     rax, [rsp+68h+ClonedOidRequest]
0x140009935  mov     [rax+0E0h], r15
0x14000993c  mov     rdx, [rsp+68h+ClonedOidRequest]; OidRequest
0x140009944  mov     rcx, [r13+80h]; NdisFilterHandle
0x14000994b  call    cs:__imp_NdisFDirectOidRequest
0x140009952  nop     dword ptr [rax+rax+00h]
0x140009957  mov     esi, eax
0x140009959  test    eax, eax
0x14000995b  jnz     loc_140009B60
0x140009961  lea     rbp, WPP_GLOBAL_Control
0x140009968  cmp     esi, 103h
0x14000996e  jz      short loc_14000998F
0x140009970  mov     rdx, [rsp+68h+ClonedOidRequest]
0x140009978  test    rdx, rdx
0x14000997b  jz      loc_140009BA0
0x140009981  xor     r9d, r9d
0x140009984  mov     r8d, esi
0x140009987  mov     rcx, r13
0x14000998a  call    FilterDirectOidRequestCompleteCommon
0x14000998f  cmp     [rsp+68h+arg_0], r12b
0x140009994  jz      loc_140009BB1
0x14000999a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400099a1  cmp     rcx, rbp
0x1400099a4  jnz     short loc_1400099C1
0x1400099a6  mov     rbx, [rsp+68h+arg_18]
0x1400099ae  mov     eax, esi
0x1400099b0  add     rsp, 30h
0x1400099b4  pop     r15
0x1400099b6  pop     r14
0x1400099b8  pop     r13
0x1400099ba  pop     r12
0x1400099bc  pop     rdi
0x1400099bd  pop     rsi
0x1400099be  pop     rbp
0x1400099bf  retn
0x1400099c1  mov     eax, [rcx+2Ch]
0x1400099c4  test    al, 20h
0x1400099c6  jz      short loc_1400099A6
0x1400099c8  mov     rcx, [rcx+18h]
0x1400099cc  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x1400099d3  mov     edx, 0C3h
0x1400099d8  mov     r9d, esi
0x1400099db  call    WPP_SF_d
0x1400099e0  jmp     short loc_1400099A6
0x1400099e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400099e9  cmp     rcx, r12
0x1400099ec  jnz     short loc_140009A62
0x1400099ee  xor     r9d, r9d
0x1400099f1  lea     rdx, aFilterunlock; "FilterUnlock"
0x1400099f8  mov     r8d, 1AEh
0x1400099fe  mov     rcx, rbp
0x140009a01  mov     esi, ebx
0x140009a03  mov     r14b, bl
0x140009a06  call    ReleaseSpinLock
0x140009a0b  xor     r12d, r12d
0x140009a0e  lea     rbx, [r15+88h]
0x140009a15  lea     rbp, WPP_GLOBAL_Control
0x140009a1c  jmp     loc_140009970
0x140009a21  mov     eax, [rcx+2Ch]
0x140009a24  test    al, 20h
0x140009a26  jnz     short loc_140009A83
0x140009a28  mov     rcx, cs:WPP_GLOBAL_Control
0x140009a2f  cmp     rcx, r12
0x140009a32  jz      loc_140009824
0x140009a38  mov     eax, [rcx+2Ch]
0x140009a3b  test    al, 4
0x140009a3d  jz      loc_140009824
0x140009a43  mov     eax, [r15+68h]
0x140009a47  mov     edx, 0BEh
0x140009a4c  mov     r9d, [rdi+20h]
0x140009a50  mov     rcx, [rcx+18h]
0x140009a54  mov     [rsp+68h+var_48], eax
0x140009a58  call    WPP_SF_Dd
0x140009a5d  jmp     loc_140009824
0x140009a62  mov     eax, [rcx+2Ch]
0x140009a65  test    al, 4
0x140009a67  jz      short loc_1400099EE
0x140009a69  mov     edx, 0C0h
0x140009a6e  mov     rcx, [rcx+18h]
0x140009a72  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140009a79  call    WPP_SF_
0x140009a7e  jmp     loc_1400099EE
0x140009a83  mov     rcx, [rcx+18h]
0x140009a87  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140009a8e  mov     edx, 0BDh
0x140009a93  call    WPP_SF_
0x140009a98  jmp     short loc_140009A28
0x140009a9a  mov     r9d, 1A7h
0x140009aa0  lea     r8, aFilterlock; "FilterLock"
0x140009aa7  mov     rdx, rbp
0x140009aaa  lea     rcx, Format; "Trying to acquire uninited lock %p, %s,"...
0x140009ab1  call    cs:__imp_DbgPrint
0x140009ab8  nop     dword ptr [rax+rax+00h]
0x140009abd  int     3; Trap to Debugger
0x140009abe  jmp     loc_140009839
0x140009ac3  mov     r8d, 0BD2h
0x140009ac9  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x140009ad0  lea     rcx, aPfilterFlowpow; "!pFilter->fLowPower"
0x140009ad7  call    TraceAssert
0x140009adc  cmp     [r13+0A60h], bl
0x140009ae3  jz      loc_14000987A
0x140009ae9  mov     rcx, cs:WPP_GLOBAL_Control
0x140009af0  cmp     rcx, r12
0x140009af3  jz      loc_1400099EE
0x140009af9  mov     eax, [rcx+2Ch]
0x140009afc  test    al, 4
0x140009afe  jz      loc_1400099EE
0x140009b04  mov     edx, 0BFh
0x140009b09  jmp     loc_140009A6E
0x140009b0e  mov     r9d, 1AEh
0x140009b14  lea     rcx, Format; "Trying to acquire uninited lock %p, %s,"...
0x140009b1b  mov     r8, r12
0x140009b1e  mov     rdx, rbp
0x140009b21  call    cs:__imp_DbgPrint
0x140009b28  nop     dword ptr [rax+rax+00h]
0x140009b2d  int     3; Trap to Debugger
0x140009b2e  jmp     loc_1400098A3
0x140009b33  mov     rcx, cs:WPP_GLOBAL_Control
0x140009b3a  lea     rbp, WPP_GLOBAL_Control
0x140009b41  cmp     rcx, rbp
0x140009b44  jz      loc_140009968
0x140009b4a  mov     edx, [rcx+2Ch]
0x140009b4d  test    r14b, dl
0x140009b50  jz      loc_140009968
0x140009b56  mov     edx, 0C1h
0x140009b5b  mov     r9d, eax
0x140009b5e  jmp     short loc_140009B8B
0x140009b60  mov     rcx, cs:WPP_GLOBAL_Control
0x140009b67  lea     rbp, WPP_GLOBAL_Control
0x140009b6e  cmp     rcx, rbp
0x140009b71  jz      loc_140009968
0x140009b77  mov     eax, [rcx+2Ch]
0x140009b7a  test    r14b, al
0x140009b7d  jz      loc_140009968
0x140009b83  mov     edx, 0C2h
0x140009b88  mov     r9d, esi
0x140009b8b  mov     rcx, [rcx+18h]
0x140009b8f  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140009b96  call    WPP_SF_d
0x140009b9b  jmp     loc_140009968
0x140009ba0  test    r14b, r14b
0x140009ba3  jz      loc_14000998F
0x140009ba9  lock dec dword ptr [rbx]
0x140009bac  jmp     loc_14000998F
0x140009bb1  mov     ecx, [rdi+4]
0x140009bb4  test    ecx, ecx
0x140009bb6  jz      short loc_140009BD8
0x140009bb8  sub     ecx, 1
0x140009bbb  jz      short loc_140009BD8
0x140009bbd  sub     ecx, 1
0x140009bc0  jz      short loc_140009BD8
0x140009bc2  cmp     ecx, 0Ah
0x140009bc5  jnz     short loc_140009BD8
0x140009bc7  mov     qword ptr [rdi+40h], 0
0x140009bcf  mov     [rdi+3Ch], r12d
0x140009bd3  jmp     loc_14000999A
0x140009bd8  mov     qword ptr [rdi+34h], 0
0x140009be0  jmp     loc_14000999A
```
