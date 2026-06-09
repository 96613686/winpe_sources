# WFDPairEnumerateCeremoniesLib(void *,uchar (*)[6],_WFD_PAIRING_PARAMETERS *,_WFD_FIREWALL_CONFIGURATION_PARAMETERS const *,void * *,_DOT11_WPS_CONFIG_METHOD *,ulong *)

- ea: `0x180055d20`
- end: `0x1800560c6`
- name: `?WFDPairEnumerateCeremoniesLib@@YAKPEAXPEAY05EPEAU_WFD_PAIRING_PARAMETERS@@PEBU_WFD_FIREWALL_CONFIGURATION_PARAMETERS@@PEAPEAXPEAW4_DOT11_WPS_CONFIG_METHOD@@PEAK@Z`
- size: `934`
- prototype: `unsigned int __usercall@<eax>(void *@<rcx>, unsigned __int8 (*)[6]@<rdx>, struct _WFD_PAIRING_PARAMETERS *@<r8>, const struct _WFD_FIREWALL_CONFIGURATION_PARAMETERS *@<r9>, void **, enum _DOT11_WPS_CONFIG_METHOD *, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18002c4b0`
- `0x18002c7a0`

## callees

- `0x1800038d0`
- `0x1800063a0`
- `0x180006934`
- `0x1800132cc`
- `0x180019a20`
- `0x18001a5bc`
- `0x18004fe34`
- `0x180055d20`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180055f65`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180055f65`
- `RPCRT4!NdrClientCall3` at `0x180055fd6`
- `RPCRT4!NdrClientCall3` at `0x180055fd6`

## pseudocode

