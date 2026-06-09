# OpenPersonalTrustDBDialogEx

- ea: `0x1800402b0`
- end: `0x18004038d`
- name: `OpenPersonalTrustDBDialogEx`
- size: `221`
- prototype: `BOOL __stdcall(HWND hwndParent, DWORD dwFlags, PVOID *pvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800402a0`

## callees

- `0x1800402b0`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040301`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040301`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004036e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004036e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004037a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004037a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004035c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004035c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800402e9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800402e9`

## string_xrefs

- `0x1800402d1`: `cryptui.dll`

## pseudocode

```c
BOOL __stdcall OpenPersonalTrustDBDialogEx(HWND hwndParent, DWORD dwFlags, PVOID *pvReserved)
{
  BOOL v3; // edi
  char v4; // bp
  HMODULE LibraryA; // rax
  HMODULE v7; // rbx
  FARPROC ProcAddress; // rdx
  DWORD LastError; // esi
  int v10; // eax
  _OWORD v12[5]; // [rsp+20h] [rbp-58h] BYREF

  v3 = 1;
  v4 = dwFlags;
  if ( (dwFlags & 1) != 0 )
    return v3;
  memset(v12, 0, 40);
  LibraryA = LoadLibraryA("cryptui.dll");
  v7 = LibraryA;
  if ( LibraryA && (ProcAddress = GetProcAddress(LibraryA, "CryptUIDlgCertMgr")) != 0 )
  {
    LastError = 0;
    *(_QWORD *)&v12[0] = 40;
    v10 = 4;
    *((_QWORD *)&v12[0] + 1) = hwndParent;
    memset((char *)&v12[1] + 4, 0, 20);
    if ( (v4 & 2) != 0 )
      v10 = 32772;
    LODWORD(v12[1]) = v10;
    if ( !((unsigned int (__fastcall *)(_OWORD *))ProcAddress)(v12) )
    {
      v3 = 0;
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = 0;
    if ( !v7 )
      goto LABEL_10;
  }
  FreeLibrary(v7);
LABEL_10:
  if ( LastError )
    SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x1800402b0  push    rbx
0x1800402b2  push    rbp
0x1800402b3  push    rsi
0x1800402b4  push    rdi
0x1800402b5  push    r14
0x1800402b7  sub     rsp, 50h
0x1800402bb  mov     edi, 1
0x1800402c0  mov     ebp, edx
0x1800402c2  mov     r14, rcx
0x1800402c5  test    dil, dl
0x1800402c8  jnz     loc_180040380
0x1800402ce  xorps   xmm0, xmm0
0x1800402d1  lea     rcx, aCryptuiDll; "cryptui.dll"
0x1800402d8  xor     eax, eax
0x1800402da  movups  [rsp+78h+var_58], xmm0
0x1800402df  mov     [rsp+78h+var_38], rax
0x1800402e4  movups  [rsp+78h+var_48], xmm0
0x1800402e9  call    cs:__imp_LoadLibraryA
0x1800402ef  mov     rbx, rax
0x1800402f2  test    rax, rax
0x1800402f5  jz      short loc_18004035C
0x1800402f7  lea     rdx, aCryptuidlgcert; "CryptUIDlgCertMgr"
0x1800402fe  mov     rcx, rax; hModule
0x180040301  call    cs:__imp_GetProcAddress
0x180040307  mov     rdx, rax
0x18004030a  test    rax, rax
0x18004030d  jz      short loc_18004035C
0x18004030f  xor     esi, esi
0x180040311  mov     qword ptr [rsp+78h+var_58], 28h ; '('
0x18004031a  lea     eax, [rdi+3]
0x18004031d  mov     dword ptr [rsp+78h+var_38+4], esi
0x180040321  mov     ecx, 8004h
0x180040326  mov     qword ptr [rsp+78h+var_58+8], r14
0x18004032b  xorps   xmm0, xmm0
0x18004032e  test    bpl, 2
0x180040332  movdqu  [rsp+78h+var_48+4], xmm0
0x180040338  cmovnz  eax, ecx
0x18004033b  lea     rcx, [rsp+78h+var_58]
0x180040340  mov     dword ptr [rsp+78h+var_48], eax
0x180040344  mov     rax, rdx
0x180040347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004034c  test    eax, eax
0x18004034e  jnz     short loc_18004036B
0x180040350  xor     edi, edi
0x180040352  call    cs:__imp_GetLastError
0x180040358  mov     esi, eax
0x18004035a  jmp     short loc_18004036B
0x18004035c  call    cs:__imp_GetLastError
0x180040362  mov     esi, eax
0x180040364  xor     edi, edi
0x180040366  test    rbx, rbx
0x180040369  jz      short loc_180040374
0x18004036b  mov     rcx, rbx; hLibModule
0x18004036e  call    cs:__imp_FreeLibrary
0x180040374  test    esi, esi
0x180040376  jz      short loc_180040380
0x180040378  mov     ecx, esi; dwErrCode
0x18004037a  call    cs:__imp_SetLastError
0x180040380  mov     eax, edi
0x180040382  add     rsp, 50h
0x180040386  pop     r14
0x180040388  pop     rdi
0x180040389  pop     rsi
0x18004038a  pop     rbp
0x18004038b  pop     rbx
0x18004038c  retn
```
