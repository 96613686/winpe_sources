# ProcessRemoveSubscriptions(HKEY__ *)

- ea: `0x180002f20`
- end: `0x18000305d`
- name: `?ProcessRemoveSubscriptions@@YAJPEAUHKEY__@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002b10`

## callees

- `0x1800024f4`
- `0x180002614`
- `0x18000272c`
- `0x18000279c`
- `0x180002f20`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180002fc8`
- `ole32!CoCreateInstance` at `0x180002fc8`
- `OLEAUT32!__imp_SysFreeString` at `0x180003001`
- `OLEAUT32!__imp_SysFreeString` at `0x180003001`

## pseudocode

```c
__int64 __fastcall ProcessRemoveSubscriptions(HKEY hKey)
{
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v5; // [rsp+40h] [rbp-C0h] BYREF
  int v6; // [rsp+48h] [rbp-B8h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  int v8; // [rsp+58h] [rbp-A8h]
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  v6 = 0;
  v5 = hKey;
  while ( !CRegKey::Next((CRegKey *)&v5, SubKey) )
  {
    phkResult = 0;
    v8 = 0;
    CRegKey::OpenForRead(&phkResult, hKey, SubKey);
    bstrString = 0;
    if ( (int)CRegKey::GetBSTRValue((CRegKey *)&phkResult, L"URL", &bstrString) >= 0 )
    {
      ppv = 0;
      if ( CoCreateInstance(&CLSID_SubscriptionMgr, 0, 1u, &IID_ISubscriptionMgr, &ppv) >= 0 )
      {
        (*(void (__fastcall **)(LPVOID, BSTR, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, bstrString, 0);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      SysFreeString(bstrString);
    }
    CRegKey::~CRegKey((CRegKey *)&phkResult);
  }
  v5 = 0;
  CRegKey::~CRegKey((CRegKey *)&v5);
  return 0;
}

```

## disassembly

```asm
0x180002f20  mov     [rsp-8+arg_8], rbx
0x180002f25  push    rbp
0x180002f26  lea     rbp, [rsp-180h]
0x180002f2e  sub     rsp, 280h
0x180002f35  mov     rax, cs:__security_cookie
0x180002f3c  xor     rax, rsp
0x180002f3f  mov     [rbp+180h+var_10], rax
0x180002f46  mov     rbx, rcx
0x180002f49  mov     [rsp+280h+var_238], 0
0x180002f51  mov     [rsp+280h+var_240], rcx
0x180002f56  jmp     loc_180003011
0x180002f5b  lea     r8, [rsp+280h+SubKey]; lpSubKey
0x180002f60  mov     [rsp+280h+phkResult], 0
0x180002f69  mov     rdx, rbx; hKey
0x180002f6c  mov     [rsp+280h+var_228], 0
0x180002f74  lea     rcx, [rsp+280h+phkResult]; phkResult
0x180002f79  call    ?OpenForRead@CRegKey@@QEAAJPEAUHKEY__@@PEBG@Z; CRegKey::OpenForRead(HKEY__ *,ushort const *)
0x180002f7e  lea     r8, [rsp+280h+bstrString]; unsigned __int16 **
0x180002f83  mov     [rsp+280h+bstrString], 0
0x180002f8c  lea     rdx, aUrl_1; "URL"
0x180002f93  lea     rcx, [rsp+280h+phkResult]; this
0x180002f98  call    ?GetBSTRValue@CRegKey@@QEAAJPEBGPEAPEAG@Z; CRegKey::GetBSTRValue(ushort const *,ushort * *)
0x180002f9d  test    eax, eax
0x180002f9f  js      short loc_180003007
0x180002fa1  xor     edx, edx; pUnkOuter
0x180002fa3  mov     [rsp+280h+var_250], 0
0x180002fac  lea     rax, [rsp+280h+var_250]
0x180002fb1  lea     r9, IID_ISubscriptionMgr; riid
0x180002fb8  mov     [rsp+280h+ppv], rax; ppv
0x180002fbd  lea     rcx, CLSID_SubscriptionMgr; rclsid
0x180002fc4  lea     r8d, [rdx+1]; dwClsContext
0x180002fc8  call    cs:__imp_CoCreateInstance
0x180002fce  test    eax, eax
0x180002fd0  js      short loc_180002FFC
0x180002fd2  mov     rcx, [rsp+280h+var_250]
0x180002fd7  xor     r8d, r8d
0x180002fda  mov     rdx, [rsp+280h+bstrString]
0x180002fdf  mov     rax, [rcx]
0x180002fe2  mov     rax, [rax+18h]
0x180002fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002feb  mov     rcx, [rsp+280h+var_250]
0x180002ff0  mov     rax, [rcx]
0x180002ff3  mov     rax, [rax+10h]
0x180002ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ffc  mov     rcx, [rsp+280h+bstrString]; bstrString
0x180003001  call    cs:__imp_SysFreeString
0x180003007  lea     rcx, [rsp+280h+phkResult]; this
0x18000300c  call    ??1CRegKey@@QEAA@XZ; CRegKey::~CRegKey(void)
0x180003011  lea     rdx, [rsp+280h+SubKey]; unsigned __int16 *
0x180003016  lea     rcx, [rsp+280h+var_240]; this
0x18000301b  call    ?Next@CRegKey@@QEAAJPEAG@Z; CRegKey::Next(ushort *)
0x180003020  test    eax, eax
0x180003022  jz      loc_180002F5B
0x180003028  lea     rcx, [rsp+280h+var_240]; this
0x18000302d  mov     [rsp+280h+var_240], 0
0x180003036  call    ??1CRegKey@@QEAA@XZ; CRegKey::~CRegKey(void)
0x18000303b  xor     eax, eax
0x18000303d  mov     rcx, [rbp+180h+var_10]
0x180003044  xor     rcx, rsp; StackCookie
0x180003047  call    __security_check_cookie
0x18000304c  mov     rbx, [rsp+280h+arg_8]
0x180003054  add     rsp, 280h
0x18000305b  pop     rbp
0x18000305c  retn
```