```c
__int64 __fastcall WFDPairEnumerateCeremoniesLib(
        void *a1,
        unsigned __int8 (*a2)[6],
        struct _WFD_PAIRING_PARAMETERS *a3,
        const struct _WFD_FIREWALL_CONFIGURATION_PARAMETERS *a4,
        void **a5,
        enum _DOT11_WPS_CONFIG_METHOD *a6,
        unsigned int *a7)
{
  union DOT11_OUI_HEADER *v10; // rcx
  unsigned int v11; // ebx
  struct _WFD_PAIRING_PARAMETERS *v12; // r15
  __int64 v13; // rdx
  struct _WFD_API_ASYNC_CONTEXT *v14; // rsi
  __int64 v15; // rcx
  struct _WFD_API_ASYNC_CONTEXT *v16; // rsi
  struct _WFD_API_ASYNC_CONTEXT *v18; // [rsp+60h] [rbp-118h] BYREF
  int Pointer; // [rsp+68h] [rbp-110h]
  unsigned int *v20; // [rsp+70h] [rbp-108h]
  __int64 v21; // [rsp+78h] [rbp-100h] BYREF
  enum _DOT11_WPS_CONFIG_METHOD *v22; // [rsp+80h] [rbp-F8h]
  const struct _WFD_FIREWALL_CONFIGURATION_PARAMETERS *v23; // [rsp+88h] [rbp-F0h]
  unsigned __int8 *v24; // [rsp+90h] [rbp-E8h]
  CLIENT_CALL_RETURN v25; // [rsp+98h] [rbp-E0h]
  void **v26; // [rsp+A0h] [rbp-D8h]
  GUID ActivityId; // [rsp+A8h] [rbp-D0h] BYREF
  _OWORD v28[4]; // [rsp+C0h] [rbp-B8h] BYREF
  _OWORD v29[2]; // [rsp+100h] [rbp-78h]
  __int64 v30; // [rsp+120h] [rbp-58h]

  v23 = a4;
  v24 = (unsigned __int8 *)a2;
  v26 = a5;
  v22 = a6;
  v20 = a7;
  v21 = 0;
  v18 = 0;
  LOBYTE(v28[0]) = 0;
  memset_0((char *)v28 + 1, 0, 0x6Fu);
  ActivityId = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 152, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  if ( !a1 || !a2 || !a5 || !a6 || !v20 )
  {
    v11 = 87;
    if ( v10 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v10 + 105)
      && (*((_DWORD *)v10 + 27) & 0x1000) != 0 )
    {
      v13 = 153;
      goto LABEL_36;
    }
    goto LABEL_38;
  }
  v11 = 0;
  v12 = 0;
  if ( a3 )
  {
    if ( *((_BYTE *)a3 + 1) )
    {
      if ( *((_BYTE *)a3 + 1) != 1 )
      {
        v11 = 87;
        if ( *((_BYTE *)a3 + 1) == 2 )
        {
          v11 = *((_WORD *)a3 + 1) < 0x70u ? 0x57 : 0;
          v12 = a3;
          if ( *((_WORD *)a3 + 1) < 0x70u )
            v12 = 0;
        }
        goto LABEL_20;
      }
      if ( *((_WORD *)a3 + 1) < 0x5Cu )
      {
        v11 = 87;
LABEL_21:
        if ( v10 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)v10 + 105)
          && (*((_DWORD *)v10 + 27) & 0x1000) != 0 )
        {
          v13 = 154;
LABEL_36:
          WPP_SF_(*((_QWORD *)v10 + 12), v13, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
LABEL_37:
          v10 = WPP_GLOBAL_Control;
          goto LABEL_38;
        }
        goto LABEL_38;
      }
    }
    v28[0] = *(_OWORD *)a3;
    v28[1] = *((_OWORD *)a3 + 1);
    v28[2] = *((_OWORD *)a3 + 2);
    v28[3] = *((_OWORD *)a3 + 3);
    v29[0] = *((_OWORD *)a3 + 4);
    *(_OWORD *)((char *)v29 + 12) = *(_OWORD *)((char *)a3 + 76);
    LODWORD(v28[0]) = 7340545;
    v30 = 0;
    v12 = (struct _WFD_PAIRING_PARAMETERS *)v28;
  }
LABEL_20:
  if ( v11 )
    goto LABEL_21;
  v11 = LocalWfdAsyncContextCreateInternal(a1, &v18, 0);
  if ( !v11 )
  {
    v14 = v18;
    *(_DWORD *)v18 = 3;
    EventActivityIdControl(1u, &ActivityId);
    v15 = **((_QWORD **)v14 + 1);
    v25.Simple = 0;
    v25.Pointer = NdrClientCall3(
                    (MIDL_STUBLESS_PROXY_INFO *)&winwlan_ProxyInfo,
                    0x52u,
                    0,
                    &ActivityId,
                    v15,
                    v24,
                    v12,
                    v23,
                    &v21,
                    v22,
                    v20).Pointer;
    Pointer = (int)v25.Pointer;
    v11 = ServiceStatus((unsigned int)v25.Pointer);
    if ( !v11 )
    {
      v16 = v18;
      *((_QWORD *)v18 + 20) = v21;
      *a5 = (void *)*((_QWORD *)v16 + 2);
      v18 = 0;
    }
    goto LABEL_37;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105)
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
  {
    v13 = 155;
    goto LABEL_36;
  }
LABEL_38:
  if ( v18 )
  {
    LocalWfdAsyncContextDeref(v18);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v10 + 105) >= 4u
    && (*((_BYTE *)v10 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v10 + 12), 156, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x180055d20  push    rbx
0x180055d22  push    rsi
0x180055d23  push    rdi
0x180055d24  push    r12
0x180055d26  push    r13
0x180055d28  push    r14
0x180055d2a  push    r15
0x180055d2c  sub     rsp, 140h
0x180055d33  mov     rax, cs:__security_cookie
0x180055d3a  xor     rax, rsp
0x180055d3d  mov     [rsp+178h+var_48], rax
0x180055d45  mov     [rsp+178h+var_F0], r9
0x180055d4d  mov     rsi, r8
0x180055d50  mov     rbx, rdx
0x180055d53  mov     [rsp+178h+var_E8], rdx
0x180055d5b  mov     r13, rcx
0x180055d5e  mov     r12, [rsp+178h+arg_20]
0x180055d66  mov     [rsp+178h+var_D8], r12
0x180055d6e  mov     r15, [rsp+178h+arg_28]
0x180055d76  mov     [rsp+178h+var_F8], r15
0x180055d7e  mov     rax, [rsp+178h+arg_30]
0x180055d86  mov     [rsp+178h+var_108], rax
0x180055d8b  xor     edi, edi
0x180055d8d  mov     [rsp+178h+var_100], rdi
0x180055d92  mov     [rsp+178h+var_118], rdi
0x180055d97  mov     byte ptr [rsp+178h+var_B8], dil
0x180055d9f  xor     edx, edx; Val
0x180055da1  lea     r8d, [rdi+6Fh]; Size
0x180055da5  lea     rcx, [rsp+178h+var_B8+1]; void *
0x180055dad  call    memset_0
0x180055db2  xorps   xmm0, xmm0
0x180055db5  movups  xmmword ptr [rsp+178h+ActivityId.Data1], xmm0
0x180055dbd  lea     r14, WPP_GLOBAL_Control
0x180055dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180055dcb  cmp     rcx, r14
0x180055dce  jz      short loc_180055DF8
0x180055dd0  cmp     byte ptr [rcx+69h], 4
0x180055dd4  jb      short loc_180055DF8
0x180055dd6  test    byte ptr [rcx+6Ch], 2
0x180055dda  jz      short loc_180055DF8
0x180055ddc  mov     edx, 98h
0x180055de1  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180055de8  mov     rcx, [rcx+60h]
0x180055dec  call    WPP_SF_
0x180055df1  mov     rcx, cs:WPP_GLOBAL_Control
0x180055df8  test    r13, r13
0x180055dfb  jz      loc_18005602C
0x180055e01  test    rbx, rbx
0x180055e04  jz      loc_18005602C
0x180055e0a  test    r12, r12
0x180055e0d  jz      loc_18005602C
0x180055e13  test    r15, r15
0x180055e16  jz      loc_18005602C
0x180055e1c  cmp     [rsp+178h+var_108], rdi
0x180055e21  jz      loc_18005602C
0x180055e27  mov     ebx, edi
0x180055e29  mov     r15, rdi
0x180055e2c  test    rsi, rsi
0x180055e2f  jz      loc_180055ED8
0x180055e35  movzx   edx, byte ptr [rsi+1]
0x180055e39  test    edx, edx
0x180055e3b  jz      short loc_180055E76
0x180055e3d  sub     edx, 1
0x180055e40  jz      short loc_180055E68
0x180055e42  mov     ebx, 57h ; 'W'
0x180055e47  cmp     edx, 1
0x180055e4a  jnz     loc_180055ED8
0x180055e50  lea     edx, [rbx+19h]
0x180055e53  cmp     [rsi+2], dx
0x180055e57  sbb     eax, eax
0x180055e59  and     ebx, eax
0x180055e5b  mov     r15, rsi
0x180055e5e  cmp     [rsi+2], dx
0x180055e62  cmovb   r15, rdi
0x180055e66  jmp     short loc_180055ED8
0x180055e68  cmp     word ptr [rsi+2], 5Ch ; '\'
0x180055e6d  jnb     short loc_180055E76
0x180055e6f  mov     ebx, 57h ; 'W'
0x180055e74  jmp     short loc_180055EDC
0x180055e76  movups  xmm0, xmmword ptr [rsi]
0x180055e79  movaps  [rsp+178h+var_B8], xmm0
0x180055e81  movups  xmm1, xmmword ptr [rsi+10h]
0x180055e85  movaps  [rsp+178h+var_A8], xmm1
0x180055e8d  movups  xmm0, xmmword ptr [rsi+20h]
0x180055e91  movaps  [rsp+178h+var_98], xmm0
0x180055e99  movups  xmm1, xmmword ptr [rsi+30h]
0x180055e9d  movaps  [rsp+178h+var_88], xmm1
0x180055ea5  movups  xmm0, xmmword ptr [rsi+40h]
0x180055ea9  movaps  xmmword ptr [rsp+178h+var_78], xmm0
0x180055eb1  movups  xmm1, xmmword ptr [rsi+4Ch]
0x180055eb5  movups  xmmword ptr [rsp+178h+var_78+0Ch], xmm1
0x180055ebd  mov     dword ptr [rsp+178h+var_B8], 700201h
0x180055ec8  mov     [rsp+178h+var_58], rdi
0x180055ed0  lea     r15, [rsp+178h+var_B8]
0x180055ed8  test    ebx, ebx
0x180055eda  jz      short loc_180055F06
0x180055edc  cmp     rcx, r14
0x180055edf  jz      loc_18005605F
0x180055ee5  cmp     byte ptr [rcx+69h], 1
0x180055ee9  jb      loc_18005605F
0x180055eef  test    dword ptr [rcx+6Ch], 1000h
0x180055ef6  jz      loc_18005605F
0x180055efc  mov     edx, 9Ah
0x180055f01  jmp     loc_180056048
0x180055f06  xor     r8d, r8d; int
0x180055f09  lea     rdx, [rsp+178h+var_118]; struct _WFD_API_ASYNC_CONTEXT **
0x180055f0e  mov     rcx, r13; void *
0x180055f11  call    ?LocalWfdAsyncContextCreateInternal@@YAKPEAXPEAPEAU_WFD_API_ASYNC_CONTEXT@@H@Z; LocalWfdAsyncContextCreateInternal(void *,_WFD_API_ASYNC_CONTEXT * *,int)
0x180055f16  mov     ebx, eax
0x180055f18  test    eax, eax
0x180055f1a  jz      short loc_180055F4D
0x180055f1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f23  cmp     rcx, r14
0x180055f26  jz      loc_18005605F
0x180055f2c  cmp     byte ptr [rcx+69h], 1
0x180055f30  jb      loc_18005605F
0x180055f36  test    dword ptr [rcx+6Ch], 1000h
0x180055f3d  jz      loc_18005605F
0x180055f43  mov     edx, 9Bh
0x180055f48  jmp     loc_180056048
0x180055f4d  mov     rsi, [rsp+178h+var_118]
0x180055f52  mov     dword ptr [rsi], 3
0x180055f58  lea     rdx, [rsp+178h+ActivityId]; ActivityId
0x180055f60  mov     ecx, 1; ControlCode
0x180055f65  call    cs:__imp_EventActivityIdControl
0x180055f6b  nop
0x180055f6c  mov     rax, [rsi+8]
0x180055f70  mov     rcx, [rax]
0x180055f73  mov     [rsp+178h+var_E0], rdi
0x180055f7b  mov     rax, [rsp+178h+var_108]
0x180055f80  mov     [rsp+178h+var_128], rax
0x180055f85  mov     rax, [rsp+178h+var_F8]
0x180055f8d  mov     [rsp+178h+var_130], rax
0x180055f92  lea     rax, [rsp+178h+var_100]
0x180055f97  mov     [rsp+178h+var_138], rax
0x180055f9c  mov     rax, [rsp+178h+var_F0]
0x180055fa4  mov     [rsp+178h+var_140], rax
0x180055fa9  mov     [rsp+178h+var_148], r15
0x180055fae  mov     rax, [rsp+178h+var_E8]
0x180055fb6  mov     [rsp+178h+var_150], rax
0x180055fbb  mov     [rsp+178h+var_158], rcx
0x180055fc0  lea     r9, [rsp+178h+ActivityId]
0x180055fc8  xor     r8d, r8d; pReturnValue
0x180055fcb  lea     edx, [r8+52h]; nProcNum
0x180055fcf  lea     rcx, ?winwlan_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180055fd6  call    cs:__imp_NdrClientCall3
0x180055fdc  mov     [rsp+178h+var_E0], rax
0x180055fe4  mov     [rsp+178h+var_110], eax
0x180055fe8  jmp     short loc_180055FFF
0x180055fea  mov     [rsp+178h+var_110], eax
0x180055fee  xor     edi, edi
0x180055ff0  lea     r14, WPP_GLOBAL_Control
0x180055ff7  mov     r12, [rsp+178h+var_D8]
0x180055fff  mov     ecx, eax; unsigned int
0x180056001  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x180056006  mov     ebx, eax
0x180056008  test    eax, eax
0x18005600a  jnz     short loc_180056058
0x18005600c  mov     rax, [rsp+178h+var_100]
0x180056011  mov     rsi, [rsp+178h+var_118]
0x180056016  mov     [rsi+0A0h], rax
0x18005601d  mov     rax, [rsi+10h]
0x180056021  mov     [r12], rax
0x180056025  mov     [rsp+178h+var_118], rdi
0x18005602a  jmp     short loc_180056058
0x18005602c  mov     ebx, 57h ; 'W'
0x180056031  cmp     rcx, r14
0x180056034  jz      short loc_18005605F
0x180056036  cmp     byte ptr [rcx+69h], 1
0x18005603a  jb      short loc_18005605F
0x18005603c  test    dword ptr [rcx+6Ch], 1000h
0x180056043  jz      short loc_18005605F
0x180056045  lea     edx, [rbx+42h]
0x180056048  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18005604f  mov     rcx, [rcx+60h]
0x180056053  call    WPP_SF_
0x180056058  mov     rcx, cs:WPP_GLOBAL_Control
0x18005605f  mov     rsi, [rsp+178h+var_118]
0x180056064  test    rsi, rsi
0x180056067  jz      short loc_180056078
0x180056069  mov     rcx, rsi; struct _WFD_API_ASYNC_CONTEXT *
0x18005606c  call    ?LocalWfdAsyncContextDeref@@YAKPEAU_WFD_API_ASYNC_CONTEXT@@@Z; LocalWfdAsyncContextDeref(_WFD_API_ASYNC_CONTEXT *)
0x180056071  mov     rcx, cs:WPP_GLOBAL_Control
0x180056078  cmp     rcx, r14
0x18005607b  jz      short loc_1800560A1
0x18005607d  cmp     byte ptr [rcx+69h], 4
0x180056081  jb      short loc_1800560A1
0x180056083  test    byte ptr [rcx+6Ch], 2
0x180056087  jz      short loc_1800560A1
0x180056089  mov     edx, 9Ch
0x18005608e  mov     r9d, ebx
0x180056091  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180056098  mov     rcx, [rcx+60h]
0x18005609c  call    WPP_SF_d
0x1800560a1  mov     eax, ebx
0x1800560a3  mov     rcx, [rsp+178h+var_48]
0x1800560ab  xor     rcx, rsp; StackCookie
0x1800560ae  call    __security_check_cookie
0x1800560b3  add     rsp, 140h
0x1800560ba  pop     r15
0x1800560bc  pop     r14
0x1800560be  pop     r13
0x1800560c0  pop     r12
0x1800560c2  pop     rdi
0x1800560c3  pop     rsi
0x1800560c4  pop     rbx
0x1800560c5  retn
0x1800610ac  push    rbp
0x1800610ae  sub     rsp, 60h
0x1800610b2  mov     rbp, rdx
0x1800610b5  mov     rcx, [rcx]
0x1800610b8  mov     ecx, [rcx]; ExceptionCode
0x1800610ba  call    cs:__imp_RpcExceptionFilter
0x1800610c0  nop
0x1800610c1  add     rsp, 60h
0x1800610c5  pop     rbp
0x1800610c6  retn
```
