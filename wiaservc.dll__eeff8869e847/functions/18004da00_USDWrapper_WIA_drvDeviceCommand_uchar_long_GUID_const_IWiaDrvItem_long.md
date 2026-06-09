# USDWrapper::WIA_drvDeviceCommand(uchar *,long,_GUID const *,IWiaDrvItem * *,long *)

- ea: `0x18004da00`
- end: `0x18004dbcf`
- name: `?WIA_drvDeviceCommand@USDWrapper@@UEAAJPEAEJPEBU_GUID@@PEAPEAUIWiaDrvItem@@PEAJ@Z`
- size: `463`
- prototype: `__int64 __fastcall(USDWrapper *__hidden this, unsigned __int8 *, int, const struct _GUID *, struct IWiaDrvItem **, int *)`
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
- `0x18004da00`
- `0x180078010`

## string_xrefs

- `0x18004daa1`: `USDWrapper::WIA_drvDeviceCommand`
- `0x18004dae0`: `USDWrapper::WIA_drvDeviceCommand`
- `0x18004db14`: `USDWrapper::WIA_drvDeviceCommand`
- `0x18004db49`: `USDWrapper::WIA_drvDeviceCommand`
- `0x18004db79`: `USDWrapper::WIA_drvDeviceCommand`
- `0x18004dbab`: `USDWrapper::WIA_drvDeviceCommand`
- `0x18004da8b`: `(%ws) completed IWiaMiniDrv::drvDeviceCommand on item (%p) returning hr 0x%08.8X`
- `0x18004dac5`: `(%ws) completed IWiaMiniDrv::drvDeviceCommand on item (%p) returning hr 0x%08.8X`
- `0x18004db67`: `We failed to make the call to IWiaMiniDrv::drvDeviceCommand for (%ws) because the driver could not be loaded`
- `0x18004db94`: `We failed to make the call to IWiaMiniDrv::drvDeviceCommand for (%ws) because the driver could not be loaded`
- `0x18004db02`: `The driver for (%ws) threw an exception (0x%08X) when the WIA service called IWiaMiniDrv::drvDeviceCommand`
- `0x18004db32`: `The driver for (%ws) threw an exception (0x%08X) when the WIA service called IWiaMiniDrv::drvDeviceCommand`

## pseudocode

