# CWmpEncoderFrame::InitializeFromBlockReader(IWICMetadataBlockReader *)

- ea: `0x18003aa30`
- end: `0x18003abbf`
- name: `?InitializeFromBlockReader@CWmpEncoderFrame@@UEAAJPEAUIWICMetadataBlockReader@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this, struct IWICMetadataBlockReader *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18002aec8`
- `0x18002db34`
- `0x180035e50`
- `0x18003aa30`
- `0x180043624`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003aa65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003aa65`

## pseudocode

```c
__int64 __fastcall CWmpEncoderFrame::InitializeFromBlockReader(
        CWmpEncoderFrame *this,
        struct IWICMetadataBlockReader *a2)
{
  char *v2; // rax
  struct _RTL_CRITICAL_SECTION *v4; // rcx
  int v6; // ebx
  struct IWICComponentFactory *WICFactory; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+38h] [rbp-28h] BYREF
  char *v13; // [rsp+40h] [rbp-20h] BYREF
  __int128 Buf2; // [rsp+48h] [rbp-18h] BYREF

  v2 = (char *)this - 64;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 56);
  v13 = v2;
  if ( LOBYTE(v4[1].DebugInfo) )
    EnterCriticalSection(v4);
  v12 = 0;
  v11 = 0;
  Buf2 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    goto LABEL_19;
  }
  v6 = ((__int64 (__fastcall *)(struct IWICMetadataBlockReader *, __int128 *))a2->lpVtbl->GetContainerFormat)(a2, &Buf2);
  if ( v6 >= 0 )
  {
    if ( !memcmp_0(&GUID_ContainerFormatWmp, &Buf2, 0x10u) )
    {
      v6 = ((__int64 (__fastcall *)(struct IWICMetadataBlockReader *, _QWORD, __int64 *))a2->lpVtbl->GetReaderByIndex)(
             a2,
             0,
             &v12);
      if ( v6 >= 0 )
      {
        WICFactory = GetWICFactory();
        v6 = ((__int64 (__fastcall *)(struct IWICComponentFactory *, __int64, __int64, __int64 *))WICFactory->lpVtbl->CreateMetadataWriterFromReader)(
               WICFactory,
               v12,
               *((_QWORD *)this + 18) + 136LL,
               &v11);
        if ( v6 >= 0 )
        {
          v8 = *((_QWORD *)this + 19);
          if ( v8 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
          v9 = v11;
          *((_QWORD *)this + 19) = v11;
          if ( !v9 )
            goto LABEL_15;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
        }
      }
    }
    else
    {
      v6 = -2147024809;
    }
  }
  v9 = v11;
LABEL_15:
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v9 = v11;
    v12 = 0;
  }
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v11 = 0;
  }
