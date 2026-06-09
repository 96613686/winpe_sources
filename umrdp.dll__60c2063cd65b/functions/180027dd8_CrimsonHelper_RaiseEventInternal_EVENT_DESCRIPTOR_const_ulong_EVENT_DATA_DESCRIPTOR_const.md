# CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)

- ea: `0x180027dd8`
- end: `0x180027e33`
- name: `?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z`
- size: `91`
- prototype: `unsigned int __fastcall(CrimsonHelper *__hidden this, const struct _EVENT_DESCRIPTOR *, unsigned int, struct _EVENT_DATA_DESCRIPTOR *const)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002b60`
- `0x180009ca8`
- `0x18002b234`

## callees

- `0x180027dd8`
- `0x180047ef0`

## import_xrefs

- `ntdll!EtwEventWriteFull` at `0x180027e1b`
- `ntdll!EtwEventWriteFull` at `0x180027e1b`

## pseudocode

```c
__int64 __fastcall CrimsonHelper::RaiseEventInternal(
        CrimsonHelper *this,
        const struct _EVENT_DESCRIPTOR *a2,
        int a3,
        struct _EVENT_DATA_DESCRIPTOR *const a4)
{
  if ( *((_BYTE *)this + 88) )
    return EtwEventWriteFull(*((_QWORD *)this + 10), a2, 0, 0, 0, a3, a4);
  else
    return 6;
}

```

## disassembly

```asm
0x180027dd8  sub     rsp, 68h
0x180027ddc  mov     rax, cs:__security_cookie
0x180027de3  xor     rax, rsp
0x180027de6  mov     [rsp+68h+var_18], rax
0x180027deb  cmp     byte ptr [rcx+58h], 0
0x180027def  mov     eax, r8d
0x180027df2  jnz     short loc_180027DFB
0x180027df4  mov     eax, 6
0x180027df9  jmp     short loc_180027E21
0x180027dfb  mov     rcx, [rcx+50h]
0x180027dff  xorps   xmm0, xmm0
0x180027e02  mov     [rsp+68h+var_38], r9
0x180027e07  xor     r8d, r8d
0x180027e0a  mov     [rsp+68h+var_40], eax
0x180027e0e  xor     r9d, r9d
0x180027e11  movups  [rsp+68h+var_28], xmm0
0x180027e16  mov     [rsp+68h+var_48], r8
0x180027e1b  call    cs:__imp_EtwEventWriteFull
0x180027e21  mov     rcx, [rsp+68h+var_18]
0x180027e26  xor     rcx, rsp; StackCookie
0x180027e29  call    __security_check_cookie
0x180027e2e  add     rsp, 68h
0x180027e32  retn
```
