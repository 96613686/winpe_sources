# SrvAdminValidateSpn

- ea: `0x14004d770`
- end: `0x14004dbd3`
- name: `SrvAdminValidateSpn`
- size: `1123`
- prototype: `__int64 __usercall@<rax>(PCtxtHandle phContext@<rcx>, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14001389c`
- `0x140015790`
- `0x140016384`
- `0x140024438`
- `0x1400244d8`
- `0x140024564`
- `0x140024654`
- `0x14004d770`
- `0x140053408`

## import_xrefs

- `ksecdd!RevertSecurityContext` at `0x14004da9b`
- `ksecdd!RevertSecurityContext` at `0x14004da9b`
- `ksecdd!ImpersonateSecurityContext` at `0x14004da78`
- `ksecdd!ImpersonateSecurityContext` at `0x14004da78`
- `ksecdd!MapSecurityError` at `0x14004d7cb`
- `ksecdd!MapSecurityError` at `0x14004d840`
- `ksecdd!MapSecurityError` at `0x14004d7cb`
- `ksecdd!MapSecurityError` at `0x14004d840`
- `ksecdd!QueryContextAttributesW` at `0x14004d7bd`
- `ksecdd!QueryContextAttributesW` at `0x14004d832`
- `ksecdd!QueryContextAttributesW` at `0x14004d7bd`
- `ksecdd!QueryContextAttributesW` at `0x14004d832`

## pseudocode

