# BlbutilQueryVolumeAccessPath(ushort *,ushort * *)

- ea: `0x14008b7d4`
- end: `0x14008b93a`
- name: `?BlbutilQueryVolumeAccessPath@@YAJPEAGPEAPEAG@Z`
- size: `358`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140010470`
- `0x140010efc`
- `0x14003f388`
- `0x14003f860`
- `0x1400eacd4`
- `0x14011a7ec`

## callees

- `0x1400063b4`
- `0x140014260`
- `0x14008b7d4`

## import_xrefs

- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14008b803`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14008b861`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14008b803`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14008b861`
- `KERNEL32!GetLastError` at `0x14008b80d`
- `KERNEL32!GetLastError` at `0x14008b86b`
- `KERNEL32!GetLastError` at `0x14008b80d`
- `KERNEL32!GetLastError` at `0x14008b86b`
- `ole32!CoTaskMemAlloc` at `0x14008b839`
- `ole32!CoTaskMemAlloc` at `0x14008b8a0`
- `ole32!CoTaskMemAlloc` at `0x14008b839`
- `ole32!CoTaskMemAlloc` at `0x14008b8a0`
- `ole32!CoTaskMemFree` at `0x14008b8d9`
- `ole32!CoTaskMemFree` at `0x14008b8e2`
- `ole32!CoTaskMemFree` at `0x14008b8d9`
- `ole32!CoTaskMemFree` at `0x14008b8e2`

## pseudocode

```c
__int64 __fastcall BlbutilQueryVolumeAccessPath(LPCWSTR lpszVolumeName, unsigned __int16 **a2)
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
      (unsigned int)WPP_4c89e0416b2b3a4e6cf04444c0dc1079_Traceguids,
      (_DWORD)lpszVolumeName,
      v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14008b7d4  mov     rax, rsp
0x14008b7d7  mov     [rax+8], rbx
0x14008b7db  push    rbp
0x14008b7dc  push    rsi
0x14008b7dd  push    rdi
0x14008b7de  push    r14
0x14008b7e0  push    r15
0x14008b7e2  sub     rsp, 30h
0x14008b7e6  xor     r15d, r15d
0x14008b7e9  lea     r9, [rax+10h]; lpcchReturnLength
0x14008b7ed  mov     [rdx], r15
0x14008b7f0  mov     r14, rdx
0x14008b7f3  xor     edx, edx; lpszVolumePathNames
0x14008b7f5  mov     [rax+10h], r15d
0x14008b7f9  xor     r8d, r8d; cchBufferLength
0x14008b7fc  mov     [rax+18h], r15d
0x14008b800  mov     rbp, rcx
0x14008b803  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x14008b809  test    eax, eax
0x14008b80b  jnz     short loc_14008B832
0x14008b80d  call    cs:__imp_GetLastError
0x14008b813  mov     ebx, eax
0x14008b815  cmp     eax, 0EAh
0x14008b81a  jz      short loc_14008B832
0x14008b81c  test    eax, eax
0x14008b81e  jle     loc_14008B8E8
0x14008b824  movzx   ebx, ax
0x14008b827  or      ebx, 80070000h
0x14008b82d  jmp     loc_14008B8E8
0x14008b832  mov     ecx, [rsp+58h+cchBufferLength]
0x14008b836  add     rcx, rcx; cb
0x14008b839  call    cs:__imp_CoTaskMemAlloc
0x14008b83f  mov     rsi, rax
0x14008b842  test    rax, rax
0x14008b845  jnz     short loc_14008B851
0x14008b847  mov     ebx, 8007000Eh
0x14008b84c  jmp     loc_14008B8EC
0x14008b851  mov     r8d, [rsp+58h+cchBufferLength]; cchBufferLength
0x14008b856  lea     r9, [rsp+58h+cchReturnLength]; lpcchReturnLength
0x14008b85b  mov     rdx, rsi; lpszVolumePathNames
0x14008b85e  mov     rcx, rbp; lpszVolumeName
0x14008b861  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x14008b867  test    eax, eax
0x14008b869  jnz     short loc_14008B882
0x14008b86b  call    cs:__imp_GetLastError
0x14008b871  mov     ebx, eax
0x14008b873  test    eax, eax
0x14008b875  jle     short loc_14008B8DF
0x14008b877  movzx   ebx, ax
0x14008b87a  or      ebx, 80070000h
0x14008b880  jmp     short loc_14008B8DF
0x14008b882  mov     ebx, r15d
0x14008b885  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14008b889  inc     rdi
0x14008b88c  cmp     [rsi+rdi*2], r15w
0x14008b891  jnz     short loc_14008B889
0x14008b893  test    edi, edi
0x14008b895  jz      short loc_14008B8DF
0x14008b897  lea     eax, [rdi+1]
0x14008b89a  lea     rcx, [rax+rax]; cb
0x14008b89e  mov     ebx, eax
0x14008b8a0  call    cs:__imp_CoTaskMemAlloc
0x14008b8a6  mov     r11, rax
0x14008b8a9  test    rax, rax
0x14008b8ac  jnz     short loc_14008B8B5
0x14008b8ae  mov     ebx, 8007000Eh
0x14008b8b3  jmp     short loc_14008B8DF
0x14008b8b5  mov     r8, rsi; unsigned __int16 *
0x14008b8b8  mov     rdx, rbx; unsigned __int64
0x14008b8bb  mov     rcx, r11; unsigned __int16 *
0x14008b8be  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14008b8c3  mov     ebx, eax
0x14008b8c5  test    eax, eax
0x14008b8c7  js      short loc_14008B8D6
0x14008b8c9  lea     ecx, [rdi-1]
0x14008b8cc  mov     [r11+rcx*2], r15w
0x14008b8d1  mov     [r14], r11
0x14008b8d4  jmp     short loc_14008B8DF
0x14008b8d6  mov     rcx, r11; pv
0x14008b8d9  call    cs:__imp_CoTaskMemFree
0x14008b8df  mov     rcx, rsi; pv
0x14008b8e2  call    cs:__imp_CoTaskMemFree
0x14008b8e8  test    ebx, ebx
0x14008b8ea  jns     short loc_14008B927
0x14008b8ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b8f3  lea     rax, WPP_GLOBAL_Control
0x14008b8fa  cmp     rcx, rax
0x14008b8fd  jz      short loc_14008B927
0x14008b8ff  test    byte ptr [rcx+1Ch], 1
0x14008b903  jz      short loc_14008B927
0x14008b905  cmp     byte ptr [rcx+19h], 3
0x14008b909  jb      short loc_14008B927
0x14008b90b  mov     rcx, [rcx+10h]
0x14008b90f  lea     r8, WPP_4c89e0416b2b3a4e6cf04444c0dc1079_Traceguids
0x14008b916  mov     edx, 0Ah
0x14008b91b  mov     [rsp+58h+var_38], ebx
0x14008b91f  mov     r9, rbp
0x14008b922  call    WPP_SF_Sd
0x14008b927  mov     eax, ebx
0x14008b929  mov     rbx, [rsp+58h+arg_0]
0x14008b92e  add     rsp, 30h
0x14008b932  pop     r15
0x14008b934  pop     r14
0x14008b936  pop     rdi
0x14008b937  pop     rsi
0x14008b938  pop     rbp
0x14008b939  retn
```
