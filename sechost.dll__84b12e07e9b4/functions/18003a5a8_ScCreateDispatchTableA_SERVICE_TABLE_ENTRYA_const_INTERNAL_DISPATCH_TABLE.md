# ScCreateDispatchTableA(_SERVICE_TABLE_ENTRYA const *,_INTERNAL_DISPATCH_TABLE * *)

- ea: `0x18003a5a8`
- end: `0x18003a75c`
- name: `?ScCreateDispatchTableA@@YAKPEBU_SERVICE_TABLE_ENTRYA@@PEAPEAU_INTERNAL_DISPATCH_TABLE@@@Z`
- size: `436`
- prototype: `unsigned int __fastcall(const struct _SERVICE_TABLE_ENTRYA *, struct _INTERNAL_DISPATCH_TABLE **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18003aa70`

## callees

- `0x18000c870`
- `0x1800198d8`
- `0x18003a5a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003a651`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003a651`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a6ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a6ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a5ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a5ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a6b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a6c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a6de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a6b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a6c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a6de`

## string_xrefs

- `0x18003a643`: `System\CurrentControlSet\Services`

## pseudocode

```c
__int64 __fastcall ScCreateDispatchTableA(const struct _SERVICE_TABLE_ENTRYA *a1, struct _INTERNAL_DISPATCH_TABLE **a2)
{
  const struct _SERVICE_TABLE_ENTRYA *v2; // rsi
  int i; // eax
  _DWORD *v5; // rax
  unsigned int v6; // r14d
  _DWORD *v7; // rdi
  HKEY v8; // rcx
  HLOCAL v9; // rcx
  HLOCAL *v10; // rdi
  HLOCAL v11; // rcx
  unsigned __int16 *v12; // rdx
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF
  _DWORD *v14; // [rsp+70h] [rbp+18h]

  v2 = a1;
  hKey = 0;
  for ( i = 0; a1->lpServiceName; ++a1 )
    ++i;
  if ( !i )
    return 87;
  v5 = LocalAlloc(0x40u, 96LL * (unsigned int)(i + 1) + 8);
  if ( !v5 )
    return 8;
  v6 = 0;
  *v5 = 875651923;
  hMem = v5;
  v7 = v5 + 2;
  v14 = v5 + 2;
  RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services", 0, 0x20019u, &hKey);
  v8 = hKey;
  while ( v2->lpServiceName )
  {
    *v7 = 892429139;
    if ( !ScConvertToUnicode((unsigned __int16 **)v7 + 1, v2->lpServiceName) )
      v6 = 8;
    if ( v6 )
    {
      v9 = hMem;
      v10 = (HLOCAL *)((char *)hMem + 8);
      if ( *((_QWORD *)hMem + 2) )
      {
        do
        {
          LocalFree(v10[1]);
          v11 = v10[3];
          if ( v11 )
            LocalFree(v11);
          v10 += 12;
        }
        while ( v10[1] );
        v9 = hMem;
      }
      LocalFree(v9);
      v8 = hKey;
      break;
    }
    v12 = (unsigned __int16 *)*((_QWORD *)v7 + 1);
    *((_QWORD *)v7 + 2) = v12;
    *((_QWORD *)v7 + 4) = v2->lpServiceProc;
    *((_QWORD *)v7 + 5) = 0;
    *((_QWORD *)v7 + 6) = 0;
    v7[14] = 0;
    v8 = hKey;
    if ( hKey )
    {
      ScReadServiceAliasFromRegistry(hKey, v12, (unsigned __int16 **)v7 + 3);
      v8 = hKey;
    }
    ++v2;
    v7 += 24;
    v14 = v7;
  }
  if ( v8 )
    RegCloseKey(v8);
  return v6;
}

```

## disassembly

