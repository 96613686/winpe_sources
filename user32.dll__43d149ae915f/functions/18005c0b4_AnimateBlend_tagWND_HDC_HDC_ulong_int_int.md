# AnimateBlend(tagWND *,HDC__ *,HDC__ *,ulong,int,int)

- ea: `0x18005c0b4`
- end: `0x18005c40f`
- name: `?AnimateBlend@@YAHPEAUtagWND@@PEAUHDC__@@1KHH@Z`
- size: `859`
- prototype: `__int64 __usercall@<rax>(struct tagWND *@<rcx>, HDC hdc@<rdx>, HDC hdcSrc@<r8>, unsigned int@<r9d>, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180035be0`

## callees

- `0x18000b4e0`
- `0x18000d210`
- `0x18005c0b4`
- `0x180091320`

## import_xrefs

- `win32u!NtUserSetWindowLong` at `0x18005c145`
- `win32u!NtUserSetWindowLong` at `0x18005c336`
- `win32u!NtUserSetWindowLong` at `0x18005c145`
- `win32u!NtUserSetWindowLong` at `0x18005c336`
- `win32u!NtUserUpdateLayeredWindow` at `0x18005c1cf`
- `win32u!NtUserUpdateLayeredWindow` at `0x18005c292`
- `win32u!NtUserUpdateLayeredWindow` at `0x18005c1cf`
- `win32u!NtUserUpdateLayeredWindow` at `0x18005c292`
- `win32u!NtUserSetWindowPos` at `0x18005c3b1`
- `win32u!NtUserSetWindowPos` at `0x18005c3fd`
- `win32u!NtUserSetWindowPos` at `0x18005c3b1`
- `win32u!NtUserSetWindowPos` at `0x18005c3fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c113`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c113`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c14b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c14b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005c2cd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005c3c1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005c2cd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005c3c1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005c1fb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005c24f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005c29c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005c1fb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005c24f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005c29c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18005c103`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18005c103`
- `GDI32!BitBlt` at `0x18005c36a`
- `GDI32!BitBlt` at `0x18005c36a`

## pseudocode

```c
__int64 __fastcall AnimateBlend(HWND *a1, HDC hdc, HDC hdcSrc, unsigned int a4, int a5, int a6)
{
  HWND v6; // rbx
  LONG WindowLongW; // edi
  int v12; // edi
  int v13; // r15d
  int v14; // edx
  int v15; // eax
  int v16; // eax
  LONGLONG v17; // rsi
  unsigned int v18; // eax
  __int64 QuadPart; // rcx
  LARGE_INTEGER v20; // r8
  LONGLONG v21; // rax
  LONG v22; // esi
  int cy[2]; // [rsp+50h] [rbp-39h] BYREF
  LARGE_INTEGER Frequency; // [rsp+58h] [rbp-31h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+60h] [rbp-29h] BYREF
  LARGE_INTEGER v27; // [rsp+68h] [rbp-21h] BYREF
  __int64 v28; // [rsp+70h] [rbp-19h] BYREF
  LARGE_INTEGER v29; // [rsp+78h] [rbp-11h] BYREF
  _QWORD v30[10]; // [rsp+80h] [rbp-9h] BYREF
  int v31; // [rsp+E0h] [rbp+57h] BYREF

  v6 = *a1;
  *(_QWORD *)cy = 0;
  v30[0] = 0;
  v28 = 0;
  v31 = 0;
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v27.QuadPart = 0;
  v29.QuadPart = 0;
  if ( !QueryPerformanceFrequency(&Frequency) )
    return 0;
  SetLastError(0);
  WindowLongW = GetWindowLongW(v6, -20);
  if ( ValidateHwnd(v6) )
    NtUserSetWindowLong(v6, 4294967276LL, WindowLongW | 0x80000u, 0);
  if ( GetLastError() )
    return 0;
  v12 = a5;
  v13 = 1;
  if ( a5 )
    Sleep(0xAu);
  v14 = *((_DWORD *)a1 + 23);
  v15 = *((_DWORD *)a1 + 24) - *((_DWORD *)a1 + 22);
  LODWORD(v28) = *((_DWORD *)a1 + 22);
  cy[0] = v15;
  v16 = *((_DWORD *)a1 + 25) - v14;
  HIDWORD(v28) = v14;
  cy[1] = v16;
  LOWORD(v31) = 0;
  HIWORD(v31) = (unsigned __int8)(v12 != 0 ? -41 : 40);
  NtUserUpdateLayeredWindow(v6, 0, &v28, cy, hdcSrc, v30, 0, &v31, 2, 0);
  if ( !v12 )
    ShowWindowNoRepaint((struct tagWND *)a1);
  LODWORD(v17) = (40 * a4 + 255) / 0xFF + 10;
  QueryPerformanceCounter(&PerformanceCount);
  for ( PerformanceCount.QuadPart += Frequency.QuadPart * (unsigned int)v17 / -1000;
        (unsigned int)v17 < a4;
        v17 = 1000 * (QuadPart - PerformanceCount.QuadPart) / v20.QuadPart )
  {
    if ( v12 )
      v18 = 255 * (a4 - v17);
    else
      v18 = 255 * v17;
    BYTE2(v31) = v18 / a4;
    QueryPerformanceCounter(&v29);
    if ( v13 && a6 )
      NtUserSetWindowPos(v6, 0, 0, 0, 0, 0, 515);
    v13 = 0;
    NtUserUpdateLayeredWindow(v6, 0, 0, 0, 0, 0, 0, &v31, 2, 0);
    QueryPerformanceCounter(&v27);
    QuadPart = v27.QuadPart;
    v20 = Frequency;
    v29.QuadPart = v27.QuadPart - v29.QuadPart;
    v21 = 1000 * v29.QuadPart / Frequency.QuadPart;
    if ( (unsigned int)v21 < 0xA )
    {
      Sleep(10 - v21);
      v20 = Frequency;
      QuadPart = v27.QuadPart;
    }
    v27.QuadPart = QuadPart - PerformanceCount.QuadPart;
  }
  if ( v12 )
    NtUserSetWindowPos(v6, 0, 0, 0, 0, 0, 151);
  v22 = GetWindowLongW(v6, -20);
  if ( ValidateHwnd(v6) )
    NtUserSetWindowLong(v6, 4294967276LL, v22 & 0xFFF7FFFF, 0);
  if ( !v12 )
    BitBlt(hdc, 0, 0, cy[0], cy[1], hdcSrc, 0, 0, 0x80CC0020);
  return 1;
}

