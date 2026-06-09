# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>)

- ea: `0x180015abc`
- end: `0x180015b54`
- name: `??$ActivateInstance@V?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015f68`

## callees

- `0x180006844`
- `0x180015abc`
- `0x18001b0ea`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180015aec`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180015aec`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>(
        __int64 a1,
        _QWORD *a2)
{
  int v4; // edi
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a2);
  *a2 = 0;
  v6 = 0;
  v4 = RoActivateInstance(a1, &v6);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v6;
    }
    else
    {
      v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v6)(
             v6,
             &GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015abc  mov     [rsp+arg_0], rbx
0x180015ac1  push    rdi
0x180015ac2  sub     rsp, 20h
0x180015ac6  mov     rbx, rdx
0x180015ac9  mov     rdi, rcx
0x180015acc  mov     rcx, rdx
0x180015acf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180015ad4  mov     qword ptr [rbx], 0
0x180015adb  mov     [rsp+28h+arg_8], 0
0x180015ae4  lea     rdx, [rsp+28h+arg_8]
0x180015ae9  mov     rcx, rdi
0x180015aec  call    cs:__imp_RoActivateInstance
0x180015af2  mov     edi, eax
0x180015af4  test    eax, eax
0x180015af6  js      short loc_180015B47
0x180015af8  mov     r8d, 10h; Size
0x180015afe  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180015b05  lea     rcx, _GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494; Buf1
0x180015b0c  call    memcmp_0
0x180015b11  mov     rcx, [rsp+28h+arg_8]
0x180015b16  test    eax, eax
0x180015b18  jnz     short loc_180015B1F
0x180015b1a  mov     [rbx], rcx
0x180015b1d  jmp     short loc_180015B47
0x180015b1f  mov     rax, [rcx]
0x180015b22  mov     r8, rbx
0x180015b25  lea     rdx, _GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494
0x180015b2c  mov     rax, [rax]
0x180015b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b34  mov     edi, eax
0x180015b36  mov     rcx, [rsp+28h+arg_8]
0x180015b3b  mov     rax, [rcx]
0x180015b3e  mov     rax, [rax+10h]
0x180015b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b47  mov     eax, edi
0x180015b49  mov     rbx, [rsp+28h+arg_0]
0x180015b4e  add     rsp, 20h
0x180015b52  pop     rdi
0x180015b53  retn
```
