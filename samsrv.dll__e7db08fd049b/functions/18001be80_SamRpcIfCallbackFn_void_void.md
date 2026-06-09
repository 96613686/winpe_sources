# SamRpcIfCallbackFn(void *,void *)

- ea: `0x18001be80`
- end: `0x18001c0d6`
- name: `?SamRpcIfCallbackFn@@YAJPEAX0@Z`
- size: `598`
- prototype: `int(void *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001be80`
- `0x180027d08`
- `0x18002cd80`
- `0x18008d7f8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001bfe3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001bfe3`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001bee3`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001bee3`
- `RPCRT4!RpcImpersonateClient` at `0x18001bfc9`
- `RPCRT4!RpcImpersonateClient` at `0x18001bfc9`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001bff4`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001c08f`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001bff4`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001c08f`

## pseudocode

```c
__int64 __fastcall SamRpcIfCallbackFn(void *a1, void *a2)
{
  unsigned int v3; // ebx
  struct _SAMP_RPC_FUNCTION_PROPERTIES near **v4; // rdx
  int v5; // eax
  char v7; // cl
  int v8; // edx
  PSID v9; // rsi
  RPC_STATUS v10; // eax
  WINBOOL IsMember[4]; // [rsp+30h] [rbp-98h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+40h] [rbp-88h] BYREF
  __int128 v13; // [rsp+48h] [rbp-80h]
  __int128 v14; // [rsp+58h] [rbp-70h]
  __int128 v15; // [rsp+68h] [rbp-60h]
  __int128 v16; // [rsp+78h] [rbp-50h]
  __int128 v17; // [rsp+88h] [rbp-40h]
  __int128 v18; // [rsp+98h] [rbp-30h]
  __int64 v19; // [rsp+A8h] [rbp-20h]

  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v19 = 0;
  v17 = 0;
  v18 = 0;
  RpcCallAttributes[0] = 2;
  RpcCallAttributes[1] = 96;
  v3 = RpcServerInqCallAttributesW(a2, RpcCallAttributes);
  if ( v3 )
    goto LABEL_5;
  if ( (unsigned __int16)v18 >= 0x52u )
  {
    v3 = 1745;
    goto LABEL_5;
  }
  v4 = &SampRPCFunctionProperties + (unsigned __int16)v18;
  v5 = *(_DWORD *)v4;
  if ( !_bittest(&v5, v16) )
  {
    v3 = 1703;
    goto LABEL_5;
  }
  if ( SamTCPDisabledAtBoot && (_DWORD)v16 == 1 )
  {
    v3 = 1703;
    goto LABEL_5;
  }
  v7 = *((_BYTE *)v4 + 4);
  v8 = DWORD1(v16);
  if ( (v7 & 1) != 0 && DWORD1(v16) != 1 )
  {
    v3 = 5;
    goto LABEL_5;
  }
  if ( (unsigned int)(v15 - 2) <= 3 )
  {
    v3 = 5;
    goto LABEL_5;
  }
  if ( (v7 & 2) == 0 )
    goto LABEL_14;
  v9 = SampAuthenticatedUsersSid;
  IsMember[0] = 0;
  v3 = RpcImpersonateClient(a2);
  if ( v3 )
  {
    IsMember[0] = 0;
  }
  else if ( CheckTokenMembership(0, v9, IsMember) )
  {
    v10 = RpcRevertToSelfEx(a2);
    if ( v10 )
      v3 = v10;
  }
  else
  {
    v3 = 5;
    IsMember[0] = 0;
    RpcRevertToSelfEx(a2);
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_DdD(WPP_GLOBAL_Control[3].Buffer, 78, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, v3, v3, v3);
  if ( !v3 )
  {
    if ( !IsMember[0] )
    {
      v3 = 5;
      goto LABEL_5;
    }
    v8 = DWORD1(v16);
LABEL_14:
    if ( v8 != 1 && SampRestrictRemoteSessionAccess )
      v3 = SampCheckRpcRemoteCallerAccess(a2);
  }
LABEL_5:
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_DdD(WPP_GLOBAL_Control[3].Buffer, 45, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, v3, v3, v3);
  return v3;
}

```

