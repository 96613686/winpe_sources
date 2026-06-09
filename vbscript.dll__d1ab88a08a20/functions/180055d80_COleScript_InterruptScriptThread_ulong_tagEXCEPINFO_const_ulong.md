# COleScript::InterruptScriptThread(ulong,tagEXCEPINFO const *,ulong)

- ea: `0x180055d80`
- end: `0x180055e4d`
- name: `?InterruptScriptThread@COleScript@@UEAAJKPEBUtagEXCEPINFO@@K@Z`
- size: `205`
- prototype: `__int64 __fastcall(COleScript *__hidden this, unsigned int, const struct tagEXCEPINFO *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180013708`
- `0x18001e2e4`
- `0x18001e32c`
- `0x180055d80`
- `0x180061068`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180055d96`
- `KERNEL32!GetCurrentThreadId` at `0x180055d96`

## pseudocode

```c
__int64 __fastcall COleScript::InterruptScriptThread(
        struct tagEXCEPINFO *this,
        DWORD CurrentThreadId,
        const struct tagEXCEPINFO *a3)
{
  int pfnDeferredFillIn_high; // eax
  unsigned int v7; // ebx
  __int64 v8; // rax

  if ( CurrentThreadId == -1 )
  {
    CurrentThreadId = GetCurrentThreadId();
  }
  else if ( CurrentThreadId + 3 <= 1 )
  {
    CurrentThreadId = HIDWORD(this[3].pfnDeferredFillIn);
  }
  pfnDeferredFillIn_high = HIDWORD(this[3].pfnDeferredFillIn);
  if ( pfnDeferredFillIn_high == -1 )
    return 2147549183LL;
  if ( CurrentThreadId != pfnDeferredFillIn_high )
    return 2147942487LL;
  if ( !(unsigned int)COleScript::DisableInterrupts((COleScript *)this) )
    return 2147500037LL;
  if ( HIDWORD(this[4].bstrSource) != 1 || *(_DWORD *)(*(_QWORD *)&this[10].wCode + 128LL) )
  {
    v7 = -2147024809;
  }
  else
  {
    v7 = 0;
    FreeExcepInfo(this + 9);
    if ( a3 )
      CopyException(this + 9, a3);
    v8 = *(_QWORD *)&this[10].wCode;
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 128));
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 132));
  }
  COleScript::EnableInterrupts((COleScript *)this);
  return v7;
}

```

## disassembly

```asm
0x180055d80  push    rbx
0x180055d82  push    rbp
0x180055d83  push    rsi
0x180055d84  push    rdi
0x180055d85  sub     rsp, 28h
0x180055d89  or      ebx, 0FFFFFFFFh
0x180055d8c  mov     rbp, r8
0x180055d8f  mov     rdi, rcx
0x180055d92  cmp     edx, ebx
0x180055d94  jnz     short loc_180055DA6
0x180055d96  call    cs:__imp_GetCurrentThreadId
0x180055d9d  nop     dword ptr [rax+rax+00h]
0x180055da2  mov     edx, eax
0x180055da4  jmp     short loc_180055DB4
0x180055da6  lea     eax, [rdx+3]
0x180055da9  cmp     eax, 1
0x180055dac  ja      short loc_180055DB4
0x180055dae  mov     edx, [rcx+0F4h]
0x180055db4  mov     eax, [rdi+0F4h]
0x180055dba  cmp     eax, ebx
0x180055dbc  jnz     short loc_180055DC5
0x180055dbe  mov     eax, 8000FFFFh
0x180055dc3  jmp     short loc_180055E43
0x180055dc5  cmp     edx, eax
0x180055dc7  jz      short loc_180055DD0
0x180055dc9  mov     eax, 80070057h
0x180055dce  jmp     short loc_180055E43
0x180055dd0  mov     rcx, rdi; this
0x180055dd3  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x180055dd8  test    eax, eax
0x180055dda  jnz     short loc_180055DE3
0x180055ddc  mov     eax, 80004005h
0x180055de1  jmp     short loc_180055E43
0x180055de3  cmp     dword ptr [rdi+10Ch], 1
0x180055dea  jnz     short loc_180055E34
0x180055dec  mov     rax, [rdi+280h]
0x180055df3  cmp     dword ptr [rax+80h], 0
0x180055dfa  jnz     short loc_180055E34
0x180055dfc  lea     rsi, [rdi+240h]
0x180055e03  xor     ebx, ebx
0x180055e05  mov     rcx, rsi; struct tagEXCEPINFO *
0x180055e08  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x180055e0d  test    rbp, rbp
0x180055e10  jz      short loc_180055E1D
0x180055e12  mov     rdx, rbp; struct tagEXCEPINFO *
0x180055e15  mov     rcx, rsi; struct tagEXCEPINFO *
0x180055e18  call    ?CopyException@@YAXPEAUtagEXCEPINFO@@PEBU1@@Z; CopyException(tagEXCEPINFO *,tagEXCEPINFO const *)
0x180055e1d  mov     rax, [rdi+280h]
0x180055e24  lock inc dword ptr [rax+80h]
0x180055e2b  lock inc dword ptr [rax+84h]
0x180055e32  jmp     short loc_180055E39
0x180055e34  mov     ebx, 80070057h
0x180055e39  mov     rcx, rdi; this
0x180055e3c  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x180055e41  mov     eax, ebx
0x180055e43  add     rsp, 28h
0x180055e47  pop     rdi
0x180055e48  pop     rsi
0x180055e49  pop     rbp
0x180055e4a  pop     rbx
0x180055e4b  retn
```