```c
bool __fastcall SrvAdminValidateSpn(
        PCtxtHandle phContext,
        int a2,
        __int64 a3,
        _QWORD *a4,
        NTSTATUS *a5,
        unsigned __int8 *a6,
        unsigned __int8 *a7)
{
  char v7; // r12
  unsigned __int8 v9; // r13
  SECURITY_STATUS v10; // eax
  NTSTATUS v11; // eax
  int Timer_high; // edx
  SECURITY_STATUS v13; // eax
  NTSTATUS v14; // r14d
  int v15; // ecx
  unsigned __int8 v16; // bl
  int v17; // r8d
  bool v18; // bl
  bool v19; // zf
  SECURITY_STATUS v20; // eax
  __int64 v21; // r8
  unsigned __int8 v23; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int8 v24[3]; // [rsp+51h] [rbp-1Fh] BYREF
  unsigned int v25; // [rsp+54h] [rbp-1Ch] BYREF
  int pBuffer; // [rsp+58h] [rbp-18h] BYREF
  _WORD *v27; // [rsp+60h] [rbp-10h] BYREF

  v7 = 0;
  v27 = 0;
  v9 = 0;
  v23 = 0;
  v24[0] = 0;
  pBuffer = 0;
  *a4 = 0;
  v10 = QueryContextAttributesW(phContext, 0x25u, &pBuffer);
  v11 = MapSecurityError(v10);
  v25 = v11;
  if ( v11 == -1073741637 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_8a84e82af7ab36740a001ca535541b54_Traceguids);
    }
    v25 = 0;
    pBuffer = 0;
  }
  else if ( v11 < 0 )
  {
    v15 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_8a84e82af7ab36740a001ca535541b54_Traceguids, v25);
    }
    v16 = v23;
    v14 = 263;
    goto LABEL_58;
  }
  v13 = QueryContextAttributesW(phContext, 0x1Bu, &v27);
  v14 = MapSecurityError(v13);
  if ( v14 == -1073741637 )
  {
    v15 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_8a84e82af7ab36740a001ca535541b54_Traceguids);
    }
    v16 = v23;
    v25 = 0;
    goto LABEL_65;
  }
  if ( v14 == -1073741634 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_8a84e82af7ab36740a001ca535541b54_Traceguids);
    }
  }
  else if ( v14 < 0
         && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_8a84e82af7ab36740a001ca535541b54_Traceguids, (unsigned int)v14);
  }
  v17 = a2;
  v15 = a2;
  if ( a2 )
  {
    v15 = a2 - 1;
    if ( a2 != 1 )
    {
      v15 = a2 - 2;
      if ( a2 != 2 )
      {
        if ( a2 != 3 )
        {
          if ( a2 != 4 )
          {
LABEL_34:
            v16 = v23;
            v25 = -1073741790;
            goto LABEL_59;
          }
          v7 = 1;
        }
        if ( !v27 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_8a84e82af7ab36740a001ca535541b54_Traceguids);
          }
          goto LABEL_34;
        }
        v18 = 1;
        goto LABEL_42;
      }
      v7 = 1;
    }
    if ( v27 )
    {
      v18 = 1;
      goto LABEL_42;
    }
LABEL_49:
    v16 = v23;
    v25 = 0;
    goto LABEL_66;
  }
  v18 = pBuffer != 0;
  if ( !v27 )
    goto LABEL_49;
LABEL_42:
  SrvAdminCheckSpn(v27, &v23, v24);
  v19 = !v18;
  v16 = v23;
  if ( !v19 && !v23 )
  {
    v9 = v24[0];
LABEL_52:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_8a84e82af7ab36740a001ca535541b54_Traceguids, v23, v9);
    }
    v25 = -1073741790;
    goto LABEL_59;
  }
  v9 = v24[0];
  if ( v7 && !v24[0] )
    goto LABEL_52;
  v25 = 0;
LABEL_58:
  if ( v25 )
  {
LABEL_59:
    v20 = ImpersonateSecurityContext(phContext);
    if ( v20 < 0 )
    {
      v15 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_8a84e82af7ab36740a001ca535541b54_Traceguids,
          (unsigned int)v20);
      }
    }
    else
    {
      SrvAdminAuditSpnCheck(v27, &v25, v21, (unsigned int)v20);
      RevertSecurityContext(phContext);
    }
  }
LABEL_65:
  v17 = a2;
LABEL_66:
  if ( SrvNetAuditClientSpnSupport )
  {
    if ( v14 )
    {
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x8000000) != 0 )
        McTemplateK0hzr0dq_EtwWriteTransfer(v15, Timer_high, v17, *(_WORD *)a3 >> 1, *(_QWORD *)(a3 + 8), v14, v17);
    }
    else if ( *v27 )
    {
      if ( (!v16 || !v9) && (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x8000000) != 0 )
        McTemplateK0hzr0zttq_EtwWriteTransfer(
          v16,
          a3,
          v17,
          *(_WORD *)a3 >> 1,
          *(_QWORD *)(a3 + 8),
          (__int64)v27,
          v16,
          v9,
          v17);
    }
    else if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x8000000) != 0 )
    {
      McTemplateK0hzr0q_EtwWriteTransfer(v15, Timer_high, v17, *(_WORD *)a3 >> 1, *(_QWORD *)(a3 + 8), v17);
    }
  }
  v19 = v25 == 0;
  *a4 = v27;
  *a5 = v14;
  *a6 = v16;
  *a7 = v9;
  return v19;
}

```

## disassembly

