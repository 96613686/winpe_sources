# ValidateInterfaces(ushort const *,HINSTANCE__ * &,_tagPluginAPITable &)

- ea: `0x180001af4`
- end: `0x180001c8b`
- name: `?ValidateInterfaces@@YAKPEBGAEAPEAUHINSTANCE__@@AEAU_tagPluginAPITable@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HINSTANCE *, struct _tagPluginAPITable *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800022c0`

## callees

- `0x180001af4`
- `0x180001e44`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001b14`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001b14`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001b5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001b78`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001b8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001b9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001bb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001bc4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001bd7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001b5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001b78`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001b8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001b9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001bb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001bc4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001bd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b22`

## string_xrefs

- `0x180001bca`: `EasEncryptProvUpdateDeviceLockoutState`

## pseudocode

```c
__int64 __fastcall ValidateInterfaces(const unsigned __int16 *a1, HINSTANCE *a2, struct _tagPluginAPITable *a3)
{
  HMODULE Library; // rax
  HMODULE v5; // rdi
  DWORD LastError; // ebx
  int v7; // r8d
  _QWORD *v8; // rcx
  int v9; // edx
  FARPROC v10; // rbp
  FARPROC v11; // r14
  FARPROC v12; // r15
  FARPROC v13; // r12
  FARPROC v14; // r13
  FARPROC v15; // rax
  FARPROC ProcAddress; // [rsp+90h] [rbp+18h]

  Library = LoadLibraryExW(a1, 0, 0x1100u);
  v5 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "EasEncryptProvQueryProtectionStatus");
    v10 = GetProcAddress(v5, "EasEncryptProvIsDeviceLockable");
    v11 = GetProcAddress(v5, "EasEncryptProvLockDevice");
    v12 = GetProcAddress(v5, "EasEncryptProvValidateDeviceLockoutState");
    v13 = GetProcAddress(v5, "EasEncryptProvDisableDeviceLockoutState");
    v14 = GetProcAddress(v5, "EasEncryptProvGetDeviceLockoutData");
    v15 = GetProcAddress(v5, "EasEncryptProvUpdateDeviceLockoutState");
    if ( ProcAddress && v10 && v11 && v14 && v12 && v13 && v15 )
    {
      LastError = 0;
      g_Table = ProcAddress;
      g_hInstance = v5;
      *(&g_Table + 1) = v10;
      *(_QWORD *)&xmmword_180008718 = v11;
      *((_QWORD *)&xmmword_180008718 + 1) = v12;
      *(_QWORD *)&xmmword_180008728 = v13;
      *((_QWORD *)&xmmword_180008728 + 1) = v14;
      qword_180008738 = (__int64)v15;
    }
    else
    {
      LastError = 632;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 11;
        goto LABEL_16;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 10;
LABEL_16:
      WPP_SF_DS(v8[2], v9, v7, LastError, (__int64)a1);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180001af4  mov     [rsp+arg_10], r8
0x180001af9  push    rbx
0x180001afa  push    rbp
0x180001afb  push    rsi
0x180001afc  push    rdi
0x180001afd  push    r12
0x180001aff  push    r13
0x180001b01  push    r14
0x180001b03  push    r15
0x180001b05  sub     rsp, 38h
0x180001b09  xor     edx, edx; hFile
0x180001b0b  mov     r8d, 1100h; dwFlags
0x180001b11  mov     rsi, rcx
0x180001b14  call    cs:__imp_LoadLibraryExW
0x180001b1a  mov     rdi, rax
0x180001b1d  test    rax, rax
0x180001b20  jnz     short loc_180001B53
0x180001b22  call    cs:__imp_GetLastError
0x180001b28  mov     ebx, eax
0x180001b2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b31  lea     rax, WPP_GLOBAL_Control
0x180001b38  cmp     rcx, rax
0x180001b3b  jz      loc_180001C78
0x180001b41  test    byte ptr [rcx+1Ch], 1
0x180001b45  jz      loc_180001C78
0x180001b4b  lea     edx, [rdi+0Ah]
0x180001b4e  jmp     loc_180001C67
0x180001b53  lea     rdx, ProcName; "EasEncryptProvQueryProtectionStatus"
0x180001b5a  mov     rcx, rdi; hModule
0x180001b5d  call    cs:__imp_GetProcAddress
0x180001b63  lea     rdx, aEasencryptprov; "EasEncryptProvIsDeviceLockable"
0x180001b6a  mov     rcx, rdi; hModule
0x180001b6d  mov     rbx, rax
0x180001b70  mov     [rsp+78h+arg_10], rax
0x180001b78  call    cs:__imp_GetProcAddress
0x180001b7e  lea     rdx, aEasencryptprov_3; "EasEncryptProvLockDevice"
0x180001b85  mov     rcx, rdi; hModule
0x180001b88  mov     rbp, rax
0x180001b8b  call    cs:__imp_GetProcAddress
0x180001b91  lea     rdx, aEasencryptprov_1; "EasEncryptProvValidateDeviceLockoutStat"...
0x180001b98  mov     rcx, rdi; hModule
0x180001b9b  mov     r14, rax
0x180001b9e  call    cs:__imp_GetProcAddress
0x180001ba4  lea     rdx, aEasencryptprov_4; "EasEncryptProvDisableDeviceLockoutState"
0x180001bab  mov     rcx, rdi; hModule
0x180001bae  mov     r15, rax
0x180001bb1  call    cs:__imp_GetProcAddress
0x180001bb7  lea     rdx, aEasencryptprov_0; "EasEncryptProvGetDeviceLockoutData"
0x180001bbe  mov     rcx, rdi; hModule
0x180001bc1  mov     r12, rax
0x180001bc4  call    cs:__imp_GetProcAddress
0x180001bca  lea     rdx, aEasencryptprov_5; "EasEncryptProvUpdateDeviceLockoutState"
0x180001bd1  mov     rcx, rdi; hModule
0x180001bd4  mov     r13, rax
0x180001bd7  call    cs:__imp_GetProcAddress
0x180001bdd  test    rbx, rbx
0x180001be0  jz      short loc_180001C44
0x180001be2  test    rbp, rbp
0x180001be5  jz      short loc_180001C44
0x180001be7  test    r14, r14
0x180001bea  jz      short loc_180001C44
0x180001bec  test    r13, r13
0x180001bef  jz      short loc_180001C44
0x180001bf1  test    r15, r15
0x180001bf4  jz      short loc_180001C44
0x180001bf6  test    r12, r12
0x180001bf9  jz      short loc_180001C44
0x180001bfb  test    rax, rax
0x180001bfe  jz      short loc_180001C44
0x180001c00  mov     rcx, [rsp+78h+arg_10]
0x180001c08  xor     ebx, ebx
0x180001c0a  mov     qword ptr cs:?g_Table@@3U_tagPluginAPITable@@A, rcx; _tagPluginAPITable g_Table
0x180001c11  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hInstance
0x180001c18  mov     qword ptr cs:?g_Table@@3U_tagPluginAPITable@@A+8, rbp; _tagPluginAPITable g_Table
0x180001c1f  mov     qword ptr cs:xmmword_180008718, r14
0x180001c26  mov     qword ptr cs:xmmword_180008718+8, r15
0x180001c2d  mov     qword ptr cs:xmmword_180008728, r12
0x180001c34  mov     qword ptr cs:xmmword_180008728+8, r13
0x180001c3b  mov     cs:qword_180008738, rax
0x180001c42  jmp     short loc_180001C78
0x180001c44  mov     ebx, 278h
0x180001c49  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c50  lea     rax, WPP_GLOBAL_Control
0x180001c57  cmp     rcx, rax
0x180001c5a  jz      short loc_180001C78
0x180001c5c  test    byte ptr [rcx+1Ch], 1
0x180001c60  jz      short loc_180001C78
0x180001c62  mov     edx, 0Bh
0x180001c67  mov     rcx, [rcx+10h]
0x180001c6b  mov     r9d, ebx
0x180001c6e  mov     [rsp+78h+var_58], rsi
0x180001c73  call    WPP_SF_DS
0x180001c78  mov     eax, ebx
0x180001c7a  add     rsp, 38h
0x180001c7e  pop     r15
0x180001c80  pop     r14
0x180001c82  pop     r13
0x180001c84  pop     r12
0x180001c86  pop     rdi
0x180001c87  pop     rsi
0x180001c88  pop     rbp
0x180001c89  pop     rbx
0x180001c8a  retn
```
