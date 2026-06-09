# Windows::Internal::Notifications::CWpnClient::GetIids(ulong *,_GUID * *)

- ea: `0x180028400`
- end: `0x180028485`
- name: `?GetIids@CWpnClient@Notifications@Internal@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::CWpnClient *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028490`
- `0x1800284a0`
- `0x1800284b0`

## callees

- `0x180028400`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028422`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028422`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Notifications::CWpnClient::GetIids(
        Windows::Internal::Notifications::CWpnClient *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x50u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_94ce9b38_4a14_43f4_be3a_1740bda3adf1;
  v5[3] = GUID_3bcc89ff_385d_4c36_b1c8_4b8a79ae4d56;
  v5[4] = GUID_660d9b4c_7cab_40b0_bd43_9c0244a8b7da;
  *a2 = 5;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180028400  mov     [rsp+arg_0], rbx
0x180028405  push    rdi
0x180028406  sub     rsp, 20h
0x18002840a  mov     qword ptr [r8], 0
0x180028411  mov     ecx, 50h ; 'P'; cb
0x180028416  mov     dword ptr [rdx], 0
0x18002841c  mov     rbx, r8
0x18002841f  mov     rdi, rdx
0x180028422  call    cs:__imp_CoTaskMemAlloc
0x180028428  test    rax, rax
0x18002842b  jnz     short loc_180028434
0x18002842d  mov     eax, 8007000Eh
0x180028432  jmp     short loc_18002847A
0x180028434  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18002843b  movdqu  xmmword ptr [rax], xmm0
0x18002843f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180028446  movdqu  xmmword ptr [rax+10h], xmm1
0x18002844b  movups  xmm0, xmmword ptr cs:_GUID_94ce9b38_4a14_43f4_be3a_1740bda3adf1.Data1
0x180028452  movdqu  xmmword ptr [rax+20h], xmm0
0x180028457  movups  xmm1, xmmword ptr cs:_GUID_3bcc89ff_385d_4c36_b1c8_4b8a79ae4d56.Data1
0x18002845e  movdqu  xmmword ptr [rax+30h], xmm1
0x180028463  movups  xmm0, xmmword ptr cs:_GUID_660d9b4c_7cab_40b0_bd43_9c0244a8b7da.Data1
0x18002846a  movdqu  xmmword ptr [rax+40h], xmm0
0x18002846f  mov     dword ptr [rdi], 5
0x180028475  mov     [rbx], rax
0x180028478  xor     eax, eax
0x18002847a  mov     rbx, [rsp+28h+arg_0]
0x18002847f  add     rsp, 20h
0x180028483  pop     rdi
0x180028484  retn
```
