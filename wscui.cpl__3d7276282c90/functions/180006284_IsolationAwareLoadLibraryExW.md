# IsolationAwareLoadLibraryExW

- ea: `0x180006284`
- end: `0x180006339`
- name: `IsolationAwareLoadLibraryExW`
- size: `181`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800052cc`

## callees

- `0x180003fa8`
- `0x180006284`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000630d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ada1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000630d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ada1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000632e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000adc1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000632e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000adc1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800062e5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800062e5`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180006322`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000adb5`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180006322`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000adb5`

## pseudocode

```c
HMODULE __fastcall IsolationAwareLoadLibraryExW(LPCWSTR lpLibFileName)
{
  HMODULE Library; // rax
  HMODULE v4; // rbx
  int v5; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Library = LoadLibraryExW(lpLibFileName, 0, 2u);
  v4 = Library;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Library )
    {
      v5 = 0;
      LastError = 0;
    }
    else
    {
      v5 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v5 )
      SetLastError(LastError);
  }
  return v4;
}

```

## disassembly

```asm
0x180006284  mov     rax, rsp
0x180006287  mov     [rax+8], rbx
0x18000628b  mov     [rax+18h], rsi
0x18000628f  mov     [rax+10h], rdx
0x180006293  push    rdi
0x180006294  sub     rsp, 30h
0x180006298  mov     rbx, rcx
0x18000629b  mov     qword ptr [rax-18h], 0
0x1800062a3  mov     qword ptr [rax+10h], 0
0x1800062ab  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800062b2  jnz     short loc_1800062DC
0x1800062b4  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800062bb  jnz     short loc_1800062DC
0x1800062bd  lea     rcx, [rax+10h]; lpCookie
0x1800062c1  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800062c6  test    eax, eax
0x1800062c8  jnz     short loc_1800062DC
0x1800062ca  xor     eax, eax
0x1800062cc  mov     rbx, [rsp+38h+arg_0]
0x1800062d1  mov     rsi, [rsp+38h+arg_10]
0x1800062d6  add     rsp, 30h
0x1800062da  pop     rdi
0x1800062db  retn
0x1800062dc  xor     edx, edx; hFile
0x1800062de  lea     r8d, [rdx+2]; dwFlags
0x1800062e2  mov     rcx, rbx; lpLibFileName
0x1800062e5  call    cs:__imp_LoadLibraryExW
0x1800062eb  mov     rbx, rax
0x1800062ee  mov     [rsp+38h+var_18], rax
0x1800062f3  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800062fa  jz      short loc_180006305
0x1800062fc  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180006303  jnz     short loc_180006334
0x180006305  test    rbx, rbx
0x180006308  jnz     short loc_180006317
0x18000630a  lea     esi, [rbx+1]
0x18000630d  call    cs:__imp_GetLastError
0x180006313  mov     edi, eax
0x180006315  jmp     short loc_18000631B
0x180006317  xor     esi, esi
0x180006319  xor     edi, edi
0x18000631b  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180006320  xor     ecx, ecx; dwFlags
0x180006322  call    cs:__imp_DeactivateActCtx
0x180006328  test    esi, esi
0x18000632a  jz      short loc_180006334
0x18000632c  mov     ecx, edi; dwErrCode
0x18000632e  call    cs:__imp_SetLastError
0x180006334  mov     rax, rbx
0x180006337  jmp     short loc_1800062CC
0x18000ad78  push    rbx
0x18000ad7a  push    rbp
0x18000ad7b  push    rdi
0x18000ad7c  sub     rsp, 20h
0x18000ad80  mov     rbp, rdx
0x18000ad83  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000ad8a  jz      short loc_18000AD95
0x18000ad8c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000ad93  jnz     short loc_18000ADC8
0x18000ad95  cmp     qword ptr [rbp+20h], 0
0x18000ad9a  jnz     short loc_18000ADAB
0x18000ad9c  mov     edi, 1
0x18000ada1  call    cs:__imp_GetLastError
0x18000ada7  mov     ebx, eax
0x18000ada9  jmp     short loc_18000ADAF
0x18000adab  xor     edi, edi
0x18000adad  xor     ebx, ebx
0x18000adaf  mov     rdx, [rbp+48h]; ulCookie
0x18000adb3  xor     ecx, ecx; dwFlags
0x18000adb5  call    cs:__imp_DeactivateActCtx
0x18000adbb  test    edi, edi
0x18000adbd  jz      short loc_18000ADC8
0x18000adbf  mov     ecx, ebx; dwErrCode
0x18000adc1  call    cs:__imp_SetLastError
0x18000adc7  nop
0x18000adc8  add     rsp, 20h
0x18000adcc  pop     rdi
0x18000adcd  pop     rbp
0x18000adce  pop     rbx
0x18000adcf  retn
```
