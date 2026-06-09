# WFDSvcLowPrivOpenSeekerSessionLib(void *,ulong,ushort const *,uchar (*)[6],ulong,ulong *,void * *)

- ea: `0x180059558`
- end: `0x18005989f`
- name: `?WFDSvcLowPrivOpenSeekerSessionLib@@YAKPEAXKPEBGPEAY05EKPEAKPEAPEAX@Z`
- size: `839`
- prototype: `unsigned int __usercall@<eax>(void *@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned __int8 (*)[6]@<r9>, unsigned int, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18002d2a0`

## callees

- `0x1800038d0`
- `0x1800063a0`
- `0x180006934`
- `0x1800132cc`
- `0x180019a20`
- `0x180043d68`
- `0x18004fe34`
- `0x18004ffb8`
- `0x180059558`
- `0x18005ab64`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005970c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005970c`
- `RPCRT4!NdrClientCall3` at `0x180059768`
- `RPCRT4!NdrClientCall3` at `0x180059768`
- `RPCRT4!RpcExceptionFilter` at `0x1800610ba`
- `RPCRT4!RpcExceptionFilter` at `0x1800610ba`

## pseudocode

```c
__int64 __fastcall WFDSvcLowPrivOpenSeekerSessionLib(
        void *a1,
        int a2,
        const unsigned __int16 *a3,
        unsigned __int8 (*a4)[6],
        unsigned int a5,
        unsigned int *a6,
        void **a7)
{
  union DOT11_OUI_HEADER *v10; // r10
  unsigned int v11; // edi
  __int64 v12; // rdx
  struct _WFD_API_ASYNC_CONTEXT *v13; // rbx
  int v14; // ecx
  __int64 v15; // rdx
  struct _WFD_API_ASYNC_CONTEXT *v16; // rbx
  struct _WFD_API_ASYNC_CONTEXT *v18; // [rsp+60h] [rbp-78h] BYREF
  int v19; // [rsp+68h] [rbp-70h]
  int Pointer; // [rsp+6Ch] [rbp-6Ch]
  CLIENT_CALL_RETURN v21; // [rsp+70h] [rbp-68h]
  void **v22; // [rsp+78h] [rbp-60h]
  GUID ActivityId; // [rsp+80h] [rbp-58h] BYREF

  v19 = a2;
  v22 = a7;
  v18 = 0;
  ActivityId = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 397, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  if ( a1 && a3 && a4 && a7 && a6 )
  {
    if ( v10 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v10 + 105) >= 3u
      && (*((_DWORD *)v10 + 27) & 0x1000) != 0 )
    {
      WPP_SF__MAC_D(*((_QWORD *)v10 + 12), 399, a3, (unsigned __int8 *)a4, a5);
    }
    v11 = LocalWfdAsyncContextCreateInternal(a1, &v18, 1);
    if ( v11 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
      {
        v12 = 400;
LABEL_29:
        WPP_SF_(*((_QWORD *)v10 + 12), v12, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
        goto LABEL_30;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
      {
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          401,
          WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids,
          *((_QWORD *)v18 + 2));
      }
      v13 = v18;
      *(_DWORD *)v18 = 7;
      *((_DWORD *)v13 + 38) = *(_DWORD *)a4;
      *((_WORD *)v13 + 78) = *(_WORD *)&(*a4)[4];
      *((_DWORD *)v13 + 40) = a5;
      EventActivityIdControl(1u, &ActivityId);
      v14 = *((_DWORD *)v13 + 40);
      v15 = **((_QWORD **)v13 + 1);
      v21.Simple = 0;
      v21.Pointer = NdrClientCall3(
                      (MIDL_STUBLESS_PROXY_INFO *)&winwlan_lowpriv_ProxyInfo,
                      0x1Au,
                      0,
                      &ActivityId,
                      v15,
                      v19,
                      a3,
                      (char *)v13 + 152,
                      v14,
                      a6,
                      (char *)v13 + 168).Pointer;
      Pointer = (int)v21.Pointer;
      v11 = ServiceStatus((unsigned int)v21.Pointer);
      if ( !v11 )
      {
        v16 = v18;
        LocalWfdAsyncContextPendingMarkIdle(v18);
        *a7 = (void *)*((_QWORD *)v16 + 2);
LABEL_30:
        v10 = WPP_GLOBAL_Control;
      }
    }
  }
  else
  {
    v11 = 87;
    if ( v10 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v10 + 105)
      && (*((_DWORD *)v10 + 27) & 0x1000) != 0 )
    {
      v12 = 398;
      goto LABEL_29;
    }
  }
  if ( v11 && v18 )
  {
    LocalWfdAsyncContextDeref(v18);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v10 + 105) >= 4u
    && (*((_BYTE *)v10 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v10 + 12), 403, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x180059558  mov     r11, rsp
0x18005955b  push    rbx
0x18005955c  push    rsi
0x18005955d  push    rdi
0x18005955e  push    r12
0x180059560  push    r13
0x180059562  push    r14
0x180059564  push    r15
0x180059566  sub     rsp, 0A0h
0x18005956d  mov     rax, cs:__security_cookie
0x180059574  xor     rax, rsp
0x180059577  mov     [rsp+0D8h+var_48], rax
0x18005957f  mov     r15, r9
0x180059582  mov     r12, r8
0x180059585  mov     [rsp+0D8h+var_70], edx
0x180059589  mov     rbx, rcx
0x18005958c  mov     r13, [rsp+0D8h+arg_28]
0x180059594  mov     r14, [rsp+0D8h+arg_30]
0x18005959c  mov     [rsp+0D8h+var_60], r14
0x1800595a1  mov     qword ptr [r11-78h], 0
0x1800595a9  xorps   xmm0, xmm0
0x1800595ac  movups  xmmword ptr [r11-58h], xmm0
0x1800595b1  lea     rsi, WPP_GLOBAL_Control
0x1800595b8  mov     r10, cs:WPP_GLOBAL_Control
0x1800595bf  cmp     r10, rsi
0x1800595c2  jz      short loc_1800595EE
0x1800595c4  cmp     byte ptr [r10+69h], 4
0x1800595c9  jb      short loc_1800595EE
0x1800595cb  test    byte ptr [r10+6Ch], 2
0x1800595d0  jz      short loc_1800595EE
0x1800595d2  mov     edx, 18Dh
0x1800595d7  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800595de  mov     rcx, [r10+60h]
0x1800595e2  call    WPP_SF_
0x1800595e7  mov     r10, cs:WPP_GLOBAL_Control
0x1800595ee  test    rbx, rbx
0x1800595f1  jz      loc_1800597FB
0x1800595f7  test    r12, r12
0x1800595fa  jz      loc_1800597FB
0x180059600  test    r15, r15
0x180059603  jz      loc_1800597FB
0x180059609  test    r14, r14
0x18005960c  jz      loc_1800597FB
0x180059612  test    r13, r13
0x180059615  jz      loc_1800597FB
0x18005961b  cmp     r10, rsi
0x18005961e  jz      short loc_18005964D
0x180059620  cmp     byte ptr [r10+69h], 3
0x180059625  jb      short loc_18005964D
0x180059627  test    dword ptr [r10+6Ch], 1000h
0x18005962f  jz      short loc_18005964D
0x180059631  mov     edx, 18Fh
0x180059636  mov     eax, [rsp+0D8h+arg_20]
0x18005963d  mov     dword ptr [rsp+0D8h+var_B8], eax
0x180059641  mov     r9, r15
0x180059644  mov     rcx, [r10+60h]
0x180059648  call    WPP_SF__MAC_D
0x18005964d  mov     r8d, 1; int
0x180059653  lea     rdx, [rsp+0D8h+var_78]; struct _WFD_API_ASYNC_CONTEXT **
0x180059658  mov     rcx, rbx; void *
0x18005965b  call    ?LocalWfdAsyncContextCreateInternal@@YAKPEAXPEAPEAU_WFD_API_ASYNC_CONTEXT@@H@Z; LocalWfdAsyncContextCreateInternal(void *,_WFD_API_ASYNC_CONTEXT * *,int)
0x180059660  mov     edi, eax
0x180059662  test    eax, eax
0x180059664  jz      short loc_180059699
0x180059666  mov     r10, cs:WPP_GLOBAL_Control
0x18005966d  cmp     r10, rsi
0x180059670  jz      loc_180059832
0x180059676  cmp     byte ptr [r10+69h], 1
0x18005967b  jb      loc_180059832
0x180059681  test    dword ptr [r10+6Ch], 1000h
0x180059689  jz      loc_180059832
0x18005968f  mov     edx, 190h
0x180059694  jmp     loc_18005981B
0x180059699  mov     rcx, cs:WPP_GLOBAL_Control
0x1800596a0  cmp     rcx, rsi
0x1800596a3  jz      short loc_1800596D2
0x1800596a5  cmp     byte ptr [rcx+69h], 3
0x1800596a9  jb      short loc_1800596D2
0x1800596ab  test    dword ptr [rcx+6Ch], 1000h
0x1800596b2  jz      short loc_1800596D2
0x1800596b4  mov     edx, 191h
0x1800596b9  mov     r9, [rsp+0D8h+var_78]
0x1800596be  mov     r9, [r9+10h]
0x1800596c2  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800596c9  mov     rcx, [rcx+60h]
0x1800596cd  call    WPP_SF_q
0x1800596d2  mov     rbx, [rsp+0D8h+var_78]
0x1800596d7  mov     dword ptr [rbx], 7
0x1800596dd  lea     rdi, [rbx+98h]
0x1800596e4  mov     eax, [r15]
0x1800596e7  mov     [rdi], eax
0x1800596e9  movzx   eax, word ptr [r15+4]
0x1800596ee  mov     [rdi+4], ax
0x1800596f2  mov     eax, [rsp+0D8h+arg_20]
0x1800596f9  mov     [rbx+0A0h], eax
0x1800596ff  lea     rdx, [rsp+0D8h+ActivityId]; ActivityId
0x180059707  mov     ecx, 1; ControlCode
0x18005970c  call    cs:__imp_EventActivityIdControl
0x180059712  nop
0x180059713  mov     ecx, [rbx+0A0h]
0x180059719  mov     rax, [rbx+8]
0x18005971d  mov     rdx, [rax]
0x180059720  mov     [rsp+0D8h+var_68], 0
0x180059729  lea     rax, [rdi+10h]
0x18005972d  mov     [rsp+0D8h+var_88], rax
0x180059732  mov     [rsp+0D8h+var_90], r13
0x180059737  mov     [rsp+0D8h+var_98], ecx
0x18005973b  mov     [rsp+0D8h+var_A0], rdi
0x180059740  mov     [rsp+0D8h+var_A8], r12
0x180059745  mov     eax, [rsp+0D8h+var_70]
0x180059749  mov     [rsp+0D8h+var_B0], eax
0x18005974d  mov     [rsp+0D8h+var_B8], rdx
0x180059752  lea     r9, [rsp+0D8h+ActivityId]
0x18005975a  xor     r8d, r8d; pReturnValue
0x18005975d  lea     edx, [r8+1Ah]; nProcNum
0x180059761  lea     rcx, ?winwlan_lowpriv_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180059768  call    cs:__imp_NdrClientCall3
0x18005976e  mov     rbx, rax
0x180059771  mov     [rsp+0D8h+var_68], rax
0x180059776  mov     [rsp+0D8h+var_6C], eax
0x18005977a  mov     r10, cs:WPP_GLOBAL_Control
0x180059781  jmp     short loc_1800597D8
0x180059783  mov     ebx, eax
0x180059785  mov     [rsp+0D8h+var_6C], eax
0x180059789  lea     rcx, WPP_GLOBAL_Control
0x180059790  mov     r10, cs:WPP_GLOBAL_Control
0x180059797  cmp     r10, rcx
0x18005979a  jz      short loc_1800597CC
0x18005979c  cmp     byte ptr [r10+69h], 1
0x1800597a1  jb      short loc_1800597CC
0x1800597a3  test    dword ptr [r10+6Ch], 1000h
0x1800597ab  jz      short loc_1800597CC
0x1800597ad  mov     edx, 192h
0x1800597b2  mov     r9d, eax
0x1800597b5  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800597bc  mov     rcx, [r10+60h]
0x1800597c0  call    WPP_SF_d
0x1800597c5  mov     r10, cs:WPP_GLOBAL_Control
0x1800597cc  lea     rsi, WPP_GLOBAL_Control
0x1800597d3  mov     r14, [rsp+0D8h+var_60]
0x1800597d8  mov     ecx, ebx; unsigned int
0x1800597da  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x1800597df  mov     edi, eax
0x1800597e1  test    eax, eax
0x1800597e3  jnz     short loc_180059832
0x1800597e5  mov     rbx, [rsp+0D8h+var_78]
0x1800597ea  mov     rcx, rbx; struct _WFD_API_ASYNC_CONTEXT *
0x1800597ed  call    ?LocalWfdAsyncContextPendingMarkIdle@@YAKPEAU_WFD_API_ASYNC_CONTEXT@@@Z; LocalWfdAsyncContextPendingMarkIdle(_WFD_API_ASYNC_CONTEXT *)
0x1800597f2  mov     rax, [rbx+10h]
0x1800597f6  mov     [r14], rax
0x1800597f9  jmp     short loc_18005982B
0x1800597fb  mov     edi, 57h ; 'W'
0x180059800  cmp     r10, rsi
0x180059803  jz      short loc_180059832
0x180059805  cmp     byte ptr [r10+69h], 1
0x18005980a  jb      short loc_180059832
0x18005980c  test    dword ptr [r10+6Ch], 1000h
0x180059814  jz      short loc_180059832
0x180059816  mov     edx, 18Eh
0x18005981b  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180059822  mov     rcx, [r10+60h]
0x180059826  call    WPP_SF_
0x18005982b  mov     r10, cs:WPP_GLOBAL_Control
0x180059832  test    edi, edi
0x180059834  jz      short loc_18005984F
0x180059836  mov     rbx, [rsp+0D8h+var_78]
0x18005983b  test    rbx, rbx
0x18005983e  jz      short loc_18005984F
0x180059840  mov     rcx, rbx; struct _WFD_API_ASYNC_CONTEXT *
0x180059843  call    ?LocalWfdAsyncContextDeref@@YAKPEAU_WFD_API_ASYNC_CONTEXT@@@Z; LocalWfdAsyncContextDeref(_WFD_API_ASYNC_CONTEXT *)
0x180059848  mov     r10, cs:WPP_GLOBAL_Control
0x18005984f  cmp     r10, rsi
0x180059852  jz      short loc_18005987A
0x180059854  cmp     byte ptr [r10+69h], 4
0x180059859  jb      short loc_18005987A
0x18005985b  test    byte ptr [r10+6Ch], 2
0x180059860  jz      short loc_18005987A
0x180059862  mov     edx, 193h
0x180059867  mov     r9d, edi
0x18005986a  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180059871  mov     rcx, [r10+60h]
0x180059875  call    WPP_SF_d
0x18005987a  mov     eax, edi
0x18005987c  mov     rcx, [rsp+0D8h+var_48]
0x180059884  xor     rcx, rsp; StackCookie
0x180059887  call    __security_check_cookie
0x18005988c  add     rsp, 0A0h
0x180059893  pop     r15
0x180059895  pop     r14
0x180059897  pop     r13
0x180059899  pop     r12
0x18005989b  pop     rdi
0x18005989c  pop     rsi
0x18005989d  pop     rbx
0x18005989e  retn
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
