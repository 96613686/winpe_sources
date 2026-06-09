# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Notifications::INotificationValueSet,Windows::Internal::Notifications::INotificationValueSet2>::GetIids(ulong *,_GUID * *)

- ea: `0x180025370`
- end: `0x1800253e9`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UINotificationValueSet@Notifications@Internal@Windows@@UINotificationValueSet2@678@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800253f0`
- `0x180025400`

## callees

- `0x180025370`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025392`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025392`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Notifications::INotificationValueSet,Windows::Internal::Notifications::INotificationValueSet2>::GetIids(
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
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_07978036_2587_417d_85d1_6fa18e9c67e1;
  v5[3] = GUID_7a68fb41_4474_44fc_99f3_00c6a39b08fd;
  *a2 = 4;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180025370  mov     [rsp+arg_0], rbx
0x180025375  push    rdi
0x180025376  sub     rsp, 20h
0x18002537a  mov     qword ptr [r8], 0
0x180025381  mov     ecx, 40h ; '@'; cb
0x180025386  mov     dword ptr [rdx], 0
0x18002538c  mov     rbx, r8
0x18002538f  mov     rdi, rdx
0x180025392  call    cs:__imp_CoTaskMemAlloc
0x180025398  test    rax, rax
0x18002539b  jnz     short loc_1800253A4
0x18002539d  mov     eax, 8007000Eh
0x1800253a2  jmp     short loc_1800253DE
0x1800253a4  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x1800253ab  movdqu  xmmword ptr [rax], xmm0
0x1800253af  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800253b6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800253bb  movups  xmm0, xmmword ptr cs:_GUID_07978036_2587_417d_85d1_6fa18e9c67e1.Data1
0x1800253c2  movdqu  xmmword ptr [rax+20h], xmm0
0x1800253c7  movups  xmm1, xmmword ptr cs:_GUID_7a68fb41_4474_44fc_99f3_00c6a39b08fd.Data1
0x1800253ce  movdqu  xmmword ptr [rax+30h], xmm1
0x1800253d3  mov     dword ptr [rdi], 4
0x1800253d9  mov     [rbx], rax
0x1800253dc  xor     eax, eax
0x1800253de  mov     rbx, [rsp+28h+arg_0]
0x1800253e3  add     rsp, 20h
0x1800253e7  pop     rdi
0x1800253e8  retn
```
