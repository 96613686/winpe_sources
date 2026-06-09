# WerpSubmitReport

- ea: `0x1400100f4`
- end: `0x1400106fd`
- name: `WerpSubmitReport`
- size: `1545`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x14000cc50`

## callees

- `0x140002750`
- `0x140002c40`
- `0x14000ce68`
- `0x14000cfa8`
- `0x14000d070`
- `0x14000d174`
- `0x14000f3e0`
- `0x14000fda8`
- `0x1400100f4`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14001021e`
- `ntoskrnl!DbgPrintEx` at `0x14001033f`
- `ntoskrnl!DbgPrintEx` at `0x14001038b`
- `ntoskrnl!DbgPrintEx` at `0x1400103cf`
- `ntoskrnl!DbgPrintEx` at `0x1400105a3`
- `ntoskrnl!DbgPrintEx` at `0x14001063b`
- `ntoskrnl!DbgPrintEx` at `0x14001021e`
- `ntoskrnl!DbgPrintEx` at `0x14001033f`
- `ntoskrnl!DbgPrintEx` at `0x14001038b`
- `ntoskrnl!DbgPrintEx` at `0x1400103cf`
- `ntoskrnl!DbgPrintEx` at `0x1400105a3`
- `ntoskrnl!DbgPrintEx` at `0x14001063b`
- `ntoskrnl!ZwAlpcSendWaitReceivePort` at `0x1400105ff`
- `ntoskrnl!ZwAlpcSendWaitReceivePort` at `0x1400105ff`
- `ntoskrnl!ZwAlpcConnectPort` at `0x140010466`
- `ntoskrnl!ZwAlpcConnectPort` at `0x140010466`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010668`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001067e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400106b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010668`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001067e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400106b1`
- `ntoskrnl!ZwClose` at `0x1400101f9`
- `ntoskrnl!ZwClose` at `0x140010694`
- `ntoskrnl!ZwClose` at `0x1400106c7`
- `ntoskrnl!ZwClose` at `0x1400101f9`
- `ntoskrnl!ZwClose` at `0x140010694`
- `ntoskrnl!ZwClose` at `0x1400106c7`
- `ntoskrnl!ZwQuerySystemInformation` at `0x140010365`
- `ntoskrnl!ZwQuerySystemInformation` at `0x140010365`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400102e4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400102e4`
- `ntoskrnl!ZwDeleteKey` at `0x1400101e8`
- `ntoskrnl!ZwDeleteKey` at `0x1400101e8`

## string_xrefs

- `0x1400102d9`: `\WindowsErrorReportingServicePort`
- `0x140010211`: `WERKERNELHOST: WerpGetRegistryKey failed for the busy key 0x%X\n`
- `0x14001052d`: `WERKERNELHOST: StringCchCopy failed for key with 0x%x\n`
- `0x140010595`: `WERKERNELHOST: StringCchCopy failed for id with 0x%x\n`
- `0x14001061c`: `WERKERNELHOST: Service returned failure, ReplyMsg->u.status 0x%X\n`

## pseudocode

