# WdsCreateStandardPathFromExtendedPath

- ea: `0x18001b3a0`
- end: `0x18001b4b6`
- name: `WdsCreateStandardPathFromExtendedPath`
- size: `278`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x1800148d0`
- `0x1800165a0`
- `0x18001a28c`
- `0x18001b3a0`
- `0x18002e468`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001b3e6`
- `msvcrt!_wcsnicmp` at `0x18001b427`
- `msvcrt!_wcsnicmp` at `0x18001b3e6`
- `msvcrt!_wcsnicmp` at `0x18001b427`

## pseudocode

```c
__int64 __fastcall WdsCreateStandardPathFromExtendedPath(unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v3; // rcx
  signed int v5; // ebx
  int v6; // eax
  const WCHAR *v7; // r8
  signed int appended; // edi
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned __int16 *v12; // [rsp+50h] [rbp+18h] BYREF

  v3 = 0;
  v12 = 0;
  v5 = 0;
  if ( !a1 || !*a1 || !a2 )
  {
    v5 = -2147024809;
LABEL_16:
    if ( v3 )
      operator delete(v3);
    return (unsigned int)v5;
  }
  if ( _wcsnicmp(a1, L"\\\\?\\", 4u) )
  {
    v5 = WcsDupHr(a1, &v12);
    if ( v5 >= 0 )
    {
LABEL_6:
      *a2 = v12;
      return (unsigned int)v5;
    }
LABEL_14:
    v3 = v12;
    goto LABEL_16;
  }
  v6 = _wcsnicmp(a1, L"\\\\?\\UNC", 7u);
  v7 = L"\\";
  if ( v6 )
    v7 = &psz;
  appended = AppendStrings(&v12, 2u, v7, (char *)a1 + (-(__int64)(v6 != 0) & 0xFFFFFFFFFFFFFFFAuLL) + 14);
  if ( !(unsigned int)ElValidateWin32_8(appended, v9, v10, 0xE22u) )
    goto LABEL_6;
  if ( appended > 0 )
    v5 = (unsigned __int16)appended | 0x80070000;
  else
    v5 = appended;
  if ( v5 < 0 )
    goto LABEL_14;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001b3a0  mov     [rsp+arg_8], rbx
0x18001b3a5  push    rbp
0x18001b3a6  push    rsi
0x18001b3a7  push    rdi
0x18001b3a8  sub     rsp, 20h
0x18001b3ac  xor     ebp, ebp
0x18001b3ae  mov     rdi, rcx
0x18001b3b1  mov     ecx, ebp; lpMem
0x18001b3b3  mov     rsi, rdx
0x18001b3b6  mov     [rsp+38h+arg_10], rcx
0x18001b3bb  mov     ebx, ebp
0x18001b3bd  test    rdi, rdi
0x18001b3c0  jz      loc_18001B497
0x18001b3c6  cmp     [rdi], bp
0x18001b3c9  jz      loc_18001B497
0x18001b3cf  test    rdx, rdx
0x18001b3d2  jz      loc_18001B497
0x18001b3d8  lea     r8d, [rbp+4]; MaxCount
0x18001b3dc  mov     rcx, rdi; String1
0x18001b3df  lea     rdx, asc_180034528; "\\\\?\\"
0x18001b3e6  call    cs:__imp__wcsnicmp
0x18001b3ed  nop     dword ptr [rax+rax+00h]
0x18001b3f2  mov     rcx, rdi; unsigned __int16 *
0x18001b3f5  test    eax, eax
0x18001b3f7  jz      short loc_18001B41A
0x18001b3f9  lea     rdx, [rsp+38h+arg_10]; unsigned __int16 **
0x18001b3fe  call    ?WcsDupHr@@YAJPEBGPEAPEAG@Z; WcsDupHr(ushort const *,ushort * *)
0x18001b403  mov     ebx, eax
0x18001b405  test    eax, eax
0x18001b407  js      loc_18001B490
0x18001b40d  mov     rax, [rsp+38h+arg_10]
0x18001b412  mov     [rsi], rax
0x18001b415  jmp     loc_18001B4A6
0x18001b41a  mov     r8d, 7; MaxCount
0x18001b420  lea     rdx, aUnc; "\\\\?\\UNC"
0x18001b427  call    cs:__imp__wcsnicmp
0x18001b42e  nop     dword ptr [rax+rax+00h]
0x18001b433  lea     r8, SubBlock; "\\"
0x18001b43a  mov     edx, 2; unsigned int
0x18001b43f  mov     ecx, eax
0x18001b441  neg     ecx
0x18001b443  lea     rcx, psz
0x18001b44a  sbb     r9, r9
0x18001b44d  and     r9, 0FFFFFFFFFFFFFFFAh
0x18001b451  add     r9, 0Eh
0x18001b455  add     r9, rdi
0x18001b458  test    eax, eax
0x18001b45a  cmovnz  r8, rcx
0x18001b45e  lea     rcx, [rsp+38h+arg_10]; unsigned __int16 **
0x18001b463  call    ?AppendStrings@@YAKPEAPEAGKZZ; AppendStrings(ushort * *,ulong,...)
0x18001b468  mov     r9d, 0E22h
0x18001b46e  mov     ecx, eax
0x18001b470  mov     edi, eax
0x18001b472  call    ElValidateWin32_8
0x18001b477  test    eax, eax
0x18001b479  jz      short loc_18001B40D
0x18001b47b  test    edi, edi
0x18001b47d  jg      short loc_18001B483
0x18001b47f  mov     ebx, edi
0x18001b481  jmp     short loc_18001B48C
0x18001b483  movzx   ebx, di
0x18001b486  or      ebx, 80070000h
0x18001b48c  test    ebx, ebx
0x18001b48e  jns     short loc_18001B4A6
0x18001b490  mov     rcx, [rsp+38h+arg_10]
0x18001b495  jmp     short loc_18001B49C
0x18001b497  mov     ebx, 80070057h
0x18001b49c  test    rcx, rcx
0x18001b49f  jz      short loc_18001B4A6
0x18001b4a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b4a6  mov     eax, ebx
0x18001b4a8  mov     rbx, [rsp+38h+arg_8]
0x18001b4ad  add     rsp, 20h
0x18001b4b1  pop     rdi
0x18001b4b2  pop     rsi
0x18001b4b3  pop     rbp
0x18001b4b4  retn
```
