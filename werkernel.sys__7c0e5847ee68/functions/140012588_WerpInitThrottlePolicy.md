# WerpInitThrottlePolicy

- ea: `0x140012588`
- end: `0x140012a8b`
- name: `WerpInitThrottlePolicy`
- size: `1283`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012080`

## callees

- `0x140002c40`
- `0x14000d174`
- `0x14000f1d4`
- `0x14000f3e0`
- `0x14000f4b8`
- `0x14000f54c`
- `0x14000f5b4`
- `0x140012588`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14001275d`
- `ntoskrnl!DbgPrintEx` at `0x1400127ca`
- `ntoskrnl!DbgPrintEx` at `0x140012901`
- `ntoskrnl!DbgPrintEx` at `0x140012a7d`
- `ntoskrnl!DbgPrintEx` at `0x14001275d`
- `ntoskrnl!DbgPrintEx` at `0x1400127ca`
- `ntoskrnl!DbgPrintEx` at `0x140012901`
- `ntoskrnl!DbgPrintEx` at `0x140012a7d`
- `ntoskrnl!ZwClose` at `0x1400127e8`
- `ntoskrnl!ZwClose` at `0x14001291a`
- `ntoskrnl!ZwClose` at `0x1400129c6`
- `ntoskrnl!ZwClose` at `0x140012a20`
- `ntoskrnl!ZwClose` at `0x140012a35`
- `ntoskrnl!ZwClose` at `0x1400127e8`
- `ntoskrnl!ZwClose` at `0x14001291a`
- `ntoskrnl!ZwClose` at `0x1400129c6`
- `ntoskrnl!ZwClose` at `0x140012a20`
- `ntoskrnl!ZwClose` at `0x140012a35`
- `ntoskrnl!ZwEnumerateKey` at `0x14001289a`
- `ntoskrnl!ZwEnumerateKey` at `0x1400129fb`
- `ntoskrnl!ZwEnumerateKey` at `0x14001289a`
- `ntoskrnl!ZwEnumerateKey` at `0x1400129fb`

## string_xrefs

- `0x14001265d`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl\FullLiveKernelReports`
- `0x1400125d0`: `ComponentThrottleThreshold`
- `0x140012614`: `VrfComponentThrottleThreshold`
- `0x14001274f`: `WERKERNELHOST: Registry PerComponentThreshold cannot be shorter than SystemThreshold.\n`
- `0x1400127bb`: `WERKERNELHOST: Registry VrfComponentThreshold cannot be shorter than VrfSystemThreshold.\n`
- `0x1400128f4`: `WERKERNELHOST: WerpInitThrottlePolicy: Failed to open key %ws\n`
- `0x1400127ff`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl`

## pseudocode

