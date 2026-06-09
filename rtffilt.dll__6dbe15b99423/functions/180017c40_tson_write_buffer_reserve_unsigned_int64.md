# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180017c40`
- end: `0x180017d39`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `249`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `15`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000dd04`
- `0x18000ddb4`
- `0x18000ecd0`
- `0x18000ef64`
- `0x18000f15c`
- `0x18000f1ec`
- `0x18000fa64`
- `0x180016768`
- `0x180017a40`
- `0x180017d40`
- `0x180018360`
- `0x180018760`
- `0x1800189d8`
- `0x180018f64`
- `0x180019178`

## callees

- `0x180002846`
- `0x1800028b4`
- `0x180017c40`
- `0x1800198b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017cbd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017cd0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017cbd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017cd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017cfc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017cfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017cf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017cf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017c6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017c6c`

## pseudocode

```c
bool __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  size_t v3; // r14
  char *v4; // rax
  char *v5; // rbp
  __int64 v6; // rbx
  size_t v7; // rsi
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  void *v11; // r15
  DWORD LastError; // ebx
  bool result; // al

  if ( *((_QWORD *)this + 260) - *((_QWORD *)this + 258) > a2 )
    a2 = *((_QWORD *)this + 260) - *((_QWORD *)this + 258);
  v3 = 2 * a2;
  v4 = (char *)CoTaskMemAlloc(2 * a2);
  v5 = v4;
  if ( !v4 )
  {
    *((_BYTE *)this + 8) = 1;
    return 0;
  }
  v6 = *((_QWORD *)this + 258);
  v7 = *((_QWORD *)this + 259) - v6;
  if ( v7 )
  {
    if ( !v6 || v3 < v7 )
    {
      memset_0(v4, 0, v3);
      if ( v6 )
      {
        if ( v3 >= v7 )
          goto LABEL_13;
        *(_DWORD *)_o__errno(v9, v8, v10) = 34;
      }
      else
      {
        *(_DWORD *)_o__errno(v9, v8, v10) = 22;
      }
      invalid_parameter_noinfo();
      goto LABEL_13;
    }
    memcpy_0(v4, *((const void **)this + 258), v7);
  }
LABEL_13:
  v11 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    CoTaskMemFree(v11);
    SetLastError(LastError);
  }
  *(_QWORD *)this = v5;
  *((_QWORD *)this + 259) = &v5[v7];
  *((_QWORD *)this + 260) = &v5[v3];
  result = 1;
  *((_QWORD *)this + 258) = v5;
  return result;
}

```

## disassembly

```asm
0x180017c40  push    rbx
0x180017c42  push    rbp
0x180017c43  push    rsi
0x180017c44  push    rdi
0x180017c45  push    r14
0x180017c47  push    r15
0x180017c49  sub     rsp, 28h
0x180017c4d  mov     rax, [rcx+820h]
0x180017c54  mov     rdi, rcx
0x180017c57  sub     rax, [rcx+810h]
0x180017c5e  cmp     rax, rdx
0x180017c61  cmova   rdx, rax
0x180017c65  lea     r14, [rdx+rdx]
0x180017c69  mov     rcx, r14; cb
0x180017c6c  call    cs:__imp_CoTaskMemAlloc
0x180017c72  mov     rbp, rax
0x180017c75  test    rax, rax
0x180017c78  jz      loc_180017D26
0x180017c7e  mov     rbx, [rdi+810h]
0x180017c85  mov     rsi, [rdi+818h]
0x180017c8c  sub     rsi, rbx
0x180017c8f  jz      short loc_180017CE1
0x180017c91  test    rbx, rbx
0x180017c94  jz      short loc_180017CAB
0x180017c96  cmp     r14, rsi
0x180017c99  jb      short loc_180017CAB
0x180017c9b  mov     r8, rsi; Size
0x180017c9e  mov     rdx, rbx; Src
0x180017ca1  mov     rcx, rax; void *
0x180017ca4  call    memcpy_0
0x180017ca9  jmp     short loc_180017CE1
0x180017cab  mov     r8, r14; Size
0x180017cae  xor     edx, edx; Val
0x180017cb0  mov     rcx, rbp; void *
0x180017cb3  call    memset_0
0x180017cb8  test    rbx, rbx
0x180017cbb  jnz     short loc_180017CCB
0x180017cbd  call    cs:__imp__o__errno
0x180017cc3  mov     dword ptr [rax], 16h
0x180017cc9  jmp     short loc_180017CDC
0x180017ccb  cmp     r14, rsi
0x180017cce  jnb     short loc_180017CE1
0x180017cd0  call    cs:__imp__o__errno
0x180017cd6  mov     dword ptr [rax], 22h ; '"'
0x180017cdc  call    _invalid_parameter_noinfo
0x180017ce1  mov     r15, [rdi]
0x180017ce4  test    r15, r15
0x180017ce7  jz      short loc_180017D02
0x180017ce9  call    cs:__imp_GetLastError
0x180017cef  mov     rcx, r15; pv
0x180017cf2  mov     ebx, eax
0x180017cf4  call    cs:__imp_CoTaskMemFree
0x180017cfa  mov     ecx, ebx; dwErrCode
0x180017cfc  call    cs:__imp_SetLastError
0x180017d02  mov     [rdi], rbp
0x180017d05  lea     rax, [rsi+rbp]
0x180017d09  mov     [rdi+818h], rax
0x180017d10  lea     rax, [r14+rbp]
0x180017d14  mov     [rdi+820h], rax
0x180017d1b  mov     al, 1
0x180017d1d  mov     [rdi+810h], rbp
0x180017d24  jmp     short loc_180017D2C
0x180017d26  mov     byte ptr [rdi+8], 1
0x180017d2a  xor     al, al
0x180017d2c  add     rsp, 28h
0x180017d30  pop     r15
0x180017d32  pop     r14
0x180017d34  pop     rdi
0x180017d35  pop     rsi
0x180017d36  pop     rbp
0x180017d37  pop     rbx
0x180017d38  retn
```
