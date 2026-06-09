# USDWrapper::WIA_drvInitItemProperties(uchar *,long,long *)

- ea: `0x18004e170`
- end: `0x18004e323`
- name: `?WIA_drvInitItemProperties@USDWrapper@@UEAAJPEAEJPEAJ@Z`
- size: `435`
- prototype: `__int64 __fastcall(USDWrapper *__hidden this, unsigned __int8 *, int, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18004e170`
- `0x180078010`

## string_xrefs

- `0x18004e1e1`: `(%ws) completed IWiaMiniDrv::drvInitItemProperties on item (%p) returning hr 0x%08.8X`
- `0x18004e21b`: `(%ws) completed IWiaMiniDrv::drvInitItemProperties on item (%p) returning hr 0x%08.8X`
- `0x18004e258`: `The driver for (%ws) threw an exception (0x%08X) when the WIA service called IWiaMiniDrv::drvInitItemProperties`
- `0x18004e288`: `The driver for (%ws) threw an exception (0x%08X) when the WIA service called IWiaMiniDrv::drvInitItemProperties`
- `0x18004e1f7`: `USDWrapper::WIA_drvInitItemProperties`
- `0x18004e236`: `USDWrapper::WIA_drvInitItemProperties`
- `0x18004e26a`: `USDWrapper::WIA_drvInitItemProperties`
- `0x18004e29f`: `USDWrapper::WIA_drvInitItemProperties`
- `0x18004e2cf`: `USDWrapper::WIA_drvInitItemProperties`
- `0x18004e301`: `USDWrapper::WIA_drvInitItemProperties`
- `0x18004e2bd`: `We failed to make the call to IWiaMiniDrv::drvInitItemProperties for (%ws) because the driver could not be loaded`
- `0x18004e2ea`: `We failed to make the call to IWiaMiniDrv::drvInitItemProperties for (%ws) because the driver could not be loaded`

## pseudocode

