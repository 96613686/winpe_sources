# wiasWritePropStr

- ea: `0x180044d80`
- end: `0x180045025`
- name: `wiasWritePropStr`
- size: `677`
- prototype: `__int64 __fastcall(CWiaItem *this, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180059ed4`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x1800189cc`
- `0x18001f614`
- `0x180026f30`
- `0x18002de18`
- `0x18002def8`
- `0x180030060`
- `0x180044d80`
- `0x18005a354`

## string_xrefs

- `0x180044d9e`: `::wiasWritePropStr`
- `0x180044dac`: `wiasWritePropStr`
- `0x180044dd2`: `wiasWritePropStr, invalid pItem`
- `0x180044df4`: `wiasWritePropStr, invalid pItem`
- `0x180044e30`: `wiasWritePropStr failed, GetItemPropStreams item failed (0x%X)`
- `0x180044e52`: `wiasWritePropStr failed, GetItemPropStreams item failed (0x%X)`
- `0x180044e72`: `wiasWritePropStr, error writing new value`
- `0x180044e94`: `wiasWritePropStr, error writing new value`
- `0x180044f17`: `wiasWritePropStr failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)`
- `0x180044f3e`: `wiasWritePropStr failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)`
- `0x180044f63`: `wiasWritePropStr failed, GetItemPropStreams for A-AIT item failed (0x%X)`
- `0x180044f87`: `wiasWritePropStr failed, GetItemPropStreams for A-AIT item failed (0x%X)`
- `0x180044fc0`: `wiasWritePropStr, error writing new value for A-AIT item (0x%X)`
- `0x180044fe2`: `wiasWritePropStr, error writing new value for A-AIT item (0x%X)`

## pseudocode

```c
__int64 __fastcall wiasWritePropStr(struct IWiaItem *this, unsigned int a2, unsigned __int16 *a3)
{
  struct tagWiaTraceData_Type *v6; // rax
  char *v7; // rdx
  unsigned int v8; // r8d
  int ItemPropStreams; // edi
  char *v10; // rbx
  void *v11; // rdx
  void **v12; // rax
  void *v13; // rdx
  __int64 v14; // rcx
  char *v15; // rbx
  void *v16; // rdx
  char *v17; // rbx
  void *v18; // rdx
  struct CWiaItem *v19; // rcx
  int RelatedAAITItem; // eax
  int v21; // eax
  struct IPropertyStorage *v22; // rsi
  char *v23; // rbx
  void *v24; // rdx
  void **v25; // rax
  void *v26; // rdx
  __int64 v27; // rcx
  char *v28; // rbx
  void *v29; // rdx
  void **v30; // rax
  void *v31; // rdx
  __int64 v32; // rcx
  char *v33; // rbx
  void *v34; // rdx
  unsigned int lpMem; // [rsp+20h] [rbp-39h]
  struct IPropertyStorage *v37; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v38[112]; // [rsp+40h] [rbp-19h] BYREF
  struct IPropertyStorage *v39; // [rsp+C0h] [rbp+67h] BYREF
  struct CWiaItem *v40; // [rsp+D8h] [rbp+7Fh] BYREF

  v6 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::wiasWritePropStr");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v38, v7, v8, "wiasWritePropStr", lpMem, v6);
  ItemPropStreams = ValidateWiaItem(this);
  if ( ItemPropStreams < 0 )
  {
    v10 = (char *)WiaTrace_TraceLog("wiasWritePropStr, invalid pItem");
    WriteDbgTraceErrorWI("wiasWritePropStr", v10);
    WiaTrcLib::Free((WiaTrcLib *)v10, v11);
    v12 = (void **)WiaTrace_Trace("wiasWritePropStr, invalid pItem");
    goto LABEL_19;
  }
  v39 = 0;
  ItemPropStreams = CWiaItem::GetItemPropStreams((CWiaItem *)this, &v39, 0, 0, 0);
  if ( ItemPropStreams < 0 )
  {
    v15 = (char *)WiaTrace_TraceLog("wiasWritePropStr failed, GetItemPropStreams item failed (0x%X)");
    WriteDbgTraceErrorWI("wiasWritePropStr", v15);
    WiaTrcLib::Free((WiaTrcLib *)v15, v16);
    v12 = (void **)WiaTrace_Trace(
                     "wiasWritePropStr failed, GetItemPropStreams item failed (0x%X)",
                     (unsigned int)ItemPropStreams);
LABEL_19:
    WiaTrace_ProcessTrace_Ex(v14, v13, (void *)"wiasWritePropStr", 1, v12);
    goto LABEL_20;
  }
  ItemPropStreams = WritePropStr(a2, v39, a3);
  if ( ItemPropStreams < 0 )
  {
    v17 = (char *)WiaTrace_TraceLog("wiasWritePropStr, error writing new value");
    WriteDbgTraceErrorWI("wiasWritePropStr", v17);
    WiaTrcLib::Free((WiaTrcLib *)v17, v18);
    v12 = (void **)WiaTrace_Trace("wiasWritePropStr, error writing new value");
    goto LABEL_19;
  }
  if ( (unsigned int)CWiaItem::IsCompatMode((CWiaItem *)this) )
  {
    v40 = 0;
    v37 = 0;
    LODWORD(v39) = 0;
    RelatedAAITItem = _FindRelatedAAITItem(v19, a2, &v40, (unsigned int *)&v39);
    ItemPropStreams = RelatedAAITItem;
    if ( RelatedAAITItem == 1 )
    {
      ItemPropStreams = 0;
      goto LABEL_20;
    }
    if ( RelatedAAITItem )
      goto LABEL_20;
    v21 = CWiaItem::GetItemPropStreams(v40, &v37, 0, 0, 0);
    v22 = v37;
    ItemPropStreams = v21;
    if ( v37 )
    {
      if ( v21 >= 0 )
      {
LABEL_17:
        ItemPropStreams = WritePropStr((unsigned int)v39, v22, a3);
        if ( ItemPropStreams < 0 )
        {
          v33 = (char *)WiaTrace_TraceLog("wiasWritePropStr, error writing new value for A-AIT item (0x%X)");
          WriteDbgTraceErrorWI("wiasWritePropStr", v33);
          WiaTrcLib::Free((WiaTrcLib *)v33, v34);
          v12 = (void **)WiaTrace_Trace(
                           "wiasWritePropStr, error writing new value for A-AIT item (0x%X)",
                           (unsigned int)ItemPropStreams);
          goto LABEL_19;
        }
        goto LABEL_20;
      }
    }
    else if ( v21 >= 0 )
    {
      ItemPropStreams = -2147467261;
      v23 = (char *)WiaTrace_TraceLog("wiasWritePropStr failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)");
      WriteDbgTraceErrorWI("wiasWritePropStr", v23);
      WiaTrcLib::Free((WiaTrcLib *)v23, v24);
      v25 = (void **)WiaTrace_Trace("wiasWritePropStr failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)");
      WiaTrace_ProcessTrace_Ex(v27, v26, (void *)"wiasWritePropStr", 1, v25);
    }
    v28 = (char *)WiaTrace_TraceLog("wiasWritePropStr failed, GetItemPropStreams for A-AIT item failed (0x%X)");
    WriteDbgTraceErrorWI("wiasWritePropStr", v28);
    WiaTrcLib::Free((WiaTrcLib *)v28, v29);
    v30 = (void **)WiaTrace_Trace(
                     "wiasWritePropStr failed, GetItemPropStreams for A-AIT item failed (0x%X)",
                     ItemPropStreams);
    WiaTrace_ProcessTrace_Ex(v32, v31, (void *)"wiasWritePropStr", 1, v30);
    if ( ItemPropStreams < 0 )
      goto LABEL_20;
    goto LABEL_17;
  }
LABEL_20:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v38);
  return (unsigned int)ItemPropStreams;
}

