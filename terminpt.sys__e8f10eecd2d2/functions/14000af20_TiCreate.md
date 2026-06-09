# TiCreate

- ea: `0x14000af20`
- end: `0x14000b2c1`
- name: `TiCreate`
- size: `929`
- prototype: `__int64 __fastcall(__int64, IRP *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x14000173c`
- `0x1400017e8`
- `0x140002c7c`
- `0x140002e58`
- `0x1400099f0`
- `0x14000acac`
- `0x14000af20`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000b272`
- `ntoskrnl!IofCompleteRequest` at `0x14000b272`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x14000b05e`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x14000b05e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000b18f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000b18f`
- `ntoskrnl!ObfReferenceObject` at `0x14000b20b`
- `ntoskrnl!ObfReferenceObject` at `0x14000b20b`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14000b0e7`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14000b0e7`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14000b151`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14000b151`

## pseudocode

```c
__int64 __fastcall TiCreate(__int64 a1, IRP *a2, int a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r12
  PFILE_OBJECT FileObject; // rax
  PWSTR Buffer; // rsi
  USHORT Length; // di
  int v10; // edx
  int v11; // ebx
  int v12; // r8d
  __int16 v13; // di
  __int16 v14; // di
  WCHAR *v15; // rsi
  int v16; // r9d
  int v17; // r8d
  struct _DEVICE_OBJECT *DeferredContext; // rax
  PSECURITY_DESCRIPTOR *p_SecurityDescriptor; // r14
  int v20; // edx
  int v21; // r8d
  const UNICODE_STRING *i; // rdi
  PWSTR *p_Buffer; // rsi
  int v24; // r9d
  int v25; // edx
  int v26; // r8d
  UNICODE_STRING String; // [rsp+40h] [rbp-20h] BYREF
  UNICODE_STRING String2; // [rsp+50h] [rbp-10h] BYREF
  char v29; // [rsp+A0h] [rbp+40h] BYREF
  ULONG Value; // [rsp+B0h] [rbp+50h] BYREF

  Value = 0;
  String = 0;
  v29 = 0;
  String2 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      a3,
      10,
      (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
  if ( *(_DWORD *)(a1 + 72) != 56 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        a3,
        11,
        (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
    return PtCreate(a1, a2);
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  Buffer = FileObject->FileName.Buffer;
  Length = FileObject->FileName.Length;
  v11 = IsCallerTermsrvService(&v29, (int)a2, a3);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      v12,
      12,
      (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
  if ( v11 < 0 )
    goto LABEL_46;
  if ( !v29 )
  {
    v11 = -1073741790;
    goto LABEL_46;
  }
  v13 = Length >> 1;
  if ( !v13 || *Buffer != 92 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v16 = 13;
      goto LABEL_44;
    }
LABEL_45:
    v11 = -1073741811;
    goto LABEL_46;
  }
  v14 = v13 - 1;
  v15 = Buffer + 1;
  String.MaximumLength = 2 * v14;
  String.Length = 2 * v14;
  String.Buffer = v15;
  v11 = RtlUnicodeStringToInteger(&String, 0xAu, &Value);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      v12,
      14,
      (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
  if ( v11 < 0 )
    goto LABEL_46;
  if ( !v14 )
  {
LABEL_20:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v16 = 15;
LABEL_44:
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v12,
        v16,
        (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
      goto LABEL_45;
    }
    goto LABEL_45;
  }
  while ( *v15 != 92 )
  {
    ++v15;
    if ( !--v14 )
      goto LABEL_20;
  }
  String2.Buffer = v15;
  String2.Length = 2 * v14;
  String2.MaximumLength = 2 * v14;
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
  DeferredContext = (struct _DEVICE_OBJECT *)WPP_MAIN_CB.Dpc.DeferredContext;
  if ( WPP_MAIN_CB.Dpc.DeferredContext == &WPP_MAIN_CB.Dpc.DeferredContext )
  {
LABEL_25:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        (unsigned int)&WPP_MAIN_CB.Dpc.DeferredContext,
        v17,
        16,
        (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
    v11 = -1073741667;
    goto LABEL_28;
  }
  while ( 1 )
  {
    p_SecurityDescriptor = &DeferredContext[-1].SecurityDescriptor;
    if ( LODWORD(DeferredContext[-1].SecurityDescriptor) == Value )
      break;
    DeferredContext = *(struct _DEVICE_OBJECT **)&DeferredContext->Type;
    if ( DeferredContext == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Dpc.DeferredContext )
      goto LABEL_25;
  }
  TiLockSession(&DeferredContext[-1].SecurityDescriptor);
  for ( i = (const UNICODE_STRING *)p_SecurityDescriptor[10]; ; i = *(const UNICODE_STRING **)&i->Length )
  {
    if ( i == (const UNICODE_STRING *)(p_SecurityDescriptor + 10) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_36:
        v11 = -1073741667;
        goto LABEL_37;
      }
      v24 = 18;
LABEL_35:
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        v20,
        v21,
        v24,
        (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
      goto LABEL_36;
    }
    p_Buffer = &i[-13].Buffer;
    if ( !RtlCompareUnicodeString(i - 2, &String2, 1u) )
      break;
  }
  if ( *((_BYTE *)p_Buffer + 216) == 2 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_36;
    v24 = 17;
    goto LABEL_35;
  }
  CurrentStackLocation->FileObject->FsContext = 0;
  CurrentStackLocation->FileObject->FsContext2 = p_Buffer;
  ObfReferenceObject(*p_Buffer);
LABEL_37:
  TiUnlockSession(p_SecurityDescriptor);
LABEL_28:
  KeReleaseGuardedMutex((PKGUARDED_MUTEX)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
LABEL_46:
  a2->IoStatus.Status = v11;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      v25,
      v26,
      19,
      (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000af20  mov     [rsp-38h+arg_8], rbx
0x14000af25  push    rbp
0x14000af26  push    rsi
0x14000af27  push    rdi
0x14000af28  push    r12
0x14000af2a  push    r13
0x14000af2c  push    r14
0x14000af2e  push    r15
0x14000af30  mov     rbp, rsp
0x14000af33  sub     rsp, 60h
0x14000af37  xor     eax, eax
0x14000af39  xorps   xmm0, xmm0
0x14000af3c  xorps   xmm1, xmm1
0x14000af3f  mov     [rbp+Value], eax
0x14000af42  movups  xmmword ptr [rbp+String.Length], xmm0
0x14000af46  mov     [rbp+arg_0], al
0x14000af49  mov     r13, rdx
0x14000af4c  movups  xmmword ptr [rbp+String2.Length], xmm1
0x14000af50  mov     rbx, rcx
0x14000af53  lea     r15, WPP_RECORDER_INITIALIZED
0x14000af5a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000af61  lea     r14, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x14000af68  jz      short loc_14000AF83
0x14000af6a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000af71  lea     r9d, [rax+0Ah]
0x14000af75  mov     [rsp+60h+var_40], r14
0x14000af7a  mov     rcx, [rcx+40h]
0x14000af7e  call    WPP_RECORDER_SF_s
0x14000af83  cmp     dword ptr [rbx+48h], 38h ; '8'
0x14000af87  jz      short loc_14000AFBD
0x14000af89  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000af90  jz      short loc_14000AFAD
0x14000af92  mov     rcx, cs:WPP_GLOBAL_Control
0x14000af99  mov     r9d, 0Bh
0x14000af9f  mov     [rsp+60h+var_40], r14
0x14000afa4  mov     rcx, [rcx+40h]
0x14000afa8  call    WPP_RECORDER_SF_s
0x14000afad  mov     rdx, r13
0x14000afb0  mov     rcx, rbx
0x14000afb3  call    PtCreate
0x14000afb8  jmp     loc_14000B2A8
0x14000afbd  mov     r12, [r13+0B8h]
0x14000afc4  lea     rcx, [rbp+arg_0]
0x14000afc8  mov     rax, [r12+30h]
0x14000afcd  mov     rsi, [rax+60h]
0x14000afd1  movzx   edi, word ptr [rax+58h]
0x14000afd5  call    IsCallerTermsrvService
0x14000afda  mov     ebx, eax
0x14000afdc  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000afe3  jz      short loc_14000B004
0x14000afe5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000afec  mov     r9d, 0Ch
0x14000aff2  mov     [rsp+60h+var_30], eax
0x14000aff6  mov     [rsp+60h+var_40], r14
0x14000affb  mov     rcx, [rcx+40h]
0x14000afff  call    WPP_RECORDER_SF_sD
0x14000b004  xor     eax, eax
0x14000b006  test    ebx, ebx
0x14000b008  js      loc_14000B261
0x14000b00e  cmp     [rbp+arg_0], al
0x14000b011  jnz     short loc_14000B01D
0x14000b013  mov     ebx, 0C0000022h
0x14000b018  jmp     loc_14000B261
0x14000b01d  shr     di, 1
0x14000b020  cmp     di, 1
0x14000b024  jb      loc_14000B238
0x14000b02a  mov     eax, 5Ch ; '\'
0x14000b02f  cmp     ax, [rsi]
0x14000b032  jnz     loc_14000B238
0x14000b038  dec     di
0x14000b03b  lea     r8, [rbp+Value]; Value
0x14000b03f  movzx   eax, di
0x14000b042  lea     rcx, [rbp+String]; String
0x14000b046  add     ax, ax
0x14000b049  add     rsi, 2
0x14000b04d  mov     edx, 0Ah; Base
0x14000b052  mov     [rbp+String.MaximumLength], ax
0x14000b056  mov     [rbp+String.Length], ax
0x14000b05a  mov     [rbp+String.Buffer], rsi
0x14000b05e  call    cs:__imp_RtlUnicodeStringToInteger
0x14000b065  nop     dword ptr [rax+rax+00h]
0x14000b06a  mov     ebx, eax
0x14000b06c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000b073  jz      short loc_14000B094
0x14000b075  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b07c  mov     r9d, 0Eh
0x14000b082  mov     [rsp+60h+var_30], eax
0x14000b086  mov     [rsp+60h+var_40], r14
0x14000b08b  mov     rcx, [rcx+40h]
0x14000b08f  call    WPP_RECORDER_SF_sD
0x14000b094  test    ebx, ebx
0x14000b096  js      loc_14000B261
0x14000b09c  test    di, di
0x14000b09f  jz      short loc_14000B0B9
0x14000b0a1  mov     ecx, 5Ch ; '\'
0x14000b0a6  cmp     cx, [rsi]
0x14000b0a9  jz      short loc_14000B0D1
0x14000b0ab  add     rsi, 2
0x14000b0af  mov     eax, 0FFFFh
0x14000b0b4  add     di, ax
0x14000b0b7  jnz     short loc_14000B0A6
0x14000b0b9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000b0c0  jz      loc_14000B25C
0x14000b0c6  mov     r9d, 0Fh
0x14000b0cc  jmp     loc_14000B247
0x14000b0d1  add     di, di
0x14000b0d4  mov     [rbp+String2.Buffer], rsi
0x14000b0d8  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; Mutex
0x14000b0df  mov     [rbp+String2.Length], di
0x14000b0e3  mov     [rbp+String2.MaximumLength], di
0x14000b0e7  call    cs:__imp_KeAcquireGuardedMutex
0x14000b0ee  nop     dword ptr [rax+rax+00h]
0x14000b0f3  mov     rax, cs:WPP_MAIN_CB.Dpc.DeferredContext
0x14000b0fa  lea     rdx, WPP_MAIN_CB.Dpc.DeferredContext
0x14000b101  cmp     rax, rdx
0x14000b104  jz      short loc_14000B121
0x14000b106  mov     ecx, [rbp+Value]
0x14000b109  lea     r14, [rax-40h]
0x14000b10d  cmp     [r14], ecx
0x14000b110  jz      short loc_14000B169
0x14000b112  mov     rax, [rax]
0x14000b115  cmp     rax, rdx
0x14000b118  jnz     short loc_14000B109
0x14000b11a  lea     r14, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x14000b121  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000b128  jz      short loc_14000B145
0x14000b12a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b131  mov     r9d, 10h
0x14000b137  mov     [rsp+60h+var_40], r14
0x14000b13c  mov     rcx, [rcx+40h]
0x14000b140  call    WPP_RECORDER_SF_s
0x14000b145  mov     ebx, 0C000009Dh
0x14000b14a  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; Mutex
0x14000b151  call    cs:__imp_KeReleaseGuardedMutex
0x14000b158  nop     dword ptr [rax+rax+00h]
0x14000b15d  lea     r14, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x14000b164  jmp     loc_14000B261
0x14000b169  mov     rcx, r14
0x14000b16c  call    TiLockSession
0x14000b171  lea     r15, [r14+50h]
0x14000b175  mov     rdi, [r15]
0x14000b178  jmp     short loc_14000B1A4
0x14000b17a  lea     rsi, [rdi-0C8h]
0x14000b181  mov     r8b, 1; CaseInSensitive
0x14000b184  lea     rcx, [rsi+0A8h]; String1
0x14000b18b  lea     rdx, [rbp+String2]; String2
0x14000b18f  call    cs:__imp_RtlCompareUnicodeString
0x14000b196  nop     dword ptr [rax+rax+00h]
0x14000b19b  xor     ecx, ecx
0x14000b19d  test    eax, eax
0x14000b19f  jz      short loc_14000B1ED
0x14000b1a1  mov     rdi, [rdi]
0x14000b1a4  cmp     rdi, r15
0x14000b1a7  jnz     short loc_14000B17A
0x14000b1a9  lea     r15, WPP_RECORDER_INITIALIZED
0x14000b1b0  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000b1b7  jz      short loc_14000B1DB
0x14000b1b9  mov     r9d, 12h
0x14000b1bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b1c6  lea     rax, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x14000b1cd  mov     [rsp+60h+var_40], rax
0x14000b1d2  mov     rcx, [rcx+40h]
0x14000b1d6  call    WPP_RECORDER_SF_s
0x14000b1db  mov     ebx, 0C000009Dh
0x14000b1e0  mov     rcx, r14
0x14000b1e3  call    TiUnlockSession
0x14000b1e8  jmp     loc_14000B14A
0x14000b1ed  cmp     byte ptr [rsi+0D8h], 2
0x14000b1f4  jz      short loc_14000B220
0x14000b1f6  mov     rax, [r12+30h]
0x14000b1fb  mov     [rax+18h], rcx
0x14000b1ff  mov     rax, [r12+30h]
0x14000b204  mov     [rax+20h], rsi
0x14000b208  mov     rcx, [rsi]; Object
0x14000b20b  call    cs:__imp_ObfReferenceObject
0x14000b212  nop     dword ptr [rax+rax+00h]
0x14000b217  lea     r15, WPP_RECORDER_INITIALIZED
0x14000b21e  jmp     short loc_14000B1E0
0x14000b220  lea     r15, WPP_RECORDER_INITIALIZED
0x14000b227  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000b22e  jz      short loc_14000B1DB
0x14000b230  mov     r9d, 11h
0x14000b236  jmp     short loc_14000B1BF
0x14000b238  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000b23f  jz      short loc_14000B25C
0x14000b241  mov     r9d, 0Dh
0x14000b247  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b24e  mov     [rsp+60h+var_40], r14
0x14000b253  mov     rcx, [rcx+40h]
0x14000b257  call    WPP_RECORDER_SF_s
0x14000b25c  mov     ebx, 0C000000Dh
0x14000b261  xor     edx, edx; PriorityBoost
0x14000b263  mov     [r13+30h], ebx
0x14000b267  mov     rcx, r13; Irp
0x14000b26a  mov     qword ptr [r13+38h], 0
0x14000b272  call    cs:__imp_IofCompleteRequest
0x14000b279  nop     dword ptr [rax+rax+00h]
0x14000b27e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000b285  jz      short loc_14000B2A6
0x14000b287  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b28e  mov     r9d, 13h
0x14000b294  mov     [rsp+60h+var_30], ebx
0x14000b298  mov     [rsp+60h+var_40], r14
0x14000b29d  mov     rcx, [rcx+40h]
0x14000b2a1  call    WPP_RECORDER_SF_sD
0x14000b2a6  mov     eax, ebx
0x14000b2a8  mov     rbx, [rsp+60h+arg_8]
0x14000b2b0  add     rsp, 60h
0x14000b2b4  pop     r15
0x14000b2b6  pop     r14
0x14000b2b8  pop     r13
0x14000b2ba  pop     r12
0x14000b2bc  pop     rdi
0x14000b2bd  pop     rsi
0x14000b2be  pop     rbp
0x14000b2bf  retn
```
