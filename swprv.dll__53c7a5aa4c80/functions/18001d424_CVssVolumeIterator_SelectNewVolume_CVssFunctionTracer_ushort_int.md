# CVssVolumeIterator::SelectNewVolume(CVssFunctionTracer &,ushort *,int)

- ea: `0x18001d424`
- end: `0x18001d641`
- name: `?SelectNewVolume@CVssVolumeIterator@@QEAA_NAEAVCVssFunctionTracer@@PEAGH@Z`
- size: `541`
- prototype: `bool(CVssVolumeIterator *__hidden this, struct CVssFunctionTracer *, unsigned __int16 *, int)`
- caller_count: `9`
- callee_count: `6`
- tags: ``

## callers

- `0x18001c4b0`
- `0x18001fb80`
- `0x1800200c0`
- `0x180024a6c`
- `0x1800250bc`
- `0x180026da0`
- `0x18002c830`
- `0x18002d1f0`
- `0x18002edd8`

## callees

- `0x18000212c`
- `0x18001b130`
- `0x18001d424`
- `0x180033a8c`
- `0x180033c78`
- `0x18003750c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5ba`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x18001d4c4`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x18001d4c4`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x18001d50f`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x18001d50f`

## string_xrefs

- `0x18001d594`: `FindFirstVolumeW( [%s], MAX_PATH)`
- `0x18001d61e`: `FindNextVolumeW( %p, [%s], MAX_PATH)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CVssVolumeIterator::SelectNewVolume(
        CVssVolumeIterator *this,
        struct CVssFunctionTracer *a2,
        unsigned __int16 *a3)
{
  HANDLE FirstVolumeW; // rax
  signed int LastError; // eax
  unsigned int v9; // ebx
  __int64 v10; // rsi
  signed int v11; // eax
  unsigned int v12; // ebx
  const unsigned __int16 *v13; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v14; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v15; // [rsp+50h] [rbp-B0h]
  int v16; // [rsp+58h] [rbp-A8h]
  int v17; // [rsp+5Ch] [rbp-A4h]
  int v18; // [rsp+60h] [rbp-A0h]
  _BYTE v19[120]; // [rsp+68h] [rbp-98h] BYREF
  int v20; // [rsp+E0h] [rbp-20h]
  LPVOID v21[14]; // [rsp+F0h] [rbp-10h] BYREF

  v13 = L"base\\stor\\vss\\inc\\vs_vol.hxx";
  v14 = L"CVssVolumeIterator::SelectNewVolume";
  v15 = L"INCVOLH";
  v16 = 427;
  v17 = 11;
  v18 = 255;
  v20 = 0x1000000;
  memset_0(v19, 0, sizeof(v19));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v21, (__int64)&v13, 0);
  while ( 1 )
  {
    if ( *((_BYTE *)this + 8) )
    {
      *((_BYTE *)this + 8) = 0;
      FirstVolumeW = FindFirstVolumeW(a3, 0x104u);
      *(_QWORD *)this = FirstVolumeW;
      if ( FirstVolumeW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        v13 = L"base\\stor\\vss\\inc\\vs_vol.hxx";
        v14 = L"CVssVolumeIterator::SelectNewVolume";
        v15 = L"INCVOLH";
        v16 = 443;
        v17 = 2;
        v18 = 255;
        v20 = 0x1000000;
        memset_0(v19, 0, sizeof(v19));
        CVssFunctionTracer::TranslateInternalProviderError(
          a2,
          &v13,
          v9,
          2147754758LL,
          L"FindFirstVolumeW( [%s], MAX_PATH)",
          a3);
      }
      goto LABEL_4;
    }
    if ( !FindNextVolumeW(*(HANDLE *)this, a3, 0x104u) )
      break;
LABEL_4:
    if ( IsVolumeValid(a3) )
    {
      CVssFunctionTracer::~CVssFunctionTracer(v21);
      return 1;
    }
  }
  if ( GetLastError() != 18 )
  {
    v10 = *(_QWORD *)this;
    v11 = GetLastError();
    v12 = v11;
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    v13 = L"base\\stor\\vss\\inc\\vs_vol.hxx";
    v14 = L"CVssVolumeIterator::SelectNewVolume";
    v15 = L"INCVOLH";
    v16 = 462;
    v17 = 2;
    v18 = 255;
    v20 = 0x1000000;
    memset_0(v19, 0, sizeof(v19));
    CVssFunctionTracer::TranslateInternalProviderError(
      a2,
      &v13,
      v12,
      2147754758LL,
      L"FindNextVolumeW( %p, [%s], MAX_PATH)",
      v10,
      a3);
  }
  CVssFunctionTracer::~CVssFunctionTracer(v21);
  return 0;
}

```

