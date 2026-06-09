# ManifestProcessor::AssertRetractChanges(void)

- ea: `0x14001ae18`
- end: `0x14001aeb8`
- name: `?AssertRetractChanges@ManifestProcessor@@QEAAKXZ`
- size: `160`
- prototype: `unsigned int __fastcall(ManifestProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x140001ce0`

## callees

- `0x1400088e0`
- `0x14001989c`
- `0x14001ae18`
- `0x14001c340`
- `0x140022cec`

## pseudocode

```c
__int64 __fastcall ManifestProcessor::AssertRetractChanges(ManifestProcessor *this)
{
  unsigned int BindingHandleForLocalService; // ebx
  __int64 v4; // [rsp+40h] [rbp+8h] BYREF

  if ( !*(_BYTE *)this )
    return 0;
  v4 = 0;
  BindingHandleForLocalService = GetBindingHandleForLocalService((__int64)&v4);
  if ( BindingHandleForLocalService )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        100,
        &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids,
        BindingHandleForLocalService);
    }
  }
  else
  {
    BindingHandleForLocalService = AssertRetractChanges(
                                     v4,
                                     *((_QWORD *)this + 2),
                                     *((_QWORD *)this + 3),
                                     *((_QWORD *)this + 4),
                                     *((_QWORD *)this + 5));
  }
  tlx::unique_any_tlx::handle_traits_void___void____cdecl___void_____MyRpcBindingFree_0___::_unique_any_tlx::handle_traits_void___void____cdecl___void_____MyRpcBindingFree_0___(&v4);
  return BindingHandleForLocalService;
}

```

## disassembly

```asm
0x14001ae18  mov     [rsp+arg_8], rbx
0x14001ae1d  push    rdi
0x14001ae1e  sub     rsp, 30h
0x14001ae22  cmp     byte ptr [rcx], 0
0x14001ae25  mov     rdi, rcx
0x14001ae28  jnz     short loc_14001AE2E
0x14001ae2a  xor     eax, eax
0x14001ae2c  jmp     short loc_14001AEAD
0x14001ae2e  lea     rcx, [rsp+38h+arg_0]
0x14001ae33  mov     [rsp+38h+arg_0], 0
0x14001ae3c  call    GetBindingHandleForLocalService
0x14001ae41  mov     ebx, eax
0x14001ae43  test    eax, eax
0x14001ae45  jz      short loc_14001AE80
0x14001ae47  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ae4e  lea     rax, WPP_GLOBAL_Control
0x14001ae55  cmp     rcx, rax
0x14001ae58  jz      short loc_14001AEA1
0x14001ae5a  test    byte ptr [rcx+1Ch], 4
0x14001ae5e  jz      short loc_14001AEA1
0x14001ae60  cmp     byte ptr [rcx+19h], 2
0x14001ae64  jb      short loc_14001AEA1
0x14001ae66  mov     rcx, [rcx+10h]
0x14001ae6a  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14001ae71  mov     edx, 64h ; 'd'
0x14001ae76  mov     r9d, ebx
0x14001ae79  call    WPP_SF_d
0x14001ae7e  jmp     short loc_14001AEA1
0x14001ae80  mov     rax, [rdi+28h]
0x14001ae84  mov     r9, [rdi+20h]
0x14001ae88  mov     r8, [rdi+18h]
0x14001ae8c  mov     rdx, [rdi+10h]
0x14001ae90  mov     rcx, [rsp+38h+arg_0]
0x14001ae95  mov     [rsp+38h+var_18], rax
0x14001ae9a  call    AssertRetractChanges
0x14001ae9f  mov     ebx, eax
0x14001aea1  lea     rcx, [rsp+38h+arg_0]
0x14001aea6  call    tlx__unique_any_tlx__handle_traits_void___void____cdecl___void_____MyRpcBindingFree_0______unique_any_tlx__handle_traits_void___void____cdecl___void_____MyRpcBindingFree_0___
0x14001aeab  mov     eax, ebx
0x14001aead  mov     rbx, [rsp+38h+arg_8]
0x14001aeb2  add     rsp, 30h
0x14001aeb6  pop     rdi
0x14001aeb7  retn
```
