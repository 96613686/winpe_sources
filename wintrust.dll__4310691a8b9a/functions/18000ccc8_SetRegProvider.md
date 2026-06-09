# SetRegProvider

- ea: `0x18000ccc8`
- end: `0x18000cf41`
- name: `SetRegProvider`
- size: `633`
- prototype: `_BOOL8 __fastcall(__int64, WCHAR *, const BYTE *, const BYTE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180036b8c`

## callees

- `0x18000ccc8`
- `0x18000cf50`
- `0x18000d1c0`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf13`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ceba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000cef1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ceba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000cef1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ce77`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ce77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cefe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cefe`

## pseudocode

```c
_BOOL8 __fastcall SetRegProvider(__int64 a1, WCHAR *a2, const BYTE *a3, const BYTE *a4)
{
  WCHAR *v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r9
  WCHAR *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  bool v14; // zf
  WCHAR *v15; // rcx
  __int64 v16; // rdx
  WCHAR *v17; // rax
  __int64 v18; // r8
  const unsigned __int16 *v19; // rcx
  __int64 v20; // rax
  WCHAR *v21; // r8
  WCHAR *v22; // rcx
  LSTATUS v23; // eax
  DWORD v24; // ecx
  __int64 v25; // rax
  LSTATUS v26; // edi
  LSTATUS v27; // ebx
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v31[40]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[128]; // [rsp+B0h] [rbp-50h] BYREF

  dwDisposition = 0;
  hKey = 0;
  v6 = a2;
  if ( !a1 )
    goto LABEL_35;
  if ( !a2 )
    goto LABEL_35;
  if ( !a3 )
    goto LABEL_35;
  if ( !a4 )
    goto LABEL_35;
  if ( !(unsigned int)guid2wstr(a1, v31) )
    goto LABEL_35;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( v31[v8] );
  v9 = -1;
  do
    ++v9;
  while ( v6[v9] );
  if ( (unsigned __int64)(v9 + v8 + 2) > 0x80 )
  {
LABEL_35:
    v24 = 87;
    goto LABEL_36;
  }
  v10 = 2147483646;
  v11 = SubKey;
  v12 = 2147483646;
  v13 = 128;
  do
  {
    if ( !v12 )
      break;
    if ( !*v6 )
      break;
    *v11++ = *v6++;
    --v12;
    --v13;
  }
  while ( v13 );
  v14 = v13 == 0;
  v15 = v11 - 1;
  v16 = 128;
  if ( !v14 )
    v15 = v11;
  v17 = SubKey;
  *v15 = 0;
  do
  {
    if ( !*v17 )
      break;
    ++v17;
    --v16;
  }
  while ( v16 );
  v18 = (128 - v16) & -(__int64)(v16 != 0);
  if ( v16 )
  {
    v19 = L"\\";
    v20 = 128 - v18;
    v14 = v18 == 128;
    v21 = &SubKey[v18];
    if ( !v14 )
    {
      do
      {
        if ( !v10 )
          break;
        if ( !*v19 )
          break;
        *v21++ = *v19++;
        --v10;
        --v20;
      }
      while ( v20 );
    }
    v22 = v21 - 1;
    if ( v20 )
      v22 = v21;
    *v22 = 0;
  }
  StringCchCatW(SubKey, 0x80u, v31);
  v23 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition);
  if ( v23 )
  {
    v24 = v23;
LABEL_36:
    SetLastError(v24);
    return 0;
  }
  v25 = -1;
  do
    ++v25;
  while ( *(_WORD *)&a3[2 * v25] );
  v26 = RegSetValueExW(hKey, L"$DLL", 0, 1u, a3, 2 * v25 + 2);
  do
    ++v7;
  while ( *(_WORD *)&a4[2 * v7] );
  v27 = RegSetValueExW(hKey, L"$Function", 0, 1u, a4, 2 * v7 + 2);
  RegCloseKey(hKey);
  return (v26 | v27) == 0;
}

