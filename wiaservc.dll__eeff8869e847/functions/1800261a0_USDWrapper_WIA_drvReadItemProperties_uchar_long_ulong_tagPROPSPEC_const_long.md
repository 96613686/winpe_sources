# USDWrapper::WIA_drvReadItemProperties(uchar *,long,ulong,tagPROPSPEC const *,long *)

- ea: `0x1800261a0`
- end: `0x180026379`
- name: `?WIA_drvReadItemProperties@USDWrapper@@UEAAJPEAEJKPEBUtagPROPSPEC@@PEAJ@Z`
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
- `0x1800261a0`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180078010`

## string_xrefs

- `0x180026246`: `USDWrapper::WIA_drvReadItemProperties`
- `0x18002628a`: `USDWrapper::WIA_drvReadItemProperties`
- `0x1800262be`: `USDWrapper::WIA_drvReadItemProperties`
- `0x1800262f3`: `USDWrapper::WIA_drvReadItemProperties`
- `0x180026323`: `USDWrapper::WIA_drvReadItemProperties`
- `0x180026355`: `USDWrapper::WIA_drvReadItemProperties`
- `0x180026230`: `(%ws) completed IWiaMiniDrv::drvReadItemProperties (%u properties) on item (%p) returning hr 0x%08.8X`
- `0x18002626f`: `(%ws) completed IWiaMiniDrv::drvReadItemProperties (%u properties) on item (%p) returning hr 0x%08.8X`
- `0x1800262ac`: `The driver for (%ws) threw an exception (0x%08X) when the WIA service called IWiaMiniDrv::drvReadItemProperties`
- `0x1800262dc`: `The driver for (%ws) threw an exception (0x%08X) when the WIA service called IWiaMiniDrv::drvReadItemProperties`
- `0x180026311`: `We failed to make the call to IWiaMiniDrv::drvReadItemProperties for (%ws) because the driver could not be loaded`
- `0x18002633e`: `We failed to make the call to IWiaMiniDrv::drvReadItemProperties for (%ws) because the driver could not be loaded`

## pseudocode

```c
__int64 __fastcall USDWrapper::WIA_drvReadItemProperties(
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
    v16 = (char *)WiaTrace_TraceLog("We failed to make the call to IWiaMiniDrv::drvReadItemProperties for (%ws) because t"
                                    "he driver could not be loaded");
    WriteDbgTraceErrorWI("USDWrapper::WIA_drvReadItemProperties", v16);
    WiaTrcLib::Free((WiaTrcLib *)v16, v17);
    v18 = (void **)WiaTrace_Trace(
                     "We failed to make the call to IWiaMiniDrv::drvReadItemProperties for (%ws) because the driver could not be loaded",
                     *((_QWORD *)this + 301));
    WiaTrace_ProcessTrace_Ex(v20, v19, (void *)"USDWrapper::WIA_drvReadItemProperties", 1, v18);
  }
  else
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, _QWORD, const struct tagPROPSPEC *, int *))(**((_QWORD **)this + 457) + 64LL))(
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
                    "(%ws) completed IWiaMiniDrv::drvReadItemProperties (%u properties) on item (%p) returning hr 0x%08.8X",
                    *((_QWORD *)this + 301),
                    lpMem,
                    a2,
                    v24);
    WriteDbgTraceInfoWI("USDWrapper::WIA_drvReadItemProperties", v11);
    WiaTrcLib::Free((WiaTrcLib *)v11, v12);
    LODWORD(v25) = v10;
    LODWORD(lpMema) = a4;
    v13 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                     0,
                     0,
                     "(%ws) completed IWiaMiniDrv::drvReadItemProperties (%u properties) on item (%p) returning hr 0x%08.8X",
                     *((_QWORD *)this + 301),
                     lpMema,
                     a2,
                     v25);
    WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"USDWrapper::WIA_drvReadItemProperties", 4, v13);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800261a0  mov     [rsp+arg_8], rbx
