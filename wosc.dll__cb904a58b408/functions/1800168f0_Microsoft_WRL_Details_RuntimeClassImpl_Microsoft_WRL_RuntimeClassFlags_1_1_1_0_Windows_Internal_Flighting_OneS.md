# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Flighting::OneSettings::IOneSettingsPayload,Windows::Internal::Flighting::OneSettings::IOneSettingsPayload2,Windows::Internal::Flighting::OneSettings::IOneSettingsPayload3>::GetIids(ulong *,_GUID * *)

- ea: `0x1800168f0`
- end: `0x180016969`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@UIOneSettingsPayload2@5678@UIOneSettingsPayload3@5678@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016970`
- `0x180016980`
- `0x180016990`

## callees

- `0x1800168f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016912`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016912`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Flighting::OneSettings::IOneSettingsPayload,Windows::Internal::Flighting::OneSettings::IOneSettingsPayload2,Windows::Internal::Flighting::OneSettings::IOneSettingsPayload3>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x40u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_1aac735e_9e3e_4c7d_81aa_9491f104c73d;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_144d624c_1177_4948_b8fb_b59641a4d2c6;
  v5[3] = GUID_7da8d456_475d_4522_afde_76f05dcf3e45;
  *a2 = 4;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800168f0  mov     [rsp+arg_0], rbx
0x1800168f5  push    rdi
0x1800168f6  sub     rsp, 20h
0x1800168fa  mov     qword ptr [r8], 0
0x180016901  mov     ecx, 40h ; '@'; cb
0x180016906  mov     dword ptr [rdx], 0
0x18001690c  mov     rbx, r8
0x18001690f  mov     rdi, rdx
0x180016912  call    cs:__imp_CoTaskMemAlloc
0x180016918  test    rax, rax
0x18001691b  jnz     short loc_180016924
0x18001691d  mov     eax, 8007000Eh
0x180016922  jmp     short loc_18001695E
0x180016924  movups  xmm0, xmmword ptr cs:_GUID_1aac735e_9e3e_4c7d_81aa_9491f104c73d.Data1
0x18001692b  movdqu  xmmword ptr [rax], xmm0
0x18001692f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180016936  movdqu  xmmword ptr [rax+10h], xmm1
0x18001693b  movups  xmm0, xmmword ptr cs:_GUID_144d624c_1177_4948_b8fb_b59641a4d2c6.Data1
0x180016942  movdqu  xmmword ptr [rax+20h], xmm0
0x180016947  movups  xmm1, xmmword ptr cs:_GUID_7da8d456_475d_4522_afde_76f05dcf3e45.Data1
0x18001694e  movdqu  xmmword ptr [rax+30h], xmm1
0x180016953  mov     dword ptr [rdi], 4
0x180016959  mov     [rbx], rax
0x18001695c  xor     eax, eax
0x18001695e  mov     rbx, [rsp+28h+arg_0]
0x180016963  add     rsp, 20h
0x180016967  pop     rdi
0x180016968  retn
```
