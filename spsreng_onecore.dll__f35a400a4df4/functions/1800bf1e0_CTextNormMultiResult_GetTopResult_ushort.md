# CTextNormMultiResult::GetTopResult(ushort * *)

- ea: `0x1800bf1e0`
- end: `0x1800bf2ba`
- name: `?GetTopResult@CTextNormMultiResult@@UEAAJPEAPEAG@Z`
- size: `218`
- prototype: `__int64 __fastcall(CTextNormMultiResult *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004312`
- `0x1800bf1e0`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf29f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf29f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf25e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf25e`

## pseudocode

```c
__int64 __fastcall CTextNormMultiResult::GetTopResult(CTextNormMultiResult *this, unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  int v4; // eax
  void *v5; // rcx
  __int64 v6; // rax
  SIZE_T v7; // rbp
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rdi
  int v11; // [rsp+58h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF

  pv = 0;
  v11 = 0;
  if ( a2 )
  {
    v4 = (*(__int64 (__fastcall **)(CTextNormMultiResult *, __int64, LPVOID *, int *))(*(_QWORD *)this + 48LL))(
           this,
           1,
           &pv,
           &v11);
    v5 = pv;
    v3 = v4;
    if ( v4 >= 0 )
    {
      if ( pv && v11 == 1 )
      {
        v6 = -1;
        do
          ++v6;
        while ( *(_WORD *)(*(_QWORD *)pv + 2 * v6) );
        v7 = 2 * v6 + 2;
        v8 = (unsigned __int16 *)CoTaskMemAlloc(v7);
        v9 = v8;
        if ( v8 )
        {
          memcpy_0(v8, *(const void **)pv, v7);
          v5 = pv;
          *a2 = v9;
          goto LABEL_13;
        }
        v5 = pv;
        v3 = -2147024882;
      }
      else
      {
        v3 = -2147467259;
      }
    }
    if ( !v5 )
      return v3;
LABEL_13:
    CoTaskMemFree(v5);
    return v3;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x1800bf1e0  mov     rax, rsp
0x1800bf1e3  mov     [rax+8], rbx
0x1800bf1e7  mov     [rax+20h], rbp
0x1800bf1eb  push    rsi
0x1800bf1ec  push    rdi
0x1800bf1ed  push    r14
0x1800bf1ef  sub     rsp, 30h
0x1800bf1f3  xor     r14d, r14d
0x1800bf1f6  mov     rsi, rdx
0x1800bf1f9  mov     [rax+18h], r14
0x1800bf1fd  mov     [rax+10h], r14d
0x1800bf201  test    rdx, rdx
0x1800bf204  jnz     short loc_1800BF210
0x1800bf206  mov     ebx, 80070057h
0x1800bf20b  jmp     loc_1800BF2A5
0x1800bf210  mov     rax, [rcx]
0x1800bf213  lea     r9, [rsp+48h+arg_8]
0x1800bf218  lea     r8, [rsp+48h+pv]
0x1800bf21d  mov     edx, 1
0x1800bf222  mov     rax, [rax+30h]
0x1800bf226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf22b  mov     rcx, [rsp+48h+pv]; pv
0x1800bf230  mov     ebx, eax
0x1800bf232  test    eax, eax
0x1800bf234  js      short loc_1800BF29A
0x1800bf236  test    rcx, rcx
0x1800bf239  jz      short loc_1800BF295
0x1800bf23b  cmp     [rsp+48h+arg_8], 1
0x1800bf240  jnz     short loc_1800BF295
0x1800bf242  mov     rdx, [rcx]
0x1800bf245  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bf249  inc     rax
0x1800bf24c  cmp     [rdx+rax*2], r14w
0x1800bf251  jnz     short loc_1800BF249
0x1800bf253  lea     rbp, ds:2[rax*2]
0x1800bf25b  mov     rcx, rbp; cb
0x1800bf25e  call    cs:__imp_CoTaskMemAlloc
0x1800bf264  mov     rdi, rax
0x1800bf267  test    rax, rax
0x1800bf26a  jnz     short loc_1800BF278
0x1800bf26c  mov     rcx, [rsp+48h+pv]
0x1800bf271  mov     ebx, 8007000Eh
0x1800bf276  jmp     short loc_1800BF29A
0x1800bf278  mov     rdx, [rsp+48h+pv]
0x1800bf27d  mov     r8, rbp; Size
0x1800bf280  mov     rcx, rdi; void *
0x1800bf283  mov     rdx, [rdx]; Src
0x1800bf286  call    memcpy_0
0x1800bf28b  mov     rcx, [rsp+48h+pv]
0x1800bf290  mov     [rsi], rdi
0x1800bf293  jmp     short loc_1800BF29F
0x1800bf295  mov     ebx, 80004005h
0x1800bf29a  test    rcx, rcx
0x1800bf29d  jz      short loc_1800BF2A5
0x1800bf29f  call    cs:__imp_CoTaskMemFree
0x1800bf2a5  mov     rbp, [rsp+48h+arg_18]
0x1800bf2aa  mov     eax, ebx
0x1800bf2ac  mov     rbx, [rsp+48h+arg_0]
0x1800bf2b1  add     rsp, 30h
0x1800bf2b5  pop     r14
0x1800bf2b7  pop     rdi
0x1800bf2b8  pop     rsi
0x1800bf2b9  retn
```
