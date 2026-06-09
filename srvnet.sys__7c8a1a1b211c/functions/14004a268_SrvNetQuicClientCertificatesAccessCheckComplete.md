# SrvNetQuicClientCertificatesAccessCheckComplete

- ea: `0x14004a268`
- end: `0x14004a453`
- name: `SrvNetQuicClientCertificatesAccessCheckComplete`
- size: `491`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400484c0`
- `0x1400491e0`

## callees

- `0x140007ec0`
- `0x14000bbcc`
- `0x140017448`
- `0x14001e238`
- `0x14001e480`
- `0x14002a4c0`
- `0x140049d48`
- `0x14004a268`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14004a3c6`
- `ntoskrnl!IoFreeWorkItem` at `0x14004a3c6`

## pseudocode

```c
__int64 __fastcall SrvNetQuicClientCertificatesAccessCheckComplete(int a1, __int64 a2)
{
  __int64 v2; // rbx
  _QWORD *v4; // rdi
  unsigned int v5; // ebp
  char v6; // si
  unsigned int v7; // r15d
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // r15d
  __int64 v13; // rcx

  v2 = a2 - 24;
  v4 = *(_QWORD **)(a2 - 24);
  v5 = *(_DWORD *)(a2 - 24 + 112);
  if ( a1 < 0 || v5 )
  {
    if ( a1 < 0 || (v7 = 49, v5 != -1067646969) )
      v7 = 80;
    v6 = 0;
  }
  else
  {
    v6 = 1;
    v7 = 0xFFFF;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_dqq(
      WPP_GLOBAL_Control->AttachedDevice,
      37,
      WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids,
      (unsigned int)a1,
      v4,
      v2);
  }
  LOBYTE(a2) = v6;
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(MsQuic + 240))(v4[49], a2, v7);
  if ( a1 >= 0 )
  {
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Dqq(WPP_GLOBAL_Control->AttachedDevice, v8, v9, v5, v4, v2);
      }
      v13 = 10;
      if ( v5 != -1067646969 )
        LOWORD(v13) = 1;
      SrvNetQUICReportShutdownError(v13, 5, v4);
    }
  }
  else
  {
    SrvNetQUICReportShutdownError(1, 6, v4);
  }
  if ( v11 < 0 )
  {
    if ( v6 )
      SrvNetQUICReportShutdownError(1, 7, v4);
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(MsQuic + 136))(v4[49], 0, 1);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    LOBYTE(v10) = v6 != 0 ? 84 : 70;
    WPP_SF_cDqq(WPP_GLOBAL_Control->AttachedDevice, v8, v9, v10, v11, v4, v2);
  }
  SrvNetDereferenceConnection(v4);
  IoFreeWorkItem(*(PIO_WORKITEM *)(v2 + 120));
  SrvNetWskNotifyCleanupProviderContext(*(_QWORD *)(v2 + 16));
  return SrvNetWskNotifyCleanupProviderContext(v2);
}

```

## disassembly