```

## disassembly

```asm
0x18005c0b4  push    rbp
0x18005c0b6  push    rbx
0x18005c0b7  push    rsi
0x18005c0b8  push    rdi
0x18005c0b9  push    r12
0x18005c0bb  push    r13
0x18005c0bd  push    r14
0x18005c0bf  push    r15
0x18005c0c1  lea     rbp, [rsp-0Fh]
0x18005c0c6  sub     rsp, 98h
0x18005c0cd  mov     rbx, [rcx]
0x18005c0d0  xor     r15d, r15d
0x18005c0d3  mov     rsi, rcx
0x18005c0d6  mov     qword ptr [rbp+47h+var_80], r15
0x18005c0da  lea     rcx, [rbp+47h+Frequency]; lpFrequency
0x18005c0de  mov     [rbp+47h+var_50], r15
0x18005c0e2  mov     [rbp+47h+var_60], r15
0x18005c0e6  mov     r14d, r9d
0x18005c0e9  mov     [rbp+47h+arg_0], r15d
0x18005c0ed  mov     r12, r8
0x18005c0f0  mov     qword ptr [rbp+47h+Frequency], r15
0x18005c0f4  mov     r13, rdx
0x18005c0f7  mov     qword ptr [rbp+47h+PerformanceCount], r15
0x18005c0fb  mov     qword ptr [rbp+47h+var_68], r15
0x18005c0ff  mov     qword ptr [rbp+47h+var_58], r15
0x18005c103  call    cs:__imp_QueryPerformanceFrequency
0x18005c109  test    eax, eax
0x18005c10b  jz      loc_18005C408
0x18005c111  xor     ecx, ecx; dwErrCode
0x18005c113  call    cs:__imp_SetLastError
0x18005c119  lea     edx, [r15-14h]; nIndex
0x18005c11d  mov     rcx, rbx; hWnd
0x18005c120  call    GetWindowLongW
0x18005c125  mov     rcx, rbx; HWND
0x18005c128  mov     edi, eax
0x18005c12a  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x18005c12f  test    rax, rax
0x18005c132  jz      short loc_18005C14B
0x18005c134  bts     edi, 13h
0x18005c138  lea     edx, [r15-14h]
0x18005c13c  mov     r8d, edi
0x18005c13f  xor     r9d, r9d
0x18005c142  mov     rcx, rbx
0x18005c145  call    cs:__imp_NtUserSetWindowLong
0x18005c14b  call    cs:__imp_GetLastError
0x18005c151  test    eax, eax
0x18005c153  jnz     loc_18005C408
0x18005c159  mov     edi, [rbp+47h+arg_20]
0x18005c15c  lea     r15d, [rax+1]
0x18005c160  test    edi, edi
0x18005c162  jnz     loc_18005C3BC
0x18005c168  mov     ecx, [rsi+58h]
0x18005c16b  lea     r9, [rbp+47h+var_80]
0x18005c16f  mov     edx, [rsi+5Ch]
0x18005c172  lea     r8, [rbp+47h+var_60]
0x18005c176  mov     eax, [rsi+60h]
0x18005c179  sub     eax, ecx
0x18005c17b  mov     dword ptr [rbp+47h+var_60], ecx
0x18005c17e  mov     [rbp+47h+var_80], eax
0x18005c181  mov     eax, [rsi+64h]
0x18005c184  sub     eax, edx
0x18005c186  mov     dword ptr [rbp+47h+var_60+4], edx
0x18005c189  xor     edx, edx
0x18005c18b  mov     [rbp+47h+var_80+4], eax
0x18005c18e  mov     [rsp+0D0h+var_88], rdx
0x18005c193  mov     eax, edi
0x18005c195  neg     eax
0x18005c197  mov     [rsp+0D0h+rop], 2
0x18005c19f  lea     rax, [rbp+47h+arg_0]
0x18005c1a3  mov     word ptr [rbp+47h+arg_0], dx
0x18005c1a7  mov     qword ptr [rsp+0D0h+y1], rax
0x18005c1ac  sbb     cl, cl
0x18005c1ae  and     cl, 0AFh
0x18005c1b1  mov     [rsp+0D0h+x1], edx
0x18005c1b5  add     cl, 28h ; '('
0x18005c1b8  mov     byte ptr [rbp+47h+arg_0+3], dl
0x18005c1bb  lea     rax, [rbp+47h+var_50]
0x18005c1bf  mov     byte ptr [rbp+47h+arg_0+2], cl
0x18005c1c2  mov     [rsp+0D0h+hdcSrc], rax
0x18005c1c7  mov     rcx, rbx
0x18005c1ca  mov     qword ptr [rsp+0D0h+cy], r12
0x18005c1cf  call    cs:__imp_NtUserUpdateLayeredWindow
0x18005c1d5  test    edi, edi
0x18005c1d7  jz      loc_18005C3CC
0x18005c1dd  lea     eax, [r14+r14*4]
0x18005c1e1  lea     ecx, ds:0FFh[rax*8]
0x18005c1e8  mov     eax, 80808081h
0x18005c1ed  mul     ecx
0x18005c1ef  lea     rcx, [rbp+47h+PerformanceCount]; lpPerformanceCount
0x18005c1f3  mov     esi, edx
0x18005c1f5  shr     esi, 7
0x18005c1f8  add     esi, 0Ah
0x18005c1fb  call    cs:__imp_QueryPerformanceCounter
0x18005c201  mov     ecx, esi
0x18005c203  mov     rax, 0DF3B645A1CAC0831h
0x18005c20d  imul    rcx, qword ptr [rbp+47h+Frequency]
0x18005c212  imul    rcx
0x18005c215  sar     rdx, 7
0x18005c219  mov     rax, rdx
0x18005c21c  shr     rax, 3Fh
0x18005c220  add     rdx, rax
0x18005c223  add     qword ptr [rbp+47h+PerformanceCount], rdx
0x18005c227  cmp     esi, r14d
0x18005c22a  jnb     loc_18005C2FB
0x18005c230  xor     edx, edx
0x18005c232  test    edi, edi
0x18005c234  jz      loc_18005C389
0x18005c23a  mov     eax, r14d
0x18005c23d  sub     eax, esi
0x18005c23f  imul    eax, 0FFh
0x18005c245  div     r14d
0x18005c248  lea     rcx, [rbp+47h+var_58]; lpPerformanceCount
0x18005c24c  mov     byte ptr [rbp+47h+arg_0+2], al
0x18005c24f  call    cs:__imp_QueryPerformanceCounter
0x18005c255  xor     esi, esi
0x18005c257  test    r15d, r15d
0x18005c25a  jnz     loc_18005C3D9
0x18005c260  mov     [rsp+0D0h+var_88], rsi
0x18005c265  lea     rax, [rbp+47h+arg_0]
0x18005c269  mov     [rsp+0D0h+rop], 2
0x18005c271  xor     r9d, r9d
0x18005c274  mov     qword ptr [rsp+0D0h+y1], rax
0x18005c279  xor     r8d, r8d
0x18005c27c  mov     [rsp+0D0h+x1], esi
0x18005c280  xor     edx, edx
0x18005c282  mov     [rsp+0D0h+hdcSrc], rsi
0x18005c287  mov     rcx, rbx
0x18005c28a  mov     qword ptr [rsp+0D0h+cy], rsi
0x18005c28f  mov     r15d, esi
0x18005c292  call    cs:__imp_NtUserUpdateLayeredWindow
0x18005c298  lea     rcx, [rbp+47h+var_68]; lpPerformanceCount
0x18005c29c  call    cs:__imp_QueryPerformanceCounter
0x18005c2a2  mov     rcx, qword ptr [rbp+47h+var_68]
0x18005c2a6  mov     r8, qword ptr [rbp+47h+Frequency]
0x18005c2aa  mov     rax, rcx
0x18005c2ad  sub     rax, qword ptr [rbp+47h+var_58]
0x18005c2b1  mov     qword ptr [rbp+47h+var_58], rax
0x18005c2b5  imul    rax, 3E8h
0x18005c2bc  cqo
0x18005c2be  idiv    r8
0x18005c2c1  cmp     eax, 0Ah
0x18005c2c4  jnb     short loc_18005C2DB
0x18005c2c6  mov     ecx, 0Ah
0x18005c2cb  sub     ecx, eax; dwMilliseconds
0x18005c2cd  call    cs:__imp_Sleep
0x18005c2d3  mov     r8, qword ptr [rbp+47h+Frequency]
0x18005c2d7  mov     rcx, qword ptr [rbp+47h+var_68]
0x18005c2db  sub     rcx, qword ptr [rbp+47h+PerformanceCount]
0x18005c2df  imul    rax, rcx, 3E8h
0x18005c2e6  mov     qword ptr [rbp+47h+var_68], rcx
0x18005c2ea  cqo
0x18005c2ec  idiv    r8
0x18005c2ef  mov     rsi, rax
0x18005c2f2  cmp     eax, r14d
0x18005c2f5  jb      loc_18005C230
0x18005c2fb  xor     r14d, r14d
0x18005c2fe  test    edi, edi
0x18005c300  jnz     loc_18005C394
0x18005c306  mov     r15d, 0FFFFFFECh
0x18005c30c  mov     rcx, rbx; hWnd
0x18005c30f  mov     edx, r15d; nIndex
0x18005c312  call    GetWindowLongW
0x18005c317  mov     rcx, rbx; HWND
0x18005c31a  mov     esi, eax
0x18005c31c  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x18005c321  test    rax, rax
0x18005c324  jz      short loc_18005C33C
0x18005c326  btr     esi, 13h
0x18005c32a  xor     r9d, r9d
0x18005c32d  mov     r8d, esi
0x18005c330  mov     edx, r15d
0x18005c333  mov     rcx, rbx
0x18005c336  call    cs:__imp_NtUserSetWindowLong
0x18005c33c  test    edi, edi
0x18005c33e  jnz     short loc_18005C370
0x18005c340  mov     ecx, [rbp+47h+var_80+4]
0x18005c343  xor     r8d, r8d; y
0x18005c346  mov     r9d, [rbp+47h+var_80]; cx
0x18005c34a  xor     edx, edx; x
0x18005c34c  mov     [rsp+0D0h+rop], 80CC0020h; rop
0x18005c354  mov     [rsp+0D0h+y1], r14d; y1
0x18005c359  mov     [rsp+0D0h+x1], r14d; x1
0x18005c35e  mov     [rsp+0D0h+hdcSrc], r12; hdcSrc
0x18005c363  mov     [rsp+0D0h+cy], ecx; cy
0x18005c367  mov     rcx, r13; hdc
0x18005c36a  call    cs:__imp_BitBlt
0x18005c370  mov     eax, 1
0x18005c375  add     rsp, 98h
0x18005c37c  pop     r15
0x18005c37e  pop     r14
0x18005c380  pop     r13
0x18005c382  pop     r12
0x18005c384  pop     rdi
0x18005c385  pop     rsi
0x18005c386  pop     rbx
0x18005c387  pop     rbp
0x18005c388  retn
0x18005c389  imul    eax, esi, 0FFh
0x18005c38f  jmp     loc_18005C245
0x18005c394  mov     [rsp+0D0h+x1], 97h
0x18005c39c  xor     r9d, r9d
0x18005c39f  mov     dword ptr [rsp+0D0h+hdcSrc], r14d
0x18005c3a4  xor     r8d, r8d
0x18005c3a7  xor     edx, edx
0x18005c3a9  mov     [rsp+0D0h+cy], r14d
0x18005c3ae  mov     rcx, rbx
0x18005c3b1  call    cs:__imp_NtUserSetWindowPos
0x18005c3b7  jmp     loc_18005C306
0x18005c3bc  mov     ecx, 0Ah; dwMilliseconds
0x18005c3c1  call    cs:__imp_Sleep
0x18005c3c7  jmp     loc_18005C168
0x18005c3cc  mov     rcx, rsi; struct tagWND *
0x18005c3cf  call    ?ShowWindowNoRepaint@@YAXPEAUtagWND@@@Z; ShowWindowNoRepaint(tagWND *)
0x18005c3d4  jmp     loc_18005C1DD
0x18005c3d9  cmp     [rbp+47h+arg_28], esi
0x18005c3dc  jz      loc_18005C260
0x18005c3e2  mov     [rsp+0D0h+x1], 203h
0x18005c3ea  xor     r9d, r9d
0x18005c3ed  mov     dword ptr [rsp+0D0h+hdcSrc], esi
0x18005c3f1  xor     r8d, r8d
0x18005c3f4  xor     edx, edx
0x18005c3f6  mov     [rsp+0D0h+cy], esi
0x18005c3fa  mov     rcx, rbx
0x18005c3fd  call    cs:__imp_NtUserSetWindowPos
0x18005c403  jmp     loc_18005C260
0x18005c408  xor     eax, eax
0x18005c40a  jmp     loc_18005C375
```
