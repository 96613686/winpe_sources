# RootFileCreate

- ea: `0x14002c0f0`
- end: `0x14002c481`
- name: `RootFileCreate`
- size: `913`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x140003d5c`
- `0x140003dd0`
- `0x140004f40`
- `0x140005b8c`
- `0x140005e6c`
- `0x140017000`
- `0x140017190`
- `0x14002c0f0`
- `0x14002c628`
- `0x14002f200`
- `0x14002f340`
- `0x14002f3dc`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14002c263`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002c263`
- `ntoskrnl!KeInitializeEvent` at `0x14002c1e7`
- `ntoskrnl!KeInitializeEvent` at `0x14002c1e7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002c2de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002c2de`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002c273`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002c273`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002c2d2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002c2d2`
- `ntoskrnl!RtlGUIDFromString` at `0x14002c41e`
- `ntoskrnl!RtlGUIDFromString` at `0x14002c41e`

## pseudocode

```c
__int64 __fastcall RootFileCreate(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rsi
  __int64 v7; // r14
  __int64 v8; // rax
  char v9; // r12
  __int64 v10; // r13
  _DWORD *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rax
  signed int v14; // ebx
  char v15; // r15
  const UNICODE_STRING *DeviceInterfaceLocked; // rax
  const UNICODE_STRING *v17; // rdi
  char v18; // al
  char v19; // al
  UNICODE_STRING GuidString; // [rsp+38h] [rbp-41h] BYREF
  __int64 v23; // [rsp+48h] [rbp-31h]
  __int64 v24; // [rsp+50h] [rbp-29h]
  __int64 v25; // [rsp+58h] [rbp-21h]
  UNICODE_STRING v26; // [rsp+60h] [rbp-19h] BYREF
  __int128 v27; // [rsp+70h] [rbp-9h] BYREF
  __int64 v28; // [rsp+80h] [rbp+7h]
  GUID Guid; // [rsp+88h] [rbp+Fh] BYREF

  v23 = a3;
  v28 = 0;
  v25 = a2;
  v26 = 0;
  GuidString = 0;
  Guid = 0;
  v27 = 0;
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a3,
         off_14001C0F0);
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 1120))(WdfDriverGlobals, a3);
  v24 = v7;
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14001C0C8);
  v9 = 0;
  *(_QWORD *)v6 = a3;
  v10 = v8;
  *(_BYTE *)(v6 + 72) = 0;
  v11 = (_DWORD *)(v6 + 8);
  *(_DWORD *)(v6 + 8) = 0;
  *(_QWORD *)(v6 + 24) = 0;
  *(_DWORD *)(v6 + 16) = 1;
  *(_DWORD *)(v6 + 32) = 0;
  KeInitializeEvent((PRKEVENT)(v6 + 40), SynchronizationEvent, 0);
  *(_QWORD *)(v7 + 24) = v6;
  v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 2216))(WdfDriverGlobals, a2);
  v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 1096))(WdfDriverGlobals, v12);
  v14 = RootFileParseFilename(v13, v6 + 8, &v26, &GuidString);
  if ( v14 < 0 )
  {
    v14 = -1073741810;
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 2104))(
             WdfDriverGlobals,
             v25,
             (unsigned int)v14);
  }
  if ( *v11 != 7 )
  {
    v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 2240))(WdfDriverGlobals, a2);
    if ( *v11 != 8 )
    {
      if ( *(_QWORD *)(v7 + 64) )
      {
        if ( GuidString.Length )
        {
          v14 = -1073741772;
          return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 2104))(
                   WdfDriverGlobals,
                   v25,
                   (unsigned int)v14);
        }
      }
      else if ( *v11 != 10 )
      {
        v14 = -1073741811;
        if ( RtlGUIDFromString(&GuidString, &Guid) < 0 )
          return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 2104))(
                   WdfDriverGlobals,
                   v25,
                   (unsigned int)v14);
      }
      v14 = -1073741808;
      return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 2104))(
               WdfDriverGlobals,
               v25,
               (unsigned int)v14);
    }
    v17 = 0;
    v19 = -v18;
    v14 = v19 != 0 ? 0xC0000010 : 0;
    if ( !v19 )
      return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 2104))(
               WdfDriverGlobals,
               v25,
               (unsigned int)v14);
    goto LABEL_22;
  }
  v15 = 0;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v10 + 24));
  DeviceInterfaceLocked = RootDeviceFindDeviceInterfaceLocked(v10, &v26, 0);
  v17 = DeviceInterfaceLocked;
  if ( DeviceInterfaceLocked )
  {
    if ( *(_QWORD *)&DeviceInterfaceLocked[1].Length )
    {
      v14 = -1073741537;
    }
    else
    {
      v9 = 1;
      *(_QWORD *)&DeviceInterfaceLocked[1].Length = v6 + 80;
      *(_QWORD *)(v6 + 456) = DeviceInterfaceLocked;
      if ( *(_DWORD *)&DeviceInterfaceLocked[3].Length == 1 )
        v15 = 1;
      else
        *(_DWORD *)&DeviceInterfaceLocked[3].Length = 3;
    }
  }
  else
  {
    v14 = -1073741810;
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v10 + 24));
  KeLeaveCriticalRegion();
  if ( v14 < 0
    || (v14 = InstanceContextInit((int)v6 + 80, *(_QWORD *)&v17[2].Length, v17[1].Buffer, v23, a1), v14 < 0)
    || (v14 = InstanceSetProcessorAffinity(v6 + 80, 0), v14 < 0)
    || !v15
    && (*(_BYTE *)(v6 + 232) & 0x10) != 0
    && ((v14 = PipeParseFilename(&GuidString, &v27), v14 < 0)
     || (v14 = PipeCreate(0, v6 + 376), v14 < 0)
     || ((*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 248))(WdfDriverGlobals, a1),
         v14 = PipeAccept(*(PKSPIN_LOCK *)(v6 + 376)),
         v14 < 0)) )
  {
LABEL_22:
    if ( v9 )
    {
      InstanceContextDestroy(v6 + 80);
      RootOnDeviceInterfaceClose(v10, v17);
    }
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 2104))(
           WdfDriverGlobals,
           v25,
           (unsigned int)v14);
}

```

