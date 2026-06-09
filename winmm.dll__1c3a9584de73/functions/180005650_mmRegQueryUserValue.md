# mmRegQueryUserValue

- ea: `0x180005650`
- end: `0x1800056e0`
- name: `mmRegQueryUserValue`
- size: `144`
- prototype: `_BOOL8 __fastcall(__int64, __int64, DWORD, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180004e0c`

## callees

- `0x180005650`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800056b7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800056b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800056c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800056c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180005678`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180005678`

## pseudocode

```c
_BOOL8 __fastcall mmRegQueryUserValue(__int64 a1, __int64 a2, DWORD a3, void *a4)
{
  BOOL v5; // ebx
  HKEY phkResult; // [rsp+58h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp+18h] BYREF

  pcbData = a3;
  phkResult = 0;
  if ( RegOpenCurrentUser(1u, &phkResult) )
    return 0;
  pcbData = 256;
  v5 = RegGetValueW(phkResult, L"AppEvents\\schemes", L"packagebase", 2u, 0, a4, &pcbData) == 0;
  RegCloseKey(phkResult);
  return v5;
}

```

## disassembly

```asm
0x180005650  mov     [rsp+arg_0], rbx
0x180005655  mov     [rsp+arg_10], r8d
0x18000565a  mov     [rsp+phkResult], rdx
0x18000565f  push    rdi
0x180005660  sub     rsp, 40h
0x180005664  xor     edi, edi
0x180005666  lea     rdx, [rsp+48h+phkResult]; phkResult
0x18000566b  mov     ecx, 1; samDesired
0x180005670  mov     [rsp+48h+phkResult], rdi
0x180005675  mov     rbx, r9
0x180005678  call    cs:__imp_RegOpenCurrentUser
0x18000567e  test    eax, eax
0x180005680  jnz     short loc_1800056DC
0x180005682  mov     rcx, [rsp+48h+phkResult]; hkey
0x180005687  lea     rax, [rsp+48h+arg_10]
0x18000568c  mov     [rsp+48h+pcbData], rax; pcbData
0x180005691  lea     r8, aPackagebase; "packagebase"
0x180005698  mov     [rsp+48h+pvData], rbx; pvData
0x18000569d  lea     rdx, aAppeventsSchem; "AppEvents\\schemes"
0x1800056a4  mov     r9d, 2; dwFlags
0x1800056aa  mov     [rsp+48h+pdwType], rdi; pdwType
0x1800056af  mov     [rsp+48h+arg_10], 100h
0x1800056b7  call    cs:__imp_RegGetValueW
0x1800056bd  mov     rcx, [rsp+48h+phkResult]; hKey
0x1800056c2  mov     ebx, edi
0x1800056c4  test    eax, eax
0x1800056c6  setz    bl
0x1800056c9  call    cs:__imp_RegCloseKey
0x1800056cf  mov     eax, ebx
0x1800056d1  mov     rbx, [rsp+48h+arg_0]
0x1800056d6  add     rsp, 40h
0x1800056da  pop     rdi
0x1800056db  retn
0x1800056dc  xor     eax, eax
0x1800056de  jmp     short loc_1800056D1
```