```c
__int64 __fastcall USDWrapper::WIA_drvDeviceCommand(
        USDWrapper *this,
        unsigned __int8 *a2,
        unsigned int a3,
        const struct _GUID *a4,
        struct IWiaDrvItem **a5,
        int *a6)
{
  int v10; // esi
  char *v11; // rbx
  void *v12; // rdx
  void **lpMem; // rax
  void *v14; // rdx
  __int64 v15; // rcx
  char *v16; // rbx
  void *v17; // rdx
  void **v18; // rax
  void *v19; // rdx
  __int64 v20; // rcx
  __int64 v22; // [rsp+28h] [rbp-40h]
  __int64 v23; // [rsp+28h] [rbp-40h]

  v10 = (*(__int64 (__fastcall **)(USDWrapper *, __int64))(*(_QWORD *)this + 104LL))(this, 2);
  if ( v10 < 0 )
  {
    v16 = (char *)WiaTrace_TraceLog("We failed to make the call to IWiaMiniDrv::drvDeviceCommand for (%ws) because the dr"
                                    "iver could not be loaded");
    WriteDbgTraceErrorWI("USDWrapper::WIA_drvDeviceCommand", v16);
    WiaTrcLib::Free((WiaTrcLib *)v16, v17);
    v18 = (void **)WiaTrace_Trace(
                     "We failed to make the call to IWiaMiniDrv::drvDeviceCommand for (%ws) because the driver could not be loaded",
                     *((_QWORD *)this + 301));
    WiaTrace_ProcessTrace_Ex(v20, v19, (void *)"USDWrapper::WIA_drvDeviceCommand", 1, v18);
  }
  else
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, const struct _GUID *, struct IWiaDrvItem **, int *))(**((_QWORD **)this + 457) + 104LL))(
            *((_QWORD *)this + 457),
            a2,
            a3,
            a4,
            a5,
            a6);
    LODWORD(v22) = v10;
    v11 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                    0,
                    0,
                    "(%ws) completed IWiaMiniDrv::drvDeviceCommand on item (%p) returning hr 0x%08.8X",
                    *((_QWORD *)this + 301),
                    a2,
                    v22);
    WriteDbgTraceInfoWI("USDWrapper::WIA_drvDeviceCommand", v11);
    WiaTrcLib::Free((WiaTrcLib *)v11, v12);
    LODWORD(v23) = v10;
    lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       0,
                       0,
                       "(%ws) completed IWiaMiniDrv::drvDeviceCommand on item (%p) returning hr 0x%08.8X",
                       *((_QWORD *)this + 301),
                       a2,
                       v23);
    WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"USDWrapper::WIA_drvDeviceCommand", 4, lpMem);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004da00  mov     [rsp+arg_8], rbx
0x18004da05  mov     [rsp+arg_10], rsi
0x18004da0a  mov     [rsp+arg_0], rcx
0x18004da0f  push    rdi
0x18004da10  push    r14
0x18004da12  push    r15
0x18004da14  sub     rsp, 50h
0x18004da18  mov     rbx, r9
0x18004da1b  mov     r15d, r8d
0x18004da1e  mov     r14, rdx
0x18004da21  mov     rdi, rcx
0x18004da24  mov     rax, [rcx]
0x18004da27  mov     edx, 2
0x18004da2c  mov     rax, [rax+68h]
0x18004da30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da35  mov     esi, eax
0x18004da37  test    eax, eax
0x18004da39  js      loc_18004DB60
0x18004da3f  mov     rcx, [rdi+0E48h]
0x18004da46  mov     rax, [rcx]
0x18004da49  mov     rdx, [rsp+68h+arg_28]
0x18004da51  mov     [rsp+68h+var_40], rdx
0x18004da56  mov     rdx, [rsp+68h+arg_20]
0x18004da5e  mov     [rsp+68h+lpMem], rdx
0x18004da63  mov     r9, rbx
0x18004da66  mov     r8d, r15d
0x18004da69  mov     rdx, r14
0x18004da6c  mov     rax, [rax+68h]
0x18004da70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da75  mov     esi, eax
0x18004da77  mov     [rsp+68h+var_28], eax
0x18004da7b  mov     dword ptr [rsp+68h+var_40], eax
0x18004da7f  mov     [rsp+68h+lpMem], r14
0x18004da84  mov     r9, [rdi+968h]
0x18004da8b  lea     r8, aWsCompletedIwi_9; "(%ws) completed IWiaMiniDrv::drvDeviceC"...
0x18004da92  xor     edx, edx
0x18004da94  xor     ecx, ecx
0x18004da96  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18004da9b  mov     rbx, rax
0x18004da9e  mov     rdx, rax; char *
0x18004daa1  lea     rcx, aUsdwrapperWiaD_13; "USDWrapper::WIA_drvDeviceCommand"
0x18004daa8  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18004daad  mov     rcx, rbx; this
0x18004dab0  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004dab5  mov     dword ptr [rsp+68h+var_40], esi
0x18004dab9  mov     [rsp+68h+lpMem], r14
0x18004dabe  mov     r9, [rdi+968h]
0x18004dac5  lea     r8, aWsCompletedIwi_9; "(%ws) completed IWiaMiniDrv::drvDeviceC"...
0x18004dacc  xor     edx, edx
0x18004dace  xor     ecx, ecx
0x18004dad0  call    WiaTrace_TraceWithSubCompTraceLevel
0x18004dad5  mov     [rsp+68h+lpMem], rax; lpMem
0x18004dada  mov     r9d, 4; int
0x18004dae0  lea     r8, aUsdwrapperWiaD_13; "USDWrapper::WIA_drvDeviceCommand"
0x18004dae7  call    WiaTrace_ProcessTrace_Ex
0x18004daec  jmp     loc_18004DBB7
0x18004daf1  mov     esi, eax
0x18004daf3  mov     r8d, eax
0x18004daf6  mov     rdi, [rsp+68h+arg_0]
0x18004dafb  mov     rdx, [rdi+968h]
0x18004db02  lea     rcx, aTheDriverForWs_10; "The driver for (%ws) threw an exception"...
0x18004db09  call    WiaTrace_TraceLog
0x18004db0e  mov     rbx, rax
0x18004db11  mov     rdx, rax; char *
0x18004db14  lea     rcx, aUsdwrapperWiaD_13; "USDWrapper::WIA_drvDeviceCommand"
0x18004db1b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004db20  mov     rcx, rbx; this
0x18004db23  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004db28  mov     r8d, esi
0x18004db2b  mov     rdx, [rdi+968h]
0x18004db32  lea     rcx, aTheDriverForWs_10; "The driver for (%ws) threw an exception"...
0x18004db39  call    WiaTrace_Trace
0x18004db3e  mov     [rsp+68h+lpMem], rax; lpMem
0x18004db43  mov     r9d, 1; int
0x18004db49  lea     r8, aUsdwrapperWiaD_13; "USDWrapper::WIA_drvDeviceCommand"
0x18004db50  call    WiaTrace_ProcessTrace_Ex
0x18004db55  mov     esi, 8021000Eh
0x18004db5a  mov     [rsp+68h+var_28], esi
0x18004db5e  jmp     short loc_18004DBB7
0x18004db60  mov     rdx, [rdi+968h]
0x18004db67  lea     rcx, aWeFailedToMake_10; "We failed to make the call to IWiaMiniD"...
0x18004db6e  call    WiaTrace_TraceLog
0x18004db73  mov     rbx, rax
0x18004db76  mov     rdx, rax; char *
0x18004db79  lea     rcx, aUsdwrapperWiaD_13; "USDWrapper::WIA_drvDeviceCommand"
0x18004db80  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004db85  mov     rcx, rbx; this
0x18004db88  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004db8d  mov     rdx, [rdi+968h]
0x18004db94  lea     rcx, aWeFailedToMake_10; "We failed to make the call to IWiaMiniD"...
0x18004db9b  call    WiaTrace_Trace
0x18004dba0  mov     [rsp+68h+lpMem], rax; lpMem
0x18004dba5  mov     r9d, 1; int
0x18004dbab  lea     r8, aUsdwrapperWiaD_13; "USDWrapper::WIA_drvDeviceCommand"
0x18004dbb2  call    WiaTrace_ProcessTrace_Ex
0x18004dbb7  mov     eax, esi
0x18004dbb9  lea     r11, [rsp+68h+var_18]
0x18004dbbe  mov     rbx, [r11+28h]
0x18004dbc2  mov     rsi, [r11+30h]
0x18004dbc6  mov     rsp, r11
0x18004dbc9  pop     r15
0x18004dbcb  pop     r14
0x18004dbcd  pop     rdi
0x18004dbce  retn
```
