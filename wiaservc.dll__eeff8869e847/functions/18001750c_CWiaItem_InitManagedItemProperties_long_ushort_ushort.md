# CWiaItem::InitManagedItemProperties(long,ushort *,ushort *)

- ea: `0x18001750c`
- end: `0x18001772e`
- name: `?InitManagedItemProperties@CWiaItem@@QEAAJJPEAG0@Z`
- size: `546`
- prototype: `__int64 __fastcall(CWiaItem *__hidden this, int, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `13`
- tags: ``

## callers

- `0x1800453c0`
- `0x1800552bc`
- `0x180060520`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18001750c`
- `0x180017740`
- `0x1800185a0`
- `0x180018ad8`
- `0x18002de18`
- `0x18002def8`
- `0x180034658`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800176c2`
- `KERNEL32!LocalFree` at `0x1800176c2`
- `KERNEL32!LocalAlloc` at `0x180017635`
- `KERNEL32!LocalAlloc` at `0x180017635`

## string_xrefs

- `0x1800176ca`: `CWiaItem::InitManagedItemProperties, Out of Memory!`
- `0x1800176ec`: `CWiaItem::InitManagedItemProperties, Out of Memory!`
- `0x180017521`: `CWiaItem::InitManagedItemProperties`
- `0x1800175e8`: `CWiaItem::InitManagedItemProperties, wiasSetPropertyAttributes failed, index: %d`
- `0x18001760c`: `CWiaItem::InitManagedItemProperties, wiasSetPropertyAttributes failed, index: %d`

## pseudocode

```c
__int64 __fastcall CWiaItem::InitManagedItemProperties(
        struct IWiaItem *this,
        int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  char ***v8; // rax
  char *v9; // rdx
  __int64 v10; // r8
  unsigned int i; // edi
  int v12; // eax
  char *v13; // rbx
  void *v14; // rdx
  void **v15; // rax
  void *v16; // rdx
  __int64 v17; // rcx
  _QWORD *v18; // rax
  _QWORD *v19; // rbx
  int v20; // eax
  unsigned int v21; // edi
  char *v22; // rbx
  void *v23; // rdx
  void **v24; // rax
  void *v25; // rdx
  __int64 v26; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-B8h]
  int v29; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v30[2]; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-90h]
  _BYTE v32[136]; // [rsp+50h] [rbp-88h] BYREF

  v8 = (char ***)WiaTrace_Trace("CWiaItem::InitManagedItemProperties");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v32, v9, v10, (char **)"CWiaItem::InitManagedItemProperties", lpMem, v8);
  wiasSetItemPropNames(this, 4, &s_piItemNameType, &s_pszItemNameType);
  *(_OWORD *)v30 = 0;
  v31 = 0;
  for ( i = 0; i < 4; ++i )
  {
    if ( i == 3 )
      LOWORD(v30[0]) = 4104;
    else
      LOWORD(v30[0]) = 3;
    v12 = 65571;
    LODWORD(v30[1]) = 0;
    if ( i != 3 )
      v12 = 65545;
    v29 = v12;
    if ( (int)wiasSetPropertyAttributes(this, 1, &s_psItemNameType + i, (__int64)&v29, (__int64)v30) < 0 )
    {
      v13 = (char *)WiaTrace_TraceLog("CWiaItem::InitManagedItemProperties, wiasSetPropertyAttributes failed, index: %d");
      WriteDbgTraceErrorWI("CWiaItem::InitManagedItemProperties", v13);
      WiaTrcLib::Free((WiaTrcLib *)v13, v14);
      v15 = (void **)WiaTrace_Trace(
                       "CWiaItem::InitManagedItemProperties, wiasSetPropertyAttributes failed, index: %d",
                       i);
      WiaTrace_ProcessTrace_Ex(v17, v16, (void *)"CWiaItem::InitManagedItemProperties", 1, v15);
      break;
    }
  }
  v18 = LocalAlloc(0x40u, 0x60u);
  v19 = v18;
  if ( v18 )
  {
    memset_0(v18, 0, 0x60u);
    v19[4] = a4;
    *(_WORD *)v19 = 8;
    *((_WORD *)v19 + 12) = 8;
    v19[1] = a3;
    *((_WORD *)v19 + 24) = 3;
    *((_DWORD *)v19 + 14) = a2;
    v20 = (*(__int64 (__fastcall **)(HRESULT (__stdcall *)(IWiaItem *, const IID *const, void **), __int64, struct tagPROPSPEC *, _QWORD *, int))(*(_QWORD *)this[27].lpVtbl->QueryInterface + 32LL))(
            this[27].lpVtbl->QueryInterface,
            4,
            &s_psItemNameType,
            v19,
            2);
    v21 = v20;
    if ( v20 < 0 )
      ReportReadWriteMultipleError(v20, "CWiaItem::InitManagedItemProperties", 0, 0, 4u, &s_psItemNameType);
    LocalFree(v19);
  }
  else
  {
    v22 = (char *)WiaTrace_TraceLog("CWiaItem::InitManagedItemProperties, Out of Memory!");
    WriteDbgTraceErrorWI("CWiaItem::InitManagedItemProperties", v22);
    WiaTrcLib::Free((WiaTrcLib *)v22, v23);
    v24 = (void **)WiaTrace_Trace("CWiaItem::InitManagedItemProperties, Out of Memory!");
    WiaTrace_ProcessTrace_Ex(v26, v25, (void *)"CWiaItem::InitManagedItemProperties", 1, v24);
    v21 = -2147024882;
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v32);
  return v21;
}

