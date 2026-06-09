# ProcessRemoveDesktopComponents(HKEY__ *)

- ea: `0x180002e30`
- end: `0x180002f0b`
- name: `?ProcessRemoveDesktopComponents@@YAJPEAUHKEY__@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800024f4`
- `0x180002614`
- `0x18000272c`
- `0x18000279c`
- `0x180002e30`
- `0x180029280`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002eb3`
- `OLEAUT32!__imp_SysFreeString` at `0x180002eb3`

## pseudocode

```c
__int64 __fastcall ProcessRemoveDesktopComponents(HKEY hKey)
{
  BSTR bstrString; // [rsp+20h] [rbp-E0h] BYREF
  HKEY v4; // [rsp+28h] [rbp-D8h] BYREF
  int v5; // [rsp+30h] [rbp-D0h]
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  int v7; // [rsp+40h] [rbp-C0h]
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  v5 = 0;
  v4 = hKey;
  while ( !CRegKey::Next((CRegKey *)&v4, SubKey) )
  {
    phkResult = 0;
    v7 = 0;
    CRegKey::OpenForRead(&phkResult, hKey, SubKey);
    bstrString = 0;
    if ( (int)CRegKey::GetBSTRValue((CRegKey *)&phkResult, L"URL", &bstrString) >= 0 )
      SysFreeString(bstrString);
    CRegKey::~CRegKey((CRegKey *)&phkResult);
  }
  v4 = 0;
  CRegKey::~CRegKey((CRegKey *)&v4);
  return 0;
}

```

## disassembly

```asm
0x180002e30  mov     [rsp-8+arg_8], rbx
0x180002e35  push    rbp
0x180002e36  lea     rbp, [rsp-170h]
0x180002e3e  sub     rsp, 270h
0x180002e45  mov     rax, cs:__security_cookie
0x180002e4c  xor     rax, rsp
0x180002e4f  mov     [rbp+170h+var_10], rax
0x180002e56  mov     rbx, rcx
0x180002e59  mov     [rsp+270h+var_240], 0
0x180002e61  mov     [rsp+270h+var_248], rcx
0x180002e66  jmp     short loc_180002EC3
0x180002e68  lea     r8, [rsp+270h+SubKey]; lpSubKey
0x180002e6d  mov     [rsp+270h+phkResult], 0
0x180002e76  mov     rdx, rbx; hKey
0x180002e79  mov     [rsp+270h+var_230], 0
0x180002e81  lea     rcx, [rsp+270h+phkResult]; phkResult
0x180002e86  call    ?OpenForRead@CRegKey@@QEAAJPEAUHKEY__@@PEBG@Z; CRegKey::OpenForRead(HKEY__ *,ushort const *)
0x180002e8b  lea     r8, [rsp+270h+bstrString]; unsigned __int16 **
0x180002e90  mov     [rsp+270h+bstrString], 0
0x180002e99  lea     rdx, aUrl_1; "URL"
0x180002ea0  lea     rcx, [rsp+270h+phkResult]; this
0x180002ea5  call    ?GetBSTRValue@CRegKey@@QEAAJPEBGPEAPEAG@Z; CRegKey::GetBSTRValue(ushort const *,ushort * *)
0x180002eaa  test    eax, eax
0x180002eac  js      short loc_180002EB9
0x180002eae  mov     rcx, [rsp+270h+bstrString]; bstrString
0x180002eb3  call    cs:__imp_SysFreeString
0x180002eb9  lea     rcx, [rsp+270h+phkResult]; this
0x180002ebe  call    ??1CRegKey@@QEAA@XZ; CRegKey::~CRegKey(void)
0x180002ec3  lea     rdx, [rsp+270h+SubKey]; unsigned __int16 *
0x180002ec8  lea     rcx, [rsp+270h+var_248]; this
0x180002ecd  call    ?Next@CRegKey@@QEAAJPEAG@Z; CRegKey::Next(ushort *)
0x180002ed2  test    eax, eax
0x180002ed4  jz      short loc_180002E68
0x180002ed6  lea     rcx, [rsp+270h+var_248]; this
0x180002edb  mov     [rsp+270h+var_248], 0
0x180002ee4  call    ??1CRegKey@@QEAA@XZ; CRegKey::~CRegKey(void)
0x180002ee9  xor     eax, eax
0x180002eeb  mov     rcx, [rbp+170h+var_10]
0x180002ef2  xor     rcx, rsp; StackCookie
0x180002ef5  call    __security_check_cookie
0x180002efa  mov     rbx, [rsp+270h+arg_8]
0x180002f02  add     rsp, 270h
0x180002f09  pop     rbp
0x180002f0a  retn
```
