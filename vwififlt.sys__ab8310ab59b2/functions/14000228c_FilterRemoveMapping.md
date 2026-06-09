# FilterRemoveMapping

- ea: `0x14000228c`
- end: `0x140002536`
- name: `FilterRemoveMapping`
- size: `682`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1400033f0`

## callees

- `0x14000228c`
- `0x140007d00`
- `0x140009270`
- `0x14000a730`
- `0x14000cc68`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000d960`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140002355`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140002355`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000240a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000240a`
- `NDIS!NdisFreeMemory` at `0x1400024a5`
- `NDIS!NdisFreeMemory` at `0x1400024b9`
- `NDIS!NdisFreeMemory` at `0x1400024ee`
- `NDIS!NdisFreeMemory` at `0x1400024a5`
- `NDIS!NdisFreeMemory` at `0x1400024b9`
- `NDIS!NdisFreeMemory` at `0x1400024ee`
- `NDIS!NdisResetEvent` at `0x14000241d`
- `NDIS!NdisResetEvent` at `0x14000241d`

## string_xrefs

- `0x14000238f`: `FilterRemoveMapping`
- `0x1400024c8`: `FilterRemoveMapping`

## pseudocode

```c
void __fastcall FilterRemoveMapping(PCUNICODE_STRING SourceString, __int64 a2, __int64 a3)
{
  int v4; // eax
  PVOID v5; // rbp
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  USHORT MaximumLength; // ax
  struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C i; // rbx
  __int64 v10; // rdx
  __int64 v11; // r8
  struct _DEVICE_OBJECT *j; // rbx
  __int64 v13; // rax
  struct _DRIVER_OBJECT *DriverObject; // rcx
  _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF
  PVOID VirtualAddress; // [rsp+70h] [rbp+8h] BYREF

  VirtualAddress = 0;
  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  v4 = AllocMem(WPP_MAIN_CB.DeviceExtension, SourceString->MaximumLength, a3, &VirtualAddress);
  v5 = VirtualAddress;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v7 = 41;
LABEL_8:
      WPP_SF_d(v6->AttachedDevice, v7, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    }
  }
  else
  {
    MaximumLength = SourceString->MaximumLength;
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.MaximumLength = MaximumLength;
    DestinationString.Buffer = (PWSTR)VirtualAddress;
    if ( RtlUpcaseUnicodeString(&DestinationString, SourceString, 0) >= 0 )
    {
      AcquireSpinLock(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, "FilterRemoveMapping", 563, 0);
      for ( i = WPP_MAIN_CB.DeviceQueue.1;
            *(struct _DEVICE_OBJECT **)&i != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.Busy;
            i = **(struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C **)&i )
      {
        if ( *(_QWORD *)(*(_QWORD *)&i + 2648LL)
          && filterEqualUnicodeString((const void **)&DestinationString, *(_QWORD *)&i + 2640LL) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, v10, v11, *(_QWORD *)&i + 160LL);
          }
          RtlInitUnicodeString((PUNICODE_STRING)(*(_QWORD *)&i + 2640LL), 0);
          NdisResetEvent((PNDIS_EVENT)(*(_QWORD *)&i + 2544LL));
          break;
        }
      }
      for ( j = (struct _DEVICE_OBJECT *)WPP_MAIN_CB.Dpc.DeferredRoutine;
            j != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Dpc.DeferredRoutine;
            j = *(struct _DEVICE_OBJECT **)&j->Type )
      {
        if ( filterEqualUnicodeString((const void **)&DestinationString, (__int64)&j->AttachedDevice) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
          }
          v13 = *(_QWORD *)&j->Type;
          if ( *(struct _DEVICE_OBJECT **)(*(_QWORD *)&j->Type + 8LL) != j
            || (DriverObject = j->DriverObject, *(struct _DEVICE_OBJECT **)&DriverObject->Type != j) )
          {
            __fastfail(3u);
          }
          *(_QWORD *)&DriverObject->Type = v13;
          *(_QWORD *)(v13 + 8) = DriverObject;
          NdisFreeMemory(j->CurrentIrp, 0, 0);
          NdisFreeMemory(j, 0, 0);
          break;
        }
      }
      ReleaseSpinLock(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, "FilterRemoveMapping", 616, 0);
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v7 = 42;
        goto LABEL_8;
      }
    }
  }
  if ( v5 )
    NdisFreeMemory(v5, 0, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
}

