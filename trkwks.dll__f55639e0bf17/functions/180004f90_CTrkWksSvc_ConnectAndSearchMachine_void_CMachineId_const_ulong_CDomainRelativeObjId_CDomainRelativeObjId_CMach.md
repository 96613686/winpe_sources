# CTrkWksSvc::ConnectAndSearchMachine(void *,CMachineId const &,ulong *,CDomainRelativeObjId *,CDomainRelativeObjId *,CMachineId *,ushort *)

- ea: `0x180004f90`
- end: `0x1800053a6`
- name: `?ConnectAndSearchMachine@CTrkWksSvc@@AEAAJPEAXAEBUCMachineId@@PEAKPEAUCDomainRelativeObjId@@3PEAU2@PEAG@Z`
- size: `1046`
- prototype: `__int64 __fastcall(CTrkWksSvc *this, void *, const struct CMachineId *, unsigned int *, struct CDomainRelativeObjId *, struct CDomainRelativeObjId *, struct CMachineId *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004ac0`

## callees

- `0x180004f60`
- `0x180004f90`
- `0x1800053b0`
- `0x18000556c`
- `0x180006700`
- `0x180007408`
- `0x18000add0`
- `0x18000aec4`
- `0x18000b4a0`
- `0x18000d038`
- `0x180010df0`
- `0x180010fca`
- `0x180011000`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180005396`
- `RPCRT4!RpcRevertToSelf` at `0x180005396`
- `RPCRT4!RpcImpersonateClient` at `0x180005199`
- `RPCRT4!RpcImpersonateClient` at `0x180005199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005222`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000539e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000539e`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180005218`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180005218`

## pseudocode

