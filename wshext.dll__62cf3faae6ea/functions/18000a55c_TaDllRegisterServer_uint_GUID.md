# TaDllRegisterServer(uint,_GUID *)

- ea: `0x18000a55c`
- end: `0x18000a703`
- name: `?TaDllRegisterServer@@YAJIPEAU_GUID@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(unsigned int, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006df0`

## callees

- `0x18000a55c`
- `0x18000d1c0`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a62a`
- `KERNEL32!GetLastError` at `0x18000a62a`
- `KERNEL32!GetModuleFileNameA` at `0x18000a65b`
- `KERNEL32!GetModuleFileNameA` at `0x18000a65b`
- `KERNEL32!MultiByteToWideChar` at `0x18000a690`
- `KERNEL32!MultiByteToWideChar` at `0x18000a690`
- `KERNEL32!GetModuleFileNameW` at `0x18000a620`
- `KERNEL32!GetModuleFileNameW` at `0x18000a620`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18000a6a3`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18000a6a3`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x18000a6b9`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x18000a6b9`

## pseudocode

```c
signed int __fastcall TaDllRegisterServer(__int64 a1, struct _GUID *a2)
{
  int v2; // r14d
  struct TaClassTable near **v3; // rbx
  int v4; // esi
  char v5; // di
  struct TaClassTable near *v6; // rax
  signed int result; // eax
  ITypeLib *pptlib; // [rsp+30h] [rbp-D0h] BYREF
  CHAR MultiByteStr[260]; // [rsp+40h] [rbp-C0h] BYREF
  char v10; // [rsp+144h] [rbp+44h]
  WCHAR Filename[260]; // [rsp+150h] [rbp+50h] BYREF
  __int16 v12; // [rsp+358h] [rbp+258h]

  v2 = 0;
  v3 = &g_TaClassTable;
  v4 = 0;
  v5 = 0;
  if ( !(_DWORD)g_TaClassTable )
    return -2147220991;
  do
  {
    v6 = v3[1];
    if ( v6 )
    {
      LOBYTE(a2) = 1;
      if ( ((int (__fastcall *)(struct TaClassTable near *, struct _GUID *))v6)(v3[2], a2) >= 0 )
      {
        ++v2;
        if ( *(_DWORD *)v3 != 1 )
          v5 = 1;
      }
      else
      {
        ++v4;
      }
    }
    v3 += 3;
  }
  while ( *(_DWORD *)v3 );
  if ( !v2 || v4 >= 1 )
    return -2147220991;
  if ( !v5 )
    return 0;
  pptlib = 0;
  if ( Global::g_fWindowsNT )
  {
    v12 = 0;
    if ( !GetModuleFileNameW(Global::g_hInstance, Filename, 0x105u) )
      goto LABEL_13;
    if ( !v12 )
      goto LABEL_21;
    return -2147024774;
  }
  v10 = 0;
  if ( GetModuleFileNameA(Global::g_hInstance, MultiByteStr, 0x105u) )
  {
    if ( v10 )
      return -2147024774;
    if ( MultiByteToWideChar(0, 0, MultiByteStr, -1, Filename, 261) )
    {
LABEL_21:
      result = LoadTypeLib(Filename, &pptlib);
      if ( result < 0 )
        return result;
      if ( RegisterTypeLib(pptlib, Filename, 0) < 0 )
        return -2147220992;
      ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
      return 0;
    }
  }
LABEL_13:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000a55c  push    rbp
0x18000a55e  push    rbx
0x18000a55f  push    rsi
0x18000a560  push    rdi
0x18000a561  push    r12
0x18000a563  push    r14
0x18000a565  lea     rbp, [rsp-278h]
0x18000a56d  sub     rsp, 378h
0x18000a574  mov     rax, cs:__security_cookie
0x18000a57b  xor     rax, rsp
0x18000a57e  mov     [rbp+2A0h+var_40], rax
0x18000a585  xor     r14d, r14d
0x18000a588  lea     rbx, ?g_TaClassTable@@3PAUTaClassTable@@A; TaClassTable near * g_TaClassTable
0x18000a58f  xor     esi, esi
0x18000a591  xor     dil, dil
0x18000a594  cmp     cs:?g_TaClassTable@@3PAUTaClassTable@@A, esi; TaClassTable near * g_TaClassTable
0x18000a59a  jz      loc_18000A6DF
0x18000a5a0  lea     r12d, [r14+1]
0x18000a5a4  mov     rax, [rbx+8]
0x18000a5a8  test    rax, rax
0x18000a5ab  jz      short loc_18000A5D0
0x18000a5ad  mov     rcx, [rbx+10h]
0x18000a5b1  mov     dl, r12b
0x18000a5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5b9  test    eax, eax
0x18000a5bb  jns     short loc_18000A5C2
0x18000a5bd  add     esi, r12d
0x18000a5c0  jmp     short loc_18000A5D0
0x18000a5c2  add     r14d, r12d
0x18000a5c5  movzx   edi, dil
0x18000a5c9  cmp     [rbx], r12d
0x18000a5cc  cmovnz  edi, r12d
0x18000a5d0  add     rbx, 18h
0x18000a5d4  cmp     dword ptr [rbx], 0
0x18000a5d7  jnz     short loc_18000A5A4
0x18000a5d9  test    r14d, r14d
0x18000a5dc  jz      loc_18000A6DF
0x18000a5e2  cmp     esi, r12d
0x18000a5e5  jge     loc_18000A6DF
0x18000a5eb  test    dil, dil
0x18000a5ee  jz      loc_18000A6DB
0x18000a5f4  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x18000a5fb  mov     r8d, 105h; nSize
0x18000a601  mov     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; hModule
0x18000a608  mov     [rsp+3A0h+pptlib], 0
0x18000a611  jz      short loc_18000A652
0x18000a613  xor     eax, eax
0x18000a615  lea     rdx, [rbp+2A0h+Filename]; lpFilename
0x18000a619  mov     [rbp+2A0h+var_48], ax
0x18000a620  call    cs:__imp_GetModuleFileNameW
0x18000a626  test    eax, eax
0x18000a628  jnz     short loc_18000A645
0x18000a62a  call    cs:__imp_GetLastError
0x18000a630  test    eax, eax
0x18000a632  jle     loc_18000A6E4
0x18000a638  movzx   eax, ax
0x18000a63b  or      eax, 80070000h
0x18000a640  jmp     loc_18000A6E4
0x18000a645  xor     eax, eax
0x18000a647  cmp     ax, [rbp+2A0h+var_48]
0x18000a64e  jnz     short loc_18000A66B
0x18000a650  jmp     short loc_18000A69A
0x18000a652  lea     rdx, [rsp+3A0h+MultiByteStr]; lpFilename
0x18000a657  mov     [rbp+2A0h+var_25C], 0
0x18000a65b  call    cs:__imp_GetModuleFileNameA
0x18000a661  test    eax, eax
0x18000a663  jz      short loc_18000A62A
0x18000a665  cmp     [rbp+2A0h+var_25C], 0
0x18000a669  jz      short loc_18000A672
0x18000a66b  mov     eax, 8007007Ah
0x18000a670  jmp     short loc_18000A6E4
0x18000a672  lea     rax, [rbp+2A0h+Filename]
0x18000a676  mov     [rsp+3A0h+cchWideChar], 105h; cchWideChar
0x18000a67e  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000a682  mov     [rsp+3A0h+lpWideCharStr], rax; lpWideCharStr
0x18000a687  lea     r8, [rsp+3A0h+MultiByteStr]; lpMultiByteStr
0x18000a68c  xor     edx, edx; dwFlags
0x18000a68e  xor     ecx, ecx; CodePage
0x18000a690  call    cs:__imp_MultiByteToWideChar
0x18000a696  test    eax, eax
0x18000a698  jz      short loc_18000A62A
0x18000a69a  lea     rdx, [rsp+3A0h+pptlib]; pptlib
0x18000a69f  lea     rcx, [rbp+2A0h+Filename]; szFile
0x18000a6a3  call    cs:__imp_LoadTypeLib
0x18000a6a9  test    eax, eax
0x18000a6ab  js      short loc_18000A6E4
0x18000a6ad  mov     rcx, [rsp+3A0h+pptlib]; ptlib
0x18000a6b2  lea     rdx, [rbp+2A0h+Filename]; szFullPath
0x18000a6b6  xor     r8d, r8d; szHelpDir
0x18000a6b9  call    cs:__imp_RegisterTypeLib
0x18000a6bf  test    eax, eax
0x18000a6c1  jns     short loc_18000A6CA
0x18000a6c3  mov     eax, 80040200h
0x18000a6c8  jmp     short loc_18000A6E4
0x18000a6ca  mov     rcx, [rsp+3A0h+pptlib]
0x18000a6cf  mov     rax, [rcx]
0x18000a6d2  mov     rax, [rax+10h]
0x18000a6d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6db  xor     eax, eax
0x18000a6dd  jmp     short loc_18000A6E4
0x18000a6df  mov     eax, 80040201h
0x18000a6e4  mov     rcx, [rbp+2A0h+var_40]
0x18000a6eb  xor     rcx, rsp; StackCookie
0x18000a6ee  call    __security_check_cookie
0x18000a6f3  add     rsp, 378h
0x18000a6fa  pop     r14
0x18000a6fc  pop     r12
0x18000a6fe  pop     rdi
0x18000a6ff  pop     rsi
0x18000a700  pop     rbx
0x18000a701  pop     rbp
0x18000a702  retn
```
