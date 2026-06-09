# CRegUdpEndpoint::Initialize(CUdpHandler *,tagWDS_PROPERTY *,ulong)

- ea: `0x180014c24`
- end: `0x180015118`
- name: `?Initialize@CRegUdpEndpoint@@QEAAKPEAVCUdpHandler@@PEAUtagWDS_PROPERTY@@K@Z`
- size: `1268`
- prototype: `__int64 __fastcall(CRegUdpEndpoint *this, struct CUdpHandler *, struct tagWDS_PROPERTY *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002108`

## callees

- `0x18000d9dc`
- `0x180014658`
- `0x180014c24`
- `0x180015660`
- `0x180017e10`
- `0x180017f24`
- `0x1800180ec`
- `0x18001c11e`
- `0x18001c12a`
- `0x18001c150`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180014ff3`
- `KERNEL32!LeaveCriticalSection` at `0x1800150de`
- `KERNEL32!LeaveCriticalSection` at `0x180014ff3`
- `KERNEL32!LeaveCriticalSection` at `0x1800150de`
- `KERNEL32!EnterCriticalSection` at `0x180014c65`
- `KERNEL32!EnterCriticalSection` at `0x180014f58`
- `KERNEL32!EnterCriticalSection` at `0x180014c65`
- `KERNEL32!EnterCriticalSection` at `0x180014f58`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014eb1`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014f01`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014f8a`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014fe4`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180015028`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800150cd`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014eb1`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014f01`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014f8a`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014fe4`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180015028`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800150cd`

## string_xrefs

- `0x180014f77`: `Attempt to register an endpoint with too many multicast group memberships`
- `0x180014ea2`: `Invalid attempt to register an endpoint with MULTICAST and MULTICAST_IPV6_ONLY properties`

## pseudocode

```c
__int64 __fastcall CRegUdpEndpoint::Initialize(
        CRegUdpEndpoint *this,
        struct CUdpHandler *a2,
        struct tagWDS_PROPERTY *a3,
        unsigned int a4)
{
  __int64 v8; // rdx
  unsigned int v9; // edi
  __int64 v10; // r8
  struct tagWDS_PROPERTY *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // ebp
  _DWORD *v15; // rsi
  unsigned int v16; // eax
  char *v17; // rcx
  char *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned __int16 *v24; // r14
  int v25; // ecx
  unsigned int DynamicPort; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // r8
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+30h] [rbp-268h]
  unsigned __int16 v34; // [rsp+40h] [rbp-258h] BYREF
  _BYTE v35[526]; // [rsp+42h] [rbp-256h] BYREF

  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_QWORD *)this + 226) = a2;
  v9 = 0;
  v10 = 0;
  if ( a4 )
  {
    v11 = a3;
    while ( *((_BYTE *)v11 + 1) != 4 || (unsigned __int8)*(_DWORD *)v11 != 7 || (*(_DWORD *)v11 & 0xFFFF0000) < 0xA0000 )
    {
      v10 = (unsigned int)(v10 + 1);
      v11 = (struct tagWDS_PROPERTY *)((char *)v11 + 56);
      if ( (unsigned int)v10 >= a4 )
        goto LABEL_9;
    }
    v9 = 87;
  }
