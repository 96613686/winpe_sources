# CUwfStaticVolumeConfiguration::FindFileExclusion(ushort const *)

- ea: `0x180007700`
- end: `0x180007846`
- name: `?FindFileExclusion@CUwfStaticVolumeConfiguration@@QEAAJPEBG@Z`
- size: `326`
- prototype: `__int64 __fastcall(CUwfStaticVolumeConfiguration *this, wchar_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180008420`
- `0x1800182e0`

## callees

- `0x180001384`
- `0x180007700`
- `0x180011a30`
- `0x180011b90`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000780b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000782b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000780b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000782b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000775d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800077de`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000775d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800077de`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::FindFileExclusion(CUwfStaticVolumeConfiguration *this, wchar_t *a2)
{
  void *v2; // rsi
  signed int v5; // ebx
  HKEY v6; // rcx
  LSTATUS ValueW; // eax
  void *pvData; // rdi
  bool v9; // cc
  DWORD pcbData; // [rsp+68h] [rbp+10h] BYREF
  DWORD pdwType; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  if ( !a2 )
  {
    v5 = -2147467261;
    goto LABEL_14;
  }
  v6 = (HKEY)*((_QWORD *)this + 2);
  pdwType = 0;
  pcbData = 0;
  ValueW = RegGetValueW(v6, 0, L"FileExceptionsUserDefined", 0x20u, &pdwType, 0, &pcbData);
  v5 = ValueW;
  if ( ValueW )
  {
    pvData = 0;
    v9 = ValueW <= 0;
LABEL_5:
    if ( !v9 )
      v5 = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_12;
  }
  pvData = operator new[](saturated_mul((unsigned __int64)pcbData >> 1, 2u));
  if ( pvData )
  {
    ValueW = RegGetValueW(*((HKEY *)this + 2), 0, L"FileExceptionsUserDefined", 0x20u, &pdwType, pvData, &pcbData);
    v5 = ValueW;
    v9 = ValueW <= 0;
    if ( !ValueW )
    {
      v2 = (void *)MultiSzAlloc(pvData);
      v5 = -2147024882;
      if ( v2 )
        v5 = 0;
      goto LABEL_12;
    }
    goto LABEL_5;
  }
  v5 = -2147024882;
LABEL_12:
  operator delete[](pvData);
  if ( v5 >= 0 )
    v5 = MultiSzFind(a2);
LABEL_14:
  operator delete[](v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007700  mov     [rsp+arg_0], rbx
0x180007705  mov     [rsp+arg_18], rbp
0x18000770a  push    rsi
0x18000770b  push    rdi
0x18000770c  push    r14
0x18000770e  sub     rsp, 40h
0x180007712  xor     esi, esi
0x180007714  mov     rbp, rdx
0x180007717  mov     r14, rcx
0x18000771a  test    rdx, rdx
0x18000771d  jnz     short loc_180007729
0x18000771f  mov     ebx, 80004003h
0x180007724  jmp     loc_180007828
0x180007729  mov     rcx, [rcx+10h]; hkey
0x18000772d  lea     rax, [rsp+58h+arg_8]
0x180007732  mov     [rsp+58h+pcbData], rax; pcbData
0x180007737  lea     r8, Value; "FileExceptionsUserDefined"
0x18000773e  lea     rax, [rsp+58h+arg_10]
0x180007743  mov     [rsp+58h+pvData], rsi; pvData
0x180007748  mov     r9d, 20h ; ' '; dwFlags
0x18000774e  mov     [rsp+58h+pdwType], rax; pdwType
0x180007753  xor     edx, edx; lpSubKey
0x180007755  mov     [rsp+58h+arg_10], esi
0x180007759  mov     [rsp+58h+arg_8], esi
0x18000775d  call    cs:__imp_RegGetValueW
0x180007763  mov     ebx, eax
0x180007765  test    eax, eax
0x180007767  jz      short loc_180007781
0x180007769  xor     edi, edi
0x18000776b  test    eax, eax
0x18000776d  jle     loc_180007808
0x180007773  movzx   ebx, ax
0x180007776  or      ebx, 80070000h
0x18000777c  jmp     loc_180007808
0x180007781  mov     ecx, [rsp+58h+arg_8]
0x180007785  mov     eax, 2
0x18000778a  shr     rcx, 1
0x18000778d  mul     rcx
0x180007790  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007797  cmovb   rax, rcx
0x18000779b  mov     rcx, rax; unsigned __int64
0x18000779e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800077a3  mov     rdi, rax
0x1800077a6  test    rax, rax
0x1800077a9  jnz     short loc_1800077B2
0x1800077ab  mov     ebx, 8007000Eh
0x1800077b0  jmp     short loc_180007808
0x1800077b2  mov     rcx, [r14+10h]; hkey
0x1800077b6  lea     rax, [rsp+58h+arg_8]
0x1800077bb  mov     [rsp+58h+pcbData], rax; pcbData
0x1800077c0  lea     r8, Value; "FileExceptionsUserDefined"
0x1800077c7  lea     rax, [rsp+58h+arg_10]
0x1800077cc  mov     [rsp+58h+pvData], rdi; pvData
0x1800077d1  mov     r9d, 20h ; ' '; dwFlags
0x1800077d7  mov     [rsp+58h+pdwType], rax; pdwType
0x1800077dc  xor     edx, edx; lpSubKey
0x1800077de  call    cs:__imp_RegGetValueW
0x1800077e4  mov     ebx, eax
0x1800077e6  test    eax, eax
0x1800077e8  jnz     short loc_18000776D
0x1800077ea  mov     edx, [rsp+58h+arg_8]
0x1800077ee  mov     rcx, rdi; Src
0x1800077f1  shr     edx, 1
0x1800077f3  call    MultiSzAlloc
0x1800077f8  mov     rsi, rax
0x1800077fb  mov     ebx, 8007000Eh
0x180007800  xor     eax, eax
0x180007802  test    rsi, rsi
0x180007805  cmovnz  ebx, eax
0x180007808  mov     rcx, rdi
0x18000780b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007811  test    ebx, ebx
0x180007813  js      short loc_180007828
0x180007815  xor     r9d, r9d
0x180007818  xor     r8d, r8d
0x18000781b  mov     rdx, rsi
0x18000781e  mov     rcx, rbp; String2
0x180007821  call    MultiSzFind
0x180007826  mov     ebx, eax
0x180007828  mov     rcx, rsi
0x18000782b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007831  mov     rbp, [rsp+58h+arg_18]
0x180007836  mov     eax, ebx
0x180007838  mov     rbx, [rsp+58h+arg_0]
0x18000783d  add     rsp, 40h
0x180007841  pop     r14
0x180007843  pop     rdi
0x180007844  pop     rsi
0x180007845  retn
```