```c
__int64 __fastcall WerpSubmitReport(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rdi
  _DWORD *Mem; // r14
  __int64 v5; // rdx
  __int64 v6; // rax
  _DWORD *v7; // r13
  signed int FullReportTime; // ebx
  int RegistryKey; // eax
  _WORD *v10; // rax
  __int64 v11; // r12
  __int64 v12; // r8
  _WORD *v13; // rax
  __int64 v14; // r15
  __int64 v15; // r8
  int started; // eax
  NTSTATUS v17; // eax
  const CHAR *v18; // r8
  char v19; // dl
  __int64 *v20; // rcx
  unsigned __int64 v21; // rcx
  _WORD *v22; // rdx
  unsigned __int64 v23; // r8
  __int64 v24; // rax
  _WORD *v25; // r9
  _WORD *v26; // rcx
  __int64 v27; // rax
  _WORD *v28; // rdx
  _WORD *v29; // r8
  _WORD *v30; // rcx
  int v31; // eax
  __int64 v32; // r9
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+28h] [rbp-D8h]
  int v36; // [rsp+30h] [rbp-D0h]
  int v37; // [rsp+38h] [rbp-C8h]
  int v38; // [rsp+40h] [rbp-C0h]
  int v39; // [rsp+48h] [rbp-B8h]
  HANDLE KeyHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 SystemInformation; // [rsp+68h] [rbp-98h] BYREF
  PVOID P; // [rsp+70h] [rbp-90h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-88h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h] BYREF
  __int64 v45; // [rsp+88h] [rbp-78h]
  __int64 v46; // [rsp+90h] [rbp-70h] BYREF
  __int64 v47; // [rsp+98h] [rbp-68h]
  _WORD *v48; // [rsp+A0h] [rbp-60h]
  _WORD *v49; // [rsp+A8h] [rbp-58h]
  __int64 *v50; // [rsp+B0h] [rbp-50h]
  _BYTE v51[48]; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E8h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v54[10]; // [rsp+100h] [rbp+0h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  Handle = 0;
  v46 = 0;
  P = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v44 = 0;
  KeyHandle = 0;
  DestinationString = 0;
  memset(v51, 0, 44);
  memset(v54, 0, 0x48u);
  SystemInformation = 0;
  if ( !a1 )
    return 3221225485LL;
  v3 = *(_QWORD *)(a1 + 16);
  if ( !v3 )
    return 3221225485LL;
  Mem = (_DWORD *)WerpAllocateMem(1400, v2);
  v6 = WerpAllocateMem(1400, v5);
  v7 = (_DWORD *)v6;
  if ( Mem && v6 )
  {
    if ( *(_DWORD *)(a1 + 4) == 2 )
    {
      FullReportTime = WerpSetLastFullReportTime(a1);
      if ( FullReportTime < 0 )
        goto LABEL_72;
    }
    RegistryKey = WerpGetRegistryKey(v3, L"Busy", 0x20000, &KeyHandle);
    if ( RegistryKey < 0 )
    {
      DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpGetRegistryKey failed for the busy key 0x%X\n", RegistryKey);
    }
    else
    {
      ZwDeleteKey(KeyHandle);
      ZwClose(KeyHandle);
      KeyHandle = 0;
    }
    v10 = (_WORD *)(a1 + 24);
    v48 = (_WORD *)(a1 + 24);
    if ( a1 == -24 )
    {
      FullReportTime = -1073741811;
      goto LABEL_72;
    }
    v11 = 16;
    v12 = 16;
    do
    {
      if ( !*v10 )
        break;
      ++v10;
      --v12;
    }
    while ( v12 );
    FullReportTime = v12 == 0 ? 0xC000000D : 0;
    v47 = (16 - v12) & -(__int64)(v12 != 0);
    if ( !v12 )
      goto LABEL_72;
    v13 = (_WORD *)(a1 + 56);
    v49 = (_WORD *)(a1 + 56);
    if ( a1 == -56 )
    {
      FullReportTime = -1073741811;
      goto LABEL_72;
    }
    v14 = 40;
    v15 = 40;
    do
    {
      if ( !*v13 )
        break;
      ++v13;
      --v15;
    }
    while ( v15 );
    FullReportTime = v15 == 0 ? 0xC000000D : 0;
    v45 = (40 - v15) & -(__int64)(v15 != 0);
    if ( !v15 )
      goto LABEL_72;
    RtlInitUnicodeString(&DestinationString, L"\\WindowsErrorReportingServicePort");
    memset(v54, 0, 0x48u);
    v54[2] = 1400;
    FullReportTime = WerpAllocateAndInitializeSid(&IdentifierAuthority, v34, v35, v36, v37, v38, v39, (__int64)&P);
    if ( FullReportTime < 0 )
      goto LABEL_72;
    started = WerStartSystemErrorHandler();
    if ( started < 0 )
    {
      DbgPrintEx(
        5u,
        1u,
        "WERKERNELHOST: WerStartSystemErrorHandler failed with 0x%x. Continuing submission.\n",
        started);
      FullReportTime = 258;
      goto LABEL_72;
    }
    v17 = ZwQuerySystemInformation(MaxSystemInfoClass|SystemObjectInformation, &SystemInformation, 8u, 0);
    FullReportTime = v17;
    if ( v17 >= 0 )
    {
      v17 = WerWaitForSystemErrorHandler((unsigned int)SystemInformation);
      FullReportTime = v17;
      if ( v17 >= 0 )
      {
        if ( v17 == 258 )
        {
          DbgPrintEx(5u, 1u, "WERKERNELHOST: WerWaitForSystemErrorHandler timed out\n");
          goto LABEL_72;
        }
        *(_OWORD *)&v51[32] = 0;
        *(_DWORD *)v51 = 48;
        *(_QWORD *)&v51[8] = 0;
        *(_DWORD *)&v51[24] = 512;
        *(_QWORD *)&v51[16] = 0;
        if ( HIDWORD(SystemInformation) == -1 )
        {
          v19 = 1;
        }
        else
        {
          v19 = 0;
          v44 = -10000LL * SHIDWORD(SystemInformation);
        }
        v20 = &v44;
        if ( v19 )
          v20 = 0;
        v50 = v20;
        v17 = ZwAlpcConnectPort(&Handle, &DestinationString, v51, v54, 0x20000, P, 0, 0, 0, 0, v20);
        FullReportTime = v17;
        if ( v17 >= 0 )
        {
          if ( v17 == 258 )
          {
            DbgPrintEx(5u, 1u, "WERKERNELHOST: ZwAlpcConnectPort timed out\n");
          }
          else
          {
            memset(Mem, 0, 0x578u);
            v21 = v47;
            v22 = Mem + 14;
            v23 = v45;
            *Mem = 91751760;
            Mem[10] = 1610612736;
            Mem[12] = *(_DWORD *)(a1 + 4) == 2;
            v24 = 15;
            if ( v21 <= 0xF )
              v24 = v21;
            v25 = v48;
            do
            {
              if ( !v24 )
                break;
              if ( !*v25 )
                break;
              *v22++ = *v25++;
              --v24;
              --v11;
            }
            while ( v11 );
            v26 = v22 - 1;
            FullReportTime = v11 == 0 ? 0x80000005 : 0;
            if ( v11 )
              v26 = v22;
            *v26 = 0;
            if ( v11 )
            {
              v27 = 39;
              v28 = Mem + 22;
              if ( v23 <= 0x27 )
                v27 = v23;
              v29 = v49;
              do
              {
                if ( !v27 )
                  break;
                if ( !*v29 )
                  break;
                *v28++ = *v29++;
                --v27;
                --v14;
              }
              while ( v14 );
              v30 = v28 - 1;
              FullReportTime = v14 == 0 ? 0x80000005 : 0;
              if ( v14 )
                v30 = v28;
              *v30 = 0;
              if ( v14 )
              {
                memset(v7 + 1, 0, 0x574u);
                *v7 = 91751760;
                v46 = 1400;
                v31 = ZwAlpcSendWaitReceivePort(Handle, 0, Mem, 0, v7, &v46, 0, v50);
                if ( v31 < 0 || v31 == 258 )
                {
                  DbgPrintEx(
                    5u,
                    1u,
                    "WERKERNELHOST: ZwAlpcSendWaitReceivePort failed, status 0x%X\n",
                    (unsigned int)v31);
                }
                else
                {
                  v32 = (unsigned int)v7[11];
                  if ( (int)v32 >= 0 )
                  {
                    FullReportTime = 0;
                    goto LABEL_72;
                  }
                  DbgPrintEx(5u, 1u, "WERKERNELHOST: Service returned failure, ReplyMsg->u.status 0x%X\n", v32);
                }
                FullReportTime = 258;
                goto LABEL_72;
              }
              DbgPrintEx(5u, 1u, "WERKERNELHOST: StringCchCopy failed for id with 0x%x\n", FullReportTime);
            }
            else
            {
              DbgPrintEx(
                5u,
                1u,
                "WERKERNELHOST: StringCchCopy failed for key with 0x%x\n",
                (unsigned int)FullReportTime);
            }
          }
LABEL_72:
          ExFreePoolWithTag(Mem, 0);
          goto LABEL_73;
        }
        v18 = "WERKERNELHOST: ZwAlpcConnectPort failed with 0x%x\n";
      }
      else
      {
        v18 = "WERKERNELHOST: WerWaitForSystemErrorHandler failed with 0x%x\n";
      }
    }
    else
    {
      v18 = "WERKERNELHOST: ZwQuerySysInfo(ErrorPortTimeouts) failed with 0x%x\n";
    }
    DbgPrintEx(5u, 1u, v18, (unsigned int)v17);
    goto LABEL_72;
  }
  FullReportTime = -1073741801;
  if ( Mem )
    goto LABEL_72;
LABEL_73:
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)FullReportTime;
}

```

