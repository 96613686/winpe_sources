# HrCheckClassExists(IWbemServices *,ushort const *,bool *)

- ea: `0x18001a280`
- end: `0x18001a50f`
- name: `?HrCheckClassExists@@YAJPEAUIWbemServices@@PEBGPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(struct IWbemServices *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18001a21c`

## callees

- `0x180005220`
- `0x180008e48`
- `0x18001a280`
- `0x180042010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001a3d7`
- `OLEAUT32!__imp_VariantInit` at `0x18001a3d7`

## pseudocode

```c
__int64 __fastcall HrCheckClassExists(struct IWbemServices *a1, const unsigned __int16 *a2, bool *a3)
{
  const unsigned __int16 *v4; // rdi
  int v6; // eax
  int v7; // ebx
  bool v9; // r15
  int v10; // eax
  int v11; // eax
  BSTR bstrVal; // rax
  int v13; // ecx
  int v14; // edx
  CThirdPartyManager *v15; // rcx
  __int64 v16; // rdx
  int v17; // [rsp+40h] [rbp-40h] BYREF
  __int64 v18; // [rsp+48h] [rbp-38h] BYREF
  __int64 v19; // [rsp+50h] [rbp-30h] BYREF
  __int64 v20; // [rsp+58h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-20h] BYREF
  int v22; // [rsp+C8h] [rbp+48h] BYREF

  v4 = a2;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl'::`2'::impl,
    a2);
  v19 = 0;
  v6 = ((__int64 (__fastcall *)(struct IWbemServices *, _QWORD, __int64, _QWORD, __int64 *))a1->lpVtbl->CreateClassEnum)(
         a1,
         0,
         32,
         0,
         &v19);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v9 = 0;
LABEL_7:
    if ( v7 == 1 )
    {
LABEL_28:
      *a3 = v9;
      goto LABEL_3;
    }
    while ( 1 )
    {
      if ( v7 < 0 )
        goto LABEL_28;
      v18 = 0;
      v20 = 0;
      v22 = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, int *))(*(_QWORD *)v19 + 32LL))(
              v19,
              1000,
              1,
              &v18,
              &v22);
      v7 = v10;
      if ( v10 == 1 || !v22 || v10 < 0 )
        goto LABEL_18;
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v18 + 56LL))(
              v18,
              0,
              0,
              0,
              &v20);
      if ( v11 < 0 )
        break;
      memset(&pvarg, 0, sizeof(pvarg));
      v17 = 0;
      VariantInit(&pvarg);
      v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, int *, _QWORD))(*(_QWORD *)v18 + 32LL))(
              v18,
              L"__CLASS",
              0,
              &pvarg,
              &v17,
              0);
      v7 = v11;
      if ( v11 >= 0 )
      {
        bstrVal = pvarg.bstrVal;
        do
        {
          v13 = *(unsigned __int16 *)((char *)v4 + (_QWORD)bstrVal - pvarg.llVal);
          v14 = *bstrVal - v13;
          if ( v14 )
            break;
          ++bstrVal;
        }
        while ( v13 );
        if ( v14 )
        {
LABEL_18:
          if ( v18 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          goto LABEL_7;
        }
        v9 = 1;
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        goto LABEL_28;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 12;
LABEL_33:
        WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_16e279f110e633c7395c5152dd3f24e1_Traceguids, (unsigned int)v11);
      }