LABEL_9:
  if ( (unsigned int)ElValidateWin32_6(v9, v8, v10, 121) )
    goto LABEL_70;
  v14 = 0;
  if ( !a4 )
  {
LABEL_48:
    if ( *((_DWORD *)this + 474) )
    {
      if ( *((_DWORD *)this + 517) )
      {
        CTrace::Trace(
          (CTrace *)qword_180039310,
          0x80000u,
          L"Invalid attempt to register an endpoint with MULTICAST and MULTICAST_IPV6_ONLY properties");
        v9 = 87;
        if ( (unsigned int)ElValidateWin32_6(87, v20, v21, 237) )
          goto LABEL_70;
      }
    }
    if ( *((_DWORD *)this + 484) )
    {
      if ( !*((_DWORD *)this + 474) && !*((_DWORD *)this + 517) )
      {
        CTrace::Trace(
          (CTrace *)qword_180039310,
          0x80000u,
          L"Multicast group address specified but multicast is disabled");
        v9 = 87;
        if ( (unsigned int)ElValidateWin32_6(87, v22, v23, 247) )
          goto LABEL_70;
      }
    }
    v24 = (unsigned __int16 *)((char *)this + 84);
    if ( !*((_DWORD *)this + 514) )
    {
      if ( !*v24 )
      {
        v9 = 87;
        if ( (unsigned int)ElValidateWin32_6(87, v12, v13, 274) )
          goto LABEL_70;
      }
LABEL_69:
      *((_DWORD *)this + 472) = *(_DWORD *)(*((_QWORD *)this + 226) + 65704LL);
      CRegEndpoint::SetCallbacks(this, a3, a4);
      CTrace::Trace(
        (CTrace *)qword_180039310,
        0x10000u,
        L"[%s][UDP][Ep=%u] Registered",
        *(_QWORD *)(*((_QWORD *)this + 8) + 16LL),
        *((unsigned __int16 *)this + 42));
      goto LABEL_70;
    }
    v34 = 0;
    memset_0(v35, 0, 0x206u);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 104));
    v25 = *((_DWORD *)a2 + 36);
    if ( v25 )
    {
      if ( v25 != 1 )
      {
        v9 = 5023;
LABEL_65:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 104));
        if ( (unsigned int)ElValidateWin32_6(v9, v30, v31, 261) )
          goto LABEL_70;
        CTrace::Trace((CTrace *)qword_180039310, 0x10000u, L"Dynamic Port: %u", *((unsigned __int16 *)this + 42));
        StringCchPrintfW(&v34, 0x104u, L"%u", *((unsigned __int16 *)this + 42));
        StringCchPrintfW((unsigned __int16 *)this + 644, 0x104u, L"%s", &v34);
        goto LABEL_69;
      }
      DynamicPort = CUdpPortRange::RangeGetDynamicPort(
                      (LPCRITICAL_SECTION)((char *)a2 + 104),
                      (unsigned __int16 *)this + 42);
      v29 = 578;
    }
    else
    {
      DynamicPort = CUdpPortRange::WinSockGetDynamicPort(
                      (LPCRITICAL_SECTION)((char *)a2 + 104),
                      (unsigned __int16 *)this + 42);
      v29 = 571;
    }
    v9 = DynamicPort;
    if ( !(unsigned int)ElValidateWin32_10(DynamicPort, v27, v28, v29) )
      CTrace::Trace((CTrace *)qword_180039310, 0x10000u, L"[UDPPorts] Allocated dynamic port %u.", *v24);
    goto LABEL_65;
  }
  v15 = (_DWORD *)((char *)a3 + 8);
  while ( 1 )
  {
    v16 = *(v15 - 2);
    if ( v16 > 0x70101 )
      break;
    switch ( v16 )
    {
      case 0x70101u:
        if ( *v15 > 0xFFu )
          goto LABEL_60;
        *((_DWORD *)this + 512) = *v15;
        break;
      case 0x10101u:
        if ( (unsigned int)(*v15 - 1) > 0xFFFE )
          goto LABEL_60;
        *((_DWORD *)this + 461) = *v15;
        break;
      case 0x20104u:
        *((_DWORD *)this + 514) = *v15;
        *((_WORD *)this + 42) = 0;
        break;
      case 0x30101u:
        *((_DWORD *)this + 460) = *v15;
        break;
      case 0x40104u:
        *((_DWORD *)this + 474) = *v15;
        break;
      case 0x50101u:
        *((_DWORD *)this + 470) = *v15;
        break;
      case 0x60101u:
        *((_DWORD *)this + 471) = *v15;
        break;
      default:
        goto LABEL_34;
    }
LABEL_47:
    ++v14;
    v15 += 14;
    if ( v14 >= a4 )
      goto LABEL_48;
  }
  if ( v16 == 524548 )
  {
    *((_DWORD *)this + 515) = *v15;
    goto LABEL_47;
  }
  if ( v16 == 590084 )
  {
    *((_DWORD *)this + 516) = *v15;
    goto LABEL_47;
  }
  if ( v16 != 655624 )
  {
    if ( v16 == 721156 )
    {
      *((_DWORD *)this + 517) = *v15;
      goto LABEL_47;
    }
    if ( v16 == 786692 )
    {
      *((_DWORD *)this + 513) = *v15;
      goto LABEL_47;
    }
LABEL_34:
    if ( *((_BYTE *)v15 - 7) != 4 || (_BYTE)v16 != 7 )
    {
      v9 = 87;
      if ( (unsigned int)ElValidateWin32_6(87, v12, v13, 227) )
        goto LABEL_70;
    }
    goto LABEL_47;
  }
  if ( !*((_DWORD *)this + 484) )
  {
    v17 = (char *)this + 1920;
    v18 = (char *)a3 + 56 * v14 + 8;
LABEL_44:
    memmove_0(v17, v18, 0x14u);
    goto LABEL_47;
  }
  v19 = *((unsigned int *)this + 485);
  if ( (unsigned int)v19 < 4 )
  {
    *((_DWORD *)this + 485) = v19 + 1;
    v18 = (char *)a3 + 56 * v14 + 8;
    v17 = (char *)this + 16 * v19 + 4 * v19 + 1944;
    goto LABEL_44;
  }
  CTrace::Trace(
    (CTrace *)qword_180039310,
    0x80000u,
    L"Attempt to register an endpoint with too many multicast group memberships");
