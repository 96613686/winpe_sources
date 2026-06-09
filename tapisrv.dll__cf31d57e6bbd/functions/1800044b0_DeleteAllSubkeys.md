# DeleteAllSubkeys

- ea: `0x1800044b0`
- end: `0x180004693`
- name: `DeleteAllSubkeys`
- size: `483`
- prototype: `__int64 __fastcall(HKEY, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180002b1c`
- `0x1800044b0`

## callees

- `0x1800044b0`
- `0x18002c8d4`
- `0x18003fb7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004646`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004646`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180004658`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180004658`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800045b5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800045b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004623`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004623`
- `KERNEL32!HeapAlloc` at `0x1800044f4`
- `KERNEL32!HeapAlloc` at `0x1800044f4`
- `KERNEL32!LocalAlloc` at `0x180004543`
- `KERNEL32!LocalAlloc` at `0x180004543`
- `KERNEL32!lstrlenW` at `0x180004661`
- `KERNEL32!lstrlenW` at `0x180004661`

## pseudocode

```c
__int64 __fastcall DeleteAllSubkeys(HKEY a1, unsigned int a2)
{
  HKEY v3; // r12
  __int64 result; // rax
  char *v5; // rdi
  unsigned int v6; // r14d
  unsigned int v7; // esi
  DWORD v8; // ebp
  unsigned int v9; // ebx
  char *v10; // rax
  char *v11; // r12
  __int64 v12; // r15
  WCHAR *v13; // r15
  DWORD v14; // edx
  __int64 v15; // r8
  const WCHAR *i; // rsi
  DWORD cchName; // [rsp+98h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp+18h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+A8h] [rbp+20h] BYREF

  phkResult = 0;
  v3 = a1;
  if ( a2 > 5 )
    return 1;
  result = (__int64)HeapAlloc(ghTapisrvHeap, 8u, 0x1000u);
  v5 = (char *)result;
  if ( result )
  {
    v6 = 2048;
    v7 = 0;
    v8 = 0;
    v9 = 1;
    while ( 1 )
    {
      ftLastWriteTime = 0;
      cchName = v6 - v7;
      if ( v6 - v7 >= 0x100 )
      {
        v12 = v7;
      }
      else
      {
        v6 *= 2;
        v10 = (char *)LocalAlloc(0x40u, 2LL * v6);
        v11 = v10;
        if ( !v10 )
        {
          v9 = 0;
          goto LABEL_18;
        }
        v12 = v7;
        memcpy_0(v10, v5, 2LL * v7);
        ServerFree(v5);
        v5 = v11;
        v3 = a1;
      }
      v13 = (WCHAR *)&v5[2 * v12];
      if ( RegEnumKeyExW(v3, v8, v13, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v14 = cchName;
      v15 = cchName + v7;
      if ( *(_WORD *)&v5[2 * (unsigned int)(v15 - 1)] )
      {
        *(_WORD *)&v5[2 * v15] = 0;
        v14 = cchName + 1;
      }
      v7 += v14;
      ++v8;
    }
    *v13 = 0;
    for ( i = (const WCHAR *)v5; *i; i += lstrlenW(i) + 1 )
    {
      if ( !RegOpenKeyExW(v3, i, 0, 0xF003Fu, &phkResult) )
      {
        DeleteAllSubkeys(phkResult, a2 + 1);
        RegCloseKey(phkResult);
      }
      RegDeleteKeyExW(v3, i, 0, 0);
    }
LABEL_18:
    ServerFree(v5);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x1800044b0  mov     rax, rsp
0x1800044b3  mov     [rax+8], rcx
0x1800044b7  push    rbx
0x1800044b8  push    rbp
0x1800044b9  push    rsi
0x1800044ba  push    rdi
0x1800044bb  push    r12
0x1800044bd  push    r13
0x1800044bf  push    r14
0x1800044c1  push    r15
0x1800044c3  sub     rsp, 48h
0x1800044c7  xor     r15d, r15d
0x1800044ca  mov     r13d, edx
0x1800044cd  mov     [rax+18h], r15
0x1800044d1  mov     r12, rcx
0x1800044d4  cmp     edx, 5
0x1800044d7  jbe     short loc_1800044E2
0x1800044d9  lea     eax, [r15+1]
0x1800044dd  jmp     loc_180004682
0x1800044e2  mov     rcx, cs:ghTapisrvHeap; hHeap
0x1800044e9  mov     edx, 8; dwFlags
0x1800044ee  mov     r8d, 1000h; dwBytes
0x1800044f4  call    cs:__imp_HeapAlloc
0x1800044fa  xor     r9d, r9d
0x1800044fd  mov     rdi, rax
0x180004500  test    rax, rax
0x180004503  jz      loc_180004682
0x180004509  mov     r14d, 800h
0x18000450f  mov     esi, r9d
0x180004512  mov     ebp, r9d
0x180004515  mov     ebx, 1
0x18000451a  mov     eax, r14d
0x18000451d  mov     qword ptr [rsp+88h+ftLastWriteTime.dwLowDateTime], r9
0x180004525  sub     eax, esi
0x180004527  mov     [rsp+88h+cchName], eax
0x18000452e  cmp     eax, 100h
0x180004533  jnb     short loc_180004582
0x180004535  add     r14d, r14d
0x180004538  mov     ecx, 40h ; '@'; uFlags
0x18000453d  mov     edx, r14d
0x180004540  add     rdx, rdx; uBytes
0x180004543  call    cs:__imp_LocalAlloc
0x180004549  xor     r15d, r15d
0x18000454c  mov     r12, rax
0x18000454f  test    rax, rax
0x180004552  jz      loc_1800045EF
0x180004558  mov     r15d, esi
0x18000455b  mov     rdx, rdi; Src
0x18000455e  mov     rcx, rax; void *
0x180004561  lea     r8, [r15+r15]; Size
0x180004565  call    memcpy_0
0x18000456a  mov     rcx, rdi; lpMem
0x18000456d  call    ServerFree
0x180004572  mov     rdi, r12
0x180004575  xor     r9d, r9d
0x180004578  mov     r12, [rsp+88h+hKey]
0x180004580  jmp     short loc_180004585
0x180004582  mov     r15d, esi
0x180004585  lea     rax, [rsp+88h+ftLastWriteTime]
0x18000458d  mov     edx, ebp; dwIndex
0x18000458f  mov     [rsp+88h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180004594  lea     r15, [rdi+r15*2]
0x180004598  mov     [rsp+88h+lpcchClass], r9; lpcchClass
0x18000459d  mov     r8, r15; lpName
0x1800045a0  mov     [rsp+88h+lpClass], r9; lpClass
0x1800045a5  mov     rcx, r12; hKey
0x1800045a8  mov     [rsp+88h+lpReserved], r9; lpReserved
0x1800045ad  lea     r9, [rsp+88h+cchName]; lpcchName
0x1800045b5  call    cs:__imp_RegEnumKeyExW
0x1800045bb  xor     r9d, r9d
0x1800045be  test    eax, eax
0x1800045c0  jnz     short loc_1800045F7
0x1800045c2  mov     edx, [rsp+88h+cchName]
0x1800045c9  lea     r8d, [rdx+rsi]
0x1800045cd  lea     eax, [r8-1]
0x1800045d1  cmp     [rdi+rax*2], r9w
0x1800045d6  jz      short loc_1800045E6
0x1800045d8  mov     [rdi+r8*2], r9w
0x1800045dd  mov     edx, [rsp+88h+cchName]
0x1800045e4  add     edx, ebx
0x1800045e6  add     esi, edx
0x1800045e8  add     ebp, ebx
0x1800045ea  jmp     loc_18000451A
0x1800045ef  mov     ebx, r15d
0x1800045f2  jmp     loc_180004678
0x1800045f7  mov     [r15], r9w
0x1800045fb  mov     rsi, rdi
0x1800045fe  cmp     [rdi], r9w
0x180004602  jz      short loc_180004678
0x180004604  xor     r15d, r15d
0x180004607  lea     rax, [rsp+88h+phkResult]
0x18000460f  mov     r9d, 0F003Fh; samDesired
0x180004615  xor     r8d, r8d; ulOptions
0x180004618  mov     [rsp+88h+lpReserved], rax; phkResult
0x18000461d  mov     rdx, rsi; lpSubKey
0x180004620  mov     rcx, r12; hKey
0x180004623  call    cs:__imp_RegOpenKeyExW
0x180004629  test    eax, eax
0x18000462b  jnz     short loc_18000464C
0x18000462d  mov     rcx, [rsp+88h+phkResult]
0x180004635  lea     edx, [r13+1]
0x180004639  call    DeleteAllSubkeys
0x18000463e  mov     rcx, [rsp+88h+phkResult]; hKey
0x180004646  call    cs:__imp_RegCloseKey
0x18000464c  xor     r9d, r9d; Reserved
0x18000464f  xor     r8d, r8d; samDesired
0x180004652  mov     rdx, rsi; lpSubKey
0x180004655  mov     rcx, r12; hKey
0x180004658  call    cs:__imp_RegDeleteKeyExW
0x18000465e  mov     rcx, rsi; lpString
0x180004661  call    cs:__imp_lstrlenW
0x180004667  movsxd  rcx, eax
0x18000466a  lea     rsi, [rsi+rcx*2]
0x18000466e  add     rsi, 2
0x180004672  cmp     [rsi], r15w
0x180004676  jnz     short loc_180004607
0x180004678  mov     rcx, rdi; lpMem
0x18000467b  call    ServerFree
0x180004680  mov     eax, ebx
0x180004682  add     rsp, 48h
0x180004686  pop     r15
0x180004688  pop     r14
0x18000468a  pop     r13
0x18000468c  pop     r12
0x18000468e  pop     rdi
0x18000468f  pop     rsi
0x180004690  pop     rbp
0x180004691  pop     rbx
0x180004692  retn
```
