# wiasWritePropLong

- ea: `0x1800178b0`
- end: `0x180017b5f`
- name: `wiasWritePropLong`
- size: `687`
- prototype: `__int64 __fastcall(CWiaItem *this, unsigned int, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180057734`
- `0x180057d44`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x1800178b0`
- `0x1800189cc`
- `0x18001f614`
- `0x180026f30`
- `0x1800284dc`
- `0x18002de18`
- `0x18002def8`
- `0x180030060`
- `0x18005a220`

## string_xrefs

- `0x18001790b`: `wiasWritePropLong, invalid pItem`
- `0x18001792d`: `wiasWritePropLong, invalid pItem`
- `0x1800178e3`: `wiasWritePropLong`
- `0x180017a21`: `wiasWritePropLong`
- `0x180017a4d`: `wiasWritePropLong`
- `0x180017a70`: `wiasWritePropLong`
- `0x180017aa0`: `wiasWritePropLong`
- `0x180017afc`: `wiasWritePropLong`
- `0x180017b21`: `wiasWritePropLong`
- `0x1800178d4`: `::wiasWritePropLong`
- `0x180017964`: `wiasWritePropLong failed, GetItemPropStreams item failed (0x%X)`
- `0x180017988`: `wiasWritePropLong failed, GetItemPropStreams item failed (0x%X)`
- `0x180017a0d`: `wiasWritePropLong failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)`
- `0x180017a38`: `wiasWritePropLong failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)`
- `0x180017a61`: `wiasWritePropLong failed, GetItemPropStreams for A-AIT item failed (0x%X)`
- `0x180017a89`: `wiasWritePropLong failed, GetItemPropStreams for A-AIT item failed (0x%X)`
- `0x180017aed`: `wiasWritePropLong, error writing new value for A-AIT item (0x%X)`
- `0x180017b15`: `wiasWritePropLong, error writing new value for A-AIT item (0x%X)`

## pseudocode

```c
__int64 __fastcall wiasWritePropLong(struct IWiaItem *this, unsigned int a2, int a3)
{
  char ***v6; // rax
  char *v7; // rdx
  __int64 v8; // r8
  int ItemPropStreams; // edi
  char *v10; // rbx
  void *v11; // rdx
  void **v12; // rax
  void *v13; // rdx
  __int64 v14; // rcx
  char *v15; // rbx
  void *v16; // rdx
  struct CWiaItem *v17; // rcx
  int RelatedAAITItem; // eax
  int v19; // eax
  struct IPropertyStorage *v20; // r13
  char *v21; // rbx
  void *v22; // rdx
  void **v23; // rax
  void *v24; // rdx
  __int64 v25; // rcx
  char *v26; // rbx
  void *v27; // rdx
  void **v28; // rax
  void *v29; // rdx
  __int64 v30; // rcx
  char *v31; // rbx
  void *v32; // rdx
  unsigned int lpMem; // [rsp+20h] [rbp-39h]
  struct IPropertyStorage *v35; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v36[80]; // [rsp+40h] [rbp-19h] BYREF
  struct IPropertyStorage *v37; // [rsp+C0h] [rbp+67h] BYREF
  struct CWiaItem *v38; // [rsp+D8h] [rbp+7Fh] BYREF

  v6 = (char ***)WiaTrace_Trace("::wiasWritePropLong");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v36, v7, v8, (char **)"wiasWritePropLong", lpMem, v6);
  ItemPropStreams = ValidateWiaItem(this);
  if ( ItemPropStreams < 0 )
  {
    v10 = (char *)WiaTrace_TraceLog("wiasWritePropLong, invalid pItem");
    WriteDbgTraceErrorWI("wiasWritePropLong", v10);
    WiaTrcLib::Free((WiaTrcLib *)v10, v11);
    v12 = (void **)WiaTrace_Trace("wiasWritePropLong, invalid pItem");
LABEL_20:
    WiaTrace_ProcessTrace_Ex(v14, v13, (void *)"wiasWritePropLong", 1, v12);
    goto LABEL_21;
  }
  v37 = 0;
  ItemPropStreams = CWiaItem::GetItemPropStreams((CWiaItem *)this, &v37, 0, 0, 0);
  if ( ItemPropStreams < 0 )
  {
    v15 = (char *)WiaTrace_TraceLog("wiasWritePropLong failed, GetItemPropStreams item failed (0x%X)");
    WriteDbgTraceErrorWI("wiasWritePropLong", v15);
    WiaTrcLib::Free((WiaTrcLib *)v15, v16);
    v12 = (void **)WiaTrace_Trace("wiasWritePropLong failed, GetItemPropStreams item failed (0x%X)", ItemPropStreams);
    goto LABEL_20;
  }
  WritePropLong(a2, v37, a3);
  if ( (unsigned int)CWiaItem::IsCompatMode((CWiaItem *)this) )
  {
    v38 = 0;
    v35 = 0;
    LODWORD(v37) = 0;
    RelatedAAITItem = _FindRelatedAAITItem(v17, a2, &v38, (unsigned int *)&v37);
    ItemPropStreams = RelatedAAITItem;
    if ( RelatedAAITItem == 1 )
    {
      ItemPropStreams = 0;
      goto LABEL_21;
    }
    if ( RelatedAAITItem )
      goto LABEL_21;
    v19 = CWiaItem::GetItemPropStreams(v38, &v35, 0, 0, 0);
    v20 = v35;
    ItemPropStreams = v19;
    if ( v35 )
    {
      if ( v19 >= 0 )
      {
LABEL_14:
        if ( a2 == 4108 && (unsigned int)CWiaItem::IsLegacyDriver((CWiaItem *)this) && a3 == 128 )
          a3 = 2;
        ItemPropStreams = WritePropLong((unsigned int)v37, v20, a3);
        if ( ItemPropStreams < 0 )
        {
          v31 = (char *)WiaTrace_TraceLog("wiasWritePropLong, error writing new value for A-AIT item (0x%X)");
          WriteDbgTraceErrorWI("wiasWritePropLong", v31);
          WiaTrcLib::Free((WiaTrcLib *)v31, v32);
          v12 = (void **)WiaTrace_Trace(
                           "wiasWritePropLong, error writing new value for A-AIT item (0x%X)",
                           ItemPropStreams);
          goto LABEL_20;
        }
        goto LABEL_21;
      }
    }
    else if ( v19 >= 0 )
    {
      ItemPropStreams = -2147467261;
      v21 = (char *)WiaTrace_TraceLog("wiasWritePropLong failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)");
      WriteDbgTraceErrorWI("wiasWritePropLong", v21);
      WiaTrcLib::Free((WiaTrcLib *)v21, v22);
      v23 = (void **)WiaTrace_Trace("wiasWritePropLong failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)");
      WiaTrace_ProcessTrace_Ex(v25, v24, (void *)"wiasWritePropLong", 1, v23);
    }
    v26 = (char *)WiaTrace_TraceLog("wiasWritePropLong failed, GetItemPropStreams for A-AIT item failed (0x%X)");
    WriteDbgTraceErrorWI("wiasWritePropLong", v26);
    WiaTrcLib::Free((WiaTrcLib *)v26, v27);
    v28 = (void **)WiaTrace_Trace(
                     "wiasWritePropLong failed, GetItemPropStreams for A-AIT item failed (0x%X)",
                     ItemPropStreams);
    WiaTrace_ProcessTrace_Ex(v30, v29, (void *)"wiasWritePropLong", 1, v28);
    if ( ItemPropStreams < 0 )
      goto LABEL_21;
    goto LABEL_14;
  }
