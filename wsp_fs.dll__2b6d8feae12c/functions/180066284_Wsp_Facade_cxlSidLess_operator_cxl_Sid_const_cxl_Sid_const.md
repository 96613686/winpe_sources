# Wsp::Facade::cxlSidLess::operator()(cxl::Sid const &,cxl::Sid const &)

- ea: `0x180066284`
- end: `0x180066300`
- name: `??RcxlSidLess@Facade@Wsp@@QEBA_NAEBVSid@cxl@@0@Z`
- size: `124`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800659f0`
- `0x180065cc4`

## callees

- `0x180004fb5`
- `0x180018854`
- `0x180066284`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800662af`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800662c4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800662af`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800662c4`

## pseudocode

```c
char __fastcall Wsp::Facade::cxlSidLess::operator()(__int64 a1, const void **a2, const struct cxl::SidBase *a3)
{
  int v5; // eax
  void *v6; // rcx
  DWORD LengthSid; // ebx
  void *v8; // rcx
  DWORD v9; // eax
  const void *v10; // rdx
  DWORD v11; // edi
  size_t v12; // r8
  unsigned int v13; // eax

  if ( cxl::SidBase::IsEqual((cxl::SidBase *)a2, a3) )
  {
    LOBYTE(v5) = 0;
  }
  else
  {
    v6 = (void *)a2[2];
    if ( v6 )
      LengthSid = GetLengthSid(v6);
    else
      LengthSid = 0;
    v8 = (void *)*((_QWORD *)a3 + 2);
    if ( v8 )
    {
      v9 = GetLengthSid(v8);
      v10 = (const void *)*((_QWORD *)a3 + 2);
      v11 = v9;
    }
    else
    {
      v11 = 0;
      v10 = 0;
    }
    v12 = v11;
    if ( v11 >= LengthSid )
      v12 = LengthSid;
    v13 = memcmp_0(a2[2], v10, v12);
    if ( !v13 && LengthSid < v11 )
      v13 = -1;
    return v13 >> 31;
  }
  return v5;
}

```

## disassembly

```asm
0x180066284  push    rbx
0x180066286  push    rbp
0x180066287  push    rsi
0x180066288  push    rdi
0x180066289  sub     rsp, 28h
0x18006628d  mov     rbp, rdx
0x180066290  mov     rsi, r8
0x180066293  mov     rcx, rbp; this
0x180066296  mov     rdx, r8; struct cxl::SidBase *
0x180066299  call    ?IsEqual@SidBase@cxl@@QEBA_NAEBV12@@Z; cxl::SidBase::IsEqual(cxl::SidBase const &)
0x18006629e  test    al, al
0x1800662a0  jz      short loc_1800662A6
0x1800662a2  xor     al, al
0x1800662a4  jmp     short loc_1800662F7
0x1800662a6  mov     rcx, [rbp+10h]; pSid
0x1800662aa  test    rcx, rcx
0x1800662ad  jz      short loc_1800662B9
0x1800662af  call    cs:__imp_GetLengthSid
0x1800662b5  mov     ebx, eax
0x1800662b7  jmp     short loc_1800662BB
0x1800662b9  xor     ebx, ebx
0x1800662bb  mov     rcx, [rsi+10h]; pSid
0x1800662bf  test    rcx, rcx
0x1800662c2  jz      short loc_1800662D2
0x1800662c4  call    cs:__imp_GetLengthSid
0x1800662ca  mov     rdx, [rsi+10h]
0x1800662ce  mov     edi, eax
0x1800662d0  jmp     short loc_1800662D6
0x1800662d2  xor     edi, edi
0x1800662d4  xor     edx, edx; Buf2
0x1800662d6  mov     rcx, [rbp+10h]; Buf1
0x1800662da  mov     r8d, edi
0x1800662dd  cmp     edi, ebx
0x1800662df  cmovnb  r8d, ebx; Size
0x1800662e3  call    memcmp_0
0x1800662e8  test    eax, eax
0x1800662ea  jnz     short loc_1800662F4
0x1800662ec  or      ecx, 0FFFFFFFFh
0x1800662ef  cmp     ebx, edi
0x1800662f1  cmovb   eax, ecx
0x1800662f4  shr     eax, 1Fh
0x1800662f7  add     rsp, 28h
0x1800662fb  pop     rdi
0x1800662fc  pop     rsi
0x1800662fd  pop     rbp
0x1800662fe  pop     rbx
0x1800662ff  retn
```
