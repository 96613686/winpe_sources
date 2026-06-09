# UdfSeqCacheInitialize

- ea: `0x14003bb18`
- end: `0x14003bdf1`
- name: `UdfSeqCacheInitialize`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140049f80`

## callees

- `0x14000cad4`
- `0x140019b90`
- `0x14001c080`
- `0x14003b608`
- `0x14003bb18`
- `0x14003cf8c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003bca7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003bca7`
- `ntoskrnl!ExRaiseStatus` at `0x14003bb99`
- `ntoskrnl!ExRaiseStatus` at `0x14003bbbf`
- `ntoskrnl!ExRaiseStatus` at `0x14003bbf6`
- `ntoskrnl!ExRaiseStatus` at `0x14003bc81`
- `ntoskrnl!ExRaiseStatus` at `0x14003bce5`
- `ntoskrnl!ExRaiseStatus` at `0x14003bdd1`
- `ntoskrnl!ExRaiseStatus` at `0x14003bb99`
- `ntoskrnl!ExRaiseStatus` at `0x14003bbbf`
- `ntoskrnl!ExRaiseStatus` at `0x14003bbf6`
- `ntoskrnl!ExRaiseStatus` at `0x14003bc81`
- `ntoskrnl!ExRaiseStatus` at `0x14003bce5`
- `ntoskrnl!ExRaiseStatus` at `0x14003bdd1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003bdaa`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003bdaa`
- `ntoskrnl!KeInitializeEvent` at `0x14003bd05`
- `ntoskrnl!KeInitializeEvent` at `0x14003bd05`
- `ntoskrnl!ZwClose` at `0x14003bdbc`
- `ntoskrnl!ZwClose` at `0x14003bdbc`
- `ntoskrnl!PsCreateSystemThread` at `0x14003bd71`
- `ntoskrnl!PsCreateSystemThread` at `0x14003bd71`

## pseudocode

