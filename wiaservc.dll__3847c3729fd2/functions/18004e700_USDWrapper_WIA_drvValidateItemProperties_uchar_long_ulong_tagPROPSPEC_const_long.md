# USDWrapper::WIA_drvValidateItemProperties(uchar *,long,ulong,tagPROPSPEC const *,long *)

- ea: `0x18004e700`
- end: `0x18004e8d9`
- name: `?WIA_drvValidateItemProperties@USDWrapper@@UEAAJPEAEJKPEBUtagPROPSPEC@@PEAJ@Z`
- size: `473`
- prototype: `__int64 __fastcall(USDWrapper *__hidden this, unsigned __int8 *, int, unsigned int, const struct tagPROPSPEC *, int *)`
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
- `0x18004e700`
- `0x180078010`

## string_xrefs

- `0x18004e790`: `(%ws) completed IWiaMiniDrv::drvValidateItemProperties (%u properties) on item (%p) returning hr 0x%08.8X`
- `0x18004e7cf`: `(%ws) completed IWiaMiniDrv::drvValidateItemProperties (%u properties) on item (%p) returning hr 0x%08.8X`
- `0x18004e80c`: `The driver for (%ws) threw an exception (0x%08X) when the WIA service called IWiaMiniDrv::drvValidateItemProperties`
- `0x18004e83c`: `The driver for (%ws) threw an exception (0x%08X) when the WIA service called IWiaMiniDrv::drvValidateItemProperties`
- `0x18004e7a6`: `USDWrapper::WIA_drvValidateItemProperties`
- `0x18004e7ea`: `USDWrapper::WIA_drvValidateItemProperties`
- `0x18004e81e`: `USDWrapper::WIA_drvValidateItemProperties`
- `0x18004e853`: `USDWrapper::WIA_drvValidateItemProperties`
- `0x18004e883`: `USDWrapper::WIA_drvValidateItemProperties`
- `0x18004e8b5`: `USDWrapper::WIA_drvValidateItemProperties`
- `0x18004e871`: `We failed to make the call to IWiaMiniDrv::drvValidateItemProperties for (%ws) because the driver could not be loaded`
- `0x18004e89e`: `We failed to make the call to IWiaMiniDrv::drvValidateItemProperties for (%ws) because the driver could not be loaded`

## pseudocode

