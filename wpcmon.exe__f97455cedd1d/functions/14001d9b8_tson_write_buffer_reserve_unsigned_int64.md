# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x14001d9b8`
- end: `0x14001da69`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `177`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `15`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140008a40`
- `0x140008af0`
- `0x14000a88c`
- `0x14000a924`
- `0x14000a9b8`
- `0x14000aa4c`
- `0x14000aadc`
- `0x14000c258`
- `0x14001d31c`
- `0x14001d944`
- `0x14001da88`
- `0x14001e0a8`
- `0x14001e67c`
- `0x14001f128`
- `0x14001f33c`

## callees

- `0x14001d9b8`
- `0x14001f828`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001da19`
- `KERNEL32!GetLastError` at `0x14001da19`
- `KERNEL32!SetLastError` at `0x14001da2c`
- `KERNEL32!SetLastError` at `0x14001da2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001d9e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001d9e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001da24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001da24`

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
0x14001d9b8  push    rbx
0x14001d9ba  push    rbp
0x14001d9bb  push    rsi
0x14001d9bc  push    rdi
0x14001d9bd  push    r14
0x14001d9bf  push    r15
0x14001d9c1  sub     rsp, 28h
0x14001d9c5  mov     rax, [rcx+820h]
0x14001d9cc  mov     rdi, rcx
0x14001d9cf  sub     rax, [rcx+810h]
0x14001d9d6  cmp     rax, rdx
0x14001d9d9  cmova   rdx, rax
0x14001d9dd  lea     r15, [rdx+rdx]
0x14001d9e1  mov     rcx, r15; cb
0x14001d9e4  call    cs:__imp_CoTaskMemAlloc
0x14001d9ea  mov     rsi, rax
0x14001d9ed  test    rax, rax
0x14001d9f0  jz      short loc_14001DA56
0x14001d9f2  mov     r8, [rdi+810h]; Source
0x14001d9f9  mov     rdx, r15; DestinationSize
0x14001d9fc  mov     r14, [rdi+818h]
0x14001da03  mov     rcx, rax; Destination
0x14001da06  sub     r14, r8
0x14001da09  mov     r9, r14; SourceSize
0x14001da0c  call    memcpy_s
0x14001da11  mov     rbp, [rdi]
0x14001da14  test    rbp, rbp
0x14001da17  jz      short loc_14001DA32
0x14001da19  call    cs:__imp_GetLastError
0x14001da1f  mov     rcx, rbp; pv
0x14001da22  mov     ebx, eax
0x14001da24  call    cs:__imp_CoTaskMemFree
0x14001da2a  mov     ecx, ebx; dwErrCode
0x14001da2c  call    cs:__imp_SetLastError
0x14001da32  mov     [rdi], rsi
0x14001da35  lea     rax, [r14+rsi]
0x14001da39  mov     [rdi+818h], rax
0x14001da40  lea     rax, [r15+rsi]
0x14001da44  mov     [rdi+820h], rax
0x14001da4b  mov     al, 1
0x14001da4d  mov     [rdi+810h], rsi
0x14001da54  jmp     short loc_14001DA5C
0x14001da56  mov     byte ptr [rdi+8], 1
0x14001da5a  xor     al, al
0x14001da5c  add     rsp, 28h
0x14001da60  pop     r15
0x14001da62  pop     r14
0x14001da64  pop     rdi
0x14001da65  pop     rsi
0x14001da66  pop     rbp
0x14001da67  pop     rbx
0x14001da68  retn
```
