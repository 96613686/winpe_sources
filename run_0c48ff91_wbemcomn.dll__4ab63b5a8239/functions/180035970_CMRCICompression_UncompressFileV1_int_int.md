# CMRCICompression::UncompressFileV1(int,int)

- ea: `0x180035970`
- end: `0x180035ab1`
- name: `?UncompressFileV1@CMRCICompression@@IEAAHHH@Z`
- size: `321`
- prototype: `int(CMRCICompression *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800358c0`

## callees

- `0x18000a290`
- `0x18000ab30`
- `0x180035890`
- `0x180035970`
- `0x180044310`

## import_xrefs

- `msvcrt!_write` at `0x180035a77`
- `msvcrt!_write` at `0x180035a77`
- `msvcrt!_filelengthi64` at `0x180035a8b`
- `msvcrt!_filelengthi64` at `0x180035a8b`
- `msvcrt!_read` at `0x1800359b0`
- `msvcrt!_read` at `0x180035a1e`
- `msvcrt!_read` at `0x180035a37`
- `msvcrt!_read` at `0x1800359b0`
- `msvcrt!_read` at `0x180035a1e`
- `msvcrt!_read` at `0x180035a37`

## pseudocode

```c
__int64 __fastcall CMRCICompression::UncompressFileV1(CMRCICompression *this, int a2, int a3)
{
  void *v6; // rdi
  void *v7; // rsi
  int v9; // eax
  unsigned int v10; // r8d
  const void *v11; // rdx
  unsigned int v12; // ebx
  __int128 DstBuf; // [rsp+30h] [rbp-30h] BYREF
  __int64 v14; // [rsp+40h] [rbp-20h]
  unsigned int MaxCharCount[2]; // [rsp+48h] [rbp-18h] BYREF
  int v16; // [rsp+50h] [rbp-10h]

  v14 = 0;
  DstBuf = 0;
  if ( _read(a2, &DstBuf, 0x18u) != 24 )
    return 0;
  v6 = CWin32DefaultArena::WbemMemAlloc((unsigned int)(DWORD1(DstBuf) + 4));
  if ( !v6 )
    return 0;
  v7 = CWin32DefaultArena::WbemMemAlloc((unsigned int)(DWORD1(DstBuf) + 4));
  if ( !v7 )
  {
    CMUILocale::_Free(v6);
    return 0;
  }
  while ( 1 )
  {
    *(_QWORD *)MaxCharCount = 0;
    v16 = 0;
    if ( _read(a2, MaxCharCount, 0xCu) != 12 )
      break;
    if ( !MaxCharCount[1] )
    {
      v12 = 1;
      goto LABEL_15;
    }
    v9 = _read(a2, v6, MaxCharCount[1]);
    v10 = MaxCharCount[1];
    if ( v9 != MaxCharCount[1] )
      break;
    v11 = v6;
    if ( LOBYTE(MaxCharCount[0]) )
    {
      v10 = CMRCICompression::UncompressBuffer(this, v6, MaxCharCount[1], v7, v16, SBYTE1(DstBuf));
      if ( v10 == -1 )
        break;
      v11 = v7;
    }
    _write(a3, v11, v10);
  }
  v12 = 0;
LABEL_15:
  if ( _filelengthi64(a3) != v14 )
    v12 = 0;
  CMUILocale::_Free(v6);
  CMUILocale::_Free(v7);
  return v12;
}

```

## disassembly

