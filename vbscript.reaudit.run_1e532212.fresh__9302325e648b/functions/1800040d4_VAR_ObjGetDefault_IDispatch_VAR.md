# VAR::ObjGetDefault(IDispatch *,VAR * *)

- ea: `0x1800040d4`
- end: `0x1800042f9`
- name: `?ObjGetDefault@VAR@@SAJPEAUIDispatch@@PEAPEAV1@@Z`
- size: `549`
- prototype: `__int64 __fastcall(struct IDispatch *, struct VAR **)`
- caller_count: `29`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x180001f70`
- `0x180002600`
- `0x180002780`
- `0x180002b70`
- `0x1800038c0`
- `0x180019e78`
- `0x18001a050`
- `0x18001b1a4`
- `0x18001b260`
- `0x18001b350`
- `0x18001bd44`
- `0x18001c050`
- `0x18001c1f0`
- `0x18001c8c0`
- `0x18001d6c0`
- `0x18001d830`
- `0x18001d9f0`
- `0x18001e210`
- `0x18001e7a0`
- `0x18001e850`
- `0x18001fa40`
- `0x18002fde0`
- `0x1800351e4`
- `0x1800361fc`
- `0x180037150`
- `0x180039ad0`
- `0x180039f50`
- `0x18003af30`
- `0x18003afc0`

## callees

- `0x1800040d4`
- `0x180004610`
- `0x180004d80`
- `0x180008040`
- `0x18001f2b0`
- `0x180022b20`
- `0x18002cce0`
- `0x18002feb0`
- `0x180076746`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000420e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000421d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000422c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000420e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000421d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000422c`

## pseudocode

```c
__int64 __fastcall VAR::ObjGetDefault(struct IDispatch *a1, struct VAR **a2)
{
  struct COleScript *CurrentOleScript; // rax
  CSession *v5; // rsi
  const struct _GUID *v6; // r9
  int DexCaller; // edi
  struct VAR *v8; // rax
  struct DexCaller *v10; // rbx
  unsigned int v11; // [rsp+50h] [rbp-49h] BYREF
  struct IDispatchEx *v12; // [rsp+58h] [rbp-41h] BYREF
  struct IServiceProvider *v13; // [rsp+60h] [rbp-39h] BYREF
  struct tagDISPPARAMS v14; // [rsp+68h] [rbp-31h] BYREF
  struct tagEXCEPINFO v15; // [rsp+80h] [rbp-19h] BYREF
  struct tagVARIANT v16; // [rsp+C0h] [rbp+27h] BYREF

  v11 = 0;
  v12 = 0;
  memset(&v14, 0, sizeof(v14));
  memset(&v16, 0, sizeof(v16));
  memset_0(&v15, 0, sizeof(v15));
  if ( a1 )
  {
    CurrentOleScript = CScriptRuntime::GetCurrentOleScript();
    if ( CurrentOleScript && (v5 = (CSession *)*((_QWORD *)CurrentOleScript + 80)) != 0 )
    {
      if ( ((__int64 (__fastcall *)(struct IDispatch *, GUID *, struct IDispatchEx **))a1->lpVtbl->QueryInterface)(
             a1,
             &IID_IDispatchEx,
             &v12) >= 0 )
      {
        v13 = 0;
        DexCaller = CSession::FetchDexCaller(v5, (struct DexCaller **)&v13);
        if ( DexCaller >= 0 )
        {
          v10 = (struct DexCaller *)v13;
          DexCaller = IDispatchExInvokeEx(v5, (struct IDispatch *)v12, 0, 0x409u, 3u, &v14, &v16, &v15, v13);
          CSession::ReleaseDexCaller(v5, v10);
        }
        ((void (__fastcall *)(struct IDispatchEx *))v12->lpVtbl->Release)(v12);
      }
      else
      {
        DexCaller = IDispatchInvoke(v5, a1, 0, v6, 0x409u, 3u, &v14, &v16, &v15, &v11);
      }
      if ( DexCaller >= 0 )
      {
        if ( v16.vt == 9 )
        {
          DexCaller = -2146828275;
        }
        else
        {
          v8 = PvarAlloc();
          if ( v8 )
          {
            *(struct tagVARIANT *)v8 = v16;
            *a2 = v8;
            v16.vt = 0;
            DexCaller = 0;
          }
          else
          {
            DexCaller = -2146828281;
          }
        }
      }
    }
    else
    {
      DexCaller = -2147418113;
    }
  }
  else
  {
    DexCaller = -2146828197;
  }
  VAR::Clear((VAR *)&v16);
  if ( v15.bstrSource )
    SysFreeString(v15.bstrSource);
  if ( v15.bstrDescription )
    SysFreeString(v15.bstrDescription);
  if ( v15.bstrHelpFile )
    SysFreeString(v15.bstrHelpFile);
  return (unsigned int)DexCaller;
}

```

