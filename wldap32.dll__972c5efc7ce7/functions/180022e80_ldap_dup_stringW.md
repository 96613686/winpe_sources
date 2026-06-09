# ldap_dup_stringW

- ea: `0x180022e80`
- end: `0x180022fdb`
- name: `ldap_dup_stringW`
- size: `347`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `33`
- callee_count: `3`
- tags: ``

## callers

- `0x1800057a0`
- `0x18000ce40`
- `0x18001b0d4`
- `0x18001f96c`
- `0x180020990`
- `0x180021454`
- `0x18002227c`
- `0x1800224cc`
- `0x1800227d8`
- `0x180022a60`
- `0x18002376c`
- `0x1800245ec`
- `0x180026b50`
- `0x18002abe0`
- `0x18002b5fc`
- `0x18002c04c`
- `0x18002ca68`
- `0x18002e6d4`
- `0x1800314a8`
- `0x1800334bc`
- `0x180039f4c`
- `0x18003c254`
- `0x18003e250`
- `0x18003edf4`
- `0x180040440`
- `0x180041030`
- `0x1800416d0`
- `0x1800434f0`
- `0x18004404c`
- `0x180046f48`
- `0x18004a984`
- `0x18004af90`
- `0x18004c440`

## callees

- `0x1800037a8`
- `0x180022e80`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022f04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022f04`

## pseudocode

```c
_DWORD *__fastcall ldap_dup_stringW(_WORD *Src, int a2, int a3)
{
  _WORD *v5; // r9
  unsigned int v6; // ebx
  unsigned __int64 v8; // rsi
  unsigned int v9; // ebp
  _DWORD *v10; // rdi
  int v11; // ecx
  unsigned int v12; // eax

  if ( !Src )
    return 0;
  v5 = Src;
  v6 = 1;
  while ( *v5 )
  {
    if ( v6 + 1 < v6 )
      return 0;
    ++v6;
    ++v5;
  }
  if ( v6 + a2 < v6 )
    return 0;
  v8 = 2LL * (v6 + a2);
  if ( v8 > 0xFFFFFFFF )
    return 0;
  v9 = v8 + 8;
  if ( (int)v8 + 8 < (unsigned int)v8 )
  {
    v10 = 0;
    v9 = -1;
  }
  else
  {
    v10 = HeapAlloc(LdapHeap, 8u, v9);
  }
  v11 = g_fTracingOn;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
  {
    LDAPClientPrint(8, "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n", v9, (_DWORD)v10, a3);
    v11 = g_fTracingOn;
  }
  v12 = LdapAllocatedHeap;
  if ( v10 )
  {
    *v10 = a3;
    v10[1] = v8;
    v10 += 2;
    v12 += v8;
    LdapAllocatedHeap = v12;
  }
  if ( v11 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
    LDAPClientPrint(8, "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n", v8, (_DWORD)v10, a3, v12);
  if ( !v10 )
    return 0;
  memcpy_0(v10, Src, 2LL * v6);
  return v10;
}

```

## disassembly

```asm
0x180022e80  mov     [rsp+arg_8], rbx
0x180022e85  mov     [rsp+arg_10], rsi
0x180022e8a  push    rdi
0x180022e8b  push    r14
0x180022e8d  push    r15
0x180022e8f  sub     rsp, 30h
0x180022e93  mov     r15d, r8d
0x180022e96  mov     r14, rcx
0x180022e99  test    rcx, rcx
0x180022e9c  jz      short loc_180022EBC
0x180022e9e  mov     r9, rcx
0x180022ea1  mov     ebx, 1
0x180022ea6  cmp     word ptr [r9], 0
0x180022eab  jz      short loc_180022ED3
0x180022ead  lea     eax, [rbx+1]
0x180022eb0  cmp     eax, ebx
0x180022eb2  jb      short loc_180022EBC
0x180022eb4  mov     ebx, eax
0x180022eb6  add     r9, 2
0x180022eba  jmp     short loc_180022EA6
0x180022ebc  xor     eax, eax
0x180022ebe  mov     rbx, [rsp+48h+arg_8]
0x180022ec3  mov     rsi, [rsp+48h+arg_10]
0x180022ec8  add     rsp, 30h
0x180022ecc  pop     r15
0x180022ece  pop     r14
0x180022ed0  pop     rdi
0x180022ed1  retn
0x180022ed3  lea     eax, [rbx+rdx]
0x180022ed6  cmp     eax, ebx
0x180022ed8  jb      short loc_180022EBC
0x180022eda  mov     esi, eax
0x180022edc  mov     eax, 0FFFFFFFFh
0x180022ee1  add     rsi, rsi
0x180022ee4  cmp     rsi, rax
0x180022ee7  ja      short loc_180022EBC
0x180022ee9  mov     [rsp+48h+arg_0], rbp
0x180022eee  lea     ebp, [rsi+8]
0x180022ef1  cmp     ebp, esi
0x180022ef3  jb      short loc_180022F65
0x180022ef5  mov     rcx, cs:LdapHeap; hHeap
0x180022efc  mov     edx, 8; dwFlags
0x180022f01  mov     r8d, ebp; dwBytes
0x180022f04  call    cs:__imp_HeapAlloc
0x180022f0b  nop     dword ptr [rax+rax+00h]
0x180022f10  mov     rdi, rax
0x180022f13  mov     ecx, cs:g_fTracingOn
0x180022f19  test    ecx, ecx
0x180022f1b  jnz     short loc_180022F6B
0x180022f1d  mov     rbp, [rsp+48h+arg_0]
0x180022f22  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x180022f28  test    rdi, rdi
0x180022f2b  jz      short loc_180022F3F
0x180022f2d  mov     [rdi], r15d
0x180022f30  mov     [rdi+4], esi
0x180022f33  add     rdi, 8
0x180022f37  add     eax, esi
0x180022f39  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x180022f3f  test    ecx, ecx
0x180022f41  jnz     short loc_180022FA4
0x180022f43  test    rdi, rdi
0x180022f46  jz      loc_180022EBC
0x180022f4c  mov     r8d, ebx
0x180022f4f  mov     rdx, r14; Src
0x180022f52  add     r8, r8; Size
0x180022f55  mov     rcx, rdi; void *
0x180022f58  call    memcpy_0
0x180022f5d  mov     rax, rdi
0x180022f60  jmp     loc_180022EBE
0x180022f65  xor     edi, edi
0x180022f67  mov     ebp, eax
0x180022f69  jmp     short loc_180022F13
0x180022f6b  cmp     cs:g_fProviderEnabled, 0
0x180022f72  jz      short loc_180022F1D
0x180022f74  test    byte ptr cs:g_ulTraceFlags, 8
0x180022f7b  jz      short loc_180022F1D
0x180022f7d  mov     r9, rdi
0x180022f80  mov     [rsp+48h+var_28], r15d
0x180022f85  mov     r8d, ebp
0x180022f88  lea     rdx, aLdapmallocAllo; "ldapMalloc allocated 0x%x bytes at addr"...
0x180022f8f  mov     ecx, 8
0x180022f94  call    LDAPClientPrint
0x180022f99  mov     ecx, cs:g_fTracingOn
0x180022f9f  jmp     loc_180022F1D
0x180022fa4  cmp     cs:g_fProviderEnabled, 0
0x180022fab  jz      short loc_180022F43
0x180022fad  test    byte ptr cs:g_ulTraceFlags, 8
0x180022fb4  jz      short loc_180022F43
0x180022fb6  mov     [rsp+48h+var_20], eax
0x180022fba  lea     rdx, aLdapmalloc0x08; "ldapMalloc 0x%08x bytes at address 0x%x"...
0x180022fc1  mov     r9, rdi
0x180022fc4  mov     [rsp+48h+var_28], r15d
0x180022fc9  mov     r8d, esi
0x180022fcc  mov     ecx, 8
0x180022fd1  call    LDAPClientPrint
0x180022fd6  jmp     loc_180022F43
```