## disassembly

```asm
0x18001d424  mov     [rsp-8+arg_8], rbx
0x18001d429  mov     [rsp-8+arg_10], rsi
0x18001d42e  push    rbp
0x18001d42f  push    rdi
0x18001d430  push    r12
0x18001d432  push    r13
0x18001d434  push    r14
0x18001d436  lea     rbp, [rsp-60h]
0x18001d43b  sub     rsp, 160h
0x18001d442  mov     rdi, r8
0x18001d445  mov     r14, rdx
0x18001d448  mov     rbx, rcx
0x18001d44b  lea     r12, aBaseStorVssInc; "base\\stor\\vss\\inc\\vs_vol.hxx"
0x18001d452  mov     [rsp+180h+var_140], r12
0x18001d457  lea     r13, aCvssvolumeiter; "CVssVolumeIterator::SelectNewVolume"
0x18001d45e  mov     [rsp+180h+var_138], r13
0x18001d463  lea     rax, aIncvolh; "INCVOLH"
0x18001d46a  mov     [rsp+180h+var_130], rax
0x18001d46f  mov     [rsp+180h+var_128], 1ABh
0x18001d477  mov     [rsp+180h+var_124], 0Bh
0x18001d47f  mov     [rsp+180h+var_120], 0FFh
0x18001d487  mov     [rbp+80h+var_A0], 1000000h
0x18001d48e  xor     edx, edx; Val
0x18001d490  lea     r8d, [rdx+78h]; Size
0x18001d494  lea     rcx, [rsp+180h+var_118]; void *
0x18001d499  call    memset_0
0x18001d49e  xor     r8d, r8d
0x18001d4a1  lea     rdx, [rsp+180h+var_140]
0x18001d4a6  lea     rcx, [rbp+80h+var_90]
0x18001d4aa  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18001d4af  nop
0x18001d4b0  mov     esi, 104h
0x18001d4b5  cmp     byte ptr [rbx+8], 0
0x18001d4b9  jz      short loc_18001D506
0x18001d4bb  mov     byte ptr [rbx+8], 0
0x18001d4bf  mov     edx, esi; cchBufferLength
0x18001d4c1  mov     rcx, rdi; lpszVolumeName
0x18001d4c4  call    cs:__imp_FindFirstVolumeW
0x18001d4ca  mov     [rbx], rax
0x18001d4cd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d4d1  jz      short loc_18001D535
0x18001d4d3  mov     rcx, rdi; unsigned __int16 *
0x18001d4d6  call    ?IsVolumeValid@@YA_NPEBG@Z; IsVolumeValid(ushort const *)
0x18001d4db  test    al, al
0x18001d4dd  jz      short loc_18001D4B5
0x18001d4df  lea     rcx, [rbp+80h+var_90]; this
0x18001d4e3  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18001d4e8  mov     al, 1
0x18001d4ea  lea     r11, [rsp+180h+var_20]
0x18001d4f2  mov     rbx, [r11+38h]
0x18001d4f6  mov     rsi, [r11+40h]
0x18001d4fa  mov     rsp, r11
0x18001d4fd  pop     r14
0x18001d4ff  pop     r13
0x18001d501  pop     r12
0x18001d503  pop     rdi
0x18001d504  pop     rbp
0x18001d505  retn
0x18001d506  mov     r8d, esi; cchBufferLength
0x18001d509  mov     rdx, rdi; lpszVolumeName
0x18001d50c  mov     rcx, [rbx]; hFindVolume
0x18001d50f  call    cs:__imp_FindNextVolumeW
0x18001d515  test    eax, eax
0x18001d517  jnz     short loc_18001D4D3
0x18001d519  call    cs:__imp_GetLastError
0x18001d51f  cmp     eax, 12h
0x18001d522  jnz     loc_18001D5B7
0x18001d528  lea     rcx, [rbp+80h+var_90]; this
0x18001d52c  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18001d531  xor     al, al
0x18001d533  jmp     short loc_18001D4EA
0x18001d535  call    cs:__imp_GetLastError
0x18001d53b  mov     ebx, eax
0x18001d53d  test    eax, eax
0x18001d53f  jle     short loc_18001D54A
0x18001d541  movzx   ebx, ax
0x18001d544  or      ebx, 80070000h
0x18001d54a  mov     [rsp+180h+var_140], r12
0x18001d54f  mov     [rsp+180h+var_138], r13
0x18001d554  lea     rax, aIncvolh; "INCVOLH"
0x18001d55b  mov     [rsp+180h+var_130], rax
0x18001d560  mov     [rsp+180h+var_128], 1BBh
0x18001d568  mov     [rsp+180h+var_124], 2
0x18001d570  mov     [rsp+180h+var_120], 0FFh
0x18001d578  mov     [rbp+80h+var_A0], 1000000h
0x18001d57f  xor     edx, edx; Val
0x18001d581  lea     r8d, [rdx+78h]; Size
0x18001d585  lea     rcx, [rsp+180h+var_118]; void *
0x18001d58a  call    memset_0
0x18001d58f  mov     [rsp+180h+var_158], rdi
0x18001d594  lea     rax, aFindfirstvolum; "FindFirstVolumeW( [%s], MAX_PATH)"
0x18001d59b  mov     [rsp+180h+var_160], rax
0x18001d5a0  mov     r9d, 80042306h
0x18001d5a6  mov     r8d, ebx
0x18001d5a9  lea     rdx, [rsp+180h+var_140]
0x18001d5ae  mov     rcx, r14
0x18001d5b1  call    ?TranslateInternalProviderError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JJPEBGZZ; CVssFunctionTracer::TranslateInternalProviderError(CVssDebugInfo,long,long,ushort const *,...)
0x18001d5b7  mov     rsi, [rbx]
0x18001d5ba  call    cs:__imp_GetLastError
0x18001d5c0  mov     ebx, eax
0x18001d5c2  test    eax, eax
0x18001d5c4  jle     short loc_18001D5CF
0x18001d5c6  movzx   ebx, ax
0x18001d5c9  or      ebx, 80070000h
0x18001d5cf  mov     [rsp+180h+var_140], r12
0x18001d5d4  mov     [rsp+180h+var_138], r13
0x18001d5d9  lea     rax, aIncvolh; "INCVOLH"
0x18001d5e0  mov     [rsp+180h+var_130], rax
0x18001d5e5  mov     [rsp+180h+var_128], 1CEh
0x18001d5ed  mov     [rsp+180h+var_124], 2
0x18001d5f5  mov     [rsp+180h+var_120], 0FFh
0x18001d5fd  mov     [rbp+80h+var_A0], 1000000h
0x18001d604  xor     edx, edx; Val
0x18001d606  lea     r8d, [rdx+78h]; Size
0x18001d60a  lea     rcx, [rsp+180h+var_118]; void *
0x18001d60f  call    memset_0
0x18001d614  mov     [rsp+180h+var_150], rdi
0x18001d619  mov     [rsp+180h+var_158], rsi
0x18001d61e  lea     rax, aFindnextvolume; "FindNextVolumeW( %p, [%s], MAX_PATH)"
0x18001d625  mov     [rsp+180h+var_160], rax
0x18001d62a  mov     r9d, 80042306h
0x18001d630  mov     r8d, ebx
0x18001d633  lea     rdx, [rsp+180h+var_140]
0x18001d638  mov     rcx, r14
0x18001d63b  call    ?TranslateInternalProviderError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JJPEBGZZ; CVssFunctionTracer::TranslateInternalProviderError(CVssDebugInfo,long,long,ushort const *,...)
```