## disassembly

```asm
0x1400100f4  push    rbp
0x1400100f6  push    rbx
0x1400100f7  push    rsi
0x1400100f8  push    rdi
0x1400100f9  push    r12
0x1400100fb  push    r13
0x1400100fd  push    r14
0x1400100ff  push    r15
0x140010101  lea     rbp, [rsp-68h]
0x140010106  sub     rsp, 168h
0x14001010d  mov     rax, cs:__security_cookie
0x140010114  xor     rax, rsp
0x140010117  mov     [rbp+0A0h+var_50], rax
0x14001011b  xor     r12d, r12d
0x14001011e  mov     word ptr [rbp+0A0h+IdentifierAuthority.Value+4], 500h
0x140010124  xorps   xmm0, xmm0
0x140010127  mov     [rsp+1A0h+Handle], r12
0x14001012c  mov     rsi, rcx
0x14001012f  mov     [rbp+0A0h+var_110], r12
0x140010133  movups  [rbp+0A0h+var_D8], xmm0
0x140010137  lea     r8d, [r12+48h]; Size
0x14001013c  mov     [rsp+1A0h+P], r12
0x140010141  xor     eax, eax
0x140010143  mov     dword ptr [rbp+0A0h+IdentifierAuthority.Value], r12d
0x140010147  xor     edx, edx; Val
0x140010149  mov     [rbp+0A0h+var_120], r12
0x14001014d  lea     rcx, [rbp+0A0h+var_A0]; void *
0x140010151  mov     [rsp+1A0h+KeyHandle], r12
0x140010156  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x14001015a  movups  [rbp+0A0h+var_E8], xmm0
0x14001015e  movups  [rbp+0A0h+var_D8+0Ch], xmm0
0x140010162  call    memset
0x140010167  mov     [rsp+1A0h+SystemInformation], r12
0x14001016c  test    rsi, rsi
0x14001016f  jz      loc_1400106D7
0x140010175  mov     rdi, [rsi+10h]
0x140010179  test    rdi, rdi
0x14001017c  jz      loc_1400106D7
0x140010182  mov     ebx, 578h
0x140010187  mov     ecx, ebx
0x140010189  call    WerpAllocateMem
0x14001018e  mov     ecx, ebx
0x140010190  mov     r14, rax
0x140010193  call    WerpAllocateMem
0x140010198  mov     r13, rax
0x14001019b  test    r14, r14
0x14001019e  jz      loc_140010659
0x1400101a4  test    rax, rax
0x1400101a7  jz      loc_140010659
0x1400101ad  cmp     dword ptr [rsi+4], 2
0x1400101b1  jnz     short loc_1400101C5
0x1400101b3  mov     rcx, rsi
0x1400101b6  call    WerpSetLastFullReportTime
0x1400101bb  mov     ebx, eax
0x1400101bd  test    eax, eax
0x1400101bf  js      loc_140010663
0x1400101c5  lea     r9, [rsp+1A0h+KeyHandle]
0x1400101ca  mov     r8d, 20000h
0x1400101d0  lea     rdx, aBusy; "Busy"
0x1400101d7  mov     rcx, rdi
0x1400101da  call    WerpGetRegistryKey
0x1400101df  test    eax, eax
0x1400101e1  js      short loc_14001020C
0x1400101e3  mov     rcx, [rsp+1A0h+KeyHandle]; KeyHandle
0x1400101e8  call    cs:__imp_ZwDeleteKey
0x1400101ef  nop     dword ptr [rax+rax+00h]
0x1400101f4  mov     rcx, [rsp+1A0h+KeyHandle]; Handle
0x1400101f9  call    cs:__imp_ZwClose
0x140010200  nop     dword ptr [rax+rax+00h]
0x140010205  mov     [rsp+1A0h+KeyHandle], r12
0x14001020a  jmp     short loc_14001022A
0x14001020c  mov     edx, 1; Level
0x140010211  lea     r8, aWerkernelhostW_55; "WERKERNELHOST: WerpGetRegistryKey faile"...
0x140010218  mov     r9d, eax
0x14001021b  lea     ecx, [rdx+4]; ComponentId
0x14001021e  call    cs:__imp_DbgPrintEx
0x140010225  nop     dword ptr [rax+rax+00h]
0x14001022a  lea     rax, [rsi+18h]
0x14001022e  mov     [rbp+0A0h+var_100], rax
0x140010232  test    rax, rax
0x140010235  jz      loc_140010652
0x14001023b  mov     r12d, 10h
0x140010241  xor     edi, edi
0x140010243  mov     r8d, r12d
0x140010246  cmp     [rax], di
0x140010249  jz      short loc_140010255
0x14001024b  add     rax, 2
0x14001024f  sub     r8, 1
0x140010253  jnz     short loc_140010246
0x140010255  mov     rax, r8
0x140010258  mov     edx, 0C000000Dh
0x14001025d  neg     rax
0x140010260  mov     rcx, r12
0x140010263  mov     rax, r8
0x140010266  sbb     ebx, ebx
0x140010268  sub     rcx, r8
0x14001026b  not     ebx
0x14001026d  and     ebx, edx
0x14001026f  neg     rax
0x140010272  sbb     rax, rax
0x140010275  and     rax, rcx
0x140010278  mov     [rbp+0A0h+var_108], rax
0x14001027c  test    r8, r8
0x14001027f  jz      loc_14001064D
0x140010285  lea     rax, [rsi+38h]
0x140010289  mov     [rbp+0A0h+var_F8], rax
0x14001028d  test    rax, rax
0x140010290  jz      loc_14001064B
0x140010296  mov     r15d, 28h ; '('
0x14001029c  mov     r8d, r15d
0x14001029f  cmp     [rax], di
0x1400102a2  jz      short loc_1400102AE
0x1400102a4  add     rax, 2
0x1400102a8  sub     r8, 1
0x1400102ac  jnz     short loc_14001029F
0x1400102ae  mov     rax, r8
0x1400102b1  mov     rcx, r15
0x1400102b4  neg     rax
0x1400102b7  mov     rax, r8
0x1400102ba  sbb     ebx, ebx
0x1400102bc  sub     rcx, r8
0x1400102bf  not     ebx
0x1400102c1  and     ebx, edx
0x1400102c3  neg     rax
0x1400102c6  sbb     rax, rax
0x1400102c9  and     rax, rcx
0x1400102cc  mov     [rbp+0A0h+var_118], rax
0x1400102d0  test    r8, r8
0x1400102d3  jz      loc_14001064D
0x1400102d9  lea     rdx, aWindowserrorre; "\\WindowsErrorReportingServicePort"
0x1400102e0  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x1400102e4  call    cs:__imp_RtlInitUnicodeString
0x1400102eb  nop     dword ptr [rax+rax+00h]
0x1400102f0  xor     edx, edx; Val
0x1400102f2  lea     rcx, [rbp+0A0h+var_A0]; void *
0x1400102f6  lea     r8d, [rdx+48h]; Size
0x1400102fa  call    memset
0x1400102ff  lea     rax, [rsp+1A0h+P]
0x140010304  mov     [rbp+0A0h+var_90], 578h
0x14001030c  lea     rcx, [rbp+0A0h+IdentifierAuthority]; IdentifierAuthority
0x140010310  mov     [rsp+1A0h+var_150], rax; __int64
0x140010315  call    WerpAllocateAndInitializeSid
0x14001031a  mov     ebx, eax
0x14001031c  test    eax, eax
0x14001031e  js      loc_14001064D
0x140010324  call    WerStartSystemErrorHandler
0x140010329  test    eax, eax
0x14001032b  jns     short loc_140010355
0x14001032d  mov     edx, 1; Level
0x140010332  lea     r8, aWerkernelhostW_56; "WERKERNELHOST: WerStartSystemErrorHandl"...
0x140010339  mov     r9d, eax
0x14001033c  lea     ecx, [rdx+4]; ComponentId
0x14001033f  call    cs:__imp_DbgPrintEx
0x140010346  nop     dword ptr [rax+rax+00h]
0x14001034b  mov     ebx, 102h
0x140010350  jmp     loc_14001064D
0x140010355  xor     r9d, r9d; ReturnLength
0x140010358  lea     rdx, [rsp+1A0h+SystemInformation]; SystemInformation
0x14001035d  lea     r8d, [r9+8]; SystemInformationLength
0x140010361  lea     ecx, [r9+73h]; SystemInformationClass
0x140010365  call    cs:__imp_ZwQuerySystemInformation
0x14001036c  nop     dword ptr [rax+rax+00h]
0x140010371  mov     ebx, eax
0x140010373  test    eax, eax
0x140010375  jns     short loc_14001039C
0x140010377  lea     r8, aWerkernelhostZ; "WERKERNELHOST: ZwQuerySysInfo(ErrorPort"...
0x14001037e  mov     r9d, eax
0x140010381  mov     edx, 1; Level
0x140010386  mov     ecx, 5; ComponentId
0x14001038b  call    cs:__imp_DbgPrintEx
0x140010392  nop     dword ptr [rax+rax+00h]
0x140010397  jmp     loc_14001064D
0x14001039c  mov     ecx, dword ptr [rsp+1A0h+SystemInformation]
0x1400103a0  call    WerWaitForSystemErrorHandler
0x1400103a5  xor     r8d, r8d
0x1400103a8  mov     ebx, eax
0x1400103aa  test    eax, eax
0x1400103ac  jns     short loc_1400103B7
0x1400103ae  lea     r8, aWerkernelhostW_23; "WERKERNELHOST: WerWaitForSystemErrorHan"...
0x1400103b5  jmp     short loc_14001037E
0x1400103b7  mov     edi, 102h
0x1400103bc  cmp     eax, edi
0x1400103be  jnz     short loc_1400103E0
0x1400103c0  lea     r8, aWerkernelhostW_29; "WERKERNELHOST: WerWaitForSystemErrorHan"...
0x1400103c7  mov     edx, 1; Level
0x1400103cc  lea     ecx, [rdx+4]; ComponentId
0x1400103cf  call    cs:__imp_DbgPrintEx
0x1400103d6  nop     dword ptr [rax+rax+00h]
0x1400103db  jmp     loc_14001064D
0x1400103e0  cmp     dword ptr [rsp+1A0h+SystemInformation+4], 0FFFFFFFFh
0x1400103e5  xorps   xmm0, xmm0
0x1400103e8  movdqu  [rbp+0A0h+var_C8], xmm0
0x1400103ed  mov     dword ptr [rbp+0A0h+var_E8], 30h ; '0'
0x1400103f4  mov     qword ptr [rbp+0A0h+var_E8+8], r8
0x1400103f8  mov     dword ptr [rbp+0A0h+var_D8+8], 200h
0x1400103ff  mov     qword ptr [rbp+0A0h+var_D8], r8
0x140010403  jnz     short loc_140010409
0x140010405  mov     dl, 1
0x140010407  jmp     short loc_14001041C
0x140010409  movsxd  rax, dword ptr [rsp+1A0h+SystemInformation+4]
0x14001040e  mov     dl, r8b
0x140010411  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x140010418  mov     [rbp+0A0h+var_120], rcx
0x14001041c  mov     rax, [rsp+1A0h+P]
0x140010421  lea     rcx, [rbp+0A0h+var_120]
0x140010425  test    dl, dl
0x140010427  lea     r9, [rbp+0A0h+var_A0]
0x14001042b  lea     rdx, [rbp+0A0h+DestinationString]
0x14001042f  cmovnz  rcx, r8
0x140010433  mov     [rsp+1A0h+var_150], rcx
0x140010438  mov     [rsp+1A0h+var_158], r8
0x14001043d  mov     [rsp+1A0h+var_160], r8
0x140010442  mov     [rsp+1A0h+var_168], r8
0x140010447  mov     [rsp+1A0h+var_170], r8
0x14001044c  lea     r8, [rbp+0A0h+var_E8]
0x140010450  mov     [rbp+0A0h+var_F0], rcx
0x140010454  lea     rcx, [rsp+1A0h+Handle]
0x140010459  mov     [rsp+1A0h+var_178], rax
0x14001045e  mov     dword ptr [rsp+1A0h+var_180], 20000h
0x140010466  call    cs:__imp_ZwAlpcConnectPort
0x14001046d  nop     dword ptr [rax+rax+00h]
0x140010472  mov     ebx, eax
0x140010474  test    eax, eax
0x140010476  jns     short loc_140010484
0x140010478  lea     r8, aWerkernelhostZ_3; "WERKERNELHOST: ZwAlpcConnectPort failed"...
0x14001047f  jmp     loc_14001037E
0x140010484  cmp     eax, edi
0x140010486  jnz     short loc_140010494
0x140010488  lea     r8, aWerkernelhostZ_7; "WERKERNELHOST: ZwAlpcConnectPort timed "...
0x14001048f  jmp     loc_1400103C7
0x140010494  xor     edx, edx; Val
0x140010496  mov     r8d, 578h; Size
0x14001049c  mov     rcx, r14; void *
0x14001049f  call    memset
0x1400104a4  mov     rcx, [rbp+0A0h+var_108]
0x1400104a8  lea     rdx, [r14+38h]
0x1400104ac  mov     r8, [rbp+0A0h+var_118]
0x1400104b0  xor     r10d, r10d
0x1400104b3  mov     eax, r10d
0x1400104b6  mov     dword ptr [r14], 5780550h
0x1400104bd  mov     dword ptr [r14+28h], 60000000h
0x1400104c5  cmp     dword ptr [rsi+4], 2
0x1400104c9  setz    al
0x1400104cc  mov     [r14+30h], eax
0x1400104d0  lea     eax, [r10+0Fh]
0x1400104d4  cmp     rcx, rax
0x1400104d7  ja      short loc_1400104DC
0x1400104d9  mov     rax, rcx
0x1400104dc  mov     r9, [rbp+0A0h+var_100]
0x1400104e0  mov     esi, 1
0x1400104e5  test    rax, rax
0x1400104e8  jz      short loc_140010506
0x1400104ea  movzx   ecx, word ptr [r9]
0x1400104ee  test    cx, cx
0x1400104f1  jz      short loc_140010506
0x1400104f3  mov     [rdx], cx
0x1400104f6  add     r9, 2
0x1400104fa  add     rdx, 2
0x1400104fe  sub     rax, rsi
0x140010501  sub     r12, rsi
0x140010504  jnz     short loc_1400104E5
0x140010506  mov     rax, r12
0x140010509  lea     rcx, [rdx-2]
0x14001050d  neg     rax
0x140010510  mov     r9d, 80000005h
0x140010516  sbb     ebx, ebx
0x140010518  not     ebx
0x14001051a  and     ebx, r9d
0x14001051d  test    r12, r12
0x140010520  cmovnz  rcx, rdx
0x140010524  mov     [rcx], r10w
0x140010528  jnz     short loc_14001053B
0x14001052a  mov     r9d, ebx
0x14001052d  lea     r8, aWerkernelhostS_4; "WERKERNELHOST: StringCchCopy failed for"...
0x140010534  mov     edx, esi
0x140010536  jmp     loc_140010386
0x14001053b  mov     eax, 27h ; '''
0x140010540  lea     rdx, [r14+58h]
0x140010544  cmp     r8, rax
0x140010547  ja      short loc_14001054C
0x140010549  mov     rax, r8
0x14001054c  mov     r8, [rbp+0A0h+var_F8]
0x140010550  xor     r12d, r12d
0x140010553  test    rax, rax
0x140010556  jz      short loc_140010574
0x140010558  movzx   ecx, word ptr [r8]
0x14001055c  test    cx, cx
0x14001055f  jz      short loc_140010574
0x140010561  mov     [rdx], cx
0x140010564  add     r8, 2
0x140010568  add     rdx, 2
0x14001056c  sub     rax, rsi
0x14001056f  sub     r15, rsi
0x140010572  jnz     short loc_140010553
0x140010574  mov     rax, r15
0x140010577  lea     rcx, [rdx-2]
0x14001057b  neg     rax
0x14001057e  sbb     ebx, ebx
0x140010580  not     ebx
0x140010582  and     ebx, r9d
  ... truncated ...
```
