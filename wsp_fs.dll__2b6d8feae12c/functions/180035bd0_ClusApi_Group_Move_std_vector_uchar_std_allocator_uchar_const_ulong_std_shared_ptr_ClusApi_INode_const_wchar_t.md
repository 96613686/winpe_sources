# ClusApi::Group::Move(std::vector<uchar,std::allocator<uchar>> const &,ulong,std::shared_ptr<ClusApi::INode> const &,wchar_t const *)

- ea: `0x180035bd0`
- end: `0x180035c49`
- name: `?Move@Group@ClusApi@@UEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@KAEBV?$shared_ptr@UINode@ClusApi@@@4@PEB_W@Z`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180035bd0`
- `0x1800a9010`

## import_xrefs

- `CLUSAPI!MoveClusterGroupEx2` at `0x180035c2e`
- `CLUSAPI!MoveClusterGroupEx2` at `0x180035c2e`

## string_xrefs

- `0x180035be1`: `cluswmiext!ClusApi::Group::Move`

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
0x180035bd0  push    rbx
0x180035bd2  push    rbp
0x180035bd3  push    rsi
0x180035bd4  push    rdi
0x180035bd5  sub     rsp, 38h
0x180035bd9  mov     rax, [rsp+58h+arg_20]
0x180035be1  lea     rbx, aCluswmiextClus_18; "cluswmiext!ClusApi::Group::Move"
0x180035be8  test    rax, rax
0x180035beb  mov     rbp, rcx
0x180035bee  mov     rcx, [r9]
0x180035bf1  mov     esi, r8d
0x180035bf4  cmovnz  rbx, rax
0x180035bf8  mov     rdi, rdx
0x180035bfb  test    rcx, rcx
0x180035bfe  jz      short loc_180035C14
0x180035c00  mov     rax, [rcx]
0x180035c03  mov     rax, [rax+98h]
0x180035c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c0f  mov     rdx, rax
0x180035c12  jmp     short loc_180035C16
0x180035c14  xor     edx, edx
0x180035c16  mov     eax, [rdi+8]
0x180035c19  mov     r8d, esi
0x180035c1c  sub     eax, [rdi]
0x180035c1e  mov     r9, [rdi]
0x180035c21  mov     rcx, [rbp+20h]
0x180035c25  mov     [rsp+58h+var_30], rbx
0x180035c2a  mov     [rsp+58h+var_38], eax
0x180035c2e  call    cs:__imp_MoveClusterGroupEx2
0x180035c34  test    eax, eax
0x180035c36  jle     short loc_180035C40
0x180035c38  movzx   eax, ax
0x180035c3b  or      eax, 80070000h
0x180035c40  add     rsp, 38h
0x180035c44  pop     rdi
0x180035c45  pop     rsi
0x180035c46  pop     rbp
0x180035c47  pop     rbx
0x180035c48  retn
```
