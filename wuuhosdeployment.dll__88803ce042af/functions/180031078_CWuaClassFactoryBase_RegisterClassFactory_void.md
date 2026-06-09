# CWuaClassFactoryBase::RegisterClassFactory(void)

- ea: `0x180031078`
- end: `0x1800311eb`
- name: `?RegisterClassFactory@CWuaClassFactoryBase@@QEAAJXZ`
- size: `371`
- prototype: `__int64 __fastcall(IUnknown *this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c06c`
- `0x180036454`

## callees

- `0x180003950`
- `0x180031078`
- `0x18003143c`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003111d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003111d`

## string_xrefs

- `0x1800310cc`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x18003112e`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`

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
0x180031078  mov     [rsp+arg_8], rbx
0x18003107d  mov     [rsp+arg_10], rsi
0x180031082  push    rdi
0x180031083  sub     rsp, 70h
0x180031087  mov     rax, cs:__security_cookie
0x18003108e  xor     rax, rsp
0x180031091  mov     [rsp+78h+var_10], rax
0x180031096  cmp     dword ptr [rcx+28h], 0
0x18003109a  mov     rbx, rcx
0x18003109d  jnz     loc_1800311CA
0x1800310a3  mov     rax, qword ptr cs:GUID_NULL.Data1
0x1800310aa  cmp     rax, [rcx+8]
0x1800310ae  jnz     short loc_1800310E2
0x1800310b0  mov     rax, qword ptr cs:GUID_NULL.Data4
0x1800310b7  cmp     rax, [rcx+10h]
0x1800310bb  jnz     short loc_1800310E2
0x1800310bd  mov     ebx, 80240004h
0x1800310c2  mov     edx, 193h; void *
0x1800310c7  mov     rcx, [rsp+78h]; this
0x1800310cc  lea     r8, aCW1SSrcClientL_27; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800310d3  mov     r9d, ebx; char *
0x1800310d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800310db  mov     eax, ebx
0x1800310dd  jmp     loc_1800311CC
0x1800310e2  cmp     dword ptr [rcx+1Ch], 0
0x1800310e6  jnz     short loc_1800310FA
0x1800310e8  call    ?RegisterClassFactoryImpl@CWuaClassFactoryBase@@AEAAJXZ; CWuaClassFactoryBase::RegisterClassFactoryImpl(void)
0x1800310ed  mov     ebx, eax
0x1800310ef  test    eax, eax
0x1800310f1  jns     short loc_1800310DB
0x1800310f3  mov     edx, 197h
0x1800310f8  jmp     short loc_1800310C7
0x1800310fa  lea     rdi, [rcx+20h]
0x1800310fe  cmp     qword ptr [rdi], 0
0x180031102  jnz     short loc_180031149
0x180031104  xor     edx, edx; pUnkOuter
0x180031106  mov     [rsp+78h+ppv], rdi; int
0x18003110b  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x180031112  lea     rcx, CLSID_ContextSwitcher; rclsid
0x180031119  lea     r8d, [rdx+1]; dwClsContext
0x18003111d  call    cs:__imp_CoCreateInstance
0x180031123  mov     esi, eax
0x180031125  test    eax, eax
0x180031127  jns     short loc_180031149
0x180031129  mov     rcx, [rsp+78h]; this
0x18003112e  lea     r8, aCW1SSrcClientL_27; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180031135  mov     r9d, eax; char *
0x180031138  mov     edx, 1A0h; void *
0x18003113d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031142  mov     eax, esi
0x180031144  jmp     loc_1800311CC
0x180031149  mov     rcx, [rdi]
0x18003114c  test    rcx, rcx
0x18003114f  jnz     short loc_180031160
0x180031151  mov     ebx, 80240FFFh
0x180031156  mov     edx, 1A3h
0x18003115b  jmp     loc_1800310C7
0x180031160  lea     rax, [rsp+78h+var_38]
0x180031165  mov     [rsp+78h+var_38], 18h
0x18003116e  mov     [rsp+78h+var_18], rax
0x180031173  lea     r9, IID_IContextCallback
0x18003117a  mov     [rsp+78h+var_28], 0
0x180031183  lea     r8, [rsp+78h+var_20]
0x180031188  mov     [rsp+78h+var_20], 0
0x180031191  lea     rdx, ?ContextCallback_Register@CWuaClassFactoryBase@@CAJPEAUtagComCallData@@@Z; CWuaClassFactoryBase::ContextCallback_Register(tagComCallData *)
0x180031198  mov     [rsp+78h+var_30], rbx
0x18003119d  mov     rax, [rcx]
0x1800311a0  mov     [rsp+78h+var_50], 0
0x1800311a9  mov     dword ptr [rsp+78h+ppv], 5
0x1800311b1  mov     rax, [rax+18h]
0x1800311b5  call    _guard_dispatch_icall
0x1800311ba  mov     ebx, eax
0x1800311bc  test    eax, eax
0x1800311be  jns     short loc_1800311CA
0x1800311c0  mov     edx, 1AEh
0x1800311c5  jmp     loc_1800310C7
0x1800311ca  xor     eax, eax
0x1800311cc  mov     rcx, [rsp+78h+var_10]
0x1800311d1  xor     rcx, rsp; StackCookie
0x1800311d4  call    __security_check_cookie
0x1800311d9  lea     r11, [rsp+78h+var_8]
0x1800311de  mov     rbx, [r11+18h]
0x1800311e2  mov     rsi, [r11+20h]
0x1800311e6  mov     rsp, r11
0x1800311e9  pop     rdi
0x1800311ea  retn
```
