# InvokeUserProfileRPC__lambda_c85f50188a6ad7c456372eb6afbcdebb_

- ea: `0x180012064`
- end: `0x1800120ea`
- name: `InvokeUserProfileRPC__lambda_c85f50188a6ad7c456372eb6afbcdebb___`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013d50`

## callees

- `0x180005c00`
- `0x180005ce0`
- `0x180005fc8`
- `0x18000cea0`
- `0x180012064`
- `0x180012998`

## string_xrefs

- `0x1800120a6`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
__int64 __fastcall InvokeUserProfileRPC__lambda_c85f50188a6ad7c456372eb6afbcdebb_(__int64 a1, unsigned __int16 *a2)
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
0x180012064  mov     [rsp+arg_0], rbx
0x180012069  push    rdi; int
0x18001206a  sub     rsp, 20h
0x18001206e  mov     rdi, rcx
0x180012071  mov     [rsp+28h+Binding], 0
0x18001207a  lea     rcx, [rsp+28h+Binding]; Binding
0x18001207f  call    ?_GetInterface@@YAJPEAPEAXPEAG@Z; _GetInterface(void * *,ushort *)
0x180012084  mov     ebx, eax
0x180012086  test    eax, eax
0x180012088  jns     short loc_180012091
0x18001208a  mov     edx, 0AEh
0x18001208f  jmp     short loc_1800120A6
0x180012091  mov     rcx, [rsp+28h+Binding]; void *
0x180012096  call    ?_RegisterClientAuthInfo@@YAJPEAX@Z; _RegisterClientAuthInfo(void *)
0x18001209b  mov     ebx, eax
0x18001209d  test    eax, eax
0x18001209f  jns     short loc_1800120BC
0x1800120a1  mov     edx, 0B1h; void *
0x1800120a6  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800120ad  mov     r9d, eax; char *
0x1800120b0  mov     rcx, [rsp+28h]; this
0x1800120b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800120ba  jmp     short loc_1800120D3
0x1800120bc  mov     rdx, [rsp+28h+Binding]
0x1800120c1  mov     rcx, rdi
0x1800120c4  call    _lambda_c85f50188a6ad7c456372eb6afbcdebb___operator__
0x1800120c9  test    eax, eax
0x1800120cb  jns     short loc_1800120D1
0x1800120cd  mov     ebx, eax
0x1800120cf  jmp     short loc_1800120D3
0x1800120d1  xor     ebx, ebx
0x1800120d3  lea     rcx, [rsp+28h+Binding]
0x1800120d8  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?_ReleaseInterface@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&_ReleaseInterface(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&_ReleaseInterface(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800120dd  mov     eax, ebx
0x1800120df  mov     rbx, [rsp+28h+arg_0]
0x1800120e4  add     rsp, 20h
0x1800120e8  pop     rdi
0x1800120e9  retn
```
