# FilterDeleteVirtualMac

- ea: `0x140003b7c`
- end: `0x140003fe1`
- name: `FilterDeleteVirtualMac`
- size: `1125`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1400038f0`
- `0x1400041a0`
- `0x14000745c`
- `0x14000ea3c`

## callees

- `0x140003b7c`
- `0x140007d58`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000f110`
- `0x14000f500`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140003e82`
- `ntoskrnl!DbgPrint` at `0x140003ec5`
- `ntoskrnl!DbgPrint` at `0x140003e82`
- `ntoskrnl!DbgPrint` at `0x140003ec5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003c2c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003c2c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003c9d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003c9d`
- `NDIS!NdisFOidRequest` at `0x140003dc1`
- `NDIS!NdisFOidRequest` at `0x140003dc1`
- `NDIS!NdisInitializeEvent` at `0x140003d7d`
- `NDIS!NdisInitializeEvent` at `0x140003d7d`
- `NDIS!NdisWaitEvent` at `0x140003ddc`
- `NDIS!NdisWaitEvent` at `0x140003ddc`

## pseudocode

```c
void __fastcall FilterDeleteVirtualMac(__int64 a1)
{
  char v1; // r15
  __int64 v3; // r14
  KIRQL v4; // dl
  int v5; // eax
  int v6; // eax
  void *v7; // rcx
  NDIS_STATUS v8; // ebx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  __int128 v12; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE OidRequest[280]; // [rsp+60h] [rbp-A0h] BYREF

  v1 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  if ( !*(_DWORD *)(a1 + 104) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    goto LABEL_18;
  }
  v3 = *(_QWORD *)(a1 + 8);
  if ( *(_DWORD *)(v3 + 24) != 1801678668 )
  {
    DbgPrint("Trying to acquire uninited lock %p, %s, Line %d\n", (const void *)(v3 + 24), "FilterLock", 423);
    __debugbreak();
  }
  _InterlockedIncrement((volatile signed __int32 *)(v3 + 28));
  *(_BYTE *)(v3 + 112) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 104));
  *(_QWORD *)(v3 + 72) = "FilterLock";
  *(_BYTE *)(v3 + 32) = 1;
  *(_DWORD *)(v3 + 80) = 423;
  if ( *(_BYTE *)(a1 + 3) )
  {
    *(_BYTE *)(a1 + 3) = 0;
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 132));
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    v1 = 1;
  }
  if ( *(_DWORD *)(v3 + 24) != 1801678668 )
  {
    DbgPrint("Trying to acquire uninited lock %p, %s, Line %d\n", (const void *)(v3 + 24), "FilterUnlock", 430);
    __debugbreak();
  }
  v4 = *(_BYTE *)(v3 + 112);
  *(_QWORD *)(v3 + 88) = "FilterUnlock";
  *(_DWORD *)(v3 + 96) = 430;
  *(_BYTE *)(v3 + 32) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 104), v4);
  _InterlockedDecrement((volatile signed __int32 *)(v3 + 28));
  if ( !v1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    v5 = *(_DWORD *)(v3 + 2692);
    if ( v5 == 16 )
    {
      v6 = *(_DWORD *)(a1 + 104);
      v12 = 0;
      DWORD1(v12) = v6;
      memset(OidRequest, 0, sizeof(OidRequest));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 237, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
      memset(OidRequest, 0, 0xF8u);
      NdisInitializeEvent((PNDIS_EVENT)&OidRequest[248]);
      v7 = *(void **)(v3 + 128);
      *(_QWORD *)&OidRequest[40] = &v12;
      *(_DWORD *)OidRequest = 15466902;
      *(_DWORD *)&OidRequest[4] = 1;
      *(_DWORD *)&OidRequest[32] = 235143426;
      *(_DWORD *)&OidRequest[48] = 16;
      *(_QWORD *)&OidRequest[16] = 1380341590;
      v8 = NdisFOidRequest(v7, (PNDIS_OID_REQUEST)OidRequest);
      if ( v8 == 259 )
      {
        NdisWaitEvent((PNDIS_EVENT)&OidRequest[248], 0);
        v8 = *(_DWORD *)&OidRequest[272];
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 238, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
      if ( !v8 )
        goto LABEL_30;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_30;
      v10 = 77;
    }
    else if ( v5 == 9 )
    {
      v11 = *(_DWORD *)(a1 + 104);
      v12 = 0;
      DWORD1(v12) = v11;
      if ( !(unsigned int)filterDoInternalRequest(v3, 1, 234946855, (unsigned int)&v12, 16, 0) )
        goto LABEL_30;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_30;
      v10 = 78;
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_30;
      v10 = 79;
    }
    WPP_SF_d(v9->AttachedDevice, v10, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
LABEL_30:
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 132));
  }
