# InvokeUserProfileRPC__lambda_34c279a10b2d290b68eee06320d75c21_

- ea: `0x180012f10`
- end: `0x180012f97`
- name: `InvokeUserProfileRPC__lambda_34c279a10b2d290b68eee06320d75c21___`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014c70`

## callees

- `0x1800063d8`
- `0x1800064d0`
- `0x180006798`
- `0x18000db08`
- `0x180012f10`
- `0x180013748`

## string_xrefs

- `0x180012f52`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InvokeUserProfileRPC__lambda_34c279a10b2d290b68eee06320d75c21_(__int64 a1, unsigned __int16 *a2)
{
  signed int Interface; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp+10h] BYREF

  Binding = 0;
  Interface = _GetInterface(&Binding, a2);
  v4 = Interface;
  if ( Interface < 0 )
  {
    v5 = 174;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
      (const char *)(unsigned int)Interface,
      v8);
    goto LABEL_9;
  }
  Interface = _RegisterClientAuthInfo(Binding);
  v4 = Interface;
  if ( Interface < 0 )
  {
    v5 = 177;
    goto LABEL_5;
  }
  v6 = lambda_34c279a10b2d290b68eee06320d75c21_::operator()(a1, Binding);
  if ( v6 >= 0 )
    v4 = 0;
  else
    v4 = v6;
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long _ReleaseInterface(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long _ReleaseInterface(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Binding);
  return v4;
}

```

## disassembly

```asm
0x180012f10  mov     [rsp+arg_0], rbx
0x180012f15  push    rdi; int
0x180012f16  sub     rsp, 20h
0x180012f1a  mov     rdi, rcx
0x180012f1d  mov     [rsp+28h+Binding], 0
0x180012f26  lea     rcx, [rsp+28h+Binding]; Binding
0x180012f2b  call    ?_GetInterface@@YAJPEAPEAXPEAG@Z; _GetInterface(void * *,ushort *)
0x180012f30  mov     ebx, eax
0x180012f32  test    eax, eax
0x180012f34  jns     short loc_180012F3D
0x180012f36  mov     edx, 0AEh
0x180012f3b  jmp     short loc_180012F52
0x180012f3d  mov     rcx, [rsp+28h+Binding]; void *
0x180012f42  call    ?_RegisterClientAuthInfo@@YAJPEAX@Z; _RegisterClientAuthInfo(void *)
0x180012f47  mov     ebx, eax
0x180012f49  test    eax, eax
0x180012f4b  jns     short loc_180012F68
0x180012f4d  mov     edx, 0B1h; void *
0x180012f52  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180012f59  mov     r9d, eax; char *
0x180012f5c  mov     rcx, [rsp+28h]; this
0x180012f61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f66  jmp     short loc_180012F7F
0x180012f68  mov     rdx, [rsp+28h+Binding]
0x180012f6d  mov     rcx, rdi
0x180012f70  call    _lambda_34c279a10b2d290b68eee06320d75c21___operator__
0x180012f75  test    eax, eax
0x180012f77  jns     short loc_180012F7D
0x180012f79  mov     ebx, eax
0x180012f7b  jmp     short loc_180012F7F
0x180012f7d  xor     ebx, ebx
0x180012f7f  lea     rcx, [rsp+28h+Binding]
0x180012f84  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?_ReleaseInterface@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&_ReleaseInterface(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&_ReleaseInterface(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180012f89  mov     eax, ebx
0x180012f8b  mov     rbx, [rsp+28h+arg_0]
0x180012f90  add     rsp, 20h
0x180012f94  pop     rdi
0x180012f95  retn
```
