# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18001c1f0`
- end: `0x18001c2b0`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800125ac`
- `0x1800126ec`
- `0x180013d2c`
- `0x18001beec`

## callees

- `0x180004640`
- `0x180005540`
- `0x180005560`
- `0x18001c1f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c221`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c221`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c263`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c263`

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
    memcpy_s(v4, v3, v6, v7);
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
0x18001c1f0  mov     [rsp+arg_8], rbx
0x18001c1f5  mov     [rsp+arg_10], rbp
0x18001c1fa  push    rsi
0x18001c1fb  push    rdi
0x18001c1fc  push    r14
0x18001c1fe  sub     rsp, 20h
0x18001c202  mov     rax, [rcx+820h]
0x18001c209  mov     rbx, rcx
0x18001c20c  sub     rax, [rcx+810h]
0x18001c213  cmp     rax, rdx
0x18001c216  cmova   rdx, rax
0x18001c21a  lea     r14, [rdx+rdx]
0x18001c21e  mov     rcx, r14; cb
0x18001c221  call    cs:__imp_CoTaskMemAlloc
0x18001c227  mov     rdi, rax
0x18001c22a  test    rax, rax
0x18001c22d  jz      short loc_18001C297
0x18001c22f  mov     r8, [rbx+810h]; Source
0x18001c236  mov     rdx, r14; DestinationSize
0x18001c239  mov     rsi, [rbx+818h]
0x18001c240  mov     rcx, rax; Destination
0x18001c243  sub     rsi, r8
0x18001c246  mov     r9, rsi; SourceSize
0x18001c249  call    memcpy_s
0x18001c24e  mov     rbp, [rbx]
0x18001c251  test    rbp, rbp
0x18001c254  jz      short loc_18001C273
0x18001c256  lea     rcx, [rsp+38h+arg_0]; this
0x18001c25b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001c260  mov     rcx, rbp; pv
0x18001c263  call    cs:__imp_CoTaskMemFree
0x18001c269  lea     rcx, [rsp+38h+arg_0]; this
0x18001c26e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001c273  mov     [rbx], rdi
0x18001c276  lea     rax, [rsi+rdi]
0x18001c27a  mov     [rbx+818h], rax
0x18001c281  lea     rax, [r14+rdi]
0x18001c285  mov     [rbx+820h], rax
0x18001c28c  mov     al, 1
0x18001c28e  mov     [rbx+810h], rdi
0x18001c295  jmp     short loc_18001C29D
0x18001c297  mov     byte ptr [rbx+8], 1
0x18001c29b  xor     al, al
0x18001c29d  mov     rbx, [rsp+38h+arg_8]
0x18001c2a2  mov     rbp, [rsp+38h+arg_10]
0x18001c2a7  add     rsp, 20h
0x18001c2ab  pop     r14
0x18001c2ad  pop     rdi
0x18001c2ae  pop     rsi
0x18001c2af  retn
```
