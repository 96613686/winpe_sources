# UdfDeEmbedFileData

- ea: `0x1400193f0`
- end: `0x14001959d`
- name: `UdfDeEmbedFileData`
- size: `429`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400010f0`
- `0x140004514`
- `0x14000efc8`
- `0x1400300ec`
- `0x140051d74`

## callees

- `0x140009380`
- `0x14000c8d0`
- `0x140010c5c`
- `0x1400193f0`

## import_xrefs

- `ntoskrnl!CcPreparePinWrite` at `0x14001952d`
- `ntoskrnl!CcPreparePinWrite` at `0x14001952d`
- `ntoskrnl!CcInitializeCacheMap` at `0x1400194ab`
- `ntoskrnl!CcInitializeCacheMap` at `0x1400194ab`
- `ntoskrnl!CcMdlWriteComplete` at `0x140019570`
- `ntoskrnl!CcMdlWriteComplete` at `0x14001dfe6`
- `ntoskrnl!CcMdlWriteComplete` at `0x140019570`
- `ntoskrnl!CcMdlWriteComplete` at `0x14001dfe6`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x1400194bf`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x1400194bf`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1400194ed`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1400194ed`

## pseudocode

```c
void __fastcall UdfDeEmbedFileData(__int64 a1, struct _CC_FILE_SIZES *a2, struct _FILE_OBJECT *a3, char a4)
{
  struct _FILE_OBJECT *v5; // rdi
  PVOID v7; // rcx
  PVOID Buffer; // [rsp+40h] [rbp-38h] BYREF
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+48h] [rbp-30h] BYREF
  PVOID Bcb; // [rsp+80h] [rbp+8h] BYREF
  PMDL MdlChain; // [rsp+88h] [rbp+10h] BYREF
  struct _FILE_OBJECT *v12; // [rsp+90h] [rbp+18h]

  v12 = a3;
  v5 = a3;
  MdlChain = 0;
  Bcb = 0;
  Buffer = 0;
  IoStatus = 0;
  v7 = *(PVOID *)&WPP_GLOBAL_Control;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
  {
    WPP_SF_qq(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      11,
      WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids,
      a2,
      a3);
  }
  if ( (a2[8].ValidDataLength.HighPart & 0x4000) == 0 )
  {
    LOBYTE(a3) = 1;
    UdfInitializeScbMcb(v7, a2, a3);
  }
  if ( a4 )
  {
    if ( LOWORD(a2->AllocationSize.LowPart) == 2356 )
    {
      if ( !v5->PrivateCacheMap )
      {
        CcInitializeCacheMap(v5, a2 + 1, 0, &Callbacks, a2);
        CcSetReadAheadGranularity(v5, 0x10000u);
      }
      CcPrepareMdlWrite(v5, &UdfLargeZero, 0x1000u, &MdlChain, &IoStatus);
    }
    else
    {
      CcPreparePinWrite(v5, &UdfLargeZero, 0x1000u, 0, 1u, &Bcb, &Buffer);
      v7 = Buffer;
      *(_BYTE *)Buffer = *(_BYTE *)Buffer;
    }
  }
  a2[8].ValidDataLength.HighPart |= 0x80000u;
  a2[8].ValidDataLength.HighPart &= ~2u;
  if ( MdlChain )
    CcMdlWriteComplete(v5, &UdfLargeZero, MdlChain);
  if ( Bcb )
    UdfUnpinData(v7, &Bcb);
}

