# CWuaClassFactoryBase::RegisterClassFactory(void)

- ea: `0x14000bf4c`
- end: `0x14000c0bf`
- name: `?RegisterClassFactory@CWuaClassFactoryBase@@QEAAJXZ`
- size: `371`
- prototype: `__int64 __fastcall(CWuaClassFactoryBase *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400197cc`

## callees

- `0x140002ac0`
- `0x14000bf4c`
- `0x14000c21c`
- `0x14001aa60`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000bff1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000bff1`

## string_xrefs

- `0x14000bfa0`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x14000c002`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`

## pseudocode

```c
__int64 __fastcall CWuaClassFactoryBase::RegisterClassFactory(IUnknown *this)
{
  int v2; // ebx
  __int64 v3; // rdx
  IUnknown *v5; // rdi
  HRESULT Instance; // eax
  unsigned int v7; // esi
  struct IUnknownVtbl *lpVtbl; // rcx
  int ppv; // [rsp+20h] [rbp-58h]
  _QWORD v10[3]; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v11[2]; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !LODWORD(this[5].lpVtbl) )
  {
    if ( *(struct IUnknownVtbl **)&GUID_NULL.Data1 == this[1].lpVtbl
      && *(struct IUnknownVtbl **)GUID_NULL.Data4 == this[2].lpVtbl )
    {
      v2 = -2145124348;
      v3 = 403;
      goto LABEL_5;
    }
    if ( !HIDWORD(this[3].lpVtbl) )
    {
      v2 = CWuaClassFactoryBase::RegisterClassFactoryImpl(this);
      if ( v2 >= 0 )
        return (unsigned int)v2;
      v3 = 407;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v3,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
        (const char *)(unsigned int)v2,
        ppv);
      return (unsigned int)v2;
    }
    v5 = this + 4;
    if ( !this[4].lpVtbl )
    {
      Instance = CoCreateInstance(
                   &CLSID_ContextSwitcher,
                   0,
                   1u,
                   &GUID_000001da_0000_0000_c000_000000000046,
                   (LPVOID *)&this[4].lpVtbl);
      v7 = Instance;
      if ( Instance < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A0,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
          (const char *)(unsigned int)Instance,
          ppv);
        return v7;
      }
    }
    lpVtbl = v5->lpVtbl;
    if ( !v5->lpVtbl )
    {
      v2 = -2145120257;
      v3 = 419;
      goto LABEL_5;
    }
    v10[0] = 24;
    v11[1] = v10;
    v10[2] = 0;
    v11[0] = 0;
    v10[1] = this;
    ppv = 5;
    v2 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, int (*)(struct tagComCallData *), _QWORD *, GUID *))lpVtbl->QueryInterface
          + 3))(
           lpVtbl,
           CWuaClassFactoryBase::ContextCallback_Register,
           v11,
           &IID_IContextCallback);
    if ( v2 < 0 )
    {
      v3 = 430;
      goto LABEL_5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000bf4c  mov     [rsp+arg_8], rbx
0x14000bf51  mov     [rsp+arg_10], rsi
0x14000bf56  push    rdi
0x14000bf57  sub     rsp, 70h
0x14000bf5b  mov     rax, cs:__security_cookie
0x14000bf62  xor     rax, rsp
0x14000bf65  mov     [rsp+78h+var_10], rax
0x14000bf6a  cmp     dword ptr [rcx+28h], 0
0x14000bf6e  mov     rbx, rcx
0x14000bf71  jnz     loc_14000C09E
0x14000bf77  mov     rax, qword ptr cs:GUID_NULL.Data1
0x14000bf7e  cmp     rax, [rcx+8]
0x14000bf82  jnz     short loc_14000BFB6
0x14000bf84  mov     rax, qword ptr cs:GUID_NULL.Data4
0x14000bf8b  cmp     rax, [rcx+10h]
0x14000bf8f  jnz     short loc_14000BFB6
0x14000bf91  mov     ebx, 80240004h
0x14000bf96  mov     edx, 193h; void *
0x14000bf9b  mov     rcx, [rsp+78h]; this
0x14000bfa0  lea     r8, aCW1SSrcClientL_10; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000bfa7  mov     r9d, ebx; char *
0x14000bfaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bfaf  mov     eax, ebx
0x14000bfb1  jmp     loc_14000C0A0
0x14000bfb6  cmp     dword ptr [rcx+1Ch], 0
0x14000bfba  jnz     short loc_14000BFCE
0x14000bfbc  call    ?RegisterClassFactoryImpl@CWuaClassFactoryBase@@AEAAJXZ; CWuaClassFactoryBase::RegisterClassFactoryImpl(void)
0x14000bfc1  mov     ebx, eax
0x14000bfc3  test    eax, eax
0x14000bfc5  jns     short loc_14000BFAF
0x14000bfc7  mov     edx, 197h
0x14000bfcc  jmp     short loc_14000BF9B
0x14000bfce  lea     rdi, [rcx+20h]
0x14000bfd2  cmp     qword ptr [rdi], 0
0x14000bfd6  jnz     short loc_14000C01D
0x14000bfd8  xor     edx, edx; pUnkOuter
0x14000bfda  mov     [rsp+78h+ppv], rdi; int
0x14000bfdf  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x14000bfe6  lea     rcx, CLSID_ContextSwitcher; rclsid
0x14000bfed  lea     r8d, [rdx+1]; dwClsContext
0x14000bff1  call    cs:__imp_CoCreateInstance
0x14000bff7  mov     esi, eax
0x14000bff9  test    eax, eax
0x14000bffb  jns     short loc_14000C01D
0x14000bffd  mov     rcx, [rsp+78h]; this
0x14000c002  lea     r8, aCW1SSrcClientL_10; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000c009  mov     r9d, eax; char *
0x14000c00c  mov     edx, 1A0h; void *
0x14000c011  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c016  mov     eax, esi
0x14000c018  jmp     loc_14000C0A0
0x14000c01d  mov     rcx, [rdi]
0x14000c020  test    rcx, rcx
0x14000c023  jnz     short loc_14000C034
0x14000c025  mov     ebx, 80240FFFh
0x14000c02a  mov     edx, 1A3h
0x14000c02f  jmp     loc_14000BF9B
0x14000c034  lea     rax, [rsp+78h+var_38]
0x14000c039  mov     [rsp+78h+var_38], 18h
0x14000c042  mov     [rsp+78h+var_18], rax
0x14000c047  lea     r9, IID_IContextCallback
0x14000c04e  mov     [rsp+78h+var_28], 0
0x14000c057  lea     r8, [rsp+78h+var_20]
0x14000c05c  mov     [rsp+78h+var_20], 0
0x14000c065  lea     rdx, ?ContextCallback_Register@CWuaClassFactoryBase@@CAJPEAUtagComCallData@@@Z; CWuaClassFactoryBase::ContextCallback_Register(tagComCallData *)
0x14000c06c  mov     [rsp+78h+var_30], rbx
0x14000c071  mov     rax, [rcx]
0x14000c074  mov     [rsp+78h+var_50], 0
0x14000c07d  mov     dword ptr [rsp+78h+ppv], 5
0x14000c085  mov     rax, [rax+18h]
0x14000c089  call    _guard_dispatch_icall
0x14000c08e  mov     ebx, eax
0x14000c090  test    eax, eax
0x14000c092  jns     short loc_14000C09E
0x14000c094  mov     edx, 1AEh
0x14000c099  jmp     loc_14000BF9B
0x14000c09e  xor     eax, eax
0x14000c0a0  mov     rcx, [rsp+78h+var_10]
0x14000c0a5  xor     rcx, rsp; StackCookie
0x14000c0a8  call    __security_check_cookie
0x14000c0ad  lea     r11, [rsp+78h+var_8]
0x14000c0b2  mov     rbx, [r11+18h]
0x14000c0b6  mov     rsi, [r11+20h]
0x14000c0ba  mov     rsp, r11
0x14000c0bd  pop     rdi
0x14000c0be  retn
```
