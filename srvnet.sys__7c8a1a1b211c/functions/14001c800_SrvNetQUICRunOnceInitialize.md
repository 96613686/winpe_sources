# SrvNetQUICRunOnceInitialize

- ea: `0x14001c800`
- end: `0x14001cb79`
- name: `SrvNetQUICRunOnceInitialize`
- size: `889`
- prototype: `RTL_RUN_ONCE_INIT_FN`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14001389c`
- `0x14001c800`
- `0x14002a4c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001c82c`
- `ntoskrnl!ExAllocatePool2` at `0x14001c82c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c8f3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c8f3`
- `ntoskrnl!KeInitializeEvent` at `0x14001c855`
- `ntoskrnl!KeInitializeEvent` at `0x14001c855`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c974`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cb4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c974`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cb4e`
- `NETIO!NmrDeregisterClient` at `0x14001c943`
- `NETIO!NmrDeregisterClient` at `0x14001cb1d`
- `NETIO!NmrDeregisterClient` at `0x14001c943`
- `NETIO!NmrDeregisterClient` at `0x14001cb1d`
- `NETIO!NmrClientDetachProviderComplete` at `0x14001c92f`
- `NETIO!NmrClientDetachProviderComplete` at `0x14001cb09`
- `NETIO!NmrClientDetachProviderComplete` at `0x14001c92f`
- `NETIO!NmrClientDetachProviderComplete` at `0x14001cb09`
- `NETIO!NmrRegisterClient` at `0x14001c8bc`
- `NETIO!NmrRegisterClient` at `0x14001c8bc`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14001c959`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14001cb33`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14001c959`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14001cb33`

## pseudocode

```c
__int64 __fastcall SrvNetQUICRunOnceInitialize(PRTL_RUN_ONCE a1, PVOID a2, PVOID *a3)
{
  __int64 Pool2; // rax
  __int64 v4; // rbx
  NTSTATUS v5; // edi
  HANDLE *v6; // rsi
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  PVOID v15; // rbx
  HANDLE *v16; // rdi
  _QWORD v17[7]; // [rsp+30h] [rbp-38h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+88h] [rbp+20h] BYREF

  v17[1] = 0;
  v17[0] = "SMB Server";
  Pool2 = ExAllocatePool2(64, 152, 1666077005);
  v4 = Pool2;
  if ( !Pool2 )
  {
    v5 = -1073741670;
LABEL_13:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          63,
          WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids,
          (unsigned int)v5);
    }
    return 0;
  }
  KeInitializeEvent((PRKEVENT)(Pool2 + 112), SynchronizationEvent, 0);
  *(_DWORD *)(v4 + 92) = 1;
  *(_WORD *)(v4 + 88) = 24;
  *(_QWORD *)(v4 + 8) = _MsQuicClientAttachProvider;
  v6 = (HANDLE *)(v4 + 80);
  *(_WORD *)(v4 + 2) = 72;
  *(GUID *)(v4 + 96) = PROV_SRV2;
  *(_QWORD *)(v4 + 16) = _MsQuicClientDetachProvider;
  *(_QWORD *)(v4 + 48) = v4 + 88;
  *(_QWORD *)(v4 + 40) = MSQUIC_NPI_ID;
  *(_DWORD *)(v4 + 32) = 2621440;
  v5 = NmrRegisterClient((PNPI_CLIENT_CHARACTERISTICS)v4, (PVOID)v4, (PHANDLE)(v4 + 80));
  if ( v5 < 0 )
  {
LABEL_6:
    _m_prefetchw((const void *)(v4 + 144));
    if ( _InterlockedOr8((volatile signed __int8 *)(v4 + 144), 1u) )
      NmrClientDetachProviderComplete(*v6);
    if ( *v6 )
    {
      if ( NmrDeregisterClient(*v6) == 259 )
        NmrWaitForClientDeregisterComplete(*v6);
      *v6 = 0;
    }
    ExFreePoolWithTag((PVOID)v4, 0x634E514Du);
    goto LABEL_13;
  }
  Timeout.QuadPart = 0;
  if ( KeWaitForSingleObject((PVOID)(v4 + 112), Executive, 0, 0, &Timeout) )
  {
    v5 = -1073741823;
    goto LABEL_6;
  }
  QuicNmrHandle = (PVOID)v4;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*((_QWORD *)QuicNmrHandle + 17) + 8LL))(2, &MsQuic);
  v11 = (unsigned int)v8;
  if ( v8 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_30;
    }
    v13 = 64;
LABEL_29:
    WPP_SF_d(v12->AttachedDevice, v13, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids, v11);
LABEL_30:
    if ( SMBQuicRegistration )
    {
      (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(MsQuic + 48))(SMBQuicRegistration, v9, v10, v11);
      SMBQuicRegistration = 0;
    }
    if ( MsQuic )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64, __int64))(*((_QWORD *)QuicNmrHandle + 17) + 16LL))(
        MsQuic,
        *((_QWORD *)QuicNmrHandle + 17),
        v10,
        v11);
      MsQuic = 0;
    }
    v15 = QuicNmrHandle;
    if ( QuicNmrHandle )
    {
      v16 = (HANDLE *)((char *)QuicNmrHandle + 80);
      _m_prefetchw((char *)QuicNmrHandle + 144);
      if ( _InterlockedOr8((volatile signed __int8 *)QuicNmrHandle + 144, 1u) )
        NmrClientDetachProviderComplete(*v16);
      if ( *v16 )
      {
        if ( NmrDeregisterClient(*v16) == 259 )
          NmrWaitForClientDeregisterComplete(*v16);
        *v16 = 0;
      }
      ExFreePoolWithTag(v15, 0x634E514Du);
      QuicNmrHandle = 0;
    }
    return 0;
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *, __int64, _QWORD))(MsQuic + 40))(
          v17,
          &SMBQuicRegistration,
          v10,
          (unsigned int)v8);
  v11 = (unsigned int)v14;
  if ( v14 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_30;
    }
    v13 = 65;
    goto LABEL_29;
  }
  return 1;
}

```

