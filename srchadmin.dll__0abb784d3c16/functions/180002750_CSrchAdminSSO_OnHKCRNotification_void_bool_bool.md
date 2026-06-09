# CSrchAdminSSO::_OnHKCRNotification(void *,bool,bool &)

- ea: `0x180002750`
- end: `0x1800028f6`
- name: `?_OnHKCRNotification@CSrchAdminSSO@@AEAAJPEAX_NAEA_N@Z`
- size: `422`
- prototype: `__int64 __fastcall(CSrchAdminSSO *this, void *, char, bool *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180002750`
- `0x18002e590`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000276b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000276b`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180002789`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180002789`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800027b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800027ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002845`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002884`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800027b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800027ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002845`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002884`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800027ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002810`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002856`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002895`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800027ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002810`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002856`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002895`
- `api-ms-win-winrt-search-folder-l1-1-0!IsMSSearchEnabled` at `0x1800028d0`
- `api-ms-win-winrt-search-folder-l1-1-0!IsMSSearchEnabled` at `0x1800028d0`

## pseudocode

```c
__int64 __fastcall CSrchAdminSSO::_OnHKCRNotification(CSrchAdminSSO *this, void *a2, char a3, bool *a4)
{
  int v8; // edi
  LSTATUS v9; // eax
  CSrchAdminSSO *v10; // rcx
  signed int v11; // ebx
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  bool v15; // sf
  HKEY phkResult[7]; // [rsp+30h] [rbp-38h] BYREF

  ResetEvent(a2);
  v8 = 1;
  RegNotifyChangeKeyValue(HKEY_CLASSES_ROOT, 0, 1u, a2, 1);
  phkResult[0] = 0;
  v9 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Outlook.Application", 0, 0x20019u, phkResult);
  v11 = v9;
  if ( !v9 )
    goto LABEL_9;
  if ( v9 == 2 )
  {
    v12 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Outlook.Application.12", 0, 0x20019u, phkResult);
    v11 = v12;
    if ( !v12 )
      goto LABEL_9;
    if ( v12 == 2 )
    {
      v13 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Outlook.Application.11", 0, 0x20019u, phkResult);
      v11 = v13;
      if ( !v13 )
      {
LABEL_9:
        RegCloseKey(phkResult[0]);
        goto LABEL_14;
      }
      if ( v13 == 2 )
      {
        v14 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Outlook.Application.10", 0, 0x20019u, phkResult);
        v11 = v14;
        if ( !v14 )
          goto LABEL_9;
        if ( v14 == 2 )
        {
          v8 = 0;
          v11 = 0;
          goto LABEL_14;
        }
      }
    }
  }
  v8 = 0;
  v15 = v11 < 0;
  if ( v11 <= 0 )
    goto LABEL_15;
  v11 = (unsigned __int16)v11 | 0x80070000;
LABEL_14:
  v15 = v11 < 0;
LABEL_15:
  if ( !v15 )
  {
    if ( !v8 && *((_DWORD *)this + 79) && (a3 || !(unsigned int)IsMSSearchEnabled(0, 0)) )
    {
      CSrchAdminSSO::_DeleteIndexedMapiItems(v10);
      *a4 = 1;
    }
    *((_DWORD *)this + 79) = v8;
  }
  return 0;
}