```

## disassembly

```asm
0x1400193f0  mov     rax, rsp
0x1400193f3  mov     [rax+18h], r8
0x1400193f7  mov     [rax+8], rcx
0x1400193fb  push    rbx
0x1400193fc  push    rsi
0x1400193fd  push    rdi
0x1400193fe  sub     rsp, 60h
0x140019402  mov     sil, r9b
0x140019405  mov     rdi, r8
0x140019408  mov     rbx, rdx
0x14001940b  mov     qword ptr [rax+10h], 0
0x140019413  mov     qword ptr [rax+8], 0
0x14001941b  mov     qword ptr [rax-38h], 0
0x140019423  xorps   xmm0, xmm0
0x140019426  movups  xmmword ptr [rax-30h], xmm0
0x14001942a  lea     rax, WPP_GLOBAL_Control
0x140019431  mov     rcx, cs:WPP_GLOBAL_Control
0x140019438  cmp     rcx, rax
0x14001943b  jz      short loc_140019463
0x14001943d  test    dword ptr [rcx+2Ch], 4000000h
0x140019444  jz      short loc_140019463
0x140019446  mov     edx, 0Bh
0x14001944b  mov     [rsp+78h+LazyWriteContext], r8
0x140019450  mov     r9, rbx
0x140019453  lea     r8, WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids
0x14001945a  mov     rcx, [rcx+18h]
0x14001945e  call    WPP_SF_qq
0x140019463  test    dword ptr [rbx+0D4h], 4000h
0x14001946d  jnz     short loc_14001947B
0x14001946f  mov     r8b, 1
0x140019472  mov     rdx, rbx
0x140019475  call    UdfInitializeScbMcb
0x14001947a  nop
0x14001947b  test    sil, sil
0x14001947e  jz      loc_140019542
0x140019484  mov     eax, 934h
0x140019489  cmp     ax, [rbx]
0x14001948c  jnz     short loc_1400194FB
0x14001948e  cmp     qword ptr [rdi+30h], 0
0x140019493  jnz     short loc_1400194CB
0x140019495  lea     rdx, [rbx+18h]; FileSizes
0x140019499  mov     [rsp+78h+LazyWriteContext], rbx; LazyWriteContext
0x14001949e  lea     r9, Callbacks; Callbacks
0x1400194a5  xor     r8d, r8d; PinAccess
0x1400194a8  mov     rcx, rdi; FileObject
0x1400194ab  call    cs:__imp_CcInitializeCacheMap
0x1400194b2  nop     dword ptr [rax+rax+00h]
0x1400194b7  mov     edx, 10000h; Granularity
0x1400194bc  mov     rcx, rdi; FileObject
0x1400194bf  call    cs:__imp_CcSetReadAheadGranularity
0x1400194c6  nop     dword ptr [rax+rax+00h]
0x1400194cb  lea     rax, [rsp+78h+IoStatus]
0x1400194d0  mov     [rsp+78h+LazyWriteContext], rax; IoStatus
0x1400194d5  lea     r9, [rsp+78h+MdlChain]; MdlChain
0x1400194dd  mov     r8d, 1000h; Length
0x1400194e3  lea     rdx, UdfLargeZero; FileOffset
0x1400194ea  mov     rcx, rdi; FileObject
0x1400194ed  call    cs:__imp_CcPrepareMdlWrite
0x1400194f4  nop     dword ptr [rax+rax+00h]
0x1400194f9  jmp     short loc_140019542
0x1400194fb  lea     rax, [rsp+78h+var_38]
0x140019500  mov     [rsp+78h+Buffer], rax; Buffer
0x140019505  lea     rax, [rsp+78h+arg_0]
0x14001950d  mov     [rsp+78h+Bcb], rax; Bcb
0x140019512  mov     dword ptr [rsp+78h+LazyWriteContext], 1; Flags
0x14001951a  xor     r9d, r9d; Zero
0x14001951d  mov     r8d, 1000h; Length
0x140019523  lea     rdx, UdfLargeZero; FileOffset
0x14001952a  mov     rcx, rdi; FileObject
0x14001952d  call    cs:__imp_CcPreparePinWrite
0x140019534  nop     dword ptr [rax+rax+00h]
0x140019539  mov     rcx, [rsp+78h+var_38]
0x14001953e  mov     al, [rcx]
0x140019540  mov     [rcx], al
0x140019542  bts     dword ptr [rbx+0D4h], 13h
0x14001954a  mov     eax, [rbx+0D4h]
0x140019550  and     eax, 0FFFFFFFDh
0x140019553  mov     [rbx+0D4h], eax
0x140019559  mov     r8, [rsp+78h+MdlChain]; MdlChain
0x140019561  test    r8, r8
0x140019564  jz      short loc_14001957C
0x140019566  lea     rdx, UdfLargeZero; FileOffset
0x14001956d  mov     rcx, rdi; FileObject
0x140019570  call    cs:__imp_CcMdlWriteComplete
0x140019577  nop     dword ptr [rax+rax+00h]
0x14001957c  cmp     [rsp+78h+arg_0], 0
0x140019585  jz      short loc_140019594
0x140019587  lea     rdx, [rsp+78h+arg_0]
0x14001958f  call    UdfUnpinData
0x140019594  add     rsp, 60h
0x140019598  pop     rdi
0x140019599  pop     rsi
0x14001959a  pop     rbx
0x14001959b  retn
0x14001dfc3  push    rbp
0x14001dfc5  sub     rsp, 40h
0x14001dfc9  mov     rbp, rdx
0x14001dfcc  mov     r8, [rbp+88h]; MdlChain
0x14001dfd3  test    r8, r8
0x14001dfd6  jz      short loc_14001DFF3
0x14001dfd8  lea     rdx, UdfLargeZero; FileOffset
0x14001dfdf  mov     rcx, [rbp+90h]; FileObject
0x14001dfe6  call    cs:__imp_CcMdlWriteComplete
0x14001dfed  nop     dword ptr [rax+rax+00h]
0x14001dff2  nop
0x14001dff3  cmp     qword ptr [rbp+80h], 0
0x14001dffb  jz      short loc_14001E00A
0x14001dffd  lea     rdx, [rbp+80h]
0x14001e004  call    UdfUnpinData
0x14001e009  nop
0x14001e00a  add     rsp, 40h
0x14001e00e  pop     rbp
0x14001e00f  retn
```
