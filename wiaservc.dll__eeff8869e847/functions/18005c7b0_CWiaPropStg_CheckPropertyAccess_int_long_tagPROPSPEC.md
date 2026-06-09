# CWiaPropStg::CheckPropertyAccess(int,long,tagPROPSPEC *)

- ea: `0x18005c7b0`
- end: `0x18005cb14`
- name: `?CheckPropertyAccess@CWiaPropStg@@QEAAJHJPEAUtagPROPSPEC@@@Z`
- size: `868`
- prototype: `__int64 __fastcall(CWiaPropStg *this, int, signed int, struct tagPROPSPEC *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x18001b2c0`
- `0x18005cb1c`
- `0x18005e2e8`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x180018ad8`
- `0x18001c1e4`
- `0x18002de18`
- `0x18002def8`
- `0x18005c7b0`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18005ca54`
- `KERNEL32!LocalFree` at `0x18005ca54`
- `KERNEL32!LocalAlloc` at `0x18005c85b`
- `KERNEL32!LocalAlloc` at `0x18005c85b`

## string_xrefs

- `0x18005c8e4`: `CWiaPropStg::CheckPropertyAccess, no write access on prop ID: %d (%ws)`
- `0x18005c919`: `CWiaPropStg::CheckPropertyAccess, no write access on prop ID: %d (%ws)`
- `0x18005c932`: `CWiaPropStg::CheckPropertyAccess, no write access prop ID: %ls`
- `0x18005c95d`: `CWiaPropStg::CheckPropertyAccess, no write access prop ID: %ls`
- `0x18005c805`: `CWiaPropStg::CheckPropertyAccess`
- `0x18005c831`: `CWiaPropStg::CheckPropertyAccess`
- `0x18005c8f3`: `CWiaPropStg::CheckPropertyAccess`
- `0x18005c941`: `CWiaPropStg::CheckPropertyAccess`
- `0x18005c974`: `CWiaPropStg::CheckPropertyAccess`
- `0x18005c999`: `CWiaPropStg::CheckPropertyAccess`
- `0x18005c9c7`: `CWiaPropStg::CheckPropertyAccess`
- `0x18005ca17`: `CWiaPropStg::CheckPropertyAccess`
- `0x18005ca45`: `CWiaPropStg::CheckPropertyAccess`
- `0x18005ca6d`: `CWiaPropStg::CheckPropertyAccess`
- `0x18005ca9d`: `CWiaPropStg::CheckPropertyAccess`
- `0x18005cac3`: `CWiaPropStg::CheckPropertyAccess`
- `0x18005caf3`: `CWiaPropStg::CheckPropertyAccess`
- `0x18005c7f6`: `CWiaPropStg::CheckPropertyAccess, PROPSPEC array is invalid`
- `0x18005c81c`: `CWiaPropStg::CheckPropertyAccess, PROPSPEC array is invalid`
- `0x18005c9fa`: `CWiaPropStg:CheckPropertyAccess`
- `0x18005ca08`: `CWiaPropStg:CheckPropertyAccess, unable to read access rights for some properties`
- `0x18005ca2e`: `CWiaPropStg:CheckPropertyAccess, unable to read access rights for some properties`
- `0x18005c98a`: `CWiaPropStg::CheckPropertyAccess, bad property specification`
- `0x18005c9b0`: `CWiaPropStg::CheckPropertyAccess, bad property specification`
- `0x18005c9e9`: `access flags`
- `0x18005ca5e`: `CWiaPropStg:CheckPropertyAccess, unable to allocate access propvar, count: %d`
- `0x18005ca86`: `CWiaPropStg:CheckPropertyAccess, unable to allocate access propvar, count: %d`

## pseudocode

