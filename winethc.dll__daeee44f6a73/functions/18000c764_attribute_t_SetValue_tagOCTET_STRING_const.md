# _attribute_t::SetValue(tagOCTET_STRING const *)

- ea: `0x18000c764`
- end: `0x18000c824`
- name: `?SetValue@_attribute_t@@QEAAJPEBUtagOCTET_STRING@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(_attribute_t *__hidden this, const struct tagOCTET_STRING *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002c54`
- `0x180004330`
- `0x180011ef0`

## callees

- `0x18000c764`
- `0x180012d62`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c7d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c7d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c77d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c79d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c77d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c79d`

## pseudocode

```c
__int64 __fastcall _attribute_t::SetValue(LPVOID *this, const struct tagOCTET_STRING *a2)
{
  __int64 result; // rax
  SIZE_T dwLength; // rbp
  void *v6; // rax

  if ( *((_DWORD *)this + 2) == 10 )
  {
    CoTaskMemFree(this[2]);
    this[2] = 0;
  }
  else if ( *((_DWORD *)this + 2) == 14 )
  {
    CoTaskMemFree(this[3]);
    this[3] = 0;
    *((_DWORD *)this + 4) = 0;
  }
  result = 0;
  if ( a2 )
  {
    if ( this == (LPVOID *)-16LL || a2->dwLength >= 0xFFFF )
    {
      result = 2147942487LL;
    }
    else
    {
      dwLength = a2->dwLength;
      v6 = CoTaskMemAlloc(dwLength);
      this[3] = v6;
      if ( v6 )
      {
        memcpy_0(v6, a2->lpValue, dwLength);
        *((_DWORD *)this + 4) = a2->dwLength;
        result = 0;
        *((_DWORD *)this + 2) = 14;
        return result;
      }
      result = 2147942414LL;
    }
    *((_DWORD *)this + 2) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000c764  push    rbx
0x18000c766  push    rbp
0x18000c767  push    rsi
0x18000c768  push    rdi
0x18000c769  sub     rsp, 28h
0x18000c76d  cmp     dword ptr [rcx+8], 0Ah
0x18000c771  mov     rdi, rdx
0x18000c774  mov     rbx, rcx
0x18000c777  jnz     short loc_18000C793
0x18000c779  mov     rcx, [rcx+10h]; pv
0x18000c77d  call    cs:__imp_CoTaskMemFree
0x18000c784  nop     dword ptr [rax+rax+00h]
0x18000c789  mov     qword ptr [rbx+10h], 0
0x18000c791  jmp     short loc_18000C7B8
0x18000c793  cmp     dword ptr [rcx+8], 0Eh
0x18000c797  jnz     short loc_18000C7B8
0x18000c799  mov     rcx, [rcx+18h]; pv
0x18000c79d  call    cs:__imp_CoTaskMemFree
0x18000c7a4  nop     dword ptr [rax+rax+00h]
0x18000c7a9  mov     qword ptr [rbx+18h], 0
0x18000c7b1  mov     dword ptr [rbx+10h], 0
0x18000c7b8  xor     eax, eax
0x18000c7ba  test    rdi, rdi
0x18000c7bd  jz      short loc_18000C81A
0x18000c7bf  lea     rsi, [rbx+10h]
0x18000c7c3  test    rsi, rsi
0x18000c7c6  jz      short loc_18000C80E
0x18000c7c8  cmp     dword ptr [rdi], 0FFFFh
0x18000c7ce  jnb     short loc_18000C80E
0x18000c7d0  mov     ebp, [rdi]
0x18000c7d2  mov     ecx, ebp; cb
0x18000c7d4  call    cs:__imp_CoTaskMemAlloc
0x18000c7db  nop     dword ptr [rax+rax+00h]
0x18000c7e0  mov     [rsi+8], rax
0x18000c7e4  test    rax, rax
0x18000c7e7  jnz     short loc_18000C7F0
0x18000c7e9  mov     eax, 8007000Eh
0x18000c7ee  jmp     short loc_18000C813
0x18000c7f0  mov     rdx, [rdi+8]; Src
0x18000c7f4  mov     r8, rbp; Size
0x18000c7f7  mov     rcx, rax; void *
0x18000c7fa  call    memcpy_0
0x18000c7ff  mov     eax, [rdi]
0x18000c801  mov     [rsi], eax
0x18000c803  xor     eax, eax
0x18000c805  mov     dword ptr [rbx+8], 0Eh
0x18000c80c  jmp     short loc_18000C81A
0x18000c80e  mov     eax, 80070057h
0x18000c813  mov     dword ptr [rbx+8], 0
0x18000c81a  add     rsp, 28h
0x18000c81e  pop     rdi
0x18000c81f  pop     rsi
0x18000c820  pop     rbp
0x18000c821  pop     rbx
0x18000c822  retn
```
