# IsolationAwareLoadLibraryExW

- ea: `0x180051334`
- end: `0x1800513ec`
- name: `IsolationAwareLoadLibraryExW`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18005072c`

## callees

- `0x180022c04`
- `0x180051334`
- `0x1800513f4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800513c0`
- `KERNEL32!GetLastError` at `0x1800513c0`
- `KERNEL32!DeactivateActCtx` at `0x1800513d5`
- `KERNEL32!DeactivateActCtx` at `0x1800513d5`
- `KERNEL32!LoadLibraryExW` at `0x180051398`
- `KERNEL32!LoadLibraryExW` at `0x180051398`
- `KERNEL32!SetLastError` at `0x1800513e1`
- `KERNEL32!SetLastError` at `0x1800513e1`

## string_xrefs

- `0x180051391`: `uxtheme.dll`

## pseudocode

```c
HMODULE IsolationAwareLoadLibraryExW()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  int v3; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Library = LoadLibraryExW(L"uxtheme.dll", 0, 0x800u);
  v2 = Library;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Library )
    {
      v3 = 0;
      LastError = 0;
    }
    else
    {
      v3 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v3 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x180051334  mov     rax, rsp
0x180051337  mov     [rax+8], rbx
0x18005133b  mov     [rax+18h], rsi
0x18005133f  mov     [rax+10h], rdx
0x180051343  push    rdi
0x180051344  sub     rsp, 30h
0x180051348  mov     qword ptr [rax-18h], 0
0x180051350  mov     qword ptr [rax+10h], 0
0x180051358  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18005135f  jnz     short loc_180051389
0x180051361  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180051368  jnz     short loc_180051389
0x18005136a  lea     rcx, [rax+10h]; lpCookie
0x18005136e  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180051373  test    eax, eax
0x180051375  jnz     short loc_180051389
0x180051377  xor     eax, eax
0x180051379  mov     rbx, [rsp+38h+arg_0]
0x18005137e  mov     rsi, [rsp+38h+arg_10]
0x180051383  add     rsp, 30h
0x180051387  pop     rdi
0x180051388  retn
0x180051389  xor     edx, edx; hFile
0x18005138b  mov     r8d, 800h; dwFlags
0x180051391  lea     rcx, aUxthemeDll; "uxtheme.dll"
0x180051398  call    cs:__imp_LoadLibraryExW
0x18005139e  mov     rbx, rax
0x1800513a1  mov     [rsp+38h+var_18], rax
0x1800513a6  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800513ad  jz      short loc_1800513B8
0x1800513af  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800513b6  jnz     short loc_1800513E7
0x1800513b8  test    rbx, rbx
0x1800513bb  jnz     short loc_1800513CA
0x1800513bd  lea     esi, [rbx+1]
0x1800513c0  call    cs:__imp_GetLastError
0x1800513c6  mov     edi, eax
0x1800513c8  jmp     short loc_1800513CE
0x1800513ca  xor     esi, esi
0x1800513cc  xor     edi, edi
0x1800513ce  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x1800513d3  xor     ecx, ecx; dwFlags
0x1800513d5  call    cs:__imp_DeactivateActCtx
0x1800513db  test    esi, esi
0x1800513dd  jz      short loc_1800513E7
0x1800513df  mov     ecx, edi; dwErrCode
0x1800513e1  call    cs:__imp_SetLastError
0x1800513e7  mov     rax, rbx
0x1800513ea  jmp     short loc_180051379
0x18007653c  push    rbx
0x18007653e  push    rbp
0x18007653f  push    rdi
0x180076540  sub     rsp, 20h
0x180076544  mov     rbp, rdx
0x180076547  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18007654e  jz      short loc_180076559
0x180076550  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180076557  jnz     short loc_18007658C
0x180076559  cmp     qword ptr [rbp+20h], 0
0x18007655e  jnz     short loc_18007656F
0x180076560  mov     edi, 1
0x180076565  call    cs:__imp_GetLastError
0x18007656b  mov     ebx, eax
0x18007656d  jmp     short loc_180076573
0x18007656f  xor     edi, edi
0x180076571  xor     ebx, ebx
0x180076573  mov     rdx, [rbp+48h]; ulCookie
0x180076577  xor     ecx, ecx; dwFlags
0x180076579  call    cs:__imp_DeactivateActCtx
0x18007657f  test    edi, edi
0x180076581  jz      short loc_18007658C
0x180076583  mov     ecx, ebx; dwErrCode
0x180076585  call    cs:__imp_SetLastError
0x18007658b  nop
0x18007658c  add     rsp, 20h
0x180076590  pop     rdi
0x180076591  pop     rbp
0x180076592  pop     rbx
0x180076593  retn
```
