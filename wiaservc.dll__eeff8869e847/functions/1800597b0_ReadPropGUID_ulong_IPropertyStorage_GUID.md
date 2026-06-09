# ReadPropGUID(ulong,IPropertyStorage *,_GUID *)

- ea: `0x1800597b0`
- end: `0x1800598c3`
- name: `?ReadPropGUID@@YAJKPEAUIPropertyStorage@@PEAU_GUID@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(unsigned int, struct IPropertyStorage *, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18006e160`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002de18`
- `0x18002def8`
- `0x1800597b0`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantClear` at `0x180059843`
- `ole32!PropVariantClear` at `0x180059843`

## string_xrefs

- `0x180059854`: `ReadMultiple of propid: %d, failed`
- `0x18005987f`: `ReadMultiple of propid: %d, failed`
- `0x1800597c2`: `::ReadPropLong`
- `0x1800597d4`: `ReadPropGUID`
- `0x180059863`: `ReadPropGUID`
- `0x180059896`: `ReadPropGUID`

## pseudocode

```c
__int64 __fastcall ReadPropGUID(__int64 a1, struct IPropertyStorage *a2, struct _GUID *a3)
{
  char ***v5; // rax
  char *v6; // rdx
  __int64 v7; // r8
  struct IPropertyStorageVtbl *lpVtbl; // rax
  int v9; // edi
  char *v10; // rbx
  void *v11; // rdx
  void **v12; // rax
  void *v13; // rdx
  __int64 v14; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-98h]
  int v17; // [rsp+30h] [rbp-88h] BYREF
  __int64 v18; // [rsp+38h] [rbp-80h]
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-78h] BYREF
  __int64 v20; // [rsp+50h] [rbp-68h]
  _BYTE v21[80]; // [rsp+60h] [rbp-58h] BYREF

  v5 = (char ***)WiaTrace_Trace("::ReadPropLong");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v21, v6, v7, (char **)"ReadPropGUID", lpMem, v5);
  v17 = 1;
  v18 = 0;
  v20 = 0;
  lpVtbl = a2->lpVtbl;
  LODWORD(v18) = 4106;
  *(_OWORD *)pvar = 0;
  v9 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, int *, PROPVARIANT *))lpVtbl->ReadMultiple)(
         a2,
         1,
         &v17,
         pvar);
  if ( v9 )
  {
    if ( v9 < 0 )
    {
      v10 = (char *)WiaTrace_TraceLog("ReadMultiple of propid: %d, failed");
      WriteDbgTraceErrorWI("ReadPropGUID", v10);
      WiaTrcLib::Free((WiaTrcLib *)v10, v11);
      v12 = (void **)WiaTrace_Trace("ReadMultiple of propid: %d, failed", 4106);
      WiaTrace_ProcessTrace_Ex(v14, v13, (void *)"ReadPropGUID", 1, v12);
    }
  }
  else
  {
    *a3 = *(struct _GUID *)pvar[1];
    PropVariantClear(pvar);
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v21);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800597b0  mov     [rsp+arg_0], rbx
0x1800597b5  mov     [rsp+arg_8], rsi
0x1800597ba  push    rdi
0x1800597bb  sub     rsp, 0B0h
0x1800597c2  lea     rcx, aReadproplong_0; "::ReadPropLong"
0x1800597c9  mov     rsi, r8
0x1800597cc  mov     rbx, rdx
0x1800597cf  call    WiaTrace_Trace
0x1800597d4  lea     r9, aReadpropguid; "ReadPropGUID"
0x1800597db  mov     [rsp+0B8h+var_90], rax; struct tagWiaTraceData_Type *
0x1800597e0  lea     rcx, [rsp+0B8h+var_58]; this
0x1800597e5  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x1800597ea  xor     eax, eax
0x1800597ec  mov     [rsp+0B8h+var_88], 1
0x1800597f4  mov     [rsp+0B8h+var_80], rax
0x1800597f9  lea     r9, [rsp+0B8h+pvar]
0x1800597fe  mov     [rsp+0B8h+var_68], rax
0x180059803  lea     r8, [rsp+0B8h+var_88]
0x180059808  mov     rax, [rbx]
0x18005980b  xorps   xmm0, xmm0
0x18005980e  mov     edx, 1
0x180059813  mov     dword ptr [rsp+0B8h+var_80], 100Ah
0x18005981b  mov     rcx, rbx
0x18005981e  movups  xmmword ptr [rsp+0B8h+pvar], xmm0
0x180059823  mov     rax, [rax+18h]
0x180059827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005982c  mov     edi, eax
0x18005982e  test    eax, eax
0x180059830  jnz     short loc_18005984B
0x180059832  mov     rcx, [rsp+0B8h+pvar+8]
0x180059837  movups  xmm0, xmmword ptr [rcx]
0x18005983a  lea     rcx, [rsp+0B8h+pvar]; pvar
0x18005983f  movdqu  xmmword ptr [rsi], xmm0
0x180059843  call    cs:__imp_PropVariantClear
0x180059849  jmp     short loc_1800598A2
0x18005984b  test    edi, edi
0x18005984d  jns     short loc_1800598A2
0x18005984f  mov     edx, 100Ah
0x180059854  lea     rcx, aReadmultipleOf; "ReadMultiple of propid: %d, failed"
0x18005985b  call    WiaTrace_TraceLog
0x180059860  mov     rdx, rax; char *
0x180059863  lea     rcx, aReadpropguid; "ReadPropGUID"
0x18005986a  mov     rbx, rax
0x18005986d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180059872  mov     rcx, rbx; this
0x180059875  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005987a  mov     edx, 100Ah
0x18005987f  lea     rcx, aReadmultipleOf; "ReadMultiple of propid: %d, failed"
0x180059886  call    WiaTrace_Trace
0x18005988b  mov     r9d, 1; int
0x180059891  mov     [rsp+0B8h+lpMem], rax; lpMem
0x180059896  lea     r8, aReadpropguid; "ReadPropGUID"
0x18005989d  call    WiaTrace_ProcessTrace_Ex
0x1800598a2  lea     rcx, [rsp+0B8h+var_58]; this
0x1800598a7  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x1800598ac  lea     r11, [rsp+0B8h+var_8]
0x1800598b4  mov     eax, edi
0x1800598b6  mov     rbx, [r11+10h]
0x1800598ba  mov     rsi, [r11+18h]
0x1800598be  mov     rsp, r11
0x1800598c1  pop     rdi
0x1800598c2  retn
```
