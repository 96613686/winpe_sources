# CTextNormMultiResult::GetTopResult(ushort * *)

- ea: `0x18000cc30`
- end: `0x18000cd0a`
- name: `?GetTopResult@CTextNormMultiResult@@UEAAJPEAPEAG@Z`
- size: `218`
- prototype: `__int64 __fastcall(CTextNormMultiResult *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800031c8`
- `0x18000cc30`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ccae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ccae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ccef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ccef`

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
0x18000cc30  mov     rax, rsp
0x18000cc33  mov     [rax+8], rbx
0x18000cc37  mov     [rax+20h], rbp
0x18000cc3b  push    rsi
0x18000cc3c  push    rdi
0x18000cc3d  push    r14
0x18000cc3f  sub     rsp, 30h
0x18000cc43  xor     r14d, r14d
0x18000cc46  mov     rsi, rdx
0x18000cc49  mov     [rax+18h], r14
0x18000cc4d  mov     [rax+10h], r14d
0x18000cc51  test    rdx, rdx
0x18000cc54  jnz     short loc_18000CC60
0x18000cc56  mov     ebx, 80070057h
0x18000cc5b  jmp     loc_18000CCF5
0x18000cc60  mov     rax, [rcx]
0x18000cc63  lea     r9, [rsp+48h+arg_8]
0x18000cc68  lea     r8, [rsp+48h+pv]
0x18000cc6d  mov     edx, 1
0x18000cc72  mov     rax, [rax+30h]
0x18000cc76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc7b  mov     rcx, [rsp+48h+pv]; pv
0x18000cc80  mov     ebx, eax
0x18000cc82  test    eax, eax
0x18000cc84  js      short loc_18000CCEA
0x18000cc86  test    rcx, rcx
0x18000cc89  jz      short loc_18000CCE5
0x18000cc8b  cmp     [rsp+48h+arg_8], 1
0x18000cc90  jnz     short loc_18000CCE5
0x18000cc92  mov     rdx, [rcx]
0x18000cc95  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cc99  inc     rax
0x18000cc9c  cmp     [rdx+rax*2], r14w
0x18000cca1  jnz     short loc_18000CC99
0x18000cca3  lea     rbp, ds:2[rax*2]
0x18000ccab  mov     rcx, rbp; cb
0x18000ccae  call    cs:__imp_CoTaskMemAlloc
0x18000ccb4  mov     rdi, rax
0x18000ccb7  test    rax, rax
0x18000ccba  jnz     short loc_18000CCC8
0x18000ccbc  mov     rcx, [rsp+48h+pv]
0x18000ccc1  mov     ebx, 8007000Eh
0x18000ccc6  jmp     short loc_18000CCEA
0x18000ccc8  mov     rdx, [rsp+48h+pv]
0x18000cccd  mov     r8, rbp; Size
0x18000ccd0  mov     rcx, rdi; void *
0x18000ccd3  mov     rdx, [rdx]; Src
0x18000ccd6  call    memcpy_0
0x18000ccdb  mov     rcx, [rsp+48h+pv]
0x18000cce0  mov     [rsi], rdi
0x18000cce3  jmp     short loc_18000CCEF
0x18000cce5  mov     ebx, 80004005h
0x18000ccea  test    rcx, rcx
0x18000cced  jz      short loc_18000CCF5
0x18000ccef  call    cs:__imp_CoTaskMemFree
0x18000ccf5  mov     rbp, [rsp+48h+arg_18]
0x18000ccfa  mov     eax, ebx
0x18000ccfc  mov     rbx, [rsp+48h+arg_0]
0x18000cd01  add     rsp, 30h
0x18000cd05  pop     r14
0x18000cd07  pop     rdi
0x18000cd08  pop     rsi
0x18000cd09  retn
```
