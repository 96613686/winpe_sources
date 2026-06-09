# tson::write_buffer::push_back<uchar>(uchar const &)

- ea: `0x18002ec8c`
- end: `0x18002ed68`
- name: `??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z`
- size: `220`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800692d0`
- `0x18006cdf8`

## callees

- `0x18002ec8c`
- `0x18002ed70`
- `0x180038ebc`
- `0x180038f20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ed4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ed4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002eccc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002eccc`

## pseudocode

```c
char __fastcall tson::write_buffer::push_back<unsigned char>(__int64 a1, char *a2)
{
  unsigned __int64 v4; // rcx
  char *v5; // r8
  unsigned __int64 v6; // rcx
  __int64 v7; // rax
  rsize_t v8; // r15
  char *v9; // rax
  char *v10; // rdi
  const void *v11; // r8
  rsize_t v12; // rsi
  void *v13; // rbp
  char result; // al
  char v15; // [rsp+60h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 2080);
  v5 = *(char **)(a1 + 2072);
  if ( (unsigned __int64)v5 < v4 )
  {
LABEL_8:
    result = 1;
    *v5 = *a2;
    ++*(_QWORD *)(a1 + 2072);
    return result;
  }
  v6 = v4 - *(_QWORD *)(a1 + 2064);
  v7 = 1;
  if ( v6 > 1 )
    v7 = v6;
  v8 = 2 * v7;
  v9 = (char *)CoTaskMemAlloc(2 * v7);
  v10 = v9;
  if ( v9 )
  {
    v11 = *(const void **)(a1 + 2064);
    v12 = *(_QWORD *)(a1 + 2072) - (_QWORD)v11;
    memcpy_s_1(v9, v8, v11, v12);
    v13 = *(void **)a1;
    if ( *(_QWORD *)a1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v15);
      CoTaskMemFree(v13);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v15);
    }
    *(_QWORD *)a1 = v10;
    v5 = &v10[v12];
    *(_QWORD *)(a1 + 2072) = &v10[v12];
    *(_QWORD *)(a1 + 2080) = &v10[v8];
    *(_QWORD *)(a1 + 2064) = v10;
    goto LABEL_8;
  }
  *(_BYTE *)(a1 + 8) = 1;
  return 0;
}

```

## disassembly

```asm
0x18002ec8c  push    rbx
0x18002ec8e  push    rbp
0x18002ec8f  push    rsi
0x18002ec90  push    rdi
0x18002ec91  push    r14
0x18002ec93  push    r15
0x18002ec95  sub     rsp, 28h
0x18002ec99  mov     rbx, rcx
0x18002ec9c  mov     r14, rdx
0x18002ec9f  mov     rcx, [rcx+820h]
0x18002eca6  mov     r8, [rbx+818h]
0x18002ecad  cmp     r8, rcx
0x18002ecb0  jb      short loc_18002ED25
0x18002ecb2  sub     rcx, [rbx+810h]
0x18002ecb9  mov     eax, 1
0x18002ecbe  cmp     rcx, rax
0x18002ecc1  cmova   rax, rcx
0x18002ecc5  lea     r15, [rax+rax]
0x18002ecc9  mov     rcx, r15; cb
0x18002eccc  call    cs:__imp_CoTaskMemAlloc
0x18002ecd2  mov     rdi, rax
0x18002ecd5  test    rax, rax
0x18002ecd8  jz      loc_18002ED60
0x18002ecde  mov     r8, [rbx+810h]; Source
0x18002ece5  mov     rdx, r15; DestinationSize
0x18002ece8  mov     rsi, [rbx+818h]
0x18002ecef  mov     rcx, rax; Destination
0x18002ecf2  sub     rsi, r8
0x18002ecf5  mov     r9, rsi; SourceSize
0x18002ecf8  call    memcpy_s_1
0x18002ecfd  mov     rbp, [rbx]
0x18002ed00  test    rbp, rbp
0x18002ed03  jnz     short loc_18002ED41
0x18002ed05  mov     [rbx], rdi
0x18002ed08  lea     r8, [rsi+rdi]
0x18002ed0c  lea     rax, [r15+rdi]
0x18002ed10  mov     [rbx+818h], r8
0x18002ed17  mov     [rbx+820h], rax
0x18002ed1e  mov     [rbx+810h], rdi
0x18002ed25  mov     cl, [r14]
0x18002ed28  mov     al, 1
0x18002ed2a  mov     [r8], cl
0x18002ed2d  inc     qword ptr [rbx+818h]
0x18002ed34  add     rsp, 28h
0x18002ed38  pop     r15
0x18002ed3a  pop     r14
0x18002ed3c  pop     rdi
0x18002ed3d  pop     rsi
0x18002ed3e  pop     rbp
0x18002ed3f  pop     rbx
0x18002ed40  retn
0x18002ed41  lea     rcx, [rsp+58h+arg_0]; this
0x18002ed46  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002ed4b  mov     rcx, rbp; pv
0x18002ed4e  call    cs:__imp_CoTaskMemFree
0x18002ed54  lea     rcx, [rsp+58h+arg_0]; this
0x18002ed59  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002ed5e  jmp     short loc_18002ED05
0x18002ed60  mov     byte ptr [rbx+8], 1
0x18002ed64  xor     al, al
0x18002ed66  jmp     short loc_18002ED34
```
