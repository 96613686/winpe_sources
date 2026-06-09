# MpAsyncScanInitialize

- ea: `0x14008e4b0`
- end: `0x14008e85e`
- name: `MpAsyncScanInitialize`
- size: `942`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14008f314`

## callees

- `0x1400026c0`
- `0x140003d20`
- `0x140003ed0`
- `0x1400051bc`
- `0x140007030`
- `0x1400118d0`
- `0x140079778`
- `0x14008e4b0`

## import_xrefs

- `ntoskrnl!KeQueryActiveProcessorCount` at `0x14008e62b`
- `ntoskrnl!KeQueryActiveProcessorCount` at `0x14008e62b`
- `ntoskrnl!ZwClose` at `0x14008e697`
- `ntoskrnl!ZwClose` at `0x14008e818`
- `ntoskrnl!ZwClose` at `0x140094aa0`
- `ntoskrnl!ZwClose` at `0x14008e697`
- `ntoskrnl!ZwClose` at `0x14008e818`
- `ntoskrnl!ZwClose` at `0x140094aa0`
- `ntoskrnl!KeInitializeEvent` at `0x14008e5ae`
- `ntoskrnl!KeInitializeEvent` at `0x14008e5cd`
- `ntoskrnl!KeInitializeEvent` at `0x14008e5ae`
- `ntoskrnl!KeInitializeEvent` at `0x14008e5cd`
- `ntoskrnl!PsThreadType` at `0x14008e755`
- `ntoskrnl!KeInitializeSemaphore` at `0x14008e5ef`
- `ntoskrnl!KeInitializeSemaphore` at `0x14008e5ef`
- `ntoskrnl!PsCreateSystemThread` at `0x14008e6d8`
- `ntoskrnl!PsCreateSystemThread` at `0x14008e6d8`

## pseudocode

```c
__int64 MpAsyncScanInitialize()
{
  __int64 result; // rax
  _QWORD *PoolWithTag; // rax
  int v2; // ebx
  ULONG ActiveProcessorCount; // eax
  unsigned int v4; // esi
  __int64 i; // rdi
  NTSTATUS v6; // eax
  __int64 v7; // rdx
  __int64 *v8; // rdx
  unsigned __int64 v9; // rax
  __int64 v10; // rax
  __int64 *v11; // rcx
  NTSTATUS ClientId; // [rsp+20h] [rbp-88h]
  HANDLE Handle; // [rsp+58h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-48h] BYREF

  memset(&ObjectAttributes, 0, 44);
  Handle = 0;
  result = (unsigned int)dword_140026A1C;
  if ( dword_140026A1C )
  {
    PoolWithTag = (_QWORD *)MpAllocatePoolWithTag((unsigned int)ExDefaultNonPagedPoolType, 1312, 1935757389);
    MpAsyncScanData = PoolWithTag;
    if ( PoolWithTag )
    {
      PoolWithTag[1] = PoolWithTag;
      *PoolWithTag = PoolWithTag;
      *((_DWORD *)PoolWithTag + 50) = 1;
      PoolWithTag[26] = 0;
      *((_DWORD *)PoolWithTag + 54) = 0;
      KeInitializeEvent((PRKEVENT)(PoolWithTag + 28), SynchronizationEvent, 0);
      KeInitializeEvent((PRKEVENT)MpAsyncScanData + 6, NotificationEvent, 0);
      KeInitializeSemaphore((PRKSEMAPHORE)((char *)MpAsyncScanData + 168), 0, 0x7FFFFFFF);
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 512;
      ObjectAttributes.ObjectName = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      ActiveProcessorCount = KeQueryActiveProcessorCount(0);
      v4 = ActiveProcessorCount;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_e14b9b336f94348117623c9565965302_Traceguids,
          ActiveProcessorCount,
          16);
      if ( v4 > 0x10 )
        v4 = 16;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= v4 )
        {
          v8 = (__int64 *)((char *)MpAsyncScanData + 272);
          v9 = (unsigned __int64)MpAsyncScanData + 1296;
          *((_DWORD *)MpAsyncScanData + 324) = 0;
          *(_DWORD *)(v9 + 4) = *(_DWORD *)(v9 + 4) & 0x1F | 0x1000;
          *(_QWORD *)(v9 + 8) = v8;
          *(_DWORD *)(v9 + 4) = 4096;
          v10 = v9 | 1;
          v11 = v8 + 128;
          if ( v8 )
          {
            while ( v8 < v11 )
              *v8++ = v10;
          }
          v2 = 0;
          goto LABEL_30;
        }
        if ( Handle )
        {
          ZwClose(Handle);
          Handle = 0;
        }
        v6 = PsCreateSystemThread(&Handle, 0, &ObjectAttributes, 0, 0, MpAsyncScanWorkerThread, (PVOID)(unsigned int)i);
        v2 = v6;
        if ( v6 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v7 = 12;
            ClientId = v6;
LABEL_20:
            _mm_lfence();
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              v7,
              WPP_e14b9b336f94348117623c9565965302_Traceguids,
              KeGetCurrentThread(),
              ClientId);
            goto LABEL_30;
          }
          goto LABEL_30;
        }
        _mm_lfence();
        v2 = MpReferenceObjectByHandle((int)Handle, 0x1FFFFF, (int)PsThreadType, 0, (PVOID *)MpAsyncScanData + i + 2);
        if ( v2 < 0 )
          break;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v7 = 13;
        ClientId = v2;
        goto LABEL_20;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          WPP_e14b9b336f94348117623c9565965302_Traceguids,
          KeGetCurrentThread());
      v2 = -1073741670;
    }
