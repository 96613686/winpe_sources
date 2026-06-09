# InvokeUserProfileRPC__lambda_c85f50188a6ad7c456372eb6afbcdebb_

- ea: `0x180013030`
- end: `0x1800130b7`
- name: `InvokeUserProfileRPC__lambda_c85f50188a6ad7c456372eb6afbcdebb___`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014e30`

## callees

- `0x1800063d8`
- `0x1800064d0`
- `0x180006798`
- `0x18000db08`
- `0x180013030`
- `0x180013a54`

## string_xrefs

- `0x180013072`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
__int64 __fastcall InvokeUserProfileRPC__lambda_c85f50188a6ad7c456372eb6afbcdebb_(__int64 a1, unsigned __int16 *a2)
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
  v6 = lambda_c85f50188a6ad7c456372eb6afbcdebb_::operator()(a1, Binding);
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
0x180013030  mov     [rsp+arg_0], rbx
0x180013035  push    rdi; int
0x180013036  sub     rsp, 20h
0x18001303a  mov     rdi, rcx
0x18001303d  mov     [rsp+28h+Binding], 0
0x180013046  lea     rcx, [rsp+28h+Binding]; Binding
0x18001304b  call    ?_GetInterface@@YAJPEAPEAXPEAG@Z; _GetInterface(void * *,ushort *)
0x180013050  mov     ebx, eax
0x180013052  test    eax, eax
0x180013054  jns     short loc_18001305D
0x180013056  mov     edx, 0AEh
0x18001305b  jmp     short loc_180013072
0x18001305d  mov     rcx, [rsp+28h+Binding]; void *
0x180013062  call    ?_RegisterClientAuthInfo@@YAJPEAX@Z; _RegisterClientAuthInfo(void *)
0x180013067  mov     ebx, eax
0x180013069  test    eax, eax
0x18001306b  jns     short loc_180013088
0x18001306d  mov     edx, 0B1h; void *
0x180013072  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180013079  mov     r9d, eax; char *
0x18001307c  mov     rcx, [rsp+28h]; this
0x180013081  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013086  jmp     short loc_18001309F
0x180013088  mov     rdx, [rsp+28h+Binding]
0x18001308d  mov     rcx, rdi
0x180013090  call    _lambda_c85f50188a6ad7c456372eb6afbcdebb___operator__
0x180013095  test    eax, eax
0x180013097  jns     short loc_18001309D
0x180013099  mov     ebx, eax
0x18001309b  jmp     short loc_18001309F
0x18001309d  xor     ebx, ebx
0x18001309f  lea     rcx, [rsp+28h+Binding]
0x1800130a4  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?_ReleaseInterface@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&_ReleaseInterface(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&_ReleaseInterface(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800130a9  mov     eax, ebx
0x1800130ab  mov     rbx, [rsp+28h+arg_0]
0x1800130b0  add     rsp, 20h
0x1800130b4  pop     rdi
0x1800130b5  retn
```
