# Windows::UI::Composition::FlattenedEffectGraph::AddRef(void)

- ea: `0x180019b40`
- end: `0x180019b7b`
- name: `?AddRef@FlattenedEffectGraph@Composition@UI@Windows@@UEAAKXZ`
- size: `59`
- prototype: `unsigned int __fastcall(Windows::UI::Composition::FlattenedEffectGraph *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026960`

## callees

- `0x180019b40`
- `0x18002b594`

## string_xrefs

- `0x180019b62`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::FlattenedEffectGraph::AddRef(
        Windows::UI::Composition::FlattenedEffectGraph *this)
{
  signed __int32 v1; // ebx
  char v2; // cc
  unsigned __int32 v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 1u);
  v2 = (v1 + 1 < 0) ^ __OFADD__(1, v1) | (v1 == -1);
  v3 = v1 + 1;
  if ( v2 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v5);
  return v3;
}

```

## disassembly

```asm
0x180019b40  push    rbx; int
0x180019b42  sub     rsp, 20h
0x180019b46  mov     ebx, 1
0x180019b4b  lock xadd [rcx+8], ebx
0x180019b50  add     ebx, 1
0x180019b53  jle     short loc_180019B5D
0x180019b55  mov     eax, ebx
0x180019b57  add     rsp, 20h
0x180019b5b  pop     rbx
0x180019b5c  retn
0x180019b5d  mov     rcx, [rsp+28h]; this
0x180019b62  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x180019b69  mov     r9d, 8007029Ch; char *
0x180019b6f  mov     edx, 18h; void *
0x180019b74  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180019b79  jmp     short loc_180019B55
```