```

## disassembly

```asm
0x180044d80  mov     [rsp-8+arg_8], rbx
0x180044d85  push    rbp
0x180044d86  push    rsi
0x180044d87  push    rdi
0x180044d88  push    r12
0x180044d8a  push    r14
0x180044d8c  lea     rbp, [rsp-37h]
0x180044d91  sub     rsp, 90h
0x180044d98  mov     rbx, rcx
0x180044d9b  mov     r14, r8
0x180044d9e  lea     rcx, aWiaswriteprops_6; "::wiasWritePropStr"
0x180044da5  mov     esi, edx
0x180044da7  call    WiaTrace_Trace
0x180044dac  lea     r12, aWiaswriteprops_5; "wiasWritePropStr"
0x180044db3  mov     [rsp+0B0h+var_88], rax; struct tagWiaTraceData_Type *
0x180044db8  mov     r9, r12; char *
0x180044dbb  lea     rcx, [rbp+57h+var_70]; this
0x180044dbf  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180044dc4  mov     rcx, rbx; struct IWiaItem *
0x180044dc7  call    ?ValidateWiaItem@@YAJPEAUIWiaItem@@@Z; ValidateWiaItem(IWiaItem *)
0x180044dcc  mov     edi, eax
0x180044dce  test    eax, eax
0x180044dd0  jns     short loc_180044E05
0x180044dd2  lea     rcx, aWiaswriteprops_7; "wiasWritePropStr, invalid pItem"
0x180044dd9  call    WiaTrace_TraceLog
0x180044dde  mov     rdx, rax; char *
0x180044de1  mov     rcx, r12; char *
0x180044de4  mov     rbx, rax
0x180044de7  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180044dec  mov     rcx, rbx; this
0x180044def  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180044df4  lea     rcx, aWiaswriteprops_7; "wiasWritePropStr, invalid pItem"
0x180044dfb  call    WiaTrace_Trace
0x180044e00  jmp     loc_180044FF0
0x180044e05  xor     r9d, r9d; struct IPropertyStorage **
0x180044e08  mov     [rbp+57h+arg_0], 0
0x180044e10  xor     r8d, r8d; struct IPropertyStorage **
0x180044e13  mov     [rsp+0B0h+lpMem], 0; struct IPropertyStorage **
0x180044e1c  lea     rdx, [rbp+57h+arg_0]; struct IPropertyStorage **
0x180044e20  mov     rcx, rbx; this
0x180044e23  call    ?GetItemPropStreams@CWiaItem@@QEAAJPEAPEAUIPropertyStorage@@000@Z; CWiaItem::GetItemPropStreams(IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *)
0x180044e28  mov     edi, eax
0x180044e2a  test    eax, eax
0x180044e2c  jns     short loc_180044E5E
0x180044e2e  mov     edx, eax
0x180044e30  lea     rcx, aWiaswriteprops_3; "wiasWritePropStr failed, GetItemPropStr"...
0x180044e37  call    WiaTrace_TraceLog
0x180044e3c  mov     rdx, rax; char *
0x180044e3f  mov     rcx, r12; char *
0x180044e42  mov     rbx, rax
0x180044e45  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180044e4a  mov     rcx, rbx; this
0x180044e4d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180044e52  lea     rcx, aWiaswriteprops_3; "wiasWritePropStr failed, GetItemPropStr"...
0x180044e59  jmp     loc_180044FE9
0x180044e5e  mov     rdx, [rbp+57h+arg_0]; struct IPropertyStorage *
0x180044e62  mov     r8, r14; unsigned __int16 *
0x180044e65  mov     ecx, esi; unsigned int
0x180044e67  call    ?WritePropStr@@YAJKPEAUIPropertyStorage@@PEAG@Z; WritePropStr(ulong,IPropertyStorage *,ushort *)
0x180044e6c  mov     edi, eax
0x180044e6e  test    eax, eax
0x180044e70  jns     short loc_180044EA0
0x180044e72  lea     rcx, aWiaswriteprops_1; "wiasWritePropStr, error writing new val"...
0x180044e79  call    WiaTrace_TraceLog
0x180044e7e  mov     rdx, rax; char *
0x180044e81  mov     rcx, r12; char *
0x180044e84  mov     rbx, rax
0x180044e87  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180044e8c  mov     rcx, rbx; this
0x180044e8f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180044e94  lea     rcx, aWiaswriteprops_1; "wiasWritePropStr, error writing new val"...
0x180044e9b  jmp     loc_180044DFB
0x180044ea0  mov     rcx, rbx; this
0x180044ea3  call    ?IsCompatMode@CWiaItem@@QEBAHXZ; CWiaItem::IsCompatMode(void)
0x180044ea8  test    eax, eax
0x180044eaa  jz      loc_180045003
0x180044eb0  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x180044eb4  mov     [rbp+57h+arg_18], 0
0x180044ebc  lea     r8, [rbp+57h+arg_18]; struct CWiaItem **
0x180044ec0  mov     [rbp+57h+var_80], 0
0x180044ec8  mov     edx, esi; unsigned int
0x180044eca  mov     dword ptr [rbp+57h+arg_0], 0
0x180044ed1  call    ?_FindRelatedAAITItem@@YAJPEAVCWiaItem@@KPEAPEAV1@PEAK@Z; _FindRelatedAAITItem(CWiaItem *,ulong,CWiaItem * *,ulong *)
0x180044ed6  mov     edi, eax
0x180044ed8  cmp     eax, 1
0x180044edb  jnz     short loc_180044EE4
0x180044edd  xor     edi, edi
0x180044edf  jmp     loc_180045003
0x180044ee4  test    eax, eax
0x180044ee6  jnz     loc_180045003
0x180044eec  mov     rcx, [rbp+57h+arg_18]; this
0x180044ef0  lea     rdx, [rbp+57h+var_80]; struct IPropertyStorage **
0x180044ef4  xor     r9d, r9d; struct IPropertyStorage **
0x180044ef7  mov     [rsp+0B0h+lpMem], 0; struct IPropertyStorage **
0x180044f00  xor     r8d, r8d; struct IPropertyStorage **
0x180044f03  call    ?GetItemPropStreams@CWiaItem@@QEAAJPEAPEAUIPropertyStorage@@000@Z; CWiaItem::GetItemPropStreams(IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *)
0x180044f08  mov     rsi, [rbp+57h+var_80]
0x180044f0c  mov     edi, eax
0x180044f0e  test    rsi, rsi
0x180044f11  jnz     short loc_180044F5D
0x180044f13  test    eax, eax
0x180044f15  js      short loc_180044F61
0x180044f17  lea     rcx, aWiaswriteprops_2; "wiasWritePropStr failed, GetItemPropStr"...
0x180044f1e  mov     edi, 80004003h
0x180044f23  call    WiaTrace_TraceLog
0x180044f28  mov     rdx, rax; char *
0x180044f2b  mov     rcx, r12; char *
0x180044f2e  mov     rbx, rax
0x180044f31  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180044f36  mov     rcx, rbx; this
0x180044f39  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180044f3e  lea     rcx, aWiaswriteprops_2; "wiasWritePropStr failed, GetItemPropStr"...
0x180044f45  call    WiaTrace_Trace
0x180044f4a  lea     r9d, [rsi+1]; int
0x180044f4e  mov     [rsp+0B0h+lpMem], rax; lpMem
0x180044f53  mov     r8, r12; int
0x180044f56  call    WiaTrace_ProcessTrace_Ex
0x180044f5b  jmp     short loc_180044F61
0x180044f5d  test    eax, eax
0x180044f5f  jns     short loc_180044FAA
0x180044f61  mov     edx, edi
0x180044f63  lea     rcx, aWiaswriteprops_4; "wiasWritePropStr failed, GetItemPropStr"...
0x180044f6a  call    WiaTrace_TraceLog
0x180044f6f  mov     rdx, rax; char *
0x180044f72  mov     rcx, r12; char *
0x180044f75  mov     rbx, rax
0x180044f78  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180044f7d  mov     rcx, rbx; this
0x180044f80  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180044f85  mov     edx, edi
0x180044f87  lea     rcx, aWiaswriteprops_4; "wiasWritePropStr failed, GetItemPropStr"...
0x180044f8e  call    WiaTrace_Trace
0x180044f93  mov     r9d, 1; int
0x180044f99  mov     [rsp+0B0h+lpMem], rax; lpMem
0x180044f9e  mov     r8, r12; int
0x180044fa1  call    WiaTrace_ProcessTrace_Ex
0x180044fa6  test    edi, edi
0x180044fa8  js      short loc_180045003
0x180044faa  mov     ecx, dword ptr [rbp+57h+arg_0]; unsigned int
0x180044fad  mov     r8, r14; unsigned __int16 *
0x180044fb0  mov     rdx, rsi; struct IPropertyStorage *
0x180044fb3  call    ?WritePropStr@@YAJKPEAUIPropertyStorage@@PEAG@Z; WritePropStr(ulong,IPropertyStorage *,ushort *)
0x180044fb8  mov     edi, eax
0x180044fba  test    eax, eax
0x180044fbc  jns     short loc_180045003
0x180044fbe  mov     edx, eax
0x180044fc0  lea     rcx, aWiaswriteprops_0; "wiasWritePropStr, error writing new val"...
0x180044fc7  call    WiaTrace_TraceLog
0x180044fcc  mov     rdx, rax; char *
0x180044fcf  mov     rcx, r12; char *
0x180044fd2  mov     rbx, rax
0x180044fd5  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180044fda  mov     rcx, rbx; this
0x180044fdd  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180044fe2  lea     rcx, aWiaswriteprops_0; "wiasWritePropStr, error writing new val"...
0x180044fe9  mov     edx, edi
0x180044feb  call    WiaTrace_Trace
0x180044ff0  mov     r9d, 1; int
0x180044ff6  mov     [rsp+0B0h+lpMem], rax; lpMem
0x180044ffb  mov     r8, r12; int
0x180044ffe  call    WiaTrace_ProcessTrace_Ex
0x180045003  lea     rcx, [rbp+57h+var_70]; this
0x180045007  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18004500c  mov     rbx, [rsp+0B0h+arg_8]
0x180045014  mov     eax, edi
0x180045016  add     rsp, 90h
0x18004501d  pop     r14
0x18004501f  pop     r12
0x180045021  pop     rdi
0x180045022  pop     rsi
0x180045023  pop     rbp
0x180045024  retn
```
