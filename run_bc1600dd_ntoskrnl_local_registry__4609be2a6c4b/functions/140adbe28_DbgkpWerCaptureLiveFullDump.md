# DbgkpWerCaptureLiveFullDump

- ea: `0x140adbe28`
- end: `0x140adc044`
- name: `DbgkpWerCaptureLiveFullDump`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1407522b4`

## callees

- `0x1402a2f90`
- `0x140500334`
- `0x14075230c`
- `0x140adbe28`
- `0x140adc04c`
- `0x140adc110`
- `0x140bb1410`

## import_xrefs

- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelSubmitReport` at `0x140adbfd7`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelSubmitReport` at `0x140adbfd7`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x140adbf2b`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x140adbf2b`

## string_xrefs

- `0x140adbe44`: `DBGK: Creating full dump.  ComponentName %ws, Defer = %d\n`
- `0x140adbf3d`: `DBGK: WerLiveKernelOpenDumpFile failed. Status = 0x%X\n`

## pseudocode

```c
__int64 __fastcall DbgkpWerCaptureLiveFullDump(__int64 a1, _BYTE *a2)
{
  unsigned int v3; // eax
  __int64 Pool2; // rax
  __int64 v6; // rsi
  int started; // ebx
  int v8; // edx
  int v9; // eax
  int v10; // eax
  const CHAR *v11; // r8
  __int64 v13; // [rsp+60h] [rbp+8h] BYREF
  __int64 v14; // [rsp+68h] [rbp+10h] BYREF

  v13 = 0;
  v14 = 0;
  v3 = *(_DWORD *)(a1 + 104);
  *a2 = 1;
  *(_DWORD *)(a1 + 80) = 0x10000000;
  DbgPrintEx(5u, 3u, "DBGK: Creating full dump.  ComponentName %ws, Defer = %d\n", a1, (v3 >> 1) & 1);
  Pool2 = ExAllocatePool2(256, 56, 1466393156);
  v6 = Pool2;
  if ( !Pool2 )
  {
    DbgPrintEx(5u, 0, "DBGK: Could not allocate an Io Control.\n");
    return (unsigned int)-1073741801;
  }
  *(_QWORD *)(a1 + 120) = Pool2;
  v8 = *(_DWORD *)(Pool2 + 24);
  *(_DWORD *)Pool2 = 2;
  *(_DWORD *)(Pool2 + 4) = 56;
  *(_QWORD *)(Pool2 + 48) = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 32LL);
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 72) + 24LL) & 1) != 0 )
  {
    v8 |= 4u;
    *(_DWORD *)(Pool2 + 24) = v8;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 72) + 24LL) & 0x10) != 0 )
  {
    v8 |= 0x20u;
    *(_DWORD *)(Pool2 + 24) = v8;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 72) + 24LL) & 4) != 0 )
    *(_DWORD *)(Pool2 + 28) |= 1u;
  *(_DWORD *)(Pool2 + 24) = v8 | 0x10;
  v9 = *(_DWORD *)(a1 + 104);
  v13 = 0;
  if ( (v9 & 2) != 0 )
  {
    *(_DWORD *)(v6 + 24) |= 8u;
    started = DbgkpWerInitializeDeferredLiveDump(a1);
    if ( started < 0 )
      return (unsigned int)started;
  }
  else
  {
    v10 = WerLiveKernelOpenDumpFile(*(_QWORD *)(a1 + 96), &v13);
    started = v10;
    if ( v10 < 0 )
    {
      v11 = "DBGK: WerLiveKernelOpenDumpFile failed. Status = 0x%X\n";
      goto LABEL_12;
    }
    *(_QWORD *)(v6 + 8) = v13;
  }
  started = DbgkpWerInvokeCallbacks(a1);
  if ( started < 0 )
    return (unsigned int)started;
  started = IoCaptureLiveDump(
              *(_DWORD *)(a1 + 32),
              *(_QWORD *)(a1 + 40),
              *(_QWORD *)(a1 + 48),
              *(_QWORD *)(a1 + 56),
              *(_QWORD *)(a1 + 64),
              v6,
              (__int64)&v14);
  if ( (*(_DWORD *)(a1 + 104) & 2) == 0 )
  {
    if ( started >= 0 )
    {
      v10 = WerLiveKernelSubmitReport(*(_QWORD *)(a1 + 96), 0);
      started = v10;
      if ( v10 >= 0 )
      {
        *(_DWORD *)(a1 + 104) |= 1u;
        return (unsigned int)started;
      }
      v11 = "DBGK: DbgkpWerCaptureLiveFullDump: WerLiveKernelSubmitReport failed with status 0x%X\n";
LABEL_12:
      DbgPrintEx(5u, 0, v11, (unsigned int)v10);
      return (unsigned int)started;
    }
LABEL_19:
    DbgPrintEx(
      5u,
      0,
      "DBGK: DbgkpWerCaptureLiveFullDump: IoCaptureLiveDump failed with status 0x%X\n",
      (unsigned int)started);
    return (unsigned int)started;
  }
  if ( (int)(started + 0x80000000) >= 0 && started != -1073741802 )
    goto LABEL_19;
  *(_QWORD *)(a1 + 128) = v14;
  started = DbgkpWerStartDeferredLiveDump(a1);
  if ( started >= 0 )
    *a2 = 0;
  return (unsigned int)started;
}

