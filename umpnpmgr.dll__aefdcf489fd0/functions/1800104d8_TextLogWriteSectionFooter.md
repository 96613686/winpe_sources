# TextLogWriteSectionFooter

- ea: `0x1800104d8`
- end: `0x180010637`
- name: `TextLogWriteSectionFooter`
- size: `351`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, int)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x1800027a0`
- `0x1800056d0`
- `0x18000b160`
- `0x1800177e0`

## callees

- `0x18000b5f0`
- `0x18000c9d0`
- `0x18000df10`
- `0x18000fb9c`
- `0x1800104d8`
- `0x180010640`
- `0x180018970`

## pseudocode

```c
__int64 __fastcall TextLogWriteSectionFooter(__int64 a1, __int64 a2, __int64 a3, int a4, int a5)
{
  __int64 result; // rax
  HRESULT v9; // eax
  __int64 v10; // r9
  const char *v11; // r9
  char pszDest[128]; // [rsp+30h] [rbp-98h] BYREF

  result = TextLogVerifyInsertionPoint(a1, *(unsigned int *)(a2 + 12));
  if ( !(_DWORD)result )
    return result;
  TextLogDeleteString(a1, *(_DWORD *)(a2 + 12));
  TextLogInsertString(a1, *(unsigned int *)(a2 + 12), "\r\n");
  if ( !a4 )
  {
    v9 = StringCchPrintfA(pszDest, 0x80u, "[Exit]");
    goto LABEL_16;
  }
  if ( a5 )
  {
    switch ( a5 )
    {
      case 1641:
        v11 = "REBOOT_INITIATED";
        break;
      case 3010:
        v11 = "REBOOT_REQUIRED";
        break;
      case 3011:
        v11 = "RESTART_REQUIRED";
        break;
      case -536870386:
        v11 = "DI_DO_DEFAULT";
        break;
      default:
        v9 = StringCchPrintfA(pszDest, 0x80u, "[Exit status: FAILURE(0x%08x)]", a5);
        goto LABEL_16;
    }
    v9 = StringCchPrintfA(pszDest, 0x80u, "[Exit status: SUCCESS (%s)]", v11);
    goto LABEL_16;
  }
  v9 = StringCchPrintfA(pszDest, 0x80u, "[Exit status: SUCCESS]");
LABEL_16:
  if ( v9 >= 0 )
    TextLogWriteEntry(a1, *(_DWORD *)(a2 + 12), (__int64)pszDest, v10, 32);
  return TextLogWriteEntry(a1, *(_DWORD *)(a2 + 12), (__int64)"Section end", v10, 65568);
}

```

## disassembly

```asm
0x1800104d8  mov     [rsp+arg_10], rbx
0x1800104dd  mov     [rsp+arg_18], rsi
0x1800104e2  push    rdi
0x1800104e3  sub     rsp, 0C0h
0x1800104ea  mov     rax, cs:__security_cookie
0x1800104f1  xor     rax, rsp
0x1800104f4  mov     [rsp+0C8h+var_18], rax
0x1800104fc  mov     rdi, rdx
0x1800104ff  mov     esi, r9d
0x180010502  mov     edx, [rdx+0Ch]
0x180010505  mov     rbx, rcx
0x180010508  call    TextLogVerifyInsertionPoint
0x18001050d  test    eax, eax
0x18001050f  jz      loc_180010612
0x180010515  mov     edx, [rdi+0Ch]
0x180010518  mov     rcx, rbx
0x18001051b  call    TextLogDeleteString
0x180010520  mov     edx, [rdi+0Ch]
0x180010523  lea     r8, asc_18001CACC; "\r\n"
0x18001052a  mov     rcx, rbx
0x18001052d  call    TextLogInsertString
0x180010532  test    esi, esi
0x180010534  jz      loc_1800105C6
0x18001053a  mov     r9d, [rsp+0C8h+arg_20]
0x180010542  test    r9d, r9d
0x180010545  jnz     short loc_180010550
0x180010547  lea     r8, aExitStatusSucc; "[Exit status: SUCCESS]"
0x18001054e  jmp     short loc_1800105CD
0x180010550  cmp     r9d, 669h
0x180010557  jz      short loc_1800105A7
0x180010559  cmp     r9d, 0BC2h
0x180010560  jz      short loc_18001059E
0x180010562  cmp     r9d, 0BC3h
0x180010569  jz      short loc_180010595
0x18001056b  cmp     r9d, 0E000020Eh
0x180010572  jnz     short loc_18001057D
0x180010574  lea     r9, aDiDoDefault; "DI_DO_DEFAULT"
0x18001057b  jmp     short loc_1800105AE
0x18001057d  lea     r8, aExitStatusFail; "[Exit status: FAILURE(0x%08x)]"
0x180010584  mov     edx, 80h; cchDest
0x180010589  lea     rcx, [rsp+0C8h+pszDest]; pszDest
0x18001058e  call    StringCchPrintfA
0x180010593  jmp     short loc_1800105DC
0x180010595  lea     r9, aRestartRequire; "RESTART_REQUIRED"
0x18001059c  jmp     short loc_1800105AE
0x18001059e  lea     r9, aRebootRequired; "REBOOT_REQUIRED"
0x1800105a5  jmp     short loc_1800105AE
0x1800105a7  lea     r9, aRebootInitiate; "REBOOT_INITIATED"
0x1800105ae  lea     r8, aExitStatusSucc_0; "[Exit status: SUCCESS (%s)]"
0x1800105b5  mov     edx, 80h; cchDest
0x1800105ba  lea     rcx, [rsp+0C8h+pszDest]; pszDest
0x1800105bf  call    StringCchPrintfA
0x1800105c4  jmp     short loc_1800105DC
0x1800105c6  lea     r8, aExit; "[Exit]"
0x1800105cd  mov     edx, 80h; cchDest
0x1800105d2  lea     rcx, [rsp+0C8h+pszDest]; pszDest
0x1800105d7  call    StringCchPrintfA
0x1800105dc  test    eax, eax
0x1800105de  js      short loc_1800105F8
0x1800105e0  mov     edx, [rdi+0Ch]
0x1800105e3  lea     r8, [rsp+0C8h+pszDest]
0x1800105e8  mov     rcx, rbx
0x1800105eb  mov     [rsp+0C8h+var_A8], 20h ; ' '
0x1800105f3  call    TextLogWriteEntry
0x1800105f8  mov     edx, [rdi+0Ch]
0x1800105fb  lea     r8, aSectionEnd; "Section end"
0x180010602  mov     rcx, rbx
0x180010605  mov     [rsp+0C8h+var_A8], 10020h
0x18001060d  call    TextLogWriteEntry
0x180010612  mov     rcx, [rsp+0C8h+var_18]
0x18001061a  xor     rcx, rsp; StackCookie
0x18001061d  call    __security_check_cookie
0x180010622  lea     r11, [rsp+0C8h+var_8]
0x18001062a  mov     rbx, [r11+20h]
0x18001062e  mov     rsi, [r11+28h]
0x180010632  mov     rsp, r11
0x180010635  pop     rdi
0x180010636  retn
```
