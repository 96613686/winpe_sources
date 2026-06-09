# ScheduleDefault(ushort const *,ushort const *)

- ea: `0x180008c60`
- end: `0x180008ddb`
- name: `?ScheduleDefault@@YAJPEBG0@Z`
- size: `379`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180008a50`
- `0x180008ea0`

## callees

- `0x180008c60`
- `0x1800188d0`
- `0x18001cd88`
- `0x18002924e`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180008cd6`
- `ole32!CoCreateInstance` at `0x180008cd6`
- `ole32!CoUninitialize` at `0x180008cde`
- `ole32!CoUninitialize` at `0x180008cde`
- `ole32!CoInitialize` at `0x180008cab`
- `ole32!CoInitialize` at `0x180008cab`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d93`
- `OLEAUT32!__imp_SysFreeString` at `0x180008da1`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d93`
- `OLEAUT32!__imp_SysFreeString` at `0x180008da1`

## pseudocode

```c
HRESULT __fastcall ScheduleDefault(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HRESULT result; // eax
  HRESULT BSTRFromTSTR; // ebx
  OLECHAR *v6; // rdi
  HRESULT v7; // eax
  OLECHAR *v8; // rsi
  LPVOID ppv; // [rsp+40h] [rbp-59h] BYREF
  OLECHAR *v10; // [rsp+48h] [rbp-51h] BYREF
  BSTR bstrString[2]; // [rsp+50h] [rbp-49h] BYREF
  int v12; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v13[108]; // [rsp+64h] [rbp-35h] BYREF

  if ( !(unsigned int)IsHTTPPrefixed(a1) )
    return -2147024809;
  ppv = 0;
  result = CoInitialize(0);
  if ( result >= 0 )
  {
    BSTRFromTSTR = CoCreateInstance(&CLSID_SubscriptionMgr, 0, 1u, &IID_ISubscriptionMgr, &ppv);
    CoUninitialize();
    if ( BSTRFromTSTR < 0 )
      return BSTRFromTSTR;
    v6 = 0;
    bstrString[0] = 0;
    v10 = 0;
    BSTRFromTSTR = CreateBSTRFromTSTR(bstrString, a1);
    if ( !BSTRFromTSTR )
    {
      v7 = CreateBSTRFromTSTR(&v10, a2);
      v6 = v10;
      BSTRFromTSTR = v7;
    }
    memset_0(v13, 0, sizeof(v13));
    v8 = bstrString[0];
    v12 = 112;
    if ( !BSTRFromTSTR )
      BSTRFromTSTR = (*(__int64 (__fastcall **)(LPVOID, _QWORD, BSTR, OLECHAR *, int, _DWORD, int *))(*(_QWORD *)ppv + 80LL))(
                       ppv,
                       0,
                       bstrString[0],
                       v6,
                       4,
                       0,
                       &v12);
    if ( ppv )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      ppv = 0;
    }
    if ( v8 )
      SysFreeString(v8);
    if ( v6 )
      SysFreeString(v6);
    if ( BSTRFromTSTR < 0 )
      return BSTRFromTSTR;
    else
      return BSTRFromTSTR == 1;
  }
  return result;
}

```

## disassembly

