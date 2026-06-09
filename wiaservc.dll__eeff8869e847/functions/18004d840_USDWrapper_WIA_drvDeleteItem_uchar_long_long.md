# USDWrapper::WIA_drvDeleteItem(uchar *,long,long *)

- ea: `0x18004d840`
- end: `0x18004d9f3`
- name: `?WIA_drvDeleteItem@USDWrapper@@UEAAJPEAEJPEAJ@Z`
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
- `0x18004d840`
- `0x180078010`

## string_xrefs

- `0x18004d8c7`: `USDWrapper::WIA_drvDeleteItem`
- `0x18004d906`: `USDWrapper::WIA_drvDeleteItem`
- `0x18004d93a`: `USDWrapper::WIA_drvDeleteItem`
- `0x18004d96f`: `USDWrapper::WIA_drvDeleteItem`
- `0x18004d99f`: `USDWrapper::WIA_drvDeleteItem`
- `0x18004d9d1`: `USDWrapper::WIA_drvDeleteItem`
- `0x18004d8b1`: `(%ws) completed IWiaMiniDrv::drvDeleteItem on item (%p) returning hr 0x%08.8X`
- `0x18004d8eb`: `(%ws) completed IWiaMiniDrv::drvDeleteItem on item (%p) returning hr 0x%08.8X`
- `0x18004d98d`: `We failed to make the call to IWiaMiniDrv::drvDeleteItem for (%ws) because the driver could not be loaded`
- `0x18004d9ba`: `We failed to make the call to IWiaMiniDrv::drvDeleteItem for (%ws) because the driver could not be loaded`
- `0x18004d928`: `The driver for (%ws) threw an exception (0x%08X) when the WIA service called IWiaMiniDrv::drvDeleteItem`
- `0x18004d958`: `The driver for (%ws) threw an exception (0x%08X) when the WIA service called IWiaMiniDrv::drvDeleteItem`

## pseudocode