```asm
0x180035970  mov     [rsp-28h+arg_18], rbx
0x180035975  push    rbp
0x180035976  push    rsi
0x180035977  push    rdi
0x180035978  push    r14
0x18003597a  push    r15
0x18003597c  mov     rbp, rsp
0x18003597f  sub     rsp, 60h
0x180035983  mov     rax, cs:__security_cookie
0x18003598a  xor     rax, rsp
0x18003598d  mov     [rbp+var_8], rax
0x180035991  xor     eax, eax
0x180035993  mov     ebx, edx
0x180035995  mov     r14d, r8d
0x180035998  mov     [rbp+var_20], rax
0x18003599c  mov     r15, rcx
0x18003599f  lea     rdx, [rbp+DstBuf]; DstBuf
0x1800359a3  xorps   xmm0, xmm0
0x1800359a6  mov     ecx, ebx; FileHandle
0x1800359a8  lea     r8d, [rax+18h]; MaxCharCount
0x1800359ac  movups  [rbp+DstBuf], xmm0
0x1800359b0  call    cs:__imp__read
0x1800359b6  cmp     eax, 18h
0x1800359b9  jnz     short loc_1800359E9
0x1800359bb  mov     ecx, dword ptr [rbp+DstBuf+4]
0x1800359be  add     ecx, 4; unsigned __int64
0x1800359c1  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800359c6  mov     rdi, rax
0x1800359c9  test    rax, rax
0x1800359cc  jz      short loc_1800359E9
0x1800359ce  mov     ecx, dword ptr [rbp+DstBuf+4]
0x1800359d1  add     ecx, 4; unsigned __int64
0x1800359d4  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800359d9  mov     rsi, rax
0x1800359dc  test    rax, rax
0x1800359df  jnz     short loc_180035A0B
0x1800359e1  mov     rcx, rdi; void *
0x1800359e4  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x1800359e9  xor     eax, eax
0x1800359eb  mov     rcx, [rbp+var_8]
0x1800359ef  xor     rcx, rsp; StackCookie
0x1800359f2  call    __security_check_cookie
0x1800359f7  mov     rbx, [rsp+60h+arg_18]
0x1800359ff  add     rsp, 60h
0x180035a03  pop     r15
0x180035a05  pop     r14
0x180035a07  pop     rdi
0x180035a08  pop     rsi
0x180035a09  pop     rbp
0x180035a0a  retn
0x180035a0b  xor     eax, eax
0x180035a0d  lea     rdx, [rbp+MaxCharCount]; DstBuf
0x180035a11  mov     ecx, ebx; FileHandle
0x180035a13  mov     qword ptr [rbp+MaxCharCount], rax
0x180035a17  mov     [rbp+var_10], eax
0x180035a1a  lea     r8d, [rax+0Ch]; MaxCharCount
0x180035a1e  call    cs:__imp__read
0x180035a24  cmp     eax, 0Ch
0x180035a27  jnz     short loc_180035A86
0x180035a29  mov     r8d, [rbp+MaxCharCount+4]; MaxCharCount
0x180035a2d  test    r8d, r8d
0x180035a30  jz      short loc_180035A7F
0x180035a32  mov     rdx, rdi; DstBuf
0x180035a35  mov     ecx, ebx; FileHandle
0x180035a37  call    cs:__imp__read
0x180035a3d  mov     r8d, [rbp+MaxCharCount+4]
0x180035a41  cmp     eax, r8d
0x180035a44  jnz     short loc_180035A86
0x180035a46  cmp     byte ptr [rbp+MaxCharCount], 0
0x180035a4a  mov     rdx, rdi
0x180035a4d  jz      short loc_180035A74
0x180035a4f  movsx   eax, byte ptr [rbp+DstBuf+1]
0x180035a53  mov     r9, rsi
0x180035a56  mov     [rsp+60h+var_38], eax
0x180035a5a  mov     rcx, r15
0x180035a5d  mov     eax, [rbp+var_10]
0x180035a60  mov     [rsp+60h+var_40], eax
0x180035a64  call    ?UncompressBuffer@CMRCICompression@@QEAAIPEAEK0KW4CompressionLevel@1@@Z; CMRCICompression::UncompressBuffer(uchar *,ulong,uchar *,ulong,CMRCICompression::CompressionLevel)
0x180035a69  mov     r8d, eax; MaxCharCount
0x180035a6c  cmp     eax, 0FFFFFFFFh
0x180035a6f  jz      short loc_180035A86
0x180035a71  mov     rdx, rsi; Buf
0x180035a74  mov     ecx, r14d; FileHandle
0x180035a77  call    cs:__imp__write
0x180035a7d  jmp     short loc_180035A0B
0x180035a7f  mov     ebx, 1
0x180035a84  jmp     short loc_180035A88
0x180035a86  xor     ebx, ebx
0x180035a88  mov     ecx, r14d; FileHandle
0x180035a8b  call    cs:__imp__filelengthi64
0x180035a91  xor     ecx, ecx
0x180035a93  cmp     rax, [rbp+var_20]
0x180035a97  cmovnz  ebx, ecx
0x180035a9a  mov     rcx, rdi; void *
0x180035a9d  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180035aa2  mov     rcx, rsi; void *
0x180035aa5  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180035aaa  mov     eax, ebx
0x180035aac  jmp     loc_1800359EB
```