```c
NTSTATUS __fastcall UdfSeqCacheInitialize(__int64 a1, __int64 a2)
{
  NTSTATUS v4; // eax
  NTSTATUS v5; // eax
  __int64 *v6; // r14
  NTSTATUS v7; // eax
  __int64 v8; // r13
  __int64 i; // rsi
  NTSTATUS v10; // eax
  __int64 v11; // r8
  __int64 v12; // rax
  unsigned int v13; // r15d
  PVOID PoolWithTag; // rax
  PVOID v15; // rsi
  bool v16; // zf
  void (__fastcall *StartRoutine)(__int64); // rax
  int v18; // ebx
  __int64 v19; // rax
  NTSTATUS result; // eax
  void *ThreadHandle; // [rsp+40h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-38h] BYREF
  SIZE_T NumberOfBytes; // [rsp+C8h] [rbp+48h] BYREF
  int v24; // [rsp+D0h] [rbp+50h] BYREF
  int v25; // [rsp+D8h] [rbp+58h] BYREF

  v25 = 0;
  memset(&ObjectAttributes, 0, 44);
  LODWORD(NumberOfBytes) = 0;
  v24 = 0;
  ThreadHandle = 0;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 14, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
  }
  v4 = UdfQueryDeviceBufferSize(*(_QWORD *)(a2 + 24), &v25);
  if ( v4 < 0 )
  {
    *(_DWORD *)(a1 + 24) = v4;
    ExRaiseStatus(v4);
  }
  v5 = UdfSeqCacheDetermineMaxTransferLength(a1, &NumberOfBytes, &v24);
  if ( v5 < 0 )
  {
    *(_DWORD *)(a1 + 24) = v5;
    ExRaiseStatus(v5);
  }
  if ( (*(_DWORD *)(a2 + 48) & 0x20000000) != 0 )
  {
    for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
    {
      v10 = UdfSeqCacheAllocate(a2, v25, NumberOfBytes, v24, a2 + 104 + 8 * i);
      if ( v10 < 0 )
      {
        *(_DWORD *)(a1 + 24) = v10;
        ExRaiseStatus(v10);
      }
      v11 = *(_QWORD *)(a2 + 8 * i + 104);
      if ( (_DWORD)i == 1 )
      {
        v12 = *(_QWORD *)(a2 + 320);
      }
      else if ( (_DWORD)i == 2 )
      {
        v12 = *(_QWORD *)(a2 + 328);
      }
      else
      {
        v12 = 0;
      }
      *(_QWORD *)(v11 + 752) = v12;
      if ( v12 )
        v12 = *(_QWORD *)(v12 + 32) / (__int64)*(unsigned int *)(a2 + 68);
      *(_DWORD *)(v11 + 744) = v12;
    }
    v13 = NumberOfBytes;
    v6 = (__int64 *)(a2 + 104);
    v8 = *(_QWORD *)(a2 + 104);
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1041, (unsigned int)NumberOfBytes, 0x57666455u);
    v15 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, v13);
    *(_QWORD *)(a2 + 128) = v15;
    if ( !v15 )
    {
      *(_DWORD *)(a1 + 24) = -1073741801;
      ExRaiseStatus(-1073741801);
    }
  }
  else
  {
    v6 = (__int64 *)(a2 + 104);
    v7 = UdfSeqCacheAllocate(a2, v25, NumberOfBytes, v24, a2 + 104);
    if ( v7 < 0 )
    {
      *(_DWORD *)(a1 + 24) = v7;
      ExRaiseStatus(v7);
    }
    v8 = *v6;
  }
  KeInitializeEvent((PRKEVENT)(v8 + 592), SynchronizationEvent, 0);
  v16 = (*(_DWORD *)(a2 + 48) & 0x20000000) == 0;
  StartRoutine = UdfSeqCacheWriterWorkerRoutineForPOW;
  ObjectAttributes.Length = 48;
  if ( v16 )
    StartRoutine = UdfSeqCacheWriterWorkerRoutineForVAT;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v18 = PsCreateSystemThread(
          &ThreadHandle,
          0x2000000u,
          &ObjectAttributes,
          0,
          0,
          (PKSTART_ROUTINE)StartRoutine,
          (PVOID)a2);
  if ( v18 < 0
    || (v19 = *v6,
        *(_DWORD *)(v19 + 4) |= 8u,
        v18 = ObReferenceObjectByHandle(ThreadHandle, 0x2000000u, 0, 0, (PVOID *)(v19 + 616), 0),
        result = ZwClose(ThreadHandle),
        v18 < 0) )
  {
    *(_DWORD *)(a1 + 24) = v18;
    ExRaiseStatus(v18);
  }
  return result;
}

```

## disassembly

