# WerpInitRootPath

- ea: `0x1400122c0`
- end: `0x14001257f`
- name: `WerpInitRootPath`
- size: `703`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140012080`

## callees

- `0x140002940`
- `0x140002c40`
- `0x14000d174`
- `0x14000dfd0`
- `0x14000eb08`
- `0x14000f1d4`
- `0x14000f3e0`
- `0x14000f640`
- `0x1400122c0`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14001240d`
- `ntoskrnl!DbgPrintEx` at `0x14001240d`
- `ntoskrnl!ZwClose` at `0x140012528`
- `ntoskrnl!ZwClose` at `0x14001253d`
- `ntoskrnl!ZwClose` at `0x140012552`
- `ntoskrnl!ZwClose` at `0x140012567`
- `ntoskrnl!ZwClose` at `0x140012528`
- `ntoskrnl!ZwClose` at `0x14001253d`
- `ntoskrnl!ZwClose` at `0x140012552`
- `ntoskrnl!ZwClose` at `0x140012567`

## string_xrefs

- `0x140012400`: `WERKERNELHOST: ZwCreateKey failed with scode 0x%x for the root\n`
- `0x1400122cc`: `LiveKernelReportsPath`
- `0x14001233a`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl\LiveKernelReports`
- `0x1400123a9`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl`

## pseudocode

```c
__int64 WerpInitRootPath()
{
  __int64 v0; // rbx
  _DWORD *v1; // rsi
  __int64 v3; // rdx
  int RegistryKey; // edi
  int RegistryValueInfo; // eax
  int v6; // eax
  __int64 v7; // rcx
  void *Mem; // rax
  HANDLE v9; // [rsp+30h] [rbp-38h] BYREF
  HANDLE v10; // [rsp+38h] [rbp-30h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-28h] BYREF
  struct _UNICODE_STRING v12; // [rsp+50h] [rbp-18h] BYREF
  __int64 v13; // [rsp+90h] [rbp+28h] BYREF
  HANDLE Handle; // [rsp+98h] [rbp+30h] BYREF
  HANDLE v15; // [rsp+A0h] [rbp+38h] BYREF
  _DWORD *v16; // [rsp+A8h] [rbp+40h] BYREF

  Handle = 0;
  v0 = 0;
  ValueName.Buffer = L"LiveKernelReportsPath";
  v1 = 0;
  v15 = 0;
  v12.Buffer = L"LiveKernelReportsQueueRoot";
  v9 = 0;
  v10 = 0;
  v13 = 0;
  v16 = 0;
  *(_QWORD *)&ValueName.Length = 2883626;
  *(_QWORD *)&v12.Length = 3538996;
  if ( WerKernelLiveReportInitialized )
    return 0;
  WerKernelLiveReportRootPath = 0;
  RegistryKey = WerpGetRegistryKey(
                  0,
                  L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl\\LiveKernelReports",
                  0x20000,
                  &Handle);
  if ( RegistryKey < 0 )
    goto LABEL_13;
  RegistryKey = WerpGetRegistryValueInfo(Handle, &ValueName, &v13);
  RegistryValueInfo = WerpGetRegistryValueInfo(Handle, &v12, &v16);
  v1 = v16;
  if ( RegistryValueInfo < 0 )
    goto LABEL_12;
  if ( !v16 )
    goto LABEL_12;
  if ( v16[1] != 1 )
    goto LABEL_12;
  if ( v16[2] > 0x206u )
    goto LABEL_12;
  memset(g_wszLiveKernelReportsQueueRoot, 0, 0x208u);
  memmove(g_wszLiveKernelReportsQueueRoot, v16 + 3, (unsigned int)v16[2]);
  v6 = WerpCreateRegistryKey(0, g_wszLiveKernelReportsQueueRoot, 0x20004u, 0, &v15, 0);
  RegistryKey = v6;
  if ( v6 >= 0 )
  {
    v6 = WerpCreateRegistryKey(v15, L"LiveKernelReports", 0x20004u, 0, &v9, 0);
    RegistryKey = v6;
    if ( v6 >= 0 )
    {
      v6 = WerpCreateRegistryKey(v15, L"FullLiveKernelReports", 0x20004u, 0, &v10, 0);
      RegistryKey = v6;
      if ( v6 >= 0 )
      {
LABEL_12:
        v0 = v13;
LABEL_13:
        if ( RegistryKey >= 0
          && v0
          && *(_DWORD *)(v0 + 4) == 1
          && (v7 = *(unsigned int *)(v0 + 8), (unsigned int)v7 <= 0x206)
          && (Mem = (void *)WerpAllocateMem(v7, v3), (WerKernelLiveReportRootPath.Buffer = (PWSTR)Mem) != 0) )
        {
          WerKernelLiveReportRootPath.Length = *(_WORD *)(v0 + 8) - 2;
          WerKernelLiveReportRootPath.MaximumLength = *(_WORD *)(v0 + 8);
          memmove(Mem, (const void *)(v0 + 12), WerKernelLiveReportRootPath.Length);
          RegistryKey = WerpCreateStoreDirectory();
        }
        else
        {
          *(_DWORD *)&WerKernelLiveReportRootPath.Length = 3932218;
          WerKernelLiveReportRootPath.Buffer = L"\\SystemRoot\\LiveKernelReports";
          RegistryKey = 0;
        }
        goto LABEL_20;
      }
    }
  }
  DbgPrintEx(5u, 1u, "WERKERNELHOST: ZwCreateKey failed with scode 0x%x for the root\n", v6);
  v0 = v13;
LABEL_20:
  if ( v0 )
    WerpFreeMem(v0);
  if ( v1 )
    WerpFreeMem(v1);
  if ( Handle )
    ZwClose(Handle);
  if ( v15 )
    ZwClose(v15);
  if ( v9 )
    ZwClose(v9);
  if ( v10 )
    ZwClose(v10);
  return (unsigned int)RegistryKey;
}

```