LABEL_19:
  CGuard<CMTALock>::~CGuard<CMTALock>(&v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003aa30  mov     [rsp-18h+arg_10], rbx
0x18003aa35  push    rbp
0x18003aa36  push    rsi
0x18003aa37  push    rdi
0x18003aa38  mov     rbp, rsp
0x18003aa3b  sub     rsp, 60h
0x18003aa3f  mov     rax, cs:__security_cookie
0x18003aa46  xor     rax, rsp
0x18003aa49  mov     [rbp+var_8], rax
0x18003aa4d  lea     rax, [rcx-40h]
0x18003aa51  mov     rsi, rcx
0x18003aa54  lea     rcx, [rax+8]; lpCriticalSection
0x18003aa58  mov     [rbp+var_20], rax
0x18003aa5c  cmp     byte ptr [rcx+28h], 0
0x18003aa60  mov     rdi, rdx
0x18003aa63  jz      short loc_18003AA6B
0x18003aa65  call    cs:__imp_EnterCriticalSection
0x18003aa6b  mov     [rbp+var_28], 0
0x18003aa73  xorps   xmm0, xmm0
0x18003aa76  mov     [rbp+var_30], 0
0x18003aa7e  movups  [rbp+Buf2], xmm0
0x18003aa82  test    rdi, rdi
0x18003aa85  jnz     short loc_18003AA91
0x18003aa87  mov     ebx, 80070057h
0x18003aa8c  jmp     loc_18003AB98
0x18003aa91  mov     rax, [rdi]
0x18003aa94  lea     rdx, [rbp+Buf2]
0x18003aa98  mov     rcx, rdi
0x18003aa9b  mov     rax, [rax+18h]
0x18003aa9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aaa4  mov     ebx, eax
0x18003aaa6  test    eax, eax
0x18003aaa8  js      loc_18003AB57
0x18003aaae  mov     r8d, 10h; Size
0x18003aab4  lea     rdx, [rbp+Buf2]; Buf2
0x18003aab8  lea     rcx, GUID_ContainerFormatWmp; Buf1
0x18003aabf  call    memcmp_0
0x18003aac4  test    eax, eax
0x18003aac6  jz      short loc_18003AAD2
0x18003aac8  mov     ebx, 80070057h
0x18003aacd  jmp     loc_18003AB57
0x18003aad2  mov     rax, [rdi]
0x18003aad5  lea     r8, [rbp+var_28]
0x18003aad9  xor     edx, edx
0x18003aadb  mov     rcx, rdi
0x18003aade  mov     rax, [rax+28h]
0x18003aae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aae7  mov     ebx, eax
0x18003aae9  test    eax, eax
0x18003aaeb  js      short loc_18003AB57
0x18003aaed  call    ?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ; GetWICFactory(void)
0x18003aaf2  mov     r8, [rsi+90h]
0x18003aaf9  lea     r9, [rbp+var_30]
0x18003aafd  mov     rdx, [rbp+var_28]
0x18003ab01  mov     r10, rax
0x18003ab04  add     r8, 88h
0x18003ab0b  mov     rcx, [rax]
0x18003ab0e  mov     rax, [rcx+0F8h]
0x18003ab15  mov     rcx, r10
0x18003ab18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab1d  mov     ebx, eax
0x18003ab1f  test    eax, eax
0x18003ab21  js      short loc_18003AB57
0x18003ab23  mov     rcx, [rsi+98h]
0x18003ab2a  test    rcx, rcx
0x18003ab2d  jz      short loc_18003AB3B
0x18003ab2f  mov     rax, [rcx]
0x18003ab32  mov     rax, [rax+10h]
0x18003ab36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab3b  mov     rcx, [rbp+var_30]
0x18003ab3f  mov     [rsi+98h], rcx
0x18003ab46  test    rcx, rcx
0x18003ab49  jz      short loc_18003AB5B
0x18003ab4b  mov     rax, [rcx]
0x18003ab4e  mov     rax, [rax+8]
0x18003ab52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab57  mov     rcx, [rbp+var_30]
0x18003ab5b  mov     rdx, [rbp+var_28]
0x18003ab5f  test    rdx, rdx
0x18003ab62  jz      short loc_18003AB7F
0x18003ab64  mov     rax, [rdx]
0x18003ab67  mov     rcx, rdx
0x18003ab6a  mov     rax, [rax+10h]
0x18003ab6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab73  mov     rcx, [rbp+var_30]
0x18003ab77  mov     [rbp+var_28], 0
0x18003ab7f  test    rcx, rcx
0x18003ab82  jz      short loc_18003AB98
0x18003ab84  mov     rax, [rcx]
0x18003ab87  mov     rax, [rax+10h]
0x18003ab8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab90  mov     [rbp+var_30], 0
0x18003ab98  lea     rcx, [rbp+var_20]
0x18003ab9c  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003aba1  mov     eax, ebx
0x18003aba3  mov     rcx, [rbp+var_8]
0x18003aba7  xor     rcx, rsp; StackCookie
0x18003abaa  call    __security_check_cookie
0x18003abaf  mov     rbx, [rsp+60h+arg_10]
0x18003abb7  add     rsp, 60h
0x18003abbb  pop     rdi
0x18003abbc  pop     rsi
0x18003abbd  pop     rbp
0x18003abbe  retn
```
