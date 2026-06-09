# RootDeviceFindDeviceInterfaceLocked

- ea: `0x140005b8c`
- end: `0x140005be9`
- name: `RootDeviceFindDeviceInterfaceLocked`
- size: `93`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000566c`
- `0x140005f28`
- `0x1400066b0`
- `0x14002c0f0`

## callees

- `0x140005b8c`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140005bb7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140005bb7`

## pseudocode

```c
const UNICODE_STRING *__fastcall RootDeviceFindDeviceInterfaceLocked(__int64 a1, const UNICODE_STRING *a2, wchar_t *a3)
{
  __int64 *v3; // r14
  const UNICODE_STRING *i; // rbx

  v3 = (__int64 *)(a1 + 96);
  for ( i = *(const UNICODE_STRING **)(a1 + 96); i != (const UNICODE_STRING *)v3; i = *(const UNICODE_STRING **)&i->Length )
  {
    if ( a2 && !RtlCompareUnicodeString(a2, i + 6, 0) || a3 && a3 == i[1].Buffer )
      return i;
  }
  return 0;
}

```

## disassembly

```asm
0x140005b8c  push    rbx
0x140005b8e  push    rsi
0x140005b8f  push    rdi
0x140005b90  push    r14
0x140005b92  sub     rsp, 28h
0x140005b96  lea     r14, [rcx+60h]
0x140005b9a  mov     rdi, r8
0x140005b9d  mov     rbx, [r14]
0x140005ba0  mov     rsi, rdx
0x140005ba3  cmp     rbx, r14
0x140005ba6  jz      short loc_140005BDC
0x140005ba8  test    rsi, rsi
0x140005bab  jz      short loc_140005BC7
0x140005bad  lea     rdx, [rbx+60h]; String2
0x140005bb1  xor     r8d, r8d; CaseInSensitive
0x140005bb4  mov     rcx, rsi; String1
0x140005bb7  call    cs:__imp_RtlCompareUnicodeString
0x140005bbe  nop     dword ptr [rax+rax+00h]
0x140005bc3  test    eax, eax
0x140005bc5  jz      short loc_140005BD7
0x140005bc7  test    rdi, rdi
0x140005bca  jz      short loc_140005BD2
0x140005bcc  cmp     rdi, [rbx+18h]
0x140005bd0  jz      short loc_140005BD7
0x140005bd2  mov     rbx, [rbx]
0x140005bd5  jmp     short loc_140005BA3
0x140005bd7  mov     rax, rbx
0x140005bda  jmp     short loc_140005BDE
0x140005bdc  xor     eax, eax
0x140005bde  add     rsp, 28h
0x140005be2  pop     r14
0x140005be4  pop     rdi
0x140005be5  pop     rsi
0x140005be6  pop     rbx
0x140005be7  retn
```