```asm
0x14004a268  push    rbx
0x14004a26a  push    rbp
0x14004a26b  push    rsi
0x14004a26c  push    rdi
0x14004a26d  push    r12
0x14004a26f  push    r14
0x14004a271  push    r15
0x14004a273  sub     rsp, 40h
0x14004a277  lea     rbx, [rdx-18h]
0x14004a27b  mov     r14d, ecx
0x14004a27e  mov     rdi, [rbx]
0x14004a281  mov     r12d, 1
0x14004a287  mov     ebp, [rbx+70h]
0x14004a28a  test    ecx, ecx
0x14004a28c  js      short loc_14004A29D
0x14004a28e  test    ebp, ebp
0x14004a290  jnz     short loc_14004A29D
0x14004a292  mov     sil, r12b
0x14004a295  mov     r15d, 0FFFFh
0x14004a29b  jmp     short loc_14004A2B9
0x14004a29d  test    r14d, r14d
0x14004a2a0  js      short loc_14004A2B0
0x14004a2a2  mov     r15d, 31h ; '1'
0x14004a2a8  cmp     ebp, 0C05D0007h
0x14004a2ae  jz      short loc_14004A2B6
0x14004a2b0  mov     r15d, 50h ; 'P'
0x14004a2b6  xor     sil, sil
0x14004a2b9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004a2c0  lea     rax, WPP_GLOBAL_Control
0x14004a2c7  cmp     rcx, rax
0x14004a2ca  jz      short loc_14004A2FD
0x14004a2cc  test    dword ptr [rcx+2Ch], 200000h
0x14004a2d3  jz      short loc_14004A2FD
0x14004a2d5  cmp     byte ptr [rcx+29h], 2
0x14004a2d9  jb      short loc_14004A2FD
0x14004a2db  mov     rcx, [rcx+18h]
0x14004a2df  lea     r8, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids
0x14004a2e6  mov     edx, 25h ; '%'
0x14004a2eb  mov     [rsp+78h+var_50], rbx
0x14004a2f0  mov     r9d, r14d
0x14004a2f3  mov     [rsp+78h+var_58], rdi
0x14004a2f8  call    WPP_SF_dqq
0x14004a2fd  mov     rax, cs:MsQuic
0x14004a304  mov     r8d, r15d
0x14004a307  mov     rcx, [rdi+188h]
0x14004a30e  mov     dl, sil
0x14004a311  mov     rax, [rax+0F0h]
0x14004a318  call    _guard_dispatch_icall
0x14004a31d  mov     r15d, eax
0x14004a320  test    r14d, r14d
0x14004a323  jns     loc_14004A3F3
0x14004a329  mov     edx, 6
0x14004a32e  mov     ecx, r12d
0x14004a331  mov     r8, rdi
0x14004a334  call    SrvNetQUICReportShutdownError
0x14004a339  lea     r14, WPP_GLOBAL_Control
0x14004a340  test    r15d, r15d
0x14004a343  jns     short loc_14004A379
0x14004a345  test    sil, sil
0x14004a348  jz      short loc_14004A35A
0x14004a34a  mov     edx, 7
0x14004a34f  mov     ecx, r12d
0x14004a352  mov     r8, rdi
0x14004a355  call    SrvNetQUICReportShutdownError
0x14004a35a  mov     rax, cs:MsQuic
0x14004a361  mov     r8, r12
0x14004a364  mov     rcx, [rdi+188h]
0x14004a36b  xor     edx, edx
0x14004a36d  mov     rax, [rax+88h]
0x14004a374  call    _guard_dispatch_icall
0x14004a379  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004a380  cmp     rcx, r14
0x14004a383  jz      short loc_14004A3BA
0x14004a385  test    dword ptr [rcx+2Ch], 200000h
0x14004a38c  jz      short loc_14004A3BA
0x14004a38e  cmp     [rcx+29h], r12b
0x14004a392  jb      short loc_14004A3BA
0x14004a394  mov     rcx, [rcx+18h]
0x14004a398  neg     sil
0x14004a39b  mov     [rsp+78h+var_48], rbx
0x14004a3a0  sbb     r9b, r9b
0x14004a3a3  mov     [rsp+78h+var_50], rdi
0x14004a3a8  and     r9b, 0Eh
0x14004a3ac  mov     dword ptr [rsp+78h+var_58], r15d
0x14004a3b1  add     r9b, 46h ; 'F'
0x14004a3b5  call    WPP_SF_cDqq
0x14004a3ba  mov     rcx, rdi; P
0x14004a3bd  call    SrvNetDereferenceConnection
0x14004a3c2  mov     rcx, [rbx+78h]; IoWorkItem
0x14004a3c6  call    cs:__imp_IoFreeWorkItem
0x14004a3cd  nop     dword ptr [rax+rax+00h]
0x14004a3d2  mov     rcx, [rbx+10h]
0x14004a3d6  call    SrvNetWskNotifyCleanupProviderContext
0x14004a3db  mov     rcx, rbx
0x14004a3de  call    SrvNetWskNotifyCleanupProviderContext
0x14004a3e3  add     rsp, 40h
0x14004a3e7  pop     r15
0x14004a3e9  pop     r14
0x14004a3eb  pop     r12
0x14004a3ed  pop     rdi
0x14004a3ee  pop     rsi
0x14004a3ef  pop     rbp
0x14004a3f0  pop     rbx
0x14004a3f1  retn
0x14004a3f3  test    ebp, ebp
0x14004a3f5  jz      loc_14004A339
0x14004a3fb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004a402  lea     r14, WPP_GLOBAL_Control
0x14004a409  cmp     rcx, r14
0x14004a40c  jz      short loc_14004A433
0x14004a40e  test    dword ptr [rcx+2Ch], 200000h
0x14004a415  jz      short loc_14004A433
0x14004a417  cmp     byte ptr [rcx+29h], 2
0x14004a41b  jb      short loc_14004A433
0x14004a41d  mov     rcx, [rcx+18h]
0x14004a421  mov     r9d, ebp
0x14004a424  mov     [rsp+78h+var_50], rbx
0x14004a429  mov     [rsp+78h+var_58], rdi
0x14004a42e  call    WPP_SF_Dqq
0x14004a433  mov     edx, 5
0x14004a438  cmp     ebp, 0C05D0007h
0x14004a43e  mov     r8, rdi
0x14004a441  lea     ecx, [rdx+5]
0x14004a444  cmovnz  cx, r12w
0x14004a449  call    SrvNetQUICReportShutdownError
0x14004a44e  jmp     loc_14004A340
```
