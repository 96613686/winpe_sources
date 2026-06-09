# CProbedAssemblyInformation::SetPolicyPath(ulong,ushort const *,unsigned __int64)

- ea: `0x18003ef00`
- end: `0x18003f05a`
- name: `?SetPolicyPath@CProbedAssemblyInformation@@QEAAHKPEBG_K@Z`
- size: `346`
- prototype: `__int64 __fastcall(CProbedAssemblyInformation *__hidden this, unsigned int, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18004029c`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180013af0`
- `0x18003ef00`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18003ef9f`
- `ntdll!RtlPopFrame` at `0x18003ef9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f040`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ef72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003efcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003effa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ef72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003efcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003effa`

## pseudocode

```c
__int64 __fastcall CProbedAssemblyInformation::SetPolicyPath(
        CProbedAssemblyInformation *this,
        __int64 a2,
        const unsigned __int16 *a3,
        size_t a4)
{
  unsigned int v7; // ebx
  DWORD LastError; // eax
  int v10; // [rsp+20h] [rbp-40h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+28h] [rbp-38h] BYREF
  __int64 v12; // [rsp+40h] [rbp-20h]
  int v13; // [rsp+48h] [rbp-18h]
  unsigned int *v14; // [rsp+50h] [rbp-10h]

  v10 = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180070D90;
  Frame.Flags = 1;
  v14 = (unsigned int *)&v10;
  Frame.Previous = 0;
  v12 = 544438355;
  v13 = 176;
  CFrame::BaseEnter((CFrame *)&Frame);
  if ( *(_QWORD *)this )
  {
    SetLastError(0);
    if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign((__int64)this + 600, a3, a4) )
    {
      *((_DWORD *)this + 149) = 2;
      SetLastError(0);
      *v14 = 1;
    }
    else
    {
      *v14 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800788C8);
    }
  }
  else
  {
    SetLastError(0x54Fu);
    *v14 = 0;
  }
  v7 = *v14;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v7 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v7;
}

```

## disassembly

```asm
0x18003ef00  mov     [rsp-18h+arg_8], rbx
0x18003ef05  push    rbp
0x18003ef06  push    rsi
0x18003ef07  push    rdi
0x18003ef08  mov     rbp, rsp
0x18003ef0b  sub     rsp, 60h
0x18003ef0f  mov     rax, cs:__security_cookie
0x18003ef16  xor     rax, rsp
0x18003ef19  mov     [rbp+var_8], rax
0x18003ef1d  lea     rax, qword_180070D90
0x18003ef24  mov     [rbp+var_40], 0
0x18003ef2b  mov     [rbp+Frame.Context], rax
0x18003ef2f  mov     rbx, rcx
0x18003ef32  lea     rax, [rbp+var_40]
0x18003ef36  mov     [rbp+Frame.Flags], 1
0x18003ef3d  lea     rcx, [rbp+Frame]; this
0x18003ef41  mov     [rbp+var_10], rax
0x18003ef45  mov     rsi, r9
0x18003ef48  mov     [rbp+Frame.Previous], 0
0x18003ef50  mov     rdi, r8
0x18003ef53  mov     [rbp+var_20], 20737853h
0x18003ef5b  mov     [rbp+var_18], 0B0h
0x18003ef62  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18003ef67  cmp     qword ptr [rbx], 0
0x18003ef6b  jnz     short loc_18003EFCA
0x18003ef6d  mov     ecx, 54Fh; dwErrCode
0x18003ef72  call    cs:__imp_SetLastError
0x18003ef79  nop     dword ptr [rax+rax+00h]
0x18003ef7e  mov     rax, [rbp+var_10]
0x18003ef82  mov     dword ptr [rax], 0
0x18003ef88  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18003ef8f  mov     rax, [rbp+var_10]
0x18003ef93  mov     ebx, [rax]
0x18003ef95  jnz     loc_18003F030
0x18003ef9b  lea     rcx, [rbp+Frame]; Frame
0x18003ef9f  call    cs:__imp_RtlPopFrame
0x18003efa6  nop     dword ptr [rax+rax+00h]
0x18003efab  mov     eax, ebx
0x18003efad  mov     rcx, [rbp+var_8]
0x18003efb1  xor     rcx, rsp; StackCookie
0x18003efb4  call    __security_check_cookie
0x18003efb9  mov     rbx, [rsp+60h+arg_8]
0x18003efc1  add     rsp, 60h
0x18003efc5  pop     rdi
0x18003efc6  pop     rsi
0x18003efc7  pop     rbp
0x18003efc8  retn
0x18003efca  xor     ecx, ecx; dwErrCode
0x18003efcc  call    cs:__imp_SetLastError
0x18003efd3  nop     dword ptr [rax+rax+00h]
0x18003efd8  lea     rcx, [rbx+258h]
0x18003efdf  mov     r8, rsi
0x18003efe2  mov     rdx, rdi
0x18003efe5  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(ushort const *,unsigned __int64)
0x18003efea  test    eax, eax
0x18003efec  jz      short loc_18003F015
0x18003efee  xor     ecx, ecx; dwErrCode
0x18003eff0  mov     dword ptr [rbx+254h], 2
0x18003effa  call    cs:__imp_SetLastError
0x18003f001  nop     dword ptr [rax+rax+00h]
0x18003f006  mov     rax, [rbp+var_10]
0x18003f00a  mov     dword ptr [rax], 1
0x18003f010  jmp     loc_18003EF88
0x18003f015  mov     rax, [rbp+var_10]
0x18003f019  lea     rcx, off_1800788C8; struct _CALL_SITE_INFO *
0x18003f020  mov     dword ptr [rax], 0
0x18003f026  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18003f02b  jmp     loc_18003EF88
0x18003f030  test    ebx, ebx
0x18003f032  jz      short loc_18003F040
0x18003f034  xor     ecx, ecx; char *
0x18003f036  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18003f03b  jmp     loc_18003EF9B
0x18003f040  call    cs:__imp_GetLastError
0x18003f047  nop     dword ptr [rax+rax+00h]
0x18003f04c  mov     ecx, eax; unsigned int
0x18003f04e  xor     edx, edx; Format
0x18003f050  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18003f055  jmp     loc_18003EF9B
```
