# IsolationAwareLoadLibraryW

- ea: `0x18007b190`
- end: `0x18007b2c0`
- name: `IsolationAwareLoadLibraryW`
- size: `304`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18007aac0`

## callees

- `0x18007b190`
- `0x18007b2c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007b2b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b697f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007b2b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b697f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b22a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b695f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b22a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b695f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18007b1e0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18007b1e0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18007b26f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18007b26f`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x18007b216`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x18007b216`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18007b2a9`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800b6973`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18007b2a9`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800b6973`

## string_xrefs

- `0x18007b268`: `wmitomi.dll`

## pseudocode

```c
HMODULE IsolationAwareLoadLibraryW()
{
  int v0; // eax
  int v1; // ecx
  int v2; // edi
  int v3; // ebx
  DWORD LastError; // eax
  HMODULE LibraryW; // rax
  HMODULE v7; // rdi
  DWORD v8; // esi
  ULONG_PTR Cookie; // [rsp+40h] [rbp+8h] BYREF

  Cookie = 0;
  if ( IsolationAwarePrivateT_SAbnPgpgk )
    goto LABEL_19;
  v0 = IsolationAwarePrivateT_SqbjaYRiRY;
  if ( IsolationAwarePrivateT_SqbjaYRiRY )
    goto LABEL_19;
  v1 = WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ;
  if ( WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ )
  {
    OutputDebugStringA("IsolationAware function called after IsolationAwareCleanup\n");
    v0 = IsolationAwarePrivateT_SqbjaYRiRY;
    v1 = WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ;
  }
  if ( v0 )
  {
LABEL_19:
    v3 = 1;
  }
  else
  {
    v2 = 0;
    if ( v1 || (unsigned int)WinbaseIsolationAwarePrivatetRgzlnPgpgk() )
    {
      v3 = 1;
      if ( ActivateActCtx(WinbaseIsolationAwarePrivateT_UnPgpgk, &Cookie) )
        v2 = 1;
    }
    else
    {
      v3 = 1;
    }
    if ( !v2 )
    {
      LastError = GetLastError();
      if ( LastError == 120 || LastError == 50 || LastError == 1 || LastError - 126 <= 1 )
      {
        IsolationAwarePrivateT_SqbjaYRiRY = 1;
        v2 = 1;
      }
      if ( !v2 )
        return 0;
    }
  }
  LibraryW = LoadLibraryW(L"wmitomi.dll");
  v7 = LibraryW;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( LibraryW )
    {
      v3 = 0;
      v8 = 0;
    }
    else
    {
      v8 = GetLastError();
    }
    DeactivateActCtx(0, Cookie);
    if ( v3 )
      SetLastError(v8);
  }
  return v7;
}

