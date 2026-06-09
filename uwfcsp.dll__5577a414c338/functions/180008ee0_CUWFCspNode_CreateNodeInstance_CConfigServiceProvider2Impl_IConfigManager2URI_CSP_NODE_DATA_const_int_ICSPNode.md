# CUWFCspNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x180008ee0`
- end: `0x1800090f6`
- name: `?CreateNodeInstance@CUWFCspNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `534`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180007788`
- `0x180007b90`
- `0x180007fc4`
- `0x180008dcc`
- `0x180008ee0`
- `0x18000b4dc`
- `0x18000b61c`
- `0x18001a210`
- `0x18001b010`

## string_xrefs

- `0x180008f3b`: `UWFCspNodeCreated`

## pseudocode

```c
__int64 __fastcall CUWFCspNode::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        int a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  struct ICSPNode *v10; // rbx
  int v11; // edi
  int v12; // eax
  struct ICSPNode *v13; // r14
  int *v14; // r14
  int v15; // esi
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  struct ICSPNode *v18; // [rsp+38h] [rbp-C8h] BYREF
  int *v19; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v20[42]; // [rsp+50h] [rbp-B0h] BYREF

  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v20);
  v20[0] = &UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable';
  UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(v20, L"UWFCspNodeCreated");
  v10 = 0;
  v19 = 0;
  v17 = 0;
  v18 = 0;
  if ( !a1 || !a2 || !a3 || !a5 || !a6 )
  {
    v11 = -2147024809;
    goto LABEL_21;
  }
  *a5 = 0;
  *a6 = 0;
  if ( !a4 || !*((_DWORD *)a3 + 6) )
  {
    v11 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v17);
    if ( v11 >= 0 )
    {
      if ( *((_DWORD *)a3 + 2) + 1 == v17 )
      {
        v12 = ATL::CComObject<CUWFCspNode>::CreateInstance(&v18);
        v10 = v18;
        v11 = v12;
        if ( v12 >= 0 )
        {
          if ( v18 )
          {
            if ( (unsigned int)(*((_DWORD *)a3 + 3) - 50) <= 2 )
              *a6 |= 2u;
            v13 = v10;
            v11 = (*(__int64 (__fastcall **)(struct ICSPNode *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v10 + 136LL))(
                    v10,
                    a1,
                    a2,
                    a3);
            if ( v11 >= 0 )
            {
              v11 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, int **))(*(_QWORD *)a2 + 88LL))(
                      a2,
                      *((unsigned int *)a3 + 2),
                      &v19);
              if ( v11 >= 0 )
              {
                (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v10 + 8LL))(v10);
                v10 = 0;
                *a5 = v13;
              }
            }
          }
          else
          {
            v11 = -2147024882;
          }
        }
      }
      else
      {
        v11 = -2147418113;
      }
    }
LABEL_21:
    v14 = v19;
    if ( v19 )
      goto LABEL_23;
    goto LABEL_22;
  }
  v11 = -2046820335;
LABEL_22:
  v14 = &dword_18001F7A4;
LABEL_23:
  if ( a3 )
    v15 = *((_DWORD *)a3 + 3);
  else
    v15 = -1;
  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
    v20,
    (unsigned int)v11);
  UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned long,unsigned short const *>((__int64)v20, v15, v14);
  if ( v10 )
    (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v10 + 16LL))(v10);
  UwfTraceLoggingProvider<2>::ConfigurationActivity::~ConfigurationActivity(v20);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180008ee0  mov     [rsp-8+arg_18], rbx
0x180008ee5  push    rbp
0x180008ee6  push    rsi
0x180008ee7  push    rdi
0x180008ee8  push    r12
0x180008eea  push    r13
0x180008eec  push    r14
0x180008eee  push    r15
0x180008ef0  lea     rbp, [rsp-0B0h]
0x180008ef8  sub     rsp, 1B0h
0x180008eff  mov     rax, cs:__security_cookie
0x180008f06  xor     rax, rsp
0x180008f09  mov     [rbp+0E0h+var_40], rax
0x180008f10  mov     r12, [rbp+0E0h+arg_20]
0x180008f17  mov     r13, rcx
0x180008f1a  mov     r14, [rbp+0E0h+arg_28]
0x180008f21  lea     rcx, [rsp+1E0h+var_190]
0x180008f26  mov     edi, r9d
0x180008f29  mov     rsi, r8
0x180008f2c  mov     r15, rdx
0x180008f2f  call    ??0?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180008f34  lea     rax, ??_7ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@6B@; const UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable'
0x180008f3b  lea     rdx, aUwfcspnodecrea; "UWFCspNodeCreated"
0x180008f42  mov     [rsp+1E0h+var_190], rax
0x180008f47  lea     rcx, [rsp+1E0h+var_190]
0x180008f4c  call    ?StartActivity@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(ushort const *)
0x180008f51  xor     ebx, ebx
0x180008f53  mov     [rsp+1E0h+var_1A0], 0
0x180008f5c  mov     [rsp+1E0h+var_1B0], 0
0x180008f64  mov     [rsp+1E0h+var_1A8], rbx
0x180008f69  test    r13, r13
0x180008f6c  jz      loc_18000906E
0x180008f72  test    r15, r15
0x180008f75  jz      loc_18000906E
0x180008f7b  test    rsi, rsi
0x180008f7e  jz      loc_18000906E
0x180008f84  test    r12, r12
0x180008f87  jz      loc_18000906E
0x180008f8d  test    r14, r14
0x180008f90  jz      loc_18000906E
0x180008f96  mov     [r12], rbx
0x180008f9a  mov     [r14], ebx
0x180008f9d  test    edi, edi
0x180008f9f  jz      short loc_180008FB0
0x180008fa1  cmp     [rsi+18h], ebx
0x180008fa4  jz      short loc_180008FB0
0x180008fa6  mov     edi, 86000011h
0x180008fab  jmp     loc_18000907D
0x180008fb0  mov     rax, [r15]
0x180008fb3  lea     rdx, [rsp+1E0h+var_1B0]
0x180008fb8  mov     rcx, r15
0x180008fbb  mov     rax, [rax+88h]
0x180008fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fc7  mov     edi, eax
0x180008fc9  test    eax, eax
0x180008fcb  js      loc_180009073
0x180008fd1  mov     eax, [rsi+8]
0x180008fd4  inc     eax
0x180008fd6  cmp     eax, [rsp+1E0h+var_1B0]
0x180008fda  jz      short loc_180008FE6
0x180008fdc  mov     edi, 8000FFFFh
0x180008fe1  jmp     loc_180009073
0x180008fe6  lea     rcx, [rsp+1E0h+var_1A8]
0x180008feb  call    ?CreateInstance@?$CComObject@VCUWFCspNode@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CUWFCspNode>::CreateInstance(ATL::CComObject<CUWFCspNode> * *)
0x180008ff0  mov     rbx, [rsp+1E0h+var_1A8]
0x180008ff5  mov     edi, eax
0x180008ff7  test    eax, eax
0x180008ff9  js      short loc_180009073
0x180008ffb  test    rbx, rbx
0x180008ffe  jnz     short loc_180009007
0x180009000  mov     edi, 8007000Eh
0x180009005  jmp     short loc_180009073
0x180009007  mov     eax, [rsi+0Ch]
0x18000900a  sub     eax, 32h ; '2'
0x18000900d  cmp     eax, 2
0x180009010  ja      short loc_180009016
0x180009012  or      dword ptr [r14], 2
0x180009016  mov     rax, [rbx]
0x180009019  mov     r9, rsi
0x18000901c  mov     r8, r15
0x18000901f  mov     rdx, r13
0x180009022  mov     rcx, rbx
0x180009025  mov     r14, rbx
0x180009028  mov     rax, [rax+88h]
0x18000902f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009034  mov     edi, eax
0x180009036  test    eax, eax
0x180009038  js      short loc_180009073
0x18000903a  mov     rax, [r15]
0x18000903d  lea     r8, [rsp+1E0h+var_1A0]
0x180009042  mov     edx, [rsi+8]
0x180009045  mov     rcx, r15
0x180009048  mov     rax, [rax+58h]
0x18000904c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009051  mov     edi, eax
0x180009053  test    eax, eax
0x180009055  js      short loc_180009073
0x180009057  mov     rax, [rbx]
0x18000905a  mov     rcx, rbx
0x18000905d  mov     rax, [rax+8]
0x180009061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009066  xor     ebx, ebx
0x180009068  mov     [r12], r14
0x18000906c  jmp     short loc_180009073
0x18000906e  mov     edi, 80070057h
0x180009073  mov     r14, [rsp+1E0h+var_1A0]
0x180009078  test    r14, r14
0x18000907b  jnz     short loc_180009084
0x18000907d  lea     r14, dword_18001F7A4
0x180009084  test    rsi, rsi
0x180009087  jz      short loc_18000908E
0x180009089  mov     esi, [rsi+0Ch]
0x18000908c  jmp     short loc_180009091
0x18000908e  or      esi, 0FFFFFFFFh
0x180009091  mov     edx, edi
0x180009093  lea     rcx, [rsp+1E0h+var_190]
0x180009098  call    ?SetStopResult@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000909d  mov     r8, r14
0x1800090a0  lea     rcx, [rsp+1E0h+var_190]
0x1800090a5  mov     edx, esi
0x1800090a7  call    ??$Stop@KPEBG@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXKPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<ulong,ushort const *>(ulong,ushort const *)
0x1800090ac  test    rbx, rbx
0x1800090af  jz      short loc_1800090C0
0x1800090b1  mov     rax, [rbx]
0x1800090b4  mov     rcx, rbx
0x1800090b7  mov     rax, [rax+10h]
0x1800090bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090c0  lea     rcx, [rsp+1E0h+var_190]
0x1800090c5  call    ??1ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAA@XZ; UwfTraceLoggingProvider<2>::ConfigurationActivity::~ConfigurationActivity(void)
0x1800090ca  mov     eax, edi
0x1800090cc  mov     rcx, [rbp+0E0h+var_40]
0x1800090d3  xor     rcx, rsp; StackCookie
0x1800090d6  call    __security_check_cookie
0x1800090db  mov     rbx, [rsp+1E0h+arg_18]
0x1800090e3  add     rsp, 1B0h
0x1800090ea  pop     r15
0x1800090ec  pop     r14
0x1800090ee  pop     r13
0x1800090f0  pop     r12
0x1800090f2  pop     rdi
0x1800090f3  pop     rsi
0x1800090f4  pop     rbp
0x1800090f5  retn
```
