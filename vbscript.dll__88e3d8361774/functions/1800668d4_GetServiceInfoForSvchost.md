# GetServiceInfoForSvchost

- ea: `0x1800668d4`
- end: `0x180066ad5`
- name: `GetServiceInfoForSvchost`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180066ec4`

## callees

- `0x180045484`
- `0x180045dd4`
- `0x1800668d4`
- `0x180077010`

## import_xrefs

- `msvcrt!_mbsnbcpy_s` at `0x180066a9a`
- `msvcrt!_mbsnbcpy_s` at `0x180066a9a`
- `KERNEL32!LoadLibraryA` at `0x1800668ff`
- `KERNEL32!LoadLibraryA` at `0x1800668ff`
- `KERNEL32!FreeLibrary` at `0x180066ab6`
- `KERNEL32!FreeLibrary` at `0x180066ab6`
- `KERNEL32!GetProcAddress` at `0x18006691b`
- `KERNEL32!GetProcAddress` at `0x18006692e`
- `KERNEL32!GetProcAddress` at `0x180066941`
- `KERNEL32!GetProcAddress` at `0x18006691b`
- `KERNEL32!GetProcAddress` at `0x18006692e`
- `KERNEL32!GetProcAddress` at `0x180066941`

## string_xrefs

- `0x1800668f5`: `advapi32.dll`
- `0x180066911`: `OpenSCManagerA`
- `0x180066921`: `EnumServicesStatusExA`
- `0x180066934`: `CloseServiceHandle`

## pseudocode

```c
int __fastcall GetServiceInfoForSvchost(int a1, unsigned __int8 *a2, unsigned __int64 a3)
{
  HMODULE LibraryA; // rax
  HMODULE v6; // rdi
  FARPROC ProcAddress; // rbx
  FARPROC v8; // rbp
  FARPROC v9; // rax
  void (__fastcall *v10)(__int64); // r15
  __int64 v11; // rax
  __int64 v12; // rsi
  char *v13; // rbx
  unsigned int v14; // ecx
  __int64 v15; // r8
  unsigned int v17; // [rsp+98h] [rbp+10h] BYREF
  unsigned __int64 v18; // [rsp+A0h] [rbp+18h] BYREF

  v18 = a3;
  *a2 = 0;
  LibraryA = LoadLibraryA("advapi32.dll");
  v6 = LibraryA;
  if ( LibraryA )
  {
    ProcAddress = GetProcAddress(LibraryA, "OpenSCManagerA");
    v8 = GetProcAddress(v6, "EnumServicesStatusExA");
    v9 = GetProcAddress(v6, "CloseServiceHandle");
    v10 = (void (__fastcall *)(__int64))v9;
    if ( ProcAddress )
    {
      if ( v8 )
      {
        if ( v9 )
        {
          v11 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))ProcAddress)(0, 0, 4);
          v12 = v11;
          if ( v11 )
          {
            LODWORD(v18) = 0;
            v17 = 0;
            ((void (__fastcall *)(__int64, _QWORD, __int64, __int64, _QWORD, _DWORD, unsigned __int64 *, unsigned int *, _QWORD, _QWORD))v8)(
              v11,
              0,
              48,
              3,
              0,
              0,
              &v18,
              &v17,
              0,
              0);
            if ( (_DWORD)v18 )
            {
              v13 = (char *)operator new[]((unsigned int)v18, (const struct std::nothrow_t *)&std::nothrow);
              if ( v13 )
              {
                if ( ((unsigned int (__fastcall *)(__int64, _QWORD, __int64, __int64, char *, _DWORD, unsigned __int64 *, unsigned int *, _QWORD, _QWORD))v8)(
                       v12,
                       0,
                       48,
                       3,
                       v13,
                       v18,
                       &v18,
                       &v17,
                       0,
                       0) )
                {
                  v14 = 0;
                  if ( v17 )
                  {
                    while ( 1 )
                    {
                      v15 = 56LL * v14;
                      if ( *(_DWORD *)&v13[v15 + 44] == a1 )
                        break;
                      if ( ++v14 >= v17 )
                        goto LABEL_14;
                    }
                    _mbsnbcpy_s(a2, 0x100u, *(const unsigned __int8 **)&v13[v15 + 8], 0xFFFFFFFFFFFFFFFFuLL);
                  }
                }
LABEL_14:
                operator delete[](v13);
              }
            }
            v10(v12);
          }
        }
      }
    }
    LODWORD(LibraryA) = FreeLibrary(v6);
  }
  return (int)LibraryA;
}

