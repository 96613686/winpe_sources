# WdcDataCollectorSetNode::CreateDataSet(int *,IDataCollectorSet * *)

- ea: `0x18005606c`
- end: `0x18005626d`
- name: `?CreateDataSet@WdcDataCollectorSetNode@@AEAAJPEAHPEAPEAUIDataCollectorSet@@@Z`
- size: `513`
- prototype: `__int64 __fastcall(WdcDataCollectorSetNode *__hidden this, int *, struct IDataCollectorSet **)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800329f8`
- `0x1800571b4`
- `0x180058580`
- `0x180062c80`
- `0x180063b80`

## callees

- `0x18000b854`
- `0x18005606c`
- `0x180057760`
- `0x180058314`
- `0x180066e18`
- `0x180086010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180056254`
- `OLEAUT32!__imp_SysFreeString` at `0x180056254`
- `ole32!CoCreateInstance` at `0x1800560b5`
- `ole32!CoCreateInstance` at `0x1800560b5`

## string_xrefs

- `0x1800560f8`: `WdcDataCollectorSetNode::CreateDataSet`
- `0x1800561ff`: `WdcDataCollectorSetNode::CreateDataSet`

## pseudocode

```c
__int64 __fastcall WdcDataCollectorSetNode::CreateDataSet(
        WdcDataCollectorSetNode *this,
        int *a2,
        struct IDataCollectorSet **a3)
{
  OLECHAR *v3; // rdi
  HRESULT Instance; // eax
  unsigned int v8; // ebx
  int Name; // eax
  __int64 v10; // r8
  ULONG (__stdcall *Release)(IUnknown *); // rax
  LPVOID *ppv; // [rsp+20h] [rbp-20h]
  BSTR bstrString; // [rsp+30h] [rbp-10h] BYREF
  struct IUnknown *v15; // [rsp+78h] [rbp+38h] BYREF
  __int64 v16; // [rsp+88h] [rbp+48h] BYREF

  v3 = 0;
  *a2 = 0;
  bstrString = 0;
  v16 = 0;
  v15 = 0;
  Instance = CoCreateInstance(&CLSID_DataCollectorSet, 0, 0x15u, &IID_IDataCollectorSet, (LPVOID *)&v15);
  v8 = Instance;
  if ( Instance >= 0 )
  {
    Instance = WdcCoSetSecurity(v15);
    v8 = Instance;
    if ( Instance >= 0 )
    {
      Name = WdcDataCollectorSetNode::GetName(this, &bstrString);
      v8 = Name;
      if ( Name < 0 )
      {
        LODWORD(ppv) = Name;
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetnode.cpp",
          "WdcDataCollectorSetNode::CreateDataSet",
          0,
          L"FAILURE: 0x%08x",
          ppv);
        v3 = bstrString;
        goto LABEL_17;
      }
      v3 = bstrString;
      v10 = *((_QWORD *)this + 6);
      Release = v15->lpVtbl[19].Release;
      if ( (*((_BYTE *)this + 108) & 1) != 0 )
      {
        if ( ((int (__fastcall *)(struct IUnknown *, BSTR, __int64))Release)(v15, bstrString, v10) >= 0 )
        {
          WdcDataCollectorSetNode::Pause(this, 0);
        }
        else
        {
          Instance = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, __int64 *))v15->lpVtbl[21].AddRef)(
                       v15,
                       *((_QWORD *)this + 64),
                       &v16);
          v8 = Instance;
          if ( Instance < 0 )
            goto LABEL_16;
          if ( v16 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
            v16 = 0;
          }
          Instance = ((__int64 (__fastcall *)(struct IUnknown *, OLECHAR *, _QWORD, __int64, __int64 *))v15->lpVtbl[20].QueryInterface)(
                       v15,
                       v3,
                       *((_QWORD *)this + 6),
                       4096,
                       &v16);
          v8 = Instance;
          if ( Instance < 0 )
            goto LABEL_16;
        }
      }
      else if ( ((int (__fastcall *)(struct IUnknown *, BSTR, __int64))Release)(v15, bstrString, v10) >= 0 )
      {
        *a2 = 1;
      }
      Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IDataCollectorSet **))v15->lpVtbl->QueryInterface)(
                   v15,
                   &IID_IDataCollectorSet,
                   a3);
      v8 = Instance;
      if ( Instance >= 0 )
        goto LABEL_17;
    }
  }
LABEL_16:
  LODWORD(ppv) = Instance;
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetnode.cpp",
    "WdcDataCollectorSetNode::CreateDataSet",
    0,
    L"FAILURE: 0x%08x",
    ppv);
LABEL_17:
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v15 )
  {
    ((void (__fastcall *)(struct IUnknown *))v15->lpVtbl->Release)(v15);
    v15 = 0;
  }
  if ( v3 )
    SysFreeString(v3);
  return v8;
}

```

