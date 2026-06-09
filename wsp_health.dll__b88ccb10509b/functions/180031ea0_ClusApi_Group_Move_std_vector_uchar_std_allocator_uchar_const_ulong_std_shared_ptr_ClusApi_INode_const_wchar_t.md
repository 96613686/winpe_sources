# ClusApi::Group::Move(std::vector<uchar,std::allocator<uchar>> const &,ulong,std::shared_ptr<ClusApi::INode> const &,wchar_t const *)

- ea: `0x180031ea0`
- end: `0x180031f19`
- name: `?Move@Group@ClusApi@@UEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@KAEBV?$shared_ptr@UINode@ClusApi@@@4@PEB_W@Z`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180031ea0`
- `0x18008c010`

## import_xrefs

- `CLUSAPI!MoveClusterGroupEx2` at `0x180031efe`
- `CLUSAPI!MoveClusterGroupEx2` at `0x180031efe`

## string_xrefs

- `0x180031eb1`: `cluswmiext!ClusApi::Group::Move`

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
0x180031ea0  push    rbx
0x180031ea2  push    rbp
0x180031ea3  push    rsi
0x180031ea4  push    rdi
0x180031ea5  sub     rsp, 38h
0x180031ea9  mov     rax, [rsp+58h+arg_20]
0x180031eb1  lea     rbx, aCluswmiextClus_18; "cluswmiext!ClusApi::Group::Move"
0x180031eb8  test    rax, rax
0x180031ebb  mov     rbp, rcx
0x180031ebe  mov     rcx, [r9]
0x180031ec1  mov     esi, r8d
0x180031ec4  cmovnz  rbx, rax
0x180031ec8  mov     rdi, rdx
0x180031ecb  test    rcx, rcx
0x180031ece  jz      short loc_180031EE4
0x180031ed0  mov     rax, [rcx]
0x180031ed3  mov     rax, [rax+98h]
0x180031eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031edf  mov     rdx, rax
0x180031ee2  jmp     short loc_180031EE6
0x180031ee4  xor     edx, edx
0x180031ee6  mov     eax, [rdi+8]
0x180031ee9  mov     r8d, esi
0x180031eec  sub     eax, [rdi]
0x180031eee  mov     r9, [rdi]
0x180031ef1  mov     rcx, [rbp+20h]
0x180031ef5  mov     [rsp+58h+var_30], rbx
0x180031efa  mov     [rsp+58h+var_38], eax
0x180031efe  call    cs:__imp_MoveClusterGroupEx2
0x180031f04  test    eax, eax
0x180031f06  jle     short loc_180031F10
0x180031f08  movzx   eax, ax
0x180031f0b  or      eax, 80070000h
0x180031f10  add     rsp, 38h
0x180031f14  pop     rdi
0x180031f15  pop     rsi
0x180031f16  pop     rbp
0x180031f17  pop     rbx
0x180031f18  retn
```