```c
__int64 __fastcall USDWrapper::WIA_drvValidateItemProperties(
        USDWrapper *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int a4,
        const struct tagPROPSPEC *a5,
        int *a6)
{
  int v10; // esi
  char *v11; // rbx
  void *v12; // rdx
  void **v13; // rax
  void *v14; // rdx
  __int64 v15; // rcx
  char *v16; // rbx
  void *v17; // rdx
  void **v18; // rax
  void *v19; // rdx
  __int64 v20; // rcx
  LPVOID lpMem; // [rsp+20h] [rbp-48h]
  LPVOID lpMema; // [rsp+20h] [rbp-48h]
  int v24; // [rsp+30h] [rbp-38h]
  __int64 v25; // [rsp+30h] [rbp-38h]

  v10 = (*(__int64 (__fastcall **)(USDWrapper *, __int64))(*(_QWORD *)this + 104LL))(this, 2);
  if ( v10 < 0 )
  {
    v16 = (char *)WiaTrace_TraceLog("We failed to make the call to IWiaMiniDrv::drvValidateItemProperties for (%ws) becau"
                                    "se the driver could not be loaded");
    WriteDbgTraceErrorWI("USDWrapper::WIA_drvValidateItemProperties", v16);
    WiaTrcLib::Free((WiaTrcLib *)v16, v17);
    v18 = (void **)WiaTrace_Trace(
                     "We failed to make the call to IWiaMiniDrv::drvValidateItemProperties for (%ws) because the driver c"
                     "ould not be loaded",
                     *((_QWORD *)this + 301));
    WiaTrace_ProcessTrace_Ex(v20, v19, (void *)"USDWrapper::WIA_drvValidateItemProperties", 1, v18);
  }
  else
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, _QWORD, const struct tagPROPSPEC *, int *))(**((_QWORD **)this + 457) + 48LL))(
            *((_QWORD *)this + 457),
            a2,
            a3,
            a4,
            a5,
            a6);
    v24 = v10;
    LODWORD(lpMem) = a4;
    v11 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                    0,
                    0,
                    "(%ws) completed IWiaMiniDrv::drvValidateItemProperties (%u properties) on item (%p) returning hr 0x%08.8X",
                    *((_QWORD *)this + 301),
                    lpMem,
                    a2,
                    v24);
    WriteDbgTraceInfoWI("USDWrapper::WIA_drvValidateItemProperties", v11);
    WiaTrcLib::Free((WiaTrcLib *)v11, v12);
    LODWORD(v25) = v10;
    LODWORD(lpMema) = a4;
    v13 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                     0,
                     0,
                     "(%ws) completed IWiaMiniDrv::drvValidateItemProperties (%u properties) on item (%p) returning hr 0x%08.8X",
                     *((_QWORD *)this + 301),
                     lpMema,
                     a2,
                     v25);
    WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"USDWrapper::WIA_drvValidateItemProperties", 4, v13);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004e700  mov     [rsp+arg_8], rbx
0x18004e705  mov     [rsp+arg_10], rsi
0x18004e70a  mov     [rsp+arg_0], rcx
0x18004e70f  push    rdi
0x18004e710  push    r14
0x18004e712  push    r15
0x18004e714  sub     rsp, 50h
0x18004e718  mov     r14d, r9d
0x18004e71b  mov     ebx, r8d
0x18004e71e  mov     r15, rdx
0x18004e721  mov     rdi, rcx
0x18004e724  mov     rax, [rcx]
0x18004e727  mov     edx, 2
0x18004e72c  mov     rax, [rax+68h]
0x18004e730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e735  mov     esi, eax
0x18004e737  test    eax, eax
0x18004e739  js      loc_18004E86A
0x18004e73f  mov     rcx, [rdi+0E48h]
0x18004e746  mov     rax, [rcx]
0x18004e749  mov     rdx, [rsp+68h+arg_28]
0x18004e751  mov     [rsp+68h+var_40], rdx
0x18004e756  mov     rdx, [rsp+68h+arg_20]
0x18004e75e  mov     [rsp+68h+lpMem], rdx
0x18004e763  mov     r9d, r14d
0x18004e766  mov     r8d, ebx
0x18004e769  mov     rdx, r15
0x18004e76c  mov     rax, [rax+30h]
0x18004e770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e775  mov     esi, eax
0x18004e777  mov     [rsp+68h+var_28], eax
0x18004e77b  mov     [rsp+68h+var_38], eax
0x18004e77f  mov     [rsp+68h+var_40], r15
0x18004e784  mov     dword ptr [rsp+68h+lpMem], r14d
0x18004e789  mov     r9, [rdi+968h]
0x18004e790  lea     r8, aWsCompletedIwi_7; "(%ws) completed IWiaMiniDrv::drvValidat"...
0x18004e797  xor     edx, edx
0x18004e799  xor     ecx, ecx
0x18004e79b  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18004e7a0  mov     rbx, rax
0x18004e7a3  mov     rdx, rax; char *
0x18004e7a6  lea     rcx, aUsdwrapperWiaD_6; "USDWrapper::WIA_drvValidateItemProperti"...
0x18004e7ad  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18004e7b2  mov     rcx, rbx; this
0x18004e7b5  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004e7ba  mov     [rsp+68h+var_38], esi
0x18004e7be  mov     [rsp+68h+var_40], r15
0x18004e7c3  mov     dword ptr [rsp+68h+lpMem], r14d
0x18004e7c8  mov     r9, [rdi+968h]
0x18004e7cf  lea     r8, aWsCompletedIwi_7; "(%ws) completed IWiaMiniDrv::drvValidat"...
0x18004e7d6  xor     edx, edx
0x18004e7d8  xor     ecx, ecx
0x18004e7da  call    WiaTrace_TraceWithSubCompTraceLevel
0x18004e7df  mov     [rsp+68h+lpMem], rax; lpMem
0x18004e7e4  mov     r9d, 4; int
0x18004e7ea  lea     r8, aUsdwrapperWiaD_6; "USDWrapper::WIA_drvValidateItemProperti"...
0x18004e7f1  call    WiaTrace_ProcessTrace_Ex
0x18004e7f6  jmp     loc_18004E8C1
0x18004e7fb  mov     esi, eax
0x18004e7fd  mov     r8d, eax
0x18004e800  mov     rdi, [rsp+68h+arg_0]
0x18004e805  mov     rdx, [rdi+968h]
0x18004e80c  lea     rcx, aTheDriverForWs_19; "The driver for (%ws) threw an exception"...
0x18004e813  call    WiaTrace_TraceLog
0x18004e818  mov     rbx, rax
0x18004e81b  mov     rdx, rax; char *
0x18004e81e  lea     rcx, aUsdwrapperWiaD_6; "USDWrapper::WIA_drvValidateItemProperti"...
0x18004e825  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004e82a  mov     rcx, rbx; this
0x18004e82d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004e832  mov     r8d, esi
0x18004e835  mov     rdx, [rdi+968h]
0x18004e83c  lea     rcx, aTheDriverForWs_19; "The driver for (%ws) threw an exception"...
0x18004e843  call    WiaTrace_Trace
0x18004e848  mov     [rsp+68h+lpMem], rax; lpMem
0x18004e84d  mov     r9d, 1; int
0x18004e853  lea     r8, aUsdwrapperWiaD_6; "USDWrapper::WIA_drvValidateItemProperti"...
0x18004e85a  call    WiaTrace_ProcessTrace_Ex
0x18004e85f  mov     esi, 8021000Eh
0x18004e864  mov     [rsp+68h+var_28], esi
0x18004e868  jmp     short loc_18004E8C1
0x18004e86a  mov     rdx, [rdi+968h]
0x18004e871  lea     rcx, aWeFailedToMake_23; "We failed to make the call to IWiaMiniD"...
0x18004e878  call    WiaTrace_TraceLog
0x18004e87d  mov     rbx, rax
0x18004e880  mov     rdx, rax; char *
0x18004e883  lea     rcx, aUsdwrapperWiaD_6; "USDWrapper::WIA_drvValidateItemProperti"...
0x18004e88a  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004e88f  mov     rcx, rbx; this
0x18004e892  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004e897  mov     rdx, [rdi+968h]
0x18004e89e  lea     rcx, aWeFailedToMake_23; "We failed to make the call to IWiaMiniD"...
0x18004e8a5  call    WiaTrace_Trace
0x18004e8aa  mov     [rsp+68h+lpMem], rax; lpMem
0x18004e8af  mov     r9d, 1; int
0x18004e8b5  lea     r8, aUsdwrapperWiaD_6; "USDWrapper::WIA_drvValidateItemProperti"...
0x18004e8bc  call    WiaTrace_ProcessTrace_Ex
0x18004e8c1  mov     eax, esi
0x18004e8c3  lea     r11, [rsp+68h+var_18]
0x18004e8c8  mov     rbx, [r11+28h]
0x18004e8cc  mov     rsi, [r11+30h]
0x18004e8d0  mov     rsp, r11
0x18004e8d3  pop     r15
0x18004e8d5  pop     r14
0x18004e8d7  pop     rdi
0x18004e8d8  retn
```
