# wistd::__function::__func<_lambda_44354332321693c583119f2a7d89b96e_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x14000b110`
- end: `0x14000b1c6`
- name: `??R?$__func@V_lambda_44354332321693c583119f2a7d89b96e_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEA_W$$QEA_K$$QEAPEA_K@Z`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003e74`
- `0x14000b110`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14000b167`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14000b167`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x14000b149`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x14000b149`

## string_xrefs

- `0x14000b192`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_44354332321693c583119f2a7d89b96e_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(
        __int64 a1,
        WCHAR **a2,
        unsigned __int64 *a3,
        __int64 **a4)
{
  unsigned int v4; // ebx
  __int64 *v5; // rsi
  unsigned __int64 v6; // rdi
  WCHAR *v7; // rdx
  void *v8; // r10
  HMODULE *v9; // rax
  DWORD ModuleFileName; // eax
  const char *v11; // r9
  __int64 v12; // rdx
  bool v13; // r8
  bool v14; // cf
  DWORD ModuleFileNameW; // eax
  int v16; // ecx
  __int64 v17; // rdx
  __int64 v18; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = 0;
  v5 = *a4;
  v6 = *a3;
  v7 = *a2;
  v8 = **(void ***)(a1 + 8);
  v9 = *(HMODULE **)(a1 + 16);
  if ( v8 )
  {
    ModuleFileName = K32GetModuleFileNameExW(v8, *v9, v7, v6);
    v12 = ModuleFileName;
    v13 = ModuleFileName == 0;
    if ( ModuleFileName )
    {
      v14 = ModuleFileName < v6 - 1;
      goto LABEL_6;
    }
  }
  else
  {
    ModuleFileNameW = GetModuleFileNameW(*v9, v7, v6);
    v12 = ModuleFileNameW;
    v13 = ModuleFileNameW == 0;
    if ( ModuleFileNameW )
    {
      v14 = ModuleFileNameW < v6;
LABEL_6:
      v16 = 1;
      if ( v14 )
        goto LABEL_8;
    }
  }
  v16 = 0;
LABEL_8:
  v17 = v12 + 1;
  if ( v13 )
  {
    return (unsigned int)wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0x205,
                           (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opens"
                                         "ource\\wil\\win32_helpers.h",
                           v11);
  }
  else
  {
    v18 = 2 * v6;
    if ( v16 )
      v18 = v17;
    *v5 = v18;
  }
  return v4;
}

```

## disassembly

```asm
0x14000b110  mov     [rsp+arg_0], rbx
0x14000b115  mov     [rsp+arg_8], rsi
0x14000b11a  push    rdi
0x14000b11b  sub     rsp, 20h
0x14000b11f  mov     rax, [rcx+8]
0x14000b123  xor     ebx, ebx
0x14000b125  mov     rsi, [r9]
0x14000b128  mov     rdi, [r8]
0x14000b12b  mov     rdx, [rdx]; lpFilename
0x14000b12e  mov     r10, [rax]
0x14000b131  mov     rax, [rcx+10h]
0x14000b135  mov     rcx, [rax]; hModule
0x14000b138  test    r10, r10
0x14000b13b  jz      short loc_14000B164
0x14000b13d  mov     r8, rdx; lpFilename
0x14000b140  mov     r9d, edi; nSize
0x14000b143  mov     rdx, rcx; hModule
0x14000b146  mov     rcx, r10; hProcess
0x14000b149  call    cs:__imp_K32GetModuleFileNameExW
0x14000b14f  test    eax, eax
0x14000b151  mov     edx, eax
0x14000b153  setz    r8b
0x14000b157  test    eax, eax
0x14000b159  jz      short loc_14000B183
0x14000b15b  lea     rax, [rdi-1]
0x14000b15f  cmp     rdx, rax
0x14000b162  jmp     short loc_14000B17C
0x14000b164  mov     r8d, edi; nSize
0x14000b167  call    cs:__imp_GetModuleFileNameW
0x14000b16d  test    eax, eax
0x14000b16f  mov     edx, eax
0x14000b171  setz    r8b
0x14000b175  test    eax, eax
0x14000b177  jz      short loc_14000B183
0x14000b179  cmp     rdx, rdi
0x14000b17c  mov     ecx, 1
0x14000b181  jb      short loc_14000B185
0x14000b183  mov     ecx, ebx
0x14000b185  inc     rdx
0x14000b188  test    r8b, r8b
0x14000b18b  jz      short loc_14000B1A7
0x14000b18d  mov     rcx, [rsp+28h]; this
0x14000b192  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14000b199  mov     edx, 205h; void *
0x14000b19e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000b1a3  mov     ebx, eax
0x14000b1a5  jmp     short loc_14000B1B4
0x14000b1a7  test    ecx, ecx
0x14000b1a9  lea     rax, [rdi+rdi]
0x14000b1ad  cmovnz  rax, rdx
0x14000b1b1  mov     [rsi], rax
0x14000b1b4  mov     rsi, [rsp+28h+arg_8]
0x14000b1b9  mov     eax, ebx
0x14000b1bb  mov     rbx, [rsp+28h+arg_0]
0x14000b1c0  add     rsp, 20h
0x14000b1c4  pop     rdi
0x14000b1c5  retn
```