```asm
0x14003bb18  push    rbp
0x14003bb1a  push    rbx
0x14003bb1b  push    rsi
0x14003bb1c  push    rdi
0x14003bb1d  push    r13
0x14003bb1f  push    r14
0x14003bb21  push    r15
0x14003bb23  mov     rbp, rsp
0x14003bb26  sub     rsp, 80h
0x14003bb2d  xor     eax, eax
0x14003bb2f  xorps   xmm0, xmm0
0x14003bb32  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14003bb36  mov     rbx, rdx
0x14003bb39  mov     rdi, rcx
0x14003bb3c  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14003bb40  mov     [rbp+arg_18], eax
0x14003bb43  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14003bb47  mov     dword ptr [rbp+NumberOfBytes], eax
0x14003bb4a  mov     [rbp+arg_10], eax
0x14003bb4d  mov     [rbp+ThreadHandle], rax
0x14003bb51  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bb58  lea     rax, WPP_GLOBAL_Control
0x14003bb5f  mov     esi, 20000000h
0x14003bb64  cmp     rcx, rax
0x14003bb67  jz      short loc_14003BB83
0x14003bb69  test    [rcx+2Ch], esi
0x14003bb6c  jz      short loc_14003BB83
0x14003bb6e  mov     rcx, [rcx+18h]
0x14003bb72  lea     r8, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids
0x14003bb79  mov     edx, 0Eh
0x14003bb7e  call    WPP_SF_
0x14003bb83  mov     rcx, [rbx+18h]
0x14003bb87  lea     rdx, [rbp+arg_18]
0x14003bb8b  call    UdfQueryDeviceBufferSize
0x14003bb90  test    eax, eax
0x14003bb92  jns     short loc_14003BBA6
0x14003bb94  mov     ecx, eax; Status
0x14003bb96  mov     [rdi+18h], eax
0x14003bb99  call    cs:__imp_ExRaiseStatus
0x14003bba6  lea     r8, [rbp+arg_10]
0x14003bbaa  mov     rcx, rdi
0x14003bbad  lea     rdx, [rbp+NumberOfBytes]
0x14003bbb1  call    UdfSeqCacheDetermineMaxTransferLength
0x14003bbb6  test    eax, eax
0x14003bbb8  jns     short loc_14003BBCC
0x14003bbba  mov     ecx, eax; Status
0x14003bbbc  mov     [rdi+18h], eax
0x14003bbbf  call    cs:__imp_ExRaiseStatus
0x14003bbcc  test    [rbx+30h], esi
0x14003bbcf  jnz     short loc_14003BC0B
0x14003bbd1  mov     r9d, [rbp+arg_10]
0x14003bbd5  lea     r14, [rbx+68h]
0x14003bbd9  mov     r8d, dword ptr [rbp+NumberOfBytes]
0x14003bbdd  mov     rcx, rbx
0x14003bbe0  mov     edx, [rbp+arg_18]
0x14003bbe3  mov     [rsp+80h+ClientId], r14
0x14003bbe8  call    UdfSeqCacheAllocate
0x14003bbed  test    eax, eax
0x14003bbef  jns     short loc_14003BC03
0x14003bbf1  mov     ecx, eax; Status
0x14003bbf3  mov     [rdi+18h], eax
0x14003bbf6  call    cs:__imp_ExRaiseStatus
0x14003bc03  mov     r13, [r14]
0x14003bc06  jmp     loc_14003BCF7
0x14003bc0b  xor     esi, esi
0x14003bc0d  cmp     esi, 3
0x14003bc10  jnb     short loc_14003BC8E
0x14003bc12  mov     r9d, [rbp+arg_10]
0x14003bc16  lea     rax, [rbx+68h]
0x14003bc1a  mov     r8d, dword ptr [rbp+NumberOfBytes]
0x14003bc1e  lea     rax, [rax+rsi*8]
0x14003bc22  mov     edx, [rbp+arg_18]
0x14003bc25  mov     rcx, rbx
0x14003bc28  mov     [rsp+80h+ClientId], rax
0x14003bc2d  call    UdfSeqCacheAllocate
0x14003bc32  test    eax, eax
0x14003bc34  js      short loc_14003BC7C
0x14003bc36  mov     r8, [rbx+rsi*8+68h]
0x14003bc3b  cmp     esi, 1
0x14003bc3e  jnz     short loc_14003BC49
0x14003bc40  mov     rax, [rbx+140h]
0x14003bc47  jmp     short loc_14003BC59
0x14003bc49  cmp     esi, 2
0x14003bc4c  jnz     short loc_14003BC57
0x14003bc4e  mov     rax, [rbx+148h]
0x14003bc55  jmp     short loc_14003BC59
0x14003bc57  xor     eax, eax
0x14003bc59  mov     [r8+2F0h], rax
0x14003bc60  test    rax, rax
0x14003bc63  jz      short loc_14003BC71
0x14003bc65  mov     rax, [rax+20h]
0x14003bc69  mov     ecx, [rbx+44h]
0x14003bc6c  cqo
0x14003bc6e  idiv    rcx
0x14003bc71  mov     [r8+2E8h], eax
0x14003bc78  inc     esi
0x14003bc7a  jmp     short loc_14003BC0D
0x14003bc7c  mov     ecx, eax; Status
0x14003bc7e  mov     [rdi+18h], eax
0x14003bc81  call    cs:__imp_ExRaiseStatus
0x14003bc8e  mov     r15d, dword ptr [rbp+NumberOfBytes]
0x14003bc92  lea     r14, [rbx+68h]
0x14003bc96  mov     r13, [r14]
0x14003bc99  mov     edx, r15d; NumberOfBytes
0x14003bc9c  mov     r8d, 57666455h; Tag
0x14003bca2  mov     ecx, 411h; PoolType
0x14003bca7  call    cs:__imp_ExAllocatePoolWithTag
0x14003bcae  nop     dword ptr [rax+rax+00h]
0x14003bcb3  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14003bcba  mov     rsi, rax
0x14003bcbd  jnz     short loc_14003BCD1
0x14003bcbf  test    rax, rax
0x14003bcc2  jz      short loc_14003BCD1
0x14003bcc4  mov     r8d, r15d; Size
0x14003bcc7  xor     edx, edx; Val
0x14003bcc9  mov     rcx, rax; void *
0x14003bccc  call    memset
0x14003bcd1  mov     [rbx+80h], rsi
0x14003bcd8  test    rsi, rsi
0x14003bcdb  jnz     short loc_14003BCF2
0x14003bcdd  mov     ecx, 0C0000017h; Status
0x14003bce2  mov     [rdi+18h], ecx
0x14003bce5  call    cs:__imp_ExRaiseStatus
0x14003bcf2  mov     esi, 20000000h
0x14003bcf7  xor     r8d, r8d; State
0x14003bcfa  lea     rcx, [r13+250h]; Event
0x14003bd01  lea     edx, [r8+1]; Type
0x14003bd05  call    cs:__imp_KeInitializeEvent
0x14003bd0c  nop     dword ptr [rax+rax+00h]
0x14003bd11  test    [rbx+30h], esi
0x14003bd14  lea     rcx, UdfSeqCacheWriterWorkerRoutineForVAT
0x14003bd1b  xorps   xmm0, xmm0
0x14003bd1e  mov     [rsp+80h+StartContext], rbx; StartContext
0x14003bd23  lea     rax, UdfSeqCacheWriterWorkerRoutineForPOW
0x14003bd2a  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14003bd31  cmovz   rax, rcx
0x14003bd35  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14003bd3d  mov     [rsp+80h+StartRoutine], rax; StartRoutine
0x14003bd42  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14003bd46  mov     esi, 2000000h
0x14003bd4b  mov     [rsp+80h+ClientId], 0; ClientId
0x14003bd54  xor     r9d, r9d; ProcessHandle
0x14003bd57  mov     [rbp+ObjectAttributes.Attributes], 200h
0x14003bd5e  mov     edx, esi; DesiredAccess
0x14003bd60  mov     [rbp+ObjectAttributes.ObjectName], 0
0x14003bd68  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x14003bd6c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14003bd71  call    cs:__imp_PsCreateSystemThread
0x14003bd78  nop     dword ptr [rax+rax+00h]
0x14003bd7d  mov     ebx, eax
0x14003bd7f  test    eax, eax
0x14003bd81  js      short loc_14003BDCC
0x14003bd83  mov     rax, [r14]
0x14003bd86  xor     r9d, r9d; AccessMode
0x14003bd89  mov     [rsp+80h+StartRoutine], 0; HandleInformation
0x14003bd92  xor     r8d, r8d; ObjectType
0x14003bd95  mov     edx, esi; DesiredAccess
0x14003bd97  or      dword ptr [rax+4], 8
0x14003bd9b  add     rax, 268h
0x14003bda1  mov     rcx, [rbp+ThreadHandle]; Handle
0x14003bda5  mov     [rsp+80h+ClientId], rax; Object
0x14003bdaa  call    cs:__imp_ObReferenceObjectByHandle
0x14003bdb1  nop     dword ptr [rax+rax+00h]
0x14003bdb6  mov     rcx, [rbp+ThreadHandle]; Handle
0x14003bdba  mov     ebx, eax
0x14003bdbc  call    cs:__imp_ZwClose
0x14003bdc3  nop     dword ptr [rax+rax+00h]
0x14003bdc8  test    ebx, ebx
0x14003bdca  jns     short loc_14003BDDE
0x14003bdcc  mov     ecx, ebx; Status
0x14003bdce  mov     [rdi+18h], ebx
0x14003bdd1  call    cs:__imp_ExRaiseStatus
0x14003bdde  add     rsp, 80h
0x14003bde5  pop     r15
0x14003bde7  pop     r14
0x14003bde9  pop     r13
0x14003bdeb  pop     rdi
0x14003bdec  pop     rsi
0x14003bded  pop     rbx
0x14003bdee  pop     rbp
0x14003bdef  retn
```
