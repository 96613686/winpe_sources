# UtilTokenGiveUIAccess

- ea: `0x1800243ac`
- end: `0x18002446e`
- name: `UtilTokenGiveUIAccess`
- size: `194`
- prototype: `__int64 __fastcall(HANDLE hExistingToken)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002060c`

## callees

- `0x180007cf8`
- `0x1800243ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002442a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002442a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800243fc`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800243fc`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180024420`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180024420`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800243d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024457`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800243d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024457`

## pseudocode

```c
__int64 __fastcall UtilTokenGiveUIAccess(HANDLE hExistingToken, void **a2)
{
  void *v4; // rcx
  void **phNewToken; // rax
  void *v6; // rcx
  signed int LastError; // eax
  signed int v8; // ebx
  void *v9; // rcx
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF

  v4 = *a2;
  *a2 = 0;
  if ( (unsigned __int64)v4 + 1 > 1 )
    CloseHandle(v4);
  phNewToken = tlx::replace<tlx::file_handle_traits>(a2);
  if ( DuplicateTokenEx(hExistingToken, 0x200EBu, 0, SecurityImpersonation, TokenPrimary, phNewToken)
    && (v6 = *a2, TokenInformation = 1, SetTokenInformation(v6, TokenUIAccess, &TokenInformation, 4u)) )
  {
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
    {
      v9 = *a2;
      *a2 = 0;
      if ( (unsigned __int64)v9 + 1 > 1 )
        CloseHandle(v9);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800243ac  mov     [rsp+arg_0], rbx
0x1800243b1  push    rdi
0x1800243b2  sub     rsp, 30h
0x1800243b6  mov     rbx, rcx
0x1800243b9  mov     rdi, rdx
0x1800243bc  mov     rcx, [rdx]; hObject
0x1800243bf  mov     qword ptr [rdx], 0
0x1800243c6  lea     rax, [rcx+1]
0x1800243ca  cmp     rax, 1
0x1800243ce  jbe     short loc_1800243D6
0x1800243d0  call    cs:__imp_CloseHandle
0x1800243d6  mov     rcx, rdi
0x1800243d9  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800243de  mov     [rsp+38h+phNewToken], rax; phNewToken
0x1800243e3  mov     r9d, 2; ImpersonationLevel
0x1800243e9  xor     r8d, r8d; lpTokenAttributes
0x1800243ec  mov     [rsp+38h+TokenType], 1; TokenType
0x1800243f4  mov     edx, 200EBh; dwDesiredAccess
0x1800243f9  mov     rcx, rbx; hExistingToken
0x1800243fc  call    cs:__imp_DuplicateTokenEx
0x180024402  test    eax, eax
0x180024404  jz      short loc_18002442A
0x180024406  mov     rcx, [rdi]; TokenHandle
0x180024409  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18002440e  mov     r9d, 4; TokenInformationLength
0x180024414  mov     [rsp+38h+TokenInformation], 1
0x18002441c  lea     edx, [r9+16h]; TokenInformationClass
0x180024420  call    cs:__imp_SetTokenInformation
0x180024426  test    eax, eax
0x180024428  jnz     short loc_18002445F
0x18002442a  call    cs:__imp_GetLastError
0x180024430  mov     ebx, eax
0x180024432  test    eax, eax
0x180024434  jle     short loc_18002443F
0x180024436  movzx   ebx, ax
0x180024439  or      ebx, 80070000h
0x18002443f  test    ebx, ebx
0x180024441  jns     short loc_180024461
0x180024443  mov     rcx, [rdi]; hObject
0x180024446  mov     qword ptr [rdi], 0
0x18002444d  lea     rax, [rcx+1]
0x180024451  cmp     rax, 1
0x180024455  jbe     short loc_180024461
0x180024457  call    cs:__imp_CloseHandle
0x18002445d  jmp     short loc_180024461
0x18002445f  xor     ebx, ebx
0x180024461  mov     eax, ebx
0x180024463  mov     rbx, [rsp+38h+arg_0]
0x180024468  add     rsp, 30h
0x18002446c  pop     rdi
0x18002446d  retn
```
