# CMRCICompression::CompressFileV1(int,int,ulong,CMRCICompression::CompressionLevel,CMRCIControl *)

- ea: `0x180035570`
- end: `0x1800357ac`
- name: `?CompressFileV1@CMRCICompression@@IEAAHHHKW4CompressionLevel@1@PEAVCMRCIControl@@@Z`
- size: `572`
- prototype: `int __high(int, int, unsigned int, enum CMRCICompression::CompressionLevel, struct CMRCIControl *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800354b0`

## callees

- `0x18000a290`
- `0x18000ab30`
- `0x180035480`
- `0x180035570`
- `0x180044310`

## import_xrefs

- `msvcrt!_lseek` at `0x180035747`
- `msvcrt!_lseek` at `0x180035747`
- `msvcrt!_write` at `0x180035630`
- `msvcrt!_write` at `0x1800356de`
- `msvcrt!_write` at `0x1800356f2`
- `msvcrt!_write` at `0x180035734`
- `msvcrt!_write` at `0x180035763`
- `msvcrt!_write` at `0x180035630`
- `msvcrt!_write` at `0x1800356de`
- `msvcrt!_write` at `0x1800356f2`
- `msvcrt!_write` at `0x180035734`
- `msvcrt!_write` at `0x180035763`
- `msvcrt!_filelengthi64` at `0x18003561b`
- `msvcrt!_filelengthi64` at `0x18003561b`
- `msvcrt!_read` at `0x180035679`
- `msvcrt!_read` at `0x180035679`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180035604`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180035604`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180035612`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180035612`

## pseudocode

```c
_BOOL8 __fastcall CMRCICompression::CompressFileV1(__int64 a1, int a2, int a3, DWORD a4, int a5, _DWORD *a6)
{
  DWORD v6; // r14d
  BOOL v9; // edi
  DWORD v10; // ebx
  void *v11; // rsi
  void *v12; // rax
  void *v13; // r13
  __int64 v14; // rsi
  unsigned int v15; // ebx
  unsigned int v16; // r14d
  int v17; // eax
  void *DstBuf; // [rsp+30h] [rbp-59h]
  void *v22; // [rsp+40h] [rbp-49h]
  __int64 Buf; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v25; // [rsp+58h] [rbp-31h]
  struct _FILETIME FileTime[2]; // [rsp+60h] [rbp-29h] BYREF
  __int64 v27; // [rsp+70h] [rbp-19h]
  struct _SYSTEMTIME SystemTime; // [rsp+78h] [rbp-11h] BYREF

  v6 = a4;
  v9 = 0;
  v10 = a4 + 4;
  DstBuf = CWin32DefaultArena::WbemMemAlloc(a4 + 4);
  v11 = DstBuf;
  v12 = CWin32DefaultArena::WbemMemAlloc(v10);
  v22 = v12;
  v13 = v12;
  if ( DstBuf )
  {
    if ( v12 )
    {
      v27 = 0;
      *(_OWORD *)&FileTime[0].dwLowDateTime = 0;
      BYTE1(FileTime[0].dwLowDateTime) = a5;
      LOBYTE(FileTime[0].dwLowDateTime) = -1;
      FileTime[0].dwHighDateTime = v6;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      SystemTimeToFileTime(&SystemTime, &FileTime[1]);
      v27 = _filelengthi64(a2);
      if ( _write(a3, FileTime, 0x18u) == 24 )
      {
        v14 = v27;
        v9 = 1;
        while ( v14 )
        {
          if ( a6 && *a6 )
            goto LABEL_26;
          v15 = v6;
          if ( v14 <= v6 )
            v15 = v14;
          if ( _read(a2, DstBuf, v15) != v15 )
            goto LABEL_19;
          v16 = CMRCICompression::CompressBuffer(a1, DstBuf, v15, v13, v6, a5);
          Buf = 0;
          v25 = 0;
          if ( v16 == -1 || v16 >= v15 )
          {
            v13 = DstBuf;
            v16 = v15;
          }
          else
          {
            LOBYTE(Buf) = 1;
          }
          HIDWORD(Buf) = v16;
          v25 = v15;
          if ( _write(a3, &Buf, 0xCu) != 12 )
          {
            v13 = v22;
LABEL_19:
            v9 = 0;
            break;
          }
          v17 = _write(a3, v13, v16);
          v13 = v22;
          if ( v17 != v16 )
            goto LABEL_19;
          v6 = a4;
          v14 -= v15;
        }
        if ( !a6 || !*a6 )
        {
          Buf = 0;
          v25 = 0;
          if ( _write(a3, &Buf, 0xCu) == -1 || _lseek(a3, 0, 0) == -1 )
          {
            v9 = 0;
          }
          else
          {
            LOBYTE(FileTime[0].dwLowDateTime) = 1;
            v9 = _write(a3, FileTime, 0x18u) != -1;
          }
        }
LABEL_26:
        v11 = DstBuf;
      }
    }
  }
  CMUILocale::_Free(v11);
  CMUILocale::_Free(v13);
  return v9;
}

```

