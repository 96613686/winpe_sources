# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)

- ea: `0x14005a250`
- end: `0x14005a29f`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004ca38`
- `0x14004caec`
- `0x140052c30`
- `0x1400572a0`
- `0x140058a48`

## callees

- `0x14005a250`
- `0x14005abdc`
- `0x140067010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(
        __int64 a1,
        volatile int *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r10

  v2 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(a1 + 12), a2);
  if ( !v2 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 32LL))(v3, v2 + 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x14005a250  push    rbx
0x14005a252  sub     rsp, 20h
0x14005a256  mov     r10, rcx
0x14005a259  add     rcx, 0Ch; this
0x14005a25d  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x14005a262  mov     ebx, eax
0x14005a264  test    eax, eax
0x14005a266  jnz     short loc_14005A297
0x14005a268  test    r10, r10
0x14005a26b  jz      short loc_14005A27F
0x14005a26d  mov     rdx, [r10]
0x14005a270  mov     rcx, r10
0x14005a273  mov     rax, [rdx+20h]
0x14005a277  lea     edx, [rbx+1]
0x14005a27a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a27f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14005a286  test    rcx, rcx
0x14005a289  jz      short loc_14005A297
0x14005a28b  mov     rax, [rcx]
0x14005a28e  mov     rax, [rax+10h]
0x14005a292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a297  mov     eax, ebx
0x14005a299  add     rsp, 20h
0x14005a29d  pop     rbx
0x14005a29e  retn
```
