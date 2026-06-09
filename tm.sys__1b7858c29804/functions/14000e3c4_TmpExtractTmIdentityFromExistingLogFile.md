# TmpExtractTmIdentityFromExistingLogFile

- ea: `0x14000e3c4`
- end: `0x14000e62d`
- name: `TmpExtractTmIdentityFromExistingLogFile`
- size: `617`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400175d0`

## callees

- `0x140001a3c`
- `0x14000e3c4`

## import_xrefs

- `CLFS!ClfsTerminateReadLog` at `0x14000e5f2`
- `CLFS!ClfsTerminateReadLog` at `0x140021bbf`
- `CLFS!ClfsTerminateReadLog` at `0x14000e5f2`
- `CLFS!ClfsTerminateReadLog` at `0x140021bbf`
- `CLFS!ClfsCreateLogFile` at `0x14000e4d0`
- `CLFS!ClfsCreateLogFile` at `0x14000e4d0`
- `CLFS!ClfsCreateMarshallingArea` at `0x14000e543`
- `CLFS!ClfsCreateMarshallingArea` at `0x14000e543`
- `CLFS!ClfsReadRestartArea` at `0x14000e584`
- `CLFS!ClfsReadRestartArea` at `0x14000e584`
- `CLFS!ClfsDeleteMarshallingArea` at `0x14000e60b`
- `CLFS!ClfsDeleteMarshallingArea` at `0x140021bd8`
- `CLFS!ClfsDeleteMarshallingArea` at `0x14000e60b`
- `CLFS!ClfsDeleteMarshallingArea` at `0x140021bd8`
- `CLFS!ClfsCloseLogFileObject` at `0x14000e61c`
- `CLFS!ClfsCloseLogFileObject` at `0x140021be9`
- `CLFS!ClfsCloseLogFileObject` at `0x14000e61c`
- `CLFS!ClfsCloseLogFileObject` at `0x140021be9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e4ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e4ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e4ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e4ff`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x14000e40a`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x14000e40a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000e452`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000e452`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000e46d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000e484`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000e46d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000e484`

## pseudocode

```c
__int64 __fastcall TmpExtractTmIdentityFromExistingLogFile(PCUNICODE_STRING Source, _OWORD *a2)
{
  NTSTATUS restarted; // ebx
  __int64 v6; // r8
  FILE_OBJECT *pplfoLog; // [rsp+68h] [rbp-50h] BYREF
  PVOID ppvReadContext; // [rsp+70h] [rbp-48h] BYREF
  PVOID ppvRestartBuffer; // [rsp+78h] [rbp-40h] BYREF
  CLFS_LSN plsn; // [rsp+80h] [rbp-38h] BYREF
  UNICODE_STRING DestinationString; // [rsp+88h] [rbp-30h] BYREF
  ULONG pcbRestartBuffer; // [rsp+D0h] [rbp+18h] BYREF
  PVOID ppvMarshalContext; // [rsp+D8h] [rbp+20h] BYREF

  *(_QWORD *)&DestinationString.Length = 0;
  pplfoLog = 0;
  ppvMarshalContext = 0;
  ppvRestartBuffer = 0;
  pcbRestartBuffer = 0;
  ppvReadContext = 0;
  plsn.ullOffset = 0;
  DestinationString.Buffer = (wchar_t *)ExAllocatePoolWithQuotaTag((POOL_TYPE)9, 0x1000u, 0x6E4C6D54u);
  if ( !DestinationString.Buffer )
    return 3221225626LL;
  *(_DWORD *)&DestinationString.Length = 0x10000000;
  RtlCopyUnicodeString(&DestinationString, 0);
  RtlAppendUnicodeStringToString(&DestinationString, &TmpLogPrefix);
  RtlAppendUnicodeStringToString(&DestinationString, Source);
  restarted = ClfsCreateLogFile(&pplfoLog, &DestinationString, 0x80000000, 3u, 0, 1u, 8u, 0, 0, 0, 0);
  if ( restarted >= 0 )
  {
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    DestinationString.Buffer = 0;
    restarted = ClfsCreateMarshallingArea(pplfoLog, PagedPool, 0, 0, 0x10000u, 0x14u, 1u, &ppvMarshalContext);
    if ( restarted >= 0 )
    {
      restarted = ClfsReadRestartArea(ppvMarshalContext, &ppvRestartBuffer, &pcbRestartBuffer, &plsn, &ppvReadContext);
      if ( restarted == 1075445772 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 42, v6, 1075445772);
        restarted = -1072103376;
      }
      if ( restarted >= 0 && ppvRestartBuffer )
        *a2 = *(_OWORD *)((char *)ppvRestartBuffer + 12);
    }
    if ( ppvReadContext )
      ClfsTerminateReadLog(ppvReadContext);
    if ( ppvMarshalContext )
      ClfsDeleteMarshallingArea(ppvMarshalContext);
    ClfsCloseLogFileObject(pplfoLog);
  }
  else
  {
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  }
  return (unsigned int)restarted;
}

```

## disassembly

