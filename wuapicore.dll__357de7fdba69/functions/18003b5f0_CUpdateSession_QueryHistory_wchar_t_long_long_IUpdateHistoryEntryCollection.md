# CUpdateSession::QueryHistory(wchar_t *,long,long,IUpdateHistoryEntryCollection * *)

- ea: `0x18003b5f0`
- end: `0x18003b812`
- name: `?QueryHistory@CUpdateSession@@UEAAJPEA_WJJPEAPEAUIUpdateHistoryEntryCollection@@@Z`
- size: `546`
- prototype: `int(CUpdateSession *__hidden this, wchar_t *, int, int, struct IUpdateHistoryEntryCollection **)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800054bc`
- `0x180006ac4`
- `0x18000725c`
- `0x18003b5f0`
- `0x18003c8f0`
- `0x180041808`
- `0x180047554`
- `0x18006850c`
- `0x180097968`
- `0x18009ae75`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b6b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b7b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b7cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b6b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b7b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b7cd`
- `OLEAUT32!__imp_SysStringLen` at `0x18003b6bd`
- `OLEAUT32!__imp_SysStringLen` at `0x18003b6bd`

## string_xrefs

- `0x18003b76c`: `C:\__w\1\s\src\Client\comapi\Session.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CUpdateSession::QueryHistory(
        CUpdateSession *this,
        wchar_t *a2,
        signed int a3,
        signed int a4,
        struct IUpdateHistoryEntryCollection **a5)
{
  CUpdateHistoryEntryCollection *v8; // rbx
  int v9; // edi
  __int64 v10; // rdx
  CUpdateHistoryEntryCollection *v11; // rax
  struct tagDSHistoryEvent_V3 *v12; // rsi
  int v14; // [rsp+20h] [rbp-E0h]
  CUpdateHistoryEntryCollection *v15; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v16; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[192]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v8 = 0;
  v15 = 0;
  pv = 0;
  v16 = 0;
  memset_0(v18, 0, 0xB8u);
  CSusInternalWrapper::CSusInternalWrapper((CSusInternalWrapper *)v18);
  if ( !a5 )
  {
    v9 = -2147467261;
    v10 = 354;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
      (const char *)(unsigned int)v9,
      v14);
    goto LABEL_24;
  }
  *a5 = 0;
  if ( a3 < 0 )
  {
    v9 = -2145124345;
    v10 = 358;
    goto LABEL_22;
  }
  if ( a4 <= 0 )
  {
    v9 = -2145124345;
    v10 = 359;
    goto LABEL_22;
  }
  v9 = CSusInternalWrapper::Initialize((CSusInternalWrapper *)v18);
  if ( v9 < 0 )
  {
    v10 = 360;
    goto LABEL_22;
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( !SysStringLen(a2) )
    a2 = (wchar_t *)&c_wszEmpty;
  v9 = CSusInternalWrapper::QueryHistoryEx(
         (CSusInternalWrapper *)v18,
         a2,
         a3,
         a4,
         &v16,
         (struct tagDSHistoryEvent_V3 **)&pv);
  if ( v9 < 0 )
  {
    v10 = 367;
    goto LABEL_22;
  }
  if ( v16 && !pv )
  {
    v9 = -2145120257;
    v10 = 369;
    goto LABEL_22;
  }
  v9 = ATL::CComObject<CUpdateHistoryEntryCollection>::CreateInstance(&v15);
  v8 = v15;
  if ( v9 < 0 )
  {
    v10 = 371;
    goto LABEL_22;
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)v15 + 1) + 8LL))((char *)v15 + 8);
  v9 = CUpdateHistoryEntryCollection::Initialize(v8, v16, (struct tagDSHistoryEvent_V3 *)pv);
  if ( v9 < 0 )
  {
    v10 = 375;
    goto LABEL_22;
  }
  v11 = v8;
  v8 = 0;
  *a5 = (struct IUpdateHistoryEntryCollection *)(((unsigned __int64)v11 + 8) & -(__int64)(v11 != 0));
  v9 = 0;