```asm
0x180008c60  mov     [rsp-8+arg_10], rbx
0x180008c65  mov     [rsp-8+arg_18], rsi
0x180008c6a  push    rbp
0x180008c6b  push    rdi
0x180008c6c  push    r14
0x180008c6e  lea     rbp, [rsp-47h]
0x180008c73  sub     rsp, 0E0h
0x180008c7a  mov     rax, cs:__security_cookie
0x180008c81  xor     rax, rsp
0x180008c84  mov     [rbp+57h+var_20], rax
0x180008c88  mov     r14, rdx
0x180008c8b  mov     rsi, rcx
0x180008c8e  call    IsHTTPPrefixed
0x180008c93  test    eax, eax
0x180008c95  jnz     short loc_180008CA1
0x180008c97  mov     eax, 80070057h
0x180008c9c  jmp     loc_180008DB7
0x180008ca1  xor     ecx, ecx; pvReserved
0x180008ca3  mov     [rbp+57h+var_B0], 0
0x180008cab  call    cs:__imp_CoInitialize
0x180008cb1  test    eax, eax
0x180008cb3  js      loc_180008DB7
0x180008cb9  xor     edx, edx; pUnkOuter
0x180008cbb  lea     rax, [rbp+57h+var_B0]
0x180008cbf  lea     r9, IID_ISubscriptionMgr; riid
0x180008cc6  mov     [rsp+0F0h+ppv], rax; ppv
0x180008ccb  lea     rcx, CLSID_SubscriptionMgr; rclsid
0x180008cd2  lea     r8d, [rdx+1]; dwClsContext
0x180008cd6  call    cs:__imp_CoCreateInstance
0x180008cdc  mov     ebx, eax
0x180008cde  call    cs:__imp_CoUninitialize
0x180008ce4  test    ebx, ebx
0x180008ce6  jns     short loc_180008CEF
0x180008ce8  mov     eax, ebx
0x180008cea  jmp     loc_180008DB7
0x180008cef  xor     edi, edi
0x180008cf1  mov     [rbp+57h+bstrString], 0
0x180008cf9  mov     rdx, rsi
0x180008cfc  mov     [rbp+57h+var_A8], rdi
0x180008d00  lea     rcx, [rbp+57h+bstrString]
0x180008d04  call    CreateBSTRFromTSTR
0x180008d09  mov     ebx, eax
0x180008d0b  test    eax, eax
0x180008d0d  jnz     short loc_180008D21
0x180008d0f  mov     rdx, r14
0x180008d12  lea     rcx, [rbp+57h+var_A8]
0x180008d16  call    CreateBSTRFromTSTR
0x180008d1b  mov     rdi, [rbp+57h+var_A8]
0x180008d1f  mov     ebx, eax
0x180008d21  xor     edx, edx; Val
0x180008d23  lea     rcx, [rbp+57h+var_8C]; void *
0x180008d27  lea     r8d, [rdx+6Ch]; Size
0x180008d2b  call    memset_0
0x180008d30  mov     rsi, [rbp+57h+bstrString]
0x180008d34  mov     [rbp+57h+var_90], 70h ; 'p'
0x180008d3b  test    ebx, ebx
0x180008d3d  jnz     short loc_180008D6E
0x180008d3f  mov     rcx, [rbp+57h+var_B0]
0x180008d43  lea     rdx, [rbp+57h+var_90]
0x180008d47  mov     [rsp+0F0h+var_C0], rdx
0x180008d4c  mov     r9, rdi
0x180008d4f  mov     [rsp+0F0h+var_C8], ebx
0x180008d53  mov     r8, rsi
0x180008d56  xor     edx, edx
0x180008d58  mov     dword ptr [rsp+0F0h+ppv], 4
0x180008d60  mov     rax, [rcx]
0x180008d63  mov     rax, [rax+50h]
0x180008d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d6c  mov     ebx, eax
0x180008d6e  mov     rcx, [rbp+57h+var_B0]
0x180008d72  test    rcx, rcx
0x180008d75  jz      short loc_180008D8B
0x180008d77  mov     rax, [rcx]
0x180008d7a  mov     rax, [rax+10h]
0x180008d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d83  mov     [rbp+57h+var_B0], 0
0x180008d8b  test    rsi, rsi
0x180008d8e  jz      short loc_180008D99
0x180008d90  mov     rcx, rsi; bstrString
0x180008d93  call    cs:__imp_SysFreeString
0x180008d99  test    rdi, rdi
0x180008d9c  jz      short loc_180008DA7
0x180008d9e  mov     rcx, rdi; bstrString
0x180008da1  call    cs:__imp_SysFreeString
0x180008da7  test    ebx, ebx
0x180008da9  js      loc_180008CE8
0x180008daf  xor     eax, eax
0x180008db1  cmp     ebx, 1
0x180008db4  setz    al
0x180008db7  mov     rcx, [rbp+57h+var_20]
0x180008dbb  xor     rcx, rsp; StackCookie
0x180008dbe  call    __security_check_cookie
0x180008dc3  lea     r11, [rsp+0F0h+var_10]
0x180008dcb  mov     rbx, [r11+30h]
0x180008dcf  mov     rsi, [r11+38h]
0x180008dd3  mov     rsp, r11
0x180008dd6  pop     r14
0x180008dd8  pop     rdi
0x180008dd9  pop     rbp
0x180008dda  retn
```
