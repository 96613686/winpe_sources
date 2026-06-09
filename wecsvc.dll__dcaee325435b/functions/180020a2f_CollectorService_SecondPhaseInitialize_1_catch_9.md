# _CollectorService::SecondPhaseInitialize_::_1_::catch$9

- ea: `0x180020a2f`
- end: `0x180020b6b`
- name: `_CollectorService::SecondPhaseInitialize_::_1_::catch$9`
- size: `316`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000696c`
- `0x180020a2f`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall CollectorService::SecondPhaseInitialize_::_1_::catch_9(__int64 a1, __int64 a2)
{
  __int64 (__fastcall ***v3)(_QWORD); // rbx
  char v4; // al
  int v5; // edx
  int v6; // r8d
  __int64 v7; // r9
  const wchar_t *v8; // rax
  const wchar_t *v9; // rcx
  __int64 v10; // rax

  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    v3 = *(__int64 (__fastcall ****)(_QWORD))(a2 + 104);
  }
  else
  {
    v3 = *(__int64 (__fastcall ****)(_QWORD))(a2 + 104);
    v4 = (**v3)(v3);
    LODWORD(v7) = a2 + 152;
    if ( *(_QWORD *)(a2 + 176) >= 8u )
      v7 = *(_QWORD *)(a2 + 152);
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, v7, v4);
  }
  *(_DWORD *)(a2 + 64) = (**v3)(v3);
  v8 = (const wchar_t *)(a2 + 152);
  if ( *(_QWORD *)(a2 + 176) >= 8u )
    v8 = *(const wchar_t **)(a2 + 152);
  v9 = &word_180026AD8;
  if ( v8 )
    v9 = v8;
  v10 = -1;
  do
    ++v10;
  while ( v9[v10] );
  *(_QWORD *)(a2 + 304) = v9;
  *(_DWORD *)(a2 + 312) = 2 * v10 + 2;
  *(_DWORD *)(a2 + 316) = 0;
  *(_QWORD *)(a2 + 320) = &word_180026AD8;
  *(_QWORD *)(a2 + 328) = 2;
  *(_QWORD *)(a2 + 336) = a2 + 64;
  *(_QWORD *)(a2 + 344) = 4;
  (*(void (__fastcall **)(_QWORD, __int64 *, __int64, __int64))(**(_QWORD **)(*(_QWORD *)(a2 + 80) + 16LL) + 8LL))(
    *(_QWORD *)(*(_QWORD *)(a2 + 80) + 16LL),
    EVTCOLL_SUBSCRIPTION_ACTIVATION_ERROR,
    3,
    a2 + 304);
  return 0;
}

```

## disassembly

```asm
0x180020a2f  mov     [rsp+arg_8], rdx
0x180020a34  push    rbx
0x180020a35  push    rbp
0x180020a36  sub     rsp, 48h
0x180020a3a  mov     rbp, rdx
0x180020a3d  lea     rcx, WPP_GLOBAL_Control
0x180020a44  mov     rax, cs:WPP_GLOBAL_Control
0x180020a4b  cmp     rax, rcx
0x180020a4e  jz      short loc_180020A9B
0x180020a50  test    byte ptr [rax+1Ch], 10h
0x180020a54  jz      short loc_180020A9B
0x180020a56  cmp     byte ptr [rax+19h], 2
0x180020a5a  jb      short loc_180020A9B
0x180020a5c  mov     rbx, [rbp+68h]
0x180020a60  mov     rax, [rbx]
0x180020a63  mov     rcx, rbx
0x180020a66  mov     rax, [rax]
0x180020a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a6e  lea     r9, [rbp+98h]
0x180020a75  cmp     qword ptr [rbp+0B0h], 8
0x180020a7d  cmovnb  r9, [rbp+98h]
0x180020a85  mov     [rsp+58h+var_38], eax
0x180020a89  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a90  mov     rcx, [rcx+10h]
0x180020a94  call    WPP_SF_SD
0x180020a99  jmp     short loc_180020A9F
0x180020a9b  mov     rbx, [rbp+68h]
0x180020a9f  mov     rax, [rbx]
0x180020aa2  mov     rcx, rbx
0x180020aa5  mov     rax, [rax]
0x180020aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020aad  mov     [rbp+40h], eax
0x180020ab0  lea     rax, [rbp+98h]
0x180020ab7  cmp     qword ptr [rbp+0B0h], 8
0x180020abf  cmovnb  rax, [rbp+98h]
0x180020ac7  lea     rcx, word_180026AD8
0x180020ace  test    rax, rax
0x180020ad1  cmovnz  rcx, rax
0x180020ad5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020ad9  inc     rax
0x180020adc  cmp     word ptr [rcx+rax*2], 0
0x180020ae1  jnz     short loc_180020AD9
0x180020ae3  mov     [rbp+130h], rcx
0x180020aea  lea     eax, ds:2[rax*2]
0x180020af1  mov     [rbp+138h], eax
0x180020af7  mov     dword ptr [rbp+13Ch], 0
0x180020b01  lea     rax, word_180026AD8
0x180020b08  mov     [rbp+140h], rax
0x180020b0f  mov     qword ptr [rbp+148h], 2
0x180020b1a  lea     rax, [rbp+40h]
0x180020b1e  mov     [rbp+150h], rax
0x180020b25  mov     qword ptr [rbp+158h], 4
0x180020b30  mov     rax, [rbp+50h]
0x180020b34  mov     rcx, [rax+10h]
0x180020b38  mov     rax, [rcx]
0x180020b3b  lea     r9, [rbp+130h]
0x180020b42  mov     r8d, 3
0x180020b48  lea     rdx, EVTCOLL_SUBSCRIPTION_ACTIVATION_ERROR
0x180020b4f  mov     rax, [rax+8]
0x180020b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b58  nop
0x180020b59  mov     rax, 0
0x180020b63  add     rsp, 48h
0x180020b67  pop     rbp
0x180020b68  pop     rbx
0x180020b69  retn
```
