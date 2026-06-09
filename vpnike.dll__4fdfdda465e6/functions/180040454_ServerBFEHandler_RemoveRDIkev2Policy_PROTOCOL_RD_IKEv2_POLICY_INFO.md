# ServerBFEHandler::RemoveRDIkev2Policy(_PROTOCOL_RD_IKEv2_POLICY_INFO *)

- ea: `0x180040454`
- end: `0x180040662`
- name: `?RemoveRDIkev2Policy@ServerBFEHandler@@SAKPEAU_PROTOCOL_RD_IKEv2_POLICY_INFO@@@Z`
- size: `526`
- prototype: `__int64 __fastcall(struct _PROTOCOL_RD_IKEv2_POLICY_INFO *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800052bc`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x18003fed8`
- `0x180040454`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## string_xrefs

- `0x18004051c`: `ServerBFEHandler::RemoveRDIkev2Policy`
- `0x1800405d8`: `RemoveRDIkev2Policy: Invalid input parameters`
- `0x18004058f`: `RemoveRDIkev2Policy: RemovePolicyForInterface failed: %d`

## pseudocode

```c
__int64 __fastcall ServerBFEHandler::RemoveRDIkev2Policy(struct _PROTOCOL_RD_IKEv2_POLICY_INFO *a1)
{
  PVOID *v2; // rbx
  unsigned int v3; // edi
  char v4; // al
  unsigned int i; // ebx
  unsigned int v7; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v8; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v9; // [rsp+30h] [rbp-D0h]
  __int128 v10; // [rsp+40h] [rbp-C0h]
  __int64 v11; // [rsp+50h] [rbp-B0h]
  int v12; // [rsp+58h] [rbp-A8h]
  int v13; // [rsp+5Ch] [rbp-A4h]
  int v14; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v15[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = 0;
  v7 = 0;
  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  v9 = 0;
  v8 = 0;
  v10 = 0;
  v11 = 0;
  v12 = -1;
  v13 = 0;
  v4 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v8,
      L"ServerBFEHandler::RemoveRDIkev2Policy",
      &v7,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v3 = v7;
    v2 = (PVOID *)WPP_GLOBAL_Control;
    v4 = byte_1800AA941;
  }
  if ( a1 && *((_DWORD *)a1 + 4) && *((_QWORD *)a1 + 3) )
  {
    for ( i = 0; i < *((_DWORD *)a1 + 4); ++i )
    {
      v3 = ServerBFEHandler::RemovePolicyForInterface(*(void **)(32LL * i + *((_QWORD *)a1 + 3)));
      v7 = v3;
      if ( v3 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v14) = 0;
          FormatRRASErrorString(&v14, L"RemoveRDIkev2Policy: RemovePolicyForInterface failed: %d", v3);
          if ( (byte_1800AA941 & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v14);
        }
        v3 = 0;
        v7 = 0;
      }
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    if ( (v4 & 4) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasVpnIkeTraceError,
        L"RemoveRDIkev2Policy: Invalid input parameters");
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    v3 = 87;
    v7 = 87;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
  {
    WPP_SF_d(v2[2], 58, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids, v3);
    v3 = v7;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v8);
  return v3;
}

```

## disassembly

```asm
0x180040454  mov     [rsp-8+arg_8], rbx
0x180040459  mov     [rsp-8+arg_10], rsi
0x18004045e  push    rbp
0x18004045f  push    rdi
0x180040460  push    r15
0x180040462  lea     rbp, [rsp-770h]
0x18004046a  sub     rsp, 870h
0x180040471  mov     rax, cs:__security_cookie
0x180040478  xor     rax, rsp
0x18004047b  mov     [rbp+780h+var_20], rax
0x180040482  mov     rsi, rcx
0x180040485  lea     r15, WPP_GLOBAL_Control
0x18004048c  mov     rbx, cs:WPP_GLOBAL_Control
0x180040493  cmp     rbx, r15
0x180040496  jz      short loc_1800404C0
0x180040498  test    byte ptr [rbx+1Ch], 1
0x18004049c  jz      short loc_1800404C0
0x18004049e  cmp     byte ptr [rbx+19h], 6
0x1800404a2  jb      short loc_1800404C0
0x1800404a4  mov     edx, 39h ; '9'
0x1800404a9  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x1800404b0  mov     rcx, [rbx+10h]
0x1800404b4  call    WPP_SF_
0x1800404b9  mov     rbx, cs:WPP_GLOBAL_Control
0x1800404c0  xor     edi, edi
0x1800404c2  mov     [rsp+880h+var_860], edi
0x1800404c6  xor     eax, eax
0x1800404c8  mov     [rsp+880h+var_820], eax
0x1800404cc  xor     edx, edx; Val
0x1800404ce  mov     r8d, 7FCh; Size
0x1800404d4  lea     rcx, [rsp+880h+var_81C]; void *
0x1800404d9  call    memset_0
0x1800404de  xorps   xmm0, xmm0
0x1800404e1  movdqu  [rsp+880h+var_850], xmm0
0x1800404e7  mov     [rsp+880h+var_858], rdi
0x1800404ec  xorps   xmm1, xmm1
0x1800404ef  movdqu  [rsp+880h+var_840], xmm1
0x1800404f5  mov     [rsp+880h+var_830], rdi
0x1800404fa  mov     [rsp+880h+var_828], 0FFFFFFFFh
0x180040502  mov     [rsp+880h+var_824], edi
0x180040506  mov     al, cs:byte_1800AA941
0x18004050c  test    al, 8
0x18004050e  jz      short loc_18004053E
0x180040510  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180040517  lea     r8, [rsp+880h+var_860]; unsigned int *
0x18004051c  lea     rdx, aServerbfehandl_9; "ServerBFEHandler::RemoveRDIkev2Policy"
0x180040523  lea     rcx, [rsp+880h+var_858]; this
0x180040528  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18004052d  mov     edi, [rsp+880h+var_860]
0x180040531  mov     rbx, cs:WPP_GLOBAL_Control
0x180040538  mov     al, cs:byte_1800AA941
0x18004053e  test    rsi, rsi
0x180040541  jz      loc_1800405D4
0x180040547  cmp     dword ptr [rsi+10h], 0
0x18004054b  jz      loc_1800405D4
0x180040551  cmp     qword ptr [rsi+18h], 0
0x180040556  jz      short loc_1800405D4
0x180040558  xor     ebx, ebx
0x18004055a  cmp     ebx, [rsi+10h]
0x18004055d  jnb     short loc_1800405CB
0x18004055f  mov     eax, ebx
0x180040561  shl     rax, 5
0x180040565  mov     rcx, [rsi+18h]
0x180040569  mov     rcx, [rax+rcx]; void *
0x18004056d  call    ?RemovePolicyForInterface@ServerBFEHandler@@KAKPEAX@Z; ServerBFEHandler::RemovePolicyForInterface(void *)
0x180040572  mov     edi, eax
0x180040574  mov     [rsp+880h+var_860], eax
0x180040578  test    eax, eax
0x18004057a  jz      short loc_1800405C7
0x18004057c  test    cs:byte_1800AA941, 4
0x180040583  jz      short loc_1800405C1
0x180040585  xor     eax, eax
0x180040587  mov     word ptr [rsp+880h+var_820], ax
0x18004058c  mov     r8d, edi
0x18004058f  lea     rdx, aRemoverdikev2p_1; "RemoveRDIkev2Policy: RemovePolicyForInt"...
0x180040596  lea     rcx, [rsp+880h+var_820]
0x18004059b  call    FormatRRASErrorString
0x1800405a0  test    cs:byte_1800AA941, 4
0x1800405a7  jz      short loc_1800405C1
0x1800405a9  lea     r8, [rsp+880h+var_820]
0x1800405ae  lea     rdx, RasVpnIkeTraceError
0x1800405b5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800405bc  call    McTemplateU0z_EventWriteTransfer
0x1800405c1  xor     edi, edi
0x1800405c3  mov     [rsp+880h+var_860], edi
0x1800405c7  inc     ebx
0x1800405c9  jmp     short loc_18004055A
0x1800405cb  mov     rbx, cs:WPP_GLOBAL_Control
0x1800405d2  jmp     short loc_180040602
0x1800405d4  test    al, 4
0x1800405d6  jz      short loc_1800405F9
0x1800405d8  lea     r8, aRemoverdikev2p_0; "RemoveRDIkev2Policy: Invalid input para"...
0x1800405df  lea     rdx, RasVpnIkeTraceError
0x1800405e6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800405ed  call    McTemplateU0z_EventWriteTransfer
0x1800405f2  mov     rbx, cs:WPP_GLOBAL_Control
0x1800405f9  mov     edi, 57h ; 'W'
0x1800405fe  mov     [rsp+880h+var_860], edi
0x180040602  cmp     rbx, r15
0x180040605  jz      short loc_18004062F
0x180040607  test    byte ptr [rbx+1Ch], 1
0x18004060b  jz      short loc_18004062F
0x18004060d  cmp     byte ptr [rbx+19h], 6
0x180040611  jb      short loc_18004062F
0x180040613  mov     edx, 3Ah ; ':'
0x180040618  mov     r9d, edi
0x18004061b  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x180040622  mov     rcx, [rbx+10h]
0x180040626  call    WPP_SF_d
0x18004062b  mov     edi, [rsp+880h+var_860]
0x18004062f  lea     rcx, [rsp+880h+var_858]; this
0x180040634  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180040639  mov     eax, edi
0x18004063b  mov     rcx, [rbp+780h+var_20]
0x180040642  xor     rcx, rsp; StackCookie
0x180040645  call    __security_check_cookie
0x18004064a  lea     r11, [rsp+880h+var_10]
0x180040652  mov     rbx, [r11+28h]
0x180040656  mov     rsi, [r11+30h]
0x18004065a  mov     rsp, r11
0x18004065d  pop     r15
0x18004065f  pop     rdi
0x180040660  pop     rbp
0x180040661  retn
```