```asm
0x18003a5a8  mov     [rsp+arg_18], rsi
0x18003a5ad  mov     [rsp+hKey], rdx
0x18003a5b2  push    rdi
0x18003a5b3  push    r14
0x18003a5b5  push    r15
0x18003a5b7  sub     rsp, 40h
0x18003a5bb  mov     rsi, rcx
0x18003a5be  mov     [rsp+58h+hKey], 0
0x18003a5c7  xor     eax, eax
0x18003a5c9  cmp     [rcx], rax
0x18003a5cc  jz      short loc_18003A5DA
0x18003a5ce  inc     eax
0x18003a5d0  lea     rcx, [rcx+10h]
0x18003a5d4  cmp     qword ptr [rcx], 0
0x18003a5d8  jnz     short loc_18003A5CE
0x18003a5da  test    eax, eax
0x18003a5dc  jnz     short loc_18003A5E8
0x18003a5de  mov     eax, 57h ; 'W'
0x18003a5e3  jmp     loc_18003A6F7
0x18003a5e8  inc     eax
0x18003a5ea  lea     rdx, [rax+rax*2]
0x18003a5ee  shl     rdx, 5
0x18003a5f2  mov     r15d, 8
0x18003a5f8  add     rdx, r15; uBytes
0x18003a5fb  lea     ecx, [r15+38h]; uFlags
0x18003a5ff  call    cs:__imp_LocalAlloc
0x18003a605  test    rax, rax
0x18003a608  jnz     short loc_18003A612
0x18003a60a  mov     eax, r15d
0x18003a60d  jmp     loc_18003A6F7
0x18003a612  xor     r14d, r14d
0x18003a615  mov     dword ptr [rax], 34316353h
0x18003a61b  mov     cs:hMem, rax
0x18003a622  mov     [rsp+58h+arg_0], rsi
0x18003a627  lea     rdi, [rax+8]
0x18003a62b  mov     [rsp+58h+arg_10], rdi
0x18003a630  lea     rax, [rsp+58h+hKey]
0x18003a635  mov     [rsp+58h+phkResult], rax; phkResult
0x18003a63a  mov     r9d, 20019h; samDesired
0x18003a640  xor     r8d, r8d; ulOptions
0x18003a643  lea     rdx, SubKey; "System\\CurrentControlSet\\Services"
0x18003a64a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003a651  call    cs:__imp_RegOpenKeyExA
0x18003a657  mov     rcx, [rsp+58h+hKey]
0x18003a65c  cmp     qword ptr [rsi], 0
0x18003a660  jz      loc_18003A6E9
0x18003a666  mov     dword ptr [rdi], 35316353h
0x18003a66c  lea     rcx, [rdi+8]; unsigned __int16 **
0x18003a670  mov     rdx, [rsi]; char *
0x18003a673  call    ?ScConvertToUnicode@@YAHPEAPEAGPEBD@Z; ScConvertToUnicode(ushort * *,char const *)
0x18003a678  test    eax, eax
0x18003a67a  cmovz   r14d, r15d
0x18003a67e  mov     [rsp+58h+var_28], r14d
0x18003a683  jmp     short loc_18003A69C
0x18003a685  mov     r14d, eax
0x18003a688  mov     [rsp+58h+var_28], eax
0x18003a68c  mov     r15d, 8
0x18003a692  mov     rdi, [rsp+58h+arg_10]
0x18003a697  mov     rsi, [rsp+58h+arg_0]
0x18003a69c  test    r14d, r14d
0x18003a69f  jz      short loc_18003A706
0x18003a6a1  mov     rcx, cs:hMem
0x18003a6a8  lea     rdi, [rcx+8]
0x18003a6ac  cmp     qword ptr [rdi+8], 0
0x18003a6b1  jz      short loc_18003A6DE
0x18003a6b3  mov     rcx, [rdi+8]; hMem
0x18003a6b7  call    cs:__imp_LocalFree
0x18003a6bd  mov     rcx, [rdi+18h]; hMem
0x18003a6c1  test    rcx, rcx
0x18003a6c4  jz      short loc_18003A6CC
0x18003a6c6  call    cs:__imp_LocalFree
0x18003a6cc  add     rdi, 60h ; '`'
0x18003a6d0  cmp     qword ptr [rdi+8], 0
0x18003a6d5  jnz     short loc_18003A6B3
0x18003a6d7  mov     rcx, cs:hMem; hMem
0x18003a6de  call    cs:__imp_LocalFree
0x18003a6e4  mov     rcx, [rsp+58h+hKey]; hKey
0x18003a6e9  test    rcx, rcx
0x18003a6ec  jz      short loc_18003A6F4
0x18003a6ee  call    cs:__imp_RegCloseKey
0x18003a6f4  mov     eax, r14d
0x18003a6f7  mov     rsi, [rsp+58h+arg_18]
0x18003a6fc  add     rsp, 40h
0x18003a700  pop     r15
0x18003a702  pop     r14
0x18003a704  pop     rdi
0x18003a705  retn
0x18003a706  mov     rdx, [rdi+8]; unsigned __int16 *
0x18003a70a  mov     [rdi+10h], rdx
0x18003a70e  mov     rax, [rsi+8]
0x18003a712  mov     [rdi+20h], rax
0x18003a716  mov     qword ptr [rdi+28h], 0
0x18003a71e  mov     qword ptr [rdi+30h], 0
0x18003a726  mov     dword ptr [rdi+38h], 0
0x18003a72d  mov     rcx, [rsp+58h+hKey]; HKEY
0x18003a732  test    rcx, rcx
0x18003a735  jz      short loc_18003A745
0x18003a737  lea     r8, [rdi+18h]; unsigned __int16 **
0x18003a73b  call    ?ScReadServiceAliasFromRegistry@@YAKPEAUHKEY__@@PEAGPEAPEAG@Z; ScReadServiceAliasFromRegistry(HKEY__ *,ushort *,ushort * *)
0x18003a740  mov     rcx, [rsp+58h+hKey]
0x18003a745  add     rsi, 10h
0x18003a749  mov     [rsp+58h+arg_0], rsi
0x18003a74e  add     rdi, 60h ; '`'
0x18003a752  mov     [rsp+58h+arg_10], rdi
0x18003a757  jmp     loc_18003A65C
```
