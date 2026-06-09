# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x1800565c4`
- end: `0x180056684`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180056400`
- `0x180089c3c`
- `0x18008a3d0`
- `0x1800d0d88`
- `0x1800d2eb8`

## callees

- `0x1800549d8`
- `0x180056534`
- `0x1800565c4`
- `0x180087a6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800565f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800565f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056637`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056637`

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
    memcpy_s_0(v4, v3, v6, v7);
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
0x1800565c4  mov     [rsp+arg_8], rbx
0x1800565c9  mov     [rsp+arg_10], rbp
0x1800565ce  push    rsi
0x1800565cf  push    rdi
0x1800565d0  push    r14
0x1800565d2  sub     rsp, 20h
0x1800565d6  mov     rax, [rcx+820h]
0x1800565dd  mov     rbx, rcx
0x1800565e0  sub     rax, [rcx+810h]
0x1800565e7  cmp     rax, rdx
0x1800565ea  cmova   rdx, rax
0x1800565ee  lea     r14, [rdx+rdx]
0x1800565f2  mov     rcx, r14; cb
0x1800565f5  call    cs:__imp_CoTaskMemAlloc
0x1800565fb  mov     rdi, rax
0x1800565fe  test    rax, rax
0x180056601  jz      short loc_18005666B
0x180056603  mov     r8, [rbx+810h]; Source
0x18005660a  mov     rdx, r14; DestinationSize
0x18005660d  mov     rsi, [rbx+818h]
0x180056614  mov     rcx, rax; Destination
0x180056617  sub     rsi, r8
0x18005661a  mov     r9, rsi; SourceSize
0x18005661d  call    memcpy_s_0
0x180056622  mov     rbp, [rbx]
0x180056625  test    rbp, rbp
0x180056628  jz      short loc_180056647
0x18005662a  lea     rcx, [rsp+38h+arg_0]; this
0x18005662f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180056634  mov     rcx, rbp; pv
0x180056637  call    cs:__imp_CoTaskMemFree
0x18005663d  lea     rcx, [rsp+38h+arg_0]; this
0x180056642  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180056647  mov     [rbx], rdi
0x18005664a  lea     rax, [rsi+rdi]
0x18005664e  mov     [rbx+818h], rax
0x180056655  lea     rax, [r14+rdi]
0x180056659  mov     [rbx+820h], rax
0x180056660  mov     al, 1
0x180056662  mov     [rbx+810h], rdi
0x180056669  jmp     short loc_180056671
0x18005666b  mov     byte ptr [rbx+8], 1
0x18005666f  xor     al, al
0x180056671  mov     rbx, [rsp+38h+arg_8]
0x180056676  mov     rbp, [rsp+38h+arg_10]
0x18005667b  add     rsp, 20h
0x18005667f  pop     r14
0x180056681  pop     rdi
0x180056682  pop     rsi
0x180056683  retn
```
