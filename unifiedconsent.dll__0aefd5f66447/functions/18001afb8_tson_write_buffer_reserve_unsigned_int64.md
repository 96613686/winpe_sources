# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18001afb8`
- end: `0x18001b0b1`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `249`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `17`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800100c8`
- `0x180010178`
- `0x180011cc4`
- `0x180011d5c`
- `0x180011e84`
- `0x180011f18`
- `0x180011fa8`
- `0x1800138c0`
- `0x18001a258`
- `0x18001ace8`
- `0x18001b134`
- `0x18001b1b4`
- `0x18001b778`
- `0x18001bc0c`
- `0x18001c584`
- `0x18001c798`
- `0x180031cb8`

## callees

- `0x1800032f2`
- `0x180003384`
- `0x1800038f9`
- `0x18001afb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b035`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b048`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b035`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b048`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001afe4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001afe4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b06c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b06c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b061`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b074`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b074`

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
0x18001afb8  push    rbx
0x18001afba  push    rbp
0x18001afbb  push    rsi
0x18001afbc  push    rdi
0x18001afbd  push    r14
0x18001afbf  push    r15
0x18001afc1  sub     rsp, 28h
0x18001afc5  mov     rax, [rcx+820h]
0x18001afcc  mov     rdi, rcx
0x18001afcf  sub     rax, [rcx+810h]
0x18001afd6  cmp     rax, rdx
0x18001afd9  cmova   rdx, rax
0x18001afdd  lea     r14, [rdx+rdx]
0x18001afe1  mov     rcx, r14; cb
0x18001afe4  call    cs:__imp_CoTaskMemAlloc
0x18001afea  mov     rbp, rax
0x18001afed  test    rax, rax
0x18001aff0  jz      loc_18001B09E
0x18001aff6  mov     rbx, [rdi+810h]
0x18001affd  mov     rsi, [rdi+818h]
0x18001b004  sub     rsi, rbx
0x18001b007  jz      short loc_18001B059
0x18001b009  test    rbx, rbx
0x18001b00c  jz      short loc_18001B023
0x18001b00e  cmp     r14, rsi
0x18001b011  jb      short loc_18001B023
0x18001b013  mov     r8, rsi; Size
0x18001b016  mov     rdx, rbx; Src
0x18001b019  mov     rcx, rax; void *
0x18001b01c  call    memcpy_0
0x18001b021  jmp     short loc_18001B059
0x18001b023  mov     r8, r14; Size
0x18001b026  xor     edx, edx; Val
0x18001b028  mov     rcx, rbp; void *
0x18001b02b  call    memset_0
0x18001b030  test    rbx, rbx
0x18001b033  jnz     short loc_18001B043
0x18001b035  call    cs:__imp__o__errno
0x18001b03b  mov     dword ptr [rax], 16h
0x18001b041  jmp     short loc_18001B054
0x18001b043  cmp     r14, rsi
0x18001b046  jnb     short loc_18001B059
0x18001b048  call    cs:__imp__o__errno
0x18001b04e  mov     dword ptr [rax], 22h ; '"'
0x18001b054  call    _invalid_parameter_noinfo
0x18001b059  mov     r15, [rdi]
0x18001b05c  test    r15, r15
0x18001b05f  jz      short loc_18001B07A
0x18001b061  call    cs:__imp_GetLastError
0x18001b067  mov     rcx, r15; pv
0x18001b06a  mov     ebx, eax
0x18001b06c  call    cs:__imp_CoTaskMemFree
0x18001b072  mov     ecx, ebx; dwErrCode
0x18001b074  call    cs:__imp_SetLastError
0x18001b07a  mov     [rdi], rbp
0x18001b07d  lea     rax, [rsi+rbp]
0x18001b081  mov     [rdi+818h], rax
0x18001b088  lea     rax, [r14+rbp]
0x18001b08c  mov     [rdi+820h], rax
0x18001b093  mov     al, 1
0x18001b095  mov     [rdi+810h], rbp
0x18001b09c  jmp     short loc_18001B0A4
0x18001b09e  mov     byte ptr [rdi+8], 1
0x18001b0a2  xor     al, al
0x18001b0a4  add     rsp, 28h
0x18001b0a8  pop     r15
0x18001b0aa  pop     r14
0x18001b0ac  pop     rdi
0x18001b0ad  pop     rsi
0x18001b0ae  pop     rbp
0x18001b0af  pop     rbx
0x18001b0b0  retn
```
