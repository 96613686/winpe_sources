# VerifyAndDispatchClientRequest(_IMG_SERVER_CONTEXT *,void *,tagWDS_ENDPOINT *,tagWDS_ENDPOINT *,void *,ulong)

- ea: `0x180006e50`
- end: `0x18000710d`
- name: `?VerifyAndDispatchClientRequest@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAXPEAUtagWDS_ENDPOINT@@21K@Z`
- size: `701`
- prototype: `__int64 __fastcall(struct _IMG_SERVER_CONTEXT *, void *, struct tagWDS_ENDPOINT *, struct tagWDS_ENDPOINT *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006ab0`

## callees

- `0x180002a0c`
- `0x180002e64`
- `0x1800036b0`
- `0x180003838`
- `0x180003af4`
- `0x180003dc4`
- `0x180006020`
- `0x180006548`
- `0x180006e50`
- `0x180007fd8`
- `0x18000b370`
- `0x180012144`
- `0x180012214`
- `0x180016020`
- `0x180017010`

## import_xrefs

- `WDSSRV!WdsPerfCounterAdd` at `0x180006ffc`
- `WDSSRV!WdsPerfCounterAdd` at `0x180007027`
- `WDSSRV!WdsPerfCounterAdd` at `0x180007052`
- `WDSSRV!WdsPerfCounterAdd` at `0x18000707a`
- `WDSSRV!WdsPerfCounterAdd` at `0x1800070b2`
- `WDSSRV!WdsPerfCounterAdd` at `0x180006ffc`
- `WDSSRV!WdsPerfCounterAdd` at `0x180007027`
- `WDSSRV!WdsPerfCounterAdd` at `0x180007052`
- `WDSSRV!WdsPerfCounterAdd` at `0x18000707a`
- `WDSSRV!WdsPerfCounterAdd` at `0x1800070b2`

## string_xrefs

- `0x180006f62`: `VerifyAndDispatchClientRequest: Invalid security channel used by client.`

## pseudocode

