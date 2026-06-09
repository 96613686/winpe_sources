# PreAuthMgrCreateOneXPort(MSMSEC_INTF_CONTEXT *,DOT11_MSMSEC_CONNECTION_PROFILE *,void * *)

- ea: `0x1800699b4`
- end: `0x180069db6`
- name: `?PreAuthMgrCreateOneXPort@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEAPEAX@Z`
- size: `1026`
- prototype: `unsigned int __fastcall(struct MSMSEC_INTF_CONTEXT *, struct DOT11_MSMSEC_CONNECTION_PROFILE *, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180068050`

## callees

- `0x18000892c`
- `0x180008998`
- `0x1800169c0`
- `0x1800198d4`
- `0x180025fd0`
- `0x180043a30`
- `0x180044554`
- `0x18004456c`
- `0x1800445e4`
- `0x1800699b4`
- `0x18006b20c`
- `0x180094810`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180069d54`
- `RPCRT4!RpcStringFreeW` at `0x180069d54`
- `RPCRT4!UuidToStringW` at `0x180069a85`
- `RPCRT4!UuidToStringW` at `0x180069a85`
- `RPCRT4!UuidCreate` at `0x180069a6d`
- `RPCRT4!UuidCreate` at `0x180069a6d`
- `OneX!OneXSetAuthParams` at `0x180069cca`
- `OneX!OneXSetAuthParams` at `0x180069cca`
- `OneX!OneXSetRuntimeState` at `0x180069c4b`
- `OneX!OneXSetRuntimeState` at `0x180069c4b`
- `OneX!OneXCreateSupplicantPort` at `0x180069bc0`
- `OneX!OneXCreateSupplicantPort` at `0x180069bc0`
- `OneX!OneXDestroySupplicantPort` at `0x180069d0d`
- `OneX!OneXDestroySupplicantPort` at `0x180069d0d`

## string_xrefs

- `0x180069c1c`: `PreAuthMgrCreateOneXPort`

## pseudocode

```c
__int64 __fastcall PreAuthMgrCreateOneXPort(
        struct MSMSEC_INTF_CONTEXT *a1,
        struct DOT11_MSMSEC_CONNECTION_PROFILE *a2,
        void **a3)
{
  __int64 v6; // r14
  unsigned int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r8
  unsigned int AuthParams; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  unsigned int v18; // [rsp+50h] [rbp-B0h] BYREF
  void *v19; // [rsp+58h] [rbp-A8h] BYREF
  RPC_WSTR StringUuid; // [rsp+60h] [rbp-A0h] BYREF
  void *v21; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v22[2176]; // [rsp+70h] [rbp-90h] BYREF
  struct MSMSEC_INTF_CONTEXT *Src; // [rsp+8F0h] [rbp+7F0h] BYREF
  int v24; // [rsp+8F8h] [rbp+7F8h]
  UUID Uuid; // [rsp+8FCh] [rbp+7FCh] BYREF
  wchar_t Buffer[1026]; // [rsp+90Ch] [rbp+80Ch] BYREF
  int v27; // [rsp+1110h] [rbp+1010h]
  unsigned int (__fastcall *v28)(void *, void *, unsigned int, struct _ONEX_RESULT *); // [rsp+1118h] [rbp+1018h]
  unsigned int (__fastcall *v29)(void *, void *, size_t, unsigned __int8 *); // [rsp+1120h] [rbp+1020h]
  unsigned int (__fastcall *v30)(struct MSMSEC_INTF_CONTEXT *, void *); // [rsp+1128h] [rbp+1028h]
  __int64 v31; // [rsp+1130h] [rbp+1030h]
  __int64 v32; // [rsp+1138h] [rbp+1038h]
  __int64 v33; // [rsp+1140h] [rbp+1040h]
  unsigned int (__fastcall *v34)(void *); // [rsp+1148h] [rbp+1048h]
  __int64 v35; // [rsp+1150h] [rbp+1050h]
  __int64 v36; // [rsp+1158h] [rbp+1058h]

  v19 = 0;
  memset_0(&Src, 0, 0x880u);
  v18 = 0;
  v21 = 0;
  StringUuid = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_c3b9857fbeac3feae34c8ad1e975ce4f_Traceguids);
  v6 = *((_QWORD *)a2 + 6);
  v7 = *((_DWORD *)a2 + 10);
  Src = a1;
  v24 = 0;
  UuidCreate(&Uuid);
  if ( !UuidToStringW(&Uuid, &StringUuid)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_c3b9857fbeac3feae34c8ad1e975ce4f_Traceguids, StringUuid);
  }
  swprintf_s(
    Buffer,
    0x401u,
    L"%s PreAuth %02X:%02X:%02X:%02X:%02X:%02X",
    (char *)a1 + 48,
    *((unsigned __int8 *)a1 + 2982),
    *((unsigned __int8 *)a1 + 2983),
    *((unsigned __int8 *)a1 + 2984),
    *((unsigned __int8 *)a1 + 2985),
    *((unsigned __int8 *)a1 + 2986),
    *((unsigned __int8 *)a1 + 2987));
  v27 = *((_DWORD *)a1 + 525);
  v36 = 0;
  v34 = PreAuthMgrOneXFree;
  v33 = 0;
  v29 = PreAuthMgrOneXSendPacket;
  v28 = PreAuthMgrOneXUpdateResult;
  v30 = PreAuthMgrOneXDestroyPortCompletion;
  v31 = 0;
  v32 = 0;
  v35 = 0;
  memcpy_0(v22, &Src, sizeof(v22));
  v8 = OneXCreateSupplicantPort(1, v22, v7, v6, &v19, 0);
  v9 = v8;
  if ( v8 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v11 = 14;
LABEL_12:
      WPP_SF_d(v10[7], v11, WPP_c3b9857fbeac3feae34c8ad1e975ce4f_Traceguids, v8);
LABEL_34:
      v10 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_35;
    }
    goto LABEL_35;
  }
  TraceAdapterId(*((_DWORD *)a1 + 624), ">>> Refing >>>");
  SecMgrRefAdapterEx(a1, "PreAuthMgrCreateOneXPort", 93);
  v12 = *((_QWORD *)a1 + 363);
  if ( v12 )
    v13 = *(_QWORD *)(v12 + 8);
  else
    v13 = 0;
  AuthParams = OneXSetRuntimeState(1, v19, v13, 0);
  v9 = AuthParams;
  if ( AuthParams )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v16 = 15;
