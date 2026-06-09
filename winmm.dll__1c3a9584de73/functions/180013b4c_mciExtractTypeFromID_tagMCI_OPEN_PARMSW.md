# mciExtractTypeFromID(tagMCI_OPEN_PARMSW *)

- ea: `0x180013b4c`
- end: `0x180013c2e`
- name: `?mciExtractTypeFromID@@YAIPEAUtagMCI_OPEN_PARMSW@@@Z`
- size: `226`
- prototype: `unsigned int __fastcall(struct tagMCI_OPEN_PARMSW *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015480`

## callees

- `0x18000b6d4`
- `0x18000f9d8`
- `0x180013b4c`
- `0x18001a408`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013b8a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013b8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013c15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013c15`

## pseudocode

```c
__int64 __fastcall mciExtractTypeFromID(struct tagMCI_OPEN_PARMSW *a1)
{
  WCHAR *v2; // rax
  WCHAR *v3; // rdi
  int StringW; // eax
  unsigned int v6; // ebx

  v2 = (WCHAR *)winmmAlloc(0xA2u);
  v3 = v2;
  if ( !v2 )
    return 264;
  StringW = LoadStringW(ghInst, LOWORD(a1->lpstrDeviceType), v2, 80);
  if ( !StringW )
  {
    v6 = 281;
LABEL_14:
    HeapFree(hHeap, 0, v3);
    return v6;
  }
  if ( WORD1(a1->lpstrDeviceType) )
  {
    if ( StringW > 69 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids);
      }
      v6 = 311;
      goto LABEL_14;
    }
    if ( StringCbPrintfW(&v3[StringW], 162 - StringW, szUnsignedFormat, WORD1(a1->lpstrDeviceType)) < 0 )
    {
      v6 = 268;
      goto LABEL_14;
    }
  }
  a1->lpstrDeviceType = v3;
  return 0;
}

```

## disassembly

```asm
0x180013b4c  push    rbx
0x180013b4e  push    rbp
0x180013b4f  push    rsi
0x180013b50  push    rdi
0x180013b51  sub     rsp, 28h
0x180013b55  mov     rbx, rcx
0x180013b58  mov     esi, 0A2h
0x180013b5d  mov     ecx, esi; Size
0x180013b5f  call    winmmAlloc
0x180013b64  xor     ebp, ebp
0x180013b66  mov     rdi, rax
0x180013b69  test    rax, rax
0x180013b6c  jnz     short loc_180013B76
0x180013b6e  lea     eax, [rsi+66h]
0x180013b71  jmp     loc_180013C25
0x180013b76  movzx   edx, word ptr [rbx+0Ch]; uID
0x180013b7a  mov     r9d, 50h ; 'P'; cchBufferMax
0x180013b80  mov     rcx, cs:ghInst; hInstance
0x180013b87  mov     r8, rdi; lpBuffer
0x180013b8a  call    cs:__imp_LoadStringW
0x180013b90  test    eax, eax
0x180013b92  jnz     short loc_180013B9B
0x180013b94  mov     ebx, 119h
0x180013b99  jmp     short loc_180013C09
0x180013b9b  cmp     [rbx+0Eh], bp
0x180013b9f  jz      short loc_180013C1F
0x180013ba1  cmp     eax, 45h ; 'E'
0x180013ba4  jle     short loc_180013BE4
0x180013ba6  mov     rcx, cs:WPP_GLOBAL_Control
0x180013bad  lea     rax, WPP_GLOBAL_Control
0x180013bb4  cmp     rcx, rax
0x180013bb7  jz      short loc_180013BDD
0x180013bb9  test    dword ptr [rcx+1Ch], 400000h
0x180013bc0  jz      short loc_180013BDD
0x180013bc2  cmp     byte ptr [rcx+19h], 1
0x180013bc6  jb      short loc_180013BDD
0x180013bc8  mov     rcx, [rcx+10h]
0x180013bcc  lea     r8, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids
0x180013bd3  mov     edx, 27h ; '''
0x180013bd8  call    WPP_SF_
0x180013bdd  mov     ebx, 137h
0x180013be2  jmp     short loc_180013C09
0x180013be4  movzx   r9d, word ptr [rbx+0Eh]
0x180013be9  lea     r8, ?szUnsignedFormat@@3PAGA; "%u"
0x180013bf0  sub     esi, eax
0x180013bf2  cdqe
0x180013bf4  movsxd  rdx, esi; unsigned __int64
0x180013bf7  lea     rcx, [rdi+rax*2]; unsigned __int16 *
0x180013bfb  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013c00  test    eax, eax
0x180013c02  jns     short loc_180013C1F
0x180013c04  mov     ebx, 10Ch
0x180013c09  mov     rcx, cs:hHeap; hHeap
0x180013c10  mov     r8, rdi; lpMem
0x180013c13  xor     edx, edx; dwFlags
0x180013c15  call    cs:__imp_HeapFree
0x180013c1b  mov     eax, ebx
0x180013c1d  jmp     short loc_180013C25
0x180013c1f  mov     [rbx+0Ch], rdi
0x180013c23  xor     eax, eax
0x180013c25  add     rsp, 28h
0x180013c29  pop     rdi
0x180013c2a  pop     rsi
0x180013c2b  pop     rbp
0x180013c2c  pop     rbx
0x180013c2d  retn
```