```c
__int64 __fastcall CWiaPropStg::CheckPropertyAccess(CWiaPropStg *this, int a2, signed int a3, struct tagPROPSPEC *a4)
{
  char *v9; // rbx
  void *v10; // rdx
  void **lpMem; // rax
  void *v12; // rdx
  __int64 v13; // rcx
  _WORD *v14; // rax
  _WORD *v15; // r12
  int v16; // eax
  unsigned int v17; // edi
  signed int i; // eax
  __int64 v19; // r14
  char *v20; // rbx
  void *v21; // rdx
  unsigned __int16 *NameFromWiaPropId; // rax
  unsigned int v23; // ecx
  void **v24; // rax
  void *v25; // rdx
  __int64 v26; // rcx
  char *v27; // rbx
  void *v28; // rdx
  char *v29; // rbx
  void *v30; // rdx
  void **v31; // rax
  void *v32; // rdx
  __int64 v33; // rcx
  char *v34; // rbx
  void *v35; // rdx
  void **v36; // rax
  void *v37; // rdx
  __int64 v38; // rcx
  char *v39; // rbx
  void *v40; // rdx
  void **v41; // rax
  void *v42; // rdx
  __int64 v43; // rcx
  char *v44; // rbx
  void *v45; // rdx
  void **v46; // rax
  void *v47; // rdx
  __int64 v48; // rcx

  if ( a3 < 0 || (unsigned __int64)a3 > 0x5555555 )
  {
    v44 = (char *)WiaTrace_TraceLog("Invalid cpspec argument (%u) (E_INVALIDARG)");
    WriteDbgTraceErrorWI("CWiaPropStg::CheckPropertyAccess", v44);
    WiaTrcLib::Free((WiaTrcLib *)v44, v45);
    v46 = (void **)WiaTrace_Trace("Invalid cpspec argument (%u) (E_INVALIDARG)", a3);
    WiaTrace_ProcessTrace_Ex(v48, v47, (void *)"CWiaPropStg::CheckPropertyAccess", 1, v46);
    return 2147942487LL;
  }
  if ( !a3 )
    return 0;
  if ( !a4 )
  {
    v9 = (char *)WiaTrace_TraceLog("CWiaPropStg::CheckPropertyAccess, PROPSPEC array is invalid");
    WriteDbgTraceErrorWI("CWiaPropStg::CheckPropertyAccess", v9);
    WiaTrcLib::Free((WiaTrcLib *)v9, v10);
    lpMem = (void **)WiaTrace_Trace("CWiaPropStg::CheckPropertyAccess, PROPSPEC array is invalid");
    WiaTrace_ProcessTrace_Ex(v13, v12, (void *)"CWiaPropStg::CheckPropertyAccess", 1, lpMem);
    return 2147500035LL;
  }
  v14 = LocalAlloc(0x40u, 24LL * a3);
  v15 = v14;
  if ( !v14 )
  {
    v39 = (char *)WiaTrace_TraceLog("CWiaPropStg:CheckPropertyAccess, unable to allocate access propvar, count: %d");
    WriteDbgTraceErrorWI("CWiaPropStg::CheckPropertyAccess", v39);
    WiaTrcLib::Free((WiaTrcLib *)v39, v40);
    v41 = (void **)WiaTrace_Trace("CWiaPropStg:CheckPropertyAccess, unable to allocate access propvar, count: %d", a3);
    WiaTrace_ProcessTrace_Ex(v43, v42, (void *)"CWiaPropStg::CheckPropertyAccess", 1, v41);
    return (unsigned int)-2147024882;
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct tagPROPSPEC *, _WORD *))(**((_QWORD **)this + 2) + 24LL))(
          *((_QWORD *)this + 2),
          (unsigned int)a3,
          a4,
          v14);
  v17 = v16;
  if ( v16 )
  {
    if ( v16 == 1 )
    {
      v17 = 0;
    }
    else
    {
      ReportReadWriteMultipleError(v16, "CWiaPropStg:CheckPropertyAccess", "access flags", 1, a3, a4);
      v34 = (char *)WiaTrace_TraceLog("CWiaPropStg:CheckPropertyAccess, unable to read access rights for some properties");
      WriteDbgTraceErrorWI("CWiaPropStg::CheckPropertyAccess", v34);
      WiaTrcLib::Free((WiaTrcLib *)v34, v35);
      v36 = (void **)WiaTrace_Trace("CWiaPropStg:CheckPropertyAccess, unable to read access rights for some properties");
      WiaTrace_ProcessTrace_Ex(v38, v37, (void *)"CWiaPropStg::CheckPropertyAccess", 1, v36);
    }
    goto LABEL_26;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= a3 )
      goto LABEL_26;
    if ( !v15[12 * i] )
    {
      v17 = 0;
      continue;
    }
    if ( (v15[12 * i + 4] & 2) == 0 )
      break;
  }
  if ( !a2 )
    goto LABEL_21;
  v19 = i;
  if ( a4[i].ulKind == 1 )
  {
    GetNameFromWiaPropId(a4[i].propid);
    v20 = (char *)WiaTrace_TraceLog("CWiaPropStg::CheckPropertyAccess, no write access on prop ID: %d (%ws)");
    WriteDbgTraceErrorWI("CWiaPropStg::CheckPropertyAccess", v20);
    WiaTrcLib::Free((WiaTrcLib *)v20, v21);
    NameFromWiaPropId = GetNameFromWiaPropId(a4[v19].propid);
    v24 = (void **)WiaTrace_Trace(
                     "CWiaPropStg::CheckPropertyAccess, no write access on prop ID: %d (%ws)",
                     v23,
                     NameFromWiaPropId);
    goto LABEL_20;
  }
  if ( !a4[i].ulKind )
  {
    v27 = (char *)WiaTrace_TraceLog("CWiaPropStg::CheckPropertyAccess, no write access prop ID: %ls");
    WriteDbgTraceErrorWI("CWiaPropStg::CheckPropertyAccess", v27);
    WiaTrcLib::Free((WiaTrcLib *)v27, v28);
    v24 = (void **)WiaTrace_Trace("CWiaPropStg::CheckPropertyAccess, no write access prop ID: %ls", a4[v19].lpwstr);
LABEL_20:
    WiaTrace_ProcessTrace_Ex(v26, v25, (void *)"CWiaPropStg::CheckPropertyAccess", 1, v24);
LABEL_21:
    v17 = -2147024891;
    goto LABEL_26;
  }
  v29 = (char *)WiaTrace_TraceLog("CWiaPropStg::CheckPropertyAccess, bad property specification");
  WriteDbgTraceErrorWI("CWiaPropStg::CheckPropertyAccess", v29);
  WiaTrcLib::Free((WiaTrcLib *)v29, v30);
  v31 = (void **)WiaTrace_Trace("CWiaPropStg::CheckPropertyAccess, bad property specification");
  WiaTrace_ProcessTrace_Ex(v33, v32, (void *)"CWiaPropStg::CheckPropertyAccess", 1, v31);
  v17 = -2147024809;
LABEL_26:
  LocalFree(v15);
  return v17;
}

```

