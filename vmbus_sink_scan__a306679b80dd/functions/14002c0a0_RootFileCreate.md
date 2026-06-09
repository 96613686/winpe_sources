# RootFileCreate

- ea: `0x14002c0a0`
- end: `0x14002c431`
- name: `RootFileCreate`
- size: `913`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
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
- `0x14002c0a0`
- `0x14002c5d8`
- `0x14002f1b0`
- `0x14002f2f0`
- `0x14002f38c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14002c213`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002c213`
- `ntoskrnl!KeInitializeEvent` at `0x14002c197`
- `ntoskrnl!KeInitializeEvent` at `0x14002c197`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002c28e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002c28e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002c223`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002c223`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002c282`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002c282`
- `ntoskrnl!RtlGUIDFromString` at `0x14002c3ce`
- `ntoskrnl!RtlGUIDFromString` at `0x14002c3ce`

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
  __int64 DeviceInterfaceLocked; // rax
  __int64 v17; // rdi
  char v18; // al
  char v19; // al
  UNICODE_STRING GuidString; // [rsp+38h] [rbp-41h] BYREF
  __int64 v23; // [rsp+48h] [rbp-31h]
  __int64 v24; // [rsp+50h] [rbp-29h]
  __int64 v25; // [rsp+58h] [rbp-21h]
  __int128 v26; // [rsp+60h] [rbp-19h] BYREF
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
    if ( *(_QWORD *)(DeviceInterfaceLocked + 16) )
    {
      v14 = -1073741537;
    }
    else
    {
      v9 = 1;
      *(_QWORD *)(DeviceInterfaceLocked + 16) = v6 + 80;
      *(_QWORD *)(v6 + 456) = DeviceInterfaceLocked;
      if ( *(_DWORD *)(DeviceInterfaceLocked + 48) == 1 )
        v15 = 1;
      else
        *(_DWORD *)(DeviceInterfaceLocked + 48) = 3;
    }
  }
  else
  {
    v14 = -1073741810;
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v10 + 24));
  KeLeaveCriticalRegion();
  if ( v14 < 0
    || (v14 = InstanceContextInit((int)v6 + 80, *(_QWORD *)(v17 + 32), *(_QWORD *)(v17 + 24), v23, a1), v14 < 0)
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
0x14002c0a0  mov     [rsp-8+arg_18], rbx
0x14002c0a5  push    rbp
0x14002c0a6  push    rsi
0x14002c0a7  push    rdi
0x14002c0a8  push    r12
0x14002c0aa  push    r13
0x14002c0ac  push    r14
0x14002c0ae  push    r15
0x14002c0b0  lea     rbp, [rsp-27h]
0x14002c0b5  sub     rsp, 0A0h
0x14002c0bc  mov     rax, cs:__security_cookie
0x14002c0c3  xor     rax, rsp
0x14002c0c6  mov     [rbp+57h+var_38], rax
0x14002c0ca  xor     eax, eax
0x14002c0cc  mov     [rbp+57h+var_88], r8
0x14002c0d0  mov     [rbp+57h+var_50], rax
0x14002c0d4  xorps   xmm0, xmm0
0x14002c0d7  mov     rax, cs:WdfFunctions_01033
0x14002c0de  xorps   xmm1, xmm1
0x14002c0e1  mov     rdi, r8
0x14002c0e4  mov     [rbp+57h+var_78], rdx
0x14002c0e8  mov     r8, cs:off_14001C0F0
0x14002c0ef  mov     r15, rdx
0x14002c0f2  mov     rbx, rcx
0x14002c0f5  mov     [rbp+57h+var_A0], rcx
0x14002c0f9  mov     rcx, cs:WdfDriverGlobals
0x14002c100  mov     rdx, rdi
0x14002c103  movups  [rbp+57h+var_70], xmm0
0x14002c107  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm1
0x14002c10b  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x14002c10f  movups  [rbp+57h+var_60], xmm1
0x14002c113  mov     rax, [rax+650h]
0x14002c11a  call    _guard_dispatch_icall
0x14002c11f  mov     rcx, cs:WdfFunctions_01033
0x14002c126  mov     rsi, rax
0x14002c129  mov     rdx, rdi
0x14002c12c  mov     rax, [rcx+460h]
0x14002c133  mov     rcx, cs:WdfDriverGlobals
0x14002c13a  call    _guard_dispatch_icall
0x14002c13f  mov     rcx, cs:WdfFunctions_01033
0x14002c146  mov     r14, rax
0x14002c149  mov     r8, cs:off_14001C0C8
0x14002c150  mov     rdx, rbx
0x14002c153  mov     [rbp+57h+var_80], rax
0x14002c157  mov     rax, [rcx+650h]
0x14002c15e  mov     rcx, cs:WdfDriverGlobals
0x14002c165  call    _guard_dispatch_icall
0x14002c16a  xor     r12d, r12d
0x14002c16d  mov     [rsi], rdi
0x14002c170  mov     r13, rax
0x14002c173  mov     [rsi+48h], r12b
0x14002c177  lea     rdi, [rsi+8]
0x14002c17b  xor     r8d, r8d; State
0x14002c17e  mov     [rdi], r12d
0x14002c181  lea     rcx, [rsi+28h]; Event
0x14002c185  lea     eax, [r12+1]
0x14002c18a  mov     [rsi+18h], r12
0x14002c18e  mov     edx, eax; Type
0x14002c190  mov     [rsi+10h], eax
0x14002c193  mov     [rsi+20h], r12d
0x14002c197  call    cs:__imp_KeInitializeEvent
0x14002c19e  nop     dword ptr [rax+rax+00h]
0x14002c1a3  mov     [r14+18h], rsi
0x14002c1a7  mov     rdx, r15
0x14002c1aa  mov     rax, cs:WdfFunctions_01033
0x14002c1b1  mov     rcx, cs:WdfDriverGlobals
0x14002c1b8  mov     rax, [rax+8A8h]
0x14002c1bf  call    _guard_dispatch_icall
0x14002c1c4  mov     rcx, cs:WdfFunctions_01033
0x14002c1cb  mov     rdx, rax
0x14002c1ce  mov     r8, [rcx+448h]
0x14002c1d5  mov     rcx, cs:WdfDriverGlobals
0x14002c1dc  mov     rax, r8
0x14002c1df  call    _guard_dispatch_icall
0x14002c1e4  lea     r9, [rbp+57h+GuidString]
0x14002c1e8  mov     rdx, rdi
0x14002c1eb  lea     r8, [rbp+57h+var_70]
0x14002c1ef  mov     rcx, rax
0x14002c1f2  call    RootFileParseFilename
0x14002c1f7  mov     ebx, eax
0x14002c1f9  test    eax, eax
0x14002c1fb  jns     short loc_14002C207
0x14002c1fd  mov     ebx, 0C000000Eh
0x14002c202  jmp     loc_14002C3E8
0x14002c207  cmp     dword ptr [rdi], 7
0x14002c20a  jnz     loc_14002C35F
0x14002c210  xor     r15b, r15b
0x14002c213  call    cs:__imp_KeEnterCriticalRegion
0x14002c21a  nop     dword ptr [rax+rax+00h]
0x14002c21f  lea     rcx, [r13+18h]; FastMutex
0x14002c223  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002c22a  nop     dword ptr [rax+rax+00h]
0x14002c22f  xor     r8d, r8d
0x14002c232  lea     rdx, [rbp+57h+var_70]
0x14002c236  mov     rcx, r13
0x14002c239  call    RootDeviceFindDeviceInterfaceLocked
0x14002c23e  mov     rdi, rax
0x14002c241  test    rax, rax
0x14002c244  jz      short loc_14002C279
0x14002c246  cmp     [rax+10h], r12
0x14002c24a  jz      short loc_14002C253
0x14002c24c  mov     ebx, 0C000011Fh
0x14002c251  jmp     short loc_14002C27E
0x14002c253  lea     rax, [rsi+50h]
0x14002c257  mov     r12b, 1
0x14002c25a  mov     [rdi+10h], rax
0x14002c25e  mov     [rsi+1C8h], rdi
0x14002c265  cmp     dword ptr [rdi+30h], 1
0x14002c269  jnz     short loc_14002C270
0x14002c26b  mov     r15b, r12b
0x14002c26e  jmp     short loc_14002C27E
0x14002c270  mov     dword ptr [rdi+30h], 3
0x14002c277  jmp     short loc_14002C27E
0x14002c279  mov     ebx, 0C000000Eh
0x14002c27e  lea     rcx, [r13+18h]; FastMutex
0x14002c282  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002c289  nop     dword ptr [rax+rax+00h]
0x14002c28e  call    cs:__imp_KeLeaveCriticalRegion
0x14002c295  nop     dword ptr [rax+rax+00h]
0x14002c29a  test    ebx, ebx
0x14002c29c  js      loc_14002C391
0x14002c2a2  mov     rax, [rbp+57h+var_A0]
0x14002c2a6  lea     rcx, [rsi+50h]
0x14002c2aa  mov     r9, [rbp+57h+var_88]
0x14002c2ae  mov     r8, [rdi+18h]
0x14002c2b2  mov     rdx, [rdi+20h]
0x14002c2b6  mov     [rsp+0D0h+var_B0], rax
0x14002c2bb  call    InstanceContextInit
0x14002c2c0  mov     ebx, eax
0x14002c2c2  test    eax, eax
0x14002c2c4  js      loc_14002C391
0x14002c2ca  xor     edx, edx
0x14002c2cc  lea     rcx, [rsi+50h]
0x14002c2d0  call    InstanceSetProcessorAffinity
0x14002c2d5  mov     ebx, eax
0x14002c2d7  test    eax, eax
0x14002c2d9  js      loc_14002C391
0x14002c2df  test    r15b, r15b
0x14002c2e2  jnz     loc_14002C3E8
0x14002c2e8  test    byte ptr [rsi+0E8h], 10h
0x14002c2ef  jz      loc_14002C3E8
0x14002c2f5  lea     rdx, [rbp+57h+var_60]
0x14002c2f9  lea     rcx, [rbp+57h+GuidString]
0x14002c2fd  call    PipeParseFilename
0x14002c302  mov     ebx, eax
0x14002c304  test    eax, eax
0x14002c306  js      loc_14002C391
0x14002c30c  lea     r14, [rsi+178h]
0x14002c313  xor     ecx, ecx
0x14002c315  mov     rdx, r14
0x14002c318  call    PipeCreate
0x14002c31d  mov     ebx, eax
0x14002c31f  test    eax, eax
0x14002c321  js      short loc_14002C391
0x14002c323  mov     rax, cs:WdfFunctions_01033
0x14002c32a  mov     rdx, [rbp+57h+var_A0]
0x14002c32e  mov     rcx, cs:WdfDriverGlobals
0x14002c335  mov     rax, [rax+0F8h]
0x14002c33c  call    _guard_dispatch_icall
0x14002c341  mov     r8, [rbp+57h+var_80]
0x14002c345  lea     r9, [rbp+57h+var_60]
0x14002c349  mov     rcx, [r14]; SpinLock
0x14002c34c  mov     rdx, rax
0x14002c34f  call    PipeAccept
0x14002c354  mov     ebx, eax
0x14002c356  test    eax, eax
0x14002c358  js      short loc_14002C391
0x14002c35a  jmp     loc_14002C3E8
0x14002c35f  mov     rax, cs:WdfFunctions_01033
0x14002c366  mov     rdx, r15
0x14002c369  mov     rcx, cs:WdfDriverGlobals
0x14002c370  mov     rax, [rax+8C0h]
0x14002c377  call    _guard_dispatch_icall
0x14002c37c  mov     ecx, [rdi]
0x14002c37e  cmp     ecx, 8
0x14002c381  jnz     short loc_14002C3AC
0x14002c383  xor     edi, edi
0x14002c385  neg     al
0x14002c387  sbb     ebx, ebx
0x14002c389  and     ebx, 0C0000010h
0x14002c38f  jge     short loc_14002C3E8
0x14002c391  test    r12b, r12b
0x14002c394  jz      short loc_14002C3E8
0x14002c396  lea     rcx, [rsi+50h]
0x14002c39a  call    InstanceContextDestroy
0x14002c39f  mov     rdx, rdi
0x14002c3a2  mov     rcx, r13
0x14002c3a5  call    RootOnDeviceInterfaceClose
0x14002c3aa  jmp     short loc_14002C3E8
0x14002c3ac  xor     ebx, ebx
0x14002c3ae  cmp     [r14+40h], rbx
0x14002c3b2  jz      short loc_14002C3C1
0x14002c3b4  cmp     [rbp+57h+GuidString.Length], bx
0x14002c3b8  jz      short loc_14002C3E3
0x14002c3ba  mov     ebx, 0C0000034h
0x14002c3bf  jmp     short loc_14002C3E8
0x14002c3c1  cmp     ecx, 0Ah
0x14002c3c4  jz      short loc_14002C3E3
0x14002c3c6  lea     rdx, [rbp+57h+Guid]; Guid
0x14002c3ca  lea     rcx, [rbp+57h+GuidString]; GuidString
0x14002c3ce  call    cs:__imp_RtlGUIDFromString
0x14002c3d5  nop     dword ptr [rax+rax+00h]
0x14002c3da  mov     ebx, 0C000000Dh
0x14002c3df  test    eax, eax
0x14002c3e1  js      short loc_14002C3E8
0x14002c3e3  mov     ebx, 0C0000010h
0x14002c3e8  mov     rax, cs:WdfFunctions_01033
0x14002c3ef  mov     r8d, ebx
0x14002c3f2  mov     rdx, [rbp+57h+var_78]
0x14002c3f6  mov     rcx, cs:WdfDriverGlobals
0x14002c3fd  mov     rax, [rax+838h]
0x14002c404  call    _guard_dispatch_icall
0x14002c409  mov     rcx, [rbp+57h+var_38]
0x14002c40d  xor     rcx, rsp; StackCookie
0x14002c410  call    __security_check_cookie
0x14002c415  mov     rbx, [rsp+0D0h+arg_18]
0x14002c41d  add     rsp, 0A0h
0x14002c424  pop     r15
0x14002c426  pop     r14
0x14002c428  pop     r13
0x14002c42a  pop     r12
0x14002c42c  pop     rdi
0x14002c42d  pop     rsi
0x14002c42e  pop     rbp
0x14002c42f  retn
```
