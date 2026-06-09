# CUserContext::IsDomainUser(void *)

- ea: `0x1800bbc20`
- end: `0x1800bbce3`
- name: `?IsDomainUser@CUserContext@@QEBAHPEAX@Z`
- size: `195`
- prototype: `int(CUserContext *__hidden this, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800bbb84`
- `0x1800bde78`

## callees

- `0x180064820`
- `0x1800bbc20`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bbc7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bbc7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800bbc5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800bbc5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbc69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbcd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbc69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbcd0`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x1800bbcba`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x1800bbcba`

## string_xrefs

- `0x1800bbc53`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall CUserContext::IsDomainUser(CUserContext *this, void *a2)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  CUserContext *v6; // rcx
  BOOL v7; // ebx
  int v8; // [rsp+40h] [rbp+10h] BYREF
  int v9; // [rsp+44h] [rbp+14h]
  BOOL pfEqual; // [rsp+50h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp+28h] BYREF

  v9 = HIDWORD(this);
  hMem = 0;
  pfEqual = 0;
  v8 = 0;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlGetNtProductType");
    v7 = ProcAddress
      && (((unsigned __int8 (__fastcall *)(int *))ProcAddress)(&v8) && v8 == 2
       || (int)CUserContext::GetDomainSid(v6, &hMem) >= 0 && EqualDomainSid(a2, hMem, &pfEqual) && !pfEqual);
    LocalFree(hMem);
    return v7;
  }
  else
  {
    LocalFree(hMem);
    return 0;
  }
}

```

## disassembly

```asm
0x1800bbc20  mov     [rsp-8+arg_8], rbx
0x1800bbc25  mov     [rsp-8+arg_0], rcx
0x1800bbc2a  push    rbp
0x1800bbc2b  mov     rbp, rsp
0x1800bbc2e  sub     rsp, 30h
0x1800bbc32  mov     rbx, rdx
0x1800bbc35  mov     [rbp+hMem], 0
0x1800bbc3d  lea     rax, [rbp+hMem]
0x1800bbc41  mov     [rbp+var_10], rax
0x1800bbc45  mov     [rbp+pfEqual], 0
0x1800bbc4c  mov     dword ptr [rbp+arg_0], 0
0x1800bbc53  lea     rcx, ModuleName; "ntdll.dll"
0x1800bbc5a  call    cs:__imp_GetModuleHandleW
0x1800bbc60  test    rax, rax
0x1800bbc63  jnz     short loc_1800BBC73
0x1800bbc65  mov     rcx, [rbp+hMem]; hMem
0x1800bbc69  call    cs:__imp_LocalFree
0x1800bbc6f  xor     eax, eax
0x1800bbc71  jmp     short loc_1800BBCD8
0x1800bbc73  lea     rdx, aRtlgetntproduc; "RtlGetNtProductType"
0x1800bbc7a  mov     rcx, rax; hModule
0x1800bbc7d  call    cs:__imp_GetProcAddress
0x1800bbc83  test    rax, rax
0x1800bbc86  jz      short loc_1800BBCCA
0x1800bbc88  lea     rcx, [rbp+arg_0]
0x1800bbc8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbc91  test    al, al
0x1800bbc93  jz      short loc_1800BBCA2
0x1800bbc95  cmp     dword ptr [rbp+arg_0], 2
0x1800bbc99  jnz     short loc_1800BBCA2
0x1800bbc9b  mov     ebx, 1
0x1800bbca0  jmp     short loc_1800BBCCC
0x1800bbca2  lea     rdx, [rbp+hMem]; void **
0x1800bbca6  call    ?GetDomainSid@CUserContext@@QEBAJPEAPEAX@Z; CUserContext::GetDomainSid(void * *)
0x1800bbcab  test    eax, eax
0x1800bbcad  js      short loc_1800BBCCA
0x1800bbcaf  lea     r8, [rbp+pfEqual]; pfEqual
0x1800bbcb3  mov     rdx, [rbp+hMem]; pSid2
0x1800bbcb7  mov     rcx, rbx; pSid1
0x1800bbcba  call    cs:__imp_EqualDomainSid
0x1800bbcc0  test    eax, eax
0x1800bbcc2  jz      short loc_1800BBCCA
0x1800bbcc4  cmp     [rbp+pfEqual], 0
0x1800bbcc8  jz      short loc_1800BBC9B
0x1800bbcca  xor     ebx, ebx
0x1800bbccc  mov     rcx, [rbp+hMem]; hMem
0x1800bbcd0  call    cs:__imp_LocalFree
0x1800bbcd6  mov     eax, ebx
0x1800bbcd8  mov     rbx, [rsp+30h+arg_8]
0x1800bbcdd  add     rsp, 30h
0x1800bbce1  pop     rbp
0x1800bbce2  retn
```