## disassembly

```asm
0x18005c7b0  push    rbx
0x18005c7b2  push    rbp
0x18005c7b3  push    rdi
0x18005c7b4  push    r12
0x18005c7b6  push    r13
0x18005c7b8  push    r14
0x18005c7ba  push    r15
0x18005c7bc  sub     rsp, 30h
0x18005c7c0  xor     r14d, r14d
0x18005c7c3  movsxd  rbp, r8d
0x18005c7c6  mov     r15, r9
0x18005c7c9  mov     r13d, edx
0x18005c7cc  mov     rbx, rcx
0x18005c7cf  test    r8d, r8d
0x18005c7d2  js      loc_18005CAB2
0x18005c7d8  cmp     rbp, 5555555h
0x18005c7df  ja      loc_18005CAB2
0x18005c7e5  test    r8d, r8d
0x18005c7e8  jnz     short loc_18005C7F1
0x18005c7ea  xor     eax, eax
0x18005c7ec  jmp     loc_18005CB04
0x18005c7f1  test    r15, r15
0x18005c7f4  jnz     short loc_18005C847
0x18005c7f6  lea     rcx, aCwiapropstgChe_6; "CWiaPropStg::CheckPropertyAccess, PROPS"...
0x18005c7fd  call    WiaTrace_TraceLog
0x18005c802  mov     rdx, rax; char *
0x18005c805  lea     rcx, aCwiapropstgChe_1; "CWiaPropStg::CheckPropertyAccess"
0x18005c80c  mov     rbx, rax
0x18005c80f  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005c814  mov     rcx, rbx; this
0x18005c817  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005c81c  lea     rcx, aCwiapropstgChe_6; "CWiaPropStg::CheckPropertyAccess, PROPS"...
0x18005c823  call    WiaTrace_Trace
0x18005c828  lea     r9d, [r15+1]; int
0x18005c82c  mov     [rsp+68h+lpMem], rax; lpMem
0x18005c831  lea     r8, aCwiapropstgChe_1; "CWiaPropStg::CheckPropertyAccess"
0x18005c838  call    WiaTrace_ProcessTrace_Ex
0x18005c83d  mov     eax, 80004003h
0x18005c842  jmp     loc_18005CB04
0x18005c847  lea     rdx, ds:0[rbp*2]
0x18005c84f  mov     ecx, 40h ; '@'; uFlags
0x18005c854  add     rdx, rbp
0x18005c857  shl     rdx, 3; uBytes
0x18005c85b  call    cs:__imp_LocalAlloc
0x18005c861  mov     r12, rax
0x18005c864  test    rax, rax
0x18005c867  jz      loc_18005CA5C
0x18005c86d  mov     rcx, [rbx+10h]
0x18005c871  mov     r9, r12
0x18005c874  mov     r8, r15
0x18005c877  mov     rdx, [rcx]
0x18005c87a  mov     rax, [rdx+18h]
0x18005c87e  mov     edx, ebp
0x18005c880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c885  mov     edi, eax
0x18005c887  test    eax, eax
0x18005c889  jnz     loc_18005C9DA
0x18005c88f  mov     eax, r14d
0x18005c892  xor     edx, edx
0x18005c894  cmp     eax, ebp
0x18005c896  jge     loc_18005CA51
0x18005c89c  movsxd  r14, eax
0x18005c89f  lea     rcx, [r14+r14*2]
0x18005c8a3  cmp     [r12+rcx*8], dx
0x18005c8a8  jnz     short loc_18005C8AE
0x18005c8aa  mov     edi, edx
0x18005c8ac  jmp     short loc_18005C8BE
0x18005c8ae  test    byte ptr [r12+rcx*8+8], 2
0x18005c8b4  jz      short loc_18005C8C2
0x18005c8b6  test    edi, edi
0x18005c8b8  js      loc_18005CA51
0x18005c8be  inc     eax
0x18005c8c0  jmp     short loc_18005C894
0x18005c8c2  test    r13d, r13d
0x18005c8c5  jz      loc_18005C980
0x18005c8cb  add     r14, r14
0x18005c8ce  cmp     dword ptr [r15+r14*8], 1
0x18005c8d3  jnz     short loc_18005C927
0x18005c8d5  mov     ecx, [r15+r14*8+8]; unsigned int
0x18005c8da  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x18005c8df  mov     edx, ecx
0x18005c8e1  mov     r8, rax
0x18005c8e4  lea     rcx, aCwiapropstgChe_5; "CWiaPropStg::CheckPropertyAccess, no wr"...
0x18005c8eb  call    WiaTrace_TraceLog
0x18005c8f0  mov     rdx, rax; char *
0x18005c8f3  lea     rcx, aCwiapropstgChe_1; "CWiaPropStg::CheckPropertyAccess"
0x18005c8fa  mov     rbx, rax
0x18005c8fd  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005c902  mov     rcx, rbx; this
0x18005c905  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005c90a  mov     ecx, [r15+r14*8+8]; unsigned int
0x18005c90f  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x18005c914  mov     edx, ecx
0x18005c916  mov     r8, rax
0x18005c919  lea     rcx, aCwiapropstgChe_5; "CWiaPropStg::CheckPropertyAccess, no wr"...
0x18005c920  call    WiaTrace_Trace
0x18005c925  jmp     short loc_18005C969
0x18005c927  cmp     [r15+r14*8], edx
0x18005c92b  jnz     short loc_18005C98A
0x18005c92d  mov     rdx, [r15+r14*8+8]
0x18005c932  lea     rcx, aCwiapropstgChe_0; "CWiaPropStg::CheckPropertyAccess, no wr"...
0x18005c939  call    WiaTrace_TraceLog
0x18005c93e  mov     rdx, rax; char *
0x18005c941  lea     rcx, aCwiapropstgChe_1; "CWiaPropStg::CheckPropertyAccess"
0x18005c948  mov     rbx, rax
0x18005c94b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005c950  mov     rcx, rbx; this
0x18005c953  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005c958  mov     rdx, [r15+r14*8+8]
0x18005c95d  lea     rcx, aCwiapropstgChe_0; "CWiaPropStg::CheckPropertyAccess, no wr"...
0x18005c964  call    WiaTrace_Trace
0x18005c969  mov     r9d, 1; int
0x18005c96f  mov     [rsp+68h+lpMem], rax; lpMem
0x18005c974  lea     r8, aCwiapropstgChe_1; "CWiaPropStg::CheckPropertyAccess"
0x18005c97b  call    WiaTrace_ProcessTrace_Ex
0x18005c980  mov     edi, 80070005h
0x18005c985  jmp     loc_18005CA51
0x18005c98a  lea     rcx, aCwiapropstgChe_2; "CWiaPropStg::CheckPropertyAccess, bad p"...
0x18005c991  call    WiaTrace_TraceLog
0x18005c996  mov     rdx, rax; char *
0x18005c999  lea     rcx, aCwiapropstgChe_1; "CWiaPropStg::CheckPropertyAccess"
0x18005c9a0  mov     rbx, rax
0x18005c9a3  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005c9a8  mov     rcx, rbx; this
0x18005c9ab  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005c9b0  lea     rcx, aCwiapropstgChe_2; "CWiaPropStg::CheckPropertyAccess, bad p"...
0x18005c9b7  call    WiaTrace_Trace
0x18005c9bc  mov     r9d, 1; int
0x18005c9c2  mov     [rsp+68h+lpMem], rax; lpMem
0x18005c9c7  lea     r8, aCwiapropstgChe_1; "CWiaPropStg::CheckPropertyAccess"
0x18005c9ce  call    WiaTrace_ProcessTrace_Ex
0x18005c9d3  mov     edi, 80070057h
0x18005c9d8  jmp     short loc_18005CA51
0x18005c9da  cmp     eax, 1
0x18005c9dd  jnz     short loc_18005C9E4
0x18005c9df  mov     edi, r14d
0x18005c9e2  jmp     short loc_18005CA51
0x18005c9e4  mov     [rsp+68h+var_40], r15; struct tagPROPSPEC *
0x18005c9e9  lea     r8, aAccessFlags; "access flags"
0x18005c9f0  mov     r9d, 1; int
0x18005c9f6  mov     dword ptr [rsp+68h+lpMem], ebp; unsigned int
0x18005c9fa  lea     rdx, aCwiapropstgChe_3; "CWiaPropStg:CheckPropertyAccess"
0x18005ca01  mov     ecx, eax; int
0x18005ca03  call    ?ReportReadWriteMultipleError@@YAXJPEAD0HKQEBUtagPROPSPEC@@@Z; ReportReadWriteMultipleError(long,char *,char *,int,ulong,tagPROPSPEC const * const)
0x18005ca08  lea     rcx, aCwiapropstgChe; "CWiaPropStg:CheckPropertyAccess, unable"...
0x18005ca0f  call    WiaTrace_TraceLog
0x18005ca14  mov     rdx, rax; char *
0x18005ca17  lea     rcx, aCwiapropstgChe_1; "CWiaPropStg::CheckPropertyAccess"
0x18005ca1e  mov     rbx, rax
0x18005ca21  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005ca26  mov     rcx, rbx; this
0x18005ca29  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005ca2e  lea     rcx, aCwiapropstgChe; "CWiaPropStg:CheckPropertyAccess, unable"...
0x18005ca35  call    WiaTrace_Trace
0x18005ca3a  mov     r9d, 1; int
0x18005ca40  mov     [rsp+68h+lpMem], rax; lpMem
0x18005ca45  lea     r8, aCwiapropstgChe_1; "CWiaPropStg::CheckPropertyAccess"
0x18005ca4c  call    WiaTrace_ProcessTrace_Ex
0x18005ca51  mov     rcx, r12; hMem
0x18005ca54  call    cs:__imp_LocalFree
0x18005ca5a  jmp     short loc_18005CAAE
0x18005ca5c  mov     edx, ebp
0x18005ca5e  lea     rcx, aCwiapropstgChe_4; "CWiaPropStg:CheckPropertyAccess, unable"...
0x18005ca65  call    WiaTrace_TraceLog
0x18005ca6a  mov     rdx, rax; char *
0x18005ca6d  lea     rcx, aCwiapropstgChe_1; "CWiaPropStg::CheckPropertyAccess"
0x18005ca74  mov     rbx, rax
0x18005ca77  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005ca7c  mov     rcx, rbx; this
0x18005ca7f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005ca84  mov     edx, ebp
0x18005ca86  lea     rcx, aCwiapropstgChe_4; "CWiaPropStg:CheckPropertyAccess, unable"...
0x18005ca8d  call    WiaTrace_Trace
0x18005ca92  mov     r9d, 1; int
0x18005ca98  mov     [rsp+68h+lpMem], rax; lpMem
0x18005ca9d  lea     r8, aCwiapropstgChe_1; "CWiaPropStg::CheckPropertyAccess"
0x18005caa4  call    WiaTrace_ProcessTrace_Ex
0x18005caa9  mov     edi, 8007000Eh
0x18005caae  mov     eax, edi
0x18005cab0  jmp     short loc_18005CB04
0x18005cab2  mov     edx, ebp
0x18005cab4  lea     rcx, aInvalidCpspecA; "Invalid cpspec argument (%u) (E_INVALID"...
0x18005cabb  call    WiaTrace_TraceLog
0x18005cac0  mov     rdx, rax; char *
0x18005cac3  lea     rcx, aCwiapropstgChe_1; "CWiaPropStg::CheckPropertyAccess"
0x18005caca  mov     rbx, rax
0x18005cacd  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005cad2  mov     rcx, rbx; this
0x18005cad5  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005cada  mov     edx, ebp
0x18005cadc  lea     rcx, aInvalidCpspecA; "Invalid cpspec argument (%u) (E_INVALID"...
0x18005cae3  call    WiaTrace_Trace
0x18005cae8  mov     r9d, 1; int
0x18005caee  mov     [rsp+68h+lpMem], rax; lpMem
0x18005caf3  lea     r8, aCwiapropstgChe_1; "CWiaPropStg::CheckPropertyAccess"
0x18005cafa  call    WiaTrace_ProcessTrace_Ex
0x18005caff  mov     eax, 80070057h
0x18005cb04  add     rsp, 30h
0x18005cb08  pop     r15
0x18005cb0a  pop     r14
0x18005cb0c  pop     r13
0x18005cb0e  pop     r12
0x18005cb10  pop     rdi
0x18005cb11  pop     rbp
0x18005cb12  pop     rbx
0x18005cb13  retn
```
