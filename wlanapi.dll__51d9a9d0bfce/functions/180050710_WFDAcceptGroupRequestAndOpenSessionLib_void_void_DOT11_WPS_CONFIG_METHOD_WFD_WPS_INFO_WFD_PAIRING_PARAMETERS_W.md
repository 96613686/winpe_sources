# WFDAcceptGroupRequestAndOpenSessionLib(void *,void *,_DOT11_WPS_CONFIG_METHOD,_WFD_WPS_INFO *,_WFD_PAIRING_PARAMETERS *,_WFD_VERTICAL_PAIRING_INFO *,_WFD_VERTICAL_PAIRING_INFO * *,ushort * *,ulong *,_GUID *,void * *)

- ea: `0x180050710`
- end: `0x180050b85`
- name: `?WFDAcceptGroupRequestAndOpenSessionLib@@YAKPEAX0W4_DOT11_WPS_CONFIG_METHOD@@PEAU_WFD_WPS_INFO@@PEAU_WFD_PAIRING_PARAMETERS@@PEAU_WFD_VERTICAL_PAIRING_INFO@@PEAPEAU4@PEAPEAGPEAKPEAU_GUID@@PEAPEAX@Z`
- size: `1141`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x18002c2f0`
- `0x180038060`

## callees

- `0x1800021cc`
- `0x1800038d0`
- `0x1800063a0`
- `0x180006934`
- `0x1800132cc`
- `0x180019a20`
- `0x180043d68`
- `0x18004fe34`
- `0x18004ffb8`
- `0x180050710`
- `0x18005acbc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180050906`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180050906`
- `RPCRT4!NdrClientCall3` at `0x1800509aa`
- `RPCRT4!NdrClientCall3` at `0x1800509aa`
- `RPCRT4!RpcExceptionFilter` at `0x1800619de`
- `RPCRT4!RpcExceptionFilter` at `0x1800619de`

## pseudocode

