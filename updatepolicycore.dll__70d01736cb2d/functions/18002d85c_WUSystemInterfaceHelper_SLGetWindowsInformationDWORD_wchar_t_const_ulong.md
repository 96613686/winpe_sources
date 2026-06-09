# WUSystemInterfaceHelper::SLGetWindowsInformationDWORD(wchar_t const *,ulong *)

- ea: `0x18002d85c`
- end: `0x18002d993`
- name: `?SLGetWindowsInformationDWORD@WUSystemInterfaceHelper@@YAJPEB_WPEAK@Z`
- size: `311`
- prototype: `__int64 __fastcall(WUSystemInterfaceHelper *__hidden this, const wchar_t *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18001f000`

## callees

- `0x18000aac0`
- `0x18002d3fc`
- `0x18002d730`
- `0x18002d85c`
- `0x18002ffd0`
- `0x180036a10`

## string_xrefs

- `0x18002d921`: `UpdatePolicy-UpdateManagementGroup`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WUSystemInterfaceHelper::SLGetWindowsInformationDWORD(
        WUSystemInterfaceHelper *this,
        const wchar_t *a2,
        unsigned int *a3)
{
  unsigned int WUSystemInterface; // ebx
  __int64 v5; // rdx
  __int64 result; // rax
  int v7; // eax
  int v8; // eax
  unsigned int v9; // edi
  int v10[2]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  WUSystemInterface = WUSystemInterfaceHelper::LoadWUSystemInterface(this);
  if ( (WUSystemInterface & 0x80000000) != 0 )
  {
    v5 = 862;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusyshelper\\wusyshelper.cpp",
      (const char *)WUSystemInterface,
      v10[0]);
    return WUSystemInterface;
  }
  result = WUSystemInterfaceHelper::IsCapabilitySupported((WUSystemInterfaceHelper *)6);
  WUSystemInterface = result;
  if ( (int)result >= 0 )
  {
    *(_QWORD *)v10 = 0;
    v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, int *))g_WUSystemInterface)(
           g_WUSystemInterface,
           &GUID_8fd9dcdc_f120_4fe5_95ce_75542fe86b18,
           v10);
    WUSystemInterface = v7;
    if ( v7 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, const wchar_t *))(**(_QWORD **)v10 + 536LL))(
             *(_QWORD *)v10,
             L"UpdatePolicy-UpdateManagementGroup",
             a2);
      v9 = v8;
      if ( v8 >= 0 )
      {
        WUSystemInterface = 0;
      }
      else
      {
        WUSystemInterface = -1073418222;
        if ( v8 != -1073418222 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x369,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusyshelper\\wusyshelper.cpp",
            (const char *)(unsigned int)v8,
            v10[0]);
          WUSystemInterface = v9;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x365,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusyshelper\\wusyshelper.cpp",
        (const char *)(unsigned int)v7,
        v10[0]);
    }
    if ( *(_QWORD *)v10 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 16LL))(*(_QWORD *)v10);
    return WUSystemInterface;
  }
  if ( (_DWORD)result != -2147467262 && (_DWORD)result != -2147024846 )
  {
    v5 = 866;
    goto LABEL_3;
  }
  return result;
}

```

## disassembly

```asm
0x18002d85c  mov     [rsp+arg_0], rbx
0x18002d861  push    rdi
0x18002d862  sub     rsp, 30h
0x18002d866  mov     rax, cs:__security_cookie
0x18002d86d  xor     rax, rsp
0x18002d870  mov     [rsp+38h+var_10], rax
0x18002d875  mov     rdi, rdx
0x18002d878  call    ?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ; WUSystemInterfaceHelper::LoadWUSystemInterface(void)
0x18002d87d  mov     ebx, eax
0x18002d87f  test    eax, eax
0x18002d881  jns     short loc_18002D8A1
0x18002d883  mov     edx, 35Eh; void *
0x18002d888  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x18002d88f  mov     r9d, ebx; char *
0x18002d892  mov     rcx, [rsp+38h]; this
0x18002d897  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d89c  jmp     loc_18002D979
0x18002d8a1  mov     ecx, 6; this
0x18002d8a6  call    ?IsCapabilitySupported@WUSystemInterfaceHelper@@YAJK@Z; WUSystemInterfaceHelper::IsCapabilitySupported(ulong)
0x18002d8ab  mov     ebx, eax
0x18002d8ad  test    eax, eax
0x18002d8af  jns     short loc_18002D8CE
0x18002d8b1  cmp     eax, 80004002h
0x18002d8b6  jz      loc_18002D97B
0x18002d8bc  cmp     eax, 80070032h
0x18002d8c1  jz      loc_18002D97B
0x18002d8c7  mov     edx, 362h
0x18002d8cc  jmp     short loc_18002D888
0x18002d8ce  mov     qword ptr [rsp+38h+var_18], 0; int
0x18002d8d7  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18002d8de  mov     rax, [rcx]
0x18002d8e1  lea     r8, [rsp+38h+var_18]
0x18002d8e6  lea     rdx, _GUID_8fd9dcdc_f120_4fe5_95ce_75542fe86b18
0x18002d8ed  mov     rax, [rax]
0x18002d8f0  call    _guard_dispatch_icall
0x18002d8f5  mov     ebx, eax
0x18002d8f7  test    eax, eax
0x18002d8f9  jns     short loc_18002D916
0x18002d8fb  mov     rcx, [rsp+38h]; this
0x18002d900  mov     r9d, eax; char *
0x18002d903  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x18002d90a  mov     edx, 365h; void *
0x18002d90f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d914  jmp     short loc_18002D962
0x18002d916  mov     rcx, qword ptr [rsp+38h+var_18]
0x18002d91b  mov     rax, [rcx]
0x18002d91e  mov     r8, rdi
0x18002d921  lea     rdx, pwszValueName; "UpdatePolicy-UpdateManagementGroup"
0x18002d928  mov     rax, [rax+218h]
0x18002d92f  call    _guard_dispatch_icall
0x18002d934  mov     edi, eax
0x18002d936  test    eax, eax
0x18002d938  jns     short loc_18002D960
0x18002d93a  mov     ebx, 0C004F012h
0x18002d93f  cmp     eax, ebx
0x18002d941  jz      short loc_18002D962
0x18002d943  mov     rcx, [rsp+38h]; this
0x18002d948  mov     r9d, eax; char *
0x18002d94b  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x18002d952  mov     edx, 369h; void *
0x18002d957  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d95c  mov     ebx, edi
0x18002d95e  jmp     short loc_18002D962
0x18002d960  xor     ebx, ebx
0x18002d962  mov     rcx, qword ptr [rsp+38h+var_18]
0x18002d967  test    rcx, rcx
0x18002d96a  jz      short loc_18002D979
0x18002d96c  mov     rdx, [rcx]
0x18002d96f  mov     rax, [rdx+10h]
0x18002d973  call    _guard_dispatch_icall
0x18002d978  nop
0x18002d979  mov     eax, ebx
0x18002d97b  mov     rcx, [rsp+38h+var_10]
0x18002d980  xor     rcx, rsp; StackCookie
0x18002d983  call    __security_check_cookie
0x18002d988  mov     rbx, [rsp+38h+arg_0]
0x18002d98d  add     rsp, 30h
0x18002d991  pop     rdi
0x18002d992  retn
```
