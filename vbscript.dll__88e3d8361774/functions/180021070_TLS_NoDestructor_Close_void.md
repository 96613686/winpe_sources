# TLS_NoDestructor::Close(void)

- ea: `0x180021070`
- end: `0x18002114d`
- name: `?Close@TLS_NoDestructor@@QEAAXXZ`
- size: `221`
- prototype: `void __fastcall(TLS_NoDestructor *__hidden this)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x180004ad0`
- `0x180006230`
- `0x180023950`
- `0x18003ff0c`
- `0x180042c64`
- `0x1800664f8`
- `0x18006b020`
- `0x180073b6c`

## callees

- `0x180021070`
- `0x180022e04`
- `0x1800238b0`
- `0x180077010`

## import_xrefs

- `msvcrt!_statusfp` at `0x18002109e`
- `msvcrt!_statusfp` at `0x18002109e`
- `msvcrt!_clearfp` at `0x180021142`
- `msvcrt!_clearfp` at `0x180021142`
- `msvcrt!_controlfp` at `0x1800210c0`
- `KERNEL32!GetCurrentThreadId` at `0x1800210d8`
- `KERNEL32!GetCurrentThreadId` at `0x1800210d8`
- `KERNEL32!LeaveCriticalSection` at `0x18002112e`
- `KERNEL32!LeaveCriticalSection` at `0x18002112e`

## pseudocode

```c
void __fastcall TLS_NoDestructor::Close(TLS_NoDestructor *this)
{
  __int64 v2; // rsi
  int v3; // edi
  __int64 v4; // rcx

  if ( *(_QWORD *)this )
  {
    v2 = *((_QWORD *)this + 1);
    if ( *((_QWORD *)this + 2) != v2 && v2 )
    {
      v3 = *(_DWORD *)(v2 + 244);
      if ( GetCurrentThreadId() == v3 )
      {
        v4 = *(_QWORD *)(v2 + 160);
        if ( v4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 80LL))(v4);
        if ( (unsigned int)COleScript::DisableInterrupts((COleScript *)v2) )
        {
          if ( (*(_DWORD *)(v2 + 272))-- == 1 )
            *(_DWORD *)(v2 + 268) = 0;
          if ( *(_DWORD *)(v2 + 528) )
            LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 536));
        }
      }
      COleScript::Release(*((COleScript **)this + 1));
    }
    *(_QWORD *)(*(_QWORD *)this + 24LL) = *((_QWORD *)this + 2);
    if ( _statusfp() )
      _clearfp();
    _controlfp(0x1Fu, 0x30F031Fu);
  }
}

```

## disassembly

```asm
0x180021070  push    rbx
0x180021072  sub     rsp, 20h
0x180021076  cmp     qword ptr [rcx], 0
0x18002107a  mov     rbx, rcx
0x18002107d  jz      short loc_1800210C7
0x18002107f  mov     [rsp+28h+arg_8], rsi
0x180021084  mov     rsi, [rcx+8]
0x180021088  cmp     [rcx+10h], rsi
0x18002108c  jz      short loc_180021093
0x18002108e  test    rsi, rsi
0x180021091  jnz     short loc_1800210CD
0x180021093  mov     rcx, [rbx]
0x180021096  mov     rax, [rbx+10h]
0x18002109a  mov     [rcx+18h], rax
0x18002109e  call    cs:__imp__statusfp
0x1800210a4  mov     rsi, [rsp+28h+arg_8]
0x1800210a9  test    eax, eax
0x1800210ab  jnz     loc_180021142
0x1800210b1  mov     edx, 30F031Fh
0x1800210b6  mov     ecx, 1Fh
0x1800210bb  add     rsp, 20h
0x1800210bf  pop     rbx
0x1800210c0  jmp     cs:__imp__controlfp
0x1800210c7  add     rsp, 20h
0x1800210cb  pop     rbx
0x1800210cc  retn
0x1800210cd  mov     [rsp+28h+arg_10], rdi
0x1800210d2  mov     edi, [rsi+0F4h]
0x1800210d8  call    cs:__imp_GetCurrentThreadId
0x1800210de  cmp     eax, edi
0x1800210e0  mov     rdi, [rsp+28h+arg_10]
0x1800210e5  jnz     short loc_180021134
0x1800210e7  mov     rcx, [rsi+0A0h]
0x1800210ee  test    rcx, rcx
0x1800210f1  jz      short loc_1800210FF
0x1800210f3  mov     rax, [rcx]
0x1800210f6  mov     rax, [rax+50h]
0x1800210fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210ff  mov     rcx, rsi; this
0x180021102  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x180021107  test    eax, eax
0x180021109  jz      short loc_180021134
0x18002110b  add     dword ptr [rsi+110h], 0FFFFFFFFh
0x180021112  jnz     short loc_18002111E
0x180021114  mov     dword ptr [rsi+10Ch], 0
0x18002111e  cmp     dword ptr [rsi+210h], 0
0x180021125  jz      short loc_180021134
0x180021127  lea     rcx, [rsi+218h]; lpCriticalSection
0x18002112e  call    cs:__imp_LeaveCriticalSection
0x180021134  mov     rcx, [rbx+8]; this
0x180021138  call    ?Release@COleScript@@UEAAKXZ; COleScript::Release(void)
0x18002113d  jmp     loc_180021093
0x180021142  call    cs:__imp__clearfp
0x180021148  jmp     loc_1800210B1
```
