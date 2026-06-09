# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Effects::IGraphicsEffect,Windows::Graphics::Effects::IGraphicsEffectSource,Windows::Graphics::Effects::IGraphicsEffectD2D1Interop,Microsoft::Internal::UI::Composition::Effects::IOpacityEffect>::GetIids(ulong *,_GUID * *)

- ea: `0x180029a00`
- end: `0x180029a85`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIGraphicsEffect@Effects@Graphics@Windows@@UIGraphicsEffectSource@567@UIGraphicsEffectD2D1Interop@567@UIOpacityEffect@5Composition@UI@Internal@3@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029a90`
- `0x180029aa0`

## callees

- `0x180029a00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029a22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029a22`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Effects::IGraphicsEffect,Windows::Graphics::Effects::IGraphicsEffectSource,Windows::Graphics::Effects::IGraphicsEffectD2D1Interop,Microsoft::Internal::UI::Composition::Effects::IOpacityEffect>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x50u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_cb51c0ce_8fe6_4636_b202_861faa07d8f3;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_2d8f9ddc_4339_4eb9_9216_f9deb75658a2;
  v5[3] = GUID_2fc57384_a068_44d7_a331_30982fcf7177;
  v5[4] = GUID_c20ae33a_1844_4650_811c_63ca823b86b6;
  *a2 = 5;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180029a00  mov     [rsp+arg_0], rbx
0x180029a05  push    rdi
0x180029a06  sub     rsp, 20h
0x180029a0a  mov     qword ptr [r8], 0
0x180029a11  mov     ecx, 50h ; 'P'; cb
0x180029a16  mov     dword ptr [rdx], 0
0x180029a1c  mov     rbx, r8
0x180029a1f  mov     rdi, rdx
0x180029a22  call    cs:__imp_CoTaskMemAlloc
0x180029a28  test    rax, rax
0x180029a2b  jnz     short loc_180029A34
0x180029a2d  mov     eax, 8007000Eh
0x180029a32  jmp     short loc_180029A7A
0x180029a34  movups  xmm0, xmmword ptr cs:_GUID_cb51c0ce_8fe6_4636_b202_861faa07d8f3.Data1
0x180029a3b  movdqu  xmmword ptr [rax], xmm0
0x180029a3f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180029a46  movdqu  xmmword ptr [rax+10h], xmm1
0x180029a4b  movups  xmm0, xmmword ptr cs:_GUID_2d8f9ddc_4339_4eb9_9216_f9deb75658a2.Data1
0x180029a52  movdqu  xmmword ptr [rax+20h], xmm0
0x180029a57  movups  xmm1, xmmword ptr cs:_GUID_2fc57384_a068_44d7_a331_30982fcf7177.Data1
0x180029a5e  movdqu  xmmword ptr [rax+30h], xmm1
0x180029a63  movups  xmm0, xmmword ptr cs:_GUID_c20ae33a_1844_4650_811c_63ca823b86b6.Data1
0x180029a6a  movdqu  xmmword ptr [rax+40h], xmm0
0x180029a6f  mov     dword ptr [rdi], 5
0x180029a75  mov     [rbx], rax
0x180029a78  xor     eax, eax
0x180029a7a  mov     rbx, [rsp+28h+arg_0]
0x180029a7f  add     rsp, 20h
0x180029a83  pop     rdi
0x180029a84  retn
```
