# WcmUpdateCapabilityAccess

- ea: `0x180002550`
- end: `0x180002722`
- name: `WcmUpdateCapabilityAccess`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180002550`
- `0x180002728`
- `0x180004450`
- `0x1800044b0`
- `0x180004d10`
- `0x180008a90`
- `0x1800111dc`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800025de`
- `RPCRT4!NdrClientCall3` at `0x1800025de`
- `RPCRT4!RpcExceptionFilter` at `0x18001c926`
- `RPCRT4!RpcExceptionFilter` at `0x18001c926`

## string_xrefs

- `0x180002691`: `WcmUpdateCapabilityAccess`
- `0x1800026cb`: `WcmUpdateCapabilityAccess`

## pseudocode

```c
__int64 __fastcall WcmUpdateCapabilityAccess(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  WcmPolicyManager *v8; // r10
  unsigned int v9; // ebx
  int v11; // [rsp+38h] [rbp-50h]
  unsigned int Pointer; // [rsp+40h] [rbp-48h]
  __int16 v13; // [rsp+50h] [rbp-38h] BYREF

  v13 = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      128,
      &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      "WcmUpdateCapabilityAccess");
    v8 = WPP_GLOBAL_Control;
  }
  if ( a1 && a2 && a3 )
  {
    v11 = a4;
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, &v13, a1, a2, a3, v11).Pointer;
    v9 = ServiceStatus(Pointer);
  }
  else
  {
    if ( v8 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v8 + 25) && (*((_BYTE *)v8 + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)v8 + 2), 129, &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
    v9 = 87;
  }
  if ( v8 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v8 + 25) >= 5u && (*((_BYTE *)v8 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v8 + 2),
      131,
      (unsigned int)&WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      (unsigned int)"WcmUpdateCapabilityAccess",
      v9);
  return v9;
}

```

## disassembly

