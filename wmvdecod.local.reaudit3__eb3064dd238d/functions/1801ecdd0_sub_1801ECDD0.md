# sub_1801ECDD0

- ea: `0x1801ecdd0`
- end: `0x1801eceef`
- name: `sub_1801ECDD0`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801ecef8`

## callees

- `0x1801ecdd0`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x1801ece10`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x1801ece10`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptImportKey` at `0x1801ece94`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptImportKey` at `0x1801ece94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ecea4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ecea4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ece28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ece28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ecec6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ecec6`

## pseudocode

```c
__int64 __fastcall sub_1801ECDD0(_OWORD *a1, HCRYPTPROV a2, HCRYPTKEY *a3)
{
  char *v6; // rax
  void *v7; // rdi
  signed int LastError; // eax
  unsigned int v10; // ebx

  if ( !a1 || !a2 || !a3 )
    return 2147500035LL;
  if ( *a3 )
  {
    CryptDestroyKey(*a3);
    *a3 = 0;
  }
  v6 = (char *)CoTaskMemAlloc(0x1Cu);
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  *(_WORD *)v6 = 520;
  *((_DWORD *)v6 + 1) = 26126;
  *((_WORD *)v6 + 1) = 0;
  *((_DWORD *)v6 + 2) = 16;
  *(_OWORD *)(v6 + 12) = *a1;
  if ( CryptImportKey(a2, (const BYTE *)v6, 0x1Cu, 0, 1u, a3) )
  {
    v10 = 0;
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
  }
  CoTaskMemFree(v7);
  return v10;
}

```

## disassembly

```asm
0x1801ecdd0  mov     [rsp+arg_8], rbx
0x1801ecdd5  mov     [rsp+arg_10], rbp
0x1801ecdda  push    rsi
0x1801ecddb  sub     rsp, 30h
0x1801ecddf  mov     rbx, r8
0x1801ecde2  mov     rsi, rdx
0x1801ecde5  mov     rbp, rcx
0x1801ecde8  test    rcx, rcx
0x1801ecdeb  jz      loc_1801ECED9
0x1801ecdf1  test    rdx, rdx
0x1801ecdf4  jz      loc_1801ECED9
0x1801ecdfa  test    rbx, rbx
0x1801ecdfd  jz      loc_1801ECED9
0x1801ece03  mov     rcx, [r8]; hKey
0x1801ece06  mov     [rsp+38h+arg_0], rdi
0x1801ece0b  test    rcx, rcx
0x1801ece0e  jz      short loc_1801ECE23
0x1801ece10  call    cs:CryptDestroyKey
0x1801ece17  nop     dword ptr [rax+rax+00h]
0x1801ece1c  mov     qword ptr [rbx], 0
0x1801ece23  mov     ecx, 1Ch; cb
0x1801ece28  call    cs:CoTaskMemAlloc
0x1801ece2f  nop     dword ptr [rax+rax+00h]
0x1801ece34  mov     rdi, rax
0x1801ece37  test    rax, rax
0x1801ece3a  jnz     short loc_1801ECE57
0x1801ece3c  mov     eax, 8007000Eh
0x1801ece41  mov     rdi, [rsp+38h+arg_0]
0x1801ece46  mov     rbx, [rsp+38h+arg_8]
0x1801ece4b  mov     rbp, [rsp+38h+arg_10]
0x1801ece50  add     rsp, 30h
0x1801ece54  pop     rsi
0x1801ece55  retn
0x1801ece57  mov     word ptr [rax], 208h
0x1801ece5c  xor     r9d, r9d; hPubKey
0x1801ece5f  mov     dword ptr [rdi+4], 660Eh
0x1801ece66  xor     eax, eax
0x1801ece68  mov     [rdi+2], ax
0x1801ece6c  mov     r8d, 1Ch; dwDataLen
0x1801ece72  mov     dword ptr [rdi+8], 10h
0x1801ece79  mov     rdx, rdi; pbData
0x1801ece7c  movups  xmm0, xmmword ptr [rbp+0]
0x1801ece80  mov     [rsp+38h+phKey], rbx; phKey
0x1801ece85  mov     rcx, rsi; hProv
0x1801ece88  mov     [rsp+38h+dwFlags], 1; dwFlags
0x1801ece90  movups  xmmword ptr [rdi+0Ch], xmm0
0x1801ece94  call    cs:CryptImportKey
0x1801ece9b  nop     dword ptr [rax+rax+00h]
0x1801ecea0  test    eax, eax
0x1801ecea2  jnz     short loc_1801ECEC1
0x1801ecea4  call    cs:GetLastError
0x1801eceab  nop     dword ptr [rax+rax+00h]
0x1801eceb0  mov     ebx, eax
0x1801eceb2  test    eax, eax
0x1801eceb4  jle     short loc_1801ECEC3
0x1801eceb6  movzx   ebx, ax
0x1801eceb9  or      ebx, 80070000h
0x1801ecebf  jmp     short loc_1801ECEC3
0x1801ecec1  xor     ebx, ebx
0x1801ecec3  mov     rcx, rdi; pv
0x1801ecec6  call    cs:CoTaskMemFree
0x1801ececd  nop     dword ptr [rax+rax+00h]
0x1801eced2  mov     eax, ebx
0x1801eced4  jmp     loc_1801ECE41
0x1801eced9  mov     rbx, [rsp+38h+arg_8]
0x1801ecede  mov     eax, 80004003h
0x1801ecee3  mov     rbp, [rsp+38h+arg_10]
0x1801ecee8  add     rsp, 30h
0x1801eceec  pop     rsi
0x1801eceed  retn
```
