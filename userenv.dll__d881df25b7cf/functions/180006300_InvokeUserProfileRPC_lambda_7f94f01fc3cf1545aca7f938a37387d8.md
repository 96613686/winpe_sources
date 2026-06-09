# InvokeUserProfileRPC__lambda_7f94f01fc3cf1545aca7f938a37387d8_

- ea: `0x180006300`
- end: `0x1800063d0`
- name: `InvokeUserProfileRPC__lambda_7f94f01fc3cf1545aca7f938a37387d8___`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006160`

## callees

- `0x180004f48`
- `0x180006300`
- `0x1800063d8`
- `0x1800064d0`
- `0x18000661c`
- `0x18000db08`

## string_xrefs

- `0x18000636f`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`
- `0x180006397`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall InvokeUserProfileRPC__lambda_7f94f01fc3cf1545aca7f938a37387d8_(__int64 a1, unsigned __int16 *a2)
{
  int Interface; // eax
  unsigned int v4; // ebx
  int v5; // eax
  RPC_BINDING_HANDLE v6; // rcx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp+10h] BYREF

  Binding = 0;
  Interface = _GetInterface(&Binding, a2);
  v4 = Interface;
  if ( Interface < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
      (const char *)(unsigned int)Interface,
      v8);
    v6 = Binding;
    if ( !Binding )
      return v4;
    goto LABEL_8;
  }
  v5 = _RegisterClientAuthInfo(Binding);
  v4 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB1,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
      (const char *)(unsigned int)v5,
      v8);
    v6 = Binding;
    if ( !Binding )
      return v4;
LABEL_8:
    _ReleaseInterface(v6);
    return v4;
  }
  v4 = lambda_7f94f01fc3cf1545aca7f938a37387d8_::operator()(a1, Binding);
  v6 = Binding;
  if ( (v4 & 0x80000000) != 0 )
  {
    if ( !Binding )
      return v4;
    goto LABEL_8;
  }
  if ( Binding )
    _ReleaseInterface(Binding);
  return 0;
}

```

## disassembly

```asm
0x180006300  mov     [rsp+arg_0], rbx
0x180006305  push    rdi; int
0x180006306  sub     rsp, 20h
0x18000630a  mov     rdi, rcx
0x18000630d  mov     [rsp+28h+Binding], 0
0x180006316  lea     rcx, [rsp+28h+Binding]; Binding
0x18000631b  call    ?_GetInterface@@YAJPEAPEAXPEAG@Z; _GetInterface(void * *,ushort *)
0x180006320  mov     ebx, eax
0x180006322  test    eax, eax
0x180006324  js      short loc_18000638F
0x180006326  mov     rcx, [rsp+28h+Binding]; void *
0x18000632b  call    ?_RegisterClientAuthInfo@@YAJPEAX@Z; _RegisterClientAuthInfo(void *)
0x180006330  mov     ebx, eax
0x180006332  test    eax, eax
0x180006334  js      short loc_180006367
0x180006336  mov     rdx, [rsp+28h+Binding]
0x18000633b  mov     rcx, rdi
0x18000633e  call    _lambda_7f94f01fc3cf1545aca7f938a37387d8___operator__
0x180006343  mov     ebx, eax
0x180006345  mov     rcx, [rsp+28h+Binding]; void *
0x18000634a  test    eax, eax
0x18000634c  js      short loc_1800063C3
0x18000634e  test    rcx, rcx
0x180006351  jz      short loc_180006359
0x180006353  call    ?_ReleaseInterface@@YAJPEAX@Z; _ReleaseInterface(void *)
0x180006358  nop
0x180006359  xor     eax, eax
0x18000635b  mov     rbx, [rsp+28h+arg_0]
0x180006360  add     rsp, 20h
0x180006364  pop     rdi
0x180006365  retn
0x180006367  mov     rcx, [rsp+28h]; this
0x18000636c  mov     r9d, ebx; char *
0x18000636f  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180006376  mov     edx, 0B1h; void *
0x18000637b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006380  nop
0x180006381  mov     rcx, [rsp+28h+Binding]; void *
0x180006386  test    rcx, rcx
0x180006389  jnz     short loc_1800063BB
0x18000638b  mov     eax, ebx
0x18000638d  jmp     short loc_18000635B
0x18000638f  mov     rcx, [rsp+28h]; this
0x180006394  mov     r9d, ebx; char *
0x180006397  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000639e  mov     edx, 0AEh; void *
0x1800063a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800063a8  nop
0x1800063a9  mov     rcx, [rsp+28h+Binding]; void *
0x1800063ae  test    rcx, rcx
0x1800063b1  jz      short loc_18000638B
0x1800063b3  call    ?_ReleaseInterface@@YAJPEAX@Z; _ReleaseInterface(void *)
0x1800063b8  nop
0x1800063b9  jmp     short loc_18000638B
0x1800063bb  call    ?_ReleaseInterface@@YAJPEAX@Z; _ReleaseInterface(void *)
0x1800063c0  nop
0x1800063c1  jmp     short loc_18000638B
0x1800063c3  test    rcx, rcx
0x1800063c6  jz      short loc_18000638B
0x1800063c8  call    ?_ReleaseInterface@@YAJPEAX@Z; _ReleaseInterface(void *)
0x1800063cd  nop
0x1800063ce  jmp     short loc_18000638B
```
