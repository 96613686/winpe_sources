# LoadSystem32LibraryA

- ea: `0x18002909c`
- end: `0x1800292a3`
- name: `LoadSystem32LibraryA`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002e24c`

## callees

- `0x1800037a8`
- `0x18000b440`
- `0x18002909c`
- `0x1800292ac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180029188`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180029188`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800290bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800290bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x18002911a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x18002911a`

## string_xrefs

- `0x18002916d`: `WS2_32.DLL`
- `0x18002924c`: `LoadSystem32LibraryA couldn't allocate 0x%x bytes.\n`
- `0x180029292`: `LoadSystem32LibraryA: GetSystemDirectory failed, error = 0x%x.\n`

## pseudocode

```c
HMODULE LoadSystem32LibraryA()
{
  HMODULE Library; // rdi
  CHAR *v1; // rax
  int v2; // ecx
  CHAR *v3; // rbx
  unsigned int v4; // eax
  UINT SystemDirectoryA; // r8d

  Library = 0;
  v1 = (CHAR *)HeapAlloc(LdapHeap, 8u, 0x119u);
  v2 = g_fTracingOn;
  v3 = v1;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
  {
    LDAPClientPrint(8, "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n", 281, (_DWORD)v1, 1936605516);
    v2 = g_fTracingOn;
  }
  v4 = LdapAllocatedHeap;
  if ( v3 )
  {
    *(_DWORD *)v3 = 1936605516;
    *((_DWORD *)v3 + 1) = 273;
    v3 += 8;
    v4 += 273;
    LdapAllocatedHeap = v4;
  }
  if ( v2 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
  {
    LDAPClientPrint(8, "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n", 273, (_DWORD)v3, 1936605516, v4);
    v2 = g_fTracingOn;
  }
  if ( v3 )
  {
    SystemDirectoryA = GetSystemDirectoryA(v3, 0x105u);
    if ( SystemDirectoryA - 1 <= 0x104 )
    {
      if ( v3[SystemDirectoryA - 1] != 92 )
        StringCchCatA(v3, 0x111u, "\\");
      StringCchCatA(v3, 0x111u, "WS2_32.DLL");
      Library = LoadLibraryExA(v3, 0, 8u);
    }
    else if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
    {
      LDAPClientPrint(0x10000000, "LoadSystem32LibraryA: GetSystemDirectory failed, error = 0x%x.\n", SystemDirectoryA);
    }
    ldapFree(v3, 1936605516);
  }
  else if ( v2 && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
  {
    LDAPClientPrint(0x10000000, "LoadSystem32LibraryA couldn't allocate 0x%x bytes.\n", 273);
  }
  return Library;
}

```

## disassembly

