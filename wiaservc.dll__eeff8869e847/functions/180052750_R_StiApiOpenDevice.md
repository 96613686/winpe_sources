# R_StiApiOpenDevice

- ea: `0x180052750`
- end: `0x180052a07`
- name: `R_StiApiOpenDevice`
- size: `695`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180050d14`
- `0x180051294`
- `0x180052750`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180052994`
- `KERNEL32!GetLastError` at `0x180052994`

## string_xrefs

- `0x180052782`: `R_StiApiOpenDevice`
- `0x18005276f`: `STI: Request to open STI device (%ws)`
- `0x1800527a2`: `STI: Request to open STI device (%ws)`
- `0x180052819`: `STI:   Access     : 0x%08X`
- `0x180052843`: `STI:   Access     : 0x%08X`
- `0x1800528c5`: `STI: Could not open device connection, Access is denied`
- `0x1800528e7`: `STI: Could not open device connection, Access is denied`
- `0x18005286b`: `STI:   ProcessId  : 0x%08X`
- `0x180052898`: `STI:   ProcessId  : 0x%08X`
- `0x18005299a`: `STI:     Could not open device connection, returning 0x%08X`
- `0x1800529c9`: `STI:     Could not open device connection, returning 0x%08X`
- `0x180052941`: `STI:   Device connection opened successfully`
- `0x180052968`: `STI:   Device connection opened successfully`

## pseudocode

```c
__int64 __fastcall R_StiApiOpenDevice(
        __int64 a1,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        unsigned int a5,
        void **a6)
{
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
  char *v19; // rbx
  void *v20; // rdx
  void **v21; // rax
  void *v22; // rdx
  __int64 v23; // rcx
  char *v24; // rbx
  void *v25; // rdx
  void **v26; // rax
  void *v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rdx
  void *v30; // rcx
  struct _GENERIC_MAPPING *v31; // r8
  unsigned int v32; // r14d
  char *v33; // rbx
  void *v34; // rdx
  void **v35; // rax
  void *v36; // rdx
  __int64 v37; // rcx
  char *v39; // rbx
  void *v40; // rdx
  void **v41; // rax
  void *v42; // rdx
  __int64 v43; // rcx
  DWORD LastError; // edi
  char *v45; // rbx
  void *v46; // rdx
  void **v47; // rax
  void *v48; // rdx
  __int64 v49; // rcx

  v9 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(8, 0, "STI: Request to open STI device (%ws)", a2);
  WriteDbgTraceInfoWI("R_StiApiOpenDevice", v9);
  WiaTrcLib::Free((WiaTrcLib *)v9, v10);
  lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(8, 0, "STI: Request to open STI device (%ws)", a2);
  WiaTrace_ProcessTrace_Ex(v13, v12, (void *)"R_StiApiOpenDevice", 4, lpMem);
  v14 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(8, 0, "STI:   Mode       : 0x%08X", a3);
  WriteDbgTraceInfoWI("R_StiApiOpenDevice", v14);
  WiaTrcLib::Free((WiaTrcLib *)v14, v15);
  v16 = (void **)WiaTrace_TraceWithSubCompTraceLevel(8, 0, "STI:   Mode       : 0x%08X", a3);
  WiaTrace_ProcessTrace_Ex(v18, v17, (void *)"R_StiApiOpenDevice", 4, v16);
  v19 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(8, 0, "STI:   Access     : 0x%08X", a4);
  WriteDbgTraceInfoWI("R_StiApiOpenDevice", v19);
  WiaTrcLib::Free((WiaTrcLib *)v19, v20);
  v21 = (void **)WiaTrace_TraceWithSubCompTraceLevel(8, 0, "STI:   Access     : 0x%08X", a4);
  WiaTrace_ProcessTrace_Ex(v23, v22, (void *)"R_StiApiOpenDevice", 4, v21);
  v24 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(8, 0, "STI:   ProcessId  : 0x%08X", a5);
  WriteDbgTraceInfoWI("R_StiApiOpenDevice", v24);
  WiaTrcLib::Free((WiaTrcLib *)v24, v25);
  v26 = (void **)WiaTrace_TraceWithSubCompTraceLevel(8, 0, "STI:   ProcessId  : 0x%08X", a5);
  WiaTrace_ProcessTrace_Ex(v28, v27, (void *)"R_StiApiOpenDevice", 4, v26);
  v32 = StiAccessCheck(v30, v29, v31);
  if ( v32 )
  {
    v33 = (char *)WiaTrace_TraceLog("STI: Could not open device connection, Access is denied");
    WriteDbgTraceErrorWI("R_StiApiOpenDevice", v33);
    WiaTrcLib::Free((WiaTrcLib *)v33, v34);
    v35 = (void **)WiaTrace_Trace("STI: Could not open device connection, Access is denied");
    WiaTrace_ProcessTrace_Ex(v37, v36, (void *)"R_StiApiOpenDevice", 1, v35);
    return v32;
  }
  else if ( a6 && a2 )
  {
    if ( (unsigned int)CreateDeviceConnection(a2, a3, a5, a6) && *a6 )
    {
      v39 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(8, 0, "STI:   Device connection opened successfully");
      WriteDbgTraceInfoWI("R_StiApiOpenDevice", v39);
      WiaTrcLib::Free((WiaTrcLib *)v39, v40);
      v41 = (void **)WiaTrace_TraceWithSubCompTraceLevel(8, 0, "STI:   Device connection opened successfully");
      WiaTrace_ProcessTrace_Ex(v43, v42, (void *)"R_StiApiOpenDevice", 4, v41);
      return 0;
    }
    else
    {
      *a6 = (void *)-1LL;
      LastError = GetLastError();
      v45 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "STI:     Could not open device connection, returning 0x%08X",
                      LastError);
      WriteDbgTraceWarningWI("R_StiApiOpenDevice", v45);
      WiaTrcLib::Free((WiaTrcLib *)v45, v46);
      v47 = (void **)WiaTrace_TraceWithSubComp(
                       1,
                       "STI:     Could not open device connection, returning 0x%08X",
                       LastError);
      WiaTrace_ProcessTrace_Ex(v49, v48, (void *)"R_StiApiOpenDevice", 2, v47);
      return LastError;
    }
  }
  else
  {
    return 87;
  }
}

```

