# CWiaItem::DeviceCommand(long,_GUID const *,IWiaItem2 * *)

- ea: `0x180061400`
- end: `0x180061569`
- name: `?DeviceCommand@CWiaItem@@UEAAJJPEBU_GUID@@PEAPEAUIWiaItem2@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(CWiaItem *this, unsigned int, const struct _GUID *, struct IWiaItem2 **)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002de18`
- `0x18002def8`
- `0x180030060`
- `0x180061118`
- `0x180061400`
- `0x180078010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006153f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006153f`

## string_xrefs

- `0x18006142d`: `CWiaItem::DeviceCommand`
- `0x18006145e`: `CWiaItem::DeviceCommand`
- `0x18006148a`: `CWiaItem::DeviceCommand`
- `0x18006144f`: `bad plCommand`
- `0x180061475`: `bad plCommand`
- `0x18006141b`: `CWiaItem::IWiaItem2::DeviceCommand`

## pseudocode

```c
__int64 __fastcall CWiaItem::DeviceCommand(
        CWiaItem *this,
        unsigned int a2,
        const struct _GUID *a3,
        struct IWiaItem2 **a4)
{
  char ***v8; // rax
  char *v9; // rdx
  __int64 v10; // r8
  int v11; // ebx
  char *v12; // rbx
  void *v13; // rdx
  void **v14; // rax
  void *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdi
  struct IWiaDrvItem *v19; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-88h]
  struct IWiaDrvItem *v22; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v23[80]; // [rsp+40h] [rbp-68h] BYREF
  BSTR bstrString; // [rsp+B0h] [rbp+8h] BYREF

  v8 = (char ***)WiaTrace_Trace("CWiaItem::IWiaItem2::DeviceCommand");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v23, v9, v10, (char **)"CWiaItem::DeviceCommand", lpMem, v8);
  v11 = 0;
  v22 = 0;
  if ( !a3 )
  {
    v12 = (char *)WiaTrace_TraceLog("bad plCommand");
    WriteDbgTraceErrorWI("CWiaItem::DeviceCommand", v12);
    WiaTrcLib::Free((WiaTrcLib *)v12, v13);
    v14 = (void **)WiaTrace_Trace("bad plCommand");
    WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"CWiaItem::DeviceCommand", 1, v14);
    v11 = -2147467261;
  }
  if ( !(unsigned int)CWiaItem::IsCompatMode((CWiaItem *)((char *)this - 56))
    || (v18 = *(_QWORD *)(*((_QWORD *)this + 19) + 64LL)) == 0 )
  {
    v18 = v17;
  }
  if ( v11 >= 0 )
  {
    v11 = CWiaItem::DeviceCommand((struct CWiaDrvItem **)v18, a2, a3, &v22);
    if ( v11 >= 0 )
    {
      v19 = v22;
      if ( v22 )
      {
        if ( a4 )
        {
          bstrString = 0;
          *a4 = 0;
          v11 = (*(__int64 (__fastcall **)(struct IWiaDrvItem *, BSTR *))(*(_QWORD *)v19 + 40LL))(v19, &bstrString);
          if ( v11 >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR, struct IWiaItem2 **))(*(_QWORD *)(v18 + 56) + 48LL))(
                    v18 + 56,
                    0,
                    bstrString,
                    a4);
            SysFreeString(bstrString);
          }
        }
      }
    }
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v23);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180061400  mov     [rsp+arg_8], rbx
0x180061405  mov     [rsp+arg_10], rbp
0x18006140a  push    rsi
0x18006140b  push    rdi
0x18006140c  push    r14
0x18006140e  sub     rsp, 90h
0x180061415  mov     rdi, rcx
0x180061418  mov     rsi, r9
0x18006141b  lea     rcx, aCwiaitemIwiait_9; "CWiaItem::IWiaItem2::DeviceCommand"
0x180061422  mov     rbp, r8
0x180061425  mov     r14d, edx
0x180061428  call    WiaTrace_Trace
0x18006142d  lea     r9, aCwiaitemDevice_0; "CWiaItem::DeviceCommand"
0x180061434  mov     [rsp+0A8h+var_80], rax; struct tagWiaTraceData_Type *
0x180061439  lea     rcx, [rsp+0A8h+var_68]; this
0x18006143e  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180061443  xor     ebx, ebx
0x180061445  mov     [rsp+0A8h+var_78], rbx
0x18006144a  test    rbp, rbp
0x18006144d  jnz     short loc_18006149B
0x18006144f  lea     rcx, aBadPlcommand; "bad plCommand"
0x180061456  call    WiaTrace_TraceLog
0x18006145b  mov     rdx, rax; char *
0x18006145e  lea     rcx, aCwiaitemDevice_0; "CWiaItem::DeviceCommand"
0x180061465  mov     rbx, rax
0x180061468  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006146d  mov     rcx, rbx; this
0x180061470  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180061475  lea     rcx, aBadPlcommand; "bad plCommand"
0x18006147c  call    WiaTrace_Trace
0x180061481  lea     r9d, [rbp+1]; int
0x180061485  mov     [rsp+0A8h+lpMem], rax; lpMem
0x18006148a  lea     r8, aCwiaitemDevice_0; "CWiaItem::DeviceCommand"
0x180061491  call    WiaTrace_ProcessTrace_Ex
0x180061496  mov     ebx, 80004003h
0x18006149b  lea     rcx, [rdi-38h]; this
0x18006149f  call    ?IsCompatMode@CWiaItem@@QEBAHXZ; CWiaItem::IsCompatMode(void)
0x1800614a4  test    eax, eax
0x1800614a6  jz      short loc_1800614B8
0x1800614a8  mov     rax, [rdi+98h]
0x1800614af  mov     rdi, [rax+40h]
0x1800614b3  test    rdi, rdi
0x1800614b6  jnz     short loc_1800614BB
0x1800614b8  mov     rdi, rcx
0x1800614bb  test    ebx, ebx
0x1800614bd  js      loc_180061545
0x1800614c3  lea     r9, [rsp+0A8h+var_78]; struct IWiaDrvItem **
0x1800614c8  mov     r8, rbp; struct _GUID *
0x1800614cb  mov     edx, r14d; int
0x1800614ce  mov     rcx, rdi; this
0x1800614d1  call    ?DeviceCommand@CWiaItem@@AEAAJJPEBU_GUID@@PEAPEAUIWiaDrvItem@@@Z; CWiaItem::DeviceCommand(long,_GUID const *,IWiaDrvItem * *)
0x1800614d6  mov     ebx, eax
0x1800614d8  test    eax, eax
0x1800614da  js      short loc_180061545
0x1800614dc  mov     rcx, [rsp+0A8h+var_78]
0x1800614e1  test    rcx, rcx
0x1800614e4  jz      short loc_180061545
0x1800614e6  test    rsi, rsi
0x1800614e9  jz      short loc_180061545
0x1800614eb  mov     [rsp+0A8h+bstrString], 0
0x1800614f7  lea     rdx, [rsp+0A8h+bstrString]
0x1800614ff  mov     qword ptr [rsi], 0
0x180061506  mov     rax, [rcx]
0x180061509  mov     rax, [rax+28h]
0x18006150d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061512  mov     ebx, eax
0x180061514  test    eax, eax
0x180061516  js      short loc_180061545
0x180061518  mov     r8, [rsp+0A8h+bstrString]
0x180061520  lea     rcx, [rdi+38h]
0x180061524  mov     rax, [rcx]
0x180061527  mov     r9, rsi
0x18006152a  xor     edx, edx
0x18006152c  mov     rax, [rax+30h]
0x180061530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061535  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x18006153d  mov     ebx, eax
0x18006153f  call    cs:__imp_SysFreeString
0x180061545  lea     rcx, [rsp+0A8h+var_68]; this
0x18006154a  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18006154f  lea     r11, [rsp+0A8h+var_18]
0x180061557  mov     eax, ebx
0x180061559  mov     rbx, [r11+28h]
0x18006155d  mov     rbp, [r11+30h]
0x180061561  mov     rsp, r11
0x180061564  pop     r14
0x180061566  pop     rdi
0x180061567  pop     rsi
0x180061568  retn
```