LABEL_28:
      WPP_SF_d(v15[7], v16, WPP_c3b9857fbeac3feae34c8ad1e975ce4f_Traceguids, AuthParams);
    }
  }
  else
  {
    AuthParams = PmkCacheGetAuthParams((struct MSMSEC_INTF_CONTEXT *)((char *)a1 + 3000), &v18, &v21);
    v9 = AuthParams;
    if ( AuthParams )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v16 = 16;
        goto LABEL_28;
      }
    }
    else
    {
      AuthParams = OneXSetAuthParams(1, v19, v18, v21, 0);
      v9 = AuthParams;
      if ( !AuthParams )
      {
        *a3 = v19;
        goto LABEL_34;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v16 = 17;
        goto LABEL_28;
      }
    }
  }
  v8 = OneXDestroySupplicantPort(1, v19, 0);
  if ( !v8 )
    goto LABEL_34;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v11 = 18;
    goto LABEL_12;
  }
LABEL_35:
  if ( StringUuid )
  {
    RpcStringFreeW(&StringUuid);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x100) != 0 )
    WPP_SF_d(v10[7], 19, WPP_c3b9857fbeac3feae34c8ad1e975ce4f_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x1800699b4  mov     [rsp-8+arg_18], rbx
0x1800699b9  push    rbp
0x1800699ba  push    rsi
0x1800699bb  push    rdi
0x1800699bc  push    r12
0x1800699be  push    r13
0x1800699c0  push    r14
0x1800699c2  push    r15
0x1800699c4  lea     rbp, [rsp-1080h]
0x1800699cc  mov     eax, 1180h
0x1800699d1  call    _alloca_probe
0x1800699d6  sub     rsp, rax
0x1800699d9  mov     rax, cs:__security_cookie
0x1800699e0  xor     rax, rsp
0x1800699e3  mov     [rbp+10B0h+var_40], rax
0x1800699ea  mov     rsi, r8
0x1800699ed  mov     rbx, rdx
0x1800699f0  mov     rdi, rcx
0x1800699f3  xor     r15d, r15d
0x1800699f6  xor     edx, edx; Val
0x1800699f8  mov     [rsp+11B0h+var_1158], r15
0x1800699fd  mov     r8d, 880h; Size
0x180069a03  lea     rcx, [rbp+10B0h+Src]; void *
0x180069a0a  call    memset_0
0x180069a0f  mov     [rsp+11B0h+var_1160], r15d
0x180069a14  mov     [rsp+11B0h+var_1148], r15
0x180069a19  mov     [rsp+11B0h+StringUuid], r15
0x180069a1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180069a25  lea     r12, WPP_GLOBAL_Control
0x180069a2c  lea     r13, WPP_c3b9857fbeac3feae34c8ad1e975ce4f_Traceguids
0x180069a33  cmp     rcx, r12
0x180069a36  jz      short loc_180069A51
0x180069a38  test    dword ptr [rcx+44h], 100h
0x180069a3f  jz      short loc_180069A51
0x180069a41  mov     rcx, [rcx+38h]
0x180069a45  lea     edx, [r15+0Ch]
0x180069a49  mov     r8, r13
0x180069a4c  call    WPP_SF_
0x180069a51  mov     r14, [rbx+30h]
0x180069a55  lea     rcx, [rbp+10B0h+Uuid]; Uuid
0x180069a5c  mov     ebx, [rbx+28h]
0x180069a5f  mov     [rbp+10B0h+Src], rdi
0x180069a66  mov     [rbp+10B0h+var_8B8], r15d
0x180069a6d  call    cs:__imp_UuidCreate
0x180069a74  nop     dword ptr [rax+rax+00h]
0x180069a79  lea     rdx, [rsp+11B0h+StringUuid]; StringUuid
0x180069a7e  lea     rcx, [rbp+10B0h+Uuid]; Uuid
0x180069a85  call    cs:__imp_UuidToStringW
0x180069a8c  nop     dword ptr [rax+rax+00h]
0x180069a91  test    eax, eax
0x180069a93  jnz     short loc_180069ABB
0x180069a95  mov     rcx, cs:WPP_GLOBAL_Control
0x180069a9c  cmp     rcx, r12
0x180069a9f  jz      short loc_180069ABB
0x180069aa1  test    byte ptr [rcx+44h], 2
0x180069aa5  jz      short loc_180069ABB
0x180069aa7  mov     r9, [rsp+11B0h+StringUuid]
0x180069aac  lea     edx, [rax+0Dh]
0x180069aaf  mov     rcx, [rcx+38h]
0x180069ab3  mov     r8, r13
0x180069ab6  call    WPP_SF_S
0x180069abb  movzx   ecx, byte ptr [rdi+0BAAh]
0x180069ac2  lea     r9, [rdi+30h]
0x180069ac6  movzx   edx, byte ptr [rdi+0BA9h]
0x180069acd  movzx   r8d, byte ptr [rdi+0BA8h]
0x180069ad5  movzx   eax, byte ptr [rdi+0BABh]
0x180069adc  movzx   r10d, byte ptr [rdi+0BA7h]
0x180069ae4  movzx   r11d, byte ptr [rdi+0BA6h]
0x180069aec  mov     [rsp+11B0h+var_1168], eax
0x180069af0  mov     [rsp+11B0h+var_1170], ecx
0x180069af4  lea     rcx, [rbp+10B0h+Buffer]; Buffer
0x180069afb  mov     [rsp+11B0h+var_1178], edx
0x180069aff  mov     edx, 401h; BufferCount
0x180069b04  mov     [rsp+11B0h+var_1180], r8d
0x180069b09  lea     r8, aSPreauth02x02x; "%s PreAuth %02X:%02X:%02X:%02X:%02X:%02"...
0x180069b10  mov     dword ptr [rsp+11B0h+var_1188], r10d
0x180069b15  mov     dword ptr [rsp+11B0h+var_1190], r11d
0x180069b1a  call    swprintf_s
0x180069b1f  mov     eax, [rdi+834h]
0x180069b25  lea     rcx, [rsp+11B0h+var_1140]; void *
0x180069b2a  mov     [rbp+10B0h+var_A0], eax
0x180069b30  lea     rdx, [rbp+10B0h+Src]; Src
0x180069b37  lea     rax, ?PreAuthMgrOneXFree@@YAKPEAX@Z; PreAuthMgrOneXFree(void *)
0x180069b3e  mov     [rbp+10B0h+var_58], r15
0x180069b45  mov     [rbp+10B0h+var_68], rax
0x180069b4c  mov     r8d, 880h; Size
0x180069b52  lea     rax, ?PreAuthMgrOneXSendPacket@@YAKPEAX0KPEAE@Z; PreAuthMgrOneXSendPacket(void *,void *,ulong,uchar *)
0x180069b59  mov     [rbp+10B0h+var_70], r15
0x180069b60  mov     [rbp+10B0h+var_90], rax
0x180069b67  lea     rax, ?PreAuthMgrOneXUpdateResult@@YAKPEAX0KPEAU_ONEX_RESULT@@@Z; PreAuthMgrOneXUpdateResult(void *,void *,ulong,_ONEX_RESULT *)
0x180069b6e  mov     [rbp+10B0h+var_98], rax
0x180069b75  lea     rax, ?PreAuthMgrOneXDestroyPortCompletion@@YAKPEAX0@Z; PreAuthMgrOneXDestroyPortCompletion(void *,void *)
0x180069b7c  mov     [rbp+10B0h+var_88], rax
0x180069b83  mov     [rbp+10B0h+var_80], r15
0x180069b8a  mov     [rbp+10B0h+var_78], r15
0x180069b91  mov     [rbp+10B0h+var_60], r15
0x180069b98  call    memcpy_0
0x180069b9d  mov     r9, r14
0x180069ba0  mov     [rsp+11B0h+var_1188], r15
0x180069ba5  lea     rax, [rsp+11B0h+var_1158]
0x180069baa  mov     r14d, 1
0x180069bb0  mov     ecx, r14d
0x180069bb3  mov     [rsp+11B0h+var_1190], rax
0x180069bb8  mov     r8d, ebx
0x180069bbb  lea     rdx, [rsp+11B0h+var_1140]
0x180069bc0  call    cs:__imp_OneXCreateSupplicantPort
0x180069bc7  nop     dword ptr [rax+rax+00h]
0x180069bcc  mov     ebx, eax
0x180069bce  test    eax, eax
0x180069bd0  jz      short loc_180069C04
0x180069bd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180069bd9  cmp     rcx, r12
0x180069bdc  jz      loc_180069D48
0x180069be2  test    [rcx+44h], r14b
0x180069be6  jz      loc_180069D48
0x180069bec  lea     edx, [r14+0Dh]
0x180069bf0  mov     rcx, [rcx+38h]
0x180069bf4  mov     r9d, eax
0x180069bf7  mov     r8, r13
0x180069bfa  call    WPP_SF_d
0x180069bff  jmp     loc_180069D41
0x180069c04  mov     ecx, [rdi+9C0h]; unsigned int
0x180069c0a  lea     rdx, aRefing; ">>> Refing >>>"
0x180069c11  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180069c16  mov     r8d, 5Dh ; ']'; int
0x180069c1c  lea     rdx, aPreauthmgrcrea; "PreAuthMgrCreateOneXPort"
0x180069c23  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180069c26  call    ?SecMgrRefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrRefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180069c2b  mov     r8, [rdi+0B58h]
0x180069c32  test    r8, r8
0x180069c35  jz      short loc_180069C3D
0x180069c37  mov     r8, [r8+8]
0x180069c3b  jmp     short loc_180069C40
0x180069c3d  mov     r8, r15
0x180069c40  mov     rdx, [rsp+11B0h+var_1158]
0x180069c45  xor     r9d, r9d
0x180069c48  mov     ecx, r14d
0x180069c4b  call    cs:__imp_OneXSetRuntimeState
0x180069c52  nop     dword ptr [rax+rax+00h]
0x180069c57  mov     ebx, eax
0x180069c59  test    eax, eax
0x180069c5b  jz      short loc_180069C7E
0x180069c5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180069c64  cmp     rcx, r12
0x180069c67  jz      loc_180069D02
0x180069c6d  test    [rcx+44h], r14b
0x180069c71  jz      loc_180069D02
0x180069c77  mov     edx, 0Fh
0x180069c7c  jmp     short loc_180069CF3
0x180069c7e  lea     rcx, [rdi+0BB8h]; struct MSMSEC_PMKCACHE_CONTEXT *
0x180069c85  lea     r8, [rsp+11B0h+var_1148]; void **
0x180069c8a  lea     rdx, [rsp+11B0h+var_1160]; unsigned int *
0x180069c8f  call    ?PmkCacheGetAuthParams@@YAKPEAUMSMSEC_PMKCACHE_CONTEXT@@PEAKPEAPEAX@Z; PmkCacheGetAuthParams(MSMSEC_PMKCACHE_CONTEXT *,ulong *,void * *)
0x180069c94  mov     ebx, eax
0x180069c96  test    eax, eax
0x180069c98  jz      short loc_180069CB3
0x180069c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180069ca1  cmp     rcx, r12
0x180069ca4  jz      short loc_180069D02
0x180069ca6  test    [rcx+44h], r14b
0x180069caa  jz      short loc_180069D02
0x180069cac  mov     edx, 10h
0x180069cb1  jmp     short loc_180069CF3
0x180069cb3  mov     r9, [rsp+11B0h+var_1148]
0x180069cb8  mov     ecx, r14d
0x180069cbb  mov     r8d, [rsp+11B0h+var_1160]
0x180069cc0  mov     rdx, [rsp+11B0h+var_1158]
0x180069cc5  mov     [rsp+11B0h+var_1190], r15
0x180069cca  call    cs:__imp_OneXSetAuthParams
0x180069cd1  nop     dword ptr [rax+rax+00h]
0x180069cd6  mov     ebx, eax
0x180069cd8  test    eax, eax
0x180069cda  jz      short loc_180069D39
0x180069cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180069ce3  cmp     rcx, r12
0x180069ce6  jz      short loc_180069D02
0x180069ce8  test    [rcx+44h], r14b
0x180069cec  jz      short loc_180069D02
0x180069cee  mov     edx, 11h
0x180069cf3  mov     rcx, [rcx+38h]
0x180069cf7  mov     r9d, eax
0x180069cfa  mov     r8, r13
0x180069cfd  call    WPP_SF_d
0x180069d02  mov     rdx, [rsp+11B0h+var_1158]
0x180069d07  xor     r8d, r8d
0x180069d0a  mov     ecx, r14d
0x180069d0d  call    cs:__imp_OneXDestroySupplicantPort
0x180069d14  nop     dword ptr [rax+rax+00h]
0x180069d19  test    eax, eax
0x180069d1b  jz      short loc_180069D41
0x180069d1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180069d24  cmp     rcx, r12
0x180069d27  jz      short loc_180069D48
0x180069d29  test    [rcx+44h], r14b
0x180069d2d  jz      short loc_180069D48
0x180069d2f  mov     edx, 12h
0x180069d34  jmp     loc_180069BF0
0x180069d39  mov     rax, [rsp+11B0h+var_1158]
0x180069d3e  mov     [rsi], rax
0x180069d41  mov     rcx, cs:WPP_GLOBAL_Control
0x180069d48  cmp     [rsp+11B0h+StringUuid], r15
0x180069d4d  jz      short loc_180069D67
0x180069d4f  lea     rcx, [rsp+11B0h+StringUuid]; String
0x180069d54  call    cs:__imp_RpcStringFreeW
0x180069d5b  nop     dword ptr [rax+rax+00h]
0x180069d60  mov     rcx, cs:WPP_GLOBAL_Control
0x180069d67  cmp     rcx, r12
0x180069d6a  jz      short loc_180069D89
0x180069d6c  test    dword ptr [rcx+44h], 100h
0x180069d73  jz      short loc_180069D89
0x180069d75  mov     rcx, [rcx+38h]
0x180069d79  mov     edx, 13h
0x180069d7e  mov     r9d, ebx
0x180069d81  mov     r8, r13
0x180069d84  call    WPP_SF_d
0x180069d89  mov     eax, ebx
0x180069d8b  mov     rcx, [rbp+10B0h+var_40]
0x180069d92  xor     rcx, rsp; StackCookie
0x180069d95  call    __security_check_cookie
0x180069d9a  mov     rbx, [rsp+11B0h+arg_18]
0x180069da2  add     rsp, 1180h
0x180069da9  pop     r15
0x180069dab  pop     r14
0x180069dad  pop     r13
0x180069daf  pop     r12
0x180069db1  pop     rdi
0x180069db2  pop     rsi
0x180069db3  pop     rbp
0x180069db4  retn
```
