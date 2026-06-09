# DupWideToAnsi

- ea: `0x18000d020`
- end: `0x18000d0a1`
- name: `DupWideToAnsi`
- size: `129`
- prototype: `__int64 __fastcall(PCWSTR pwszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021bb0`

## callees

- `0x18000d020`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000d060`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000d060`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x18000d082`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x18000d082`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d06b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d06b`

## pseudocode

```c
__int64 __fastcall DupWideToAnsi(PCWSTR pwszSrc, CHAR **a2)
{
  unsigned int v4; // esi
  CHAR *v5; // rax

  v4 = WideCharToMultiByte(0, 0, pwszSrc, -1, 0, 0, 0, 0) + 1;
  v5 = (CHAR *)CoTaskMemAlloc(v4);
  *a2 = v5;
  if ( !v5 )
    return 2147942414LL;
  SHUnicodeToAnsi(pwszSrc, v5, v4);
  return 0;
}

```

## disassembly

```asm
0x18000d020  mov     rax, rsp
0x18000d023  mov     [rax+8], rbx
0x18000d027  mov     [rax+10h], rsi
0x18000d02b  push    rdi
0x18000d02c  sub     rsp, 40h
0x18000d030  mov     qword ptr [rax-10h], 0
0x18000d038  mov     rbx, rdx
0x18000d03b  mov     qword ptr [rax-18h], 0
0x18000d043  mov     rdi, rcx
0x18000d046  mov     r8, rcx; lpWideCharStr
0x18000d049  mov     dword ptr [rax-20h], 0
0x18000d050  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000d054  mov     qword ptr [rax-28h], 0
0x18000d05c  xor     edx, edx; dwFlags
0x18000d05e  xor     ecx, ecx; CodePage
0x18000d060  call    cs:__imp_WideCharToMultiByte
0x18000d066  lea     esi, [rax+1]
0x18000d069  mov     ecx, esi; cb
0x18000d06b  call    cs:__imp_CoTaskMemAlloc
0x18000d071  mov     [rbx], rax
0x18000d074  test    rax, rax
0x18000d077  jz      short loc_18000D08C
0x18000d079  mov     r8d, esi; cchBuf
0x18000d07c  mov     rdx, rax; pszDst
0x18000d07f  mov     rcx, rdi; pwszSrc
0x18000d082  call    cs:__imp_SHUnicodeToAnsi
0x18000d088  xor     eax, eax
0x18000d08a  jmp     short loc_18000D091
0x18000d08c  mov     eax, 8007000Eh
0x18000d091  mov     rbx, [rsp+48h+arg_0]
0x18000d096  mov     rsi, [rsp+48h+arg_8]
0x18000d09b  add     rsp, 40h
0x18000d09f  pop     rdi
0x18000d0a0  retn
```
