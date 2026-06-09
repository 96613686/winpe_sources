# SmscpExecuteInitialCommand

- ea: `0x140007420`
- end: `0x14000765e`
- name: `SmscpExecuteInitialCommand`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006680`

## callees

- `0x1400010ec`
- `0x140003450`
- `0x140005998`
- `0x140007420`
- `0x140008e60`
- `0x140012bb8`
- `0x140018458`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtTerminateProcess` at `0x140007634`
- `ntdll!NtTerminateProcess` at `0x140007634`

## string_xrefs

- `0x140007595`: `SmscpExecuteInitialCommand`
- `0x1400075e5`: `SmscpExecuteInitialCommand`

## pseudocode

```c
__int64 __fastcall SmscpExecuteInitialCommand(unsigned int a1, int *a2, __int64 a3)
{
  int v5; // ebx
  int v6; // eax
  __int64 v7; // r8
  int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // r8
  __int64 result; // rax
  signed __int32 v13[8]; // [rsp+0h] [rbp-100h] BYREF
  bool v14; // [rsp+30h] [rbp-D0h] BYREF
  bool v15[7]; // [rsp+31h] [rbp-CFh] BYREF
  struct _UNICODE_STRING v16; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING v17; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE ProcessHandle[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v19; // [rsp+70h] [rbp-90h]
  __int128 v20; // [rsp+80h] [rbp-80h]
  __int128 v21; // [rsp+90h] [rbp-70h]
  __int128 v22; // [rsp+A0h] [rbp-60h]
  __int128 v23; // [rsp+B0h] [rbp-50h]
  __int64 v24; // [rsp+C0h] [rbp-40h]
  _BYTE v25[224]; // [rsp+D0h] [rbp-30h] BYREF

  *(_QWORD *)&v16.Length = 4849736;
  v24 = 0;
  v14 = 0;
  v15[0] = 0;
  *(_QWORD *)&v17.Length = 3932218;
  v16.Buffer = L"RequireMicrosoftSignedCodeInWinlogon";
  v5 = 2080;
  v17.Buffer = L"ProhibitDynamicCodeInWinlogon";
  v6 = *a2;
  *(_OWORD *)ProcessHandle = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  if ( (v6 & 8) != 0 )
  {
    v5 = 10272;
    if ( (v6 & 6) == 2 )
      v5 = 14368;
  }
  if ( (unsigned int)Feature_WinlogonProcessMitigations__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( !(unsigned int)SmscpShouldRequireProcessMitigation(a3, &v16, &v14, v15) )
    {
      if ( v14 )
      {
        v5 |= 0x20000u;
      }
      else if ( v15[0] )
      {
        v5 |= 0x40000u;
      }
    }
    if ( !(unsigned int)SmscpShouldRequireProcessMitigation(a3, &v17, &v14, v15) )
    {
      if ( v14 )
      {
        v5 |= 0x80000u;
      }
      else if ( v15[0] )
      {
        v5 |= 0x100000u;
      }
    }
  }
  v8 = SmpExecuteCommand(a3, a1, v7, v5, ProcessHandle);
  v10 = v8;
  if ( v8 >= 0 )
  {
    *(_DWORD *)SmscpSharedWindow = 2;
    result = SmExecPgmEx(v9, ProcessHandle);
    v10 = result;
    if ( (int)result >= 0 )
      return result;
    memset_0(v25, 0, sizeof(v25));
    SmpInternalLogFailure("SmscpExecuteInitialCommand", 1221, v10, v25);
    *(_DWORD *)SmscpSharedWindow = 1;
    _InterlockedOr(v13, 0);
    *((_DWORD *)SmscpSharedWindow + 2) = 1223;
    *((_DWORD *)SmscpSharedWindow + 1) = v10;
    *((_QWORD *)SmscpSharedWindow + 2) = SmscpExecuteInitialCommand;
    NtTerminateProcess(ProcessHandle[1], v10);
  }
  else
  {
    *(_DWORD *)SmscpSharedWindow = 1;
    _InterlockedOr(v13, 0);
    *((_DWORD *)SmscpSharedWindow + 2) = 1200;
    *((_DWORD *)SmscpSharedWindow + 1) = v8;
    *((_QWORD *)SmscpSharedWindow + 2) = SmscpExecuteInitialCommand;
    if ( a3 )
      v11 = *(_QWORD *)(a3 + 8);
    else
      v11 = 0;
    SmpLogFailureString("SmscpExecuteInitialCommand", 1201, v11, (unsigned int)v8);
  }
  return v10;
}

```

