# GetTokenIL

- ea: `0x18002c424`
- end: `0x18002c485`
- name: `GetTokenIL`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c3b0`

## callees

- `0x18002c424`
- `0x18002c48c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c47d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c47d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002c470`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002c470`

## pseudocode

```c
__int64 __fastcall GetTokenIL(void *a1, DWORD *a2, DWORD a3)
{
  int v4; // edi
  HLOCAL v6; // rbx
  HLOCAL hMem; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  hMem = 0;
  v4 = SHQueryToken<_TOKEN_MANDATORY_LABEL>(a1, (__int64)a2, a3, &hMem);
  if ( v4 >= 0 )
  {
    v6 = hMem;
    *a2 = *GetSidSubAuthority(*(PSID *)hMem, 0);
    LocalFree(v6);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002c424  mov     rax, rsp
0x18002c427  mov     [rax+8], rbx
0x18002c42b  mov     [rax+18h], rsi
0x18002c42f  push    rdi
0x18002c430  sub     rsp, 20h
0x18002c434  lea     r9, [rax+10h]
0x18002c438  mov     dword ptr [rdx], 0
0x18002c43e  mov     rsi, rdx
0x18002c441  mov     qword ptr [rax+10h], 0
0x18002c449  call    ??$SHQueryToken@U_TOKEN_MANDATORY_LABEL@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_MANDATORY_LABEL@@@Z; SHQueryToken<_TOKEN_MANDATORY_LABEL>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_MANDATORY_LABEL * *)
0x18002c44e  mov     edi, eax
0x18002c450  test    eax, eax
0x18002c452  jns     short loc_18002C466
0x18002c454  mov     rbx, [rsp+28h+arg_0]
0x18002c459  mov     eax, edi
0x18002c45b  mov     rsi, [rsp+28h+arg_10]
0x18002c460  add     rsp, 20h
0x18002c464  pop     rdi
0x18002c465  retn
0x18002c466  mov     rbx, [rsp+28h+hMem]
0x18002c46b  xor     edx, edx; nSubAuthority
0x18002c46d  mov     rcx, [rbx]; pSid
0x18002c470  call    cs:__imp_GetSidSubAuthority
0x18002c476  mov     rcx, rbx; hMem
0x18002c479  mov     edx, [rax]
0x18002c47b  mov     [rsi], edx
0x18002c47d  call    cs:__imp_LocalFree
0x18002c483  jmp     short loc_18002C454
```
