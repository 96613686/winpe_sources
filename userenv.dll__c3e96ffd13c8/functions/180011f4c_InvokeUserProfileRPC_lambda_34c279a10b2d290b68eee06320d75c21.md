# InvokeUserProfileRPC__lambda_34c279a10b2d290b68eee06320d75c21_

- ea: `0x180011f4c`
- end: `0x180011fd2`
- name: `InvokeUserProfileRPC__lambda_34c279a10b2d290b68eee06320d75c21___`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013bc0`

## callees

- `0x180005c00`
- `0x180005ce0`
- `0x180005fc8`
- `0x18000cea0`
- `0x180011f4c`
- `0x18001274c`

## string_xrefs

- `0x180011f8e`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InvokeUserProfileRPC__lambda_34c279a10b2d290b68eee06320d75c21_(__int64 a1, unsigned __int16 *a2)
{
  signed int Interface; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
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
      (int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
      (const char *)(unsigned int)Interface);
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
0x180011f4c  mov     [rsp+arg_0], rbx
0x180011f51  push    rdi; int
0x180011f52  sub     rsp, 20h
0x180011f56  mov     rdi, rcx
0x180011f59  mov     [rsp+28h+Binding], 0
0x180011f62  lea     rcx, [rsp+28h+Binding]; Binding
0x180011f67  call    ?_GetInterface@@YAJPEAPEAXPEAG@Z; _GetInterface(void * *,ushort *)
0x180011f6c  mov     ebx, eax
0x180011f6e  test    eax, eax
0x180011f70  jns     short loc_180011F79
0x180011f72  mov     edx, 0AEh
0x180011f77  jmp     short loc_180011F8E
0x180011f79  mov     rcx, [rsp+28h+Binding]; void *
0x180011f7e  call    ?_RegisterClientAuthInfo@@YAJPEAX@Z; _RegisterClientAuthInfo(void *)
0x180011f83  mov     ebx, eax
0x180011f85  test    eax, eax
0x180011f87  jns     short loc_180011FA4
0x180011f89  mov     edx, 0B1h; void *
0x180011f8e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180011f95  mov     r9d, eax; char *
0x180011f98  mov     rcx, [rsp+28h]; this
0x180011f9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011fa2  jmp     short loc_180011FBB
0x180011fa4  mov     rdx, [rsp+28h+Binding]
0x180011fa9  mov     rcx, rdi
0x180011fac  call    _lambda_34c279a10b2d290b68eee06320d75c21___operator__
0x180011fb1  test    eax, eax
0x180011fb3  jns     short loc_180011FB9
0x180011fb5  mov     ebx, eax
0x180011fb7  jmp     short loc_180011FBB
0x180011fb9  xor     ebx, ebx
0x180011fbb  lea     rcx, [rsp+28h+Binding]
0x180011fc0  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?_ReleaseInterface@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&_ReleaseInterface(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&_ReleaseInterface(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180011fc5  mov     eax, ebx
0x180011fc7  mov     rbx, [rsp+28h+arg_0]
0x180011fcc  add     rsp, 20h
0x180011fd0  pop     rdi
0x180011fd1  retn
```
