# CMRCICompression::GetCompressedFileInfo(ushort const *,CMRCICompression::CompressionLevel &,ulong &,_FILETIME &,__int64 &)

- ea: `0x1800357c0`
- end: `0x180035871`
- name: `?GetCompressedFileInfo@CMRCICompression@@SAHPEBGAEAW4CompressionLevel@1@AEAKAEAU_FILETIME@@AEA_J@Z`
- size: `177`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum CMRCICompression::CompressionLevel *, unsigned int *, struct _FILETIME *, __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800357c0`
- `0x180044310`

## import_xrefs

- `msvcrt!_close` at `0x18003584f`
- `msvcrt!_close` at `0x18003584f`
- `msvcrt!_read` at `0x18003581e`
- `msvcrt!_read` at `0x18003581e`
- `msvcrt!_wopen` at `0x1800357f7`
- `msvcrt!_wopen` at `0x1800357f7`

## pseudocode

```c
__int64 __fastcall CMRCICompression::GetCompressedFileInfo(
        const unsigned __int16 *a1,
        enum CMRCICompression::CompressionLevel *a2,
        unsigned int *a3,
        struct _FILETIME *a4,
        __int64 *a5)
{
  unsigned int v8; // ebx
  int v9; // edi
  __int128 DstBuf; // [rsp+20h] [rbp-58h] BYREF
  __int64 v12; // [rsp+30h] [rbp-48h]

  v8 = 0;
  v9 = _wopen(a1, 0x8000, 0);
  if ( v9 != -1 )
  {
    v12 = 0;
    DstBuf = 0;
    if ( _read(v9, &DstBuf, 0x18u) == 24 )
    {
      v8 = 1;
      *(_DWORD *)a2 = (char)DstBuf;
      *a3 = DWORD1(DstBuf);
      *a4 = *(struct _FILETIME *)((char *)&DstBuf + 8);
      *a5 = v12;
    }
    _close(v9);
  }
  return v8;
}

```

## disassembly

```asm
0x1800357c0  push    rbx
0x1800357c2  push    rbp
0x1800357c3  push    rsi
0x1800357c4  push    rdi
0x1800357c5  push    r14
0x1800357c7  push    r15
0x1800357c9  sub     rsp, 48h
0x1800357cd  mov     rax, cs:__security_cookie
0x1800357d4  xor     rax, rsp
0x1800357d7  mov     [rsp+78h+var_40], rax
0x1800357dc  mov     rbp, [rsp+78h+arg_20]
0x1800357e4  mov     r14, r8
0x1800357e7  mov     rsi, rdx
0x1800357ea  xor     r8d, r8d
0x1800357ed  mov     edx, 8000h; OpenFlag
0x1800357f2  mov     r15, r9
0x1800357f5  xor     ebx, ebx
0x1800357f7  call    cs:__imp__wopen
0x1800357fd  mov     edi, eax
0x1800357ff  cmp     eax, 0FFFFFFFFh
0x180035802  jz      short loc_180035855
0x180035804  xorps   xmm0, xmm0
0x180035807  lea     r8d, [rbx+18h]; MaxCharCount
0x18003580b  xor     eax, eax
0x18003580d  lea     rdx, [rsp+78h+DstBuf]; DstBuf
0x180035812  mov     ecx, edi; FileHandle
0x180035814  mov     [rsp+78h+var_48], rax
0x180035819  movups  [rsp+78h+DstBuf], xmm0
0x18003581e  call    cs:__imp__read
0x180035824  cmp     eax, 18h
0x180035827  jnz     short loc_18003584D
0x180035829  movsx   eax, byte ptr [rsp+78h+DstBuf]
0x18003582e  mov     ebx, 1
0x180035833  mov     [rsi], eax
0x180035835  mov     eax, dword ptr [rsp+78h+DstBuf+4]
0x180035839  mov     [r14], eax
0x18003583c  mov     rax, qword ptr [rsp+78h+DstBuf+8]
0x180035841  mov     [r15], rax
0x180035844  mov     rax, [rsp+78h+var_48]
0x180035849  mov     [rbp+0], rax
0x18003584d  mov     ecx, edi; FileHandle
0x18003584f  call    cs:__imp__close
0x180035855  mov     eax, ebx
0x180035857  mov     rcx, [rsp+78h+var_40]
0x18003585c  xor     rcx, rsp; StackCookie
0x18003585f  call    __security_check_cookie
0x180035864  add     rsp, 48h
0x180035868  pop     r15
0x18003586a  pop     r14
0x18003586c  pop     rdi
0x18003586d  pop     rsi
0x18003586e  pop     rbp
0x18003586f  pop     rbx
0x180035870  retn
```
