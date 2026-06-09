# MpDlpSetEaOnDestination

- ea: `0x140032be0`
- end: `0x14003308c`
- name: `MpDlpSetEaOnDestination`
- size: `1196`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x140030380`

## callees

- `0x1400051bc`
- `0x140005c30`
- `0x14000e704`
- `0x1400118d0`
- `0x140032be0`
- `0x140033090`
- `0x140033318`
- `0x1400510e4`
- `0x140054230`
- `0x140066180`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140032cf3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140032cf3`
- `FLTMGR!FltReleaseContext` at `0x140033063`
- `FLTMGR!FltReleaseContext` at `0x14008c872`
- `FLTMGR!FltReleaseContext` at `0x140033063`
- `FLTMGR!FltReleaseContext` at `0x14008c872`
- `FLTMGR!FltReleasePushLock` at `0x140032db1`
- `FLTMGR!FltReleasePushLock` at `0x140032db1`
- `FLTMGR!FltGetStreamHandleContext` at `0x140032e52`
- `FLTMGR!FltGetStreamHandleContext` at `0x140032f71`
- `FLTMGR!FltGetStreamHandleContext` at `0x140032e52`
- `FLTMGR!FltGetStreamHandleContext` at `0x140032f71`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x140032d2b`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x140032d2b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003307e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14008c832`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003307e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14008c832`

## pseudocode

```c
void __fastcall MpDlpSetEaOnDestination(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        PFLT_CONTEXT a4,
        UNICODE_STRING *a5,
        char a6,
        char a7)
{
  __int64 v9; // r12
  __int64 v10; // r13
  UNICODE_STRING *v11; // r8
  unsigned __int64 v12; // rsi
  NTSTATUS StreamHandleContext; // edx
  UNICODE_STRING *v14; // r14
  struct _FLT_FILE_NAME_INFORMATION *v15; // rdi
  int v16; // ecx
  char v17; // r12
  HANDLE CurrentThreadId; // rbx
  __int64 v19; // rdx
  __int64 v20; // r8
  unsigned __int64 v21; // r13
  unsigned int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // r9
  __int64 v25; // rcx
  int v26; // eax
  UNICODE_STRING *p_Name; // rdx
  int v28; // edx
  int v29; // r8d
  __int64 v31; // [rsp+58h] [rbp-90h]
  __int64 v32; // [rsp+68h] [rbp-80h]
  PFLT_CONTEXT Context; // [rsp+98h] [rbp-50h] BYREF

  v9 = a2;
  v10 = a1;
  v11 = a5;
  v12 = 0;
  StreamHandleContext = 0;
  v14 = 0;
  v15 = 0;
  Context = a4;
  if ( *(_QWORD *)(MpData + 184) && *(_QWORD *)(MpData + 104) )
    v16 = *(_DWORD *)(MpData + 4132);
  else
    LOBYTE(v16) = 0;
  if ( (v16 & 1) != 0 )
  {
    if ( !a4 )
    {
      StreamHandleContext = FltGetStreamHandleContext(*(PFLT_INSTANCE *)(v9 + 24), *(PFILE_OBJECT *)(v9 + 32), &Context);
      v11 = a5;
    }
    if ( StreamHandleContext >= 0 )
    {
      if ( Context )
      {
        if ( (*((_DWORD *)Context + 10) & 0x1000) != 0 )
        {
          v15 = (struct _FLT_FILE_NAME_INFORMATION *)_InterlockedExchange64((volatile __int64 *)Context + 14, 0);
          if ( v15 )
          {
            _InterlockedOr((volatile signed __int32 *)Context + 10, 0x400u);
            p_Name = &v15->Name;
            goto LABEL_58;
          }
        }
      }
    }
  }
  if ( a7 )
  {
    if ( !a6 || !v11 || !v11->Length )
      goto LABEL_60;
    goto LABEL_36;
  }
  if ( !*a3 && (int)MpQueryNetworkOpenInformation(v9, a3) < 0 )
    goto LABEL_60;
  v17 = 0;
  if ( !v10 )
    goto LABEL_34;
  v31 = a3[2];
  v32 = a3[5];
  CurrentThreadId = PsGetCurrentThreadId();
  v14 = 0;
  if ( !*(_QWORD *)(v10 + 264) )
    goto LABEL_60;
  FltAcquirePushLockExclusive((PULONG_PTR)(v10 + 272));
  v20 = *(_QWORD *)(v10 + 264);
  if ( !v20 )
    goto LABEL_24;
  v21 = 0;
  v22 = dword_1400269EC;
  while ( 1 )
  {
    v23 = v22--;
    if ( !(_DWORD)v23 )
      break;
    v24 = v20 + 56LL * v22;
    v19 = v20;
    if ( (*(_BYTE *)v24 & 0xF) != 0xF || *(HANDLE *)(v24 + 8) != CurrentThreadId )
      goto LABEL_21;
    v25 = v20;
    if ( v32 )
    {
      if ( *(_QWORD *)(v24 + 24) == v32 )
      {
        v25 = *(_QWORD *)(a1 + 264);
        goto LABEL_30;
      }
    }
    else
    {
LABEL_30:
      if ( !v31 || (v19 = v25, *(_QWORD *)(v24 + 32) == v31) )
      {
        if ( *(_QWORD *)(v24 + 40) > v12 )
        {
          v12 = *(_QWORD *)(v24 + 40);
          v21 = v20 + 56LL * v22;
        }
LABEL_21:
        v20 = v19;
      }
    }
  }
  v12 = v21;
  if ( v21 )
  {
    if ( !(unsigned __int8)IsThisCallBeingThrottled(v23, v19, v20) )
      MpSendCopyHintTelemetry();
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_qIZ(WPP_GLOBAL_Control->AttachedDevice, v28, v29, v21, *(_QWORD *)(v21 + 24), *(_QWORD *)(v21 + 16));
    v14 = *(UNICODE_STRING **)(v21 + 16);
    v17 = *(_BYTE *)(v21 + 48);
    *(_OWORD *)v21 = 0;
    *(_OWORD *)(v21 + 16) = 0;
    *(_OWORD *)(v21 + 32) = 0;
    *(_QWORD *)(v21 + 48) = 0;
    _InterlockedDecrement(&dword_140026A4C);
    _InterlockedIncrement(&dword_140026A54);
    v10 = a1;
  }
  else
  {
    v10 = a1;
  }
LABEL_24:
  FltReleasePushLock((PULONG_PTR)(v10 + 272));
  if ( v12 )
  {
LABEL_34:
    if ( !v17 )
      goto LABEL_60;
    v9 = a2;
    v11 = a5;
LABEL_36:
    if ( !Context )
    {
      if ( FltGetStreamHandleContext(*(PFLT_INSTANCE *)(v9 + 24), *(PFILE_OBJECT *)(v9 + 32), &Context) < 0 )
      {
        v26 = MpCreateHandleContext(v9, &Context, 0);
        if ( v26 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            188,
            WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
            KeGetCurrentThread(),
            v26);
        }
      }
      v11 = a5;
    }
    if ( !Context )
      goto LABEL_60;
    _InterlockedOr((volatile signed __int32 *)Context + 10, 0x400u);
    if ( v14 )
      v11 = v14;
    p_Name = v11;
LABEL_58:
    MpDlpCopyPolicyToDestination(v9, p_Name);
  }
