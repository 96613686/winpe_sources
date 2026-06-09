# PopulateRepairInfo(tagRepairInfoMap const *,tagRepairInfo *)

- ea: `0x180012510`
- end: `0x180012621`
- name: `?PopulateRepairInfo@@YAJPEBUtagRepairInfoMap@@PEAUtagRepairInfo@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(const struct tagRepairInfoMap *, struct tagRepairInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180007800`

## callees

- `0x180012510`
- `0x180012d62`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18001255f`
- `msvcrt!wcsnlen` at `0x18001255f`
- `KERNEL32!GetLastError` at `0x1800125e3`
- `KERNEL32!GetLastError` at `0x1800125e3`
- `USER32!LoadStringW` at `0x1800125d3`
- `USER32!LoadStringW` at `0x1800125d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012576`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800125ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012576`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800125ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012601`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012601`

## pseudocode

```c
__int64 __fastcall PopulateRepairInfo(const struct tagRepairInfoMap *a1, struct tagRepairInfo *a2)
{
  SIZE_T v4; // rbp
  WCHAR *v5; // rax
  WCHAR *v6; // rdi
  unsigned int v7; // ebx
  WCHAR *v8; // rax
  WCHAR *v9; // rdi
  signed int LastError; // eax

  *a2 = *(struct tagRepairInfo *)((char *)a1 + 8);
  v4 = 2 * wcsnlen(*((const wchar_t **)a1 + 3), 0x100u) + 2;
  v5 = (WCHAR *)CoTaskMemAlloc(v4);
  v6 = v5;
  if ( v5
    && (memcpy_0(v5, *((const void **)a1 + 3), v4),
        a2->pwszClassName = v6,
        v8 = (WCHAR *)CoTaskMemAlloc(0x800u),
        (v9 = v8) != 0) )
  {
    if ( LoadStringW(hInstance, *((_DWORD *)a1 + 1), v8, 1024) )
    {
      v7 = 0;
      a2->pwszDescription = v9;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      CoTaskMemFree(v9);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x180012510  push    rbx
0x180012512  push    rbp
0x180012513  push    rsi
0x180012514  push    rdi
0x180012515  sub     rsp, 28h
0x180012519  movups  xmm0, xmmword ptr [rcx+8]
0x18001251d  mov     rsi, rdx
0x180012520  mov     rbx, rcx
0x180012523  movups  xmmword ptr [rdx], xmm0
0x180012526  movups  xmm1, xmmword ptr [rcx+18h]
0x18001252a  movups  xmmword ptr [rdx+10h], xmm1
0x18001252e  movups  xmm0, xmmword ptr [rcx+28h]
0x180012532  movups  xmmword ptr [rdx+20h], xmm0
0x180012536  movups  xmm1, xmmword ptr [rcx+38h]
0x18001253a  movups  xmmword ptr [rdx+30h], xmm1
0x18001253e  movups  xmm0, xmmword ptr [rcx+48h]
0x180012542  movups  xmmword ptr [rdx+40h], xmm0
0x180012546  movups  xmm1, xmmword ptr [rcx+58h]
0x18001254a  movups  xmmword ptr [rdx+50h], xmm1
0x18001254e  movups  xmm0, xmmword ptr [rcx+68h]
0x180012552  movups  xmmword ptr [rdx+60h], xmm0
0x180012556  mov     rcx, [rcx+18h]; Source
0x18001255a  mov     edx, 100h; MaxCount
0x18001255f  call    cs:__imp_wcsnlen
0x180012566  nop     dword ptr [rax+rax+00h]
0x18001256b  lea     rbp, ds:2[rax*2]
0x180012573  mov     rcx, rbp; cb
0x180012576  call    cs:__imp_CoTaskMemAlloc
0x18001257d  nop     dword ptr [rax+rax+00h]
0x180012582  mov     rdi, rax
0x180012585  test    rax, rax
0x180012588  jnz     short loc_180012594
0x18001258a  mov     ebx, 8007000Eh
0x18001258f  jmp     loc_180012615
0x180012594  mov     rdx, [rbx+18h]; Src
0x180012598  mov     r8, rbp; Size
0x18001259b  mov     rcx, rdi; void *
0x18001259e  call    memcpy_0
0x1800125a3  mov     ecx, 800h; cb
0x1800125a8  mov     [rsi+10h], rdi
0x1800125ac  call    cs:__imp_CoTaskMemAlloc
0x1800125b3  nop     dword ptr [rax+rax+00h]
0x1800125b8  mov     rdi, rax
0x1800125bb  test    rax, rax
0x1800125be  jz      short loc_18001258A
0x1800125c0  mov     edx, [rbx+4]; uID
0x1800125c3  mov     r9d, 400h; cchBufferMax
0x1800125c9  mov     rcx, cs:hInstance; hInstance
0x1800125d0  mov     r8, rax; lpBuffer
0x1800125d3  call    cs:__imp_LoadStringW
0x1800125da  nop     dword ptr [rax+rax+00h]
0x1800125df  test    eax, eax
0x1800125e1  jnz     short loc_18001260F
0x1800125e3  call    cs:__imp_GetLastError
0x1800125ea  nop     dword ptr [rax+rax+00h]
0x1800125ef  mov     ebx, eax
0x1800125f1  test    eax, eax
0x1800125f3  jle     short loc_1800125FE
0x1800125f5  movzx   ebx, ax
0x1800125f8  or      ebx, 80070000h
0x1800125fe  mov     rcx, rdi; pv
0x180012601  call    cs:__imp_CoTaskMemFree
0x180012608  nop     dword ptr [rax+rax+00h]
0x18001260d  jmp     short loc_180012615
0x18001260f  xor     ebx, ebx
0x180012611  mov     [rsi+18h], rdi
0x180012615  mov     eax, ebx
0x180012617  add     rsp, 28h
0x18001261b  pop     rdi
0x18001261c  pop     rsi
0x18001261d  pop     rbp
0x18001261e  pop     rbx
0x18001261f  retn
```
