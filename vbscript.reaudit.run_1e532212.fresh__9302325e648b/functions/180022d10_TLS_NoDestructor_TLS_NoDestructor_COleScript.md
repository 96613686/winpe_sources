# TLS_NoDestructor::TLS_NoDestructor(COleScript *)

- ea: `0x180022d10`
- end: `0x180022dfd`
- name: `??0TLS_NoDestructor@@QEAA@PEAVCOleScript@@@Z`
- size: `237`
- prototype: `TLS_NoDestructor *__fastcall(TLS_NoDestructor *__hidden this, struct COleScript *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18003ff0c`
- `0x180042c64`
- `0x18006b020`
- `0x180073b6c`

## callees

- `0x180022d10`
- `0x180022e04`
- `0x180022e44`
- `0x180077010`

## import_xrefs

- `msvcrt!_statusfp` at `0x180022d52`
- `msvcrt!_statusfp` at `0x180022d52`
- `msvcrt!_clearfp` at `0x180022df2`
- `msvcrt!_clearfp` at `0x180022df2`
- `KERNEL32!TlsGetValue` at `0x180022d26`
- `KERNEL32!TlsGetValue` at `0x180022d26`
- `KERNEL32!GetCurrentThreadId` at `0x180022d84`
- `KERNEL32!GetCurrentThreadId` at `0x180022d84`
- `KERNEL32!LeaveCriticalSection` at `0x180022dcf`
- `KERNEL32!LeaveCriticalSection` at `0x180022dcf`

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
0x180022d10  mov     [rsp+arg_8], rbx
0x180022d15  push    rdi
0x180022d16  sub     rsp, 20h
0x180022d1a  mov     rbx, rcx
0x180022d1d  mov     rdi, rdx
0x180022d20  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180022d26  call    cs:__imp_TlsGetValue
0x180022d2c  mov     [rbx], rax
0x180022d2f  test    rax, rax
0x180022d32  jz      short loc_180022D60
0x180022d34  mov     rcx, [rax+18h]
0x180022d38  mov     [rbx+10h], rcx
0x180022d3c  mov     [rbx+8], rdi
0x180022d40  cmp     rcx, rdi
0x180022d43  jz      short loc_180022D52
0x180022d45  mov     [rax+18h], rdi
0x180022d49  mov     rax, [rbx+8]
0x180022d4d  test    rax, rax
0x180022d50  jnz     short loc_180022D6E
0x180022d52  call    cs:__imp__statusfp
0x180022d58  test    eax, eax
0x180022d5a  jnz     loc_180022DF2
0x180022d60  mov     rax, rbx
0x180022d63  mov     rbx, [rsp+28h+arg_8]
0x180022d68  add     rsp, 20h
0x180022d6c  pop     rdi
0x180022d6d  retn
0x180022d6e  mov     [rsp+28h+arg_0], rsi
0x180022d73  lock inc dword ptr [rax+94h]
0x180022d7a  mov     rsi, [rbx+8]
0x180022d7e  mov     edi, [rsi+0F4h]
0x180022d84  call    cs:__imp_GetCurrentThreadId
0x180022d8a  cmp     eax, edi
0x180022d8c  jnz     short loc_180022DE8
0x180022d8e  mov     rcx, rsi; this
0x180022d91  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x180022d96  test    eax, eax
0x180022d98  jz      short loc_180022DE8
0x180022d9a  inc     dword ptr [rsi+110h]
0x180022da0  cmp     dword ptr [rsi+110h], 1
0x180022da7  mov     dword ptr [rsi+10Ch], 1
0x180022db1  jnz     short loc_180022DBF
0x180022db3  lea     rcx, [rsi+240h]; struct tagEXCEPINFO *
0x180022dba  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x180022dbf  cmp     dword ptr [rsi+210h], 0
0x180022dc6  jz      short loc_180022DD5
0x180022dc8  lea     rcx, [rsi+218h]; lpCriticalSection
0x180022dcf  call    cs:__imp_LeaveCriticalSection
0x180022dd5  mov     rcx, [rsi+0A0h]
0x180022ddc  mov     rax, [rcx]
0x180022ddf  mov     rax, [rax+48h]
0x180022de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022de8  mov     rsi, [rsp+28h+arg_0]
0x180022ded  jmp     loc_180022D52
0x180022df2  call    cs:__imp__clearfp
0x180022df8  jmp     loc_180022D60
```
