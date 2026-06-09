# ClusApi::Group::Move(std::vector<uchar,std::allocator<uchar>> const &,ulong,std::shared_ptr<ClusApi::INode> const &,wchar_t const *)

- ea: `0x180036d70`
- end: `0x180036df0`
- name: `?Move@Group@ClusApi@@UEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@KAEBV?$shared_ptr@UINode@ClusApi@@@4@PEB_W@Z`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180036d70`
- `0x1800ab010`

## import_xrefs

- `CLUSAPI!MoveClusterGroupEx2` at `0x180036dce`
- `CLUSAPI!MoveClusterGroupEx2` at `0x180036dce`

## string_xrefs

- `0x180036d81`: `cluswmiext!ClusApi::Group::Move`

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
0x180036d70  push    rbx
0x180036d72  push    rbp
0x180036d73  push    rsi
0x180036d74  push    rdi
0x180036d75  sub     rsp, 38h
0x180036d79  mov     rax, [rsp+58h+arg_20]
0x180036d81  lea     rbx, aCluswmiextClus_18; "cluswmiext!ClusApi::Group::Move"
0x180036d88  test    rax, rax
0x180036d8b  mov     rbp, rcx
0x180036d8e  mov     rcx, [r9]
0x180036d91  mov     esi, r8d
0x180036d94  cmovnz  rbx, rax
0x180036d98  mov     rdi, rdx
0x180036d9b  test    rcx, rcx
0x180036d9e  jz      short loc_180036DB4
0x180036da0  mov     rax, [rcx]
0x180036da3  mov     rax, [rax+98h]
0x180036daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036daf  mov     rdx, rax
0x180036db2  jmp     short loc_180036DB6
0x180036db4  xor     edx, edx
0x180036db6  mov     eax, [rdi+8]
0x180036db9  mov     r8d, esi
0x180036dbc  sub     eax, [rdi]
0x180036dbe  mov     r9, [rdi]
0x180036dc1  mov     rcx, [rbp+20h]
0x180036dc5  mov     [rsp+58h+var_30], rbx
0x180036dca  mov     [rsp+58h+var_38], eax
0x180036dce  call    cs:__imp_MoveClusterGroupEx2
0x180036dd5  nop     dword ptr [rax+rax+00h]
0x180036dda  test    eax, eax
0x180036ddc  jle     short loc_180036DE6
0x180036dde  movzx   eax, ax
0x180036de1  or      eax, 80070000h
0x180036de6  add     rsp, 38h
0x180036dea  pop     rdi
0x180036deb  pop     rsi
0x180036dec  pop     rbp
0x180036ded  pop     rbx
0x180036dee  retn
```