```asm
0x180002550  push    rbx
0x180002552  push    rsi
0x180002553  push    rdi
0x180002554  push    r14
0x180002556  push    r15
0x180002558  sub     rsp, 60h
0x18000255c  mov     rax, cs:__security_cookie
0x180002563  xor     rax, rsp
0x180002566  mov     [rsp+88h+var_30], rax
0x18000256b  mov     r15d, r9d
0x18000256e  mov     r14, r8
0x180002571  mov     rsi, rdx
0x180002574  mov     rbx, rcx
0x180002577  xor     eax, eax
0x180002579  mov     [rsp+88h+var_38], ax
0x18000257e  lea     rdi, WPP_GLOBAL_Control
0x180002585  mov     r10, cs:WPP_GLOBAL_Control
0x18000258c  cmp     r10, rdi
0x18000258f  jnz     loc_180002676
0x180002595  test    rbx, rbx
0x180002598  jz      loc_1800026E7
0x18000259e  test    rsi, rsi
0x1800025a1  jz      loc_1800026E7
0x1800025a7  test    r14, r14
0x1800025aa  jz      loc_1800026E7
0x1800025b0  mov     [rsp+88h+var_40], 0
0x1800025b9  mov     [rsp+88h+var_50], r15d
0x1800025be  mov     [rsp+88h+var_58], r14
0x1800025c3  mov     [rsp+88h+var_60], rsi
0x1800025c8  mov     [rsp+88h+var_68], rbx
0x1800025cd  lea     r9, [rsp+88h+var_38]
0x1800025d2  xor     r8d, r8d; pReturnValue
0x1800025d5  xor     edx, edx; nProcNum
0x1800025d7  lea     rcx, pProxyInfo; pProxyInfo
0x1800025de  call    cs:__imp_NdrClientCall3
0x1800025e5  nop     dword ptr [rax+rax+00h]
0x1800025ea  mov     rbx, rax
0x1800025ed  mov     [rsp+88h+var_40], rax
0x1800025f2  mov     [rsp+88h+var_48], eax
0x1800025f6  mov     r10, cs:WPP_GLOBAL_Control
0x1800025fd  jmp     short loc_18000264C
0x1800025ff  mov     ebx, eax
0x180002601  mov     [rsp+88h+var_48], eax
0x180002605  lea     rcx, WPP_GLOBAL_Control
0x18000260c  mov     r10, cs:WPP_GLOBAL_Control
0x180002613  cmp     r10, rcx
0x180002616  jz      short loc_180002645
0x180002618  cmp     byte ptr [r10+19h], 1
0x18000261d  jb      short loc_180002645
0x18000261f  test    byte ptr [r10+1Ch], 1
0x180002624  jz      short loc_180002645
0x180002626  mov     edx, 82h
0x18000262b  mov     r9d, eax
0x18000262e  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180002635  mov     rcx, [r10+10h]
0x180002639  call    WPP_SF_D
0x18000263e  mov     r10, cs:WPP_GLOBAL_Control
0x180002645  lea     rdi, WPP_GLOBAL_Control
0x18000264c  mov     ecx, ebx; unsigned int
0x18000264e  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x180002653  mov     ebx, eax
0x180002655  cmp     r10, rdi
0x180002658  jnz     short loc_1800026B4
0x18000265a  mov     eax, ebx
0x18000265c  mov     rcx, [rsp+88h+var_30]
0x180002661  xor     rcx, rsp; StackCookie
0x180002664  call    __security_check_cookie
0x180002669  add     rsp, 60h
0x18000266d  pop     r15
0x18000266f  pop     r14
0x180002671  pop     rdi
0x180002672  pop     rsi
0x180002673  pop     rbx
0x180002674  retn
0x180002676  cmp     byte ptr [r10+19h], 5
0x18000267b  jb      loc_180002595
0x180002681  test    byte ptr [r10+1Ch], 1
0x180002686  jz      loc_180002595
0x18000268c  mov     edx, 80h
0x180002691  lea     r9, aWcmupdatecapab_0; "WcmUpdateCapabilityAccess"
0x180002698  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x18000269f  mov     rcx, [r10+10h]
0x1800026a3  call    WPP_SF_s
0x1800026a8  mov     r10, cs:WPP_GLOBAL_Control
0x1800026af  jmp     loc_180002595
0x1800026b4  cmp     byte ptr [r10+19h], 5
0x1800026b9  jb      short loc_18000265A
0x1800026bb  test    byte ptr [r10+1Ch], 1
0x1800026c0  jz      short loc_18000265A
0x1800026c2  mov     edx, 83h
0x1800026c7  mov     dword ptr [rsp+88h+var_68], ebx
0x1800026cb  lea     r9, aWcmupdatecapab_0; "WcmUpdateCapabilityAccess"
0x1800026d2  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x1800026d9  mov     rcx, [r10+10h]
0x1800026dd  call    WPP_SF_sL
0x1800026e2  jmp     loc_18000265A
0x1800026e7  cmp     r10, rdi
0x1800026ea  jnz     short loc_1800026F6
0x1800026ec  mov     ebx, 57h ; 'W'
0x1800026f1  jmp     loc_180002655
0x1800026f6  cmp     byte ptr [r10+19h], 1
0x1800026fb  jb      short loc_1800026EC
0x1800026fd  test    byte ptr [r10+1Ch], 1
0x180002702  jz      short loc_1800026EC
0x180002704  mov     edx, 81h
0x180002709  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180002710  mov     rcx, [r10+10h]
0x180002714  call    WPP_SF_
0x180002719  mov     r10, cs:WPP_GLOBAL_Control
0x180002720  jmp     short loc_1800026EC
0x18001c918  push    rbp
0x18001c91a  sub     rsp, 40h
0x18001c91e  mov     rbp, rdx
0x18001c921  mov     rcx, [rcx]
0x18001c924  mov     ecx, [rcx]; ExceptionCode
0x18001c926  call    cs:__imp_RpcExceptionFilter
0x18001c92d  nop     dword ptr [rax+rax+00h]
0x18001c932  nop
0x18001c933  add     rsp, 40h
0x18001c937  pop     rbp
0x18001c938  retn
```
