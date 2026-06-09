# WerpQueryComponentOverridePolicy

- ea: `0x14000f6d8`
- end: `0x14000f8b3`
- name: `WerpQueryComponentOverridePolicy`
- size: `475`
- prototype: `__int64 __fastcall(WCHAR *, _BYTE *, __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000efa4`
- `0x14000fda8`

## callees

- `0x140001a24`
- `0x14000d174`
- `0x14000f3e0`
- `0x14000f54c`
- `0x14000f6d8`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000f74b`
- `ntoskrnl!DbgPrintEx` at `0x14000f813`
- `ntoskrnl!DbgPrintEx` at `0x14000f839`
- `ntoskrnl!DbgPrintEx` at `0x14000f88d`
- `ntoskrnl!DbgPrintEx` at `0x14000f74b`
- `ntoskrnl!DbgPrintEx` at `0x14000f813`
- `ntoskrnl!DbgPrintEx` at `0x14000f839`
- `ntoskrnl!DbgPrintEx` at `0x14000f88d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f86e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f86e`
- `ntoskrnl!ZwClose` at `0x14000f84f`
- `ntoskrnl!ZwClose` at `0x14000f84f`

## string_xrefs

- `0x14000f883`: `WERKERNELHOST: WerpQueryComponentOverridePolicy: Invalid params\n`
- `0x14000f761`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl\FullLiveKernelReports`
- `0x14000f787`: `WERKERNELHOST: RtlStringCbPrintfW failed for generating KeyBuffer for component %ws, status 0x%X.\n`
- `0x14000f7b1`: `WERKERNELHOST: WerpGetRegistryKey failed for opening %ws, status 0x%X.\n`
- `0x14000f7e0`: `WERKERNELHOST: OverridePolicy found for component %ws, Overridden threshold time %lli\n`
- `0x14000f803`: `WERKERNELHOST: OverridePolicy not found for component %ws\n`
- `0x14000f821`: `WERKERNELHOST: Failed to query OverridePolicy for component %ws, status 0x%X\n`

## pseudocode

```c
__int64 __fastcall WerpQueryComponentOverridePolicy(WCHAR *a1, _BYTE *a2, __int64 *a3)
{
  wchar_t *Mem; // rax
  WCHAR *v7; // rdi
  unsigned int v8; // ebx
  int RegistryKey; // eax
  const CHAR *v10; // r8
  WCHAR *v11; // r9
  ULONG v12; // edx
  __int64 v14; // [rsp+20h] [rbp-38h]
  __int64 v15; // [rsp+20h] [rbp-38h]
  struct _UNICODE_STRING v16; // [rsp+30h] [rbp-28h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp+18h] BYREF

  *(_QWORD *)&v16.Length = 3407922;
  v16.Buffer = L"OverrideThrottleThreshold";
  if ( !a3 || !a2 )
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpQueryComponentOverridePolicy: Invalid params\n");
    return 3221225485LL;
  }
  *a2 = 0;
  *a3 = 0;
  Handle = 0;
  Mem = (wchar_t *)WerpAllocateMem(208);
  v7 = Mem;
  if ( Mem )
  {
    RegistryKey = RtlStringCchPrintfW(
                    Mem,
                    0x68u,
                    L"%ws\\%ws",
                    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl\\FullLiveKernelReports",
                    a1);
    v8 = RegistryKey;
    if ( RegistryKey >= 0 )
    {
      RegistryKey = WerpGetRegistryKey(0, v7, 0x20019u, &Handle);
      v8 = RegistryKey;
      if ( RegistryKey < 0 )
      {
        v11 = v7;
        v10 = "WERKERNELHOST: WerpGetRegistryKey failed for opening %ws, status 0x%X.\n";
        v12 = 3;
LABEL_15:
        LODWORD(v14) = RegistryKey;
        DbgPrintEx(5u, v12, v10, v11, v14);
        goto LABEL_16;
      }
      RegistryKey = WerpGetRegistryTimeoutValue(Handle, &v16, 0xA8u, a3);
      v8 = RegistryKey;
      if ( RegistryKey >= 0 )
      {
        v15 = *a3;
        *a2 = 1;
        DbgPrintEx(
          5u,
          3u,
          "WERKERNELHOST: OverridePolicy found for component %ws, Overridden threshold time %lli\n",
          a1,
          v15);
        goto LABEL_16;
      }
      if ( RegistryKey == -1073741772 )
      {
        v8 = 0;
        DbgPrintEx(5u, 3u, "WERKERNELHOST: OverridePolicy not found for component %ws\n", a1);
        goto LABEL_16;
      }
      v10 = "WERKERNELHOST: Failed to query OverridePolicy for component %ws, status 0x%X\n";
    }
    else
    {
      v10 = "WERKERNELHOST: RtlStringCbPrintfW failed for generating KeyBuffer for component %ws, status 0x%X.\n";
    }
    v11 = a1;
    v12 = 1;
    goto LABEL_15;
  }
  DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpAllocateMem failed: Out of memory.\n");
  v8 = -1073741801;
LABEL_16:
  if ( Handle )
  {
    ZwClose(Handle);
    Handle = 0;
  }
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  return v8;
}

```