```

## disassembly

```asm
0x180002750  push    rbx
0x180002752  push    rbp
0x180002753  push    rsi
0x180002754  push    rdi
0x180002755  push    r14
0x180002757  sub     rsp, 40h
0x18000275b  mov     rsi, rcx
0x18000275e  mov     r14, r9
0x180002761  mov     rcx, rdx; hEvent
0x180002764  movzx   ebp, r8b
0x180002768  mov     rbx, rdx
0x18000276b  call    cs:__imp_ResetEvent
0x180002771  mov     edi, 1
0x180002776  mov     r9, rbx; hEvent
0x180002779  mov     r8d, edi; dwNotifyFilter
0x18000277c  mov     [rsp+68h+fAsynchronous], edi; fAsynchronous
0x180002780  xor     edx, edx; bWatchSubtree
0x180002782  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002789  call    cs:__imp_RegNotifyChangeKeyValue
0x18000278f  lea     rax, [rsp+68h+phkResult]
0x180002794  mov     [rsp+68h+phkResult], 0
0x18000279d  mov     r9d, 20019h; samDesired
0x1800027a3  mov     qword ptr [rsp+68h+fAsynchronous], rax; phkResult
0x1800027a8  xor     r8d, r8d; ulOptions
0x1800027ab  lea     rdx, SubKey; "Outlook.Application"
0x1800027b2  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800027b9  call    cs:__imp_RegOpenKeyExW
0x1800027bf  mov     ebx, eax
0x1800027c1  test    eax, eax
0x1800027c3  jnz     short loc_1800027D5
0x1800027c5  mov     rcx, [rsp+68h+phkResult]; hKey
0x1800027ca  call    cs:__imp_RegCloseKey
0x1800027d0  jmp     loc_1800028B7
0x1800027d5  cmp     eax, 2
0x1800027d8  jnz     loc_1800028A8
0x1800027de  lea     rax, [rsp+68h+phkResult]
0x1800027e3  mov     r9d, 20019h; samDesired
0x1800027e9  xor     r8d, r8d; ulOptions
0x1800027ec  mov     qword ptr [rsp+68h+fAsynchronous], rax; phkResult
0x1800027f1  lea     rdx, aOutlookApplica_0; "Outlook.Application.12"
0x1800027f8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800027ff  call    cs:__imp_RegOpenKeyExW
0x180002805  mov     ebx, eax
0x180002807  test    eax, eax
0x180002809  jnz     short loc_18000281B
0x18000280b  mov     rcx, [rsp+68h+phkResult]; hKey
0x180002810  call    cs:__imp_RegCloseKey
0x180002816  jmp     loc_1800028B7
0x18000281b  cmp     eax, 2
0x18000281e  jnz     loc_1800028A8
0x180002824  lea     rax, [rsp+68h+phkResult]
0x180002829  mov     r9d, 20019h; samDesired
0x18000282f  xor     r8d, r8d; ulOptions
0x180002832  mov     qword ptr [rsp+68h+fAsynchronous], rax; phkResult
0x180002837  lea     rdx, aOutlookApplica; "Outlook.Application.11"
0x18000283e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002845  call    cs:__imp_RegOpenKeyExW
0x18000284b  mov     ebx, eax
0x18000284d  test    eax, eax
0x18000284f  jnz     short loc_18000285E
0x180002851  mov     rcx, [rsp+68h+phkResult]; hKey
0x180002856  call    cs:__imp_RegCloseKey
0x18000285c  jmp     short loc_1800028B7
0x18000285e  cmp     eax, 2
0x180002861  jnz     short loc_1800028A8
0x180002863  lea     rax, [rsp+68h+phkResult]
0x180002868  mov     r9d, 20019h; samDesired
0x18000286e  xor     r8d, r8d; ulOptions
0x180002871  mov     qword ptr [rsp+68h+fAsynchronous], rax; phkResult
0x180002876  lea     rdx, aOutlookApplica_1; "Outlook.Application.10"
0x18000287d  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002884  call    cs:__imp_RegOpenKeyExW
0x18000288a  mov     ebx, eax
0x18000288c  test    eax, eax
0x18000288e  jnz     short loc_18000289D
0x180002890  mov     rcx, [rsp+68h+phkResult]; hKey
0x180002895  call    cs:__imp_RegCloseKey
0x18000289b  jmp     short loc_1800028B7
0x18000289d  cmp     eax, 2
0x1800028a0  jnz     short loc_1800028A8
0x1800028a2  xor     edi, edi
0x1800028a4  xor     ebx, ebx
0x1800028a6  jmp     short loc_1800028B7
0x1800028a8  xor     edi, edi
0x1800028aa  test    ebx, ebx
0x1800028ac  jle     short loc_1800028B9
0x1800028ae  movzx   ebx, bx
0x1800028b1  or      ebx, 80070000h
0x1800028b7  test    ebx, ebx
0x1800028b9  js      short loc_1800028E9
0x1800028bb  test    edi, edi
0x1800028bd  jnz     short loc_1800028E3
0x1800028bf  cmp     [rsi+13Ch], edi
0x1800028c5  jz      short loc_1800028E3
0x1800028c7  test    bpl, bpl
0x1800028ca  jnz     short loc_1800028DA
0x1800028cc  xor     edx, edx
0x1800028ce  xor     ecx, ecx
0x1800028d0  call    cs:__imp_IsMSSearchEnabled
0x1800028d6  test    eax, eax
0x1800028d8  jnz     short loc_1800028E3
0x1800028da  call    ?_DeleteIndexedMapiItems@CSrchAdminSSO@@AEAAJXZ; CSrchAdminSSO::_DeleteIndexedMapiItems(void)
0x1800028df  mov     byte ptr [r14], 1
0x1800028e3  mov     [rsi+13Ch], edi
0x1800028e9  xor     eax, eax
0x1800028eb  add     rsp, 40h
0x1800028ef  pop     r14
0x1800028f1  pop     rdi
0x1800028f2  pop     rsi
0x1800028f3  pop     rbp
0x1800028f4  pop     rbx
0x1800028f5  retn
```
