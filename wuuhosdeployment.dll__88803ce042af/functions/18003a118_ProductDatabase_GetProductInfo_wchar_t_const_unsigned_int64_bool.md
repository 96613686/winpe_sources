# ProductDatabase::GetProductInfo(wchar_t const *,unsigned __int64 *,bool *)

- ea: `0x18003a118`
- end: `0x18003a222`
- name: `?GetProductInfo@ProductDatabase@@YAJPEB_WPEA_KPEA_N@Z`
- size: `266`
- prototype: `int(ProductDatabase *__hidden this, const wchar_t *, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003a228`

## callees

- `0x180003950`
- `0x1800265dc`
- `0x180031d8c`
- `0x18003a118`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a200`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a200`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProductDatabase::GetProductInfo(ProductDatabase *this, wchar_t *a2, unsigned __int64 *a3, bool *a4)
{
  int v7; // ebx
  __int64 v8; // rdx
  int WUSystemInterface; // eax
  __int64 v10; // rdx
  unsigned __int64 v11; // r9
  int v12; // r8d
  void *v13; // rcx
  int v15; // [rsp+20h] [rbp-38h]
  LPVOID pv; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  pv = 0;
  if ( !a2 )
  {
    v7 = -2147467261;
    v8 = 152;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\productdb\\ProductDB.cpp",
      (const char *)(unsigned int)v7,
      v15);
    v13 = pv;
    goto LABEL_14;
  }
  *(_QWORD *)a2 = 0;
  WUSystemInterface = WUSystemInterfaceHelper::LoadWUSystemInterface(this);
  v7 = WUSystemInterface;
  if ( WUSystemInterface < 0 )
  {
    v10 = 277;
    v11 = (unsigned int)WUSystemInterface;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusyshelper\\wusyshelper.cpp",
      (const char *)v11,
      v15);
    v8 = 156;
    goto LABEL_11;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, ProductDatabase *, LPVOID *, unsigned __int64 *))(*(_QWORD *)g_WUSystemInterface
                                                                                           + 208LL))(
         g_WUSystemInterface,
         this,
         &pv,
         a3);
  v11 = (unsigned int)v7;
  if ( v7 < 0 )
  {
    v10 = 278;
    goto LABEL_7;
  }
  v13 = pv;
  if ( pv )
  {
    v7 = ConvertStringVerToFileVerW((const wchar_t *)pv, (unsigned __int64 *)a2, v12, v7);
    if ( v7 < 0 )
    {
      v8 = 160;
      goto LABEL_11;
    }
    v13 = pv;
  }
  v7 = 0;
LABEL_14:
  if ( v13 )
    CoTaskMemFree(v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003a118  mov     [rsp+arg_18], rbx
0x18003a11d  push    rbp
0x18003a11e  push    rsi
0x18003a11f  push    rdi
0x18003a120  sub     rsp, 40h
0x18003a124  mov     rax, cs:__security_cookie
0x18003a12b  xor     rax, rsp
0x18003a12e  mov     [rsp+58h+var_20], rax
0x18003a133  mov     rbp, r8
0x18003a136  mov     rdi, rdx
0x18003a139  mov     rsi, rcx
0x18003a13c  mov     [rsp+58h+pv], 0
0x18003a145  test    rdx, rdx
0x18003a148  jnz     short loc_18003A159
0x18003a14a  mov     ebx, 80004003h
0x18003a14f  mov     edx, 98h
0x18003a154  jmp     loc_18003A1D9
0x18003a159  mov     qword ptr [rdx], 0
0x18003a160  call    ?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ; WUSystemInterfaceHelper::LoadWUSystemInterface(void)
0x18003a165  mov     ebx, eax
0x18003a167  test    eax, eax
0x18003a169  jns     short loc_18003A175
0x18003a16b  mov     edx, 115h
0x18003a170  mov     r9d, eax
0x18003a173  jmp     short loc_18003A1A4
0x18003a175  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18003a17c  mov     rax, [rcx]
0x18003a17f  mov     r9, rbp
0x18003a182  lea     r8, [rsp+58h+pv]
0x18003a187  mov     rdx, rsi
0x18003a18a  mov     rax, [rax+0D0h]
0x18003a191  call    _guard_dispatch_icall
0x18003a196  mov     ebx, eax
0x18003a198  mov     r9d, eax; wchar_t
0x18003a19b  test    eax, eax
0x18003a19d  jns     short loc_18003A1BC
0x18003a19f  mov     edx, 116h; void *
0x18003a1a4  lea     r8, aCW1SSrcClientL_11; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x18003a1ab  mov     rcx, [rsp+58h]; this
0x18003a1b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a1b5  mov     edx, 9Ch
0x18003a1ba  jmp     short loc_18003A1D9
0x18003a1bc  mov     rcx, [rsp+58h+pv]; wchar_t *
0x18003a1c1  test    rcx, rcx
0x18003a1c4  jz      short loc_18003A1F9
0x18003a1c6  mov     rdx, rdi; unsigned __int64 *
0x18003a1c9  call    ?ConvertStringVerToFileVerW@@YAJPEB_WPEA_KH_W@Z; ConvertStringVerToFileVerW(wchar_t const *,unsigned __int64 *,int,wchar_t)
0x18003a1ce  mov     ebx, eax
0x18003a1d0  test    eax, eax
0x18003a1d2  jns     short loc_18003A1F4
0x18003a1d4  mov     edx, 0A0h; void *
0x18003a1d9  mov     rcx, [rsp+58h]; this
0x18003a1de  mov     r9d, ebx; char *
0x18003a1e1  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\produc"...
0x18003a1e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a1ed  mov     rcx, [rsp+58h+pv]
0x18003a1f2  jmp     short loc_18003A1FB
0x18003a1f4  mov     rcx, [rsp+58h+pv]; pv
0x18003a1f9  xor     ebx, ebx
0x18003a1fb  test    rcx, rcx
0x18003a1fe  jz      short loc_18003A206
0x18003a200  call    cs:__imp_CoTaskMemFree
0x18003a206  mov     eax, ebx
0x18003a208  mov     rcx, [rsp+58h+var_20]
0x18003a20d  xor     rcx, rsp; StackCookie
0x18003a210  call    __security_check_cookie
0x18003a215  mov     rbx, [rsp+58h+arg_18]
0x18003a21a  add     rsp, 40h
0x18003a21e  pop     rdi
0x18003a21f  pop     rsi
0x18003a220  pop     rbp
0x18003a221  retn
```
