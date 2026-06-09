# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Storage::Pickers::IFileOpenPicker>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Pickers::IFileOpenPicker>>)

- ea: `0x18000c824`
- end: `0x18000c8bc`
- name: `??$ActivateInstance@V?$ComPtr@UIFileOpenPicker@Pickers@Storage@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIFileOpenPicker@Pickers@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011b74`

## callees

- `0x1800043a4`
- `0x18000c824`
- `0x18001e394`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000c854`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000c854`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Storage::Pickers::IFileOpenPicker>>(
        __int64 a1,
        _QWORD *a2)
{
  int v4; // edi
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a2);
  *a2 = 0;
  v6 = 0;
  v4 = RoActivateInstance(a1, &v6);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&GUID_2ca8278a_12c5_4c5f_8977_94547793c241, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v6;
    }
    else
    {
      v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v6)(
             v6,
             &GUID_2ca8278a_12c5_4c5f_8977_94547793c241,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c824  mov     [rsp+arg_0], rbx
0x18000c829  push    rdi
0x18000c82a  sub     rsp, 20h
0x18000c82e  mov     rdi, rcx
0x18000c831  mov     rbx, rdx
0x18000c834  mov     rcx, rdx
0x18000c837  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000c83c  lea     rdx, [rsp+28h+arg_8]
0x18000c841  mov     qword ptr [rbx], 0
0x18000c848  mov     rcx, rdi
0x18000c84b  mov     [rsp+28h+arg_8], 0
0x18000c854  call    cs:__imp_RoActivateInstance
0x18000c85a  mov     edi, eax
0x18000c85c  test    eax, eax
0x18000c85e  js      short loc_18000C8AF
0x18000c860  mov     r8d, 10h; Size
0x18000c866  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18000c86d  lea     rcx, _GUID_2ca8278a_12c5_4c5f_8977_94547793c241; Buf1
0x18000c874  call    memcmp_0
0x18000c879  mov     rcx, [rsp+28h+arg_8]
0x18000c87e  test    eax, eax
0x18000c880  jnz     short loc_18000C887
0x18000c882  mov     [rbx], rcx
0x18000c885  jmp     short loc_18000C8AF
0x18000c887  mov     rax, [rcx]
0x18000c88a  lea     rdx, _GUID_2ca8278a_12c5_4c5f_8977_94547793c241
0x18000c891  mov     r8, rbx
0x18000c894  mov     rax, [rax]
0x18000c897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c89c  mov     rcx, [rsp+28h+arg_8]
0x18000c8a1  mov     edi, eax
0x18000c8a3  mov     rax, [rcx]
0x18000c8a6  mov     rax, [rax+10h]
0x18000c8aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8af  mov     rbx, [rsp+28h+arg_0]
0x18000c8b4  mov     eax, edi
0x18000c8b6  add     rsp, 20h
0x18000c8ba  pop     rdi
0x18000c8bb  retn
```
