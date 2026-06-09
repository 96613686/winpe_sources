# _anonymous_namespace_::IsDeviceDomainJoined

- ea: `0x180035838`
- end: `0x1800359db`
- name: `_anonymous_namespace_::IsDeviceDomainJoined`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180035dd0`

## callees

- `0x180007660`
- `0x180035838`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180035867`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180035867`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035887`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003589a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003592d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035940`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035887`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003589a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003592d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035940`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035903`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800359b5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035903`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800359b5`

## string_xrefs

- `0x180035860`: `netapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char anonymous_namespace_::IsDeviceDomainJoined()
{
  HMODULE Library; // rax
  HMODULE v1; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v3; // rax
  FARPROC v5; // rdi
  FARPROC v6; // rax
  _DWORD *v7; // [rsp+40h] [rbp-30h] BYREF
  void (*v8)(void); // [rsp+48h] [rbp-28h]
  void (__fastcall *v9)(_QWORD); // [rsp+50h] [rbp-20h]
  int v10; // [rsp+58h] [rbp-18h] BYREF

  Library = LoadLibraryExW(L"netapi32.dll", 0, 0x800u);
  v1 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "NetGetJoinInformation");
    v3 = GetProcAddress(v1, "NetApiBufferFree");
    v8 = (void (*)(void))v3;
    if ( ProcAddress && v3 )
    {
      v7 = 0;
      v10 = 0;
      if ( !((unsigned int (__fastcall *)(_QWORD, _DWORD **, int *))ProcAddress)(0, &v7, &v10) && v10 == 3 )
      {
        if ( v7 )
          v8();
        goto LABEL_8;
      }
      if ( v7 )
        v8();
    }
    v5 = GetProcAddress(v1, "NetGetAadJoinInformation");
    v6 = GetProcAddress(v1, "NetFreeAadJoinInformation");
    v9 = (void (__fastcall *)(_QWORD))v6;
    if ( v5 && v6 )
    {
      v7 = 0;
      if ( ((int (__fastcall *)(_QWORD, _DWORD **))v5)(0, &v7) >= 0 && v7 && (unsigned int)(*v7 - 1) <= 1 )
      {
        v9(v7);
LABEL_8:
        FreeLibrary(v1);
        return 1;
      }
      v9(v7);
    }
  }
  if ( v1 )
    FreeLibrary(v1);
  return 0;
}

```

## disassembly