## disassembly

```asm
0x140007420  mov     [rsp-8+arg_8], rbx
0x140007425  push    rbp
0x140007426  push    rsi
0x140007427  push    rdi
0x140007428  lea     rbp, [rsp-0C0h]
0x140007430  sub     rsp, 1C0h
0x140007437  mov     rax, cs:__security_cookie
0x14000743e  xor     rax, rsp
0x140007441  mov     [rbp+0D0h+var_20], rax
0x140007448  xor     eax, eax
0x14000744a  mov     [rsp+1D0h+var_198], 4A0048h
0x140007453  xorps   xmm0, xmm0
0x140007456  mov     [rbp+0D0h+var_110], rax
0x14000745a  mov     [rsp+1D0h+var_1A0], al
0x14000745e  mov     rdi, r8
0x140007461  mov     [rsp+1D0h+var_19F], al
0x140007465  mov     esi, ecx
0x140007467  lea     rax, aRequiremicroso; "RequireMicrosoftSignedCodeInWinlogon"
0x14000746e  mov     [rsp+1D0h+var_188], 3C003Ah
0x140007477  mov     [rsp+1D0h+var_190], rax
0x14000747c  mov     ebx, 820h
0x140007481  lea     rax, aProhibitdynami; "ProhibitDynamicCodeInWinlogon"
0x140007488  mov     [rsp+1D0h+var_180], rax
0x14000748d  mov     eax, [rdx]
0x14000748f  movups  xmmword ptr [rsp+1D0h+ProcessHandle], xmm0
0x140007494  movups  [rsp+1D0h+var_160], xmm0
0x140007499  movups  [rbp+0D0h+var_150], xmm0
0x14000749d  movups  [rbp+0D0h+var_140], xmm0
0x1400074a1  movups  [rbp+0D0h+var_130], xmm0
0x1400074a5  movups  [rbp+0D0h+var_120], xmm0
0x1400074a9  test    al, 8
0x1400074ab  jz      short loc_1400074BE
0x1400074ad  and     al, 6
0x1400074af  mov     ebx, 2820h
0x1400074b4  cmp     al, 2
0x1400074b6  mov     ecx, 3820h
0x1400074bb  cmovz   ebx, ecx
0x1400074be  call    Feature_WinlogonProcessMitigations__private_IsEnabledDeviceUsageNoInline
0x1400074c3  test    eax, eax
0x1400074c5  jz      short loc_14000752B
0x1400074c7  lea     r9, [rsp+1D0h+var_19F]
0x1400074cc  mov     rcx, rdi
0x1400074cf  lea     r8, [rsp+1D0h+var_1A0]
0x1400074d4  lea     rdx, [rsp+1D0h+var_198]
0x1400074d9  call    SmscpShouldRequireProcessMitigation
0x1400074de  test    eax, eax
0x1400074e0  jnz     short loc_1400074F9
0x1400074e2  cmp     [rsp+1D0h+var_1A0], al
0x1400074e6  jz      short loc_1400074EE
0x1400074e8  bts     ebx, 11h
0x1400074ec  jmp     short loc_1400074F9
0x1400074ee  cmp     [rsp+1D0h+var_19F], 0
0x1400074f3  jz      short loc_1400074F9
0x1400074f5  bts     ebx, 12h
0x1400074f9  lea     r9, [rsp+1D0h+var_19F]
0x1400074fe  mov     rcx, rdi
0x140007501  lea     r8, [rsp+1D0h+var_1A0]
0x140007506  lea     rdx, [rsp+1D0h+var_188]
0x14000750b  call    SmscpShouldRequireProcessMitigation
0x140007510  test    eax, eax
0x140007512  jnz     short loc_14000752B
0x140007514  cmp     [rsp+1D0h+var_1A0], al
0x140007518  jz      short loc_140007520
0x14000751a  bts     ebx, 13h
0x14000751e  jmp     short loc_14000752B
0x140007520  cmp     [rsp+1D0h+var_19F], 0
0x140007525  jz      short loc_14000752B
0x140007527  bts     ebx, 14h
0x14000752b  lea     rax, [rsp+1D0h+ProcessHandle]
0x140007530  mov     r9d, ebx
0x140007533  mov     edx, esi
0x140007535  mov     [rsp+1D0h+var_1B0], rax
0x14000753a  mov     rcx, rdi
0x14000753d  call    SmpExecuteCommand
0x140007542  mov     ebx, eax
0x140007544  test    eax, eax
0x140007546  jns     short loc_1400075AB
0x140007548  mov     rcx, cs:SmscpSharedWindow
0x14000754f  mov     dword ptr [rcx], 1
0x140007555  lock or [rsp+1D0h+var_1D0], 0
0x14000755a  mov     rcx, cs:SmscpSharedWindow
0x140007561  lea     rdx, SmscpExecuteInitialCommand
0x140007568  mov     dword ptr [rcx+8], 4B0h
0x14000756f  mov     rcx, cs:SmscpSharedWindow
0x140007576  mov     [rcx+4], eax
0x140007579  mov     rcx, cs:SmscpSharedWindow
0x140007580  mov     [rcx+10h], rdx
0x140007584  test    rdi, rdi
0x140007587  jz      short loc_14000758F
0x140007589  mov     r8, [rdi+8]
0x14000758d  jmp     short loc_140007592
0x14000758f  xor     r8d, r8d
0x140007592  mov     r9d, ebx
0x140007595  lea     rcx, aSmscpexecutein; "SmscpExecuteInitialCommand"
0x14000759c  mov     edx, 4B1h
0x1400075a1  call    SmpLogFailureString
0x1400075a6  jmp     loc_14000763A
0x1400075ab  mov     rax, cs:SmscpSharedWindow
0x1400075b2  lea     rdx, [rsp+1D0h+ProcessHandle]
0x1400075b7  mov     dword ptr [rax], 2
0x1400075bd  call    SmExecPgmEx
0x1400075c2  mov     ebx, eax
0x1400075c4  test    eax, eax
0x1400075c6  jns     short loc_14000763C
0x1400075c8  xor     edx, edx; Val
0x1400075ca  lea     rcx, [rbp+0D0h+var_100]; void *
0x1400075ce  mov     r8d, 0E0h; Size
0x1400075d4  call    memset_0
0x1400075d9  lea     r9, [rbp+0D0h+var_100]
0x1400075dd  mov     r8d, ebx
0x1400075e0  mov     edx, 4C5h
0x1400075e5  lea     rcx, aSmscpexecutein; "SmscpExecuteInitialCommand"
0x1400075ec  call    SmpInternalLogFailure
0x1400075f1  mov     rax, cs:SmscpSharedWindow
0x1400075f8  mov     dword ptr [rax], 1
0x1400075fe  lock or [rsp+1D0h+var_1D0], 0
0x140007603  mov     rax, cs:SmscpSharedWindow
0x14000760a  lea     rdx, SmscpExecuteInitialCommand
0x140007611  mov     dword ptr [rax+8], 4C7h
0x140007618  mov     rax, cs:SmscpSharedWindow
0x14000761f  mov     [rax+4], ebx
0x140007622  mov     rax, cs:SmscpSharedWindow
0x140007629  mov     [rax+10h], rdx
0x14000762d  mov     rcx, [rsp+1D0h+ProcessHandle+8]; ProcessHandle
0x140007632  mov     edx, ebx; ExitStatus
0x140007634  call    cs:__imp_NtTerminateProcess
0x14000763a  mov     eax, ebx
0x14000763c  mov     rcx, [rbp+0D0h+var_20]
0x140007643  xor     rcx, rsp; StackCookie
0x140007646  call    __security_check_cookie
0x14000764b  mov     rbx, [rsp+1D0h+arg_8]
0x140007653  add     rsp, 1C0h
0x14000765a  pop     rdi
0x14000765b  pop     rsi
0x14000765c  pop     rbp
0x14000765d  retn
```
