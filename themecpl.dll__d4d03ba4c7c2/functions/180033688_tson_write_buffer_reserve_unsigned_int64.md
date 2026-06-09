# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180033688`
- end: `0x180033752`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `202`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `13`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e140`
- `0x18002ef74`
- `0x18002f00c`
- `0x18002f0a4`
- `0x18002f224`
- `0x18002fa4c`
- `0x1800323e0`
- `0x180033354`
- `0x180033758`
- `0x180033df4`
- `0x180034340`
- `0x1800349b4`
- `0x180034bc8`

## callees

- `0x180008bfc`
- `0x180033688`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003370e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003370e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800336ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800336ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033700`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033700`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800336b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800336b4`

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
0x180033688  push    rbx
0x18003368a  push    rbp
0x18003368b  push    rsi
0x18003368c  push    rdi
0x18003368d  push    r14
0x18003368f  push    r15
0x180033691  sub     rsp, 28h
0x180033695  mov     rax, [rcx+820h]
0x18003369c  mov     rdi, rcx
0x18003369f  sub     rax, [rcx+810h]
0x1800336a6  cmp     rax, rdx
0x1800336a9  cmova   rdx, rax
0x1800336ad  lea     r15, [rdx+rdx]
0x1800336b1  mov     rcx, r15; cb
0x1800336b4  call    cs:__imp_CoTaskMemAlloc
0x1800336bb  nop     dword ptr [rax+rax+00h]
0x1800336c0  mov     rsi, rax
0x1800336c3  test    rax, rax
0x1800336c6  jz      short loc_18003373E
0x1800336c8  mov     r8, [rdi+810h]; Source
0x1800336cf  mov     rdx, r15; DestinationSize
0x1800336d2  mov     r14, [rdi+818h]
0x1800336d9  mov     rcx, rax; Destination
0x1800336dc  sub     r14, r8
0x1800336df  mov     r9, r14; SourceSize
0x1800336e2  call    memcpy_s
0x1800336e7  mov     rbp, [rdi]
0x1800336ea  test    rbp, rbp
0x1800336ed  jz      short loc_18003371A
0x1800336ef  call    cs:__imp_GetLastError
0x1800336f6  nop     dword ptr [rax+rax+00h]
0x1800336fb  mov     rcx, rbp; pv
0x1800336fe  mov     ebx, eax
0x180033700  call    cs:__imp_CoTaskMemFree
0x180033707  nop     dword ptr [rax+rax+00h]
0x18003370c  mov     ecx, ebx; dwErrCode
0x18003370e  call    cs:__imp_SetLastError
0x180033715  nop     dword ptr [rax+rax+00h]
0x18003371a  mov     [rdi], rsi
0x18003371d  lea     rax, [r14+rsi]
0x180033721  mov     [rdi+818h], rax
0x180033728  lea     rax, [r15+rsi]
0x18003372c  mov     [rdi+820h], rax
0x180033733  mov     al, 1
0x180033735  mov     [rdi+810h], rsi
0x18003373c  jmp     short loc_180033744
0x18003373e  mov     byte ptr [rdi+8], 1
0x180033742  xor     al, al
0x180033744  add     rsp, 28h
0x180033748  pop     r15
0x18003374a  pop     r14
0x18003374c  pop     rdi
0x18003374d  pop     rsi
0x18003374e  pop     rbp
0x18003374f  pop     rbx
0x180033750  retn
```
