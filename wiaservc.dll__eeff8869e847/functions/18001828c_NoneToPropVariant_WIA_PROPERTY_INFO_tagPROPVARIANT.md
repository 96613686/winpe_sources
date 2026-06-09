# NoneToPropVariant(_WIA_PROPERTY_INFO *,tagPROPVARIANT *)

- ea: `0x18001828c`
- end: `0x180018380`
- name: `?NoneToPropVariant@@YAJPEAU_WIA_PROPERTY_INFO@@PEAUtagPROPVARIANT@@@Z`
- size: `244`
- prototype: `__int64 __fastcall(struct _WIA_PROPERTY_INFO *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018180`

## callees

- `0x18000b6a0`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18001828c`
- `0x18002e9d8`
- `0x18002eab4`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800182d9`
- `ole32!CoTaskMemAlloc` at `0x1800182d9`
- `RPCRT4!UuidCreateNil` at `0x1800182ed`
- `RPCRT4!UuidCreateNil` at `0x1800182ed`

## string_xrefs

- `0x18001832b`: `::NoneToPropVariant, UuidCreateNil returned 0x%08X`
- `0x180018356`: `::NoneToPropVariant, UuidCreateNil returned 0x%08X`

## pseudocode

```c
__int64 __fastcall NoneToPropVariant(struct _WIA_PROPERTY_INFO *a1, struct tagPROPVARIANT *a2)
{
  char ***v4; // rax
  char *v5; // rdx
  __int64 v6; // r8
  UUID *v7; // rax
  unsigned int v8; // edi
  RPC_STATUS Nil; // eax
  RPC_STATUS v10; // esi
  char *v12; // rbx
  void *v13; // rdx
  void **v14; // rax
  void *v15; // rdx
  __int64 v16; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-68h]
  _BYTE v18[80]; // [rsp+30h] [rbp-58h] BYREF

  v4 = (char ***)WiaTrace_Trace("::NoneToPropVariant");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v18, v5, v6, (char **)"NoneToPropVariant", lpMem, v4);
  a2->vt = *((_WORD *)a1 + 2);
  if ( *((_WORD *)a1 + 2) == 72 )
  {
    v7 = (UUID *)CoTaskMemAlloc(0x10u);
    v8 = 0;
    a2->hVal.QuadPart = (LONGLONG)v7;
    if ( v7 )
    {
      Nil = UuidCreateNil(v7);
      v10 = Nil;
      if ( Nil )
      {
        v12 = (char *)WiaTrace_TraceLogWithSubComp(0, "::NoneToPropVariant, UuidCreateNil returned 0x%08X", Nil);
        WriteDbgTraceWarningWI("NoneToPropVariant", v12);
        WiaTrcLib::Free((WiaTrcLib *)v12, v13);
        v14 = (void **)WiaTrace_TraceWithSubComp(0, "::NoneToPropVariant, UuidCreateNil returned 0x%08X", v10);
        WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"NoneToPropVariant", 2, v14);
      }
    }
    else
    {
      v8 = -2147024882;
    }
  }
  else
  {
    v8 = 0;
    a2->lVal = 0;
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v18);
  return v8;
}

```

## disassembly

```asm
0x18001828c  mov     [rsp+arg_0], rbx
0x180018291  mov     [rsp+arg_8], rsi
0x180018296  push    rdi
0x180018297  sub     rsp, 80h
0x18001829e  mov     rbx, rcx
0x1800182a1  mov     rsi, rdx
0x1800182a4  lea     rcx, aNonetopropvari_1; "::NoneToPropVariant"
0x1800182ab  call    WiaTrace_Trace
0x1800182b0  lea     r9, aNonetopropvari_0; "NoneToPropVariant"
0x1800182b7  mov     [rsp+88h+var_60], rax; struct tagWiaTraceData_Type *
0x1800182bc  lea     rcx, [rsp+88h+var_58]; this
0x1800182c1  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x1800182c6  movzx   eax, word ptr [rbx+4]
0x1800182ca  mov     [rsi], ax
0x1800182cd  cmp     word ptr [rbx+4], 48h ; 'H'
0x1800182d2  jnz     short loc_180018321
0x1800182d4  mov     ecx, 10h; cb
0x1800182d9  call    cs:__imp_CoTaskMemAlloc
0x1800182df  xor     edi, edi
0x1800182e1  mov     [rsi+8], rax
0x1800182e5  test    rax, rax
0x1800182e8  jz      short loc_18001831A
0x1800182ea  mov     rcx, rax; NilUuid
0x1800182ed  call    cs:__imp_UuidCreateNil
0x1800182f3  mov     esi, eax
0x1800182f5  test    eax, eax
0x1800182f7  jnz     short loc_180018328
0x1800182f9  lea     rcx, [rsp+88h+var_58]; this
0x1800182fe  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180018303  lea     r11, [rsp+88h+var_8]
0x18001830b  mov     eax, edi
0x18001830d  mov     rbx, [r11+10h]
0x180018311  mov     rsi, [r11+18h]
0x180018315  mov     rsp, r11
0x180018318  pop     rdi
0x180018319  retn
0x18001831a  mov     edi, 8007000Eh
0x18001831f  jmp     short loc_1800182F9
0x180018321  xor     edi, edi
0x180018323  mov     [rsi+8], edi
0x180018326  jmp     short loc_1800182F9
0x180018328  mov     r8d, esi
0x18001832b  lea     rdx, aNonetopropvari; "::NoneToPropVariant, UuidCreateNil retu"...
0x180018332  xor     ecx, ecx
0x180018334  call    WiaTrace_TraceLogWithSubComp
0x180018339  mov     rdx, rax; char *
0x18001833c  lea     rcx, aNonetopropvari_0; "NoneToPropVariant"
0x180018343  mov     rbx, rax
0x180018346  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18001834b  mov     rcx, rbx; this
0x18001834e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018353  mov     r8d, esi
0x180018356  lea     rdx, aNonetopropvari; "::NoneToPropVariant, UuidCreateNil retu"...
0x18001835d  xor     ecx, ecx
0x18001835f  call    WiaTrace_TraceWithSubComp
0x180018364  mov     r9d, 2; int
0x18001836a  mov     [rsp+88h+lpMem], rax; lpMem
0x18001836f  lea     r8, aNonetopropvari_0; "NoneToPropVariant"
0x180018376  call    WiaTrace_ProcessTrace_Ex
0x18001837b  jmp     loc_1800182F9
```
