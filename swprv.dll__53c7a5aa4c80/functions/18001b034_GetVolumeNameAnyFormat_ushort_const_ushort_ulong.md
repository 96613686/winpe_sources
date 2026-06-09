# GetVolumeNameAnyFormat(ushort const *,ushort *,ulong)

- ea: `0x18001b034`
- end: `0x18001b129`
- name: `?GetVolumeNameAnyFormat@@YAJPEBGPEAGK@Z`
- size: `245`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x18001b380`
- `0x18001de8c`
- `0x18001e270`
- `0x18001e6f8`

## callees

- `0x18000212c`
- `0x180007604`
- `0x18001b034`
- `0x18001b130`
- `0x180033a8c`
- `0x180033c78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0cb`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18001b0c1`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18001b0c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetVolumeNameAnyFormat(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  signed int LastError; // ebx
  _QWORD v6[3]; // [rsp+20h] [rbp-E0h] BYREF
  int v7; // [rsp+38h] [rbp-C8h]
  int v8; // [rsp+3Ch] [rbp-C4h]
  int v9; // [rsp+40h] [rbp-C0h]
  _BYTE v10[120]; // [rsp+48h] [rbp-B8h] BYREF
  int v11; // [rsp+C0h] [rbp-40h]
  LPVOID v12; // [rsp+D0h] [rbp-30h] BYREF
  signed int v13; // [rsp+D8h] [rbp-28h]

  v6[0] = L"base\\stor\\vss\\inc\\vs_vol.hxx";
  v6[1] = L"GetVolumeNameAnyFormat";
  v6[2] = L"INCVOLH";
  v7 = 506;
  v8 = 11;
  v9 = 255;
  v11 = 0x1000000;
  memset_0(v10, 0, sizeof(v10));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v12, (__int64)v6, 0);
  *a2 = 0;
  if ( GetVolumeNameForVolumeMountPointW(a1, a2, 0x104u) )
  {
    LastError = v13;
    goto LABEL_9;
  }
  LastError = GetLastError();
  if ( LastError != 4390 )
  {
    if ( LastError <= 0 )
    {
LABEL_7:
      v13 = LastError;
      goto LABEL_9;
    }
LABEL_6:
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_7;
  }
  if ( !IsVolumeValid(a1) )
    goto LABEL_6;
  LastError = StringCchCopyW(a2, 0x104u, a1);
  v13 = LastError;
LABEL_9:
  CVssFunctionTracer::~CVssFunctionTracer(&v12);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001b034  push    rbp
0x18001b036  push    rbx
0x18001b037  push    rsi
0x18001b038  push    rdi
0x18001b039  lea     rbp, [rsp-48h]
0x18001b03e  sub     rsp, 148h
0x18001b045  mov     rsi, rdx
0x18001b048  mov     rdi, rcx
0x18001b04b  lea     rax, aBaseStorVssInc; "base\\stor\\vss\\inc\\vs_vol.hxx"
0x18001b052  mov     [rsp+160h+var_140], rax
0x18001b057  lea     rax, aGetvolumenamea; "GetVolumeNameAnyFormat"
0x18001b05e  mov     [rsp+160h+var_138], rax
0x18001b063  lea     rax, aIncvolh; "INCVOLH"
0x18001b06a  mov     [rsp+160h+var_130], rax
0x18001b06f  mov     [rsp+160h+var_128], 1FAh
0x18001b077  mov     [rsp+160h+var_124], 0Bh
0x18001b07f  mov     [rsp+160h+var_120], 0FFh
0x18001b087  mov     [rbp+60h+var_A0], 1000000h
0x18001b08e  xor     edx, edx; Val
0x18001b090  lea     r8d, [rdx+78h]; Size
0x18001b094  lea     rcx, [rsp+160h+var_118]; void *
0x18001b099  call    memset_0
0x18001b09e  xor     r8d, r8d
0x18001b0a1  lea     rdx, [rsp+160h+var_140]
0x18001b0a6  lea     rcx, [rbp+60h+var_90]
0x18001b0aa  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18001b0af  nop
0x18001b0b0  xor     eax, eax
0x18001b0b2  mov     [rsi], ax
0x18001b0b5  mov     r8d, 104h; cchBufferLength
0x18001b0bb  mov     rdx, rsi; lpszVolumeName
0x18001b0be  mov     rcx, rdi; lpszVolumeMountPoint
0x18001b0c1  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18001b0c7  test    eax, eax
0x18001b0c9  jnz     short loc_18001B10F
0x18001b0cb  call    cs:__imp_GetLastError
0x18001b0d1  mov     ebx, eax
0x18001b0d3  cmp     eax, 1126h
0x18001b0d8  jnz     short loc_18001B0FD
0x18001b0da  mov     rcx, rdi; unsigned __int16 *
0x18001b0dd  call    ?IsVolumeValid@@YA_NPEBG@Z; IsVolumeValid(ushort const *)
0x18001b0e2  test    al, al
0x18001b0e4  jz      short loc_18001B101
0x18001b0e6  mov     r8, rdi; unsigned __int16 *
0x18001b0e9  mov     edx, 104h; unsigned __int64
0x18001b0ee  mov     rcx, rsi; unsigned __int16 *
0x18001b0f1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b0f6  mov     ebx, eax
0x18001b0f8  mov     [rbp+60h+var_88], eax
0x18001b0fb  jmp     short loc_18001B112
0x18001b0fd  test    ebx, ebx
0x18001b0ff  jle     short loc_18001B10A
0x18001b101  movzx   ebx, bx
0x18001b104  or      ebx, 80070000h
0x18001b10a  mov     [rbp+60h+var_88], ebx
0x18001b10d  jmp     short loc_18001B112
0x18001b10f  mov     ebx, [rbp+60h+var_88]
0x18001b112  lea     rcx, [rbp+60h+var_90]; this
0x18001b116  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18001b11b  mov     eax, ebx
0x18001b11d  add     rsp, 148h
0x18001b124  pop     rdi
0x18001b125  pop     rsi
0x18001b126  pop     rbx
0x18001b127  pop     rbp
0x18001b128  retn
```