## disassembly

```asm
0x1400122c0  push    rbp
0x1400122c2  push    rbx
0x1400122c3  push    rsi
0x1400122c4  push    rdi
0x1400122c5  mov     rbp, rsp
0x1400122c8  sub     rsp, 68h
0x1400122cc  lea     rax, aLivekernelrepo_1; "LiveKernelReportsPath"
0x1400122d3  mov     [rbp+Handle], 0
0x1400122db  xor     ebx, ebx
0x1400122dd  mov     [rbp+ValueName.Buffer], rax
0x1400122e1  xor     esi, esi
0x1400122e3  mov     [rbp+arg_10], 0
0x1400122eb  cmp     cs:WerKernelLiveReportInitialized, bl
0x1400122f1  lea     rax, aLivekernelrepo; "LiveKernelReportsQueueRoot"
0x1400122f8  mov     [rbp+var_18.Buffer], rax
0x1400122fc  mov     [rbp+var_38], 0
0x140012304  mov     [rbp+var_30], 0
0x14001230c  mov     [rbp+arg_0], rbx
0x140012310  mov     [rbp+arg_18], rsi
0x140012314  mov     qword ptr [rbp+ValueName.Length], 2C002Ah
0x14001231c  mov     qword ptr [rbp+var_18.Length], 360034h
0x140012324  jz      short loc_14001232D
0x140012326  xor     eax, eax
0x140012328  jmp     loc_140012575
0x14001232d  xorps   xmm0, xmm0
0x140012330  lea     r9, [rbp+Handle]
0x140012334  mov     r8d, 20000h
0x14001233a  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x140012341  xor     ecx, ecx
0x140012343  movups  xmmword ptr cs:WerKernelLiveReportRootPath.Length, xmm0
0x14001234a  call    WerpGetRegistryKey
0x14001234f  mov     edi, eax
0x140012351  test    eax, eax
0x140012353  js      loc_14001248C
0x140012359  mov     rcx, [rbp+Handle]; KeyHandle
0x14001235d  lea     r8, [rbp+arg_0]
0x140012361  lea     rdx, [rbp+ValueName]; ValueName
0x140012365  call    WerpGetRegistryValueInfo
0x14001236a  mov     rcx, [rbp+Handle]; KeyHandle
0x14001236e  lea     r8, [rbp+arg_18]
0x140012372  lea     rdx, [rbp+var_18]; ValueName
0x140012376  mov     edi, eax
0x140012378  call    WerpGetRegistryValueInfo
0x14001237d  mov     rsi, [rbp+arg_18]
0x140012381  test    eax, eax
0x140012383  js      loc_140012488
0x140012389  test    rsi, rsi
0x14001238c  jz      loc_140012488
0x140012392  cmp     dword ptr [rsi+4], 1
0x140012396  jnz     loc_140012488
0x14001239c  cmp     dword ptr [rsi+8], 206h
0x1400123a3  ja      loc_140012488
0x1400123a9  lea     rbx, g_wszLiveKernelReportsQueueRoot; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400123b0  xor     edx, edx; Val
0x1400123b2  mov     rcx, rbx; void *
0x1400123b5  mov     r8d, 208h; Size
0x1400123bb  call    memset
0x1400123c0  mov     r8d, [rsi+8]; Size
0x1400123c4  lea     rdx, [rsi+0Ch]; Src
0x1400123c8  mov     rcx, rbx; void *
0x1400123cb  call    memmove
0x1400123d0  lea     rax, [rbp+arg_10]
0x1400123d4  mov     [rsp+68h+var_40], 0
0x1400123dd  xor     r9d, r9d
0x1400123e0  mov     [rsp+68h+var_48], rax
0x1400123e5  mov     r8d, 20004h
0x1400123eb  mov     rdx, rbx
0x1400123ee  xor     ecx, ecx
0x1400123f0  call    WerpCreateRegistryKey
0x1400123f5  mov     edi, eax
0x1400123f7  test    eax, eax
0x1400123f9  jns     short loc_140012422
0x1400123fb  mov     edx, 1; Level
0x140012400  lea     r8, aWerkernelhostZ_5; "WERKERNELHOST: ZwCreateKey failed with "...
0x140012407  mov     r9d, eax
0x14001240a  lea     ecx, [rdx+4]; ComponentId
0x14001240d  call    cs:__imp_DbgPrintEx
0x140012414  nop     dword ptr [rax+rax+00h]
0x140012419  mov     rbx, [rbp+arg_0]
0x14001241d  jmp     loc_140012505
0x140012422  mov     rcx, [rbp+arg_10]
0x140012426  lea     rax, [rbp+var_38]
0x14001242a  mov     [rsp+68h+var_40], 0
0x140012433  lea     rdx, aLivekernelrepo_0; "LiveKernelReports"
0x14001243a  xor     r9d, r9d
0x14001243d  mov     [rsp+68h+var_48], rax
0x140012442  mov     r8d, 20004h
0x140012448  call    WerpCreateRegistryKey
0x14001244d  mov     edi, eax
0x14001244f  test    eax, eax
0x140012451  js      short loc_1400123FB
0x140012453  mov     rcx, [rbp+arg_10]
0x140012457  lea     rax, [rbp+var_30]
0x14001245b  mov     [rsp+68h+var_40], 0
0x140012464  lea     rdx, aFulllivekernel; "FullLiveKernelReports"
0x14001246b  xor     r9d, r9d
0x14001246e  mov     [rsp+68h+var_48], rax
0x140012473  mov     r8d, 20004h
0x140012479  call    WerpCreateRegistryKey
0x14001247e  mov     edi, eax
0x140012480  test    eax, eax
0x140012482  js      loc_1400123FB
0x140012488  mov     rbx, [rbp+arg_0]
0x14001248c  test    edi, edi
0x14001248e  js      short loc_1400124EB
0x140012490  test    rbx, rbx
0x140012493  jz      short loc_1400124EB
0x140012495  cmp     dword ptr [rbx+4], 1
0x140012499  jnz     short loc_1400124EB
0x14001249b  mov     ecx, [rbx+8]
0x14001249e  cmp     ecx, 206h
0x1400124a4  ja      short loc_1400124EB
0x1400124a6  call    WerpAllocateMem
0x1400124ab  mov     cs:WerKernelLiveReportRootPath.Buffer, rax
0x1400124b2  test    rax, rax
0x1400124b5  jz      short loc_1400124EB
0x1400124b7  movzx   ecx, word ptr [rbx+8]
0x1400124bb  lea     rdx, [rbx+0Ch]; Src
0x1400124bf  sub     cx, 2
0x1400124c3  movzx   r8d, cx; Size
0x1400124c7  mov     cs:WerKernelLiveReportRootPath.Length, r8w
0x1400124cf  movzx   ecx, word ptr [rbx+8]
0x1400124d3  mov     cs:WerKernelLiveReportRootPath.MaximumLength, cx
0x1400124da  mov     rcx, rax; void *
0x1400124dd  call    memmove
0x1400124e2  call    WerpCreateStoreDirectory
0x1400124e7  mov     edi, eax
0x1400124e9  jmp     short loc_140012505
0x1400124eb  lea     rax, aSystemrootLive; "\\SystemRoot\\LiveKernelReports"
0x1400124f2  mov     dword ptr cs:WerKernelLiveReportRootPath.Length, 3C003Ah
0x1400124fc  mov     cs:WerKernelLiveReportRootPath.Buffer, rax
0x140012503  xor     edi, edi
0x140012505  test    rbx, rbx
0x140012508  jz      short loc_140012512
0x14001250a  mov     rcx, rbx
0x14001250d  call    WerpFreeMem
0x140012512  test    rsi, rsi
0x140012515  jz      short loc_14001251F
0x140012517  mov     rcx, rsi
0x14001251a  call    WerpFreeMem
0x14001251f  mov     rcx, [rbp+Handle]; Handle
0x140012523  test    rcx, rcx
0x140012526  jz      short loc_140012534
0x140012528  call    cs:__imp_ZwClose
0x14001252f  nop     dword ptr [rax+rax+00h]
0x140012534  mov     rcx, [rbp+arg_10]; Handle
0x140012538  test    rcx, rcx
0x14001253b  jz      short loc_140012549
0x14001253d  call    cs:__imp_ZwClose
0x140012544  nop     dword ptr [rax+rax+00h]
0x140012549  mov     rcx, [rbp+var_38]; Handle
0x14001254d  test    rcx, rcx
0x140012550  jz      short loc_14001255E
0x140012552  call    cs:__imp_ZwClose
0x140012559  nop     dword ptr [rax+rax+00h]
0x14001255e  mov     rcx, [rbp+var_30]; Handle
0x140012562  test    rcx, rcx
0x140012565  jz      short loc_140012573
0x140012567  call    cs:__imp_ZwClose
0x14001256e  nop     dword ptr [rax+rax+00h]
0x140012573  mov     eax, edi
0x140012575  add     rsp, 68h
0x140012579  pop     rdi
0x14001257a  pop     rsi
0x14001257b  pop     rbx
0x14001257c  pop     rbp
0x14001257d  retn
```
