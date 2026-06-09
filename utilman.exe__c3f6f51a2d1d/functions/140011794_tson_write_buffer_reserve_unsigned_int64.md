# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x140011794`
- end: `0x140011861`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `205`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000ab9c`
- `0x14000b0b0`
- `0x14000baac`
- `0x1400112c0`

## callees

- `0x1400045a0`
- `0x140004ba4`
- `0x14000a384`
- `0x140011794`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14001180d`
- `ole32!CoTaskMemFree` at `0x14001180d`
- `ole32!CoTaskMemAlloc` at `0x1400117c5`
- `ole32!CoTaskMemAlloc` at `0x1400117c5`

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
0x140011794  mov     [rsp+arg_8], rbx
0x140011799  mov     [rsp+arg_10], rbp
0x14001179e  push    rsi
0x14001179f  push    rdi
0x1400117a0  push    r14
0x1400117a2  sub     rsp, 20h
0x1400117a6  mov     rax, [rcx+820h]
0x1400117ad  mov     rbx, rcx
0x1400117b0  sub     rax, [rcx+810h]
0x1400117b7  cmp     rax, rdx
0x1400117ba  cmova   rdx, rax
0x1400117be  lea     r14, [rdx+rdx]
0x1400117c2  mov     rcx, r14; cb
0x1400117c5  call    cs:__imp_CoTaskMemAlloc
0x1400117cc  nop     dword ptr [rax+rax+00h]
0x1400117d1  mov     rdi, rax
0x1400117d4  test    rax, rax
0x1400117d7  jz      short loc_140011847
0x1400117d9  mov     r8, [rbx+810h]; Source
0x1400117e0  mov     rdx, r14; DestinationSize
0x1400117e3  mov     rsi, [rbx+818h]
0x1400117ea  mov     rcx, rax; Destination
0x1400117ed  sub     rsi, r8
0x1400117f0  mov     r9, rsi; SourceSize
0x1400117f3  call    memcpy_s_0
0x1400117f8  mov     rbp, [rbx]
0x1400117fb  test    rbp, rbp
0x1400117fe  jz      short loc_140011823
0x140011800  lea     rcx, [rsp+38h+arg_0]; this
0x140011805  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001180a  mov     rcx, rbp; pv
0x14001180d  call    cs:__imp_CoTaskMemFree
0x140011814  nop     dword ptr [rax+rax+00h]
0x140011819  lea     rcx, [rsp+38h+arg_0]; this
0x14001181e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140011823  mov     [rbx], rdi
0x140011826  lea     rax, [rsi+rdi]
0x14001182a  mov     [rbx+818h], rax
0x140011831  lea     rax, [r14+rdi]
0x140011835  mov     [rbx+820h], rax
0x14001183c  mov     al, 1
0x14001183e  mov     [rbx+810h], rdi
0x140011845  jmp     short loc_14001184D
0x140011847  mov     byte ptr [rbx+8], 1
0x14001184b  xor     al, al
0x14001184d  mov     rbx, [rsp+38h+arg_8]
0x140011852  mov     rbp, [rsp+38h+arg_10]
0x140011857  add     rsp, 20h
0x14001185b  pop     r14
0x14001185d  pop     rdi
0x14001185e  pop     rsi
0x14001185f  retn
```
