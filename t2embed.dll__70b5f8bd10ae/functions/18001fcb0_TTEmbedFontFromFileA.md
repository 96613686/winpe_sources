# TTEmbedFontFromFileA

- ea: `0x18001fcb0`
- end: `0x180020074`
- name: `TTEmbedFontFromFileA`
- size: `964`
- prototype: `LONG __stdcall(HDC hDC, LPCSTR szFontFileName, USHORT usTTCIndex, ULONG ulFlags, ULONG ulCharSet, ULONG *pulPrivStatus, ULONG *pulStatus, WRITEEMBEDPROC lpfnWriteToStream, LPVOID lpvWriteStream, USHORT *pusCharCodeSet, USHORT usCharCodeCount, USHORT usLanguage, TTEMBEDINFO *pTTEmbedInfo)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x180017ee0`
- `0x180019dc0`
- `0x18001ecf8`
- `0x18001ef10`
- `0x18001ef44`
- `0x18001f11c`
- `0x18001fcb0`
- `0x180021394`
- `0x180027278`
- `0x1800272f4`
- `0x18002a566`
- `0x18002a590`

## pseudocode

```c
LONG __stdcall TTEmbedFontFromFileA(
        HDC hDC,
        LPCSTR szFontFileName,
        USHORT usTTCIndex,
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
  void *v17; // r14
  unsigned int SFNTImageFromFile; // eax
  LONG v20; // ebx
  unsigned int v21; // edi
  void *v22; // rbx
  int v23; // esi
  unsigned int v24; // ebx
  __int16 v25; // [rsp+A4h] [rbp-484h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp-480h] BYREF
  unsigned int v27; // [rsp+B0h] [rbp-478h] BYREF
  unsigned int v28; // [rsp+B4h] [rbp-474h] BYREF
  LPVOID v29; // [rsp+B8h] [rbp-470h] BYREF
  USHORT *v30; // [rsp+C0h] [rbp-468h]
  void *v31; // [rsp+C8h] [rbp-460h]
  TTEMBEDINFO *v32; // [rsp+D0h] [rbp-458h]
  LPVOID v33; // [rsp+D8h] [rbp-450h]
  WRITEEMBEDPROC v34; // [rsp+E0h] [rbp-448h]
  ULONG *v35; // [rsp+E8h] [rbp-440h]
  ULONG *v36; // [rsp+F0h] [rbp-438h]
  _OWORD v37[2]; // [rsp+F8h] [rbp-430h] BYREF
  __int64 v38; // [rsp+118h] [rbp-410h]
  _BYTE v39[936]; // [rsp+120h] [rbp-408h] BYREF
  HDC v40; // [rsp+4C8h] [rbp-60h]
  unsigned int v41; // [rsp+4D0h] [rbp-58h]

  v36 = pulPrivStatus;
  v35 = pulStatus;
  v34 = lpfnWriteToStream;
  v33 = lpvWriteStream;
  v30 = pusCharCodeSet;
  v32 = pTTEmbedInfo;
  v17 = 0;
  v28 = 0;
  memset_0(v39, 0, 0x3B8u);
  memset(v37, 0, sizeof(v37));
  v38 = 0;
  lpMem = 0;
  v29 = 0;
  v27 = 0;
  if ( (ulFlags & 0xCFFFFF0A) != 0 )
    return 268;
  if ( !hDC )
    return 6;
  v40 = hDC;
  v41 = 0;
  if ( ulCharSet - 1 > 1 )
    return 21;
  SFNTImageFromFile = GetSFNTImageFromFile(szFontFileName, usTTCIndex, (unsigned __int8 **)&lpMem, &v28);
  v20 = SFNTImageFromFile;
  if ( SFNTImageFromFile )
  {
    LogTTEmbedFontFromFileA(SFNTImageFromFile);
    return v20;
  }
  else
  {
    v21 = FillT2Description(hDC);
    if ( v21 )
    {
      T2free(lpMem);
      LogTTEmbedFontFromFileA(v21);
      return v21;
    }
    else
    {
      if ( (ulFlags & 0x20) != 0 )
      {
        GetEUDCImage(hDC, (unsigned __int8 **)&v29, &v27);
        v17 = v29;
      }
      v22 = 0;
      v31 = 0;
      v25 = 0;
      v23 = (int)v30;
      if ( v30 )
      {
        v22 = (void *)T2malloc(4 * (unsigned int)usCharCodeCount);
        v31 = v22;
        if ( !v22 || (unsigned __int16)UTF16toUCS4(v23, usCharCodeCount, (_DWORD)v22, usCharCodeCount, (__int64)&v25) )
          v21 = 7;
      }
      if ( !v21 )
        v21 = T2EmbedFont(
                (_DWORD)lpMem,
                v28,
                (_DWORD)v17,
                v27,
                ulFlags,
                0,
                (__int64)v36,
                (__int64)v35,
                (__int64)v34,
                (__int64)v33,
                usLanguage);
      if ( v22 )
        T2free(v22);
      FreeT2Description(v37);
      T2free(lpMem);
      T2free(v17);
      if ( v21 )
      {
        v24 = v41;
        if ( !v41 )
          v24 = v21;
        LogTTEmbedFontFromFileA(v24);
        return v24;
      }
      else
      {
        LogTTEmbedFontFromFileA(0);
        return 0;
      }
    }
  }
}

```