LABEL_60:
  v9 = 87;
LABEL_70:
  LeaveCriticalSection(lpCriticalSection);
  return v9;
}

```

## disassembly

```asm
0x180014c24  mov     [rsp+arg_18], rbx
0x180014c29  push    rbp
0x180014c2a  push    rsi
0x180014c2b  push    rdi
0x180014c2c  push    r12
0x180014c2e  push    r13
0x180014c30  push    r14
0x180014c32  push    r15
0x180014c34  sub     rsp, 260h
0x180014c3b  mov     rax, cs:__security_cookie
0x180014c42  xor     rax, rsp
0x180014c45  mov     [rsp+298h+var_48], rax
0x180014c4d  lea     rax, [rcx+10h]
0x180014c51  mov     rbx, rcx
0x180014c54  mov     rcx, rax; lpCriticalSection
0x180014c57  mov     [rsp+298h+lpCriticalSection], rax
0x180014c5c  mov     r15d, r9d
0x180014c5f  mov     r13, r8
0x180014c62  mov     r12, rdx
0x180014c65  call    cs:__imp_EnterCriticalSection
0x180014c6c  nop     dword ptr [rax+rax+00h]
0x180014c71  xor     r14d, r14d
0x180014c74  mov     [rbx+710h], r12
0x180014c7b  mov     edi, r14d
0x180014c7e  mov     r8d, r14d
0x180014c81  test    r15d, r15d
0x180014c84  jz      short loc_180014CB7
0x180014c86  mov     rax, r13
0x180014c89  cmp     byte ptr [rax+1], 4
0x180014c8d  jnz     short loc_180014CA4
0x180014c8f  mov     ecx, [rax]
0x180014c91  cmp     cl, 7
0x180014c94  jnz     short loc_180014CA4
0x180014c96  and     ecx, 0FFFF0000h
0x180014c9c  cmp     ecx, 0A0000h
0x180014ca2  jnb     short loc_180014CB2
0x180014ca4  inc     r8d
0x180014ca7  add     rax, 38h ; '8'
0x180014cab  cmp     r8d, r15d
0x180014cae  jb      short loc_180014C89
0x180014cb0  jmp     short loc_180014CB7
0x180014cb2  mov     edi, 57h ; 'W'
0x180014cb7  mov     r9d, 79h ; 'y'
0x180014cbd  mov     ecx, edi
0x180014cbf  call    ElValidateWin32_6
0x180014cc4  test    eax, eax
0x180014cc6  jnz     loc_1800150D9
0x180014ccc  mov     ebp, r14d
0x180014ccf  test    r15d, r15d
0x180014cd2  jz      loc_180014E89
0x180014cd8  lea     rsi, [r13+8]
0x180014cdc  mov     eax, [rsi-8]
0x180014cdf  cmp     eax, 70101h
0x180014ce4  ja      loc_180014D97
0x180014cea  jz      loc_180014D7F
0x180014cf0  cmp     eax, 10101h
0x180014cf5  jz      short loc_180014D64
0x180014cf7  cmp     eax, 20104h
0x180014cfc  jz      short loc_180014D52
0x180014cfe  cmp     eax, 30101h
0x180014d03  jz      short loc_180014D45
0x180014d05  cmp     eax, 40104h
0x180014d0a  jz      short loc_180014D38
0x180014d0c  cmp     eax, 50101h
0x180014d11  jz      short loc_180014D2B
0x180014d13  cmp     eax, 60101h
0x180014d18  jnz     loc_180014DC2
0x180014d1e  mov     eax, [rsi]
0x180014d20  mov     [rbx+75Ch], eax
0x180014d26  jmp     loc_180014E7A
0x180014d2b  mov     eax, [rsi]
0x180014d2d  mov     [rbx+758h], eax
0x180014d33  jmp     loc_180014E7A
0x180014d38  mov     eax, [rsi]
0x180014d3a  mov     [rbx+768h], eax
0x180014d40  jmp     loc_180014E7A
0x180014d45  mov     eax, [rsi]
0x180014d47  mov     [rbx+730h], eax
0x180014d4d  jmp     loc_180014E7A
0x180014d52  mov     eax, [rsi]
0x180014d54  mov     [rbx+808h], eax
0x180014d5a  mov     [rbx+54h], r14w
0x180014d5f  jmp     loc_180014E7A
0x180014d64  mov     ecx, [rsi]
0x180014d66  lea     eax, [rcx-1]
0x180014d69  cmp     eax, 0FFFEh
0x180014d6e  ja      loc_180014F96
0x180014d74  mov     [rbx+734h], ecx
0x180014d7a  jmp     loc_180014E7A
0x180014d7f  mov     eax, [rsi]
0x180014d81  cmp     eax, 0FFh
0x180014d86  ja      loc_180014F96
0x180014d8c  mov     [rbx+800h], eax
0x180014d92  jmp     loc_180014E7A
0x180014d97  cmp     eax, 80104h
0x180014d9c  jz      loc_180014E72
0x180014da2  cmp     eax, 90104h
0x180014da7  jz      loc_180014E68
0x180014dad  cmp     eax, 0A0108h
0x180014db2  jz      short loc_180014E05
0x180014db4  cmp     eax, 0B0104h
0x180014db9  jz      short loc_180014DFB
0x180014dbb  cmp     eax, 0C0104h
0x180014dc0  jz      short loc_180014DF1
0x180014dc2  cmp     byte ptr [rsi-7], 4
0x180014dc6  jnz     short loc_180014DD0
0x180014dc8  cmp     al, 7
0x180014dca  jz      loc_180014E7A
0x180014dd0  mov     eax, 57h ; 'W'
0x180014dd5  mov     r9d, 0E3h
0x180014ddb  mov     ecx, eax
0x180014ddd  mov     edi, eax
0x180014ddf  call    ElValidateWin32_6
0x180014de4  test    eax, eax
0x180014de6  jnz     loc_1800150D9
0x180014dec  jmp     loc_180014E7A
0x180014df1  mov     eax, [rsi]
0x180014df3  mov     [rbx+804h], eax
0x180014df9  jmp     short loc_180014E7A
0x180014dfb  mov     eax, [rsi]
0x180014dfd  mov     [rbx+814h], eax
0x180014e03  jmp     short loc_180014E7A
0x180014e05  cmp     [rbx+790h], r14d
0x180014e0c  jnz     short loc_180014E24
0x180014e0e  mov     eax, ebp
0x180014e10  lea     rcx, [rbx+780h]
0x180014e17  imul    rdx, rax, 38h ; '8'
0x180014e1b  add     rdx, 8
0x180014e1f  add     rdx, r13
0x180014e22  jmp     short loc_180014E5B
0x180014e24  mov     r8d, [rbx+794h]
0x180014e2b  cmp     r8d, 4
0x180014e2f  jnb     loc_180014F77
0x180014e35  lea     eax, [r8+1]
0x180014e39  mov     [rbx+794h], eax
0x180014e3f  lea     rcx, ds:1E6h[r8*4]
0x180014e47  mov     eax, ebp
0x180014e49  imul    rdx, rax, 38h ; '8'
0x180014e4d  add     rdx, 8
0x180014e51  add     rdx, r13; Src
0x180014e54  add     rcx, r8
0x180014e57  lea     rcx, [rbx+rcx*4]; void *
0x180014e5b  mov     r8d, 14h; Size
0x180014e61  call    memmove_0
0x180014e66  jmp     short loc_180014E7A
0x180014e68  mov     eax, [rsi]
0x180014e6a  mov     [rbx+810h], eax
0x180014e70  jmp     short loc_180014E7A
0x180014e72  mov     eax, [rsi]
0x180014e74  mov     [rbx+80Ch], eax
0x180014e7a  inc     ebp
0x180014e7c  add     rsi, 38h ; '8'
0x180014e80  cmp     ebp, r15d
0x180014e83  jb      loc_180014CDC
0x180014e89  lea     rsi, qword_180039310
0x180014e90  cmp     [rbx+768h], r14d
0x180014e97  jz      short loc_180014ED7
0x180014e99  cmp     [rbx+814h], r14d
0x180014ea0  jz      short loc_180014ED7
0x180014ea2  lea     r8, aInvalidAttempt; "Invalid attempt to register an endpoint"...
0x180014ea9  mov     edx, 80000h
0x180014eae  mov     rcx, rsi
0x180014eb1  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180014eb8  nop     dword ptr [rax+rax+00h]
0x180014ebd  mov     edi, 57h ; 'W'
0x180014ec2  mov     r9d, 0EDh
0x180014ec8  mov     ecx, edi
0x180014eca  call    ElValidateWin32_6
0x180014ecf  test    eax, eax
0x180014ed1  jnz     loc_1800150D9
0x180014ed7  cmp     [rbx+790h], r14d
0x180014ede  jz      short loc_180014F27
0x180014ee0  cmp     [rbx+768h], r14d
0x180014ee7  jnz     short loc_180014F27
0x180014ee9  cmp     [rbx+814h], r14d
0x180014ef0  jnz     short loc_180014F27
0x180014ef2  lea     r8, aMulticastGroup; "Multicast group address specified but m"...
0x180014ef9  mov     edx, 80000h
0x180014efe  mov     rcx, rsi
0x180014f01  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180014f08  nop     dword ptr [rax+rax+00h]
0x180014f0d  mov     edi, 57h ; 'W'
0x180014f12  mov     r9d, 0F7h
0x180014f18  mov     ecx, edi
0x180014f1a  call    ElValidateWin32_6
0x180014f1f  test    eax, eax
0x180014f21  jnz     loc_1800150D9
0x180014f27  xor     ebp, ebp
0x180014f29  lea     r14, [rbx+54h]
0x180014f2d  cmp     [rbx+808h], ebp
0x180014f33  jz      loc_18001506D
0x180014f39  xor     edx, edx; Val
0x180014f3b  mov     [rsp+298h+var_258], bp
0x180014f40  mov     r8d, 206h; Size
0x180014f46  lea     rcx, [rsp+298h+var_256]; void *
0x180014f4b  call    memset_0
0x180014f50  lea     rbp, [r12+68h]
0x180014f55  mov     rcx, rbp; lpCriticalSection
0x180014f58  call    cs:__imp_EnterCriticalSection
0x180014f5f  nop     dword ptr [rax+rax+00h]
0x180014f64  mov     ecx, [rbp+28h]
0x180014f67  test    ecx, ecx
0x180014f69  jz      short loc_180014FB3
0x180014f6b  cmp     ecx, 1
0x180014f6e  jz      short loc_180014FA0
0x180014f70  mov     edi, 139Fh
0x180014f75  jmp     short loc_180014FF0
0x180014f77  lea     r8, aAttemptToRegis; "Attempt to register an endpoint with to"...
0x180014f7e  mov     edx, 80000h
0x180014f83  lea     rcx, qword_180039310
0x180014f8a  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180014f91  nop     dword ptr [rax+rax+00h]
0x180014f96  mov     edi, 57h ; 'W'
0x180014f9b  jmp     loc_1800150D9
0x180014fa0  mov     rdx, r14; unsigned __int16 *
0x180014fa3  mov     rcx, rbp; lpCriticalSection
0x180014fa6  call    ?RangeGetDynamicPort@CUdpPortRange@@AEAAKPEAG@Z; CUdpPortRange::RangeGetDynamicPort(ushort *)
0x180014fab  mov     r9d, 242h
0x180014fb1  jmp     short loc_180014FC4
0x180014fb3  mov     rdx, r14; unsigned __int16 *
0x180014fb6  mov     rcx, rbp; lpCriticalSection
0x180014fb9  call    ?WinSockGetDynamicPort@CUdpPortRange@@AEAAKPEAG@Z; CUdpPortRange::WinSockGetDynamicPort(ushort *)
0x180014fbe  mov     r9d, 23Bh
0x180014fc4  mov     ecx, eax
0x180014fc6  mov     edi, eax
0x180014fc8  call    ElValidateWin32_10
0x180014fcd  test    eax, eax
0x180014fcf  jnz     short loc_180014FF0
0x180014fd1  movzx   r9d, word ptr [r14]
0x180014fd5  lea     r8, aUdpportsAlloca; "[UDPPorts] Allocated dynamic port %u."
0x180014fdc  mov     edx, 10000h
0x180014fe1  mov     rcx, rsi
0x180014fe4  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180014feb  nop     dword ptr [rax+rax+00h]
0x180014ff0  mov     rcx, rbp; lpCriticalSection
0x180014ff3  call    cs:__imp_LeaveCriticalSection
0x180014ffa  nop     dword ptr [rax+rax+00h]
0x180014fff  mov     r9d, 105h
0x180015005  mov     ecx, edi
0x180015007  call    ElValidateWin32_6
0x18001500c  test    eax, eax
0x18001500e  jnz     loc_1800150D9
0x180015014  movzx   r9d, word ptr [rbx+54h]
0x180015019  lea     r8, aDynamicPortU; "Dynamic Port: %u"
0x180015020  mov     edx, 10000h
0x180015025  mov     rcx, rsi
0x180015028  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18001502f  nop     dword ptr [rax+rax+00h]
0x180015034  movzx   r9d, word ptr [rbx+54h]
0x180015039  lea     r8, aU; "%u"
0x180015040  mov     ebp, 104h
0x180015045  lea     rcx, [rsp+298h+var_258]; unsigned __int16 *
0x18001504a  mov     edx, ebp; unsigned __int64
0x18001504c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015051  lea     rcx, [rbx+508h]; unsigned __int16 *
0x180015058  mov     edx, ebp; unsigned __int64
0x18001505a  lea     r9, [rsp+298h+var_258]
0x18001505f  lea     r8, aS; "%s"
0x180015066  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001506b  jmp     short loc_18001508B
0x18001506d  cmp     [r14], bp
0x180015071  jnz     short loc_18001508B
0x180015073  mov     eax, 57h ; 'W'
0x180015078  mov     r9d, 112h
0x18001507e  mov     ecx, eax
0x180015080  mov     edi, eax
0x180015082  call    ElValidateWin32_6
0x180015087  test    eax, eax
0x180015089  jnz     short loc_1800150D9
0x18001508b  mov     rax, [rbx+710h]
0x180015092  mov     r8d, r15d; unsigned int
0x180015095  mov     rdx, r13; struct tagWDS_PROPERTY *
0x180015098  mov     ecx, [rax+100A8h]
0x18001509e  mov     [rbx+760h], ecx
0x1800150a4  mov     rcx, rbx; this
0x1800150a7  call    ?SetCallbacks@CRegEndpoint@@QEAAKPEAUtagWDS_PROPERTY@@K@Z; CRegEndpoint::SetCallbacks(tagWDS_PROPERTY *,ulong)
0x1800150ac  movzx   r8d, word ptr [rbx+54h]
0x1800150b1  mov     edx, 10000h
0x1800150b6  mov     r9, [rbx+40h]
0x1800150ba  mov     rcx, rsi
0x1800150bd  mov     [rsp+298h+var_278], r8d
0x1800150c2  lea     r8, aSUdpEpURegiste; "[%s][UDP][Ep=%u] Registered"
0x1800150c9  mov     r9, [r9+10h]
0x1800150cd  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800150d4  nop     dword ptr [rax+rax+00h]
0x1800150d9  mov     rcx, [rsp+298h+lpCriticalSection]; lpCriticalSection
0x1800150de  call    cs:__imp_LeaveCriticalSection
0x1800150e5  nop     dword ptr [rax+rax+00h]
0x1800150ea  mov     eax, edi
0x1800150ec  mov     rcx, [rsp+298h+var_48]
0x1800150f4  xor     rcx, rsp; StackCookie
0x1800150f7  call    __security_check_cookie
0x1800150fc  mov     rbx, [rsp+298h+arg_18]
0x180015104  add     rsp, 260h
0x18001510b  pop     r15
0x18001510d  pop     r14
0x18001510f  pop     r13
0x180015111  pop     r12
0x180015113  pop     rdi
0x180015114  pop     rsi
  ... truncated ...
```
