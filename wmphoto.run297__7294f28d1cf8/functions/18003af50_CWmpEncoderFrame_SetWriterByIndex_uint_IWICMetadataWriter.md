# CWmpEncoderFrame::SetWriterByIndex(uint,IWICMetadataWriter *)

- ea: `0x18003af50`
- end: `0x18003b03a`
- name: `?SetWriterByIndex@CWmpEncoderFrame@@UEAAJIPEAUIWICMetadataWriter@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this, unsigned int, struct IWICMetadataWriter *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18002db34`
- `0x180035e50`
- `0x18003af50`
- `0x180043624`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003af89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003af89`

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
0x18003af50  mov     [rsp+arg_8], rbx
0x18003af55  mov     [rsp+arg_18], rsi
0x18003af5a  push    rdi
0x18003af5b  sub     rsp, 40h
0x18003af5f  mov     rax, cs:__security_cookie
0x18003af66  xor     rax, rsp
0x18003af69  mov     [rsp+48h+var_10], rax
0x18003af6e  lea     rax, [rcx-40h]
0x18003af72  mov     rsi, rcx
0x18003af75  lea     rcx, [rax+8]; lpCriticalSection
0x18003af79  mov     [rsp+48h+var_28], rax
0x18003af7e  cmp     byte ptr [rcx+28h], 0
0x18003af82  mov     rdi, r8
0x18003af85  mov     ebx, edx
0x18003af87  jz      short loc_18003AF8F
0x18003af89  call    cs:__imp_EnterCriticalSection
0x18003af8f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003af96  movdqu  [rsp+48h+Buf2], xmm0
0x18003af9c  test    ebx, ebx
0x18003af9e  jnz     short loc_18003B00C
0x18003afa0  test    rdi, rdi
0x18003afa3  jz      short loc_18003B00C
0x18003afa5  mov     rax, [rdi]
0x18003afa8  lea     rdx, [rsp+48h+Buf2]
0x18003afad  mov     rcx, rdi
0x18003afb0  mov     rax, [rax+18h]
0x18003afb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afb9  mov     ebx, eax
0x18003afbb  test    eax, eax
0x18003afbd  js      short loc_18003B011
0x18003afbf  mov     r8d, 10h; Size
0x18003afc5  lea     rdx, [rsp+48h+Buf2]; Buf2
0x18003afca  lea     rcx, GUID_MetadataFormatIfd; Buf1
0x18003afd1  call    memcmp_0
0x18003afd6  test    eax, eax
0x18003afd8  jnz     short loc_18003B00C
0x18003afda  mov     rcx, [rsi+98h]
0x18003afe1  xor     ebx, ebx
0x18003afe3  test    rcx, rcx
0x18003afe6  jz      short loc_18003AFF4
0x18003afe8  mov     rax, [rcx]
0x18003afeb  mov     rax, [rax+10h]
0x18003afef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aff4  mov     [rsi+98h], rdi
0x18003affb  mov     rcx, rdi
0x18003affe  mov     rax, [rdi]
0x18003b001  mov     rax, [rax+8]
0x18003b005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b00a  jmp     short loc_18003B011
0x18003b00c  mov     ebx, 80070057h
0x18003b011  lea     rcx, [rsp+48h+var_28]
0x18003b016  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003b01b  mov     eax, ebx
0x18003b01d  mov     rcx, [rsp+48h+var_10]
0x18003b022  xor     rcx, rsp; StackCookie
0x18003b025  call    __security_check_cookie
0x18003b02a  mov     rbx, [rsp+48h+arg_8]
0x18003b02f  mov     rsi, [rsp+48h+arg_18]
0x18003b034  add     rsp, 40h
0x18003b038  pop     rdi
0x18003b039  retn
```