## disassembly

```asm
0x18001be80  mov     r11, rsp
0x18001be83  push    rbx
0x18001be84  sub     rsp, 0C0h
0x18001be8b  mov     rax, cs:__security_cookie
0x18001be92  xor     rax, rsp
0x18001be95  mov     [rsp+0C8h+var_18], rax
0x18001be9d  xorps   xmm0, xmm0
0x18001bea0  mov     [r11+18h], rdi
0x18001bea4  movups  [rsp+0C8h+var_80], xmm0
0x18001bea9  mov     rdi, rdx
0x18001beac  xor     eax, eax
0x18001beae  movups  [rsp+0C8h+var_70], xmm0
0x18001beb3  mov     rcx, rdi; ClientBinding
0x18001beb6  lea     rdx, [rsp+0C8h+RpcCallAttributes]; RpcCallAttributes
0x18001bebb  movups  [rsp+0C8h+var_60], xmm0
0x18001bec0  movups  [rsp+0C8h+var_50], xmm0
0x18001bec5  mov     [r11-20h], rax
0x18001bec9  movups  xmmword ptr [r11-40h], xmm0
0x18001bece  movups  xmmword ptr [r11-30h], xmm0
0x18001bed3  mov     [rsp+0C8h+RpcCallAttributes], 2
0x18001bedb  mov     [rsp+0C8h+var_84], 60h ; '`'
0x18001bee3  call    cs:__imp_RpcServerInqCallAttributesW
0x18001bee9  mov     ebx, eax
0x18001beeb  test    eax, eax
0x18001beed  jnz     short loc_18001BF1B
0x18001beef  movzx   eax, word ptr [rsp+0C8h+var_30]
0x18001bef7  cmp     eax, 52h ; 'R'
0x18001befa  jnb     loc_18001C05B
0x18001bf00  lea     rcx, ?SampRPCFunctionProperties@@3PAU_SAMP_RPC_FUNCTION_PROPERTIES@@A; _SAMP_RPC_FUNCTION_PROPERTIES near * SampRPCFunctionProperties
0x18001bf07  lea     rdx, [rcx+rax*8]
0x18001bf0b  mov     ecx, dword ptr [rsp+0C8h+var_50]
0x18001bf0f  mov     eax, [rdx]
0x18001bf11  bt      eax, ecx
0x18001bf14  jb      short loc_18001BF52
0x18001bf16  mov     ebx, 6A7h
0x18001bf1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf22  mov     rdi, [rsp+0C8h+arg_10]
0x18001bf2a  test    dword ptr [rcx+44h], 20000h
0x18001bf31  jnz     loc_18001C036
0x18001bf37  mov     eax, ebx
0x18001bf39  mov     rcx, [rsp+0C8h+var_18]
0x18001bf41  xor     rcx, rsp; StackCookie
0x18001bf44  call    __security_check_cookie
0x18001bf49  add     rsp, 0C0h
0x18001bf50  pop     rbx
0x18001bf51  retn
0x18001bf52  cmp     cs:?SamTCPDisabledAtBoot@@3EA, 0; uchar SamTCPDisabledAtBoot
0x18001bf59  jz      short loc_18001BF67
0x18001bf5b  cmp     ecx, 1
0x18001bf5e  jnz     short loc_18001BF67
0x18001bf60  mov     ebx, 6A7h
0x18001bf65  jmp     short loc_18001BF1B
0x18001bf67  movzx   ecx, byte ptr [rdx+4]
0x18001bf6b  mov     edx, dword ptr [rsp+0C8h+var_50+4]
0x18001bf6f  test    cl, 1
0x18001bf72  jnz     loc_18001C065
0x18001bf78  mov     eax, dword ptr [rsp+0C8h+var_60]
0x18001bf7c  add     eax, 0FFFFFFFEh
0x18001bf7f  cmp     eax, 3
0x18001bf82  jbe     loc_18001C078
0x18001bf88  test    cl, 2
0x18001bf8b  jnz     short loc_18001BFAF
0x18001bf8d  cmp     edx, 1
0x18001bf90  jz      short loc_18001BF1B
0x18001bf92  cmp     cs:?SampRestrictRemoteSessionAccess@@3PEAXEA, 0; void * SampRestrictRemoteSessionAccess
0x18001bf9a  jz      loc_18001BF1B
0x18001bfa0  mov     rcx, rdi; BindingHandle
0x18001bfa3  call    ?SampCheckRpcRemoteCallerAccess@@YAJPEAX@Z; SampCheckRpcRemoteCallerAccess(void *)
0x18001bfa8  mov     ebx, eax
0x18001bfaa  jmp     loc_18001BF1B
0x18001bfaf  mov     [rsp+0C8h+arg_0], rsi
0x18001bfb7  mov     rcx, rdi; BindingHandle
0x18001bfba  mov     rsi, cs:SampAuthenticatedUsersSid
0x18001bfc1  mov     [rsp+0C8h+IsMember], 0
0x18001bfc9  call    cs:__imp_RpcImpersonateClient
0x18001bfcf  mov     ebx, eax
0x18001bfd1  test    eax, eax
0x18001bfd3  jnz     loc_18001C09A
0x18001bfd9  lea     r8, [rsp+0C8h+IsMember]; IsMember
0x18001bfde  mov     rdx, rsi; SidToCheck
0x18001bfe1  xor     ecx, ecx; TokenHandle
0x18001bfe3  call    cs:__imp_CheckTokenMembership
0x18001bfe9  mov     rcx, rdi; BindingHandle
0x18001bfec  test    eax, eax
0x18001bfee  jz      loc_18001C082
0x18001bff4  call    cs:__imp_RpcRevertToSelfEx
0x18001bffa  test    eax, eax
0x18001bffc  cmovnz  ebx, eax
0x18001bfff  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c006  mov     rsi, [rsp+0C8h+arg_0]
0x18001c00e  test    dword ptr [rcx+44h], 20000h
0x18001c015  jnz     loc_18001C0A7
0x18001c01b  test    ebx, ebx
0x18001c01d  jnz     loc_18001BF1B
0x18001c023  cmp     [rsp+0C8h+IsMember], ebx
0x18001c027  jz      loc_18001C0CC
0x18001c02d  mov     edx, dword ptr [rsp+0C8h+var_50+4]
0x18001c031  jmp     loc_18001BF8D
0x18001c036  mov     rcx, [rcx+38h]
0x18001c03a  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18001c041  mov     edx, 2Dh ; '-'
0x18001c046  mov     [rsp+0C8h+var_A0], ebx
0x18001c04a  mov     r9d, ebx
0x18001c04d  mov     [rsp+0C8h+var_A8], ebx
0x18001c051  call    WPP_SF_DdD
0x18001c056  jmp     loc_18001BF37
0x18001c05b  mov     ebx, 6D1h
0x18001c060  jmp     loc_18001BF1B
0x18001c065  cmp     edx, 1
0x18001c068  jz      loc_18001BF78
0x18001c06e  mov     ebx, 5
0x18001c073  jmp     loc_18001BF1B
0x18001c078  mov     ebx, 5
0x18001c07d  jmp     loc_18001BF1B
0x18001c082  mov     ebx, 5
0x18001c087  mov     [rsp+0C8h+IsMember], 0
0x18001c08f  call    cs:__imp_RpcRevertToSelfEx
0x18001c095  jmp     loc_18001BFFF
0x18001c09a  mov     [rsp+0C8h+IsMember], 0
0x18001c0a2  jmp     loc_18001BFFF
0x18001c0a7  mov     rcx, [rcx+38h]
0x18001c0ab  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18001c0b2  mov     edx, 4Eh ; 'N'
0x18001c0b7  mov     [rsp+0C8h+var_A0], ebx
0x18001c0bb  mov     r9d, ebx
0x18001c0be  mov     [rsp+0C8h+var_A8], ebx
0x18001c0c2  call    WPP_SF_DdD
0x18001c0c7  jmp     loc_18001C01B
0x18001c0cc  mov     ebx, 5
0x18001c0d1  jmp     loc_18001BF1B
```
