# IsDesiredProcess(ushort const *)

- ea: `0x180002908`
- end: `0x1800029b6`
- name: `?IsDesiredProcess@@YA_NPEBG@Z`
- size: `174`
- prototype: `bool __fastcall(PCNZWCH lpString2)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800039ac`
- `0x180003ae0`

## callees

- `0x180002908`
- `0x180005680`
- `0x180012614`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180002939`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180002939`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000297d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000297d`

## pseudocode

```c
char __fastcall IsDesiredProcess(PCNZWCH lpString2)
{
  char v2; // bl
  unsigned __int16 v3; // dx
  unsigned __int16 *v4; // rax
  WCHAR *v5; // rax
  WCHAR Filename[264]; // [rsp+30h] [rbp-228h] BYREF

  v2 = 0;
  if ( GetModuleFileNameW(0, Filename, 0x105u) )
  {
    v4 = wcsrchr(Filename, v3);
    if ( v4 )
      v5 = v4 + 1;
    else
      v5 = Filename;
    return CompareStringW(0x7Fu, 1u, v5, -1, lpString2, -1) == 2;
  }
  return v2;
}

```

## disassembly

```asm
0x180002908  mov     [rsp+arg_8], rbx
0x18000290d  push    rdi
0x18000290e  sub     rsp, 250h
0x180002915  mov     rax, cs:__security_cookie
0x18000291c  xor     rax, rsp
0x18000291f  mov     [rsp+258h+var_18], rax
0x180002927  mov     rdi, rcx
0x18000292a  lea     rdx, [rsp+258h+Filename]; lpFilename
0x18000292f  xor     ecx, ecx; hModule
0x180002931  mov     r8d, 105h; nSize
0x180002937  xor     bl, bl
0x180002939  call    cs:__imp_GetModuleFileNameW
0x180002940  nop     dword ptr [rax+rax+00h]
0x180002945  test    eax, eax
0x180002947  jz      short loc_180002992
0x180002949  lea     rcx, [rsp+258h+Filename]; unsigned __int16 *
0x18000294e  call    ?wcsrchr@@YAPEAGPEAGG@Z; wcsrchr(ushort *,ushort)
0x180002953  test    rax, rax
0x180002956  jnz     short loc_18000295F
0x180002958  lea     rax, [rsp+258h+Filename]
0x18000295d  jmp     short loc_180002963
0x18000295f  add     rax, 2
0x180002963  or      r9d, 0FFFFFFFFh; cchCount1
0x180002967  mov     r8, rax; lpString1
0x18000296a  mov     [rsp+258h+cchCount2], r9d; cchCount2
0x18000296f  mov     [rsp+258h+lpString2], rdi; lpString2
0x180002974  lea     edi, [r9+2]
0x180002978  mov     edx, edi; dwCmpFlags
0x18000297a  lea     ecx, [rdi+7Eh]; Locale
0x18000297d  call    cs:__imp_CompareStringW
0x180002984  nop     dword ptr [rax+rax+00h]
0x180002989  cmp     eax, 2
0x18000298c  movzx   ebx, bl
0x18000298f  cmovz   ebx, edi
0x180002992  mov     al, bl
0x180002994  mov     rcx, [rsp+258h+var_18]
0x18000299c  xor     rcx, rsp; StackCookie
0x18000299f  call    __security_check_cookie
0x1800029a4  mov     rbx, [rsp+258h+arg_8]
0x1800029ac  add     rsp, 250h
0x1800029b3  pop     rdi
0x1800029b4  retn
```
