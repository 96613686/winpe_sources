# Windows::System::Internal::SignInContext::RuntimeClassInitialize(Windows::System::Internal::ISignInContext *)

- ea: `0x18006511c`
- end: `0x1800653a1`
- name: `?RuntimeClassInitialize@SignInContext@Internal@System@Windows@@QEAAJPEAUISignInContext@234@@Z`
- size: `645`
- prototype: `int(Windows::System::Internal::SignInContext *__hidden this, struct Windows::System::Internal::ISignInContext *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180063774`

## callees

- `0x18000acdc`
- `0x18000c988`
- `0x18000ce48`
- `0x180024828`
- `0x18006511c`
- `0x1800653a8`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006520d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006533c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006520d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006533c`

## string_xrefs

- `0x18006513f`: `onecore\ds\security\umstartup\usermgr\lib\signincontext.cpp`
- `0x18006518e`: `onecore\ds\security\umstartup\usermgr\lib\signincontext.cpp`
- `0x1800651be`: `onecore\ds\security\umstartup\usermgr\lib\signincontext.cpp`
- `0x1800651ee`: `onecore\ds\security\umstartup\usermgr\lib\signincontext.cpp`
- `0x180065234`: `onecore\ds\security\umstartup\usermgr\lib\signincontext.cpp`
- `0x180065264`: `onecore\ds\security\umstartup\usermgr\lib\signincontext.cpp`
- `0x1800652a5`: `onecore\ds\security\umstartup\usermgr\lib\signincontext.cpp`
- `0x1800652e9`: `onecore\ds\security\umstartup\usermgr\lib\signincontext.cpp`
- `0x180065315`: `onecore\ds\security\umstartup\usermgr\lib\signincontext.cpp`
- `0x180065363`: `onecore\ds\security\umstartup\usermgr\lib\signincontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::System::Internal::SignInContext::RuntimeClassInitialize(
        Windows::System::Internal::SignInContext *this,
        struct Windows::System::Internal::ISignInContext *a2)
{
  __int64 (__fastcall *v4)(char *, _QWORD); // rdi
  unsigned int CallerSessionId; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  __int64 (__fastcall *v9)(struct Windows::System::Internal::ISignInContext *, char *); // rdi
  int v10; // eax
  int v11; // eax
  __int64 (__fastcall *v12)(struct Windows::System::Internal::ISignInContext *, char *); // rdi
  int v13; // eax
  __int64 (__fastcall *v14)(struct Windows::System::Internal::ISignInContext *, char *); // rdi
  int v15; // eax
  int v16; // eax
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, char *); // rdi
  int v19; // eax
  const char *v20; // r9
  __int64 result; // rax
  int v22; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v24; // [rsp+48h] [rbp+10h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64); // [rsp+50h] [rbp+18h] BYREF

  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x38,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\signincontext.cpp",
        (const char *)0x80004003LL,
        v22);
    v25 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a2;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v25);
    v24 = 0;
    v4 = *(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 3) + 56LL);
    CallerSessionId = Windows::System::Internal::Implementation::ComUtils::GetCallerSessionId();
    v6 = v4((char *)this + 24, CallerSessionId);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3D,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\signincontext.cpp",
        (const char *)(unsigned int)v6,
        v22);
    v7 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::ISignInContext *, char *))(*(_QWORD *)a2 + 48LL))(
           a2,
           (char *)this + 92);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\signincontext.cpp",
        (const char *)(unsigned int)v7,
        v22);
    v8 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::ISignInContext *, char *))(*(_QWORD *)a2 + 64LL))(
           a2,
           (char *)this + 96);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\signincontext.cpp",
        (const char *)(unsigned int)v8,
        v22);
    v9 = *(__int64 (__fastcall **)(struct Windows::System::Internal::ISignInContext *, char *))(*(_QWORD *)a2 + 96LL);
    WindowsDeleteString(*((HSTRING *)this + 15));
    *((_QWORD *)this + 15) = 0;
    v10 = v9(a2, (char *)this + 120);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\signincontext.cpp",
        (const char *)(unsigned int)v10,
        v22);
    v11 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::ISignInContext *, char *))(*(_QWORD *)a2 + 80LL))(
            a2,
            (char *)this + 112);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\signincontext.cpp",
        (const char *)(unsigned int)v11,
        v22);
    v12 = *(__int64 (__fastcall **)(struct Windows::System::Internal::ISignInContext *, char *))(*(_QWORD *)a2 + 112LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 128);
    v13 = v12(a2, (char *)this + 128);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\signincontext.cpp",
        (const char *)(unsigned int)v13,
        v22);
    v14 = *(__int64 (__fastcall **)(struct Windows::System::Internal::ISignInContext *, char *))(*(_QWORD *)a2 + 128LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 136);
    v15 = v14(a2, (char *)this + 136);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\signincontext.cpp",
        (const char *)(unsigned int)v15,
        v22);
    v16 = Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInContext>::As<Windows::System::Internal::ISignInContext2>(
            &v25,
            (__int64)&v24);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\signincontext.cpp",
        (const char *)(unsigned int)v16,
        v22);
    v17 = v24;
    v18 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v24 + 48LL);
    WindowsDeleteString(*((HSTRING *)this + 18));
    *((_QWORD *)this + 18) = 0;
    v19 = v18(v17, (char *)this + 144);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\signincontext.cpp",
        (const char *)(unsigned int)v19,
        v22);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4C,
                           (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\signincontext.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x18006511c  mov     [rsp+arg_0], rbx
0x180065121  push    rsi
0x180065122  push    rdi
0x180065123  push    r14; int
0x180065125  sub     rsp, 20h
0x180065129  mov     rsi, rdx
0x18006512c  mov     r14, rcx
0x18006512f  mov     rcx, [rsp+38h]; this
0x180065134  test    rdx, rdx
0x180065137  jnz     short loc_18006514E
0x180065139  mov     r9d, 80004003h; char *
0x18006513f  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\umstartup\\userm"...
0x180065146  lea     edx, [rsi+38h]; void *
0x180065149  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006514e  mov     [rsp+38h+arg_10], rsi
0x180065153  lea     rcx, [rsp+38h+arg_10]
0x180065158  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18006515d  nop
0x18006515e  mov     [rsp+38h+arg_8], 0
0x180065167  mov     rax, [r14+18h]
0x18006516b  mov     rdi, [rax+38h]
0x18006516f  call    ?GetCallerSessionId@ComUtils@Implementation@Internal@System@Windows@@SAKXZ; Windows::System::Internal::Implementation::ComUtils::GetCallerSessionId(void)
0x180065174  mov     edx, eax
0x180065176  lea     rcx, [r14+18h]
0x18006517a  mov     rax, rdi
0x18006517d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065182  mov     rcx, [rsp+38h]; this
0x180065187  test    eax, eax
0x180065189  jns     short loc_18006519F
0x18006518b  mov     r9d, eax; char *
0x18006518e  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\umstartup\\userm"...
0x180065195  mov     edx, 3Dh ; '='; void *
0x18006519a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006519f  mov     rax, [rsi]
0x1800651a2  lea     rdx, [r14+5Ch]
0x1800651a6  mov     rcx, rsi
0x1800651a9  mov     rax, [rax+30h]
0x1800651ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800651b2  mov     rcx, [rsp+38h]; this
0x1800651b7  test    eax, eax
0x1800651b9  jns     short loc_1800651CF
0x1800651bb  mov     r9d, eax; char *
0x1800651be  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\umstartup\\userm"...
0x1800651c5  mov     edx, 3Eh ; '>'; void *
0x1800651ca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800651cf  mov     rax, [rsi]
0x1800651d2  lea     rdx, [r14+60h]
0x1800651d6  mov     rcx, rsi
0x1800651d9  mov     rax, [rax+40h]
0x1800651dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800651e2  mov     rcx, [rsp+38h]; this
0x1800651e7  test    eax, eax
0x1800651e9  jns     short loc_1800651FF
0x1800651eb  mov     r9d, eax; char *
0x1800651ee  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\umstartup\\userm"...
0x1800651f5  mov     edx, 3Fh ; '?'; void *
0x1800651fa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800651ff  mov     rax, [rsi]
0x180065202  mov     rdi, [rax+60h]
0x180065206  lea     rbx, [r14+78h]
0x18006520a  mov     rcx, [rbx]; string
0x18006520d  call    cs:__imp_WindowsDeleteString
0x180065213  mov     qword ptr [rbx], 0
0x18006521a  mov     rdx, rbx
0x18006521d  mov     rcx, rsi
0x180065220  mov     rax, rdi
0x180065223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065228  mov     rcx, [rsp+38h]; this
0x18006522d  test    eax, eax
0x18006522f  jns     short loc_180065245
0x180065231  mov     r9d, eax; char *
0x180065234  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\umstartup\\userm"...
0x18006523b  mov     edx, 40h ; '@'; void *
0x180065240  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065245  mov     rax, [rsi]
0x180065248  lea     rdx, [r14+70h]
0x18006524c  mov     rcx, rsi
0x18006524f  mov     rax, [rax+50h]
0x180065253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065258  mov     rcx, [rsp+38h]; this
0x18006525d  test    eax, eax
0x18006525f  jns     short loc_180065275
0x180065261  mov     r9d, eax; char *
0x180065264  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\umstartup\\userm"...
0x18006526b  mov     edx, 41h ; 'A'; void *
0x180065270  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065275  mov     rax, [rsi]
0x180065278  mov     rdi, [rax+70h]
0x18006527c  lea     rbx, [r14+80h]
0x180065283  mov     rcx, rbx
0x180065286  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006528b  mov     rdx, rbx
0x18006528e  mov     rcx, rsi
0x180065291  mov     rax, rdi
0x180065294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065299  mov     rcx, [rsp+38h]; this
0x18006529e  test    eax, eax
0x1800652a0  jns     short loc_1800652B6
0x1800652a2  mov     r9d, eax; char *
0x1800652a5  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\umstartup\\userm"...
0x1800652ac  mov     edx, 42h ; 'B'; void *
0x1800652b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800652b6  mov     rax, [rsi]
0x1800652b9  mov     rdi, [rax+80h]
0x1800652c0  lea     rbx, [r14+88h]
0x1800652c7  mov     rcx, rbx
0x1800652ca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800652cf  mov     rdx, rbx
0x1800652d2  mov     rcx, rsi
0x1800652d5  mov     rax, rdi
0x1800652d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800652dd  mov     rcx, [rsp+38h]; this
0x1800652e2  test    eax, eax
0x1800652e4  jns     short loc_1800652FA
0x1800652e6  mov     r9d, eax; char *
0x1800652e9  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\umstartup\\userm"...
0x1800652f0  mov     edx, 43h ; 'C'; void *
0x1800652f5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800652fa  lea     rdx, [rsp+38h+arg_8]
0x1800652ff  lea     rcx, [rsp+38h+arg_10]
0x180065304  call    ??$As@UISignInContext2@Internal@System@Windows@@@?$ComPtr@UISignInContext@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISignInContext2@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInContext>::As<Windows::System::Internal::ISignInContext2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInContext2>>)
0x180065309  mov     rcx, [rsp+38h]; this
0x18006530e  test    eax, eax
0x180065310  jns     short loc_180065326
0x180065312  mov     r9d, eax; char *
0x180065315  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\umstartup\\userm"...
0x18006531c  mov     edx, 47h ; 'G'; void *
0x180065321  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065326  mov     rsi, [rsp+38h+arg_8]
0x18006532b  mov     rax, [rsi]
0x18006532e  mov     rdi, [rax+30h]
0x180065332  lea     rbx, [r14+90h]
0x180065339  mov     rcx, [rbx]; string
0x18006533c  call    cs:__imp_WindowsDeleteString
0x180065342  mov     qword ptr [rbx], 0
0x180065349  mov     rdx, rbx
0x18006534c  mov     rcx, rsi
0x18006534f  mov     rax, rdi
0x180065352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065357  mov     rcx, [rsp+38h]; this
0x18006535c  test    eax, eax
0x18006535e  jns     short loc_180065375
0x180065360  mov     r9d, eax; char *
0x180065363  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\umstartup\\userm"...
0x18006536a  mov     edx, 48h ; 'H'; void *
0x18006536f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065375  lea     rcx, [rsp+38h+arg_8]
0x18006537a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006537f  nop
0x180065380  lea     rcx, [rsp+38h+arg_10]
0x180065385  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006538a  xor     eax, eax
0x18006538c  jmp     short loc_180065392
0x18006538e  mov     eax, dword ptr [rsp+38h+arg_8]
0x180065392  mov     rbx, [rsp+38h+arg_0]
0x180065397  add     rsp, 20h
0x18006539b  pop     r14
0x18006539d  pop     rdi
0x18006539e  pop     rsi
0x18006539f  retn
```
