# GetCurrentKernelDumpType

- ea: `0x140006d34`
- end: `0x140007056`
- name: `GetCurrentKernelDumpType`
- size: `802`
- prototype: `LSTATUS __fastcall(_DWORD *pvData, _DWORD *, _DWORD *, _BYTE *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x140004e18`
- `0x140009c34`

## callees

- `0x140003224`
- `0x140006d34`
- `0x14000e098`
- `0x14001c99c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006d9d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006de7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006e24`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006e82`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006ec8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006f0a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006fae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006d9d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006de7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006e24`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006e82`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006ec8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006f0a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006fae`

## string_xrefs

- `0x140006ea7`: `Overwrite`

## pseudocode

```c
LSTATUS __fastcall GetCurrentKernelDumpType(_DWORD *pvData, _DWORD *a2, _DWORD *a3, _BYTE *a4)
{
  LSTATUS result; // eax
  bool v9; // cc
  _OWORD *v10; // rax
  PVOID v11; // rbx
  LSTATUS ValueW; // eax
  unsigned int v13; // edi
  PVOID Buf2[2]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v15; // [rsp+50h] [rbp-18h]
  DWORD pcbData; // [rsp+B0h] [rbp+48h] BYREF
  int v17; // [rsp+B8h] [rbp+50h] BYREF
  int v18; // [rsp+C0h] [rbp+58h] BYREF
  int v19; // [rsp+C8h] [rbp+60h] BYREF

  pcbData = 4;
  *pvData = 0;
  *a2 = 0;
  *a3 = 0;
  *a4 = 1;
  result = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\CrashControl",
             L"CrashDumpEnabled",
             0x10u,
             0,
             pvData,
             &pcbData);
  v9 = result <= 0;
  if ( result )
    goto LABEL_2;
  pcbData = 4;
  result = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\CrashControl",
             L"CrashDumpEnabled.Old",
             0x10u,
             0,
             a2,
             &pcbData);
  if ( (result & 0xFFFFFFFD) != 0
    || (pcbData = 4,
        result = RegGetValueW(
                   HKEY_LOCAL_MACHINE,
                   L"System\\CurrentControlSet\\Control\\CrashControl",
                   L"CrashDumpEnabled.New",
                   0x10u,
                   0,
                   a3,
                   &pcbData),
        (result & 0xFFFFFFFD) != 0) )
  {
LABEL_5:
    v9 = result <= 0;
    goto LABEL_2;
  }
  if ( *a3 && *pvData != *a3 || ((*pvData - 3) & 0xFFFFFFFB) != 0 )
    return 1;
  v17 = 0;
  pcbData = 4;
  result = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\CrashControl",
             L"AutoReboot",
             0x10u,
             0,
             &v17,
             &pcbData);
  v9 = result <= 0;
  if ( result )
    goto LABEL_2;
  if ( v17 != 1 )
    return 1;
  v18 = 0;
  pcbData = 4;
  result = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\CrashControl",
             L"Overwrite",
             0x10u,
             0,
             &v18,
             &pcbData);
  v9 = result <= 0;
  if ( result )
  {
LABEL_2:
    if ( !v9 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( v18 != 1 )
    return 1;
  v19 = 0;
  pcbData = 4;
  result = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\CrashControl",
             L"FilterPages",
             0x10u,
             0,
             &v19,
             &pcbData);
  if ( result )
  {
    if ( result == 2 )
      goto LABEL_19;
    goto LABEL_5;
  }
  if ( v19 )
    return 1;
LABEL_19:
  *(__m128i *)Buf2 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v15 = -1;
  if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(Buf2, 48) )
  {
    v10 = Buf2[1];
    v11 = Buf2[0];
    *(_OWORD *)Buf2[1] = 0;
    v10[1] = 0;
    v10[2] = 0;
    pcbData = 48;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"System\\CurrentControlSet\\Control\\CrashControl",
               L"DumpFile",
               0x10000006u,
               0,
               v11,
               &pcbData);
    v13 = ValueW;
    if ( ValueW )
    {
      if ( ValueW > 0 )
        v13 = (unsigned __int16)ValueW | 0x80070000;
      if ( v11 != (PVOID)-1LL )
        operator delete(v11, (const struct std::nothrow_t *)&std::nothrow);
      return v13;
    }
    else
    {
      if ( pcbData != 48 || memcmp_0(L"%SystemRoot%\\MEMORY.DMP", v11, 0x30u) )
      {
        if ( v11 != (PVOID)-1LL )
          operator delete(v11, (const struct std::nothrow_t *)&std::nothrow);
        return 1;
      }
      *a4 = 0;
      if ( v11 != (PVOID)-1LL )
        operator delete(v11, (const struct std::nothrow_t *)&std::nothrow);
      return 0;
    }
  }
  else
  {
    if ( Buf2[0] != (PVOID)-1LL )
      operator delete(Buf2[0], (const struct std::nothrow_t *)&std::nothrow);
    return -2147024882;
  }
}

```

