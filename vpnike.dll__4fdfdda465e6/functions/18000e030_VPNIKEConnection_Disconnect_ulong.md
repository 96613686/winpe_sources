# VPNIKEConnection::Disconnect(ulong)

- ea: `0x18000e030`
- end: `0x18000e3b0`
- name: `?Disconnect@VPNIKEConnection@@UEAAXK@Z`
- size: `896`
- prototype: `void __fastcall(VPNIKEConnection *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800177a0`
- `0x1800227f0`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18000e030`
- `0x180014d38`
- `0x18004a4b0`
- `0x18004f40c`
- `0x18005dce0`
- `0x18005de2c`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000e234`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000e234`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e350`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e350`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e334`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e334`

## pseudocode

```c
void __fastcall VPNIKEConnection::Disconnect(VPNIKEConnection *this, unsigned int a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rdx
  __int128 *v9; // r9
  unsigned int RemoteUserName; // eax
  unsigned int v11; // r8d
  unsigned int PortName; // eax
  PVOID *v13; // rcx
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v15; // [rsp+38h] [rbp-C8h]
  __int128 v16; // [rsp+48h] [rbp-B8h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+60h] [rbp-A0h]
  int v19; // [rsp+64h] [rbp-9Ch]
  __int128 v20; // [rsp+68h] [rbp-98h] BYREF
  int v21; // [rsp+78h] [rbp-88h] BYREF
  __int128 v22; // [rsp+7Ch] [rbp-84h]
  __int128 v23; // [rsp+8Ch] [rbp-74h]
  int v24; // [rsp+9Ch] [rbp-64h]
  unsigned __int16 v25[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v26; // [rsp+B0h] [rbp-50h]
  __int16 v27; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v28[280]; // [rsp+D0h] [rbp-30h] BYREF
  int v29; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v30[2044]; // [rsp+304h] [rbp+204h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, a2);
  }
  v29 = 0;
  memset_0(v30, 0, sizeof(v30));
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v20 = 0;
  v15 = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  v4 = -1;
  v18 = -1;
  v19 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v14,
      L"VPNIKEConnection::Disconnect",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      *((void **)this + 14));
  memset_0(v28, 0, 0x222u);
  *(_OWORD *)v25 = 0;
  v26 = 0;
  v27 = 0;
  *((_DWORD *)this + 39) = a2;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v29) = 0;
    LOWORD(v21) = 0;
    v7 = *((_QWORD *)this + 14);
    if ( v7 && *(_QWORD *)(v7 + 16) )
      v4 = *(_DWORD *)(v7 + 16);
    ConvertPortNoToString(&v21, v4);
    FormatRRASErrorString(&v29, L"DisconnectReason: %u", *((unsigned int *)this + 39));
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v8 = *((_QWORD *)this + 14);
      LODWORD(v9) = v8 + 2120;
      if ( !v8 )
        v9 = &v20;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceInfo,
        (unsigned int)&v29,
        (_DWORD)v9,
        (v8 + 2686) & -(__int64)(v8 != 0),
        (__int64)&v21);
    }
  }
  if ( *((_BYTE *)this + 264) && *((_BYTE *)this + 265) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, *((_QWORD *)this + 1));
    }
    SubmitThreadpoolWork(*((PTP_WORK *)this + 44));
  }
  RemoteUserName = BaseConnection::GetRemoteUserName(this, v28, v6);
  if ( RemoteUserName
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, RemoteUserName);
  }
  PortName = BaseConnection::GetPortName(this, v25, v11);
  if ( !PortName )
    goto LABEL_32;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids, PortName);
LABEL_32:
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 4) )
  {
    IPv4Helper::Cleanup(*((IPv4Helper **)this + 4), v28, v25);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 5) )
  {
    IPv6Helper::Cleanup(*((IPv6Helper **)this + 5), v28, v25);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 != 2 && (*((_DWORD *)this + 38) & 0xC00) == 0 )
  {
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 5u )
      WPP_SF_(v13[2], 40, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 4);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 24LL))(*((_QWORD *)this + 26));
    EnterCriticalSection((LPCRITICAL_SECTION)this + 4);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 6u )
    WPP_SF_(v13[2], 41, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v14);
}

