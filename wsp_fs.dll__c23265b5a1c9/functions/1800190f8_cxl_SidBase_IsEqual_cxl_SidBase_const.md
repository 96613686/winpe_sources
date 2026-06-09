# cxl::SidBase::IsEqual(cxl::SidBase const &)

- ea: `0x1800190f8`
- end: `0x180019133`
- name: `?IsEqual@SidBase@cxl@@QEBA_NAEBV12@@Z`
- size: `59`
- prototype: `bool __fastcall(cxl::SidBase *__hidden this, const struct cxl::SidBase *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800183b4`
- `0x18006756c`

## callees

- `0x1800190f8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001910e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001910e`

## pseudocode

```c
bool __fastcall cxl::SidBase::IsEqual(cxl::SidBase *this, const struct cxl::SidBase *a2)
{
  void *v2; // rdx
  void *v3; // rcx

  v2 = (void *)*((_QWORD *)a2 + 2);
  if ( !v2 )
    return *((_QWORD *)this + 2) == 0;
  v3 = (void *)*((_QWORD *)this + 2);
  return v3 && EqualSid(v3, v2);
}

```

## disassembly

```asm
0x1800190f8  sub     rsp, 28h
0x1800190fc  mov     rdx, [rdx+10h]; pSid2
0x180019100  test    rdx, rdx
0x180019103  jz      short loc_180019125
0x180019105  mov     rcx, [rcx+10h]; pSid1
0x180019109  test    rcx, rcx
0x18001910c  jz      short loc_180019121
0x18001910e  call    cs:__imp_EqualSid
0x180019115  nop     dword ptr [rax+rax+00h]
0x18001911a  test    eax, eax
0x18001911c  setnz   al
0x18001911f  jmp     short loc_18001912D
0x180019121  xor     al, al
0x180019123  jmp     short loc_18001912D
0x180019125  cmp     qword ptr [rcx+10h], 0
0x18001912a  setz    al
0x18001912d  add     rsp, 28h
0x180019131  retn
```
