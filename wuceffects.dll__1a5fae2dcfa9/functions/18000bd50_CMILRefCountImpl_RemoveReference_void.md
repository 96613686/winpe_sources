# CMILRefCountImpl::RemoveReference(void)

- ea: `0x18000bd50`
- end: `0x18000bd8c`
- name: `?RemoveReference@CMILRefCountImpl@@IEAAKXZ`
- size: `60`
- prototype: `unsigned int __fastcall(CMILRefCountImpl *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000adec`
- `0x18000bcd0`

## callees

- `0x18000bd50`
- `0x18002b594`

## string_xrefs

- `0x18000bd73`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`

## pseudocode

```c
__int64 __fastcall CMILRefCountImpl::RemoveReference(CMILRefCountImpl *this)
{
  int v1; // ebx
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = _InterlockedDecrement((volatile signed __int32 *)this);
  if ( v1 < -1 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v3);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000bd50  push    rbx; int
0x18000bd52  sub     rsp, 20h
0x18000bd56  mov     ebx, 0FFFFFFFFh
0x18000bd5b  lock xadd [rcx], ebx
0x18000bd5f  dec     ebx
0x18000bd61  cmp     ebx, 0FFFFFFFFh
0x18000bd64  jl      short loc_18000BD6E
0x18000bd66  mov     eax, ebx
0x18000bd68  add     rsp, 20h
0x18000bd6c  pop     rbx
0x18000bd6d  retn
0x18000bd6e  mov     rcx, [rsp+28h]; this
0x18000bd73  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x18000bd7a  mov     r9d, 8007029Ch; char *
0x18000bd80  mov     edx, 26h ; '&'; void *
0x18000bd85  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000bd8a  jmp     short loc_18000BD66
```
