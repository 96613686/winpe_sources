# sub_14006FBDC

- ea: `0x14006fbdc`
- end: `0x14006fcda`
- name: `sub_14006FBDC`
- size: `254`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14008f848`

## callees

- `0x140069e18`
- `0x14006adb4`
- `0x14006de60`
- `0x14006fbdc`
- `0x14007cfb4`
- `0x14007ff54`

## import_xrefs

- `ADVAPI32!RegSetKeySecurity` at `0x14006fc87`
- `ADVAPI32!RegSetKeySecurity` at `0x14006fc87`

## pseudocode

```c
__int64 __fastcall sub_14006FBDC(HKEY a1, const WCHAR *a2, __int64 a3, __int64 a4, __int64 a5)
{
  PSECURITY_DESCRIPTOR v7; // rax
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // ecx
  LSTATUS v11; // eax
  HKEY hKey; // [rsp+60h] [rbp+20h] BYREF
  DWORD v14; // [rsp+70h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+78h] [rbp+38h] BYREF

  v14 = 0;
  hKey = 0;
  a5 = 0;
  pSecurityDescriptor = 0;
  if ( a1 != HKEY_CURRENT_USER || (sub_14007CFB4(0), (v7 = pSecurityDescriptor) == 0) )
    v7 = 0;
  v8 = sub_140069E18(a1, a2, a3, a4, (__int64)v7, &hKey, &v14);
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( v14 == 1 )
    {
      v9 = 0;
      goto LABEL_17;
    }
    if ( v14 == 2 )
    {
      if ( !pSecurityDescriptor || (v11 = RegSetKeySecurity(hKey, 4u, pSecurityDescriptor), (v9 = v11) == 0) )
      {
        v9 = 1;
        goto LABEL_17;
      }
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
    }
    else
    {
      v9 = -2147418113;
    }
    v10 = v9;
  }
  else
  {
    v10 = v8;
  }
  sub_14006DE60(v10);
LABEL_17:
  sub_14007CFB4(v9);
  sub_14006ADB4(&pSecurityDescriptor);
  sub_14007FF54(&a5);
  sub_14007FF54(&hKey);
  return v9;
}

```

## disassembly

```asm
0x14006fbdc  mov     [rsp-18h+pSecurityDescriptor], r9
0x14006fbe1  mov     [rsp-18h+arg_10], r8d
0x14006fbe6  push    rbp
0x14006fbe7  push    rbx
0x14006fbe8  push    rdi
0x14006fbe9  mov     rbp, rsp
0x14006fbec  sub     rsp, 40h
0x14006fbf0  mov     [rbp+arg_10], 0
0x14006fbf7  mov     rdi, rdx
0x14006fbfa  mov     [rbp+hKey], 0
0x14006fc02  mov     rbx, rcx
0x14006fc05  mov     [rbp+arg_20], 0
0x14006fc0d  mov     [rbp+pSecurityDescriptor], 0
0x14006fc15  cmp     rcx, 0FFFFFFFF80000001h
0x14006fc1c  jnz     short loc_14006FC2E
0x14006fc1e  xor     ecx, ecx
0x14006fc20  call    sub_14007CFB4
0x14006fc25  mov     rax, [rbp+pSecurityDescriptor]
0x14006fc29  test    rax, rax
0x14006fc2c  jnz     short loc_14006FC30
0x14006fc2e  xor     eax, eax
0x14006fc30  lea     rcx, [rbp+arg_10]
0x14006fc34  mov     rdx, rdi; int
0x14006fc37  mov     [rsp+40h+var_10], rcx; LPDWORD
0x14006fc3c  lea     rcx, [rbp+hKey]
0x14006fc40  mov     [rsp+40h+var_18], rcx; __int64
0x14006fc45  mov     rcx, rbx; int
0x14006fc48  mov     [rsp+40h+var_20], rax; __int64
0x14006fc4d  call    sub_140069E18
0x14006fc52  mov     ebx, eax
0x14006fc54  test    eax, eax
0x14006fc56  jns     short loc_14006FC61
0x14006fc58  mov     ecx, eax
0x14006fc5a  call    sub_14006DE60
0x14006fc5f  jmp     short loc_14006FCAD
0x14006fc61  mov     eax, [rbp+arg_10]
0x14006fc64  sub     eax, 1
0x14006fc67  jz      short loc_14006FCAB
0x14006fc69  cmp     eax, 1
0x14006fc6c  jz      short loc_14006FC75
0x14006fc6e  mov     ebx, 8000FFFFh
0x14006fc73  jmp     short loc_14006FCA0
0x14006fc75  mov     r8, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x14006fc79  test    r8, r8
0x14006fc7c  jz      short loc_14006FCA4
0x14006fc7e  mov     rcx, [rbp+hKey]; hKey
0x14006fc82  mov     edx, 4; SecurityInformation
0x14006fc87  call    cs:RegSetKeySecurity
0x14006fc8d  mov     ebx, eax
0x14006fc8f  test    eax, eax
0x14006fc91  jz      short loc_14006FCA4
0x14006fc93  test    eax, eax
0x14006fc95  jle     short loc_14006FCA0
0x14006fc97  movzx   ebx, bx
0x14006fc9a  or      ebx, 80070000h
0x14006fca0  mov     ecx, ebx
0x14006fca2  jmp     short loc_14006FC5A
0x14006fca4  mov     ebx, 1
0x14006fca9  jmp     short loc_14006FCAD
0x14006fcab  xor     ebx, ebx
0x14006fcad  mov     ecx, ebx
0x14006fcaf  call    sub_14007CFB4
0x14006fcb4  lea     rcx, [rbp+pSecurityDescriptor]
0x14006fcb8  call    sub_14006ADB4
0x14006fcbd  lea     rcx, [rbp+arg_20]
0x14006fcc1  call    sub_14007FF54
0x14006fcc6  lea     rcx, [rbp+hKey]
0x14006fcca  call    sub_14007FF54
0x14006fccf  mov     eax, ebx
0x14006fcd1  add     rsp, 40h
0x14006fcd5  pop     rdi
0x14006fcd6  pop     rbx
0x14006fcd7  pop     rbp
0x14006fcd8  retn
```
