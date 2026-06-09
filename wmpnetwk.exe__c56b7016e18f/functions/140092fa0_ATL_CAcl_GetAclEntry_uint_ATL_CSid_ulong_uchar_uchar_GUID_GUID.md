# ATL::CAcl::GetAclEntry(uint,ATL::CSid *,ulong *,uchar *,uchar *,_GUID *,_GUID *)

- ea: `0x140092fa0`
- end: `0x140093086`
- name: `?GetAclEntry@CAcl@ATL@@QEBAXIPEAVCSid@2@PEAKPEAE2PEAU_GUID@@3@Z`
- size: `230`
- prototype: `void __fastcall(ATL::CAcl *__hidden this, unsigned int, struct ATL::CSid *, unsigned int *, unsigned __int8 *, unsigned __int8 *, struct _GUID *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400920b4`

## callees

- `0x14000b3f0`
- `0x1400396dc`
- `0x14004bb5c`
- `0x140092fa0`
- `0x14009e010`

## import_xrefs

- `ADVAPI32!CopySid` at `0x14009302b`
- `ADVAPI32!CopySid` at `0x14009302b`
- `ADVAPI32!GetLengthSid` at `0x14009301b`
- `ADVAPI32!GetLengthSid` at `0x14009301b`

## pseudocode

```c
void __fastcall ATL::CAcl::GetAclEntry(
        ATL::CAcl *this,
        __int64 a2,
        struct ATL::CSid *a3,
        unsigned int *a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6)
{
  __int64 v8; // rax
  __int64 v9; // rsi
  __int64 v10; // rbx
  char v11; // al
  DWORD LengthSid; // eax
  int Error; // eax

  v8 = (*(__int64 (__fastcall **)(ATL::CAcl *))(*(_QWORD *)this + 32LL))(this);
  v9 = v8;
  if ( a3 )
  {
    v10 = v8 + 8;
    if ( a3 != (struct ATL::CSid *)(v8 + 8) )
    {
      *((_DWORD *)a3 + 20) = *(_DWORD *)(v8 + 88);
      ATL::CSimpleStringT<unsigned short,0>::operator=((_QWORD *)a3 + 11, (_QWORD *)(v8 + 96));
      ATL::CSimpleStringT<unsigned short,0>::operator=((_QWORD *)a3 + 12, (_QWORD *)(v10 + 96));
      ATL::CSimpleStringT<unsigned short,0>::operator=((_QWORD *)a3 + 13, (_QWORD *)(v10 + 104));
      v11 = *(_BYTE *)(v10 + 76);
      *((_BYTE *)a3 + 76) = v11;
      if ( v11 )
      {
        LengthSid = GetLengthSid((PSID)(v10 + 8));
        if ( !CopySid(LengthSid, (char *)a3 + 8, (PSID)(v10 + 8)) )
        {
          Error = ATL::AtlHresultFromLastError();
          *((_BYTE *)a3 + 76) = 0;
          ATL::AtlThrowImpl(Error);
        }
      }
    }
  }
  if ( a4 )
    *a4 = *(_DWORD *)(v9 + 128);
  if ( a5 )
    *a5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
  if ( a6 )
    *a6 = *(_BYTE *)(v9 + 132);
}

```

## disassembly

```asm
0x140092fa0  push    rbx
0x140092fa2  push    rbp
0x140092fa3  push    rsi
0x140092fa4  push    rdi
0x140092fa5  push    r14
0x140092fa7  push    r15
0x140092fa9  sub     rsp, 28h
0x140092fad  mov     rax, [rcx]
0x140092fb0  mov     r15, r9
0x140092fb3  mov     rbp, [rsp+58h+arg_20]
0x140092fbb  mov     rdi, r8
0x140092fbe  mov     r14, [rsp+58h+arg_28]
0x140092fc6  mov     rax, [rax+20h]
0x140092fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092fcf  mov     rsi, rax
0x140092fd2  test    rdi, rdi
0x140092fd5  jz      short loc_140093046
0x140092fd7  lea     rbx, [rax+8]
0x140092fdb  cmp     rdi, rbx
0x140092fde  jz      short loc_140093046
0x140092fe0  mov     ecx, [rbx+50h]
0x140092fe3  lea     rdx, [rbx+58h]
0x140092fe7  mov     [rdi+50h], ecx
0x140092fea  lea     rcx, [rdi+58h]
0x140092fee  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140092ff3  lea     rdx, [rbx+60h]
0x140092ff7  lea     rcx, [rdi+60h]
0x140092ffb  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140093000  lea     rdx, [rbx+68h]
0x140093004  lea     rcx, [rdi+68h]
0x140093008  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14009300d  mov     al, [rbx+4Ch]
0x140093010  mov     [rdi+4Ch], al
0x140093013  test    al, al
0x140093015  jz      short loc_140093046
0x140093017  lea     rcx, [rbx+8]; pSid
0x14009301b  call    cs:__imp_GetLengthSid
0x140093021  mov     ecx, eax; nDestinationSidLength
0x140093023  lea     rdx, [rdi+8]; pDestinationSid
0x140093027  lea     r8, [rbx+8]; pSourceSid
0x14009302b  call    cs:__imp_CopySid
0x140093031  test    eax, eax
0x140093033  jnz     short loc_140093046
0x140093035  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14009303a  mov     ecx, eax; int
0x14009303c  mov     byte ptr [rdi+4Ch], 0
0x140093040  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140093046  test    r15, r15
0x140093049  jz      short loc_140093054
0x14009304b  mov     eax, [rsi+80h]
0x140093051  mov     [r15], eax
0x140093054  test    rbp, rbp
0x140093057  jz      short loc_14009306B
0x140093059  mov     rax, [rsi]
0x14009305c  mov     rcx, rsi
0x14009305f  mov     rax, [rax+18h]
0x140093063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140093068  mov     [rbp+0], al
0x14009306b  test    r14, r14
0x14009306e  jz      short loc_140093079
0x140093070  mov     al, [rsi+84h]
0x140093076  mov     [r14], al
0x140093079  add     rsp, 28h
0x14009307d  pop     r15
0x14009307f  pop     r14
0x140093081  pop     rdi
0x140093082  pop     rsi
0x140093083  pop     rbp
0x140093084  pop     rbx
0x140093085  retn
```
