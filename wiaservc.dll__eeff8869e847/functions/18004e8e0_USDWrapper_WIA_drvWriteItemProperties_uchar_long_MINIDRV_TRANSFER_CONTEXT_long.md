# USDWrapper::WIA_drvWriteItemProperties(uchar *,long,_MINIDRV_TRANSFER_CONTEXT *,long *)

- ea: `0x18004e8e0`
- end: `0x18004eaa0`
- name: `?WIA_drvWriteItemProperties@USDWrapper@@UEAAJPEAEJPEAU_MINIDRV_TRANSFER_CONTEXT@@PEAJ@Z`
- size: `448`
- prototype: `__int64 __fastcall(USDWrapper *__hidden this, unsigned __int8 *, int, struct _MINIDRV_TRANSFER_CONTEXT *, int *)`
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
- `0x18004e8e0`
- `0x180078010`

## string_xrefs

- `0x18004e95e`: `(%ws) completed IWiaMiniDrv::drvWriteItemProperties on item (%p) returning hr 0x%08.8X`
- `0x18004e998`: `(%ws) completed IWiaMiniDrv::drvWriteItemProperties on item (%p) returning hr 0x%08.8X`
- `0x18004e9d5`: `The driver for (%ws) threw an exception (0x%08X) when the WIA service called IWiaMiniDrv::drvWriteItemProperties`
- `0x18004ea05`: `The driver for (%ws) threw an exception (0x%08X) when the WIA service called IWiaMiniDrv::drvWriteItemProperties`
- `0x18004e974`: `USDWrapper::WIA_drvWriteItemProperties`
- `0x18004e9b3`: `USDWrapper::WIA_drvWriteItemProperties`
- `0x18004e9e7`: `USDWrapper::WIA_drvWriteItemProperties`
- `0x18004ea1c`: `USDWrapper::WIA_drvWriteItemProperties`
- `0x18004ea4c`: `USDWrapper::WIA_drvWriteItemProperties`
- `0x18004ea7e`: `USDWrapper::WIA_drvWriteItemProperties`
- `0x18004ea3a`: `We failed to make the call to IWiaMiniDrv::drvWriteItemProperties for (%ws) because the driver could not be loaded`
- `0x18004ea67`: `We failed to make the call to IWiaMiniDrv::drvWriteItemProperties for (%ws) because the driver could not be loaded`

## pseudocode

