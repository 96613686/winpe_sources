# SocketTransport::ProcessConnectCompletion(ulong)

- ea: `0x140061ab4`
- end: `0x140061d6b`
- name: `?ProcessConnectCompletion@SocketTransport@@AEAAXK@Z`
- size: `695`
- prototype: `void __fastcall(SocketTransport *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140061070`

## callees

- `0x140005360`
- `0x140006098`
- `0x14000ddac`
- `0x14005dce0`
- `0x14005efac`
- `0x14005f2e4`
- `0x140060248`
- `0x140061428`
- `0x140061ab4`
- `0x140062518`

## import_xrefs

- `WS2_32!__imp_setsockopt` at `0x140061c0c`
- `WS2_32!__imp_setsockopt` at `0x140061c95`
- `WS2_32!__imp_setsockopt` at `0x140061ce3`
- `WS2_32!__imp_setsockopt` at `0x140061c0c`
- `WS2_32!__imp_setsockopt` at `0x140061c95`
- `WS2_32!__imp_setsockopt` at `0x140061ce3`
- `WS2_32!__imp_WSAGetLastError` at `0x140061c1a`
- `WS2_32!__imp_WSAGetLastError` at `0x140061c9f`
- `WS2_32!__imp_WSAGetLastError` at `0x140061ced`
- `WS2_32!__imp_WSAGetLastError` at `0x140061c1a`
- `WS2_32!__imp_WSAGetLastError` at `0x140061c9f`
- `WS2_32!__imp_WSAGetLastError` at `0x140061ced`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x140061b68`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x140061b68`

## string_xrefs