```c
__int64 __fastcall USDWrapper::WIA_drvDeleteItem(USDWrapper *this, unsigned __int8 *a2, unsigned int a3, int *a4)
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
    v14 = (char *)WiaTrace_TraceLog("We failed to make the call to IWiaMiniDrv::drvDeleteItem for (%ws) because the drive"
                                    "r could not be loaded");
    WriteDbgTraceErrorWI("USDWrapper::WIA_drvDeleteItem", v14);
    WiaTrcLib::Free((WiaTrcLib *)v14, v15);
    v16 = (void **)WiaTrace_Trace(
                     "We failed to make the call to IWiaMiniDrv::drvDeleteItem for (%ws) because the driver could not be loaded",
                     *((_QWORD *)this + 301));
    WiaTrace_ProcessTrace_Ex(v18, v17, (void *)"USDWrapper::WIA_drvDeleteItem", 1, v16);
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, int *))(**((_QWORD **)this + 457) + 120LL))(
           *((_QWORD *)this + 457),
           a2,
           a3,
           a4);
    v22 = v8;
    v20 = v8;
    v9 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                   0,
                   0,
                   "(%ws) completed IWiaMiniDrv::drvDeleteItem on item (%p) returning hr 0x%08.8X",
                   *((_QWORD *)this + 301),
                   a2,
                   v20,
                   v22);
    WriteDbgTraceInfoWI("USDWrapper::WIA_drvDeleteItem", v9);
    WiaTrcLib::Free((WiaTrcLib *)v9, v10);
    LODWORD(v21) = v8;
    lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       0,
                       0,
                       "(%ws) completed IWiaMiniDrv::drvDeleteItem on item (%p) returning hr 0x%08.8X",
                       *((_QWORD *)this + 301),
                       a2,
                       v21);
    WiaTrace_ProcessTrace_Ex(v13, v12, (void *)"USDWrapper::WIA_drvDeleteItem", 4, lpMem);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004d840  mov     [rsp+arg_8], rbx
0x18004d845  mov     [rsp+arg_10], rsi
0x18004d84a  mov     [rsp+arg_0], rcx
0x18004d84f  push    rdi
0x18004d850  push    r14
0x18004d852  push    r15
0x18004d854  sub     rsp, 40h
0x18004d858  mov     rbx, r9
0x18004d85b  mov     r15d, r8d
0x18004d85e  mov     r14, rdx
0x18004d861  mov     rdi, rcx
0x18004d864  mov     rax, [rcx]
0x18004d867  mov     edx, 2
0x18004d86c  mov     rax, [rax+68h]
0x18004d870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d875  mov     esi, eax
0x18004d877  test    eax, eax
0x18004d879  js      loc_18004D986
0x18004d87f  mov     rcx, [rdi+0E48h]
0x18004d886  mov     rax, [rcx]
0x18004d889  mov     r9, rbx
0x18004d88c  mov     r8d, r15d
0x18004d88f  mov     rdx, r14
0x18004d892  mov     rax, [rax+78h]
0x18004d896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d89b  mov     esi, eax
0x18004d89d  mov     [rsp+58h+var_28], eax
0x18004d8a1  mov     dword ptr [rsp+58h+var_30], eax
0x18004d8a5  mov     [rsp+58h+lpMem], r14
0x18004d8aa  mov     r9, [rdi+968h]
0x18004d8b1  lea     r8, aWsCompletedIwi_10; "(%ws) completed IWiaMiniDrv::drvDeleteI"...
0x18004d8b8  xor     edx, edx
0x18004d8ba  xor     ecx, ecx
0x18004d8bc  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18004d8c1  mov     rbx, rax
0x18004d8c4  mov     rdx, rax; char *
0x18004d8c7  lea     rcx, aUsdwrapperWiaD_15; "USDWrapper::WIA_drvDeleteItem"
0x18004d8ce  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18004d8d3  mov     rcx, rbx; this
0x18004d8d6  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004d8db  mov     dword ptr [rsp+58h+var_30], esi
0x18004d8df  mov     [rsp+58h+lpMem], r14
0x18004d8e4  mov     r9, [rdi+968h]
0x18004d8eb  lea     r8, aWsCompletedIwi_10; "(%ws) completed IWiaMiniDrv::drvDeleteI"...
0x18004d8f2  xor     edx, edx
0x18004d8f4  xor     ecx, ecx
0x18004d8f6  call    WiaTrace_TraceWithSubCompTraceLevel
0x18004d8fb  mov     [rsp+58h+lpMem], rax; lpMem
0x18004d900  mov     r9d, 4; int
0x18004d906  lea     r8, aUsdwrapperWiaD_15; "USDWrapper::WIA_drvDeleteItem"
0x18004d90d  call    WiaTrace_ProcessTrace_Ex
0x18004d912  jmp     loc_18004D9DD
0x18004d917  mov     esi, eax
0x18004d919  mov     r8d, eax
0x18004d91c  mov     rdi, [rsp+58h+arg_0]
0x18004d921  mov     rdx, [rdi+968h]
0x18004d928  lea     rcx, aTheDriverForWs_24; "The driver for (%ws) threw an exception"...
0x18004d92f  call    WiaTrace_TraceLog
0x18004d934  mov     rbx, rax
0x18004d937  mov     rdx, rax; char *
0x18004d93a  lea     rcx, aUsdwrapperWiaD_15; "USDWrapper::WIA_drvDeleteItem"
0x18004d941  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004d946  mov     rcx, rbx; this
0x18004d949  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004d94e  mov     r8d, esi
0x18004d951  mov     rdx, [rdi+968h]
0x18004d958  lea     rcx, aTheDriverForWs_24; "The driver for (%ws) threw an exception"...
0x18004d95f  call    WiaTrace_Trace
0x18004d964  mov     [rsp+58h+lpMem], rax; lpMem
0x18004d969  mov     r9d, 1; int
0x18004d96f  lea     r8, aUsdwrapperWiaD_15; "USDWrapper::WIA_drvDeleteItem"
0x18004d976  call    WiaTrace_ProcessTrace_Ex
0x18004d97b  mov     esi, 8021000Eh
0x18004d980  mov     [rsp+58h+var_28], esi
0x18004d984  jmp     short loc_18004D9DD
0x18004d986  mov     rdx, [rdi+968h]
0x18004d98d  lea     rcx, aWeFailedToMake_5; "We failed to make the call to IWiaMiniD"...
0x18004d994  call    WiaTrace_TraceLog
0x18004d999  mov     rbx, rax
0x18004d99c  mov     rdx, rax; char *
0x18004d99f  lea     rcx, aUsdwrapperWiaD_15; "USDWrapper::WIA_drvDeleteItem"
0x18004d9a6  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004d9ab  mov     rcx, rbx; this
0x18004d9ae  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004d9b3  mov     rdx, [rdi+968h]
0x18004d9ba  lea     rcx, aWeFailedToMake_5; "We failed to make the call to IWiaMiniD"...
0x18004d9c1  call    WiaTrace_Trace
0x18004d9c6  mov     [rsp+58h+lpMem], rax; lpMem
0x18004d9cb  mov     r9d, 1; int
0x18004d9d1  lea     r8, aUsdwrapperWiaD_15; "USDWrapper::WIA_drvDeleteItem"
0x18004d9d8  call    WiaTrace_ProcessTrace_Ex
0x18004d9dd  mov     eax, esi
0x18004d9df  mov     rbx, [rsp+58h+arg_8]
0x18004d9e4  mov     rsi, [rsp+58h+arg_10]
0x18004d9e9  add     rsp, 40h
0x18004d9ed  pop     r15
0x18004d9ef  pop     r14
0x18004d9f1  pop     rdi
0x18004d9f2  retn
```
