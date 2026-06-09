# WinNatInitializeGlobals

- ea: `0x14002e780`
- end: `0x14002e9fa`
- name: `WinNatInitializeGlobals`
- size: `634`
- prototype: `__int64 __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140035078`

## callees

- `0x14000caa0`
- `0x14000d8c8`
- `0x14000dac8`
- `0x14000ddd4`
- `0x14001ede0`
- `0x14001f140`
- `0x14001f440`
- `0x14002e780`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x14002e908`
- `ntoskrnl!KeInitializeDpc` at `0x14002e908`
- `ntoskrnl!ExAllocatePool2` at `0x14002e83e`
- `ntoskrnl!ExAllocatePool2` at `0x14002e8be`
- `ntoskrnl!ExAllocatePool2` at `0x14002e83e`
- `ntoskrnl!ExAllocatePool2` at `0x14002e8be`
- `ntoskrnl!KeInitializeEvent` at `0x14002e816`
- `ntoskrnl!KeInitializeEvent` at `0x14002e816`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002e7f7`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002e7f7`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14002e7a0`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14002e7a0`
- `NETIO!MdpCreatePool` at `0x14002e967`
- `NETIO!MdpCreatePool` at `0x14002e967`
- `NETIO!NetioInitializeWorkQueue` at `0x14002e88d`
- `NETIO!NetioInitializeWorkQueue` at `0x14002e88d`

## pseudocode

```c
__int64 __fastcall WinNatInitializeGlobals(struct _DRIVER_OBJECT *a1)
{
  __int64 MaximumProcessorCount; // rsi
  __int64 result; // rax
  int v4; // edx
  _QWORD *v5; // rcx
  int v6; // r8d
  int v7; // r9d
  unsigned int i; // edi
  __int64 v9; // rbx
  size_t v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rcx
  NTSTATUS v13; // ebx
  __int64 v14; // r8
  int v15; // [rsp+20h] [rbp-78h]
  int v16; // [rsp+38h] [rbp-60h]
  wchar_t pszSrc[12]; // [rsp+50h] [rbp-48h] BYREF

  MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
  qword_140026AA8 = (__int64)&qword_140026AA0;
  qword_140026AA0 = (__int64)&qword_140026AA0;
  qword_140026AB8 = (__int64)&qword_140026AB0;
  qword_140026AB0 = (__int64)&qword_140026AB0;
  wcscpy(pszSrc, L"Wildcard");
  KeInitializeSpinLock(&SpinLock);
  DriverObject = a1;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  dword_140026B60 = MaximumProcessorCount;
  qword_140026B68 = (PVOID)ExAllocatePool2(64, 136 * MaximumProcessorCount, 1668304471);
  if ( !qword_140026B68 )
    return 3221225626LL;
  qword_140026B10 = (__int64)&qword_140026B08;
  qword_140026B08 = &qword_140026B08;
  result = NetioInitializeWorkQueue(qword_140026B18, WinNatGlobalWorkQueueRoutine, DriverObject, deviceObject);
  if ( (int)result < 0 )
    return result;
  dword_140026A84 = 2;
  WinNatGlobalDriverState = 1;
  P = (PVOID)ExAllocatePool2(64, 104LL * (unsigned int)MaximumProcessorCount, 1668566615);
  if ( !P )
    return 3221225626LL;
  for ( i = 0; i < (unsigned int)MaximumProcessorCount; *v5 = v5 )
  {
    v9 = 104LL * i;
    *(_DWORD *)((char *)P + v9) = i;
    KeInitializeDpc((PRKDPC)((char *)P + v9 + 24), WinNatTranslationDpc, 0);
    ++i;
    v5 = (char *)P + v9 + 88;
    v5[1] = v5;
  }
  qword_140026B00 = (PVOID)PplCreateLookasideList((int)v5, v4, v6, v7, v15, 0x28u, 0x63744E57u, v16, 0x63744E57u);
  if ( !qword_140026B00 )
    return 3221225626LL;
  qword_140026AE8 = MdpCreatePool(120, 1651396183);
  WinNatReadRegistryConfig();
  memset(&pszDest, 0, 0x50u);
  v13 = RtlStringCchCopyW(&pszDest, v10, pszSrc);
  if ( v13 < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v12, v11);
  v14 = -1;
  do
    ++v14;
  while ( pszSrc[v14] );
  memmove(&pszDest, pszSrc, 2 * v14);
  result = (unsigned int)v13;
  qword_140026BD8 = 1;
  return result;
}

