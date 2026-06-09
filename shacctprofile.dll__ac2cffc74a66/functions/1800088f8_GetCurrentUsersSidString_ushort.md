# GetCurrentUsersSidString(ushort * *)

- ea: `0x1800088f8`
- end: `0x1800089a0`
- name: `?GetCurrentUsersSidString@@YAJPEAPEAG@Z`
- size: `168`
- prototype: `__int64 __fastcall(LPWSTR *ppwsz, int, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006f54`

## callees

- `0x1800088f8`
- `0x18000911c`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x180008972`
- `SHCORE!SHStrDupW` at `0x180008972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008949`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008949`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000897f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008988`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000897f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008988`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000893f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000893f`

## pseudocode

```c
__int64 __fastcall GetCurrentUsersSidString(LPWSTR *ppwsz, int a2, DWORD a3)
{
  int v4; // ebx
  HLOCAL v5; // rsi
  signed int LastError; // eax
  LPWSTR StringSid; // [rsp+30h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp+10h] BYREF

  *ppwsz = 0;
  hMem = 0;
  v4 = SHQueryToken<_TOKEN_USER>((unsigned int)ppwsz, a2, a3, &hMem);
  if ( v4 >= 0 )
  {
    v5 = hMem;
    StringSid = 0;
    if ( ConvertSidToStringSidW(*(PSID *)hMem, &StringSid) )
    {
      v4 = SHStrDupW(StringSid, ppwsz);
      LocalFree(StringSid);
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147467259;
    }
    LocalFree(v5);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800088f8  mov     rax, rsp
0x1800088fb  mov     [rax+18h], rbx
0x1800088ff  mov     [rax+20h], rsi
0x180008903  push    rdi
0x180008904  sub     rsp, 20h
0x180008908  lea     r9, [rax+10h]
0x18000890c  mov     qword ptr [rcx], 0
0x180008913  mov     rdi, rcx
0x180008916  mov     qword ptr [rax+10h], 0
0x18000891e  call    ??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z; SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)
0x180008923  mov     ebx, eax
0x180008925  test    eax, eax
0x180008927  js      short loc_18000898E
0x180008929  mov     rsi, [rsp+28h+hMem]
0x18000892e  lea     rdx, [rsp+28h+StringSid]; StringSid
0x180008933  mov     [rsp+28h+StringSid], 0
0x18000893c  mov     rcx, [rsi]; Sid
0x18000893f  call    cs:__imp_ConvertSidToStringSidW
0x180008945  test    eax, eax
0x180008947  jnz     short loc_18000896A
0x180008949  call    cs:__imp_GetLastError
0x18000894f  mov     ebx, eax
0x180008951  test    eax, eax
0x180008953  jle     short loc_18000895E
0x180008955  movzx   ebx, ax
0x180008958  or      ebx, 80070000h
0x18000895e  test    ebx, ebx
0x180008960  mov     eax, 80004005h
0x180008965  cmovns  ebx, eax
0x180008968  jmp     short loc_180008985
0x18000896a  mov     rcx, [rsp+28h+StringSid]; psz
0x18000896f  mov     rdx, rdi; ppwsz
0x180008972  call    cs:__imp_SHStrDupW
0x180008978  mov     rcx, [rsp+28h+StringSid]; hMem
0x18000897d  mov     ebx, eax
0x18000897f  call    cs:__imp_LocalFree
0x180008985  mov     rcx, rsi; hMem
0x180008988  call    cs:__imp_LocalFree
0x18000898e  mov     rsi, [rsp+28h+arg_18]
0x180008993  mov     eax, ebx
0x180008995  mov     rbx, [rsp+28h+arg_10]
0x18000899a  add     rsp, 20h
0x18000899e  pop     rdi
0x18000899f  retn
```
