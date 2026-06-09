# CWmpEncoderFrame::InitializeFromBlockReader(IWICMetadataBlockReader *)

- ea: `0x18003b1e0`
- end: `0x18003b376`
- name: `?InitializeFromBlockReader@CWmpEncoderFrame@@UEAAJPEAUIWICMetadataBlockReader@@@Z`
- size: `406`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this, struct IWICMetadataBlockReader *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18002b078`
- `0x18002de30`
- `0x180036420`
- `0x18003b1e0`
- `0x180043e34`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b215`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b215`

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
0x18003b1e0  mov     [rsp-18h+arg_10], rbx
0x18003b1e5  push    rbp
0x18003b1e6  push    rsi
0x18003b1e7  push    rdi
0x18003b1e8  mov     rbp, rsp
0x18003b1eb  sub     rsp, 60h
0x18003b1ef  mov     rax, cs:__security_cookie
0x18003b1f6  xor     rax, rsp
0x18003b1f9  mov     [rbp+var_8], rax
0x18003b1fd  lea     rax, [rcx-40h]
0x18003b201  mov     rsi, rcx
0x18003b204  lea     rcx, [rax+8]; lpCriticalSection
0x18003b208  mov     [rbp+var_20], rax
0x18003b20c  cmp     byte ptr [rcx+28h], 0
0x18003b210  mov     rdi, rdx
0x18003b213  jz      short loc_18003B221
0x18003b215  call    cs:__imp_EnterCriticalSection
0x18003b21c  nop     dword ptr [rax+rax+00h]
0x18003b221  mov     [rbp+var_28], 0
0x18003b229  xorps   xmm0, xmm0
0x18003b22c  mov     [rbp+var_30], 0
0x18003b234  movups  [rbp+Buf2], xmm0
0x18003b238  test    rdi, rdi
0x18003b23b  jnz     short loc_18003B247
0x18003b23d  mov     ebx, 80070057h
0x18003b242  jmp     loc_18003B34E
0x18003b247  mov     rax, [rdi]
0x18003b24a  lea     rdx, [rbp+Buf2]
0x18003b24e  mov     rcx, rdi
0x18003b251  mov     rax, [rax+18h]
0x18003b255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b25a  mov     ebx, eax
0x18003b25c  test    eax, eax
0x18003b25e  js      loc_18003B30D
0x18003b264  mov     r8d, 10h; Size
0x18003b26a  lea     rdx, [rbp+Buf2]; Buf2
0x18003b26e  lea     rcx, GUID_ContainerFormatWmp; Buf1
0x18003b275  call    memcmp_0
0x18003b27a  test    eax, eax
0x18003b27c  jz      short loc_18003B288
0x18003b27e  mov     ebx, 80070057h
0x18003b283  jmp     loc_18003B30D
0x18003b288  mov     rax, [rdi]
0x18003b28b  lea     r8, [rbp+var_28]
0x18003b28f  xor     edx, edx
0x18003b291  mov     rcx, rdi
0x18003b294  mov     rax, [rax+28h]
0x18003b298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b29d  mov     ebx, eax
0x18003b29f  test    eax, eax
0x18003b2a1  js      short loc_18003B30D
0x18003b2a3  call    ?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ; GetWICFactory(void)
0x18003b2a8  mov     r8, [rsi+90h]
0x18003b2af  lea     r9, [rbp+var_30]
0x18003b2b3  mov     rdx, [rbp+var_28]
0x18003b2b7  mov     r10, rax
0x18003b2ba  add     r8, 88h
0x18003b2c1  mov     rcx, [rax]
0x18003b2c4  mov     rax, [rcx+0F8h]
0x18003b2cb  mov     rcx, r10
0x18003b2ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b2d3  mov     ebx, eax
0x18003b2d5  test    eax, eax
0x18003b2d7  js      short loc_18003B30D
0x18003b2d9  mov     rcx, [rsi+98h]
0x18003b2e0  test    rcx, rcx
0x18003b2e3  jz      short loc_18003B2F1
0x18003b2e5  mov     rax, [rcx]
0x18003b2e8  mov     rax, [rax+10h]
0x18003b2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b2f1  mov     rcx, [rbp+var_30]
0x18003b2f5  mov     [rsi+98h], rcx
0x18003b2fc  test    rcx, rcx
0x18003b2ff  jz      short loc_18003B311
0x18003b301  mov     rax, [rcx]
0x18003b304  mov     rax, [rax+8]
0x18003b308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b30d  mov     rcx, [rbp+var_30]
0x18003b311  mov     rdx, [rbp+var_28]
0x18003b315  test    rdx, rdx
0x18003b318  jz      short loc_18003B335
0x18003b31a  mov     rax, [rdx]
0x18003b31d  mov     rcx, rdx
0x18003b320  mov     rax, [rax+10h]
0x18003b324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b329  mov     rcx, [rbp+var_30]
0x18003b32d  mov     [rbp+var_28], 0
0x18003b335  test    rcx, rcx
0x18003b338  jz      short loc_18003B34E
0x18003b33a  mov     rax, [rcx]
0x18003b33d  mov     rax, [rax+10h]
0x18003b341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b346  mov     [rbp+var_30], 0
0x18003b34e  lea     rcx, [rbp+var_20]
0x18003b352  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003b357  mov     eax, ebx
0x18003b359  mov     rcx, [rbp+var_8]
0x18003b35d  xor     rcx, rsp; StackCookie
0x18003b360  call    __security_check_cookie
0x18003b365  mov     rbx, [rsp+60h+arg_10]
0x18003b36d  add     rsp, 60h
0x18003b371  pop     rdi
0x18003b372  pop     rsi
0x18003b373  pop     rbp
0x18003b374  retn
```
