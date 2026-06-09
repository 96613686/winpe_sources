# WFDStartOpenSessionLib(void *,uchar (*)[6],void *,void (*)(void *,void *,_GUID,ulong,ulong),ushort *,_WFD_FIREWALL_CONFIGURATION_PARAMETERS const *,void * *)

- ea: `0x1800572d4`
- end: `0x1800576c4`
- name: `?WFDStartOpenSessionLib@@YAKPEAXPEAY05E0P6AX00U_GUID@@KK@ZPEAGPEBU_WFD_FIREWALL_CONFIGURATION_PARAMETERS@@PEAPEAX@Z`
- size: `1008`
- prototype: `unsigned int __usercall@<eax>(void *@<rcx>, unsigned __int8 (*)[6]@<rdx>, void *@<r8>, void (*)(void *, void *, struct _GUID *__struct_ptr, unsigned int, unsigned int)@<r9>, unsigned __int16 *, const struct _WFD_FIREWALL_CONFIGURATION_PARAMETERS *, void **)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021d10`
- `0x18002c5e0`
- `0x18002c7a0`
- `0x180038060`

## callees

- `0x1800038d0`
- `0x1800063a0`
- `0x180006934`
- `0x1800132cc`
- `0x180019a20`
- `0x180043d68`
- `0x18004fe34`
- `0x1800572d4`
- `0x18005ab24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057473`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800575fd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800575fd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005745d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005745d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180057649`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180057649`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800574f2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800574f2`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180057564`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180057564`

## pseudocode

```c
__int64 __fastcall WFDStartOpenSessionLib(
        void *a1,
        unsigned __int8 (*a2)[6],
        void *a3,
        void (*a4)(void *, void *, struct _GUID *__struct_ptr, unsigned int, unsigned int),
        unsigned __int16 *a5,
        const struct _WFD_FIREWALL_CONFIGURATION_PARAMETERS *a6,
        void **a7)
{
  void (*v7)(void *, void *, struct _GUID *__struct_ptr, unsigned int, unsigned int); // rax
  struct _WFD_API_ASYNC_CONTEXT *v10; // rdi
  struct _TP_WAIT *ThreadpoolWait; // r14
  union DOT11_OUI_HEADER *v12; // r10
  DWORD LastError; // ebx
  _QWORD *v14; // r15
  struct _WFD_API_ASYNC_CONTEXT *v16; // [rsp+60h] [rbp-88h] BYREF
  void (*v17)(void *, void *, struct _GUID *__struct_ptr, unsigned int, unsigned int); // [rsp+68h] [rbp-80h]
  void *v18; // [rsp+70h] [rbp-78h]
  const struct _WFD_FIREWALL_CONFIGURATION_PARAMETERS *v19; // [rsp+78h] [rbp-70h]
  unsigned __int16 *v20; // [rsp+80h] [rbp-68h]
  struct _TP_WAIT *v21; // [rsp+88h] [rbp-60h]
  void **v22; // [rsp+90h] [rbp-58h]
  char *v23; // [rsp+98h] [rbp-50h]
  GUID ActivityId; // [rsp+A0h] [rbp-48h] BYREF

  v7 = a4;
  v17 = a4;
  v18 = a3;
  v20 = a5;
  v19 = a6;
  v22 = a7;
  v10 = 0;
  v16 = 0;
  ActivityId = 0;
  ThreadpoolWait = 0;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 177, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
    v12 = WPP_GLOBAL_Control;
    v7 = v17;
  }
  if ( a1 && a2 && v7 && a7 )
  {
    if ( v12 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v12 + 105) >= 3u
      && (*((_DWORD *)v12 + 27) & 0x1000) != 0 )
    {
      WPP_SF__MAC_(*((_QWORD *)v12 + 12), (unsigned __int8 *)a2, a3, (unsigned __int8 *)a2);
    }
    LastError = LocalWfdAsyncContextCreateInternal(a1, &v16, 0);
    if ( LastError )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) == 0 )
      {
        v10 = v16;
        goto LABEL_32;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 180, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
      v10 = v16;
      goto LABEL_31;
    }
    v10 = v16;
    v14 = (_QWORD *)((char *)v16 + 16);
    v23 = (char *)v16 + 16;
    ThreadpoolWait = CreateThreadpoolWait(
                       wfdAsyncCompletionCallback,
                       *((PVOID *)v16 + 2),
                       (PTP_CALLBACK_ENVIRON)(*((_QWORD *)v16 + 1) + 232LL));
    v21 = ThreadpoolWait;
    if ( !ThreadpoolWait )
    {
      LastError = GetLastError();
LABEL_31:
      v12 = WPP_GLOBAL_Control;
      goto LABEL_32;
    }
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 181, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, *v14);
    }
    *(_DWORD *)v10 = 1;
    *((_QWORD *)v10 + 3) = v18;
    *((_QWORD *)v10 + 21) = v17;
    *((_DWORD *)v10 + 38) = *(_DWORD *)a2;
    *((_WORD *)v10 + 78) = *(_WORD *)&(*a2)[4];
    EventActivityIdControl(1u, &ActivityId);
    Ndr64AsyncClientCall(
      (MIDL_STUBLESS_PROXY_INFO *)&winwlan_ProxyInfo,
      0x57u,
      0,
      (char *)v10 + 32,
      &ActivityId,
      **((_QWORD **)v10 + 1),
      a2,
      (char *)v10 + 176,
      (char *)v10 + 192,
      v20,
      v19,
      (char *)v10 + 160);
    LastError = ServiceStatus(LastError);
    if ( !LastError )
    {
      *a7 = (void *)*v14;
      SetThreadpoolWait(ThreadpoolWait, *((HANDLE *)v10 + 18), 0);
      ThreadpoolWait = 0;
      goto LABEL_31;
    }
  }
  else
  {
    LastError = 87;
    if ( v12 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v12 + 105)
      && (*((_DWORD *)v12 + 27) & 0x1000) != 0 )
    {
      WPP_SF_(*((_QWORD *)v12 + 12), 178, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
      goto LABEL_31;
    }
  }
