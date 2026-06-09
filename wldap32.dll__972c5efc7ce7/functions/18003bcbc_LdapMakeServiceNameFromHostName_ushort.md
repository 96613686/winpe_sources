# LdapMakeServiceNameFromHostName(ushort *)

- ea: `0x18003bcbc`
- end: `0x18003bd2c`
- name: `?LdapMakeServiceNameFromHostName@@YAPEAGPEAG@Z`
- size: `112`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800164a0`

## callees

- `0x18001ce90`
- `0x180020970`
- `0x180034ecc`
- `0x18003bcbc`

## pseudocode

```c
unsigned __int16 *__fastcall LdapMakeServiceNameFromHostName(unsigned __int16 *a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // eax
  __int64 v5; // r8
  int v6; // eax
  int v7; // edx
  unsigned int v8; // esi
  unsigned __int16 *result; // rax
  unsigned __int16 *v10; // rbx

  v4 = strlenW(a1, a2, a3);
  v6 = strlenW(L"ldap", v4, v5);
  v8 = v7 + v6 + 2;
  result = (unsigned __int16 *)ldapMalloc(2 * v8, 1987203916);
  v10 = result;
  if ( result )
  {
    swprintf_s(result, v8, L"%s/%s", L"ldap", a1);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x18003bcbc  mov     [rsp+arg_0], rbx
0x18003bcc1  mov     [rsp+arg_8], rsi
0x18003bcc6  push    rdi
0x18003bcc7  sub     rsp, 30h
0x18003bccb  mov     rdi, rcx
0x18003bcce  call    strlenW
0x18003bcd3  lea     rcx, ServiceClass; "ldap"
0x18003bcda  mov     edx, eax
0x18003bcdc  call    strlenW
0x18003bce1  lea     esi, [rax+2]
0x18003bce4  add     esi, edx
0x18003bce6  mov     edx, 7672534Ch
0x18003bceb  lea     ecx, [rsi+rsi]
0x18003bcee  call    ldapMalloc
0x18003bcf3  mov     rbx, rax
0x18003bcf6  test    rax, rax
0x18003bcf9  jz      short loc_18003BD1B
0x18003bcfb  mov     edx, esi; BufferCount
0x18003bcfd  lea     r9, ServiceClass; "ldap"
0x18003bd04  lea     r8, aSS_0; "%s/%s"
0x18003bd0b  mov     [rsp+38h+var_18], rdi
0x18003bd10  mov     rcx, rbx; Buffer
0x18003bd13  call    swprintf_s
0x18003bd18  mov     rax, rbx
0x18003bd1b  mov     rbx, [rsp+38h+arg_0]
0x18003bd20  mov     rsi, [rsp+38h+arg_8]
0x18003bd25  add     rsp, 30h
0x18003bd29  pop     rdi
0x18003bd2a  retn
```
