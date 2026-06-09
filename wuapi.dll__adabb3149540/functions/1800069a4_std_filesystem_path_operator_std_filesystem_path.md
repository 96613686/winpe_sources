# std::filesystem::path::operator=(std::filesystem::path &&)

- ea: `0x1800069a4`
- end: `0x180006a48`
- name: `??4path@filesystem@std@@QEAAAEAV012@$$QEAV012@@Z`
- size: `164`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006f90`
- `0x180007308`

## callees

- `0x1800069a4`
- `0x1800100d4`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180006a41`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180006a41`

## pseudocode

```c
__int64 __fastcall std::filesystem::path::operator=(__int64 a1, __int64 a2)
{
  unsigned __int64 v4; // rdx
  _QWORD *v5; // rcx
  const struct std::nothrow_t *v6; // rdx

  if ( a1 != a2 )
  {
    v4 = *(_QWORD *)(a1 + 24);
    if ( v4 > 7 )
    {
      v5 = *(_QWORD **)a1;
      v6 = (const struct std::nothrow_t *)(2 * v4 + 2);
      if ( (unsigned __int64)v6 >= 0x1000 )
      {
        v6 = (const struct std::nothrow_t *)((char *)v6 + 39);
        if ( (unsigned __int64)v5 - *(v5 - 1) - 8 > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
        v5 = (_QWORD *)*(v5 - 1);
      }
      operator delete(v5, v6);
    }
    *(_QWORD *)(a1 + 24) = 7;
    *(_QWORD *)(a1 + 16) = 0;
    *(_WORD *)a1 = 0;
    *(_OWORD *)a1 = *(_OWORD *)a2;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)(a2 + 16);
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 7;
    *(_WORD *)a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x1800069a4  mov     [rsp+arg_10], rbx
0x1800069a9  push    rdi
0x1800069aa  sub     rsp, 30h
0x1800069ae  mov     rdi, rdx
0x1800069b1  mov     rbx, rcx
0x1800069b4  cmp     rcx, rdx
0x1800069b7  jz      short loc_180006A22
0x1800069b9  mov     rdx, [rcx+18h]
0x1800069bd  cmp     rdx, 7
0x1800069c1  jbe     short loc_1800069F4
0x1800069c3  mov     rcx, [rcx]
0x1800069c6  lea     rdx, ds:2[rdx*2]
0x1800069ce  cmp     rdx, 1000h
0x1800069d5  jb      short loc_1800069EF
0x1800069d7  mov     rax, [rcx-8]
0x1800069db  add     rdx, 27h ; '''; struct std::nothrow_t *
0x1800069df  sub     rcx, rax
0x1800069e2  sub     rcx, 8
0x1800069e6  cmp     rcx, 1Fh
0x1800069ea  ja      short loc_180006A30
0x1800069ec  mov     rcx, rax; void *
0x1800069ef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800069f4  mov     qword ptr [rbx+18h], 7
0x1800069fc  xor     eax, eax
0x1800069fe  mov     [rbx+10h], rax
0x180006a02  mov     [rbx], ax
0x180006a05  movups  xmm0, xmmword ptr [rdi]
0x180006a08  movups  xmmword ptr [rbx], xmm0
0x180006a0b  movups  xmm1, xmmword ptr [rdi+10h]
0x180006a0f  movups  xmmword ptr [rbx+10h], xmm1
0x180006a13  mov     [rdi+10h], rax
0x180006a17  mov     qword ptr [rdi+18h], 7
0x180006a1f  mov     [rdi], ax
0x180006a22  mov     rax, rbx
0x180006a25  mov     rbx, [rsp+38h+arg_10]
0x180006a2a  add     rsp, 30h
0x180006a2e  pop     rdi
0x180006a2f  retn
0x180006a30  xor     eax, eax
0x180006a32  xor     r9d, r9d; LineNo
0x180006a35  xor     r8d, r8d; FileName
0x180006a38  mov     [rsp+38h+Reserved], rax; Reserved
0x180006a3d  xor     edx, edx; FunctionName
0x180006a3f  xor     ecx, ecx; Expression
0x180006a41  call    cs:__imp__invoke_watson
```
