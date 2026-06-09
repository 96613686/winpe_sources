# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)

- ea: `0x180018730`
- end: `0x18001877f`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012db8`
- `0x180012e80`
- `0x180014aec`
- `0x180014b8c`
- `0x180016e90`
- `0x180018f90`

## callees

- `0x180018730`
- `0x180019690`
- `0x180029010`

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
0x180018730  push    rbx
0x180018732  sub     rsp, 20h
0x180018736  mov     r10, rcx
0x180018739  add     rcx, 0Ch; this
0x18001873d  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x180018742  mov     ebx, eax
0x180018744  test    eax, eax
0x180018746  jnz     short loc_180018777
0x180018748  test    r10, r10
0x18001874b  jz      short loc_18001875F
0x18001874d  mov     rdx, [r10]
0x180018750  mov     rcx, r10
0x180018753  mov     rax, [rdx+20h]
0x180018757  lea     edx, [rbx+1]
0x18001875a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001875f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180018766  test    rcx, rcx
0x180018769  jz      short loc_180018777
0x18001876b  mov     rax, [rcx]
0x18001876e  mov     rax, [rax+10h]
0x180018772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018777  mov     eax, ebx
0x180018779  add     rsp, 20h
0x18001877d  pop     rbx
0x18001877e  retn
```
