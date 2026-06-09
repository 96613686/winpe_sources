# SxGetPresentableVolumeName(ushort const *,ushort *,ulong)

- ea: `0x180095914`
- end: `0x180095b8e`
- name: `?SxGetPresentableVolumeName@@YAJPEBGPEAGK@Z`
- size: `634`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180021194`
- `0x180095808`

## callees

- `0x180009d44`
- `0x180014eac`
- `0x180072e08`
- `0x180072f14`
- `0x180095914`
- `0x180097a68`
- `0x180097ba0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180095a11`
- `KERNEL32!GetLastError` at `0x180095a11`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x1800959fd`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x1800959fd`
- `ole32!CoTaskMemFree` at `0x180095b5f`
- `ole32!CoTaskMemFree` at `0x180095b5f`
- `ole32!CoTaskMemRealloc` at `0x1800959ce`
- `ole32!CoTaskMemRealloc` at `0x1800959ce`

## pseudocode

```c
__int64 __fastcall SxGetPresentableVolumeName(LPCWSTR lpszVolumeName, unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int64 v3; // r14
  WCHAR *v6; // rbx
  __int16 v7; // ax
  DWORD v8; // eax
  WCHAR *v9; // rax
  signed int LastError; // eax
  unsigned int v11; // r9d
  WCHAR *v12; // r8
  const unsigned __int16 *i; // r11
  __int64 v14; // rdx
  const unsigned __int16 *v15; // rax
  __int64 v16; // rax
  int v17; // eax
  int v18; // r8d
  int v19; // r9d
  __int64 v20; // r11
  unsigned int v21; // ebx
  __int64 v23; // [rsp+28h] [rbp-41h]
  int v24; // [rsp+40h] [rbp-29h] BYREF
  __int16 v25; // [rsp+44h] [rbp-25h]
  __int16 v26; // [rsp+46h] [rbp-23h]
  DWORD cchReturnLength; // [rsp+D0h] [rbp+67h] BYREF

  v3 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_Sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, a3, (_DWORD)lpszVolumeName, (char)a2, a3);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v24, "SxGetPresentableVolumeName", 0x32u, 1u);
  cchReturnLength = 0;
  v6 = 0;
  v7 = 61;
  if ( !lpszVolumeName )
    goto LABEL_34;
  v25 = 61;
  if ( !a2 )
  {
    v7 = 62;
LABEL_34:
    v26 = v7;
    v24 = -2147024809;
    goto LABEL_35;
  }
  v24 = 0;
  v25 = 63;
  v8 = 261;
  *a2 = 0;
  cchReturnLength = 261;
  while ( 1 )
  {
    v9 = (WCHAR *)CoTaskMemRealloc(v6, 2LL * v8);
    v6 = v9;
    if ( !v9 )
    {
      v24 = -2147024882;
      v26 = 74;
      goto LABEL_35;
    }
    v24 = 0;
    v25 = 74;
    if ( GetVolumePathNamesForVolumeNameW(lpszVolumeName, v9, cchReturnLength, &cchReturnLength) )
      break;
    LastError = GetLastError();
    if ( LastError == 122 || LastError == 234 )
    {
      LastError = 0;
    }
    else if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
    }
    v24 = LastError;
    if ( LastError < 0 )
    {
      v26 = 84;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        LODWORD(v23) = LastError;
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
          (unsigned int)"dwErr",
          (__int64)lpszVolumeName,
          v23);
      }
      goto LABEL_35;
    }
    v8 = cchReturnLength;
    v25 = 84;
  }
  v11 = -1;
  v12 = v6;
  for ( i = v6; *v12; v12 += v16 )
  {
    v14 = -1;
    do
      ++v14;
    while ( v12[v14] );
    v15 = v12;
    if ( (unsigned int)v14 >= v11 )
      v15 = i;
    i = v15;
    v16 = (unsigned int)(v14 + 1);
    if ( (unsigned int)v14 >= v11 )
      LODWORD(v14) = v11;
    v11 = v14;
  }
  v17 = StringCchCopyW(a2, v3, i);
  v24 = v17;
  if ( v17 >= 0 )
  {
    v25 = 112;
  }
  else
  {
    v26 = 112;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      WPP_SF_sSSdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        v18,
        v19,
        (__int64)lpszVolumeName,
        v20,
        v3,
        v17);
  }
LABEL_35:
  CoTaskMemFree(v6);
  v21 = v24;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v24);
  return v21;
}