```c
__int64 __fastcall WFDAcceptGroupRequestAndOpenSessionLib(
        void *a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _DWORD *a9,
        __int64 a10,
        _QWORD *a11)
{
  __int64 v12; // r8
  union DOT11_OUI_HEADER *v14; // r10
  unsigned int v15; // ebx
  struct _WFD_API_ASYNC_CONTEXT *v16; // rdi
  __int64 v17; // rdx
  CLIENT_CALL_RETURN v18; // rax
  unsigned int Pointer; // ebx
  struct _WFD_API_ASYNC_CONTEXT *v20; // rdi
  struct _WFD_API_ASYNC_CONTEXT *v22; // [rsp+80h] [rbp-A8h] BYREF
  int v23; // [rsp+88h] [rbp-A0h]
  int v24; // [rsp+8Ch] [rbp-9Ch]
  __int64 v25; // [rsp+90h] [rbp-98h]
  __int64 v26; // [rsp+98h] [rbp-90h]
  __int64 v27; // [rsp+A0h] [rbp-88h]
  __int64 v28; // [rsp+A8h] [rbp-80h]
  __int64 v29; // [rsp+B0h] [rbp-78h]
  __int64 v30; // [rsp+B8h] [rbp-70h]
  CLIENT_CALL_RETURN v31; // [rsp+C0h] [rbp-68h]
  _DWORD *v32; // [rsp+C8h] [rbp-60h]
  _QWORD *v33; // [rsp+D0h] [rbp-58h]
  GUID ActivityId; // [rsp+D8h] [rbp-50h] BYREF

  v23 = a3;
  v12 = a2;
  v26 = a2;
  v30 = a5;
  v29 = a6;
  v28 = a7;
  v27 = a8;
  v32 = a9;
  v25 = a10;
  v33 = a11;
  v22 = 0;
  ActivityId = 0;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 127, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
      v14 = WPP_GLOBAL_Control;
      v12 = v26;
    }
    if ( v14 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v14 + 105) >= 3u
      && (*((_DWORD *)v14 + 27) & 0x1000) != 0 )
    {
      WPP_SF_q(*((_QWORD *)v14 + 12), 128, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v12);
      v14 = WPP_GLOBAL_Control;
    }
  }
  if ( a1 && a4 && a8 && a9 && v25 && a11 )
  {
    v15 = LocalWfdAsyncContextCreateInternal(a1, &v22, 0);
    if ( v15 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 130, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
        v14 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      v16 = v22;
      *(_DWORD *)v22 = 4;
      EventActivityIdControl(1u, &ActivityId);
      v17 = **((_QWORD **)v16 + 1);
      v31.Simple = 0;
      v18.Pointer = NdrClientCall3(
                      (MIDL_STUBLESS_PROXY_INFO *)&winwlan_ProxyInfo,
                      0x5Fu,
                      0,
                      &ActivityId,
                      v17,
                      v26,
                      v23,
                      a4,
                      v30,
                      v29,
                      v28,
                      v27,
                      a9,
                      v25,
                      (char *)v16 + 152).Pointer;
      Pointer = (unsigned int)v18.Pointer;
      v31.Pointer = v18.Pointer;
      v24 = (int)v18.Pointer;
      if ( LODWORD(v18.Pointer) )
      {
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
        {
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            132,
            WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids,
            LODWORD(v18.Pointer),
            *a9);
        }
      }
      else
      {
        v20 = v22;
        LocalWfdAsyncContextPendingMarkIdle(v22);
        *a11 = *((_QWORD *)v20 + 2);
        v22 = 0;
      }
      v15 = ServiceStatus(Pointer);
    }
  }
  else
  {
    if ( v14 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v14 + 105)
      && (*((_DWORD *)v14 + 27) & 0x1000) != 0 )
    {
      WPP_SF_qqqqq(*((_QWORD *)v14 + 12), a2, v12, a1, a4, a8, a9, a11);
      v14 = WPP_GLOBAL_Control;
    }
    v15 = 87;
  }
  if ( v22 )
  {
    LocalWfdAsyncContextDeref(v22);
    v14 = WPP_GLOBAL_Control;
  }
  if ( v15 )
  {
    if ( v14 == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
      return v15;
    if ( *((_BYTE *)v14 + 105) && (*((_DWORD *)v14 + 27) & 0x1000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v14 + 12), 133, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v15);
      v14 = WPP_GLOBAL_Control;
    }
  }
  if ( v14 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v14 + 105) >= 4u
    && (*((_BYTE *)v14 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v14 + 12), 134, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v15);
  }
  return v15;
}

```

## disassembly

