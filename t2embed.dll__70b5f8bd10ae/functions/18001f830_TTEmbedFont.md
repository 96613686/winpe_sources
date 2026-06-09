# TTEmbedFont

- ea: `0x18001f830`
- end: `0x18001f94a`
- name: `TTEmbedFont`
- size: `282`
- prototype: `LONG __stdcall(HDC hDC, ULONG ulFlags, ULONG ulCharSet, ULONG *pulPrivStatus, ULONG *pulStatus, WRITEEMBEDPROC lpfnWriteToStream, LPVOID lpvWriteStream, USHORT *pusCharCodeSet, USHORT usCharCodeCount, USHORT usLanguage, TTEMBEDINFO *pTTEmbedInfo)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180017ee0`
- `0x180019dc0`
- `0x18001f830`
- `0x18001f950`
- `0x180027180`
- `0x1800272f4`

## pseudocode

```c
LONG __stdcall TTEmbedFont(
        HDC hDC,
        ULONG ulFlags,
        ULONG ulCharSet,
        ULONG *pulPrivStatus,
        ULONG *pulStatus,
        WRITEEMBEDPROC lpfnWriteToStream,
        LPVOID lpvWriteStream,
        USHORT *pusCharCodeSet,
        USHORT usCharCodeCount,
        USHORT usLanguage,
        TTEMBEDINFO *pTTEmbedInfo)
{
  ULONG *pulCharCodeSet; // rbx
  USHORT v16; // r10
  unsigned int v17; // edi
  USHORT v19[36]; // [rsp+60h] [rbp-48h] BYREF

  pulCharCodeSet = 0;
  v16 = 0;
  v19[0] = 0;
  if ( pusCharCodeSet )
  {
    pulCharCodeSet = (ULONG *)T2malloc(4 * (unsigned int)usCharCodeCount);
    if ( !pulCharCodeSet
      || (unsigned __int16)UTF16toUCS4(
                             (_DWORD)pusCharCodeSet,
                             usCharCodeCount,
                             (_DWORD)pulCharCodeSet,
                             usCharCodeCount,
                             (__int64)v19) )
    {
      LogTTEmbedFont(7);
      return 7;
    }
    v16 = v19[0];
  }
  v17 = TTEmbedFontEx(
          hDC,
          ulFlags,
          ulCharSet,
          pulPrivStatus,
          pulStatus,
          lpfnWriteToStream,
          lpvWriteStream,
          pulCharCodeSet,
          v16,
          usLanguage,
          pTTEmbedInfo);
  if ( pulCharCodeSet )
    T2free(pulCharCodeSet);
  LogTTEmbedFont(v17);
  return v17;
}

```

## disassembly

```asm
0x18001f830  push    rbx
0x18001f832  push    rbp
0x18001f833  push    rdi
0x18001f834  push    r12
0x18001f836  push    r13
0x18001f838  push    r14
0x18001f83a  push    r15
0x18001f83c  sub     rsp, 70h
0x18001f840  xor     r13d, r13d
0x18001f843  mov     rbp, r9
0x18001f846  mov     r14d, r8d
0x18001f849  mov     r15d, edx
0x18001f84c  mov     r12, rcx
0x18001f84f  mov     ebx, r13d
0x18001f852  mov     r10d, r13d
0x18001f855  mov     [rsp+0A8h+var_48], r13w
0x18001f85b  cmp     [rsp+0A8h+pusCharCodeSet], r13
0x18001f863  jz      short loc_18001F8B5
0x18001f865  movzx   edi, [rsp+0A8h+usCharCodeCount]
0x18001f86d  xor     edx, edx
0x18001f86f  mov     ecx, edi
0x18001f871  shl     ecx, 2; dwBytes
0x18001f874  call    T2malloc
0x18001f879  mov     rbx, rax
0x18001f87c  test    rax, rax
0x18001f87f  jz      loc_18001F93A
0x18001f885  mov     rcx, [rsp+0A8h+pusCharCodeSet]
0x18001f88d  lea     rax, [rsp+0A8h+var_48]
0x18001f892  movzx   r9d, di
0x18001f896  mov     [rsp+0A8h+var_88], rax
0x18001f89b  mov     r8, rbx
0x18001f89e  movzx   edx, di
0x18001f8a1  call    UTF16toUCS4
0x18001f8a6  test    ax, ax
0x18001f8a9  jnz     loc_18001F93A
0x18001f8af  movzx   r10d, [rsp+0A8h+var_48]
0x18001f8b5  mov     rax, [rsp+0A8h+pTTEmbedInfo]
0x18001f8bd  mov     r9, rbp; pulPrivStatus
0x18001f8c0  mov     [rsp+0A8h+var_58], rax; pTTEmbedInfo
0x18001f8c5  mov     r8d, r14d; ulCharSet
0x18001f8c8  movzx   eax, [rsp+0A8h+usLanguage]
0x18001f8d0  mov     edx, r15d; ulFlags
0x18001f8d3  mov     [rsp+0A8h+var_60], ax; usLanguage
0x18001f8d8  mov     rcx, r12; hDC
0x18001f8db  mov     rax, [rsp+0A8h+lpvWriteStream]
0x18001f8e3  mov     [rsp+0A8h+var_68], r10w; usCharCodeCount
0x18001f8e9  mov     [rsp+0A8h+pulCharCodeSet], rbx; pulCharCodeSet
0x18001f8ee  mov     [rsp+0A8h+var_78], rax; lpvWriteStream
0x18001f8f3  mov     rax, [rsp+0A8h+lpfnWriteToStream]
0x18001f8fb  mov     [rsp+0A8h+var_80], rax; lpfnWriteToStream
0x18001f900  mov     rax, [rsp+0A8h+pulStatus]
0x18001f908  mov     [rsp+0A8h+var_88], rax; pulStatus
0x18001f90d  call    TTEmbedFontEx
0x18001f912  mov     edi, eax
0x18001f914  test    rbx, rbx
0x18001f917  jz      short loc_18001F921
0x18001f919  mov     rcx, rbx; lpMem
0x18001f91c  call    T2free
0x18001f921  mov     ecx, edi
0x18001f923  call    LogTTEmbedFont
0x18001f928  mov     eax, edi
0x18001f92a  add     rsp, 70h
0x18001f92e  pop     r15
0x18001f930  pop     r14
0x18001f932  pop     r13
0x18001f934  pop     r12
0x18001f936  pop     rdi
0x18001f937  pop     rbp
0x18001f938  pop     rbx
0x18001f939  retn
0x18001f93a  mov     ebx, 7
0x18001f93f  mov     ecx, ebx
0x18001f941  call    LogTTEmbedFont
0x18001f946  mov     eax, ebx
0x18001f948  jmp     short loc_18001F92A
```
