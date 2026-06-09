# SampCheckAccessToLogonUIInformation(_SAMP_OBJECT *)

- ea: `0x180025fe4`
- end: `0x1800261b8`
- name: `?SampCheckAccessToLogonUIInformation@@YAJPEAU_SAMP_OBJECT@@@Z`
- size: `468`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000b150`

## callees

- `0x18001cc00`
- `0x18002421c`
- `0x180025fe4`
- `0x180027e24`
- `0x18002cd80`
- `0x18005645c`
- `0x180074a34`

## import_xrefs

- `ntdll!RtlCheckTokenCapability` at `0x180026132`
- `ntdll!RtlCheckTokenCapability` at `0x180026132`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18002608e`
- `ntdll!RtlCheckTokenMembershipEx` at `0x1800260ee`
- `ntdll!RtlCheckTokenMembershipEx` at `0x180026113`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18002608e`
- `ntdll!RtlCheckTokenMembershipEx` at `0x1800260ee`
- `ntdll!RtlCheckTokenMembershipEx` at `0x180026113`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002604d`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002604d`
- `RPCRT4!RpcRevertToSelf` at `0x180026149`
- `RPCRT4!RpcRevertToSelf` at `0x180026149`
- `RPCRT4!RpcImpersonateClient` at `0x180026045`
- `RPCRT4!RpcImpersonateClient` at `0x180026045`

## pseudocode

```c
__int64 __fastcall SampCheckAccessToLogonUIInformation(struct _SAMP_OBJECT *a1)
{
  int v2; // ebx
  RPC_STATUS v3; // edi
  char v4; // r14
  RPC_STATUS v5; // eax
  int v6; // eax
  __int64 v7; // rax
  char v9; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v10[7]; // [rsp+31h] [rbp-2Fh] BYREF
  _BYTE v11[32]; // [rsp+38h] [rbp-28h] BYREF

  v9 = 0;
  v10[0] = 0;
  if ( SampProductType == NtProductLanManNt )
  {
    v2 = -1073741637;
  }
  else if ( SampIsClientLocal() && *((_DWORD *)a1 + 4) == 4 )
  {
    v3 = 0;
    v4 = 0;
    v5 = RpcImpersonateClient(0);
    v2 = I_RpcMapWin32Status(v5);
    if ( v2 >= 0 )
    {
      v6 = SampRtlWellKnownPrivilegeCheck(0, 7, 0);
      v2 = v6;
      if ( v6 == -1073741727 || v6 == -1073741790 )
      {
        v2 = RtlCheckTokenMembershipEx(0, SampAdministratorsAliasSid, 0, &v9);
        if ( v2 >= 0 && !v9 )
        {
          v7 = *((unsigned int *)a1 + 50);
          memset(v11, 0, 28);
          v2 = SampBuildNT4FullSid(*((void **)SampDefinedDomains + 170 * v7 + 1));
          if ( v2 >= 0 )
          {
            v2 = RtlCheckTokenMembershipEx(0, v11, 0, &v9);
            if ( v2 >= 0 && !v9 )
            {
              v4 = 1;
              v2 = RtlCheckTokenMembershipEx(0, SampAuthenticatedUsersSid, 0, &v9);
              if ( v2 >= 0 && !v9 )
              {
                v2 = RtlCheckTokenCapability(0, SampUserSigninSupportCapabilitySid, v10);
                if ( v2 >= 0 && !v10[0] )
                  v2 = -1073741790;
              }
            }
          }
        }
      }
      v3 = RpcRevertToSelf();
    }
    if ( v2 >= 0 && v3 < 0 )
      v2 = v3;
    if ( v4 )
      SampAuditQueryBlankPassword(a1, v2);
  }
  else
  {
    v2 = -1073741790;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 82, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, (unsigned int)v2, v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180025fe4  mov     [rsp-18h+arg_8], rbx
0x180025fe9  mov     [rsp-18h+arg_10], rsi
0x180025fee  push    rbp
0x180025fef  push    rdi
0x180025ff0  push    r14
0x180025ff2  mov     rbp, rsp
0x180025ff5  sub     rsp, 60h
0x180025ff9  mov     rax, cs:__security_cookie
0x180026000  xor     rax, rsp
0x180026003  mov     [rbp+var_8], rax
0x180026007  cmp     cs:?SampProductType@@3W4_NT_PRODUCT_TYPE@@A, 2; _NT_PRODUCT_TYPE SampProductType
0x18002600e  mov     rsi, rcx
0x180026011  mov     [rbp+var_30], 0
0x180026015  mov     [rbp+var_2F], 0
0x180026019  jnz     short loc_180026025
0x18002601b  mov     ebx, 0C00000BBh
0x180026020  jmp     loc_180026169
0x180026025  call    ?SampIsClientLocal@@YAEXZ; SampIsClientLocal(void)
0x18002602a  test    al, al
0x18002602c  jnz     short loc_180026038
0x18002602e  mov     ebx, 0C0000022h
0x180026033  jmp     loc_180026169
0x180026038  cmp     dword ptr [rsi+10h], 4
0x18002603c  jnz     short loc_18002602E
0x18002603e  xor     ecx, ecx; BindingHandle
0x180026040  xor     edi, edi
0x180026042  xor     r14b, r14b
0x180026045  call    cs:__imp_RpcImpersonateClient
0x18002604b  mov     ecx, eax; Status
0x18002604d  call    cs:__imp_I_RpcMapWin32Status
0x180026053  mov     ebx, eax
0x180026055  test    eax, eax
0x180026057  js      loc_180026151
0x18002605d  xor     r8d, r8d
0x180026060  lea     edx, [rdi+7]
0x180026063  xor     ecx, ecx
0x180026065  call    SampRtlWellKnownPrivilegeCheck
0x18002606a  mov     ebx, eax
0x18002606c  cmp     eax, 0C0000061h
0x180026071  jz      short loc_18002607E
0x180026073  cmp     eax, 0C0000022h
0x180026078  jnz     loc_180026149
0x18002607e  mov     rdx, cs:SampAdministratorsAliasSid
0x180026085  lea     r9, [rbp+var_30]
0x180026089  xor     r8d, r8d
0x18002608c  xor     ecx, ecx
0x18002608e  call    cs:__imp_RtlCheckTokenMembershipEx
0x180026094  mov     ebx, eax
0x180026096  test    eax, eax
0x180026098  js      loc_180026149
0x18002609e  cmp     [rbp+var_30], dil
0x1800260a2  jnz     loc_180026149
0x1800260a8  mov     eax, [rsi+0C8h]
0x1800260ae  lea     r8, [rbp+var_28]
0x1800260b2  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800260b9  xorps   xmm0, xmm0
0x1800260bc  mov     edx, [rsi+0F8h]
0x1800260c2  movups  xmmword ptr [rbp+var_28], xmm0
0x1800260c6  imul    r9, rax, 550h
0x1800260cd  movups  xmmword ptr [rbp+var_28+0Ch], xmm0
0x1800260d1  mov     rcx, [r9+rcx+8]; Src
0x1800260d6  call    SampBuildNT4FullSid
0x1800260db  mov     ebx, eax
0x1800260dd  test    eax, eax
0x1800260df  js      short loc_180026149
0x1800260e1  lea     r9, [rbp+var_30]
0x1800260e5  xor     r8d, r8d
0x1800260e8  lea     rdx, [rbp+var_28]
0x1800260ec  xor     ecx, ecx
0x1800260ee  call    cs:__imp_RtlCheckTokenMembershipEx
0x1800260f4  mov     ebx, eax
0x1800260f6  test    eax, eax
0x1800260f8  js      short loc_180026149
0x1800260fa  cmp     [rbp+var_30], dil
0x1800260fe  jnz     short loc_180026149
0x180026100  mov     rdx, cs:SampAuthenticatedUsersSid
0x180026107  lea     r9, [rbp+var_30]
0x18002610b  xor     r8d, r8d
0x18002610e  xor     ecx, ecx
0x180026110  mov     r14b, 1
0x180026113  call    cs:__imp_RtlCheckTokenMembershipEx
0x180026119  mov     ebx, eax
0x18002611b  test    eax, eax
0x18002611d  js      short loc_180026149
0x18002611f  cmp     [rbp+var_30], dil
0x180026123  jnz     short loc_180026149
0x180026125  mov     rdx, cs:SampUserSigninSupportCapabilitySid
0x18002612c  lea     r8, [rbp+var_2F]
0x180026130  xor     ecx, ecx
0x180026132  call    cs:__imp_RtlCheckTokenCapability
0x180026138  mov     ebx, eax
0x18002613a  test    eax, eax
0x18002613c  js      short loc_180026149
0x18002613e  cmp     [rbp+var_2F], dil
0x180026142  jnz     short loc_180026149
0x180026144  mov     ebx, 0C0000022h
0x180026149  call    cs:__imp_RpcRevertToSelf
0x18002614f  mov     edi, eax
0x180026151  test    ebx, ebx
0x180026153  js      short loc_18002615A
0x180026155  test    edi, edi
0x180026157  cmovs   ebx, edi
0x18002615a  test    r14b, r14b
0x18002615d  jz      short loc_180026169
0x18002615f  mov     edx, ebx; int
0x180026161  mov     rcx, rsi; struct _SAMP_OBJECT *
0x180026164  call    ?SampAuditQueryBlankPassword@@YAXPEAU_SAMP_OBJECT@@J@Z; SampAuditQueryBlankPassword(_SAMP_OBJECT *,long)
0x180026169  mov     rcx, cs:WPP_GLOBAL_Control
0x180026170  test    dword ptr [rcx+44h], 20000h
0x180026177  jz      short loc_180026195
0x180026179  mov     rcx, [rcx+38h]
0x18002617d  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x180026184  mov     edx, 52h ; 'R'
0x180026189  mov     [rsp+60h+var_40], ebx
0x18002618d  mov     r9d, ebx
0x180026190  call    WPP_SF_Dd
0x180026195  mov     eax, ebx
0x180026197  mov     rcx, [rbp+var_8]
0x18002619b  xor     rcx, rsp; StackCookie
0x18002619e  call    __security_check_cookie
0x1800261a3  lea     r11, [rsp+60h+var_s0]
0x1800261a8  mov     rbx, [r11+28h]
0x1800261ac  mov     rsi, [r11+30h]
0x1800261b0  mov     rsp, r11
0x1800261b3  pop     r14
0x1800261b5  pop     rdi
0x1800261b6  pop     rbp
0x1800261b7  retn
```