```c
__int64 __fastcall USDWrapper::WIA_drvWriteItemProperties(
        USDWrapper *this,
        unsigned __int8 *a2,
        unsigned int a3,
        struct _MINIDRV_TRANSFER_CONTEXT *a4,
        int *a5)
{
  int v9; // esi
  char *v10; // rbx
  void *v11; // rdx
  void **lpMem; // rax
  void *v13; // rdx
  __int64 v14; // rcx
  char *v15; // rbx
  void *v16; // rdx
  void **v17; // rax
  void *v18; // rdx
  __int64 v19; // rcx
  int v21; // [rsp+28h] [rbp-30h]
  __int64 v22; // [rsp+28h] [rbp-30h]
  int v23; // [rsp+30h] [rbp-28h]

  v9 = (*(__int64 (__fastcall **)(USDWrapper *, __int64))(*(_QWORD *)this + 104LL))(this, 2);
  if ( v9 < 0 )
  {
    v15 = (char *)WiaTrace_TraceLog("We failed to make the call to IWiaMiniDrv::drvWriteItemProperties for (%ws) because "
                                    "the driver could not be loaded");
    WriteDbgTraceErrorWI("USDWrapper::WIA_drvWriteItemProperties", v15);
    WiaTrcLib::Free((WiaTrcLib *)v15, v16);
    v17 = (void **)WiaTrace_Trace(
                     "We failed to make the call to IWiaMiniDrv::drvWriteItemProperties for (%ws) because the driver could not be loaded",
                     *((_QWORD *)this + 301));
    WiaTrace_ProcessTrace_Ex(v19, v18, (void *)"USDWrapper::WIA_drvWriteItemProperties", 1, v17);
  }
  else
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, struct _MINIDRV_TRANSFER_CONTEXT *, int *))(**((_QWORD **)this + 457) + 56LL))(
           *((_QWORD *)this + 457),
           a2,
           a3,
           a4,
           a5);
    v23 = v9;
    v21 = v9;
    v10 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                    0,
                    0,
                    "(%ws) completed IWiaMiniDrv::drvWriteItemProperties on item (%p) returning hr 0x%08.8X",
                    *((_QWORD *)this + 301),
                    a2,
                    v21,
                    v23);
    WriteDbgTraceInfoWI("USDWrapper::WIA_drvWriteItemProperties", v10);
    WiaTrcLib::Free((WiaTrcLib *)v10, v11);
    LODWORD(v22) = v9;
    lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       0,
                       0,
                       "(%ws) completed IWiaMiniDrv::drvWriteItemProperties on item (%p) returning hr 0x%08.8X",
                       *((_QWORD *)this + 301),
                       a2,
                       v22);
    WiaTrace_ProcessTrace_Ex(v14, v13, (void *)"USDWrapper::WIA_drvWriteItemProperties", 4, lpMem);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004e8e0  mov     [rsp+arg_8], rbx
0x18004e8e5  mov     [rsp+arg_10], rsi
0x18004e8ea  mov     [rsp+arg_0], rcx
0x18004e8ef  push    rdi
0x18004e8f0  push    r14
0x18004e8f2  push    r15
0x18004e8f4  sub     rsp, 40h
0x18004e8f8  mov     rbx, r9
0x18004e8fb  mov     r15d, r8d
0x18004e8fe  mov     r14, rdx
0x18004e901  mov     rdi, rcx
0x18004e904  mov     rax, [rcx]
0x18004e907  mov     edx, 2
0x18004e90c  mov     rax, [rax+68h]
0x18004e910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e915  mov     esi, eax
0x18004e917  test    eax, eax
0x18004e919  js      loc_18004EA33
0x18004e91f  mov     rcx, [rdi+0E48h]
0x18004e926  mov     rax, [rcx]
0x18004e929  mov     rdx, [rsp+58h+arg_20]
0x18004e931  mov     [rsp+58h+lpMem], rdx
0x18004e936  mov     r9, rbx
0x18004e939  mov     r8d, r15d
0x18004e93c  mov     rdx, r14
0x18004e93f  mov     rax, [rax+38h]
0x18004e943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e948  mov     esi, eax
0x18004e94a  mov     [rsp+58h+var_28], eax
0x18004e94e  mov     dword ptr [rsp+58h+var_30], eax
0x18004e952  mov     [rsp+58h+lpMem], r14
0x18004e957  mov     r9, [rdi+968h]
0x18004e95e  lea     r8, aWsCompletedIwi_3; "(%ws) completed IWiaMiniDrv::drvWriteIt"...
0x18004e965  xor     edx, edx
0x18004e967  xor     ecx, ecx
0x18004e969  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18004e96e  mov     rbx, rax
0x18004e971  mov     rdx, rax; char *
0x18004e974  lea     rcx, aUsdwrapperWiaD_1; "USDWrapper::WIA_drvWriteItemProperties"
0x18004e97b  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18004e980  mov     rcx, rbx; this
0x18004e983  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004e988  mov     dword ptr [rsp+58h+var_30], esi
0x18004e98c  mov     [rsp+58h+lpMem], r14
0x18004e991  mov     r9, [rdi+968h]
0x18004e998  lea     r8, aWsCompletedIwi_3; "(%ws) completed IWiaMiniDrv::drvWriteIt"...
0x18004e99f  xor     edx, edx
0x18004e9a1  xor     ecx, ecx
0x18004e9a3  call    WiaTrace_TraceWithSubCompTraceLevel
0x18004e9a8  mov     [rsp+58h+lpMem], rax; lpMem
0x18004e9ad  mov     r9d, 4; int
0x18004e9b3  lea     r8, aUsdwrapperWiaD_1; "USDWrapper::WIA_drvWriteItemProperties"
0x18004e9ba  call    WiaTrace_ProcessTrace_Ex
0x18004e9bf  jmp     loc_18004EA8A
0x18004e9c4  mov     esi, eax
0x18004e9c6  mov     r8d, eax
0x18004e9c9  mov     rdi, [rsp+58h+arg_0]
0x18004e9ce  mov     rdx, [rdi+968h]
0x18004e9d5  lea     rcx, aTheDriverForWs_26; "The driver for (%ws) threw an exception"...
0x18004e9dc  call    WiaTrace_TraceLog
0x18004e9e1  mov     rbx, rax
0x18004e9e4  mov     rdx, rax; char *
0x18004e9e7  lea     rcx, aUsdwrapperWiaD_1; "USDWrapper::WIA_drvWriteItemProperties"
0x18004e9ee  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004e9f3  mov     rcx, rbx; this
0x18004e9f6  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004e9fb  mov     r8d, esi
0x18004e9fe  mov     rdx, [rdi+968h]
0x18004ea05  lea     rcx, aTheDriverForWs_26; "The driver for (%ws) threw an exception"...
0x18004ea0c  call    WiaTrace_Trace
0x18004ea11  mov     [rsp+58h+lpMem], rax; lpMem
0x18004ea16  mov     r9d, 1; int
0x18004ea1c  lea     r8, aUsdwrapperWiaD_1; "USDWrapper::WIA_drvWriteItemProperties"
0x18004ea23  call    WiaTrace_ProcessTrace_Ex
0x18004ea28  mov     esi, 8021000Eh
0x18004ea2d  mov     [rsp+58h+var_28], esi
0x18004ea31  jmp     short loc_18004EA8A
0x18004ea33  mov     rdx, [rdi+968h]
0x18004ea3a  lea     rcx, aWeFailedToMake_11; "We failed to make the call to IWiaMiniD"...
0x18004ea41  call    WiaTrace_TraceLog
0x18004ea46  mov     rbx, rax
0x18004ea49  mov     rdx, rax; char *
0x18004ea4c  lea     rcx, aUsdwrapperWiaD_1; "USDWrapper::WIA_drvWriteItemProperties"
0x18004ea53  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004ea58  mov     rcx, rbx; this
0x18004ea5b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004ea60  mov     rdx, [rdi+968h]
0x18004ea67  lea     rcx, aWeFailedToMake_11; "We failed to make the call to IWiaMiniD"...
0x18004ea6e  call    WiaTrace_Trace
0x18004ea73  mov     [rsp+58h+lpMem], rax; lpMem
0x18004ea78  mov     r9d, 1; int
0x18004ea7e  lea     r8, aUsdwrapperWiaD_1; "USDWrapper::WIA_drvWriteItemProperties"
0x18004ea85  call    WiaTrace_ProcessTrace_Ex
0x18004ea8a  mov     eax, esi
0x18004ea8c  mov     rbx, [rsp+58h+arg_8]
0x18004ea91  mov     rsi, [rsp+58h+arg_10]
0x18004ea96  add     rsp, 40h
0x18004ea9a  pop     r15
0x18004ea9c  pop     r14
0x18004ea9e  pop     rdi
0x18004ea9f  retn
```