LABEL_60:
  if ( v15 )
    FltReleaseFileNameInformation(v15);
  if ( v14 )
    MpFreeString(v14);
  if ( Context )
  {
    _InterlockedAnd((volatile signed __int32 *)Context + 10, 0xFFFFFBFF);
    if ( Context != a4 )
      FltReleaseContext(Context);
  }
}

```

## disassembly

```asm
0x140032be0  push    rbx
0x140032be2  push    rsi
0x140032be3  push    rdi
0x140032be4  push    r12
0x140032be6  push    r13
0x140032be8  push    r14
0x140032bea  push    r15
0x140032bec  sub     rsp, 0B0h
0x140032bf3  mov     rax, cs:__security_cookie
0x140032bfa  xor     rax, rsp
0x140032bfd  mov     [rsp+0E8h+var_48], rax
0x140032c05  mov     r15, r9
0x140032c08  mov     rbx, r8
0x140032c0b  mov     r12, rdx
0x140032c0e  mov     [rsp+0E8h+var_60], rdx
0x140032c16  mov     r13, rcx
0x140032c19  mov     [rsp+0E8h+var_A0], rcx
0x140032c1e  mov     r8, [rsp+0E8h+arg_20]
0x140032c26  mov     [rsp+0E8h+var_B0], r8
0x140032c2b  mov     [rsp+0E8h+var_58], r9
0x140032c33  xor     esi, esi
0x140032c35  mov     edx, esi
0x140032c37  mov     r14d, esi
0x140032c3a  mov     [rsp+0E8h+var_98], rsi
0x140032c3f  mov     edi, esi
0x140032c41  mov     [rsp+0E8h+var_88], rsi
0x140032c46  mov     [rsp+0E8h+Context], r9
0x140032c4e  mov     rax, cs:MpData
0x140032c55  cmp     [rax+0B8h], rsi
0x140032c5c  jz      short loc_140032C68
0x140032c5e  cmp     [rax+68h], rsi
0x140032c62  jnz     loc_140032F54
0x140032c68  mov     ecx, esi
0x140032c6a  test    cl, 1
0x140032c6d  jz      short loc_140032C80
0x140032c6f  test    r15, r15
0x140032c72  jz      loc_140032F5F
0x140032c78  test    edx, edx
0x140032c7a  jns     loc_140032F89
0x140032c80  cmp     [rsp+0E8h+arg_30], 0
0x140032c88  jz      short loc_140032CB7
0x140032c8a  cmp     [rsp+0E8h+arg_28], 0
0x140032c92  jz      loc_140033013
0x140032c98  test    r8, r8
0x140032c9b  jz      loc_140033013
0x140032ca1  cmp     si, [r8]
0x140032ca5  jz      loc_140033013
0x140032cab  lea     rbx, WPP_GLOBAL_Control
0x140032cb2  jmp     loc_140032E31
0x140032cb7  cmp     qword ptr [rbx], 0
0x140032cbb  jnz     short loc_140032CD0
0x140032cbd  mov     rdx, rbx
0x140032cc0  mov     rcx, r12
0x140032cc3  call    MpQueryNetworkOpenInformation
0x140032cc8  test    eax, eax
0x140032cca  js      loc_140033013
0x140032cd0  xor     r12b, r12b
0x140032cd3  mov     [rsp+0E8h+var_B8], r12b
0x140032cd8  test    r13, r13
0x140032cdb  jz      loc_140032E14
0x140032ce1  mov     rax, [rbx+10h]
0x140032ce5  mov     [rsp+0E8h+var_90], rax
0x140032cea  mov     rax, [rbx+28h]
0x140032cee  mov     [rsp+0E8h+var_80], rax
0x140032cf3  call    cs:__imp_PsGetCurrentThreadId
0x140032cfa  nop     dword ptr [rax+rax+00h]
0x140032cff  mov     rbx, rax
0x140032d02  mov     [rsp+0E8h+var_68], rsi
0x140032d0a  mov     [rsp+0E8h+var_B8], r12b
0x140032d0f  mov     r14, rsi
0x140032d12  mov     [rsp+0E8h+var_98], rsi
0x140032d17  cmp     [r13+108h], rsi
0x140032d1e  jz      loc_140033013
0x140032d24  lea     rcx, [r13+110h]; PushLock
0x140032d2b  call    cs:__imp_FltAcquirePushLockExclusive
0x140032d32  nop     dword ptr [rax+rax+00h]
0x140032d37  mov     r8, [r13+108h]
0x140032d3e  test    r8, r8
0x140032d41  jz      short loc_140032DA3
0x140032d43  mov     r13, rsi
0x140032d46  mov     [rsp+0E8h+var_70], rsi
0x140032d4b  mov     [rsp+0E8h+var_78], rsi
0x140032d50  mov     eax, cs:dword_1400269EC
0x140032d56  mov     [rsp+0E8h+var_A8], eax
0x140032d5a  mov     r10, [rsp+0E8h+var_A0]
0x140032d5f  mov     r11, [rsp+0E8h+var_80]
0x140032d64  mov     ecx, eax
0x140032d66  dec     eax
0x140032d68  mov     [rsp+0E8h+var_A8], eax
0x140032d6c  test    ecx, ecx
0x140032d6e  jz      short loc_140032D8C
0x140032d70  mov     ecx, eax
0x140032d72  imul    r9, rcx, 38h ; '8'
0x140032d76  add     r9, r8
0x140032d79  mov     rdx, r8
0x140032d7c  mov     ecx, [r9]
0x140032d7f  and     ecx, 0Fh
0x140032d82  cmp     cl, 0Fh
0x140032d85  jz      short loc_140032DC7
0x140032d87  mov     r8, rdx
0x140032d8a  jmp     short loc_140032D64
0x140032d8c  mov     rsi, r13
0x140032d8f  mov     [rsp+0E8h+var_68], r13
0x140032d97  test    r13, r13
0x140032d9a  jnz     loc_140032EE6
0x140032da0  mov     r13, r10
0x140032da3  lea     rbx, WPP_GLOBAL_Control
0x140032daa  lea     rcx, [r13+110h]; PushLock
0x140032db1  call    cs:__imp_FltReleasePushLock
0x140032db8  nop     dword ptr [rax+rax+00h]
0x140032dbd  test    rsi, rsi
0x140032dc0  jnz     short loc_140032E1B
0x140032dc2  jmp     loc_140033013
0x140032dc7  cmp     [r9+8], rbx
0x140032dcb  jnz     short loc_140032D87
0x140032dcd  mov     rcx, r8
0x140032dd0  test    r11, r11
0x140032dd3  jz      short loc_140032DE1
0x140032dd5  cmp     [r9+18h], r11
0x140032dd9  jz      loc_140032FDA
0x140032ddf  jmp     short loc_140032D64
0x140032de1  cmp     [rsp+0E8h+var_90], r14
0x140032de6  jz      short loc_140032DF6
0x140032de8  mov     rdx, rcx
0x140032deb  mov     rcx, [rsp+0E8h+var_90]
0x140032df0  cmp     [r9+20h], rcx
0x140032df4  jnz     short loc_140032DDF
0x140032df6  mov     rcx, [r9+28h]
0x140032dfa  cmp     rcx, rsi
0x140032dfd  jbe     short loc_140032D87
0x140032dff  mov     rsi, rcx
0x140032e02  mov     [rsp+0E8h+var_78], rcx
0x140032e07  mov     r13, r9
0x140032e0a  mov     [rsp+0E8h+var_70], r9
0x140032e0f  jmp     loc_140032D87
0x140032e14  lea     rbx, WPP_GLOBAL_Control
0x140032e1b  test    r12b, r12b
0x140032e1e  jz      loc_140033013
0x140032e24  mov     r12, [rsp+0E8h+var_60]
0x140032e2c  mov     r8, [rsp+0E8h+var_B0]
0x140032e31  cmp     [rsp+0E8h+Context], 0
0x140032e3a  jnz     loc_140032EBE
0x140032e40  lea     r8, [rsp+0E8h+Context]; Context
0x140032e48  mov     rdx, [r12+20h]; FileObject
0x140032e4d  mov     rcx, [r12+18h]; Instance
0x140032e52  call    cs:__imp_FltGetStreamHandleContext
0x140032e59  nop     dword ptr [rax+rax+00h]
0x140032e5e  test    eax, eax
0x140032e60  jns     short loc_140032EB9
0x140032e62  xor     r8d, r8d
0x140032e65  lea     rdx, [rsp+0E8h+Context]
0x140032e6d  mov     rcx, r12
0x140032e70  call    MpCreateHandleContext
0x140032e75  test    eax, eax
0x140032e77  jns     short loc_140032EB9
0x140032e79  mov     rcx, cs:WPP_GLOBAL_Control
0x140032e80  cmp     rcx, rbx
0x140032e83  jz      short loc_140032EB9
0x140032e85  mov     ecx, [rcx+2Ch]
0x140032e88  test    cl, 1
0x140032e8b  jz      short loc_140032EB9
0x140032e8d  lfence
0x140032e90  mov     r9, gs:188h
0x140032e99  mov     edx, 0BCh
0x140032e9e  mov     dword ptr [rsp+0E8h+var_C8], eax
0x140032ea2  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x140032ea9  mov     rcx, cs:WPP_GLOBAL_Control
0x140032eb0  mov     rcx, [rcx+18h]
0x140032eb4  call    WPP_SF_qD
0x140032eb9  mov     r8, [rsp+0E8h+var_B0]
0x140032ebe  mov     rdx, [rsp+0E8h+Context]
0x140032ec6  test    rdx, rdx
0x140032ec9  jz      loc_140033013
0x140032ecf  lock or dword ptr [rdx+28h], 400h
0x140032ed7  test    r14, r14
0x140032eda  cmovnz  r8, r14
0x140032ede  mov     rdx, r8
0x140032ee1  jmp     loc_140032FD0
0x140032ee6  call    IsThisCallBeingThrottled
0x140032eeb  test    al, al
0x140032eed  jz      loc_140032FE6
0x140032ef3  lea     rbx, WPP_GLOBAL_Control
0x140032efa  mov     rcx, cs:WPP_GLOBAL_Control
0x140032f01  cmp     rcx, rbx
0x140032f04  jz      short loc_140032F11
0x140032f06  mov     eax, [rcx+2Ch]
0x140032f09  test    al, 4
0x140032f0b  jnz     loc_140032FF0
0x140032f11  mov     r14, [r13+10h]
0x140032f15  mov     [rsp+0E8h+var_98], r14
0x140032f1a  movzx   r12d, byte ptr [r13+30h]
0x140032f1f  mov     [rsp+0E8h+var_B8], r12b
0x140032f24  xorps   xmm0, xmm0
0x140032f27  xor     eax, eax
0x140032f29  movups  xmmword ptr [r13+0], xmm0
0x140032f2e  movups  xmmword ptr [r13+10h], xmm0
0x140032f33  movups  xmmword ptr [r13+20h], xmm0
0x140032f38  mov     [r13+30h], rax
0x140032f3c  lock dec cs:dword_140026A4C
0x140032f43  lock inc cs:dword_140026A54
0x140032f4a  mov     r13, [rsp+0E8h+var_A0]
0x140032f4f  jmp     loc_140032DAA
0x140032f54  mov     ecx, [rax+1024h]
0x140032f5a  jmp     loc_140032C6A
0x140032f5f  lea     r8, [rsp+0E8h+Context]; Context
0x140032f67  mov     rdx, [r12+20h]; FileObject
0x140032f6c  mov     rcx, [r12+18h]; Instance
0x140032f71  call    cs:__imp_FltGetStreamHandleContext
0x140032f78  nop     dword ptr [rax+rax+00h]
0x140032f7d  mov     edx, eax
0x140032f7f  mov     r8, [rsp+0E8h+var_B0]
0x140032f84  jmp     loc_140032C78
0x140032f89  mov     rdx, [rsp+0E8h+Context]
0x140032f91  test    rdx, rdx
0x140032f94  jz      loc_140032C80
0x140032f9a  test    dword ptr [rdx+28h], 1000h
0x140032fa1  jz      loc_140032C80
0x140032fa7  mov     rdi, rsi
0x140032faa  xchg    rdi, [rdx+70h]
0x140032fae  mov     [rsp+0E8h+var_88], rdi
0x140032fb3  test    rdi, rdi
0x140032fb6  jz      loc_140032C80
0x140032fbc  mov     rax, [rsp+0E8h+Context]
0x140032fc4  lock or dword ptr [rax+28h], 400h
0x140032fcc  lea     rdx, [rdi+8]
0x140032fd0  mov     rcx, r12
0x140032fd3  call    MpDlpCopyPolicyToDestination
0x140032fd8  jmp     short loc_140033013
0x140032fda  mov     rcx, [r10+108h]
0x140032fe1  jmp     loc_140032DE1
0x140032fe6  call    MpSendCopyHintTelemetry
0x140032feb  jmp     loc_140032EF3
0x140032ff0  mov     rax, [r13+10h]
0x140032ff4  mov     [rsp+0E8h+var_C0], rax
0x140032ff9  mov     rax, [r13+18h]
0x140032ffd  mov     [rsp+0E8h+var_C8], rax
0x140033002  mov     r9, r13
0x140033005  mov     rcx, [rcx+18h]
0x140033009  call    WPP_SF_qIZ
0x14003300e  jmp     loc_140032F11
0x140033013  test    rdi, rdi
0x140033016  jnz     short loc_14003307B
0x140033018  test    r14, r14
0x14003301b  jnz     short loc_140033071
0x14003301d  mov     rdx, [rsp+0E8h+Context]
0x140033025  test    rdx, rdx
0x140033028  jnz     short loc_14003304E
0x14003302a  mov     rcx, [rsp+0E8h+var_48]
0x140033032  xor     rcx, rsp; StackCookie
0x140033035  call    __security_check_cookie
0x14003303a  add     rsp, 0B0h
0x140033041  pop     r15
0x140033043  pop     r14
0x140033045  pop     r13
0x140033047  pop     r12
0x140033049  pop     rdi
0x14003304a  pop     rsi
0x14003304b  pop     rbx
0x14003304c  retn
0x14003304e  lock and dword ptr [rdx+28h], 0FFFFFBFFh
0x140033056  mov     rcx, [rsp+0E8h+Context]; Context
0x14003305e  cmp     rcx, r15
0x140033061  jz      short loc_14003302A
0x140033063  call    cs:__imp_FltReleaseContext
0x14003306a  nop     dword ptr [rax+rax+00h]
0x14003306f  jmp     short loc_14003302A
0x140033071  mov     rcx, r14
0x140033074  call    MpFreeString
0x140033079  jmp     short loc_14003301D
0x14003307b  mov     rcx, rdi; FileNameInformation
0x14003307e  call    cs:__imp_FltReleaseFileNameInformation
0x140033085  nop     dword ptr [rax+rax+00h]
0x14003308a  jmp     short loc_140033018
0x14008c820  push    rbp
0x14008c822  sub     rsp, 30h
0x14008c826  mov     rbp, rdx
0x14008c829  mov     rcx, [rbp+60h]; FileNameInformation
0x14008c82d  test    rcx, rcx
0x14008c830  jz      short loc_14008C83F
0x14008c832  call    cs:__imp_FltReleaseFileNameInformation
0x14008c839  nop     dword ptr [rax+rax+00h]
0x14008c83e  nop
0x14008c83f  mov     rcx, [rbp+50h]
0x14008c843  test    rcx, rcx
0x14008c846  jz      short loc_14008C84E
0x14008c848  call    MpFreeString
0x14008c84d  nop
0x14008c84e  mov     rax, [rbp+98h]
0x14008c855  test    rax, rax
0x14008c858  jz      short loc_14008C87F
0x14008c85a  lock and dword ptr [rax+28h], 0FFFFFBFFh
0x14008c862  mov     rcx, [rbp+98h]; Context
0x14008c869  cmp     rcx, [rbp+90h]
0x14008c870  jz      short loc_14008C87F
0x14008c872  call    cs:__imp_FltReleaseContext
0x14008c879  nop     dword ptr [rax+rax+00h]
0x14008c87e  nop
0x14008c87f  add     rsp, 30h
0x14008c883  pop     rbp
0x14008c884  retn
  ... truncated ...
```