```c
__int64 __fastcall VerifyAndDispatchClientRequest(
        struct _IMG_SERVER_CONTEXT *a1,
        void *a2,
        struct tagWDS_ENDPOINT *a3,
        struct tagWDS_ENDPOINT *a4,
        void *a5,
        unsigned int a6)
{
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // r8
  struct tagWDS_ENDPOINT *v15; // rdx
  struct _IMG_SERVER_CONTEXT *v16; // rcx
  void *v17; // r9
  unsigned int v18; // r14d
  struct tagWDS_ENDPOINT *v19; // rdx
  struct _IMG_SERVER_CONTEXT *v20; // rcx
  unsigned int v21; // eax
  void *v23[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v24; // [rsp+40h] [rbp-20h]
  unsigned int v25; // [rsp+48h] [rbp-18h]

  v24 = 0;
  v25 = 0;
  *(_OWORD *)v23 = 0;
  WdsImgTrace(0x10000u, L"-> VerifyAndDispatchClientRequest");
  if ( a1 || (LODWORD(v12) = 87, !(unsigned int)ElValidateWin32(87, v10, v11, 2621)) )
  {
    v12 = CControlPacket::RecvInitialize((CControlPacket *)v23, g_hProvider, a5, a6);
    if ( !(unsigned int)ElValidateWin32(v12, v13, v14, 2629) )
    {
      v18 = v25;
      if ( v25 < 9 )
      {
        if ( (*((_BYTE *)a4 + 8) & *((_BYTE *)&g_AuthMatrix + 4 * v25) & 3) != 0 )
        {
          switch ( v25 )
          {
            case 2u:
              WdsPerfCounterAdd(20);
              v21 = HandlerImageEnumeration(a1, a4, a2, (struct CImgSrvPacket *)v23);
              break;
            case 3u:
              v21 = HandlerLogInitialize(a1, a4, a2, v17);
              break;
            case 4u:
              WdsPerfCounterAdd(24);
              v21 = HandlerLogMessage(a1, a4, a2, v23[1]);
              break;
            case 5u:
              WdsPerfCounterAdd(22);
              v21 = HandlerClientUnattend(a1, a4, a2, v23[1]);
              break;
            case 6u:
              WdsPerfCounterAdd(22);
              v21 = HandlerUnattendVariables(a1, a4, a2, v23[1]);
              break;
            case 7u:
              WdsPerfCounterAdd(26);
              v21 = HandlerDomainJoinInformation(a1, a4, a2, v23[1]);
              break;
            case 8u:
              v21 = HandlerResetBootProgram(a1, a3, a4, a2, v23[1]);
              break;
            default:
              WdsImgTrace(0x80000u, L"Unknown OpCode. OpCode [%u].", v25);
              v21 = HandlerError(v20, v19, a2, 1u);
              break;
          }
          LODWORD(v12) = v21;
        }
        else
        {
          LODWORD(v12) = HandlerError(
                           (struct _IMG_SERVER_CONTEXT *)(unsigned int)(*((_DWORD *)a4 + 2)
                                                                      & *((_DWORD *)&g_AuthMatrix + v25)),
                           v15,
                           a2,
                           0xBu);
          if ( g_ErrLibTraceFunctionEx )
            g_ErrLibTraceFunctionEx(
              0x10000u,
              L"VerifyAndDispatchClientRequest: Invalid security channel used by client.");
        }
      }
      else
      {
        LODWORD(v12) = HandlerError(v16, v15, a2, 1u);
        if ( g_ErrLibTraceFunctionEx )
          g_ErrLibTraceFunctionEx(
            0x10000u,
            L"VerifyAndDispatchClientRequest: Invalid OP code received from client: %u",
            v18);
      }
    }
  }
  WdsImgTrace(0x10000u, L"<- VerifyAndDispatchClientRequest=%x", (unsigned int)v12);
  CControlPacket::Shutdown((CControlPacket *)v23);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180006e50  push    rbp
0x180006e52  push    rbx
0x180006e53  push    rsi
0x180006e54  push    rdi
0x180006e55  push    r12
0x180006e57  push    r14
0x180006e59  push    r15
0x180006e5b  mov     rbp, rsp
0x180006e5e  sub     rsp, 60h
0x180006e62  mov     rax, cs:__security_cookie
0x180006e69  xor     rax, rsp
0x180006e6c  mov     [rbp+var_10], rax
0x180006e70  mov     r14, [rbp+arg_20]
0x180006e74  xor     eax, eax
0x180006e76  mov     rdi, rdx
0x180006e79  mov     [rbp+var_20], rax
0x180006e7d  mov     r15, rcx
0x180006e80  mov     [rbp+var_18], eax
0x180006e83  xorps   xmm0, xmm0
0x180006e86  lea     rdx, aVerifyanddispa_1; "-> VerifyAndDispatchClientRequest"
0x180006e8d  mov     ecx, 10000h; unsigned int
0x180006e92  mov     rsi, r9
0x180006e95  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180006e9a  mov     r12, r8
0x180006e9d  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x180006ea2  test    r15, r15
0x180006ea5  jnz     short loc_180006EC0
0x180006ea7  lea     ebx, [r15+57h]
0x180006eab  mov     r9d, 0A3Dh
0x180006eb1  mov     ecx, ebx
0x180006eb3  call    ElValidateWin32
0x180006eb8  test    eax, eax
0x180006eba  jnz     loc_1800070D2
0x180006ec0  mov     r9d, [rbp+arg_28]; unsigned int
0x180006ec4  lea     rcx, [rbp+var_30]; this
0x180006ec8  mov     rdx, cs:?g_hProvider@@3PEAXEA; void *
0x180006ecf  mov     r8, r14; void *
0x180006ed2  call    ?RecvInitialize@CControlPacket@@QEAAKPEAX0K@Z; CControlPacket::RecvInitialize(void *,void *,ulong)
0x180006ed7  mov     r9d, 0A45h
0x180006edd  mov     ecx, eax
0x180006edf  mov     ebx, eax
0x180006ee1  call    ElValidateWin32
0x180006ee6  test    eax, eax
0x180006ee8  jnz     loc_1800070D2
0x180006eee  mov     r14d, [rbp+var_18]
0x180006ef2  cmp     r14d, 9
0x180006ef6  jb      short loc_180006F2F
0x180006ef8  lea     r9d, [rax+1]; unsigned int
0x180006efc  mov     r8, rdi; void *
0x180006eff  call    ?HandlerError@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAUtagWDS_ENDPOINT@@PEAXK@Z; HandlerError(_IMG_SERVER_CONTEXT *,tagWDS_ENDPOINT *,void *,ulong)
0x180006f04  mov     ebx, eax
0x180006f06  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180006f0d  test    rax, rax
0x180006f10  jz      loc_1800070D2
0x180006f16  mov     r8d, r14d
0x180006f19  lea     rdx, aVerifyanddispa_2; "VerifyAndDispatchClientRequest: Invalid"...
0x180006f20  mov     ecx, 10000h
0x180006f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f2a  jmp     loc_1800070D2
0x180006f2f  lea     rcx, ?g_AuthMatrix@@3PAKA; ulong near * g_AuthMatrix
0x180006f36  mov     ecx, [rcx+r14*4]
0x180006f3a  and     ecx, [rsi+8]; struct _IMG_SERVER_CONTEXT *
0x180006f3d  test    cl, 3
0x180006f40  jnz     short loc_180006F78
0x180006f42  mov     r9d, 0Bh; unsigned int
0x180006f48  mov     r8, rdi; void *
0x180006f4b  call    ?HandlerError@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAUtagWDS_ENDPOINT@@PEAXK@Z; HandlerError(_IMG_SERVER_CONTEXT *,tagWDS_ENDPOINT *,void *,ulong)
0x180006f50  mov     ebx, eax
0x180006f52  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180006f59  test    rax, rax
0x180006f5c  jz      loc_1800070D2
0x180006f62  lea     rdx, aVerifyanddispa; "VerifyAndDispatchClientRequest: Invalid"...
0x180006f69  mov     ecx, 10000h
0x180006f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f73  jmp     loc_1800070D2
0x180006f78  mov     eax, r14d
0x180006f7b  sub     eax, 2
0x180006f7e  jz      loc_1800070AA
0x180006f84  sub     eax, 1
0x180006f87  jz      loc_18000709A
0x180006f8d  sub     eax, 1
0x180006f90  jz      loc_180007072
0x180006f96  sub     eax, 1
0x180006f99  jz      loc_18000704A
0x180006f9f  sub     eax, 1
0x180006fa2  jz      short loc_18000701F
0x180006fa4  sub     eax, 1
0x180006fa7  jz      short loc_180006FF4
0x180006fa9  cmp     eax, 1
0x180006fac  jz      short loc_180006FD5
0x180006fae  mov     r8d, r14d
0x180006fb1  lea     rdx, aUnknownOpcodeO; "Unknown OpCode. OpCode [%u]."
0x180006fb8  mov     ecx, 80000h; unsigned int
0x180006fbd  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x180006fc2  mov     r9d, 1; unsigned int
0x180006fc8  mov     r8, rdi; void *
0x180006fcb  call    ?HandlerError@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAUtagWDS_ENDPOINT@@PEAXK@Z; HandlerError(_IMG_SERVER_CONTEXT *,tagWDS_ENDPOINT *,void *,ulong)
0x180006fd0  jmp     loc_1800070D0
0x180006fd5  mov     rax, [rbp+var_30+8]
0x180006fd9  mov     r9, rdi; void *
0x180006fdc  mov     r8, rsi; struct tagWDS_ENDPOINT *
0x180006fdf  mov     [rsp+60h+var_40], rax; void *
0x180006fe4  mov     rdx, r12; struct tagWDS_ENDPOINT *
0x180006fe7  mov     rcx, r15; struct _IMG_SERVER_CONTEXT *
0x180006fea  call    ?HandlerResetBootProgram@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAUtagWDS_ENDPOINT@@1PEAX2@Z; HandlerResetBootProgram(_IMG_SERVER_CONTEXT *,tagWDS_ENDPOINT *,tagWDS_ENDPOINT *,void *,void *)
0x180006fef  jmp     loc_1800070D0
0x180006ff4  mov     edx, 1
0x180006ff9  lea     ecx, [rdx+19h]
0x180006ffc  call    cs:__imp_WdsPerfCounterAdd
0x180007003  nop     dword ptr [rax+rax+00h]
0x180007008  mov     r9, [rbp+var_30+8]; void *
0x18000700c  mov     r8, rdi; void *
0x18000700f  mov     rdx, rsi; struct tagWDS_ENDPOINT *
0x180007012  mov     rcx, r15; struct _IMG_SERVER_CONTEXT *
0x180007015  call    ?HandlerDomainJoinInformation@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAUtagWDS_ENDPOINT@@PEAX2@Z; HandlerDomainJoinInformation(_IMG_SERVER_CONTEXT *,tagWDS_ENDPOINT *,void *,void *)
0x18000701a  jmp     loc_1800070D0
0x18000701f  mov     edx, 1
0x180007024  lea     ecx, [rdx+15h]
0x180007027  call    cs:__imp_WdsPerfCounterAdd
0x18000702e  nop     dword ptr [rax+rax+00h]
0x180007033  mov     r9, [rbp+var_30+8]; void *
0x180007037  mov     r8, rdi; void *
0x18000703a  mov     rdx, rsi; struct tagWDS_ENDPOINT *
0x18000703d  mov     rcx, r15; struct _IMG_SERVER_CONTEXT *
0x180007040  call    ?HandlerUnattendVariables@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAUtagWDS_ENDPOINT@@PEAX2@Z; HandlerUnattendVariables(_IMG_SERVER_CONTEXT *,tagWDS_ENDPOINT *,void *,void *)
0x180007045  jmp     loc_1800070D0
0x18000704a  mov     edx, 1
0x18000704f  lea     ecx, [rdx+15h]
0x180007052  call    cs:__imp_WdsPerfCounterAdd
0x180007059  nop     dword ptr [rax+rax+00h]
0x18000705e  mov     r9, [rbp+var_30+8]; void *
0x180007062  mov     r8, rdi; void *
0x180007065  mov     rdx, rsi; struct tagWDS_ENDPOINT *
0x180007068  mov     rcx, r15; struct _IMG_SERVER_CONTEXT *
0x18000706b  call    ?HandlerClientUnattend@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAUtagWDS_ENDPOINT@@PEAX2@Z; HandlerClientUnattend(_IMG_SERVER_CONTEXT *,tagWDS_ENDPOINT *,void *,void *)
0x180007070  jmp     short loc_1800070D0
0x180007072  mov     edx, 1
0x180007077  lea     ecx, [rdx+17h]
0x18000707a  call    cs:__imp_WdsPerfCounterAdd
0x180007081  nop     dword ptr [rax+rax+00h]
0x180007086  mov     r9, [rbp+var_30+8]; void *
0x18000708a  mov     r8, rdi; void *
0x18000708d  mov     rdx, rsi; struct tagWDS_ENDPOINT *
0x180007090  mov     rcx, r15; struct _IMG_SERVER_CONTEXT *
0x180007093  call    ?HandlerLogMessage@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAUtagWDS_ENDPOINT@@PEAX2@Z; HandlerLogMessage(_IMG_SERVER_CONTEXT *,tagWDS_ENDPOINT *,void *,void *)
0x180007098  jmp     short loc_1800070D0
0x18000709a  mov     r8, rdi; void *
0x18000709d  mov     rdx, rsi; struct tagWDS_ENDPOINT *
0x1800070a0  mov     rcx, r15; struct _IMG_SERVER_CONTEXT *
0x1800070a3  call    ?HandlerLogInitialize@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAUtagWDS_ENDPOINT@@PEAX2@Z; HandlerLogInitialize(_IMG_SERVER_CONTEXT *,tagWDS_ENDPOINT *,void *,void *)
0x1800070a8  jmp     short loc_1800070D0
0x1800070aa  mov     edx, 1
0x1800070af  lea     ecx, [rdx+13h]
0x1800070b2  call    cs:__imp_WdsPerfCounterAdd
0x1800070b9  nop     dword ptr [rax+rax+00h]
0x1800070be  lea     r9, [rbp+var_30]; struct CImgSrvPacket *
0x1800070c2  mov     r8, rdi; void *
0x1800070c5  mov     rdx, rsi; struct tagWDS_ENDPOINT *
0x1800070c8  mov     rcx, r15; struct _IMG_SERVER_CONTEXT *
0x1800070cb  call    ?HandlerImageEnumeration@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAUtagWDS_ENDPOINT@@PEAXPEAVCImgSrvPacket@@@Z; HandlerImageEnumeration(_IMG_SERVER_CONTEXT *,tagWDS_ENDPOINT *,void *,CImgSrvPacket *)
0x1800070d0  mov     ebx, eax
0x1800070d2  mov     r8d, ebx
0x1800070d5  lea     rdx, aVerifyanddispa_0; "<- VerifyAndDispatchClientRequest=%x"
0x1800070dc  mov     ecx, 10000h; unsigned int
0x1800070e1  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x1800070e6  lea     rcx, [rbp+var_30]; this
0x1800070ea  call    ?Shutdown@CControlPacket@@QEAAKXZ; CControlPacket::Shutdown(void)
0x1800070ef  mov     eax, ebx
0x1800070f1  mov     rcx, [rbp+var_10]
0x1800070f5  xor     rcx, rsp; StackCookie
0x1800070f8  call    __security_check_cookie
0x1800070fd  add     rsp, 60h
0x180007101  pop     r15
0x180007103  pop     r14
0x180007105  pop     r12
0x180007107  pop     rdi
0x180007108  pop     rsi
0x180007109  pop     rbx
0x18000710a  pop     rbp
0x18000710b  retn
```
