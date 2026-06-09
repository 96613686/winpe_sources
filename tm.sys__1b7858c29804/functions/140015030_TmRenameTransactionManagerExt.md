# TmRenameTransactionManagerExt

- ea: `0x140015030`
- end: `0x14001530e`
- name: `TmRenameTransactionManagerExt`
- size: `734`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING LogFileName, LPGUID ExistingTransactionManagerGuid)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140017e20`

## callees

- `0x140015030`

## import_xrefs

- `CLFS!CLFS_LSN_NULL` at `0x140015069`
- `CLFS!ClfsWriteRestartArea` at `0x1400152b7`
- `CLFS!ClfsWriteRestartArea` at `0x1400152b7`
- `CLFS!ClfsTerminateReadLog` at `0x1400152d3`
- `CLFS!ClfsTerminateReadLog` at `0x1400224ce`
- `CLFS!ClfsTerminateReadLog` at `0x1400152d3`
- `CLFS!ClfsTerminateReadLog` at `0x1400224ce`
- `CLFS!ClfsCreateLogFile` at `0x140015160`
- `CLFS!ClfsCreateLogFile` at `0x140015160`
- `CLFS!ClfsCreateMarshallingArea` at `0x1400151d7`
- `CLFS!ClfsCreateMarshallingArea` at `0x1400151d7`
- `CLFS!ClfsReadRestartArea` at `0x140015218`
- `CLFS!ClfsReadRestartArea` at `0x140015218`
- `CLFS!ClfsDeleteMarshallingArea` at `0x1400152ec`
- `CLFS!ClfsDeleteMarshallingArea` at `0x1400224e7`
- `CLFS!ClfsDeleteMarshallingArea` at `0x1400152ec`
- `CLFS!ClfsDeleteMarshallingArea` at `0x1400224e7`
- `CLFS!ClfsCloseLogFileObject` at `0x1400152fd`
- `CLFS!ClfsCloseLogFileObject` at `0x1400224f8`
- `CLFS!ClfsCloseLogFileObject` at `0x1400152fd`
- `CLFS!ClfsCloseLogFileObject` at `0x1400224f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001517c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001518f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001517c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001518f`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x1400150b9`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x1400150b9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400150e3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400150e3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400150fe`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140015115`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400150fe`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140015115`
- `ntoskrnl!ExUuidCreate` at `0x140015279`
- `ntoskrnl!ExUuidCreate` at `0x140015279`

## pseudocode

```c
NTSTATUS __stdcall TmRenameTransactionManagerExt(PUNICODE_STRING LogFileName, LPGUID ExistingTransactionManagerGuid)
{
  int Length; // edx
  SIZE_T v6; // rdx
  int restarted; // ebx
  __int64 v8; // rcx
  FILE_OBJECT *pplfoLog; // [rsp+68h] [rbp-50h] BYREF
  PVOID ppvRestartBuffer; // [rsp+70h] [rbp-48h] BYREF
  PVOID ppvReadContext; // [rsp+78h] [rbp-40h] BYREF
  CLFS_LSN plsn; // [rsp+80h] [rbp-38h] BYREF
  CLFS_LSN plsnNext; // [rsp+88h] [rbp-30h] BYREF
  UNICODE_STRING DestinationString; // [rsp+90h] [rbp-28h] BYREF
  ULONG pcbRestartBuffer; // [rsp+C0h] [rbp+8h] BYREF
  ULONG pcbWritten; // [rsp+D0h] [rbp+18h] BYREF
  PVOID ppvMarshalContext; // [rsp+D8h] [rbp+20h] BYREF

  DestinationString = 0;
  pplfoLog = 0;
  ppvMarshalContext = 0;
  ppvRestartBuffer = 0;
  pcbRestartBuffer = 0;
  ppvReadContext = 0;
  plsn.ullOffset = 0;
  pcbWritten = 0;
  plsnNext = CLFS_LSN_NULL;
  Length = LogFileName->Length;
  if ( Length + (unsigned int)TmpLogPrefix.Length > 0xFFFF )
    return -2147483643;
  v6 = (unsigned __int16)(TmpLogPrefix.Length + Length);
  DestinationString.MaximumLength = v6;
  DestinationString.Buffer = (wchar_t *)ExAllocatePoolWithQuotaTag((POOL_TYPE)9, v6, 0x6E4C6D54u);
  if ( !DestinationString.Buffer )
    return -1073741670;
  RtlCopyUnicodeString(&DestinationString, 0);
  RtlAppendUnicodeStringToString(&DestinationString, &TmpLogPrefix);
  RtlAppendUnicodeStringToString(&DestinationString, LogFileName);
  restarted = ClfsCreateLogFile(&pplfoLog, &DestinationString, 0xC0000000, 1u, 0, 1u, 8u, 0, 0, 0, 0);
  if ( restarted >= 0 )
  {
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    DestinationString.Buffer = 0;
    restarted = ClfsCreateMarshallingArea(pplfoLog, PagedPool, 0, 0, 0x10000u, 0x14u, 1u, &ppvMarshalContext);
    if ( restarted >= 0 )
    {
      restarted = ClfsReadRestartArea(ppvMarshalContext, &ppvRestartBuffer, &pcbRestartBuffer, &plsn, &ppvReadContext);
      if ( restarted == 1075445772 )
        restarted = -1072103376;
      if ( restarted >= 0 && ppvRestartBuffer )
      {
        v8 = *(_QWORD *)((char *)ppvRestartBuffer + 12) - *(_QWORD *)&ExistingTransactionManagerGuid->Data1;
        if ( !v8 )
          v8 = *(_QWORD *)((char *)ppvRestartBuffer + 20) - *(_QWORD *)ExistingTransactionManagerGuid->Data4;
        if ( v8 )
        {
          restarted = -1072103332;
        }
        else
        {
          ExUuidCreate((UUID *)((char *)ppvRestartBuffer + 12));
          restarted = ClfsWriteRestartArea(ppvMarshalContext, ppvRestartBuffer, 0x20u, 0, 0, &pcbWritten, &plsnNext);
        }
      }
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
  return restarted;
}

```