```

## disassembly

```asm
0x18007b190  mov     rax, rsp
0x18007b193  mov     [rax+10h], rbx
0x18007b197  mov     [rax+18h], rsi
0x18007b19b  mov     [rax+8], rcx
0x18007b19f  push    rdi
0x18007b1a0  sub     rsp, 30h
0x18007b1a4  mov     qword ptr [rax-18h], 0
0x18007b1ac  mov     qword ptr [rax+8], 0
0x18007b1b4  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18007b1bb  jnz     loc_18007B263
0x18007b1c1  mov     eax, cs:IsolationAwarePrivateT_SqbjaYRiRY
0x18007b1c7  test    eax, eax
0x18007b1c9  jnz     loc_18007B263
0x18007b1cf  mov     ecx, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x18007b1d5  test    ecx, ecx
0x18007b1d7  jz      short loc_18007B1F2
0x18007b1d9  lea     rcx, ?debugString@?4??IsolationAwarePrivatenPgViNgRzlnPgpgk@@9@4QBDB; "IsolationAware function called after Is"...
0x18007b1e0  call    cs:__imp_OutputDebugStringA
0x18007b1e6  mov     eax, cs:IsolationAwarePrivateT_SqbjaYRiRY
0x18007b1ec  mov     ecx, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x18007b1f2  test    eax, eax
0x18007b1f4  jnz     short loc_18007B263
0x18007b1f6  xor     edi, edi
0x18007b1f8  test    ecx, ecx
0x18007b1fa  jnz     short loc_18007B20A
0x18007b1fc  call    WinbaseIsolationAwarePrivatetRgzlnPgpgk
0x18007b201  test    eax, eax
0x18007b203  jnz     short loc_18007B20A
0x18007b205  lea     ebx, [rdi+1]
0x18007b208  jmp     short loc_18007B226
0x18007b20a  lea     rdx, [rsp+38h+Cookie]; lpCookie
0x18007b20f  mov     rcx, cs:WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18007b216  call    cs:__imp_ActivateActCtx
0x18007b21c  mov     ebx, 1
0x18007b221  test    eax, eax
0x18007b223  cmovnz  edi, ebx
0x18007b226  test    edi, edi
0x18007b228  jnz     short loc_18007B268
0x18007b22a  call    cs:__imp_GetLastError
0x18007b230  cmp     eax, 78h ; 'x'
0x18007b233  jz      short loc_18007B245
0x18007b235  cmp     eax, 32h ; '2'
0x18007b238  jz      short loc_18007B245
0x18007b23a  cmp     eax, ebx
0x18007b23c  jz      short loc_18007B245
0x18007b23e  add     eax, 0FFFFFF82h
0x18007b241  cmp     eax, ebx
0x18007b243  ja      short loc_18007B24D
0x18007b245  mov     cs:IsolationAwarePrivateT_SqbjaYRiRY, ebx
0x18007b24b  mov     edi, ebx
0x18007b24d  test    edi, edi
0x18007b24f  jnz     short loc_18007B268
0x18007b251  xor     eax, eax
0x18007b253  mov     rbx, [rsp+38h+arg_8]
0x18007b258  mov     rsi, [rsp+38h+arg_10]
0x18007b25d  add     rsp, 30h
0x18007b261  pop     rdi
0x18007b262  retn
0x18007b263  mov     ebx, 1
0x18007b268  lea     rcx, aWmitomiDll; "wmitomi.dll"
0x18007b26f  call    cs:__imp_LoadLibraryW
0x18007b275  mov     rdi, rax
0x18007b278  mov     [rsp+38h+var_18], rax
0x18007b27d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18007b284  jz      short loc_18007B28F
0x18007b286  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18007b28d  jnz     short loc_18007B2BB
0x18007b28f  test    rdi, rdi
0x18007b292  jnz     short loc_18007B29E
0x18007b294  call    cs:__imp_GetLastError
0x18007b29a  mov     esi, eax
0x18007b29c  jmp     short loc_18007B2A2
0x18007b29e  xor     ebx, ebx
0x18007b2a0  xor     esi, esi
0x18007b2a2  mov     rdx, [rsp+38h+Cookie]; ulCookie
0x18007b2a7  xor     ecx, ecx; dwFlags
0x18007b2a9  call    cs:__imp_DeactivateActCtx
0x18007b2af  test    ebx, ebx
0x18007b2b1  jz      short loc_18007B2BB
0x18007b2b3  mov     ecx, esi; dwErrCode
0x18007b2b5  call    cs:__imp_SetLastError
0x18007b2bb  mov     rax, rdi
0x18007b2be  jmp     short loc_18007B253
0x1800b6936  push    rbx
0x1800b6938  push    rbp
0x1800b6939  push    rdi
0x1800b693a  sub     rsp, 20h
0x1800b693e  mov     rbp, rdx
0x1800b6941  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800b6948  jz      short loc_1800B6953
0x1800b694a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800b6951  jnz     short loc_1800B6986
0x1800b6953  cmp     qword ptr [rbp+20h], 0
0x1800b6958  jnz     short loc_1800B6969
0x1800b695a  mov     edi, 1
0x1800b695f  call    cs:__imp_GetLastError
0x1800b6965  mov     ebx, eax
0x1800b6967  jmp     short loc_1800B696D
0x1800b6969  xor     edi, edi
0x1800b696b  xor     ebx, ebx
0x1800b696d  mov     rdx, [rbp+40h]; ulCookie
0x1800b6971  xor     ecx, ecx; dwFlags
0x1800b6973  call    cs:__imp_DeactivateActCtx
0x1800b6979  test    edi, edi
0x1800b697b  jz      short loc_1800B6986
0x1800b697d  mov     ecx, ebx; dwErrCode
0x1800b697f  call    cs:__imp_SetLastError
0x1800b6985  nop
0x1800b6986  add     rsp, 20h
0x1800b698a  pop     rdi
0x1800b698b  pop     rbp
0x1800b698c  pop     rbx
0x1800b698d  retn
```
