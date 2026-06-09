# _lambda_c6450af2d9a061790d765de9558053f0_::_lambda_invoker_cdecl_(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180003c50`
- end: `0x180003ccc`
- name: `?_lambda_invoker_cdecl_@_lambda_c6450af2d9a061790d765de9558053f0_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `124`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003c50`
- `0x18000e460`

## import_xrefs

- `combase!__imp_CoGetSharedServiceId` at `0x180003c9e`
- `combase!__imp_CoGetSharedServiceId` at `0x180003c9e`

## string_xrefs

- `0x180003cb7`: `onecore\internal\sdk\inc\wil\wrlservicecomponent.h`

## pseudocode

```c
__int64 __fastcall _lambda_c6450af2d9a061790d765de9558053f0_::_lambda_invoker_cdecl_(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  int SharedServiceId; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  byte_18009D158 = 1;
  Microsoft::WRL::Details::ModuleBase::module_ = (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<wil::SvchostModule,1,int>::instance_;
  qword_18009D140 = 0;
  Microsoft::WRL::Details::StaticStorage<wil::SvchostModule,1,int>::instance_ = (__int64)&wil::SvchostModule::`vftable';
  qword_18009D148 = 0;
  dword_18009D150 = 0;
  SharedServiceId = CoGetSharedServiceId(&dword_18009D150, Parameter, Context);
  if ( SharedServiceId < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\wrlservicecomponent.h",
      (const char *)(unsigned int)SharedServiceId,
      v5);
  return 1;
}

```

## disassembly

```asm
0x180003c50  sub     rsp, 28h
0x180003c54  lea     rax, ?instance_@?$StaticStorage@VSvchostModule@wil@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<wil::SvchostModule,1,int> Microsoft::WRL::Details::StaticStorage<wil::SvchostModule,1,int>::instance_
0x180003c5b  mov     cs:byte_18009D158, 1
0x180003c62  mov     cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA, rax; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180003c69  lea     rcx, dword_18009D150
0x180003c70  lea     rax, ??_7SvchostModule@wil@@6B@; const wil::SvchostModule::`vftable'
0x180003c77  mov     cs:qword_18009D140, 0
0x180003c82  mov     cs:?instance_@?$StaticStorage@VSvchostModule@wil@@$00H@Details@WRL@Microsoft@@0V1234@A, rax; Microsoft::WRL::Details::StaticStorage<wil::SvchostModule,1,int> Microsoft::WRL::Details::StaticStorage<wil::SvchostModule,1,int>::instance_
0x180003c89  mov     cs:qword_18009D148, 0
0x180003c94  mov     cs:dword_18009D150, 0
0x180003c9e  call    cs:__imp_CoGetSharedServiceId
0x180003ca4  test    eax, eax
0x180003ca6  js      short loc_180003CB2
0x180003ca8  mov     eax, 1
0x180003cad  add     rsp, 28h
0x180003cb1  retn
0x180003cb2  mov     rcx, [rsp+28h]; this
0x180003cb7  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\wrlse"...
0x180003cbe  mov     r9d, eax; char *
0x180003cc1  mov     edx, 37h ; '7'; void *
0x180003cc6  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
