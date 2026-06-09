# COleScript::InterruptScriptThread(ulong,tagEXCEPINFO const *,ulong)

- ea: `0x180054480`
- end: `0x180054546`
- name: `?InterruptScriptThread@COleScript@@UEAAJKPEBUtagEXCEPINFO@@K@Z`
- size: `198`
- prototype: `__int64 __fastcall(COleScript *__hidden this, unsigned int, const struct tagEXCEPINFO *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180018b50`
- `0x180022e04`
- `0x180022e44`
- `0x180054480`
- `0x18005f3f8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180054496`
- `KERNEL32!GetCurrentThreadId` at `0x180054496`

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
0x180054480  push    rbx
0x180054482  push    rbp
0x180054483  push    rsi
0x180054484  push    rdi
0x180054485  sub     rsp, 28h
0x180054489  or      ebx, 0FFFFFFFFh
0x18005448c  mov     rbp, r8
0x18005448f  mov     rdi, rcx
0x180054492  cmp     edx, ebx
0x180054494  jnz     short loc_1800544A0
0x180054496  call    cs:__imp_GetCurrentThreadId
0x18005449c  mov     edx, eax
0x18005449e  jmp     short loc_1800544AE
0x1800544a0  lea     eax, [rdx+3]
0x1800544a3  cmp     eax, 1
0x1800544a6  ja      short loc_1800544AE
0x1800544a8  mov     edx, [rcx+0F4h]
0x1800544ae  mov     eax, [rdi+0F4h]
0x1800544b4  cmp     eax, ebx
0x1800544b6  jnz     short loc_1800544BF
0x1800544b8  mov     eax, 8000FFFFh
0x1800544bd  jmp     short loc_18005453D
0x1800544bf  cmp     edx, eax
0x1800544c1  jz      short loc_1800544CA
0x1800544c3  mov     eax, 80070057h
0x1800544c8  jmp     short loc_18005453D
0x1800544ca  mov     rcx, rdi; this
0x1800544cd  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x1800544d2  test    eax, eax
0x1800544d4  jnz     short loc_1800544DD
0x1800544d6  mov     eax, 80004005h
0x1800544db  jmp     short loc_18005453D
0x1800544dd  cmp     dword ptr [rdi+10Ch], 1
0x1800544e4  jnz     short loc_18005452E
0x1800544e6  mov     rax, [rdi+280h]
0x1800544ed  cmp     dword ptr [rax+80h], 0
0x1800544f4  jnz     short loc_18005452E
0x1800544f6  lea     rsi, [rdi+240h]
0x1800544fd  xor     ebx, ebx
0x1800544ff  mov     rcx, rsi; struct tagEXCEPINFO *
0x180054502  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x180054507  test    rbp, rbp
0x18005450a  jz      short loc_180054517
0x18005450c  mov     rdx, rbp; struct tagEXCEPINFO *
0x18005450f  mov     rcx, rsi; struct tagEXCEPINFO *
0x180054512  call    ?CopyException@@YAXPEAUtagEXCEPINFO@@PEBU1@@Z; CopyException(tagEXCEPINFO *,tagEXCEPINFO const *)
0x180054517  mov     rax, [rdi+280h]
0x18005451e  lock inc dword ptr [rax+80h]
0x180054525  lock inc dword ptr [rax+84h]
0x18005452c  jmp     short loc_180054533
0x18005452e  mov     ebx, 80070057h
0x180054533  mov     rcx, rdi; this
0x180054536  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x18005453b  mov     eax, ebx
0x18005453d  add     rsp, 28h
0x180054541  pop     rdi
0x180054542  pop     rsi
0x180054543  pop     rbp
0x180054544  pop     rbx
0x180054545  retn
```
