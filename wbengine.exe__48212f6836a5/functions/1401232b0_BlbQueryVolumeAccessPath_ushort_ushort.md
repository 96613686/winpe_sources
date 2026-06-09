# BlbQueryVolumeAccessPath(ushort *,ushort * *)

- ea: `0x1401232b0`
- end: `0x140123416`
- name: `?BlbQueryVolumeAccessPath@@YAJPEAGPEAPEAG@Z`
- size: `358`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName, unsigned __int16 **)`
- caller_count: `15`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140024088`
- `0x1400290e4`
- `0x140029cf4`
- `0x14004504c`
- `0x140045dec`
- `0x14004647c`
- `0x140049700`
- `0x1400572c0`
- `0x140101124`
- `0x140101a94`
- `0x140101b64`
- `0x140104e8c`
- `0x14010e004`
- `0x14010e288`
- `0x14010fc5c`

## callees

- `0x1400063b4`
- `0x140014260`
- `0x1401232b0`

## import_xrefs

- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x1401232df`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14012333d`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x1401232df`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14012333d`
- `KERNEL32!GetLastError` at `0x1401232e9`
- `KERNEL32!GetLastError` at `0x140123347`
- `KERNEL32!GetLastError` at `0x1401232e9`
- `KERNEL32!GetLastError` at `0x140123347`
- `ole32!CoTaskMemAlloc` at `0x140123315`
- `ole32!CoTaskMemAlloc` at `0x14012337c`
- `ole32!CoTaskMemAlloc` at `0x140123315`
- `ole32!CoTaskMemAlloc` at `0x14012337c`
- `ole32!CoTaskMemFree` at `0x1401233b5`
- `ole32!CoTaskMemFree` at `0x1401233be`
- `ole32!CoTaskMemFree` at `0x1401233b5`
- `ole32!CoTaskMemFree` at `0x1401233be`

## pseudocode

