# TLS_NoDestructor::Close(void)

- ea: `0x18001ca30`
- end: `0x18001cb2b`
- name: `?Close@TLS_NoDestructor@@QEAAXXZ`
- size: `251`
- prototype: `void __fastcall(TLS_NoDestructor *__hidden this)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x1800040a0`
- `0x18001c5c0`
- `0x18001ef50`
- `0x180041644`
- `0x1800683d8`
- `0x18006d184`
- `0x180076120`
- `0x1800763f8`

## callees

- `0x18001ca30`
- `0x18001e2e4`
- `0x18001ecc0`
- `0x18007a010`

## import_xrefs

- `msvcrt!_statusfp` at `0x18001ca5e`
- `msvcrt!_statusfp` at `0x18001ca5e`
- `msvcrt!_clearfp` at `0x18001cb1a`
- `msvcrt!_clearfp` at `0x18001cb1a`
- `msvcrt!_controlfp` at `0x18001ca86`
- `KERNEL32!GetCurrentThreadId` at `0x18001caa4`
- `KERNEL32!GetCurrentThreadId` at `0x18001caa4`
- `KERNEL32!LeaveCriticalSection` at `0x18001cb00`
- `KERNEL32!LeaveCriticalSection` at `0x18001cb00`

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
0x18001ca30  push    rbx
0x18001ca32  sub     rsp, 20h
0x18001ca36  cmp     qword ptr [rcx], 0
0x18001ca3a  mov     rbx, rcx
0x18001ca3d  jz      short loc_18001CA92
0x18001ca3f  mov     [rsp+28h+arg_8], rsi
0x18001ca44  mov     rsi, [rcx+8]
0x18001ca48  cmp     [rcx+10h], rsi
0x18001ca4c  jz      short loc_18001CA53
0x18001ca4e  test    rsi, rsi
0x18001ca51  jnz     short loc_18001CA99
0x18001ca53  mov     rcx, [rbx]
0x18001ca56  mov     rax, [rbx+10h]
0x18001ca5a  mov     [rcx+18h], rax
0x18001ca5e  call    cs:__imp__statusfp
0x18001ca65  nop     dword ptr [rax+rax+00h]
0x18001ca6a  mov     rsi, [rsp+28h+arg_8]
0x18001ca6f  test    eax, eax
0x18001ca71  jnz     loc_18001CB1A
0x18001ca77  mov     edx, 30F031Fh
0x18001ca7c  mov     ecx, 1Fh
0x18001ca81  add     rsp, 20h
0x18001ca85  pop     rbx
0x18001ca86  jmp     cs:__imp__controlfp
0x18001ca92  add     rsp, 20h
0x18001ca96  pop     rbx
0x18001ca97  retn
0x18001ca99  mov     [rsp+28h+arg_10], rdi
0x18001ca9e  mov     edi, [rsi+0F4h]
0x18001caa4  call    cs:__imp_GetCurrentThreadId
0x18001caab  nop     dword ptr [rax+rax+00h]
0x18001cab0  cmp     eax, edi
0x18001cab2  mov     rdi, [rsp+28h+arg_10]
0x18001cab7  jnz     short loc_18001CB0C
0x18001cab9  mov     rcx, [rsi+0A0h]
0x18001cac0  test    rcx, rcx
0x18001cac3  jz      short loc_18001CAD1
0x18001cac5  mov     rax, [rcx]
0x18001cac8  mov     rax, [rax+50h]
0x18001cacc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cad1  mov     rcx, rsi; this
0x18001cad4  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x18001cad9  test    eax, eax
0x18001cadb  jz      short loc_18001CB0C
0x18001cadd  add     dword ptr [rsi+110h], 0FFFFFFFFh
0x18001cae4  jnz     short loc_18001CAF0
0x18001cae6  mov     dword ptr [rsi+10Ch], 0
0x18001caf0  cmp     dword ptr [rsi+210h], 0
0x18001caf7  jz      short loc_18001CB0C
0x18001caf9  lea     rcx, [rsi+218h]; lpCriticalSection
0x18001cb00  call    cs:__imp_LeaveCriticalSection
0x18001cb07  nop     dword ptr [rax+rax+00h]
0x18001cb0c  mov     rcx, [rbx+8]; this
0x18001cb10  call    ?Release@COleScript@@UEAAKXZ; COleScript::Release(void)
0x18001cb15  jmp     loc_18001CA53
0x18001cb1a  call    cs:__imp__clearfp
0x18001cb21  nop     dword ptr [rax+rax+00h]
0x18001cb26  jmp     loc_18001CA77
```
