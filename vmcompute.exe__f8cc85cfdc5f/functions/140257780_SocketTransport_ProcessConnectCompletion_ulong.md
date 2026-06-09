# SocketTransport::ProcessConnectCompletion(ulong)

- ea: `0x140257780`
- end: `0x140257a52`
- name: `?ProcessConnectCompletion@SocketTransport@@AEAAXK@Z`
- size: `722`
- prototype: `void __fastcall(SocketTransport *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140022030`

## callees

- `0x140022d94`
- `0x140080180`
- `0x1400ec27c`
- `0x1401332f0`
- `0x140134048`
- `0x14022aac0`
- `0x1402566c0`
- `0x140256f2c`
- `0x140257780`

## import_xrefs

- `WS2_32!__imp_setsockopt` at `0x1402578ed`
- `WS2_32!__imp_setsockopt` at `0x140257982`
- `WS2_32!__imp_setsockopt` at `0x1402579e3`
- `WS2_32!__imp_setsockopt` at `0x1402578ed`
- `WS2_32!__imp_setsockopt` at `0x140257982`
- `WS2_32!__imp_setsockopt` at `0x1402579e3`
- `WS2_32!__imp_WSAGetLastError` at `0x140257901`
- `WS2_32!__imp_WSAGetLastError` at `0x140257992`
- `WS2_32!__imp_WSAGetLastError` at `0x1402579f3`
- `WS2_32!__imp_WSAGetLastError` at `0x140257901`
- `WS2_32!__imp_WSAGetLastError` at `0x140257992`
- `WS2_32!__imp_WSAGetLastError` at `0x1402579f3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x14025782e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x14025782e`

## string_xrefs

- `0x140257845`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x1402579a6`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x140257a09`: `onecore\vm\compute\common\transport\sockettransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SocketTransport::ProcessConnectCompletion(SocketTransport *this, int a2)
{
  _DWORD *v4; // rdi
  const char *v5; // r9
  int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rdx
  unsigned int Error; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  unsigned int optlen; // [rsp+20h] [rbp-E0h]
  unsigned int optlena; // [rsp+20h] [rbp-E0h]
  char v14[8]; // [rsp+30h] [rbp-D0h] BYREF
  char optval[8]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v16[42]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  *(_DWORD *)v14 = a2;
  v4 = (_DWORD *)((char *)this + 228);
  if ( *((_DWORD *)this + 57) != 9 )
    *v4 = a2 != 0 ? 8 : 6;
  memset_0(v16, 0, sizeof(v16));
  *(_QWORD *)optval = this;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v16);
  v16[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_ProcessConnect::`vftable';
  ComputeService::Diagnostics::TraceProvider::SocketTransport_ProcessConnect::StartActivity<SocketTransport *,unsigned long &,enum SocketTransport::TransportState &>(
    v16,
    optval,
    v14,
    v4);
  if ( !a2 && *v4 != 9 )
  {
    if ( !SetFileCompletionNotificationModes(*((HANDLE *)this + 15), 1u) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x63B,
        (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
        v5);
    v6 = *((_DWORD *)this + 24);
    if ( *((_BYTE *)this + 108) )
    {
      v7 = *((unsigned int *)this + 44);
      v8 = *((_QWORD *)this + 19);
      if ( v6 == 2 )
      {
        *((_OWORD *)this + 17) = *(_OWORD *)(v7 + v8 + 4);
        *((_OWORD *)this + 18) = *(_OWORD *)(v7 + v8 + 20);
      }
      else if ( v6 == 3 )
      {
        *((_DWORD *)this + 80) = *(_DWORD *)(v7 + v8 + 4);
        *((_WORD *)this + 162) = *(_WORD *)(v7 + v8 + 2);
      }
      else
      {
        *(_OWORD *)((char *)this + 344) = *(_OWORD *)(v7 + v8 + 8);
        *((_WORD *)this + 180) = *(_WORD *)(v7 + v8 + 2);
      }
      *(_QWORD *)optval = *((_QWORD *)this + 14);
      if ( !setsockopt(*((_QWORD *)this + 15), 0xFFFF, 28683, optval, 8) )
        goto LABEL_23;
      Error = WSAGetLastError();
      v10 = 1638;
    }
    else
    {
      if ( v6 == 2 )
      {
        *((_OWORD *)this + 17) = *(_OWORD *)((char *)this + 60);
        *((_OWORD *)this + 18) = *(_OWORD *)((char *)this + 76);
      }
      else if ( v6 == 3 )
      {
        *((_DWORD *)this + 80) = *((_DWORD *)this + 4);
        *((_WORD *)this + 162) = *((_WORD *)this + 10);
      }
      else
      {
        *(_OWORD *)((char *)this + 344) = *((_OWORD *)this + 2);
        *((_WORD *)this + 180) = *((_WORD *)this + 24);
      }
      if ( !setsockopt(*((_QWORD *)this + 15), 0xFFFF, 28688, 0, 0) )
        goto LABEL_23;
      Error = WSAGetLastError();
      v10 = 1675;
    }
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      (const char *)Error,
      optlen);
LABEL_23:
    if ( *((_DWORD *)this + 24) == 2 )
    {
      *(_DWORD *)v14 = 0;
      if ( setsockopt(*((_QWORD *)this + 15), 0xFFFF, 4097, v14, 4) )
      {
        v11 = WSAGetLastError();
        wil::details::in1diag3::Log_Win32(
          retaddr,
          (void *)0x69C,
          (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
          (const char *)v11,
          optlena);
      }
    }
  }
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v16);
  ComputeService::Diagnostics::TraceProvider::SocketTransport_ProcessConnect::~SocketTransport_ProcessConnect((ComputeService::Diagnostics::TraceProvider::SocketTransport_ProcessConnect *)v16);
}

