# cxl::SidBase::IsEqual(_SID const *)

- ea: `0x18001913c`
- end: `0x180019190`
- name: `?IsEqual@SidBase@cxl@@QEBA_NPEBU_SID@@@Z`
- size: `84`
- prototype: `bool(cxl::SidBase *__hidden this, const struct _SID *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018658`
- `0x180018938`

## callees

- `0x18001913c`
- `0x180019740`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180019169`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180019169`

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
0x18001913c  mov     [rsp+arg_0], rbx
0x180019141  push    rdi
0x180019142  sub     rsp, 20h
0x180019146  mov     rbx, rdx
0x180019149  mov     rdi, rcx
0x18001914c  test    rdx, rdx
0x18001914f  jz      short loc_18001917C
0x180019151  mov     rcx, rdx; struct _SID *
0x180019154  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x180019159  mov     rcx, [rdi+10h]; pSid1
0x18001915d  test    rcx, rcx
0x180019160  jnz     short loc_180019166
0x180019162  xor     al, al
0x180019164  jmp     short loc_180019184
0x180019166  mov     rdx, rbx; pSid2
0x180019169  call    cs:__imp_EqualSid
0x180019170  nop     dword ptr [rax+rax+00h]
0x180019175  test    eax, eax
0x180019177  setnz   al
0x18001917a  jmp     short loc_180019184
0x18001917c  cmp     qword ptr [rcx+10h], 0
0x180019181  setz    al
0x180019184  mov     rbx, [rsp+28h+arg_0]
0x180019189  add     rsp, 20h
0x18001918d  pop     rdi
0x18001918e  retn
```