LABEL_32:
  if ( LastError )
  {
    if ( ThreadpoolWait )
    {
      CloseThreadpoolWait(ThreadpoolWait);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v10 )
    {
      LocalWfdAsyncContextDeref(v10);
      v12 = WPP_GLOBAL_Control;
    }
  }
  if ( v12 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v12 + 105) >= 4u
    && (*((_BYTE *)v12 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v12 + 12), 183, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800572d4  mov     r11, rsp
0x1800572d7  mov     [r11+18h], rbx
0x1800572db  mov     [r11+20h], rsi
0x1800572df  push    rdi
0x1800572e0  push    r12
0x1800572e2  push    r13
0x1800572e4  push    r14
0x1800572e6  push    r15
0x1800572e8  sub     rsp, 0C0h
0x1800572ef  mov     rax, cs:__security_cookie
0x1800572f6  xor     rax, rsp
0x1800572f9  mov     [rsp+0E8h+var_38], rax
0x180057301  mov     rax, r9
0x180057304  mov     [rsp+0E8h+var_80], rax
0x180057309  mov     [rsp+0E8h+var_78], r8
0x18005730e  mov     r12, rdx
0x180057311  mov     rbx, rcx
0x180057314  mov     rcx, [rsp+0E8h+arg_20]
0x18005731c  mov     [rsp+0E8h+var_68], rcx
0x180057324  mov     rcx, [rsp+0E8h+arg_28]
0x18005732c  mov     [rsp+0E8h+var_70], rcx
0x180057331  mov     r13, [rsp+0E8h+arg_30]
0x180057339  mov     [rsp+0E8h+var_58], r13
0x180057341  xor     edi, edi
0x180057343  mov     [rsp+0E8h+var_88], rdi
0x180057348  xorps   xmm0, xmm0
0x18005734b  movups  xmmword ptr [r11-48h], xmm0
0x180057350  xor     r14d, r14d
0x180057353  lea     rsi, WPP_GLOBAL_Control
0x18005735a  mov     r10, cs:WPP_GLOBAL_Control
0x180057361  cmp     r10, rsi
0x180057364  jz      short loc_180057395
0x180057366  cmp     byte ptr [r10+69h], 4
0x18005736b  jb      short loc_180057395
0x18005736d  test    byte ptr [r10+6Ch], 2
0x180057372  jz      short loc_180057395
0x180057374  mov     edx, 0B1h
0x180057379  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180057380  mov     rcx, [r10+60h]
0x180057384  call    WPP_SF_
0x180057389  mov     r10, cs:WPP_GLOBAL_Control
0x180057390  mov     rax, [rsp+0E8h+var_80]
0x180057395  test    rbx, rbx
0x180057398  jz      loc_180057608
0x18005739e  test    r12, r12
0x1800573a1  jz      loc_180057608
0x1800573a7  test    rax, rax
0x1800573aa  jz      loc_180057608
0x1800573b0  test    r13, r13
0x1800573b3  jz      loc_180057608
0x1800573b9  cmp     r10, rsi
0x1800573bc  jz      short loc_1800573DB
0x1800573be  cmp     byte ptr [r10+69h], 3
0x1800573c3  jb      short loc_1800573DB
0x1800573c5  test    dword ptr [r10+6Ch], 1000h
0x1800573cd  jz      short loc_1800573DB
0x1800573cf  mov     r9, r12
0x1800573d2  mov     rcx, [r10+60h]
0x1800573d6  call    WPP_SF__MAC_
0x1800573db  xor     r8d, r8d; int
0x1800573de  lea     rdx, [rsp+0E8h+var_88]; struct _WFD_API_ASYNC_CONTEXT **
0x1800573e3  mov     rcx, rbx; void *
0x1800573e6  call    ?LocalWfdAsyncContextCreateInternal@@YAKPEAXPEAPEAU_WFD_API_ASYNC_CONTEXT@@H@Z; LocalWfdAsyncContextCreateInternal(void *,_WFD_API_ASYNC_CONTEXT * *,int)
0x1800573eb  mov     ebx, eax
0x1800573ed  test    eax, eax
0x1800573ef  jz      short loc_180057437
0x1800573f1  mov     r10, cs:WPP_GLOBAL_Control
0x1800573f8  cmp     r10, rsi
0x1800573fb  jz      short loc_18005742D
0x1800573fd  cmp     byte ptr [r10+69h], 1
0x180057402  jb      short loc_18005742D
0x180057404  test    dword ptr [r10+6Ch], 1000h
0x18005740c  jz      short loc_18005742D
0x18005740e  mov     edx, 0B4h
0x180057413  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18005741a  mov     rcx, [r10+60h]
0x18005741e  call    WPP_SF_
0x180057423  mov     rdi, [rsp+0E8h+var_88]
0x180057428  jmp     loc_180057636
0x18005742d  mov     rdi, [rsp+0E8h+var_88]
0x180057432  jmp     loc_18005763D
0x180057437  mov     rdi, [rsp+0E8h+var_88]
0x18005743c  lea     r15, [rdi+10h]
0x180057440  mov     [rsp+0E8h+var_50], r15
0x180057448  mov     r8, [rdi+8]
0x18005744c  add     r8, 0E8h; pcbe
0x180057453  mov     rdx, [r15]; pv
0x180057456  lea     rcx, ?wfdAsyncCompletionCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18005745d  call    cs:__imp_CreateThreadpoolWait
0x180057463  mov     r14, rax
0x180057466  mov     [rsp+0E8h+var_60], rax
0x18005746e  test    rax, rax
0x180057471  jnz     short loc_180057480
0x180057473  call    cs:__imp_GetLastError
0x180057479  mov     ebx, eax
0x18005747b  jmp     loc_180057636
0x180057480  mov     rcx, cs:WPP_GLOBAL_Control
0x180057487  cmp     rcx, rsi
0x18005748a  jz      short loc_1800574B3
0x18005748c  cmp     byte ptr [rcx+69h], 3
0x180057490  jb      short loc_1800574B3
0x180057492  test    dword ptr [rcx+6Ch], 1000h
0x180057499  jz      short loc_1800574B3
0x18005749b  mov     edx, 0B5h
0x1800574a0  mov     r9, [r15]
0x1800574a3  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800574aa  mov     rcx, [rcx+60h]
0x1800574ae  call    WPP_SF_q
0x1800574b3  mov     dword ptr [rdi], 1
0x1800574b9  mov     rax, [rsp+0E8h+var_78]
0x1800574be  mov     [rdi+18h], rax
0x1800574c2  mov     rax, [rsp+0E8h+var_80]
0x1800574c7  mov     [rdi+0A8h], rax
0x1800574ce  mov     eax, [r12]
0x1800574d2  mov     [rdi+98h], eax
0x1800574d8  movzx   eax, word ptr [r12+4]
0x1800574de  mov     [rdi+9Ch], ax
0x1800574e5  lea     rdx, [rsp+0E8h+ActivityId]; ActivityId
0x1800574ed  mov     ecx, 1; ControlCode
0x1800574f2  call    cs:__imp_EventActivityIdControl
0x1800574f8  nop
0x1800574f9  lea     rax, [rdi+0A0h]
0x180057500  lea     rcx, [rdi+0C0h]
0x180057507  lea     rdx, [rdi+0B0h]
0x18005750e  mov     r8, [rdi+8]
0x180057512  lea     r9, [rdi+20h]
0x180057516  mov     [rsp+0E8h+var_90], rax
0x18005751b  mov     rax, [rsp+0E8h+var_70]
0x180057520  mov     [rsp+0E8h+var_98], rax
0x180057525  mov     rax, [rsp+0E8h+var_68]
0x18005752d  mov     [rsp+0E8h+var_A0], rax
0x180057532  mov     [rsp+0E8h+var_A8], rcx
0x180057537  mov     [rsp+0E8h+var_B0], rdx
0x18005753c  mov     [rsp+0E8h+var_B8], r12
0x180057541  mov     rax, [r8]
0x180057544  mov     [rsp+0E8h+var_C0], rax
0x180057549  lea     rax, [rsp+0E8h+ActivityId]
0x180057551  mov     [rsp+0E8h+var_C8], rax
0x180057556  xor     r8d, r8d; pReturnValue
0x180057559  lea     edx, [r8+57h]; nProcNum
0x18005755d  lea     rcx, ?winwlan_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180057564  call    cs:__imp_Ndr64AsyncClientCall
0x18005756a  mov     r10, cs:WPP_GLOBAL_Control
0x180057571  jmp     short loc_1800575DC
0x180057573  mov     ebx, eax
0x180057575  lea     rax, WPP_GLOBAL_Control
0x18005757c  mov     r10, cs:WPP_GLOBAL_Control
0x180057583  cmp     r10, rax
0x180057586  jz      short loc_1800575B8
0x180057588  cmp     byte ptr [r10+69h], 1
0x18005758d  jb      short loc_1800575B8
0x18005758f  test    dword ptr [r10+6Ch], 1000h
0x180057597  jz      short loc_1800575B8
0x180057599  mov     edx, 0B6h
0x18005759e  mov     r9d, ebx
0x1800575a1  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800575a8  mov     rcx, [r10+60h]
0x1800575ac  call    WPP_SF_d
0x1800575b1  mov     r10, cs:WPP_GLOBAL_Control
0x1800575b8  lea     rsi, WPP_GLOBAL_Control
0x1800575bf  mov     rdi, [rsp+0E8h+var_88]
0x1800575c4  mov     r14, [rsp+0E8h+var_60]
0x1800575cc  mov     r13, [rsp+0E8h+var_58]
0x1800575d4  mov     r15, [rsp+0E8h+var_50]
0x1800575dc  mov     ecx, ebx; unsigned int
0x1800575de  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x1800575e3  mov     ebx, eax
0x1800575e5  test    eax, eax
0x1800575e7  jnz     short loc_18005763D
0x1800575e9  mov     rax, [r15]
0x1800575ec  mov     [r13+0], rax
0x1800575f0  xor     r8d, r8d; pftTimeout
0x1800575f3  mov     rdx, [rdi+90h]; h
0x1800575fa  mov     rcx, r14; pwa
0x1800575fd  call    cs:__imp_SetThreadpoolWait
0x180057603  xor     r14d, r14d
0x180057606  jmp     short loc_180057636
0x180057608  mov     ebx, 57h ; 'W'
0x18005760d  cmp     r10, rsi
0x180057610  jz      short loc_18005763D
0x180057612  cmp     byte ptr [r10+69h], 1
0x180057617  jb      short loc_18005763D
0x180057619  test    dword ptr [r10+6Ch], 1000h
0x180057621  jz      short loc_18005763D
0x180057623  lea     edx, [rbx+5Bh]
0x180057626  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18005762d  mov     rcx, [r10+60h]
0x180057631  call    WPP_SF_
0x180057636  mov     r10, cs:WPP_GLOBAL_Control
0x18005763d  test    ebx, ebx
0x18005763f  jz      short loc_18005766A
0x180057641  test    r14, r14
0x180057644  jz      short loc_180057656
0x180057646  mov     rcx, r14; pwa
0x180057649  call    cs:__imp_CloseThreadpoolWait
0x18005764f  mov     r10, cs:WPP_GLOBAL_Control
0x180057656  test    rdi, rdi
0x180057659  jz      short loc_18005766A
0x18005765b  mov     rcx, rdi; struct _WFD_API_ASYNC_CONTEXT *
0x18005765e  call    ?LocalWfdAsyncContextDeref@@YAKPEAU_WFD_API_ASYNC_CONTEXT@@@Z; LocalWfdAsyncContextDeref(_WFD_API_ASYNC_CONTEXT *)
0x180057663  mov     r10, cs:WPP_GLOBAL_Control
0x18005766a  cmp     r10, rsi
0x18005766d  jz      short loc_180057695
0x18005766f  cmp     byte ptr [r10+69h], 4
0x180057674  jb      short loc_180057695
0x180057676  test    byte ptr [r10+6Ch], 2
0x18005767b  jz      short loc_180057695
0x18005767d  mov     edx, 0B7h
0x180057682  mov     r9d, ebx
0x180057685  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18005768c  mov     rcx, [r10+60h]
0x180057690  call    WPP_SF_d
0x180057695  mov     eax, ebx
0x180057697  mov     rcx, [rsp+0E8h+var_38]
0x18005769f  xor     rcx, rsp; StackCookie
0x1800576a2  call    __security_check_cookie
0x1800576a7  lea     r11, [rsp+0E8h+var_28]
0x1800576af  mov     rbx, [r11+40h]
0x1800576b3  mov     rsi, [r11+48h]
0x1800576b7  mov     rsp, r11
0x1800576ba  pop     r15
0x1800576bc  pop     r14
0x1800576be  pop     r13
0x1800576c0  pop     r12
0x1800576c2  pop     rdi
0x1800576c3  retn
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
