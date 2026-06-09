# CSharedBitmap::~CSharedBitmap(void)

- ea: `0x180027304`
- end: `0x180027394`
- name: `??1CSharedBitmap@@AEAA@XZ`
- size: `144`
- prototype: `void __fastcall(CSharedBitmap *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800272c0`

## callees

- `0x180027304`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027367`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027367`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002733a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002733a`
- `OLEAUT32!__imp_SysFreeString` at `0x180027371`
- `OLEAUT32!__imp_SysFreeString` at `0x180027371`
- `GDI32!DeleteObject` at `0x180027320`
- `GDI32!DeleteObject` at `0x180027320`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSharedBitmap::~CSharedBitmap(CSharedBitmap *this)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &CSharedBitmap::`vftable';
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
    DeleteObject(v2);
  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_180062B08 = 1;
  (*(void (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                 + 16LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
  v3 = (void *)*((_QWORD *)this + 6);
  if ( v3 )
    CloseHandle(v3);
  SysFreeString(*((BSTR *)this + 5));
  v4 = *((_QWORD *)this + 4);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
}

```

## disassembly

```asm
0x180027304  push    rbx
0x180027306  sub     rsp, 20h
0x18002730a  mov     rbx, rcx
0x18002730d  lea     rax, ??_7CSharedBitmap@@6B@; const CSharedBitmap::`vftable'
0x180027314  mov     [rcx], rax
0x180027317  mov     rcx, [rcx+10h]; ho
0x18002731b  test    rcx, rcx
0x18002731e  jz      short loc_180027326
0x180027320  call    cs:__imp_DeleteObject
0x180027326  xor     r9d, r9d; Context
0x180027329  xor     r8d, r8d; Parameter
0x18002732c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180027333  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18002733a  call    cs:__imp_InitOnceExecuteOnce
0x180027340  mov     cs:byte_180062B08, 1
0x180027347  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18002734e  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180027355  mov     rax, [rax+10h]
0x180027359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002735e  mov     rcx, [rbx+30h]; hObject
0x180027362  test    rcx, rcx
0x180027365  jz      short loc_18002736D
0x180027367  call    cs:__imp_CloseHandle
0x18002736d  mov     rcx, [rbx+28h]; bstrString
0x180027371  call    cs:__imp_SysFreeString
0x180027377  nop
0x180027378  mov     rcx, [rbx+20h]
0x18002737c  test    rcx, rcx
0x18002737f  jz      short loc_18002738E
0x180027381  mov     rax, [rcx]
0x180027384  mov     rax, [rax+10h]
0x180027388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002738d  nop
0x18002738e  add     rsp, 20h
0x180027392  pop     rbx
0x180027393  retn
```