```asm
0x180050710  mov     r11, rsp
0x180050713  push    rbx
0x180050714  push    rdi
0x180050715  push    r12
0x180050717  push    r13
0x180050719  push    r14
0x18005071b  push    r15
0x18005071d  sub     rsp, 0F8h
0x180050724  mov     rax, cs:__security_cookie
0x18005072b  xor     rax, rsp
0x18005072e  mov     [rsp+128h+var_40], rax
0x180050736  mov     r13, r9
0x180050739  mov     [rsp+128h+var_A0], r8d
0x180050741  mov     r8, rdx
0x180050744  mov     [rsp+128h+var_90], rdx
0x18005074c  mov     rbx, rcx
0x18005074f  mov     rax, [rsp+128h+arg_20]
0x180050757  mov     [rsp+128h+var_70], rax
0x18005075f  mov     rax, [rsp+128h+arg_28]
0x180050767  mov     [rsp+128h+var_78], rax
0x18005076f  mov     rax, [rsp+128h+arg_30]
0x180050777  mov     [rsp+128h+var_80], rax
0x18005077f  mov     rdi, [rsp+128h+arg_38]
0x180050787  mov     [rsp+128h+var_88], rdi
0x18005078f  mov     r15, [rsp+128h+arg_40]
0x180050797  mov     [rsp+128h+var_60], r15
0x18005079f  mov     rax, [rsp+128h+arg_48]
0x1800507a7  mov     [rsp+128h+var_98], rax
0x1800507af  mov     r12, [rsp+128h+arg_50]
0x1800507b7  mov     [rsp+128h+var_58], r12
0x1800507bf  mov     qword ptr [r11-0A8h], 0
0x1800507ca  xorps   xmm0, xmm0
0x1800507cd  movups  xmmword ptr [r11-50h], xmm0
0x1800507d2  lea     r14, WPP_GLOBAL_Control
0x1800507d9  mov     r10, cs:WPP_GLOBAL_Control
0x1800507e0  cmp     r10, r14
0x1800507e3  jz      short loc_18005084C
0x1800507e5  cmp     byte ptr [r10+69h], 4
0x1800507ea  jb      short loc_180050817
0x1800507ec  test    byte ptr [r10+6Ch], 2
0x1800507f1  jz      short loc_180050817
0x1800507f3  mov     edx, 7Fh
0x1800507f8  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800507ff  mov     rcx, [r10+60h]
0x180050803  call    WPP_SF_
0x180050808  mov     r10, cs:WPP_GLOBAL_Control
0x18005080f  mov     r8, [rsp+128h+var_90]
0x180050817  cmp     r10, r14
0x18005081a  jz      short loc_18005084C
0x18005081c  cmp     byte ptr [r10+69h], 3
0x180050821  jb      short loc_18005084C
0x180050823  test    dword ptr [r10+6Ch], 1000h
0x18005082b  jz      short loc_18005084C
0x18005082d  mov     edx, 80h
0x180050832  mov     r9, r8
0x180050835  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18005083c  mov     rcx, [r10+60h]
0x180050840  call    WPP_SF_q
0x180050845  mov     r10, cs:WPP_GLOBAL_Control
0x18005084c  test    rbx, rbx
0x18005084f  jz      loc_180050A9F
0x180050855  test    r13, r13
0x180050858  jz      loc_180050A9F
0x18005085e  test    rdi, rdi
0x180050861  jz      loc_180050A9F
0x180050867  test    r15, r15
0x18005086a  jz      loc_180050A9F
0x180050870  cmp     [rsp+128h+var_98], 0
0x180050879  jz      loc_180050A9F
0x18005087f  test    r12, r12
0x180050882  jz      loc_180050A9F
0x180050888  xor     r8d, r8d; int
0x18005088b  lea     rdx, [rsp+128h+var_A8]; struct _WFD_API_ASYNC_CONTEXT **
0x180050893  mov     rcx, rbx; void *
0x180050896  call    ?LocalWfdAsyncContextCreateInternal@@YAKPEAXPEAPEAU_WFD_API_ASYNC_CONTEXT@@H@Z; LocalWfdAsyncContextCreateInternal(void *,_WFD_API_ASYNC_CONTEXT * *,int)
0x18005089b  mov     ebx, eax
0x18005089d  test    eax, eax
0x18005089f  jz      short loc_1800508EB
0x1800508a1  mov     r10, cs:WPP_GLOBAL_Control
0x1800508a8  cmp     r10, r14
0x1800508ab  jz      loc_180050AE1
0x1800508b1  cmp     byte ptr [r10+69h], 1
0x1800508b6  jb      loc_180050AE1
0x1800508bc  test    dword ptr [r10+6Ch], 1000h
0x1800508c4  jz      loc_180050AE1
0x1800508ca  mov     edx, 82h
0x1800508cf  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800508d6  mov     rcx, [r10+60h]
0x1800508da  call    WPP_SF_
0x1800508df  mov     r10, cs:WPP_GLOBAL_Control
0x1800508e6  jmp     loc_180050AE1
0x1800508eb  mov     rdi, [rsp+128h+var_A8]
0x1800508f3  mov     dword ptr [rdi], 4
0x1800508f9  lea     rdx, [rsp+128h+ActivityId]; ActivityId
0x180050901  mov     ecx, 1; ControlCode
0x180050906  call    cs:__imp_EventActivityIdControl
0x18005090c  nop
0x18005090d  lea     rcx, [rdi+98h]
0x180050914  mov     rax, [rdi+8]
0x180050918  mov     rdx, [rax]
0x18005091b  mov     [rsp+128h+var_68], 0
0x180050927  mov     [rsp+128h+var_B8], rcx
0x18005092c  mov     rax, [rsp+128h+var_98]
0x180050934  mov     [rsp+128h+var_C0], rax
0x180050939  mov     [rsp+128h+var_C8], r15
0x18005093e  mov     rax, [rsp+128h+var_88]
0x180050946  mov     [rsp+128h+var_D0], rax
0x18005094b  mov     rax, [rsp+128h+var_80]
0x180050953  mov     [rsp+128h+var_D8], rax
0x180050958  mov     rax, [rsp+128h+var_78]
0x180050960  mov     [rsp+128h+var_E0], rax
0x180050965  mov     rax, [rsp+128h+var_70]
0x18005096d  mov     [rsp+128h+var_E8], rax
0x180050972  mov     [rsp+128h+var_F0], r13
0x180050977  mov     eax, [rsp+128h+var_A0]
0x18005097e  mov     dword ptr [rsp+128h+var_F8], eax
0x180050982  mov     rax, [rsp+128h+var_90]
0x18005098a  mov     [rsp+128h+var_100], rax
0x18005098f  mov     [rsp+128h+var_108], rdx
0x180050994  lea     r9, [rsp+128h+ActivityId]
0x18005099c  xor     r8d, r8d; pReturnValue
0x18005099f  lea     edx, [r8+5Fh]; nProcNum
0x1800509a3  lea     rcx, ?winwlan_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800509aa  call    cs:__imp_NdrClientCall3
0x1800509b0  mov     rbx, rax
0x1800509b3  mov     [rsp+128h+var_68], rax
0x1800509bb  mov     [rsp+128h+var_9C], eax
0x1800509c2  mov     r10, cs:WPP_GLOBAL_Control
0x1800509c9  jmp     short loc_180050A2E
0x1800509cb  mov     ebx, eax
0x1800509cd  mov     [rsp+128h+var_9C], eax
0x1800509d4  lea     rcx, WPP_GLOBAL_Control
0x1800509db  mov     r10, cs:WPP_GLOBAL_Control
0x1800509e2  cmp     r10, rcx
0x1800509e5  jz      short loc_180050A17
0x1800509e7  cmp     byte ptr [r10+69h], 1
0x1800509ec  jb      short loc_180050A17
0x1800509ee  test    dword ptr [r10+6Ch], 1000h
0x1800509f6  jz      short loc_180050A17
0x1800509f8  mov     edx, 83h
0x1800509fd  mov     r9d, eax
0x180050a00  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180050a07  mov     rcx, [r10+60h]
0x180050a0b  call    WPP_SF_d
0x180050a10  mov     r10, cs:WPP_GLOBAL_Control
0x180050a17  lea     r14, WPP_GLOBAL_Control
0x180050a1e  mov     r15, [rsp+128h+var_60]
0x180050a26  mov     r12, [rsp+128h+var_58]
0x180050a2e  test    ebx, ebx
0x180050a30  jz      short loc_180050A69
0x180050a32  cmp     r10, r14
0x180050a35  jz      short loc_180050A94
0x180050a37  cmp     byte ptr [r10+69h], 1
0x180050a3c  jb      short loc_180050A94
0x180050a3e  test    dword ptr [r10+6Ch], 1000h
0x180050a46  jz      short loc_180050A94
0x180050a48  mov     edx, 84h
0x180050a4d  mov     eax, [r15]
0x180050a50  mov     dword ptr [rsp+128h+var_108], eax
0x180050a54  mov     r9d, ebx
0x180050a57  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180050a5e  mov     rcx, [r10+60h]
0x180050a62  call    WPP_SF_dd
0x180050a67  jmp     short loc_180050A8D
0x180050a69  mov     rdi, [rsp+128h+var_A8]
0x180050a71  mov     rcx, rdi; struct _WFD_API_ASYNC_CONTEXT *
0x180050a74  call    ?LocalWfdAsyncContextPendingMarkIdle@@YAKPEAU_WFD_API_ASYNC_CONTEXT@@@Z; LocalWfdAsyncContextPendingMarkIdle(_WFD_API_ASYNC_CONTEXT *)
0x180050a79  mov     rax, [rdi+10h]
0x180050a7d  mov     [r12], rax
0x180050a81  mov     [rsp+128h+var_A8], 0
0x180050a8d  mov     r10, cs:WPP_GLOBAL_Control
0x180050a94  mov     ecx, ebx; unsigned int
0x180050a96  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x180050a9b  mov     ebx, eax
0x180050a9d  jmp     short loc_180050AE1
0x180050a9f  cmp     r10, r14
0x180050aa2  jz      short loc_180050ADC
0x180050aa4  cmp     byte ptr [r10+69h], 1
0x180050aa9  jb      short loc_180050ADC
0x180050aab  test    dword ptr [r10+6Ch], 1000h
0x180050ab3  jz      short loc_180050ADC
0x180050ab5  mov     [rsp+128h+var_F0], r12
0x180050aba  mov     [rsp+128h+var_F8], r15
0x180050abf  mov     [rsp+128h+var_100], rdi
0x180050ac4  mov     [rsp+128h+var_108], r13
0x180050ac9  mov     r9, rbx
0x180050acc  mov     rcx, [r10+60h]
0x180050ad0  call    WPP_SF_qqqqq
0x180050ad5  mov     r10, cs:WPP_GLOBAL_Control
0x180050adc  mov     ebx, 57h ; 'W'
0x180050ae1  mov     rdi, [rsp+128h+var_A8]
0x180050ae9  test    rdi, rdi
0x180050aec  jz      short loc_180050AFD
0x180050aee  mov     rcx, rdi; struct _WFD_API_ASYNC_CONTEXT *
0x180050af1  call    ?LocalWfdAsyncContextDeref@@YAKPEAU_WFD_API_ASYNC_CONTEXT@@@Z; LocalWfdAsyncContextDeref(_WFD_API_ASYNC_CONTEXT *)
0x180050af6  mov     r10, cs:WPP_GLOBAL_Control
0x180050afd  test    ebx, ebx
0x180050aff  jz      short loc_180050B36
0x180050b01  cmp     r10, r14
0x180050b04  jz      short loc_180050B61
0x180050b06  cmp     byte ptr [r10+69h], 1
0x180050b0b  jb      short loc_180050B36
0x180050b0d  test    dword ptr [r10+6Ch], 1000h
0x180050b15  jz      short loc_180050B36
0x180050b17  mov     edx, 85h
0x180050b1c  mov     r9d, ebx
0x180050b1f  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180050b26  mov     rcx, [r10+60h]
0x180050b2a  call    WPP_SF_d
0x180050b2f  mov     r10, cs:WPP_GLOBAL_Control
0x180050b36  cmp     r10, r14
0x180050b39  jz      short loc_180050B61
0x180050b3b  cmp     byte ptr [r10+69h], 4
0x180050b40  jb      short loc_180050B61
0x180050b42  test    byte ptr [r10+6Ch], 2
0x180050b47  jz      short loc_180050B61
0x180050b49  mov     edx, 86h
0x180050b4e  mov     r9d, ebx
0x180050b51  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180050b58  mov     rcx, [r10+60h]
0x180050b5c  call    WPP_SF_d
0x180050b61  mov     eax, ebx
0x180050b63  mov     rcx, [rsp+128h+var_40]
0x180050b6b  xor     rcx, rsp; StackCookie
0x180050b6e  call    __security_check_cookie
0x180050b73  add     rsp, 0F8h
0x180050b7a  pop     r15
0x180050b7c  pop     r14
0x180050b7e  pop     r13
0x180050b80  pop     r12
0x180050b82  pop     rdi
0x180050b83  pop     rbx
0x180050b84  retn
0x1800619cd  push    rbp
0x1800619cf  sub     rsp, 80h
0x1800619d6  mov     rbp, rdx
0x1800619d9  mov     rcx, [rcx]
0x1800619dc  mov     ecx, [rcx]; ExceptionCode
0x1800619de  call    cs:__imp_RpcExceptionFilter
0x1800619e4  nop
0x1800619e5  add     rsp, 80h
0x1800619ec  pop     rbp
0x1800619ed  retn
```
