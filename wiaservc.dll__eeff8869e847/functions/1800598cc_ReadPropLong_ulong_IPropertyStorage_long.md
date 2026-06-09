# ReadPropLong(ulong,IPropertyStorage *,long *)

- ea: `0x1800598cc`
- end: `0x1800599bc`
- name: `?ReadPropLong@@YAJKPEAUIPropertyStorage@@PEAJ@Z`
- size: `240`
- prototype: `__int64 __fastcall(unsigned int, struct IPropertyStorage *, int *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180059b20`
- `0x18006d5f0`
- `0x18006e160`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002de18`
- `0x18002def8`
- `0x1800598cc`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantClear` at `0x18005994e`
- `ole32!PropVariantClear` at `0x18005994e`

## string_xrefs

- `0x180059958`: `ReadMultiple of propid: %d, failed`
- `0x180059980`: `ReadMultiple of propid: %d, failed`
- `0x1800598ed`: `ReadPropLong`
- `0x180059967`: `ReadPropLong`
- `0x180059997`: `ReadPropLong`
- `0x1800598de`: `::ReadPropLong`

## pseudocode

```c
__int64 __fastcall ReadPropLong(int a1, struct IPropertyStorage *a2, int *a3)
{
  char ***v6; // rax
  char *v7; // rdx
  __int64 v8; // r8
  struct IPropertyStorageVtbl *lpVtbl; // rax
  unsigned int v10; // edi
  char *v11; // rbx
  void *v12; // rdx
  void **v13; // rax
  void *v14; // rdx
  __int64 v15; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-B8h]
  _DWORD v18[4]; // [rsp+30h] [rbp-A8h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-98h] BYREF
  __int64 v20; // [rsp+50h] [rbp-88h]
  _BYTE v21[120]; // [rsp+60h] [rbp-78h] BYREF

  v6 = (char ***)WiaTrace_Trace("::ReadPropLong");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v21, v7, v8, (char **)"ReadPropLong", lpMem, v6);
  v18[0] = 1;
  v20 = 0;
  lpVtbl = a2->lpVtbl;
  v18[2] = a1;
  *(_OWORD *)pvar = 0;
  v10 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, _DWORD *, PROPVARIANT *))lpVtbl->ReadMultiple)(
          a2,
          1,
          v18,
          pvar);
  if ( v10 )
  {
    v11 = (char *)WiaTrace_TraceLog("ReadMultiple of propid: %d, failed");
    WriteDbgTraceErrorWI("ReadPropLong", v11);
    WiaTrcLib::Free((WiaTrcLib *)v11, v12);
    v13 = (void **)WiaTrace_Trace("ReadMultiple of propid: %d, failed", a1);
    WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"ReadPropLong", 1, v13);
  }
  else
  {
    *a3 = (int)pvar[1];
    PropVariantClear(pvar);
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v21);
  return v10;
}

```

## disassembly

```asm
0x1800598cc  push    rbx
0x1800598ce  push    rsi
0x1800598cf  push    rdi
0x1800598d0  push    r14
0x1800598d2  sub     rsp, 0B8h
0x1800598d9  mov     esi, ecx
0x1800598db  mov     r14, r8
0x1800598de  lea     rcx, aReadproplong_0; "::ReadPropLong"
0x1800598e5  mov     rbx, rdx
0x1800598e8  call    WiaTrace_Trace
0x1800598ed  lea     r9, aReadproplong; "ReadPropLong"
0x1800598f4  mov     [rsp+0D8h+var_B0], rax; struct tagWiaTraceData_Type *
0x1800598f9  lea     rcx, [rsp+0D8h+var_78]; this
0x1800598fe  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180059903  xor     eax, eax
0x180059905  mov     [rsp+0D8h+var_A8], 1
0x18005990d  mov     [rsp+0D8h+var_88], rax
0x180059912  lea     r9, [rsp+0D8h+pvar]
0x180059917  mov     rax, [rbx]
0x18005991a  lea     r8, [rsp+0D8h+var_A8]
0x18005991f  xorps   xmm0, xmm0
0x180059922  mov     [rsp+0D8h+var_A0], esi
0x180059926  mov     edx, 1
0x18005992b  mov     rcx, rbx
0x18005992e  movups  xmmword ptr [rsp+0D8h+pvar], xmm0
0x180059933  mov     rax, [rax+18h]
0x180059937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005993c  mov     edi, eax
0x18005993e  test    eax, eax
0x180059940  jnz     short loc_180059956
0x180059942  mov     ecx, dword ptr [rsp+0D8h+pvar+8]
0x180059946  mov     [r14], ecx
0x180059949  lea     rcx, [rsp+0D8h+pvar]; pvar
0x18005994e  call    cs:__imp_PropVariantClear
0x180059954  jmp     short loc_1800599A3
0x180059956  mov     edx, esi
0x180059958  lea     rcx, aReadmultipleOf; "ReadMultiple of propid: %d, failed"
0x18005995f  call    WiaTrace_TraceLog
0x180059964  mov     rdx, rax; char *
0x180059967  lea     rcx, aReadproplong; "ReadPropLong"
0x18005996e  mov     rbx, rax
0x180059971  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180059976  mov     rcx, rbx; this
0x180059979  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005997e  mov     edx, esi
0x180059980  lea     rcx, aReadmultipleOf; "ReadMultiple of propid: %d, failed"
0x180059987  call    WiaTrace_Trace
0x18005998c  mov     r9d, 1; int
0x180059992  mov     [rsp+0D8h+lpMem], rax; lpMem
0x180059997  lea     r8, aReadproplong; "ReadPropLong"
0x18005999e  call    WiaTrace_ProcessTrace_Ex
0x1800599a3  lea     rcx, [rsp+0D8h+var_78]; this
0x1800599a8  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x1800599ad  mov     eax, edi
0x1800599af  add     rsp, 0B8h
0x1800599b6  pop     r14
0x1800599b8  pop     rdi
0x1800599b9  pop     rsi
0x1800599ba  pop     rbx
0x1800599bb  retn
```
