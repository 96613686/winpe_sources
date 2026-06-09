# CRpcHandler::MakeSpn(ulong,ushort * *)

- ea: `0x180004818`
- end: `0x1800049ae`
- name: `?MakeSpn@CRpcHandler@@AEAAKKPEAPEAG@Z`
- size: `406`
- prototype: `unsigned int __fastcall(CRpcHandler *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800042f0`

## callees

- `0x180001984`
- `0x180003944`
- `0x180004818`

## import_xrefs

- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180004979`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18000498f`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180004979`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18000498f`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180004886`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180004965`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180004886`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180004965`
- `WdsServerCommonLib!?GetHostName@@YAKW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z` at `0x180004844`
- `WdsServerCommonLib!?GetHostName@@YAKW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z` at `0x180004844`
- `NTDSAPI!DsMakeSpnW` at `0x1800048b8`
- `NTDSAPI!DsMakeSpnW` at `0x180004929`
- `NTDSAPI!DsMakeSpnW` at `0x1800048b8`
- `NTDSAPI!DsMakeSpnW` at `0x180004929`

## pseudocode

```c
__int64 __fastcall CRpcHandler::MakeSpn(CRpcHandler *this, __int64 a2, unsigned __int16 **a3)
{
  unsigned int HostName; // eax
  __int64 v5; // rdx
  DWORD SpnW; // ebx
  unsigned __int64 v7; // rax
  WCHAR *pszSpn; // rdi
  DWORD v9; // eax
  __int64 v10; // rdx
  LPCWSTR ServiceName; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcSpnLength; // [rsp+58h] [rbp+10h] BYREF

  ServiceName = 0;
  pcSpnLength = 0;
  HostName = GetHostName(ComputerNameDnsFullyQualified, (unsigned __int16 **)&ServiceName);
  SpnW = ElValidateWin32(HostName, v5, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 400);
  if ( !SpnW )
  {
    CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[RPC] Host Name: %s", ServiceName);
    SpnW = DsMakeSpnW(L"ldap", ServiceName, 0, 0, 0, &pcSpnLength, 0);
    if ( SpnW == 111 )
    {
      v7 = 2LL * pcSpnLength;
      if ( !is_mul_ok(pcSpnLength, 2u) )
        v7 = -1;
      pszSpn = (WCHAR *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
      if ( pszSpn )
      {
        v9 = DsMakeSpnW(L"ldap", ServiceName, 0, 0, 0, &pcSpnLength, pszSpn);
        SpnW = ElValidateWin32(v9, v10, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 437);
        if ( SpnW )
        {
          WdsPrivateHpFree(pszSpn);
        }
        else
        {
          CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[RPC] NTLM/Kerberos Spn: %s", pszSpn);
          *a3 = pszSpn;
        }
      }
      else
      {
        SpnW = 8;
      }
    }
  }
  if ( ServiceName )
    WdsPrivateHpFree((void *)ServiceName);
  return SpnW;
}

```

## disassembly