LABEL_24:
  v12 = (struct tagDSHistoryEvent_V3 *)pv;
  pv = 0;
  if ( v12 )
  {
    DsqFreeObject(v12, v16);
    CoTaskMemFree(v12);
  }
  CSusInternalWrapper::~CSusInternalWrapper((CSusInternalWrapper *)v18);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v8 + 1) + 16LL))((__int64)v8 + 8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003b5f0  push    rbp
0x18003b5f2  push    rbx
0x18003b5f3  push    rsi
0x18003b5f4  push    rdi
0x18003b5f5  push    r12
0x18003b5f7  push    r14
0x18003b5f9  push    r15
0x18003b5fb  lea     rbp, [rsp-20h]
0x18003b600  sub     rsp, 120h
0x18003b607  mov     rax, cs:__security_cookie
0x18003b60e  xor     rax, rsp
0x18003b611  mov     [rbp+50h+var_40], rax
0x18003b615  mov     r15d, r9d
0x18003b618  mov     r14d, r8d
0x18003b61b  mov     r12, rdx
0x18003b61e  mov     rsi, [rbp+50h+arg_20]
0x18003b625  xor     ebx, ebx
0x18003b627  mov     [rsp+150h+var_120], rbx
0x18003b62c  mov     [rsp+150h+pv], rbx
0x18003b631  mov     [rsp+150h+var_118], ebx
0x18003b635  xor     edx, edx; Val
0x18003b637  mov     r8d, 0B8h; Size
0x18003b63d  lea     rcx, [rsp+150h+var_100]; void *
0x18003b642  call    memset_0
0x18003b647  lea     rcx, [rsp+150h+var_100]; this
0x18003b64c  call    ??0CSusInternalWrapper@@QEAA@XZ; CSusInternalWrapper::CSusInternalWrapper(void)
0x18003b651  test    rsi, rsi
0x18003b654  jnz     short loc_18003B665
0x18003b656  mov     edi, 80004003h
0x18003b65b  mov     edx, 162h
0x18003b660  jmp     loc_18003B765
0x18003b665  mov     [rsi], rbx
0x18003b668  test    r14d, r14d
0x18003b66b  jns     short loc_18003B67C
0x18003b66d  mov     edi, 80240007h
0x18003b672  mov     edx, 166h
0x18003b677  jmp     loc_18003B765
0x18003b67c  test    r15d, r15d
0x18003b67f  jg      short loc_18003B690
0x18003b681  mov     edi, 80240007h
0x18003b686  mov     edx, 167h
0x18003b68b  jmp     loc_18003B765
0x18003b690  lea     rcx, [rsp+150h+var_100]; this
0x18003b695  call    ?Initialize@CSusInternalWrapper@@QEAAJXZ; CSusInternalWrapper::Initialize(void)
0x18003b69a  mov     edi, eax
0x18003b69c  test    eax, eax
0x18003b69e  jns     short loc_18003B6AA
0x18003b6a0  mov     edx, 168h
0x18003b6a5  jmp     loc_18003B765
0x18003b6aa  mov     rcx, [rsp+150h+pv]; pv
0x18003b6af  test    rcx, rcx
0x18003b6b2  jz      short loc_18003B6BA
0x18003b6b4  call    cs:__imp_CoTaskMemFree
0x18003b6ba  mov     rcx, r12; pbstr
0x18003b6bd  call    cs:__imp_SysStringLen
0x18003b6c3  lea     rcx, ?c_wszEmpty@@3QB_WB; wchar_t const near * const c_wszEmpty
0x18003b6ca  test    eax, eax
0x18003b6cc  cmovz   r12, rcx
0x18003b6d0  lea     rax, [rsp+150h+pv]
0x18003b6d5  mov     [rsp+150h+var_128], rax; struct tagDSHistoryEvent_V3 **
0x18003b6da  lea     rax, [rsp+150h+var_118]
0x18003b6df  mov     [rsp+150h+var_130], rax; int
0x18003b6e4  mov     r9d, r15d; unsigned int
0x18003b6e7  mov     r8d, r14d; unsigned int
0x18003b6ea  mov     rdx, r12; wchar_t *
0x18003b6ed  lea     rcx, [rsp+150h+var_100]; this
0x18003b6f2  call    ?QueryHistoryEx@CSusInternalWrapper@@QEAAJPEB_WKKPEAKPEAPEAUtagDSHistoryEvent_V3@@@Z; CSusInternalWrapper::QueryHistoryEx(wchar_t const *,ulong,ulong,ulong *,tagDSHistoryEvent_V3 * *)
0x18003b6f7  mov     edi, eax
0x18003b6f9  test    eax, eax
0x18003b6fb  jns     short loc_18003B704
0x18003b6fd  mov     edx, 16Fh
0x18003b702  jmp     short loc_18003B765
0x18003b704  cmp     [rsp+150h+var_118], ebx
0x18003b708  jbe     short loc_18003B71D
0x18003b70a  cmp     [rsp+150h+pv], rbx
0x18003b70f  jnz     short loc_18003B71D
0x18003b711  mov     edi, 80240FFFh
0x18003b716  mov     edx, 171h
0x18003b71b  jmp     short loc_18003B765
0x18003b71d  lea     rcx, [rsp+150h+var_120]
0x18003b722  call    ?CreateInstance@?$CComObject@VCUpdateHistoryEntryCollection@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CUpdateHistoryEntryCollection>::CreateInstance(ATL::CComObject<CUpdateHistoryEntryCollection> * *)
0x18003b727  mov     edi, eax
0x18003b729  mov     rbx, [rsp+150h+var_120]
0x18003b72e  test    eax, eax
0x18003b730  jns     short loc_18003B739
0x18003b732  mov     edx, 173h
0x18003b737  jmp     short loc_18003B765
0x18003b739  lea     rcx, [rbx+8]
0x18003b73d  mov     rax, [rcx]
0x18003b740  mov     rax, [rax+8]
0x18003b744  call    _guard_dispatch_icall
0x18003b749  mov     r8, [rsp+150h+pv]; struct tagDSHistoryEvent_V3 *
0x18003b74e  mov     edx, [rsp+150h+var_118]; unsigned int
0x18003b752  mov     rcx, rbx; this
0x18003b755  call    ?Initialize@CUpdateHistoryEntryCollection@@AEAAJKPEAUtagDSHistoryEvent_V3@@@Z; CUpdateHistoryEntryCollection::Initialize(ulong,tagDSHistoryEvent_V3 *)
0x18003b75a  mov     edi, eax
0x18003b75c  test    eax, eax
0x18003b75e  jns     short loc_18003B77A
0x18003b760  mov     edx, 177h; void *
0x18003b765  mov     rcx, [rbp+58h]; this
0x18003b769  mov     r9d, edi; char *
0x18003b76c  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003b773  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b778  jmp     short loc_18003B791
0x18003b77a  mov     rax, rbx
0x18003b77d  xor     ebx, ebx
0x18003b77f  lea     rcx, [rax+8]
0x18003b783  neg     rax
0x18003b786  sbb     rax, rax
0x18003b789  and     rax, rcx
0x18003b78c  mov     [rsi], rax
0x18003b78f  xor     edi, edi
0x18003b791  mov     rsi, [rsp+150h+pv]
0x18003b796  mov     [rsp+150h+pv], 0
0x18003b79f  test    rsi, rsi
0x18003b7a2  jz      short loc_18003B7B9
0x18003b7a4  mov     edx, [rsp+150h+var_118]; unsigned int
0x18003b7a8  mov     rcx, rsi; struct tagDSHistoryEvent_V3 *
0x18003b7ab  call    ?DsqFreeObject@@YAXPEAUtagDSHistoryEvent_V3@@K@Z; DsqFreeObject(tagDSHistoryEvent_V3 *,ulong)
0x18003b7b0  mov     rcx, rsi; pv
0x18003b7b3  call    cs:__imp_CoTaskMemFree
0x18003b7b9  lea     rcx, [rsp+150h+var_100]; this
0x18003b7be  call    ??1CSusInternalWrapper@@UEAA@XZ; CSusInternalWrapper::~CSusInternalWrapper(void)
0x18003b7c3  mov     rcx, [rsp+150h+pv]; pv
0x18003b7c8  test    rcx, rcx
0x18003b7cb  jz      short loc_18003B7DC
0x18003b7cd  call    cs:__imp_CoTaskMemFree
0x18003b7d3  mov     [rsp+150h+pv], 0
0x18003b7dc  test    rbx, rbx
0x18003b7df  jz      short loc_18003B7F2
0x18003b7e1  lea     rcx, [rbx+8]
0x18003b7e5  mov     rdx, [rcx]
0x18003b7e8  mov     rax, [rdx+10h]
0x18003b7ec  call    _guard_dispatch_icall
0x18003b7f1  nop
0x18003b7f2  mov     eax, edi
0x18003b7f4  mov     rcx, [rbp+50h+var_40]
0x18003b7f8  xor     rcx, rsp; StackCookie
0x18003b7fb  call    __security_check_cookie
0x18003b800  add     rsp, 120h
0x18003b807  pop     r15
0x18003b809  pop     r14
0x18003b80b  pop     r12
0x18003b80d  pop     rdi
0x18003b80e  pop     rsi
0x18003b80f  pop     rbx
0x18003b810  pop     rbp
0x18003b811  retn
```
