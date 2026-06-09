# PfSvSuperfetchStart

- ea: `0x1800838e4`
- end: `0x180083aed`
- name: `PfSvSuperfetchStart`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006a020`

## callees

- `0x18003252c`
- `0x180039490`
- `0x18003c814`
- `0x18003cbe4`
- `0x18003cffc`
- `0x18006df54`
- `0x18008219c`
- `0x1800838e4`
- `0x18008c9c4`
- `0x18008ceec`
- `0x18008e818`
- `0x180090b2c`

## import_xrefs

- `msvcrt!qsort` at `0x1800839b8`
- `msvcrt!qsort` at `0x1800839b8`
- `ntdll!RtlInitUnicodeString` at `0x180083a21`
- `ntdll!RtlInitUnicodeString` at `0x180083a21`
- `ntdll!NtOpenEvent` at `0x180083a5d`
- `ntdll!NtOpenEvent` at `0x180083a5d`
- `ntdll!RtlNtStatusToDosError` at `0x180083a69`
- `ntdll!RtlNtStatusToDosError` at `0x180083a69`

## pseudocode

```c
ULONG __fastcall PfSvSuperfetchStart(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  unsigned int v5; // esi
  ULONG result; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // eax
  struct _RTL_CRITICAL_SECTION *v11; // r10
  __int64 v12; // rax
  __int64 v13; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF
  __int64 CurrentTime; // [rsp+90h] [rbp+28h] BYREF

  v4 = *(_QWORD *)&PfSvcGlobals;
  v5 = a2;
  *(_QWORD *)(a1 + 1968) = *(_QWORD *)&PfSvcGlobals;
  *(_OWORD *)&ObjectAttributes.ObjectName = 0;
  *(_QWORD *)(v4 + 4456) = a1;
  *(_QWORD *)(a1 + 1296) = L"ProcessorTime";
  *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
  result = PfClStart(a1, a2, a3, a4, 0, 0, 0, 0);
  if ( !result )
  {
    *(_QWORD *)(a1 + 2256) = a1;
    result = PfPrStart(a1 + 1176, a1);
    if ( !result
      && ((*(_BYTE *)(*(_QWORD *)&PfSvcGlobals + 244LL) & 1) != 0 || (result = PfSvLoadDefaultAgents(a1 + 1176, v5)) == 0) )
    {
      result = PfPrAgentsLoadFromRegistry(a1 + 1176);
      if ( !result )
      {
        if ( *(_DWORD *)(a1 + 1224) )
        {
          qsort(*(void **)(a1 + 1232), *(unsigned int *)(a1 + 1224), 0x50u, PfPrAgentOrderCompare);
          v8 = *(_QWORD *)(a1 + 1192);
          *(_DWORD *)(a1 + 1960) |= 8u;
          if ( v8 )
            PfCrCombine(*(_QWORD *)(v8 + 16));
          result = PfSvSuperfetchTracingControl(a1, 0);
          if ( !result && ((v5 & 4) != 0 || (result = PfSiStart(a1 + 2000, 1)) == 0) )
          {
            *(_QWORD *)(a1 + 8) = a1 + 2000;
            if ( (v5 & 1) != 0
              && (RtlInitUnicodeString(&DestinationString, L"\\KernelObjects\\SuperfetchParametersChanged"),
                  ObjectAttributes.Length = 48,
                  ObjectAttributes.ObjectName = &DestinationString,
                  ObjectAttributes.RootDirectory = 0,
                  ObjectAttributes.Attributes = 0,
                  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
                  v10 = NtOpenEvent((PHANDLE)(a1 + 2544), 0x120001u, &ObjectAttributes),
                  v10 < 0) )
            {
              return RtlNtStatusToDosError(v10);
            }
            else
            {
              *(_DWORD *)(a1 + 2504) = 300000;
              CurrentTime = PfsActionItemGetCurrentTime(v9);
              PfsActionItemQueueEx(v11 + 43, 3u, (unsigned __int64 *)&CurrentTime, 0);
              *(_DWORD *)(a1 + 2516) = 0;
              *(_DWORD *)(a1 + 2512) = PfsGetUnbiasedTickCount();
              v12 = *(_QWORD *)&PfSvcGlobals;
              *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 1696LL) = a1;
              *(_QWORD *)(v12 + 3704) = a1;
              if ( !(unsigned int)PfSvPowerNotifyRegister(v13, 0xFFFFFFFFLL, 0) )
                *(_DWORD *)(a1 + 2552) |= 1u;
              return 0;
            }
          }
        }
        else
        {
          return -536870384;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800838e4  push    rbp
0x1800838e6  push    rbx
0x1800838e7  push    rsi
0x1800838e8  push    rdi
0x1800838e9  mov     rbp, rsp
0x1800838ec  sub     rsp, 68h
0x1800838f0  xorps   xmm0, xmm0
0x1800838f3  xor     eax, eax
0x1800838f5  mov     rax, cs:PfSvcGlobals
0x1800838fc  mov     esi, edx
0x1800838fe  mov     [rcx+7B0h], rax
0x180083905  mov     rbx, rcx
0x180083908  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18008390c  mov     [rax+1168h], rcx
0x180083913  lea     rax, aProcessortime; "ProcessorTime"
0x18008391a  mov     [rcx+510h], rax
0x180083921  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180083925  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180083929  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18008392d  call    PfClStart
0x180083932  test    eax, eax
0x180083934  jnz     loc_180083AE4
0x18008393a  lea     rdi, [rbx+498h]
0x180083941  mov     [rbx+8D0h], rbx
0x180083948  mov     rcx, rdi
0x18008394b  mov     rdx, rbx
0x18008394e  call    PfPrStart
0x180083953  test    eax, eax
0x180083955  jnz     loc_180083AE4
0x18008395b  mov     rax, cs:PfSvcGlobals
0x180083962  test    byte ptr [rax+0F4h], 1
0x180083969  jnz     short loc_18008397D
0x18008396b  mov     edx, esi
0x18008396d  mov     rcx, rdi
0x180083970  call    PfSvLoadDefaultAgents
0x180083975  test    eax, eax
0x180083977  jnz     loc_180083AE4
0x18008397d  mov     rcx, rdi
0x180083980  call    PfPrAgentsLoadFromRegistry
0x180083985  test    eax, eax
0x180083987  jnz     loc_180083AE4
0x18008398d  mov     eax, [rbx+4C8h]
0x180083993  test    eax, eax
0x180083995  jnz     short loc_1800839A1
0x180083997  mov     eax, 0E0000210h
0x18008399c  jmp     loc_180083AE4
0x1800839a1  mov     rcx, [rbx+4D0h]; Base
0x1800839a8  lea     r9, PfPrAgentOrderCompare; CompareFunction
0x1800839af  mov     rdx, rax; NumOfElements
0x1800839b2  mov     r8d, 50h ; 'P'; SizeOfElements
0x1800839b8  call    cs:__imp_qsort
0x1800839be  mov     rcx, [rbx+4A8h]
0x1800839c5  or      dword ptr [rbx+7A8h], 8
0x1800839cc  test    rcx, rcx
0x1800839cf  jz      short loc_1800839DA
0x1800839d1  mov     rcx, [rcx+10h]
0x1800839d5  call    PfCrCombine
0x1800839da  xor     edx, edx
0x1800839dc  mov     rcx, rbx
0x1800839df  call    PfSvSuperfetchTracingControl
0x1800839e4  test    eax, eax
0x1800839e6  jnz     loc_180083AE4
0x1800839ec  lea     rdi, [rbx+7D0h]
0x1800839f3  test    sil, 4
0x1800839f7  jnz     short loc_180083A0C
0x1800839f9  lea     edx, [rax+1]
0x1800839fc  mov     rcx, rdi
0x1800839ff  call    PfSiStart
0x180083a04  test    eax, eax
0x180083a06  jnz     loc_180083AE4
0x180083a0c  mov     [rbx+8], rdi
0x180083a10  test    sil, 1
0x180083a14  jz      short loc_180083A71
0x180083a16  lea     rdx, aKernelobjectsS_0; "\\KernelObjects\\SuperfetchParametersCh"...
0x180083a1d  lea     rcx, [rbp+DestinationString]; DestinationString
0x180083a21  call    cs:__imp_RtlInitUnicodeString
0x180083a27  lea     rax, [rbp+DestinationString]
0x180083a2b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180083a32  xorps   xmm0, xmm0
0x180083a35  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180083a39  lea     rcx, [rbx+9F0h]; EventHandle
0x180083a40  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180083a48  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180083a4c  mov     [rbp+ObjectAttributes.Attributes], 0
0x180083a53  mov     edx, 120001h; DesiredAccess
0x180083a58  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180083a5d  call    cs:__imp_NtOpenEvent
0x180083a63  test    eax, eax
0x180083a65  jns     short loc_180083A71
0x180083a67  mov     ecx, eax; Status
0x180083a69  call    cs:__imp_RtlNtStatusToDosError
0x180083a6f  jmp     short loc_180083AE4
0x180083a71  mov     dword ptr [rbx+9C8h], 493E0h
0x180083a7b  mov     r10, cs:PfSvcGlobals
0x180083a82  call    PfsActionItemGetCurrentTime
0x180083a87  xor     r9d, r9d
0x180083a8a  mov     [rbp+arg_0], rax
0x180083a8e  lea     r8, [rbp+arg_0]
0x180083a92  lea     rcx, [r10+6B8h]; lpCriticalSection
0x180083a99  lea     edx, [r9+3]
0x180083a9d  call    PfsActionItemQueueEx
0x180083aa2  mov     dword ptr [rbx+9D4h], 0
0x180083aac  call    PfsGetUnbiasedTickCount
0x180083ab1  mov     [rbx+9D0h], eax
0x180083ab7  xor     r8d, r8d
0x180083aba  mov     rax, cs:PfSvcGlobals
0x180083ac1  or      edx, 0FFFFFFFFh
0x180083ac4  mov     [rax+6A0h], rbx
0x180083acb  mov     [rax+0E78h], rbx
0x180083ad2  call    PfSvPowerNotifyRegister
0x180083ad7  test    eax, eax
0x180083ad9  jnz     short loc_180083AE2
0x180083adb  or      dword ptr [rbx+9F8h], 1
0x180083ae2  xor     eax, eax
0x180083ae4  add     rsp, 68h
0x180083ae8  pop     rdi
0x180083ae9  pop     rsi
0x180083aea  pop     rbx
0x180083aeb  pop     rbp
0x180083aec  retn
```