```c
__int64 WerpInitThrottlePolicy()
{
  int RegistryKey; // eax
  __int64 result; // rax
  unsigned int *v2; // r15
  int v3; // ebx
  void *v4; // r8
  __int64 v5; // rdx
  unsigned int *Mem; // rsi
  unsigned int v7; // r14d
  NTSTATUS i; // eax
  ULONG v9; // r13d
  _WORD *v10; // r14
  void *v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r12
  _WORD *v14; // rax
  _WORD *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  _WORD *v18; // rcx
  PCWSTR *v19; // rax
  HANDLE v20; // [rsp+30h] [rbp-59h] BYREF
  PCWSTR *v21; // [rsp+38h] [rbp-51h]
  struct _UNICODE_STRING v22; // [rsp+40h] [rbp-49h] BYREF
  struct _UNICODE_STRING v23; // [rsp+50h] [rbp-39h] BYREF
  struct _UNICODE_STRING v24; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING v25; // [rsp+70h] [rbp-19h] BYREF
  struct _UNICODE_STRING v26; // [rsp+80h] [rbp-9h] BYREF
  struct _UNICODE_STRING v27; // [rsp+90h] [rbp+7h] BYREF
  struct _UNICODE_STRING v28; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v29; // [rsp+F0h] [rbp+67h] BYREF
  ULONG ResultLength; // [rsp+F8h] [rbp+6Fh] BYREF
  HANDLE Handle; // [rsp+100h] [rbp+77h] BYREF
  HANDLE v32; // [rsp+108h] [rbp+7Fh] BYREF

  *(_QWORD *)&v22.Length = 2490404;
  v22.Buffer = L"LastFullLiveReport";
  *(_QWORD *)&v23.Length = 2490404;
  v23.Buffer = L"FullLiveReportsMax";
  *(_QWORD *)&v26.Length = 3538996;
  v26.Buffer = L"ComponentThrottleThreshold";
  *(_QWORD *)&v24.Length = 4456514;
  v24.Buffer = L"SystemMemoryThrottleThresholdInGB";
  *(_QWORD *)&v25.Length = 3145774;
  v25.Buffer = L"SystemThrottleThreshold";
  *(_QWORD *)&v28.Length = 3932218;
  v28.Buffer = L"VrfComponentThrottleThreshold";
  v27.Buffer = L"VrfSystemThrottleThreshold";
  *(_QWORD *)&v27.Length = 3538996;
  v32 = 0;
  ResultLength = 0;
  memset(&WerKernelThrottlePolicy, 0, 0x40u);
  Handle = 0;
  v20 = 0;
  RegistryKey = WerpGetRegistryKey(
                  0,
                  L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl\\FullLiveKernelReports",
                  131097,
                  &Handle);
  dword_1400093C8 = 1;
  if ( RegistryKey >= 0 )
  {
    v2 = 0;
    WerpGetRegistryUlongValue(Handle, &v23, 1, &dword_1400093C8);
    LODWORD(v29) = 256;
    WerpGetRegistryUlongValue(Handle, &v24, 256, &v29);
    if ( (_DWORD)v29 == -1 )
      qword_1400093D0 = -1;
    else
      qword_1400093D0 = (unsigned __int64)(unsigned int)v29 << 30;
    WerpGetRegistryTimeoutValue(Handle, &v25, 0x30u, (__int64 *)&xmmword_1400093A8);
    WerpGetRegistryTimeoutValue(Handle, &v26, 0xA8u, (__int64 *)&xmmword_1400093A8 + 1);
    if ( *((__int64 *)&xmmword_1400093A8 + 1) < (__int64)xmmword_1400093A8 )
    {
      DbgPrintEx(5u, 1u, "WERKERNELHOST: Registry PerComponentThreshold cannot be shorter than SystemThreshold.\n");
      *((_QWORD *)&xmmword_1400093A8 + 1) = xmmword_1400093A8;
    }
    WerpGetRegistryTimeoutValue(Handle, &v27, 1u, (__int64 *)&xmmword_1400093B8);
    WerpGetRegistryTimeoutValue(Handle, &v28, 0x18u, (__int64 *)&xmmword_1400093B8 + 1);
    if ( *((__int64 *)&xmmword_1400093B8 + 1) < (__int64)xmmword_1400093B8 )
    {
      DbgPrintEx(5u, 1u, "WERKERNELHOST: Registry VrfComponentThreshold cannot be shorter than VrfSystemThreshold.\n");
      *((_QWORD *)&xmmword_1400093B8 + 1) = xmmword_1400093B8;
    }
    ZwClose(Handle);
    Handle = 0;
    v3 = WerpGetRegistryKey(0, g_wszLiveKernelReportsQueueRoot, 131097, &v20);
    if ( v3 >= 0 )
    {
      v3 = WerpGetRegistryKey(v20, L"FullLiveKernelReports", 131097, &Handle);
      if ( v3 >= 0 )
      {
        WerpGetRegistryLong64Value(Handle, &v22, v4, &WerKernelThrottlePolicy);
        Mem = (unsigned int *)WerpAllocateMem(56, v5);
        if ( Mem )
        {
          v32 = 0;
          v7 = 0;
          v21 = &SourceString;
          v2 = Mem;
          for ( i = ZwEnumerateKey(Handle, 0, KeyBasicInformation, Mem, 0x36u, &ResultLength);
                ;
                i = ZwEnumerateKey(Handle, v9, KeyBasicInformation, Mem, 0x36u, &ResultLength) )
          {
            v3 = i;
            if ( i == -2147483622 )
            {
              v3 = 0;
              goto LABEL_36;
            }
            if ( i < 0 )
              break;
            v9 = v7 + 1;
            if ( v7 + 1 < v7 )
            {
              v3 = -1073741675;
              goto LABEL_36;
            }
            v10 = Mem + 4;
            *((_WORD *)Mem + ((unsigned __int64)Mem[3] >> 1) + 8) = 0;
            v3 = WerpGetRegistryKey(Handle, Mem + 4, 131097, &v32);
            if ( v3 >= 0 )
            {
              v29 = 0;
              WerpGetRegistryLong64Value(v32, &v22, v11, &v29);
              v13 = v29;
              if ( v29 )
              {
                v14 = (_WORD *)WerpAllocateMem(48, v12);
                v15 = v14;
                if ( v14 )
                {
                  v16 = 2147483646;
                  v17 = 16;
                  do
                  {
                    if ( !v16 )
                      break;
                    if ( !*v10 )
                      break;
                    *v14++ = *v10++;
                    --v16;
                    --v17;
                  }
                  while ( v17 );
                  v18 = v14 - 1;
                  if ( v17 )
                    v18 = v14;
                  v19 = v21;
                  *v18 = 0;
                  *((_QWORD *)v15 + 4) = v13;
                  *v19 = v15;
                  v21 = (PCWSTR *)(v15 + 20);
                }
                else
                {
                  v3 = -1073741801;
                }
              }
              if ( v32 )
              {
                ZwClose(v32);
                v32 = 0;
              }
              if ( v3 < 0 )
                goto LABEL_36;
            }
            else
            {
              DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpInitThrottlePolicy: Failed to open key %ws\n", Mem + 4);
              if ( v32 )
              {
                ZwClose(v32);
                v32 = 0;
              }
            }
            v7 = v9;
          }
          DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpInitThrottlePolicy: ZwEnumerateKey returned status 0x%X\n", i);
        }
        else
        {
          v3 = -1073741670;
        }
      }
    }
LABEL_36:
    if ( Handle )
      ZwClose(Handle);
    if ( v20 )
      ZwClose(v20);
    if ( v2 )
      WerpFreeMem(v2);
    return (unsigned int)v3;
  }
  else
  {
    qword_1400093D0 = 0x4000000000LL;
    result = 0;
    xmmword_1400093A8 = (__int128)_mm_load_si128((const __m128i *)&_xmm);
    xmmword_1400093B8 = (__int128)_mm_load_si128((const __m128i *)&_xmm);
  }
  return result;
}

```

