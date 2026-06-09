# CWmpEncoderFrame::Commit(void)

- ea: `0x18002c090`
- end: `0x18002c25a`
- name: `?Commit@CWmpEncoderFrame@@UEAAJXZ`
- size: `458`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18002b078`
- `0x18002c090`
- `0x18002c260`
- `0x180035480`
- `0x180035a80`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c0e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c190`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c0e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c190`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c0b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c128`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c0b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c128`

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
0x18002c090  push    rbx
0x18002c092  push    rbp
0x18002c093  push    rsi
0x18002c094  push    rdi
0x18002c095  push    r12
0x18002c097  push    r14
0x18002c099  push    r15
0x18002c09b  sub     rsp, 30h
0x18002c09f  lea     rbp, [rcx-38h]
0x18002c0a3  mov     rdi, rcx
0x18002c0a6  lea     rsi, [rbp+8]
0x18002c0aa  cmp     byte ptr [rsi+28h], 0
0x18002c0ae  jz      short loc_18002C0BF
0x18002c0b0  mov     rcx, rsi; lpCriticalSection
0x18002c0b3  call    cs:__imp_EnterCriticalSection
0x18002c0ba  nop     dword ptr [rax+rax+00h]
0x18002c0bf  lea     r12, [rdi-10348h]
0x18002c0c6  cmp     dword ptr [r12+64h], 0
0x18002c0cc  ja      loc_18002C21D
0x18002c0d2  mov     ebx, 88982F8Fh
0x18002c0d7  test    rbp, rbp
0x18002c0da  jz      short loc_18002C0F1
0x18002c0dc  cmp     byte ptr [rbp+30h], 0
0x18002c0e0  jz      short loc_18002C0F1
0x18002c0e2  mov     rcx, rsi; lpCriticalSection
0x18002c0e5  call    cs:__imp_LeaveCriticalSection
0x18002c0ec  nop     dword ptr [rax+rax+00h]
0x18002c0f1  mov     eax, ebx
0x18002c0f3  add     rsp, 30h
0x18002c0f7  pop     r15
0x18002c0f9  pop     r14
0x18002c0fb  pop     r12
0x18002c0fd  pop     rdi
0x18002c0fe  pop     rsi
0x18002c0ff  pop     rbp
0x18002c100  pop     rbx
0x18002c101  retn
0x18002c103  mov     ecx, [rdi-10338h]
0x18002c109  xor     r14d, r14d
0x18002c10c  xor     ebx, ebx
0x18002c10e  sub     ecx, 3
0x18002c111  jnz     loc_18002C20E
0x18002c117  cmp     [rdi+10h], edx
0x18002c11a  jnz     loc_18002C230
0x18002c120  cmp     [rsi+28h], bl
0x18002c123  jz      short loc_18002C134
0x18002c125  mov     rcx, rsi; lpCriticalSection
0x18002c128  call    cs:__imp_EnterCriticalSection
0x18002c12f  nop     dword ptr [rax+rax+00h]
0x18002c134  lea     r15, [rdi+0A0h]
0x18002c13b  cmp     [r15], rbx
0x18002c13e  jnz     loc_18002C23A
0x18002c144  call    ?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ; GetWICFactory(void)
0x18002c149  mov     r8, [rdi+98h]
0x18002c150  lea     rdx, GUID_MetadataFormatIfd
0x18002c157  mov     rcx, rax
0x18002c15a  mov     [rsp+68h+var_48], r15
0x18002c15f  add     r8, 88h
0x18002c166  xor     r9d, r9d
0x18002c169  mov     rax, [rax]
0x18002c16c  mov     rax, [rax+0F0h]
0x18002c173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c178  mov     ebx, eax
0x18002c17a  test    eax, eax
0x18002c17c  jns     loc_18002C23A
0x18002c182  test    rbp, rbp
0x18002c185  jz      short loc_18002C19C
0x18002c187  cmp     byte ptr [rbp+30h], 0
0x18002c18b  jz      short loc_18002C19C
0x18002c18d  mov     rcx, rsi; lpCriticalSection
0x18002c190  call    cs:__imp_LeaveCriticalSection
0x18002c197  nop     dword ptr [rax+rax+00h]
0x18002c19c  test    ebx, ebx
0x18002c19e  js      short loc_18002C1F1
0x18002c1a0  mov     rcx, r12; this
0x18002c1a3  call    ?HrEncodeFrame@CWmpEncoderFrame@@MEAAJXZ; CWmpEncoderFrame::HrEncodeFrame(void)
0x18002c1a8  mov     ebx, eax
0x18002c1aa  test    eax, eax
0x18002c1ac  js      short loc_18002C1F1
0x18002c1ae  cmp     dword ptr [rdi+84h], 0
0x18002c1b5  jnz     short loc_18002C1D0
0x18002c1b7  mov     rcx, [rdi+98h]; this
0x18002c1be  lea     rdx, [rdi+8Ch]; struct CGpWmpEncoder::CWmpEncoderFrameInfo *
0x18002c1c5  call    ?HrCommitFrame@CGpWmpEncoder@@UEAAJPEAUCWmpEncoderFrameInfo@1@@Z; CGpWmpEncoder::HrCommitFrame(CGpWmpEncoder::CWmpEncoderFrameInfo *)
0x18002c1ca  mov     ebx, eax
0x18002c1cc  test    eax, eax
0x18002c1ce  js      short loc_18002C1F1
0x18002c1d0  cmp     dword ptr [rdi+0D0h], 0
0x18002c1d7  jz      short loc_18002C1E7
0x18002c1d9  mov     rcx, r12; this
0x18002c1dc  call    ?HrEncodeThumbnail@CWmpEncoderFrame@@MEAAJXZ; CWmpEncoderFrame::HrEncodeThumbnail(void)
0x18002c1e1  mov     ebx, eax
0x18002c1e3  test    eax, eax
0x18002c1e5  js      short loc_18002C1F1
0x18002c1e7  mov     dword ptr [rdi-10338h], 0
0x18002c1f1  test    r14, r14
0x18002c1f4  jz      loc_18002C0D7
0x18002c1fa  mov     rax, [r14]
0x18002c1fd  mov     rcx, r14
0x18002c200  mov     rax, [rax+10h]
0x18002c204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c209  jmp     loc_18002C0D7
0x18002c20e  cmp     ecx, 1
0x18002c211  jz      short loc_18002C1AE
0x18002c213  mov     ebx, 88982F04h
0x18002c218  jmp     loc_18002C0D7
0x18002c21d  mov     edx, [rdi-102E0h]
0x18002c223  test    edx, edx
0x18002c225  jz      loc_18002C0D2
0x18002c22b  jmp     loc_18002C103
0x18002c230  mov     ebx, 88982F49h
0x18002c235  jmp     loc_18002C0D7
0x18002c23a  mov     r14, [r15]
0x18002c23d  test    r14, r14
0x18002c240  jz      loc_18002C182
0x18002c246  mov     rax, [r14]
0x18002c249  mov     rcx, r14
0x18002c24c  mov     rax, [rax+8]
0x18002c250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c255  jmp     loc_18002C182
```
