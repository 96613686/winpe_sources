# InvokeUserProfileRPC__lambda_7f94f01fc3cf1545aca7f938a37387d8_

- ea: `0x180005b28`
- end: `0x180005bf7`
- name: `InvokeUserProfileRPC__lambda_7f94f01fc3cf1545aca7f938a37387d8___`
- size: `207`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800059a4`

## callees

- `0x180004938`
- `0x180005b28`
- `0x180005c00`
- `0x180005ce0`
- `0x180005e68`
- `0x18000cea0`

## string_xrefs

- `0x180005b96`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`
- `0x180005bbe`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
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
0x180005b28  mov     [rsp+arg_0], rbx
0x180005b2d  push    rdi; int
0x180005b2e  sub     rsp, 20h
0x180005b32  mov     rdi, rcx
0x180005b35  mov     [rsp+28h+Binding], 0
0x180005b3e  lea     rcx, [rsp+28h+Binding]; Binding
0x180005b43  call    ?_GetInterface@@YAJPEAPEAXPEAG@Z; _GetInterface(void * *,ushort *)
0x180005b48  mov     ebx, eax
0x180005b4a  test    eax, eax
0x180005b4c  js      short loc_180005BB6
0x180005b4e  mov     rcx, [rsp+28h+Binding]; void *
0x180005b53  call    ?_RegisterClientAuthInfo@@YAJPEAX@Z; _RegisterClientAuthInfo(void *)
0x180005b58  mov     ebx, eax
0x180005b5a  test    eax, eax
0x180005b5c  js      short loc_180005B8E
0x180005b5e  mov     rdx, [rsp+28h+Binding]
0x180005b63  mov     rcx, rdi
0x180005b66  call    _lambda_7f94f01fc3cf1545aca7f938a37387d8___operator__
0x180005b6b  mov     ebx, eax
0x180005b6d  mov     rcx, [rsp+28h+Binding]; void *
0x180005b72  test    eax, eax
0x180005b74  js      short loc_180005BEA
0x180005b76  test    rcx, rcx
0x180005b79  jz      short loc_180005B81
0x180005b7b  call    ?_ReleaseInterface@@YAJPEAX@Z; _ReleaseInterface(void *)
0x180005b80  nop
0x180005b81  xor     eax, eax
0x180005b83  mov     rbx, [rsp+28h+arg_0]
0x180005b88  add     rsp, 20h
0x180005b8c  pop     rdi
0x180005b8d  retn
0x180005b8e  mov     rcx, [rsp+28h]; this
0x180005b93  mov     r9d, ebx; char *
0x180005b96  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180005b9d  mov     edx, 0B1h; void *
0x180005ba2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005ba7  nop
0x180005ba8  mov     rcx, [rsp+28h+Binding]; void *
0x180005bad  test    rcx, rcx
0x180005bb0  jnz     short loc_180005BE2
0x180005bb2  mov     eax, ebx
0x180005bb4  jmp     short loc_180005B83
0x180005bb6  mov     rcx, [rsp+28h]; this
0x180005bbb  mov     r9d, ebx; char *
0x180005bbe  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180005bc5  mov     edx, 0AEh; void *
0x180005bca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005bcf  nop
0x180005bd0  mov     rcx, [rsp+28h+Binding]; void *
0x180005bd5  test    rcx, rcx
0x180005bd8  jz      short loc_180005BB2
0x180005bda  call    ?_ReleaseInterface@@YAJPEAX@Z; _ReleaseInterface(void *)
0x180005bdf  nop
0x180005be0  jmp     short loc_180005BB2
0x180005be2  call    ?_ReleaseInterface@@YAJPEAX@Z; _ReleaseInterface(void *)
0x180005be7  nop
0x180005be8  jmp     short loc_180005BB2
0x180005bea  test    rcx, rcx
0x180005bed  jz      short loc_180005BB2
0x180005bef  call    ?_ReleaseInterface@@YAJPEAX@Z; _ReleaseInterface(void *)
0x180005bf4  nop
0x180005bf5  jmp     short loc_180005BB2
```
