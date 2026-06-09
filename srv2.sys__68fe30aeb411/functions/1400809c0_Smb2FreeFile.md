# Smb2FreeFile

- ea: `0x1400809c0`
- end: `0x140080da6`
- name: `Smb2FreeFile`
- size: `998`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14000cdf0`
- `0x140012790`
- `0x1400128b0`
- `0x14002a890`
- `0x14007a84c`

## callees

- `0x140004df4`
- `0x140005070`
- `0x140012c30`
- `0x140013810`
- `0x140013920`
- `0x14002a410`
- `0x14002b49c`
- `0x140038490`
- `0x140063ba4`
- `0x140077340`
- `0x1400809c0`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140080a4a`
- `ntoskrnl!ExDeleteResourceLite` at `0x140080a4a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140080c4f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098723`
- `ntoskrnl!ExReleaseResourceLite` at `0x140080c4f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098723`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140080c25`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140098706`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140080c25`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140098706`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140080bb8`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140080bb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080b46`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080cc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080d95`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080b46`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080cc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080d95`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140098756`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140098756`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140080cf9`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140080cf9`
- `srvnet!SrvNetFreePool` at `0x140080d84`
- `srvnet!SrvNetFreePool` at `0x140080d84`
- `srvnet!SrvAdminDeregisterFile` at `0x140080a0a`
- `srvnet!SrvAdminDeregisterFile` at `0x140080a0a`

## string_xrefs

- `0x140080b99`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Smb2FreeFile(char *P, __int64 a2, __int64 a3)
{
  __int64 v4; // rdx
  signed __int64 v5; // rcx
  volatile signed __int64 **v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rsi
  signed __int64 v9; // rax
  _QWORD *v10; // rsi
  __int64 result; // rax
  bool v12; // zf
  __int64 v13; // rdi
  USHORT CurrentNodeNumber; // ax
  __int64 v15; // r8
  __int64 v16; // rcx
  volatile signed __int64 **v17; // r14
  volatile signed __int64 *v18; // r12
  volatile signed __int64 *v19; // rbp
  volatile signed __int64 *v20; // r15
  signed __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 *v24; // rax
  struct _ERESOURCE *v25; // rcx
  struct _ERESOURCE *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r8
  PVOID BackTrace[2]; // [rsp+48h] [rbp-50h] BYREF
  __int64 v30; // [rsp+58h] [rbp-40h]

  if ( (byte_14004C339 & 8) != 0 )
    McTemplateK0j_EtwWriteTransfer(P, SMB2_EVENT_FILE_TERMINATE, a3, P + 96);
  v4 = *((_QWORD *)P + 40);
  if ( v4 != -1 )
  {
    SrvAdminDeregisterFile((unsigned int)Smb2ProviderId, v4, **((unsigned __int8 **)P + 8));
    *((_QWORD *)P + 40) = -1;
  }
  if ( P[232] )
  {
    v12 = *((_DWORD *)P + 2) == 5;
    *((_QWORD *)P + 6) = Smb2ScheduleFileAndFree;
    *((_DWORD *)P + 18) = 2;
    if ( v12 )
    {
      LOBYTE(v4) = 1;
      SRV2_PERF_ENTER_EX(P + 584, v4, 391, "Srv2PostToThreadPool", 1);
    }
    v13 = *(_QWORD *)(*((_QWORD *)P + 8) + 152LL);
    CurrentNodeNumber = KeGetCurrentNodeNumber();
    LOBYTE(v15) = 1;
    return RfspThreadPoolNodeQueueWorkItem(*(_QWORD *)(v13 + 8LL * CurrentNodeNumber + 8), P + 32, v15);
  }
  else
  {
    if ( P[792] )
      ExDeleteResourceLite((PERESOURCE)(P + 688));
    v5 = *((_QWORD *)P + 18);
    if ( v5 )
    {
      Smb2DereferenceSession(v5);
      *((_QWORD *)P + 18) = 0;
      *((_QWORD *)P + 19) = 0;
    }
    if ( P[245] )
      ExReleaseRundownProtection((PEX_RUNDOWN_REF)(**((_QWORD **)P + 16) + 304LL));
    v6 = (volatile signed __int64 **)*((_QWORD *)P + 16);
    if ( v6 )
    {
      v5 = _InterlockedDecrement64(*v6);
      if ( v5 == -1 )
      {
        __int2c();
      }
      else if ( !v5 )
      {
        Smb2FreeShare((char *)v6);
      }
      *((_QWORD *)P + 16) = 0;
      *((_QWORD *)P + 17) = 0;
    }
    v7 = *((_QWORD *)P + 20);
    if ( v7 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v7 + 148));
      v8 = *((_QWORD *)P + 20);
      v9 = _InterlockedDecrement64((volatile signed __int64 *)v8);
      if ( v9 == -1 )
      {
        __int2c();
      }
      else if ( !v9 )
      {
        if ( (byte_14004C339 & 1) != 0 )
        {
          v23 = *(_QWORD *)(v8 + 112);
          if ( v23 )
            v24 = (__int64 *)(v23 + 72);
          else
            v24 = &Srv2ZeroGuid;
          McTemplateK0jj_EtwWriteTransfer(v5, (unsigned int)SMB2_EVENT_TREECONNECT_TERMINATE, a3, v8 + 24, (__int64)v24);
        }
        v16 = *(_QWORD *)(v8 + 112);
        if ( v16 )
          Smb2DereferenceSession(v16);
        v17 = *(volatile signed __int64 ***)(v8 + 96);
        if ( v17 )
        {
          ExAcquireResourceExclusiveLite((PERESOURCE)(*v17 + 12), 1u);
          v12 = (*((_DWORD *)v17 + 50))-- == 1;
          if ( v12 )
          {
            v18 = v17[40];
            v25 = (struct _ERESOURCE *)(*v17 + 25);
            v20 = v17[39];
            v19 = v17[41];
            v17[40] = 0;
            v17[39] = 0;
            v17[41] = 0;
            ExAcquireResourceExclusiveLite(v25, 1u);
            v26 = (struct _ERESOURCE *)(*v17 + 25);
            *((_DWORD *)v17 + 88) = 0;
            ExReleaseResourceLite(v26);
          }
          else
          {
            v18 = 0;
            v19 = 0;
            v20 = 0;
          }
          ExReleaseResourceLite((PERESOURCE)(*v17 + 12));
          v21 = _InterlockedDecrement64(*v17);
          if ( v21 == -1 )
          {
            __int2c();
          }
          else if ( !v21 )
          {
            Smb2FreeShare((char *)v17);
          }
          if ( v18 )
            Smb2DereferenceHandle((PVOID)v18);
          if ( v20 )
            Smb2DereferenceHandle((PVOID)v20);
          if ( v19 )
            Smb2DereferenceHandle((PVOID)v19);
        }
        v22 = *(_QWORD *)(v8 + 120);
        if ( v22 )
          Smb2DereferenceSecurityContext(v22);
        ExFreePoolWithTag((PVOID)v8, 0);
      }
      *((_QWORD *)P + 20) = 0;
    }
    v10 = (_QWORD *)*((_QWORD *)P + 51);
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10, 0xFFFFFFFF) == 1 )
      {
        SrvNetFreePool(v10[1]);
        ExFreePoolWithTag(v10, 0);
      }
      *((_QWORD *)P + 51) = 0;
    }
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      v30 = 0;
      *(_OWORD *)BackTrace = 0;
      RtlCaptureStackBackTrace(1u, 3u, BackTrace, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqq(WPP_GLOBAL_Control->AttachedDevice, v27, v28, P, BackTrace[0], BackTrace[1], v30);
      }
    }
    ExFreePoolWithTag(P, 0);
    result = Srv2Statistics;
    _InterlockedDecrement((volatile signed __int32 *)(Srv2Statistics + 72));
  }
  return result;
}

```

