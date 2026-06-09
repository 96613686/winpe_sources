# BiOpenEffectiveToken

- ea: `0x18006c978`
- end: `0x18006ca00`
- name: `BiOpenEffectiveToken`
- size: `136`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18006c85c`

## callees

- `0x18006c978`

## import_xrefs

- `ntdll!NtOpenProcessTokenEx` at `0x18006c9ed`
- `ntdll!NtOpenProcessTokenEx` at `0x18006c9ed`
- `ntdll!NtOpenThreadTokenEx` at `0x18006c9a7`
- `ntdll!NtOpenThreadTokenEx` at `0x18006c9cd`
- `ntdll!NtOpenThreadTokenEx` at `0x18006c9a7`
- `ntdll!NtOpenThreadTokenEx` at `0x18006c9cd`

## pseudocode

```c
int __fastcall BiOpenEffectiveToken(PHANDLE TokenHandle)
{
  int result; // eax

  if ( !NtCurrentTeb()->IsImpersonating )
    return NtOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x28u, 0x200u, TokenHandle);
  result = NtOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 1u, 0x200u, TokenHandle);
  if ( result < 0 )
    return NtOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 0, 0x200u, TokenHandle);
  return result;
}

```

## disassembly

```asm
0x18006c978  push    rbx
0x18006c97a  sub     rsp, 30h
0x18006c97e  mov     eax, gs:179Ch
0x18006c986  mov     rbx, rcx
0x18006c989  mov     edx, 28h ; '('; DesiredAccess
0x18006c98e  test    eax, eax
0x18006c990  jz      short loc_18006C9E0
0x18006c992  mov     [rsp+38h+TokenHandle], rcx; TokenHandle
0x18006c997  mov     r9d, 200h; HandleAttributes
0x18006c99d  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18006c9a4  mov     r8b, 1; OpenAsSelf
0x18006c9a7  call    cs:__imp_NtOpenThreadTokenEx
0x18006c9ae  nop     dword ptr [rax+rax+00h]
0x18006c9b3  test    eax, eax
0x18006c9b5  jns     short loc_18006C9F9
0x18006c9b7  xor     r8d, r8d; OpenAsSelf
0x18006c9ba  mov     [rsp+38h+TokenHandle], rbx; TokenHandle
0x18006c9bf  mov     r9d, 200h; HandleAttributes
0x18006c9c5  lea     edx, [r8+28h]; DesiredAccess
0x18006c9c9  lea     rcx, [r8-2]; ThreadHandle
0x18006c9cd  call    cs:__imp_NtOpenThreadTokenEx
0x18006c9d4  nop     dword ptr [rax+rax+00h]
0x18006c9d9  add     rsp, 30h
0x18006c9dd  pop     rbx
0x18006c9de  retn
0x18006c9e0  mov     r9, rbx; TokenHandle
0x18006c9e3  mov     r8d, 200h; HandleAttributes
0x18006c9e9  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18006c9ed  call    cs:__imp_NtOpenProcessTokenEx
0x18006c9f4  nop     dword ptr [rax+rax+00h]
0x18006c9f9  add     rsp, 30h
0x18006c9fd  pop     rbx
0x18006c9fe  retn
```