```

## disassembly

```asm
0x180095914  push    rbp
0x180095916  push    rbx
0x180095917  push    rsi
0x180095918  push    rdi
0x180095919  push    r12
0x18009591b  push    r13
0x18009591d  push    r14
0x18009591f  push    r15
0x180095921  lea     rbp, [rsp-1Fh]
0x180095926  sub     rsp, 88h
0x18009592d  mov     r14d, r8d
0x180095930  mov     rsi, rdx
0x180095933  mov     rdi, rcx
0x180095936  mov     rcx, cs:WPP_GLOBAL_Control
0x18009593d  lea     rax, WPP_GLOBAL_Control
0x180095944  cmp     rcx, rax
0x180095947  jz      short loc_180095968
0x180095949  test    dword ptr [rcx+1Ch], 20000000h
0x180095950  jz      short loc_180095968
0x180095952  mov     rcx, [rcx+10h]
0x180095956  mov     r9, rdi
0x180095959  mov     dword ptr [rsp+0C0h+var_98], r14d
0x18009595e  mov     [rsp+0C0h+var_A0], rdx
0x180095963  call    WPP_SF_Sqd
0x180095968  mov     r9d, 1; unsigned __int16
0x18009596e  lea     rdx, aSxgetpresentab; "SxGetPresentableVolumeName"
0x180095975  lea     rcx, [rbp+57h+var_80]; this
0x180095979  lea     r8d, [r9+31h]; unsigned __int16
0x18009597d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180095982  xor     r15d, r15d
0x180095985  mov     [rbp+57h+cchReturnLength], r15d
0x180095989  mov     ebx, r15d
0x18009598c  lea     eax, [r15+3Dh]
0x180095990  test    rdi, rdi
0x180095993  jz      loc_180095B51
0x180095999  mov     [rbp+57h+var_7C], ax
0x18009599d  test    rsi, rsi
0x1800959a0  jz      loc_180095B4C
0x1800959a6  lea     eax, [r15+3Fh]
0x1800959aa  mov     [rbp+57h+var_80], r15d
0x1800959ae  mov     [rbp+57h+var_7C], ax
0x1800959b2  lea     r12d, [r15+4Ah]
0x1800959b6  mov     eax, 105h
0x1800959bb  mov     [rsi], r15w
0x1800959bf  mov     [rbp+57h+cchReturnLength], eax
0x1800959c2  lea     r13d, [r15+54h]
0x1800959c6  mov     edx, eax
0x1800959c8  mov     rcx, rbx; pv
0x1800959cb  add     rdx, rdx; cb
0x1800959ce  call    cs:__imp_CoTaskMemRealloc
0x1800959d5  nop     dword ptr [rax+rax+00h]
0x1800959da  mov     rbx, rax
0x1800959dd  test    rax, rax
0x1800959e0  jz      loc_180095B3E
0x1800959e6  mov     r8d, [rbp+57h+cchReturnLength]; cchBufferLength
0x1800959ea  lea     r9, [rbp+57h+cchReturnLength]; lpcchReturnLength
0x1800959ee  mov     rdx, rax; lpszVolumePathNames
0x1800959f1  mov     [rbp+57h+var_80], r15d
0x1800959f5  mov     rcx, rdi; lpszVolumeName
0x1800959f8  mov     [rbp+57h+var_7C], r12w
0x1800959fd  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180095a04  nop     dword ptr [rax+rax+00h]
0x180095a09  test    eax, eax
0x180095a0b  jnz     loc_180095AA1
0x180095a11  call    cs:__imp_GetLastError
0x180095a18  nop     dword ptr [rax+rax+00h]
0x180095a1d  cmp     eax, 7Ah ; 'z'
0x180095a20  jz      short loc_180095A37
0x180095a22  cmp     eax, 0EAh
0x180095a27  jz      short loc_180095A37
0x180095a29  test    eax, eax
0x180095a2b  jle     short loc_180095A3A
0x180095a2d  movzx   eax, ax
0x180095a30  or      eax, 80070000h
0x180095a35  jmp     short loc_180095A3A
0x180095a37  mov     eax, r15d
0x180095a3a  mov     [rbp+57h+var_80], eax
0x180095a3d  test    eax, eax
0x180095a3f  js      short loc_180095A4E
0x180095a41  mov     eax, [rbp+57h+cchReturnLength]
0x180095a44  mov     [rbp+57h+var_7C], r13w
0x180095a49  jmp     loc_1800959C6
0x180095a4e  mov     [rbp+57h+var_7A], r13w
0x180095a53  mov     rcx, cs:WPP_GLOBAL_Control
0x180095a5a  lea     rdx, WPP_GLOBAL_Control
0x180095a61  cmp     rcx, rdx
0x180095a64  jz      loc_180095B5C
0x180095a6a  test    dword ptr [rcx+1Ch], 2000000h
0x180095a71  jz      loc_180095B5C
0x180095a77  mov     rcx, [rcx+10h]
0x180095a7b  lea     r9, aDwerr; "dwErr"
0x180095a82  mov     dword ptr [rsp+0C0h+var_98], eax
0x180095a86  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180095a8d  mov     edx, 0Bh
0x180095a92  mov     [rsp+0C0h+var_A0], rdi
0x180095a97  call    WPP_SF_sSd
0x180095a9c  jmp     loc_180095B5C
0x180095aa1  or      r9d, 0FFFFFFFFh
0x180095aa5  mov     r8, rbx
0x180095aa8  mov     r11, rbx
0x180095aab  cmp     [rbx], r15w
0x180095aaf  jz      short loc_180095AE0
0x180095ab1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180095ab5  inc     rdx
0x180095ab8  cmp     [r8+rdx*2], r15w
0x180095abd  jnz     short loc_180095AB5
0x180095abf  cmp     edx, r9d
0x180095ac2  mov     rax, r8
0x180095ac5  cmovnb  rax, r11
0x180095ac9  mov     r11, rax
0x180095acc  lea     eax, [rdx+1]
0x180095acf  cmovnb  edx, r9d
0x180095ad3  mov     r9d, edx
0x180095ad6  lea     r8, [r8+rax*2]
0x180095ada  cmp     [r8], r15w
0x180095ade  jnz     short loc_180095AB1
0x180095ae0  mov     rdx, r14; unsigned __int64
0x180095ae3  mov     r8, r11; unsigned __int16 *
0x180095ae6  mov     rcx, rsi; unsigned __int16 *
0x180095ae9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180095aee  mov     [rbp+57h+var_80], eax
0x180095af1  mov     ecx, 70h ; 'p'
0x180095af6  test    eax, eax
0x180095af8  jns     short loc_180095B38
0x180095afa  mov     [rbp+57h+var_7A], cx
0x180095afe  mov     rcx, cs:WPP_GLOBAL_Control
0x180095b05  lea     rdx, WPP_GLOBAL_Control
0x180095b0c  cmp     rcx, rdx
0x180095b0f  jz      short loc_180095B5C
0x180095b11  test    dword ptr [rcx+1Ch], 2000000h
0x180095b18  jz      short loc_180095B5C
0x180095b1a  mov     rcx, [rcx+10h]
0x180095b1e  mov     [rsp+0C0h+var_88], eax
0x180095b22  mov     [rsp+0C0h+var_90], r14d
0x180095b27  mov     [rsp+0C0h+var_98], r11
0x180095b2c  mov     [rsp+0C0h+var_A0], rdi
0x180095b31  call    WPP_SF_sSSdd
0x180095b36  jmp     short loc_180095B5C
0x180095b38  mov     [rbp+57h+var_7C], cx
0x180095b3c  jmp     short loc_180095B5C
0x180095b3e  mov     [rbp+57h+var_80], 8007000Eh
0x180095b45  mov     [rbp+57h+var_7A], r12w
0x180095b4a  jmp     short loc_180095B5C
0x180095b4c  mov     eax, 3Eh ; '>'
0x180095b51  mov     [rbp+57h+var_7A], ax
0x180095b55  mov     [rbp+57h+var_80], 80070057h
0x180095b5c  mov     rcx, rbx; pv
0x180095b5f  call    cs:__imp_CoTaskMemFree
0x180095b66  nop     dword ptr [rax+rax+00h]
0x180095b6b  mov     ebx, [rbp+57h+var_80]
0x180095b6e  lea     rcx, [rbp+57h+var_80]; this
0x180095b72  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180095b77  mov     eax, ebx
0x180095b79  add     rsp, 88h
0x180095b80  pop     r15
0x180095b82  pop     r14
0x180095b84  pop     r13
0x180095b86  pop     r12
0x180095b88  pop     rdi
0x180095b89  pop     rsi
0x180095b8a  pop     rbx
0x180095b8b  pop     rbp
0x180095b8c  retn
```
