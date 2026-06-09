# SclRegKeyExists

- ea: `0x180009864`
- end: `0x1800098fc`
- name: `SclRegKeyExists`
- size: `152`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009cd0`

## callees

- `0x180001c74`
- `0x180009864`

## import_xrefs

- `ntdll!NtClose` at `0x1800098df`
- `ntdll!NtClose` at `0x1800098df`
- `ntdll!NtOpenKey` at `0x1800098c6`
- `ntdll!NtOpenKey` at `0x1800098c6`

## pseudocode

```c
__int64 __fastcall SclRegKeyExists(__int64 a1, const WCHAR *a2, bool *a3)
{
  NTSTATUS v4; // eax
  void *v5; // rcx
  struct _UNICODE_STRING v7; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+80h] [rbp+10h] BYREF

  KeyHandle = 0;
  v7 = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !a1 || !a2 || !a3 )
    return 3221225485LL;
  INIT_OBJA_EX((__int64)&ObjectAttributes, &v7, a2, 0, a1);
  KeyHandle = 0;
  v4 = NtOpenKey(&KeyHandle, 0, &ObjectAttributes);
  v5 = KeyHandle;
  *a3 = v4 != -1073741772;
  if ( v5 )
    NtClose(v5);
  return 0;
}

```

## disassembly

```asm
0x180009864  mov     [rsp-8+arg_8], rbx
0x180009869  push    rbp
0x18000986a  mov     rbp, rsp
0x18000986d  sub     rsp, 70h
0x180009871  xorps   xmm0, xmm0
0x180009874  xor     eax, eax
0x180009876  mov     [rbp+KeyHandle], rax
0x18000987a  mov     rbx, r8
0x18000987d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180009881  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180009885  movups  [rbp+var_40], xmm0
0x180009889  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000988d  test    rcx, rcx
0x180009890  jz      short loc_1800098E9
0x180009892  test    rdx, rdx
0x180009895  jz      short loc_1800098E9
0x180009897  test    rbx, rbx
0x18000989a  jz      short loc_1800098E9
0x18000989c  mov     [rsp+70h+var_50], rcx
0x1800098a1  mov     r8, rdx
0x1800098a4  lea     rdx, [rbp+var_40]
0x1800098a8  xor     r9d, r9d
0x1800098ab  lea     rcx, [rbp+ObjectAttributes]
0x1800098af  call    INIT_OBJA_EX
0x1800098b4  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800098b8  mov     [rbp+KeyHandle], 0
0x1800098c0  xor     edx, edx; DesiredAccess
0x1800098c2  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1800098c6  call    cs:__imp_NtOpenKey
0x1800098cc  mov     rcx, [rbp+KeyHandle]; Handle
0x1800098d0  cmp     eax, 0C0000034h
0x1800098d5  setnz   al
0x1800098d8  mov     [rbx], al
0x1800098da  test    rcx, rcx
0x1800098dd  jz      short loc_1800098E5
0x1800098df  call    cs:__imp_NtClose
0x1800098e5  xor     eax, eax
0x1800098e7  jmp     short loc_1800098EE
0x1800098e9  mov     eax, 0C000000Dh
0x1800098ee  mov     rbx, [rsp+70h+arg_8]
0x1800098f6  add     rsp, 70h
0x1800098fa  pop     rbp
0x1800098fb  retn
```
