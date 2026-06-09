# BFEHandler::GetBfeHandle(void * *)

- ea: `0x18002e6f4`
- end: `0x18002e92b`
- name: `?GetBfeHandle@BFEHandler@@SAKPEAPEAX@Z`
- size: `567`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `14`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001287c`
- `0x180016ae0`
- `0x180021e70`
- `0x18002c2a0`
- `0x18002d860`
- `0x180031220`
- `0x180031788`
- `0x180032690`
- `0x1800389e4`
- `0x180039278`
- `0x18003b62c`
- `0x18003d434`
- `0x18003fd14`
- `0x1800400a8`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x18002e6f4`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `fwpuclnt!FwpmEngineOpen0` at `0x18002e80f`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002e80f`

## string_xrefs

- `0x18002e840`: `FwpmEngineOpen failed: %d`

## pseudocode

```c
__int64 __fastcall BFEHandler::GetBfeHandle(void **a1)
{
  PVOID *v2; // rbx
  unsigned int v3; // edi
  HANDLE v4; // rax
  unsigned int v6; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v7; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v8; // [rsp+40h] [rbp-C0h]
  __int128 v9; // [rsp+50h] [rbp-B0h]
  __int64 v10; // [rsp+60h] [rbp-A0h]
  int v11; // [rsp+68h] [rbp-98h]
  int v12; // [rsp+6Ch] [rbp-94h]
  FWPM_SESSION0 session; // [rsp+70h] [rbp-90h] BYREF
  int v14; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v15[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = 0;
  v6 = 0;
  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  v8 = 0;
  v7 = 0;
  v9 = 0;
  v10 = 0;
  v11 = -1;
  v12 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v7,
      L"BFEHandler::GetBfeHandle",
      &v6,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v3 = v6;
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v4 = BFEHandler::hFwpEngine;
  if ( !BFEHandler::hFwpEngine )
  {
    memset_0(&session, 0, sizeof(session));
    v3 = FwpmEngineOpen0(0, 0xAu, 0, &session, &BFEHandler::hFwpEngine);
    v6 = v3;
    if ( v3 )
    {
      BFEHandler::hFwpEngine = 0;
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v14) = 0;
        FormatRRASErrorString(&v14, L"FwpmEngineOpen failed: %d", v3);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v14);
        v3 = v6;
      }
      if ( !v3 )
        goto LABEL_21;
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_26;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v3);
        v3 = v6;
LABEL_21:
        v2 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_22;
      }
      goto LABEL_22;
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
    v4 = BFEHandler::hFwpEngine;
  }
  if ( a1 )
  {
    *a1 = v4;
    goto LABEL_21;
  }
LABEL_22:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
  {
    WPP_SF_d(v2[2], 106, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v3);
    v3 = v6;
  }
LABEL_26:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v7);
  return v3;
}

