# WFDLowPrivOpenSessionByDafObjectIdLib(void *,ushort const *,ushort const *,uchar,ulong,_WFD_PAIR_WITH_DEVICE_PREFERENCE,ulong,_DOT11_WPS_CONFIG_METHOD *,void *,void (*)(void *,void *,_GUID,uchar * const,ulong,ulong),void * *)

- ea: `0x180012e84`
- end: `0x1800132c6`
- name: `?WFDLowPrivOpenSessionByDafObjectIdLib@@YAKPEAXPEBG1EKW4_WFD_PAIR_WITH_DEVICE_PREFERENCE@@KPEAW4_DOT11_WPS_CONFIG_METHOD@@0P6AX00U_GUID@@QEAEKK@ZPEAPEAX@Z`
- size: `1090`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002d0f0`

## callees

- `0x1800038d0`
- `0x1800053c0`
- `0x1800063a0`
- `0x180006934`
- `0x180012e84`
- `0x1800132cc`
- `0x180028140`
- `0x180043d68`
- `0x18004fe34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800130c6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800130c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001302a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001302a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180013215`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180013215`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180013014`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180013014`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180013265`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180013265`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180013177`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180013177`
- `RPCRT4!RpcExceptionFilter` at `0x180060a81`
- `RPCRT4!RpcExceptionFilter` at `0x180060a81`

## pseudocode

