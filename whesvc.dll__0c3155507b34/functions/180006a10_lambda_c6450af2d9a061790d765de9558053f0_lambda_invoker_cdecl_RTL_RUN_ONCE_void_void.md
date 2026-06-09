# _lambda_c6450af2d9a061790d765de9558053f0_::_lambda_invoker_cdecl_(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180006a10`
- end: `0x180006a80`
- name: `?_lambda_invoker_cdecl_@_lambda_c6450af2d9a061790d765de9558053f0_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `112`
- prototype: `__int64 __fastcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006a10`
- `0x180009d78`

## import_xrefs

- `combase!__imp_CoGetSharedServiceId` at `0x180006a5e`
- `combase!__imp_CoGetSharedServiceId` at `0x180006a5e`

## pseudocode

```c
__int64 __fastcall _lambda_c6450af2d9a061790d765de9558053f0_::_lambda_invoker_cdecl_(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  int SharedServiceId; // eax
  void *v4; // rdx
  __int64 v5; // r8
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  byte_180034E68 = 1;
  Microsoft::WRL::Details::ModuleBase::module_ = (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<wil::SvchostModule,1,int>::instance_;
  qword_180034E50 = 0;
  Microsoft::WRL::Details::StaticStorage<wil::SvchostModule,1,int>::instance_ = (__int64)&wil::SvchostModule::`vftable';
  qword_180034E58 = 0;
  dword_180034E60 = 0;
  SharedServiceId = CoGetSharedServiceId(&dword_180034E60, Parameter, Context);
  if ( SharedServiceId < 0 )
    wil::details::in1diag3::_FailFast_Hr(retaddr, v4, v5, (const char *)(unsigned int)SharedServiceId, v7);
  return 1;
}

```

## disassembly

```asm
0x180006a10  sub     rsp, 28h
0x180006a14  lea     rax, ?instance_@?$StaticStorage@VSvchostModule@wil@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<wil::SvchostModule,1,int> Microsoft::WRL::Details::StaticStorage<wil::SvchostModule,1,int>::instance_
0x180006a1b  mov     cs:byte_180034E68, 1
0x180006a22  mov     cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA, rax; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180006a29  lea     rcx, dword_180034E60
0x180006a30  lea     rax, ??_7SvchostModule@wil@@6B@; const wil::SvchostModule::`vftable'
0x180006a37  mov     cs:qword_180034E50, 0
0x180006a42  mov     cs:?instance_@?$StaticStorage@VSvchostModule@wil@@$00H@Details@WRL@Microsoft@@0V1234@A, rax; Microsoft::WRL::Details::StaticStorage<wil::SvchostModule,1,int> Microsoft::WRL::Details::StaticStorage<wil::SvchostModule,1,int>::instance_
0x180006a49  mov     cs:qword_180034E58, 0
0x180006a54  mov     cs:dword_180034E60, 0
0x180006a5e  call    cs:__imp_CoGetSharedServiceId
0x180006a64  test    eax, eax
0x180006a66  js      short loc_180006A72
0x180006a68  mov     eax, 1
0x180006a6d  add     rsp, 28h
0x180006a71  retn
0x180006a72  mov     rcx, [rsp+28h]; this
0x180006a77  mov     r9d, eax; char *
0x180006a7a  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