## disassembly

```asm
0x140015030  mov     r11, rsp
0x140015033  push    rbx
0x140015034  push    rsi
0x140015035  push    rdi
0x140015036  sub     rsp, 0A0h
0x14001503d  mov     rdi, rdx
0x140015040  mov     rbx, rcx
0x140015043  xorps   xmm0, xmm0
0x140015046  movups  xmmword ptr [r11-28h], xmm0
0x14001504b  xor     esi, esi
0x14001504d  mov     [r11-50h], rsi
0x140015051  mov     [r11+20h], rsi
0x140015055  mov     [r11-48h], rsi
0x140015059  mov     [r11+8], esi
0x14001505d  mov     [r11-40h], rsi
0x140015061  mov     [r11-38h], rsi
0x140015065  mov     [r11+18h], esi
0x140015069  mov     rax, cs:__imp_CLFS_LSN_NULL
0x140015070  mov     r8, [rax]
0x140015073  mov     [r11-30h], r8
0x140015077  movzx   edx, word ptr [rcx]
0x14001507a  movzx   r8d, cs:TmpLogPrefix.Length
0x140015082  lea     ecx, [rdx+r8]
0x140015086  cmp     ecx, 0FFFFh
0x14001508c  jbe     short loc_14001509F
0x14001508e  mov     eax, 80000005h
0x140015093  add     rsp, 0A0h
0x14001509a  pop     rdi
0x14001509b  pop     rsi
0x14001509c  pop     rbx
0x14001509d  retn
0x14001509f  add     dx, r8w
0x1400150a3  movzx   edx, dx; NumberOfBytes
0x1400150a6  mov     [rsp+0B8h+DestinationString.MaximumLength], dx
0x1400150ae  mov     ecx, 9; PoolType
0x1400150b3  mov     r8d, 6E4C6D54h; Tag
0x1400150b9  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x1400150c0  nop     dword ptr [rax+rax+00h]
0x1400150c5  mov     [rsp+0B8h+DestinationString.Buffer], rax
0x1400150cd  test    rax, rax
0x1400150d0  jnz     short loc_1400150D9
0x1400150d2  mov     eax, 0C000009Ah
0x1400150d7  jmp     short loc_140015093
0x1400150d9  xor     edx, edx; SourceString
0x1400150db  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x1400150e3  call    cs:__imp_RtlCopyUnicodeString
0x1400150ea  nop     dword ptr [rax+rax+00h]
0x1400150ef  lea     rdx, TmpLogPrefix; Source
0x1400150f6  lea     rcx, [rsp+0B8h+DestinationString]; Destination
0x1400150fe  call    cs:__imp_RtlAppendUnicodeStringToString
0x140015105  nop     dword ptr [rax+rax+00h]
0x14001510a  mov     rdx, rbx; Source
0x14001510d  lea     rcx, [rsp+0B8h+DestinationString]; Destination
0x140015115  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001511c  nop     dword ptr [rax+rax+00h]
0x140015121  mov     [rsp+0B8h+cbContext], esi; cbContext
0x140015125  mov     [rsp+0B8h+pvContext], rsi; pvContext
0x14001512a  mov     [rsp+0B8h+fLogOptionFlag], esi; fLogOptionFlag
0x14001512e  mov     [rsp+0B8h+fFlagsAndAttributes], esi; fFlagsAndAttributes
0x140015132  mov     [rsp+0B8h+fCreateOptions], 8; fCreateOptions
0x14001513a  mov     [rsp+0B8h+fCreateDisposition], 1; fCreateDisposition
0x140015142  mov     [rsp+0B8h+psdLogFile], rsi; psdLogFile
0x140015147  mov     r9d, 1; dwShareMode
0x14001514d  mov     r8d, 0C0000000h; fDesiredAccess
0x140015153  lea     rdx, [rsp+0B8h+DestinationString]; puszLogFileName
0x14001515b  lea     rcx, [rsp+0B8h+pplfoLog]; pplfoLog
0x140015160  call    cs:__imp_ClfsCreateLogFile
0x140015167  nop     dword ptr [rax+rax+00h]
0x14001516c  mov     ebx, eax
0x14001516e  xor     edx, edx; Tag
0x140015170  mov     rcx, [rsp+0B8h+DestinationString.Buffer]; P
0x140015178  test    eax, eax
0x14001517a  jns     short loc_14001518F
0x14001517c  call    cs:__imp_ExFreePoolWithTag
0x140015183  nop     dword ptr [rax+rax+00h]
0x140015188  mov     eax, ebx
0x14001518a  jmp     loc_140015093
0x14001518f  call    cs:__imp_ExFreePoolWithTag
0x140015196  nop     dword ptr [rax+rax+00h]
0x14001519b  mov     [rsp+0B8h+DestinationString.Buffer], rsi
0x1400151a3  lea     rax, [rsp+0B8h+ppvMarshalContext]
0x1400151ab  mov     qword ptr [rsp+0B8h+fFlagsAndAttributes], rax; ppvMarshalContext
0x1400151b0  mov     [rsp+0B8h+fCreateOptions], 1; cMaxReadBuffers
0x1400151b8  mov     [rsp+0B8h+fCreateDisposition], 14h; cMaxWriteBuffers
0x1400151c0  mov     dword ptr [rsp+0B8h+psdLogFile], 10000h; cbMarshallingBuffer
0x1400151c8  xor     r9d, r9d; pfnFreeBuffer
0x1400151cb  xor     r8d, r8d; pfnAllocBuffer
0x1400151ce  lea     edx, [r9+1]; ePoolType
0x1400151d2  mov     rcx, [rsp+0B8h+pplfoLog]; plfoLog
0x1400151d7  call    cs:__imp_ClfsCreateMarshallingArea
0x1400151de  nop     dword ptr [rax+rax+00h]
0x1400151e3  mov     ebx, eax
0x1400151e5  mov     [rsp+0B8h+var_58], eax
0x1400151e9  test    eax, eax
0x1400151eb  js      loc_1400152C9
0x1400151f1  lea     rax, [rsp+0B8h+ppvReadContext]
0x1400151f6  mov     [rsp+0B8h+psdLogFile], rax; ppvReadContext
0x1400151fb  lea     r9, [rsp+0B8h+plsn]; plsn
0x140015203  lea     r8, [rsp+0B8h+pcbRestartBuffer]; pcbRestartBuffer
0x14001520b  lea     rdx, [rsp+0B8h+ppvRestartBuffer]; ppvRestartBuffer
0x140015210  mov     rcx, [rsp+0B8h+ppvMarshalContext]; pvMarshalContext
0x140015218  call    cs:__imp_ClfsReadRestartArea
0x14001521f  nop     dword ptr [rax+rax+00h]
0x140015224  mov     ebx, eax
0x140015226  mov     [rsp+0B8h+var_58], eax
0x14001522a  mov     eax, 0C0190030h
0x14001522f  cmp     ebx, 401A000Ch
0x140015235  cmovz   ebx, eax
0x140015238  mov     [rsp+0B8h+var_58], ebx
0x14001523c  test    ebx, ebx
0x14001523e  js      loc_1400152C9
0x140015244  mov     rdx, [rsp+0B8h+ppvRestartBuffer]
0x140015249  test    rdx, rdx
0x14001524c  jz      short loc_1400152C9
0x14001524e  mov     rcx, [rdx+0Ch]
0x140015252  mov     rax, [rdi]
0x140015255  sub     rcx, rax
0x140015258  jnz     short loc_140015265
0x14001525a  mov     rcx, [rdx+14h]
0x14001525e  mov     rax, [rdi+8]
0x140015262  sub     rcx, rax
0x140015265  test    rcx, rcx
0x140015268  jz      short loc_140015275
0x14001526a  mov     ebx, 0C019005Ch
0x14001526f  mov     [rsp+0B8h+var_58], ebx
0x140015273  jmp     short loc_1400152C9
0x140015275  lea     rcx, [rdx+0Ch]; Uuid
0x140015279  call    cs:__imp_ExUuidCreate
0x140015280  nop     dword ptr [rax+rax+00h]
0x140015285  lea     rax, [rsp+0B8h+plsnNext]
0x14001528d  mov     qword ptr [rsp+0B8h+fCreateOptions], rax; plsnNext
0x140015292  lea     rax, [rsp+0B8h+pcbWritten]
0x14001529a  mov     qword ptr [rsp+0B8h+fCreateDisposition], rax; pcbWritten
0x14001529f  mov     dword ptr [rsp+0B8h+psdLogFile], esi; fFlags
0x1400152a3  xor     r9d, r9d; plsnBase
0x1400152a6  lea     r8d, [r9+20h]; cbRestartBuffer
0x1400152aa  mov     rdx, [rsp+0B8h+ppvRestartBuffer]; pvRestartBuffer
0x1400152af  mov     rcx, [rsp+0B8h+ppvMarshalContext]; pvMarshalContext
0x1400152b7  call    cs:__imp_ClfsWriteRestartArea
0x1400152be  nop     dword ptr [rax+rax+00h]
0x1400152c3  mov     ebx, eax
0x1400152c5  mov     [rsp+0B8h+var_58], eax
0x1400152c9  mov     rcx, [rsp+0B8h+ppvReadContext]; pvCursorContext
0x1400152ce  test    rcx, rcx
0x1400152d1  jz      short loc_1400152DF
0x1400152d3  call    cs:__imp_ClfsTerminateReadLog
0x1400152da  nop     dword ptr [rax+rax+00h]
0x1400152df  mov     rcx, [rsp+0B8h+ppvMarshalContext]; pvMarshalContext
0x1400152e7  test    rcx, rcx
0x1400152ea  jz      short loc_1400152F8
0x1400152ec  call    cs:__imp_ClfsDeleteMarshallingArea
0x1400152f3  nop     dword ptr [rax+rax+00h]
0x1400152f8  mov     rcx, [rsp+0B8h+pplfoLog]; plfoLog
0x1400152fd  call    cs:__imp_ClfsCloseLogFileObject
0x140015304  nop     dword ptr [rax+rax+00h]
0x140015309  jmp     loc_140015188
0x1400224bc  push    rbp
0x1400224be  sub     rsp, 60h
0x1400224c2  mov     rbp, rdx
0x1400224c5  mov     rcx, [rbp+78h]; pvCursorContext
0x1400224c9  test    rcx, rcx
0x1400224cc  jz      short loc_1400224DB
0x1400224ce  call    cs:__imp_ClfsTerminateReadLog
0x1400224d5  nop     dword ptr [rax+rax+00h]
0x1400224da  nop
0x1400224db  mov     rcx, [rbp+0D8h]; pvMarshalContext
0x1400224e2  test    rcx, rcx
0x1400224e5  jz      short loc_1400224F4
0x1400224e7  call    cs:__imp_ClfsDeleteMarshallingArea
0x1400224ee  nop     dword ptr [rax+rax+00h]
0x1400224f3  nop
0x1400224f4  mov     rcx, [rbp+68h]; plfoLog
0x1400224f8  call    cs:__imp_ClfsCloseLogFileObject
0x1400224ff  nop     dword ptr [rax+rax+00h]
0x140022504  nop
0x140022505  add     rsp, 60h
0x140022509  pop     rbp
0x14002250a  retn
```
