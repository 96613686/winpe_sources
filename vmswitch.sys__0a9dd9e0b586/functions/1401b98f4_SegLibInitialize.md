# SegLibInitialize

- ea: `0x1401b98f4`
- end: `0x1401b9a01`
- name: `SegLibInitialize`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400a2918`

## callees

- `0x1400a568c`
- `0x1401b9814`
- `0x1401b98f4`
- `0x1401bbe80`

## import_xrefs

- `ntoskrnl!RtlFindExportedRoutineByName` at `0x1401b99ac`
- `ntoskrnl!RtlFindExportedRoutineByName` at `0x1401b99ac`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1401b9956`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1401b9956`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b9945`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b9976`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b9945`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b9976`
- `NETIO!MdpCreatePool` at `0x1401b99e0`
- `NETIO!MdpCreatePool` at `0x1401b99e0`

## string_xrefs

- `0x1401b99a2`: `NetioCopyNetBufferListQoSInformation`
- `0x1401b9982`: `NetioCopyNetBufferListQosInformation`

## pseudocode

```c
__int64 __fastcall SegLibInitialize(signed __int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 (__fastcall *SystemRoutineAddress)(struct _UNICODE_STRING *, const char *); // rbx
  __int64 v7; // r8
  __int64 v8; // r9
  signed __int64 ExportedRoutineByName; // rax
  __int64 ModuleBase; // rax
  __int64 result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING v13; // [rsp+30h] [rbp-18h] BYREF

  qword_140224C88 = (__int64)&g_BatchLibContext;
  g_SegLibContext = 0;
  v13 = 0;
  DestinationString = 0;
  xmmword_140224C90 = 0;
  if ( !NetioCopyNetBufferListQosInformationFnPtr )
  {
    RtlInitUnicodeString(&DestinationString, L"MmGetSystemRoutineAddressEx");
    SystemRoutineAddress = (__int64 (__fastcall *)(struct _UNICODE_STRING *, const char *))MmGetSystemRoutineAddress(&DestinationString);
    if ( SystemRoutineAddress )
    {
      RtlInitUnicodeString(&v13, L"netio.sys");
      ExportedRoutineByName = SystemRoutineAddress(&v13, "NetioCopyNetBufferListQosInformation");
    }
    else
    {
      ModuleBase = SegLibGetModuleBase(v5, v4, v7, v8);
      if ( !ModuleBase )
        goto LABEL_7;
      ExportedRoutineByName = RtlFindExportedRoutineByName(ModuleBase, "NetioCopyNetBufferListQoSInformation");
    }
    a1 = ExportedRoutineByName;
    _InterlockedCompareExchange64(&NetioCopyNetBufferListQosInformationFnPtr, ExportedRoutineByName, 0);
  }
LABEL_7:
  result = Feature_TCPIP_2025_Wave2_SegLibHeap__private_IsEnabledDeviceUsageNoInline(a1, a2, a3, a4);
  if ( (_DWORD)result )
  {
    BYTE8(xmmword_140224C90) = 1;
    result = MdpCreatePool(1800, 1819243340);
    *(_QWORD *)&xmmword_140224C90 = result;
  }
  LOBYTE(g_SegLibContext) = 1;
  return result;
}

```

## disassembly

```asm
0x1401b98f4  push    rbx
0x1401b98f6  sub     rsp, 40h
0x1401b98fa  cmp     cs:NetioCopyNetBufferListQosInformationFnPtr, 0
0x1401b9902  lea     rax, g_BatchLibContext
0x1401b9909  xorps   xmm0, xmm0
0x1401b990c  mov     cs:qword_140224C88, rax
0x1401b9913  xorps   xmm1, xmm1
0x1401b9916  mov     cs:g_SegLibContext, 0
0x1401b9921  movups  xmmword ptr [rsp+48h+var_18.Length], xmm0
0x1401b9926  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm1
0x1401b992b  movdqu  cs:xmmword_140224C90, xmm0
0x1401b9933  jnz     loc_1401B99C6
0x1401b9939  lea     rdx, SourceString; "MmGetSystemRoutineAddressEx"
0x1401b9940  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1401b9945  call    cs:__imp_RtlInitUnicodeString
0x1401b994c  nop     dword ptr [rax+rax+00h]
0x1401b9951  lea     rcx, [rsp+48h+DestinationString]; SystemRoutineName
0x1401b9956  call    cs:__imp_MmGetSystemRoutineAddress
0x1401b995d  nop     dword ptr [rax+rax+00h]
0x1401b9962  mov     rbx, rax
0x1401b9965  test    rax, rax
0x1401b9968  jz      short loc_1401B9998
0x1401b996a  lea     rdx, aNetioSys_0; "netio.sys"
0x1401b9971  lea     rcx, [rsp+48h+var_18]; DestinationString
0x1401b9976  call    cs:__imp_RtlInitUnicodeString
0x1401b997d  nop     dword ptr [rax+rax+00h]
0x1401b9982  lea     rdx, aNetiocopynetbu; "NetioCopyNetBufferListQosInformation"
0x1401b9989  mov     rax, rbx
0x1401b998c  lea     rcx, [rsp+48h+var_18]
0x1401b9991  call    _guard_dispatch_icall
0x1401b9996  jmp     short loc_1401B99B8
0x1401b9998  call    SegLibGetModuleBase
0x1401b999d  test    rax, rax
0x1401b99a0  jz      short loc_1401B99C6
0x1401b99a2  lea     rdx, aNetiocopynetbu_0; "NetioCopyNetBufferListQoSInformation"
0x1401b99a9  mov     rcx, rax
0x1401b99ac  call    cs:__imp_RtlFindExportedRoutineByName
0x1401b99b3  nop     dword ptr [rax+rax+00h]
0x1401b99b8  mov     rcx, rax
0x1401b99bb  xor     eax, eax
0x1401b99bd  lock cmpxchg cs:NetioCopyNetBufferListQosInformationFnPtr, rcx
0x1401b99c6  call    Feature_TCPIP_2025_Wave2_SegLibHeap__private_IsEnabledDeviceUsageNoInline
0x1401b99cb  test    eax, eax
0x1401b99cd  jz      short loc_1401B99F3
0x1401b99cf  mov     ecx, 708h
0x1401b99d4  mov     byte ptr cs:xmmword_140224C90+8, 1
0x1401b99db  mov     edx, 6C6F734Ch
0x1401b99e0  call    cs:__imp_MdpCreatePool
0x1401b99e7  nop     dword ptr [rax+rax+00h]
0x1401b99ec  mov     qword ptr cs:xmmword_140224C90, rax
0x1401b99f3  mov     byte ptr cs:g_SegLibContext, 1
0x1401b99fa  add     rsp, 40h
0x1401b99fe  pop     rbx
0x1401b99ff  retn
```
