# std::basic_ostream<wchar_t,std::char_traits<wchar_t>>::sentry::sentry(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &)

- ea: `0x18000957c`
- end: `0x180009605`
- name: `??0sentry@?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAA@AEAV12@@Z`
- size: `137`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180008f78`
- `0x180009320`
- `0x18000960c`
- `0x1800096f4`

## callees

- `0x18000957c`
- `0x18000960c`
- `0x1800148e0`

## pseudocode

```c
__int64 __fastcall std::wostream::sentry::sentry(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  bool v5; // di
  __int64 v6; // rcx
  __int64 v7; // rcx

  *(_QWORD *)a1 = a2;
  v4 = *(_QWORD *)(*(int *)(*(_QWORD *)a2 + 4LL) + a2 + 72);
  v5 = 0;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  v6 = *(int *)(*(_QWORD *)a2 + 4LL);
  if ( !*(_DWORD *)(v6 + a2 + 16) )
  {
    v7 = *(_QWORD *)(v6 + a2 + 80);
    if ( !v7 || v7 == a2 )
    {
      v5 = 1;
    }
    else
    {
      std::wostream::flush(v7);
      v5 = *(_DWORD *)(*(int *)(*(_QWORD *)a2 + 4LL) + a2 + 16) == 0;
    }
  }
  *(_BYTE *)(a1 + 8) = v5;
  return a1;
}

```

## disassembly

```asm
0x18000957c  mov     [rsp+arg_8], rbx
0x180009581  mov     [rsp+arg_10], rsi
0x180009586  mov     [rsp+arg_0], rcx
0x18000958b  push    rdi
0x18000958c  sub     rsp, 20h
0x180009590  mov     rbx, rdx
0x180009593  mov     rsi, rcx
0x180009596  mov     [rcx], rdx
0x180009599  mov     rax, [rdx]
0x18000959c  movsxd  r8, dword ptr [rax+4]
0x1800095a0  mov     rcx, [r8+rdx+48h]
0x1800095a5  xor     edi, edi
0x1800095a7  test    rcx, rcx
0x1800095aa  jz      short loc_1800095B9
0x1800095ac  mov     rax, [rcx]
0x1800095af  mov     rax, [rax+8]
0x1800095b3  call    _guard_dispatch_icall
0x1800095b8  nop
0x1800095b9  mov     rax, [rbx]
0x1800095bc  movsxd  rcx, dword ptr [rax+4]
0x1800095c0  cmp     [rcx+rbx+10h], edi
0x1800095c4  jnz     short loc_1800095EE
0x1800095c6  mov     rcx, [rcx+rbx+50h]
0x1800095cb  test    rcx, rcx
0x1800095ce  jz      short loc_1800095EB
0x1800095d0  cmp     rcx, rbx
0x1800095d3  jz      short loc_1800095EB
0x1800095d5  call    ?flush@?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV12@XZ; std::wostream::flush(void)
0x1800095da  mov     rax, [rbx]
0x1800095dd  movsxd  rcx, dword ptr [rax+4]
0x1800095e1  cmp     [rcx+rbx+10h], edi
0x1800095e5  setz    dil
0x1800095e9  jmp     short loc_1800095EE
0x1800095eb  mov     dil, 1
0x1800095ee  mov     [rsi+8], dil
0x1800095f2  mov     rax, rsi
0x1800095f5  mov     rbx, [rsp+28h+arg_8]
0x1800095fa  mov     rsi, [rsp+28h+arg_10]
0x1800095ff  add     rsp, 20h
0x180009603  pop     rdi
0x180009604  retn
```
