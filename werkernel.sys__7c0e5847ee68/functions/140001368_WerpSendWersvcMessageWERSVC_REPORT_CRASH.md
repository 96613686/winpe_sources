# WerpSendWersvcMessageWERSVC_REPORT_CRASH

- ea: `0x140001368`
- end: `0x1400015aa`
- name: `WerpSendWersvcMessageWERSVC_REPORT_CRASH`
- size: `578`
- prototype: `__int64 __fastcall(PVOID *, __int64, int, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c010`

## callees

- `0x1400011a0`
- `0x140001368`
- `0x140002c40`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1400014be`
- `ntoskrnl!DbgPrintEx` at `0x1400014da`
- `ntoskrnl!DbgPrintEx` at `0x14000155a`
- `ntoskrnl!DbgPrintEx` at `0x14000157a`
- `ntoskrnl!DbgPrintEx` at `0x1400014be`
- `ntoskrnl!DbgPrintEx` at `0x1400014da`
- `ntoskrnl!DbgPrintEx` at `0x14000155a`
- `ntoskrnl!DbgPrintEx` at `0x14000157a`
- `ntoskrnl!ZwDuplicateObject` at `0x140001420`
- `ntoskrnl!ZwDuplicateObject` at `0x140001420`
- `ntoskrnl!PsProcessType` at `0x1400014f0`
- `ntoskrnl!ObCloseHandle` at `0x140001490`
- `ntoskrnl!ObCloseHandle` at `0x140001490`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140001522`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140001522`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000139c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000139c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000158e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000158e`

## pseudocode

