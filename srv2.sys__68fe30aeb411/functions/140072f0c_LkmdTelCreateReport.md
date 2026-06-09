# LkmdTelCreateReport

- ea: `0x140072f0c`
- end: `0x140073199`
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
- `0x140072f0c`
- `0x140073298`

## import_xrefs

- `ntoskrnl!KeCapturePersistentThreadState` at `0x14007317d`
- `ntoskrnl!KeCapturePersistentThreadState` at `0x14007317d`
- `ntoskrnl!DbgPrintEx` at `0x140073050`
- `ntoskrnl!DbgPrintEx` at `0x14007309f`
- `ntoskrnl!DbgPrintEx` at `0x1400730d2`
- `ntoskrnl!DbgPrintEx` at `0x14007311f`
- `ntoskrnl!DbgPrintEx` at `0x140073050`
- `ntoskrnl!DbgPrintEx` at `0x14007309f`
- `ntoskrnl!DbgPrintEx` at `0x1400730d2`
- `ntoskrnl!DbgPrintEx` at `0x14007311f`
- `ntoskrnl!RtlCaptureContext` at `0x14007313e`
- `ntoskrnl!RtlCaptureContext` at `0x14007313e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140072f72`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140072fbd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140072f72`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140072fbd`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCreateReport` at `0x14007302d`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCreateReport` at `0x14007302d`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCancelReport` at `0x14007307d`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCancelReport` at `0x14007307d`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCloseHandle` at `0x1400730b0`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCloseHandle` at `0x1400730b0`

## string_xrefs

