# Windows::Foundation::ActivateInstance<Windows::Data::Xml::Dom::IXmlDocument>(HSTRING__ *,Windows::Data::Xml::Dom::IXmlDocument * *)

- ea: `0x18002f9d4`
- end: `0x18002fa5e`
- name: `??$ActivateInstance@UIXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIXmlDocument@Dom@Xml@Data@1@@Z`
- size: `138`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180030b0c`
- `0x180030cb0`
- `0x180030e24`

## callees

- `0x1800229ec`
- `0x18002f9d4`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18002f9f6`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18002f9f6`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Windows::Data::Xml::Dom::IXmlDocument>(__int64 a1, _QWORD *a2)
{
  int v3; // ebx
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v5 = 0;
  v3 = RoActivateInstance(a1, &v5);
  if ( v3 >= 0 )
  {
    if ( !memcmp_0(&GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v5;
    }
    else
    {
      v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v5)(
             v5,
             &GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002f9d4  mov     [rsp+arg_0], rbx
0x18002f9d9  push    rdi
0x18002f9da  sub     rsp, 20h
0x18002f9de  mov     rdi, rdx
0x18002f9e1  mov     qword ptr [rdx], 0
0x18002f9e8  lea     rdx, [rsp+28h+arg_8]
0x18002f9ed  mov     [rsp+28h+arg_8], 0
0x18002f9f6  call    cs:__imp_RoActivateInstance
0x18002f9fc  mov     ebx, eax
0x18002f9fe  test    eax, eax
0x18002fa00  js      short loc_18002FA51
0x18002fa02  mov     r8d, 10h; Size
0x18002fa08  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18002fa0f  lea     rcx, _GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494; Buf1
0x18002fa16  call    memcmp_0
0x18002fa1b  mov     rcx, [rsp+28h+arg_8]
0x18002fa20  test    eax, eax
0x18002fa22  jnz     short loc_18002FA29
0x18002fa24  mov     [rdi], rcx
0x18002fa27  jmp     short loc_18002FA51
0x18002fa29  mov     rax, [rcx]
0x18002fa2c  lea     rdx, _GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494
0x18002fa33  mov     r8, rdi
0x18002fa36  mov     rax, [rax]
0x18002fa39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa3e  mov     rcx, [rsp+28h+arg_8]
0x18002fa43  mov     ebx, eax
0x18002fa45  mov     rax, [rcx]
0x18002fa48  mov     rax, [rax+10h]
0x18002fa4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa51  mov     eax, ebx
0x18002fa53  mov     rbx, [rsp+28h+arg_0]
0x18002fa58  add     rsp, 20h
0x18002fa5c  pop     rdi
0x18002fa5d  retn
```