```

## disassembly

```asm
0x18002e6f4  mov     [rsp-8+arg_8], rbx
0x18002e6f9  mov     [rsp-8+arg_10], rsi
0x18002e6fe  push    rbp
0x18002e6ff  push    rdi
0x18002e700  push    r12
0x18002e702  lea     rbp, [rsp-7D0h]
0x18002e70a  sub     rsp, 8D0h
0x18002e711  mov     rax, cs:__security_cookie
0x18002e718  xor     rax, rsp
0x18002e71b  mov     [rbp+7E0h+var_20], rax
0x18002e722  mov     rsi, rcx
0x18002e725  lea     r12, WPP_GLOBAL_Control
0x18002e72c  mov     rbx, cs:WPP_GLOBAL_Control
0x18002e733  cmp     rbx, r12
0x18002e736  jz      short loc_18002E760
0x18002e738  test    byte ptr [rbx+1Ch], 1
0x18002e73c  jz      short loc_18002E760
0x18002e73e  cmp     byte ptr [rbx+19h], 6
0x18002e742  jb      short loc_18002E760
0x18002e744  mov     edx, 68h ; 'h'
0x18002e749  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002e750  mov     rcx, [rbx+10h]
0x18002e754  call    WPP_SF_
0x18002e759  mov     rbx, cs:WPP_GLOBAL_Control
0x18002e760  xor     edi, edi
0x18002e762  mov     [rsp+8E0h+var_8B0], edi
0x18002e766  xor     eax, eax
0x18002e768  mov     [rbp+7E0h+var_820], eax
0x18002e76b  xor     edx, edx; Val
0x18002e76d  mov     r8d, 7FCh; Size
0x18002e773  lea     rcx, [rbp+7E0h+var_81C]; void *
0x18002e777  call    memset_0
0x18002e77c  xorps   xmm0, xmm0
0x18002e77f  movdqu  [rsp+8E0h+var_8A0], xmm0
0x18002e785  mov     [rsp+8E0h+var_8A8], rdi
0x18002e78a  xorps   xmm1, xmm1
0x18002e78d  movdqu  [rsp+8E0h+var_890], xmm1
0x18002e793  mov     [rsp+8E0h+var_880], rdi
0x18002e798  mov     [rsp+8E0h+var_878], 0FFFFFFFFh
0x18002e7a0  mov     [rsp+8E0h+var_874], edi
0x18002e7a4  test    cs:byte_1800AA941, 8
0x18002e7ab  jz      short loc_18002E7D5
0x18002e7ad  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18002e7b4  lea     r8, [rsp+8E0h+var_8B0]; unsigned int *
0x18002e7b9  lea     rdx, aBfehandlerGetb; "BFEHandler::GetBfeHandle"
0x18002e7c0  lea     rcx, [rsp+8E0h+var_8A8]; this
0x18002e7c5  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18002e7ca  mov     edi, [rsp+8E0h+var_8B0]
0x18002e7ce  mov     rbx, cs:WPP_GLOBAL_Control
0x18002e7d5  mov     rax, cs:?hFwpEngine@BFEHandler@@0PEAXEA; void * BFEHandler::hFwpEngine
0x18002e7dc  test    rax, rax
0x18002e7df  jnz     loc_18002E8BC
0x18002e7e5  xor     edx, edx; Val
0x18002e7e7  lea     r8d, [rax+48h]; Size
0x18002e7eb  lea     rcx, [rsp+8E0h+session]; void *
0x18002e7f0  call    memset_0
0x18002e7f5  lea     rax, ?hFwpEngine@BFEHandler@@0PEAXEA; void * BFEHandler::hFwpEngine
0x18002e7fc  mov     [rsp+8E0h+engineHandle], rax; engineHandle
0x18002e801  lea     r9, [rsp+8E0h+session]; session
0x18002e806  xor     r8d, r8d; authIdentity
0x18002e809  lea     edx, [r8+0Ah]; authnService
0x18002e80d  xor     ecx, ecx; serverName
0x18002e80f  call    cs:__imp_FwpmEngineOpen0
0x18002e815  mov     edi, eax
0x18002e817  mov     [rsp+8E0h+var_8B0], eax
0x18002e81b  test    eax, eax
0x18002e81d  jz      loc_18002E8AE
0x18002e823  mov     cs:?hFwpEngine@BFEHandler@@0PEAXEA, 0; void * BFEHandler::hFwpEngine
0x18002e82e  test    cs:byte_1800AA941, 4
0x18002e835  jz      short loc_18002E874
0x18002e837  xor     eax, eax
0x18002e839  mov     word ptr [rbp+7E0h+var_820], ax
0x18002e83d  mov     r8d, edi
0x18002e840  lea     rdx, aFwpmengineopen; "FwpmEngineOpen failed: %d"
0x18002e847  lea     rcx, [rbp+7E0h+var_820]
0x18002e84b  call    FormatRRASErrorString
0x18002e850  test    cs:byte_1800AA941, 4
0x18002e857  jz      short loc_18002E870
0x18002e859  lea     r8, [rbp+7E0h+var_820]
0x18002e85d  lea     rdx, RasVpnIkeTraceError
0x18002e864  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002e86b  call    McTemplateU0z_EventWriteTransfer
0x18002e870  mov     edi, [rsp+8E0h+var_8B0]
0x18002e874  test    edi, edi
0x18002e876  jz      short loc_18002E8C4
0x18002e878  mov     rbx, cs:WPP_GLOBAL_Control
0x18002e87f  cmp     rbx, r12
0x18002e882  jz      short loc_18002E8F8
0x18002e884  test    byte ptr [rbx+1Ch], 1
0x18002e888  jz      short loc_18002E8CB
0x18002e88a  cmp     byte ptr [rbx+19h], 2
0x18002e88e  jb      short loc_18002E8CB
0x18002e890  mov     edx, 69h ; 'i'
0x18002e895  mov     r9d, edi
0x18002e898  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002e89f  mov     rcx, [rbx+10h]
0x18002e8a3  call    WPP_SF_d
0x18002e8a8  mov     edi, [rsp+8E0h+var_8B0]
0x18002e8ac  jmp     short loc_18002E8C4
0x18002e8ae  mov     rbx, cs:WPP_GLOBAL_Control
0x18002e8b5  mov     rax, cs:?hFwpEngine@BFEHandler@@0PEAXEA; void * BFEHandler::hFwpEngine
0x18002e8bc  test    rsi, rsi
0x18002e8bf  jz      short loc_18002E8CB
0x18002e8c1  mov     [rsi], rax
0x18002e8c4  mov     rbx, cs:WPP_GLOBAL_Control
0x18002e8cb  cmp     rbx, r12
0x18002e8ce  jz      short loc_18002E8F8
0x18002e8d0  test    byte ptr [rbx+1Ch], 1
0x18002e8d4  jz      short loc_18002E8F8
0x18002e8d6  cmp     byte ptr [rbx+19h], 6
0x18002e8da  jb      short loc_18002E8F8
0x18002e8dc  mov     edx, 6Ah ; 'j'
0x18002e8e1  mov     r9d, edi
0x18002e8e4  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002e8eb  mov     rcx, [rbx+10h]
0x18002e8ef  call    WPP_SF_d
0x18002e8f4  mov     edi, [rsp+8E0h+var_8B0]
0x18002e8f8  lea     rcx, [rsp+8E0h+var_8A8]; this
0x18002e8fd  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18002e902  mov     eax, edi
0x18002e904  mov     rcx, [rbp+7E0h+var_20]
0x18002e90b  xor     rcx, rsp; StackCookie
0x18002e90e  call    __security_check_cookie
0x18002e913  lea     r11, [rsp+8E0h+var_10]
0x18002e91b  mov     rbx, [r11+28h]
0x18002e91f  mov     rsi, [r11+30h]
0x18002e923  mov     rsp, r11
0x18002e926  pop     r12
0x18002e928  pop     rdi
0x18002e929  pop     rbp
0x18002e92a  retn
```
