# SegLibInitialize

- ea: `0x1401b9884`
- end: `0x1401b9991`
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
- `0x1401b97a4`
- `0x1401b9884`
- `0x1401bbe10`

## import_xrefs

- `ntoskrnl!RtlFindExportedRoutineByName` at `0x1401b993c`
- `ntoskrnl!RtlFindExportedRoutineByName` at `0x1401b993c`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1401b98e6`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1401b98e6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b98d5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b9906`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b98d5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b9906`
- `NETIO!MdpCreatePool` at `0x1401b9970`
- `NETIO!MdpCreatePool` at `0x1401b9970`

## string_xrefs

- `0x1401b9912`: `NetioCopyNetBufferListQosInformation`
- `0x1401b9932`: `NetioCopyNetBufferListQoSInformation`

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
0x1401b9884  push    rbx
0x1401b9886  sub     rsp, 40h
0x1401b988a  cmp     cs:NetioCopyNetBufferListQosInformationFnPtr, 0
0x1401b9892  lea     rax, g_BatchLibContext
0x1401b9899  xorps   xmm0, xmm0
0x1401b989c  mov     cs:qword_140224C88, rax
0x1401b98a3  xorps   xmm1, xmm1
0x1401b98a6  mov     cs:g_SegLibContext, 0
0x1401b98b1  movups  xmmword ptr [rsp+48h+var_18.Length], xmm0
0x1401b98b6  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm1
0x1401b98bb  movdqu  cs:xmmword_140224C90, xmm0
0x1401b98c3  jnz     loc_1401B9956
0x1401b98c9  lea     rdx, SourceString; "MmGetSystemRoutineAddressEx"
0x1401b98d0  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1401b98d5  call    cs:__imp_RtlInitUnicodeString
0x1401b98dc  nop     dword ptr [rax+rax+00h]
0x1401b98e1  lea     rcx, [rsp+48h+DestinationString]; SystemRoutineName
0x1401b98e6  call    cs:__imp_MmGetSystemRoutineAddress
0x1401b98ed  nop     dword ptr [rax+rax+00h]
0x1401b98f2  mov     rbx, rax
0x1401b98f5  test    rax, rax
0x1401b98f8  jz      short loc_1401B9928
0x1401b98fa  lea     rdx, aNetioSys_0; "netio.sys"
0x1401b9901  lea     rcx, [rsp+48h+var_18]; DestinationString
0x1401b9906  call    cs:__imp_RtlInitUnicodeString
0x1401b990d  nop     dword ptr [rax+rax+00h]
0x1401b9912  lea     rdx, aNetiocopynetbu; "NetioCopyNetBufferListQosInformation"
0x1401b9919  mov     rax, rbx
0x1401b991c  lea     rcx, [rsp+48h+var_18]
0x1401b9921  call    _guard_dispatch_icall
0x1401b9926  jmp     short loc_1401B9948
0x1401b9928  call    SegLibGetModuleBase
0x1401b992d  test    rax, rax
0x1401b9930  jz      short loc_1401B9956
0x1401b9932  lea     rdx, aNetiocopynetbu_0; "NetioCopyNetBufferListQoSInformation"
0x1401b9939  mov     rcx, rax
0x1401b993c  call    cs:__imp_RtlFindExportedRoutineByName
0x1401b9943  nop     dword ptr [rax+rax+00h]
0x1401b9948  mov     rcx, rax
0x1401b994b  xor     eax, eax
0x1401b994d  lock cmpxchg cs:NetioCopyNetBufferListQosInformationFnPtr, rcx
0x1401b9956  call    Feature_TCPIP_2025_Wave2_SegLibHeap__private_IsEnabledDeviceUsageNoInline
0x1401b995b  test    eax, eax
0x1401b995d  jz      short loc_1401B9983
0x1401b995f  mov     ecx, 708h
0x1401b9964  mov     byte ptr cs:xmmword_140224C90+8, 1
0x1401b996b  mov     edx, 6C6F734Ch
0x1401b9970  call    cs:__imp_MdpCreatePool
0x1401b9977  nop     dword ptr [rax+rax+00h]
0x1401b997c  mov     qword ptr cs:xmmword_140224C90, rax
0x1401b9983  mov     byte ptr cs:g_SegLibContext, 1
0x1401b998a  add     rsp, 40h
0x1401b998e  pop     rbx
0x1401b998f  retn
```