## disassembly

```asm
0x14002c0f0  mov     [rsp-8+arg_18], rbx
0x14002c0f5  push    rbp
0x14002c0f6  push    rsi
0x14002c0f7  push    rdi
0x14002c0f8  push    r12
0x14002c0fa  push    r13
0x14002c0fc  push    r14
0x14002c0fe  push    r15
0x14002c100  lea     rbp, [rsp-27h]
0x14002c105  sub     rsp, 0A0h
0x14002c10c  mov     rax, cs:__security_cookie
0x14002c113  xor     rax, rsp
0x14002c116  mov     [rbp+57h+var_38], rax
0x14002c11a  xor     eax, eax
0x14002c11c  mov     [rbp+57h+var_88], r8
0x14002c120  mov     [rbp+57h+var_50], rax
0x14002c124  xorps   xmm0, xmm0
0x14002c127  mov     rax, cs:WdfFunctions_01033
0x14002c12e  xorps   xmm1, xmm1
0x14002c131  mov     rdi, r8
0x14002c134  mov     [rbp+57h+var_78], rdx
0x14002c138  mov     r8, cs:off_14001C0F0
0x14002c13f  mov     r15, rdx
0x14002c142  mov     rbx, rcx
0x14002c145  mov     [rbp+57h+var_A0], rcx
0x14002c149  mov     rcx, cs:WdfDriverGlobals
0x14002c150  mov     rdx, rdi
0x14002c153  movups  [rbp+57h+var_70], xmm0
0x14002c157  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm1
0x14002c15b  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x14002c15f  movups  [rbp+57h+var_60], xmm1
0x14002c163  mov     rax, [rax+650h]
0x14002c16a  call    _guard_dispatch_icall
0x14002c16f  mov     rcx, cs:WdfFunctions_01033
0x14002c176  mov     rsi, rax
0x14002c179  mov     rdx, rdi
0x14002c17c  mov     rax, [rcx+460h]
0x14002c183  mov     rcx, cs:WdfDriverGlobals
0x14002c18a  call    _guard_dispatch_icall
0x14002c18f  mov     rcx, cs:WdfFunctions_01033
0x14002c196  mov     r14, rax
0x14002c199  mov     r8, cs:off_14001C0C8
0x14002c1a0  mov     rdx, rbx
0x14002c1a3  mov     [rbp+57h+var_80], rax
0x14002c1a7  mov     rax, [rcx+650h]
0x14002c1ae  mov     rcx, cs:WdfDriverGlobals
0x14002c1b5  call    _guard_dispatch_icall
0x14002c1ba  xor     r12d, r12d
0x14002c1bd  mov     [rsi], rdi
0x14002c1c0  mov     r13, rax
0x14002c1c3  mov     [rsi+48h], r12b
0x14002c1c7  lea     rdi, [rsi+8]
0x14002c1cb  xor     r8d, r8d; State
0x14002c1ce  mov     [rdi], r12d
0x14002c1d1  lea     rcx, [rsi+28h]; Event
0x14002c1d5  lea     eax, [r12+1]
0x14002c1da  mov     [rsi+18h], r12
0x14002c1de  mov     edx, eax; Type
0x14002c1e0  mov     [rsi+10h], eax
0x14002c1e3  mov     [rsi+20h], r12d
0x14002c1e7  call    cs:__imp_KeInitializeEvent
0x14002c1ee  nop     dword ptr [rax+rax+00h]
0x14002c1f3  mov     [r14+18h], rsi
0x14002c1f7  mov     rdx, r15
0x14002c1fa  mov     rax, cs:WdfFunctions_01033
0x14002c201  mov     rcx, cs:WdfDriverGlobals
0x14002c208  mov     rax, [rax+8A8h]
0x14002c20f  call    _guard_dispatch_icall
0x14002c214  mov     rcx, cs:WdfFunctions_01033
0x14002c21b  mov     rdx, rax
0x14002c21e  mov     r8, [rcx+448h]
0x14002c225  mov     rcx, cs:WdfDriverGlobals
0x14002c22c  mov     rax, r8
0x14002c22f  call    _guard_dispatch_icall
0x14002c234  lea     r9, [rbp+57h+GuidString]
0x14002c238  mov     rdx, rdi
0x14002c23b  lea     r8, [rbp+57h+var_70]
0x14002c23f  mov     rcx, rax
0x14002c242  call    RootFileParseFilename
0x14002c247  mov     ebx, eax
0x14002c249  test    eax, eax
0x14002c24b  jns     short loc_14002C257
0x14002c24d  mov     ebx, 0C000000Eh
0x14002c252  jmp     loc_14002C438
0x14002c257  cmp     dword ptr [rdi], 7
0x14002c25a  jnz     loc_14002C3AF
0x14002c260  xor     r15b, r15b
0x14002c263  call    cs:__imp_KeEnterCriticalRegion
0x14002c26a  nop     dword ptr [rax+rax+00h]
0x14002c26f  lea     rcx, [r13+18h]; FastMutex
0x14002c273  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002c27a  nop     dword ptr [rax+rax+00h]
0x14002c27f  xor     r8d, r8d
0x14002c282  lea     rdx, [rbp+57h+var_70]
0x14002c286  mov     rcx, r13
0x14002c289  call    RootDeviceFindDeviceInterfaceLocked
0x14002c28e  mov     rdi, rax
0x14002c291  test    rax, rax
0x14002c294  jz      short loc_14002C2C9
0x14002c296  cmp     [rax+10h], r12
0x14002c29a  jz      short loc_14002C2A3
0x14002c29c  mov     ebx, 0C000011Fh
0x14002c2a1  jmp     short loc_14002C2CE
0x14002c2a3  lea     rax, [rsi+50h]
0x14002c2a7  mov     r12b, 1
0x14002c2aa  mov     [rdi+10h], rax
0x14002c2ae  mov     [rsi+1C8h], rdi
0x14002c2b5  cmp     dword ptr [rdi+30h], 1
0x14002c2b9  jnz     short loc_14002C2C0
0x14002c2bb  mov     r15b, r12b
0x14002c2be  jmp     short loc_14002C2CE
0x14002c2c0  mov     dword ptr [rdi+30h], 3
0x14002c2c7  jmp     short loc_14002C2CE
0x14002c2c9  mov     ebx, 0C000000Eh
0x14002c2ce  lea     rcx, [r13+18h]; FastMutex
0x14002c2d2  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002c2d9  nop     dword ptr [rax+rax+00h]
0x14002c2de  call    cs:__imp_KeLeaveCriticalRegion
0x14002c2e5  nop     dword ptr [rax+rax+00h]
0x14002c2ea  test    ebx, ebx
0x14002c2ec  js      loc_14002C3E1
0x14002c2f2  mov     rax, [rbp+57h+var_A0]
0x14002c2f6  lea     rcx, [rsi+50h]
0x14002c2fa  mov     r9, [rbp+57h+var_88]
0x14002c2fe  mov     r8, [rdi+18h]
0x14002c302  mov     rdx, [rdi+20h]
0x14002c306  mov     [rsp+0D0h+var_B0], rax
0x14002c30b  call    InstanceContextInit
0x14002c310  mov     ebx, eax
0x14002c312  test    eax, eax
0x14002c314  js      loc_14002C3E1
0x14002c31a  xor     edx, edx
0x14002c31c  lea     rcx, [rsi+50h]
0x14002c320  call    InstanceSetProcessorAffinity
0x14002c325  mov     ebx, eax
0x14002c327  test    eax, eax
0x14002c329  js      loc_14002C3E1
0x14002c32f  test    r15b, r15b
0x14002c332  jnz     loc_14002C438
0x14002c338  test    byte ptr [rsi+0E8h], 10h
0x14002c33f  jz      loc_14002C438
0x14002c345  lea     rdx, [rbp+57h+var_60]
0x14002c349  lea     rcx, [rbp+57h+GuidString]
0x14002c34d  call    PipeParseFilename
0x14002c352  mov     ebx, eax
0x14002c354  test    eax, eax
0x14002c356  js      loc_14002C3E1
0x14002c35c  lea     r14, [rsi+178h]
0x14002c363  xor     ecx, ecx
0x14002c365  mov     rdx, r14
0x14002c368  call    PipeCreate
0x14002c36d  mov     ebx, eax
0x14002c36f  test    eax, eax
0x14002c371  js      short loc_14002C3E1
0x14002c373  mov     rax, cs:WdfFunctions_01033
0x14002c37a  mov     rdx, [rbp+57h+var_A0]
0x14002c37e  mov     rcx, cs:WdfDriverGlobals
0x14002c385  mov     rax, [rax+0F8h]
0x14002c38c  call    _guard_dispatch_icall
0x14002c391  mov     r8, [rbp+57h+var_80]
0x14002c395  lea     r9, [rbp+57h+var_60]
0x14002c399  mov     rcx, [r14]; SpinLock
0x14002c39c  mov     rdx, rax
0x14002c39f  call    PipeAccept
0x14002c3a4  mov     ebx, eax
0x14002c3a6  test    eax, eax
0x14002c3a8  js      short loc_14002C3E1
0x14002c3aa  jmp     loc_14002C438
0x14002c3af  mov     rax, cs:WdfFunctions_01033
0x14002c3b6  mov     rdx, r15
0x14002c3b9  mov     rcx, cs:WdfDriverGlobals
0x14002c3c0  mov     rax, [rax+8C0h]
0x14002c3c7  call    _guard_dispatch_icall
0x14002c3cc  mov     ecx, [rdi]
0x14002c3ce  cmp     ecx, 8
0x14002c3d1  jnz     short loc_14002C3FC
0x14002c3d3  xor     edi, edi
0x14002c3d5  neg     al
0x14002c3d7  sbb     ebx, ebx
0x14002c3d9  and     ebx, 0C0000010h
0x14002c3df  jge     short loc_14002C438
0x14002c3e1  test    r12b, r12b
0x14002c3e4  jz      short loc_14002C438
0x14002c3e6  lea     rcx, [rsi+50h]
0x14002c3ea  call    InstanceContextDestroy
0x14002c3ef  mov     rdx, rdi
0x14002c3f2  mov     rcx, r13
0x14002c3f5  call    RootOnDeviceInterfaceClose
0x14002c3fa  jmp     short loc_14002C438
0x14002c3fc  xor     ebx, ebx
0x14002c3fe  cmp     [r14+40h], rbx
0x14002c402  jz      short loc_14002C411
0x14002c404  cmp     [rbp+57h+GuidString.Length], bx
0x14002c408  jz      short loc_14002C433
0x14002c40a  mov     ebx, 0C0000034h
0x14002c40f  jmp     short loc_14002C438
0x14002c411  cmp     ecx, 0Ah
0x14002c414  jz      short loc_14002C433
0x14002c416  lea     rdx, [rbp+57h+Guid]; Guid
0x14002c41a  lea     rcx, [rbp+57h+GuidString]; GuidString
0x14002c41e  call    cs:__imp_RtlGUIDFromString
0x14002c425  nop     dword ptr [rax+rax+00h]
0x14002c42a  mov     ebx, 0C000000Dh
0x14002c42f  test    eax, eax
0x14002c431  js      short loc_14002C438
0x14002c433  mov     ebx, 0C0000010h
0x14002c438  mov     rax, cs:WdfFunctions_01033
0x14002c43f  mov     r8d, ebx
0x14002c442  mov     rdx, [rbp+57h+var_78]
0x14002c446  mov     rcx, cs:WdfDriverGlobals
0x14002c44d  mov     rax, [rax+838h]
0x14002c454  call    _guard_dispatch_icall
0x14002c459  mov     rcx, [rbp+57h+var_38]
0x14002c45d  xor     rcx, rsp; StackCookie
0x14002c460  call    __security_check_cookie
0x14002c465  mov     rbx, [rsp+0D0h+arg_18]
0x14002c46d  add     rsp, 0A0h
0x14002c474  pop     r15
0x14002c476  pop     r14
0x14002c478  pop     r13
0x14002c47a  pop     r12
0x14002c47c  pop     rdi
0x14002c47d  pop     rsi
0x14002c47e  pop     rbp
0x14002c47f  retn
```
