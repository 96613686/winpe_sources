# HTTP2ReadHttpLegacyResponse(BASE_HTTP2_CONNECTION *,ulong,ulong *)

- ea: `0x18000b7a0`
- end: `0x18000b8af`
- name: `?HTTP2ReadHttpLegacyResponse@@YAJPEAVBASE_HTTP2_CONNECTION@@KPEAK@Z`
- size: `271`
- prototype: `__int64 __fastcall(struct BASE_HTTP2_CONNECTION *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000b7a0`
- `0x18002461d`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall HTTP2ReadHttpLegacyResponse(struct BASE_HTTP2_CONNECTION *a1, int a2, unsigned int *a3)
{
  __int64 v3; // rbx
  unsigned int v6; // r9d
  __int64 v7; // rdx
  __int64 result; // rax
  __int64 v9; // rcx
  unsigned int v10; // ebp
  __int64 v11; // rdx
  void *v12; // rax
  void *v13; // r14
  struct _RUNTIME_IMPORT_TABLE *v14; // rax

  v3 = *((_QWORD *)a1 + 5);
  v6 = a2 + *(_DWORD *)(v3 + 72);
  v7 = *(_QWORD *)(v3 + 128);
  if ( *(_DWORD *)v7 != 1667326830 )
  {
    *a3 = v6;
LABEL_17:
    result = 0;
    goto LABEL_18;
  }
  if ( v6 < 0xE )
  {
    *(_DWORD *)(v3 + 72) = v6;
    return 3221360674LL;
  }
  if ( v6 != 14 )
  {
    v9 = *(_QWORD *)v7 - 0x74685F6E6361636ELL;
    if ( *(_QWORD *)v7 == 0x74685F6E6361636ELL )
    {
      v9 = *(unsigned int *)(v7 + 8) - 825192564LL;
      if ( *(_DWORD *)(v7 + 8) == 825192564 )
        v9 = *(unsigned __int16 *)(v7 + 12) - 12334LL;
    }
    if ( v9 )
      return 1728;
    v10 = v6 - 14;
    v11 = *(unsigned int *)(v3 + 64);
    if ( (unsigned int)v11 <= v6 - 14 )
      v11 = v10;
    v12 = (void *)(*((__int64 (__fastcall **)(__int64, __int64))pRuntimeImportTable + 35))(v3, v11);
    v13 = v12;
    if ( !v12 )
      return 14;
    memcpy_0(v12, (const void *)(*(_QWORD *)(v3 + 128) + 14LL), v10);
    v14 = pRuntimeImportTable;
    *a3 = v10;
    (*((void (__fastcall **)(_QWORD))v14 + 1))(*(_QWORD *)(v3 + 128));
    *(_QWORD *)(v3 + 128) = v13;
    goto LABEL_17;
  }
  result = 3221360674LL;
LABEL_18:
  *(_DWORD *)(v3 + 72) = 0;
  *((_DWORD *)a1 + 4) = 1;
  return result;
}

```

## disassembly

```asm
0x18000b7a0  push    rbx
0x18000b7a2  push    rbp
0x18000b7a3  push    rsi
0x18000b7a4  push    rdi
0x18000b7a5  push    r14
0x18000b7a7  sub     rsp, 20h
0x18000b7ab  mov     rbx, [rcx+28h]
0x18000b7af  mov     rsi, r8
0x18000b7b2  mov     rdi, rcx
0x18000b7b5  mov     r9d, [rbx+48h]
0x18000b7b9  add     r9d, edx
0x18000b7bc  mov     rdx, [rbx+80h]
0x18000b7c3  cmp     dword ptr [rdx], 6361636Eh
0x18000b7c9  jnz     loc_18000B891
0x18000b7cf  cmp     r9d, 0Eh
0x18000b7d3  jnb     short loc_18000B7E3
0x18000b7d5  mov     [rbx+48h], r9d
0x18000b7d9  mov     eax, 0C0021022h
0x18000b7de  jmp     loc_18000B8A4
0x18000b7e3  jnz     short loc_18000B7EF
0x18000b7e5  mov     eax, 0C0021022h
0x18000b7ea  jmp     loc_18000B896
0x18000b7ef  mov     rcx, [rdx]
0x18000b7f2  mov     rax, 74685F6E6361636Eh
0x18000b7fc  sub     rcx, rax
0x18000b7ff  jnz     short loc_18000B81D
0x18000b801  mov     ecx, [rdx+8]
0x18000b804  mov     eax, 312F7074h
0x18000b809  sub     rcx, rax
0x18000b80c  jnz     short loc_18000B81D
0x18000b80e  movzx   ecx, word ptr [rdx+0Ch]
0x18000b812  mov     eax, 302Eh
0x18000b817  movzx   eax, ax
0x18000b81a  sub     rcx, rax
0x18000b81d  test    rcx, rcx
0x18000b820  jz      short loc_18000B829
0x18000b822  mov     eax, 6C0h
0x18000b827  jmp     short loc_18000B8A4
0x18000b829  mov     rcx, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000b830  lea     ebp, [r9-0Eh]
0x18000b834  mov     edx, [rbx+40h]
0x18000b837  cmp     edx, ebp
0x18000b839  cmovbe  edx, ebp
0x18000b83c  mov     rax, [rcx+118h]
0x18000b843  mov     rcx, rbx
0x18000b846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b84b  mov     r14, rax
0x18000b84e  test    rax, rax
0x18000b851  jnz     short loc_18000B859
0x18000b853  lea     eax, [r14+0Eh]
0x18000b857  jmp     short loc_18000B8A4
0x18000b859  mov     rdx, [rbx+80h]
0x18000b860  mov     rcx, r14; void *
0x18000b863  add     rdx, 0Eh; Src
0x18000b867  mov     r8d, ebp; Size
0x18000b86a  call    memcpy_0
0x18000b86f  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000b876  mov     [rsi], ebp
0x18000b878  mov     rcx, [rbx+80h]
0x18000b87f  mov     rax, [rax+8]
0x18000b883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b888  mov     [rbx+80h], r14
0x18000b88f  jmp     short loc_18000B894
0x18000b891  mov     [r8], r9d
0x18000b894  xor     eax, eax
0x18000b896  mov     dword ptr [rbx+48h], 0
0x18000b89d  mov     dword ptr [rdi+10h], 1
0x18000b8a4  add     rsp, 20h
0x18000b8a8  pop     r14
0x18000b8aa  pop     rdi
0x18000b8ab  pop     rsi
0x18000b8ac  pop     rbp
0x18000b8ad  pop     rbx
0x18000b8ae  retn
```
