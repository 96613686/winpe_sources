# __ClientLoadLibrary

- ea: `0x18001f880`
- end: `0x18001fa13`
- name: `__ClientLoadLibrary`
- size: `403`
- prototype: `__int64 __fastcall(struct _CAPTUREBUF *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x18001f880`
- `0x18001fa1c`
- `0x180020058`
- `0x180020084`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `ntdll!NtCallbackReturn` at `0x18001f96f`
- `ntdll!NtCallbackReturn` at `0x18001f96f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f9de`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f9de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f9f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f9f1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f947`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f947`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001f9cb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001f9cb`

## pseudocode

```c
NTSTATUS __fastcall _ClientLoadLibrary(struct _CAPTUREBUF *a1)
{
  __int64 v2; // rdx
  bool v3; // zf
  HMODULE Library; // rbx
  const WCHAR *v5; // r8
  HMODULE v7; // rdi
  int (*ProcAddress)(unsigned int, void *); // rax
  int v9; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v11; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD Result[3]; // [rsp+58h] [rbp-A8h] BYREF
  CHAR MultiByteStr; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v14[271]; // [rsp+71h] [rbp-8Fh] BYREF

  MultiByteStr = 0;
  memset_0(v14, 0, 0x103u);
  v3 = *((_DWORD *)a1 + 2) == 0;
  memset(Result, 0, sizeof(Result));
  if ( !v3 && !*((_QWORD *)a1 + 4) )
    FixupCallbackPointers(a1);
  v9 = 0x40000;
  v10 = 0;
  v11 = 0;
  AppModelPolicy_GetPolicy_Internal(-6, v2, &v9, &v11, &v10);
  Library = LoadLibraryExW(*((LPCWSTR *)a1 + 6), 0, v9 != 262145 ? 8 : 0);
  if ( Library )
  {
    v5 = (const WCHAR *)*((_QWORD *)a1 + 8);
    if ( v5 )
    {
      v7 = Library;
      if ( WideCharToMultiByte(0, 0x400u, v5, -1, &MultiByteStr, 260, 0, 0) )
      {
        ProcAddress = (int (*)(unsigned int, void *))GetProcAddress(Library, &MultiByteStr);
        if ( ProcAddress && (unsigned int)InitUserApiHook(Library, ProcAddress) )
          goto LABEL_6;
        Library = 0;
      }
      else
      {
        Library = 0;
      }
      FreeLibrary(v7);
    }
  }
LABEL_6:
  Result[0] = Library;
  return NtCallbackReturn(Result, 0x18u, 0);
}