```

## disassembly

```asm
0x18001750c  push    rbx
0x18001750e  push    rbp
0x18001750f  push    rsi
0x180017510  push    rdi
0x180017511  push    r12
0x180017513  push    r14
0x180017515  push    r15
0x180017517  sub     rsp, 0A0h
0x18001751e  mov     rsi, rcx
0x180017521  lea     r12, aCwiaitemInitma; "CWiaItem::InitManagedItemProperties"
0x180017528  mov     rcx, r12
0x18001752b  mov     rbp, r9
0x18001752e  mov     r14, r8
0x180017531  mov     r15d, edx
0x180017534  call    WiaTrace_Trace
0x180017539  mov     r9, r12; char *
0x18001753c  mov     [rsp+0D8h+var_B0], rax; struct tagWiaTraceData_Type *
0x180017541  lea     rcx, [rsp+0D8h+var_88]; this
0x180017546  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18001754b  lea     r9, ?s_pszItemNameType@@3PAPEAGA; unsigned __int16 **
0x180017552  mov     edx, 4; int
0x180017557  lea     r8, ?s_piItemNameType@@3PAKA; unsigned int *
0x18001755e  mov     rcx, rsi; this
0x180017561  call    wiasSetItemPropNames
0x180017566  xor     eax, eax
0x180017568  xorps   xmm0, xmm0
0x18001756b  movups  xmmword ptr [rsp+0D8h+var_A0], xmm0
0x180017570  mov     [rsp+0D8h+var_90], rax
0x180017575  xor     edi, edi
0x180017577  lea     r9, ?s_psItemNameType@@3PAUtagPROPSPEC@@A; tagPROPSPEC near * s_psItemNameType
0x18001757e  mov     edx, 3
0x180017583  cmp     edi, 4
0x180017586  jnb     loc_18001762B
0x18001758c  cmp     edi, edx
0x18001758e  jnz     short loc_18001759C
0x180017590  mov     eax, 1008h
0x180017595  mov     word ptr [rsp+0D8h+var_A0], ax
0x18001759a  jmp     short loc_1800175A1
0x18001759c  mov     word ptr [rsp+0D8h+var_A0], dx
0x1800175a1  mov     eax, 10023h
0x1800175a6  mov     r8d, edi
0x1800175a9  mov     edx, 1
0x1800175ae  mov     dword ptr [rsp+0D8h+var_A0+8], 0
0x1800175b6  lea     ecx, [rax-1Ah]
0x1800175b9  cmovnz  eax, ecx
0x1800175bc  shl     r8, 4
0x1800175c0  mov     [rsp+0D8h+var_A8], eax
0x1800175c4  add     r8, r9
0x1800175c7  lea     rax, [rsp+0D8h+var_A0]
0x1800175cc  mov     rcx, rsi; this
0x1800175cf  lea     r9, [rsp+0D8h+var_A8]
0x1800175d4  mov     [rsp+0D8h+lpMem], rax; __int64
0x1800175d9  call    wiasSetPropertyAttributes
0x1800175de  test    eax, eax
0x1800175e0  js      short loc_1800175E6
0x1800175e2  inc     edi
0x1800175e4  jmp     short loc_180017577
0x1800175e6  mov     edx, edi
0x1800175e8  lea     rcx, aCwiaitemInitma_1; "CWiaItem::InitManagedItemProperties, wi"...
0x1800175ef  call    WiaTrace_TraceLog
0x1800175f4  mov     rdx, rax; char *
0x1800175f7  mov     rcx, r12; char *
0x1800175fa  mov     rbx, rax
0x1800175fd  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180017602  mov     rcx, rbx; this
0x180017605  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001760a  mov     edx, edi
0x18001760c  lea     rcx, aCwiaitemInitma_1; "CWiaItem::InitManagedItemProperties, wi"...
0x180017613  call    WiaTrace_Trace
0x180017618  mov     r9d, 1; int
0x18001761e  mov     [rsp+0D8h+lpMem], rax; lpMem
0x180017623  mov     r8, r12; int
0x180017626  call    WiaTrace_ProcessTrace_Ex
0x18001762b  mov     edi, 60h ; '`'
0x180017630  mov     edx, edi; uBytes
0x180017632  lea     ecx, [rdi-20h]; uFlags
0x180017635  call    cs:__imp_LocalAlloc
0x18001763b  mov     rbx, rax
0x18001763e  test    rax, rax
0x180017641  jz      loc_1800176CA
0x180017647  mov     r8d, edi; Size
0x18001764a  xor     edx, edx; Val
0x18001764c  mov     rcx, rax; void *
0x18001764f  call    memset_0
0x180017654  mov     [rbx+20h], rbp
0x180017658  lea     eax, [rdi-58h]
0x18001765b  mov     [rbx], ax
0x18001765e  lea     rbp, ?s_psItemNameType@@3PAUtagPROPSPEC@@A; tagPROPSPEC near * s_psItemNameType
0x180017665  mov     [rbx+18h], ax
0x180017669  mov     r9, rbx
0x18001766c  mov     [rbx+8], r14
0x180017670  mov     r8, rbp
0x180017673  mov     word ptr [rbx+30h], 3
0x180017679  mov     [rbx+38h], r15d
0x18001767d  mov     rax, [rsi+0D8h]
0x180017684  lea     esi, [rdi-5Ch]
0x180017687  mov     edx, esi
0x180017689  mov     dword ptr [rsp+0D8h+lpMem], 2
0x180017691  mov     rcx, [rax]
0x180017694  mov     rax, [rcx]
0x180017697  mov     rax, [rax+20h]
0x18001769b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176a0  mov     edi, eax
0x1800176a2  test    eax, eax
0x1800176a4  jns     short loc_1800176BF
0x1800176a6  mov     [rsp+0D8h+var_B0], rbp; struct tagPROPSPEC *
0x1800176ab  xor     r9d, r9d; int
0x1800176ae  xor     r8d, r8d; char *
0x1800176b1  mov     dword ptr [rsp+0D8h+lpMem], esi; unsigned int
0x1800176b5  mov     rdx, r12; char *
0x1800176b8  mov     ecx, eax; int
0x1800176ba  call    ?ReportReadWriteMultipleError@@YAXJPEAD0HKQEBUtagPROPSPEC@@@Z; ReportReadWriteMultipleError(long,char *,char *,int,ulong,tagPROPSPEC const * const)
0x1800176bf  mov     rcx, rbx; hMem
0x1800176c2  call    cs:__imp_LocalFree
0x1800176c8  jmp     short loc_180017710
0x1800176ca  lea     rcx, aCwiaitemInitma_0; "CWiaItem::InitManagedItemProperties, Ou"...
0x1800176d1  call    WiaTrace_TraceLog
0x1800176d6  mov     rdx, rax; char *
0x1800176d9  mov     rcx, r12; char *
0x1800176dc  mov     rbx, rax
0x1800176df  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800176e4  mov     rcx, rbx; this
0x1800176e7  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800176ec  lea     rcx, aCwiaitemInitma_0; "CWiaItem::InitManagedItemProperties, Ou"...
0x1800176f3  call    WiaTrace_Trace
0x1800176f8  mov     r9d, 1; int
0x1800176fe  mov     [rsp+0D8h+lpMem], rax; lpMem
0x180017703  mov     r8, r12; int
0x180017706  call    WiaTrace_ProcessTrace_Ex
0x18001770b  mov     edi, 8007000Eh
0x180017710  lea     rcx, [rsp+0D8h+var_88]; this
0x180017715  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18001771a  mov     eax, edi
0x18001771c  add     rsp, 0A0h
0x180017723  pop     r15
0x180017725  pop     r14
0x180017727  pop     r12
0x180017729  pop     rdi
0x18001772a  pop     rsi
0x18001772b  pop     rbp
0x18001772c  pop     rbx
0x18001772d  retn
```
