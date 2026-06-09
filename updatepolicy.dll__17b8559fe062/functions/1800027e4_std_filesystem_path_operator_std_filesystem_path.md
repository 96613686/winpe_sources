# std::filesystem::path::operator=(std::filesystem::path &&)

- ea: `0x1800027e4`
- end: `0x180002888`
- name: `??4path@filesystem@std@@QEAAAEAV012@$$QEAV012@@Z`
- size: `164`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002db0`
- `0x180003128`

## callees

- `0x1800027e4`
- `0x18000ed64`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180002881`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180002881`

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
0x1800027e4  mov     [rsp+arg_10], rbx
0x1800027e9  push    rdi
0x1800027ea  sub     rsp, 30h
0x1800027ee  mov     rdi, rdx
0x1800027f1  mov     rbx, rcx
0x1800027f4  cmp     rcx, rdx
0x1800027f7  jz      short loc_180002862
0x1800027f9  mov     rdx, [rcx+18h]
0x1800027fd  cmp     rdx, 7
0x180002801  jbe     short loc_180002834
0x180002803  mov     rcx, [rcx]
0x180002806  lea     rdx, ds:2[rdx*2]
0x18000280e  cmp     rdx, 1000h
0x180002815  jb      short loc_18000282F
0x180002817  mov     rax, [rcx-8]
0x18000281b  add     rdx, 27h ; '''; struct std::nothrow_t *
0x18000281f  sub     rcx, rax
0x180002822  sub     rcx, 8
0x180002826  cmp     rcx, 1Fh
0x18000282a  ja      short loc_180002870
0x18000282c  mov     rcx, rax; void *
0x18000282f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002834  mov     qword ptr [rbx+18h], 7
0x18000283c  xor     eax, eax
0x18000283e  mov     [rbx+10h], rax
0x180002842  mov     [rbx], ax
0x180002845  movups  xmm0, xmmword ptr [rdi]
0x180002848  movups  xmmword ptr [rbx], xmm0
0x18000284b  movups  xmm1, xmmword ptr [rdi+10h]
0x18000284f  movups  xmmword ptr [rbx+10h], xmm1
0x180002853  mov     [rdi+10h], rax
0x180002857  mov     qword ptr [rdi+18h], 7
0x18000285f  mov     [rdi], ax
0x180002862  mov     rax, rbx
0x180002865  mov     rbx, [rsp+38h+arg_10]
0x18000286a  add     rsp, 30h
0x18000286e  pop     rdi
0x18000286f  retn
0x180002870  xor     eax, eax
0x180002872  xor     r9d, r9d; LineNo
0x180002875  xor     r8d, r8d; FileName
0x180002878  mov     [rsp+38h+Reserved], rax; Reserved
0x18000287d  xor     edx, edx; FunctionName
0x18000287f  xor     ecx, ecx; Expression
0x180002881  call    cs:__imp__invoke_watson
```