```

## disassembly

```asm
0x1800668d4  mov     [rsp+arg_0], rbx
0x1800668d9  mov     [rsp+arg_18], rbp
0x1800668de  mov     [rsp+arg_10], r8
0x1800668e3  push    rsi
0x1800668e4  push    rdi
0x1800668e5  push    r12
0x1800668e7  push    r14
0x1800668e9  push    r15
0x1800668eb  sub     rsp, 60h
0x1800668ef  mov     r12d, ecx
0x1800668f2  mov     byte ptr [rdx], 0
0x1800668f5  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x1800668fc  mov     r14, rdx
0x1800668ff  call    cs:__imp_LoadLibraryA
0x180066905  mov     rdi, rax
0x180066908  test    rax, rax
0x18006690b  jz      loc_180066ABC
0x180066911  lea     rdx, aOpenscmanagera; "OpenSCManagerA"
0x180066918  mov     rcx, rax; hModule
0x18006691b  call    cs:__imp_GetProcAddress
0x180066921  lea     rdx, aEnumservicesst; "EnumServicesStatusExA"
0x180066928  mov     rcx, rdi; hModule
0x18006692b  mov     rbx, rax
0x18006692e  call    cs:__imp_GetProcAddress
0x180066934  lea     rdx, aCloseserviceha; "CloseServiceHandle"
0x18006693b  mov     rcx, rdi; hModule
0x18006693e  mov     rbp, rax
0x180066941  call    cs:__imp_GetProcAddress
0x180066947  mov     r15, rax
0x18006694a  test    rbx, rbx
0x18006694d  jz      loc_180066AB3
0x180066953  test    rbp, rbp
0x180066956  jz      loc_180066AB3
0x18006695c  test    rax, rax
0x18006695f  jz      loc_180066AB3
0x180066965  xor     edx, edx
0x180066967  xor     ecx, ecx
0x180066969  mov     rax, rbx
0x18006696c  lea     r8d, [rdx+4]
0x180066970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066975  mov     rsi, rax
0x180066978  test    rax, rax
0x18006697b  jz      loc_180066AB3
0x180066981  mov     [rsp+88h+var_40], 0
0x18006698a  lea     rax, [rsp+88h+arg_8]
0x180066992  mov     [rsp+88h+var_48], 0
0x18006699b  xor     edx, edx
0x18006699d  mov     [rsp+88h+var_50], rax
0x1800669a2  mov     rcx, rsi
0x1800669a5  lea     rax, [rsp+88h+arg_10]
0x1800669ad  mov     dword ptr [rsp+88h+arg_10], 0
0x1800669b8  mov     [rsp+88h+var_58], rax
0x1800669bd  mov     rax, rbp
0x1800669c0  mov     [rsp+88h+var_60], 0
0x1800669c8  lea     r9d, [rdx+3]
0x1800669cc  lea     r8d, [rdx+30h]
0x1800669d0  mov     [rsp+88h+var_68], 0
0x1800669d9  mov     [rsp+88h+arg_8], 0
0x1800669e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800669e9  mov     eax, dword ptr [rsp+88h+arg_10]
0x1800669f0  test    eax, eax
0x1800669f2  jz      loc_180066AA8
0x1800669f8  mov     ecx, eax; unsigned __int64
0x1800669fa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180066a01  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180066a06  mov     rbx, rax
0x180066a09  test    rax, rax
0x180066a0c  jz      loc_180066AA8
0x180066a12  mov     ecx, dword ptr [rsp+88h+arg_10]
0x180066a19  lea     rax, [rsp+88h+arg_8]
0x180066a21  mov     [rsp+88h+var_40], 0
0x180066a2a  xor     edx, edx
0x180066a2c  mov     [rsp+88h+var_48], 0
0x180066a35  mov     [rsp+88h+var_50], rax
0x180066a3a  lea     rax, [rsp+88h+arg_10]
0x180066a42  mov     [rsp+88h+var_58], rax
0x180066a47  mov     rax, rbp
0x180066a4a  mov     [rsp+88h+var_60], ecx
0x180066a4e  lea     r9d, [rdx+3]
0x180066a52  mov     rcx, rsi
0x180066a55  mov     [rsp+88h+var_68], rbx
0x180066a5a  lea     r8d, [rdx+30h]
0x180066a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a63  test    eax, eax
0x180066a65  jz      short loc_180066AA0
0x180066a67  mov     edx, [rsp+88h+arg_8]
0x180066a6e  xor     ecx, ecx
0x180066a70  test    edx, edx
0x180066a72  jz      short loc_180066AA0
0x180066a74  mov     eax, ecx
0x180066a76  imul    r8, rax, 38h ; '8'
0x180066a7a  cmp     [r8+rbx+2Ch], r12d
0x180066a7f  jz      short loc_180066A89
0x180066a81  inc     ecx
0x180066a83  cmp     ecx, edx
0x180066a85  jb      short loc_180066A74
0x180066a87  jmp     short loc_180066AA0
0x180066a89  mov     r8, [r8+rbx+8]; Src
0x180066a8e  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180066a92  mov     edx, 100h; SizeInBytes
0x180066a97  mov     rcx, r14; Dst
0x180066a9a  call    cs:__imp__mbsnbcpy_s
0x180066aa0  mov     rcx, rbx; Block
0x180066aa3  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180066aa8  mov     rcx, rsi
0x180066aab  mov     rax, r15
0x180066aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ab3  mov     rcx, rdi; hLibModule
0x180066ab6  call    cs:__imp_FreeLibrary
0x180066abc  lea     r11, [rsp+88h+var_28]
0x180066ac1  mov     rbx, [r11+30h]
0x180066ac5  mov     rbp, [r11+48h]
0x180066ac9  mov     rsp, r11
0x180066acc  pop     r15
0x180066ace  pop     r14
0x180066ad0  pop     r12
0x180066ad2  pop     rdi
0x180066ad3  pop     rsi
0x180066ad4  retn
```