LABEL_30:
    if ( Handle )
      ZwClose(Handle);
    if ( v2 < 0 )
      MpAsyncScanShutdown();
    return (unsigned int)v2;
  }
  return result;
}

```

## disassembly

```asm
0x14008e4b0  mov     r11, rsp
0x14008e4b3  mov     [r11+8], rbx
0x14008e4b7  mov     [r11+10h], rsi
0x14008e4bb  mov     [r11+18h], rdi
0x14008e4bf  mov     [r11+20h], r14
0x14008e4c3  push    r15
0x14008e4c5  sub     rsp, 0A0h
0x14008e4cc  mov     rax, cs:__security_cookie
0x14008e4d3  xor     rax, rsp
0x14008e4d6  mov     [rsp+0A8h+var_18], rax
0x14008e4de  mov     [rsp+0A8h+var_68], 0C0000001h
0x14008e4e6  xor     eax, eax
0x14008e4e8  xorps   xmm0, xmm0
0x14008e4eb  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x14008e4f0  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x14008e4f5  mov     [r11-28h], rax
0x14008e4f9  mov     [r11-20h], eax
0x14008e4fd  mov     [r11-50h], rax
0x14008e501  mov     eax, cs:dword_140026A1C
0x14008e507  test    eax, eax
0x14008e509  jz      loc_14008E82F
0x14008e50f  mov     edx, 520h
0x14008e514  mov     r8d, 7361504Dh
0x14008e51a  mov     ecx, cs:ExDefaultNonPagedPoolType
0x14008e520  call    MpAllocatePoolWithTag
0x14008e525  mov     cs:MpAsyncScanData, rax
0x14008e52c  test    rax, rax
0x14008e52f  jnz     short loc_14008E57A
0x14008e531  lea     r14, WPP_GLOBAL_Control
0x14008e538  mov     rax, cs:WPP_GLOBAL_Control
0x14008e53f  cmp     rax, r14
0x14008e542  jz      short loc_14008E570
0x14008e544  mov     eax, [rax+2Ch]
0x14008e547  test    al, 1
0x14008e549  jz      short loc_14008E570
0x14008e54b  mov     r9, gs:188h
0x14008e554  mov     edx, 0Ah
0x14008e559  lea     r8, WPP_e14b9b336f94348117623c9565965302_Traceguids
0x14008e560  mov     rcx, cs:WPP_GLOBAL_Control
0x14008e567  mov     rcx, [rcx+18h]
0x14008e56b  call    WPP_SF_q
0x14008e570  mov     ebx, 0C000009Ah
0x14008e575  jmp     loc_14008E80A
0x14008e57a  mov     [rax+8], rax
0x14008e57e  mov     [rax], rax
0x14008e581  mov     dword ptr [rax+0C8h], 1
0x14008e58b  mov     qword ptr [rax+0D0h], 0
0x14008e596  mov     dword ptr [rax+0D8h], 0
0x14008e5a0  lea     rcx, [rax+0E0h]; Event
0x14008e5a7  xor     r8d, r8d; State
0x14008e5aa  lea     edx, [r8+1]; Type
0x14008e5ae  call    cs:__imp_KeInitializeEvent
0x14008e5b5  nop     dword ptr [rax+rax+00h]
0x14008e5ba  mov     rcx, cs:MpAsyncScanData
0x14008e5c1  add     rcx, 90h; Event
0x14008e5c8  xor     r8d, r8d; State
0x14008e5cb  xor     edx, edx; Type
0x14008e5cd  call    cs:__imp_KeInitializeEvent
0x14008e5d4  nop     dword ptr [rax+rax+00h]
0x14008e5d9  mov     rcx, cs:MpAsyncScanData
0x14008e5e0  add     rcx, 0A8h; Semaphore
0x14008e5e7  xor     edx, edx; Count
0x14008e5e9  mov     r8d, 7FFFFFFFh; Limit
0x14008e5ef  call    cs:__imp_KeInitializeSemaphore
0x14008e5f6  nop     dword ptr [rax+rax+00h]
0x14008e5fb  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x14008e603  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], 0
0x14008e60c  mov     [rsp+0A8h+ObjectAttributes.Attributes], 200h
0x14008e614  mov     [rsp+0A8h+ObjectAttributes.ObjectName], 0
0x14008e61d  xorps   xmm0, xmm0
0x14008e620  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14008e629  xor     ecx, ecx; ActiveProcessors
0x14008e62b  call    cs:__imp_KeQueryActiveProcessorCount
0x14008e632  nop     dword ptr [rax+rax+00h]
0x14008e637  mov     esi, eax
0x14008e639  lea     r14, WPP_GLOBAL_Control
0x14008e640  mov     rcx, cs:WPP_GLOBAL_Control
0x14008e647  cmp     rcx, r14
0x14008e64a  jz      short loc_14008E675
0x14008e64c  mov     edx, [rcx+2Ch]
0x14008e64f  test    dl, 2
0x14008e652  jz      short loc_14008E675
0x14008e654  mov     edx, 0Bh
0x14008e659  lea     ebx, [rdx+5]
0x14008e65c  mov     dword ptr [rsp+0A8h+ClientId], ebx
0x14008e660  mov     r9d, eax
0x14008e663  lea     r8, WPP_e14b9b336f94348117623c9565965302_Traceguids
0x14008e66a  mov     rcx, [rcx+18h]
0x14008e66e  call    WPP_SF_dd
0x14008e673  jmp     short loc_14008E67A
0x14008e675  mov     ebx, 10h
0x14008e67a  cmp     esi, ebx
0x14008e67c  cmova   esi, ebx
0x14008e67f  xor     edi, edi
0x14008e681  mov     [rsp+0A8h+var_64], edi
0x14008e685  cmp     edi, esi
0x14008e687  jnb     loc_14008E7A4
0x14008e68d  mov     rcx, [rsp+0A8h+Handle]; Handle
0x14008e692  test    rcx, rcx
0x14008e695  jz      short loc_14008E6AC
0x14008e697  call    cs:__imp_ZwClose
0x14008e69e  nop     dword ptr [rax+rax+00h]
0x14008e6a3  mov     [rsp+0A8h+Handle], 0
0x14008e6ac  mov     r15d, edi
0x14008e6af  mov     [rsp+0A8h+StartContext], r15; StartContext
0x14008e6b4  lea     rax, MpAsyncScanWorkerThread
0x14008e6bb  mov     [rsp+0A8h+StartRoutine], rax; StartRoutine
0x14008e6c0  mov     [rsp+0A8h+ClientId], 0; ClientId
0x14008e6c9  xor     r9d, r9d; ProcessHandle
0x14008e6cc  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x14008e6d1  xor     edx, edx; DesiredAccess
0x14008e6d3  lea     rcx, [rsp+0A8h+Handle]; ThreadHandle
0x14008e6d8  call    cs:__imp_PsCreateSystemThread
0x14008e6df  nop     dword ptr [rax+rax+00h]
0x14008e6e4  mov     ebx, eax
0x14008e6e6  mov     [rsp+0A8h+var_68], eax
0x14008e6ea  test    eax, eax
0x14008e6ec  jns     short loc_14008E73B
0x14008e6ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14008e6f5  cmp     rcx, r14
0x14008e6f8  jz      loc_14008E80E
0x14008e6fe  mov     ecx, [rcx+2Ch]
0x14008e701  test    cl, 1
0x14008e704  jz      loc_14008E80E
0x14008e70a  mov     edx, 0Ch
0x14008e70f  mov     dword ptr [rsp+0A8h+ClientId], eax
0x14008e713  lfence
0x14008e716  mov     r9, gs:188h
0x14008e71f  lea     r8, WPP_e14b9b336f94348117623c9565965302_Traceguids
0x14008e726  mov     rcx, cs:WPP_GLOBAL_Control
0x14008e72d  mov     rcx, [rcx+18h]
0x14008e731  call    WPP_SF_qD
0x14008e736  jmp     loc_14008E80E
0x14008e73b  lfence
0x14008e73e  mov     rcx, cs:MpAsyncScanData
0x14008e745  add     rcx, 10h
0x14008e749  lea     rcx, [rcx+rdi*8]
0x14008e74d  mov     [rsp+0A8h+ClientId], rcx; PVOID *
0x14008e752  xor     r9d, r9d; int
0x14008e755  mov     r8, cs:__imp_PsThreadType
0x14008e75c  mov     r8, [r8]; int
0x14008e75f  mov     edx, 1FFFFFh; int
0x14008e764  mov     rcx, [rsp+0A8h+Handle]; int
0x14008e769  call    MpReferenceObjectByHandle
0x14008e76e  mov     ebx, eax
0x14008e770  mov     [rsp+0A8h+var_68], eax
0x14008e774  test    eax, eax
0x14008e776  jns     short loc_14008E79D
0x14008e778  mov     rax, cs:WPP_GLOBAL_Control
0x14008e77f  cmp     rax, r14
0x14008e782  jz      loc_14008E80E
0x14008e788  mov     eax, [rax+2Ch]
0x14008e78b  test    al, 1
0x14008e78d  jz      short loc_14008E80E
0x14008e78f  mov     edx, 0Dh
0x14008e794  mov     dword ptr [rsp+0A8h+ClientId], ebx
0x14008e798  jmp     loc_14008E713
0x14008e79d  inc     edi
0x14008e79f  jmp     loc_14008E681
0x14008e7a4  mov     rax, cs:MpAsyncScanData
0x14008e7ab  lea     rdx, [rax+110h]
0x14008e7b2  mov     [rsp+0A8h+var_58], rdx
0x14008e7b7  add     rax, 510h
0x14008e7bd  mov     [rsp+0A8h+var_60], 0
0x14008e7c5  mov     dword ptr [rax], 0
0x14008e7cb  mov     ecx, [rax+4]
0x14008e7ce  and     ecx, 1Fh
0x14008e7d1  mov     r8d, 1000h
0x14008e7d7  or      ecx, r8d
0x14008e7da  mov     [rax+4], ecx
0x14008e7dd  mov     [rax+8], rdx
0x14008e7e1  mov     [rax+4], r8d
0x14008e7e5  or      rax, 1
0x14008e7e9  lea     rcx, [rdx+400h]
0x14008e7f0  test    rdx, rdx
0x14008e7f3  jz      short loc_14008E808
0x14008e7f5  cmp     rdx, rcx
0x14008e7f8  jnb     short loc_14008E808
0x14008e7fa  mov     [rdx], rax
0x14008e7fd  add     rdx, 8
0x14008e801  mov     [rsp+0A8h+var_58], rdx
0x14008e806  jmp     short loc_14008E7F5
0x14008e808  xor     ebx, ebx
0x14008e80a  mov     [rsp+0A8h+var_68], ebx
0x14008e80e  mov     rcx, [rsp+0A8h+Handle]; Handle
0x14008e813  test    rcx, rcx
0x14008e816  jz      short loc_14008E824
0x14008e818  call    cs:__imp_ZwClose
0x14008e81f  nop     dword ptr [rax+rax+00h]
0x14008e824  test    ebx, ebx
0x14008e826  jns     short loc_14008E82D
0x14008e828  call    MpAsyncScanShutdown
0x14008e82d  mov     eax, ebx
0x14008e82f  mov     rcx, [rsp+0A8h+var_18]
0x14008e837  xor     rcx, rsp; StackCookie
0x14008e83a  call    __security_check_cookie
0x14008e83f  lea     r11, [rsp+0A8h+var_8]
0x14008e847  mov     rbx, [r11+10h]
0x14008e84b  mov     rsi, [r11+18h]
0x14008e84f  mov     rdi, [r11+20h]
0x14008e853  mov     r14, [r11+28h]
0x14008e857  mov     rsp, r11
0x14008e85a  pop     r15
0x14008e85c  retn
0x140094a8e  push    rbp
0x140094a90  sub     rsp, 40h
0x140094a94  mov     rbp, rdx
0x140094a97  mov     rcx, [rbp+58h]; Handle
0x140094a9b  test    rcx, rcx
0x140094a9e  jz      short loc_140094AAD
0x140094aa0  call    cs:__imp_ZwClose
0x140094aa7  nop     dword ptr [rax+rax+00h]
0x140094aac  nop
0x140094aad  cmp     dword ptr [rbp+40h], 0
0x140094ab1  jge     short loc_140094AB9
0x140094ab3  call    MpAsyncScanShutdown
0x140094ab8  nop
0x140094ab9  add     rsp, 40h
0x140094abd  pop     rbp
0x140094abe  retn
```
