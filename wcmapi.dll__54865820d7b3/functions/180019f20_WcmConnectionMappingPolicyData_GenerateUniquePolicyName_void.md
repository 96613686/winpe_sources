# WcmConnectionMappingPolicyData::GenerateUniquePolicyName(void)

- ea: `0x180019f20`
- end: `0x18001a055`
- name: `?GenerateUniquePolicyName@WcmConnectionMappingPolicyData@@UEAAJXZ`
- size: `309`
- prototype: `__int64 __fastcall(WcmConnectionMappingPolicyData *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x180008a90`
- `0x180018d84`
- `0x180018fc4`
- `0x180019f20`
- `0x18001a9b0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180019f8a`
- `RPCRT4!UuidCreate` at `0x180019f8a`

## pseudocode

```c
__int64 __fastcall WcmConnectionMappingPolicyData::GenerateUniquePolicyName(WcmConnectionMappingPolicyData *this)
{
  RPC_STATUS v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  WcmPolicyManager *v7; // r10
  __int64 v8; // rax
  __int64 v9; // r10
  UUID Uuid; // [rsp+38h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      &WPP_12c04c40514534d8737ded40bb3f712d_Traceguids,
      "WcmConnectionMappingPolicyData::GenerateUniquePolicyName");
  }
  Uuid = 0;
  v2 = UuidCreate(&Uuid);
  try
  {
    v3 = v2;
    if ( v2 < 0 )
      goto LABEL_11;
    v3 = GuidToString(&Uuid, (char *)this + 16);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 16, v4, v5, v6);
      WPP_SF_S(*(_QWORD *)(v9 + 16), 29, &WPP_12c04c40514534d8737ded40bb3f712d_Traceguids, v8);
LABEL_11:
      v7 = WPP_GLOBAL_Control;
    }
  }
  catch ( std::bad_alloc )
  {
    v3 = -2147024882;
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v7 + 25) >= 5u && (*((_BYTE *)v7 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v7 + 2),
      30,
      (unsigned int)&WPP_12c04c40514534d8737ded40bb3f712d_Traceguids,
      (unsigned int)"WcmConnectionMappingPolicyData::GenerateUniquePolicyName",
      v3);
  return v3;
}

```

## disassembly

```asm
0x180019f20  mov     [rsp+arg_8], rbx
0x180019f25  mov     [rsp+arg_10], rsi
0x180019f2a  push    rdi
0x180019f2b  sub     rsp, 50h
0x180019f2f  mov     rax, cs:__security_cookie
0x180019f36  xor     rax, rsp
0x180019f39  mov     [rsp+58h+var_10], rax
0x180019f3e  mov     rsi, rcx
0x180019f41  lea     rdi, WPP_GLOBAL_Control
0x180019f48  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f4f  cmp     rcx, rdi
0x180019f52  jz      short loc_180019F7D
0x180019f54  cmp     byte ptr [rcx+19h], 5
0x180019f58  jb      short loc_180019F7D
0x180019f5a  test    byte ptr [rcx+1Ch], 1
0x180019f5e  jz      short loc_180019F7D
0x180019f60  mov     edx, 1Ch
0x180019f65  lea     r9, aWcmconnectionm_4; "WcmConnectionMappingPolicyData::Generat"...
0x180019f6c  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x180019f73  mov     rcx, [rcx+10h]
0x180019f77  call    WPP_SF_s
0x180019f7c  nop
0x180019f7d  xorps   xmm0, xmm0
0x180019f80  movups  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x180019f85  lea     rcx, [rsp+58h+Uuid]; Uuid
0x180019f8a  call    cs:__imp_UuidCreate
0x180019f91  nop     dword ptr [rax+rax+00h]
0x180019f96  mov     ebx, eax
0x180019f98  test    eax, eax
0x180019f9a  js      short loc_180019FE7
0x180019f9c  lea     rdx, [rsi+10h]
0x180019fa0  lea     rcx, [rsp+58h+Uuid]
0x180019fa5  call    ?GuidToString@@YAJAEAU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GuidToString(_GUID &,std::wstring &)
0x180019faa  mov     ebx, eax
0x180019fac  mov     r10, cs:WPP_GLOBAL_Control
0x180019fb3  cmp     r10, rdi
0x180019fb6  jz      short loc_180019FEE
0x180019fb8  cmp     byte ptr [r10+19h], 4
0x180019fbd  jb      short loc_180019FEE
0x180019fbf  test    byte ptr [r10+1Ch], 1
0x180019fc4  jz      short loc_180019FEE
0x180019fc6  lea     rcx, [rsi+10h]
0x180019fca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180019fcf  mov     edx, 1Dh
0x180019fd4  mov     r9, rax
0x180019fd7  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x180019fde  mov     rcx, [r10+10h]
0x180019fe2  call    WPP_SF_S
0x180019fe7  mov     r10, cs:WPP_GLOBAL_Control
0x180019fee  jmp     short loc_18001A002
0x180019ff0  lea     rdi, WPP_GLOBAL_Control
0x180019ff7  mov     ebx, [rsp+58h+var_28]
0x180019ffb  mov     r10, cs:WPP_GLOBAL_Control
0x18001a002  cmp     r10, rdi
0x18001a005  jz      short loc_18001A035
0x18001a007  cmp     byte ptr [r10+19h], 5
0x18001a00c  jb      short loc_18001A035
0x18001a00e  test    byte ptr [r10+1Ch], 1
0x18001a013  jz      short loc_18001A035
0x18001a015  mov     edx, 1Eh
0x18001a01a  mov     [rsp+58h+var_38], ebx
0x18001a01e  lea     r9, aWcmconnectionm_4; "WcmConnectionMappingPolicyData::Generat"...
0x18001a025  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x18001a02c  mov     rcx, [r10+10h]
0x18001a030  call    WPP_SF_sL
0x18001a035  mov     eax, ebx
0x18001a037  mov     rcx, [rsp+58h+var_10]
0x18001a03c  xor     rcx, rsp; StackCookie
0x18001a03f  call    __security_check_cookie
0x18001a044  mov     rbx, [rsp+58h+arg_8]
0x18001a049  mov     rsi, [rsp+58h+arg_10]
0x18001a04e  add     rsp, 50h
0x18001a052  pop     rdi
0x18001a053  retn
```
