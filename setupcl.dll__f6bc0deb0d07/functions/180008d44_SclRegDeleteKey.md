# SclRegDeleteKey

- ea: `0x180008d44`
- end: `0x180008e39`
- name: `SclRegDeleteKey`
- size: `245`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180001de0`
- `0x1800051d8`
- `0x1800088bc`
- `0x180008e40`

## callees

- `0x180001c74`
- `0x180008d44`
- `0x180014fa0`

## import_xrefs

- `ntdll!NtClose` at `0x180008e03`
- `ntdll!NtClose` at `0x180008e03`
- `ntdll!RtlFreeHeap` at `0x180008e20`
- `ntdll!RtlFreeHeap` at `0x180008e20`
- `ntdll!NtOpenKey` at `0x180008ddc`
- `ntdll!NtOpenKey` at `0x180008ddc`
- `ntdll!NtDeleteKey` at `0x180008d66`
- `ntdll!NtDeleteKey` at `0x180008dec`
- `ntdll!NtDeleteKey` at `0x180008d66`
- `ntdll!NtDeleteKey` at `0x180008dec`

## pseudocode

```c
__int64 __fastcall SclRegDeleteKey(HANDLE Handle)
{
  NTSTATUS v3; // ebx
  int v4; // eax
  PVOID v5; // rdi
  struct _UNICODE_STRING v6; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+90h] [rbp+20h] BYREF
  PVOID P; // [rsp+98h] [rbp+28h] BYREF

  if ( !Handle )
    return 3221225485LL;
  v3 = NtDeleteKey(Handle);
  if ( v3 == -1073741790 )
  {
    P = 0;
    KeyHandle = 0;
    v6 = 0;
    memset(&ObjectAttributes, 0, 44);
    v4 = CanonicalizeObjectPathByHandle(Handle, &P);
    v5 = P;
    v3 = v4;
    if ( v4 >= 0 )
    {
      INIT_OBJA_EX((__int64)&ObjectAttributes, &v6, (const WCHAR *)P, 64, 0);
      v3 = NtOpenKey(&KeyHandle, 0x10000u, &ObjectAttributes);
      if ( v3 >= 0 )
        v3 = NtDeleteKey(KeyHandle);
    }
    if ( v3 < 0 )
      v3 = -1073741790;
    if ( KeyHandle )
      NtClose(KeyHandle);
    if ( v5 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008d44  mov     [rsp-18h+arg_10], rbx
0x180008d49  push    rbp
0x180008d4a  push    rdi
0x180008d4b  push    r14
0x180008d4d  mov     rbp, rsp
0x180008d50  sub     rsp, 70h
0x180008d54  mov     rdi, rcx
0x180008d57  test    rcx, rcx
0x180008d5a  jnz     short loc_180008D66
0x180008d5c  mov     eax, 0C000000Dh
0x180008d61  jmp     loc_180008E28
0x180008d66  call    cs:__imp_NtDeleteKey
0x180008d6c  mov     r14d, 0C0000022h
0x180008d72  mov     ebx, eax
0x180008d74  cmp     eax, r14d
0x180008d77  jnz     loc_180008E26
0x180008d7d  xorps   xmm0, xmm0
0x180008d80  lea     rdx, [rbp+P]
0x180008d84  xor     eax, eax
0x180008d86  mov     rcx, rdi; Handle
0x180008d89  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180008d8d  mov     [rbp+P], rax
0x180008d91  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180008d95  mov     [rbp+KeyHandle], rax
0x180008d99  movups  [rbp+var_40], xmm0
0x180008d9d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180008da1  call    CanonicalizeObjectPathByHandle
0x180008da6  mov     rdi, [rbp+P]
0x180008daa  mov     ebx, eax
0x180008dac  test    eax, eax
0x180008dae  js      short loc_180008DF4
0x180008db0  mov     r9d, 40h ; '@'
0x180008db6  mov     [rsp+70h+var_50], 0
0x180008dbf  mov     r8, rdi
0x180008dc2  lea     rdx, [rbp+var_40]
0x180008dc6  lea     rcx, [rbp+ObjectAttributes]
0x180008dca  call    INIT_OBJA_EX
0x180008dcf  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180008dd3  mov     edx, 10000h; DesiredAccess
0x180008dd8  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180008ddc  call    cs:__imp_NtOpenKey
0x180008de2  mov     ebx, eax
0x180008de4  test    eax, eax
0x180008de6  js      short loc_180008DF4
0x180008de8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180008dec  call    cs:__imp_NtDeleteKey
0x180008df2  mov     ebx, eax
0x180008df4  mov     rcx, [rbp+KeyHandle]; Handle
0x180008df8  test    ebx, ebx
0x180008dfa  cmovs   ebx, r14d
0x180008dfe  test    rcx, rcx
0x180008e01  jz      short loc_180008E09
0x180008e03  call    cs:__imp_NtClose
0x180008e09  test    rdi, rdi
0x180008e0c  jz      short loc_180008E26
0x180008e0e  mov     rcx, gs:60h
0x180008e17  mov     r8, rdi; P
0x180008e1a  xor     edx, edx; Flags
0x180008e1c  mov     rcx, [rcx+30h]; HeapHandle
0x180008e20  call    cs:__imp_RtlFreeHeap
0x180008e26  mov     eax, ebx
0x180008e28  mov     rbx, [rsp+70h+arg_10]
0x180008e30  add     rsp, 70h
0x180008e34  pop     r14
0x180008e36  pop     rdi
0x180008e37  pop     rbp
0x180008e38  retn
```