```

## disassembly

```asm
0x18000ccc8  mov     [rsp-8+arg_8], rbx
0x18000cccd  push    rbp
0x18000ccce  push    rsi
0x18000cccf  push    rdi
0x18000ccd0  push    r14
0x18000ccd2  push    r15
0x18000ccd4  lea     rbp, [rsp-0C0h]
0x18000ccdc  sub     rsp, 1C0h
0x18000cce3  mov     rax, cs:__security_cookie
0x18000ccea  xor     rax, rsp
0x18000cced  mov     [rbp+0E0h+var_30], rax
0x18000ccf4  xor     r15d, r15d
0x18000ccf7  mov     r14, r9
0x18000ccfa  mov     [rsp+1E0h+dwDisposition], r15d
0x18000ccff  mov     rsi, r8
0x18000cd02  mov     [rsp+1E0h+hKey], r15
0x18000cd07  mov     rdi, rdx
0x18000cd0a  test    rcx, rcx
0x18000cd0d  jz      loc_18000CF0E
0x18000cd13  test    rdx, rdx
0x18000cd16  jz      loc_18000CF0E
0x18000cd1c  test    r8, r8
0x18000cd1f  jz      loc_18000CF0E
0x18000cd25  test    r9, r9
0x18000cd28  jz      loc_18000CF0E
0x18000cd2e  lea     rdx, [rsp+1E0h+var_180]
0x18000cd33  call    guid2wstr
0x18000cd38  test    eax, eax
0x18000cd3a  jz      loc_18000CF0E
0x18000cd40  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000cd44  lea     rcx, [rsp+1E0h+var_180]
0x18000cd49  mov     rax, rbx
0x18000cd4c  inc     rax
0x18000cd4f  cmp     [rcx+rax*2], r15w
0x18000cd54  jnz     short loc_18000CD4C
0x18000cd56  mov     rcx, rbx
0x18000cd59  inc     rcx
0x18000cd5c  cmp     [rdi+rcx*2], r15w
0x18000cd61  jnz     short loc_18000CD59
0x18000cd63  add     rax, 2
0x18000cd67  mov     r10d, 80h
0x18000cd6d  add     rax, rcx
0x18000cd70  cmp     rax, r10
0x18000cd73  ja      loc_18000CF0E
0x18000cd79  mov     r9d, 7FFFFFFEh
0x18000cd7f  lea     rax, [rbp+0E0h+SubKey]
0x18000cd83  mov     ecx, r9d
0x18000cd86  mov     edx, r10d
0x18000cd89  test    rcx, rcx
0x18000cd8c  jz      short loc_18000CDAD
0x18000cd8e  movzx   r8d, word ptr [rdi]
0x18000cd92  test    r8w, r8w
0x18000cd96  jz      short loc_18000CDAD
0x18000cd98  mov     [rax], r8w
0x18000cd9c  add     rdi, 2
0x18000cda0  add     rax, 2
0x18000cda4  dec     rcx
0x18000cda7  sub     rdx, 1
0x18000cdab  jnz     short loc_18000CD89
0x18000cdad  test    rdx, rdx
0x18000cdb0  lea     rcx, [rax-2]
0x18000cdb4  mov     rdx, r10
0x18000cdb7  cmovnz  rcx, rax
0x18000cdbb  lea     rax, [rbp+0E0h+SubKey]
0x18000cdbf  mov     [rcx], r15w
0x18000cdc3  cmp     [rax], r15w
0x18000cdc7  jz      short loc_18000CDD3
0x18000cdc9  add     rax, 2
0x18000cdcd  sub     rdx, 1
0x18000cdd1  jnz     short loc_18000CDC3
0x18000cdd3  mov     rcx, r10
0x18000cdd6  mov     rax, rdx
0x18000cdd9  sub     rcx, rdx
0x18000cddc  neg     rax
0x18000cddf  sbb     r8, r8
0x18000cde2  and     r8, rcx
0x18000cde5  test    rdx, rdx
0x18000cde8  jz      short loc_18000CE2F
0x18000cdea  mov     rax, r10
0x18000cded  lea     rcx, asc_1800557E4; "\\"
0x18000cdf4  sub     rax, r8
0x18000cdf7  lea     r8, [rbp+r8*2+0E0h+SubKey]
0x18000cdfc  jz      short loc_18000CE20
0x18000cdfe  test    r9, r9
0x18000ce01  jz      short loc_18000CE20
0x18000ce03  movzx   edx, word ptr [rcx]
0x18000ce06  test    dx, dx
0x18000ce09  jz      short loc_18000CE20
0x18000ce0b  mov     [r8], dx
0x18000ce0f  add     rcx, 2
0x18000ce13  add     r8, 2
0x18000ce17  dec     r9
0x18000ce1a  sub     rax, 1
0x18000ce1e  jnz     short loc_18000CDFE
0x18000ce20  test    rax, rax
0x18000ce23  lea     rcx, [r8-2]
0x18000ce27  cmovnz  rcx, r8
0x18000ce2b  mov     [rcx], r15w
0x18000ce2f  lea     r8, [rsp+1E0h+var_180]; unsigned __int16 *
0x18000ce34  mov     rdx, r10; unsigned __int64
0x18000ce37  lea     rcx, [rbp+0E0h+SubKey]; unsigned __int16 *
0x18000ce3b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ce40  lea     rax, [rsp+1E0h+dwDisposition]
0x18000ce45  xor     r9d, r9d; lpClass
0x18000ce48  mov     [rsp+1E0h+lpdwDisposition], rax; lpdwDisposition
0x18000ce4d  lea     rdx, [rbp+0E0h+SubKey]; lpSubKey
0x18000ce51  lea     rax, [rsp+1E0h+hKey]
0x18000ce56  xor     r8d, r8d; Reserved
0x18000ce59  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18000ce5e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ce65  mov     [rsp+1E0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18000ce6a  mov     [rsp+1E0h+samDesired], 20006h; samDesired
0x18000ce72  mov     [rsp+1E0h+dwOptions], r15d; dwOptions
0x18000ce77  call    cs:__imp_RegCreateKeyExW
0x18000ce7d  test    eax, eax
0x18000ce7f  jz      short loc_18000CE88
0x18000ce81  mov     ecx, eax
0x18000ce83  jmp     loc_18000CF13
0x18000ce88  mov     rax, rbx
0x18000ce8b  inc     rax
0x18000ce8e  cmp     [rsi+rax*2], r15w
0x18000ce93  jnz     short loc_18000CE8B
0x18000ce95  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18000ce9a  lea     eax, ds:2[rax*2]
0x18000cea1  mov     [rsp+1E0h+samDesired], eax; cbData
0x18000cea5  lea     rdx, aDll; "$DLL"
0x18000ceac  mov     r9d, 1; dwType
0x18000ceb2  mov     qword ptr [rsp+1E0h+dwOptions], rsi; lpData
0x18000ceb7  xor     r8d, r8d; Reserved
0x18000ceba  call    cs:__imp_RegSetValueExW
0x18000cec0  mov     edi, eax
0x18000cec2  inc     rbx
0x18000cec5  cmp     [r14+rbx*2], r15w
0x18000ceca  jnz     short loc_18000CEC2
0x18000cecc  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18000ced1  lea     eax, ds:2[rbx*2]
0x18000ced8  mov     [rsp+1E0h+samDesired], eax; cbData
0x18000cedc  lea     rdx, aFunction; "$Function"
0x18000cee3  mov     r9d, 1; dwType
0x18000cee9  mov     qword ptr [rsp+1E0h+dwOptions], r14; lpData
0x18000ceee  xor     r8d, r8d; Reserved
0x18000cef1  call    cs:__imp_RegSetValueExW
0x18000cef7  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18000cefc  mov     ebx, eax
0x18000cefe  call    cs:__imp_RegCloseKey
0x18000cf04  or      ebx, edi
0x18000cf06  mov     eax, r15d
0x18000cf09  setz    al
0x18000cf0c  jmp     short loc_18000CF1B
0x18000cf0e  mov     ecx, 57h ; 'W'; dwErrCode
0x18000cf13  call    cs:__imp_SetLastError
0x18000cf19  xor     eax, eax
0x18000cf1b  mov     rcx, [rbp+0E0h+var_30]
0x18000cf22  xor     rcx, rsp; StackCookie
0x18000cf25  call    __security_check_cookie
0x18000cf2a  mov     rbx, [rsp+1E0h+arg_8]
0x18000cf32  add     rsp, 1C0h
0x18000cf39  pop     r15
0x18000cf3b  pop     r14
0x18000cf3d  pop     rdi
0x18000cf3e  pop     rsi
0x18000cf3f  pop     rbp
0x18000cf40  retn
```