```c
__int64 __fastcall WFDLowPrivOpenSessionByDafObjectIdLib(
        void *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int8 a4,
        int a5,
        int a6,
        int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        _QWORD *a11)
{
  __int64 v11; // rax
  struct _WFD_API_ASYNC_CONTEXT *v13; // rdi
  struct _TP_WAIT *ThreadpoolWait; // r12
  union DOT11_OUI_HEADER *v15; // r10
  DWORD LastError; // esi
  _QWORD *v17; // r13
  __int64 v18; // r14
  __int64 v20; // [rsp+80h] [rbp-58h]
  struct _WFD_API_ASYNC_CONTEXT *v21; // [rsp+E0h] [rbp+8h] BYREF
  __int64 v22; // [rsp+E8h] [rbp+10h]
  __int64 v23; // [rsp+F0h] [rbp+18h]
  unsigned __int8 v24; // [rsp+F8h] [rbp+20h]

  v24 = a4;
  v23 = a3;
  v22 = a2;
  v11 = a2;
  v13 = 0;
  v21 = 0;
  ThreadpoolWait = 0;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 332, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
    v15 = WPP_GLOBAL_Control;
    v11 = v22;
  }
  if ( a1 && v11 && a6 < 3 && (!a7 || a8) && a10 && a11 )
  {
    if ( v15 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v15 + 105) >= 3u
      && (*((_DWORD *)v15 + 27) & 0x1000) != 0 )
    {
      WPP_SF_S(*((_QWORD *)v15 + 12), 334, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v11);
    }
    LastError = LocalWfdAsyncContextCreateInternal(a1, &v21, 1);
    if ( LastError )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) == 0 )
      {
        v13 = v21;
        goto LABEL_37;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 335, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
      v13 = v21;
      goto LABEL_36;
    }
    v13 = v21;
    v17 = (_QWORD *)((char *)v21 + 16);
    ThreadpoolWait = CreateThreadpoolWait(
                       wfdAsyncCompletionCallback,
                       *((PVOID *)v21 + 2),
                       (PTP_CALLBACK_ENVIRON)(*((_QWORD *)v21 + 1) + 232LL));
    if ( !ThreadpoolWait )
    {
      LastError = GetLastError();
LABEL_36:
      v15 = WPP_GLOBAL_Control;
      goto LABEL_37;
    }
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 336, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, *v17);
    }
    *(_DWORD *)v13 = 2;
    *((_QWORD *)v13 + 3) = a9;
    *((_QWORD *)v13 + 21) = a10;
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)(v22 + 2 * v18) );
    v20 = AllocWLMem(2 * v18 + 2);
    _o_wcsncpy_s(v20, v18 + 1, v22, v18);
    *((_QWORD *)v13 + 19) = v20;
    Ndr64AsyncClientCall(
      (MIDL_STUBLESS_PROXY_INFO *)&winwlan_lowpriv_ProxyInfo,
      0x14u,
      0,
      (char *)v13 + 32,
      **((_QWORD **)v13 + 1),
      v20,
      v23,
      v24,
      a5,
      a6,
      a7,
      a8,
      (char *)v13 + 176,
      (char *)v13 + 192,
      (char *)v13 + 200,
      (char *)v13 + 160);
    LastError = ServiceStatus(LastError);
    if ( !LastError )
    {
      *a11 = *v17;
      SetThreadpoolWait(ThreadpoolWait, *((HANDLE *)v13 + 18), 0);
      ThreadpoolWait = 0;
      goto LABEL_36;
    }
  }
  else
  {
    LastError = 87;
    if ( v15 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v15 + 105)
      && (*((_DWORD *)v15 + 27) & 0x1000) != 0 )
    {
      WPP_SF_(*((_QWORD *)v15 + 12), 333, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
      goto LABEL_36;
    }
  }
LABEL_37:
  if ( LastError )
  {
    if ( ThreadpoolWait )
    {
      CloseThreadpoolWait(ThreadpoolWait);
      v15 = WPP_GLOBAL_Control;
    }
    if ( v13 )
    {
      LocalWfdAsyncContextDeref(v13);
      v15 = WPP_GLOBAL_Control;
    }
  }
  if ( v15 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v15 + 105) >= 4u
    && (*((_BYTE *)v15 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v15 + 12), 338, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180012e84  mov     r11, rsp
0x180012e87  mov     [r11+20h], r9b
0x180012e8b  mov     [r11+18h], r8
0x180012e8f  mov     [r11+10h], rdx
0x180012e93  push    rbx
0x180012e94  push    rsi
0x180012e95  push    rdi
0x180012e96  push    r12
0x180012e98  push    r13
0x180012e9a  push    r14
0x180012e9c  push    r15
0x180012e9e  sub     rsp, 0A0h
0x180012ea5  mov     rax, rdx
0x180012ea8  mov     rsi, rcx
0x180012eab  xor     ebx, ebx
0x180012ead  mov     edi, ebx
0x180012eaf  mov     [r11+8], rbx
0x180012eb3  mov     r12d, ebx
0x180012eb6  lea     r15, WPP_GLOBAL_Control
0x180012ebd  mov     r10, cs:WPP_GLOBAL_Control
0x180012ec4  cmp     r10, r15
0x180012ec7  jz      short loc_180012EFB
0x180012ec9  cmp     byte ptr [r10+69h], 4
0x180012ece  jb      short loc_180012EFB
0x180012ed0  test    byte ptr [r10+6Ch], 2
0x180012ed5  jz      short loc_180012EFB
0x180012ed7  mov     edx, 14Ch
0x180012edc  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180012ee3  mov     rcx, [r10+60h]
0x180012ee7  call    WPP_SF_
0x180012eec  mov     r10, cs:WPP_GLOBAL_Control
0x180012ef3  mov     rax, [rsp+0D8h+arg_8]
0x180012efb  test    rsi, rsi
0x180012efe  jz      loc_180013220
0x180012f04  test    rax, rax
0x180012f07  jz      loc_180013220
0x180012f0d  cmp     [rsp+0D8h+arg_28], 3
0x180012f15  jge     loc_180013220
0x180012f1b  cmp     [rsp+0D8h+arg_30], ebx
0x180012f22  jz      short loc_180012F32
0x180012f24  cmp     [rsp+0D8h+arg_38], rbx
0x180012f2c  jz      loc_180013220
0x180012f32  cmp     [rsp+0D8h+arg_48], rbx
0x180012f3a  jz      loc_180013220
0x180012f40  cmp     [rsp+0D8h+arg_50], rbx
0x180012f48  jz      loc_180013220
0x180012f4e  cmp     r10, r15
0x180012f51  jz      short loc_180012F80
0x180012f53  cmp     byte ptr [r10+69h], 3
0x180012f58  jb      short loc_180012F80
0x180012f5a  mov     r14d, 1000h
0x180012f60  test    [r10+6Ch], r14d
0x180012f64  jz      short loc_180012F86
0x180012f66  mov     edx, 14Eh
0x180012f6b  mov     r9, rax
0x180012f6e  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180012f75  mov     rcx, [r10+60h]
0x180012f79  call    WPP_SF_S
0x180012f7e  jmp     short loc_180012F86
0x180012f80  mov     r14d, 1000h
0x180012f86  mov     r8d, 1; int
0x180012f8c  lea     rdx, [rsp+0D8h+arg_0]; struct _WFD_API_ASYNC_CONTEXT **
0x180012f94  mov     rcx, rsi; void *
0x180012f97  call    ?LocalWfdAsyncContextCreateInternal@@YAKPEAXPEAPEAU_WFD_API_ASYNC_CONTEXT@@H@Z; LocalWfdAsyncContextCreateInternal(void *,_WFD_API_ASYNC_CONTEXT * *,int)
0x180012f9c  mov     esi, eax
0x180012f9e  test    eax, eax
0x180012fa0  jz      short loc_180012FEA
0x180012fa2  mov     r10, cs:WPP_GLOBAL_Control
0x180012fa9  cmp     r10, r15
0x180012fac  jz      short loc_180012FDD
0x180012fae  cmp     byte ptr [r10+69h], 1
0x180012fb3  jb      short loc_180012FDD
0x180012fb5  test    [r10+6Ch], r14d
0x180012fb9  jz      short loc_180012FDD
0x180012fbb  mov     edx, 14Fh
0x180012fc0  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180012fc7  mov     rcx, [r10+60h]
0x180012fcb  call    WPP_SF_
0x180012fd0  mov     rdi, [rsp+0D8h+arg_0]
0x180012fd8  jmp     loc_180013252
0x180012fdd  mov     rdi, [rsp+0D8h+arg_0]
0x180012fe5  jmp     loc_180013259
0x180012fea  mov     rdi, [rsp+0D8h+arg_0]
0x180012ff2  lea     r13, [rdi+10h]
0x180012ff6  mov     [rsp+0D8h+var_48], r13
0x180012ffe  mov     r8, [rdi+8]
0x180013002  add     r8, 0E8h; pcbe
0x180013009  mov     rdx, [r13+0]; pv
0x18001300d  lea     rcx, ?wfdAsyncCompletionCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180013014  call    cs:__imp_CreateThreadpoolWait
0x18001301a  mov     r12, rax
0x18001301d  mov     [rsp+0D8h+var_50], rax
0x180013025  test    rax, rax
0x180013028  jnz     short loc_180013037
0x18001302a  call    cs:__imp_GetLastError
0x180013030  mov     esi, eax
0x180013032  jmp     loc_180013252
0x180013037  mov     rcx, cs:WPP_GLOBAL_Control
0x18001303e  cmp     rcx, r15
0x180013041  jz      short loc_180013068
0x180013043  cmp     byte ptr [rcx+69h], 3
0x180013047  jb      short loc_180013068
0x180013049  test    [rcx+6Ch], r14d
0x18001304d  jz      short loc_180013068
0x18001304f  mov     edx, 150h
0x180013054  mov     r9, [r13+0]
0x180013058  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18001305f  mov     rcx, [rcx+60h]
0x180013063  call    WPP_SF_q
0x180013068  mov     dword ptr [rdi], 2
0x18001306e  mov     rax, [rsp+0D8h+arg_40]
0x180013076  mov     [rdi+18h], rax
0x18001307a  mov     rax, [rsp+0D8h+arg_48]
0x180013082  mov     [rdi+0A8h], rax
0x180013089  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001308d  mov     rax, [rsp+0D8h+arg_8]
0x180013095  inc     r14
0x180013098  cmp     [rax+r14*2], bx
0x18001309d  jnz     short loc_180013095
0x18001309f  lea     rcx, ds:2[r14*2]; dwBytes
0x1800130a7  call    AllocWLMem
0x1800130ac  mov     [rsp+0D8h+var_58], rax
0x1800130b4  lea     rdx, [r14+1]
0x1800130b8  mov     r9, r14
0x1800130bb  mov     r8, [rsp+0D8h+arg_8]
0x1800130c3  mov     rcx, rax
0x1800130c6  call    cs:__imp__o_wcsncpy_s
0x1800130cc  mov     r14, [rsp+0D8h+var_58]
0x1800130d4  mov     [rdi+98h], r14
0x1800130db  lea     rcx, [rdi+0A0h]
0x1800130e2  lea     rdx, [rdi+0C8h]
0x1800130e9  lea     rax, [rdi+0C0h]
0x1800130f0  lea     r8, [rdi+0B0h]
0x1800130f7  movzx   r10d, [rsp+0D8h+arg_18]
0x180013100  mov     r11, [rdi+8]
0x180013104  lea     r9, [rdi+20h]
0x180013108  mov     [rsp+0D8h+var_60], rcx
0x18001310d  mov     [rsp+0D8h+var_68], rdx
0x180013112  mov     [rsp+0D8h+var_70], rax
0x180013117  mov     [rsp+0D8h+var_78], r8
0x18001311c  mov     rax, [rsp+0D8h+arg_38]
0x180013124  mov     [rsp+0D8h+var_80], rax
0x180013129  mov     eax, [rsp+0D8h+arg_30]
0x180013130  mov     [rsp+0D8h+var_88], eax
0x180013134  mov     eax, [rsp+0D8h+arg_28]
0x18001313b  mov     [rsp+0D8h+var_90], eax
0x18001313f  mov     eax, [rsp+0D8h+arg_20]
0x180013146  mov     [rsp+0D8h+var_98], eax
0x18001314a  mov     [rsp+0D8h+var_A0], r10d
0x18001314f  mov     rax, [rsp+0D8h+arg_10]
0x180013157  mov     [rsp+0D8h+var_A8], rax
0x18001315c  mov     [rsp+0D8h+var_B0], r14
0x180013161  mov     rax, [r11]
0x180013164  mov     [rsp+0D8h+var_B8], rax
0x180013169  xor     r8d, r8d; pReturnValue
0x18001316c  lea     edx, [r8+14h]; nProcNum
0x180013170  lea     rcx, ?winwlan_lowpriv_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180013177  call    cs:__imp_Ndr64AsyncClientCall
0x18001317d  mov     r10, cs:WPP_GLOBAL_Control
0x180013184  jmp     short loc_1800131EC
0x180013186  mov     esi, eax
0x180013188  lea     rax, WPP_GLOBAL_Control
0x18001318f  mov     r10, cs:WPP_GLOBAL_Control
0x180013196  cmp     r10, rax
0x180013199  jz      short loc_1800131CB
0x18001319b  cmp     byte ptr [r10+69h], 1
0x1800131a0  jb      short loc_1800131CB
0x1800131a2  test    dword ptr [r10+6Ch], 1000h
0x1800131aa  jz      short loc_1800131CB
0x1800131ac  mov     edx, 151h
0x1800131b1  mov     r9d, esi
0x1800131b4  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800131bb  mov     rcx, [r10+60h]
0x1800131bf  call    WPP_SF_d
0x1800131c4  mov     r10, cs:WPP_GLOBAL_Control
0x1800131cb  xor     ebx, ebx
0x1800131cd  lea     r15, WPP_GLOBAL_Control
0x1800131d4  mov     rdi, [rsp+0D8h+arg_0]
0x1800131dc  mov     r12, [rsp+0D8h+var_50]
0x1800131e4  mov     r13, [rsp+0D8h+var_48]
0x1800131ec  mov     ecx, esi; unsigned int
0x1800131ee  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x1800131f3  mov     esi, eax
0x1800131f5  test    eax, eax
0x1800131f7  jnz     short loc_180013259
0x1800131f9  mov     rax, [r13+0]
0x1800131fd  mov     rcx, [rsp+0D8h+arg_50]
0x180013205  mov     [rcx], rax
0x180013208  xor     r8d, r8d; pftTimeout
0x18001320b  mov     rdx, [rdi+90h]; h
0x180013212  mov     rcx, r12; pwa
0x180013215  call    cs:__imp_SetThreadpoolWait
0x18001321b  mov     r12, rbx
0x18001321e  jmp     short loc_180013252
0x180013220  mov     esi, 57h ; 'W'
0x180013225  cmp     r10, r15
0x180013228  jz      short loc_180013259
0x18001322a  cmp     byte ptr [r10+69h], 1
0x18001322f  jb      short loc_180013259
0x180013231  mov     r14d, 1000h
0x180013237  test    [r10+6Ch], r14d
0x18001323b  jz      short loc_180013259
0x18001323d  mov     edx, 14Dh
0x180013242  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180013249  mov     rcx, [r10+60h]
0x18001324d  call    WPP_SF_
0x180013252  mov     r10, cs:WPP_GLOBAL_Control
0x180013259  test    esi, esi
0x18001325b  jz      short loc_180013286
0x18001325d  test    r12, r12
0x180013260  jz      short loc_180013272
0x180013262  mov     rcx, r12; pwa
0x180013265  call    cs:__imp_CloseThreadpoolWait
0x18001326b  mov     r10, cs:WPP_GLOBAL_Control
0x180013272  test    rdi, rdi
0x180013275  jz      short loc_180013286
0x180013277  mov     rcx, rdi; struct _WFD_API_ASYNC_CONTEXT *
0x18001327a  call    ?LocalWfdAsyncContextDeref@@YAKPEAU_WFD_API_ASYNC_CONTEXT@@@Z; LocalWfdAsyncContextDeref(_WFD_API_ASYNC_CONTEXT *)
0x18001327f  mov     r10, cs:WPP_GLOBAL_Control
0x180013286  cmp     r10, r15
0x180013289  jz      short loc_1800132B1
0x18001328b  cmp     byte ptr [r10+69h], 4
0x180013290  jb      short loc_1800132B1
0x180013292  test    byte ptr [r10+6Ch], 2
0x180013297  jz      short loc_1800132B1
0x180013299  mov     edx, 152h
0x18001329e  mov     r9d, esi
0x1800132a1  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800132a8  mov     rcx, [r10+60h]
0x1800132ac  call    WPP_SF_d
0x1800132b1  mov     eax, esi
0x1800132b3  add     rsp, 0A0h
0x1800132ba  pop     r15
0x1800132bc  pop     r14
0x1800132be  pop     r13
0x1800132c0  pop     r12
0x1800132c2  pop     rdi
0x1800132c3  pop     rsi
0x1800132c4  pop     rbx
0x1800132c5  retn
0x180060a70  push    rbp
0x180060a72  sub     rsp, 80h
0x180060a79  mov     rbp, rdx
0x180060a7c  mov     rcx, [rcx]
0x180060a7f  mov     ecx, [rcx]; ExceptionCode
0x180060a81  call    cs:__imp_RpcExceptionFilter
0x180060a87  nop
0x180060a88  add     rsp, 80h
0x180060a8f  pop     rbp
0x180060a90  retn
```
