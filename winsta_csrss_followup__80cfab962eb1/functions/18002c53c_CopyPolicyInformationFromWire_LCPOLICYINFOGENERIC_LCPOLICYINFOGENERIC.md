# CopyPolicyInformationFromWire(LCPOLICYINFOGENERIC * *,LCPOLICYINFOGENERIC *)

- ea: `0x18002c53c`
- end: `0x18002c698`
- name: `?CopyPolicyInformationFromWire@@YAEPEAPEAULCPOLICYINFOGENERIC@@PEAU1@@Z`
- size: `348`
- prototype: `unsigned __int8 __fastcall(struct LCPOLICYINFOGENERIC **, struct LCPOLICYINFOGENERIC *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002cae0`

## callees

- `0x180025cc6`
- `0x18002c53c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c5fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c675`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c5fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c675`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c564`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c585`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c5bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c564`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c585`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c5bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c617`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c63a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c654`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c617`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c63a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c654`

## pseudocode

```c
char __fastcall CopyPolicyInformationFromWire(HLOCAL *a1, struct LCPOLICYINFOGENERIC *a2)
{
  char v2; // di
  struct LCPOLICYINFOGENERIC *v5; // rax
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  DWORD v10; // ecx

  v2 = 1;
  if ( *(_DWORD *)a2 != 1 )
  {
    v10 = 1305;
    goto LABEL_13;
  }
  v5 = (struct LCPOLICYINFOGENERIC *)LocalAlloc(0x40u, 0x18u);
  *a1 = v5;
  if ( !v5 )
  {
    v10 = 14;
LABEL_13:
    SetLastError(v10);
    return 0;
  }
  *(_DWORD *)v5 = 1;
  *((_QWORD *)*a1 + 1) = LocalAlloc(0x40u, *((unsigned __int16 *)a2 + 2));
  v6 = (void *)*((_QWORD *)*a1 + 1);
  if ( v6
    && (memcpy_0(v6, (char *)a2 + *((unsigned __int16 *)a2 + 3), *((unsigned __int16 *)a2 + 2)),
        *((_QWORD *)*a1 + 2) = LocalAlloc(0x40u, *((unsigned __int16 *)a2 + 4)),
        (v7 = (void *)*((_QWORD *)*a1 + 2)) != 0) )
  {
    memcpy_0(v7, (char *)a2 + *((unsigned __int16 *)a2 + 5), *((unsigned __int16 *)a2 + 4));
  }
  else
  {
    SetLastError(0xEu);
    v2 = 0;
    v8 = (void *)*((_QWORD *)*a1 + 1);
    if ( v8 )
    {
      LocalFree(v8);
      *((_QWORD *)*a1 + 1) = 0;
    }
    v9 = (void *)*((_QWORD *)*a1 + 2);
    if ( v9 )
    {
      LocalFree(v9);
      *((_QWORD *)*a1 + 2) = 0;
    }
    LocalFree(*a1);
    *a1 = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x18002c53c  mov     [rsp+arg_0], rbx
0x18002c541  mov     [rsp+arg_8], rsi
0x18002c546  push    rdi
0x18002c547  sub     rsp, 20h
0x18002c54b  mov     edi, 1
0x18002c550  mov     rsi, rdx
0x18002c553  mov     rbx, rcx
0x18002c556  cmp     [rdx], edi
0x18002c558  jnz     loc_18002C670
0x18002c55e  lea     edx, [rdi+17h]; uBytes
0x18002c561  lea     ecx, [rdi+3Fh]; uFlags
0x18002c564  call    cs:__imp_LocalAlloc
0x18002c56b  nop     dword ptr [rax+rax+00h]
0x18002c570  mov     [rbx], rax
0x18002c573  test    rax, rax
0x18002c576  jz      loc_18002C669
0x18002c57c  mov     [rax], edi
0x18002c57e  lea     ecx, [rdi+3Fh]; uFlags
0x18002c581  movzx   edx, word ptr [rsi+4]; uBytes
0x18002c585  call    cs:__imp_LocalAlloc
0x18002c58c  nop     dword ptr [rax+rax+00h]
0x18002c591  mov     rdx, rax
0x18002c594  mov     rax, [rbx]
0x18002c597  mov     [rax+8], rdx
0x18002c59b  mov     rax, [rbx]
0x18002c59e  mov     rcx, [rax+8]; void *
0x18002c5a2  test    rcx, rcx
0x18002c5a5  jz      short loc_18002C5F7
0x18002c5a7  movzx   edx, word ptr [rsi+6]
0x18002c5ab  movzx   r8d, word ptr [rsi+4]; Size
0x18002c5b0  add     rdx, rsi; Src
0x18002c5b3  call    memcpy_0
0x18002c5b8  movzx   edx, word ptr [rsi+8]; uBytes
0x18002c5bc  lea     ecx, [rdi+3Fh]; uFlags
0x18002c5bf  call    cs:__imp_LocalAlloc
0x18002c5c6  nop     dword ptr [rax+rax+00h]
0x18002c5cb  mov     rcx, rax
0x18002c5ce  mov     rax, [rbx]
0x18002c5d1  mov     [rax+10h], rcx
0x18002c5d5  mov     rax, [rbx]
0x18002c5d8  mov     rcx, [rax+10h]; void *
0x18002c5dc  test    rcx, rcx
0x18002c5df  jz      short loc_18002C5F7
0x18002c5e1  movzx   edx, word ptr [rsi+0Ah]
0x18002c5e5  movzx   r8d, word ptr [rsi+8]; Size
0x18002c5ea  add     rdx, rsi; Src
0x18002c5ed  call    memcpy_0
0x18002c5f2  jmp     loc_18002C684
0x18002c5f7  mov     ecx, 0Eh; dwErrCode
0x18002c5fc  call    cs:__imp_SetLastError
0x18002c603  nop     dword ptr [rax+rax+00h]
0x18002c608  xor     dil, dil
0x18002c60b  mov     rax, [rbx]
0x18002c60e  mov     rcx, [rax+8]; hMem
0x18002c612  test    rcx, rcx
0x18002c615  jz      short loc_18002C62E
0x18002c617  call    cs:__imp_LocalFree
0x18002c61e  nop     dword ptr [rax+rax+00h]
0x18002c623  mov     rax, [rbx]
0x18002c626  mov     qword ptr [rax+8], 0
0x18002c62e  mov     rax, [rbx]
0x18002c631  mov     rcx, [rax+10h]; hMem
0x18002c635  test    rcx, rcx
0x18002c638  jz      short loc_18002C651
0x18002c63a  call    cs:__imp_LocalFree
0x18002c641  nop     dword ptr [rax+rax+00h]
0x18002c646  mov     rax, [rbx]
0x18002c649  mov     qword ptr [rax+10h], 0
0x18002c651  mov     rcx, [rbx]; hMem
0x18002c654  call    cs:__imp_LocalFree
0x18002c65b  nop     dword ptr [rax+rax+00h]
0x18002c660  mov     qword ptr [rbx], 0
0x18002c667  jmp     short loc_18002C684
0x18002c669  mov     ecx, 0Eh
0x18002c66e  jmp     short loc_18002C675
0x18002c670  mov     ecx, 519h; dwErrCode
0x18002c675  call    cs:__imp_SetLastError
0x18002c67c  nop     dword ptr [rax+rax+00h]
0x18002c681  xor     dil, dil
0x18002c684  mov     rbx, [rsp+28h+arg_0]
0x18002c689  mov     al, dil
0x18002c68c  mov     rsi, [rsp+28h+arg_8]
0x18002c691  add     rsp, 20h
0x18002c695  pop     rdi
0x18002c696  retn
```