- `0x140061d59`: `onecore\vm\compute\common\transport\sockettransport.cpp`

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
  unsigned int v10; // r8d
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // r8d
  unsigned int optlen; // [rsp+20h] [rbp-E0h]
  unsigned int optlena; // [rsp+20h] [rbp-E0h]
  char v16[8]; // [rsp+30h] [rbp-D0h] BYREF
  char optval[8]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v18[42]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  *(_DWORD *)v16 = a2;
  v4 = (_DWORD *)((char *)this + 228);
  if ( *((_DWORD *)this + 57) != 9 )
    *v4 = a2 != 0 ? 8 : 6;
  memset_0(v18, 0, sizeof(v18));
  *(_QWORD *)optval = this;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v18,
    "SocketTransport_ProcessConnect");
  v18[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_ProcessConnect::`vftable';
  ComputeService::Diagnostics::TraceProvider::SocketTransport_ProcessConnect::StartActivity<SocketTransport *,unsigned long &,enum SocketTransport::TransportState &>(
    v18,
    optval,
    v16,
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
        goto LABEL_22;
      Error = WSAGetLastError();
      v11 = 1638;
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
        goto LABEL_22;
      Error = WSAGetLastError();
      v11 = 1675;
    }
    wil::details::in1diag3::Log_Win32(retaddr, (void *)v11, v10, (const char *)Error, optlen);
LABEL_22:
    if ( *((_DWORD *)this + 24) == 2 )
    {
      *(_DWORD *)v16 = 0;
      if ( setsockopt(*((_QWORD *)this + 15), 0xFFFF, 4097, v16, 4) )
      {
        v12 = WSAGetLastError();
        wil::details::in1diag3::Log_Win32(retaddr, (void *)0x69C, v13, (const char *)v12, optlena);
      }
    }
  }
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v18);
  v18[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_ProcessConnect::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v18);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(v18);
}

```

## disassembly

```asm
0x140061ab4  mov     [rsp-8+arg_10], rbx
0x140061ab9  mov     [rsp-8+arg_18], rsi
0x140061abe  push    rbp
0x140061abf  push    rdi
0x140061ac0  push    r15
0x140061ac2  lea     rbp, [rsp-0A0h]
0x140061aca  sub     rsp, 1A0h
0x140061ad1  mov     rax, cs:__security_cookie
0x140061ad8  xor     rax, rsp
0x140061adb  mov     [rbp+0B0h+var_20], rax
0x140061ae2  mov     esi, edx
0x140061ae4  mov     rbx, rcx
0x140061ae7  mov     dword ptr [rsp+1B0h+var_180], edx
0x140061aeb  lea     rdi, [rcx+0E4h]
0x140061af2  cmp     dword ptr [rdi], 9
0x140061af5  jz      short loc_140061B05
0x140061af7  mov     eax, edx
0x140061af9  neg     eax
0x140061afb  sbb     ecx, ecx
0x140061afd  and     ecx, 2
0x140061b00  add     ecx, 6
0x140061b03  mov     [rdi], ecx
0x140061b05  xor     edx, edx; Val
0x140061b07  mov     r8d, 150h; Size
0x140061b0d  lea     rcx, [rsp+1B0h+var_170]; void *
0x140061b12  call    memset_0
0x140061b17  mov     qword ptr [rsp+1B0h+optval], rbx
0x140061b1c  lea     rdx, aSockettranspor_0; "SocketTransport_ProcessConnect"
0x140061b23  lea     rcx, [rsp+1B0h+var_170]
0x140061b28  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140061b2d  lea     r15, ??_7SocketTransport_ProcessConnect@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::SocketTransport_ProcessConnect::`vftable'
0x140061b34  mov     [rsp+1B0h+var_170], r15
0x140061b39  mov     r9, rdi
0x140061b3c  lea     r8, [rsp+1B0h+var_180]
0x140061b41  lea     rdx, [rsp+1B0h+optval]
0x140061b46  lea     rcx, [rsp+1B0h+var_170]
0x140061b4b  call    ??$StartActivity@PEAVSocketTransport@@AEAKAEAW4TransportState@1@@SocketTransport_ProcessConnect@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEAVSocketTransport@@AEAKAEAW4TransportState@4@@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_ProcessConnect::StartActivity<SocketTransport *,ulong &,SocketTransport::TransportState &>(SocketTransport * &&,ulong &,SocketTransport::TransportState &)
0x140061b50  nop
0x140061b51  test    esi, esi
0x140061b53  jnz     loc_140061D07
0x140061b59  cmp     dword ptr [rdi], 9
0x140061b5c  jz      loc_140061D07
0x140061b62  mov     dl, 1; Flags
0x140061b64  mov     rcx, [rbx+78h]; FileHandle
0x140061b68  call    cs:__imp_SetFileCompletionNotificationModes
0x140061b6e  test    eax, eax
0x140061b70  jz      loc_140061D52
0x140061b76  mov     eax, [rbx+60h]
0x140061b79  cmp     [rbx+6Ch], sil
0x140061b7d  jz      loc_140061C2A
0x140061b83  mov     ecx, [rbx+0B0h]
0x140061b89  mov     rdx, [rbx+98h]
0x140061b90  cmp     eax, 2
0x140061b93  jnz     short loc_140061BB1
0x140061b95  movups  xmm0, xmmword ptr [rcx+rdx+4]
0x140061b9a  movdqu  xmmword ptr [rbx+110h], xmm0
0x140061ba2  movups  xmm1, xmmword ptr [rcx+rdx+14h]
0x140061ba7  movdqu  xmmword ptr [rbx+120h], xmm1
0x140061baf  jmp     short loc_140061BE7
0x140061bb1  cmp     eax, 3
0x140061bb4  jnz     short loc_140061BCE
0x140061bb6  mov     eax, [rcx+rdx+4]
0x140061bba  mov     [rbx+140h], eax
0x140061bc0  movzx   eax, word ptr [rcx+rdx+2]
0x140061bc5  mov     [rbx+144h], ax
0x140061bcc  jmp     short loc_140061BE7
0x140061bce  movups  xmm0, xmmword ptr [rcx+rdx+8]
0x140061bd3  movdqu  xmmword ptr [rbx+158h], xmm0
0x140061bdb  movzx   eax, word ptr [rcx+rdx+2]
0x140061be0  mov     [rbx+168h], ax
0x140061be7  mov     rax, [rbx+70h]
0x140061beb  mov     qword ptr [rsp+1B0h+optval], rax
0x140061bf0  mov     [rsp+1B0h+optlen], 8; optlen
0x140061bf8  lea     r9, [rsp+1B0h+optval]; optval
0x140061bfd  mov     edx, 0FFFFh; level
0x140061c02  mov     r8d, 700Bh; optname
0x140061c08  mov     rcx, [rbx+78h]; s
0x140061c0c  call    cs:__imp_setsockopt
0x140061c12  test    eax, eax
0x140061c14  jz      loc_140061CB9
0x140061c1a  call    cs:__imp_WSAGetLastError
0x140061c20  mov     edx, 666h
0x140061c25  jmp     loc_140061CAA
0x140061c2a  cmp     eax, 2
0x140061c2d  jnz     short loc_140061C49
0x140061c2f  movups  xmm0, xmmword ptr [rbx+3Ch]
0x140061c33  movdqu  xmmword ptr [rbx+110h], xmm0
0x140061c3b  movups  xmm1, xmmword ptr [rbx+4Ch]
0x140061c3f  movdqu  xmmword ptr [rbx+120h], xmm1
0x140061c47  jmp     short loc_140061C7B
0x140061c49  cmp     eax, 3
0x140061c4c  jnz     short loc_140061C64
0x140061c4e  mov     eax, [rbx+10h]
0x140061c51  mov     [rbx+140h], eax
0x140061c57  movzx   eax, word ptr [rbx+14h]
0x140061c5b  mov     [rbx+144h], ax
0x140061c62  jmp     short loc_140061C7B
0x140061c64  movups  xmm0, xmmword ptr [rbx+20h]
0x140061c68  movdqu  xmmword ptr [rbx+158h], xmm0
0x140061c70  movzx   eax, word ptr [rbx+30h]
0x140061c74  mov     [rbx+168h], ax
0x140061c7b  mov     [rsp+1B0h+optlen], 0; unsigned int
0x140061c83  xor     r9d, r9d; optval
0x140061c86  mov     edx, 0FFFFh; level
0x140061c8b  mov     r8d, 7010h; optname
0x140061c91  mov     rcx, [rbx+78h]; s
0x140061c95  call    cs:__imp_setsockopt
0x140061c9b  test    eax, eax
0x140061c9d  jz      short loc_140061CB9
0x140061c9f  call    cs:__imp_WSAGetLastError
0x140061ca5  mov     edx, 68Bh; void *
0x140061caa  mov     r9d, eax; char *
0x140061cad  mov     rcx, [rbp+0B8h]; this
0x140061cb4  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x140061cb9  cmp     dword ptr [rbx+60h], 2
0x140061cbd  jnz     short loc_140061D07
0x140061cbf  mov     dword ptr [rsp+1B0h+var_180], 0
0x140061cc7  mov     [rsp+1B0h+optlen], 4; unsigned int
0x140061ccf  lea     r9, [rsp+1B0h+var_180]; optval
0x140061cd4  mov     edx, 0FFFFh; level
0x140061cd9  mov     r8d, 1001h; optname
0x140061cdf  mov     rcx, [rbx+78h]; s
0x140061ce3  call    cs:__imp_setsockopt
0x140061ce9  test    eax, eax
0x140061ceb  jz      short loc_140061D07
0x140061ced  call    cs:__imp_WSAGetLastError
0x140061cf3  mov     r9d, eax; char *
0x140061cf6  mov     rcx, [rbp+0B8h]; this
0x140061cfd  mov     edx, 69Ch; void *
0x140061d02  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x140061d07  lea     rcx, [rsp+1B0h+var_170]
0x140061d0c  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140061d11  nop
0x140061d12  mov     [rsp+1B0h+var_170], r15
0x140061d17  lea     rcx, [rsp+1B0h+var_170]
0x140061d1c  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140061d21  lea     rcx, [rsp+1B0h+var_170]
0x140061d26  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140061d2b  mov     rcx, [rbp+0B0h+var_20]
0x140061d32  xor     rcx, rsp; StackCookie
0x140061d35  call    __security_check_cookie
0x140061d3a  lea     r11, [rsp+1B0h+var_10]
0x140061d42  mov     rbx, [r11+30h]
0x140061d46  mov     rsi, [r11+38h]
0x140061d4a  mov     rsp, r11
0x140061d4d  pop     r15
0x140061d4f  pop     rdi
0x140061d50  pop     rbp
0x140061d51  retn
0x140061d52  mov     rcx, [rbp+0B8h]; this
0x140061d59  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x140061d60  mov     edx, 63Bh; void *
0x140061d65  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