```asm
0x180035838  mov     [rsp-8+arg_0], rbx
0x18003583d  mov     [rsp-8+arg_8], rdi
0x180035842  push    rbp
0x180035843  mov     rbp, rsp
0x180035846  sub     rsp, 70h
0x18003584a  mov     rax, cs:__security_cookie
0x180035851  xor     rax, rsp
0x180035854  mov     [rbp+var_10], rax
0x180035858  xor     edx, edx; hFile
0x18003585a  mov     r8d, 800h; dwFlags
0x180035860  lea     rcx, aNetapi32Dll; "netapi32.dll"
0x180035867  call    cs:__imp_LoadLibraryExW
0x18003586d  mov     rbx, rax
0x180035870  mov     [rbp+var_38], rax
0x180035874  test    rax, rax
0x180035877  jz      loc_1800359AD
0x18003587d  lea     rdx, aNetgetjoininfo; "NetGetJoinInformation"
0x180035884  mov     rcx, rax; hModule
0x180035887  call    cs:__imp_GetProcAddress
0x18003588d  mov     rdi, rax
0x180035890  lea     rdx, aNetapibufferfr; "NetApiBufferFree"
0x180035897  mov     rcx, rbx; hModule
0x18003589a  call    cs:__imp_GetProcAddress
0x1800358a0  mov     [rbp+var_28], rax
0x1800358a4  test    rdi, rdi
0x1800358a7  jz      short loc_180035923
0x1800358a9  test    rax, rax
0x1800358ac  jz      short loc_180035923
0x1800358ae  mov     [rbp+var_30], 0
0x1800358b6  mov     [rbp+var_18], 0
0x1800358bd  lea     rax, [rbp+var_30]
0x1800358c1  mov     [rbp+var_50], rax
0x1800358c5  lea     rax, [rbp+var_28]
0x1800358c9  mov     [rbp+var_48], rax
0x1800358cd  mov     [rbp+var_40], 1
0x1800358d1  lea     r8, [rbp+var_18]
0x1800358d5  lea     rdx, [rbp+var_30]
0x1800358d9  xor     ecx, ecx
0x1800358db  mov     rax, rdi
0x1800358de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358e3  test    eax, eax
0x1800358e5  jnz     short loc_180035910
0x1800358e7  cmp     [rbp+var_18], 3
0x1800358eb  jnz     short loc_180035910
0x1800358ed  mov     rcx, [rbp+var_30]
0x1800358f1  test    rcx, rcx
0x1800358f4  jz      short loc_180035900
0x1800358f6  mov     rax, [rbp+var_28]
0x1800358fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358ff  nop
0x180035900  mov     rcx, rbx; hLibModule
0x180035903  call    cs:__imp_FreeLibrary
0x180035909  mov     al, 1
0x18003590b  jmp     loc_1800359BD
0x180035910  mov     rcx, [rbp+var_30]
0x180035914  test    rcx, rcx
0x180035917  jz      short loc_180035923
0x180035919  mov     rax, [rbp+var_28]
0x18003591d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035922  nop
0x180035923  lea     rdx, aNetgetaadjoini; "NetGetAadJoinInformation"
0x18003592a  mov     rcx, rbx; hModule
0x18003592d  call    cs:__imp_GetProcAddress
0x180035933  mov     rdi, rax
0x180035936  lea     rdx, aNetfreeaadjoin; "NetFreeAadJoinInformation"
0x18003593d  mov     rcx, rbx; hModule
0x180035940  call    cs:__imp_GetProcAddress
0x180035946  mov     [rbp+var_20], rax
0x18003594a  test    rdi, rdi
0x18003594d  jz      short loc_1800359AD
0x18003594f  test    rax, rax
0x180035952  jz      short loc_1800359AD
0x180035954  mov     [rbp+var_30], 0
0x18003595c  lea     rax, [rbp+var_20]
0x180035960  mov     [rbp+var_50], rax
0x180035964  lea     rax, [rbp+var_30]
0x180035968  mov     [rbp+var_48], rax
0x18003596c  mov     [rbp+var_40], 1
0x180035970  lea     rdx, [rbp+var_30]
0x180035974  xor     ecx, ecx
0x180035976  mov     rax, rdi
0x180035979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003597e  mov     rcx, [rbp+var_30]
0x180035982  test    eax, eax
0x180035984  js      short loc_1800359A3
0x180035986  test    rcx, rcx
0x180035989  jz      short loc_1800359A3
0x18003598b  mov     eax, [rcx]
0x18003598d  dec     eax
0x18003598f  cmp     eax, 1
0x180035992  ja      short loc_1800359A3
0x180035994  mov     rax, [rbp+var_20]
0x180035998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003599d  nop
0x18003599e  jmp     loc_180035900
0x1800359a3  mov     rax, [rbp+var_20]
0x1800359a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359ac  nop
0x1800359ad  test    rbx, rbx
0x1800359b0  jz      short loc_1800359BB
0x1800359b2  mov     rcx, rbx; hLibModule
0x1800359b5  call    cs:__imp_FreeLibrary
0x1800359bb  xor     al, al
0x1800359bd  mov     rcx, [rbp+var_10]
0x1800359c1  xor     rcx, rsp; StackCookie
0x1800359c4  call    __security_check_cookie
0x1800359c9  lea     r11, [rsp+70h+var_s0]
0x1800359ce  mov     rbx, [r11+10h]
0x1800359d2  mov     rdi, [r11+18h]
0x1800359d6  mov     rsp, r11
0x1800359d9  pop     rbp
0x1800359da  retn
```
