# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180002de4`
- end: `0x180002eac`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `200`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `14`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002eb4`
- `0x180002f28`
- `0x180003148`
- `0x180003294`
- `0x1800033ac`
- `0x180003dac`
- `0x18000429c`
- `0x180004f0c`
- `0x18000546c`
- `0x180005504`
- `0x1800056c4`
- `0x1800066ec`
- `0x18000678c`
- `0x1800072f4`

## callees

- `0x180002de4`
- `0x180008890`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002e1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002e1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002e5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002e5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002e63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e50`

## pseudocode

```c
bool __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  rsize_t v3; // rbp
  char *v4; // rax
  char *v5; // rsi
  const void *v6; // r8
  rsize_t v7; // r14
  void *v8; // r15
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
0x180002de4  mov     [rsp+arg_0], rbx
0x180002de9  mov     [rsp+arg_8], rbp
0x180002dee  mov     [rsp+arg_10], rsi
0x180002df3  push    rdi
0x180002df4  push    r14
0x180002df6  push    r15
0x180002df8  sub     rsp, 20h
0x180002dfc  mov     rax, [rcx+820h]
0x180002e03  mov     rdi, rcx
0x180002e06  sub     rax, [rcx+810h]
0x180002e0d  cmp     rax, rdx
0x180002e10  cmova   rdx, rax
0x180002e14  lea     rbp, [rdx+rdx]
0x180002e18  mov     rcx, rbp; cb
0x180002e1b  call    cs:__imp_CoTaskMemAlloc
0x180002e21  mov     rsi, rax
0x180002e24  test    rax, rax
0x180002e27  jz      short loc_180002E8D
0x180002e29  mov     r8, [rdi+810h]; Source
0x180002e30  mov     rdx, rbp; DestinationSize
0x180002e33  mov     r14, [rdi+818h]
0x180002e3a  mov     rcx, rax; Destination
0x180002e3d  sub     r14, r8
0x180002e40  mov     r9, r14; SourceSize
0x180002e43  call    memcpy_s
0x180002e48  mov     r15, [rdi]
0x180002e4b  test    r15, r15
0x180002e4e  jz      short loc_180002E69
0x180002e50  call    cs:__imp_GetLastError
0x180002e56  mov     rcx, r15; pv
0x180002e59  mov     ebx, eax
0x180002e5b  call    cs:__imp_CoTaskMemFree
0x180002e61  mov     ecx, ebx; dwErrCode
0x180002e63  call    cs:__imp_SetLastError
0x180002e69  mov     [rdi], rsi
0x180002e6c  lea     rax, [r14+rsi]
0x180002e70  mov     [rdi+818h], rax
0x180002e77  lea     rax, [rsi+rbp]
0x180002e7b  mov     [rdi+820h], rax
0x180002e82  mov     al, 1
0x180002e84  mov     [rdi+810h], rsi
0x180002e8b  jmp     short loc_180002E93
0x180002e8d  mov     byte ptr [rdi+8], 1
0x180002e91  xor     al, al
0x180002e93  mov     rbx, [rsp+38h+arg_0]
0x180002e98  mov     rbp, [rsp+38h+arg_8]
0x180002e9d  mov     rsi, [rsp+38h+arg_10]
0x180002ea2  add     rsp, 20h
0x180002ea6  pop     r15
0x180002ea8  pop     r14
0x180002eaa  pop     rdi
0x180002eab  retn
```