```asm
0x18002909c  mov     [rsp+arg_0], rbx
0x1800290a1  mov     [rsp+arg_8], rbp
0x1800290a6  push    rdi
0x1800290a7  sub     rsp, 30h
0x1800290ab  mov     rcx, cs:LdapHeap; hHeap
0x1800290b2  xor     edi, edi
0x1800290b4  mov     ebp, 119h
0x1800290b9  mov     r8d, ebp; dwBytes
0x1800290bc  lea     edx, [rdi+8]; dwFlags
0x1800290bf  call    cs:__imp_HeapAlloc
0x1800290c6  nop     dword ptr [rax+rax+00h]
0x1800290cb  mov     ecx, cs:g_fTracingOn
0x1800290d1  mov     rbx, rax
0x1800290d4  test    ecx, ecx
0x1800290d6  jnz     loc_180029199
0x1800290dc  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x1800290e2  mov     ebp, 111h
0x1800290e7  test    rbx, rbx
0x1800290ea  jz      short loc_180029101
0x1800290ec  mov     dword ptr [rbx], 736E414Ch
0x1800290f2  mov     [rbx+4], ebp
0x1800290f5  add     rbx, 8
0x1800290f9  add     eax, ebp
0x1800290fb  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x180029101  test    ecx, ecx
0x180029103  jnz     loc_1800291DC
0x180029109  test    rbx, rbx
0x18002910c  jz      loc_180029223
0x180029112  mov     edx, 105h; uSize
0x180029117  mov     rcx, rbx; lpBuffer
0x18002911a  call    cs:__imp_GetSystemDirectoryA
0x180029121  nop     dword ptr [rax+rax+00h]
0x180029126  mov     r8d, eax
0x180029129  dec     eax
0x18002912b  cmp     eax, 104h
0x180029130  jbe     short loc_18002915F
0x180029132  cmp     cs:g_fTracingOn, edi
0x180029138  jnz     loc_180029274
0x18002913e  mov     edx, 736E414Ch
0x180029143  mov     rcx, rbx
0x180029146  call    ldapFree
0x18002914b  mov     rbx, [rsp+38h+arg_0]
0x180029150  mov     rax, rdi
0x180029153  mov     rbp, [rsp+38h+arg_8]
0x180029158  add     rsp, 30h
0x18002915c  pop     rdi
0x18002915d  retn
0x18002915f  lea     eax, [r8-1]
0x180029163  cmp     byte ptr [rax+rbx], 5Ch ; '\'
0x180029167  jnz     loc_18002925D
0x18002916d  lea     r8, pszSrc; "WS2_32.DLL"
0x180029174  mov     rdx, rbp; cchDest
0x180029177  mov     rcx, rbx; pszDest
0x18002917a  call    StringCchCatA
0x18002917f  xor     edx, edx; hFile
0x180029181  mov     rcx, rbx; lpLibFileName
0x180029184  lea     r8d, [rdx+8]; dwFlags
0x180029188  call    cs:__imp_LoadLibraryExA
0x18002918f  nop     dword ptr [rax+rax+00h]
0x180029194  mov     rdi, rax
0x180029197  jmp     short loc_18002913E
0x180029199  cmp     cs:g_fProviderEnabled, edi
0x18002919f  jz      loc_1800290DC
0x1800291a5  test    byte ptr cs:g_ulTraceFlags, 8
0x1800291ac  jz      loc_1800290DC
0x1800291b2  mov     r9, rbx
0x1800291b5  mov     [rsp+38h+var_18], 736E414Ch
0x1800291bd  mov     r8d, ebp
0x1800291c0  lea     rdx, aLdapmallocAllo; "ldapMalloc allocated 0x%x bytes at addr"...
0x1800291c7  mov     ecx, 8
0x1800291cc  call    LDAPClientPrint
0x1800291d1  mov     ecx, cs:g_fTracingOn
0x1800291d7  jmp     loc_1800290DC
0x1800291dc  cmp     cs:g_fProviderEnabled, edi
0x1800291e2  jz      loc_180029109
0x1800291e8  test    byte ptr cs:g_ulTraceFlags, 8
0x1800291ef  jz      loc_180029109
0x1800291f5  mov     [rsp+38h+var_10], eax
0x1800291f9  lea     rdx, aLdapmalloc0x08; "ldapMalloc 0x%08x bytes at address 0x%x"...
0x180029200  mov     r9, rbx
0x180029203  mov     [rsp+38h+var_18], 736E414Ch
0x18002920b  mov     r8d, ebp
0x18002920e  mov     ecx, 8
0x180029213  call    LDAPClientPrint
0x180029218  mov     ecx, cs:g_fTracingOn
0x18002921e  jmp     loc_180029109
0x180029223  test    ecx, ecx
0x180029225  jz      loc_18002914B
0x18002922b  cmp     cs:g_fProviderEnabled, edi
0x180029231  jz      loc_18002914B
0x180029237  mov     ecx, 10000000h
0x18002923c  test    cs:g_ulTraceFlags, rcx
0x180029243  jz      loc_18002914B
0x180029249  mov     r8d, ebp
0x18002924c  lea     rdx, aLoadsystem32li_0; "LoadSystem32LibraryA couldn't allocate "...
0x180029253  call    LDAPClientPrint
0x180029258  jmp     loc_18002914B
0x18002925d  lea     r8, asc_18005C5EC; "\\"
0x180029264  mov     rdx, rbp; cchDest
0x180029267  mov     rcx, rbx; pszDest
0x18002926a  call    StringCchCatA
0x18002926f  jmp     loc_18002916D
0x180029274  cmp     cs:g_fProviderEnabled, edi
0x18002927a  jz      loc_18002913E
0x180029280  mov     ecx, 10000000h
0x180029285  test    cs:g_ulTraceFlags, rcx
0x18002928c  jz      loc_18002913E
0x180029292  lea     rdx, aLoadsystem32li; "LoadSystem32LibraryA: GetSystemDirector"...
0x180029299  call    LDAPClientPrint
0x18002929e  jmp     loc_18002913E
```
