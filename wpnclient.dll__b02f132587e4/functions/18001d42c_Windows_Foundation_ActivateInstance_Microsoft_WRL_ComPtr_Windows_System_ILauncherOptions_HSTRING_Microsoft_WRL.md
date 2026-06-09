# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::System::ILauncherOptions>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::ILauncherOptions>>)

- ea: `0x18001d42c`
- end: `0x18001d4c4`
- name: `??$ActivateInstance@V?$ComPtr@UILauncherOptions@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILauncherOptions@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d0d0`

## callees

- `0x180005670`
- `0x18001d42c`
- `0x1800307c0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001d45c`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001d45c`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::System::ILauncherOptions>>(
        __int64 a1,
        __int64 *a2)
{
  int v4; // edi
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
  *a2 = 0;
  v6 = 0;
  v4 = RoActivateInstance(a1, &v6);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&GUID_bafa21d8_b071_4cd8_853e_341203e557d3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v6;
    }
    else
    {
      v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v6)(
             v6,
             &GUID_bafa21d8_b071_4cd8_853e_341203e557d3,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001d42c  mov     [rsp+arg_0], rbx
0x18001d431  push    rdi
0x18001d432  sub     rsp, 20h
0x18001d436  mov     rbx, rdx
0x18001d439  mov     rdi, rcx
0x18001d43c  mov     rcx, rdx
0x18001d43f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d444  mov     qword ptr [rbx], 0
0x18001d44b  mov     [rsp+28h+arg_8], 0
0x18001d454  lea     rdx, [rsp+28h+arg_8]
0x18001d459  mov     rcx, rdi
0x18001d45c  call    cs:__imp_RoActivateInstance
0x18001d462  mov     edi, eax
0x18001d464  test    eax, eax
0x18001d466  js      short loc_18001D4B7
0x18001d468  mov     r8d, 10h; Size
0x18001d46e  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18001d475  lea     rcx, _GUID_bafa21d8_b071_4cd8_853e_341203e557d3; Buf1
0x18001d47c  call    memcmp_0
0x18001d481  mov     rcx, [rsp+28h+arg_8]
0x18001d486  test    eax, eax
0x18001d488  jnz     short loc_18001D48F
0x18001d48a  mov     [rbx], rcx
0x18001d48d  jmp     short loc_18001D4B7
0x18001d48f  mov     rax, [rcx]
0x18001d492  mov     r8, rbx
0x18001d495  lea     rdx, _GUID_bafa21d8_b071_4cd8_853e_341203e557d3
0x18001d49c  mov     rax, [rax]
0x18001d49f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4a4  mov     edi, eax
0x18001d4a6  mov     rcx, [rsp+28h+arg_8]
0x18001d4ab  mov     rax, [rcx]
0x18001d4ae  mov     rax, [rax+10h]
0x18001d4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4b7  mov     eax, edi
0x18001d4b9  mov     rbx, [rsp+28h+arg_0]
0x18001d4be  add     rsp, 20h
0x18001d4c2  pop     rdi
0x18001d4c3  retn
```
