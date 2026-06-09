# Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_b84298806a3ade5bf2f206695eab1b51_ &>,_lambda_b84298806a3ade5bf2f206695eab1b51_ &>(_lambda_b84298806a3ade5bf2f206695eab1b51_ &)

- ea: `0x14004ca38`
- end: `0x14004cae4`
- name: `??$Make@V?$CTaskWrapper@AEAV_lambda_b84298806a3ade5bf2f206695eab1b51_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_b84298806a3ade5bf2f206695eab1b51_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_b84298806a3ade5bf2f206695eab1b51_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_b84298806a3ade5bf2f206695eab1b51_@@@Z`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140058a48`

## callees

- `0x14000fafc`
- `0x14004ca38`
- `0x140051fdc`
- `0x140052c14`
- `0x14005a250`
- `0x140067010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_b84298806a3ade5bf2f206695eab1b51_ &>,_lambda_b84298806a3ade5bf2f206695eab1b51_ &>(
        _QWORD *a1,
        _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  _QWORD *v7; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  v7 = v4;
  if ( v4 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(v4);
    *v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v5[2] = *a2;
    *v5 = &Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_b84298806a3ade5bf2f206695eab1b51_ &>::`vftable';
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
    *a1 = v5;
    v7 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>::~MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>(&v7);
  return a1;
}

```

## disassembly

```asm
0x14004ca38  mov     [rsp+arg_8], rbx
0x14004ca3d  mov     [rsp+arg_10], rsi
0x14004ca42  push    rdi
0x14004ca43  sub     rsp, 20h
0x14004ca47  mov     rsi, rdx
0x14004ca4a  mov     rdi, rcx
0x14004ca4d  mov     qword ptr [rcx], 0
0x14004ca54  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14004ca5b  mov     ecx, 18h; unsigned __int64
0x14004ca60  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14004ca65  mov     rbx, rax
0x14004ca68  mov     [rsp+28h+arg_0], rax
0x14004ca6d  test    rax, rax
0x14004ca70  jz      short loc_14004CAC7
0x14004ca72  mov     rcx, rax
0x14004ca75  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(void)
0x14004ca7a  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable'
0x14004ca81  mov     [rbx], rcx
0x14004ca84  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14004ca8b  test    rcx, rcx
0x14004ca8e  jz      short loc_14004CA9D
0x14004ca90  mov     rax, [rcx]
0x14004ca93  mov     rax, [rax+8]
0x14004ca97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ca9c  nop
0x14004ca9d  mov     rax, [rsi]
0x14004caa0  mov     [rbx+10h], rax
0x14004caa4  lea     rax, ??_7?$CTaskWrapper@AEAV_lambda_b84298806a3ade5bf2f206695eab1b51_@@@ComTaskPool@Internal@Windows@@6B@; const Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_b84298806a3ade5bf2f206695eab1b51_ &>::`vftable'
0x14004caab  mov     [rbx], rax
0x14004caae  mov     rcx, [rdi]
0x14004cab1  test    rcx, rcx
0x14004cab4  jz      short loc_14004CABB
0x14004cab6  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x14004cabb  mov     [rdi], rbx
0x14004cabe  mov     [rsp+28h+arg_0], 0
0x14004cac7  lea     rcx, [rsp+28h+arg_0]
0x14004cacc  call    ??1?$MakeAllocator@V?$CBuffer@V_lambda_8fcabb03306c9f8765c03020018d7da6_@@UDefaultMarshaler@Streams@Storage@Windows@@@Streams@Storage@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>::~MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>(void)
0x14004cad1  mov     rax, rdi
0x14004cad4  mov     rbx, [rsp+28h+arg_8]
0x14004cad9  mov     rsi, [rsp+28h+arg_10]
0x14004cade  add     rsp, 20h
0x14004cae2  pop     rdi
0x14004cae3  retn
```