```c
__int64 __fastcall BlbQueryVolumeAccessPath(LPCWSTR lpszVolumeName, unsigned __int16 **a2)
{
  signed int LastError; // eax
  int v5; // ebx
  WCHAR *v6; // rax
  unsigned __int16 *v7; // rsi
  signed int v8; // eax
  __int64 v9; // rdi
  unsigned __int16 *v10; // rax
  void *v11; // r11
  DWORD cchBufferLength; // [rsp+68h] [rbp+10h] BYREF
  DWORD cchReturnLength; // [rsp+70h] [rbp+18h] BYREF

  *a2 = 0;
  cchBufferLength = 0;
  cchReturnLength = 0;
  if ( !GetVolumePathNamesForVolumeNameW(lpszVolumeName, 0, 0, &cchBufferLength) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 234 )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_19;
    }
  }
  v6 = (WCHAR *)CoTaskMemAlloc(2LL * cchBufferLength);
  v7 = v6;
  if ( v6 )
  {
    if ( GetVolumePathNamesForVolumeNameW(lpszVolumeName, v6, cchBufferLength, &cchReturnLength) )
    {
      v5 = 0;
      v9 = -1;
      do
        ++v9;
      while ( v7[v9] );
      if ( (_DWORD)v9 )
      {
        v10 = (unsigned __int16 *)CoTaskMemAlloc(2LL * (unsigned int)(v9 + 1));
        if ( v10 )
        {
          v5 = StringCchCopyW(v10, (unsigned int)(v9 + 1), v7);
          if ( v5 < 0 )
          {
            CoTaskMemFree(v11);
          }
          else
          {
            *((_WORD *)v11 + (unsigned int)(v9 - 1)) = 0;
            *a2 = (unsigned __int16 *)v11;
          }
        }
        else
        {
          v5 = -2147024882;
        }
      }
    }
    else
    {
      v8 = GetLastError();
      v5 = v8;
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
    }
    CoTaskMemFree(v7);
LABEL_19:
    if ( v5 >= 0 )
      return (unsigned int)v5;
    goto LABEL_20;
  }
  v5 = -2147024882;
LABEL_20:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids,
      (_DWORD)lpszVolumeName,
      v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1401232b0  mov     rax, rsp
0x1401232b3  mov     [rax+8], rbx
0x1401232b7  push    rbp
0x1401232b8  push    rsi
0x1401232b9  push    rdi
0x1401232ba  push    r14
0x1401232bc  push    r15
0x1401232be  sub     rsp, 30h
0x1401232c2  xor     r15d, r15d
0x1401232c5  lea     r9, [rax+10h]; lpcchReturnLength
0x1401232c9  mov     [rdx], r15
0x1401232cc  mov     r14, rdx
0x1401232cf  xor     edx, edx; lpszVolumePathNames
0x1401232d1  mov     [rax+10h], r15d
0x1401232d5  xor     r8d, r8d; cchBufferLength
0x1401232d8  mov     [rax+18h], r15d
0x1401232dc  mov     rbp, rcx
0x1401232df  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1401232e5  test    eax, eax
0x1401232e7  jnz     short loc_14012330E
0x1401232e9  call    cs:__imp_GetLastError
0x1401232ef  mov     ebx, eax
0x1401232f1  cmp     eax, 0EAh
0x1401232f6  jz      short loc_14012330E
0x1401232f8  test    eax, eax
0x1401232fa  jle     loc_1401233C4
0x140123300  movzx   ebx, ax
0x140123303  or      ebx, 80070000h
0x140123309  jmp     loc_1401233C4
0x14012330e  mov     ecx, [rsp+58h+cchBufferLength]
0x140123312  add     rcx, rcx; cb
0x140123315  call    cs:__imp_CoTaskMemAlloc
0x14012331b  mov     rsi, rax
0x14012331e  test    rax, rax
0x140123321  jnz     short loc_14012332D
0x140123323  mov     ebx, 8007000Eh
0x140123328  jmp     loc_1401233C8
0x14012332d  mov     r8d, [rsp+58h+cchBufferLength]; cchBufferLength
0x140123332  lea     r9, [rsp+58h+cchReturnLength]; lpcchReturnLength
0x140123337  mov     rdx, rsi; lpszVolumePathNames
0x14012333a  mov     rcx, rbp; lpszVolumeName
0x14012333d  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x140123343  test    eax, eax
0x140123345  jnz     short loc_14012335E
0x140123347  call    cs:__imp_GetLastError
0x14012334d  mov     ebx, eax
0x14012334f  test    eax, eax
0x140123351  jle     short loc_1401233BB
0x140123353  movzx   ebx, ax
0x140123356  or      ebx, 80070000h
0x14012335c  jmp     short loc_1401233BB
0x14012335e  mov     ebx, r15d
0x140123361  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140123365  inc     rdi
0x140123368  cmp     [rsi+rdi*2], r15w
0x14012336d  jnz     short loc_140123365
0x14012336f  test    edi, edi
0x140123371  jz      short loc_1401233BB
0x140123373  lea     eax, [rdi+1]
0x140123376  lea     rcx, [rax+rax]; cb
0x14012337a  mov     ebx, eax
0x14012337c  call    cs:__imp_CoTaskMemAlloc
0x140123382  mov     r11, rax
0x140123385  test    rax, rax
0x140123388  jnz     short loc_140123391
0x14012338a  mov     ebx, 8007000Eh
0x14012338f  jmp     short loc_1401233BB
0x140123391  mov     r8, rsi; unsigned __int16 *
0x140123394  mov     rdx, rbx; unsigned __int64
0x140123397  mov     rcx, r11; unsigned __int16 *
0x14012339a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14012339f  mov     ebx, eax
0x1401233a1  test    eax, eax
0x1401233a3  js      short loc_1401233B2
0x1401233a5  lea     ecx, [rdi-1]
0x1401233a8  mov     [r11+rcx*2], r15w
0x1401233ad  mov     [r14], r11
0x1401233b0  jmp     short loc_1401233BB
0x1401233b2  mov     rcx, r11; pv
0x1401233b5  call    cs:__imp_CoTaskMemFree
0x1401233bb  mov     rcx, rsi; pv
0x1401233be  call    cs:__imp_CoTaskMemFree
0x1401233c4  test    ebx, ebx
0x1401233c6  jns     short loc_140123403
0x1401233c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1401233cf  lea     rax, WPP_GLOBAL_Control
0x1401233d6  cmp     rcx, rax
0x1401233d9  jz      short loc_140123403
0x1401233db  test    byte ptr [rcx+1Ch], 1
0x1401233df  jz      short loc_140123403
0x1401233e1  cmp     byte ptr [rcx+19h], 3
0x1401233e5  jb      short loc_140123403
0x1401233e7  mov     rcx, [rcx+10h]
0x1401233eb  lea     r8, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids
0x1401233f2  mov     edx, 0Ah
0x1401233f7  mov     [rsp+58h+var_38], ebx
0x1401233fb  mov     r9, rbp
0x1401233fe  call    WPP_SF_Sd
0x140123403  mov     eax, ebx
0x140123405  mov     rbx, [rsp+58h+arg_0]
0x14012340a  add     rsp, 30h
0x14012340e  pop     r15
0x140123410  pop     r14
0x140123412  pop     rdi
0x140123413  pop     rsi
0x140123414  pop     rbp
0x140123415  retn
```