```asm
0x180004818  mov     rax, rsp
0x18000481b  mov     [rax+18h], rbx
0x18000481f  mov     [rax+20h], rsi
0x180004823  mov     [rax+10h], edx
0x180004826  mov     [rax+8], rcx
0x18000482a  push    rdi
0x18000482b  sub     rsp, 40h
0x18000482f  and     qword ptr [rax+8], 0
0x180004834  lea     rdx, [rax+8]
0x180004838  and     dword ptr [rax+10h], 0
0x18000483c  mov     ecx, 3
0x180004841  mov     rsi, r8
0x180004844  call    cs:__imp_?GetHostName@@YAKW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z; GetHostName(_COMPUTER_NAME_FORMAT,ushort * *)
0x18000484b  nop     dword ptr [rax+rax+00h]
0x180004850  mov     r9d, 190h
0x180004856  lea     r8, aBaseEcoWdsWdss_6; "base\\eco\\wds\\wdssrv\\server\\src\\rp"...
0x18000485d  mov     ecx, eax
0x18000485f  call    ElValidateWin32
0x180004864  mov     ebx, eax
0x180004866  test    eax, eax
0x180004868  jnz     loc_180004985
0x18000486e  mov     r9, [rsp+48h+ServiceName]
0x180004873  lea     r8, aRpcHostNameS; "[RPC] Host Name: %s"
0x18000487a  mov     edx, 20000h
0x18000487f  lea     rcx, qword_180039310
0x180004886  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000488d  nop     dword ptr [rax+rax+00h]
0x180004892  mov     rdx, [rsp+48h+ServiceName]; ServiceName
0x180004897  lea     rax, [rsp+48h+arg_8]
0x18000489c  xor     r9d, r9d; InstancePort
0x18000489f  lea     rcx, ServiceClass; "ldap"
0x1800048a6  and     [rsp+48h+pszSpn], r9
0x1800048ab  xor     r8d, r8d; InstanceName
0x1800048ae  mov     [rsp+48h+pcSpnLength], rax; pcSpnLength
0x1800048b3  and     [rsp+48h+var_28], r9
0x1800048b8  call    cs:__imp_DsMakeSpnW
0x1800048bf  nop     dword ptr [rax+rax+00h]
0x1800048c4  mov     ebx, eax
0x1800048c6  cmp     eax, 6Fh ; 'o'
0x1800048c9  jnz     loc_180004985
0x1800048cf  mov     ecx, [rsp+48h+arg_8]
0x1800048d3  lea     eax, [rbx-6Dh]
0x1800048d6  mul     rcx
0x1800048d9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800048e0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800048e7  cmovo   rax, rcx
0x1800048eb  mov     rcx, rax; unsigned __int64
0x1800048ee  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800048f3  mov     rdi, rax
0x1800048f6  test    rax, rax
0x1800048f9  jnz     short loc_180004903
0x1800048fb  lea     ebx, [rax+8]
0x1800048fe  jmp     loc_180004985
0x180004903  mov     rdx, [rsp+48h+ServiceName]; ServiceName
0x180004908  lea     rax, [rsp+48h+arg_8]
0x18000490d  xor     r9d, r9d; InstancePort
0x180004910  mov     [rsp+48h+pszSpn], rdi; pszSpn
0x180004915  mov     [rsp+48h+pcSpnLength], rax; pcSpnLength
0x18000491a  lea     rcx, ServiceClass; "ldap"
0x180004921  and     [rsp+48h+var_28], r9
0x180004926  xor     r8d, r8d; InstanceName
0x180004929  call    cs:__imp_DsMakeSpnW
0x180004930  nop     dword ptr [rax+rax+00h]
0x180004935  mov     r9d, 1B5h
0x18000493b  lea     r8, aBaseEcoWdsWdss_6; "base\\eco\\wds\\wdssrv\\server\\src\\rp"...
0x180004942  mov     ecx, eax
0x180004944  call    ElValidateWin32
0x180004949  mov     ebx, eax
0x18000494b  test    eax, eax
0x18000494d  jnz     short loc_180004976
0x18000494f  mov     r9, rdi
0x180004952  lea     r8, aRpcNtlmKerbero; "[RPC] NTLM/Kerberos Spn: %s"
0x180004959  mov     edx, 20000h
0x18000495e  lea     rcx, qword_180039310
0x180004965  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000496c  nop     dword ptr [rax+rax+00h]
0x180004971  mov     [rsi], rdi
0x180004974  jmp     short loc_180004985
0x180004976  mov     rcx, rdi
0x180004979  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180004980  nop     dword ptr [rax+rax+00h]
0x180004985  mov     rcx, [rsp+48h+ServiceName]
0x18000498a  test    rcx, rcx
0x18000498d  jz      short loc_18000499B
0x18000498f  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180004996  nop     dword ptr [rax+rax+00h]
0x18000499b  mov     rsi, [rsp+48h+arg_18]
0x1800049a0  mov     eax, ebx
0x1800049a2  mov     rbx, [rsp+48h+arg_10]
0x1800049a7  add     rsp, 40h
0x1800049ab  pop     rdi
0x1800049ac  retn
```