## disassembly

```asm
0x1400809c0  push    rbx
0x1400809c2  push    rdi
0x1400809c3  sub     rsp, 88h
0x1400809ca  mov     rax, cs:__security_cookie
0x1400809d1  xor     rax, rsp
0x1400809d4  mov     [rsp+98h+var_38], rax
0x1400809d9  test    cs:byte_14004C339, 8
0x1400809e0  mov     rbx, rcx
0x1400809e3  jnz     loc_140080CD3
0x1400809e9  mov     rdx, [rbx+140h]
0x1400809f0  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1400809f7  cmp     rdx, rdi
0x1400809fa  jz      short loc_140080A1D
0x1400809fc  mov     rax, [rbx+40h]
0x140080a00  mov     ecx, cs:Smb2ProviderId
0x140080a06  movzx   r8d, byte ptr [rax]
0x140080a0a  call    cs:__imp_SrvAdminDeregisterFile
0x140080a11  nop     dword ptr [rax+rax+00h]
0x140080a16  mov     [rbx+140h], rdi
0x140080a1d  cmp     byte ptr [rbx+0E8h], 0
0x140080a24  jnz     loc_140080B75
0x140080a2a  cmp     byte ptr [rbx+318h], 0
0x140080a31  mov     [rsp+98h+arg_10], rsi
0x140080a39  mov     [rsp+98h+var_18], r13
0x140080a41  jz      short loc_140080A56
0x140080a43  lea     rcx, [rbx+2B0h]; Resource
0x140080a4a  call    cs:__imp_ExDeleteResourceLite
0x140080a51  nop     dword ptr [rax+rax+00h]
0x140080a56  mov     rcx, [rbx+90h]
0x140080a5d  xor     r13d, r13d
0x140080a60  test    rcx, rcx
0x140080a63  jz      short loc_140080A78
0x140080a65  call    Smb2DereferenceSession
0x140080a6a  mov     [rbx+90h], r13
0x140080a71  mov     [rbx+98h], r13
0x140080a78  cmp     [rbx+0F5h], r13b
0x140080a7f  jnz     loc_140080CE8
0x140080a85  mov     rdx, [rbx+80h]
0x140080a8c  test    rdx, rdx
0x140080a8f  jz      short loc_140080ABF
0x140080a91  mov     rax, [rdx]
0x140080a94  mov     rcx, rdi
0x140080a97  lock xadd [rax], rcx
0x140080a9c  dec     rcx
0x140080a9f  cmp     rcx, rdi
0x140080aa2  jnb     loc_140080D0A
0x140080aa8  test    rcx, rcx
0x140080aab  jz      loc_140080D11
0x140080ab1  mov     [rbx+80h], r13
0x140080ab8  mov     [rbx+88h], r13
0x140080abf  mov     rax, [rbx+0A0h]
0x140080ac6  test    rax, rax
0x140080ac9  jz      short loc_140080AFD
0x140080acb  lock dec dword ptr [rax+94h]
0x140080ad2  mov     rax, rdi
0x140080ad5  mov     rsi, [rbx+0A0h]
0x140080adc  lock xadd [rsi], rax
0x140080ae1  dec     rax
0x140080ae4  cmp     rax, rdi
0x140080ae7  jnb     loc_140080D1E
0x140080aed  test    rax, rax
0x140080af0  jz      loc_140080BDA
0x140080af6  mov     [rbx+0A0h], r13
0x140080afd  mov     rsi, [rbx+198h]
0x140080b04  test    rsi, rsi
0x140080b07  jz      short loc_140080B1D
0x140080b09  lock xadd [rsi], edi
0x140080b0d  cmp     edi, 1
0x140080b10  jz      loc_140080D80
0x140080b16  mov     [rbx+198h], r13
0x140080b1d  mov     rax, cs:WPP_GLOBAL_Control
0x140080b24  mov     r13, [rsp+98h+var_18]
0x140080b2c  mov     rsi, [rsp+98h+arg_10]
0x140080b34  test    dword ptr [rax+2Ch], 100000h
0x140080b3b  jnz     loc_140098735
0x140080b41  xor     edx, edx; Tag
0x140080b43  mov     rcx, rbx; P
0x140080b46  call    cs:__imp_ExFreePoolWithTag
0x140080b4d  nop     dword ptr [rax+rax+00h]
0x140080b52  mov     rax, cs:Srv2Statistics
0x140080b59  lock dec dword ptr [rax+48h]
0x140080b5d  mov     rcx, [rsp+98h+var_38]
0x140080b62  xor     rcx, rsp; StackCookie
0x140080b65  call    __security_check_cookie
0x140080b6a  add     rsp, 88h
0x140080b71  pop     rdi
0x140080b72  pop     rbx
0x140080b73  retn
0x140080b75  cmp     dword ptr [rbx+8], 5
0x140080b79  lea     rax, Smb2ScheduleFileAndFree
0x140080b80  mov     [rbx+30h], rax
0x140080b84  mov     dword ptr [rbx+48h], 2
0x140080b8b  jnz     short loc_140080BAD
0x140080b8d  lea     rcx, [rbx+248h]
0x140080b94  mov     byte ptr [rsp+98h+var_78], 1
0x140080b99  lea     r9, SourceString; "Srv2PostToThreadPool"
0x140080ba0  mov     r8d, 187h
0x140080ba6  mov     dl, 1
0x140080ba8  call    SRV2_PERF_ENTER_EX
0x140080bad  mov     rax, [rbx+40h]
0x140080bb1  mov     rdi, [rax+98h]
0x140080bb8  call    cs:__imp_KeGetCurrentNodeNumber
0x140080bbf  nop     dword ptr [rax+rax+00h]
0x140080bc4  movzx   ecx, ax
0x140080bc7  mov     r8b, 1
0x140080bca  lea     rdx, [rbx+20h]
0x140080bce  mov     rcx, [rdi+rcx*8+8]
0x140080bd3  call    RfspThreadPoolNodeQueueWorkItem
0x140080bd8  jmp     short loc_140080B5D
0x140080bda  test    cs:byte_14004C339, 1
0x140080be1  mov     [rsp+98h+var_20], r14
0x140080be6  jnz     loc_140080D25
0x140080bec  mov     rcx, [rsi+70h]
0x140080bf0  test    rcx, rcx
0x140080bf3  jz      short loc_140080BFA
0x140080bf5  call    Smb2DereferenceSession
0x140080bfa  mov     r14, [rsi+60h]
0x140080bfe  test    r14, r14
0x140080c01  jz      loc_140080CAB
0x140080c07  mov     rcx, [r14]
0x140080c0a  mov     dl, 1; Wait
0x140080c0c  mov     [rsp+98h+arg_8], rbp
0x140080c14  add     rcx, 60h ; '`'; Resource
0x140080c18  mov     [rsp+98h+arg_18], r12
0x140080c20  mov     [rsp+98h+var_28], r15
0x140080c25  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140080c2c  nop     dword ptr [rax+rax+00h]
0x140080c31  add     dword ptr [r14+0C8h], 0FFFFFFFFh
0x140080c39  jz      loc_1400986D0
0x140080c3f  mov     r12, r13
0x140080c42  mov     rbp, r13
0x140080c45  mov     r15, r13
0x140080c48  mov     rcx, [r14]
0x140080c4b  add     rcx, 60h ; '`'; Resource
0x140080c4f  call    cs:__imp_ExReleaseResourceLite
0x140080c56  nop     dword ptr [rax+rax+00h]
0x140080c5b  mov     rax, [r14]
0x140080c5e  mov     rcx, rdi
0x140080c61  lock xadd [rax], rcx
0x140080c66  dec     rcx
0x140080c69  cmp     rcx, rdi
0x140080c6c  jnb     loc_140080D3B
0x140080c72  test    rcx, rcx
0x140080c75  jz      loc_140080D42
0x140080c7b  test    r12, r12
0x140080c7e  jnz     loc_140080D4F
0x140080c84  mov     r12, [rsp+98h+arg_18]
0x140080c8c  test    r15, r15
0x140080c8f  jnz     loc_140080D5C
0x140080c95  mov     r15, [rsp+98h+var_28]
0x140080c9a  test    rbp, rbp
0x140080c9d  jnz     loc_140080D69
0x140080ca3  mov     rbp, [rsp+98h+arg_8]
0x140080cab  mov     rcx, [rsi+78h]
0x140080caf  mov     r14, [rsp+98h+var_20]
0x140080cb4  test    rcx, rcx
0x140080cb7  jnz     loc_140080D76
0x140080cbd  xor     edx, edx; Tag
0x140080cbf  mov     rcx, rsi; P
0x140080cc2  call    cs:__imp_ExFreePoolWithTag
0x140080cc9  nop     dword ptr [rax+rax+00h]
0x140080cce  jmp     loc_140080AF6
0x140080cd3  lea     r9, [rcx+60h]
0x140080cd7  lea     rdx, SMB2_EVENT_FILE_TERMINATE
0x140080cde  call    McTemplateK0j_EtwWriteTransfer
0x140080ce3  jmp     loc_1400809E9
0x140080ce8  mov     rax, [rbx+80h]
0x140080cef  mov     rcx, [rax]
0x140080cf2  add     rcx, 130h; RunRef
0x140080cf9  call    cs:__imp_ExReleaseRundownProtection
0x140080d00  nop     dword ptr [rax+rax+00h]
0x140080d05  jmp     loc_140080A85
0x140080d0a  int     2Ch; Windows NT - assertion failure
0x140080d0c  jmp     loc_140080AB1
0x140080d11  mov     rcx, rdx; P
0x140080d14  call    Smb2FreeShare
0x140080d19  jmp     loc_140080AB1
0x140080d1e  int     2Ch; Windows NT - assertion failure
0x140080d20  jmp     loc_140080AF6
0x140080d25  mov     rax, [rsi+70h]
0x140080d29  test    rax, rax
0x140080d2c  jz      loc_1400986AE
0x140080d32  add     rax, 48h ; 'H'
0x140080d36  jmp     loc_1400986B5
0x140080d3b  int     2Ch; Windows NT - assertion failure
0x140080d3d  jmp     loc_140080C7B
0x140080d42  mov     rcx, r14; P
0x140080d45  call    Smb2FreeShare
0x140080d4a  jmp     loc_140080C7B
0x140080d4f  mov     rcx, r12; P
0x140080d52  call    Smb2DereferenceHandle
0x140080d57  jmp     loc_140080C84
0x140080d5c  mov     rcx, r15; P
0x140080d5f  call    Smb2DereferenceHandle
0x140080d64  jmp     loc_140080C95
0x140080d69  mov     rcx, rbp; P
0x140080d6c  call    Smb2DereferenceHandle
0x140080d71  jmp     loc_140080CA3
0x140080d76  call    Smb2DereferenceSecurityContext
0x140080d7b  jmp     loc_140080CBD
0x140080d80  mov     rcx, [rsi+8]
0x140080d84  call    cs:__imp_SrvNetFreePool
0x140080d8b  nop     dword ptr [rax+rax+00h]
0x140080d90  xor     edx, edx; Tag
0x140080d92  mov     rcx, rsi; P
0x140080d95  call    cs:__imp_ExFreePoolWithTag
0x140080d9c  nop     dword ptr [rax+rax+00h]
0x140080da1  jmp     loc_140080B16
0x1400986ae  lea     rax, Srv2ZeroGuid
0x1400986b5  lea     r9, [rsi+18h]
0x1400986b9  mov     [rsp+98h+var_78], rax
0x1400986be  lea     rdx, SMB2_EVENT_TREECONNECT_TERMINATE
0x1400986c5  call    McTemplateK0jj_EtwWriteTransfer
0x1400986ca  nop
0x1400986cb  jmp     loc_140080BEC
0x1400986d0  mov     rcx, [r14]
0x1400986d3  mov     dl, 1; Wait
0x1400986d5  mov     r12, [r14+140h]
0x1400986dc  add     rcx, 0C8h; Resource
0x1400986e3  mov     r15, [r14+138h]
0x1400986ea  mov     rbp, [r14+148h]
0x1400986f1  mov     [r14+140h], r13
0x1400986f8  mov     [r14+138h], r13
0x1400986ff  mov     [r14+148h], r13
0x140098706  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14009870d  nop     dword ptr [rax+rax+00h]
0x140098712  mov     rcx, [r14]
0x140098715  add     rcx, 0C8h; Resource
0x14009871c  mov     [r14+160h], r13d
0x140098723  call    cs:__imp_ExReleaseResourceLite
0x14009872a  nop     dword ptr [rax+rax+00h]
0x14009872f  nop
0x140098730  jmp     loc_140080C48
0x140098735  xorps   xmm0, xmm0
0x140098738  lea     r8, [rsp+98h+BackTrace]; BackTrace
0x14009873d  xor     eax, eax
0x14009873f  xor     r9d, r9d; BackTraceHash
0x140098742  mov     edx, 3; FramesToCapture
0x140098747  mov     [rsp+98h+var_40], rax
0x14009874c  mov     ecx, 1; FramesToSkip
0x140098751  movups  xmmword ptr [rsp+98h+BackTrace], xmm0
0x140098756  call    cs:__imp_RtlCaptureStackBackTrace
0x14009875d  nop     dword ptr [rax+rax+00h]
0x140098762  mov     rcx, cs:WPP_GLOBAL_Control
0x140098769  lea     rax, WPP_GLOBAL_Control
0x140098770  cmp     rcx, rax
0x140098773  jz      loc_140080B41
0x140098779  test    dword ptr [rcx+2Ch], 100000h
0x140098780  jz      loc_140080B41
0x140098786  cmp     byte ptr [rcx+29h], 2
0x14009878a  jb      loc_140080B41
0x140098790  mov     rax, [rsp+98h+var_40]
0x140098795  mov     r9, rbx
0x140098798  mov     rcx, [rcx+18h]
0x14009879c  mov     [rsp+98h+var_68], rax
0x1400987a1  mov     rax, [rsp+98h+BackTrace+8]
0x1400987a6  mov     [rsp+98h+var_70], rax
0x1400987ab  mov     rax, [rsp+98h+BackTrace]
0x1400987b0  mov     [rsp+98h+var_78], rax
0x1400987b5  call    WPP_SF_qqqq
0x1400987ba  nop
0x1400987bb  jmp     loc_140080B41
```
