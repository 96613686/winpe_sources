# ClusApi::Group::Move(std::vector<uchar,std::allocator<uchar>> const &,ulong,std::shared_ptr<ClusApi::INode> const &,wchar_t const *)

- ea: `0x180032f30`
- end: `0x180032fb0`
- name: `?Move@Group@ClusApi@@UEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@KAEBV?$shared_ptr@UINode@ClusApi@@@4@PEB_W@Z`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180032f30`
- `0x18008e010`

## import_xrefs

- `CLUSAPI!MoveClusterGroupEx2` at `0x180032f8e`
- `CLUSAPI!MoveClusterGroupEx2` at `0x180032f8e`

## string_xrefs

- `0x180032f41`: `cluswmiext!ClusApi::Group::Move`

## pseudocode

```c
__int64 __fastcall ClusApi::Group::Move(__int64 a1, __int64 a2, unsigned int a3, __int64 *a4, const wchar_t *a5)
{
  const wchar_t *v5; // rbx
  __int64 v7; // rcx
  __int64 v10; // rdx
  __int64 result; // rax

  v5 = L"cluswmiext!ClusApi::Group::Move";
  v7 = *a4;
  if ( a5 )
    v5 = a5;
  if ( v7 )
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 152LL))(v7);
  else
    v10 = 0;
  result = MoveClusterGroupEx2(*(_QWORD *)(a1 + 32), v10, a3, *(_QWORD *)a2, *(_DWORD *)(a2 + 8) - *(_DWORD *)a2, v5);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180032f30  push    rbx
0x180032f32  push    rbp
0x180032f33  push    rsi
0x180032f34  push    rdi
0x180032f35  sub     rsp, 38h
0x180032f39  mov     rax, [rsp+58h+arg_20]
0x180032f41  lea     rbx, aCluswmiextClus_18; "cluswmiext!ClusApi::Group::Move"
0x180032f48  test    rax, rax
0x180032f4b  mov     rbp, rcx
0x180032f4e  mov     rcx, [r9]
0x180032f51  mov     esi, r8d
0x180032f54  cmovnz  rbx, rax
0x180032f58  mov     rdi, rdx
0x180032f5b  test    rcx, rcx
0x180032f5e  jz      short loc_180032F74
0x180032f60  mov     rax, [rcx]
0x180032f63  mov     rax, [rax+98h]
0x180032f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f6f  mov     rdx, rax
0x180032f72  jmp     short loc_180032F76
0x180032f74  xor     edx, edx
0x180032f76  mov     eax, [rdi+8]
0x180032f79  mov     r8d, esi
0x180032f7c  sub     eax, [rdi]
0x180032f7e  mov     r9, [rdi]
0x180032f81  mov     rcx, [rbp+20h]
0x180032f85  mov     [rsp+58h+var_30], rbx
0x180032f8a  mov     [rsp+58h+var_38], eax
0x180032f8e  call    cs:__imp_MoveClusterGroupEx2
0x180032f95  nop     dword ptr [rax+rax+00h]
0x180032f9a  test    eax, eax
0x180032f9c  jle     short loc_180032FA6
0x180032f9e  movzx   eax, ax
0x180032fa1  or      eax, 80070000h
0x180032fa6  add     rsp, 38h
0x180032faa  pop     rdi
0x180032fab  pop     rsi
0x180032fac  pop     rbp
0x180032fad  pop     rbx
0x180032fae  retn
```
