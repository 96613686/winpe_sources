# CWdsMetadataValue::Copy(CWdsMetadataValue const *)

- ea: `0x18000dda0`
- end: `0x18000de8d`
- name: `?Copy@CWdsMetadataValue@@QEAAKPEBV1@@Z`
- size: `237`
- prototype: `unsigned int __fastcall(CWdsMetadataValue *__hidden this, const struct CWdsMetadataValue *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800096e8`

## callees

- `0x1800016b8`
- `0x1800025d8`
- `0x18000dda0`
- `0x18000f9b8`
- `0x18000fd28`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000de69`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000de69`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000ddde`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000ddde`

## pseudocode

```c
__int64 __fastcall CWdsMetadataValue::Copy(CWdsMetadataValue *this, const struct CWdsMetadataValue *a2)
{
  unsigned int v2; // esi
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  void *v8; // rax
  void *v9; // rbp
  unsigned __int16 *v11; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  v11 = 0;
  if ( this != a2 )
  {
    CWdsMetadataValue::Shutdown(this);
    v5 = *(_DWORD *)a2;
    if ( *(_DWORD *)a2 == 1 )
    {
      v2 = DuplicateStringW(*((const unsigned __int16 **)a2 + 1), &v11);
      if ( !(unsigned int)ElValidateWin32_2(v2, v6, v7, 1461) )
      {
        *((_QWORD *)this + 1) = v11;
        *(_DWORD *)this = 1;
        return v2;
      }
    }
    else if ( v5 == 7 )
    {
      v8 = operator new[](*((_QWORD *)a2 + 2), (const struct std::nothrow_t *)&std::nothrow);
      v9 = v8;
      if ( v8 )
      {
        memcpy_0(v8, *((const void **)a2 + 1), *((_QWORD *)a2 + 2));
        *(_DWORD *)this = 7;
        *((_QWORD *)this + 1) = v9;
        *((_QWORD *)this + 2) = *((_QWORD *)a2 + 2);
      }
      else
      {
        v2 = 8;
      }
    }
    else
    {
      *(_DWORD *)this = v5;
      *(_OWORD *)((char *)this + 8) = *(_OWORD *)((char *)a2 + 8);
    }
    if ( v11 )
      operator delete(v11);
  }
  return v2;
}

```

## disassembly

```asm
0x18000dda0  mov     rax, rsp
0x18000dda3  mov     [rax+10h], rbx
0x18000dda7  mov     [rax+18h], rbp
0x18000ddab  mov     [rax+20h], rsi
0x18000ddaf  push    rdi
0x18000ddb0  sub     rsp, 20h
0x18000ddb4  xor     esi, esi
0x18000ddb6  mov     rdi, rdx
0x18000ddb9  and     [rax+8], rsi
0x18000ddbd  mov     rbx, rcx
0x18000ddc0  cmp     rcx, rdx
0x18000ddc3  jz      loc_18000DE75
0x18000ddc9  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x18000ddce  mov     eax, [rdi]
0x18000ddd0  cmp     eax, 1
0x18000ddd3  jnz     short loc_18000DE0E
0x18000ddd5  mov     rcx, [rdi+8]
0x18000ddd9  lea     rdx, [rsp+28h+arg_0]
0x18000ddde  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x18000dde5  nop     dword ptr [rax+rax+00h]
0x18000ddea  mov     ecx, eax
0x18000ddec  mov     r9d, 5B5h
0x18000ddf2  mov     esi, eax
0x18000ddf4  call    ElValidateWin32_2
0x18000ddf9  test    eax, eax
0x18000ddfb  jnz     short loc_18000DE5F
0x18000ddfd  mov     rcx, [rsp+28h+arg_0]
0x18000de02  mov     [rbx+8], rcx
0x18000de06  mov     dword ptr [rbx], 1
0x18000de0c  jmp     short loc_18000DE75
0x18000de0e  cmp     eax, 7
0x18000de11  jnz     short loc_18000DE54
0x18000de13  mov     rcx, [rdi+10h]; unsigned __int64
0x18000de17  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000de1e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000de23  mov     rbp, rax
0x18000de26  test    rax, rax
0x18000de29  jnz     short loc_18000DE30
0x18000de2b  lea     esi, [rax+8]
0x18000de2e  jmp     short loc_18000DE5F
0x18000de30  mov     r8, [rdi+10h]; Size
0x18000de34  mov     rcx, rbp; void *
0x18000de37  mov     rdx, [rdi+8]; Src
0x18000de3b  call    memcpy_0
0x18000de40  mov     dword ptr [rbx], 7
0x18000de46  mov     [rbx+8], rbp
0x18000de4a  mov     rax, [rdi+10h]
0x18000de4e  mov     [rbx+10h], rax
0x18000de52  jmp     short loc_18000DE5F
0x18000de54  mov     [rbx], eax
0x18000de56  movups  xmm0, xmmword ptr [rdi+8]
0x18000de5a  movdqu  xmmword ptr [rbx+8], xmm0
0x18000de5f  mov     rcx, [rsp+28h+arg_0]
0x18000de64  test    rcx, rcx
0x18000de67  jz      short loc_18000DE75
0x18000de69  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000de70  nop     dword ptr [rax+rax+00h]
0x18000de75  mov     rbx, [rsp+28h+arg_8]
0x18000de7a  mov     eax, esi
0x18000de7c  mov     rsi, [rsp+28h+arg_18]
0x18000de81  mov     rbp, [rsp+28h+arg_10]
0x18000de86  add     rsp, 20h
0x18000de8a  pop     rdi
0x18000de8b  retn
```