LABEL_18:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
}

```

## disassembly

```asm
0x140003b7c  push    rbp
0x140003b7e  push    rbx
0x140003b7f  push    rsi
0x140003b80  push    rdi
0x140003b81  push    r12
0x140003b83  push    r13
0x140003b85  push    r14
0x140003b87  push    r15
0x140003b89  lea     rbp, [rsp-98h]
0x140003b91  sub     rsp, 198h
0x140003b98  mov     rax, cs:__security_cookie
0x140003b9f  xor     rax, rsp
0x140003ba2  mov     [rbp+0D0h+var_50], rax
0x140003ba9  xor     r15d, r15d
0x140003bac  mov     rdi, rcx
0x140003baf  mov     ebx, r15d
0x140003bb2  mov     [rsp+1D0h+var_190], r15d
0x140003bb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140003bbe  lea     r13, WPP_GLOBAL_Control
0x140003bc5  cmp     rcx, r13
0x140003bc8  jz      short loc_140003BD5
0x140003bca  mov     eax, [rcx+2Ch]
0x140003bcd  test    al, 20h
0x140003bcf  jnz     loc_140003E51
0x140003bd5  cmp     [rdi+68h], r15d
0x140003bd9  jnz     short loc_140003C10
0x140003bdb  mov     rcx, cs:WPP_GLOBAL_Control
0x140003be2  cmp     rcx, r13
0x140003be5  jz      loc_140003CB2
0x140003beb  mov     eax, [rcx+2Ch]
0x140003bee  test    al, 4
0x140003bf0  jz      loc_140003CB2
0x140003bf6  mov     rcx, [rcx+18h]
0x140003bfa  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140003c01  mov     edx, 4Ah ; 'J'
0x140003c06  call    WPP_SF_
0x140003c0b  jmp     loc_140003CB2
0x140003c10  mov     r14, [rdi+8]
0x140003c14  lea     rsi, [r14+18h]
0x140003c18  cmp     dword ptr [rsi], 6B636F4Ch
0x140003c1e  jnz     loc_140003E6B
0x140003c24  lock inc dword ptr [rsi+4]
0x140003c28  lea     rcx, [rsi+50h]; SpinLock
0x140003c2c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003c33  nop     dword ptr [rax+rax+00h]
0x140003c38  mov     [rsi+58h], al
0x140003c3b  lea     rax, aFilterlock; "FilterLock"
0x140003c42  mov     [rsi+30h], rax
0x140003c46  mov     byte ptr [rsi+8], 1
0x140003c4a  mov     dword ptr [rsi+38h], 1A7h
0x140003c51  cmp     [rdi+3], r15b
0x140003c55  jnz     loc_140003D03
0x140003c5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c62  cmp     rcx, r13
0x140003c65  jz      short loc_140003C72
0x140003c67  mov     eax, [rcx+2Ch]
0x140003c6a  test    al, 1
0x140003c6c  jnz     loc_140003E94
0x140003c72  mov     r15b, 1
0x140003c75  cmp     dword ptr [rsi], 6B636F4Ch
0x140003c7b  lea     rax, aFilterunlock; "FilterUnlock"
0x140003c82  jnz     loc_140003EB2
0x140003c88  mov     dl, [rsi+58h]; NewIrql
0x140003c8b  lea     rcx, [rsi+50h]; SpinLock
0x140003c8f  mov     [rsi+40h], rax
0x140003c93  mov     dword ptr [rsi+48h], 1AEh
0x140003c9a  mov     [rsi+8], bl
0x140003c9d  call    cs:__imp_KeReleaseSpinLock
0x140003ca4  nop     dword ptr [rax+rax+00h]
0x140003ca9  lock dec dword ptr [rsi+4]
0x140003cad  test    r15b, r15b
0x140003cb0  jz      short loc_140003D12
0x140003cb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140003cb9  cmp     rcx, r13
0x140003cbc  jnz     short loc_140003CE2
0x140003cbe  mov     rcx, [rbp+0D0h+var_50]
0x140003cc5  xor     rcx, rsp; StackCookie
0x140003cc8  call    __security_check_cookie
0x140003ccd  add     rsp, 198h
0x140003cd4  pop     r15
0x140003cd6  pop     r14
0x140003cd8  pop     r13
0x140003cda  pop     r12
0x140003cdc  pop     rdi
0x140003cdd  pop     rsi
0x140003cde  pop     rbx
0x140003cdf  pop     rbp
0x140003ce0  retn
0x140003ce2  mov     eax, [rcx+2Ch]
0x140003ce5  test    al, 20h
0x140003ce7  jz      short loc_140003CBE
0x140003ce9  mov     rcx, [rcx+18h]
0x140003ced  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140003cf4  mov     edx, 50h ; 'P'
0x140003cf9  mov     r9d, ebx
0x140003cfc  call    WPP_SF_d
0x140003d01  jmp     short loc_140003CBE
0x140003d03  mov     [rdi+3], bl
0x140003d06  lock inc dword ptr [rdi+84h]
0x140003d0d  jmp     loc_140003C75
0x140003d12  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d19  cmp     rcx, r13
0x140003d1c  jnz     loc_140003EDE
0x140003d22  mov     eax, [r14+0A84h]
0x140003d29  mov     ebx, 10h
0x140003d2e  cmp     eax, ebx
0x140003d30  jnz     loc_140003F2F
0x140003d36  mov     eax, [rdi+68h]
0x140003d39  lea     rcx, [rsp+1D0h+OidRequest]; void *
0x140003d3e  xorps   xmm0, xmm0
0x140003d41  xor     edx, edx; Val
0x140003d43  movups  [rsp+1D0h+var_188], xmm0
0x140003d48  mov     r8d, 118h; Size
0x140003d4e  mov     dword ptr [rsp+1D0h+var_188+4], eax
0x140003d52  call    memset
0x140003d57  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d5e  cmp     rcx, r13
0x140003d61  jnz     loc_140003E0B
0x140003d67  xor     edx, edx; Val
0x140003d69  lea     rcx, [rsp+1D0h+OidRequest]; void *
0x140003d6e  mov     r8d, 0F8h; Size
0x140003d74  call    memset
0x140003d79  lea     rcx, [rbp+0D0h+Event]; Event
0x140003d7d  call    cs:__imp_NdisInitializeEvent
0x140003d84  nop     dword ptr [rax+rax+00h]
0x140003d89  mov     rcx, [r14+80h]; NdisFilterHandle
0x140003d90  lea     rax, [rsp+1D0h+var_188]
0x140003d95  lea     rdx, [rsp+1D0h+OidRequest]; OidRequest
0x140003d9a  mov     qword ptr [rbp+0D0h+OidRequest.DATA+8], rax
0x140003d9e  mov     dword ptr [rsp+1D0h+OidRequest.Header.Type], 0EC0196h
0x140003da6  mov     [rsp+1D0h+OidRequest.RequestType], 1
0x140003dae  mov     dword ptr [rbp+0D0h+OidRequest.DATA], 0E040102h
0x140003db5  mov     dword ptr [rbp+0D0h+OidRequest.DATA+10h], ebx
0x140003db8  mov     [rsp+1D0h+OidRequest.RequestId], 52465756h
0x140003dc1  call    cs:__imp_NdisFOidRequest
0x140003dc8  nop     dword ptr [rax+rax+00h]
0x140003dcd  mov     ebx, eax
0x140003dcf  cmp     eax, 103h
0x140003dd4  jnz     short loc_140003DEB
0x140003dd6  xor     edx, edx; MsToWait
0x140003dd8  lea     rcx, [rbp+0D0h+Event]; Event
0x140003ddc  call    cs:__imp_NdisWaitEvent
0x140003de3  nop     dword ptr [rax+rax+00h]
0x140003de8  mov     ebx, [rbp+0D0h+var_60]
0x140003deb  mov     rcx, cs:WPP_GLOBAL_Control
0x140003df2  cmp     rcx, r13
0x140003df5  jnz     short loc_140003E30
0x140003df7  test    ebx, ebx
0x140003df9  jnz     loc_140003F07
0x140003dff  lock dec dword ptr [rdi+84h]
0x140003e06  jmp     loc_140003CB2
0x140003e0b  mov     eax, [rcx+2Ch]
0x140003e0e  test    al, 20h
0x140003e10  jz      loc_140003D67
0x140003e16  mov     rcx, [rcx+18h]
0x140003e1a  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140003e21  mov     edx, 0EDh
0x140003e26  call    WPP_SF_
0x140003e2b  jmp     loc_140003D67
0x140003e30  mov     eax, [rcx+2Ch]
0x140003e33  test    al, 20h
0x140003e35  jz      short loc_140003DF7
0x140003e37  mov     rcx, [rcx+18h]
0x140003e3b  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140003e42  mov     edx, 0EEh
0x140003e47  mov     r9d, ebx
0x140003e4a  call    WPP_SF_d
0x140003e4f  jmp     short loc_140003DF7
0x140003e51  mov     rcx, [rcx+18h]
0x140003e55  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140003e5c  mov     edx, 49h ; 'I'
0x140003e61  call    WPP_SF_
0x140003e66  jmp     loc_140003BD5
0x140003e6b  mov     r9d, 1A7h
0x140003e71  lea     r8, aFilterlock; "FilterLock"
0x140003e78  mov     rdx, rsi
0x140003e7b  lea     rcx, Format; "Trying to acquire uninited lock %p, %s,"...
0x140003e82  call    cs:__imp_DbgPrint
0x140003e89  nop     dword ptr [rax+rax+00h]
0x140003e8e  int     3; Trap to Debugger
0x140003e8f  jmp     loc_140003C24
0x140003e94  mov     r9d, [rdi+68h]
0x140003e98  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140003e9f  mov     rcx, [rcx+18h]
0x140003ea3  mov     edx, 4Bh ; 'K'
0x140003ea8  call    WPP_SF_d
0x140003ead  jmp     loc_140003C72
0x140003eb2  mov     r9d, 1AEh
0x140003eb8  lea     rcx, Format; "Trying to acquire uninited lock %p, %s,"...
0x140003ebf  mov     r8, rax
0x140003ec2  mov     rdx, rsi
0x140003ec5  call    cs:__imp_DbgPrint
0x140003ecc  nop     dword ptr [rax+rax+00h]
0x140003ed1  int     3; Trap to Debugger
0x140003ed2  lea     rax, aFilterunlock; "FilterUnlock"
0x140003ed9  jmp     loc_140003C88
0x140003ede  mov     eax, [rcx+2Ch]
0x140003ee1  test    al, 4
0x140003ee3  jz      loc_140003D22
0x140003ee9  mov     r9d, [rdi+68h]
0x140003eed  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140003ef4  mov     rcx, [rcx+18h]
0x140003ef8  mov     edx, 4Ch ; 'L'
0x140003efd  call    WPP_SF_d
0x140003f02  jmp     loc_140003D22
0x140003f07  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f0e  cmp     rcx, r13
0x140003f11  jz      loc_140003DFF
0x140003f17  mov     eax, [rcx+2Ch]
0x140003f1a  test    al, 1
0x140003f1c  jz      loc_140003DFF
0x140003f22  mov     edx, 4Dh ; 'M'
0x140003f27  mov     r9d, ebx
0x140003f2a  jmp     loc_140003FCC
0x140003f2f  cmp     eax, 9
0x140003f32  jnz     short loc_140003FA1
0x140003f34  mov     eax, [rdi+68h]
0x140003f37  lea     r9, [rsp+1D0h+var_188]
0x140003f3c  xorps   xmm0, xmm0
0x140003f3f  mov     edx, 1
0x140003f44  movups  [rsp+1D0h+var_188], xmm0
0x140003f49  mov     dword ptr [rsp+1D0h+var_188+4], eax
0x140003f4d  mov     r8d, 0E010127h
0x140003f53  lea     rax, [rsp+1D0h+var_190]
0x140003f58  mov     rcx, r14
0x140003f5b  mov     [rsp+1D0h+var_198], rax
0x140003f60  mov     [rsp+1D0h+var_1A8], 0
0x140003f68  mov     [rsp+1D0h+var_1B0], ebx
0x140003f6c  call    filterDoInternalRequest
0x140003f71  mov     ebx, eax
0x140003f73  test    eax, eax
0x140003f75  jz      loc_140003DFF
0x140003f7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f82  cmp     rcx, r13
0x140003f85  jz      loc_140003DFF
0x140003f8b  mov     edx, [rcx+2Ch]
0x140003f8e  test    dl, 1
0x140003f91  jz      loc_140003DFF
0x140003f97  mov     edx, 4Eh ; 'N'
0x140003f9c  mov     r9d, eax
0x140003f9f  jmp     short loc_140003FCC
0x140003fa1  mov     ebx, 0C0000001h
0x140003fa6  mov     rcx, cs:WPP_GLOBAL_Control
0x140003fad  cmp     rcx, r13
0x140003fb0  jz      loc_140003DFF
0x140003fb6  mov     eax, [rcx+2Ch]
0x140003fb9  test    al, 1
0x140003fbb  jz      loc_140003DFF
0x140003fc1  mov     edx, 4Fh ; 'O'
0x140003fc6  mov     r9d, 0C0000001h
0x140003fcc  mov     rcx, [rcx+18h]
0x140003fd0  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140003fd7  call    WPP_SF_d
0x140003fdc  jmp     loc_140003DFF
```