```c
__int64 __fastcall WerpSendWersvcMessageWERSVC_REPORT_CRASH(PVOID *a1, __int64 a2, int a3, int a4, __int64 a5)
{
  char *PoolWithTag; // rax
  char *v10; // rbx
  __int64 v11; // rcx
  NTSTATUS v13; // edi
  int v14; // eax
  void *v15; // rcx
  void *TargetHandle; // [rsp+40h] [rbp-48h] BYREF
  PVOID Object; // [rsp+48h] [rbp-40h] BYREF

  TargetHandle = 0;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1025, 0xAF0u, 0x4D534B57u);
  v10 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
      goto LABEL_4;
    return 3221225626LL;
  }
  if ( !PoolWithTag )
    return 3221225626LL;
  memset(PoolWithTag, 0, 0xAF0u);
LABEL_4:
  *(_DWORD *)v10 = 91751760;
  *((_WORD *)v10 + 2) = 0x8000;
  *((_DWORD *)v10 + 10) = 0x20000000;
  *((_QWORD *)v10 + 7) = a2;
  *((_DWORD *)v10 + 12) = a3;
  *((_DWORD *)v10 + 13) = a4;
  *((_QWORD *)v10 + 8) = (unsigned int)a2;
  if ( ZwDuplicateObject(
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         &TargetHandle,
         0x101000u,
         2u,
         8u) < 0 )
  {
    *((_QWORD *)v10 + 9) = 0;
    v11 = 72;
    TargetHandle = 0;
  }
  else
  {
    v11 = 80;
    *((_QWORD *)v10 + 9) = (unsigned int)TargetHandle;
  }
  if ( a5 )
    *(_QWORD *)&v10[v11] = (unsigned int)a5;
  v13 = WerpSendWersvcMessage(v10 + 1400, v10);
  if ( TargetHandle )
    ObCloseHandle(TargetHandle, 1);
  if ( v13 < 0 )
  {
    DbgPrintEx(
      5u,
      0,
      "WERKERNELHOST: WerpSendWersvcMessageWERSVC_REPORT_CRASH: WerpSendWersvcMessage returned NTSTATUS %08X\n",
      v13);
  }
  else
  {
    DbgPrintEx(
      5u,
      3u,
      "WERKERNELHOST: WerpSendWersvcMessageWERSVC_REPORT_CRASH: Response message ID: %08X.\n",
      *((_DWORD *)v10 + 360));
    DbgPrintEx(
      5u,
      3u,
      "WERKERNELHOST: WerpSendWersvcMessageWERSVC_REPORT_CRASH: Response message status: NTSTATUS %08X.\n",
      *((_DWORD *)v10 + 361));
    v14 = *((_DWORD *)v10 + 360);
    if ( v14 == 536870914 )
    {
      v15 = (void *)*((_QWORD *)v10 + 181);
      Object = 0;
      v13 = ObReferenceObjectByHandle(v15, 0x100000u, (POBJECT_TYPE)PsProcessType, 1, &Object, 0);
      *a1 = Object;
      if ( v13 < 0 )
        *a1 = 0;
    }
    else if ( v14 == 536870916 )
    {
      DbgPrintEx(
        5u,
        0,
        "WERKERNELHOST: WerpSendWersvcMessageWERSVC_REPORT_CRASH: WERSVC_CRASH_REPORTING_FAILED with NTSTATUS %08X\n",
        v13);
      v13 = *((_DWORD *)v10 + 361);
    }
  }
  ExFreePoolWithTag(v10, 0x4D534B57u);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140001368  push    rbx
0x14000136a  push    rbp
0x14000136b  push    rsi
0x14000136c  push    rdi
0x14000136d  push    r14
0x14000136f  push    r15
0x140001371  sub     rsp, 58h
0x140001375  mov     r15d, r8d
0x140001378  mov     [rsp+88h+TargetHandle], 0
0x140001381  mov     rdi, rdx
0x140001384  mov     r14, rcx
0x140001387  mov     ebp, 0AF0h
0x14000138c  mov     r8d, 4D534B57h; Tag
0x140001392  mov     edx, ebp; NumberOfBytes
0x140001394  mov     ecx, 401h; PoolType
0x140001399  mov     esi, r9d
0x14000139c  call    cs:__imp_ExAllocatePoolWithTag
0x1400013a3  nop     dword ptr [rax+rax+00h]
0x1400013a8  cmp     cs:ExPoolZeroingNativelySupported, 0
0x1400013af  mov     rbx, rax
0x1400013b2  jnz     loc_14000143F
0x1400013b8  test    rax, rax
0x1400013bb  jz      loc_140001444
0x1400013c1  mov     r8d, ebp; Size
0x1400013c4  xor     edx, edx; Val
0x1400013c6  mov     rcx, rax; void *
0x1400013c9  call    memset
0x1400013ce  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x1400013d2  mov     eax, edi
0x1400013d4  mov     [rsp+88h+Options], 8; Options
0x1400013dc  lea     r9, [rsp+88h+TargetHandle]; TargetHandle
0x1400013e1  mov     dword ptr [rbx], 5780550h
0x1400013e7  lea     rbp, [rbx+578h]
0x1400013ee  mov     word ptr [rbx+4], 8000h
0x1400013f4  mov     r8, rcx; TargetProcessHandle
0x1400013f7  mov     dword ptr [rbx+28h], 20000000h
0x1400013fe  mov     rdx, rcx; SourceHandle
0x140001401  mov     [rbx+38h], rdi
0x140001405  mov     [rbx+30h], r15d
0x140001409  mov     [rbx+34h], esi
0x14000140c  mov     [rsp+88h+HandleAttributes], 2; HandleAttributes
0x140001414  mov     [rbx+40h], rax
0x140001418  mov     [rsp+88h+DesiredAccess], 101000h; DesiredAccess
0x140001420  call    cs:__imp_ZwDuplicateObject
0x140001427  nop     dword ptr [rax+rax+00h]
0x14000142c  test    eax, eax
0x14000142e  js      short loc_14000144E
0x140001430  mov     eax, dword ptr [rsp+88h+TargetHandle]
0x140001434  mov     ecx, 50h ; 'P'
0x140001439  mov     [rbx+48h], rax
0x14000143d  jmp     short loc_140001464
0x14000143f  test    rbx, rbx
0x140001442  jnz     short loc_1400013CE
0x140001444  mov     eax, 0C000009Ah
0x140001449  jmp     loc_14000159C
0x14000144e  mov     qword ptr [rbx+48h], 0
0x140001456  mov     ecx, 48h ; 'H'
0x14000145b  mov     [rsp+88h+TargetHandle], 0
0x140001464  mov     rax, [rsp+88h+arg_20]
0x14000146c  test    rax, rax
0x14000146f  jz      short loc_140001477
0x140001471  mov     eax, eax
0x140001473  mov     [rbx+rcx], rax
0x140001477  mov     rdx, rbx
0x14000147a  mov     rcx, rbp
0x14000147d  call    WerpSendWersvcMessage
0x140001482  mov     rcx, [rsp+88h+TargetHandle]; Handle
0x140001487  mov     edi, eax
0x140001489  test    rcx, rcx
0x14000148c  jz      short loc_14000149C
0x14000148e  mov     dl, 1; PreviousMode
0x140001490  call    cs:__imp_ObCloseHandle
0x140001497  nop     dword ptr [rax+rax+00h]
0x14000149c  test    edi, edi
0x14000149e  js      loc_14000156B
0x1400014a4  mov     r9d, [rbp+28h]
0x1400014a8  lea     r8, aWerkernelhostW_40; "WERKERNELHOST: WerpSendWersvcMessageWER"...
0x1400014af  mov     r15d, 3
0x1400014b5  mov     edx, r15d; Level
0x1400014b8  lea     esi, [r15+2]
0x1400014bc  mov     ecx, esi; ComponentId
0x1400014be  call    cs:__imp_DbgPrintEx
0x1400014c5  nop     dword ptr [rax+rax+00h]
0x1400014ca  mov     r9d, [rbp+2Ch]
0x1400014ce  lea     r8, aWerkernelhostW_41; "WERKERNELHOST: WerpSendWersvcMessageWER"...
0x1400014d5  mov     edx, r15d; Level
0x1400014d8  mov     ecx, esi; ComponentId
0x1400014da  call    cs:__imp_DbgPrintEx
0x1400014e1  nop     dword ptr [rax+rax+00h]
0x1400014e6  mov     eax, [rbp+28h]
0x1400014e9  cmp     eax, 20000002h
0x1400014ee  jnz     short loc_140001545
0x1400014f0  mov     r8, cs:__imp_PsProcessType
0x1400014f7  lea     rax, [rsp+88h+Object]
0x1400014fc  mov     rcx, [rbp+30h]; Handle
0x140001500  mov     r9b, 1; AccessMode
0x140001503  mov     qword ptr [rsp+88h+HandleAttributes], 0; HandleInformation
0x14000150c  mov     edx, 100000h; DesiredAccess
0x140001511  mov     [rsp+88h+Object], 0
0x14000151a  mov     r8, [r8]; ObjectType
0x14000151d  mov     qword ptr [rsp+88h+DesiredAccess], rax; Object
0x140001522  call    cs:__imp_ObReferenceObjectByHandle
0x140001529  nop     dword ptr [rax+rax+00h]
0x14000152e  mov     edi, eax
0x140001530  mov     rax, [rsp+88h+Object]
0x140001535  mov     [r14], rax
0x140001538  test    edi, edi
0x14000153a  jns     short loc_140001586
0x14000153c  mov     qword ptr [r14], 0
0x140001543  jmp     short loc_140001586
0x140001545  cmp     eax, 20000004h
0x14000154a  jnz     short loc_140001586
0x14000154c  mov     r9d, edi
0x14000154f  lea     r8, aWerkernelhostW_50; "WERKERNELHOST: WerpSendWersvcMessageWER"...
0x140001556  xor     edx, edx; Level
0x140001558  mov     ecx, esi; ComponentId
0x14000155a  call    cs:__imp_DbgPrintEx
0x140001561  nop     dword ptr [rax+rax+00h]
0x140001566  mov     edi, [rbp+2Ch]
0x140001569  jmp     short loc_140001586
0x14000156b  xor     edx, edx; Level
0x14000156d  lea     r8, aWerkernelhostW_45; "WERKERNELHOST: WerpSendWersvcMessageWER"...
0x140001574  mov     r9d, edi
0x140001577  lea     ecx, [rdx+5]; ComponentId
0x14000157a  call    cs:__imp_DbgPrintEx
0x140001581  nop     dword ptr [rax+rax+00h]
0x140001586  mov     edx, 4D534B57h; Tag
0x14000158b  mov     rcx, rbx; P
0x14000158e  call    cs:__imp_ExFreePoolWithTag
0x140001595  nop     dword ptr [rax+rax+00h]
0x14000159a  mov     eax, edi
0x14000159c  add     rsp, 58h
0x1400015a0  pop     r15
0x1400015a2  pop     r14
0x1400015a4  pop     rdi
0x1400015a5  pop     rsi
0x1400015a6  pop     rbp
0x1400015a7  pop     rbx
0x1400015a8  retn
```
