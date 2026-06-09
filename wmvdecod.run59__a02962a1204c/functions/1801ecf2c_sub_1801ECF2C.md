# sub_1801ECF2C

- ea: `0x1801ecf2c`
- end: `0x1801ed00c`
- name: `sub_1801ECF2C`
- size: `224`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c5ae8`
- `0x1800c5fb8`

## callees

- `0x1800ad3e0`
- `0x1801ecf2c`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptImportKey` at `0x1801ecfc0`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptImportKey` at `0x1801ecfc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ecfd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ecfd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ecf4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ecf4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ecfee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ecfee`

## pseudocode

```c
__int64 __fastcall sub_1801ECF2C(HCRYPTPROV *a1, const void *a2, unsigned int a3, int a4, HCRYPTKEY *phKey)
{
  size_t v5; // rsi
  DWORD v9; // ebp
  BYTE *v10; // rax
  BYTE *v11; // rdi
  unsigned int v12; // ebx
  signed int LastError; // eax

  v5 = a3;
  v9 = a3 + 20;
  v10 = (BYTE *)CoTaskMemAlloc(a3 + 20);
  v11 = v10;
  if ( v10 )
  {
    *(_WORD *)v10 = 518;
    *((_DWORD *)v10 + 1) = 41984;
    *((_WORD *)v10 + 1) = 0;
    *((_DWORD *)v10 + 2) = 826364754;
    *((_DWORD *)v10 + 3) = 8 * v5;
    v12 = 0;
    *((_DWORD *)v10 + 4) = a4;
    memcpy(v10 + 20, a2, v5);
    if ( !CryptImportKey(*a1, v11, v9, 0, 0, phKey) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
    }
    CoTaskMemFree(v11);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v12;
}

```

## disassembly

```asm
0x1801ecf2c  push    rbx
0x1801ecf2e  push    rbp
0x1801ecf2f  push    rsi
0x1801ecf30  push    rdi
0x1801ecf31  push    r12
0x1801ecf33  push    r14
0x1801ecf35  push    r15
0x1801ecf37  sub     rsp, 30h
0x1801ecf3b  mov     esi, r8d
0x1801ecf3e  mov     r12, rcx
0x1801ecf41  mov     r14d, r9d
0x1801ecf44  mov     r15, rdx
0x1801ecf47  lea     ebp, [rsi+14h]
0x1801ecf4a  mov     ecx, ebp; cb
0x1801ecf4c  call    cs:CoTaskMemAlloc
0x1801ecf53  nop     dword ptr [rax+rax+00h]
0x1801ecf58  mov     rdi, rax
0x1801ecf5b  test    rax, rax
0x1801ecf5e  jnz     short loc_1801ECF6A
0x1801ecf60  mov     ebx, 8007000Eh
0x1801ecf65  jmp     loc_1801ECFFA
0x1801ecf6a  mov     word ptr [rax], 206h
0x1801ecf6f  lea     rcx, [rdi+14h]; void *
0x1801ecf73  xor     eax, eax
0x1801ecf75  mov     dword ptr [rdi+4], 0A400h
0x1801ecf7c  mov     [rdi+2], ax
0x1801ecf80  mov     r8, rsi; Size
0x1801ecf83  lea     eax, ds:0[rsi*8]
0x1801ecf8a  mov     dword ptr [rdi+8], 31415352h
0x1801ecf91  mov     rdx, r15; Src
0x1801ecf94  mov     [rdi+0Ch], eax
0x1801ecf97  xor     ebx, ebx
0x1801ecf99  mov     [rdi+10h], r14d
0x1801ecf9d  call    memcpy
0x1801ecfa2  mov     rax, [rsp+68h+arg_20]
0x1801ecfaa  xor     r9d, r9d; hPubKey
0x1801ecfad  mov     rcx, [r12]; hProv
0x1801ecfb1  mov     r8d, ebp; dwDataLen
0x1801ecfb4  mov     [rsp+68h+phKey], rax; phKey
0x1801ecfb9  mov     rdx, rdi; pbData
0x1801ecfbc  mov     [rsp+68h+dwFlags], ebx; dwFlags
0x1801ecfc0  call    cs:CryptImportKey
0x1801ecfc7  nop     dword ptr [rax+rax+00h]
0x1801ecfcc  test    eax, eax
0x1801ecfce  jnz     short loc_1801ECFEB
0x1801ecfd0  call    cs:GetLastError
0x1801ecfd7  nop     dword ptr [rax+rax+00h]
0x1801ecfdc  mov     ebx, eax
0x1801ecfde  test    eax, eax
0x1801ecfe0  jle     short loc_1801ECFEB
0x1801ecfe2  movzx   ebx, ax
0x1801ecfe5  or      ebx, 80070000h
0x1801ecfeb  mov     rcx, rdi; pv
0x1801ecfee  call    cs:CoTaskMemFree
0x1801ecff5  nop     dword ptr [rax+rax+00h]
0x1801ecffa  mov     eax, ebx
0x1801ecffc  add     rsp, 30h
0x1801ed000  pop     r15
0x1801ed002  pop     r14
0x1801ed004  pop     r12
0x1801ed006  pop     rdi
0x1801ed007  pop     rsi
0x1801ed008  pop     rbp
0x1801ed009  pop     rbx
0x1801ed00a  retn
```
