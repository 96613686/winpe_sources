# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18002e4a8`
- end: `0x18002e568`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `10`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002dbec`
- `0x18002dd48`
- `0x18002e058`
- `0x18002e210`
- `0x18002e80c`
- `0x18002e8fc`
- `0x18002e968`
- `0x18002ee58`
- `0x180069244`
- `0x180069444`

## callees

- `0x18002e4a8`
- `0x18002ed70`
- `0x180038ebc`
- `0x180038f20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e51b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e51b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e4d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e4d9`

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
0x18002e4a8  mov     [rsp+arg_8], rbx
0x18002e4ad  mov     [rsp+arg_10], rbp
0x18002e4b2  push    rsi
0x18002e4b3  push    rdi
0x18002e4b4  push    r14
0x18002e4b6  sub     rsp, 20h
0x18002e4ba  mov     rax, [rcx+820h]
0x18002e4c1  mov     rbx, rcx
0x18002e4c4  sub     rax, [rcx+810h]
0x18002e4cb  cmp     rax, rdx
0x18002e4ce  cmova   rdx, rax
0x18002e4d2  lea     r14, [rdx+rdx]
0x18002e4d6  mov     rcx, r14; cb
0x18002e4d9  call    cs:__imp_CoTaskMemAlloc
0x18002e4df  mov     rdi, rax
0x18002e4e2  test    rax, rax
0x18002e4e5  jz      short loc_18002E54F
0x18002e4e7  mov     r8, [rbx+810h]; Source
0x18002e4ee  mov     rdx, r14; DestinationSize
0x18002e4f1  mov     rsi, [rbx+818h]
0x18002e4f8  mov     rcx, rax; Destination
0x18002e4fb  sub     rsi, r8
0x18002e4fe  mov     r9, rsi; SourceSize
0x18002e501  call    memcpy_s_1
0x18002e506  mov     rbp, [rbx]
0x18002e509  test    rbp, rbp
0x18002e50c  jz      short loc_18002E52B
0x18002e50e  lea     rcx, [rsp+38h+arg_0]; this
0x18002e513  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002e518  mov     rcx, rbp; pv
0x18002e51b  call    cs:__imp_CoTaskMemFree
0x18002e521  lea     rcx, [rsp+38h+arg_0]; this
0x18002e526  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002e52b  mov     [rbx], rdi
0x18002e52e  lea     rax, [rsi+rdi]
0x18002e532  mov     [rbx+818h], rax
0x18002e539  lea     rax, [r14+rdi]
0x18002e53d  mov     [rbx+820h], rax
0x18002e544  mov     al, 1
0x18002e546  mov     [rbx+810h], rdi
0x18002e54d  jmp     short loc_18002E555
0x18002e54f  mov     byte ptr [rbx+8], 1
0x18002e553  xor     al, al
0x18002e555  mov     rbx, [rsp+38h+arg_8]
0x18002e55a  mov     rbp, [rsp+38h+arg_10]
0x18002e55f  add     rsp, 20h
0x18002e563  pop     r14
0x18002e565  pop     rdi
0x18002e566  pop     rsi
0x18002e567  retn
```
