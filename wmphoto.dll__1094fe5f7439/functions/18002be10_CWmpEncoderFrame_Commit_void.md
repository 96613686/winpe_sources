# CWmpEncoderFrame::Commit(void)

- ea: `0x18002be10`
- end: `0x18002bfc1`
- name: `?Commit@CWmpEncoderFrame@@UEAAJXZ`
- size: `433`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18002aec8`
- `0x18002be10`
- `0x18002bfd0`
- `0x180034eb0`
- `0x1800354b0`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002befd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002befd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002be33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002be9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002be33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002be9b`

## pseudocode

```c
__int64 __fastcall CWmpEncoderFrame::Commit(CWmpEncoderFrame *this)
{
  char *v1; // rbp
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  int v4; // ebx
  __int64 v6; // r14
  _QWORD *v7; // r15
  struct IWICComponentFactory *WICFactory; // rax
  int v9; // edx

  v1 = (char *)this - 56;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 48);
  if ( *((_BYTE *)this - 8) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this - 48));
  if ( !*((_DWORD *)this - 16569) || (v9 = *((_DWORD *)this - 16568)) == 0 )
  {
    v4 = -2003292273;
    goto LABEL_5;
  }
  v6 = 0;
  v4 = 0;
  if ( *((_DWORD *)this - 16590) == 3 )
  {
    if ( *((_DWORD *)this + 4) != v9 )
    {
      v4 = -2003292343;
      goto LABEL_5;
    }
    if ( LOBYTE(v3[1].DebugInfo) )
      EnterCriticalSection(v3);
    v7 = (_QWORD *)((char *)this + 160);
    if ( *((_QWORD *)this + 20)
      || (WICFactory = GetWICFactory(),
          v4 = ((__int64 (__fastcall *)(struct IWICComponentFactory *, GUID *, __int64, _QWORD, char *))WICFactory->lpVtbl->CreateMetadataWriter)(
                 WICFactory,
                 &GUID_MetadataFormatIfd,
                 *((_QWORD *)this + 19) + 136LL,
                 0,
                 (char *)this + 160),
          v4 >= 0) )
    {
      v6 = *v7;
      if ( *v7 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v6 + 8LL))(*v7);
    }
    if ( v1 && v1[48] )
      LeaveCriticalSection(v3);
    if ( v4 < 0 )
      goto LABEL_25;
    v4 = CWmpEncoderFrame::HrEncodeFrame((CWmpEncoderFrame *)((char *)this - 66376));
    if ( v4 < 0 )
      goto LABEL_25;
  }
  else if ( *((_DWORD *)this - 16590) != 4 )
  {
    v4 = -2003292412;
    goto LABEL_5;
  }
  if ( *((_DWORD *)this + 33)
    || (v4 = CGpWmpEncoder::HrCommitFrame(*((CGpWmpEncoder **)this + 19), (CWmpEncoderFrame *)((char *)this + 140)),
        v4 >= 0) )
  {
    if ( !*((_DWORD *)this + 52)
      || (v4 = CWmpEncoderFrame::HrEncodeThumbnail((CWmpEncoderFrame *)((char *)this - 66376)), v4 >= 0) )
    {
      *((_DWORD *)this - 16590) = 0;
    }
  }
LABEL_25:
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
LABEL_5:
  if ( v1 && v1[48] )
    LeaveCriticalSection(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002be10  push    rbx
0x18002be12  push    rbp
0x18002be13  push    rsi
0x18002be14  push    rdi
0x18002be15  push    r12
0x18002be17  push    r14
0x18002be19  push    r15
0x18002be1b  sub     rsp, 30h
0x18002be1f  lea     rbp, [rcx-38h]
0x18002be23  mov     rdi, rcx
0x18002be26  lea     rsi, [rbp+8]
0x18002be2a  cmp     byte ptr [rsi+28h], 0
0x18002be2e  jz      short loc_18002BE39
0x18002be30  mov     rcx, rsi; lpCriticalSection
0x18002be33  call    cs:__imp_EnterCriticalSection
0x18002be39  lea     r12, [rdi-10348h]
0x18002be40  cmp     dword ptr [r12+64h], 0
0x18002be46  ja      loc_18002BF84
0x18002be4c  mov     ebx, 88982F8Fh
0x18002be51  test    rbp, rbp
0x18002be54  jz      short loc_18002BE65
0x18002be56  cmp     byte ptr [rbp+30h], 0
0x18002be5a  jz      short loc_18002BE65
0x18002be5c  mov     rcx, rsi; lpCriticalSection
0x18002be5f  call    cs:__imp_LeaveCriticalSection
0x18002be65  mov     eax, ebx
0x18002be67  add     rsp, 30h
0x18002be6b  pop     r15
0x18002be6d  pop     r14
0x18002be6f  pop     r12
0x18002be71  pop     rdi
0x18002be72  pop     rsi
0x18002be73  pop     rbp
0x18002be74  pop     rbx
0x18002be75  retn
0x18002be76  mov     ecx, [rdi-10338h]
0x18002be7c  xor     r14d, r14d
0x18002be7f  xor     ebx, ebx
0x18002be81  sub     ecx, 3
0x18002be84  jnz     loc_18002BF75
0x18002be8a  cmp     [rdi+10h], edx
0x18002be8d  jnz     loc_18002BF97
0x18002be93  cmp     [rsi+28h], bl
0x18002be96  jz      short loc_18002BEA1
0x18002be98  mov     rcx, rsi; lpCriticalSection
0x18002be9b  call    cs:__imp_EnterCriticalSection
0x18002bea1  lea     r15, [rdi+0A0h]
0x18002bea8  cmp     [r15], rbx
0x18002beab  jnz     loc_18002BFA1
0x18002beb1  call    ?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ; GetWICFactory(void)
0x18002beb6  mov     r8, [rdi+98h]
0x18002bebd  lea     rdx, GUID_MetadataFormatIfd
0x18002bec4  mov     rcx, rax
0x18002bec7  mov     [rsp+68h+var_48], r15
0x18002becc  add     r8, 88h
0x18002bed3  xor     r9d, r9d
0x18002bed6  mov     rax, [rax]
0x18002bed9  mov     rax, [rax+0F0h]
0x18002bee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bee5  mov     ebx, eax
0x18002bee7  test    eax, eax
0x18002bee9  jns     loc_18002BFA1
0x18002beef  test    rbp, rbp
0x18002bef2  jz      short loc_18002BF03
0x18002bef4  cmp     byte ptr [rbp+30h], 0
0x18002bef8  jz      short loc_18002BF03
0x18002befa  mov     rcx, rsi; lpCriticalSection
0x18002befd  call    cs:__imp_LeaveCriticalSection
0x18002bf03  test    ebx, ebx
0x18002bf05  js      short loc_18002BF58
0x18002bf07  mov     rcx, r12; this
0x18002bf0a  call    ?HrEncodeFrame@CWmpEncoderFrame@@MEAAJXZ; CWmpEncoderFrame::HrEncodeFrame(void)
0x18002bf0f  mov     ebx, eax
0x18002bf11  test    eax, eax
0x18002bf13  js      short loc_18002BF58
0x18002bf15  cmp     dword ptr [rdi+84h], 0
0x18002bf1c  jnz     short loc_18002BF37
0x18002bf1e  mov     rcx, [rdi+98h]; this
0x18002bf25  lea     rdx, [rdi+8Ch]; struct CGpWmpEncoder::CWmpEncoderFrameInfo *
0x18002bf2c  call    ?HrCommitFrame@CGpWmpEncoder@@UEAAJPEAUCWmpEncoderFrameInfo@1@@Z; CGpWmpEncoder::HrCommitFrame(CGpWmpEncoder::CWmpEncoderFrameInfo *)
0x18002bf31  mov     ebx, eax
0x18002bf33  test    eax, eax
0x18002bf35  js      short loc_18002BF58
0x18002bf37  cmp     dword ptr [rdi+0D0h], 0
0x18002bf3e  jz      short loc_18002BF4E
0x18002bf40  mov     rcx, r12; this
0x18002bf43  call    ?HrEncodeThumbnail@CWmpEncoderFrame@@MEAAJXZ; CWmpEncoderFrame::HrEncodeThumbnail(void)
0x18002bf48  mov     ebx, eax
0x18002bf4a  test    eax, eax
0x18002bf4c  js      short loc_18002BF58
0x18002bf4e  mov     dword ptr [rdi-10338h], 0
0x18002bf58  test    r14, r14
0x18002bf5b  jz      loc_18002BE51
0x18002bf61  mov     rax, [r14]
0x18002bf64  mov     rcx, r14
0x18002bf67  mov     rax, [rax+10h]
0x18002bf6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf70  jmp     loc_18002BE51
0x18002bf75  cmp     ecx, 1
0x18002bf78  jz      short loc_18002BF15
0x18002bf7a  mov     ebx, 88982F04h
0x18002bf7f  jmp     loc_18002BE51
0x18002bf84  mov     edx, [rdi-102E0h]
0x18002bf8a  test    edx, edx
0x18002bf8c  jz      loc_18002BE4C
0x18002bf92  jmp     loc_18002BE76
0x18002bf97  mov     ebx, 88982F49h
0x18002bf9c  jmp     loc_18002BE51
0x18002bfa1  mov     r14, [r15]
0x18002bfa4  test    r14, r14
0x18002bfa7  jz      loc_18002BEEF
0x18002bfad  mov     rax, [r14]
0x18002bfb0  mov     rcx, r14
0x18002bfb3  mov     rax, [rax+8]
0x18002bfb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfbc  jmp     loc_18002BEEF
```
