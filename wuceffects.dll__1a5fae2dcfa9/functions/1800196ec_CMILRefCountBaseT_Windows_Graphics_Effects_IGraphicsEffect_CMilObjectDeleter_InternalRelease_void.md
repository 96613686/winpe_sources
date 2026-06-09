# CMILRefCountBaseT<Windows::Graphics::Effects::IGraphicsEffect,CMilObjectDeleter>::InternalRelease(void)

- ea: `0x1800196ec`
- end: `0x1800197ec`
- name: `?InternalRelease@?$CMILRefCountBaseT@UIGraphicsEffect@Effects@Graphics@Windows@@VCMilObjectDeleter@@@@IEAAKXZ`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800196e0`

## callees

- `0x1800196ec`
- `0x18002b594`
- `0x18002e010`

## string_xrefs

- `0x180019773`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x180019791`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x1800197af`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x1800197d0`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`

## pseudocode

```c
__int64 __fastcall CMILRefCountBaseT<Windows::Graphics::Effects::IGraphicsEffect,CMilObjectDeleter>::InternalRelease(
        volatile signed __int32 *a1)
{
  int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = _InterlockedDecrement(a1 + 2);
  if ( v2 < -1 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v4);
  if ( !v2 )
  {
    if ( _InterlockedAdd(a1 + 2, 1u) <= 0 )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
        (const char *)0x8007029CLL,
        v4);
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)a1 + 72LL))(a1);
    v2 = _InterlockedDecrement(a1 + 2);
    if ( v2 < -1 )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
        (const char *)0x8007029CLL,
        v4);
    if ( !v2 )
    {
      if ( _InterlockedDecrement(a1 + 2) < -1 )
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x26,
          (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
          (const char *)0x8007029CLL,
          v4);
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 64LL))(a1, 1);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800196ec  mov     [rsp+arg_0], rbx
0x1800196f1  mov     [rsp+arg_8], rsi
0x1800196f6  push    rdi; int
0x1800196f7  sub     rsp, 20h
0x1800196fb  or      esi, 0FFFFFFFFh
0x1800196fe  mov     rdi, rcx
0x180019701  mov     ebx, esi
0x180019703  lock xadd [rcx+8], ebx
0x180019708  add     ebx, esi
0x18001970a  cmp     ebx, esi
0x18001970c  jl      short loc_18001976E
0x18001970e  test    ebx, ebx
0x180019710  jz      short loc_180019724
0x180019712  mov     rsi, [rsp+28h+arg_8]
0x180019717  mov     eax, ebx
0x180019719  mov     rbx, [rsp+28h+arg_0]
0x18001971e  add     rsp, 20h
0x180019722  pop     rdi
0x180019723  retn
0x180019724  lock add dword ptr [rdi+8], 1
0x180019729  jle     short loc_18001978C
0x18001972b  mov     rax, [rdi]
0x18001972e  mov     rcx, rdi
0x180019731  mov     rax, [rax+48h]
0x180019735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001973a  mov     ebx, esi
0x18001973c  lock xadd [rdi+8], ebx
0x180019741  add     ebx, esi
0x180019743  cmp     ebx, esi
0x180019745  jl      short loc_1800197AA
0x180019747  test    ebx, ebx
0x180019749  jnz     short loc_180019712
0x18001974b  mov     eax, esi
0x18001974d  lock xadd [rdi+8], eax
0x180019752  add     eax, esi
0x180019754  cmp     eax, esi
0x180019756  jl      short loc_1800197CB
0x180019758  mov     rax, [rdi]
0x18001975b  mov     edx, 1
0x180019760  mov     rcx, rdi
0x180019763  mov     rax, [rax+40h]
0x180019767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001976c  jmp     short loc_180019712
0x18001976e  mov     rcx, [rsp+28h]; this
0x180019773  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x18001977a  mov     r9d, 8007029Ch; char *
0x180019780  mov     edx, 26h ; '&'; void *
0x180019785  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001978a  jmp     short loc_18001970E
0x18001978c  mov     rcx, [rsp+28h]; this
0x180019791  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x180019798  mov     r9d, 8007029Ch; char *
0x18001979e  mov     edx, 18h; void *
0x1800197a3  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800197a8  jmp     short loc_18001972B
0x1800197aa  mov     rcx, [rsp+28h]; this
0x1800197af  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800197b6  mov     r9d, 8007029Ch; char *
0x1800197bc  mov     edx, 26h ; '&'; void *
0x1800197c1  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800197c6  jmp     loc_180019747
0x1800197cb  mov     rcx, [rsp+28h]; this
0x1800197d0  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800197d7  mov     r9d, 8007029Ch; char *
0x1800197dd  mov     edx, 26h ; '&'; void *
0x1800197e2  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800197e7  jmp     loc_180019758
```