## disassembly

```asm
0x180035570  push    rbp
0x180035572  push    rbx
0x180035573  push    rsi
0x180035574  push    rdi
0x180035575  push    r12
0x180035577  push    r13
0x180035579  push    r14
0x18003557b  push    r15
0x18003557d  lea     rbp, [rsp-0Fh]
0x180035582  sub     rsp, 98h
0x180035589  mov     rax, cs:__security_cookie
0x180035590  xor     rax, rsp
0x180035593  mov     [rbp+47h+var_48], rax
0x180035597  lea     eax, [r9+4]
0x18003559b  mov     [rbp+47h+var_88], rcx
0x18003559f  mov     ecx, eax; unsigned __int64
0x1800355a1  mov     r14d, r9d
0x1800355a4  mov     [rbp+47h+var_94], r9d
0x1800355a8  mov     r12d, r8d
0x1800355ab  mov     r15d, edx
0x1800355ae  mov     [rbp+47h+FileHandle], edx
0x1800355b1  xor     edi, edi
0x1800355b3  mov     ebx, eax
0x1800355b5  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800355ba  mov     ecx, ebx; unsigned __int64
0x1800355bc  mov     [rbp+47h+DstBuf], rax
0x1800355c0  mov     rsi, rax
0x1800355c3  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800355c8  mov     [rbp+47h+var_90], rax
0x1800355cc  mov     r13, rax
0x1800355cf  test    rsi, rsi
0x1800355d2  jz      loc_18003577A
0x1800355d8  test    rax, rax
0x1800355db  jz      loc_18003577A
0x1800355e1  xor     eax, eax
0x1800355e3  lea     rcx, [rbp+47h+SystemTime]; lpSystemTime
0x1800355e7  xorps   xmm0, xmm0
0x1800355ea  mov     [rbp+47h+var_60], rax
0x1800355ee  mov     eax, [rbp+47h+arg_20]
0x1800355f1  movups  xmmword ptr [rbp+47h+FileTime.dwLowDateTime], xmm0
0x1800355f5  mov     byte ptr [rbp+47h+FileTime.dwLowDateTime+1], al
0x1800355f8  mov     byte ptr [rbp+47h+FileTime.dwLowDateTime], 0FFh
0x1800355fc  mov     [rbp+47h+FileTime.dwHighDateTime], r14d
0x180035600  movups  xmmword ptr [rbp+47h+SystemTime.wYear], xmm0
0x180035604  call    cs:__imp_GetSystemTime
0x18003560a  lea     rdx, [rbp+47h+FileTime.dwLowDateTime+8]; lpFileTime
0x18003560e  lea     rcx, [rbp+47h+SystemTime]; lpSystemTime
0x180035612  call    cs:__imp_SystemTimeToFileTime
0x180035618  mov     ecx, r15d; FileHandle
0x18003561b  call    cs:__imp__filelengthi64
0x180035621  lea     r8d, [rdi+18h]; MaxCharCount
0x180035625  mov     ecx, r12d; FileHandle
0x180035628  lea     rdx, [rbp+47h+FileTime]; Buf
0x18003562c  mov     [rbp+47h+var_60], rax
0x180035630  call    cs:__imp__write
0x180035636  cmp     eax, 18h
0x180035639  jnz     loc_18003577A
0x18003563f  mov     rsi, [rbp+47h+var_60]
0x180035643  lea     edi, [rax-17h]
0x180035646  mov     r15, [rbp+47h+arg_28]
0x18003564a  test    rsi, rsi
0x18003564d  jz      loc_180035715
0x180035653  test    r15, r15
0x180035656  jz      short loc_180035662
0x180035658  cmp     dword ptr [r15], 0
0x18003565c  jnz     loc_180035776
0x180035662  mov     eax, r14d
0x180035665  mov     ebx, r14d
0x180035668  cmp     rsi, rax
0x18003566b  jg      short loc_18003566F
0x18003566d  mov     ebx, esi
0x18003566f  mov     rdx, [rbp+47h+DstBuf]; DstBuf
0x180035673  mov     r8d, ebx; MaxCharCount
0x180035676  mov     ecx, [rbp+47h+FileHandle]; FileHandle
0x180035679  call    cs:__imp__read
0x18003567f  cmp     eax, ebx
0x180035681  jnz     loc_180035713
0x180035687  mov     eax, [rbp+47h+arg_20]
0x18003568a  mov     r9, r13
0x18003568d  mov     rdx, [rbp+47h+DstBuf]
0x180035691  mov     r8d, ebx
0x180035694  mov     rcx, [rbp+47h+var_88]
0x180035698  mov     [rsp+0D0h+var_A8], eax
0x18003569c  mov     [rsp+0D0h+var_B0], r14d
0x1800356a1  call    ?CompressBuffer@CMRCICompression@@QEAAIPEAEK0KW4CompressionLevel@1@@Z; CMRCICompression::CompressBuffer(uchar *,ulong,uchar *,ulong,CMRCICompression::CompressionLevel)
0x1800356a6  mov     r14d, eax
0x1800356a9  xor     eax, eax
0x1800356ab  mov     [rbp+47h+Buf], rax
0x1800356af  mov     [rbp+47h+var_78], eax
0x1800356b2  cmp     r14d, 0FFFFFFFFh
0x1800356b6  jz      short loc_1800356C3
0x1800356b8  cmp     r14d, ebx
0x1800356bb  jnb     short loc_1800356C3
0x1800356bd  mov     byte ptr [rbp+47h+Buf], dil
0x1800356c1  jmp     short loc_1800356CA
0x1800356c3  mov     r13, [rbp+47h+DstBuf]
0x1800356c7  mov     r14d, ebx
0x1800356ca  mov     r8d, 0Ch; MaxCharCount
0x1800356d0  mov     dword ptr [rbp+47h+Buf+4], r14d
0x1800356d4  lea     rdx, [rbp+47h+Buf]; Buf
0x1800356d8  mov     [rbp+47h+var_78], ebx
0x1800356db  mov     ecx, r12d; FileHandle
0x1800356de  call    cs:__imp__write
0x1800356e4  cmp     eax, 0Ch
0x1800356e7  jnz     short loc_18003570F
0x1800356e9  mov     r8d, r14d; MaxCharCount
0x1800356ec  mov     rdx, r13; Buf
0x1800356ef  mov     ecx, r12d; FileHandle
0x1800356f2  call    cs:__imp__write
0x1800356f8  mov     r13, [rbp+47h+var_90]
0x1800356fc  cmp     eax, r14d
0x1800356ff  jnz     short loc_180035713
0x180035701  mov     r14d, [rbp+47h+var_94]
0x180035705  mov     eax, ebx
0x180035707  sub     rsi, rax
0x18003570a  jmp     loc_18003564A
0x18003570f  mov     r13, [rbp+47h+var_90]
0x180035713  xor     edi, edi
0x180035715  test    r15, r15
0x180035718  jz      short loc_180035720
0x18003571a  cmp     dword ptr [r15], 0
0x18003571e  jnz     short loc_180035776
0x180035720  xor     eax, eax
0x180035722  lea     rdx, [rbp+47h+Buf]; Buf
0x180035726  mov     ecx, r12d; FileHandle
0x180035729  mov     [rbp+47h+Buf], rax
0x18003572d  mov     [rbp+47h+var_78], eax
0x180035730  lea     r8d, [rax+0Ch]; MaxCharCount
0x180035734  call    cs:__imp__write
0x18003573a  cmp     eax, 0FFFFFFFFh
0x18003573d  jz      short loc_180035774
0x18003573f  xor     r8d, r8d; Origin
0x180035742  xor     edx, edx; Offset
0x180035744  mov     ecx, r12d; FileHandle
0x180035747  call    cs:__imp__lseek
0x18003574d  cmp     eax, 0FFFFFFFFh
0x180035750  jz      short loc_180035774
0x180035752  mov     r8d, 18h; MaxCharCount
0x180035758  mov     byte ptr [rbp+47h+FileTime.dwLowDateTime], 1
0x18003575c  lea     rdx, [rbp+47h+FileTime]; Buf
0x180035760  mov     ecx, r12d; FileHandle
0x180035763  call    cs:__imp__write
0x180035769  xor     edi, edi
0x18003576b  cmp     eax, 0FFFFFFFFh
0x18003576e  setnz   dil
0x180035772  jmp     short loc_180035776
0x180035774  xor     edi, edi
0x180035776  mov     rsi, [rbp+47h+DstBuf]
0x18003577a  mov     rcx, rsi; void *
0x18003577d  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180035782  mov     rcx, r13; void *
0x180035785  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18003578a  mov     eax, edi
0x18003578c  mov     rcx, [rbp+47h+var_48]
0x180035790  xor     rcx, rsp; StackCookie
0x180035793  call    __security_check_cookie
0x180035798  add     rsp, 98h
0x18003579f  pop     r15
0x1800357a1  pop     r14
0x1800357a3  pop     r13
0x1800357a5  pop     r12
0x1800357a7  pop     rdi
0x1800357a8  pop     rsi
0x1800357a9  pop     rbx
0x1800357aa  pop     rbp
0x1800357ab  retn
```