```asm
0x14000e3c4  mov     rax, rsp
0x14000e3c7  mov     [rax+8], rbx
0x14000e3cb  push    rsi
0x14000e3cc  push    rdi
0x14000e3cd  push    r14
0x14000e3cf  sub     rsp, 0A0h
0x14000e3d6  mov     rdi, rdx
0x14000e3d9  mov     rbx, rcx
0x14000e3dc  xorps   xmm0, xmm0
0x14000e3df  movups  xmmword ptr [rax-30h], xmm0
0x14000e3e3  xor     esi, esi
0x14000e3e5  mov     [rax-50h], rsi
0x14000e3e9  mov     [rax+20h], rsi
0x14000e3ed  mov     [rax-40h], rsi
0x14000e3f1  mov     [rax+18h], esi
0x14000e3f4  mov     [rax-48h], rsi
0x14000e3f8  mov     [rax-38h], rsi
0x14000e3fc  mov     edx, 1000h; NumberOfBytes
0x14000e401  lea     ecx, [rsi+9]; PoolType
0x14000e404  mov     r8d, 6E4C6D54h; Tag
0x14000e40a  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x14000e411  nop     dword ptr [rax+rax+00h]
0x14000e416  mov     [rsp+0B8h+DestinationString.Buffer], rax
0x14000e41e  test    rax, rax
0x14000e421  jnz     short loc_14000E43D
0x14000e423  mov     eax, 0C000009Ah
0x14000e428  mov     rbx, [rsp+0B8h+arg_0]
0x14000e430  add     rsp, 0A0h
0x14000e437  pop     r14
0x14000e439  pop     rdi
0x14000e43a  pop     rsi
0x14000e43b  retn
0x14000e43d  mov     dword ptr [rsp+0B8h+DestinationString.Length], 10000000h
0x14000e448  xor     edx, edx; SourceString
0x14000e44a  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x14000e452  call    cs:__imp_RtlCopyUnicodeString
0x14000e459  nop     dword ptr [rax+rax+00h]
0x14000e45e  lea     rdx, TmpLogPrefix; Source
0x14000e465  lea     rcx, [rsp+0B8h+DestinationString]; Destination
0x14000e46d  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000e474  nop     dword ptr [rax+rax+00h]
0x14000e479  mov     rdx, rbx; Source
0x14000e47c  lea     rcx, [rsp+0B8h+DestinationString]; Destination
0x14000e484  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000e48b  nop     dword ptr [rax+rax+00h]
0x14000e490  mov     [rsp+0B8h+cbContext], esi; cbContext
0x14000e494  mov     [rsp+0B8h+pvContext], rsi; pvContext
0x14000e499  mov     [rsp+0B8h+fLogOptionFlag], esi; fLogOptionFlag
0x14000e49d  mov     [rsp+0B8h+fFlagsAndAttributes], esi; fFlagsAndAttributes
0x14000e4a1  mov     [rsp+0B8h+fCreateOptions], 8; fCreateOptions
0x14000e4a9  mov     r14d, 1
0x14000e4af  mov     [rsp+0B8h+fCreateDisposition], r14d; fCreateDisposition
0x14000e4b4  mov     [rsp+0B8h+psdLogFile], rsi; psdLogFile
0x14000e4b9  lea     r9d, [r14+2]; dwShareMode
0x14000e4bd  mov     r8d, 80000000h; fDesiredAccess
0x14000e4c3  lea     rdx, [rsp+0B8h+DestinationString]; puszLogFileName
0x14000e4cb  lea     rcx, [rsp+0B8h+pplfoLog]; pplfoLog
0x14000e4d0  call    cs:__imp_ClfsCreateLogFile
0x14000e4d7  nop     dword ptr [rax+rax+00h]
0x14000e4dc  mov     ebx, eax
0x14000e4de  xor     edx, edx; Tag
0x14000e4e0  mov     rcx, [rsp+0B8h+DestinationString.Buffer]; P
0x14000e4e8  test    eax, eax
0x14000e4ea  jns     short loc_14000E4FF
0x14000e4ec  call    cs:__imp_ExFreePoolWithTag
0x14000e4f3  nop     dword ptr [rax+rax+00h]
0x14000e4f8  mov     eax, ebx
0x14000e4fa  jmp     loc_14000E428
0x14000e4ff  call    cs:__imp_ExFreePoolWithTag
0x14000e506  nop     dword ptr [rax+rax+00h]
0x14000e50b  mov     [rsp+0B8h+DestinationString.Buffer], rsi
0x14000e513  lea     rax, [rsp+0B8h+ppvMarshalContext]
0x14000e51b  mov     qword ptr [rsp+0B8h+fFlagsAndAttributes], rax; ppvMarshalContext
0x14000e520  mov     [rsp+0B8h+fCreateOptions], r14d; cMaxReadBuffers
0x14000e525  mov     [rsp+0B8h+fCreateDisposition], 14h; cMaxWriteBuffers
0x14000e52d  mov     dword ptr [rsp+0B8h+psdLogFile], 10000h; cbMarshallingBuffer
0x14000e535  xor     r9d, r9d; pfnFreeBuffer
0x14000e538  xor     r8d, r8d; pfnAllocBuffer
0x14000e53b  mov     edx, r14d; ePoolType
0x14000e53e  mov     rcx, [rsp+0B8h+pplfoLog]; plfoLog
0x14000e543  call    cs:__imp_ClfsCreateMarshallingArea
0x14000e54a  nop     dword ptr [rax+rax+00h]
0x14000e54f  mov     ebx, eax
0x14000e551  mov     [rsp+0B8h+var_58], eax
0x14000e555  test    eax, eax
0x14000e557  js      loc_14000E5E8
0x14000e55d  lea     rax, [rsp+0B8h+ppvReadContext]
0x14000e562  mov     [rsp+0B8h+psdLogFile], rax; ppvReadContext
0x14000e567  lea     r9, [rsp+0B8h+plsn]; plsn
0x14000e56f  lea     r8, [rsp+0B8h+pcbRestartBuffer]; pcbRestartBuffer
0x14000e577  lea     rdx, [rsp+0B8h+ppvRestartBuffer]; ppvRestartBuffer
0x14000e57c  mov     rcx, [rsp+0B8h+ppvMarshalContext]; pvMarshalContext
0x14000e584  call    cs:__imp_ClfsReadRestartArea
0x14000e58b  nop     dword ptr [rax+rax+00h]
0x14000e590  mov     ebx, eax
0x14000e592  mov     [rsp+0B8h+var_58], eax
0x14000e596  mov     r9d, 401A000Ch
0x14000e59c  cmp     eax, r9d
0x14000e59f  jnz     short loc_14000E5D2
0x14000e5a1  lea     rax, WPP_GLOBAL_Control
0x14000e5a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e5af  cmp     rcx, rax
0x14000e5b2  jz      short loc_14000E5C9
0x14000e5b4  mov     eax, [rcx+2Ch]
0x14000e5b7  test    al, 8
0x14000e5b9  jz      short loc_14000E5C9
0x14000e5bb  mov     edx, 2Ah ; '*'
0x14000e5c0  mov     rcx, [rcx+18h]
0x14000e5c4  call    WPP_SF_d
0x14000e5c9  mov     ebx, 0C0190030h
0x14000e5ce  mov     [rsp+0B8h+var_58], ebx
0x14000e5d2  test    ebx, ebx
0x14000e5d4  js      short loc_14000E5E8
0x14000e5d6  mov     rax, [rsp+0B8h+ppvRestartBuffer]
0x14000e5db  test    rax, rax
0x14000e5de  jz      short loc_14000E5E8
0x14000e5e0  movups  xmm0, xmmword ptr [rax+0Ch]
0x14000e5e4  movdqu  xmmword ptr [rdi], xmm0
0x14000e5e8  mov     rcx, [rsp+0B8h+ppvReadContext]; pvCursorContext
0x14000e5ed  test    rcx, rcx
0x14000e5f0  jz      short loc_14000E5FE
0x14000e5f2  call    cs:__imp_ClfsTerminateReadLog
0x14000e5f9  nop     dword ptr [rax+rax+00h]
0x14000e5fe  mov     rcx, [rsp+0B8h+ppvMarshalContext]; pvMarshalContext
0x14000e606  test    rcx, rcx
0x14000e609  jz      short loc_14000E617
0x14000e60b  call    cs:__imp_ClfsDeleteMarshallingArea
0x14000e612  nop     dword ptr [rax+rax+00h]
0x14000e617  mov     rcx, [rsp+0B8h+pplfoLog]; plfoLog
0x14000e61c  call    cs:__imp_ClfsCloseLogFileObject
0x14000e623  nop     dword ptr [rax+rax+00h]
0x14000e628  jmp     loc_14000E4F8
0x140021bad  push    rbp
0x140021baf  sub     rsp, 60h
0x140021bb3  mov     rbp, rdx
0x140021bb6  mov     rcx, [rbp+70h]; pvCursorContext
0x140021bba  test    rcx, rcx
0x140021bbd  jz      short loc_140021BCC
0x140021bbf  call    cs:__imp_ClfsTerminateReadLog
0x140021bc6  nop     dword ptr [rax+rax+00h]
0x140021bcb  nop
0x140021bcc  mov     rcx, [rbp+0D8h]; pvMarshalContext
0x140021bd3  test    rcx, rcx
0x140021bd6  jz      short loc_140021BE5
0x140021bd8  call    cs:__imp_ClfsDeleteMarshallingArea
0x140021bdf  nop     dword ptr [rax+rax+00h]
0x140021be4  nop
0x140021be5  mov     rcx, [rbp+68h]; plfoLog
0x140021be9  call    cs:__imp_ClfsCloseLogFileObject
0x140021bf0  nop     dword ptr [rax+rax+00h]
0x140021bf5  nop
0x140021bf6  add     rsp, 60h
0x140021bfa  pop     rbp
0x140021bfb  retn
```
