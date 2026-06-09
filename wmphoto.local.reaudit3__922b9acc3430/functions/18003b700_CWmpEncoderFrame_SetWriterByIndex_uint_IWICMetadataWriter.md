# CWmpEncoderFrame::SetWriterByIndex(uint,IWICMetadataWriter *)

- ea: `0x18003b700`
- end: `0x18003b7f1`
- name: `?SetWriterByIndex@CWmpEncoderFrame@@UEAAJIPEAUIWICMetadataWriter@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this, unsigned int, struct IWICMetadataWriter *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18002de30`
- `0x180036420`
- `0x18003b700`
- `0x180043e34`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b739`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b739`

## pseudocode

```c
__int64 __fastcall CWmpEncoderFrame::SetWriterByIndex(CWmpEncoderFrame *this, int a2, struct IWICMetadataWriter *a3)
{
  char *v3; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  char *v11; // [rsp+20h] [rbp-28h] BYREF
  GUID Buf2; // [rsp+28h] [rbp-20h] BYREF

  v3 = (char *)this - 64;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 56);
  v11 = v3;
  if ( LOBYTE(v5[1].DebugInfo) )
    EnterCriticalSection(v5);
  Buf2 = GUID_NULL;
  if ( a2 || !a3 )
    goto LABEL_10;
  v8 = ((__int64 (__fastcall *)(struct IWICMetadataWriter *, GUID *))a3->lpVtbl->GetMetadataFormat)(a3, &Buf2);
  if ( v8 < 0 )
    goto LABEL_11;
  if ( memcmp_0(&GUID_MetadataFormatIfd, &Buf2, 0x10u) )
  {
LABEL_10:
    v8 = -2147024809;
    goto LABEL_11;
  }
  v9 = *((_QWORD *)this + 19);
  v8 = 0;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  *((_QWORD *)this + 19) = a3;
  ((void (__fastcall *)(struct IWICMetadataWriter *))a3->lpVtbl->AddRef)(a3);
LABEL_11:
  CGuard<CMTALock>::~CGuard<CMTALock>(&v11);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003b700  mov     [rsp+arg_8], rbx
0x18003b705  mov     [rsp+arg_18], rsi
0x18003b70a  push    rdi
0x18003b70b  sub     rsp, 40h
0x18003b70f  mov     rax, cs:__security_cookie
0x18003b716  xor     rax, rsp
0x18003b719  mov     [rsp+48h+var_10], rax
0x18003b71e  lea     rax, [rcx-40h]
0x18003b722  mov     rsi, rcx
0x18003b725  lea     rcx, [rax+8]; lpCriticalSection
0x18003b729  mov     [rsp+48h+var_28], rax
0x18003b72e  cmp     byte ptr [rcx+28h], 0
0x18003b732  mov     rdi, r8
0x18003b735  mov     ebx, edx
0x18003b737  jz      short loc_18003B745
0x18003b739  call    cs:__imp_EnterCriticalSection
0x18003b740  nop     dword ptr [rax+rax+00h]
0x18003b745  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003b74c  movdqu  [rsp+48h+Buf2], xmm0
0x18003b752  test    ebx, ebx
0x18003b754  jnz     short loc_18003B7C2
0x18003b756  test    rdi, rdi
0x18003b759  jz      short loc_18003B7C2
0x18003b75b  mov     rax, [rdi]
0x18003b75e  lea     rdx, [rsp+48h+Buf2]
0x18003b763  mov     rcx, rdi
0x18003b766  mov     rax, [rax+18h]
0x18003b76a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b76f  mov     ebx, eax
0x18003b771  test    eax, eax
0x18003b773  js      short loc_18003B7C7
0x18003b775  mov     r8d, 10h; Size
0x18003b77b  lea     rdx, [rsp+48h+Buf2]; Buf2
0x18003b780  lea     rcx, GUID_MetadataFormatIfd; Buf1
0x18003b787  call    memcmp_0
0x18003b78c  test    eax, eax
0x18003b78e  jnz     short loc_18003B7C2
0x18003b790  mov     rcx, [rsi+98h]
0x18003b797  xor     ebx, ebx
0x18003b799  test    rcx, rcx
0x18003b79c  jz      short loc_18003B7AA
0x18003b79e  mov     rax, [rcx]
0x18003b7a1  mov     rax, [rax+10h]
0x18003b7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b7aa  mov     [rsi+98h], rdi
0x18003b7b1  mov     rcx, rdi
0x18003b7b4  mov     rax, [rdi]
0x18003b7b7  mov     rax, [rax+8]
0x18003b7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b7c0  jmp     short loc_18003B7C7
0x18003b7c2  mov     ebx, 80070057h
0x18003b7c7  lea     rcx, [rsp+48h+var_28]
0x18003b7cc  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003b7d1  mov     eax, ebx
0x18003b7d3  mov     rcx, [rsp+48h+var_10]
0x18003b7d8  xor     rcx, rsp; StackCookie
0x18003b7db  call    __security_check_cookie
0x18003b7e0  mov     rbx, [rsp+48h+arg_8]
0x18003b7e5  mov     rsi, [rsp+48h+arg_18]
0x18003b7ea  add     rsp, 40h
0x18003b7ee  pop     rdi
0x18003b7ef  retn
```
