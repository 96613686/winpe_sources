# TTEmbedFontEx

- ea: `0x18001f950`
- end: `0x18001fca7`
- name: `TTEmbedFontEx`
- size: `855`
- prototype: `LONG __stdcall(HDC hDC, ULONG ulFlags, ULONG ulCharSet, ULONG *pulPrivStatus, ULONG *pulStatus, WRITEEMBEDPROC lpfnWriteToStream, LPVOID lpvWriteStream, ULONG *pulCharCodeSet, USHORT usCharCodeCount, USHORT usLanguage, TTEMBEDINFO *pTTEmbedInfo)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001f830`

## callees

- `0x180019dc0`
- `0x18001b538`
- `0x18001ecf8`
- `0x18001ef10`
- `0x18001ef44`
- `0x18001f950`
- `0x180021394`
- `0x1800271fc`
- `0x18002a566`
- `0x18002a590`

## pseudocode

```c
LONG __stdcall TTEmbedFontEx(
        HDC hDC,
        ULONG ulFlags,
        ULONG ulCharSet,
        ULONG *pulPrivStatus,
        ULONG *pulStatus,
        WRITEEMBEDPROC lpfnWriteToStream,
        LPVOID lpvWriteStream,
        ULONG *pulCharCodeSet,
        USHORT usCharCodeCount,
        USHORT usLanguage,
        TTEMBEDINFO *pTTEmbedInfo)
{
  unsigned int v15; // r12d
  void *v16; // r14
  unsigned int SFNTImage; // eax
  LONG v19; // edi
  unsigned int v20; // edi
  void *v21; // rbx
  unsigned int v22; // edi
  unsigned int v23; // ebx
  ULONG v24; // [rsp+20h] [rbp-508h]
  unsigned int v25; // [rsp+A4h] [rbp-484h] BYREF
  __int64 v26; // [rsp+A8h] [rbp-480h] BYREF
  LPVOID lpMem; // [rsp+B0h] [rbp-478h]
  ULONG v28; // [rsp+B8h] [rbp-470h]
  LPVOID v29[3]; // [rsp+C0h] [rbp-468h] BYREF
  LPVOID v30; // [rsp+D8h] [rbp-450h]
  WRITEEMBEDPROC v31; // [rsp+E0h] [rbp-448h]
  ULONG *v32; // [rsp+E8h] [rbp-440h]
  _OWORD v33[2]; // [rsp+F0h] [rbp-438h] BYREF
  __int64 v34; // [rsp+110h] [rbp-418h]
  _BYTE v35[936]; // [rsp+120h] [rbp-408h] BYREF
  HDC v36; // [rsp+4C8h] [rbp-60h]
  unsigned int v37; // [rsp+4D0h] [rbp-58h]

  v32 = pulStatus;
  v31 = lpfnWriteToStream;
  v30 = lpvWriteStream;
  v29[2] = pulCharCodeSet;
  v29[1] = pTTEmbedInfo;
  v15 = 0;
  memset_0(v35, 0, 0x3B8u);
  v26 = 0;
  memset(v33, 0, sizeof(v33));
  v34 = 0;
  lpMem = 0;
  v16 = 0;
  v29[0] = 0;
  v25 = 0;
  if ( (ulFlags & 0xCFFFFF0A) != 0 )
    return 268;
  if ( !hDC )
    return 6;
  v36 = hDC;
  v37 = 0;
  if ( ulCharSet - 1 > 2 )
    return 21;
  if ( ulCharSet == 3 )
  {
    ulFlags |= 0x20000000u;
    v28 = ulFlags;
  }
  SFNTImage = GetSFNTImage(hDC, (__int64)&v26);
  v19 = SFNTImage;
  if ( SFNTImage )
  {
    LogTTEmbedFontEx(SFNTImage);
    return v19;
  }
  else
  {
    v20 = FillT2Description(hDC);
    if ( v20 )
    {
      T2free(lpMem);
      LogTTEmbedFontEx(v20);
      return v20;
    }
    else
    {
      if ( (ulFlags & 0x80u) != 0 )
      {
        ulFlags |= 0x10000000u;
        v28 = ulFlags;
      }
      if ( (ulFlags & 0x20) != 0 )
      {
        GetEUDCImage(hDC, (unsigned __int8 **)v29, &v25);
        v16 = v29[0];
        v15 = v25;
      }
      v24 = ulFlags;
      v21 = lpMem;
      v22 = T2EmbedFont(
              (_DWORD)lpMem,
              HIDWORD(v26),
              (_DWORD)v16,
              v15,
              v24,
              v26,
              (__int64)pulPrivStatus,
              (__int64)v32,
              (__int64)v31,
              (__int64)v30,
              usLanguage);
      FreeT2Description(v33);
      T2free(v21);
      T2free(v16);
      if ( v22 )
      {
        v23 = v37;
        if ( !v37 )
          v23 = v22;
        LogTTEmbedFontEx(v23);
        return v23;
      }
      else
      {
        LogTTEmbedFontEx(0);
        return 0;
      }
    }
  }
}

```

