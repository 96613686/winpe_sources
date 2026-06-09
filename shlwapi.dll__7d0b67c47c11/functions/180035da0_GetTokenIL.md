# GetTokenIL

- ea: `0x180035da0`
- end: `0x180035dff`
- name: `GetTokenIL`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800235ec`

## callees

- `0x180035c04`
- `0x180035da0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035de7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035de7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180035dda`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180035dda`

## pseudocode

```c
__int64 __fastcall GetTokenIL(void *a1, DWORD *a2, DWORD a3)
{
  int v4; // edi
  HLOCAL v5; // rbx
  HLOCAL hMem; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  hMem = 0;
  v4 = SHQueryToken<_TOKEN_MANDATORY_LABEL>(a1, (__int64)a2, a3, &hMem);
  if ( v4 >= 0 )
  {
    v5 = hMem;
    *a2 = *GetSidSubAuthority(*(PSID *)hMem, 0);
    LocalFree(v5);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180035da0  mov     rax, rsp
0x180035da3  mov     [rax+8], rbx
0x180035da7  mov     [rax+18h], rsi
0x180035dab  push    rdi
0x180035dac  sub     rsp, 20h
0x180035db0  lea     r9, [rax+10h]
0x180035db4  mov     dword ptr [rdx], 0
0x180035dba  mov     rsi, rdx
0x180035dbd  mov     qword ptr [rax+10h], 0
0x180035dc5  call    ??$SHQueryToken@U_TOKEN_MANDATORY_LABEL@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_MANDATORY_LABEL@@@Z; SHQueryToken<_TOKEN_MANDATORY_LABEL>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_MANDATORY_LABEL * *)
0x180035dca  mov     edi, eax
0x180035dcc  test    eax, eax
0x180035dce  js      short loc_180035DED
0x180035dd0  mov     rbx, [rsp+28h+hMem]
0x180035dd5  xor     edx, edx; nSubAuthority
0x180035dd7  mov     rcx, [rbx]; pSid
0x180035dda  call    cs:__imp_GetSidSubAuthority
0x180035de0  mov     rcx, rbx; hMem
0x180035de3  mov     edx, [rax]
0x180035de5  mov     [rsi], edx
0x180035de7  call    cs:__imp_LocalFree
0x180035ded  mov     rbx, [rsp+28h+arg_0]
0x180035df2  mov     eax, edi
0x180035df4  mov     rsi, [rsp+28h+arg_10]
0x180035df9  add     rsp, 20h
0x180035dfd  pop     rdi
0x180035dfe  retn
```