```

## disassembly

```asm
0x140adbe28  mov     rax, rsp
0x140adbe2b  mov     [rax+18h], rbx
0x140adbe2f  mov     [rax+20h], rsi
0x140adbe33  push    rdi
0x140adbe34  push    r14
0x140adbe36  push    r15
0x140adbe38  sub     rsp, 40h
0x140adbe3c  mov     qword ptr [rax+8], 0
0x140adbe44  lea     r8, aDbgkCreatingFu; "DBGK: Creating full dump.  ComponentNam"...
0x140adbe4b  mov     qword ptr [rax+10h], 0
0x140adbe53  mov     r14, rdx
0x140adbe56  mov     eax, [rcx+68h]
0x140adbe59  mov     rdi, rcx
0x140adbe5c  mov     byte ptr [rdx], 1
0x140adbe5f  mov     r9, rcx
0x140adbe62  mov     edx, 3; Level
0x140adbe67  shr     eax, 1
0x140adbe69  mov     dword ptr [rcx+50h], 10000000h
0x140adbe70  and     eax, 1
0x140adbe73  mov     dword ptr [rsp+58h+var_38], eax
0x140adbe77  lea     r15d, [rdx+2]
0x140adbe7b  mov     ecx, r15d; ComponentId
0x140adbe7e  call    DbgPrintEx
0x140adbe83  lea     ebx, [r15+33h]
0x140adbe87  mov     r8d, 57676244h
0x140adbe8d  mov     edx, ebx
0x140adbe8f  mov     ecx, 100h
0x140adbe94  call    ExAllocatePool2
0x140adbe99  mov     rsi, rax
0x140adbe9c  test    rax, rax
0x140adbe9f  jnz     short loc_140ADBEBC
0x140adbea1  lea     r8, aDbgkCouldNotAl_1; "DBGK: Could not allocate an Io Control."...
0x140adbea8  xor     edx, edx; Level
0x140adbeaa  mov     ecx, r15d; ComponentId
0x140adbead  call    DbgPrintEx
0x140adbeb2  mov     ebx, 0C0000017h
0x140adbeb7  jmp     loc_140ADC02D
0x140adbebc  mov     [rdi+78h], rsi
0x140adbec0  mov     edx, [rsi+18h]
0x140adbec3  mov     dword ptr [rax], 2
0x140adbec9  mov     [rax+4], ebx
0x140adbecc  mov     rax, [rdi+48h]
0x140adbed0  mov     rcx, [rax+20h]
0x140adbed4  mov     [rsi+30h], rcx
0x140adbed8  mov     rax, [rdi+48h]
0x140adbedc  mov     ecx, [rax+18h]
0x140adbedf  test    cl, 1
0x140adbee2  jz      short loc_140ADBEEA
0x140adbee4  or      edx, 4
0x140adbee7  mov     [rsi+18h], edx
0x140adbeea  mov     rax, [rdi+48h]
0x140adbeee  mov     ecx, [rax+18h]
0x140adbef1  test    cl, 10h
0x140adbef4  jz      short loc_140ADBEFC
0x140adbef6  or      edx, 20h
0x140adbef9  mov     [rsi+18h], edx
0x140adbefc  mov     rax, [rdi+48h]
0x140adbf00  mov     ecx, [rax+18h]
0x140adbf03  test    cl, 4
0x140adbf06  jz      short loc_140ADBF0C
0x140adbf08  or      dword ptr [rsi+1Ch], 1
0x140adbf0c  or      edx, 10h
0x140adbf0f  mov     [rsi+18h], edx
0x140adbf12  mov     eax, [rdi+68h]
0x140adbf15  mov     [rsp+58h+arg_0], 0
0x140adbf1e  test    al, 2
0x140adbf20  jnz     short loc_140ADBF61
0x140adbf22  mov     rcx, [rdi+60h]
0x140adbf26  lea     rdx, [rsp+58h+arg_0]
0x140adbf2b  call    cs:__imp_WerLiveKernelOpenDumpFile
0x140adbf32  nop     dword ptr [rax+rax+00h]
0x140adbf37  mov     ebx, eax
0x140adbf39  test    eax, eax
0x140adbf3b  jns     short loc_140ADBF56
0x140adbf3d  lea     r8, aDbgkWerliveker; "DBGK: WerLiveKernelOpenDumpFile failed."...
0x140adbf44  mov     r9d, eax
0x140adbf47  xor     edx, edx; Level
0x140adbf49  mov     ecx, r15d; ComponentId
0x140adbf4c  call    DbgPrintEx
0x140adbf51  jmp     loc_140ADC02D
0x140adbf56  mov     rax, [rsp+58h+arg_0]
0x140adbf5b  mov     [rsi+8], rax
0x140adbf5f  jmp     short loc_140ADBF77
0x140adbf61  or      dword ptr [rsi+18h], 8
0x140adbf65  mov     rcx, rdi
0x140adbf68  call    DbgkpWerInitializeDeferredLiveDump
0x140adbf6d  mov     ebx, eax
0x140adbf6f  test    eax, eax
0x140adbf71  js      loc_140ADC02D
0x140adbf77  mov     rcx, rdi
0x140adbf7a  call    DbgkpWerInvokeCallbacks
0x140adbf7f  mov     ebx, eax
0x140adbf81  test    eax, eax
0x140adbf83  js      loc_140ADC02D
0x140adbf89  mov     r9, [rdi+38h]
0x140adbf8d  lea     rax, [rsp+58h+arg_8]
0x140adbf92  mov     r8, [rdi+30h]
0x140adbf96  mov     rdx, [rdi+28h]
0x140adbf9a  mov     ecx, [rdi+20h]
0x140adbf9d  mov     [rsp+58h+var_28], rax
0x140adbfa2  mov     rax, [rdi+40h]
0x140adbfa6  mov     [rsp+58h+var_30], rsi
0x140adbfab  mov     [rsp+58h+var_38], rax
0x140adbfb0  call    IoCaptureLiveDump
0x140adbfb5  mov     ebx, eax
0x140adbfb7  mov     eax, [rdi+68h]
0x140adbfba  test    al, 2
0x140adbfbc  jnz     short loc_140ADBFFB
0x140adbfbe  test    ebx, ebx
0x140adbfc0  jns     short loc_140ADBFD1
0x140adbfc2  mov     r9d, ebx
0x140adbfc5  lea     r8, aDbgkDbgkpwerca_1; "DBGK: DbgkpWerCaptureLiveFullDump: IoCa"...
0x140adbfcc  jmp     loc_140ADBF47
0x140adbfd1  mov     rcx, [rdi+60h]
0x140adbfd5  xor     edx, edx
0x140adbfd7  call    cs:__imp_WerLiveKernelSubmitReport
0x140adbfde  nop     dword ptr [rax+rax+00h]
0x140adbfe3  mov     ebx, eax
0x140adbfe5  test    eax, eax
0x140adbfe7  jns     short loc_140ADBFF5
0x140adbfe9  lea     r8, aDbgkDbgkpwerca_0; "DBGK: DbgkpWerCaptureLiveFullDump: WerL"...
0x140adbff0  jmp     loc_140ADBF44
0x140adbff5  or      dword ptr [rdi+68h], 1
0x140adbff9  jmp     short loc_140ADC02D
0x140adbffb  mov     ecx, 80000000h
0x140adc000  lea     eax, [rbx+rcx]
0x140adc003  test    ecx, eax
0x140adc005  jnz     short loc_140ADC00F
0x140adc007  cmp     ebx, 0C0000016h
0x140adc00d  jnz     short loc_140ADBFC2
0x140adc00f  mov     rax, [rsp+58h+arg_8]
0x140adc014  mov     rcx, rdi
0x140adc017  mov     [rdi+80h], rax
0x140adc01e  call    DbgkpWerStartDeferredLiveDump
0x140adc023  mov     ebx, eax
0x140adc025  test    eax, eax
0x140adc027  js      short loc_140ADC02D
0x140adc029  mov     byte ptr [r14], 0
0x140adc02d  mov     rsi, [rsp+58h+arg_18]
0x140adc032  mov     eax, ebx
0x140adc034  mov     rbx, [rsp+58h+arg_10]
0x140adc039  add     rsp, 40h
0x140adc03d  pop     r15
0x140adc03f  pop     r14
0x140adc041  pop     rdi
0x140adc042  retn
```
