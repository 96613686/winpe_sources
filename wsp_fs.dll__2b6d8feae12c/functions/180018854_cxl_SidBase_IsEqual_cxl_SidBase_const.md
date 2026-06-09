# cxl::SidBase::IsEqual(cxl::SidBase const &)

- ea: `0x180018854`
- end: `0x180018888`
- name: `?IsEqual@SidBase@cxl@@QEBA_NAEBV12@@Z`
- size: `52`
- prototype: `bool __fastcall(cxl::SidBase *__hidden this, const struct cxl::SidBase *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017bb4`
- `0x180066284`

## callees

- `0x180018854`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001886a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001886a`

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
0x180018854  sub     rsp, 28h
0x180018858  mov     rdx, [rdx+10h]; pSid2
0x18001885c  test    rdx, rdx
0x18001885f  jz      short loc_18001887B
0x180018861  mov     rcx, [rcx+10h]; pSid1
0x180018865  test    rcx, rcx
0x180018868  jz      short loc_180018877
0x18001886a  call    cs:__imp_EqualSid
0x180018870  test    eax, eax
0x180018872  setnz   al
0x180018875  jmp     short loc_180018883
0x180018877  xor     al, al
0x180018879  jmp     short loc_180018883
0x18001887b  cmp     qword ptr [rcx+10h], 0
0x180018880  setz    al
0x180018883  add     rsp, 28h
0x180018887  retn
```
