# CUwfConfiguration::DeleteTreeFromRoot(CUwfRegKey &,ushort const *)

- ea: `0x180007390`
- end: `0x180007414`
- name: `?DeleteTreeFromRoot@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBG@Z`
- size: `132`
- prototype: `__int64 __fastcall(CUwfConfiguration *this, HKEY *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007420`

## callees

- `0x180007390`
- `0x18000dc00`
- `0x18000dc40`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800073f0`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800073f0`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x1800073e8`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x1800073e8`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::DeleteTreeFromRoot(CUwfConfiguration *this, HKEY *a2, const unsigned __int16 *a3)
{
  void *v5; // r8
  int v7; // eax
  unsigned int v8; // ebx
  void *hTransaction; // rax
  HKEY v10; // rcx
  LSTATUS v11; // eax

  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 == (void *)-1LL )
    v7 = CUwfRegKey::DeleteTree(a2, a3);
  else
    v7 = CUwfRegKey::DeleteTreeTransacted((CUwfRegKey *)a2, a3, v5);
  v8 = v7;
  if ( v7 >= 0 )
  {
    hTransaction = (void *)*((_QWORD *)this + 1);
    v10 = *a2;
    if ( hTransaction == (void *)-1LL )
      v11 = RegDeleteKeyW(v10, a3);
    else
      v11 = RegDeleteKeyTransactedW(v10, a3, 0, 0, hTransaction, 0);
    if ( v11 )
    {
      if ( v11 > 0 )
        return (unsigned __int16)v11 | 0x80070000;
      else
        return (unsigned int)v11;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180007390  push    rbx
0x180007392  push    rbp
0x180007393  push    rsi
0x180007394  push    rdi
0x180007395  sub     rsp, 38h
0x180007399  mov     rdi, r8
0x18000739c  mov     rsi, rdx
0x18000739f  mov     r8, [rcx+8]; void *
0x1800073a3  mov     rbp, rcx
0x1800073a6  mov     rdx, rdi; unsigned __int16 *
0x1800073a9  mov     rcx, rsi; this
0x1800073ac  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800073b0  jz      short loc_1800073B9
0x1800073b2  call    ?DeleteTreeTransacted@CUwfRegKey@@QEAAJPEBGPEAX@Z; CUwfRegKey::DeleteTreeTransacted(ushort const *,void *)
0x1800073b7  jmp     short loc_1800073BE
0x1800073b9  call    ?DeleteTree@CUwfRegKey@@QEAAJPEBG@Z; CUwfRegKey::DeleteTree(ushort const *)
0x1800073be  mov     ebx, eax
0x1800073c0  test    eax, eax
0x1800073c2  js      short loc_180007409
0x1800073c4  mov     rax, [rbp+8]
0x1800073c8  mov     rdx, rdi; lpSubKey
0x1800073cb  mov     rcx, [rsi]; hKey
0x1800073ce  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800073d2  jz      short loc_1800073F0
0x1800073d4  mov     [rsp+58h+pExtendedParameter], 0; pExtendedParameter
0x1800073dd  xor     r9d, r9d; Reserved
0x1800073e0  xor     r8d, r8d; samDesired
0x1800073e3  mov     [rsp+58h+hTransaction], rax; hTransaction
0x1800073e8  call    cs:__imp_RegDeleteKeyTransactedW
0x1800073ee  jmp     short loc_1800073F6
0x1800073f0  call    cs:__imp_RegDeleteKeyW
0x1800073f6  test    eax, eax
0x1800073f8  jz      short loc_180007409
0x1800073fa  jg      short loc_180007400
0x1800073fc  mov     ebx, eax
0x1800073fe  jmp     short loc_180007409
0x180007400  movzx   ebx, ax
0x180007403  or      ebx, 80070000h
0x180007409  mov     eax, ebx
0x18000740b  add     rsp, 38h
0x18000740f  pop     rdi
0x180007410  pop     rsi
0x180007411  pop     rbp
0x180007412  pop     rbx
0x180007413  retn
```