```

## disassembly

```asm
0x18000e030  mov     [rsp-8+arg_10], rbx
0x18000e035  push    rbp
0x18000e036  push    rsi
0x18000e037  push    rdi
0x18000e038  push    r12
0x18000e03a  push    r13
0x18000e03c  lea     rbp, [rsp-0A10h]
0x18000e044  sub     rsp, 0B10h
0x18000e04b  mov     rax, cs:__security_cookie
0x18000e052  xor     rax, rsp
0x18000e055  mov     [rbp+0A30h+var_30], rax
0x18000e05c  mov     esi, edx
0x18000e05e  mov     rdi, rcx
0x18000e061  lea     r12, WPP_GLOBAL_Control
0x18000e068  lea     r13, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18000e06f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e076  cmp     rcx, r12
0x18000e079  jz      short loc_18000E09B
0x18000e07b  test    byte ptr [rcx+1Ch], 1
0x18000e07f  jz      short loc_18000E09B
0x18000e081  cmp     byte ptr [rcx+19h], 6
0x18000e085  jb      short loc_18000E09B
0x18000e087  mov     edx, 24h ; '$'
0x18000e08c  mov     r9d, esi
0x18000e08f  mov     r8, r13
0x18000e092  mov     rcx, [rcx+10h]
0x18000e096  call    WPP_SF_d
0x18000e09b  xor     eax, eax
0x18000e09d  mov     [rbp+0A30h+var_830], eax
0x18000e0a3  xor     edx, edx; Val
0x18000e0a5  mov     r8d, 7FCh; Size
0x18000e0ab  lea     rcx, [rbp+0A30h+var_82C]; void *
0x18000e0b2  call    memset_0
0x18000e0b7  xor     eax, eax
0x18000e0b9  mov     [rsp+0B30h+var_AB8], eax
0x18000e0bd  xorps   xmm0, xmm0
0x18000e0c0  movups  [rsp+0B30h+var_AB4], xmm0
0x18000e0c5  movups  [rbp+0A30h+var_AA4], xmm0
0x18000e0c9  mov     [rbp+0A30h+var_A94], eax
0x18000e0cc  movups  [rsp+0B30h+var_AC8], xmm0
0x18000e0d1  xorps   xmm1, xmm1
0x18000e0d4  movdqu  [rsp+0B30h+var_AF8], xmm1
0x18000e0da  mov     [rsp+0B30h+var_B00], rax
0x18000e0df  movdqu  [rsp+0B30h+var_AE8], xmm0
0x18000e0e5  mov     [rsp+0B30h+var_AD8], rax
0x18000e0ea  or      ebx, 0FFFFFFFFh
0x18000e0ed  mov     [rsp+0B30h+var_AD0], ebx
0x18000e0f1  mov     [rsp+0B30h+var_ACC], eax
0x18000e0f5  test    cs:byte_1800AA941, 8
0x18000e0fc  jz      short loc_18000E122
0x18000e0fe  mov     rax, [rdi+70h]
0x18000e102  mov     [rsp+0B30h+var_B10], rax; void *
0x18000e107  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18000e10e  xor     r8d, r8d; unsigned int *
0x18000e111  lea     rdx, aVpnikeconnecti; "VPNIKEConnection::Disconnect"
0x18000e118  lea     rcx, [rsp+0B30h+var_B00]; this
0x18000e11d  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18000e122  xor     edx, edx; Val
0x18000e124  mov     r8d, 222h; Size
0x18000e12a  lea     rcx, [rbp+0A30h+var_A60]; void *
0x18000e12e  call    memset_0
0x18000e133  xorps   xmm0, xmm0
0x18000e136  xor     eax, eax
0x18000e138  movups  xmmword ptr [rbp+0A30h+var_A90], xmm0
0x18000e13c  movups  [rbp+0A30h+var_A80], xmm0
0x18000e140  mov     [rbp+0A30h+var_A70], ax
0x18000e144  mov     [rdi+9Ch], esi
0x18000e14a  test    cs:byte_1800AA941, 8
0x18000e151  jz      loc_18000E1F6
0x18000e157  mov     word ptr [rbp+0A30h+var_830], ax
0x18000e15e  mov     word ptr [rsp+0B30h+var_AB8], ax
0x18000e163  mov     rax, [rdi+70h]
0x18000e167  test    rax, rax
0x18000e16a  jz      short loc_18000E176
0x18000e16c  cmp     qword ptr [rax+10h], 0
0x18000e171  jz      short loc_18000E176
0x18000e173  mov     ebx, [rax+10h]
0x18000e176  mov     edx, ebx
0x18000e178  lea     rcx, [rsp+0B30h+var_AB8]
0x18000e17d  call    ConvertPortNoToString
0x18000e182  mov     r8d, [rdi+9Ch]
0x18000e189  lea     rdx, aDisconnectreas; "DisconnectReason: %u"
0x18000e190  lea     rcx, [rbp+0A30h+var_830]
0x18000e197  call    FormatRRASErrorString
0x18000e19c  test    cs:byte_1800AA941, 8
0x18000e1a3  jz      short loc_18000E1F6
0x18000e1a5  mov     rdx, [rdi+70h]
0x18000e1a9  mov     rax, rdx
0x18000e1ac  lea     rcx, [rdx+0A7Eh]
0x18000e1b3  neg     rax
0x18000e1b6  sbb     r8, r8
0x18000e1b9  and     r8, rcx
0x18000e1bc  test    rdx, rdx
0x18000e1bf  lea     r9, [rdx+848h]
0x18000e1c6  jnz     short loc_18000E1CD
0x18000e1c8  lea     r9, [rsp+0B30h+var_AC8]
0x18000e1cd  lea     rax, [rsp+0B30h+var_AB8]
0x18000e1d2  mov     [rsp+0B30h+var_B08], rax
0x18000e1d7  mov     [rsp+0B30h+var_B10], r8
0x18000e1dc  lea     r8, [rbp+0A30h+var_830]
0x18000e1e3  lea     rdx, RasVpnIkeParamTraceInfo
0x18000e1ea  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e1f1  call    McTemplateU0zjzz_EventWriteTransfer
0x18000e1f6  cmp     byte ptr [rdi+108h], 0
0x18000e1fd  jz      short loc_18000E23A
0x18000e1ff  cmp     byte ptr [rdi+109h], 0
0x18000e206  jz      short loc_18000E23A
0x18000e208  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e20f  cmp     rcx, r12
0x18000e212  jz      short loc_18000E22D
0x18000e214  test    byte ptr [rcx+1Ch], 1
0x18000e218  jz      short loc_18000E22D
0x18000e21a  cmp     byte ptr [rcx+19h], 5
0x18000e21e  jb      short loc_18000E22D
0x18000e220  mov     r9, [rdi+8]
0x18000e224  mov     rcx, [rcx+10h]
0x18000e228  call    WPP_SF_i
0x18000e22d  mov     rcx, [rdi+160h]; pwk
0x18000e234  call    cs:__imp_SubmitThreadpoolWork
0x18000e23a  lea     rdx, [rbp+0A30h+var_A60]; unsigned __int16 *
0x18000e23e  mov     rcx, rdi; this
0x18000e241  call    ?GetRemoteUserName@BaseConnection@@QEAAKPEAGK@Z; BaseConnection::GetRemoteUserName(ushort *,ulong)
0x18000e246  test    eax, eax
0x18000e248  jz      short loc_18000E276
0x18000e24a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e251  cmp     rcx, r12
0x18000e254  jz      short loc_18000E276
0x18000e256  test    byte ptr [rcx+1Ch], 1
0x18000e25a  jz      short loc_18000E276
0x18000e25c  cmp     byte ptr [rcx+19h], 3
0x18000e260  jb      short loc_18000E276
0x18000e262  mov     edx, 26h ; '&'
0x18000e267  mov     r9d, eax
0x18000e26a  mov     r8, r13
0x18000e26d  mov     rcx, [rcx+10h]
0x18000e271  call    WPP_SF_d
0x18000e276  lea     rdx, [rbp+0A30h+var_A90]; unsigned __int16 *
0x18000e27a  mov     rcx, rdi; this
0x18000e27d  call    ?GetPortName@BaseConnection@@QEAAKPEAGK@Z; BaseConnection::GetPortName(ushort *,ulong)
0x18000e282  test    eax, eax
0x18000e284  jz      short loc_18000E2B2
0x18000e286  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e28d  cmp     rcx, r12
0x18000e290  jz      short loc_18000E2B9
0x18000e292  test    byte ptr [rcx+1Ch], 1
0x18000e296  jz      short loc_18000E2B9
0x18000e298  cmp     byte ptr [rcx+19h], 3
0x18000e29c  jb      short loc_18000E2B9
0x18000e29e  mov     edx, 27h ; '''
0x18000e2a3  mov     r9d, eax
0x18000e2a6  mov     r8, r13
0x18000e2a9  mov     rcx, [rcx+10h]
0x18000e2ad  call    WPP_SF_d
0x18000e2b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2b9  cmp     qword ptr [rdi+20h], 0
0x18000e2be  jz      short loc_18000E2D8
0x18000e2c0  lea     r8, [rbp+0A30h+var_A90]; unsigned __int16 *
0x18000e2c4  lea     rdx, [rbp+0A30h+var_A60]; unsigned __int16 *
0x18000e2c8  mov     rcx, [rdi+20h]; this
0x18000e2cc  call    ?Cleanup@IPv4Helper@@QEAAKPEAG0@Z; IPv4Helper::Cleanup(ushort *,ushort *)
0x18000e2d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2d8  cmp     qword ptr [rdi+28h], 0
0x18000e2dd  jz      short loc_18000E2F7
0x18000e2df  lea     r8, [rbp+0A30h+var_A90]; unsigned __int16 *
0x18000e2e3  lea     rdx, [rbp+0A30h+var_A60]; unsigned __int16 *
0x18000e2e7  mov     rcx, [rdi+28h]; this
0x18000e2eb  call    ?Cleanup@IPv6Helper@@QEAAKPEAG0@Z; IPv6Helper::Cleanup(ushort *,ushort *)
0x18000e2f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2f7  cmp     esi, 2
0x18000e2fa  jz      short loc_18000E35D
0x18000e2fc  test    dword ptr [rdi+98h], 0C00h
0x18000e306  jnz     short loc_18000E35D
0x18000e308  cmp     rcx, r12
0x18000e30b  jz      short loc_18000E32A
0x18000e30d  test    byte ptr [rcx+1Ch], 1
0x18000e311  jz      short loc_18000E32A
0x18000e313  cmp     byte ptr [rcx+19h], 5
0x18000e317  jb      short loc_18000E32A
0x18000e319  mov     edx, 28h ; '('
0x18000e31e  mov     r8, r13
0x18000e321  mov     rcx, [rcx+10h]
0x18000e325  call    WPP_SF_
0x18000e32a  lea     rbx, [rdi+0A0h]
0x18000e331  mov     rcx, rbx; lpCriticalSection
0x18000e334  call    cs:__imp_LeaveCriticalSection
0x18000e33a  mov     rcx, [rdi+0D0h]
0x18000e341  mov     rax, [rcx]
0x18000e344  mov     rax, [rax+18h]
0x18000e348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e34d  mov     rcx, rbx; lpCriticalSection
0x18000e350  call    cs:__imp_EnterCriticalSection
0x18000e356  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e35d  cmp     rcx, r12
0x18000e360  jz      short loc_18000E380
0x18000e362  test    byte ptr [rcx+1Ch], 1
0x18000e366  jz      short loc_18000E380
0x18000e368  cmp     byte ptr [rcx+19h], 6
0x18000e36c  jb      short loc_18000E380
0x18000e36e  mov     edx, 29h ; ')'
0x18000e373  mov     r8, r13
0x18000e376  mov     rcx, [rcx+10h]
0x18000e37a  call    WPP_SF_
0x18000e37f  nop
0x18000e380  lea     rcx, [rsp+0B30h+var_B00]; this
0x18000e385  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18000e38a  mov     rcx, [rbp+0A30h+var_30]
0x18000e391  xor     rcx, rsp; StackCookie
0x18000e394  call    __security_check_cookie
0x18000e399  mov     rbx, [rsp+0B30h+arg_10]
0x18000e3a1  add     rsp, 0B10h
0x18000e3a8  pop     r13
0x18000e3aa  pop     r12
0x18000e3ac  pop     rdi
0x18000e3ad  pop     rsi
0x18000e3ae  pop     rbp
0x18000e3af  retn
```