```c
__int64 __fastcall CTrkWksSvc::ConnectAndSearchMachine(
        CTrkWksSvc *this,
        void *a2,
        const struct CMachineId *a3,
        unsigned int *a4,
        struct CDomainRelativeObjId *a5,
        struct CDomainRelativeObjId *a6,
        struct CMachineId *a7,
        unsigned __int16 *a8)
{
  CMachineId *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  int v14; // ebx
  unsigned __int64 v15; // rax
  RPC_STATUS v16; // eax
  __int64 v17; // r8
  int v18; // eax
  DWORD LastError; // eax
  int v20; // eax
  int v21; // eax
  int v23; // [rsp+48h] [rbp-340h]
  _BYTE v24[40]; // [rsp+A0h] [rbp-2E8h] BYREF
  __int64 v25; // [rsp+C8h] [rbp-2C0h]
  __int128 v26; // [rsp+D0h] [rbp-2B8h] BYREF
  __int128 v27; // [rsp+E0h] [rbp-2A8h] BYREF
  __int128 v28; // [rsp+F0h] [rbp-298h]
  __int128 v29; // [rsp+100h] [rbp-288h] BYREF
  __int128 v30; // [rsp+110h] [rbp-278h]
  _BYTE v31[16]; // [rsp+120h] [rbp-268h] BYREF
  unsigned __int16 v32[264]; // [rsp+130h] [rbp-258h] BYREF

  CRpcClientBinding::CRpcClientBinding((CRpcClientBinding *)v24);
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v26 = 0;
  v23 = 0;
  memset_0(v32, 0, 0x20Cu);
  v11 = CMachineId::CMachineId((CMachineId *)v31);
  v12 = *(_QWORD *)v11 - *(_QWORD *)a3;
  if ( !v12 )
    v12 = *((_QWORD *)v11 + 1) - *((_QWORD *)a3 + 1);
  if ( v12 )
  {
    v15 = -*(_QWORD *)a3;
    if ( !*(_QWORD *)a3 )
      v15 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] - *((_QWORD *)a3 + 1);
    if ( !v15 )
    {
      v14 = -1913990908;
      goto LABEL_14;
    }
    if ( (unsigned int)CTrkRpcConfig::RpcSecurityEnabled() )
    {
      v16 = RpcImpersonateClient(a2);
      if ( v16 )
        TrkRaiseWin32Error(v16);
    }
    else if ( !ImpersonateSelf(SecurityImpersonation) )
    {
      LastError = GetLastError();
      TrkRaiseWin32Error(LastError);
    }
    v23 = 1;
    CRpcClientBinding::RcInitialize(v24, a3, v17, L"\\pipe\\trkwks");
    v20 = LnkSearchMachine(v25, *a4, (_DWORD)a5, (_DWORD)a6, (__int64)&v27, (__int64)&v29, (__int64)&v26, (__int64)v32);
    v14 = v20;
    if ( v20 >= 0 || v20 == -1913990906 )
    {
      v21 = StringCchCopyW(a8, 0x104u, v32);
      if ( v21 < 0 )
        v14 = v21;
    }
  }
  else
  {
    v13 = StubLnkSearchMachine(a2, *a4, a5, a6, &v27, &v29, &v26, v32, -2147467259);
    v14 = v13;
    if ( v13 >= 0 || v13 == -1913990906 )
    {
      v18 = StringCchCopyW(a8, 0x104u, v32);
      if ( v18 < 0 )
        v14 = v18;
    }
  }
  if ( v14 >= 0 )
  {
LABEL_7:
    *(_OWORD *)a5 = v27;
    *((_OWORD *)a5 + 1) = v28;
    *(_OWORD *)a6 = v29;
    *((_OWORD *)a6 + 1) = v30;
    *(_OWORD *)a7 = v26;
    goto LABEL_28;
  }
LABEL_14:
  if ( v14 != -1913991141 )
  {
    if ( v14 == -1913990911 || v14 == -1913990906 )
      goto LABEL_7;
    v14 = -1913990908;
  }
LABEL_28:
  if ( v23 )
  {
    if ( (unsigned int)CTrkRpcConfig::RpcSecurityEnabled() )
      RpcRevertToSelf();
    else
      RevertToSelf();
  }
  CRpcClientBinding::~CRpcClientBinding((CRpcClientBinding *)v24);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180004f90  push    rbx
0x180004f92  push    rsi
0x180004f93  push    rdi
0x180004f94  push    r12
0x180004f96  push    r13
0x180004f98  push    r14
0x180004f9a  push    r15
0x180004f9c  sub     rsp, 350h
0x180004fa3  mov     rax, cs:__security_cookie
0x180004faa  xor     rax, rsp
0x180004fad  mov     [rsp+388h+var_48], rax
0x180004fb5  mov     r15, r9
0x180004fb8  mov     rdi, r8
0x180004fbb  mov     r12, rdx
0x180004fbe  mov     r14, [rsp+388h+arg_28]
0x180004fc6  mov     [rsp+388h+var_300], r14
0x180004fce  mov     rsi, [rsp+388h+arg_20]
0x180004fd6  mov     [rsp+388h+var_308], rsi
0x180004fde  mov     [rsp+388h+var_328], r8
0x180004fe3  mov     [rsp+388h+var_320], r9
0x180004fe8  mov     [rsp+388h+var_318], rsi
0x180004fed  mov     [rsp+388h+var_310], r14
0x180004ff2  mov     rax, [rsp+388h+arg_30]
0x180004ffa  mov     [rsp+388h+var_2F8], rax
0x180005002  mov     r13, [rsp+388h+arg_38]
0x18000500a  mov     [rsp+388h+var_338], r13
0x18000500f  lea     rcx, [rsp+388h+var_2E8]; this
0x180005017  call    ??0CRpcClientBinding@@QEAA@XZ; CRpcClientBinding::CRpcClientBinding(void)
0x18000501c  mov     ebx, 80004005h
0x180005021  mov     [rsp+388h+var_348], ebx
0x180005025  xorps   xmm0, xmm0
0x180005028  movups  [rsp+388h+var_2A8], xmm0
0x180005030  xorps   xmm1, xmm1
0x180005033  movups  [rsp+388h+var_298], xmm1
0x18000503b  movups  [rsp+388h+var_288], xmm0
0x180005043  movups  [rsp+388h+var_278], xmm1
0x18000504b  movups  [rsp+388h+var_2B8], xmm0
0x180005053  mov     [rsp+388h+var_340], 0
0x18000505b  xor     edx, edx; Val
0x18000505d  mov     r8d, 20Ch; Size
0x180005063  lea     rcx, [rsp+388h+var_258]; void *
0x18000506b  call    memset_0
0x180005070  lea     rcx, [rsp+388h+var_268]
0x180005078  call    ??0CMachineId@@QEAA@W4MCID_CREATE_TYPE@@@Z; CMachineId::CMachineId(MCID_CREATE_TYPE)
0x18000507d  mov     rcx, rax
0x180005080  mov     rax, [rax]
0x180005083  sub     rax, [rdi]
0x180005086  jnz     short loc_180005090
0x180005088  mov     rax, [rcx+8]
0x18000508c  sub     rax, [rdi+8]
0x180005090  test    rax, rax
0x180005093  jnz     loc_18000516D
0x180005099  lea     rax, [rsp+388h+var_258]
0x1800050a1  mov     [rsp+388h+var_350], rax
0x1800050a6  lea     rax, [rsp+388h+var_2B8]
0x1800050ae  mov     [rsp+388h+var_358], rax
0x1800050b3  lea     rax, [rsp+388h+var_288]
0x1800050bb  mov     [rsp+388h+var_360], rax
0x1800050c0  lea     rax, [rsp+388h+var_2A8]
0x1800050c8  mov     [rsp+388h+var_368], rax
0x1800050cd  mov     r9, r14
0x1800050d0  mov     r8, rsi
0x1800050d3  mov     edx, [r15]
0x1800050d6  mov     rcx, r12
0x1800050d9  call    StubLnkSearchMachine
0x1800050de  mov     ebx, eax
0x1800050e0  mov     [rsp+388h+var_348], eax
0x1800050e4  test    eax, eax
0x1800050e6  jns     loc_1800051E0
0x1800050ec  cmp     eax, 8DEAD106h
0x1800050f1  jz      loc_1800051E0
0x1800050f7  test    ebx, ebx
0x1800050f9  js      loc_1800051AE
0x1800050ff  mov     rax, [rsp+388h+var_308]
0x180005107  movups  xmm0, [rsp+388h+var_2A8]
0x18000510f  movups  xmmword ptr [rax], xmm0
0x180005112  mov     rax, qword ptr [rsp+388h+var_298]
0x18000511a  mov     [rsi+10h], rax
0x18000511e  mov     rax, qword ptr [rsp+388h+var_298+8]
0x180005126  mov     [rsi+18h], rax
0x18000512a  mov     rax, [rsp+388h+var_300]
0x180005132  movups  xmm0, [rsp+388h+var_288]
0x18000513a  movups  xmmword ptr [rax], xmm0
0x18000513d  mov     rax, qword ptr [rsp+388h+var_278]
0x180005145  mov     [r14+10h], rax
0x180005149  mov     rax, qword ptr [rsp+388h+var_278+8]
0x180005151  mov     [r14+18h], rax
0x180005155  mov     rax, [rsp+388h+var_2F8]
0x18000515d  movups  xmm0, [rsp+388h+var_2B8]
0x180005165  movups  xmmword ptr [rax], xmm0
0x180005168  jmp     loc_180005349
0x18000516d  xorps   xmm0, xmm0
0x180005170  movq    rax, xmm0
0x180005175  sub     rax, [rdi]
0x180005178  jnz     short loc_180005188
0x18000517a  psrldq  xmm0, 8
0x18000517f  movq    rax, xmm0
0x180005184  sub     rax, [rdi+8]
0x180005188  test    rax, rax
0x18000518b  jz      short loc_180005208
0x18000518d  call    ?RpcSecurityEnabled@CTrkRpcConfig@@SAHXZ; CTrkRpcConfig::RpcSecurityEnabled(void)
0x180005192  test    eax, eax
0x180005194  jz      short loc_180005213
0x180005196  mov     rcx, r12; BindingHandle
0x180005199  call    cs:__imp_RpcImpersonateClient
0x18000519f  test    eax, eax
0x1800051a1  jz      loc_180005230
0x1800051a7  mov     ecx, eax; int
0x1800051a9  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x1800051ae  cmp     ebx, 8DEAD01Bh
0x1800051b4  jz      loc_180005349
0x1800051ba  cmp     ebx, 8DEAD101h
0x1800051c0  jz      loc_1800050FF
0x1800051c6  cmp     ebx, 8DEAD106h
0x1800051cc  jz      loc_1800050FF
0x1800051d2  mov     ebx, 8DEAD104h
0x1800051d7  mov     [rsp+388h+var_348], ebx
0x1800051db  jmp     loc_180005349
0x1800051e0  lea     r8, [rsp+388h+var_258]; unsigned __int16 *
0x1800051e8  mov     edx, 104h; unsigned __int64
0x1800051ed  mov     rcx, r13; unsigned __int16 *
0x1800051f0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800051f5  test    eax, eax
0x1800051f7  jns     loc_1800050F7
0x1800051fd  mov     ebx, eax
0x1800051ff  mov     [rsp+388h+var_348], eax
0x180005203  jmp     loc_1800050F7
0x180005208  mov     ebx, 8DEAD104h
0x18000520d  mov     [rsp+388h+var_348], ebx
0x180005211  jmp     short loc_1800051AE
0x180005213  mov     ecx, 2; ImpersonationLevel
0x180005218  call    cs:__imp_ImpersonateSelf
0x18000521e  test    eax, eax
0x180005220  jnz     short loc_180005230
0x180005222  call    cs:__imp_GetLastError
0x180005228  mov     ecx, eax; int
0x18000522a  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180005230  mov     [rsp+388h+var_340], 1
0x180005238  xor     r12d, r12d
0x18000523b  lea     rax, ?s_tszTrkWksRemoteRpcEndPointOld@@3QBGB; "\\pipe\\ntsvcs"
0x180005242  mov     [rsp+388h+var_344], r12d
0x180005247  cmp     r12d, 2
0x18000524b  jge     loc_1800050F7
0x180005251  xor     r13d, r13d
0x180005254  mov     [rsp+388h+var_33C], r13d
0x180005259  lea     r9, ?s_tszTrkWksRemoteRpcEndPoint@@3QBGB; "\\pipe\\trkwks"
0x180005260  test    r12d, r12d
0x180005263  cmovnz  r9, rax
0x180005267  mov     rdx, rdi
0x18000526a  lea     rcx, [rsp+388h+var_2E8]
0x180005272  call    ?RcInitialize@CRpcClientBinding@@QEAAXAEBUCMachineId@@PEBG1W4RC_AUTHENTICATE@@@Z; CRpcClientBinding::RcInitialize(CMachineId const &,ushort const *,ushort const *,RC_AUTHENTICATE)
0x180005277  nop
0x180005278  lea     rax, [rsp+388h+var_258]
0x180005280  mov     [rsp+388h+var_350], rax
0x180005285  lea     rax, [rsp+388h+var_2B8]
0x18000528d  mov     [rsp+388h+var_358], rax
0x180005292  lea     rax, [rsp+388h+var_288]
0x18000529a  mov     [rsp+388h+var_360], rax
0x18000529f  lea     rax, [rsp+388h+var_2A8]
0x1800052a7  mov     [rsp+388h+var_368], rax
0x1800052ac  mov     r9, r14
0x1800052af  mov     r8, rsi
0x1800052b2  mov     edx, [r15]
0x1800052b5  mov     rcx, [rsp+388h+var_2C0]
0x1800052bd  call    LnkSearchMachine
0x1800052c2  mov     ebx, eax
0x1800052c4  mov     [rsp+388h+var_348], eax
0x1800052c8  test    eax, eax
0x1800052ca  jns     short loc_1800052D3
0x1800052cc  cmp     eax, 8DEAD106h
0x1800052d1  jnz     short loc_1800052F3
0x1800052d3  lea     r8, [rsp+388h+var_258]; unsigned __int16 *
0x1800052db  mov     edx, 104h; unsigned __int64
0x1800052e0  mov     rcx, [rsp+388h+var_338]; unsigned __int16 *
0x1800052e5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800052ea  test    eax, eax
0x1800052ec  cmovs   ebx, eax
0x1800052ef  mov     [rsp+388h+var_348], ebx
0x1800052f3  lea     rax, ?s_tszTrkWksRemoteRpcEndPointOld@@3QBGB; "\\pipe\\ntsvcs"
0x1800052fa  jmp     short loc_180005338
0x1800052fc  lea     rcx, [rsp+388h+var_2E8]; this
0x180005304  call    ?UnInitialize@CRpcClientBinding@@QEAAXXZ; CRpcClientBinding::UnInitialize(void)
0x180005309  mov     r13d, 1
0x18000530f  mov     [rsp+388h+var_33C], r13d
0x180005314  lea     rax, ?s_tszTrkWksRemoteRpcEndPointOld@@3QBGB; "\\pipe\\ntsvcs"
0x18000531b  mov     ebx, [rsp+388h+var_348]
0x18000531f  mov     r12d, [rsp+388h+var_344]
0x180005324  mov     rdi, [rsp+388h+var_328]
0x180005329  mov     r15, [rsp+388h+var_320]
0x18000532e  mov     rsi, [rsp+388h+var_318]
0x180005333  mov     r14, [rsp+388h+var_310]
0x180005338  test    r13d, r13d
0x18000533b  jz      loc_1800050F7
0x180005341  inc     r12d
0x180005344  jmp     loc_180005242
0x180005349  jmp     short loc_180005354
0x18000534b  mov     ebx, 8DEAD104h
0x180005350  mov     [rsp+388h+var_348], ebx
0x180005354  cmp     [rsp+388h+var_340], 0
0x180005359  jnz     short loc_18000538D
0x18000535b  lea     rcx, [rsp+388h+var_2E8]; this
0x180005363  call    ??1CRpcClientBinding@@QEAA@XZ; CRpcClientBinding::~CRpcClientBinding(void)
0x180005368  mov     eax, ebx
0x18000536a  mov     rcx, [rsp+388h+var_48]
0x180005372  xor     rcx, rsp; StackCookie
0x180005375  call    __security_check_cookie
0x18000537a  add     rsp, 350h
0x180005381  pop     r15
0x180005383  pop     r14
0x180005385  pop     r13
0x180005387  pop     r12
0x180005389  pop     rdi
0x18000538a  pop     rsi
0x18000538b  pop     rbx
0x18000538c  retn
0x18000538d  call    ?RpcSecurityEnabled@CTrkRpcConfig@@SAHXZ; CTrkRpcConfig::RpcSecurityEnabled(void)
0x180005392  test    eax, eax
0x180005394  jz      short loc_18000539E
0x180005396  call    cs:__imp_RpcRevertToSelf
0x18000539c  jmp     short loc_18000535B
0x18000539e  call    cs:__imp_RevertToSelf
0x1800053a4  jmp     short loc_18000535B
0x1800113a0  push    rbp
0x1800113a2  sub     rsp, 40h
0x1800113a6  mov     rbp, rdx
0x1800113a9  mov     rax, [rcx]
0x1800113ac  cmp     dword ptr [rbp+44h], 0
0x1800113b0  jnz     short loc_1800113C1
0x1800113b2  cmp     dword ptr [rax], 6BAh
0x1800113b8  jnz     short loc_1800113C1
0x1800113ba  mov     eax, 1
0x1800113bf  jmp     short loc_1800113C3
0x1800113c1  xor     eax, eax
0x1800113c3  add     rsp, 40h
0x1800113c7  pop     rbp
0x1800113c8  retn
0x1800113ca  push    rbp
0x1800113cc  sub     rsp, 40h
0x1800113d0  mov     rbp, rdx
0x1800113d3  mov     eax, 1
0x1800113d8  add     rsp, 40h
0x1800113dc  pop     rbp
0x1800113dd  retn
```
