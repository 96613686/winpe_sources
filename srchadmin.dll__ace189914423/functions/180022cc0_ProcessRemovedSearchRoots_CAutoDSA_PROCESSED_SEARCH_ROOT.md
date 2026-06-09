# ProcessRemovedSearchRoots(CAutoDSA<PROCESSED_SEARCH_ROOT> *)

- ea: `0x180022cc0`
- end: `0x180022df7`
- name: `?ProcessRemovedSearchRoots@@YAXPEAV?$CAutoDSA@UPROCESSED_SEARCH_ROOT@@@@@Z`
- size: `311`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022840`
- `0x180022aa0`

## callees

- `0x18002195c`
- `0x180022cc0`
- `0x180022e44`
- `0x180022f50`
- `0x18002ff1c`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180022d47`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180022d47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022cfe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022d86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022cfe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022d86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022dbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022de0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022dbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022de0`

## pseudocode

```c
LSTATUS __fastcall ProcessRemovedSearchRoots(HDSA *a1)
{
  LSTATUS result; // eax
  int v3; // esi
  int i; // edi
  const unsigned __int16 **ItemPtr; // rax
  const unsigned __int16 **v6; // r15
  const unsigned __int16 *v7; // rbx
  int v8; // eax
  const WCHAR *v9; // rdx
  HKEY phkResult; // [rsp+68h] [rbp+38h] BYREF
  struct CAddRemoveSynchronizer *v11; // [rsp+70h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  hKey = 0;
  result = RegOpenKeyExW(
             HKEY_CURRENT_USER,
             L"SOFTWARE\\Microsoft\\Windows Search\\ProcessedSearchRoots",
             0,
             0x20019u,
             &hKey);
  if ( !result )
  {
    if ( *a1 )
    {
      v3 = *(_DWORD *)*a1;
      for ( i = 0; i < v3; ++i )
      {
        ItemPtr = (const unsigned __int16 **)DSA_GetItemPtr(*a1, i);
        v11 = 0;
        v6 = ItemPtr;
        v7 = ItemPtr[1];
        v8 = wcstol(ItemPtr[2], 0, 10);
        if ( (int)CAddRemoveSynchronizer::Create(v8, 1, v7, (IUnknown **)&v11) >= 0 )
        {
          v9 = v6[2];
          phkResult = 0;
          if ( !RegOpenKeyExW(hKey, v9, 0, 2u, &phkResult) )
          {
            if ( !(unsigned int)RegSetDWORDValue(phkResult, L"Removing", 1u) )
              QueueWorkItem(
                (void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *))RemoveLocationsForSearchRootWorker,
                v11);
            RegCloseKey(phkResult);
          }
          (*(void (__fastcall **)(struct CAddRemoveSynchronizer *))(*(_QWORD *)v11 + 16LL))(v11);
        }
      }
    }
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x180022cc0  mov     [rsp-28h+arg_0], rbx
0x180022cc5  push    rbp
0x180022cc6  push    rsi
0x180022cc7  push    rdi
0x180022cc8  push    r14
0x180022cca  push    r15
0x180022ccc  mov     rbp, rsp
0x180022ccf  sub     rsp, 30h
0x180022cd3  mov     r14, rcx
0x180022cd6  mov     [rbp+hKey], 0
0x180022cde  lea     rax, [rbp+hKey]
0x180022ce2  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180022ce9  mov     r9d, 20019h; samDesired
0x180022cef  mov     [rsp+30h+phkResult], rax; phkResult
0x180022cf4  xor     r8d, r8d; ulOptions
0x180022cf7  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows Search\\Pr"...
0x180022cfe  call    cs:__imp_RegOpenKeyExW
0x180022d04  test    eax, eax
0x180022d06  jnz     loc_180022DE6
0x180022d0c  mov     rax, [r14]
0x180022d0f  test    rax, rax
0x180022d12  jz      loc_180022DDC
0x180022d18  mov     esi, [rax]
0x180022d1a  xor     edi, edi
0x180022d1c  test    esi, esi
0x180022d1e  jle     loc_180022DDC
0x180022d24  mov     rcx, [r14]; hdsa
0x180022d27  mov     edx, edi; i
0x180022d29  call    DSA_GetItemPtr
0x180022d2e  mov     [rbp+arg_10], 0
0x180022d36  xor     edx, edx; EndPtr
0x180022d38  mov     r15, rax
0x180022d3b  mov     rcx, [rax+10h]; String
0x180022d3f  mov     rbx, [rax+8]
0x180022d43  lea     r8d, [rdx+0Ah]; Radix
0x180022d47  call    cs:__imp_wcstol
0x180022d4d  lea     r9, [rbp+arg_10]; struct CAddRemoveSynchronizer **
0x180022d51  mov     r8, rbx; unsigned __int16 *
0x180022d54  mov     ecx, eax; int
0x180022d56  mov     edx, 1; int
0x180022d5b  call    ?Create@CAddRemoveSynchronizer@@SAJHHPEBGPEAPEAV1@@Z; CAddRemoveSynchronizer::Create(int,int,ushort const *,CAddRemoveSynchronizer * *)
0x180022d60  test    eax, eax
0x180022d62  js      short loc_180022DD2
0x180022d64  mov     rdx, [r15+10h]; lpSubKey
0x180022d68  lea     rax, [rbp+arg_8]
0x180022d6c  mov     rcx, [rbp+hKey]; hKey
0x180022d70  mov     r9d, 2; samDesired
0x180022d76  xor     r8d, r8d; ulOptions
0x180022d79  mov     [rsp+30h+phkResult], rax; phkResult
0x180022d7e  mov     [rbp+arg_8], 0
0x180022d86  call    cs:__imp_RegOpenKeyExW
0x180022d8c  test    eax, eax
0x180022d8e  jnz     short loc_180022DC2
0x180022d90  mov     rcx, [rbp+arg_8]; HKEY
0x180022d94  lea     r8d, [rax+1]; unsigned int
0x180022d98  lea     rdx, aRemoving; "Removing"
0x180022d9f  call    ?RegSetDWORDValue@@YAJPEAUHKEY__@@PEBGK@Z; RegSetDWORDValue(HKEY__ *,ushort const *,ulong)
0x180022da4  test    eax, eax
0x180022da6  jnz     short loc_180022DB8
0x180022da8  mov     rdx, [rbp+arg_10]; struct CAddRemoveSynchronizer *
0x180022dac  lea     rcx, ?RemoveLocationsForSearchRootWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)
0x180022db3  call    ?QueueWorkItem@@YAXP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@ZPEAVCAddRemoveSynchronizer@@@Z; QueueWorkItem(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),CAddRemoveSynchronizer *)
0x180022db8  mov     rcx, [rbp+arg_8]; hKey
0x180022dbc  call    cs:__imp_RegCloseKey
0x180022dc2  mov     rcx, [rbp+arg_10]
0x180022dc6  mov     rax, [rcx]
0x180022dc9  mov     rax, [rax+10h]
0x180022dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022dd2  inc     edi
0x180022dd4  cmp     edi, esi
0x180022dd6  jl      loc_180022D24
0x180022ddc  mov     rcx, [rbp+hKey]; hKey
0x180022de0  call    cs:__imp_RegCloseKey
0x180022de6  mov     rbx, [rsp+30h+arg_0]
0x180022deb  add     rsp, 30h
0x180022def  pop     r15
0x180022df1  pop     r14
0x180022df3  pop     rdi
0x180022df4  pop     rsi
0x180022df5  pop     rbp
0x180022df6  retn
```
