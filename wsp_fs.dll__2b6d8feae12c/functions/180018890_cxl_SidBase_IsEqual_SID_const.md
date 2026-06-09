# cxl::SidBase::IsEqual(_SID const *)

- ea: `0x180018890`
- end: `0x1800188dd`
- name: `?IsEqual@SidBase@cxl@@QEBA_NPEBU_SID@@@Z`
- size: `77`
- prototype: `bool(cxl::SidBase *__hidden this, const struct _SID *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017e4c`
- `0x1800180fc`

## callees

- `0x180018890`
- `0x180018e0c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800188bd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800188bd`

## pseudocode

```c
bool __fastcall cxl::SidBase::IsEqual(cxl::SidBase *this, struct _SID *a2)
{
  void *v4; // rcx

  if ( !a2 )
    return *((_QWORD *)this + 2) == 0;
  cxl::SidBase::VerifySid(a2);
  v4 = (void *)*((_QWORD *)this + 2);
  return v4 && EqualSid(v4, a2);
}

```

## disassembly

```asm
0x180018890  mov     [rsp+arg_0], rbx
0x180018895  push    rdi
0x180018896  sub     rsp, 20h
0x18001889a  mov     rbx, rdx
0x18001889d  mov     rdi, rcx
0x1800188a0  test    rdx, rdx
0x1800188a3  jz      short loc_1800188CA
0x1800188a5  mov     rcx, rdx; struct _SID *
0x1800188a8  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x1800188ad  mov     rcx, [rdi+10h]; pSid1
0x1800188b1  test    rcx, rcx
0x1800188b4  jnz     short loc_1800188BA
0x1800188b6  xor     al, al
0x1800188b8  jmp     short loc_1800188D2
0x1800188ba  mov     rdx, rbx; pSid2
0x1800188bd  call    cs:__imp_EqualSid
0x1800188c3  test    eax, eax
0x1800188c5  setnz   al
0x1800188c8  jmp     short loc_1800188D2
0x1800188ca  cmp     qword ptr [rcx+10h], 0
0x1800188cf  setz    al
0x1800188d2  mov     rbx, [rsp+28h+arg_0]
0x1800188d7  add     rsp, 20h
0x1800188db  pop     rdi
0x1800188dc  retn
```
