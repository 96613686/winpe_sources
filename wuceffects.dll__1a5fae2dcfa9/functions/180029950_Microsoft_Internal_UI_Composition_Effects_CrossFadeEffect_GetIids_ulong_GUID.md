# Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect::GetIids(ulong *,_GUID * *)

- ea: `0x180029950`
- end: `0x1800299d5`
- name: `?GetIids@CrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800299e0`
- `0x1800299f0`

## callees

- `0x180029950`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029972`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029972`

## pseudocode

```c
__int64 __fastcall Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect::GetIids(
        Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x50u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_cb51c0ce_8fe6_4636_b202_861faa07d8f3;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_2d8f9ddc_4339_4eb9_9216_f9deb75658a2;
  v5[3] = GUID_2fc57384_a068_44d7_a331_30982fcf7177;
  v5[4] = GUID_2a451393_ccc3_4c7e_b9bc_5ad9f9538c09;
  *a2 = 5;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180029950  mov     [rsp+arg_0], rbx
0x180029955  push    rdi
0x180029956  sub     rsp, 20h
0x18002995a  mov     qword ptr [r8], 0
0x180029961  mov     ecx, 50h ; 'P'; cb
0x180029966  mov     dword ptr [rdx], 0
0x18002996c  mov     rbx, r8
0x18002996f  mov     rdi, rdx
0x180029972  call    cs:__imp_CoTaskMemAlloc
0x180029978  test    rax, rax
0x18002997b  jnz     short loc_180029984
0x18002997d  mov     eax, 8007000Eh
0x180029982  jmp     short loc_1800299CA
0x180029984  movups  xmm0, xmmword ptr cs:_GUID_cb51c0ce_8fe6_4636_b202_861faa07d8f3.Data1
0x18002998b  movdqu  xmmword ptr [rax], xmm0
0x18002998f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180029996  movdqu  xmmword ptr [rax+10h], xmm1
0x18002999b  movups  xmm0, xmmword ptr cs:_GUID_2d8f9ddc_4339_4eb9_9216_f9deb75658a2.Data1
0x1800299a2  movdqu  xmmword ptr [rax+20h], xmm0
0x1800299a7  movups  xmm1, xmmword ptr cs:_GUID_2fc57384_a068_44d7_a331_30982fcf7177.Data1
0x1800299ae  movdqu  xmmword ptr [rax+30h], xmm1
0x1800299b3  movups  xmm0, xmmword ptr cs:_GUID_2a451393_ccc3_4c7e_b9bc_5ad9f9538c09.Data1
0x1800299ba  movdqu  xmmword ptr [rax+40h], xmm0
0x1800299bf  mov     dword ptr [rdi], 5
0x1800299c5  mov     [rbx], rax
0x1800299c8  xor     eax, eax
0x1800299ca  mov     rbx, [rsp+28h+arg_0]
0x1800299cf  add     rsp, 20h
0x1800299d3  pop     rdi
0x1800299d4  retn
```