0x1800261a5  mov     [rsp+arg_10], rsi
0x1800261aa  mov     [rsp+arg_0], rcx
0x1800261af  push    rdi
0x1800261b0  push    r14
0x1800261b2  push    r15
0x1800261b4  sub     rsp, 50h
0x1800261b8  mov     r14d, r9d
0x1800261bb  mov     ebx, r8d
0x1800261be  mov     r15, rdx
0x1800261c1  mov     rdi, rcx
0x1800261c4  mov     rax, [rcx]
0x1800261c7  mov     edx, 2
0x1800261cc  mov     rax, [rax+68h]
0x1800261d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261d5  mov     esi, eax
0x1800261d7  test    eax, eax
0x1800261d9  js      loc_18002630A
0x1800261df  mov     rcx, [rdi+0E48h]
0x1800261e6  mov     rax, [rcx]
0x1800261e9  mov     rdx, [rsp+68h+arg_28]
0x1800261f1  mov     [rsp+68h+var_40], rdx
0x1800261f6  mov     rdx, [rsp+68h+arg_20]
0x1800261fe  mov     [rsp+68h+lpMem], rdx
0x180026203  mov     r9d, r14d
0x180026206  mov     r8d, ebx
0x180026209  mov     rdx, r15
0x18002620c  mov     rax, [rax+40h]
0x180026210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026215  mov     esi, eax
0x180026217  mov     [rsp+68h+var_28], eax
0x18002621b  mov     [rsp+68h+var_38], eax
0x18002621f  mov     [rsp+68h+var_40], r15
0x180026224  mov     dword ptr [rsp+68h+lpMem], r14d
0x180026229  mov     r9, [rdi+968h]
0x180026230  lea     r8, aWsCompletedIwi_8; "(%ws) completed IWiaMiniDrv::drvReadIte"...
0x180026237  xor     edx, edx
0x180026239  xor     ecx, ecx
0x18002623b  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180026240  mov     rbx, rax
0x180026243  mov     rdx, rax; char *
0x180026246  lea     rcx, aUsdwrapperWiaD_10; "USDWrapper::WIA_drvReadItemProperties"
0x18002624d  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180026252  mov     rcx, rbx; this
0x180026255  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002625a  mov     [rsp+68h+var_38], esi
0x18002625e  mov     [rsp+68h+var_40], r15
0x180026263  mov     dword ptr [rsp+68h+lpMem], r14d
0x180026268  mov     r9, [rdi+968h]
0x18002626f  lea     r8, aWsCompletedIwi_8; "(%ws) completed IWiaMiniDrv::drvReadIte"...
0x180026276  xor     edx, edx
0x180026278  xor     ecx, ecx
0x18002627a  call    WiaTrace_TraceWithSubCompTraceLevel
0x18002627f  mov     [rsp+68h+lpMem], rax; lpMem
0x180026284  mov     r9d, 4; int
0x18002628a  lea     r8, aUsdwrapperWiaD_10; "USDWrapper::WIA_drvReadItemProperties"
0x180026291  call    WiaTrace_ProcessTrace_Ex
0x180026296  jmp     loc_180026361
0x18002629b  mov     esi, eax
0x18002629d  mov     r8d, eax
0x1800262a0  mov     rdi, [rsp+68h+arg_0]
0x1800262a5  mov     rdx, [rdi+968h]
0x1800262ac  lea     rcx, aTheDriverForWs_18; "The driver for (%ws) threw an exception"...
0x1800262b3  call    WiaTrace_TraceLog
0x1800262b8  mov     rbx, rax
0x1800262bb  mov     rdx, rax; char *
0x1800262be  lea     rcx, aUsdwrapperWiaD_10; "USDWrapper::WIA_drvReadItemProperties"
0x1800262c5  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800262ca  mov     rcx, rbx; this
0x1800262cd  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800262d2  mov     r8d, esi
0x1800262d5  mov     rdx, [rdi+968h]
0x1800262dc  lea     rcx, aTheDriverForWs_18; "The driver for (%ws) threw an exception"...
0x1800262e3  call    WiaTrace_Trace
0x1800262e8  mov     [rsp+68h+lpMem], rax; lpMem
0x1800262ed  mov     r9d, 1; int
0x1800262f3  lea     r8, aUsdwrapperWiaD_10; "USDWrapper::WIA_drvReadItemProperties"
0x1800262fa  call    WiaTrace_ProcessTrace_Ex
0x1800262ff  mov     esi, 8021000Eh
0x180026304  mov     [rsp+68h+var_28], esi
0x180026308  jmp     short loc_180026361
0x18002630a  mov     rdx, [rdi+968h]
0x180026311  lea     rcx, aWeFailedToMake_0; "We failed to make the call to IWiaMiniD"...
0x180026318  call    WiaTrace_TraceLog
0x18002631d  mov     rbx, rax
0x180026320  mov     rdx, rax; char *
0x180026323  lea     rcx, aUsdwrapperWiaD_10; "USDWrapper::WIA_drvReadItemProperties"
0x18002632a  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002632f  mov     rcx, rbx; this
0x180026332  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180026337  mov     rdx, [rdi+968h]
0x18002633e  lea     rcx, aWeFailedToMake_0; "We failed to make the call to IWiaMiniD"...
0x180026345  call    WiaTrace_Trace
0x18002634a  mov     [rsp+68h+lpMem], rax; lpMem
0x18002634f  mov     r9d, 1; int
0x180026355  lea     r8, aUsdwrapperWiaD_10; "USDWrapper::WIA_drvReadItemProperties"
0x18002635c  call    WiaTrace_ProcessTrace_Ex
0x180026361  mov     eax, esi
0x180026363  lea     r11, [rsp+68h+var_18]
0x180026368  mov     rbx, [r11+28h]
0x18002636c  mov     rsi, [r11+30h]
0x180026370  mov     rsp, r11
0x180026373  pop     r15
0x180026375  pop     r14
0x180026377  pop     rdi
0x180026378  retn
```
