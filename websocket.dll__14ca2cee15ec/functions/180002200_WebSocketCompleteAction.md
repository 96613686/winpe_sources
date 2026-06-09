# WebSocketCompleteAction

- ea: `0x180002200`
- end: `0x1800022a1`
- name: `WebSocketCompleteAction`
- size: `161`
- prototype: `void __fastcall(__int64, _DWORD *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002200`
- `0x18000872c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002292`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002292`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000222f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002268`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000222f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002268`

## pseudocode

```c
void __fastcall WebSocketCompleteAction(__int64 a1, _DWORD *a2, unsigned int a3)
{
  __int64 v6; // rbx
  struct _RTL_CRITICAL_SECTION *v7; // rcx

  WebSocket::VerifyCookie((WebSocket *)a1);
  if ( *(_DWORD *)(a1 + 4) == 6 && a2 )
  {
    v6 = *(_QWORD *)(a1 + 24);
    if ( a2[11] == 1 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)v6);
      --*(_DWORD *)(v6 + 432);
      (*(void (__fastcall **)(_DWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(a2, v6 + 80, a3);
      if ( !v6 )
        return;
      v7 = (struct _RTL_CRITICAL_SECTION *)v6;
      goto LABEL_9;
    }
    if ( !a2[11] )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 40));
      --*(_DWORD *)(v6 + 436);
      (*(void (__fastcall **)(_DWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(a2, v6 + 80, a3);
      if ( v6 != -40 )
      {
        v7 = (struct _RTL_CRITICAL_SECTION *)(v6 + 40);
LABEL_9:
        LeaveCriticalSection(v7);
      }
    }
  }
}

```

## disassembly

```asm
0x180002200  push    rbx
0x180002202  push    rbp
0x180002203  push    rsi
0x180002204  push    rdi
0x180002205  sub     rsp, 28h
0x180002209  mov     ebp, r8d
0x18000220c  mov     rdi, rdx
0x18000220f  mov     rbx, rcx
0x180002212  call    ?VerifyCookie@WebSocket@@AEAAXXZ; WebSocket::VerifyCookie(void)
0x180002217  cmp     dword ptr [rbx+4], 6
0x18000221b  jnz     short loc_180002298
0x18000221d  test    rdi, rdi
0x180002220  jz      short loc_180002298
0x180002222  cmp     dword ptr [rdi+2Ch], 1
0x180002226  mov     rbx, [rbx+18h]
0x18000222a  jnz     short loc_18000225B
0x18000222c  mov     rcx, rbx; lpCriticalSection
0x18000222f  call    cs:__imp_EnterCriticalSection
0x180002235  dec     dword ptr [rbx+1B0h]
0x18000223b  lea     rdx, [rbx+50h]
0x18000223f  mov     rax, [rdi]
0x180002242  mov     r8d, ebp
0x180002245  mov     rcx, rdi
0x180002248  mov     rax, [rax+8]
0x18000224c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002251  test    rbx, rbx
0x180002254  jz      short loc_180002298
0x180002256  mov     rcx, rbx
0x180002259  jmp     short loc_180002292
0x18000225b  cmp     dword ptr [rdi+2Ch], 0
0x18000225f  jnz     short loc_180002298
0x180002261  lea     rsi, [rbx+28h]
0x180002265  mov     rcx, rsi; lpCriticalSection
0x180002268  call    cs:__imp_EnterCriticalSection
0x18000226e  dec     dword ptr [rbx+1B4h]
0x180002274  lea     rdx, [rbx+50h]
0x180002278  mov     rax, [rdi]
0x18000227b  mov     r8d, ebp
0x18000227e  mov     rcx, rdi
0x180002281  mov     rax, [rax+8]
0x180002285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000228a  test    rsi, rsi
0x18000228d  jz      short loc_180002298
0x18000228f  mov     rcx, rsi; lpCriticalSection
0x180002292  call    cs:__imp_LeaveCriticalSection
0x180002298  add     rsp, 28h
0x18000229c  pop     rdi
0x18000229d  pop     rsi
0x18000229e  pop     rbp
0x18000229f  pop     rbx
0x1800022a0  retn
```
