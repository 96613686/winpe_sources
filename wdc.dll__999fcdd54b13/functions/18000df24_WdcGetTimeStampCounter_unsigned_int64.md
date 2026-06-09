# WdcGetTimeStampCounter(unsigned __int64 *)

- ea: `0x18000df24`
- end: `0x18000dfdb`
- name: `?WdcGetTimeStampCounter@@YAJPEA_K@Z`
- size: `183`
- prototype: `__int64 __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000c090`

## callees

- `0x18000b854`
- `0x18000df24`
- `0x18003a3c0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000df99`
- `ntdll!RtlNtStatusToDosError` at `0x18000df99`
- `ntdll!NtQueryInformationThread` at `0x18000df69`
- `ntdll!NtQueryInformationThread` at `0x18000df69`
- `KERNEL32!GetCurrentThread` at `0x18000df48`
- `KERNEL32!GetCurrentThread` at `0x18000df48`

## pseudocode

```c
__int64 __fastcall WdcGetTimeStampCounter(unsigned __int64 *a1)
{
  HANDLE CurrentThread; // rax
  NTSTATUS v3; // eax
  unsigned int v4; // ebx
  signed int v6; // eax
  PULONG ReturnLength; // [rsp+20h] [rbp-38h]
  __int128 ThreadInformation; // [rsp+30h] [rbp-28h] BYREF

  ThreadInformation = 0;
  CurrentThread = GetCurrentThread();
  v3 = NtQueryInformationThread(CurrentThread, ThreadCycleTime, &ThreadInformation, 0x10u, 0);
  if ( v3 )
  {
    v6 = RtlNtStatusToDosError(v3);
    v4 = 0;
    if ( v6 )
    {
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      else
        v4 = v6;
    }
    if ( (v4 & 0x80000000) != 0 )
    {
      LODWORD(ReturnLength) = v4;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
        "WdcGetTimeStampCounter",
        0,
        L"FAILURE: 0x%08x",
        ReturnLength);
      return v4;
    }
  }
  else
  {
    v4 = 0;
  }
  *a1 = *((_QWORD *)&ThreadInformation + 1);
  return v4;
}

```

## disassembly

```asm
0x18000df24  mov     [rsp+arg_8], rbx
0x18000df29  push    rdi
0x18000df2a  sub     rsp, 50h
0x18000df2e  mov     rax, cs:__security_cookie
0x18000df35  xor     rax, rsp
0x18000df38  mov     [rsp+58h+var_18], rax
0x18000df3d  xorps   xmm0, xmm0
0x18000df40  mov     rdi, rcx
0x18000df43  movups  [rsp+58h+ThreadInformation], xmm0
0x18000df48  call    cs:__imp_GetCurrentThread
0x18000df4e  mov     r9d, 10h; ThreadInformationLength
0x18000df54  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x18000df5d  mov     rcx, rax; ThreadHandle
0x18000df60  lea     r8, [rsp+58h+ThreadInformation]; ThreadInformation
0x18000df65  lea     edx, [r9+7]; ThreadInformationClass
0x18000df69  call    cs:__imp_NtQueryInformationThread
0x18000df6f  test    eax, eax
0x18000df71  jnz     short loc_18000DF97
0x18000df73  xor     ebx, ebx
0x18000df75  mov     rcx, qword ptr [rsp+58h+ThreadInformation+8]
0x18000df7a  mov     [rdi], rcx
0x18000df7d  mov     eax, ebx
0x18000df7f  mov     rcx, [rsp+58h+var_18]
0x18000df84  xor     rcx, rsp; StackCookie
0x18000df87  call    __security_check_cookie
0x18000df8c  mov     rbx, [rsp+58h+arg_8]
0x18000df91  add     rsp, 50h
0x18000df95  pop     rdi
0x18000df96  retn
0x18000df97  mov     ecx, eax; Status
0x18000df99  call    cs:__imp_RtlNtStatusToDosError
0x18000df9f  xor     ebx, ebx
0x18000dfa1  test    eax, eax
0x18000dfa3  jz      short loc_18000DFB4
0x18000dfa5  jg      short loc_18000DFAB
0x18000dfa7  mov     ebx, eax
0x18000dfa9  jmp     short loc_18000DFB4
0x18000dfab  movzx   ebx, ax
0x18000dfae  or      ebx, 80070000h
0x18000dfb4  test    ebx, ebx
0x18000dfb6  jns     short loc_18000DF75
0x18000dfb8  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18000dfbf  mov     dword ptr [rsp+58h+ReturnLength], ebx
0x18000dfc3  xor     r8d, r8d; int
0x18000dfc6  lea     rdx, aWdcgettimestam; "WdcGetTimeStampCounter"
0x18000dfcd  lea     rcx, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x18000dfd4  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18000dfd9  jmp     short loc_18000DF7D
```