```

## disassembly

```asm
0x14002e780  push    rbx
0x14002e782  push    rbp
0x14002e783  push    rsi
0x14002e784  push    rdi
0x14002e785  sub     rsp, 78h
0x14002e789  mov     rax, cs:__security_cookie
0x14002e790  xor     rax, rsp
0x14002e793  mov     [rsp+98h+var_30], rax
0x14002e798  mov     rbx, rcx
0x14002e79b  mov     ecx, 0FFFFh; GroupNumber
0x14002e7a0  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x14002e7a7  nop     dword ptr [rax+rax+00h]
0x14002e7ac  movups  xmm0, xmmword ptr cs:aWildcard; "Wildcard"
0x14002e7b3  movzx   edx, word ptr cs:aWildcard+10h; ""
0x14002e7ba  lea     rcx, SpinLock; SpinLock
0x14002e7c1  mov     esi, eax
0x14002e7c3  lea     rax, qword_140026AA0
0x14002e7ca  mov     cs:qword_140026AA8, rax
0x14002e7d1  mov     cs:qword_140026AA0, rax
0x14002e7d8  lea     rax, qword_140026AB0
0x14002e7df  mov     cs:qword_140026AB8, rax
0x14002e7e6  mov     cs:qword_140026AB0, rax
0x14002e7ed  movups  xmmword ptr [rsp+98h+pszSrc], xmm0
0x14002e7f2  mov     [rsp+98h+var_38], dx
0x14002e7f7  call    cs:__imp_KeInitializeSpinLock
0x14002e7fe  nop     dword ptr [rax+rax+00h]
0x14002e803  xor     r8d, r8d; State
0x14002e806  mov     cs:DriverObject, rbx
0x14002e80d  xor     edx, edx; Type
0x14002e80f  lea     rcx, Event; Event
0x14002e816  call    cs:__imp_KeInitializeEvent
0x14002e81d  nop     dword ptr [rax+rax+00h]
0x14002e822  imul    rdx, rsi, 88h
0x14002e829  mov     edi, 40h ; '@'
0x14002e82e  mov     cs:dword_140026B60, esi
0x14002e834  mov     r8d, 63704E57h
0x14002e83a  mov     ecx, edi
0x14002e83c  mov     ebx, esi
0x14002e83e  call    cs:__imp_ExAllocatePool2
0x14002e845  nop     dword ptr [rax+rax+00h]
0x14002e84a  xor     ebp, ebp
0x14002e84c  mov     cs:qword_140026B68, rax
0x14002e853  test    rax, rax
0x14002e856  jz      loc_14002E9DE
0x14002e85c  mov     r9, cs:deviceObject
0x14002e863  lea     rax, qword_140026B08
0x14002e86a  mov     r8, cs:DriverObject
0x14002e871  lea     rdx, WinNatGlobalWorkQueueRoutine
0x14002e878  lea     rcx, qword_140026B18
0x14002e87f  mov     cs:qword_140026B10, rax
0x14002e886  mov     cs:qword_140026B08, rax
0x14002e88d  call    cs:__imp_NetioInitializeWorkQueue
0x14002e894  nop     dword ptr [rax+rax+00h]
0x14002e899  test    eax, eax
0x14002e89b  js      loc_14002E9E3
0x14002e8a1  imul    rdx, rbx, 68h ; 'h'
0x14002e8a5  mov     r8d, 63744E57h
0x14002e8ab  mov     cs:dword_140026A84, 2
0x14002e8b5  mov     ecx, edi
0x14002e8b7  mov     cs:WinNatGlobalDriverState, 1
0x14002e8be  call    cs:__imp_ExAllocatePool2
0x14002e8c5  nop     dword ptr [rax+rax+00h]
0x14002e8ca  mov     cs:P, rax
0x14002e8d1  test    rax, rax
0x14002e8d4  jz      loc_14002E9DE
0x14002e8da  mov     edi, ebp
0x14002e8dc  test    esi, esi
0x14002e8de  jz      short loc_14002E92F
0x14002e8e0  mov     eax, edi
0x14002e8e2  lea     rdx, WinNatTranslationDpc; DeferredRoutine
0x14002e8e9  imul    rbx, rax, 68h ; 'h'
0x14002e8ed  mov     rax, cs:P
0x14002e8f4  xor     r8d, r8d; DeferredContext
0x14002e8f7  mov     [rbx+rax], edi
0x14002e8fa  mov     rcx, cs:P
0x14002e901  add     rcx, 18h
0x14002e905  add     rcx, rbx; Dpc
0x14002e908  call    cs:__imp_KeInitializeDpc
0x14002e90f  nop     dword ptr [rax+rax+00h]
0x14002e914  mov     rcx, cs:P
0x14002e91b  inc     edi
0x14002e91d  add     rcx, 58h ; 'X'
0x14002e921  add     rcx, rbx; int
0x14002e924  mov     [rcx+8], rcx
0x14002e928  mov     [rcx], rcx
0x14002e92b  cmp     edi, esi
0x14002e92d  jb      short loc_14002E8E0
0x14002e92f  mov     [rsp+98h+var_58], 63744E57h; ULONG
0x14002e937  mov     [rsp+98h+var_68], 63744E57h; ULONG
0x14002e93f  mov     [rsp+98h+var_70], 28h ; '('; SIZE_T
0x14002e948  call    PplCreateLookasideList
0x14002e94d  mov     cs:qword_140026B00, rax
0x14002e954  test    rax, rax
0x14002e957  jz      loc_14002E9DE
0x14002e95d  mov     ecx, 78h ; 'x'
0x14002e962  mov     edx, 626E4E57h
0x14002e967  call    cs:__imp_MdpCreatePool
0x14002e96e  nop     dword ptr [rax+rax+00h]
0x14002e973  mov     cs:qword_140026AE8, rax
0x14002e97a  call    WinNatReadRegistryConfig
0x14002e97f  xor     edx, edx; Val
0x14002e981  lea     rdi, pszDest
0x14002e988  mov     rcx, rdi; void *
0x14002e98b  lea     r8d, [rdx+50h]; Size
0x14002e98f  call    memset
0x14002e994  lea     r8, [rsp+98h+pszSrc]; pszSrc
0x14002e999  mov     rcx, rdi; pszDest
0x14002e99c  call    RtlStringCchCopyW
0x14002e9a1  mov     ebx, eax
0x14002e9a3  test    eax, eax
0x14002e9a5  jns     short loc_14002E9AC
0x14002e9a7  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002e9ac  lea     rax, [rsp+98h+pszSrc]
0x14002e9b1  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002e9b5  inc     r8
0x14002e9b8  cmp     [rax+r8*2], bp
0x14002e9bd  jnz     short loc_14002E9B5
0x14002e9bf  add     r8, r8; Size
0x14002e9c2  lea     rdx, [rsp+98h+pszSrc]; Src
0x14002e9c7  mov     rcx, rdi; void *
0x14002e9ca  call    memmove
0x14002e9cf  mov     eax, ebx
0x14002e9d1  mov     cs:qword_140026BD8, 1
0x14002e9dc  jmp     short loc_14002E9E3
0x14002e9de  mov     eax, 0C000009Ah
0x14002e9e3  mov     rcx, [rsp+98h+var_30]
0x14002e9e8  xor     rcx, rsp; StackCookie
0x14002e9eb  call    __security_check_cookie
0x14002e9f0  add     rsp, 78h
0x14002e9f4  pop     rdi
0x14002e9f5  pop     rsi
0x14002e9f6  pop     rbp
0x14002e9f7  pop     rbx
0x14002e9f8  retn
```