## disassembly

```asm
0x18001fcb0  push    rbx
0x18001fcb2  push    rsi
0x18001fcb3  push    rdi
0x18001fcb4  push    r12
0x18001fcb6  push    r13
0x18001fcb8  push    r14
0x18001fcba  push    r15
0x18001fcbc  sub     rsp, 4F0h
0x18001fcc3  mov     rax, cs:__security_cookie
0x18001fcca  xor     rax, rsp
0x18001fccd  mov     [rsp+528h+var_48], rax
0x18001fcd5  mov     r15d, r9d
0x18001fcd8  movzx   edi, r8w
0x18001fcdc  mov     rbx, rdx
0x18001fcdf  mov     rsi, rcx
0x18001fce2  mov     rax, [rsp+528h+pulPrivStatus]
0x18001fcea  mov     [rsp+528h+var_438], rax
0x18001fcf2  mov     rax, [rsp+528h+pulStatus]
0x18001fcfa  mov     [rsp+528h+var_440], rax
0x18001fd02  mov     rax, [rsp+528h+lpfnWriteToStream]
0x18001fd0a  mov     [rsp+528h+var_448], rax
0x18001fd12  mov     rax, [rsp+528h+lpvWriteStream]
0x18001fd1a  mov     [rsp+528h+var_450], rax
0x18001fd22  mov     rax, [rsp+528h+pusCharCodeSet]
0x18001fd2a  mov     [rsp+528h+var_468], rax
0x18001fd32  movzx   r12d, [rsp+528h+usCharCodeCount]
0x18001fd3b  mov     rax, [rsp+528h+pTTEmbedInfo]
0x18001fd43  mov     [rsp+528h+var_458], rax
0x18001fd4b  xor     r14d, r14d
0x18001fd4e  mov     [rsp+528h+var_488], r14d
0x18001fd56  mov     [rsp+528h+var_474], r14d
0x18001fd5e  xor     edx, edx; Val
0x18001fd60  mov     r8d, 3B8h; Size
0x18001fd66  lea     rcx, [rsp+528h+var_408]; void *
0x18001fd6e  call    memset_0
0x18001fd73  mov     r13d, r14d
0x18001fd76  xorps   xmm0, xmm0
0x18001fd79  xor     eax, eax
0x18001fd7b  movups  [rsp+528h+var_430], xmm0
0x18001fd83  movups  [rsp+528h+var_420], xmm0
0x18001fd8b  mov     [rsp+528h+var_410], rax
0x18001fd93  mov     [rsp+528h+lpMem], r14
0x18001fd9b  mov     [rsp+528h+var_470], r14
0x18001fda3  mov     [rsp+528h+var_478], eax
0x18001fdaa  test    r15d, 0CFFFFF0Ah
0x18001fdb1  jz      short loc_18001FDBD
0x18001fdb3  mov     eax, 10Ch
0x18001fdb8  jmp     loc_180020051
0x18001fdbd  test    rsi, rsi
0x18001fdc0  jnz     short loc_18001FDCA
0x18001fdc2  lea     eax, [rsi+6]
0x18001fdc5  jmp     loc_180020051
0x18001fdca  mov     [rsp+528h+var_60], rsi
0x18001fdd2  mov     [rsp+528h+var_58], eax
0x18001fdd9  mov     eax, [rsp+528h+ulCharSet]
0x18001fde0  dec     eax
0x18001fde2  cmp     eax, 1
0x18001fde5  ja      loc_18002000C
0x18001fdeb  lea     r9, [rsp+528h+var_474]
0x18001fdf3  lea     r8, [rsp+528h+lpMem]
0x18001fdfb  movzx   edx, di
0x18001fdfe  mov     rcx, rbx
0x18001fe01  call    GetSFNTImageFromFile
0x18001fe06  mov     ebx, eax
0x18001fe08  mov     [rsp+528h+var_488], eax
0x18001fe0f  test    eax, eax
0x18001fe11  jz      short loc_18001FE21
0x18001fe13  mov     ecx, eax
0x18001fe15  call    LogTTEmbedFontFromFileA
0x18001fe1a  mov     eax, ebx
0x18001fe1c  jmp     loc_180020051
0x18001fe21  lea     rdx, [rsp+528h+var_430]
0x18001fe29  mov     rcx, rsi; hdc
0x18001fe2c  call    FillT2Description
0x18001fe31  mov     edi, eax
0x18001fe33  mov     [rsp+528h+var_488], eax
0x18001fe3a  xor     ecx, ecx
0x18001fe3c  test    eax, eax
0x18001fe3e  jz      short loc_18001FE5B
0x18001fe40  mov     rcx, [rsp+528h+lpMem]; lpMem
0x18001fe48  call    T2free
0x18001fe4d  mov     ecx, edi
0x18001fe4f  call    LogTTEmbedFontFromFileA
0x18001fe54  mov     eax, edi
0x18001fe56  jmp     loc_180020051
0x18001fe5b  test    r15b, 20h
0x18001fe5f  jz      short loc_18001FE83
0x18001fe61  lea     r8, [rsp+528h+var_478]
0x18001fe69  lea     rdx, [rsp+528h+var_470]
0x18001fe71  mov     rcx, rsi; hdc
0x18001fe74  call    GetEUDCImage
0x18001fe79  mov     r14, [rsp+528h+var_470]
0x18001fe81  xor     ecx, ecx
0x18001fe83  mov     rbx, rcx
0x18001fe86  mov     [rsp+528h+var_460], rcx
0x18001fe8e  mov     [rsp+528h+var_484], cx
0x18001fe96  mov     rsi, [rsp+528h+var_468]
0x18001fe9e  test    rsi, rsi
0x18001fea1  jz      short loc_18001FEF1
0x18001fea3  mov     ecx, r12d
0x18001fea6  shl     ecx, 2; dwBytes
0x18001fea9  xor     edx, edx
0x18001feab  call    T2malloc
0x18001feb0  mov     rbx, rax
0x18001feb3  mov     [rsp+528h+var_460], rax
0x18001febb  test    rax, rax
0x18001febe  jz      short loc_18001FEE5
0x18001fec0  lea     rax, [rsp+528h+var_484]
0x18001fec8  mov     [rsp+528h+var_508], rax
0x18001fecd  movzx   r9d, r12w
0x18001fed1  mov     r8, rbx
0x18001fed4  movzx   edx, r12w
0x18001fed8  mov     rcx, rsi
0x18001fedb  call    UTF16toUCS4
0x18001fee0  test    ax, ax
0x18001fee3  jz      short loc_18001FEF1
0x18001fee5  mov     edi, 7
0x18001feea  mov     [rsp+528h+var_488], edi
0x18001fef1  xor     esi, esi
0x18001fef3  test    edi, edi
0x18001fef5  jnz     loc_18001FFB9
0x18001fefb  mov     ecx, 0FFFFh
0x18001ff00  lea     rax, [rsp+528h+var_408]
0x18001ff08  mov     [rsp+528h+var_498], rax
0x18001ff10  mov     rax, [rsp+528h+var_458]
0x18001ff18  mov     [rsp+528h+var_4A0], rax
0x18001ff20  lea     rax, [rsp+528h+var_430]
0x18001ff28  mov     [rsp+528h+var_4A8], rax
0x18001ff30  movzx   eax, [rsp+528h+var_484]
0x18001ff38  mov     [rsp+528h+var_4B8], ax
0x18001ff3d  mov     [rsp+528h+var_4C0], rbx
0x18001ff42  mov     [rsp+528h+var_4C8], cx
0x18001ff47  movzx   eax, [rsp+528h+usLanguage]
0x18001ff4f  mov     [rsp+528h+var_4D8], ax
0x18001ff54  mov     rax, [rsp+528h+var_450]
0x18001ff5c  mov     [rsp+528h+var_4E0], rax
0x18001ff61  mov     rax, [rsp+528h+var_448]
0x18001ff69  mov     [rsp+528h+var_4E8], rax
0x18001ff6e  mov     rax, [rsp+528h+var_440]
0x18001ff76  mov     [rsp+528h+var_4F0], rax
0x18001ff7b  mov     rax, [rsp+528h+var_438]
0x18001ff83  mov     [rsp+528h+var_4F8], rax
0x18001ff88  mov     [rsp+528h+var_500], esi
0x18001ff8c  mov     dword ptr [rsp+528h+var_508], r15d
0x18001ff91  mov     r9d, [rsp+528h+var_478]
0x18001ff99  mov     r8, r14
0x18001ff9c  mov     edx, [rsp+528h+var_474]
0x18001ffa3  mov     rcx, [rsp+528h+lpMem]
0x18001ffab  call    T2EmbedFont
0x18001ffb0  mov     edi, eax
0x18001ffb2  mov     [rsp+528h+var_488], eax
0x18001ffb9  test    rbx, rbx
0x18001ffbc  jz      short loc_18001FFC6
0x18001ffbe  mov     rcx, rbx; lpMem
0x18001ffc1  call    T2free
0x18001ffc6  lea     rcx, [rsp+528h+var_430]
0x18001ffce  call    FreeT2Description
0x18001ffd3  mov     rcx, [rsp+528h+lpMem]; lpMem
0x18001ffdb  call    T2free
0x18001ffe0  mov     rcx, r14; lpMem
0x18001ffe3  call    T2free
0x18001ffe8  test    edi, edi
0x18001ffea  jz      short loc_18002000A
0x18001ffec  mov     ebx, [rsp+528h+var_58]
0x18001fff3  test    ebx, ebx
0x18001fff5  cmovz   ebx, edi
0x18001fff8  mov     [rsp+528h+var_488], ebx
0x18001ffff  mov     ecx, ebx
0x180020001  call    LogTTEmbedFontFromFileA
0x180020006  mov     eax, ebx
0x180020008  jmp     short loc_180020051
0x18002000a  jmp     short loc_180020047
0x18002000c  mov     eax, 15h
0x180020011  jmp     short loc_180020051
0x180020013  lea     rcx, [rsp+528h+var_430]
0x18002001b  call    FreeT2Description
0x180020020  mov     rcx, [rsp+528h+lpMem]; lpMem
0x180020028  call    T2free
0x18002002d  mov     rcx, [rsp+528h+var_470]; lpMem
0x180020035  call    T2free
0x18002003a  mov     r13d, 13h
0x180020040  mov     edi, [rsp+528h+var_488]
0x180020047  mov     ecx, edi
0x180020049  call    LogTTEmbedFontFromFileA
0x18002004e  mov     eax, r13d
0x180020051  mov     rcx, [rsp+528h+var_48]
0x180020059  xor     rcx, rsp; StackCookie
0x18002005c  call    __security_check_cookie
0x180020061  add     rsp, 4F0h
0x180020068  pop     r15
0x18002006a  pop     r14
0x18002006c  pop     r13
0x18002006e  pop     r12
0x180020070  pop     rdi
0x180020071  pop     rsi
0x180020072  pop     rbx
0x180020073  retn
```
