# InvokeUserProfileRPC__lambda_c3e8d726eb567336769114f33ed11b9b_

- ea: `0x180011fd8`
- end: `0x18001205e`
- name: `InvokeUserProfileRPC__lambda_c3e8d726eb567336769114f33ed11b9b___`
- size: `134`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000965c`

## callees

- `0x180005c00`
- `0x180005ce0`
- `0x180005fc8`
- `0x18000cea0`
- `0x180011fd8`
- `0x1800128cc`

## string_xrefs

- `0x18001201a`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
__int64 __fastcall InvokeUserProfileRPC__lambda_c3e8d726eb567336769114f33ed11b9b_(__int64 a1, unsigned __int16 *a2)
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
0x180011fd8  mov     [rsp+arg_0], rbx
0x180011fdd  push    rdi; int
0x180011fde  sub     rsp, 20h
0x180011fe2  mov     rdi, rcx
0x180011fe5  mov     [rsp+28h+Binding], 0
0x180011fee  lea     rcx, [rsp+28h+Binding]; Binding
0x180011ff3  call    ?_GetInterface@@YAJPEAPEAXPEAG@Z; _GetInterface(void * *,ushort *)
0x180011ff8  mov     ebx, eax
0x180011ffa  test    eax, eax
0x180011ffc  jns     short loc_180012005
0x180011ffe  mov     edx, 0AEh
0x180012003  jmp     short loc_18001201A
0x180012005  mov     rcx, [rsp+28h+Binding]; void *
0x18001200a  call    ?_RegisterClientAuthInfo@@YAJPEAX@Z; _RegisterClientAuthInfo(void *)
0x18001200f  mov     ebx, eax
0x180012011  test    eax, eax
0x180012013  jns     short loc_180012030
0x180012015  mov     edx, 0B1h; void *
0x18001201a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180012021  mov     r9d, eax; char *
0x180012024  mov     rcx, [rsp+28h]; this
0x180012029  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001202e  jmp     short loc_180012047
0x180012030  mov     rdx, [rsp+28h+Binding]
0x180012035  mov     rcx, rdi
0x180012038  call    _lambda_c3e8d726eb567336769114f33ed11b9b___operator__
0x18001203d  test    eax, eax
0x18001203f  jns     short loc_180012045
0x180012041  mov     ebx, eax
0x180012043  jmp     short loc_180012047
0x180012045  xor     ebx, ebx
0x180012047  lea     rcx, [rsp+28h+Binding]
0x18001204c  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?_ReleaseInterface@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&_ReleaseInterface(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&_ReleaseInterface(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180012051  mov     eax, ebx
0x180012053  mov     rbx, [rsp+28h+arg_0]
0x180012058  add     rsp, 20h
0x18001205c  pop     rdi
0x18001205d  retn
```
