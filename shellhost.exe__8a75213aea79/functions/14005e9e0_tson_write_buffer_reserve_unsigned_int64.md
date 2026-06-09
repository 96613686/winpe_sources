# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x14005e9e0`
- end: `0x14005eaa0`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004c340`
- `0x14004c40c`
- `0x140050ec0`
- `0x14005e818`

## callees

- `0x14000a7b0`
- `0x14000a834`
- `0x14004b970`
- `0x14005e9e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005ea11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005ea11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005ea53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005ea53`

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
0x14005e9e0  mov     [rsp+arg_8], rbx
0x14005e9e5  mov     [rsp+arg_10], rbp
0x14005e9ea  push    rsi
0x14005e9eb  push    rdi
0x14005e9ec  push    r14
0x14005e9ee  sub     rsp, 20h
0x14005e9f2  mov     rax, [rcx+820h]
0x14005e9f9  mov     rbx, rcx
0x14005e9fc  sub     rax, [rcx+810h]
0x14005ea03  cmp     rax, rdx
0x14005ea06  cmova   rdx, rax
0x14005ea0a  lea     r14, [rdx+rdx]
0x14005ea0e  mov     rcx, r14; cb
0x14005ea11  call    cs:__imp_CoTaskMemAlloc
0x14005ea17  mov     rdi, rax
0x14005ea1a  test    rax, rax
0x14005ea1d  jz      short loc_14005EA87
0x14005ea1f  mov     r8, [rbx+810h]; Source
0x14005ea26  mov     rdx, r14; DestinationSize
0x14005ea29  mov     rsi, [rbx+818h]
0x14005ea30  mov     rcx, rax; Destination
0x14005ea33  sub     rsi, r8
0x14005ea36  mov     r9, rsi; SourceSize
0x14005ea39  call    memcpy_s
0x14005ea3e  mov     rbp, [rbx]
0x14005ea41  test    rbp, rbp
0x14005ea44  jz      short loc_14005EA63
0x14005ea46  lea     rcx, [rsp+38h+arg_0]; this
0x14005ea4b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14005ea50  mov     rcx, rbp; pv
0x14005ea53  call    cs:__imp_CoTaskMemFree
0x14005ea59  lea     rcx, [rsp+38h+arg_0]; this
0x14005ea5e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14005ea63  mov     [rbx], rdi
0x14005ea66  lea     rax, [rsi+rdi]
0x14005ea6a  mov     [rbx+818h], rax
0x14005ea71  lea     rax, [r14+rdi]
0x14005ea75  mov     [rbx+820h], rax
0x14005ea7c  mov     al, 1
0x14005ea7e  mov     [rbx+810h], rdi
0x14005ea85  jmp     short loc_14005EA8D
0x14005ea87  mov     byte ptr [rbx+8], 1
0x14005ea8b  xor     al, al
0x14005ea8d  mov     rbx, [rsp+38h+arg_8]
0x14005ea92  mov     rbp, [rsp+38h+arg_10]
0x14005ea97  add     rsp, 20h
0x14005ea9b  pop     r14
0x14005ea9d  pop     rdi
0x14005ea9e  pop     rsi
0x14005ea9f  retn
```
