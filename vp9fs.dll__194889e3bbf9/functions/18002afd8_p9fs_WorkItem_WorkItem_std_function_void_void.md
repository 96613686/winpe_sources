# p9fs::WorkItem::WorkItem(std::function<void (void)>)

- ea: `0x18002afd8`
- end: `0x18002b08d`
- name: `??0WorkItem@p9fs@@QEAA@V?$function@$$A6AXXZ@std@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002f40`

## callees

- `0x1800286fc`
- `0x18002afd8`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002b006`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002b006`

## string_xrefs

- `0x18002b07b`: `onecore\vm\dv\storage\plan9\dll\windows\p9windows.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char *__fastcall p9fs::WorkItem::WorkItem(char *pv, __int64 a2)
{
  __int64 v4; // rdx
  const char *v5; // r9
  __int64 (__fastcall ***v6)(_QWORD, char *); // rcx
  __int64 v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)pv = &p9fs::WorkItem::`vftable';
  *((_QWORD *)pv + 1) = CreateThreadpoolWork(p9fs::WorkItem::WorkerCallback, pv, 0);
  *((_QWORD *)pv + 9) = 0;
  v6 = *(__int64 (__fastcall ****)(_QWORD, char *))(a2 + 56);
  if ( v6 )
    *((_QWORD *)pv + 9) = (**v6)(v6, pv + 16);
  if ( !*((_QWORD *)pv + 1) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9windows.cpp",
      v5);
  v7 = *(_QWORD *)(a2 + 56);
  if ( v7 )
  {
    LOBYTE(v4) = v7 != a2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 32LL))(v7, v4);
    *(_QWORD *)(a2 + 56) = 0;
  }
  return pv;
}

```

## disassembly

```asm
0x18002afd8  mov     [rsp+arg_8], rdx
0x18002afdd  mov     [rsp+arg_0], rcx
0x18002afe2  push    rbx
0x18002afe3  push    rsi
0x18002afe4  push    rdi
0x18002afe5  sub     rsp, 20h
0x18002afe9  mov     rdi, rdx
0x18002afec  mov     rbx, rcx
0x18002afef  lea     rax, ??_7WorkItem@p9fs@@6B@; const p9fs::WorkItem::`vftable'
0x18002aff6  mov     [rcx], rax
0x18002aff9  xor     r8d, r8d; pcbe
0x18002affc  mov     rdx, rcx; pv
0x18002afff  lea     rcx, ?WorkerCallback@WorkItem@p9fs@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002b006  call    cs:__imp_CreateThreadpoolWork
0x18002b00c  mov     [rbx+8], rax
0x18002b010  lea     rsi, [rbx+10h]
0x18002b014  mov     [rsp+38h+arg_10], rsi
0x18002b019  mov     qword ptr [rsi+38h], 0
0x18002b021  mov     rcx, [rdi+38h]
0x18002b025  test    rcx, rcx
0x18002b028  jz      short loc_18002B03C
0x18002b02a  mov     rax, [rcx]
0x18002b02d  mov     rdx, rsi
0x18002b030  mov     rax, [rax]
0x18002b033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b038  mov     [rsi+38h], rax
0x18002b03c  cmp     qword ptr [rbx+8], 0
0x18002b041  setz    al
0x18002b044  mov     rcx, [rsp+38h]; this
0x18002b049  test    al, al
0x18002b04b  jnz     short loc_18002B07B
0x18002b04d  mov     rcx, [rdi+38h]
0x18002b051  test    rcx, rcx
0x18002b054  jz      short loc_18002B070
0x18002b056  mov     rax, [rcx]
0x18002b059  cmp     rcx, rdi
0x18002b05c  setnz   dl
0x18002b05f  mov     rax, [rax+20h]
0x18002b063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b068  mov     qword ptr [rdi+38h], 0
0x18002b070  mov     rax, rbx
0x18002b073  add     rsp, 20h
0x18002b077  pop     rdi
0x18002b078  pop     rsi
0x18002b079  pop     rbx
0x18002b07a  retn
0x18002b07b  lea     r8, aOnecoreVmDvSto_9; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002b082  mov     edx, 5Eh ; '^'; void *
0x18002b087  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
