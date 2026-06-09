# _LoadUnloadUserProfileClient(bool,void *,_PROFILEINFOW *)

- ea: `0x180006160`
- end: `0x1800062a5`
- name: `?_LoadUnloadUserProfileClient@@YAJ_NPEAXPEAU_PROFILEINFOW@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(bool, void *, struct _PROFILEINFOW *)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800046ac`
- `0x180004968`
- `0x180006bb0`
- `0x180006ce0`

## callees

- `0x1800055d8`
- `0x180005a48`
- `0x180006160`
- `0x1800062ac`
- `0x180006300`
- `0x1800065d8`
- `0x18000db08`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000620d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006261`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000620d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006261`
- `RPCRT4!RpcRevertToSelf` at `0x180006271`
- `RPCRT4!RpcRevertToSelf` at `0x18000628d`
- `RPCRT4!RpcRevertToSelf` at `0x180006271`
- `RPCRT4!RpcRevertToSelf` at `0x18000628d`

## string_xrefs

- `0x180006231`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _LoadUnloadUserProfileClient(char a1, void *a2, struct _PROFILEINFOW *a3)
{
  int v3; // eax
  int v4; // ebx
  unsigned __int16 *v5; // rdx
  _QWORD v7[4]; // [rsp+20h] [rbp-50h] BYREF
  HANDLE v8[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v9; // [rsp+50h] [rbp-20h]
  int v10; // [rsp+58h] [rbp-18h]
  __int128 v11; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  char v13; // [rsp+80h] [rbp+10h] BYREF
  void *v14; // [rsp+88h] [rbp+18h] BYREF
  struct _PROFILEINFOW *v15; // [rsp+90h] [rbp+20h] BYREF

  v15 = a3;
  v14 = a2;
  v13 = a1;
  LODWORD(v8[0]) = 0;
  v8[1] = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v3 = CThreadContext::ImpersonateUser((CThreadContext *)v8, a2);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
      (const char *)(unsigned int)v3,
      v7[0]);
    CThreadContext::RevertPrivileges((CThreadContext *)v8);
    CThreadContext::RevertToPreviousToken(v8);
    if ( HIDWORD(v9) )
    {
      RpcRevertToSelf();
      HIDWORD(v9) = 0;
    }
    if ( (_DWORD)v9 )
      RevertToSelf();
    return (unsigned int)v4;
  }
  CThreadContext::RevertToPreviousToken(v8);
  v7[0] = v8;
  v7[1] = &v15;
  v7[2] = &v14;
  v7[3] = &v13;
  v4 = InvokeUserProfileRPC__lambda_7f94f01fc3cf1545aca7f938a37387d8_((__int64)v7, v5);
  if ( v4 < 0 )
  {
    CThreadContext::~CThreadContext((CThreadContext *)v8);
    return (unsigned int)v4;
  }
  CThreadContext::RevertPrivileges((CThreadContext *)v8);
  CThreadContext::RevertToPreviousToken(v8);
  if ( HIDWORD(v9) )
  {
    RpcRevertToSelf();
    HIDWORD(v9) = 0;
  }
  if ( (_DWORD)v9 )
    RevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x180006160  mov     rax, rsp
0x180006163  mov     [rax+20h], rbx
0x180006167  mov     [rax+18h], r8
0x18000616b  mov     [rax+10h], rdx
0x18000616f  mov     [rax+8], cl
0x180006172  push    rbp
0x180006173  mov     rbp, rsp
0x180006176  sub     rsp, 70h
0x18000617a  mov     [rbp+var_30], 0
0x180006181  mov     [rbp+var_28], 0
0x180006189  mov     [rbp+var_20], 0
0x180006191  mov     [rbp+var_18], 0
0x180006198  xorps   xmm0, xmm0
0x18000619b  movdqu  [rbp+var_10], xmm0
0x1800061a0  lea     rcx, [rbp+var_30]; this
0x1800061a4  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x1800061a9  mov     ebx, eax
0x1800061ab  test    eax, eax
0x1800061ad  js      short loc_18000622A
0x1800061af  lea     rcx, [rbp+var_30]; this
0x1800061b3  call    ?RevertToPreviousToken@CThreadContext@@QEAAXXZ; CThreadContext::RevertToPreviousToken(void)
0x1800061b8  lea     rax, [rbp+var_30]
0x1800061bc  mov     [rbp+var_50], rax
0x1800061c0  lea     rax, [rbp+arg_10]
0x1800061c4  mov     [rbp+var_48], rax
0x1800061c8  lea     rax, [rbp+arg_8]
0x1800061cc  mov     [rbp+var_40], rax
0x1800061d0  lea     rax, [rbp+arg_0]
0x1800061d4  mov     [rbp+var_38], rax
0x1800061d8  lea     rcx, [rbp+var_50]
0x1800061dc  call    InvokeUserProfileRPC__lambda_7f94f01fc3cf1545aca7f938a37387d8___; InvokeUserProfileRPC__lambda_7f94f01fc3cf1545aca7f938a37387d8_
0x1800061e1  mov     ebx, eax
0x1800061e3  lea     rcx, [rbp+var_30]; this
0x1800061e7  test    eax, eax
0x1800061e9  js      loc_180006286
0x1800061ef  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x1800061f4  lea     rcx, [rbp+var_30]; this
0x1800061f8  call    ?RevertToPreviousToken@CThreadContext@@QEAAXXZ; CThreadContext::RevertToPreviousToken(void)
0x1800061fd  cmp     dword ptr [rbp+var_20+4], 0
0x180006201  jnz     loc_18000628D
0x180006207  cmp     dword ptr [rbp+var_20], 0
0x18000620b  jz      short loc_180006219
0x18000620d  call    cs:__imp_RevertToSelf
0x180006214  nop     dword ptr [rax+rax+00h]
0x180006219  xor     eax, eax
0x18000621b  mov     rbx, [rsp+70h+arg_18]
0x180006223  add     rsp, 70h
0x180006227  pop     rbp
0x180006228  retn
0x18000622a  mov     rcx, [rbp+8]; this
0x18000622e  mov     r9d, ebx; char *
0x180006231  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180006238  mov     edx, 0CDh; void *
0x18000623d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006242  nop
0x180006243  lea     rcx, [rbp+var_30]; this
0x180006247  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x18000624c  lea     rcx, [rbp+var_30]; this
0x180006250  call    ?RevertToPreviousToken@CThreadContext@@QEAAXXZ; CThreadContext::RevertToPreviousToken(void)
0x180006255  cmp     dword ptr [rbp+var_20+4], 0
0x180006259  jnz     short loc_180006271
0x18000625b  cmp     dword ptr [rbp+var_20], 0
0x18000625f  jz      short loc_18000626D
0x180006261  call    cs:__imp_RevertToSelf
0x180006268  nop     dword ptr [rax+rax+00h]
0x18000626d  mov     eax, ebx
0x18000626f  jmp     short loc_18000621B
0x180006271  call    cs:__imp_RpcRevertToSelf
0x180006278  nop     dword ptr [rax+rax+00h]
0x18000627d  mov     dword ptr [rbp+var_20+4], 0
0x180006284  jmp     short loc_18000625B
0x180006286  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18000628b  jmp     short loc_18000626D
0x18000628d  call    cs:__imp_RpcRevertToSelf
0x180006294  nop     dword ptr [rax+rax+00h]
0x180006299  mov     dword ptr [rbp+var_20+4], 0
0x1800062a0  jmp     loc_180006207
```