LABEL_21:
      v7 = 0;
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_21;
    }
    v16 = 11;
    goto LABEL_33;
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_16e279f110e633c7395c5152dd3f24e1_Traceguids, (unsigned int)v6);
LABEL_3:
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001a280  mov     [rsp-28h+arg_0], rbx
0x18001a285  mov     [rsp-28h+arg_8], rsi
0x18001a28a  push    rbp
0x18001a28b  push    rdi
0x18001a28c  push    r12
0x18001a28e  push    r14
0x18001a290  push    r15
0x18001a292  mov     rbp, rsp
0x18001a295  sub     rsp, 80h
0x18001a29c  mov     r14, r8
0x18001a29f  mov     rdi, rdx
0x18001a2a2  mov     rbx, rcx
0x18001a2a5  mov     dl, 1
0x18001a2a7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl(void)'::`2'::impl
0x18001a2ae  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001a2b3  xor     r12d, r12d
0x18001a2b6  mov     [rbp+var_30], r12
0x18001a2ba  mov     rax, [rbx]
0x18001a2bd  lea     rcx, [rbp+var_30]
0x18001a2c1  mov     [rsp+80h+var_60], rcx
0x18001a2c6  xor     r9d, r9d
0x18001a2c9  xor     edx, edx
0x18001a2cb  mov     r8d, 20h ; ' '
0x18001a2d1  mov     rcx, rbx
0x18001a2d4  mov     rax, [rax+60h]
0x18001a2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2dd  mov     ebx, eax
0x18001a2df  test    eax, eax
0x18001a2e1  jns     short loc_18001A32D
0x18001a2e3  lea     rsi, WPP_GLOBAL_Control
0x18001a2ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a2f1  cmp     rcx, rsi
0x18001a2f4  jnz     loc_18001A4C0
0x18001a2fa  mov     rcx, [rbp+var_30]
0x18001a2fe  test    rcx, rcx
0x18001a301  jz      short loc_18001A30F
0x18001a303  mov     rax, [rcx]
0x18001a306  mov     rax, [rax+10h]
0x18001a30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a30f  mov     eax, ebx
0x18001a311  lea     r11, [rsp+80h+var_s0]
0x18001a319  mov     rbx, [r11+30h]
0x18001a31d  mov     rsi, [r11+38h]
0x18001a321  mov     rsp, r11
0x18001a324  pop     r15
0x18001a326  pop     r14
0x18001a328  pop     r12
0x18001a32a  pop     rdi
0x18001a32b  pop     rbp
0x18001a32c  retn
0x18001a32d  xor     r15b, r15b
0x18001a330  lea     rsi, WPP_GLOBAL_Control
0x18001a337  cmp     ebx, 1
0x18001a33a  jz      loc_18001A4B8
0x18001a340  test    ebx, ebx
0x18001a342  js      loc_18001A4B8
0x18001a348  mov     [rbp+var_38], r12
0x18001a34c  mov     [rbp+var_28], r12
0x18001a350  mov     [rbp+arg_18], r12d
0x18001a354  mov     rcx, [rbp+var_30]
0x18001a358  mov     rax, [rcx]
0x18001a35b  lea     rdx, [rbp+arg_18]
0x18001a35f  mov     [rsp+80h+var_60], rdx
0x18001a364  lea     r9, [rbp+var_38]
0x18001a368  mov     edx, 3E8h
0x18001a36d  mov     r8d, 1
0x18001a373  mov     rax, [rax+20h]
0x18001a377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a37c  mov     ebx, eax
0x18001a37e  cmp     eax, 1
0x18001a381  jz      loc_18001A438
0x18001a387  cmp     [rbp+arg_18], 0
0x18001a38b  jz      loc_18001A438
0x18001a391  test    eax, eax
0x18001a393  js      loc_18001A438
0x18001a399  mov     rcx, [rbp+var_38]
0x18001a39d  mov     rax, [rcx]
0x18001a3a0  lea     rdx, [rbp+var_28]
0x18001a3a4  mov     [rsp+80h+var_60], rdx
0x18001a3a9  xor     r9d, r9d
0x18001a3ac  xor     r8d, r8d
0x18001a3af  xor     edx, edx
0x18001a3b1  mov     rax, [rax+38h]
0x18001a3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3ba  test    eax, eax
0x18001a3bc  js      loc_18001A487
0x18001a3c2  xorps   xmm0, xmm0
0x18001a3c5  xor     eax, eax
0x18001a3c7  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001a3cb  mov     qword ptr [rbp+pvarg+10h], rax
0x18001a3cf  mov     [rbp+var_40], r12d
0x18001a3d3  lea     rcx, [rbp+pvarg]; pvarg
0x18001a3d7  call    cs:__imp_VariantInit
0x18001a3dd  mov     rcx, [rbp+var_38]
0x18001a3e1  mov     rax, [rcx]
0x18001a3e4  mov     [rsp+80h+var_58], r12
0x18001a3e9  lea     rdx, [rbp+var_40]
0x18001a3ed  mov     [rsp+80h+var_60], rdx
0x18001a3f2  lea     r9, [rbp+pvarg]
0x18001a3f6  xor     r8d, r8d
0x18001a3f9  lea     rdx, aClass; "__CLASS"
0x18001a400  mov     rax, [rax+20h]
0x18001a404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a409  mov     ebx, eax
0x18001a40b  test    eax, eax
0x18001a40d  js      short loc_18001A456
0x18001a40f  mov     rax, qword ptr [rbp+pvarg+8]
0x18001a413  mov     r8, rdi
0x18001a416  sub     r8, rax
0x18001a419  nop     dword ptr [rax+00000000h]
0x18001a420  movzx   edx, word ptr [rax]
0x18001a423  movzx   ecx, word ptr [rax+r8]
0x18001a428  sub     edx, ecx
0x18001a42a  jnz     short loc_18001A434
0x18001a42c  add     rax, 2
0x18001a430  test    ecx, ecx
0x18001a432  jnz     short loc_18001A420
0x18001a434  test    edx, edx
0x18001a436  jz      short loc_18001A4A0
0x18001a438  mov     rcx, [rbp+var_38]
0x18001a43c  test    rcx, rcx
0x18001a43f  jz      loc_18001A337
0x18001a445  mov     rax, [rcx]
0x18001a448  mov     rax, [rax+10h]
0x18001a44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a451  jmp     loc_18001A337
0x18001a456  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a45d  cmp     rcx, rsi
0x18001a460  jnz     loc_18001A4E7
0x18001a466  mov     ebx, r12d
0x18001a469  mov     rcx, [rbp+var_38]
0x18001a46d  test    rcx, rcx
0x18001a470  jz      loc_18001A340
0x18001a476  mov     rax, [rcx]
0x18001a479  mov     rax, [rax+10h]
0x18001a47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a482  jmp     loc_18001A340
0x18001a487  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a48e  cmp     rcx, rsi
0x18001a491  jz      short loc_18001A466
0x18001a493  test    byte ptr [rcx+1Ch], 1
0x18001a497  jz      short loc_18001A466
0x18001a499  mov     edx, 0Bh
0x18001a49e  jmp     short loc_18001A4F6
0x18001a4a0  mov     r15b, 1
0x18001a4a3  mov     rcx, [rbp+var_38]
0x18001a4a7  test    rcx, rcx
0x18001a4aa  jz      short loc_18001A4B8
0x18001a4ac  mov     rax, [rcx]
0x18001a4af  mov     rax, [rax+10h]
0x18001a4b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4b8  mov     [r14], r15b
0x18001a4bb  jmp     loc_18001A2FA
0x18001a4c0  test    byte ptr [rcx+1Ch], 1
0x18001a4c4  jz      loc_18001A2FA
0x18001a4ca  mov     edx, 0Ah
0x18001a4cf  mov     r9d, ebx
0x18001a4d2  lea     r8, WPP_16e279f110e633c7395c5152dd3f24e1_Traceguids
0x18001a4d9  mov     rcx, [rcx+10h]
0x18001a4dd  call    WPP_SF_d
0x18001a4e2  jmp     loc_18001A2FA
0x18001a4e7  test    byte ptr [rcx+1Ch], 1
0x18001a4eb  jz      loc_18001A466
0x18001a4f1  mov     edx, 0Ch
0x18001a4f6  mov     r9d, eax
0x18001a4f9  lea     r8, WPP_16e279f110e633c7395c5152dd3f24e1_Traceguids
0x18001a500  mov     rcx, [rcx+10h]
0x18001a504  call    WPP_SF_d
0x18001a509  jmp     loc_18001A466
```
