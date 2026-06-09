# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18002b040`
- end: `0x18002b100`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028308`
- `0x1800283d0`
- `0x180028cc8`
- `0x18002af34`

## callees

- `0x180013042`
- `0x180015cb4`
- `0x180015e20`
- `0x18002b040`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b0b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b0b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b071`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b071`

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
0x18002b040  mov     [rsp+arg_8], rbx
0x18002b045  mov     [rsp+arg_10], rbp
0x18002b04a  push    rsi
0x18002b04b  push    rdi
0x18002b04c  push    r14
0x18002b04e  sub     rsp, 20h
0x18002b052  mov     rax, [rcx+820h]
0x18002b059  mov     rbx, rcx
0x18002b05c  sub     rax, [rcx+810h]
0x18002b063  cmp     rax, rdx
0x18002b066  cmova   rdx, rax
0x18002b06a  lea     r14, [rdx+rdx]
0x18002b06e  mov     rcx, r14; cb
0x18002b071  call    cs:__imp_CoTaskMemAlloc
0x18002b077  mov     rdi, rax
0x18002b07a  test    rax, rax
0x18002b07d  jz      short loc_18002B0E7
0x18002b07f  mov     r8, [rbx+810h]; Source
0x18002b086  mov     rdx, r14; DestinationSize
0x18002b089  mov     rsi, [rbx+818h]
0x18002b090  mov     rcx, rax; Destination
0x18002b093  sub     rsi, r8
0x18002b096  mov     r9, rsi; SourceSize
0x18002b099  call    memcpy_s
0x18002b09e  mov     rbp, [rbx]
0x18002b0a1  test    rbp, rbp
0x18002b0a4  jz      short loc_18002B0C3
0x18002b0a6  lea     rcx, [rsp+38h+arg_0]; this
0x18002b0ab  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002b0b0  mov     rcx, rbp; pv
0x18002b0b3  call    cs:__imp_CoTaskMemFree
0x18002b0b9  lea     rcx, [rsp+38h+arg_0]; this
0x18002b0be  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002b0c3  mov     [rbx], rdi
0x18002b0c6  lea     rax, [rsi+rdi]
0x18002b0ca  mov     [rbx+818h], rax
0x18002b0d1  lea     rax, [r14+rdi]
0x18002b0d5  mov     [rbx+820h], rax
0x18002b0dc  mov     al, 1
0x18002b0de  mov     [rbx+810h], rdi
0x18002b0e5  jmp     short loc_18002B0ED
0x18002b0e7  mov     byte ptr [rbx+8], 1
0x18002b0eb  xor     al, al
0x18002b0ed  mov     rbx, [rsp+38h+arg_8]
0x18002b0f2  mov     rbp, [rsp+38h+arg_10]
0x18002b0f7  add     rsp, 20h
0x18002b0fb  pop     r14
0x18002b0fd  pop     rdi
0x18002b0fe  pop     rsi
0x18002b0ff  retn
```