## disassembly

```asm
0x180052750  push    rbx
0x180052752  push    rbp
0x180052753  push    rsi
0x180052754  push    rdi
0x180052755  push    r12
0x180052757  push    r13
0x180052759  push    r14
0x18005275b  push    r15
0x18005275d  sub     rsp, 38h
0x180052761  mov     edi, r9d
0x180052764  mov     rsi, rdx
0x180052767  mov     r9, rdx
0x18005276a  mov     ebp, r8d
0x18005276d  xor     edx, edx
0x18005276f  lea     r8, aStiRequestToOp; "STI: Request to open STI device (%ws)"
0x180052776  lea     r12d, [rdx+8]
0x18005277a  mov     ecx, r12d
0x18005277d  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180052782  lea     r15, aRStiapiopendev; "R_StiApiOpenDevice"
0x180052789  mov     rdx, rax; char *
0x18005278c  mov     rcx, r15; char *
0x18005278f  mov     rbx, rax
0x180052792  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180052797  mov     rcx, rbx; this
0x18005279a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005279f  mov     r9, rsi
0x1800527a2  lea     r8, aStiRequestToOp; "STI: Request to open STI device (%ws)"
0x1800527a9  xor     edx, edx
0x1800527ab  mov     ecx, r12d
0x1800527ae  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800527b3  lea     r13d, [r12-4]
0x1800527b8  mov     [rsp+78h+lpMem], rax; lpMem
0x1800527bd  mov     r9d, r13d; int
0x1800527c0  mov     r8, r15; int
0x1800527c3  call    WiaTrace_ProcessTrace_Ex
0x1800527c8  mov     r9d, ebp
0x1800527cb  lea     r8, aStiMode0x08x; "STI:   Mode       : 0x%08X"
0x1800527d2  xor     edx, edx
0x1800527d4  mov     ecx, r12d
0x1800527d7  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800527dc  mov     rdx, rax; char *
0x1800527df  mov     rcx, r15; char *
0x1800527e2  mov     rbx, rax
0x1800527e5  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800527ea  mov     rcx, rbx; this
0x1800527ed  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800527f2  mov     r9d, ebp
0x1800527f5  lea     r8, aStiMode0x08x; "STI:   Mode       : 0x%08X"
0x1800527fc  xor     edx, edx
0x1800527fe  mov     ecx, r12d
0x180052801  call    WiaTrace_TraceWithSubCompTraceLevel
0x180052806  mov     r9d, r13d; int
0x180052809  mov     [rsp+78h+lpMem], rax; lpMem
0x18005280e  mov     r8, r15; int
0x180052811  call    WiaTrace_ProcessTrace_Ex
0x180052816  mov     r9d, edi
0x180052819  lea     r8, aStiAccess0x08x; "STI:   Access     : 0x%08X"
0x180052820  xor     edx, edx
0x180052822  mov     ecx, r12d
0x180052825  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18005282a  mov     rdx, rax; char *
0x18005282d  mov     rcx, r15; char *
0x180052830  mov     rbx, rax
0x180052833  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180052838  mov     rcx, rbx; this
0x18005283b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180052840  mov     r9d, edi
0x180052843  lea     r8, aStiAccess0x08x; "STI:   Access     : 0x%08X"
0x18005284a  xor     edx, edx
0x18005284c  mov     ecx, r12d
0x18005284f  call    WiaTrace_TraceWithSubCompTraceLevel
0x180052854  mov     r9d, r13d; int
0x180052857  mov     [rsp+78h+lpMem], rax; lpMem
0x18005285c  mov     r8, r15; int
0x18005285f  call    WiaTrace_ProcessTrace_Ex
0x180052864  mov     edi, [rsp+78h+arg_20]
0x18005286b  lea     r8, aStiProcessid0x; "STI:   ProcessId  : 0x%08X"
0x180052872  mov     r9d, edi
0x180052875  xor     edx, edx
0x180052877  mov     ecx, r12d
0x18005287a  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18005287f  mov     rdx, rax; char *
0x180052882  mov     rcx, r15; char *
0x180052885  mov     rbx, rax
0x180052888  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18005288d  mov     rcx, rbx; this
0x180052890  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180052895  mov     r9d, edi
0x180052898  lea     r8, aStiProcessid0x; "STI:   ProcessId  : 0x%08X"
0x18005289f  xor     edx, edx
0x1800528a1  mov     ecx, r12d
0x1800528a4  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800528a9  mov     r9d, r13d; int
0x1800528ac  mov     [rsp+78h+lpMem], rax; lpMem
0x1800528b1  mov     r8, r15; int
0x1800528b4  call    WiaTrace_ProcessTrace_Ex
0x1800528b9  call    ?StiAccessCheck@@YAKPEAXKPEAU_GENERIC_MAPPING@@@Z; StiAccessCheck(void *,ulong,_GENERIC_MAPPING *)
0x1800528be  mov     r14d, eax
0x1800528c1  test    eax, eax
0x1800528c3  jz      short loc_18005290D
0x1800528c5  lea     rcx, aStiCouldNotOpe_0; "STI: Could not open device connection, "...
0x1800528cc  call    WiaTrace_TraceLog
0x1800528d1  mov     rdx, rax; char *
0x1800528d4  mov     rcx, r15; char *
0x1800528d7  mov     rbx, rax
0x1800528da  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800528df  mov     rcx, rbx; this
0x1800528e2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800528e7  lea     rcx, aStiCouldNotOpe_0; "STI: Could not open device connection, "...
0x1800528ee  call    WiaTrace_Trace
0x1800528f3  lea     r9d, [r12-7]; int
0x1800528f8  mov     [rsp+78h+lpMem], rax; lpMem
0x1800528fd  mov     r8, r15; int
0x180052900  call    WiaTrace_ProcessTrace_Ex
0x180052905  mov     eax, r14d
0x180052908  jmp     loc_1800529F6
0x18005290d  mov     rbx, [rsp+78h+arg_28]
0x180052915  test    rbx, rbx
0x180052918  jz      loc_1800529F1
0x18005291e  test    rsi, rsi
0x180052921  jz      loc_1800529F1
0x180052927  mov     r9, rbx; void **
0x18005292a  mov     r8d, edi; unsigned int
0x18005292d  mov     edx, ebp; unsigned int
0x18005292f  mov     rcx, rsi; unsigned __int16 *
0x180052932  call    ?CreateDeviceConnection@@YAHPEBGKKPEAPEAX@Z; CreateDeviceConnection(ushort const *,ulong,ulong,void * *)
0x180052937  test    eax, eax
0x180052939  jz      short loc_18005298D
0x18005293b  cmp     qword ptr [rbx], 0
0x18005293f  jz      short loc_18005298D
0x180052941  lea     r8, aStiDeviceConne; "STI:   Device connection opened success"...
0x180052948  xor     edx, edx
0x18005294a  mov     ecx, r12d
0x18005294d  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180052952  mov     rdx, rax; char *
0x180052955  mov     rcx, r15; char *
0x180052958  mov     rbx, rax
0x18005295b  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180052960  mov     rcx, rbx; this
0x180052963  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180052968  lea     r8, aStiDeviceConne; "STI:   Device connection opened success"...
0x18005296f  xor     edx, edx
0x180052971  mov     ecx, r12d
0x180052974  call    WiaTrace_TraceWithSubCompTraceLevel
0x180052979  mov     r9d, r13d; int
0x18005297c  mov     [rsp+78h+lpMem], rax; lpMem
0x180052981  mov     r8, r15; int
0x180052984  call    WiaTrace_ProcessTrace_Ex
0x180052989  xor     eax, eax
0x18005298b  jmp     short loc_1800529F6
0x18005298d  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180052994  call    cs:__imp_GetLastError
0x18005299a  lea     rdx, aStiCouldNotOpe; "STI:     Could not open device connecti"...
0x1800529a1  mov     ecx, 1
0x1800529a6  mov     r8d, eax
0x1800529a9  mov     edi, eax
0x1800529ab  call    WiaTrace_TraceLogWithSubComp
0x1800529b0  mov     rdx, rax; char *
0x1800529b3  mov     rcx, r15; char *
0x1800529b6  mov     rbx, rax
0x1800529b9  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x1800529be  mov     rcx, rbx; this
0x1800529c1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800529c6  mov     r8d, edi
0x1800529c9  lea     rdx, aStiCouldNotOpe; "STI:     Could not open device connecti"...
0x1800529d0  mov     ecx, 1
0x1800529d5  call    WiaTrace_TraceWithSubComp
0x1800529da  mov     r9d, 2; int
0x1800529e0  mov     [rsp+78h+lpMem], rax; lpMem
0x1800529e5  mov     r8, r15; int
0x1800529e8  call    WiaTrace_ProcessTrace_Ex
0x1800529ed  mov     eax, edi
0x1800529ef  jmp     short loc_1800529F6
0x1800529f1  mov     eax, 57h ; 'W'
0x1800529f6  add     rsp, 38h
0x1800529fa  pop     r15
0x1800529fc  pop     r14
0x1800529fe  pop     r13
0x180052a00  pop     r12
0x180052a02  pop     rdi
0x180052a03  pop     rsi
0x180052a04  pop     rbp
0x180052a05  pop     rbx
0x180052a06  retn
```