```asm
0x14004d770  mov     rax, rsp
0x14004d773  mov     [rax+20h], r9
0x14004d777  mov     [rax+18h], r8
0x14004d77b  mov     [rax+10h], edx
0x14004d77e  mov     [rax+8], rcx
0x14004d782  push    rbp
0x14004d783  push    rbx
0x14004d784  push    rsi
0x14004d785  push    r12
0x14004d787  push    r13
0x14004d789  push    r14
0x14004d78b  push    r15
0x14004d78d  mov     rbp, rsp
0x14004d790  sub     rsp, 70h
0x14004d794  xor     r12d, r12d
0x14004d797  lea     r8, [rbp+pBuffer]; pBuffer
0x14004d79b  mov     r14, rcx
0x14004d79e  mov     [rbp+var_10], r12
0x14004d7a2  mov     [rbp+var_1C], r12d
0x14004d7a6  mov     r13b, r12b
0x14004d7a9  mov     [rbp+var_20], r12b
0x14004d7ad  lea     edx, [r12+25h]; ulAttribute
0x14004d7b2  mov     [rbp+var_1F], r12b
0x14004d7b6  mov     [rbp+pBuffer], r12d
0x14004d7ba  mov     [r9], r12
0x14004d7bd  call    cs:__imp_QueryContextAttributesW
0x14004d7c4  nop     dword ptr [rax+rax+00h]
0x14004d7c9  mov     ecx, eax; SecStatus
0x14004d7cb  call    cs:__imp_MapSecurityError
0x14004d7d2  nop     dword ptr [rax+rax+00h]
0x14004d7d7  mov     [rbp+var_1C], eax
0x14004d7da  lea     rsi, WPP_GLOBAL_Control
0x14004d7e1  mov     bl, 4
0x14004d7e3  lea     r15, WPP_8a84e82af7ab36740a001ca535541b54_Traceguids
0x14004d7ea  cmp     eax, 0C00000BBh
0x14004d7ef  jnz     loc_14004D890
0x14004d7f5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d7fc  cmp     rcx, rsi
0x14004d7ff  jz      short loc_14004D81E
0x14004d801  mov     eax, [rcx+2Ch]
0x14004d804  test    al, 20h
0x14004d806  jz      short loc_14004D81E
0x14004d808  cmp     [rcx+29h], bl
0x14004d80b  jb      short loc_14004D81E
0x14004d80d  mov     rcx, [rcx+18h]
0x14004d811  lea     edx, [r12+0Ah]
0x14004d816  mov     r8, r15
0x14004d819  call    WPP_SF_
0x14004d81e  mov     [rbp+var_1C], r12d
0x14004d822  mov     [rbp+pBuffer], r12d
0x14004d826  lea     r8, [rbp+var_10]; pBuffer
0x14004d82a  mov     edx, 1Bh; ulAttribute
0x14004d82f  mov     rcx, r14; phContext
0x14004d832  call    cs:__imp_QueryContextAttributesW
0x14004d839  nop     dword ptr [rax+rax+00h]
0x14004d83e  mov     ecx, eax; SecStatus
0x14004d840  call    cs:__imp_MapSecurityError
0x14004d847  nop     dword ptr [rax+rax+00h]
0x14004d84c  mov     r14d, eax
0x14004d84f  cmp     eax, 0C00000BBh
0x14004d854  jnz     loc_14004D8DD
0x14004d85a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d861  cmp     rcx, rsi
0x14004d864  jz      short loc_14004D884
0x14004d866  mov     edx, [rcx+2Ch]
0x14004d869  test    dl, 20h
0x14004d86c  jz      short loc_14004D884
0x14004d86e  cmp     [rcx+29h], bl
0x14004d871  jb      short loc_14004D884
0x14004d873  mov     rcx, [rcx+18h]
0x14004d877  mov     edx, 0Ch
0x14004d87c  mov     r8, r15
0x14004d87f  call    WPP_SF_
0x14004d884  mov     bl, [rbp+var_20]
0x14004d887  mov     [rbp+var_1C], r12d
0x14004d88b  jmp     loc_14004DAD6
0x14004d890  test    eax, eax
0x14004d892  jns     short loc_14004D826
0x14004d894  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d89b  lea     rsi, WPP_GLOBAL_Control
0x14004d8a2  lea     r15, WPP_8a84e82af7ab36740a001ca535541b54_Traceguids
0x14004d8a9  cmp     rcx, rsi
0x14004d8ac  jz      short loc_14004D8CF
0x14004d8ae  mov     eax, [rcx+2Ch]
0x14004d8b1  test    al, 20h
0x14004d8b3  jz      short loc_14004D8CF
0x14004d8b5  cmp     [rcx+29h], bl
0x14004d8b8  jb      short loc_14004D8CF
0x14004d8ba  mov     r9d, [rbp+var_1C]
0x14004d8be  mov     edx, 0Bh
0x14004d8c3  mov     rcx, [rcx+18h]
0x14004d8c7  mov     r8, r15
0x14004d8ca  call    WPP_SF_d
0x14004d8cf  mov     bl, [rbp+var_20]
0x14004d8d2  mov     r14d, 107h
0x14004d8d8  jmp     loc_14004DA6B
0x14004d8dd  cmp     r14d, 0C00000BEh
0x14004d8e4  jnz     short loc_14004D911
0x14004d8e6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d8ed  cmp     rcx, rsi
0x14004d8f0  jz      short loc_14004D942
0x14004d8f2  mov     eax, [rcx+2Ch]
0x14004d8f5  test    al, 20h
0x14004d8f7  jz      short loc_14004D942
0x14004d8f9  cmp     [rcx+29h], bl
0x14004d8fc  jb      short loc_14004D942
0x14004d8fe  mov     rcx, [rcx+18h]
0x14004d902  mov     edx, 0Dh
0x14004d907  mov     r8, r15
0x14004d90a  call    WPP_SF_
0x14004d90f  jmp     short loc_14004D942
0x14004d911  test    r14d, r14d
0x14004d914  jns     short loc_14004D942
0x14004d916  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d91d  cmp     rcx, rsi
0x14004d920  jz      short loc_14004D942
0x14004d922  mov     eax, [rcx+2Ch]
0x14004d925  test    al, 20h
0x14004d927  jz      short loc_14004D942
0x14004d929  cmp     [rcx+29h], bl
0x14004d92c  jb      short loc_14004D942
0x14004d92e  mov     rcx, [rcx+18h]
0x14004d932  mov     edx, 0Eh
0x14004d937  mov     r9d, r14d
0x14004d93a  mov     r8, r15
0x14004d93d  call    WPP_SF_d
0x14004d942  mov     r8d, [rbp+arg_8]
0x14004d946  mov     ecx, r8d
0x14004d949  test    r8d, r8d
0x14004d94c  jz      loc_14004D9F1
0x14004d952  sub     ecx, 1
0x14004d955  jz      loc_14004D9E1
0x14004d95b  sub     ecx, 1
0x14004d95e  jz      short loc_14004D9DE
0x14004d960  sub     ecx, 1
0x14004d963  jz      short loc_14004D983
0x14004d965  cmp     ecx, 1
0x14004d968  jz      short loc_14004D979
0x14004d96a  mov     bl, [rbp+var_20]
0x14004d96d  mov     [rbp+var_1C], 0C0000022h
0x14004d974  jmp     loc_14004DA71
0x14004d979  mov     edx, 1
0x14004d97e  mov     r12b, dl
0x14004d981  jmp     short loc_14004D988
0x14004d983  mov     edx, 1
0x14004d988  cmp     [rbp+var_10], 0
0x14004d98d  jnz     short loc_14004D9BA
0x14004d98f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d996  cmp     rcx, rsi
0x14004d999  jz      short loc_14004D96A
0x14004d99b  mov     eax, [rcx+2Ch]
0x14004d99e  test    al, 20h
0x14004d9a0  jz      short loc_14004D96A
0x14004d9a2  cmp     [rcx+29h], dl
0x14004d9a5  jb      short loc_14004D96A
0x14004d9a7  mov     rcx, [rcx+18h]
0x14004d9ab  mov     edx, 0Fh
0x14004d9b0  mov     r8, r15
0x14004d9b3  call    WPP_SF_
0x14004d9b8  jmp     short loc_14004D96A
0x14004d9ba  mov     bl, dl
0x14004d9bc  mov     rcx, [rbp+var_10]
0x14004d9c0  lea     r8, [rbp+var_1F]
0x14004d9c4  lea     rdx, [rbp+var_20]
0x14004d9c8  call    SrvAdminCheckSpn
0x14004d9cd  test    bl, bl
0x14004d9cf  mov     bl, [rbp+var_20]
0x14004d9d2  jz      short loc_14004DA14
0x14004d9d4  test    bl, bl
0x14004d9d6  jnz     short loc_14004DA14
0x14004d9d8  mov     r13b, [rbp+var_1F]
0x14004d9dc  jmp     short loc_14004DA25
0x14004d9de  mov     r12b, 1
0x14004d9e1  cmp     [rbp+var_10], 0
0x14004d9e6  jnz     short loc_14004D9ED
0x14004d9e8  xor     r12d, r12d
0x14004d9eb  jmp     short loc_14004DA08
0x14004d9ed  mov     bl, 1
0x14004d9ef  jmp     short loc_14004D9BC
0x14004d9f1  xor     al, al
0x14004d9f3  cmp     [rbp+pBuffer], r12d
0x14004d9f7  movzx   ebx, al
0x14004d9fa  mov     eax, 1
0x14004d9ff  cmovnz  ebx, eax
0x14004da02  cmp     [rbp+var_10], r12
0x14004da06  jnz     short loc_14004D9BC
0x14004da08  mov     bl, [rbp+var_20]
0x14004da0b  mov     [rbp+var_1C], r12d
0x14004da0f  jmp     loc_14004DADA
0x14004da14  mov     r13b, [rbp+var_1F]
0x14004da18  test    r12b, r12b
0x14004da1b  jz      short loc_14004DA64
0x14004da1d  xor     r12d, r12d
0x14004da20  test    r13b, r13b
0x14004da23  jnz     short loc_14004DA67
0x14004da25  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004da2c  cmp     rcx, rsi
0x14004da2f  jz      short loc_14004DA5B
0x14004da31  mov     eax, [rcx+2Ch]
0x14004da34  test    al, 20h
0x14004da36  jz      short loc_14004DA5B
0x14004da38  cmp     byte ptr [rcx+29h], 1
0x14004da3c  jb      short loc_14004DA5B
0x14004da3e  mov     rcx, [rcx+18h]
0x14004da42  mov     edx, 10h
0x14004da47  movzx   eax, r13b
0x14004da4b  mov     r8, r15
0x14004da4e  movzx   r9d, bl
0x14004da52  mov     dword ptr [rsp+70h+var_50], eax
0x14004da56  call    WPP_SF_Dd
0x14004da5b  mov     [rbp+var_1C], 0C0000022h
0x14004da62  jmp     short loc_14004DA71
0x14004da64  xor     r12d, r12d
0x14004da67  mov     [rbp+var_1C], r12d
0x14004da6b  cmp     [rbp+var_1C], r12d
0x14004da6f  jz      short loc_14004DAD6
0x14004da71  mov     r12, [rbp+phContext]
0x14004da75  mov     rcx, r12; phContext
0x14004da78  call    cs:__imp_ImpersonateSecurityContext
0x14004da7f  nop     dword ptr [rax+rax+00h]
0x14004da84  mov     r9d, eax
0x14004da87  test    eax, eax
0x14004da89  js      short loc_14004DAA9
0x14004da8b  mov     rcx, [rbp+var_10]
0x14004da8f  lea     rdx, [rbp+var_1C]
0x14004da93  call    SrvAdminAuditSpnCheck
0x14004da98  mov     rcx, r12; phContext
0x14004da9b  call    cs:__imp_RevertSecurityContext
0x14004daa2  nop     dword ptr [rax+rax+00h]
0x14004daa7  jmp     short loc_14004DAD3
0x14004daa9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004dab0  cmp     rcx, rsi
0x14004dab3  jz      short loc_14004DAD3
0x14004dab5  mov     eax, [rcx+2Ch]
0x14004dab8  test    al, 20h
0x14004daba  jz      short loc_14004DAD3
0x14004dabc  cmp     byte ptr [rcx+29h], 1
0x14004dac0  jb      short loc_14004DAD3
0x14004dac2  mov     rcx, [rcx+18h]
0x14004dac6  mov     edx, 11h
0x14004dacb  mov     r8, r15
0x14004dace  call    WPP_SF_d
0x14004dad3  xor     r12d, r12d
0x14004dad6  mov     r8d, [rbp+arg_8]
0x14004dada  cmp     cs:SrvNetAuditClientSpnSupport, r12b
0x14004dae1  jz      loc_14004DB9C
0x14004dae7  test    r14d, r14d
0x14004daea  jz      short loc_14004DB1F
0x14004daec  test    byte ptr cs:WPP_MAIN_CB.Queue+13h, 8
0x14004daf3  jz      loc_14004DB9C
0x14004daf9  mov     rax, [rbp+arg_10]
0x14004dafd  mov     [rsp+70h+var_40], r8d
0x14004db02  mov     dword ptr [rsp+70h+var_48], r14d
0x14004db07  movzx   r9d, word ptr [rax]
0x14004db0b  mov     rax, [rax+8]
0x14004db0f  shr     r9w, 1
0x14004db13  mov     [rsp+70h+var_50], rax
0x14004db18  call    McTemplateK0hzr0dq_EtwWriteTransfer
0x14004db1d  jmp     short loc_14004DB9C
0x14004db1f  mov     rax, [rbp+var_10]
0x14004db23  cmp     [rax], r12w
0x14004db27  jnz     short loc_14004DB53
0x14004db29  test    byte ptr cs:WPP_MAIN_CB.Queue+13h, 8
0x14004db30  jz      short loc_14004DB9C
0x14004db32  mov     rax, [rbp+arg_10]
0x14004db36  mov     dword ptr [rsp+70h+var_48], r8d
0x14004db3b  movzx   r9d, word ptr [rax]
0x14004db3f  mov     rax, [rax+8]
0x14004db43  shr     r9w, 1
0x14004db47  mov     [rsp+70h+var_50], rax
0x14004db4c  call    McTemplateK0hzr0q_EtwWriteTransfer
0x14004db51  jmp     short loc_14004DB9C
0x14004db53  test    bl, bl
0x14004db55  jz      short loc_14004DB5C
0x14004db57  test    r13b, r13b
0x14004db5a  jnz     short loc_14004DB9C
0x14004db5c  test    byte ptr cs:WPP_MAIN_CB.Queue+13h, 8
0x14004db63  jz      short loc_14004DB9C
0x14004db65  mov     rdx, [rbp+arg_10]
0x14004db69  mov     [rsp+70h+var_30], r8d
0x14004db6e  movzx   eax, r13b
0x14004db72  mov     [rsp+70h+var_38], eax
0x14004db76  mov     rax, [rbp+var_10]
0x14004db7a  movzx   r9d, word ptr [rdx]
0x14004db7e  movzx   ecx, bl
0x14004db81  mov     [rsp+70h+var_40], ecx
0x14004db85  mov     [rsp+70h+var_48], rax
0x14004db8a  mov     rax, [rdx+8]
0x14004db8e  shr     r9w, 1
0x14004db92  mov     [rsp+70h+var_50], rax
0x14004db97  call    McTemplateK0hzr0zttq_EtwWriteTransfer
0x14004db9c  mov     rax, [rbp+var_10]
0x14004dba0  mov     rcx, [rbp+arg_18]
0x14004dba4  cmp     [rbp+var_1C], r12d
0x14004dba8  mov     [rcx], rax
0x14004dbab  mov     rax, [rbp+arg_20]
0x14004dbaf  mov     [rax], r14d
0x14004dbb2  mov     rax, [rbp+arg_28]
0x14004dbb6  mov     [rax], bl
0x14004dbb8  mov     rax, [rbp+arg_30]
  ... truncated ...
```
