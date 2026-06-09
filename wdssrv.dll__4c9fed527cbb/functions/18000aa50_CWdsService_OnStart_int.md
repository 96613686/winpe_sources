# CWdsService::OnStart(int *)

- ea: `0x18000aa50`
- end: `0x18000aba8`
- name: `?OnStart@CWdsService@@QEAAKPEAH@Z`
- size: `344`
- prototype: `unsigned int __fastcall(CWdsService *__hidden this, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009da4`

## callees

- `0x180008214`
- `0x18000aa50`
- `0x18000f0dc`
- `0x18001b694`
- `0x18001c12a`
- `0x18001c150`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ab44`
- `KERNEL32!GetLastError` at `0x18000ab44`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000ab2d`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000ab2d`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000aace`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000ab74`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000aace`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000ab74`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000aaaf`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000aaaf`
- `ualapi!UalStart` at `0x18000ab15`
- `ualapi!UalStart` at `0x18000ab15`

## pseudocode

```c
__int64 __fastcall CWdsService::OnStart(CWdsService *this, int *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  const CHAR *v7; // rcx
  DWORD v8; // eax
  DWORD LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  int v13; // [rsp+20h] [rbp-2C8h] BYREF
  __int128 v14; // [rsp+24h] [rbp-2C4h]
  _BYTE v15[668]; // [rsp+34h] [rbp-2B4h] BYREF

  v4 = CWdsService::ChangeState(this, 4, 0, 0);
  if ( !(unsigned int)ElValidateWin32_0(v4, v5, v6, 0x290u) )
  {
    CEventLog::Log((CEventLog *)qword_180039300, 0x41010100u, 0);
    CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"WDS Server started successfully.\n");
    *a2 = 1;
    memset_0(v15, 0, sizeof(v15));
    v13 = 688;
    v14 = SumGuid_WDS;
    if ( (unsigned int)DelayLoadUalApi(v7) )
      UalStart(&v13);
    do
      v8 = WaitForSingleObjectEx(*(HANDLE *)this, 0xFFFFFFFF, 1);
    while ( v8 == 192 );
    if ( v8 )
    {
      LastError = GetLastError();
      return (unsigned int)ElValidateWin32_0(LastError, v10, v11, 0x2A9u);
    }
    else
    {
      CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"WDS Server shutdown started.\n");
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000aa50  mov     [rsp+arg_10], rbx
0x18000aa55  mov     [rsp+arg_18], rsi
0x18000aa5a  push    rdi
0x18000aa5b  sub     rsp, 2E0h
0x18000aa62  mov     rax, cs:__security_cookie
0x18000aa69  xor     rax, rsp
0x18000aa6c  mov     [rsp+2E8h+var_18], rax
0x18000aa74  xor     r9d, r9d; unsigned int
0x18000aa77  mov     rsi, rdx
0x18000aa7a  xor     r8d, r8d; int
0x18000aa7d  mov     rdi, rcx
0x18000aa80  lea     edx, [r9+4]; unsigned int
0x18000aa84  call    ?ChangeState@CWdsService@@AEAAKKHK@Z; CWdsService::ChangeState(ulong,int,ulong)
0x18000aa89  mov     r9d, 290h
0x18000aa8f  mov     ecx, eax
0x18000aa91  mov     ebx, eax
0x18000aa93  call    ElValidateWin32_0
0x18000aa98  test    eax, eax
0x18000aa9a  jnz     loc_18000AB80
0x18000aaa0  xor     r8d, r8d
0x18000aaa3  lea     rcx, qword_180039300
0x18000aaaa  mov     edx, 41010100h
0x18000aaaf  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18000aab6  nop     dword ptr [rax+rax+00h]
0x18000aabb  lea     r8, aWdsServerStart; "WDS Server started successfully.\n"
0x18000aac2  mov     edx, 20000h
0x18000aac7  lea     rcx, qword_180039310
0x18000aace  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000aad5  nop     dword ptr [rax+rax+00h]
0x18000aada  xor     edx, edx; Val
0x18000aadc  mov     dword ptr [rsi], 1
0x18000aae2  mov     r8d, 29Ch; Size
0x18000aae8  lea     rcx, [rsp+2E8h+var_2B4]; void *
0x18000aaed  call    memset_0
0x18000aaf2  movups  xmm0, cs:SumGuid_WDS
0x18000aaf9  mov     [rsp+2E8h+var_2C8], 2B0h
0x18000ab01  movdqu  [rsp+2E8h+var_2C4], xmm0
0x18000ab07  call    ?DelayLoadUalApi@@YAHXZ; DelayLoadUalApi(void)
0x18000ab0c  test    eax, eax
0x18000ab0e  jz      short loc_18000AB21
0x18000ab10  lea     rcx, [rsp+2E8h+var_2C8]
0x18000ab15  call    cs:__imp_UalStart
0x18000ab1c  nop     dword ptr [rax+rax+00h]
0x18000ab21  mov     rcx, [rdi]; hHandle
0x18000ab24  mov     r8d, 1; bAlertable
0x18000ab2a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ab2d  call    cs:__imp_WaitForSingleObjectEx
0x18000ab34  nop     dword ptr [rax+rax+00h]
0x18000ab39  cmp     eax, 0C0h
0x18000ab3e  jz      short loc_18000AB21
0x18000ab40  test    eax, eax
0x18000ab42  jz      short loc_18000AB61
0x18000ab44  call    cs:__imp_GetLastError
0x18000ab4b  nop     dword ptr [rax+rax+00h]
0x18000ab50  mov     ecx, eax
0x18000ab52  mov     r9d, 2A9h
0x18000ab58  call    ElValidateWin32_0
0x18000ab5d  mov     ebx, eax
0x18000ab5f  jmp     short loc_18000AB80
0x18000ab61  lea     r8, aWdsServerShutd; "WDS Server shutdown started.\n"
0x18000ab68  mov     edx, 20000h
0x18000ab6d  lea     rcx, qword_180039310
0x18000ab74  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000ab7b  nop     dword ptr [rax+rax+00h]
0x18000ab80  mov     eax, ebx
0x18000ab82  mov     rcx, [rsp+2E8h+var_18]
0x18000ab8a  xor     rcx, rsp; StackCookie
0x18000ab8d  call    __security_check_cookie
0x18000ab92  lea     r11, [rsp+2E8h+var_8]
0x18000ab9a  mov     rbx, [r11+20h]
0x18000ab9e  mov     rsi, [r11+28h]
0x18000aba2  mov     rsp, r11
0x18000aba5  pop     rdi
0x18000aba6  retn
```