## disassembly

```asm
0x140006d34  push    rbp
0x140006d36  push    rbx
0x140006d37  push    rsi
0x140006d38  push    rdi
0x140006d39  push    r12
0x140006d3b  push    r13
0x140006d3d  push    r14
0x140006d3f  push    r15
0x140006d41  mov     rbp, rsp
0x140006d44  sub     rsp, 68h
0x140006d48  xor     r15d, r15d
0x140006d4b  mov     [rbp+arg_0], 4
0x140006d52  mov     [rcx], r15d
0x140006d55  lea     rax, [rbp+arg_0]
0x140006d59  mov     [rdx], r15d
0x140006d5c  lea     r13, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Cra"...
0x140006d63  mov     [r8], r15d
0x140006d66  mov     r14, r9
0x140006d69  mov     [rsp+68h+pcbData], rax; pcbData
0x140006d6e  mov     rdi, r8
0x140006d71  mov     [rsp+68h+pvData], rcx; pvData
0x140006d76  lea     r8, aCrashdumpenabl; "CrashDumpEnabled"
0x140006d7d  mov     byte ptr [r9], 1
0x140006d81  mov     rsi, rdx
0x140006d84  mov     rbx, rcx
0x140006d87  mov     [rsp+68h+pdwType], r15; pdwType
0x140006d8c  mov     r12, 0FFFFFFFF80000002h
0x140006d93  lea     r9d, [r15+10h]; dwFlags
0x140006d97  mov     rdx, r13; lpSubKey
0x140006d9a  mov     rcx, r12; hkey
0x140006d9d  call    cs:__imp_RegGetValueW
0x140006da3  test    eax, eax
0x140006da5  jz      short loc_140006DBA
0x140006da7  jle     loc_140006F1F
0x140006dad  movzx   eax, ax
0x140006db0  or      eax, 80070000h
0x140006db5  jmp     loc_140006F1F
0x140006dba  lea     rax, [rbp+arg_0]
0x140006dbe  mov     [rbp+arg_0], 4
0x140006dc5  mov     [rsp+68h+pcbData], rax; pcbData
0x140006dca  lea     r8, aCrashdumpenabl_2; "CrashDumpEnabled.Old"
0x140006dd1  mov     [rsp+68h+pvData], rsi; pvData
0x140006dd6  mov     r9d, 10h; dwFlags
0x140006ddc  mov     rdx, r13; lpSubKey
0x140006ddf  mov     [rsp+68h+pdwType], r15; pdwType
0x140006de4  mov     rcx, r12; hkey
0x140006de7  call    cs:__imp_RegGetValueW
0x140006ded  test    eax, 0FFFFFFFDh
0x140006df2  jz      short loc_140006DF8
0x140006df4  test    eax, eax
0x140006df6  jmp     short loc_140006DA7
0x140006df8  mov     esi, 4
0x140006dfd  lea     rax, [rbp+arg_0]
0x140006e01  mov     [rsp+68h+pcbData], rax; pcbData
0x140006e06  lea     r8, aCrashdumpenabl_0; "CrashDumpEnabled.New"
0x140006e0d  mov     [rsp+68h+pvData], rdi; pvData
0x140006e12  mov     rdx, r13; lpSubKey
0x140006e15  mov     rcx, r12; hkey
0x140006e18  mov     [rbp+arg_0], esi
0x140006e1b  lea     r9d, [rsi+0Ch]; dwFlags
0x140006e1f  mov     [rsp+68h+pdwType], r15; pdwType
0x140006e24  call    cs:__imp_RegGetValueW
0x140006e2a  test    eax, 0FFFFFFFDh
0x140006e2f  jnz     short loc_140006DF4
0x140006e31  mov     eax, [rdi]
0x140006e33  test    eax, eax
0x140006e35  jz      short loc_140006E3F
0x140006e37  cmp     [rbx], eax
0x140006e39  jnz     loc_140006F1A
0x140006e3f  mov     eax, [rbx]
0x140006e41  sub     eax, 3
0x140006e44  test    eax, 0FFFFFFFBh
0x140006e49  jnz     loc_140006F1A
0x140006e4f  lea     rax, [rbp+arg_0]
0x140006e53  mov     [rbp+arg_8], r15d
0x140006e57  mov     [rsp+68h+pcbData], rax; pcbData
0x140006e5c  lea     r8, aAutoreboot; "AutoReboot"
0x140006e63  lea     rax, [rbp+arg_8]
0x140006e67  mov     [rbp+arg_0], esi
0x140006e6a  mov     [rsp+68h+pvData], rax; pvData
0x140006e6f  mov     ebx, 10h
0x140006e74  mov     r9d, ebx; dwFlags
0x140006e77  mov     [rsp+68h+pdwType], r15; pdwType
0x140006e7c  mov     rdx, r13; lpSubKey
0x140006e7f  mov     rcx, r12; hkey
0x140006e82  call    cs:__imp_RegGetValueW
0x140006e88  test    eax, eax
0x140006e8a  jnz     loc_140006DA7
0x140006e90  cmp     [rbp+arg_8], 1
0x140006e94  jnz     loc_140006F1A
0x140006e9a  lea     rax, [rbp+arg_0]
0x140006e9e  mov     [rbp+arg_10], r15d
0x140006ea2  mov     [rsp+68h+pcbData], rax; pcbData
0x140006ea7  lea     r8, aOverwrite; "Overwrite"
0x140006eae  lea     rax, [rbp+arg_10]
0x140006eb2  mov     [rbp+arg_0], esi
0x140006eb5  mov     [rsp+68h+pvData], rax; pvData
0x140006eba  mov     r9d, ebx; dwFlags
0x140006ebd  mov     rdx, r13; lpSubKey
0x140006ec0  mov     [rsp+68h+pdwType], r15; pdwType
0x140006ec5  mov     rcx, r12; hkey
0x140006ec8  call    cs:__imp_RegGetValueW
0x140006ece  test    eax, eax
0x140006ed0  jnz     loc_140006DA7
0x140006ed6  cmp     [rbp+arg_10], 1
0x140006eda  jnz     short loc_140006F1A
0x140006edc  lea     rax, [rbp+arg_0]
0x140006ee0  mov     [rbp+arg_18], r15d
0x140006ee4  mov     [rsp+68h+pcbData], rax; pcbData
0x140006ee9  lea     r8, aFilterpages; "FilterPages"
0x140006ef0  lea     rax, [rbp+arg_18]
0x140006ef4  mov     [rbp+arg_0], esi
0x140006ef7  mov     [rsp+68h+pvData], rax; pvData
0x140006efc  mov     r9d, ebx; dwFlags
0x140006eff  mov     rdx, r13; lpSubKey
0x140006f02  mov     [rsp+68h+pdwType], r15; pdwType
0x140006f07  mov     rcx, r12; hkey
0x140006f0a  call    cs:__imp_RegGetValueW
0x140006f10  test    eax, eax
0x140006f12  jnz     short loc_140006F30
0x140006f14  cmp     [rbp+arg_18], r15d
0x140006f18  jz      short loc_140006F39
0x140006f1a  mov     eax, 1
0x140006f1f  add     rsp, 68h
0x140006f23  pop     r15
0x140006f25  pop     r14
0x140006f27  pop     r13
0x140006f29  pop     r12
0x140006f2b  pop     rdi
0x140006f2c  pop     rsi
0x140006f2d  pop     rbx
0x140006f2e  pop     rbp
0x140006f2f  retn
0x140006f30  cmp     eax, 2
0x140006f33  jnz     loc_140006DF4
0x140006f39  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140006f41  lea     rcx, [rbp+Buf2]
0x140006f45  or      r12, 0FFFFFFFFFFFFFFFFh
0x140006f49  movdqu  xmmword ptr [rbp+Buf2], xmm0
0x140006f4e  mov     [rbp+var_18], r12
0x140006f52  lea     edx, [r12+31h]
0x140006f57  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x140006f5c  test    al, al
0x140006f5e  jz      loc_140007037
0x140006f64  mov     rax, [rbp+Buf2+8]
0x140006f68  lea     r8, aDumpfile; "DumpFile"
0x140006f6f  mov     rbx, [rbp+Buf2]
0x140006f73  xorps   xmm0, xmm0
0x140006f76  mov     r9d, 10000006h; dwFlags
0x140006f7c  mov     rdx, r13; lpSubKey
0x140006f7f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140006f86  movups  xmmword ptr [rax], xmm0
0x140006f89  lea     rsi, [rbx+30h]
0x140006f8d  movups  xmmword ptr [rax+10h], xmm0
0x140006f91  sub     rsi, rbx
0x140006f94  movups  xmmword ptr [rax+20h], xmm0
0x140006f98  lea     rax, [rbp+arg_0]
0x140006f9c  mov     [rbp+arg_0], esi
0x140006f9f  mov     [rsp+68h+pcbData], rax; pcbData
0x140006fa4  mov     [rsp+68h+pvData], rbx; pvData
0x140006fa9  mov     [rsp+68h+pdwType], r15; pdwType
0x140006fae  call    cs:__imp_RegGetValueW
0x140006fb4  mov     edi, eax
0x140006fb6  test    eax, eax
0x140006fb8  jz      short loc_140006FE0
0x140006fba  jle     short loc_140006FC5
0x140006fbc  movzx   edi, ax
0x140006fbf  or      edi, 80070000h
0x140006fc5  cmp     rbx, r12
0x140006fc8  jz      short loc_140006FD9
0x140006fca  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140006fd1  mov     rcx, rbx; void *
0x140006fd4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140006fd9  mov     eax, edi
0x140006fdb  jmp     loc_140006F1F
0x140006fe0  mov     r8d, [rbp+arg_0]; Size
0x140006fe4  cmp     r8, rsi
0x140006fe7  jz      short loc_140007006
0x140006fe9  cmp     rbx, r12
0x140006fec  jz      loc_140006F1A
0x140006ff2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140006ff9  mov     rcx, rbx; void *
0x140006ffc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140007001  jmp     loc_140006F1A
0x140007006  mov     rdx, rbx; Buf2
0x140007009  lea     rcx, aSystemrootMemo; "%SystemRoot%\\MEMORY.DMP"
0x140007010  call    memcmp_0
0x140007015  test    eax, eax
0x140007017  jnz     short loc_140006FE9
0x140007019  mov     [r14], r15b
0x14000701c  cmp     rbx, r12
0x14000701f  jz      short loc_140007030
0x140007021  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140007028  mov     rcx, rbx; void *
0x14000702b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140007030  xor     eax, eax
0x140007032  jmp     loc_140006F1F
0x140007037  mov     rcx, [rbp+Buf2]; void *
0x14000703b  cmp     rcx, r12
0x14000703e  jz      short loc_14000704C
0x140007040  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140007047  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000704c  mov     eax, 8007000Eh
0x140007051  jmp     loc_140006F1F
```
