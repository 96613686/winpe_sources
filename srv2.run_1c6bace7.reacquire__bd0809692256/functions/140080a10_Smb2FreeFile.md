# Smb2FreeFile

- ea: `0x140080a10`
- end: `0x140080df6`
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
- `0x14007a89c`

## callees

- `0x140004df4`
- `0x140005070`
- `0x140012c30`
- `0x140013810`
- `0x140013920`
- `0x14002a410`
- `0x14002b49c`
- `0x140038490`
- `0x140063bf4`
- `0x140077390`
- `0x140080a10`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140080a9a`
- `ntoskrnl!ExDeleteResourceLite` at `0x140080a9a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140080c9f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098773`
- `ntoskrnl!ExReleaseResourceLite` at `0x140080c9f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098773`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140080c75`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140098756`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140080c75`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140098756`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140080c08`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140080c08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080b96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080d12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080de5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080b96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080d12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080de5`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400987a6`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400987a6`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140080d49`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140080d49`
- `srvnet!SrvNetFreePool` at `0x140080dd4`
- `srvnet!SrvNetFreePool` at `0x140080dd4`
- `srvnet!SrvAdminDeregisterFile` at `0x140080a5a`
- `srvnet!SrvAdminDeregisterFile` at `0x140080a5a`

## string_xrefs

- `0x140080be9`: `Srv2PostToThreadPool`

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
0x140080a10  push    rbx
0x140080a12  push    rdi
0x140080a13  sub     rsp, 88h
0x140080a1a  mov     rax, cs:__security_cookie
0x140080a21  xor     rax, rsp
0x140080a24  mov     [rsp+98h+var_38], rax
0x140080a29  test    cs:byte_14004C339, 8
0x140080a30  mov     rbx, rcx
0x140080a33  jnz     loc_140080D23
0x140080a39  mov     rdx, [rbx+140h]
0x140080a40  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x140080a47  cmp     rdx, rdi
0x140080a4a  jz      short loc_140080A6D
0x140080a4c  mov     rax, [rbx+40h]
0x140080a50  mov     ecx, cs:Smb2ProviderId
0x140080a56  movzx   r8d, byte ptr [rax]
0x140080a5a  call    cs:__imp_SrvAdminDeregisterFile
0x140080a61  nop     dword ptr [rax+rax+00h]
0x140080a66  mov     [rbx+140h], rdi
0x140080a6d  cmp     byte ptr [rbx+0E8h], 0
0x140080a74  jnz     loc_140080BC5
0x140080a7a  cmp     byte ptr [rbx+318h], 0
0x140080a81  mov     [rsp+98h+arg_10], rsi
0x140080a89  mov     [rsp+98h+var_18], r13
0x140080a91  jz      short loc_140080AA6
0x140080a93  lea     rcx, [rbx+2B0h]; Resource
0x140080a9a  call    cs:__imp_ExDeleteResourceLite
0x140080aa1  nop     dword ptr [rax+rax+00h]
0x140080aa6  mov     rcx, [rbx+90h]
0x140080aad  xor     r13d, r13d
0x140080ab0  test    rcx, rcx
0x140080ab3  jz      short loc_140080AC8
0x140080ab5  call    Smb2DereferenceSession
0x140080aba  mov     [rbx+90h], r13
0x140080ac1  mov     [rbx+98h], r13
0x140080ac8  cmp     [rbx+0F5h], r13b
0x140080acf  jnz     loc_140080D38
0x140080ad5  mov     rdx, [rbx+80h]
0x140080adc  test    rdx, rdx
0x140080adf  jz      short loc_140080B0F
0x140080ae1  mov     rax, [rdx]
0x140080ae4  mov     rcx, rdi
0x140080ae7  lock xadd [rax], rcx
0x140080aec  dec     rcx
0x140080aef  cmp     rcx, rdi
0x140080af2  jnb     loc_140080D5A
0x140080af8  test    rcx, rcx
0x140080afb  jz      loc_140080D61
0x140080b01  mov     [rbx+80h], r13
0x140080b08  mov     [rbx+88h], r13
0x140080b0f  mov     rax, [rbx+0A0h]
0x140080b16  test    rax, rax
0x140080b19  jz      short loc_140080B4D
0x140080b1b  lock dec dword ptr [rax+94h]
0x140080b22  mov     rax, rdi
0x140080b25  mov     rsi, [rbx+0A0h]
0x140080b2c  lock xadd [rsi], rax
0x140080b31  dec     rax
0x140080b34  cmp     rax, rdi
0x140080b37  jnb     loc_140080D6E
0x140080b3d  test    rax, rax
0x140080b40  jz      loc_140080C2A
0x140080b46  mov     [rbx+0A0h], r13
0x140080b4d  mov     rsi, [rbx+198h]
0x140080b54  test    rsi, rsi
0x140080b57  jz      short loc_140080B6D
0x140080b59  lock xadd [rsi], edi
0x140080b5d  cmp     edi, 1
0x140080b60  jz      loc_140080DD0
0x140080b66  mov     [rbx+198h], r13
0x140080b6d  mov     rax, cs:WPP_GLOBAL_Control
0x140080b74  mov     r13, [rsp+98h+var_18]
0x140080b7c  mov     rsi, [rsp+98h+arg_10]
0x140080b84  test    dword ptr [rax+2Ch], 100000h
0x140080b8b  jnz     loc_140098785
0x140080b91  xor     edx, edx; Tag
0x140080b93  mov     rcx, rbx; P
0x140080b96  call    cs:__imp_ExFreePoolWithTag
0x140080b9d  nop     dword ptr [rax+rax+00h]
0x140080ba2  mov     rax, cs:Srv2Statistics
0x140080ba9  lock dec dword ptr [rax+48h]
0x140080bad  mov     rcx, [rsp+98h+var_38]
0x140080bb2  xor     rcx, rsp; StackCookie
0x140080bb5  call    __security_check_cookie
0x140080bba  add     rsp, 88h
0x140080bc1  pop     rdi
0x140080bc2  pop     rbx
0x140080bc3  retn
0x140080bc5  cmp     dword ptr [rbx+8], 5
0x140080bc9  lea     rax, Smb2ScheduleFileAndFree
0x140080bd0  mov     [rbx+30h], rax
0x140080bd4  mov     dword ptr [rbx+48h], 2
0x140080bdb  jnz     short loc_140080BFD
0x140080bdd  lea     rcx, [rbx+248h]
0x140080be4  mov     byte ptr [rsp+98h+var_78], 1
0x140080be9  lea     r9, SourceString; "Srv2PostToThreadPool"
0x140080bf0  mov     r8d, 187h
0x140080bf6  mov     dl, 1
0x140080bf8  call    SRV2_PERF_ENTER_EX
0x140080bfd  mov     rax, [rbx+40h]
0x140080c01  mov     rdi, [rax+98h]
0x140080c08  call    cs:__imp_KeGetCurrentNodeNumber
0x140080c0f  nop     dword ptr [rax+rax+00h]
0x140080c14  movzx   ecx, ax
0x140080c17  mov     r8b, 1
0x140080c1a  lea     rdx, [rbx+20h]
0x140080c1e  mov     rcx, [rdi+rcx*8+8]
0x140080c23  call    RfspThreadPoolNodeQueueWorkItem
0x140080c28  jmp     short loc_140080BAD
0x140080c2a  test    cs:byte_14004C339, 1
0x140080c31  mov     [rsp+98h+var_20], r14
0x140080c36  jnz     loc_140080D75
0x140080c3c  mov     rcx, [rsi+70h]
0x140080c40  test    rcx, rcx
0x140080c43  jz      short loc_140080C4A
0x140080c45  call    Smb2DereferenceSession
0x140080c4a  mov     r14, [rsi+60h]
0x140080c4e  test    r14, r14
0x140080c51  jz      loc_140080CFB
0x140080c57  mov     rcx, [r14]
0x140080c5a  mov     dl, 1; Wait
0x140080c5c  mov     [rsp+98h+arg_8], rbp
0x140080c64  add     rcx, 60h ; '`'; Resource
0x140080c68  mov     [rsp+98h+arg_18], r12
0x140080c70  mov     [rsp+98h+var_28], r15
0x140080c75  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140080c7c  nop     dword ptr [rax+rax+00h]
0x140080c81  add     dword ptr [r14+0C8h], 0FFFFFFFFh
0x140080c89  jz      loc_140098720
0x140080c8f  mov     r12, r13
0x140080c92  mov     rbp, r13
0x140080c95  mov     r15, r13
0x140080c98  mov     rcx, [r14]
0x140080c9b  add     rcx, 60h ; '`'; Resource
0x140080c9f  call    cs:__imp_ExReleaseResourceLite
0x140080ca6  nop     dword ptr [rax+rax+00h]
0x140080cab  mov     rax, [r14]
0x140080cae  mov     rcx, rdi
0x140080cb1  lock xadd [rax], rcx
0x140080cb6  dec     rcx
0x140080cb9  cmp     rcx, rdi
0x140080cbc  jnb     loc_140080D8B
0x140080cc2  test    rcx, rcx
0x140080cc5  jz      loc_140080D92
0x140080ccb  test    r12, r12
0x140080cce  jnz     loc_140080D9F
0x140080cd4  mov     r12, [rsp+98h+arg_18]
0x140080cdc  test    r15, r15
0x140080cdf  jnz     loc_140080DAC
0x140080ce5  mov     r15, [rsp+98h+var_28]
0x140080cea  test    rbp, rbp
0x140080ced  jnz     loc_140080DB9
0x140080cf3  mov     rbp, [rsp+98h+arg_8]
0x140080cfb  mov     rcx, [rsi+78h]
0x140080cff  mov     r14, [rsp+98h+var_20]
0x140080d04  test    rcx, rcx
0x140080d07  jnz     loc_140080DC6
0x140080d0d  xor     edx, edx; Tag
0x140080d0f  mov     rcx, rsi; P
0x140080d12  call    cs:__imp_ExFreePoolWithTag
0x140080d19  nop     dword ptr [rax+rax+00h]
0x140080d1e  jmp     loc_140080B46
0x140080d23  lea     r9, [rcx+60h]
0x140080d27  lea     rdx, SMB2_EVENT_FILE_TERMINATE
0x140080d2e  call    McTemplateK0j_EtwWriteTransfer
0x140080d33  jmp     loc_140080A39
0x140080d38  mov     rax, [rbx+80h]
0x140080d3f  mov     rcx, [rax]
0x140080d42  add     rcx, 130h; RunRef
0x140080d49  call    cs:__imp_ExReleaseRundownProtection
0x140080d50  nop     dword ptr [rax+rax+00h]
0x140080d55  jmp     loc_140080AD5
0x140080d5a  int     2Ch; Windows NT - assertion failure
0x140080d5c  jmp     loc_140080B01
0x140080d61  mov     rcx, rdx; P
0x140080d64  call    Smb2FreeShare
0x140080d69  jmp     loc_140080B01
0x140080d6e  int     2Ch; Windows NT - assertion failure
0x140080d70  jmp     loc_140080B46
0x140080d75  mov     rax, [rsi+70h]
0x140080d79  test    rax, rax
0x140080d7c  jz      loc_1400986FE
0x140080d82  add     rax, 48h ; 'H'
0x140080d86  jmp     loc_140098705
0x140080d8b  int     2Ch; Windows NT - assertion failure
0x140080d8d  jmp     loc_140080CCB
0x140080d92  mov     rcx, r14; P
0x140080d95  call    Smb2FreeShare
0x140080d9a  jmp     loc_140080CCB
0x140080d9f  mov     rcx, r12; P
0x140080da2  call    Smb2DereferenceHandle
0x140080da7  jmp     loc_140080CD4
0x140080dac  mov     rcx, r15; P
0x140080daf  call    Smb2DereferenceHandle
0x140080db4  jmp     loc_140080CE5
0x140080db9  mov     rcx, rbp; P
0x140080dbc  call    Smb2DereferenceHandle
0x140080dc1  jmp     loc_140080CF3
0x140080dc6  call    Smb2DereferenceSecurityContext
0x140080dcb  jmp     loc_140080D0D
0x140080dd0  mov     rcx, [rsi+8]
0x140080dd4  call    cs:__imp_SrvNetFreePool
0x140080ddb  nop     dword ptr [rax+rax+00h]
0x140080de0  xor     edx, edx; Tag
0x140080de2  mov     rcx, rsi; P
0x140080de5  call    cs:__imp_ExFreePoolWithTag
0x140080dec  nop     dword ptr [rax+rax+00h]
0x140080df1  jmp     loc_140080B66
0x1400986fe  lea     rax, Srv2ZeroGuid
0x140098705  lea     r9, [rsi+18h]
0x140098709  mov     [rsp+98h+var_78], rax
0x14009870e  lea     rdx, SMB2_EVENT_TREECONNECT_TERMINATE
0x140098715  call    McTemplateK0jj_EtwWriteTransfer
0x14009871a  nop
0x14009871b  jmp     loc_140080C3C
0x140098720  mov     rcx, [r14]
0x140098723  mov     dl, 1; Wait
0x140098725  mov     r12, [r14+140h]
0x14009872c  add     rcx, 0C8h; Resource
0x140098733  mov     r15, [r14+138h]
0x14009873a  mov     rbp, [r14+148h]
0x140098741  mov     [r14+140h], r13
0x140098748  mov     [r14+138h], r13
0x14009874f  mov     [r14+148h], r13
0x140098756  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14009875d  nop     dword ptr [rax+rax+00h]
0x140098762  mov     rcx, [r14]
0x140098765  add     rcx, 0C8h; Resource
0x14009876c  mov     [r14+160h], r13d
0x140098773  call    cs:__imp_ExReleaseResourceLite
0x14009877a  nop     dword ptr [rax+rax+00h]
0x14009877f  nop
0x140098780  jmp     loc_140080C98
0x140098785  xorps   xmm0, xmm0
0x140098788  lea     r8, [rsp+98h+BackTrace]; BackTrace
0x14009878d  xor     eax, eax
0x14009878f  xor     r9d, r9d; BackTraceHash
0x140098792  mov     edx, 3; FramesToCapture
0x140098797  mov     [rsp+98h+var_40], rax
0x14009879c  mov     ecx, 1; FramesToSkip
0x1400987a1  movups  xmmword ptr [rsp+98h+BackTrace], xmm0
0x1400987a6  call    cs:__imp_RtlCaptureStackBackTrace
0x1400987ad  nop     dword ptr [rax+rax+00h]
0x1400987b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400987b9  lea     rax, WPP_GLOBAL_Control
0x1400987c0  cmp     rcx, rax
0x1400987c3  jz      loc_140080B91
0x1400987c9  test    dword ptr [rcx+2Ch], 100000h
0x1400987d0  jz      loc_140080B91
0x1400987d6  cmp     byte ptr [rcx+29h], 2
0x1400987da  jb      loc_140080B91
0x1400987e0  mov     rax, [rsp+98h+var_40]
0x1400987e5  mov     r9, rbx
0x1400987e8  mov     rcx, [rcx+18h]
0x1400987ec  mov     [rsp+98h+var_68], rax
0x1400987f1  mov     rax, [rsp+98h+BackTrace+8]
0x1400987f6  mov     [rsp+98h+var_70], rax
0x1400987fb  mov     rax, [rsp+98h+BackTrace]
0x140098800  mov     [rsp+98h+var_78], rax
0x140098805  call    WPP_SF_qqqq
0x14009880a  nop
0x14009880b  jmp     loc_140080B91
```
