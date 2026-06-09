# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18005d58c`
- end: `0x18005d63d`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `177`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `13`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006a00`
- `0x180011078`
- `0x180011110`
- `0x1800111a4`
- `0x1800114b4`
- `0x180014bc4`
- `0x18005783c`
- `0x18005bd84`
- `0x18005e290`
- `0x18005e92c`
- `0x18005ee70`
- `0x18005f718`
- `0x18005f92c`

## callees

- `0x18005d58c`
- `0x18005faa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d600`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d5ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d5ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d5f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d5f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005d5b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005d5b8`

## pseudocode

```c
bool __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  rsize_t v3; // r15
  char *v4; // rax
  char *v5; // rsi
  const void *v6; // r8
  rsize_t v7; // r14
  void *v8; // rbp
  DWORD LastError; // ebx
  bool result; // al

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
      LastError = GetLastError();
      CoTaskMemFree(v8);
      SetLastError(LastError);
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
0x18005d58c  push    rbx
0x18005d58e  push    rbp
0x18005d58f  push    rsi
0x18005d590  push    rdi
0x18005d591  push    r14
0x18005d593  push    r15
0x18005d595  sub     rsp, 28h
0x18005d599  mov     rax, [rcx+820h]
0x18005d5a0  mov     rdi, rcx
0x18005d5a3  sub     rax, [rcx+810h]
0x18005d5aa  cmp     rax, rdx
0x18005d5ad  cmova   rdx, rax
0x18005d5b1  lea     r15, [rdx+rdx]
0x18005d5b5  mov     rcx, r15; cb
0x18005d5b8  call    cs:__imp_CoTaskMemAlloc
0x18005d5be  mov     rsi, rax
0x18005d5c1  test    rax, rax
0x18005d5c4  jz      short loc_18005D62A
0x18005d5c6  mov     r8, [rdi+810h]; Source
0x18005d5cd  mov     rdx, r15; DestinationSize
0x18005d5d0  mov     r14, [rdi+818h]
0x18005d5d7  mov     rcx, rax; Destination
0x18005d5da  sub     r14, r8
0x18005d5dd  mov     r9, r14; SourceSize
0x18005d5e0  call    memcpy_s
0x18005d5e5  mov     rbp, [rdi]
0x18005d5e8  test    rbp, rbp
0x18005d5eb  jz      short loc_18005D606
0x18005d5ed  call    cs:__imp_GetLastError
0x18005d5f3  mov     rcx, rbp; pv
0x18005d5f6  mov     ebx, eax
0x18005d5f8  call    cs:__imp_CoTaskMemFree
0x18005d5fe  mov     ecx, ebx; dwErrCode
0x18005d600  call    cs:__imp_SetLastError
0x18005d606  mov     [rdi], rsi
0x18005d609  lea     rax, [r14+rsi]
0x18005d60d  mov     [rdi+818h], rax
0x18005d614  lea     rax, [r15+rsi]
0x18005d618  mov     [rdi+820h], rax
0x18005d61f  mov     al, 1
0x18005d621  mov     [rdi+810h], rsi
0x18005d628  jmp     short loc_18005D630
0x18005d62a  mov     byte ptr [rdi+8], 1
0x18005d62e  xor     al, al
0x18005d630  add     rsp, 28h
0x18005d634  pop     r15
0x18005d636  pop     r14
0x18005d638  pop     rdi
0x18005d639  pop     rsi
0x18005d63a  pop     rbp
0x18005d63b  pop     rbx
0x18005d63c  retn
```