## disassembly

```asm
0x18001f950  push    rbx
0x18001f952  push    rsi
0x18001f953  push    rdi
0x18001f954  push    r12
0x18001f956  push    r13
0x18001f958  push    r14
0x18001f95a  push    r15
0x18001f95c  sub     rsp, 4F0h
0x18001f963  mov     rax, cs:__security_cookie
0x18001f96a  xor     rax, rsp
0x18001f96d  mov     [rsp+528h+var_48], rax
0x18001f975  mov     r13, r9
0x18001f978  mov     edi, r8d
0x18001f97b  mov     ebx, edx
0x18001f97d  mov     rsi, rcx
0x18001f980  mov     rax, [rsp+528h+pulStatus]
0x18001f988  mov     [rsp+528h+var_440], rax
0x18001f990  mov     rax, [rsp+528h+lpfnWriteToStream]
0x18001f998  mov     [rsp+528h+var_448], rax
0x18001f9a0  mov     rax, [rsp+528h+lpvWriteStream]
0x18001f9a8  mov     [rsp+528h+var_450], rax
0x18001f9b0  mov     rax, [rsp+528h+pulCharCodeSet]
0x18001f9b8  mov     [rsp+528h+var_458], rax
0x18001f9c0  mov     rax, [rsp+528h+pTTEmbedInfo]
0x18001f9c8  mov     [rsp+528h+var_460], rax
0x18001f9d0  xor     r12d, r12d
0x18001f9d3  mov     [rsp+528h+var_488], r12d
0x18001f9db  mov     dword ptr [rsp+528h+var_480+4], r12d
0x18001f9e3  xor     edx, edx; Val
0x18001f9e5  mov     r8d, 3B8h; Size
0x18001f9eb  lea     rcx, [rsp+528h+var_408]; void *
0x18001f9f3  call    memset_0
0x18001f9f8  mov     dword ptr [rsp+528h+var_480], r12d
0x18001fa00  mov     r15d, r12d
0x18001fa03  xorps   xmm0, xmm0
0x18001fa06  xor     eax, eax
0x18001fa08  movups  [rsp+528h+var_438], xmm0
0x18001fa10  movups  [rsp+528h+var_428], xmm0
0x18001fa18  mov     [rsp+528h+var_418], rax
0x18001fa20  mov     [rsp+528h+lpMem], r12
0x18001fa28  mov     r14d, r12d
0x18001fa2b  mov     [rsp+528h+var_468], r12
0x18001fa33  mov     [rsp+528h+var_484], r12d
0x18001fa3b  test    ebx, 0CFFFFF0Ah
0x18001fa41  jz      short loc_18001FA4D
0x18001fa43  mov     eax, 10Ch
0x18001fa48  jmp     loc_18001FC84
0x18001fa4d  test    rsi, rsi
0x18001fa50  jnz     short loc_18001FA5A
0x18001fa52  lea     eax, [rsi+6]
0x18001fa55  jmp     loc_18001FC84
0x18001fa5a  mov     [rsp+528h+var_60], rsi
0x18001fa62  mov     [rsp+528h+var_58], 0
0x18001fa6d  lea     eax, [rdi-1]
0x18001fa70  cmp     eax, 2
0x18001fa73  jbe     short loc_18001FA7F
0x18001fa75  mov     eax, 15h
0x18001fa7a  jmp     loc_18001FC84
0x18001fa7f  cmp     edi, 3
0x18001fa82  jnz     short loc_18001FA8F
0x18001fa84  bts     ebx, 1Dh
0x18001fa88  mov     [rsp+528h+var_470], ebx
0x18001fa8f  lea     rax, [rsp+528h+var_480]
0x18001fa97  mov     [rsp+528h+var_508], rax; __int64
0x18001fa9c  lea     r9, [rsp+528h+var_480+4]
0x18001faa4  lea     r8, [rsp+528h+lpMem]
0x18001faac  mov     rcx, rsi; hdc
0x18001faaf  call    GetSFNTImage
0x18001fab4  mov     edi, eax
0x18001fab6  mov     [rsp+528h+var_488], eax
0x18001fabd  test    eax, eax
0x18001fabf  jz      short loc_18001FACF
0x18001fac1  mov     ecx, eax
0x18001fac3  call    LogTTEmbedFontEx
0x18001fac8  mov     eax, edi
0x18001faca  jmp     loc_18001FC84
0x18001facf  lea     rdx, [rsp+528h+var_438]
0x18001fad7  mov     rcx, rsi; hdc
0x18001fada  call    FillT2Description
0x18001fadf  mov     edi, eax
0x18001fae1  mov     [rsp+528h+var_488], eax
0x18001fae8  test    eax, eax
0x18001faea  jz      short loc_18001FB07
0x18001faec  mov     rcx, [rsp+528h+lpMem]; lpMem
0x18001faf4  call    T2free
0x18001faf9  mov     ecx, edi
0x18001fafb  call    LogTTEmbedFontEx
0x18001fb00  mov     eax, edi
0x18001fb02  jmp     loc_18001FC84
0x18001fb07  test    bl, bl
0x18001fb09  jns     short loc_18001FB16
0x18001fb0b  bts     ebx, 1Ch
0x18001fb0f  mov     [rsp+528h+var_470], ebx
0x18001fb16  test    bl, 20h
0x18001fb19  jz      short loc_18001FB43
0x18001fb1b  lea     r8, [rsp+528h+var_484]
0x18001fb23  lea     rdx, [rsp+528h+var_468]
0x18001fb2b  mov     rcx, rsi; hdc
0x18001fb2e  call    GetEUDCImage
0x18001fb33  mov     r14, [rsp+528h+var_468]
0x18001fb3b  mov     r12d, [rsp+528h+var_484]
0x18001fb43  mov     ecx, 0FFFFh
0x18001fb48  lea     rax, [rsp+528h+var_408]
0x18001fb50  mov     [rsp+528h+var_498], rax
0x18001fb58  mov     rax, [rsp+528h+var_460]
0x18001fb60  mov     [rsp+528h+var_4A0], rax
0x18001fb68  lea     rax, [rsp+528h+var_438]
0x18001fb70  mov     [rsp+528h+var_4A8], rax
0x18001fb78  movzx   eax, [rsp+528h+usCharCodeCount]
0x18001fb80  mov     [rsp+528h+var_4B8], ax
0x18001fb85  mov     rax, [rsp+528h+var_458]
0x18001fb8d  mov     [rsp+528h+var_4C0], rax
0x18001fb92  mov     [rsp+528h+var_4C8], cx
0x18001fb97  movzx   eax, [rsp+528h+usLanguage]
0x18001fb9f  mov     [rsp+528h+var_4D8], ax
0x18001fba4  mov     rax, [rsp+528h+var_450]
0x18001fbac  mov     [rsp+528h+var_4E0], rax
0x18001fbb1  mov     rax, [rsp+528h+var_448]
0x18001fbb9  mov     [rsp+528h+var_4E8], rax
0x18001fbbe  mov     rax, [rsp+528h+var_440]
0x18001fbc6  mov     [rsp+528h+var_4F0], rax
0x18001fbcb  mov     [rsp+528h+var_4F8], r13
0x18001fbd0  mov     eax, dword ptr [rsp+528h+var_480]
0x18001fbd7  mov     [rsp+528h+var_500], eax
0x18001fbdb  mov     dword ptr [rsp+528h+var_508], ebx
0x18001fbdf  mov     r9d, r12d
0x18001fbe2  mov     r8, r14
0x18001fbe5  mov     edx, dword ptr [rsp+528h+var_480+4]
0x18001fbec  mov     rbx, [rsp+528h+lpMem]
0x18001fbf4  mov     rcx, rbx
0x18001fbf7  call    T2EmbedFont
0x18001fbfc  mov     edi, eax
0x18001fbfe  mov     [rsp+528h+var_488], eax
0x18001fc05  lea     rcx, [rsp+528h+var_438]
0x18001fc0d  call    FreeT2Description
0x18001fc12  mov     rcx, rbx; lpMem
0x18001fc15  call    T2free
0x18001fc1a  mov     rcx, r14; lpMem
0x18001fc1d  call    T2free
0x18001fc22  test    edi, edi
0x18001fc24  jz      short loc_18001FC44
0x18001fc26  mov     ebx, [rsp+528h+var_58]
0x18001fc2d  test    ebx, ebx
0x18001fc2f  cmovz   ebx, edi
0x18001fc32  mov     [rsp+528h+var_488], ebx
0x18001fc39  mov     ecx, ebx
0x18001fc3b  call    LogTTEmbedFontEx
0x18001fc40  mov     eax, ebx
0x18001fc42  jmp     short loc_18001FC84
0x18001fc44  jmp     short loc_18001FC7A
0x18001fc46  lea     rcx, [rsp+528h+var_438]
0x18001fc4e  call    FreeT2Description
0x18001fc53  mov     rcx, [rsp+528h+lpMem]; lpMem
0x18001fc5b  call    T2free
0x18001fc60  mov     rcx, [rsp+528h+var_468]; lpMem
0x18001fc68  call    T2free
0x18001fc6d  mov     r15d, 13h
0x18001fc73  mov     edi, [rsp+528h+var_488]
0x18001fc7a  mov     ecx, edi
0x18001fc7c  call    LogTTEmbedFontEx
0x18001fc81  mov     eax, r15d
0x18001fc84  mov     rcx, [rsp+528h+var_48]
0x18001fc8c  xor     rcx, rsp; StackCookie
0x18001fc8f  call    __security_check_cookie
0x18001fc94  add     rsp, 4F0h
0x18001fc9b  pop     r15
0x18001fc9d  pop     r14
0x18001fc9f  pop     r13
0x18001fca1  pop     r12
0x18001fca3  pop     rdi
0x18001fca4  pop     rsi
0x18001fca5  pop     rbx
0x18001fca6  retn
```