## disassembly

```asm
0x14000f6d8  mov     r11, rsp
0x14000f6db  mov     [r11+8], rbx
0x14000f6df  mov     [r11+10h], rsi
0x14000f6e3  push    rdi
0x14000f6e4  push    r14
0x14000f6e6  push    r15
0x14000f6e8  sub     rsp, 40h
0x14000f6ec  mov     qword ptr [r11-28h], 340032h
0x14000f6f4  lea     rax, aOverridethrott; "OverrideThrottleThreshold"
0x14000f6fb  mov     [r11-20h], rax
0x14000f6ff  mov     r14, r8
0x14000f702  mov     r15, rdx
0x14000f705  mov     rsi, rcx
0x14000f708  test    r8, r8
0x14000f70b  jz      loc_14000F87E
0x14000f711  test    rdx, rdx
0x14000f714  jz      loc_14000F87E
0x14000f71a  mov     ecx, 0D0h
0x14000f71f  mov     byte ptr [rdx], 0
0x14000f722  mov     qword ptr [r8], 0
0x14000f729  mov     qword ptr [r11+18h], 0
0x14000f731  call    WerpAllocateMem
0x14000f736  mov     rdi, rax
0x14000f739  test    rax, rax
0x14000f73c  jnz     short loc_14000F761
0x14000f73e  lea     r8, aWerkernelhostW_22; "WERKERNELHOST: WerpAllocateMem failed: "...
0x14000f745  lea     edx, [rax+1]; Level
0x14000f748  lea     ecx, [rax+5]; ComponentId
0x14000f74b  call    cs:__imp_DbgPrintEx
0x14000f752  nop     dword ptr [rax+rax+00h]
0x14000f757  mov     ebx, 0C0000017h
0x14000f75c  jmp     loc_14000F845
0x14000f761  lea     r9, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000f768  mov     [rsp+58h+var_38], rsi
0x14000f76d  lea     r8, aWsWs; "%ws\\%ws"
0x14000f774  mov     edx, 68h ; 'h'; cchDest
0x14000f779  mov     rcx, rdi; pszDest
0x14000f77c  call    RtlStringCchPrintfW
0x14000f781  mov     ebx, eax
0x14000f783  test    eax, eax
0x14000f785  jns     short loc_14000F793
0x14000f787  lea     r8, aWerkernelhostR_0; "WERKERNELHOST: RtlStringCbPrintfW faile"...
0x14000f78e  jmp     loc_14000F828
0x14000f793  lea     r9, [rsp+58h+Handle]
0x14000f798  mov     r8d, 20019h
0x14000f79e  mov     rdx, rdi
0x14000f7a1  xor     ecx, ecx
0x14000f7a3  call    WerpGetRegistryKey
0x14000f7a8  mov     ebx, eax
0x14000f7aa  test    eax, eax
0x14000f7ac  jns     short loc_14000F7BF
0x14000f7ae  mov     r9, rdi
0x14000f7b1  lea     r8, aWerkernelhostW_14; "WERKERNELHOST: WerpGetRegistryKey faile"...
0x14000f7b8  mov     edx, 3
0x14000f7bd  jmp     short loc_14000F830
0x14000f7bf  mov     rcx, [rsp+58h+Handle]
0x14000f7c4  lea     rdx, [rsp+58h+var_28]
0x14000f7c9  mov     r9, r14
0x14000f7cc  mov     r8d, 0A8h
0x14000f7d2  call    WerpGetRegistryTimeoutValue
0x14000f7d7  mov     ebx, eax
0x14000f7d9  test    eax, eax
0x14000f7db  js      short loc_14000F7FA
0x14000f7dd  mov     rax, [r14]
0x14000f7e0  lea     r8, aWerkernelhostO; "WERKERNELHOST: OverridePolicy found for"...
0x14000f7e7  mov     [rsp+58h+var_38], rax
0x14000f7ec  mov     r9, rsi
0x14000f7ef  mov     byte ptr [r15], 1
0x14000f7f3  mov     edx, 3
0x14000f7f8  jmp     short loc_14000F834
0x14000f7fa  cmp     eax, 0C0000034h
0x14000f7ff  jnz     short loc_14000F821
0x14000f801  xor     ebx, ebx
0x14000f803  lea     r8, aWerkernelhostO_0; "WERKERNELHOST: OverridePolicy not found"...
0x14000f80a  mov     r9, rsi
0x14000f80d  lea     edx, [rbx+3]; Level
0x14000f810  lea     ecx, [rbx+5]; ComponentId
0x14000f813  call    cs:__imp_DbgPrintEx
0x14000f81a  nop     dword ptr [rax+rax+00h]
0x14000f81f  jmp     short loc_14000F845
0x14000f821  lea     r8, aWerkernelhostF_8; "WERKERNELHOST: Failed to query Override"...
0x14000f828  mov     r9, rsi
0x14000f82b  mov     edx, 1; Level
0x14000f830  mov     dword ptr [rsp+58h+var_38], eax
0x14000f834  mov     ecx, 5; ComponentId
0x14000f839  call    cs:__imp_DbgPrintEx
0x14000f840  nop     dword ptr [rax+rax+00h]
0x14000f845  mov     rcx, [rsp+58h+Handle]; Handle
0x14000f84a  test    rcx, rcx
0x14000f84d  jz      short loc_14000F864
0x14000f84f  call    cs:__imp_ZwClose
0x14000f856  nop     dword ptr [rax+rax+00h]
0x14000f85b  mov     [rsp+58h+Handle], 0
0x14000f864  test    rdi, rdi
0x14000f867  jz      short loc_14000F87A
0x14000f869  xor     edx, edx; Tag
0x14000f86b  mov     rcx, rdi; P
0x14000f86e  call    cs:__imp_ExFreePoolWithTag
0x14000f875  nop     dword ptr [rax+rax+00h]
0x14000f87a  mov     eax, ebx
0x14000f87c  jmp     short loc_14000F89E
0x14000f87e  mov     edx, 1; Level
0x14000f883  lea     r8, aWerkernelhostW_53; "WERKERNELHOST: WerpQueryComponentOverri"...
0x14000f88a  lea     ecx, [rdx+4]; ComponentId
0x14000f88d  call    cs:__imp_DbgPrintEx
0x14000f894  nop     dword ptr [rax+rax+00h]
0x14000f899  mov     eax, 0C000000Dh
0x14000f89e  mov     rbx, [rsp+58h+arg_0]
0x14000f8a3  mov     rsi, [rsp+58h+arg_8]
0x14000f8a8  add     rsp, 40h
0x14000f8ac  pop     r15
0x14000f8ae  pop     r14
0x14000f8b0  pop     rdi
0x14000f8b1  retn
```