## disassembly

```asm
0x1800040d4  mov     [rsp-8+arg_10], rbx
0x1800040d9  mov     [rsp-8+arg_18], rsi
0x1800040de  push    rbp
0x1800040df  push    rdi
0x1800040e0  push    r14
0x1800040e2  lea     rbp, [rsp-47h]
0x1800040e7  sub     rsp, 0E0h
0x1800040ee  mov     rax, cs:__security_cookie
0x1800040f5  xor     rax, rsp
0x1800040f8  mov     [rbp+57h+var_18], rax
0x1800040fc  xor     eax, eax
0x1800040fe  mov     [rbp+57h+var_A0], 0
0x180004105  mov     r14, rdx
0x180004108  mov     qword ptr [rbp+57h+var_88.cArgs], rax
0x18000410c  mov     rbx, rcx
0x18000410f  mov     qword ptr [rbp+57h+var_30+10h], rax
0x180004113  xorps   xmm0, xmm0
0x180004116  mov     [rbp+57h+var_98], rax
0x18000411a  xorps   xmm1, xmm1
0x18000411d  lea     r8d, [rax+40h]; Size
0x180004121  xor     edx, edx; Val
0x180004123  lea     rcx, [rbp+57h+var_70]; void *
0x180004127  movups  xmmword ptr [rbp+57h+var_88.rgvarg], xmm0
0x18000412b  movups  xmmword ptr [rbp+57h+var_30], xmm1
0x18000412f  call    memset_0
0x180004134  test    rbx, rbx
0x180004137  jz      loc_180004258
0x18000413d  call    ?GetCurrentOleScript@CScriptRuntime@@SAPEAVCOleScript@@XZ; CScriptRuntime::GetCurrentOleScript(void)
0x180004142  test    rax, rax
0x180004145  jz      loc_1800042EF
0x18000414b  mov     rsi, [rax+280h]
0x180004152  test    rsi, rsi
0x180004155  jz      loc_1800042EF
0x18000415b  mov     rax, [rbx]
0x18000415e  lea     r8, [rbp+57h+var_98]
0x180004162  lea     rdx, IID_IDispatchEx
0x180004169  mov     rcx, rbx
0x18000416c  mov     rax, [rax]
0x18000416f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004174  test    eax, eax
0x180004176  jns     loc_18000425F
0x18000417c  lea     rcx, [rbp+57h+var_A0]
0x180004180  xor     r8d, r8d; int
0x180004183  mov     [rsp+0F0h+var_A8], rcx; unsigned int *
0x180004188  mov     rdx, rbx; struct IDispatch *
0x18000418b  lea     rcx, [rbp+57h+var_70]
0x18000418f  mov     [rsp+0F0h+var_B0], rcx; struct tagEXCEPINFO *
0x180004194  lea     rcx, [rbp+57h+var_30]
0x180004198  mov     [rsp+0F0h+var_B8], rcx; struct tagVARIANT *
0x18000419d  lea     rcx, [rbp+57h+var_88]
0x1800041a1  mov     [rsp+0F0h+var_C0], rcx; struct tagDISPPARAMS *
0x1800041a6  mov     rcx, rsi; struct CSession *
0x1800041a9  mov     word ptr [rsp+0F0h+var_C8], 3; unsigned __int16
0x1800041b0  mov     [rsp+0F0h+var_D0], 409h; unsigned int
0x1800041b8  call    ?IDispatchInvoke@@YAJPEAVCSession@@PEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z; IDispatchInvoke(CSession *,IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)
0x1800041bd  mov     edi, eax
0x1800041bf  test    edi, edi
0x1800041c1  js      short loc_1800041FC
0x1800041c3  mov     eax, 9
0x1800041c8  cmp     ax, word ptr [rbp+57h+var_30]
0x1800041cc  jz      loc_1800042DB
0x1800041d2  call    ?PvarAlloc@@YAPEAVVAR@@XZ; PvarAlloc(void)
0x1800041d7  test    rax, rax
0x1800041da  jz      loc_1800042E5
0x1800041e0  movups  xmm0, xmmword ptr [rbp+57h+var_30]
0x1800041e4  movups  xmmword ptr [rax], xmm0
0x1800041e7  movsd   xmm1, qword ptr [rbp+57h+var_30+10h]
0x1800041ec  movsd   qword ptr [rax+10h], xmm1
0x1800041f1  mov     [r14], rax
0x1800041f4  xor     eax, eax
0x1800041f6  mov     word ptr [rbp+57h+var_30], ax
0x1800041fa  xor     edi, edi
0x1800041fc  lea     rcx, [rbp+57h+var_30]; this
0x180004200  call    ?Clear@VAR@@QEAAJXZ; VAR::Clear(void)
0x180004205  mov     rcx, [rbp+57h+var_70.bstrSource]; bstrString
0x180004209  test    rcx, rcx
0x18000420c  jz      short loc_180004214
0x18000420e  call    cs:__imp_SysFreeString
0x180004214  mov     rcx, [rbp+57h+var_70.bstrDescription]; bstrString
0x180004218  test    rcx, rcx
0x18000421b  jz      short loc_180004223
0x18000421d  call    cs:__imp_SysFreeString
0x180004223  mov     rcx, [rbp+57h+var_70.bstrHelpFile]; bstrString
0x180004227  test    rcx, rcx
0x18000422a  jz      short loc_180004232
0x18000422c  call    cs:__imp_SysFreeString
0x180004232  mov     eax, edi
0x180004234  mov     rcx, [rbp+57h+var_18]
0x180004238  xor     rcx, rsp; StackCookie
0x18000423b  call    __security_check_cookie
0x180004240  lea     r11, [rsp+0F0h+var_10]
0x180004248  mov     rbx, [r11+30h]
0x18000424c  mov     rsi, [r11+38h]
0x180004250  mov     rsp, r11
0x180004253  pop     r14
0x180004255  pop     rdi
0x180004256  pop     rbp
0x180004257  retn
0x180004258  mov     edi, 800A005Bh
0x18000425d  jmp     short loc_1800041FC
0x18000425f  lea     rdx, [rbp+57h+var_90]; struct DexCaller **
0x180004263  mov     [rbp+57h+var_90], 0
0x18000426b  mov     rcx, rsi; this
0x18000426e  call    ?FetchDexCaller@CSession@@QEAAJPEAPEAVDexCaller@@@Z; CSession::FetchDexCaller(DexCaller * *)
0x180004273  mov     edi, eax
0x180004275  test    eax, eax
0x180004277  js      short loc_1800042C6
0x180004279  mov     rbx, [rbp+57h+var_90]
0x18000427d  lea     rcx, [rbp+57h+var_70]
0x180004281  mov     rdx, [rbp+57h+var_98]; struct IDispatchEx *
0x180004285  mov     r9d, 409h; unsigned int
0x18000428b  mov     [rsp+0F0h+var_B0], rbx; struct IServiceProvider *
0x180004290  xor     r8d, r8d; int
0x180004293  mov     [rsp+0F0h+var_B8], rcx; struct tagEXCEPINFO *
0x180004298  lea     rcx, [rbp+57h+var_30]
0x18000429c  mov     [rsp+0F0h+var_C0], rcx; struct tagVARIANT *
0x1800042a1  lea     rcx, [rbp+57h+var_88]
0x1800042a5  mov     [rsp+0F0h+var_C8], rcx; struct tagDISPPARAMS *
0x1800042aa  mov     rcx, rsi; struct CSession *
0x1800042ad  mov     word ptr [rsp+0F0h+var_D0], 3; unsigned __int16
0x1800042b4  call    ?IDispatchExInvokeEx@@YAJPEAVCSession@@PEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z; IDispatchExInvokeEx(CSession *,IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)
0x1800042b9  mov     rdx, rbx; struct DexCaller *
0x1800042bc  mov     rcx, rsi; this
0x1800042bf  mov     edi, eax
0x1800042c1  call    ?ReleaseDexCaller@CSession@@QEAAXPEAVDexCaller@@@Z; CSession::ReleaseDexCaller(DexCaller *)
0x1800042c6  mov     rcx, [rbp+57h+var_98]
0x1800042ca  mov     rax, [rcx]
0x1800042cd  mov     rax, [rax+10h]
0x1800042d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042d6  jmp     loc_1800041BF
0x1800042db  mov     edi, 800A000Dh
0x1800042e0  jmp     loc_1800041FC
0x1800042e5  mov     edi, 800A0007h
0x1800042ea  jmp     loc_1800041FC
0x1800042ef  mov     edi, 8000FFFFh
0x1800042f4  jmp     loc_1800041FC
```
