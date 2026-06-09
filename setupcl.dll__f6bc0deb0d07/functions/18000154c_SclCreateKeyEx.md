# SclCreateKeyEx

- ea: `0x18000154c`
- end: `0x180001635`
- name: `SclCreateKeyEx`
- size: `233`
- prototype: `__int64 __fastcall(void *, struct _UNICODE_STRING *, ACCESS_MASK, int, ULONG *Disposition, void **KeyHandle)`
- caller_count: `7`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800014e8`
- `0x180004428`
- `0x180004844`
- `0x1800051d8`
- `0x1800088bc`
- `0x18000acec`
- `0x18000b21c`

## callees

- `0x18000154c`
- `0x1800179e0`

## import_xrefs

- `ntdll!NtQueryKey` at `0x1800015f8`
- `ntdll!NtQueryKey` at `0x1800015f8`
- `ntdll!NtClose` at `0x180001603`
- `ntdll!NtClose` at `0x180001603`
- `ntdll!NtCreateKey` at `0x1800015bb`
- `ntdll!NtCreateKey` at `0x1800015bb`

## pseudocode

```c
__int64 __fastcall SclCreateKeyEx(
        void *a1,
        struct _UNICODE_STRING *a2,
        ACCESS_MASK a3,
        int a4,
        ULONG *Disposition,
        void **KeyHandle)
{
  NTSTATUS v6; // edi
  void *v7; // rcx
  ULONG ResultLength; // [rsp+40h] [rbp-39h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-31h] BYREF
  __int128 KeyInformation; // [rsp+78h] [rbp-1h] BYREF
  __int128 v12; // [rsp+88h] [rbp+Fh]
  __int64 v13; // [rsp+98h] [rbp+1Fh]

  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = a4 | 0x40;
  ObjectAttributes.ObjectName = a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v6 = NtCreateKey(KeyHandle, a3, &ObjectAttributes, 0, 0, 4u, Disposition);
  if ( v6 == 1073741846 )
  {
    v7 = *KeyHandle;
    v13 = 0;
    ResultLength = 0;
    KeyInformation = 0;
    v12 = 0;
    v6 = NtQueryKey(v7, KeyCachedInformation, &KeyInformation, 0x28u, &ResultLength);
    NtClose(*KeyHandle);
    if ( v6 < 0 )
      *KeyHandle = 0;
    else
      *KeyHandle = (void *)DWORD1(v12);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000154c  push    rbp
0x18000154e  push    rbx
0x18000154f  push    rdi
0x180001550  lea     rbp, [rsp-37h]
0x180001555  sub     rsp, 0B0h
0x18000155c  mov     rax, cs:__security_cookie
0x180001563  xor     rax, rsp
0x180001566  mov     [rbp+47h+var_20], rax
0x18000156a  mov     rax, [rbp+47h+arg_20]
0x18000156e  mov     r10d, r8d
0x180001571  mov     rbx, [rbp+47h+KeyHandle]
0x180001575  xor     r8d, r8d
0x180001578  mov     [rsp+0C0h+Disposition], rax; Disposition
0x18000157d  or      r9d, 40h
0x180001581  mov     dword ptr [rbp+47h+ObjectAttributes+1Ch], r8d
0x180001585  xorps   xmm0, xmm0
0x180001588  mov     [rbp+47h+ObjectAttributes.RootDirectory], rcx
0x18000158c  mov     rcx, rbx; KeyHandle
0x18000158f  mov     [rbp+47h+ObjectAttributes.Attributes], r9d
0x180001593  xor     r9d, r9d; TitleIndex
0x180001596  mov     [rbp+47h+ObjectAttributes.ObjectName], rdx
0x18000159a  mov     edx, r10d; DesiredAccess
0x18000159d  mov     [rsp+0C0h+CreateOptions], 4; CreateOptions
0x1800015a5  mov     [rsp+0C0h+Class], r8; Class
0x1800015aa  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x1800015ae  mov     qword ptr [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x1800015b6  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800015bb  call    cs:__imp_NtCreateKey
0x1800015c1  mov     edi, eax
0x1800015c3  cmp     eax, 40000016h
0x1800015c8  jnz     short loc_18000161C
0x1800015ca  mov     rcx, [rbx]; KeyHandle
0x1800015cd  lea     r8, [rbp+47h+KeyInformation]; KeyInformation
0x1800015d1  xor     eax, eax
0x1800015d3  xorps   xmm0, xmm0
0x1800015d6  mov     r9d, 28h ; '('; Length
0x1800015dc  mov     [rbp+47h+var_28], rax
0x1800015e0  mov     [rbp+47h+ResultLength], eax
0x1800015e3  lea     rax, [rbp+47h+ResultLength]
0x1800015e7  movups  [rbp+47h+KeyInformation], xmm0
0x1800015eb  mov     [rsp+0C0h+Class], rax; ResultLength
0x1800015f0  lea     edx, [r9-24h]; KeyInformationClass
0x1800015f4  movups  [rbp+47h+var_38], xmm0
0x1800015f8  call    cs:__imp_NtQueryKey
0x1800015fe  mov     rcx, [rbx]; Handle
0x180001601  mov     edi, eax
0x180001603  call    cs:__imp_NtClose
0x180001609  test    edi, edi
0x18000160b  js      short loc_180001615
0x18000160d  mov     eax, dword ptr [rbp+47h+var_38+4]
0x180001610  mov     [rbx], rax
0x180001613  jmp     short loc_18000161C
0x180001615  mov     qword ptr [rbx], 0
0x18000161c  mov     eax, edi
0x18000161e  mov     rcx, [rbp+47h+var_20]
0x180001622  xor     rcx, rsp; StackCookie
0x180001625  call    __security_check_cookie
0x18000162a  add     rsp, 0B0h
0x180001631  pop     rdi
0x180001632  pop     rbx
0x180001633  pop     rbp
0x180001634  retn
```
