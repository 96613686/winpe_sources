# std::filesystem::path::operator=(std::filesystem::path &&)

- ea: `0x140006f90`
- end: `0x140007034`
- name: `??4path@filesystem@std@@QEAAAEAV012@$$QEAV012@@Z`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400074c8`

## callees

- `0x140006f90`
- `0x14001acf4`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x14000702d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x14000702d`

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
0x140006f90  mov     [rsp+arg_10], rbx
0x140006f95  push    rdi
0x140006f96  sub     rsp, 30h
0x140006f9a  mov     rdi, rdx
0x140006f9d  mov     rbx, rcx
0x140006fa0  cmp     rcx, rdx
0x140006fa3  jz      short loc_14000700E
0x140006fa5  mov     rdx, [rcx+18h]
0x140006fa9  cmp     rdx, 7
0x140006fad  jbe     short loc_140006FE0
0x140006faf  mov     rcx, [rcx]
0x140006fb2  lea     rdx, ds:2[rdx*2]
0x140006fba  cmp     rdx, 1000h
0x140006fc1  jb      short loc_140006FDB
0x140006fc3  mov     rax, [rcx-8]
0x140006fc7  add     rdx, 27h ; '''; struct std::nothrow_t *
0x140006fcb  sub     rcx, rax
0x140006fce  sub     rcx, 8
0x140006fd2  cmp     rcx, 1Fh
0x140006fd6  ja      short loc_14000701C
0x140006fd8  mov     rcx, rax; void *
0x140006fdb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140006fe0  mov     qword ptr [rbx+18h], 7
0x140006fe8  xor     eax, eax
0x140006fea  mov     [rbx+10h], rax
0x140006fee  mov     [rbx], ax
0x140006ff1  movups  xmm0, xmmword ptr [rdi]
0x140006ff4  movups  xmmword ptr [rbx], xmm0
0x140006ff7  movups  xmm1, xmmword ptr [rdi+10h]
0x140006ffb  movups  xmmword ptr [rbx+10h], xmm1
0x140006fff  mov     [rdi+10h], rax
0x140007003  mov     qword ptr [rdi+18h], 7
0x14000700b  mov     [rdi], ax
0x14000700e  mov     rax, rbx
0x140007011  mov     rbx, [rsp+38h+arg_10]
0x140007016  add     rsp, 30h
0x14000701a  pop     rdi
0x14000701b  retn
0x14000701c  xor     eax, eax
0x14000701e  xor     r9d, r9d; LineNo
0x140007021  xor     r8d, r8d; FileName
0x140007024  mov     [rsp+38h+Reserved], rax; Reserved
0x140007029  xor     edx, edx; FunctionName
0x14000702b  xor     ecx, ecx; Expression
0x14000702d  call    cs:__imp__invoke_watson
```
