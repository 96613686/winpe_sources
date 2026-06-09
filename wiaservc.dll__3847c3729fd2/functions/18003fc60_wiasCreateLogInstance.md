# wiasCreateLogInstance

- ea: `0x18003fc60`
- end: `0x18003fd6e`
- name: `wiasCreateLogInstance`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18002de18`
- `0x18002def8`
- `0x18003fc60`
- `0x180078010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18003fced`
- `ole32!CoCreateInstance` at `0x18003fced`

## string_xrefs

- `0x18003fc7a`: `wiasCreateLogInstance, Invalid pointer argument`
- `0x18003fca0`: `wiasCreateLogInstance, Invalid pointer argument`
- `0x18003fc89`: `wiasCreateLogInstance`
- `0x18003fcb7`: `wiasCreateLogInstance`
- `0x18003fd20`: `wiasCreateLogInstance`
- `0x18003fd50`: `wiasCreateLogInstance`
- `0x18003fd11`: `wiasCreateLogInstance, Failed to CoCreateInstance on Logging object (0x%X)`
- `0x18003fd39`: `wiasCreateLogInstance, Failed to CoCreateInstance on Logging object (0x%X)`

## pseudocode

```c
__int64 __fastcall wiasCreateLogInstance(__int64 a1, LPVOID *ppv)
{
  char *v4; // rbx
  void *v5; // rdx
  void **v6; // rax
  void *v7; // rdx
  __int64 v8; // rcx
  HRESULT Instance; // edi
  char *v11; // rbx
  void *v12; // rdx
  void **v13; // rax
  void *v14; // rdx
  __int64 v15; // rcx

  if ( ppv )
  {
    *ppv = 0;
    Instance = CoCreateInstance(&CLSID_WiaLog, 0, 1u, &IID_IWiaLogEx, ppv);
    if ( Instance < 0 )
    {
      v11 = (char *)WiaTrace_TraceLog("wiasCreateLogInstance, Failed to CoCreateInstance on Logging object (0x%X)");
      WriteDbgTraceErrorWI("wiasCreateLogInstance", v11);
      WiaTrcLib::Free((WiaTrcLib *)v11, v12);
      v13 = (void **)WiaTrace_Trace(
                       "wiasCreateLogInstance, Failed to CoCreateInstance on Logging object (0x%X)",
                       Instance);
      WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"wiasCreateLogInstance", 1, v13);
    }
    else
    {
      return (unsigned int)(*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)*ppv + 24LL))(*ppv, a1);
    }
    return (unsigned int)Instance;
  }
  else
  {
    v4 = (char *)WiaTrace_TraceLog("wiasCreateLogInstance, Invalid pointer argument");
    WriteDbgTraceErrorWI("wiasCreateLogInstance", v4);
    WiaTrcLib::Free((WiaTrcLib *)v4, v5);
    v6 = (void **)WiaTrace_Trace("wiasCreateLogInstance, Invalid pointer argument");
    WiaTrace_ProcessTrace_Ex(v8, v7, (void *)"wiasCreateLogInstance", 1, v6);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18003fc60  mov     [rsp+arg_0], rbx
0x18003fc65  mov     [rsp+arg_8], rsi
0x18003fc6a  push    rdi
0x18003fc6b  sub     rsp, 30h
0x18003fc6f  mov     rbx, rdx
0x18003fc72  mov     rsi, rcx
0x18003fc75  test    rdx, rdx
0x18003fc78  jnz     short loc_18003FCCD
0x18003fc7a  lea     rcx, aWiascreatelogi_0; "wiasCreateLogInstance, Invalid pointer "...
0x18003fc81  call    WiaTrace_TraceLog
0x18003fc86  mov     rdx, rax; char *
0x18003fc89  lea     rcx, aWiascreatelogi_1; "wiasCreateLogInstance"
0x18003fc90  mov     rbx, rax
0x18003fc93  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003fc98  mov     rcx, rbx; this
0x18003fc9b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003fca0  lea     rcx, aWiascreatelogi_0; "wiasCreateLogInstance, Invalid pointer "...
0x18003fca7  call    WiaTrace_Trace
0x18003fcac  mov     r9d, 1; int
0x18003fcb2  mov     [rsp+38h+ppv], rax; lpMem
0x18003fcb7  lea     r8, aWiascreatelogi_1; "wiasCreateLogInstance"
0x18003fcbe  call    WiaTrace_ProcessTrace_Ex
0x18003fcc3  mov     eax, 80004003h
0x18003fcc8  jmp     loc_18003FD5E
0x18003fccd  mov     qword ptr [rdx], 0
0x18003fcd4  lea     r9, IID_IWiaLogEx; riid
0x18003fcdb  xor     edx, edx; pUnkOuter
0x18003fcdd  mov     [rsp+38h+ppv], rbx; ppv
0x18003fce2  lea     rcx, CLSID_WiaLog; rclsid
0x18003fce9  lea     r8d, [rdx+1]; dwClsContext
0x18003fced  call    cs:__imp_CoCreateInstance
0x18003fcf3  mov     edi, eax
0x18003fcf5  test    eax, eax
0x18003fcf7  js      short loc_18003FD0F
0x18003fcf9  mov     rcx, [rbx]
0x18003fcfc  mov     rdx, rsi
0x18003fcff  mov     rax, [rcx]
0x18003fd02  mov     rax, [rax+18h]
0x18003fd06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd0b  mov     edi, eax
0x18003fd0d  jmp     short loc_18003FD5C
0x18003fd0f  mov     edx, edi
0x18003fd11  lea     rcx, aWiascreatelogi_2; "wiasCreateLogInstance, Failed to CoCrea"...
0x18003fd18  call    WiaTrace_TraceLog
0x18003fd1d  mov     rdx, rax; char *
0x18003fd20  lea     rcx, aWiascreatelogi_1; "wiasCreateLogInstance"
0x18003fd27  mov     rbx, rax
0x18003fd2a  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003fd2f  mov     rcx, rbx; this
0x18003fd32  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003fd37  mov     edx, edi
0x18003fd39  lea     rcx, aWiascreatelogi_2; "wiasCreateLogInstance, Failed to CoCrea"...
0x18003fd40  call    WiaTrace_Trace
0x18003fd45  mov     r9d, 1; int
0x18003fd4b  mov     [rsp+38h+ppv], rax; lpMem
0x18003fd50  lea     r8, aWiascreatelogi_1; "wiasCreateLogInstance"
0x18003fd57  call    WiaTrace_ProcessTrace_Ex
0x18003fd5c  mov     eax, edi
0x18003fd5e  mov     rbx, [rsp+38h+arg_0]
0x18003fd63  mov     rsi, [rsp+38h+arg_8]
0x18003fd68  add     rsp, 30h
0x18003fd6c  pop     rdi
0x18003fd6d  retn
```
