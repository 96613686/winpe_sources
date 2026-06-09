# InvokeUserProfileRPC__lambda_c3e8d726eb567336769114f33ed11b9b_

- ea: `0x180012fa0`
- end: `0x180013027`
- name: `InvokeUserProfileRPC__lambda_c3e8d726eb567336769114f33ed11b9b___`
- size: `135`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009f74`

## callees

- `0x1800063d8`
- `0x1800064d0`
- `0x180006798`
- `0x18000db08`
- `0x180012fa0`
- `0x180013984`

## string_xrefs

- `0x180012fe2`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
__int64 __fastcall InvokeUserProfileRPC__lambda_c3e8d726eb567336769114f33ed11b9b_(__int64 a1, unsigned __int16 *a2)
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
  v6 = lambda_c3e8d726eb567336769114f33ed11b9b_::operator()(a1, Binding);
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
0x180012fa0  mov     [rsp+arg_0], rbx
0x180012fa5  push    rdi; int
0x180012fa6  sub     rsp, 20h
0x180012faa  mov     rdi, rcx
0x180012fad  mov     [rsp+28h+Binding], 0
0x180012fb6  lea     rcx, [rsp+28h+Binding]; Binding
0x180012fbb  call    ?_GetInterface@@YAJPEAPEAXPEAG@Z; _GetInterface(void * *,ushort *)
0x180012fc0  mov     ebx, eax
0x180012fc2  test    eax, eax
0x180012fc4  jns     short loc_180012FCD
0x180012fc6  mov     edx, 0AEh
0x180012fcb  jmp     short loc_180012FE2
0x180012fcd  mov     rcx, [rsp+28h+Binding]; void *
0x180012fd2  call    ?_RegisterClientAuthInfo@@YAJPEAX@Z; _RegisterClientAuthInfo(void *)
0x180012fd7  mov     ebx, eax
0x180012fd9  test    eax, eax
0x180012fdb  jns     short loc_180012FF8
0x180012fdd  mov     edx, 0B1h; void *
0x180012fe2  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180012fe9  mov     r9d, eax; char *
0x180012fec  mov     rcx, [rsp+28h]; this
0x180012ff1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ff6  jmp     short loc_18001300F
0x180012ff8  mov     rdx, [rsp+28h+Binding]
0x180012ffd  mov     rcx, rdi
0x180013000  call    _lambda_c3e8d726eb567336769114f33ed11b9b___operator__
0x180013005  test    eax, eax
0x180013007  jns     short loc_18001300D
0x180013009  mov     ebx, eax
0x18001300b  jmp     short loc_18001300F
0x18001300d  xor     ebx, ebx
0x18001300f  lea     rcx, [rsp+28h+Binding]
0x180013014  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?_ReleaseInterface@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&_ReleaseInterface(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&_ReleaseInterface(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180013019  mov     eax, ebx
0x18001301b  mov     rbx, [rsp+28h+arg_0]
0x180013020  add     rsp, 20h
0x180013024  pop     rdi
0x180013025  retn
```