## disassembly

```asm
0x140012588  push    rbp
0x14001258a  push    rbx
0x14001258b  push    rsi
0x14001258c  push    r12
0x14001258e  push    r13
0x140012590  push    r14
0x140012592  push    r15
0x140012594  lea     rbp, [rsp-27h]
0x140012599  sub     rsp, 0B0h
0x1400125a0  lea     rax, aLastfulllivere; "LastFullLiveReport"
0x1400125a7  mov     [rbp+57h+var_A0], 260024h
0x1400125af  mov     [rbp+57h+var_98], rax
0x1400125b3  lea     rcx, WerKernelThrottlePolicy; void *
0x1400125ba  lea     rax, aFulllivereport; "FullLiveReportsMax"
0x1400125c1  mov     [rbp+57h+var_90], 260024h
0x1400125c9  mov     [rbp+57h+var_88], rax
0x1400125cd  xor     r12d, r12d
0x1400125d0  lea     rax, aComponentthrot; "ComponentThrottleThreshold"
0x1400125d7  mov     [rbp+57h+var_60], 360034h
0x1400125df  mov     [rbp+57h+var_58], rax
0x1400125e3  mov     ebx, 30h ; '0'
0x1400125e8  lea     rax, aSystemmemoryth; "SystemMemoryThrottleThresholdInGB"
0x1400125ef  mov     [rbp+57h+var_80], 440042h
0x1400125f7  mov     [rbp+57h+var_78], rax
0x1400125fb  xor     edx, edx; Val
0x1400125fd  lea     rax, aSystemthrottle; "SystemThrottleThreshold"
0x140012604  mov     [rbp+57h+var_70], 30002Eh
0x14001260c  mov     [rbp+57h+var_68], rax
0x140012610  lea     r8d, [rbx+10h]; Size
0x140012614  lea     rax, aVrfcomponentth; "VrfComponentThrottleThreshold"
0x14001261b  mov     [rbp+57h+var_40], 3C003Ah
0x140012623  mov     [rbp+57h+var_38], rax
0x140012627  lea     rax, aVrfsystemthrot; "VrfSystemThrottleThreshold"
0x14001262e  mov     [rbp+57h+var_48], rax
0x140012632  mov     [rbp+57h+var_50], 360034h
0x14001263a  mov     [rbp+57h+arg_18], r12
0x14001263e  mov     [rbp+57h+arg_8], r12d
0x140012642  call    memset
0x140012647  mov     esi, 20019h
0x14001264c  mov     [rbp+57h+Handle], r12
0x140012650  mov     r8d, esi
0x140012653  mov     [rbp+57h+var_B0], r12
0x140012657  lea     r9, [rbp+57h+Handle]
0x14001265b  xor     ecx, ecx
0x14001265d  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140012664  call    WerpGetRegistryKey
0x140012669  mov     cs:dword_1400093C8, 1
0x140012673  test    eax, eax
0x140012675  jns     short loc_1400126AF
0x140012677  movdqa  xmm0, cs:__xmm@0000058028e440000000019254d38000
0x14001267f  mov     rax, 4000000000h
0x140012689  movdqa  xmm1, cs:__xmm@000000c92a69c0000000000861c46800
0x140012691  mov     cs:qword_1400093D0, rax
0x140012698  xor     eax, eax
0x14001269a  movdqu  cs:xmmword_1400093A8, xmm0
0x1400126a2  movdqu  cs:xmmword_1400093B8, xmm1
0x1400126aa  jmp     loc_140012A50
0x1400126af  mov     rcx, [rbp+57h+Handle]
0x1400126b3  lea     r9, dword_1400093C8
0x1400126ba  mov     r8d, 1
0x1400126c0  lea     rdx, [rbp+57h+var_90]
0x1400126c4  mov     r15, r12
0x1400126c7  call    WerpGetRegistryUlongValue
0x1400126cc  mov     rcx, [rbp+57h+Handle]
0x1400126d0  lea     r9, [rbp+57h+arg_0]
0x1400126d4  mov     r8d, 100h
0x1400126da  lea     rdx, [rbp+57h+var_80]
0x1400126de  mov     dword ptr [rbp+57h+arg_0], r8d
0x1400126e2  call    WerpGetRegistryUlongValue
0x1400126e7  cmp     dword ptr [rbp+57h+arg_0], 0FFFFFFFFh
0x1400126eb  jz      short loc_1400126FD
0x1400126ed  mov     eax, dword ptr [rbp+57h+arg_0]
0x1400126f0  shl     rax, 1Eh
0x1400126f4  mov     cs:qword_1400093D0, rax
0x1400126fb  jmp     short loc_140012708
0x1400126fd  mov     cs:qword_1400093D0, 0FFFFFFFFFFFFFFFFh
0x140012708  mov     rcx, [rbp+57h+Handle]
0x14001270c  lea     r9, xmmword_1400093A8
0x140012713  mov     r8d, ebx
0x140012716  lea     rdx, [rbp+57h+var_70]
0x14001271a  call    WerpGetRegistryTimeoutValue
0x14001271f  mov     rcx, [rbp+57h+Handle]
0x140012723  lea     r9, xmmword_1400093A8+8
0x14001272a  mov     r8d, 0A8h
0x140012730  lea     rdx, [rbp+57h+var_60]
0x140012734  call    WerpGetRegistryTimeoutValue
0x140012739  mov     rax, qword ptr cs:xmmword_1400093A8
0x140012740  mov     r13d, 5
0x140012746  cmp     qword ptr cs:xmmword_1400093A8+8, rax
0x14001274d  jge     short loc_140012777
0x14001274f  lea     r8, aWerkernelhostR_3; "WERKERNELHOST: Registry PerComponentThr"...
0x140012756  mov     ecx, r13d; ComponentId
0x140012759  lea     edx, [r13-4]; Level
0x14001275d  call    cs:__imp_DbgPrintEx
0x140012764  nop     dword ptr [rax+rax+00h]
0x140012769  mov     rax, qword ptr cs:xmmword_1400093A8
0x140012770  mov     qword ptr cs:xmmword_1400093A8+8, rax
0x140012777  mov     rcx, [rbp+57h+Handle]
0x14001277b  lea     r9, xmmword_1400093B8
0x140012782  mov     r8d, 1
0x140012788  lea     rdx, [rbp+57h+var_50]
0x14001278c  call    WerpGetRegistryTimeoutValue
0x140012791  mov     rcx, [rbp+57h+Handle]
0x140012795  lea     r9, xmmword_1400093B8+8
0x14001279c  mov     r8d, 18h
0x1400127a2  lea     rdx, [rbp+57h+var_40]
0x1400127a6  call    WerpGetRegistryTimeoutValue
0x1400127ab  mov     rax, qword ptr cs:xmmword_1400093B8
0x1400127b2  cmp     qword ptr cs:xmmword_1400093B8+8, rax
0x1400127b9  jge     short loc_1400127E4
0x1400127bb  lea     r8, aWerkernelhostR; "WERKERNELHOST: Registry VrfComponentThr"...
0x1400127c2  mov     edx, 1; Level
0x1400127c7  mov     ecx, r13d; ComponentId
0x1400127ca  call    cs:__imp_DbgPrintEx
0x1400127d1  nop     dword ptr [rax+rax+00h]
0x1400127d6  mov     rax, qword ptr cs:xmmword_1400093B8
0x1400127dd  mov     qword ptr cs:xmmword_1400093B8+8, rax
0x1400127e4  mov     rcx, [rbp+57h+Handle]; Handle
0x1400127e8  call    cs:__imp_ZwClose
0x1400127ef  nop     dword ptr [rax+rax+00h]
0x1400127f4  lea     r9, [rbp+57h+var_B0]
0x1400127f8  mov     [rbp+57h+Handle], r12
0x1400127fc  mov     r8d, esi
0x1400127ff  lea     rdx, g_wszLiveKernelReportsQueueRoot; "\\Registry\\Machine\\System\\CurrentCon"...
0x140012806  xor     ecx, ecx
0x140012808  call    WerpGetRegistryKey
0x14001280d  mov     ebx, eax
0x14001280f  test    eax, eax
0x140012811  js      loc_140012A17
0x140012817  mov     rcx, [rbp+57h+var_B0]
0x14001281b  lea     r9, [rbp+57h+Handle]
0x14001281f  mov     r8d, esi
0x140012822  lea     rdx, aFulllivekernel; "FullLiveKernelReports"
0x140012829  call    WerpGetRegistryKey
0x14001282e  mov     ebx, eax
0x140012830  test    eax, eax
0x140012832  js      loc_140012A17
0x140012838  mov     rcx, [rbp+57h+Handle]
0x14001283c  lea     r9, WerKernelThrottlePolicy
0x140012843  lea     rdx, [rbp+57h+var_A0]
0x140012847  call    WerpGetRegistryLong64Value
0x14001284c  mov     ecx, 38h ; '8'
0x140012851  call    WerpAllocateMem
0x140012856  mov     rsi, rax
0x140012859  test    rax, rax
0x14001285c  jnz     short loc_140012868
0x14001285e  mov     ebx, 0C000009Ah
0x140012863  jmp     loc_140012A17
0x140012868  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001286c  lea     rax, [rbp+57h+arg_8]
0x140012870  mov     [rbp+57h+arg_18], r12
0x140012874  mov     r14d, r12d
0x140012877  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x14001287c  lea     r12, SourceString
0x140012883  mov     r9, rsi; KeyInformation
0x140012886  mov     [rbp+57h+var_A8], r12
0x14001288a  xor     r8d, r8d; KeyInformationClass
0x14001288d  mov     [rsp+0E0h+Length], 36h ; '6'; Length
0x140012895  xor     edx, edx; Index
0x140012897  mov     r15, rsi
0x14001289a  call    cs:__imp_ZwEnumerateKey
0x1400128a1  nop     dword ptr [rax+rax+00h]
0x1400128a6  xor     r12d, r12d
0x1400128a9  jmp     loc_140012A07
0x1400128ae  test    ebx, ebx
0x1400128b0  js      loc_140012A6B
0x1400128b6  lea     r13d, [r14+1]
0x1400128ba  cmp     r13d, r14d
0x1400128bd  jb      loc_140012A64
0x1400128c3  mov     ecx, [rsi+0Ch]
0x1400128c6  lea     r14, [rsi+10h]
0x1400128ca  shr     rcx, 1
0x1400128cd  lea     r9, [rbp+57h+arg_18]
0x1400128d1  mov     r8d, 20019h
0x1400128d7  mov     rdx, r14
0x1400128da  mov     [rsi+rcx*2+10h], r12w
0x1400128e0  mov     rcx, [rbp+57h+Handle]
0x1400128e4  call    WerpGetRegistryKey
0x1400128e9  mov     ebx, eax
0x1400128eb  test    eax, eax
0x1400128ed  jns     short loc_14001292F
0x1400128ef  mov     edx, 1; Level
0x1400128f4  lea     r8, aWerkernelhostW_10; "WERKERNELHOST: WerpInitThrottlePolicy: "...
0x1400128fb  mov     r9, r14
0x1400128fe  lea     ecx, [rdx+4]; ComponentId
0x140012901  call    cs:__imp_DbgPrintEx
0x140012908  nop     dword ptr [rax+rax+00h]
0x14001290d  mov     rcx, [rbp+57h+arg_18]; Handle
0x140012911  test    rcx, rcx
0x140012914  jz      loc_1400129DA
0x14001291a  call    cs:__imp_ZwClose
0x140012921  nop     dword ptr [rax+rax+00h]
0x140012926  mov     [rbp+57h+arg_18], r12
0x14001292a  jmp     loc_1400129DA
0x14001292f  mov     rcx, [rbp+57h+arg_18]
0x140012933  lea     r9, [rbp+57h+arg_0]
0x140012937  lea     rdx, [rbp+57h+var_A0]
0x14001293b  mov     [rbp+57h+arg_0], r12
0x14001293f  call    WerpGetRegistryLong64Value
0x140012944  mov     r12, [rbp+57h+arg_0]
0x140012948  test    r12, r12
0x14001294b  jz      short loc_1400129BA
0x14001294d  mov     ecx, 30h ; '0'
0x140012952  call    WerpAllocateMem
0x140012957  xor     r10d, r10d
0x14001295a  mov     rdx, rax
0x14001295d  test    rax, rax
0x140012960  jnz     short loc_140012969
0x140012962  mov     ebx, 0C0000017h
0x140012967  jmp     short loc_1400129BA
0x140012969  mov     ecx, 7FFFFFFEh
0x14001296e  mov     r8d, 10h
0x140012974  test    rcx, rcx
0x140012977  jz      short loc_140012998
0x140012979  movzx   r9d, word ptr [r14]
0x14001297d  test    r9w, r9w
0x140012981  jz      short loc_140012998
0x140012983  mov     [rax], r9w
0x140012987  add     r14, 2
0x14001298b  add     rax, 2
0x14001298f  dec     rcx
0x140012992  sub     r8, 1
0x140012996  jnz     short loc_140012974
0x140012998  lea     rcx, [rax-2]
0x14001299c  test    r8, r8
0x14001299f  cmovnz  rcx, rax
0x1400129a3  mov     rax, [rbp+57h+var_A8]
0x1400129a7  mov     [rcx], r10w
0x1400129ab  mov     [rdx+20h], r12
0x1400129af  mov     [rax], rdx
0x1400129b2  lea     rax, [rdx+28h]
0x1400129b6  mov     [rbp+57h+var_A8], rax
0x1400129ba  mov     rcx, [rbp+57h+arg_18]; Handle
0x1400129be  xor     r12d, r12d
0x1400129c1  test    rcx, rcx
0x1400129c4  jz      short loc_1400129D6
0x1400129c6  call    cs:__imp_ZwClose
0x1400129cd  nop     dword ptr [rax+rax+00h]
0x1400129d2  mov     [rbp+57h+arg_18], r12
0x1400129d6  test    ebx, ebx
0x1400129d8  js      short loc_140012A17
0x1400129da  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x1400129de  lea     rax, [rbp+57h+arg_8]
0x1400129e2  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400129e7  mov     r9, rsi; KeyInformation
0x1400129ea  xor     r8d, r8d; KeyInformationClass
0x1400129ed  mov     [rsp+0E0h+Length], 36h ; '6'; Length
0x1400129f5  mov     edx, r13d; Index
0x1400129f8  mov     r14d, r13d
0x1400129fb  call    cs:__imp_ZwEnumerateKey
0x140012a02  nop     dword ptr [rax+rax+00h]
0x140012a07  mov     ebx, eax
0x140012a09  cmp     eax, 8000001Ah
0x140012a0e  jnz     loc_1400128AE
0x140012a14  mov     ebx, r12d
0x140012a17  mov     rcx, [rbp+57h+Handle]; Handle
0x140012a1b  test    rcx, rcx
0x140012a1e  jz      short loc_140012A2C
0x140012a20  call    cs:__imp_ZwClose
0x140012a27  nop     dword ptr [rax+rax+00h]
0x140012a2c  mov     rcx, [rbp+57h+var_B0]; Handle
0x140012a30  test    rcx, rcx
0x140012a33  jz      short loc_140012A41
0x140012a35  call    cs:__imp_ZwClose
0x140012a3c  nop     dword ptr [rax+rax+00h]
0x140012a41  test    r15, r15
0x140012a44  jz      short loc_140012A4E
0x140012a46  mov     rcx, r15
0x140012a49  call    WerpFreeMem
0x140012a4e  mov     eax, ebx
0x140012a50  add     rsp, 0B0h
0x140012a57  pop     r15
0x140012a59  pop     r14
0x140012a5b  pop     r13
0x140012a5d  pop     r12
0x140012a5f  pop     rsi
0x140012a60  pop     rbx
0x140012a61  pop     rbp
0x140012a62  retn
0x140012a64  mov     ebx, 0C0000095h
0x140012a69  jmp     short loc_140012A17
0x140012a6b  mov     edx, 1; Level
0x140012a70  lea     r8, aWerkernelhostW_3; "WERKERNELHOST: WerpInitThrottlePolicy: "...
0x140012a77  mov     r9d, ebx
0x140012a7a  lea     ecx, [rdx+4]; ComponentId
0x140012a7d  call    cs:__imp_DbgPrintEx
0x140012a84  nop     dword ptr [rax+rax+00h]
0x140012a89  jmp     short loc_140012A17
```
