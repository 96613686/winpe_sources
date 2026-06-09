# Microsoft::WRL::ComPtr<IWpnRegistrationEndpoint>::As<IWpnSystemRegistrationEndpoint>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWpnSystemRegistrationEndpoint>>)

- ea: `0x180015b5c`
- end: `0x180015ba5`
- name: `??$As@UIWpnSystemRegistrationEndpoint@@@?$ComPtr@UIWpnRegistrationEndpoint@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWpnSystemRegistrationEndpoint@@@WRL@Microsoft@@@Details@12@@Z`
- size: `73`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, __int64), __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016880`
- `0x180016bc0`

## callees

- `0x180006844`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IWpnRegistrationEndpoint>::As<IWpnSystemRegistrationEndpoint>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64),
        __int64 a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64); // rdi

  v3 = *a1;
  v4 = ***a1;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a2);
  return v4(v3, &GUID_7d85494e_d99e_493a_bf51_80d2c9feab49, a2);
}

```

## disassembly

```asm
0x180015b5c  mov     [rsp+arg_0], rbx
0x180015b61  mov     [rsp+arg_8], rsi
0x180015b66  push    rdi
0x180015b67  sub     rsp, 20h
0x180015b6b  mov     rbx, rdx
0x180015b6e  mov     rsi, [rcx]
0x180015b71  mov     rax, [rsi]
0x180015b74  mov     rdi, [rax]
0x180015b77  mov     rcx, rdx
0x180015b7a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180015b7f  mov     r8, rbx
0x180015b82  lea     rdx, _GUID_7d85494e_d99e_493a_bf51_80d2c9feab49
0x180015b89  mov     rcx, rsi
0x180015b8c  mov     rax, rdi
0x180015b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b94  nop
0x180015b95  mov     rbx, [rsp+28h+arg_0]
0x180015b9a  mov     rsi, [rsp+28h+arg_8]
0x180015b9f  add     rsp, 20h
0x180015ba3  pop     rdi
0x180015ba4  retn
```
