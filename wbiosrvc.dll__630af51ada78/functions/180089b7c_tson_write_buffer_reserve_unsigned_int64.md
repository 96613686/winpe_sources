# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180089b7c`
- end: `0x180089c3c`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180082fd4`
- `0x1800834e0`
- `0x180084874`
- `0x1800897fc`

## callees

- `0x180037f44`
- `0x18006bdec`
- `0x18006bfb8`
- `0x180089b7c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089bef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089bef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180089bad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180089bad`

## pseudocode

```c
bool __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  rsize_t v3; // r14
  char *v4; // rax
  char *v5; // rdi
  const void *v6; // r8
  rsize_t v7; // rsi
  void *v8; // rbp
  bool result; // al
  char v10; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 260) - *((_QWORD *)this + 258) > a2 )
    a2 = *((_QWORD *)this + 260) - *((_QWORD *)this + 258);
  v3 = 2 * a2;
  v4 = (char *)CoTaskMemAlloc(2 * a2);
  v5 = v4;
  if ( v4 )
  {
    v6 = (const void *)*((_QWORD *)this + 258);
    v7 = *((_QWORD *)this + 259) - (_QWORD)v6;
    memcpy_s_1(v4, v3, v6, v7);
    v8 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
      CoTaskMemFree(v8);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
    }
    *(_QWORD *)this = v5;
    *((_QWORD *)this + 259) = &v5[v7];
    *((_QWORD *)this + 260) = &v5[v3];
    result = 1;
    *((_QWORD *)this + 258) = v5;
  }
  else
  {
    *((_BYTE *)this + 8) = 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180089b7c  mov     [rsp+arg_8], rbx
0x180089b81  mov     [rsp+arg_10], rbp
0x180089b86  push    rsi
0x180089b87  push    rdi
0x180089b88  push    r14
0x180089b8a  sub     rsp, 20h
0x180089b8e  mov     rax, [rcx+820h]
0x180089b95  mov     rbx, rcx
0x180089b98  sub     rax, [rcx+810h]
0x180089b9f  cmp     rax, rdx
0x180089ba2  cmova   rdx, rax
0x180089ba6  lea     r14, [rdx+rdx]
0x180089baa  mov     rcx, r14; cb
0x180089bad  call    cs:__imp_CoTaskMemAlloc
0x180089bb3  mov     rdi, rax
0x180089bb6  test    rax, rax
0x180089bb9  jz      short loc_180089C23
0x180089bbb  mov     r8, [rbx+810h]; Source
0x180089bc2  mov     rdx, r14; DestinationSize
0x180089bc5  mov     rsi, [rbx+818h]
0x180089bcc  mov     rcx, rax; Destination
0x180089bcf  sub     rsi, r8
0x180089bd2  mov     r9, rsi; SourceSize
0x180089bd5  call    memcpy_s_1
0x180089bda  mov     rbp, [rbx]
0x180089bdd  test    rbp, rbp
0x180089be0  jz      short loc_180089BFF
0x180089be2  lea     rcx, [rsp+38h+arg_0]; this
0x180089be7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180089bec  mov     rcx, rbp; pv
0x180089bef  call    cs:__imp_CoTaskMemFree
0x180089bf5  lea     rcx, [rsp+38h+arg_0]; this
0x180089bfa  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180089bff  mov     [rbx], rdi
0x180089c02  lea     rax, [rsi+rdi]
0x180089c06  mov     [rbx+818h], rax
0x180089c0d  lea     rax, [r14+rdi]
0x180089c11  mov     [rbx+820h], rax
0x180089c18  mov     al, 1
0x180089c1a  mov     [rbx+810h], rdi
0x180089c21  jmp     short loc_180089C29
0x180089c23  mov     byte ptr [rbx+8], 1
0x180089c27  xor     al, al
0x180089c29  mov     rbx, [rsp+38h+arg_8]
0x180089c2e  mov     rbp, [rsp+38h+arg_10]
0x180089c33  add     rsp, 20h
0x180089c37  pop     r14
0x180089c39  pop     rdi
0x180089c3a  pop     rsi
0x180089c3b  retn
```
