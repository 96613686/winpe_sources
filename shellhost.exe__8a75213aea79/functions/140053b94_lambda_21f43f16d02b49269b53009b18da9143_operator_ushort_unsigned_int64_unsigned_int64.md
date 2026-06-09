# _lambda_21f43f16d02b49269b53009b18da9143_::operator()(ushort *,unsigned __int64,unsigned __int64 *)

- ea: `0x140053b94`
- end: `0x140053c3b`
- name: `??R_lambda_21f43f16d02b49269b53009b18da9143_@@QEBAJPEAG_KPEA_K@Z`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140054550`

## callees

- `0x14000d39c`
- `0x140053b94`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140053be4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140053be4`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x140053bc2`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x140053bc2`

## string_xrefs

- `0x140053c0a`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall _lambda_21f43f16d02b49269b53009b18da9143_::operator()(
        __int64 a1,
        WCHAR *a2,
        unsigned __int64 a3,
        __int64 *a4)
{
  void *v6; // r10
  HMODULE *v7; // rax
  DWORD ModuleFileName; // eax
  const char *v9; // r9
  __int64 v10; // r8
  bool v11; // cl
  char v12; // dl
  DWORD ModuleFileNameW; // eax
  __int64 result; // rax
  __int64 v15; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v6 = **(void ***)a1;
  v7 = *(HMODULE **)(a1 + 8);
  if ( v6 )
  {
    ModuleFileName = K32GetModuleFileNameExW(v6, *v7, a2, a3);
    v10 = ModuleFileName;
    if ( !ModuleFileName )
    {
      v11 = 1;
LABEL_4:
      v12 = 0;
      goto LABEL_11;
    }
    v11 = 0;
    if ( ModuleFileName >= a3 - 1 )
      goto LABEL_4;
    goto LABEL_6;
  }
  ModuleFileNameW = GetModuleFileNameW(*v7, a2, a3);
  v10 = ModuleFileNameW;
  if ( ModuleFileNameW && ModuleFileNameW < a3 )
  {
    v11 = 0;
LABEL_6:
    v12 = 1;
    goto LABEL_11;
  }
  v12 = 0;
  v11 = ModuleFileNameW == 0;
LABEL_11:
  if ( v11 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x215,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
             v9);
  v15 = v10 + 1;
  if ( !v12 )
    v15 = 2 * a3;
  result = 0;
  *a4 = v15;
  return result;
}

```

## disassembly

```asm
0x140053b94  mov     [rsp+arg_0], rbx
0x140053b99  push    rdi
0x140053b9a  sub     rsp, 20h
0x140053b9e  mov     rax, [rcx]
0x140053ba1  mov     rdi, r9
0x140053ba4  mov     rbx, r8
0x140053ba7  mov     r10, [rax]
0x140053baa  mov     rax, [rcx+8]
0x140053bae  mov     rcx, [rax]; hModule
0x140053bb1  test    r10, r10
0x140053bb4  jz      short loc_140053BE4
0x140053bb6  mov     r8, rdx; lpFilename
0x140053bb9  mov     r9d, ebx; nSize
0x140053bbc  mov     rdx, rcx; hModule
0x140053bbf  mov     rcx, r10; hProcess
0x140053bc2  call    cs:__imp_K32GetModuleFileNameExW
0x140053bc8  mov     r8d, eax; nSize
0x140053bcb  test    eax, eax
0x140053bcd  jnz     short loc_140053BD5
0x140053bcf  mov     cl, 1
0x140053bd1  xor     dl, dl
0x140053bd3  jmp     short loc_140053C01
0x140053bd5  xor     cl, cl
0x140053bd7  lea     rax, [rbx-1]
0x140053bdb  cmp     r8, rax
0x140053bde  jnb     short loc_140053BD1
0x140053be0  mov     dl, 1; lpFilename
0x140053be2  jmp     short loc_140053C01
0x140053be4  call    cs:__imp_GetModuleFileNameW
0x140053bea  mov     r8d, eax
0x140053bed  test    eax, eax
0x140053bef  jz      short loc_140053BFA
0x140053bf1  cmp     r8, rbx
0x140053bf4  jnb     short loc_140053BFA
0x140053bf6  xor     cl, cl
0x140053bf8  jmp     short loc_140053BE0
0x140053bfa  xor     dl, dl
0x140053bfc  test    eax, eax
0x140053bfe  setz    cl
0x140053c01  test    cl, cl
0x140053c03  jz      short loc_140053C1D
0x140053c05  mov     rcx, [rsp+28h]; this
0x140053c0a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140053c11  mov     edx, 215h; void *
0x140053c16  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140053c1b  jmp     short loc_140053C30
0x140053c1d  test    dl, dl
0x140053c1f  lea     rax, [rbx+rbx]
0x140053c23  lea     rcx, [r8+1]
0x140053c27  cmovz   rcx, rax
0x140053c2b  xor     eax, eax
0x140053c2d  mov     [rdi], rcx
0x140053c30  mov     rbx, [rsp+28h+arg_0]
0x140053c35  add     rsp, 20h
0x140053c39  pop     rdi
0x140053c3a  retn
```