- `0x140073043`: `LKMDTEL: WerLiveKernelCreateReport failed with status 0x%X\n`

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
0x140072f0c  mov     [rsp-8+arg_0], rbx
0x140072f11  mov     [rsp-8+arg_8], rsi
0x140072f16  push    rbp
0x140072f17  push    rdi
0x140072f18  push    r14
0x140072f1a  lea     rbp, [rsp-430h]
0x140072f22  sub     rsp, 530h
0x140072f29  mov     rax, cs:__security_cookie
0x140072f30  xor     rax, rsp
0x140072f33  mov     [rbp+440h+var_20], rax
0x140072f3a  mov     r14, r8
0x140072f3d  lea     rcx, [rsp+540h+ContextRecord]; void *
0x140072f42  mov     r8d, 4D0h; Size
0x140072f48  xor     edx, edx; Val
0x140072f4a  call    memset
0x140072f4f  mov     edi, 88h
0x140072f54  mov     [rsp+540h+var_4F8], 0
0x140072f5d  mov     edx, edi; NumberOfBytes
0x140072f5f  mov     [rsp+540h+var_500], 0
0x140072f67  mov     r8d, 74614454h; Tag
0x140072f6d  mov     ecx, 600h; PoolType
0x140072f72  call    cs:__imp_ExAllocatePoolWithTag
0x140072f79  nop     dword ptr [rax+rax+00h]
0x140072f7e  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140072f85  mov     rbx, rax
0x140072f88  jnz     short loc_140072FA1
0x140072f8a  test    rax, rax
0x140072f8d  jz      short loc_140072FA1
0x140072f8f  mov     r8d, edi; Size
0x140072f92  xor     edx, edx; Val
0x140072f94  mov     rcx, rax; void *
0x140072f97  call    memset
0x140072f9c  mov     rsi, rbx
0x140072f9f  jmp     short loc_140072FAD
0x140072fa1  mov     rsi, rbx
0x140072fa4  test    rbx, rbx
0x140072fa7  jz      loc_140073073
0x140072fad  mov     edx, 40000h; NumberOfBytes
0x140072fb2  mov     ecx, 600h; PoolType
0x140072fb7  mov     r8d, 74614454h; Tag
0x140072fbd  call    cs:__imp_ExAllocatePoolWithTag
0x140072fc4  nop     dword ptr [rax+rax+00h]
0x140072fc9  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140072fd0  mov     rdi, rax
0x140072fd3  jnz     short loc_140072FEF
0x140072fd5  test    rax, rax
0x140072fd8  jz      short loc_140072FEF
0x140072fda  xor     edx, edx; Val
0x140072fdc  mov     r8d, 40000h; Size
0x140072fe2  mov     rcx, rax; void *
0x140072fe5  call    memset
0x140072fea  mov     [rbx], rdi
0x140072fed  jmp     short loc_140072FF7
0x140072fef  mov     [rbx], rdi
0x140072ff2  test    rdi, rdi
0x140072ff5  jz      short loc_14007305C
0x140072ff7  lea     r9, aSmb2reqvf; "SMB2ReqVF"
0x140072ffe  mov     edx, 20h ; ' '; cbDest
0x140073003  lea     r8, aWs; "%ws"
0x14007300a  lea     rcx, [rbx+68h]; pszDest
0x14007300e  call    RtlStringCbPrintfW
0x140073013  test    eax, eax
0x140073015  js      short loc_14007305C
0x140073017  lea     r8, [rsp+540h+var_4F8]
0x14007301c  mov     [rsp+540h+var_500], 1
0x140073024  lea     rdx, [rsp+540h+var_500]
0x140073029  lea     rcx, [rbx+68h]
0x14007302d  call    cs:__imp_WerLiveKernelCreateReport
0x140073034  nop     dword ptr [rax+rax+00h]
0x140073039  test    eax, eax
0x14007303b  jns     loc_140073109
0x140073041  xor     edx, edx; Level
0x140073043  lea     r8, Format; "LKMDTEL: WerLiveKernelCreateReport fail"...
0x14007304a  mov     r9d, eax
0x14007304d  lea     ecx, [rdx+5]; ComponentId
0x140073050  call    cs:__imp_DbgPrintEx
0x140073057  nop     dword ptr [rax+rax+00h]
0x14007305c  mov     rcx, [rbx]
0x14007305f  test    rcx, rcx
0x140073062  jz      short loc_140073069
0x140073064  call    LkmdTelpFreeMem
0x140073069  mov     rcx, rbx
0x14007306c  call    LkmdTelpFreeMem
0x140073071  xor     esi, esi
0x140073073  mov     rcx, [rsp+540h+var_4F8]
0x140073078  test    rcx, rcx
0x14007307b  jz      short loc_1400730DE
0x14007307d  call    cs:__imp_WerLiveKernelCancelReport
0x140073084  nop     dword ptr [rax+rax+00h]
0x140073089  test    eax, eax
0x14007308b  jns     short loc_1400730AB
0x14007308d  mov     edx, 1; Level
0x140073092  lea     r8, aLkmdtelWerlive; "LKMDTEL: WerLiveCancelReport failed, st"...
0x140073099  mov     r9d, eax
0x14007309c  lea     ecx, [rdx+4]; ComponentId
0x14007309f  call    cs:__imp_DbgPrintEx
0x1400730a6  nop     dword ptr [rax+rax+00h]
0x1400730ab  mov     rcx, [rsp+540h+var_4F8]
0x1400730b0  call    cs:__imp_WerLiveKernelCloseHandle
0x1400730b7  nop     dword ptr [rax+rax+00h]
0x1400730bc  test    eax, eax
0x1400730be  jns     short loc_1400730DE
0x1400730c0  mov     edx, 1; Level
0x1400730c5  lea     r8, aLkmdtelWerlive; "LKMDTEL: WerLiveCancelReport failed, st"...
0x1400730cc  mov     r9d, eax
0x1400730cf  lea     ecx, [rdx+4]; ComponentId
0x1400730d2  call    cs:__imp_DbgPrintEx
0x1400730d9  nop     dword ptr [rax+rax+00h]
0x1400730de  mov     rax, rsi
0x1400730e1  mov     rcx, [rbp+440h+var_20]
0x1400730e8  xor     rcx, rsp; StackCookie
0x1400730eb  call    __security_check_cookie
0x1400730f0  lea     r11, [rsp+540h+var_10]
0x1400730f8  mov     rbx, [r11+20h]
0x1400730fc  mov     rsi, [r11+28h]
0x140073100  mov     rsp, r11
0x140073103  pop     r14
0x140073105  pop     rdi
0x140073106  pop     rbp
0x140073107  retn
0x140073109  cmp     [rsp+540h+var_500], 0
0x14007310e  jnz     short loc_140073130
0x140073110  mov     edx, 1; Level
0x140073115  lea     r8, aLkmdtelWerpoli; "LKMDTEL: WerPolicy is WerLiveKernelPoli"...
0x14007311c  lea     ecx, [rdx+4]; ComponentId
0x14007311f  call    cs:__imp_DbgPrintEx
0x140073126  nop     dword ptr [rax+rax+00h]
0x14007312b  jmp     loc_14007305C
0x140073130  mov     rax, [rsp+540h+var_4F8]
0x140073135  lea     rcx, [rsp+540h+ContextRecord]; ContextRecord
0x14007313a  mov     [rbx+60h], rax
0x14007313e  call    cs:__imp_RtlCaptureContext
0x140073145  nop     dword ptr [rax+rax+00h]
0x14007314a  mov     rax, [rbx]
0x14007314d  lea     rcx, [rsp+540h+ContextRecord]
0x140073152  mov     [rsp+540h+var_508], rax
0x140073157  mov     r9, r14
0x14007315a  mov     [rsp+540h+var_510], 0
0x140073163  xor     edx, edx
0x140073165  mov     [rsp+540h+var_518], 0
0x14007316e  mov     r8d, 1FAh
0x140073174  mov     [rsp+540h+var_520], 0
0x14007317d  call    cs:__imp_KeCapturePersistentThreadState
0x140073184  nop     dword ptr [rax+rax+00h]
0x140073189  test    eax, eax
0x14007318b  jz      loc_14007305C
0x140073191  mov     [rbx+8], eax
0x140073194  jmp     loc_1400730DE
```
