# WscServiceUtils::AddNonCompliantProduct(void *)

- ea: `0x18003532c`
- end: `0x18003543d`
- name: `?AddNonCompliantProduct@WscServiceUtils@@YAJPEAX@Z`
- size: `273`
- prototype: `__int64 __fastcall(WscServiceUtils *__hidden this, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180035518`

## callees

- `0x180008e48`
- `0x18001abb0`
- `0x18001bb90`
- `0x18001fb24`
- `0x1800202e8`
- `0x180029e74`
- `0x1800351ac`
- `0x18003532c`

## pseudocode

```c
__int64 __fastcall WscServiceUtils::AddNonCompliantProduct(WscServiceUtils *this, void *a2)
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
        42,
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
    WscServiceUtils::OneWayAMPPLEnablementAgent::AddNonCompliantProduct(
      (HANDLE *)g_pOneWayAMPPLEnablementAgent,
      (const unsigned __int16 *)Block);
    if ( v4 )
      operator delete(v4);
    return CallerProcessPath;
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids);
  if ( v4 )
    operator delete(v4);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18003532c  mov     rax, rsp
0x18003532f  mov     [rax+8], rbx
0x180035333  mov     [rax+20h], rsi
0x180035337  push    rdi
0x180035338  sub     rsp, 30h
0x18003533c  mov     rbx, rcx
0x18003533f  xor     esi, esi
0x180035341  mov     [rax+18h], rsi
0x180035345  mov     rdx, rcx; void *
0x180035348  lea     rcx, [rax+10h]; this
0x18003534c  call    ??0CRpcImpersonateClient@@QEAA@PEAX@Z; CRpcImpersonateClient::CRpcImpersonateClient(void *)
0x180035351  lea     rdx, [rsp+38h+Block]; unsigned __int16 **
0x180035356  mov     rcx, rbx; void *
0x180035359  call    ?GetCallerProcessPath@CSecurityVerificationManager@@SAJPEAXPEAPEAG@Z; CSecurityVerificationManager::GetCallerProcessPath(void *,ushort * *)
0x18003535e  mov     edi, eax
0x180035360  lea     rcx, [rsp+38h+arg_8]; this
0x180035365  call    ??1CRpcImpersonateClient@@QEAA@XZ; CRpcImpersonateClient::~CRpcImpersonateClient(void)
0x18003536a  test    edi, edi
0x18003536c  jns     short loc_1800353AA
0x18003536e  lea     rdx, WPP_GLOBAL_Control
0x180035375  mov     rcx, cs:WPP_GLOBAL_Control
0x18003537c  cmp     rcx, rdx
0x18003537f  jz      loc_18003542B
0x180035385  test    byte ptr [rcx+1Ch], 1
0x180035389  jz      loc_18003542B
0x18003538f  lea     edx, [rsi+2Ah]
0x180035392  mov     r9d, edi
0x180035395  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x18003539c  mov     rcx, [rcx+10h]
0x1800353a0  call    WPP_SF_d
0x1800353a5  jmp     loc_18003542B
0x1800353aa  mov     rbx, [rsp+38h+Block]
0x1800353af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800353b3  inc     rax
0x1800353b6  cmp     [rbx+rax*2], si
0x1800353ba  jnz     short loc_1800353B3
0x1800353bc  mov     [rsp+38h+var_18], rbx
0x1800353c1  mov     [rsp+38h+var_10], rax
0x1800353c6  mov     rcx, cs:?g_pOneWayAMPPLEnablementAgent@@3V?$unique_ptr@VOneWayAMPPLEnablementAgent@WscServiceUtils@@U?$default_delete@VOneWayAMPPLEnablementAgent@WscServiceUtils@@@wistd@@@wistd@@A; this
0x1800353cd  test    rcx, rcx
0x1800353d0  jnz     short loc_180035415
0x1800353d2  lea     rdx, WPP_GLOBAL_Control
0x1800353d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800353e0  cmp     rcx, rdx
0x1800353e3  jz      short loc_180035401
0x1800353e5  test    byte ptr [rcx+1Ch], 1
0x1800353e9  jz      short loc_180035401
0x1800353eb  mov     edx, 2Bh ; '+'
0x1800353f0  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x1800353f7  mov     rcx, [rcx+10h]
0x1800353fb  call    WPP_SF_
0x180035400  nop
0x180035401  test    rbx, rbx
0x180035404  jz      short loc_18003540E
0x180035406  mov     rcx, rbx; Block
0x180035409  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003540e  mov     eax, 80004005h
0x180035413  jmp     short loc_18003542D
0x180035415  mov     rdx, rbx; unsigned __int16 *
0x180035418  call    ?AddNonCompliantProduct@OneWayAMPPLEnablementAgent@WscServiceUtils@@QEAAXQEBG@Z; WscServiceUtils::OneWayAMPPLEnablementAgent::AddNonCompliantProduct(ushort const * const)
0x18003541d  nop
0x18003541e  test    rbx, rbx
0x180035421  jz      short loc_18003542B
0x180035423  mov     rcx, rbx; Block
0x180035426  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003542b  mov     eax, edi
0x18003542d  mov     rbx, [rsp+38h+arg_0]
0x180035432  mov     rsi, [rsp+38h+arg_18]
0x180035437  add     rsp, 30h
0x18003543b  pop     rdi
0x18003543c  retn
```
