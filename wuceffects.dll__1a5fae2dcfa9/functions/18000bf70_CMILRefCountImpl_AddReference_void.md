# CMILRefCountImpl::AddReference(void)

- ea: `0x18000bf70`
- end: `0x18000bfaa`
- name: `?AddReference@CMILRefCountImpl@@IEAAKXZ`
- size: `58`
- prototype: `unsigned int __fastcall(CMILRefCountImpl *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000adec`
- `0x18000bcd0`
- `0x18000bda0`
- `0x18000bef0`

## callees

- `0x18000bf70`
- `0x18002b594`

## string_xrefs

- `0x18000bf91`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`

## pseudocode

```c
__int64 __fastcall CMILRefCountImpl::AddReference(CMILRefCountImpl *this)
{
  signed __int32 v1; // ebx
  char v2; // cc
  unsigned __int32 v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = _InterlockedExchangeAdd((volatile signed __int32 *)this, 1u);
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
0x18000bf70  push    rbx; int
0x18000bf72  sub     rsp, 20h
0x18000bf76  mov     ebx, 1
0x18000bf7b  lock xadd [rcx], ebx
0x18000bf7f  add     ebx, 1
0x18000bf82  jle     short loc_18000BF8C
0x18000bf84  mov     eax, ebx
0x18000bf86  add     rsp, 20h
0x18000bf8a  pop     rbx
0x18000bf8b  retn
0x18000bf8c  mov     rcx, [rsp+28h]; this
0x18000bf91  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x18000bf98  mov     r9d, 8007029Ch; char *
0x18000bf9e  mov     edx, 18h; void *
0x18000bfa3  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000bfa8  jmp     short loc_18000BF84
```