```

## disassembly

```asm
0x140257780  mov     [rsp-8+arg_10], rbx
0x140257785  push    rbp
0x140257786  push    rsi
0x140257787  push    rdi
0x140257788  lea     rbp, [rsp-0A0h]
0x140257790  sub     rsp, 1A0h
0x140257797  mov     rax, cs:__security_cookie
0x14025779e  xor     rax, rsp
0x1402577a1  mov     [rbp+0B0h+var_20], rax
0x1402577a8  mov     esi, edx
0x1402577aa  mov     rbx, rcx
0x1402577ad  mov     dword ptr [rsp+1B0h+var_180], edx
0x1402577b1  lea     rdi, [rcx+0E4h]
0x1402577b8  cmp     dword ptr [rdi], 9
0x1402577bb  jz      short loc_1402577CB
0x1402577bd  mov     eax, edx
0x1402577bf  neg     eax
0x1402577c1  sbb     ecx, ecx
0x1402577c3  and     ecx, 2
0x1402577c6  add     ecx, 6
0x1402577c9  mov     [rdi], ecx
0x1402577cb  xor     edx, edx; Val
0x1402577cd  mov     r8d, 150h; Size
0x1402577d3  lea     rcx, [rsp+1B0h+var_170]; void *
0x1402577d8  call    memset_0
0x1402577dd  mov     qword ptr [rsp+1B0h+optval], rbx
0x1402577e2  lea     rdx, aSockettranspor_0; "SocketTransport_ProcessConnect"
0x1402577e9  lea     rcx, [rsp+1B0h+var_170]; struct wil::details::IFailureCallback *
0x1402577ee  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1402577f3  lea     rax, ??_7SocketTransport_ProcessConnect@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::SocketTransport_ProcessConnect::`vftable'
0x1402577fa  mov     [rsp+1B0h+var_170], rax
0x1402577ff  mov     r9, rdi
0x140257802  lea     r8, [rsp+1B0h+var_180]
0x140257807  lea     rdx, [rsp+1B0h+optval]
0x14025780c  lea     rcx, [rsp+1B0h+var_170]
0x140257811  call    ??$StartActivity@PEAVSocketTransport@@AEAKAEAW4TransportState@1@@SocketTransport_ProcessConnect@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEAVSocketTransport@@AEAKAEAW4TransportState@4@@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_ProcessConnect::StartActivity<SocketTransport *,ulong &,SocketTransport::TransportState &>(SocketTransport * &&,ulong &,SocketTransport::TransportState &)
0x140257816  nop
0x140257817  test    esi, esi
0x140257819  jnz     loc_140257A1A
0x14025781f  cmp     dword ptr [rdi], 9
0x140257822  jz      loc_140257A1A
0x140257828  mov     dl, 1; Flags
0x14025782a  mov     rcx, [rbx+78h]; FileHandle
0x14025782e  call    cs:__imp_SetFileCompletionNotificationModes
0x140257835  nop     dword ptr [rax+rax+00h]
0x14025783a  test    eax, eax
0x14025783c  jnz     short loc_140257857
0x14025783e  mov     rcx, [rbp+0B8h]; this
0x140257845  lea     r8, aOnecoreVmCompu_44; "onecore\\vm\\compute\\common\\transport"...
0x14025784c  mov     edx, 63Bh; void *
0x140257851  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140257857  mov     eax, [rbx+60h]
0x14025785a  cmp     byte ptr [rbx+6Ch], 0
0x14025785e  jz      loc_140257917
0x140257864  mov     ecx, [rbx+0B0h]
0x14025786a  mov     rdx, [rbx+98h]
0x140257871  cmp     eax, 2
0x140257874  jnz     short loc_140257892
0x140257876  movups  xmm0, xmmword ptr [rcx+rdx+4]
0x14025787b  movdqu  xmmword ptr [rbx+110h], xmm0
0x140257883  movups  xmm1, xmmword ptr [rcx+rdx+14h]
0x140257888  movdqu  xmmword ptr [rbx+120h], xmm1
0x140257890  jmp     short loc_1402578C8
0x140257892  cmp     eax, 3
0x140257895  jnz     short loc_1402578AF
0x140257897  mov     eax, [rcx+rdx+4]
0x14025789b  mov     [rbx+140h], eax
0x1402578a1  movzx   eax, word ptr [rcx+rdx+2]
0x1402578a6  mov     [rbx+144h], ax
0x1402578ad  jmp     short loc_1402578C8
0x1402578af  movups  xmm0, xmmword ptr [rcx+rdx+8]
0x1402578b4  movdqu  xmmword ptr [rbx+158h], xmm0
0x1402578bc  movzx   eax, word ptr [rcx+rdx+2]
0x1402578c1  mov     [rbx+168h], ax
0x1402578c8  mov     rax, [rbx+70h]
0x1402578cc  mov     qword ptr [rsp+1B0h+optval], rax
0x1402578d1  mov     [rsp+1B0h+optlen], 8; optlen
0x1402578d9  lea     r9, [rsp+1B0h+optval]; optval
0x1402578de  mov     edx, 0FFFFh; level
0x1402578e3  mov     r8d, 700Bh; optname
0x1402578e9  mov     rcx, [rbx+78h]; s
0x1402578ed  call    cs:__imp_setsockopt
0x1402578f4  nop     dword ptr [rax+rax+00h]
0x1402578f9  test    eax, eax
0x1402578fb  jz      loc_1402579B9
0x140257901  call    cs:__imp_WSAGetLastError
0x140257908  nop     dword ptr [rax+rax+00h]
0x14025790d  mov     edx, 666h
0x140257912  jmp     loc_1402579A3
0x140257917  cmp     eax, 2
0x14025791a  jnz     short loc_140257936
0x14025791c  movups  xmm0, xmmword ptr [rbx+3Ch]
0x140257920  movdqu  xmmword ptr [rbx+110h], xmm0
0x140257928  movups  xmm1, xmmword ptr [rbx+4Ch]
0x14025792c  movdqu  xmmword ptr [rbx+120h], xmm1
0x140257934  jmp     short loc_140257968
0x140257936  cmp     eax, 3
0x140257939  jnz     short loc_140257951
0x14025793b  mov     eax, [rbx+10h]
0x14025793e  mov     [rbx+140h], eax
0x140257944  movzx   eax, word ptr [rbx+14h]
0x140257948  mov     [rbx+144h], ax
0x14025794f  jmp     short loc_140257968
0x140257951  movups  xmm0, xmmword ptr [rbx+20h]
0x140257955  movdqu  xmmword ptr [rbx+158h], xmm0
0x14025795d  movzx   eax, word ptr [rbx+30h]
0x140257961  mov     [rbx+168h], ax
0x140257968  mov     [rsp+1B0h+optlen], 0; unsigned int
0x140257970  xor     r9d, r9d; optval
0x140257973  mov     edx, 0FFFFh; level
0x140257978  mov     r8d, 7010h; optname
0x14025797e  mov     rcx, [rbx+78h]; s
0x140257982  call    cs:__imp_setsockopt
0x140257989  nop     dword ptr [rax+rax+00h]
0x14025798e  test    eax, eax
0x140257990  jz      short loc_1402579B9
0x140257992  call    cs:__imp_WSAGetLastError
0x140257999  nop     dword ptr [rax+rax+00h]
0x14025799e  mov     edx, 68Bh; void *
0x1402579a3  mov     r9d, eax; char *
0x1402579a6  lea     r8, aOnecoreVmCompu_44; "onecore\\vm\\compute\\common\\transport"...
0x1402579ad  mov     rcx, [rbp+0B8h]; this
0x1402579b4  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1402579b9  cmp     dword ptr [rbx+60h], 2
0x1402579bd  jnz     short loc_140257A1A
0x1402579bf  mov     dword ptr [rsp+1B0h+var_180], 0
0x1402579c7  mov     [rsp+1B0h+optlen], 4; unsigned int
0x1402579cf  lea     r9, [rsp+1B0h+var_180]; optval
0x1402579d4  mov     edx, 0FFFFh; level
0x1402579d9  mov     r8d, 1001h; optname
0x1402579df  mov     rcx, [rbx+78h]; s
0x1402579e3  call    cs:__imp_setsockopt
0x1402579ea  nop     dword ptr [rax+rax+00h]
0x1402579ef  test    eax, eax
0x1402579f1  jz      short loc_140257A1A
0x1402579f3  call    cs:__imp_WSAGetLastError
0x1402579fa  nop     dword ptr [rax+rax+00h]
0x1402579ff  mov     r9d, eax; char *
0x140257a02  mov     rcx, [rbp+0B8h]; this
0x140257a09  lea     r8, aOnecoreVmCompu_44; "onecore\\vm\\compute\\common\\transport"...
0x140257a10  mov     edx, 69Ch; void *
0x140257a15  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x140257a1a  lea     rcx, [rsp+1B0h+var_170]
0x140257a1f  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140257a24  nop
0x140257a25  lea     rcx, [rsp+1B0h+var_170]; this
0x140257a2a  call    ??1SocketTransport_ProcessConnect@TraceProvider@Diagnostics@ComputeService@@QEAA@XZ; ComputeService::Diagnostics::TraceProvider::SocketTransport_ProcessConnect::~SocketTransport_ProcessConnect(void)
0x140257a2f  mov     rcx, [rbp+0B0h+var_20]
0x140257a36  xor     rcx, rsp; StackCookie
0x140257a39  call    __security_check_cookie
0x140257a3e  mov     rbx, [rsp+1B0h+arg_10]
0x140257a46  add     rsp, 1A0h
0x140257a4d  pop     rdi
0x140257a4e  pop     rsi
0x140257a4f  pop     rbp
0x140257a50  retn
```
