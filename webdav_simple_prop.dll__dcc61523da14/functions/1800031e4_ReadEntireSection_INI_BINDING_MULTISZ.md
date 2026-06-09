# ReadEntireSection(INI_BINDING *,MULTISZ *)

- ea: `0x1800031e4`
- end: `0x180003277`
- name: `?ReadEntireSection@@YAJPEAUINI_BINDING@@PEAVMULTISZ@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(LPCWSTR *, LPWSTR *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001a04`
- `0x180001cdc`
- `0x180002080`

## callees

- `0x1800031e4`

## import_xrefs

- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x1800031fb`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x1800031fb`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003209`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003250`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003209`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003250`
- `iisutil!?RecalcLen@MULTISZ@@QEAAXXZ` at `0x18000326f`
- `iisutil!?RecalcLen@MULTISZ@@QEAAXXZ` at `0x18000326f`
- `KERNEL32!GetPrivateProfileSectionW` at `0x180003227`
- `KERNEL32!GetPrivateProfileSectionW` at `0x180003227`

## pseudocode

```c
__int64 __fastcall ReadEntireSection(LPCWSTR *a1, LPWSTR *a2)
{
  DWORD v4; // ebx
  unsigned int v5; // edx
  unsigned int v6; // ebx

  v4 = 2048;
  MULTISZ::Reset((MULTISZ *)a2);
  if ( BUFFER::Resize((BUFFER *)a2, 0x1000u) )
  {
    while ( 1 )
    {
      if ( GetPrivateProfileSectionW(a1[11], a2[4], v4, a1[4]) < v4 - 2 )
      {
        v6 = 0;
        MULTISZ::RecalcLen((MULTISZ *)a2);
        return v6;
      }
      v5 = 2 * v4;
      if ( v4 >= 0x7A120 )
        break;
      if ( v5 <= 0x7A120 )
        goto LABEL_7;
      v5 = 500000;
      v4 = 500000;
LABEL_8:
      if ( !BUFFER::Resize((BUFFER *)a2, 2 * v5) )
        return (unsigned int)-2147024888;
    }
    if ( v5 > 0x7A120 )
      return (unsigned int)-2147024888;
LABEL_7:
    v4 *= 2;
    goto LABEL_8;
  }
  return (unsigned int)-2147024888;
}

```

## disassembly

```asm
0x1800031e4  push    rbx
0x1800031e6  push    rbp
0x1800031e7  push    rsi
0x1800031e8  push    rdi
0x1800031e9  sub     rsp, 28h
0x1800031ed  mov     rsi, rcx
0x1800031f0  mov     rdi, rdx
0x1800031f3  mov     rcx, rdx
0x1800031f6  mov     ebx, 800h
0x1800031fb  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x180003201  mov     edx, 1000h
0x180003206  mov     rcx, rdi
0x180003209  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000320f  test    al, al
0x180003211  jz      short loc_18000325A
0x180003213  mov     ebp, 7A120h
0x180003218  mov     r9, [rsi+20h]; lpFileName
0x18000321c  mov     r8d, ebx; nSize
0x18000321f  mov     rdx, [rdi+20h]; lpReturnedString
0x180003223  mov     rcx, [rsi+58h]; lpAppName
0x180003227  call    cs:__imp_GetPrivateProfileSectionW
0x18000322d  lea     ecx, [rbx-2]
0x180003230  cmp     eax, ecx
0x180003232  jb      short loc_18000326A
0x180003234  lea     edx, [rbx+rbx]
0x180003237  cmp     ebx, ebp
0x180003239  jnb     short loc_180003245
0x18000323b  cmp     edx, ebp
0x18000323d  jbe     short loc_180003249
0x18000323f  mov     edx, ebp
0x180003241  mov     ebx, ebp
0x180003243  jmp     short loc_18000324B
0x180003245  cmp     edx, ebp
0x180003247  ja      short loc_18000325A
0x180003249  mov     ebx, edx
0x18000324b  add     edx, edx
0x18000324d  mov     rcx, rdi
0x180003250  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180003256  test    al, al
0x180003258  jnz     short loc_180003218
0x18000325a  mov     ebx, 80070008h
0x18000325f  mov     eax, ebx
0x180003261  add     rsp, 28h
0x180003265  pop     rdi
0x180003266  pop     rsi
0x180003267  pop     rbp
0x180003268  pop     rbx
0x180003269  retn
0x18000326a  xor     ebx, ebx
0x18000326c  mov     rcx, rdi
0x18000326f  call    cs:__imp_?RecalcLen@MULTISZ@@QEAAXXZ; MULTISZ::RecalcLen(void)
0x180003275  jmp     short loc_18000325F
```
