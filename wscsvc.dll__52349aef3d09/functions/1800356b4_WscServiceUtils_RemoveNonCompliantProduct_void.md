# WscServiceUtils::RemoveNonCompliantProduct(void *)

- ea: `0x1800356b4`
- end: `0x1800357c5`
- name: `?RemoveNonCompliantProduct@WscServiceUtils@@YAJPEAX@Z`
- size: `273`
- prototype: `__int64 __fastcall(WscServiceUtils *__hidden this, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800250c0`

## callees

- `0x180008e48`
- `0x18001abb0`
- `0x18001bb90`
- `0x18001fb24`
- `0x1800202e8`
- `0x180029e74`
- `0x180035548`
- `0x1800356b4`

## pseudocode

```c
__int64 __fastcall WscServiceUtils::RemoveNonCompliantProduct(WscServiceUtils *this, void *a2)
{
  unsigned int CallerProcessPath; // edi
  void *v4; // rbx
  __int64 v5; // rax
  char v7; // [rsp+48h] [rbp+10h] BYREF
  void *Block; // [rsp+50h] [rbp+18h] BYREF

  Block = 0;
  CRpcImpersonateClient::CRpcImpersonateClient((CRpcImpersonateClient *)&v7, this);
  CallerProcessPath = CSecurityVerificationManager::GetCallerProcessPath(this, (unsigned __int16 **)&Block);
  CRpcImpersonateClient::~CRpcImpersonateClient((CRpcImpersonateClient *)&v7);
  if ( (CallerProcessPath & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids,
        CallerProcessPath);
    }
    return CallerProcessPath;
  }
  v4 = Block;
  v5 = -1;
  do
    ++v5;
  while ( *((_WORD *)Block + v5) );
  if ( g_pOneWayAMPPLEnablementAgent )
  {
    WscServiceUtils::OneWayAMPPLEnablementAgent::RemoveNonCompliantProduct(
      (HANDLE *)g_pOneWayAMPPLEnablementAgent,
      (const unsigned __int16 *)Block);
    if ( v4 )
      operator delete(v4);
    return CallerProcessPath;
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids);
  if ( v4 )
    operator delete(v4);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800356b4  mov     rax, rsp
0x1800356b7  mov     [rax+8], rbx
0x1800356bb  mov     [rax+20h], rsi
0x1800356bf  push    rdi
0x1800356c0  sub     rsp, 30h
0x1800356c4  mov     rbx, rcx
0x1800356c7  xor     esi, esi
0x1800356c9  mov     [rax+18h], rsi
0x1800356cd  mov     rdx, rcx; void *
0x1800356d0  lea     rcx, [rax+10h]; this
0x1800356d4  call    ??0CRpcImpersonateClient@@QEAA@PEAX@Z; CRpcImpersonateClient::CRpcImpersonateClient(void *)
0x1800356d9  lea     rdx, [rsp+38h+Block]; unsigned __int16 **
0x1800356de  mov     rcx, rbx; void *
0x1800356e1  call    ?GetCallerProcessPath@CSecurityVerificationManager@@SAJPEAXPEAPEAG@Z; CSecurityVerificationManager::GetCallerProcessPath(void *,ushort * *)
0x1800356e6  mov     edi, eax
0x1800356e8  lea     rcx, [rsp+38h+arg_8]; this
0x1800356ed  call    ??1CRpcImpersonateClient@@QEAA@XZ; CRpcImpersonateClient::~CRpcImpersonateClient(void)
0x1800356f2  test    edi, edi
0x1800356f4  jns     short loc_180035732
0x1800356f6  lea     rdx, WPP_GLOBAL_Control
0x1800356fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180035704  cmp     rcx, rdx
0x180035707  jz      loc_1800357B3
0x18003570d  test    byte ptr [rcx+1Ch], 1
0x180035711  jz      loc_1800357B3
0x180035717  lea     edx, [rsi+2Ch]
0x18003571a  mov     r9d, edi
0x18003571d  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x180035724  mov     rcx, [rcx+10h]
0x180035728  call    WPP_SF_d
0x18003572d  jmp     loc_1800357B3
0x180035732  mov     rbx, [rsp+38h+Block]
0x180035737  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003573b  inc     rax
0x18003573e  cmp     [rbx+rax*2], si
0x180035742  jnz     short loc_18003573B
0x180035744  mov     [rsp+38h+var_18], rbx
0x180035749  mov     [rsp+38h+var_10], rax
0x18003574e  mov     rcx, cs:?g_pOneWayAMPPLEnablementAgent@@3V?$unique_ptr@VOneWayAMPPLEnablementAgent@WscServiceUtils@@U?$default_delete@VOneWayAMPPLEnablementAgent@WscServiceUtils@@@wistd@@@wistd@@A; this
0x180035755  test    rcx, rcx
0x180035758  jnz     short loc_18003579D
0x18003575a  lea     rdx, WPP_GLOBAL_Control
0x180035761  mov     rcx, cs:WPP_GLOBAL_Control
0x180035768  cmp     rcx, rdx
0x18003576b  jz      short loc_180035789
0x18003576d  test    byte ptr [rcx+1Ch], 1
0x180035771  jz      short loc_180035789
0x180035773  mov     edx, 2Dh ; '-'
0x180035778  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x18003577f  mov     rcx, [rcx+10h]
0x180035783  call    WPP_SF_
0x180035788  nop
0x180035789  test    rbx, rbx
0x18003578c  jz      short loc_180035796
0x18003578e  mov     rcx, rbx; Block
0x180035791  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180035796  mov     eax, 80004005h
0x18003579b  jmp     short loc_1800357B5
0x18003579d  mov     rdx, rbx; unsigned __int16 *
0x1800357a0  call    ?RemoveNonCompliantProduct@OneWayAMPPLEnablementAgent@WscServiceUtils@@QEAAXQEBG@Z; WscServiceUtils::OneWayAMPPLEnablementAgent::RemoveNonCompliantProduct(ushort const * const)
0x1800357a5  nop
0x1800357a6  test    rbx, rbx
0x1800357a9  jz      short loc_1800357B3
0x1800357ab  mov     rcx, rbx; Block
0x1800357ae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800357b3  mov     eax, edi
0x1800357b5  mov     rbx, [rsp+38h+arg_0]
0x1800357ba  mov     rsi, [rsp+38h+arg_18]
0x1800357bf  add     rsp, 30h
0x1800357c3  pop     rdi
0x1800357c4  retn
```
