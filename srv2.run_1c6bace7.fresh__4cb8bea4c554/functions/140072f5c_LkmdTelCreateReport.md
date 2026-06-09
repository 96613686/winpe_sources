# LkmdTelCreateReport

- ea: `0x140072f5c`
- end: `0x1400731e9`
- name: `LkmdTelCreateReport`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14001d724`

## callees

- `0x14001b5a8`
- `0x140038490`
- `0x140038980`
- `0x140072f5c`
- `0x1400732e8`

## import_xrefs

- `ntoskrnl!KeCapturePersistentThreadState` at `0x1400731cd`
- `ntoskrnl!KeCapturePersistentThreadState` at `0x1400731cd`
- `ntoskrnl!DbgPrintEx` at `0x1400730a0`
- `ntoskrnl!DbgPrintEx` at `0x1400730ef`
- `ntoskrnl!DbgPrintEx` at `0x140073122`
- `ntoskrnl!DbgPrintEx` at `0x14007316f`
- `ntoskrnl!DbgPrintEx` at `0x1400730a0`
- `ntoskrnl!DbgPrintEx` at `0x1400730ef`
- `ntoskrnl!DbgPrintEx` at `0x140073122`
- `ntoskrnl!DbgPrintEx` at `0x14007316f`
- `ntoskrnl!RtlCaptureContext` at `0x14007318e`
- `ntoskrnl!RtlCaptureContext` at `0x14007318e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140072fc2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14007300d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140072fc2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14007300d`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCreateReport` at `0x14007307d`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCreateReport` at `0x14007307d`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCancelReport` at `0x1400730cd`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCancelReport` at `0x1400730cd`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCloseHandle` at `0x140073100`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCloseHandle` at `0x140073100`

## string_xrefs

- `0x140073093`: `LKMDTEL: WerLiveKernelCreateReport failed with status 0x%X\n`

## pseudocode

```c
wchar_t *__fastcall LkmdTelCreateReport(__int64 a1, __int64 a2, __int64 a3)
{
  wchar_t *PoolWithTag; // rax
  wchar_t *v5; // rbx
  wchar_t *v6; // rsi
  PVOID v7; // rax
  PVOID v8; // rdi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v13; // eax
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  CONTEXT ContextRecord; // [rsp+50h] [rbp-B0h] BYREF

  memset(&ContextRecord, 0, sizeof(ContextRecord));
  v15 = 0;
  v14 = 0;
  PoolWithTag = (wchar_t *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x88u, 0x74614454u);
  v5 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
  {
    memset(PoolWithTag, 0, 0x88u);
    v6 = v5;
LABEL_5:
    v7 = ExAllocatePoolWithTag((POOL_TYPE)1536, 0x40000u, 0x74614454u);
    v8 = v7;
    if ( ExPoolZeroingNativelySupported || !v7 )
    {
      *(_QWORD *)v5 = v7;
      if ( !v7 )
      {
LABEL_12:
        if ( *(_QWORD *)v5 )
          ((void (*)(void))LkmdTelpFreeMem)();
        LkmdTelpFreeMem(v5);
        v6 = 0;
        goto LABEL_15;
      }
    }
    else
    {
      memset(v7, 0, 0x40000u);
      *(_QWORD *)v5 = v8;
    }
    if ( RtlStringCbPrintfW(v5 + 52, 0x20u, L"%ws", L"SMB2ReqVF") >= 0 )
    {
      v14 = 1;
      v9 = WerLiveKernelCreateReport(v5 + 52, &v14, &v15);
      if ( v9 >= 0 )
      {
        if ( v14 )
        {
          *((_QWORD *)v5 + 12) = v15;
          RtlCaptureContext(&ContextRecord);
          v13 = KeCapturePersistentThreadState(&ContextRecord, 0, 506, a3, 0, 0, 0, *(_QWORD *)v5);
          if ( v13 )
          {
            *((_DWORD *)v5 + 2) = v13;
            return v6;
          }
        }
        else
        {
          DbgPrintEx(5u, 1u, "LKMDTEL: WerPolicy is WerLiveKernelPolicyNoDump, no dump is allowed.\n");
        }
      }
      else
      {
        DbgPrintEx(5u, 0, "LKMDTEL: WerLiveKernelCreateReport failed with status 0x%X\n", v9);
      }
    }
    goto LABEL_12;
  }
  v6 = PoolWithTag;
  if ( PoolWithTag )
    goto LABEL_5;
LABEL_15:
  if ( v15 )
  {
    v10 = WerLiveKernelCancelReport();
    if ( v10 < 0 )
      DbgPrintEx(5u, 1u, "LKMDTEL: WerLiveCancelReport failed, status 0x%X\n", v10);
    v11 = WerLiveKernelCloseHandle(v15);
    if ( v11 < 0 )
      DbgPrintEx(5u, 1u, "LKMDTEL: WerLiveCancelReport failed, status 0x%X\n", v11);
  }
  return v6;
}

