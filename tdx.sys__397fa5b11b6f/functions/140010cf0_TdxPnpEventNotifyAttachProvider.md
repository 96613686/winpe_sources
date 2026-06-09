# TdxPnpEventNotifyAttachProvider

- ea: `0x140010cf0`
- end: `0x140010dab`
- name: `TdxPnpEventNotifyAttachProvider`
- size: `187`
- prototype: `__int64 __fastcall(HANDLE NmrBindingHandle)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140010cf0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140010d11`
- `ntoskrnl!RtlCompareMemory` at `0x140010d11`
- `ntoskrnl!ExAllocatePool2` at `0x140010d38`
- `ntoskrnl!ExAllocatePool2` at `0x140010d38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010d91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010d91`
- `NETIO!NmrClientAttachProvider` at `0x140010d74`
- `NETIO!NmrClientAttachProvider` at `0x140010d74`

## pseudocode

```c
__int64 __fastcall TdxPnpEventNotifyAttachProvider(HANDLE NmrBindingHandle, __int64 a2, __int64 a3)
{
  __int64 ProviderDispatch; // rax
  volatile signed __int32 *v6; // rbx
  NTSTATUS v7; // edi

  if ( RtlCompareMemory(*(const void **)(a3 + 16), &NPI_MS_IPV4_MODULEID, 0x18u) != 24 )
    return 3221225473LL;
  ProviderDispatch = ExAllocatePool2(64, 40, 1417176148);
  v6 = (volatile signed __int32 *)ProviderDispatch;
  if ( !ProviderDispatch )
    return 3221225626LL;
  *(_QWORD *)&WPP_MAIN_CB.DeviceType = ProviderDispatch;
  *(_QWORD *)(ProviderDispatch + 32) = NmrBindingHandle;
  v7 = NmrClientAttachProvider(
         NmrBindingHandle,
         (PVOID)ProviderDispatch,
         &TdxPnpEventClientDispatch,
         (PVOID *)(ProviderDispatch + 16),
         (const void **)ProviderDispatch);
  if ( v7 < 0 )
    ExFreePoolWithTag((PVOID)v6, 0);
  else
    _InterlockedIncrement(v6 + 6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140010cf0  mov     [rsp+arg_0], rbx
0x140010cf5  push    rdi
0x140010cf6  sub     rsp, 30h
0x140010cfa  mov     rax, r8
0x140010cfd  lea     rdx, NPI_MS_IPV4_MODULEID; Source2
0x140010d04  mov     rdi, rcx
0x140010d07  mov     r8d, 18h; Length
0x140010d0d  mov     rcx, [rax+10h]; Source1
0x140010d11  call    cs:__imp_RtlCompareMemory
0x140010d18  nop     dword ptr [rax+rax+00h]
0x140010d1d  cmp     rax, 18h
0x140010d21  jz      short loc_140010D2A
0x140010d23  mov     eax, 0C0000001h
0x140010d28  jmp     short loc_140010D9F
0x140010d2a  mov     edx, 28h ; '('
0x140010d2f  mov     r8d, 54786454h
0x140010d35  lea     ecx, [rdx+18h]
0x140010d38  call    cs:__imp_ExAllocatePool2
0x140010d3f  nop     dword ptr [rax+rax+00h]
0x140010d44  mov     rbx, rax
0x140010d47  test    rax, rax
0x140010d4a  jnz     short loc_140010D53
0x140010d4c  mov     eax, 0C000009Ah
0x140010d51  jmp     short loc_140010D9F
0x140010d53  lea     r9, [rax+10h]; ProviderBindingContext
0x140010d57  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rbx
0x140010d5e  lea     r8, TdxPnpEventClientDispatch; ClientDispatch
0x140010d65  mov     [rax+20h], rdi
0x140010d69  mov     rdx, rbx; ClientBindingContext
0x140010d6c  mov     [rsp+38h+ProviderDispatch], rbx; ProviderDispatch
0x140010d71  mov     rcx, rdi; NmrBindingHandle
0x140010d74  call    cs:__imp_NmrClientAttachProvider
0x140010d7b  nop     dword ptr [rax+rax+00h]
0x140010d80  mov     edi, eax
0x140010d82  test    eax, eax
0x140010d84  js      short loc_140010D8C
0x140010d86  lock inc dword ptr [rbx+18h]
0x140010d8a  jmp     short loc_140010D9D
0x140010d8c  xor     edx, edx; Tag
0x140010d8e  mov     rcx, rbx; P
0x140010d91  call    cs:__imp_ExFreePoolWithTag
0x140010d98  nop     dword ptr [rax+rax+00h]
0x140010d9d  mov     eax, edi
0x140010d9f  mov     rbx, [rsp+38h+arg_0]
0x140010da4  add     rsp, 30h
0x140010da8  pop     rdi
0x140010da9  retn
```