LABEL_21:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v36);
  return (unsigned int)ItemPropStreams;
}

```

## disassembly

```asm
0x1800178b0  mov     [rsp-8+arg_8], rbx
0x1800178b5  mov     [rsp-8+arg_10], rsi
0x1800178ba  push    rbp
0x1800178bb  push    rdi
0x1800178bc  push    r12
0x1800178be  push    r13
0x1800178c0  push    r15
0x1800178c2  lea     rbp, [rsp-37h]
0x1800178c7  sub     rsp, 90h
0x1800178ce  mov     r15, rcx
0x1800178d1  mov     esi, r8d
0x1800178d4  lea     rcx, aWiaswritepropl_1; "::wiasWritePropLong"
0x1800178db  mov     r12d, edx
0x1800178de  call    WiaTrace_Trace
0x1800178e3  lea     r13, aWiaswritepropl_6; "wiasWritePropLong"
0x1800178ea  mov     [rsp+0B0h+var_88], rax; struct tagWiaTraceData_Type *
0x1800178ef  mov     r9, r13; char *
0x1800178f2  lea     rcx, [rbp+57h+var_70]; this
0x1800178f6  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x1800178fb  mov     rcx, r15; struct IWiaItem *
0x1800178fe  call    ?ValidateWiaItem@@YAJPEAUIWiaItem@@@Z; ValidateWiaItem(IWiaItem *)
0x180017903  xor     ebx, ebx
0x180017905  mov     edi, eax
0x180017907  test    eax, eax
0x180017909  jns     short loc_180017941
0x18001790b  lea     rcx, aWiaswritepropl_4; "wiasWritePropLong, invalid pItem"
0x180017912  call    WiaTrace_TraceLog
0x180017917  mov     rdx, rax; char *
0x18001791a  mov     rcx, r13; char *
0x18001791d  mov     rbx, rax
0x180017920  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180017925  mov     rcx, rbx; this
0x180017928  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001792d  lea     rcx, aWiaswritepropl_4; "wiasWritePropLong, invalid pItem"
0x180017934  call    WiaTrace_Trace
0x180017939  mov     r8, r13
0x18001793c  jmp     loc_180017B28
0x180017941  xor     r9d, r9d; struct IPropertyStorage **
0x180017944  mov     [rbp+57h+arg_0], rbx
0x180017948  xor     r8d, r8d; struct IPropertyStorage **
0x18001794b  mov     [rsp+0B0h+lpMem], rbx; struct IPropertyStorage **
0x180017950  lea     rdx, [rbp+57h+arg_0]; struct IPropertyStorage **
0x180017954  mov     rcx, r15; this
0x180017957  call    ?GetItemPropStreams@CWiaItem@@QEAAJPEAPEAUIPropertyStorage@@000@Z; CWiaItem::GetItemPropStreams(IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *)
0x18001795c  mov     edi, eax
0x18001795e  test    eax, eax
0x180017960  jns     short loc_180017996
0x180017962  mov     edx, eax
0x180017964  lea     rcx, aWiaswritepropl_0; "wiasWritePropLong failed, GetItemPropSt"...
0x18001796b  call    WiaTrace_TraceLog
0x180017970  mov     rdx, rax; char *
0x180017973  mov     rcx, r13; char *
0x180017976  mov     rbx, rax
0x180017979  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001797e  mov     rcx, rbx; this
0x180017981  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180017986  mov     edx, edi
0x180017988  lea     rcx, aWiaswritepropl_0; "wiasWritePropLong failed, GetItemPropSt"...
0x18001798f  call    WiaTrace_Trace
0x180017994  jmp     short loc_180017939
0x180017996  mov     rdx, [rbp+57h+arg_0]; struct IPropertyStorage *
0x18001799a  mov     r8d, esi; int
0x18001799d  mov     ecx, r12d; unsigned int
0x1800179a0  call    ?WritePropLong@@YAJKPEAUIPropertyStorage@@J@Z; WritePropLong(ulong,IPropertyStorage *,long)
0x1800179a5  mov     rcx, r15; this
0x1800179a8  call    ?IsCompatMode@CWiaItem@@QEBAHXZ; CWiaItem::IsCompatMode(void)
0x1800179ad  test    eax, eax
0x1800179af  jz      loc_180017B38
0x1800179b5  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x1800179b9  mov     [rbp+57h+arg_18], rbx
0x1800179bd  lea     r8, [rbp+57h+arg_18]; struct CWiaItem **
0x1800179c1  mov     [rbp+57h+var_80], rbx
0x1800179c5  mov     edx, r12d; unsigned int
0x1800179c8  mov     dword ptr [rbp+57h+arg_0], ebx
0x1800179cb  call    ?_FindRelatedAAITItem@@YAJPEAVCWiaItem@@KPEAPEAV1@PEAK@Z; _FindRelatedAAITItem(CWiaItem *,ulong,CWiaItem * *,ulong *)
0x1800179d0  mov     edi, eax
0x1800179d2  cmp     eax, 1
0x1800179d5  jnz     short loc_1800179DE
0x1800179d7  mov     edi, ebx
0x1800179d9  jmp     loc_180017B38
0x1800179de  test    eax, eax
0x1800179e0  jnz     loc_180017B38
0x1800179e6  mov     rcx, [rbp+57h+arg_18]; this
0x1800179ea  lea     rdx, [rbp+57h+var_80]; struct IPropertyStorage **
0x1800179ee  xor     r9d, r9d; struct IPropertyStorage **
0x1800179f1  mov     [rsp+0B0h+lpMem], rbx; struct IPropertyStorage **
0x1800179f6  xor     r8d, r8d; struct IPropertyStorage **
0x1800179f9  call    ?GetItemPropStreams@CWiaItem@@QEAAJPEAPEAUIPropertyStorage@@000@Z; CWiaItem::GetItemPropStreams(IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *)
0x1800179fe  mov     r13, [rbp+57h+var_80]
0x180017a02  mov     edi, eax
0x180017a04  test    r13, r13
0x180017a07  jnz     short loc_180017A5B
0x180017a09  test    eax, eax
0x180017a0b  js      short loc_180017A5F
0x180017a0d  lea     rcx, aWiaswritepropl_5; "wiasWritePropLong failed, GetItemPropSt"...
0x180017a14  mov     edi, 80004003h
0x180017a19  call    WiaTrace_TraceLog
0x180017a1e  mov     rdx, rax; char *
0x180017a21  lea     rcx, aWiaswritepropl_6; "wiasWritePropLong"
0x180017a28  mov     rbx, rax
0x180017a2b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180017a30  mov     rcx, rbx; this
0x180017a33  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180017a38  lea     rcx, aWiaswritepropl_5; "wiasWritePropLong failed, GetItemPropSt"...
0x180017a3f  call    WiaTrace_Trace
0x180017a44  lea     r9d, [r13+1]; int
0x180017a48  mov     [rsp+0B0h+lpMem], rax; lpMem
0x180017a4d  lea     r8, aWiaswritepropl_6; "wiasWritePropLong"
0x180017a54  call    WiaTrace_ProcessTrace_Ex
0x180017a59  jmp     short loc_180017A5F
0x180017a5b  test    eax, eax
0x180017a5d  jns     short loc_180017AB4
0x180017a5f  mov     edx, edi
0x180017a61  lea     rcx, aWiaswritepropl_2; "wiasWritePropLong failed, GetItemPropSt"...
0x180017a68  call    WiaTrace_TraceLog
0x180017a6d  mov     rdx, rax; char *
0x180017a70  lea     rcx, aWiaswritepropl_6; "wiasWritePropLong"
0x180017a77  mov     rbx, rax
0x180017a7a  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180017a7f  mov     rcx, rbx; this
0x180017a82  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180017a87  mov     edx, edi
0x180017a89  lea     rcx, aWiaswritepropl_2; "wiasWritePropLong failed, GetItemPropSt"...
0x180017a90  call    WiaTrace_Trace
0x180017a95  mov     r9d, 1; int
0x180017a9b  mov     [rsp+0B0h+lpMem], rax; lpMem
0x180017aa0  lea     r8, aWiaswritepropl_6; "wiasWritePropLong"
0x180017aa7  call    WiaTrace_ProcessTrace_Ex
0x180017aac  test    edi, edi
0x180017aae  js      loc_180017B38
0x180017ab4  cmp     r12d, 100Ch
0x180017abb  jnz     short loc_180017AD7
0x180017abd  mov     rcx, r15; this
0x180017ac0  call    ?IsLegacyDriver@CWiaItem@@QEAAHXZ; CWiaItem::IsLegacyDriver(void)
0x180017ac5  test    eax, eax
0x180017ac7  jz      short loc_180017AD7
0x180017ac9  cmp     esi, 80h
0x180017acf  mov     eax, 2
0x180017ad4  cmovz   esi, eax
0x180017ad7  mov     ecx, dword ptr [rbp+57h+arg_0]; unsigned int
0x180017ada  mov     r8d, esi; int
0x180017add  mov     rdx, r13; struct IPropertyStorage *
0x180017ae0  call    ?WritePropLong@@YAJKPEAUIPropertyStorage@@J@Z; WritePropLong(ulong,IPropertyStorage *,long)
0x180017ae5  mov     edi, eax
0x180017ae7  test    eax, eax
0x180017ae9  jns     short loc_180017B38
0x180017aeb  mov     edx, eax
0x180017aed  lea     rcx, aWiaswritepropl_3; "wiasWritePropLong, error writing new va"...
0x180017af4  call    WiaTrace_TraceLog
0x180017af9  mov     rdx, rax; char *
0x180017afc  lea     rcx, aWiaswritepropl_6; "wiasWritePropLong"
0x180017b03  mov     rbx, rax
0x180017b06  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180017b0b  mov     rcx, rbx; this
0x180017b0e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180017b13  mov     edx, edi
0x180017b15  lea     rcx, aWiaswritepropl_3; "wiasWritePropLong, error writing new va"...
0x180017b1c  call    WiaTrace_Trace
0x180017b21  lea     r8, aWiaswritepropl_6; "wiasWritePropLong"
0x180017b28  mov     r9d, 1; int
0x180017b2e  mov     [rsp+0B0h+lpMem], rax; lpMem
0x180017b33  call    WiaTrace_ProcessTrace_Ex
0x180017b38  lea     rcx, [rbp+57h+var_70]; this
0x180017b3c  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180017b41  lea     r11, [rsp+0B0h+var_20]
0x180017b49  mov     eax, edi
0x180017b4b  mov     rbx, [r11+38h]
0x180017b4f  mov     rsi, [r11+40h]
0x180017b53  mov     rsp, r11
0x180017b56  pop     r15
0x180017b58  pop     r13
0x180017b5a  pop     r12
0x180017b5c  pop     rdi
0x180017b5d  pop     rbp
0x180017b5e  retn
```
