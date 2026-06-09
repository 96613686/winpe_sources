# CNtSid::CopyTo(void *)

- ea: `0x18001bb60`
- end: `0x18001bba6`
- name: `?CopyTo@CNtSid@@QEAAHPEAX@Z`
- size: `70`
- prototype: `__int64 __fastcall(CNtSid *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001ba10`
- `0x18003a980`

## callees

- `0x18001bb60`
- `0x18002ee96`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18001bb7e`
- `ntdll!RtlLengthSid` at `0x18001bb7e`

## pseudocode

```c
__int64 __fastcall CNtSid::CopyTo(CNtSid *this, void *a2)
{
  void *v4; // rcx
  ULONG v5; // eax

  v4 = *(void **)this;
  if ( !v4 || *((_DWORD *)this + 2) )
    return 0;
  v5 = RtlLengthSid(v4);
  memcpy_0(a2, *(const void **)this, v5);
  return 1;
}

```

## disassembly

```asm
0x18001bb60  mov     [rsp+arg_0], rbx
0x18001bb65  push    rdi
0x18001bb66  sub     rsp, 20h
0x18001bb6a  mov     rbx, rcx
0x18001bb6d  mov     rdi, rdx
0x18001bb70  mov     rcx, [rcx]; Sid
0x18001bb73  test    rcx, rcx
0x18001bb76  jz      short loc_18001BBA2
0x18001bb78  cmp     dword ptr [rbx+8], 0
0x18001bb7c  jnz     short loc_18001BBA2
0x18001bb7e  call    cs:__imp_RtlLengthSid
0x18001bb84  mov     rdx, [rbx]; Src
0x18001bb87  mov     rcx, rdi; void *
0x18001bb8a  mov     r8d, eax; Size
0x18001bb8d  call    memcpy_0
0x18001bb92  mov     eax, 1
0x18001bb97  mov     rbx, [rsp+28h+arg_0]
0x18001bb9c  add     rsp, 20h
0x18001bba0  pop     rdi
0x18001bba1  retn
0x18001bba2  xor     eax, eax
0x18001bba4  jmp     short loc_18001BB97
```
