# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x1800119ac`
- end: `0x180011a3e`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `146`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006d6c`
- `0x180007328`
- `0x180008e30`
- `0x180011608`

## callees

- `0x1800119ac`
- `0x180011acc`
- `0x180012c68`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800119d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800119d5`

## pseudocode

```c
char __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  rsize_t v3; // r14
  char *v4; // rax
  char *v5; // rsi
  const void *v6; // r8
  rsize_t v7; // rbx

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
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      this,
      v5);
    *((_QWORD *)this + 258) = v5;
    *((_QWORD *)this + 259) = &v5[v7];
    *((_QWORD *)this + 260) = &v5[v3];
    return 1;
  }
  else
  {
    *((_BYTE *)this + 8) = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x1800119ac  push    rbx
0x1800119ae  push    rsi
0x1800119af  push    rdi
0x1800119b0  push    r14
0x1800119b2  sub     rsp, 28h
0x1800119b6  mov     rax, [rcx+820h]
0x1800119bd  mov     rdi, rcx
0x1800119c0  sub     rax, [rcx+810h]
0x1800119c7  cmp     rax, rdx
0x1800119ca  cmova   rdx, rax
0x1800119ce  lea     r14, [rdx+rdx]
0x1800119d2  mov     rcx, r14; cb
0x1800119d5  call    cs:__imp_CoTaskMemAlloc
0x1800119db  mov     rsi, rax
0x1800119de  test    rax, rax
0x1800119e1  jz      short loc_180011A2E
0x1800119e3  mov     r8, [rdi+810h]; Source
0x1800119ea  mov     rdx, r14; DestinationSize
0x1800119ed  mov     rbx, [rdi+818h]
0x1800119f4  mov     rcx, rax; Destination
0x1800119f7  sub     rbx, r8
0x1800119fa  mov     r9, rbx; SourceSize
0x1800119fd  call    memcpy_s
0x180011a02  mov     rdx, rsi
0x180011a05  mov     rcx, rdi
0x180011a08  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180011a0d  lea     rax, [rbx+rsi]
0x180011a11  mov     [rdi+810h], rsi
0x180011a18  mov     [rdi+818h], rax
0x180011a1f  lea     rax, [r14+rsi]
0x180011a23  mov     [rdi+820h], rax
0x180011a2a  mov     al, 1
0x180011a2c  jmp     short loc_180011A34
0x180011a2e  mov     byte ptr [rdi+8], 1
0x180011a32  xor     al, al
0x180011a34  add     rsp, 28h
0x180011a38  pop     r14
0x180011a3a  pop     rdi
0x180011a3b  pop     rsi
0x180011a3c  pop     rbx
0x180011a3d  retn
```