```c
__int64 __fastcall USDWrapper::WIA_drvInitItemProperties(
        USDWrapper *this,
        unsigned __int8 *a2,
        unsigned int a3,
        int *a4)
{
  int v8; // esi
  char *v9; // rbx
  void *v10; // rdx
  void **lpMem; // rax
  void *v12; // rdx
  __int64 v13; // rcx
  char *v14; // rbx
  void *v15; // rdx
  void **v16; // rax
  void *v17; // rdx
  __int64 v18; // rcx
  int v20; // [rsp+28h] [rbp-30h]
  __int64 v21; // [rsp+28h] [rbp-30h]
  int v22; // [rsp+30h] [rbp-28h]

  v8 = (*(__int64 (__fastcall **)(USDWrapper *, __int64))(*(_QWORD *)this + 104LL))(this, 2);
  if ( v8 < 0 )
  {
    v14 = (char *)WiaTrace_TraceLog("We failed to make the call to IWiaMiniDrv::drvInitItemProperties for (%ws) because t"
                                    "he driver could not be loaded");
    WriteDbgTraceErrorWI("USDWrapper::WIA_drvInitItemProperties", v14);
    WiaTrcLib::Free((WiaTrcLib *)v14, v15);
    v16 = (void **)WiaTrace_Trace(
                     "We failed to make the call to IWiaMiniDrv::drvInitItemProperties for (%ws) because the driver could not be loaded",
                     *((_QWORD *)this + 301));
    WiaTrace_ProcessTrace_Ex(v18, v17, (void *)"USDWrapper::WIA_drvInitItemProperties", 1, v16);
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, int *))(**((_QWORD **)this + 457) + 40LL))(
           *((_QWORD *)this + 457),
           a2,
           a3,
           a4);
    v22 = v8;
    v20 = v8;
    v9 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                   0,
                   0,
                   "(%ws) completed IWiaMiniDrv::drvInitItemProperties on item (%p) returning hr 0x%08.8X",
                   *((_QWORD *)this + 301),
                   a2,
                   v20,
                   v22);
    WriteDbgTraceInfoWI("USDWrapper::WIA_drvInitItemProperties", v9);
    WiaTrcLib::Free((WiaTrcLib *)v9, v10);
    LODWORD(v21) = v8;
    lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       0,
                       0,
                       "(%ws) completed IWiaMiniDrv::drvInitItemProperties on item (%p) returning hr 0x%08.8X",
                       *((_QWORD *)this + 301),
                       a2,
                       v21);
    WiaTrace_ProcessTrace_Ex(v13, v12, (void *)"USDWrapper::WIA_drvInitItemProperties", 4, lpMem);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004e170  mov     [rsp+arg_8], rbx
0x18004e175  mov     [rsp+arg_10], rsi
0x18004e17a  mov     [rsp+arg_0], rcx
0x18004e17f  push    rdi
0x18004e180  push    r14
0x18004e182  push    r15
0x18004e184  sub     rsp, 40h
0x18004e188  mov     rbx, r9
0x18004e18b  mov     r15d, r8d
0x18004e18e  mov     r14, rdx
0x18004e191  mov     rdi, rcx
0x18004e194  mov     rax, [rcx]
0x18004e197  mov     edx, 2
0x18004e19c  mov     rax, [rax+68h]
0x18004e1a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e1a5  mov     esi, eax
0x18004e1a7  test    eax, eax
0x18004e1a9  js      loc_18004E2B6
0x18004e1af  mov     rcx, [rdi+0E48h]
0x18004e1b6  mov     rax, [rcx]
0x18004e1b9  mov     r9, rbx
0x18004e1bc  mov     r8d, r15d
0x18004e1bf  mov     rdx, r14
0x18004e1c2  mov     rax, [rax+28h]
0x18004e1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e1cb  mov     esi, eax
0x18004e1cd  mov     [rsp+58h+var_28], eax
0x18004e1d1  mov     dword ptr [rsp+58h+var_30], eax
0x18004e1d5  mov     [rsp+58h+lpMem], r14
0x18004e1da  mov     r9, [rdi+968h]
0x18004e1e1  lea     r8, aWsCompletedIwi_12; "(%ws) completed IWiaMiniDrv::drvInitIte"...
0x18004e1e8  xor     edx, edx
0x18004e1ea  xor     ecx, ecx
0x18004e1ec  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18004e1f1  mov     rbx, rax
0x18004e1f4  mov     rdx, rax; char *
0x18004e1f7  lea     rcx, aUsdwrapperWiaD_0; "USDWrapper::WIA_drvInitItemProperties"
0x18004e1fe  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18004e203  mov     rcx, rbx; this
0x18004e206  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004e20b  mov     dword ptr [rsp+58h+var_30], esi
0x18004e20f  mov     [rsp+58h+lpMem], r14
0x18004e214  mov     r9, [rdi+968h]
0x18004e21b  lea     r8, aWsCompletedIwi_12; "(%ws) completed IWiaMiniDrv::drvInitIte"...
0x18004e222  xor     edx, edx
0x18004e224  xor     ecx, ecx
0x18004e226  call    WiaTrace_TraceWithSubCompTraceLevel
0x18004e22b  mov     [rsp+58h+lpMem], rax; lpMem
0x18004e230  mov     r9d, 4; int
0x18004e236  lea     r8, aUsdwrapperWiaD_0; "USDWrapper::WIA_drvInitItemProperties"
0x18004e23d  call    WiaTrace_ProcessTrace_Ex
0x18004e242  jmp     loc_18004E30D
0x18004e247  mov     esi, eax
0x18004e249  mov     r8d, eax
0x18004e24c  mov     rdi, [rsp+58h+arg_0]
0x18004e251  mov     rdx, [rdi+968h]
0x18004e258  lea     rcx, aTheDriverForWs_6; "The driver for (%ws) threw an exception"...
0x18004e25f  call    WiaTrace_TraceLog
0x18004e264  mov     rbx, rax
0x18004e267  mov     rdx, rax; char *
0x18004e26a  lea     rcx, aUsdwrapperWiaD_0; "USDWrapper::WIA_drvInitItemProperties"
0x18004e271  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004e276  mov     rcx, rbx; this
0x18004e279  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004e27e  mov     r8d, esi
0x18004e281  mov     rdx, [rdi+968h]
0x18004e288  lea     rcx, aTheDriverForWs_6; "The driver for (%ws) threw an exception"...
0x18004e28f  call    WiaTrace_Trace
0x18004e294  mov     [rsp+58h+lpMem], rax; lpMem
0x18004e299  mov     r9d, 1; int
0x18004e29f  lea     r8, aUsdwrapperWiaD_0; "USDWrapper::WIA_drvInitItemProperties"
0x18004e2a6  call    WiaTrace_ProcessTrace_Ex
0x18004e2ab  mov     esi, 8021000Eh
0x18004e2b0  mov     [rsp+58h+var_28], esi
0x18004e2b4  jmp     short loc_18004E30D
0x18004e2b6  mov     rdx, [rdi+968h]
0x18004e2bd  lea     rcx, aWeFailedToMake_2; "We failed to make the call to IWiaMiniD"...
0x18004e2c4  call    WiaTrace_TraceLog
0x18004e2c9  mov     rbx, rax
0x18004e2cc  mov     rdx, rax; char *
0x18004e2cf  lea     rcx, aUsdwrapperWiaD_0; "USDWrapper::WIA_drvInitItemProperties"
0x18004e2d6  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004e2db  mov     rcx, rbx; this
0x18004e2de  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004e2e3  mov     rdx, [rdi+968h]
0x18004e2ea  lea     rcx, aWeFailedToMake_2; "We failed to make the call to IWiaMiniD"...
0x18004e2f1  call    WiaTrace_Trace
0x18004e2f6  mov     [rsp+58h+lpMem], rax; lpMem
0x18004e2fb  mov     r9d, 1; int
0x18004e301  lea     r8, aUsdwrapperWiaD_0; "USDWrapper::WIA_drvInitItemProperties"
0x18004e308  call    WiaTrace_ProcessTrace_Ex
0x18004e30d  mov     eax, esi
0x18004e30f  mov     rbx, [rsp+58h+arg_8]
0x18004e314  mov     rsi, [rsp+58h+arg_10]
0x18004e319  add     rsp, 40h
0x18004e31d  pop     r15
0x18004e31f  pop     r14
0x18004e321  pop     rdi
0x18004e322  retn
```