```

## disassembly

```asm
0x140072f5c  mov     [rsp-8+arg_0], rbx
0x140072f61  mov     [rsp-8+arg_8], rsi
0x140072f66  push    rbp
0x140072f67  push    rdi
0x140072f68  push    r14
0x140072f6a  lea     rbp, [rsp-430h]
0x140072f72  sub     rsp, 530h
0x140072f79  mov     rax, cs:__security_cookie
0x140072f80  xor     rax, rsp
0x140072f83  mov     [rbp+440h+var_20], rax
0x140072f8a  mov     r14, r8
0x140072f8d  lea     rcx, [rsp+540h+ContextRecord]; void *
0x140072f92  mov     r8d, 4D0h; Size
0x140072f98  xor     edx, edx; Val
0x140072f9a  call    memset
0x140072f9f  mov     edi, 88h
0x140072fa4  mov     [rsp+540h+var_4F8], 0
0x140072fad  mov     edx, edi; NumberOfBytes
0x140072faf  mov     [rsp+540h+var_500], 0
0x140072fb7  mov     r8d, 74614454h; Tag
0x140072fbd  mov     ecx, 600h; PoolType
0x140072fc2  call    cs:__imp_ExAllocatePoolWithTag
0x140072fc9  nop     dword ptr [rax+rax+00h]
0x140072fce  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140072fd5  mov     rbx, rax
0x140072fd8  jnz     short loc_140072FF1
0x140072fda  test    rax, rax
0x140072fdd  jz      short loc_140072FF1
0x140072fdf  mov     r8d, edi; Size
0x140072fe2  xor     edx, edx; Val
0x140072fe4  mov     rcx, rax; void *
0x140072fe7  call    memset
0x140072fec  mov     rsi, rbx
0x140072fef  jmp     short loc_140072FFD
0x140072ff1  mov     rsi, rbx
0x140072ff4  test    rbx, rbx
0x140072ff7  jz      loc_1400730C3
0x140072ffd  mov     edx, 40000h; NumberOfBytes
0x140073002  mov     ecx, 600h; PoolType
0x140073007  mov     r8d, 74614454h; Tag
0x14007300d  call    cs:__imp_ExAllocatePoolWithTag
0x140073014  nop     dword ptr [rax+rax+00h]
0x140073019  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140073020  mov     rdi, rax
0x140073023  jnz     short loc_14007303F
0x140073025  test    rax, rax
0x140073028  jz      short loc_14007303F
0x14007302a  xor     edx, edx; Val
0x14007302c  mov     r8d, 40000h; Size
0x140073032  mov     rcx, rax; void *
0x140073035  call    memset
0x14007303a  mov     [rbx], rdi
0x14007303d  jmp     short loc_140073047
0x14007303f  mov     [rbx], rdi
0x140073042  test    rdi, rdi
0x140073045  jz      short loc_1400730AC
0x140073047  lea     r9, aSmb2reqvf; "SMB2ReqVF"
0x14007304e  mov     edx, 20h ; ' '; cbDest
0x140073053  lea     r8, aWs; "%ws"
0x14007305a  lea     rcx, [rbx+68h]; pszDest
0x14007305e  call    RtlStringCbPrintfW
0x140073063  test    eax, eax
0x140073065  js      short loc_1400730AC
0x140073067  lea     r8, [rsp+540h+var_4F8]
0x14007306c  mov     [rsp+540h+var_500], 1
0x140073074  lea     rdx, [rsp+540h+var_500]
0x140073079  lea     rcx, [rbx+68h]
0x14007307d  call    cs:__imp_WerLiveKernelCreateReport
0x140073084  nop     dword ptr [rax+rax+00h]
0x140073089  test    eax, eax
0x14007308b  jns     loc_140073159
0x140073091  xor     edx, edx; Level
0x140073093  lea     r8, Format; "LKMDTEL: WerLiveKernelCreateReport fail"...
0x14007309a  mov     r9d, eax
0x14007309d  lea     ecx, [rdx+5]; ComponentId
0x1400730a0  call    cs:__imp_DbgPrintEx
0x1400730a7  nop     dword ptr [rax+rax+00h]
0x1400730ac  mov     rcx, [rbx]
0x1400730af  test    rcx, rcx
0x1400730b2  jz      short loc_1400730B9
0x1400730b4  call    LkmdTelpFreeMem
0x1400730b9  mov     rcx, rbx
0x1400730bc  call    LkmdTelpFreeMem
0x1400730c1  xor     esi, esi
0x1400730c3  mov     rcx, [rsp+540h+var_4F8]
0x1400730c8  test    rcx, rcx
0x1400730cb  jz      short loc_14007312E
0x1400730cd  call    cs:__imp_WerLiveKernelCancelReport
0x1400730d4  nop     dword ptr [rax+rax+00h]
0x1400730d9  test    eax, eax
0x1400730db  jns     short loc_1400730FB
0x1400730dd  mov     edx, 1; Level
0x1400730e2  lea     r8, aLkmdtelWerlive; "LKMDTEL: WerLiveCancelReport failed, st"...
0x1400730e9  mov     r9d, eax
0x1400730ec  lea     ecx, [rdx+4]; ComponentId
0x1400730ef  call    cs:__imp_DbgPrintEx
0x1400730f6  nop     dword ptr [rax+rax+00h]
0x1400730fb  mov     rcx, [rsp+540h+var_4F8]
0x140073100  call    cs:__imp_WerLiveKernelCloseHandle
0x140073107  nop     dword ptr [rax+rax+00h]
0x14007310c  test    eax, eax
0x14007310e  jns     short loc_14007312E
0x140073110  mov     edx, 1; Level
0x140073115  lea     r8, aLkmdtelWerlive; "LKMDTEL: WerLiveCancelReport failed, st"...
0x14007311c  mov     r9d, eax
0x14007311f  lea     ecx, [rdx+4]; ComponentId
0x140073122  call    cs:__imp_DbgPrintEx
0x140073129  nop     dword ptr [rax+rax+00h]
0x14007312e  mov     rax, rsi
0x140073131  mov     rcx, [rbp+440h+var_20]
0x140073138  xor     rcx, rsp; StackCookie
0x14007313b  call    __security_check_cookie
0x140073140  lea     r11, [rsp+540h+var_10]
0x140073148  mov     rbx, [r11+20h]
0x14007314c  mov     rsi, [r11+28h]
0x140073150  mov     rsp, r11
0x140073153  pop     r14
0x140073155  pop     rdi
0x140073156  pop     rbp
0x140073157  retn
0x140073159  cmp     [rsp+540h+var_500], 0
0x14007315e  jnz     short loc_140073180
0x140073160  mov     edx, 1; Level
0x140073165  lea     r8, aLkmdtelWerpoli; "LKMDTEL: WerPolicy is WerLiveKernelPoli"...
0x14007316c  lea     ecx, [rdx+4]; ComponentId
0x14007316f  call    cs:__imp_DbgPrintEx
0x140073176  nop     dword ptr [rax+rax+00h]
0x14007317b  jmp     loc_1400730AC
0x140073180  mov     rax, [rsp+540h+var_4F8]
0x140073185  lea     rcx, [rsp+540h+ContextRecord]; ContextRecord
0x14007318a  mov     [rbx+60h], rax
0x14007318e  call    cs:__imp_RtlCaptureContext
0x140073195  nop     dword ptr [rax+rax+00h]
0x14007319a  mov     rax, [rbx]
0x14007319d  lea     rcx, [rsp+540h+ContextRecord]
0x1400731a2  mov     [rsp+540h+var_508], rax
0x1400731a7  mov     r9, r14
0x1400731aa  mov     [rsp+540h+var_510], 0
0x1400731b3  xor     edx, edx
0x1400731b5  mov     [rsp+540h+var_518], 0
0x1400731be  mov     r8d, 1FAh
0x1400731c4  mov     [rsp+540h+var_520], 0
0x1400731cd  call    cs:__imp_KeCapturePersistentThreadState
0x1400731d4  nop     dword ptr [rax+rax+00h]
0x1400731d9  test    eax, eax
0x1400731db  jz      loc_1400730AC
0x1400731e1  mov     [rbx+8], eax
0x1400731e4  jmp     loc_14007312E
```
