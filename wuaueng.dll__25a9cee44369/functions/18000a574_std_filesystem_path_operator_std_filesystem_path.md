# std::filesystem::path::operator=(std::filesystem::path &&)

- ea: `0x18000a574`
- end: `0x18000a618`
- name: `??4path@filesystem@std@@QEAAAEAV012@$$QEAV012@@Z`
- size: `164`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005524`
- `0x180008848`

## callees

- `0x18000a574`
- `0x180010084`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000a611`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000a611`

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
0x18000a574  mov     [rsp+arg_10], rbx
0x18000a579  push    rdi
0x18000a57a  sub     rsp, 30h
0x18000a57e  mov     rdi, rdx
0x18000a581  mov     rbx, rcx
0x18000a584  cmp     rcx, rdx
0x18000a587  jz      short loc_18000A5F2
0x18000a589  mov     rdx, [rcx+18h]
0x18000a58d  cmp     rdx, 7
0x18000a591  jbe     short loc_18000A5C4
0x18000a593  mov     rcx, [rcx]
0x18000a596  lea     rdx, ds:2[rdx*2]
0x18000a59e  cmp     rdx, 1000h
0x18000a5a5  jb      short loc_18000A5BF
0x18000a5a7  mov     rax, [rcx-8]
0x18000a5ab  add     rdx, 27h ; '''; struct std::nothrow_t *
0x18000a5af  sub     rcx, rax
0x18000a5b2  sub     rcx, 8
0x18000a5b6  cmp     rcx, 1Fh
0x18000a5ba  ja      short loc_18000A600
0x18000a5bc  mov     rcx, rax; void *
0x18000a5bf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a5c4  mov     qword ptr [rbx+18h], 7
0x18000a5cc  xor     eax, eax
0x18000a5ce  mov     [rbx+10h], rax
0x18000a5d2  mov     [rbx], ax
0x18000a5d5  movups  xmm0, xmmword ptr [rdi]
0x18000a5d8  movups  xmmword ptr [rbx], xmm0
0x18000a5db  movups  xmm1, xmmword ptr [rdi+10h]
0x18000a5df  movups  xmmword ptr [rbx+10h], xmm1
0x18000a5e3  mov     [rdi+10h], rax
0x18000a5e7  mov     qword ptr [rdi+18h], 7
0x18000a5ef  mov     [rdi], ax
0x18000a5f2  mov     rax, rbx
0x18000a5f5  mov     rbx, [rsp+38h+arg_10]
0x18000a5fa  add     rsp, 30h
0x18000a5fe  pop     rdi
0x18000a5ff  retn
0x18000a600  xor     eax, eax
0x18000a602  xor     r9d, r9d; LineNo
0x18000a605  xor     r8d, r8d; FileName
0x18000a608  mov     [rsp+38h+Reserved], rax; Reserved
0x18000a60d  xor     edx, edx; FunctionName
0x18000a60f  xor     ecx, ecx; Expression
0x18000a611  call    cs:__imp__invoke_watson
```