## disassembly

```asm
0x18005606c  mov     [rsp-28h+arg_0], rbx
0x180056071  push    rbp
0x180056072  push    rsi
0x180056073  push    rdi
0x180056074  push    r14
0x180056076  push    r15
0x180056078  mov     rbp, rsp
0x18005607b  sub     rsp, 40h
0x18005607f  xor     edi, edi
0x180056081  lea     rax, [rbp+arg_8]
0x180056085  mov     r15, r8
0x180056088  mov     [rdx], edi
0x18005608a  mov     r14, rdx
0x18005608d  mov     [rbp+bstrString], rdi
0x180056091  mov     rsi, rcx
0x180056094  mov     [rbp+arg_18], rdi
0x180056098  lea     r8d, [rdi+15h]; dwClsContext
0x18005609c  mov     [rbp+arg_8], rdi
0x1800560a0  lea     r9, IID_IDataCollectorSet; riid
0x1800560a7  mov     [rsp+40h+ppv], rax; ppv
0x1800560ac  xor     edx, edx; pUnkOuter
0x1800560ae  lea     rcx, CLSID_DataCollectorSet; rclsid
0x1800560b5  call    cs:__imp_CoCreateInstance
0x1800560bb  mov     ebx, eax
0x1800560bd  test    eax, eax
0x1800560bf  js      loc_1800561F1
0x1800560c5  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x1800560c9  call    ?WdcCoSetSecurity@@YAJPEAUIUnknown@@@Z; WdcCoSetSecurity(IUnknown *)
0x1800560ce  mov     ebx, eax
0x1800560d0  test    eax, eax
0x1800560d2  js      loc_1800561F1
0x1800560d8  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x1800560dc  mov     rcx, rsi; this
0x1800560df  call    ?GetName@WdcDataCollectorSetNode@@IEAAJPEAPEAG@Z; WdcDataCollectorSetNode::GetName(ushort * *)
0x1800560e4  mov     ebx, eax
0x1800560e6  test    eax, eax
0x1800560e8  jns     short loc_180056114
0x1800560ea  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800560f1  mov     dword ptr [rsp+40h+ppv], eax
0x1800560f5  xor     r8d, r8d; int
0x1800560f8  lea     rdx, aWdcdatacollect_56; "WdcDataCollectorSetNode::CreateDataSet"
0x1800560ff  lea     rcx, aBaseDiagnosisP_30; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x180056106  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18005610b  mov     rdi, [rbp+bstrString]
0x18005610f  jmp     loc_180056212
0x180056114  test    byte ptr [rsi+6Ch], 1
0x180056118  mov     rcx, [rbp+arg_8]
0x18005611c  mov     rdi, [rbp+bstrString]
0x180056120  mov     r8, [rsi+30h]
0x180056124  mov     rdx, rdi
0x180056127  mov     rax, [rcx]
0x18005612a  mov     rax, [rax+1D8h]
0x180056131  jz      loc_1800561C2
0x180056137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005613c  test    eax, eax
0x18005613e  jns     short loc_1800561B6
0x180056140  mov     rcx, [rbp+arg_8]
0x180056144  lea     r8, [rbp+arg_18]
0x180056148  mov     rdx, [rsi+200h]
0x18005614f  mov     rax, [rcx]
0x180056152  mov     rax, [rax+200h]
0x180056159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005615e  mov     ebx, eax
0x180056160  test    eax, eax
0x180056162  js      loc_1800561F1
0x180056168  mov     rcx, [rbp+arg_18]
0x18005616c  test    rcx, rcx
0x18005616f  jz      short loc_180056185
0x180056171  mov     rax, [rcx]
0x180056174  mov     rax, [rax+10h]
0x180056178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005617d  mov     [rbp+arg_18], 0
0x180056185  mov     rcx, [rbp+arg_8]
0x180056189  lea     rdx, [rbp+arg_18]
0x18005618d  mov     r8, [rsi+30h]
0x180056191  mov     r9d, 1000h
0x180056197  mov     [rsp+40h+ppv], rdx
0x18005619c  mov     rdx, rdi
0x18005619f  mov     rax, [rcx]
0x1800561a2  mov     rax, [rax+1E0h]
0x1800561a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561ae  mov     ebx, eax
0x1800561b0  test    eax, eax
0x1800561b2  jns     short loc_1800561D2
0x1800561b4  jmp     short loc_1800561F1
0x1800561b6  xor     edx, edx; int
0x1800561b8  mov     rcx, rsi; this
0x1800561bb  call    ?Pause@WdcDataCollectorSetNode@@QEAAJH@Z; WdcDataCollectorSetNode::Pause(int)
0x1800561c0  jmp     short loc_1800561D2
0x1800561c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561c7  test    eax, eax
0x1800561c9  js      short loc_1800561D2
0x1800561cb  mov     dword ptr [r14], 1
0x1800561d2  mov     rcx, [rbp+arg_8]
0x1800561d6  lea     rdx, IID_IDataCollectorSet
0x1800561dd  mov     r8, r15
0x1800561e0  mov     rax, [rcx]
0x1800561e3  mov     rax, [rax]
0x1800561e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561eb  mov     ebx, eax
0x1800561ed  test    eax, eax
0x1800561ef  jns     short loc_180056212
0x1800561f1  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800561f8  mov     dword ptr [rsp+40h+ppv], eax
0x1800561fc  xor     r8d, r8d; int
0x1800561ff  lea     rdx, aWdcdatacollect_56; "WdcDataCollectorSetNode::CreateDataSet"
0x180056206  lea     rcx, aBaseDiagnosisP_30; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x18005620d  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180056212  mov     rcx, [rbp+arg_18]
0x180056216  test    rcx, rcx
0x180056219  jz      short loc_18005622F
0x18005621b  mov     rax, [rcx]
0x18005621e  mov     rax, [rax+10h]
0x180056222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056227  mov     [rbp+arg_18], 0
0x18005622f  mov     rcx, [rbp+arg_8]
0x180056233  test    rcx, rcx
0x180056236  jz      short loc_18005624C
0x180056238  mov     rax, [rcx]
0x18005623b  mov     rax, [rax+10h]
0x18005623f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056244  mov     [rbp+arg_8], 0
0x18005624c  test    rdi, rdi
0x18005624f  jz      short loc_18005625A
0x180056251  mov     rcx, rdi; bstrString
0x180056254  call    cs:__imp_SysFreeString
0x18005625a  mov     eax, ebx
0x18005625c  mov     rbx, [rsp+40h+arg_0]
0x180056261  add     rsp, 40h
0x180056265  pop     r15
0x180056267  pop     r14
0x180056269  pop     rdi
0x18005626a  pop     rsi
0x18005626b  pop     rbp
0x18005626c  retn
```