```

## disassembly

```asm
0x14000228c  push    rbx
0x14000228e  push    rbp
0x14000228f  push    rsi
0x140002290  push    rdi
0x140002291  push    r14
0x140002293  push    r15
0x140002295  sub     rsp, 38h
0x140002299  xorps   xmm0, xmm0
0x14000229c  mov     [rsp+68h+VirtualAddress], 0
0x1400022a5  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1400022aa  mov     rbx, rcx
0x1400022ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400022b4  lea     r14, WPP_GLOBAL_Control
0x1400022bb  lea     r15, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x1400022c2  cmp     rcx, r14
0x1400022c5  jz      short loc_1400022DF
0x1400022c7  mov     eax, [rcx+2Ch]
0x1400022ca  test    al, 20h
0x1400022cc  jz      short loc_1400022DF
0x1400022ce  mov     rcx, [rcx+18h]
0x1400022d2  mov     edx, 28h ; '('
0x1400022d7  mov     r8, r15
0x1400022da  call    WPP_SF_
0x1400022df  movzx   edx, word ptr [rbx+2]
0x1400022e3  lea     r9, [rsp+68h+VirtualAddress]
0x1400022e8  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400022ef  call    AllocMem
0x1400022f4  mov     rbp, [rsp+68h+VirtualAddress]
0x1400022f9  mov     edi, eax
0x1400022fb  test    eax, eax
0x1400022fd  jz      short loc_140002334
0x1400022ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140002306  cmp     rcx, r14
0x140002309  jz      loc_1400024E1
0x14000230f  mov     edx, [rcx+2Ch]
0x140002312  test    dl, 1
0x140002315  jz      loc_1400024E1
0x14000231b  mov     edx, 29h ; ')'
0x140002320  mov     r9d, eax
0x140002323  mov     rcx, [rcx+18h]
0x140002327  mov     r8, r15
0x14000232a  call    WPP_SF_d
0x14000232f  jmp     loc_1400024E1
0x140002334  movzx   eax, word ptr [rbx+2]
0x140002338  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14000233d  xorps   xmm0, xmm0
0x140002340  xor     r8d, r8d; AllocateDestinationString
0x140002343  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140002348  mov     rdx, rbx; SourceString
0x14000234b  mov     [rsp+68h+DestinationString.MaximumLength], ax
0x140002350  mov     [rsp+68h+DestinationString.Buffer], rbp
0x140002355  call    cs:__imp_RtlUpcaseUnicodeString
0x14000235c  nop     dword ptr [rax+rax+00h]
0x140002361  mov     edi, eax
0x140002363  test    eax, eax
0x140002365  jns     short loc_14000238C
0x140002367  mov     rcx, cs:WPP_GLOBAL_Control
0x14000236e  cmp     rcx, r14
0x140002371  jz      loc_1400024E1
0x140002377  mov     eax, [rcx+2Ch]
0x14000237a  test    al, 1
0x14000237c  jz      loc_1400024E1
0x140002382  mov     edx, 2Ah ; '*'
0x140002387  mov     r9d, edi
0x14000238a  jmp     short loc_140002323
0x14000238c  xor     r9d, r9d
0x14000238f  lea     rdx, aFilterremovema; "FilterRemoveMapping"
0x140002396  mov     r8d, 233h
0x14000239c  lea     rcx, WPP_MAIN_CB.Queue+10h
0x1400023a3  call    AcquireSpinLock
0x1400023a8  mov     rbx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x1400023af  lea     rax, WPP_MAIN_CB.DeviceQueue.20h
0x1400023b6  cmp     rbx, rax
0x1400023b9  jz      short loc_140002429
0x1400023bb  cmp     qword ptr [rbx+0A58h], 0
0x1400023c3  jz      short loc_1400023DD
0x1400023c5  lea     rsi, [rbx+0A50h]
0x1400023cc  mov     rdx, rsi
0x1400023cf  lea     rcx, [rsp+68h+DestinationString]
0x1400023d4  call    filterEqualUnicodeString
0x1400023d9  test    al, al
0x1400023db  jnz     short loc_1400023E2
0x1400023dd  mov     rbx, [rbx]
0x1400023e0  jmp     short loc_1400023AF
0x1400023e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023e9  cmp     rcx, r14
0x1400023ec  jz      short loc_140002405
0x1400023ee  mov     eax, [rcx+2Ch]
0x1400023f1  test    al, 4
0x1400023f3  jz      short loc_140002405
0x1400023f5  mov     rcx, [rcx+18h]
0x1400023f9  lea     r9, [rbx+0A0h]
0x140002400  call    WPP_SF_S
0x140002405  xor     edx, edx; SourceString
0x140002407  mov     rcx, rsi; DestinationString
0x14000240a  call    cs:__imp_RtlInitUnicodeString
0x140002411  nop     dword ptr [rax+rax+00h]
0x140002416  lea     rcx, [rbx+9F0h]; Event
0x14000241d  call    cs:__imp_NdisResetEvent
0x140002424  nop     dword ptr [rax+rax+00h]
0x140002429  mov     rbx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x140002430  lea     rax, WPP_MAIN_CB.Dpc.DeferredRoutine
0x140002437  cmp     rbx, rax
0x14000243a  jz      loc_1400024C5
0x140002440  lea     rdx, [rbx+18h]
0x140002444  lea     rcx, [rsp+68h+DestinationString]
0x140002449  call    filterEqualUnicodeString
0x14000244e  test    al, al
0x140002450  jnz     short loc_140002457
0x140002452  mov     rbx, [rbx]
0x140002455  jmp     short loc_140002430
0x140002457  mov     rcx, cs:WPP_GLOBAL_Control
0x14000245e  cmp     rcx, r14
0x140002461  jz      short loc_14000247B
0x140002463  mov     eax, [rcx+2Ch]
0x140002466  test    al, 4
0x140002468  jz      short loc_14000247B
0x14000246a  mov     rcx, [rcx+18h]
0x14000246e  mov     edx, 2Ch ; ','
0x140002473  mov     r8, r15
0x140002476  call    WPP_SF_
0x14000247b  mov     rax, [rbx]
0x14000247e  cmp     [rax+8], rbx
0x140002482  jnz     loc_14000252F
0x140002488  mov     rcx, [rbx+8]
0x14000248c  cmp     [rcx], rbx
0x14000248f  jnz     loc_14000252F
0x140002495  mov     [rcx], rax
0x140002498  xor     r8d, r8d; MemoryFlags
0x14000249b  mov     [rax+8], rcx
0x14000249f  xor     edx, edx; Length
0x1400024a1  mov     rcx, [rbx+20h]; VirtualAddress
0x1400024a5  call    cs:__imp_NdisFreeMemory
0x1400024ac  nop     dword ptr [rax+rax+00h]
0x1400024b1  xor     r8d, r8d; MemoryFlags
0x1400024b4  xor     edx, edx; Length
0x1400024b6  mov     rcx, rbx; VirtualAddress
0x1400024b9  call    cs:__imp_NdisFreeMemory
0x1400024c0  nop     dword ptr [rax+rax+00h]
0x1400024c5  xor     r9d, r9d
0x1400024c8  lea     rdx, aFilterremovema; "FilterRemoveMapping"
0x1400024cf  mov     r8d, 268h
0x1400024d5  lea     rcx, WPP_MAIN_CB.Queue+10h
0x1400024dc  call    ReleaseSpinLock
0x1400024e1  test    rbp, rbp
0x1400024e4  jz      short loc_1400024FA
0x1400024e6  xor     r8d, r8d; MemoryFlags
0x1400024e9  xor     edx, edx; Length
0x1400024eb  mov     rcx, rbp; VirtualAddress
0x1400024ee  call    cs:__imp_NdisFreeMemory
0x1400024f5  nop     dword ptr [rax+rax+00h]
0x1400024fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140002501  cmp     rcx, r14
0x140002504  jz      short loc_140002521
0x140002506  mov     eax, [rcx+2Ch]
0x140002509  test    al, 20h
0x14000250b  jz      short loc_140002521
0x14000250d  mov     rcx, [rcx+18h]
0x140002511  mov     edx, 2Dh ; '-'
0x140002516  mov     r9d, edi
0x140002519  mov     r8, r15
0x14000251c  call    WPP_SF_d
0x140002521  add     rsp, 38h
0x140002525  pop     r15
0x140002527  pop     r14
0x140002529  pop     rdi
0x14000252a  pop     rsi
0x14000252b  pop     rbp
0x14000252c  pop     rbx
0x14000252d  retn
0x14000252f  mov     ecx, 3
0x140002534  int     29h; Win8: RtlFailFast(ecx)
```