```

## disassembly

```asm
0x18001f880  mov     [rsp-8+arg_8], rbx
0x18001f885  mov     [rsp-8+arg_10], rdi
0x18001f88a  push    rbp
0x18001f88b  lea     rbp, [rsp-90h]
0x18001f893  sub     rsp, 190h
0x18001f89a  mov     rax, cs:__security_cookie
0x18001f8a1  xor     rax, rsp
0x18001f8a4  mov     [rbp+90h+var_10], rax
0x18001f8ab  mov     rdi, rcx
0x18001f8ae  mov     [rsp+190h+MultiByteStr], 0
0x18001f8b3  lea     rcx, [rsp+190h+var_11F]; void *
0x18001f8b8  xor     edx, edx; Val
0x18001f8ba  mov     r8d, 103h; Size
0x18001f8c0  call    memset_0
0x18001f8c5  cmp     dword ptr [rdi+8], 0
0x18001f8c9  mov     [rsp+190h+Result], 0
0x18001f8d2  mov     [rsp+190h+var_130], 0
0x18001f8db  mov     [rsp+190h+var_128], 0
0x18001f8e4  jz      short loc_18001F8F5
0x18001f8e6  cmp     qword ptr [rdi+20h], 0
0x18001f8eb  jnz     short loc_18001F8F5
0x18001f8ed  mov     rcx, rdi; struct _CAPTUREBUF *
0x18001f8f0  call    ?FixupCallbackPointers@@YAXPEAU_CAPTUREBUF@@@Z; FixupCallbackPointers(_CAPTUREBUF *)
0x18001f8f5  lea     rax, [rsp+190h+var_148]
0x18001f8fa  mov     [rsp+190h+var_150], 40000h
0x18001f902  lea     r9, [rsp+190h+var_140]
0x18001f907  mov     [rsp+190h+lpMultiByteStr], rax
0x18001f90c  lea     r8, [rsp+190h+var_150]
0x18001f911  mov     [rsp+190h+var_148], 0
0x18001f91a  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x18001f921  mov     [rsp+190h+var_140], 0
0x18001f92a  call    ?AppModelPolicy_GetPolicy_Internal@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@PEAU_PS_PKG_CLAIM@@PEA_K@Z; AppModelPolicy_GetPolicy_Internal(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *,_PS_PKG_CLAIM *,unsigned __int64 *)
0x18001f92f  mov     eax, [rsp+190h+var_150]
0x18001f933  mov     rcx, [rdi+30h]; lpLibFileName
0x18001f937  sub     eax, 40001h
0x18001f93c  neg     eax
0x18001f93e  sbb     r8d, r8d
0x18001f941  xor     edx, edx; hFile
0x18001f943  and     r8d, 8; dwFlags
0x18001f947  call    cs:__imp_LoadLibraryExW
0x18001f94d  mov     rbx, rax
0x18001f950  test    rax, rax
0x18001f953  jz      short loc_18001F95E
0x18001f955  mov     r8, [rdi+40h]; lpWideCharStr
0x18001f959  test    r8, r8
0x18001f95c  jnz     short loc_18001F999
0x18001f95e  xor     r8d, r8d; Status
0x18001f961  mov     [rsp+190h+Result], rbx
0x18001f966  lea     rcx, [rsp+190h+Result]; Result
0x18001f96b  lea     edx, [r8+18h]; ResultLength
0x18001f96f  call    cs:__imp_NtCallbackReturn
0x18001f975  mov     rcx, [rbp+90h+var_10]
0x18001f97c  xor     rcx, rsp; StackCookie
0x18001f97f  call    __security_check_cookie
0x18001f984  lea     r11, [rsp+190h+var_s0]
0x18001f98c  mov     rbx, [r11+18h]
0x18001f990  mov     rdi, [r11+20h]
0x18001f994  mov     rsp, r11
0x18001f997  pop     rbp
0x18001f998  retn
0x18001f999  mov     [rsp+190h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001f9a2  lea     rax, [rsp+190h+MultiByteStr]
0x18001f9a7  mov     [rsp+190h+lpDefaultChar], 0; lpDefaultChar
0x18001f9b0  or      r9d, 0FFFFFFFFh; cchWideChar
0x18001f9b4  mov     [rsp+190h+cbMultiByte], 104h; cbMultiByte
0x18001f9bc  mov     edx, 400h; dwFlags
0x18001f9c1  xor     ecx, ecx; CodePage
0x18001f9c3  mov     [rsp+190h+lpMultiByteStr], rax; lpMultiByteStr
0x18001f9c8  mov     rdi, rbx
0x18001f9cb  call    cs:__imp_WideCharToMultiByte
0x18001f9d1  movsxd  rcx, eax
0x18001f9d4  test    eax, eax
0x18001f9d6  jnz     short loc_18001F9E9
0x18001f9d8  mov     rbx, rcx
0x18001f9db  mov     rcx, rdi; hLibModule
0x18001f9de  call    cs:__imp_FreeLibrary
0x18001f9e4  jmp     loc_18001F95E
0x18001f9e9  lea     rdx, [rsp+190h+MultiByteStr]; lpProcName
0x18001f9ee  mov     rcx, rbx; hModule
0x18001f9f1  call    cs:__imp_GetProcAddress
0x18001f9f7  test    rax, rax
0x18001f9fa  jz      short loc_18001FA0F
0x18001f9fc  mov     rdx, rax; int (*)(unsigned int, void *)
0x18001f9ff  mov     rcx, rbx; HINSTANCE
0x18001fa02  call    ?InitUserApiHook@@YAHPEAUHINSTANCE__@@P6AHKPEAX@Z@Z; InitUserApiHook(HINSTANCE__ *,int (*)(ulong,void *))
0x18001fa07  test    eax, eax
0x18001fa09  jnz     loc_18001F95E
0x18001fa0f  xor     ebx, ebx
0x18001fa11  jmp     short loc_18001F9DB
```
