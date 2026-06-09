# CopyPolicyInformationFromWire(LCPOLICYINFOGENERIC * *,LCPOLICYINFOGENERIC *)

- ea: `0x18002a7d8`
- end: `0x18002a900`
- name: `?CopyPolicyInformationFromWire@@YAEPEAPEAULCPOLICYINFOGENERIC@@PEAU1@@Z`
- size: `296`
- prototype: `unsigned __int8 __fastcall(struct LCPOLICYINFOGENERIC **, struct LCPOLICYINFOGENERIC *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002acc0`

## callees

- `0x180024376`
- `0x18002a7d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a883`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a8e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a883`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a8e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a800`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a81b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a84f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a800`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a81b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a84f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a898`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a8b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a8c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a898`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a8b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a8c9`

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
0x18002a7d8  mov     [rsp+arg_0], rbx
0x18002a7dd  mov     [rsp+arg_8], rsi
0x18002a7e2  push    rdi
0x18002a7e3  sub     rsp, 20h
0x18002a7e7  mov     edi, 1
0x18002a7ec  mov     rsi, rdx
0x18002a7ef  mov     rbx, rcx
0x18002a7f2  cmp     [rdx], edi
0x18002a7f4  jnz     loc_18002A8DF
0x18002a7fa  lea     edx, [rdi+17h]; uBytes
0x18002a7fd  lea     ecx, [rdi+3Fh]; uFlags
0x18002a800  call    cs:__imp_LocalAlloc
0x18002a806  mov     [rbx], rax
0x18002a809  test    rax, rax
0x18002a80c  jz      loc_18002A8D8
0x18002a812  mov     [rax], edi
0x18002a814  lea     ecx, [rdi+3Fh]; uFlags
0x18002a817  movzx   edx, word ptr [rsi+4]; uBytes
0x18002a81b  call    cs:__imp_LocalAlloc
0x18002a821  mov     rdx, rax
0x18002a824  mov     rax, [rbx]
0x18002a827  mov     [rax+8], rdx
0x18002a82b  mov     rax, [rbx]
0x18002a82e  mov     rcx, [rax+8]; void *
0x18002a832  test    rcx, rcx
0x18002a835  jz      short loc_18002A87E
0x18002a837  movzx   edx, word ptr [rsi+6]
0x18002a83b  movzx   r8d, word ptr [rsi+4]; Size
0x18002a840  add     rdx, rsi; Src
0x18002a843  call    memcpy_0
0x18002a848  movzx   edx, word ptr [rsi+8]; uBytes
0x18002a84c  lea     ecx, [rdi+3Fh]; uFlags
0x18002a84f  call    cs:__imp_LocalAlloc
0x18002a855  mov     rcx, rax
0x18002a858  mov     rax, [rbx]
0x18002a85b  mov     [rax+10h], rcx
0x18002a85f  mov     rax, [rbx]
0x18002a862  mov     rcx, [rax+10h]; void *
0x18002a866  test    rcx, rcx
0x18002a869  jz      short loc_18002A87E
0x18002a86b  movzx   edx, word ptr [rsi+0Ah]
0x18002a86f  movzx   r8d, word ptr [rsi+8]; Size
0x18002a874  add     rdx, rsi; Src
0x18002a877  call    memcpy_0
0x18002a87c  jmp     short loc_18002A8ED
0x18002a87e  mov     ecx, 0Eh; dwErrCode
0x18002a883  call    cs:__imp_SetLastError
0x18002a889  xor     dil, dil
0x18002a88c  mov     rax, [rbx]
0x18002a88f  mov     rcx, [rax+8]; hMem
0x18002a893  test    rcx, rcx
0x18002a896  jz      short loc_18002A8A9
0x18002a898  call    cs:__imp_LocalFree
0x18002a89e  mov     rax, [rbx]
0x18002a8a1  mov     qword ptr [rax+8], 0
0x18002a8a9  mov     rax, [rbx]
0x18002a8ac  mov     rcx, [rax+10h]; hMem
0x18002a8b0  test    rcx, rcx
0x18002a8b3  jz      short loc_18002A8C6
0x18002a8b5  call    cs:__imp_LocalFree
0x18002a8bb  mov     rax, [rbx]
0x18002a8be  mov     qword ptr [rax+10h], 0
0x18002a8c6  mov     rcx, [rbx]; hMem
0x18002a8c9  call    cs:__imp_LocalFree
0x18002a8cf  mov     qword ptr [rbx], 0
0x18002a8d6  jmp     short loc_18002A8ED
0x18002a8d8  mov     ecx, 0Eh
0x18002a8dd  jmp     short loc_18002A8E4
0x18002a8df  mov     ecx, 519h; dwErrCode
0x18002a8e4  call    cs:__imp_SetLastError
0x18002a8ea  xor     dil, dil
0x18002a8ed  mov     rbx, [rsp+28h+arg_0]
0x18002a8f2  mov     al, dil
0x18002a8f5  mov     rsi, [rsp+28h+arg_8]
0x18002a8fa  add     rsp, 20h
0x18002a8fe  pop     rdi
0x18002a8ff  retn
```
