# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Notifications::IWpnToastActivator>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Notifications::IWpnToastActivator>>)

- ea: `0x1800137c4`
- end: `0x180013870`
- name: `??$ActivateInstance@V?$ComPtr@UIWpnToastActivator@Notifications@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWpnToastActivator@Notifications@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800082b8`
- `0x180026d70`

## callees

- `0x1800137c4`
- `0x1800307c0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180013808`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180013808`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Notifications::IWpnToastActivator>>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v4; // rcx
  int v5; // edi
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v4 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  *a2 = 0;
  v7 = 0;
  v5 = RoActivateInstance(a1, &v7);
  if ( v5 >= 0 )
  {
    if ( !memcmp_0(&GUID_6152e266_8805_4b1e_9fc9_4df263e44e8b, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v7;
    }
    else
    {
      v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v7)(
             v7,
             &GUID_6152e266_8805_4b1e_9fc9_4df263e44e8b,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800137c4  mov     [rsp+arg_0], rbx
0x1800137c9  push    rdi
0x1800137ca  sub     rsp, 20h
0x1800137ce  mov     rbx, rdx
0x1800137d1  mov     rdi, rcx
0x1800137d4  mov     rcx, [rdx]
0x1800137d7  test    rcx, rcx
0x1800137da  jz      short loc_1800137F0
0x1800137dc  mov     qword ptr [rdx], 0
0x1800137e3  mov     rax, [rcx]
0x1800137e6  mov     rax, [rax+10h]
0x1800137ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137ef  nop
0x1800137f0  mov     qword ptr [rbx], 0
0x1800137f7  mov     [rsp+28h+arg_8], 0
0x180013800  lea     rdx, [rsp+28h+arg_8]
0x180013805  mov     rcx, rdi
0x180013808  call    cs:__imp_RoActivateInstance
0x18001380e  mov     edi, eax
0x180013810  test    eax, eax
0x180013812  js      short loc_180013839
0x180013814  mov     r8d, 10h; Size
0x18001381a  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180013821  lea     rcx, _GUID_6152e266_8805_4b1e_9fc9_4df263e44e8b; Buf1
0x180013828  call    memcmp_0
0x18001382d  mov     rcx, [rsp+28h+arg_8]
0x180013832  test    eax, eax
0x180013834  jnz     short loc_180013846
0x180013836  mov     [rbx], rcx
0x180013839  mov     eax, edi
0x18001383b  mov     rbx, [rsp+28h+arg_0]
0x180013840  add     rsp, 20h
0x180013844  pop     rdi
0x180013845  retn
0x180013846  mov     rax, [rcx]
0x180013849  mov     r8, rbx
0x18001384c  lea     rdx, _GUID_6152e266_8805_4b1e_9fc9_4df263e44e8b
0x180013853  mov     rax, [rax]
0x180013856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001385b  mov     edi, eax
0x18001385d  mov     rcx, [rsp+28h+arg_8]
0x180013862  mov     rax, [rcx]
0x180013865  mov     rax, [rax+10h]
0x180013869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001386e  jmp     short loc_180013839
```
