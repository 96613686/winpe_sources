# GetKeyFromEnvType

- ea: `0x18000b730`
- end: `0x18000b834`
- name: `GetKeyFromEnvType`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000bdc0`

## callees

- `0x18000b730`

## import_xrefs

- `ADVAPI32!RegCreateKeyExA` at `0x18000b7bb`
- `ADVAPI32!RegCreateKeyExA` at `0x18000b804`
- `ADVAPI32!RegCreateKeyExA` at `0x18000b7bb`
- `ADVAPI32!RegCreateKeyExA` at `0x18000b804`

## pseudocode

```c
__int64 __fastcall GetKeyFromEnvType(int a1, HKEY *phkResult)
{
  int v3; // ecx
  __int64 result; // rax
  __int64 v5; // rbx
  const CHAR *v6; // rdi
  LSTATUS Key; // eax
  bool v8; // sf
  LSTATUS v9; // eax
  signed int v10; // ecx

  if ( a1 )
  {
    v3 = a1 - 1;
    if ( v3 )
    {
      if ( v3 != 1 )
        return 2147549183LL;
      v5 = -2147483647;
      v6 = "Volatile Environment";
    }
    else
    {
      v5 = -2147483647;
      v6 = "Environment";
    }
  }
  else
  {
    v5 = -2147483646;
    v6 = "System\\CurrentControlSet\\Control\\Session Manager\\Environment";
  }
  Key = RegCreateKeyExA((HKEY)v5, v6, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
  v8 = Key < 0;
  if ( Key > 0 )
    v8 = 1;
  if ( !v8 )
    return 0;
  v9 = RegCreateKeyExA((HKEY)v5, v6, 0, 0, 0, 0x20019u, 0, phkResult, 0);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  result = 0;
  if ( v10 < 0 )
    return (unsigned int)v10;
  return result;
}

```

## disassembly

```asm
0x18000b730  mov     [rsp+arg_0], rbx
0x18000b735  mov     [rsp+arg_8], rsi
0x18000b73a  push    rdi
0x18000b73b  sub     rsp, 50h
0x18000b73f  mov     rsi, rdx
0x18000b742  test    ecx, ecx
0x18000b744  jz      short loc_18000B77A
0x18000b746  sub     ecx, 1
0x18000b749  jz      short loc_18000B76A
0x18000b74b  cmp     ecx, 1
0x18000b74e  jz      short loc_18000B75A
0x18000b750  mov     eax, 8000FFFFh
0x18000b755  jmp     loc_18000B824
0x18000b75a  mov     rbx, 0FFFFFFFF80000001h
0x18000b761  lea     rdi, SubKey; "Volatile Environment"
0x18000b768  jmp     short loc_18000B788
0x18000b76a  mov     rbx, 0FFFFFFFF80000001h
0x18000b771  lea     rdi, aEnvironment; "Environment"
0x18000b778  jmp     short loc_18000B788
0x18000b77a  mov     rbx, 0FFFFFFFF80000002h
0x18000b781  lea     rdi, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ses"...
0x18000b788  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18000b791  xor     r9d, r9d; lpClass
0x18000b794  mov     [rsp+58h+phkResult], rsi; phkResult
0x18000b799  xor     r8d, r8d; Reserved
0x18000b79c  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000b7a5  mov     rdx, rdi; lpSubKey
0x18000b7a8  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18000b7b0  mov     rcx, rbx; hKey
0x18000b7b3  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000b7bb  call    cs:__imp_RegCreateKeyExA
0x18000b7c1  test    eax, eax
0x18000b7c3  jle     short loc_18000B7CF
0x18000b7c5  movzx   eax, ax
0x18000b7c8  or      eax, 80070000h
0x18000b7cd  test    eax, eax
0x18000b7cf  jns     short loc_18000B822
0x18000b7d1  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18000b7da  xor     r9d, r9d; lpClass
0x18000b7dd  mov     [rsp+58h+phkResult], rsi; phkResult
0x18000b7e2  xor     r8d, r8d; Reserved
0x18000b7e5  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000b7ee  mov     rdx, rdi; lpSubKey
0x18000b7f1  mov     [rsp+58h+samDesired], 20019h; samDesired
0x18000b7f9  mov     rcx, rbx; hKey
0x18000b7fc  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000b804  call    cs:__imp_RegCreateKeyExA
0x18000b80a  mov     ecx, eax
0x18000b80c  test    eax, eax
0x18000b80e  jle     short loc_18000B819
0x18000b810  movzx   ecx, ax
0x18000b813  or      ecx, 80070000h
0x18000b819  xor     eax, eax
0x18000b81b  test    ecx, ecx
0x18000b81d  cmovs   eax, ecx
0x18000b820  jmp     short loc_18000B824
0x18000b822  xor     eax, eax
0x18000b824  mov     rbx, [rsp+58h+arg_0]
0x18000b829  mov     rsi, [rsp+58h+arg_8]
0x18000b82e  add     rsp, 50h
0x18000b832  pop     rdi
0x18000b833  retn
```
