# TLS_NoDestructor::TLS_NoDestructor(COleScript *)

- ea: `0x18001e1d0`
- end: `0x18001e2dc`
- name: `??0TLS_NoDestructor@@QEAA@PEAVCOleScript@@@Z`
- size: `268`
- prototype: `TLS_NoDestructor *__fastcall(TLS_NoDestructor *__hidden this, struct COleScript *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180041644`
- `0x18006d184`
- `0x180076120`
- `0x1800763f8`

## callees

- `0x18001e1d0`
- `0x18001e2e4`
- `0x18001e32c`
- `0x18007a010`

## import_xrefs

- `msvcrt!_statusfp` at `0x18001e218`
- `msvcrt!_statusfp` at `0x18001e218`
- `msvcrt!_clearfp` at `0x18001e2cb`
- `msvcrt!_clearfp` at `0x18001e2cb`
- `KERNEL32!TlsGetValue` at `0x18001e1e6`
- `KERNEL32!TlsGetValue` at `0x18001e1e6`
- `KERNEL32!GetCurrentThreadId` at `0x18001e251`
- `KERNEL32!GetCurrentThreadId` at `0x18001e251`
- `KERNEL32!LeaveCriticalSection` at `0x18001e2a2`
- `KERNEL32!LeaveCriticalSection` at `0x18001e2a2`

## pseudocode

```c
TLS_NoDestructor *__fastcall TLS_NoDestructor::TLS_NoDestructor(TLS_NoDestructor *this, struct COleScript *a2)
{
  LPVOID Value; // rax
  struct COleScript *v5; // rcx
  __int64 v6; // rax
  __int64 v8; // rsi
  int v9; // edi
  bool v10; // zf

  Value = TlsGetValue(g_luTls);
  *(_QWORD *)this = Value;
  if ( Value )
  {
    v5 = (struct COleScript *)*((_QWORD *)Value + 3);
    *((_QWORD *)this + 2) = v5;
    *((_QWORD *)this + 1) = a2;
    if ( v5 != a2 )
    {
      *((_QWORD *)Value + 3) = a2;
      v6 = *((_QWORD *)this + 1);
      if ( v6 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v6 + 148));
        v8 = *((_QWORD *)this + 1);
        v9 = *(_DWORD *)(v8 + 244);
        if ( GetCurrentThreadId() == v9 )
        {
          if ( (unsigned int)COleScript::DisableInterrupts((COleScript *)v8) )
          {
            v10 = ++*(_DWORD *)(v8 + 272) == 1;
            *(_DWORD *)(v8 + 268) = 1;
            if ( v10 )
              FreeExcepInfo((struct tagEXCEPINFO *)(v8 + 576));
            if ( *(_DWORD *)(v8 + 528) )
              LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 536));
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v8 + 160) + 72LL))(*(_QWORD *)(v8 + 160));
          }
        }
      }
    }
    if ( _statusfp() )
      _clearfp();
  }
  return this;
}

```

## disassembly

```asm
0x18001e1d0  mov     [rsp+arg_8], rbx
0x18001e1d5  push    rdi
0x18001e1d6  sub     rsp, 20h
0x18001e1da  mov     rbx, rcx
0x18001e1dd  mov     rdi, rdx
0x18001e1e0  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18001e1e6  call    cs:__imp_TlsGetValue
0x18001e1ed  nop     dword ptr [rax+rax+00h]
0x18001e1f2  mov     [rbx], rax
0x18001e1f5  test    rax, rax
0x18001e1f8  jz      short loc_18001E22C
0x18001e1fa  mov     rcx, [rax+18h]
0x18001e1fe  mov     [rbx+10h], rcx
0x18001e202  mov     [rbx+8], rdi
0x18001e206  cmp     rcx, rdi
0x18001e209  jz      short loc_18001E218
0x18001e20b  mov     [rax+18h], rdi
0x18001e20f  mov     rax, [rbx+8]
0x18001e213  test    rax, rax
0x18001e216  jnz     short loc_18001E23B
0x18001e218  call    cs:__imp__statusfp
0x18001e21f  nop     dword ptr [rax+rax+00h]
0x18001e224  test    eax, eax
0x18001e226  jnz     loc_18001E2CB
0x18001e22c  mov     rax, rbx
0x18001e22f  mov     rbx, [rsp+28h+arg_8]
0x18001e234  add     rsp, 20h
0x18001e238  pop     rdi
0x18001e239  retn
0x18001e23b  mov     [rsp+28h+arg_0], rsi
0x18001e240  lock inc dword ptr [rax+94h]
0x18001e247  mov     rsi, [rbx+8]
0x18001e24b  mov     edi, [rsi+0F4h]
0x18001e251  call    cs:__imp_GetCurrentThreadId
0x18001e258  nop     dword ptr [rax+rax+00h]
0x18001e25d  cmp     eax, edi
0x18001e25f  jnz     short loc_18001E2C1
0x18001e261  mov     rcx, rsi; this
0x18001e264  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x18001e269  test    eax, eax
0x18001e26b  jz      short loc_18001E2C1
0x18001e26d  inc     dword ptr [rsi+110h]
0x18001e273  cmp     dword ptr [rsi+110h], 1
0x18001e27a  mov     dword ptr [rsi+10Ch], 1
0x18001e284  jnz     short loc_18001E292
0x18001e286  lea     rcx, [rsi+240h]; struct tagEXCEPINFO *
0x18001e28d  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x18001e292  cmp     dword ptr [rsi+210h], 0
0x18001e299  jz      short loc_18001E2AE
0x18001e29b  lea     rcx, [rsi+218h]; lpCriticalSection
0x18001e2a2  call    cs:__imp_LeaveCriticalSection
0x18001e2a9  nop     dword ptr [rax+rax+00h]
0x18001e2ae  mov     rcx, [rsi+0A0h]
0x18001e2b5  mov     rax, [rcx]
0x18001e2b8  mov     rax, [rax+48h]
0x18001e2bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2c1  mov     rsi, [rsp+28h+arg_0]
0x18001e2c6  jmp     loc_18001E218
0x18001e2cb  call    cs:__imp__clearfp
0x18001e2d2  nop     dword ptr [rax+rax+00h]
0x18001e2d7  jmp     loc_18001E22C
```
