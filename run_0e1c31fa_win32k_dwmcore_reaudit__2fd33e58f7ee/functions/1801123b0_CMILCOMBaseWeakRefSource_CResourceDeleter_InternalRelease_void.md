# CMILCOMBaseWeakRefSource<CResourceDeleter>::InternalRelease(void)

- ea: `0x1801123b0`
- end: `0x1801124d7`
- name: `?InternalRelease@?$CMILCOMBaseWeakRefSource@VCResourceDeleter@@@@IEAAKXZ`
- size: `295`
- prototype: ``
- caller_count: `36`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b810`
- `0x18001bccc`
- `0x18001c33c`
- `0x1800a5cd4`
- `0x1800a672c`
- `0x1800f968c`
- `0x180111950`
- `0x180112f40`
- `0x180112fc0`
- `0x180112fdc`
- `0x180113610`
- `0x1801139cc`
- `0x180113b5c`
- `0x180120228`
- `0x180153f10`
- `0x180154b50`
- `0x18016fdf8`
- `0x18017a480`
- `0x180189268`
- `0x18018a038`
- `0x18018bc30`
- `0x1801a9a38`
- `0x1801bb230`
- `0x1801c82dc`
- `0x1801d83d8`
- `0x1801d9fa0`
- `0x1801de75c`
- `0x18020e24c`
- `0x1802139c0`
- `0x180216914`
- `0x18021a990`
- `0x1802272e0`
- `0x180251190`
- `0x180259874`
- `0x18026fc90`
- `0x18029af90`

## callees

- `0x1801123b0`
- `0x1801124e0`
- `0x180202b60`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801123fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801123fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801123d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801123d8`

## string_xrefs

- `0x180112422`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x180112447`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x1801124a0`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x1801124be`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`

## pseudocode

```c
__int64 __fastcall CMILCOMBaseWeakRefSource<CResourceDeleter>::InternalRelease(CResource *this)
{
  __int64 v1; // rbx
  int v3; // edi
  int v5; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = *((_QWORD *)this + 2);
  if ( v1 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v1 + 8LL))(*((_QWORD *)this + 2));
    EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 16));
  }
  v3 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( v3 < -1 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v5);
  if ( !v3 )
  {
    if ( _InterlockedAdd((volatile signed __int32 *)this + 2, 1u) <= 0 )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
        (const char *)0x8007029CLL,
        v5);
    (*(void (__fastcall **)(CResource *))(*(_QWORD *)this + 40LL))(this);
    v3 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
    if ( v3 < -1 )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
        (const char *)0x8007029CLL,
        v5);
    if ( !v3 )
    {
      if ( _InterlockedDecrement((volatile signed __int32 *)this + 2) < -1 )
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x26,
          (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
          (const char *)0x8007029CLL,
          v5);
      CResource::Delete(this);
    }
  }
  if ( v1 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 16));
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1801123b0  push    rbx
0x1801123b2  push    rbp
0x1801123b3  push    rsi
0x1801123b4  push    rdi
0x1801123b5  sub     rsp, 28h
0x1801123b9  mov     rbx, [rcx+10h]
0x1801123bd  mov     rsi, rcx
0x1801123c0  test    rbx, rbx
0x1801123c3  jz      short loc_1801123DE
0x1801123c5  mov     rax, [rbx]
0x1801123c8  mov     rcx, rbx
0x1801123cb  mov     rax, [rax+8]
0x1801123cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801123d4  lea     rcx, [rbx+10h]; lpCriticalSection
0x1801123d8  call    cs:__imp_EnterCriticalSection
0x1801123de  mov     ebp, 0FFFFFFFFh
0x1801123e3  mov     edi, ebp
0x1801123e5  lock xadd [rsi+8], edi
0x1801123ea  dec     edi
0x1801123ec  cmp     edi, ebp
0x1801123ee  jl      short loc_18011241D
0x1801123f0  test    edi, edi
0x1801123f2  jz      short loc_18011243B
0x1801123f4  test    rbx, rbx
0x1801123f7  jz      short loc_180112412
0x1801123f9  lea     rcx, [rbx+10h]; lpCriticalSection
0x1801123fd  call    cs:__imp_LeaveCriticalSection
0x180112403  mov     rcx, [rbx]
0x180112406  mov     rax, [rcx+10h]
0x18011240a  mov     rcx, rbx
0x18011240d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180112412  mov     eax, edi
0x180112414  add     rsp, 28h
0x180112418  pop     rdi
0x180112419  pop     rsi
0x18011241a  pop     rbp
0x18011241b  pop     rbx
0x18011241c  retn
0x18011241d  mov     rcx, [rsp+48h]; this
0x180112422  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x180112429  mov     r9d, 8007029Ch; char *
0x18011242f  mov     edx, 26h ; '&'; void *
0x180112434  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180112439  jmp     short loc_1801123F0
0x18011243b  lock add dword ptr [rsi+8], 1
0x180112440  jg      short loc_18011245E
0x180112442  mov     rcx, [rsp+48h]; this
0x180112447  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x18011244e  mov     r9d, 8007029Ch; char *
0x180112454  mov     edx, 18h; void *
0x180112459  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18011245e  mov     rax, [rsi]
0x180112461  mov     rcx, rsi
0x180112464  mov     rax, [rax+28h]
0x180112468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011246d  mov     edi, ebp
0x18011246f  lock xadd [rsi+8], edi
0x180112474  dec     edi
0x180112476  cmp     edi, ebp
0x180112478  jl      short loc_18011249B
0x18011247a  test    edi, edi
0x18011247c  jnz     loc_1801123F4
0x180112482  lock xadd [rsi+8], ebp
0x180112487  dec     ebp
0x180112489  cmp     ebp, 0FFFFFFFFh
0x18011248c  jl      short loc_1801124B9
0x18011248e  mov     rcx, rsi; this
0x180112491  call    ?Delete@CResource@@IEAAXXZ; CResource::Delete(void)
0x180112496  jmp     loc_1801123F4
0x18011249b  mov     rcx, [rsp+48h]; this
0x1801124a0  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x1801124a7  mov     r9d, 8007029Ch; char *
0x1801124ad  mov     edx, 26h ; '&'; void *
0x1801124b2  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1801124b7  jmp     short loc_18011247A
0x1801124b9  mov     rcx, [rsp+48h]; this
0x1801124be  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x1801124c5  mov     r9d, 8007029Ch; char *
0x1801124cb  mov     edx, 26h ; '&'; void *
0x1801124d0  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1801124d5  jmp     short loc_18011248E
```
