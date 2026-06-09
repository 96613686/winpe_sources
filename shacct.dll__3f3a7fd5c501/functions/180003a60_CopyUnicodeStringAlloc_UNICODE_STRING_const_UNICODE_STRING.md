# CopyUnicodeStringAlloc(_UNICODE_STRING * const,_UNICODE_STRING *)

- ea: `0x180003a60`
- end: `0x180003afb`
- name: `?CopyUnicodeStringAlloc@@YAJQEAU_UNICODE_STRING@@PEAU1@@Z`
- size: `155`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *const, struct _UNICODE_STRING *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800020d0`
- `0x180002670`
- `0x180012acc`
- `0x180013ffc`

## callees

- `0x180003a60`
- `0x180016ce9`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003a97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003a97`

## pseudocode

```c
__int64 __fastcall CopyUnicodeStringAlloc(struct _UNICODE_STRING *const a1, struct _UNICODE_STRING *a2)
{
  SIZE_T MaximumLength; // rsi
  WCHAR *v5; // rax
  __int64 result; // rax

  if ( !a1 || !a2 )
    return 2147500035LL;
  if ( a1->Length && a1->Buffer )
  {
    MaximumLength = a1->MaximumLength;
    v5 = (WCHAR *)CoTaskMemAlloc(MaximumLength);
    if ( v5 )
    {
      a2->Length = a1->Length;
      a2->MaximumLength = a1->MaximumLength;
      a2->Buffer = v5;
      memcpy_0(v5, a1->Buffer, MaximumLength);
      return 0;
    }
    else
    {
      return 2147942414LL;
    }
  }
  else
  {
    result = 0;
    *(_DWORD *)&a2->Length = 0;
    a2->Buffer = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180003a60  mov     [rsp+arg_10], rbx
0x180003a65  push    rdi
0x180003a66  sub     rsp, 20h
0x180003a6a  mov     rdi, rdx
0x180003a6d  mov     rbx, rcx
0x180003a70  test    rcx, rcx
0x180003a73  jz      short loc_180003AEB
0x180003a75  test    rdx, rdx
0x180003a78  jz      short loc_180003AEB
0x180003a7a  mov     [rsp+28h+arg_0], rbp
0x180003a7f  xor     ebp, ebp
0x180003a81  cmp     [rcx], bp
0x180003a84  jz      short loc_180003AE1
0x180003a86  cmp     [rcx+8], rbp
0x180003a8a  jz      short loc_180003AE1
0x180003a8c  mov     [rsp+28h+arg_8], rsi
0x180003a91  movzx   esi, word ptr [rcx+2]
0x180003a95  mov     ecx, esi; cb
0x180003a97  call    cs:__imp_CoTaskMemAlloc
0x180003a9d  test    rax, rax
0x180003aa0  jnz     short loc_180003ABC
0x180003aa2  mov     eax, 8007000Eh
0x180003aa7  mov     rsi, [rsp+28h+arg_8]
0x180003aac  mov     rbp, [rsp+28h+arg_0]
0x180003ab1  mov     rbx, [rsp+28h+arg_10]
0x180003ab6  add     rsp, 20h
0x180003aba  pop     rdi
0x180003abb  retn
0x180003abc  movzx   ecx, word ptr [rbx]
0x180003abf  mov     r8, rsi; Size
0x180003ac2  mov     [rdi], cx
0x180003ac5  movzx   ecx, word ptr [rbx+2]
0x180003ac9  mov     [rdi+2], cx
0x180003acd  mov     rcx, rax; void *
0x180003ad0  mov     [rdi+8], rax
0x180003ad4  mov     rdx, [rbx+8]; Src
0x180003ad8  call    memcpy_0
0x180003add  mov     eax, ebp
0x180003adf  jmp     short loc_180003AA7
0x180003ae1  xor     eax, eax
0x180003ae3  mov     [rdx], eax
0x180003ae5  mov     [rdx+8], rax
0x180003ae9  jmp     short loc_180003AAC
0x180003aeb  mov     rbx, [rsp+28h+arg_10]
0x180003af0  mov     eax, 80004003h
0x180003af5  add     rsp, 20h
0x180003af9  pop     rdi
0x180003afa  retn
```