## disassembly

```asm
0x14001c800  push    rbx
0x14001c802  push    rbp
0x14001c803  push    rsi
0x14001c804  push    rdi
0x14001c805  sub     rsp, 48h
0x14001c809  mov     edx, 98h
0x14001c80e  mov     [rsp+68h+var_30], 0
0x14001c817  lea     rax, aSmbServer; "SMB Server"
0x14001c81e  mov     r8d, 634E514Dh
0x14001c824  mov     [rsp+68h+var_38], rax
0x14001c829  lea     ecx, [rdx-58h]
0x14001c82c  call    cs:__imp_ExAllocatePool2
0x14001c833  nop     dword ptr [rax+rax+00h]
0x14001c838  mov     rbx, rax
0x14001c83b  test    rax, rax
0x14001c83e  jnz     short loc_14001C84A
0x14001c840  mov     edi, 0C000009Ah
0x14001c845  jmp     loc_14001C984
0x14001c84a  xor     r8d, r8d; State
0x14001c84d  lea     rcx, [rax+70h]; Event
0x14001c851  lea     edx, [r8+1]; Type
0x14001c855  call    cs:__imp_KeInitializeEvent
0x14001c85c  nop     dword ptr [rax+rax+00h]
0x14001c861  mov     dword ptr [rbx+5Ch], 1
0x14001c868  lea     rcx, [rbx+58h]
0x14001c86c  mov     word ptr [rcx], 18h
0x14001c871  lea     rax, __MsQuicClientAttachProvider
0x14001c878  movups  xmm0, xmmword ptr cs:PROV_SRV2.Data1
0x14001c87f  mov     [rbx+8], rax
0x14001c883  lea     rsi, [rbx+50h]
0x14001c887  lea     rax, __MsQuicClientDetachProvider
0x14001c88e  mov     word ptr [rbx+2], 48h ; 'H'
0x14001c894  movdqu  xmmword ptr [rbx+60h], xmm0
0x14001c899  mov     [rbx+10h], rax
0x14001c89d  mov     r8, rsi; NmrClientHandle
0x14001c8a0  lea     rax, MSQUIC_NPI_ID
0x14001c8a7  mov     [rbx+30h], rcx
0x14001c8ab  mov     rcx, rbx; ClientCharacteristics
0x14001c8ae  mov     [rbx+28h], rax
0x14001c8b2  mov     rdx, rbx; ClientContext
0x14001c8b5  mov     dword ptr [rbx+20h], 280000h
0x14001c8bc  call    cs:__imp_NmrRegisterClient
0x14001c8c3  nop     dword ptr [rax+rax+00h]
0x14001c8c8  mov     edi, eax
0x14001c8ca  test    eax, eax
0x14001c8cc  js      short loc_14001C90C
0x14001c8ce  lea     rax, [rsp+68h+arg_18]
0x14001c8d6  mov     qword ptr [rsp+68h+arg_18], 0
0x14001c8e2  xor     r9d, r9d; Alertable
0x14001c8e5  mov     [rsp+68h+Timeout], rax; Timeout
0x14001c8ea  xor     r8d, r8d; WaitMode
0x14001c8ed  lea     rcx, [rbx+70h]; Object
0x14001c8f1  xor     edx, edx; WaitReason
0x14001c8f3  call    cs:__imp_KeWaitForSingleObject
0x14001c8fa  nop     dword ptr [rax+rax+00h]
0x14001c8ff  test    eax, eax
0x14001c901  jz      loc_14001C9C5
0x14001c907  mov     edi, 0C0000001h
0x14001c90c  prefetchw byte ptr [rbx+90h]
0x14001c913  mov     al, [rbx+90h]
0x14001c919  mov     cl, al
0x14001c91b  or      cl, 1
0x14001c91e  lock cmpxchg [rbx+90h], cl
0x14001c926  jnz     short loc_14001C919
0x14001c928  test    al, al
0x14001c92a  jz      short loc_14001C93B
0x14001c92c  mov     rcx, [rsi]; NmrBindingHandle
0x14001c92f  call    cs:__imp_NmrClientDetachProviderComplete
0x14001c936  nop     dword ptr [rax+rax+00h]
0x14001c93b  mov     rcx, [rsi]; NmrClientHandle
0x14001c93e  test    rcx, rcx
0x14001c941  jz      short loc_14001C96C
0x14001c943  call    cs:__imp_NmrDeregisterClient
0x14001c94a  nop     dword ptr [rax+rax+00h]
0x14001c94f  cmp     eax, 103h
0x14001c954  jnz     short loc_14001C965
0x14001c956  mov     rcx, [rsi]; NmrClientHandle
0x14001c959  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x14001c960  nop     dword ptr [rax+rax+00h]
0x14001c965  mov     qword ptr [rsi], 0
0x14001c96c  mov     edx, 634E514Dh; Tag
0x14001c971  mov     rcx, rbx; P
0x14001c974  call    cs:__imp_ExFreePoolWithTag
0x14001c97b  nop     dword ptr [rax+rax+00h]
0x14001c980  test    edi, edi
0x14001c982  jns     short loc_14001C9CC
0x14001c984  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001c98b  lea     rax, WPP_GLOBAL_Control
0x14001c992  cmp     rcx, rax
0x14001c995  jz      short loc_14001C9BE
0x14001c997  test    dword ptr [rcx+2Ch], 200000h
0x14001c99e  jz      short loc_14001C9BE
0x14001c9a0  cmp     byte ptr [rcx+29h], 1
0x14001c9a4  jb      short loc_14001C9BE
0x14001c9a6  mov     rcx, [rcx+18h]
0x14001c9aa  lea     r8, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids
0x14001c9b1  mov     edx, 3Fh ; '?'
0x14001c9b6  mov     r9d, edi
0x14001c9b9  call    WPP_SF_d
0x14001c9be  xor     eax, eax
0x14001c9c0  jmp     loc_14001CB6F
0x14001c9c5  mov     cs:QuicNmrHandle, rbx
0x14001c9cc  mov     rax, cs:QuicNmrHandle
0x14001c9d3  lea     rdx, MsQuic
0x14001c9da  mov     rcx, [rax+88h]
0x14001c9e1  mov     rax, [rcx+8]
0x14001c9e5  mov     ecx, 2
0x14001c9ea  call    _guard_dispatch_icall
0x14001c9ef  mov     r9d, eax
0x14001c9f2  test    eax, eax
0x14001c9f4  jns     short loc_14001CA1F
0x14001c9f6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001c9fd  lea     rax, WPP_GLOBAL_Control
0x14001ca04  cmp     rcx, rax
0x14001ca07  jz      short loc_14001CA7D
0x14001ca09  test    dword ptr [rcx+2Ch], 200000h
0x14001ca10  jz      short loc_14001CA7D
0x14001ca12  cmp     byte ptr [rcx+29h], 1
0x14001ca16  jb      short loc_14001CA7D
0x14001ca18  mov     edx, 40h ; '@'
0x14001ca1d  jmp     short loc_14001CA6D
0x14001ca1f  mov     rax, cs:MsQuic
0x14001ca26  lea     rdx, SMBQuicRegistration
0x14001ca2d  lea     rcx, [rsp+68h+var_38]
0x14001ca32  mov     rax, [rax+28h]
0x14001ca36  call    _guard_dispatch_icall
0x14001ca3b  mov     r9d, eax
0x14001ca3e  test    eax, eax
0x14001ca40  jns     loc_14001CB6A
0x14001ca46  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001ca4d  lea     rax, WPP_GLOBAL_Control
0x14001ca54  cmp     rcx, rax
0x14001ca57  jz      short loc_14001CA7D
0x14001ca59  test    dword ptr [rcx+2Ch], 200000h
0x14001ca60  jz      short loc_14001CA7D
0x14001ca62  cmp     byte ptr [rcx+29h], 1
0x14001ca66  jb      short loc_14001CA7D
0x14001ca68  mov     edx, 41h ; 'A'
0x14001ca6d  mov     rcx, [rcx+18h]
0x14001ca71  lea     r8, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids
0x14001ca78  call    WPP_SF_d
0x14001ca7d  mov     rcx, cs:SMBQuicRegistration
0x14001ca84  test    rcx, rcx
0x14001ca87  jz      short loc_14001CAA4
0x14001ca89  mov     rax, cs:MsQuic
0x14001ca90  mov     rax, [rax+30h]
0x14001ca94  call    _guard_dispatch_icall
0x14001ca99  mov     cs:SMBQuicRegistration, 0
0x14001caa4  mov     rcx, cs:MsQuic
0x14001caab  test    rcx, rcx
0x14001caae  jz      short loc_14001CAD2
0x14001cab0  mov     rax, cs:QuicNmrHandle
0x14001cab7  mov     rdx, [rax+88h]
0x14001cabe  mov     rax, [rdx+10h]
0x14001cac2  call    _guard_dispatch_icall
0x14001cac7  mov     cs:MsQuic, 0
0x14001cad2  mov     rbx, cs:QuicNmrHandle
0x14001cad9  test    rbx, rbx
0x14001cadc  jz      loc_14001C9BE
0x14001cae2  lea     rdi, [rbx+50h]
0x14001cae6  prefetchw byte ptr [rbx+90h]
0x14001caed  mov     al, [rbx+90h]
0x14001caf3  mov     cl, al
0x14001caf5  or      cl, 1
0x14001caf8  lock cmpxchg [rbx+90h], cl
0x14001cb00  jnz     short loc_14001CAF3
0x14001cb02  test    al, al
0x14001cb04  jz      short loc_14001CB15
0x14001cb06  mov     rcx, [rdi]; NmrBindingHandle
0x14001cb09  call    cs:__imp_NmrClientDetachProviderComplete
0x14001cb10  nop     dword ptr [rax+rax+00h]
0x14001cb15  mov     rcx, [rdi]; NmrClientHandle
0x14001cb18  test    rcx, rcx
0x14001cb1b  jz      short loc_14001CB46
0x14001cb1d  call    cs:__imp_NmrDeregisterClient
0x14001cb24  nop     dword ptr [rax+rax+00h]
0x14001cb29  cmp     eax, 103h
0x14001cb2e  jnz     short loc_14001CB3F
0x14001cb30  mov     rcx, [rdi]; NmrClientHandle
0x14001cb33  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x14001cb3a  nop     dword ptr [rax+rax+00h]
0x14001cb3f  mov     qword ptr [rdi], 0
0x14001cb46  mov     edx, 634E514Dh; Tag
0x14001cb4b  mov     rcx, rbx; P
0x14001cb4e  call    cs:__imp_ExFreePoolWithTag
0x14001cb55  nop     dword ptr [rax+rax+00h]
0x14001cb5a  mov     cs:QuicNmrHandle, 0
0x14001cb65  jmp     loc_14001C9BE
0x14001cb6a  mov     eax, 1
0x14001cb6f  add     rsp, 48h
0x14001cb73  pop     rdi
0x14001cb74  pop     rsi
0x14001cb75  pop     rbp
0x14001cb76  pop     rbx
0x14001cb77  retn
```
