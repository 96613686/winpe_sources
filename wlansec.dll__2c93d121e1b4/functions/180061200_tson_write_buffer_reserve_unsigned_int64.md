# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180061200`
- end: `0x1800612cd`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `205`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005e280`
- `0x180061004`
- `0x1800612fc`

## callees

- `0x18003fdec`
- `0x18003fe7c`
- `0x180061200`
- `0x18006228c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061279`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061279`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180061231`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180061231`

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
0x180061200  mov     [rsp+arg_8], rbx
0x180061205  mov     [rsp+arg_10], rbp
0x18006120a  push    rsi
0x18006120b  push    rdi
0x18006120c  push    r14
0x18006120e  sub     rsp, 20h
0x180061212  mov     rax, [rcx+820h]
0x180061219  mov     rbx, rcx
0x18006121c  sub     rax, [rcx+810h]
0x180061223  cmp     rax, rdx
0x180061226  cmova   rdx, rax
0x18006122a  lea     r14, [rdx+rdx]
0x18006122e  mov     rcx, r14; cb
0x180061231  call    cs:__imp_CoTaskMemAlloc
0x180061238  nop     dword ptr [rax+rax+00h]
0x18006123d  mov     rdi, rax
0x180061240  test    rax, rax
0x180061243  jz      short loc_1800612B3
0x180061245  mov     r8, [rbx+810h]; Source
0x18006124c  mov     rdx, r14; DestinationSize
0x18006124f  mov     rsi, [rbx+818h]
0x180061256  mov     rcx, rax; Destination
0x180061259  sub     rsi, r8
0x18006125c  mov     r9, rsi; SourceSize
0x18006125f  call    memcpy_s_1
0x180061264  mov     rbp, [rbx]
0x180061267  test    rbp, rbp
0x18006126a  jz      short loc_18006128F
0x18006126c  lea     rcx, [rsp+38h+arg_0]; this
0x180061271  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180061276  mov     rcx, rbp; pv
0x180061279  call    cs:__imp_CoTaskMemFree
0x180061280  nop     dword ptr [rax+rax+00h]
0x180061285  lea     rcx, [rsp+38h+arg_0]; this
0x18006128a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18006128f  mov     [rbx], rdi
0x180061292  lea     rax, [rsi+rdi]
0x180061296  mov     [rbx+818h], rax
0x18006129d  lea     rax, [r14+rdi]
0x1800612a1  mov     [rbx+820h], rax
0x1800612a8  mov     al, 1
0x1800612aa  mov     [rbx+810h], rdi
0x1800612b1  jmp     short loc_1800612B9
0x1800612b3  mov     byte ptr [rbx+8], 1
0x1800612b7  xor     al, al
0x1800612b9  mov     rbx, [rsp+38h+arg_8]
0x1800612be  mov     rbp, [rsp+38h+arg_10]
0x1800612c3  add     rsp, 20h
0x1800612c7  pop     r14
0x1800612c9  pop     rdi
0x1800612ca  pop     rsi
0x1800612cb  retn
```
