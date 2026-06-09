# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Effects::IGraphicsEffect,Windows::Graphics::Effects::IGraphicsEffectSource,Windows::Graphics::Effects::IGraphicsEffectD2D1Interop,Microsoft::Internal::UI::Composition::Effects::IGaussianBlurEffect>::GetIids(ulong *,_GUID * *)

- ea: `0x1800e59c0`
- end: `0x1800e5a45`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIGraphicsEffect@Effects@Graphics@Windows@@UIGraphicsEffectSource@567@UIGraphicsEffectD2D1Interop@567@UIGaussianBlurEffect@5Composition@UI@Internal@3@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800e5a50`
- `0x1800e5a60`

## callees

- `0x1800e59c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e59e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e59e2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Effects::IGraphicsEffect,Windows::Graphics::Effects::IGraphicsEffectSource,Windows::Graphics::Effects::IGraphicsEffectD2D1Interop,Microsoft::Internal::UI::Composition::Effects::IGaussianBlurEffect>::GetIids(
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
  v5[4] = GUID_cc3ff255_a83d_5aed_8187_70f64bbd9e51;
  *a2 = 5;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800e59c0  mov     [rsp+arg_0], rbx
0x1800e59c5  push    rdi
0x1800e59c6  sub     rsp, 20h
0x1800e59ca  mov     qword ptr [r8], 0
0x1800e59d1  mov     ecx, 50h ; 'P'; cb
0x1800e59d6  mov     dword ptr [rdx], 0
0x1800e59dc  mov     rbx, r8
0x1800e59df  mov     rdi, rdx
0x1800e59e2  call    cs:__imp_CoTaskMemAlloc
0x1800e59e8  test    rax, rax
0x1800e59eb  jnz     short loc_1800E59F4
0x1800e59ed  mov     eax, 8007000Eh
0x1800e59f2  jmp     short loc_1800E5A3A
0x1800e59f4  movups  xmm0, xmmword ptr cs:_GUID_cb51c0ce_8fe6_4636_b202_861faa07d8f3.Data1
0x1800e59fb  movdqu  xmmword ptr [rax], xmm0
0x1800e59ff  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800e5a06  movdqu  xmmword ptr [rax+10h], xmm1
0x1800e5a0b  movups  xmm0, xmmword ptr cs:_GUID_2d8f9ddc_4339_4eb9_9216_f9deb75658a2.Data1
0x1800e5a12  movdqu  xmmword ptr [rax+20h], xmm0
0x1800e5a17  movups  xmm1, xmmword ptr cs:_GUID_2fc57384_a068_44d7_a331_30982fcf7177.Data1
0x1800e5a1e  movdqu  xmmword ptr [rax+30h], xmm1
0x1800e5a23  movups  xmm0, xmmword ptr cs:_GUID_cc3ff255_a83d_5aed_8187_70f64bbd9e51.Data1
0x1800e5a2a  movdqu  xmmword ptr [rax+40h], xmm0
0x1800e5a2f  mov     dword ptr [rdi], 5
0x1800e5a35  mov     [rbx], rax
0x1800e5a38  xor     eax, eax
0x1800e5a3a  mov     rbx, [rsp+28h+arg_0]
0x1800e5a3f  add     rsp, 20h
0x1800e5a43  pop     rdi
0x1800e5a44  retn
```
