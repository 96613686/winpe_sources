# CreateInstanceName(ushort * *)

- ea: `0x18002b284`
- end: `0x18002b3ec`
- name: `?CreateInstanceName@@YAHPEAPEAG@Z`
- size: `360`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18003216c`

## callees

- `0x1800037a8`
- `0x18002b284`
- `0x180034510`
- `0x180034e6c`
- `0x180034ecc`
- `0x18004c5d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002b2fd`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002b2fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002b2d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002b2d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002b347`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002b347`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b3b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c8a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b3b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c8a3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b32e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b32e`

## string_xrefs

- `0x18002b39d`: `CreateInstanceName:122`

## pseudocode

```c
__int64 __fastcall CreateInstanceName(unsigned __int16 **a1)
{
  unsigned int v2; // esi
  wchar_t *v3; // rbx
  DWORD ModuleFileNameW; // eax
  wchar_t *v5; // rax
  size_t v6; // rdx
  WCHAR *v7; // rdi
  __int64 v8; // rax
  unsigned int v9; // r14d
  DWORD CurrentProcessId; // [rsp+20h] [rbp-258h]
  WCHAR Filename[264]; // [rsp+40h] [rbp-238h] BYREF

  v2 = 0;
  memset_0(Filename, 0, 0x20Au);
  v3 = 0;
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  if ( !ModuleFileNameW || ModuleFileNameW == 260 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000000) != 0 )
      LDAPClientPrint(0x4000000, "%s  Failed to get process name\n", "CreateInstanceName:122");
  }
  else
  {
    v5 = wcsrchr(Filename, 0x5Cu);
    v7 = Filename;
    if ( v5 )
      v7 = v5 + 1;
    v8 = (unsigned int)wcsnlen_s(v7, v6) + 20;
    v9 = v8;
    v3 = (wchar_t *)LocalAlloc(0x40u, 2 * v8);
    if ( v3 )
    {
      CurrentProcessId = GetCurrentProcessId();
      swprintf_s(v3, v9, L"%s:%d", v7, CurrentProcessId);
      v2 = 1;
      *a1 = v3;
      v3 = 0;
    }
  }
  LocalFree(v3);
  return v2;
}

```

## disassembly

```asm
0x18002b284  mov     [rsp+arg_8], rbx
0x18002b289  mov     [rsp+arg_10], rsi
0x18002b28e  push    rdi
0x18002b28f  push    r14
0x18002b291  push    r15
0x18002b293  sub     rsp, 260h
0x18002b29a  mov     rax, cs:__security_cookie
0x18002b2a1  xor     rax, rsp
0x18002b2a4  mov     [rsp+278h+var_28], rax
0x18002b2ac  mov     r15, rcx
0x18002b2af  xor     esi, esi
0x18002b2b1  xor     edx, edx; Val
0x18002b2b3  mov     r8d, 20Ah; Size
0x18002b2b9  lea     rcx, [rsp+278h+Filename]; void *
0x18002b2be  call    memset_0
0x18002b2c3  xor     ebx, ebx
0x18002b2c5  mov     [rsp+278h+var_248], rbx
0x18002b2ca  mov     edi, 104h
0x18002b2cf  mov     r8d, edi; nSize
0x18002b2d2  lea     rdx, [rsp+278h+Filename]; lpFilename
0x18002b2d7  xor     ecx, ecx; hModule
0x18002b2d9  call    cs:__imp_GetModuleFileNameW
0x18002b2e0  nop     dword ptr [rax+rax+00h]
0x18002b2e5  test    eax, eax
0x18002b2e7  jz      loc_18002B37D
0x18002b2ed  cmp     eax, edi
0x18002b2ef  jz      loc_18002B37D
0x18002b2f5  lea     edx, [rsi+5Ch]; Ch
0x18002b2f8  lea     rcx, [rsp+278h+Filename]; Str
0x18002b2fd  call    cs:__imp_wcsrchr
0x18002b304  nop     dword ptr [rax+rax+00h]
0x18002b309  test    rax, rax
0x18002b30c  lea     rdi, [rsp+278h+Filename]
0x18002b311  jz      short loc_18002B317
0x18002b313  lea     rdi, [rax+2]
0x18002b317  mov     rcx, rdi; Source
0x18002b31a  call    wcsnlen_s
0x18002b31f  add     eax, 14h
0x18002b322  mov     r14d, eax
0x18002b325  lea     rdx, [rax+rax]; uBytes
0x18002b329  mov     ecx, 40h ; '@'; uFlags
0x18002b32e  call    cs:__imp_LocalAlloc
0x18002b335  nop     dword ptr [rax+rax+00h]
0x18002b33a  mov     rbx, rax
0x18002b33d  mov     [rsp+278h+var_248], rax
0x18002b342  test    rax, rax
0x18002b345  jz      short loc_18002B3B1
0x18002b347  call    cs:__imp_GetCurrentProcessId
0x18002b34e  nop     dword ptr [rax+rax+00h]
0x18002b353  mov     [rsp+278h+var_258], eax
0x18002b357  mov     r9, rdi
0x18002b35a  lea     r8, aSD; "%s:%d"
0x18002b361  mov     edx, r14d; BufferCount
0x18002b364  mov     rcx, rbx; Buffer
0x18002b367  call    swprintf_s
0x18002b36c  mov     esi, 1
0x18002b371  mov     [r15], rbx
0x18002b374  xor     ebx, ebx
0x18002b376  mov     [rsp+278h+var_248], rbx
0x18002b37b  jmp     short loc_18002B3B1
0x18002b37d  cmp     cs:g_fTracingOn, 0
0x18002b384  jz      short loc_18002B3B1
0x18002b386  cmp     cs:g_fProviderEnabled, 0
0x18002b38d  jz      short loc_18002B3B1
0x18002b38f  mov     ecx, 4000000h
0x18002b394  test    cs:g_ulTraceFlags, rcx
0x18002b39b  jz      short loc_18002B3B1
0x18002b39d  lea     r8, aCreateinstance; "CreateInstanceName:122"
0x18002b3a4  lea     rdx, aSFailedToGetPr; "%s  Failed to get process name\n"
0x18002b3ab  call    LDAPClientPrint
0x18002b3b0  nop
0x18002b3b1  mov     rcx, rbx; hMem
0x18002b3b4  call    cs:__imp_LocalFree
0x18002b3bb  nop     dword ptr [rax+rax+00h]
0x18002b3c0  mov     eax, esi
0x18002b3c2  mov     rcx, [rsp+278h+var_28]
0x18002b3ca  xor     rcx, rsp; StackCookie
0x18002b3cd  call    __security_check_cookie
0x18002b3d2  lea     r11, [rsp+278h+var_18]
0x18002b3da  mov     rbx, [r11+28h]
0x18002b3de  mov     rsi, [r11+30h]
0x18002b3e2  mov     rsp, r11
0x18002b3e5  pop     r15
0x18002b3e7  pop     r14
0x18002b3e9  pop     rdi
0x18002b3ea  retn
0x18004c896  push    rbp
0x18004c898  sub     rsp, 30h
0x18004c89c  mov     rbp, rdx
0x18004c89f  mov     rcx, [rbp+30h]; hMem
0x18004c8a3  call    cs:__imp_LocalFree
0x18004c8aa  nop     dword ptr [rax+rax+00h]
0x18004c8af  nop
0x18004c8b0  add     rsp, 30h
0x18004c8b4  pop     rbp
0x18004c8b5  retn
```
