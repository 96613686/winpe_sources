# SusMakeDirectoryW(wchar_t const *,ulong,void *)

- ea: `0x18000cbc4`
- end: `0x18000cd38`
- name: `?SusMakeDirectoryW@@YAJPEB_WKPEAX@Z`
- size: `372`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, unsigned int, void *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000cd40`
- `0x18001a094`
- `0x18002b2d4`
- `0x18003b800`

## callees

- `0x180003950`
- `0x18000c3a0`
- `0x18000c684`
- `0x18000cbc4`
- `0x18000e530`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000ccd7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000ccd7`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x18000cca2`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x18000cca2`

## pseudocode

```c
__int64 __fastcall SusMakeDirectoryW(PCNZWCH lpString1, __int64 a2, void *a3)
{
  int v4; // ebp
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rcx
  PCNZWCH v9; // rax
  int i; // esi
  int v12; // eax
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = 0;
  if ( lpString1 )
  {
    v7 = 0;
    v8 = 0x7FFFFFFF;
    v9 = lpString1;
    do
    {
      if ( !*v9 )
        break;
      ++v9;
      --v8;
    }
    while ( v8 );
    if ( v8 )
    {
      if ( ((0x7FFFFFFF - v8) & (unsigned __int64)-(__int64)(v8 != 0)) > 4
        && *lpString1 == 92
        && lpString1[1] == 92
        && lpString1[2] == 63
        && lpString1[3] == 92 )
      {
        v7 = 4;
      }
      if ( (unsigned int)HasLocalShortPathPrefix(&lpString1[v7]) )
        goto LABEL_16;
    }
    if ( VolumeUtil::HasVolumeIdPathPrefix(lpString1, (const wchar_t *)v7) )
    {
LABEL_16:
      if ( CheckIfDirExists(lpString1) >= 0 )
        return 0;
      v5 = 0;
      for ( i = 0; !i; i = 1 )
      {
        v12 = SHCreateDirectoryExW(0, lpString1, 0);
        if ( !v12 )
          return 0;
        if ( v12 != 5 && v12 != 32 )
        {
          if ( v12 == 80 || v12 == 183 )
            return 0;
          v5 = (unsigned __int16)v12 | 0x80070000;
          if ( v12 <= 0 )
            v5 = v12;
          break;
        }
        v5 = (unsigned __int16)v12 | 0x80070000;
        if ( v4-- )
          Sleep(0x1F4u);
      }
      if ( (v5 & 0x80000000) == 0 )
        return v5;
      v6 = 826;
    }
    else
    {
      v5 = -2147024735;
      v6 = 766;
    }
  }
  else
  {
    v5 = -2147024809;
    v6 = 758;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
    (const char *)v5,
    v14);
  return v5;
}

```

## disassembly

```asm
0x18000cbc4  mov     rax, rsp
0x18000cbc7  mov     [rax+8], rbx
0x18000cbcb  mov     [rax+10h], rbp
0x18000cbcf  mov     [rax+18h], rsi
0x18000cbd3  mov     [rax+20h], rdi
0x18000cbd7  push    r14; int
0x18000cbd9  sub     rsp, 20h
0x18000cbdd  xor     r14d, r14d
0x18000cbe0  mov     rdi, rcx
0x18000cbe3  mov     ebp, r14d
0x18000cbe6  test    rcx, rcx
0x18000cbe9  jnz     short loc_18000CBFA
0x18000cbeb  mov     ebx, 80070057h
0x18000cbf0  mov     edx, 2F6h
0x18000cbf5  jmp     loc_18000CD02
0x18000cbfa  mov     r8d, 7FFFFFFFh
0x18000cc00  mov     rdx, r14
0x18000cc03  mov     ecx, r8d
0x18000cc06  mov     rax, rdi
0x18000cc09  cmp     [rax], r14w
0x18000cc0d  jz      short loc_18000CC19
0x18000cc0f  add     rax, 2
0x18000cc13  sub     rcx, 1
0x18000cc17  jnz     short loc_18000CC09
0x18000cc19  sub     r8, rcx
0x18000cc1c  mov     rax, rcx
0x18000cc1f  neg     rax
0x18000cc22  sbb     r9, r9
0x18000cc25  and     r9, r8
0x18000cc28  test    rcx, rcx
0x18000cc2b  jz      short loc_18000CC61
0x18000cc2d  mov     eax, 4
0x18000cc32  cmp     r9, rax
0x18000cc35  jbe     short loc_18000CC54
0x18000cc37  cmp     word ptr [rdi], 5Ch ; '\'
0x18000cc3b  jnz     short loc_18000CC54
0x18000cc3d  cmp     word ptr [rdi+2], 5Ch ; '\'
0x18000cc42  jnz     short loc_18000CC54
0x18000cc44  cmp     word ptr [rdi+4], 3Fh ; '?'
0x18000cc49  jnz     short loc_18000CC54
0x18000cc4b  cmp     word ptr [rdi+6], 5Ch ; '\'
0x18000cc50  cmovz   rdx, rax
0x18000cc54  lea     rcx, [rdi+rdx*2]; wchar_t *
0x18000cc58  call    ?HasLocalShortPathPrefix@@YAHPEB_W@Z; HasLocalShortPathPrefix(wchar_t const *)
0x18000cc5d  test    eax, eax
0x18000cc5f  jnz     short loc_18000CC7C
0x18000cc61  mov     rcx, rdi; lpString1
0x18000cc64  call    ?HasVolumeIdPathPrefix@VolumeUtil@@YA_NPEB_W@Z; VolumeUtil::HasVolumeIdPathPrefix(wchar_t const *)
0x18000cc69  test    al, al
0x18000cc6b  jnz     short loc_18000CC7C
0x18000cc6d  mov     ebx, 800700A1h
0x18000cc72  mov     edx, 2FEh
0x18000cc77  jmp     loc_18000CD02
0x18000cc7c  mov     rcx, rdi; wchar_t *
0x18000cc7f  call    ?CheckIfDirExists@@YAJPEB_W@Z; CheckIfDirExists(wchar_t const *)
0x18000cc84  test    eax, eax
0x18000cc86  js      short loc_18000CC8F
0x18000cc88  xor     eax, eax
0x18000cc8a  jmp     loc_18000CD18
0x18000cc8f  mov     ebx, r14d
0x18000cc92  mov     esi, r14d
0x18000cc95  cmp     esi, 1
0x18000cc98  jnb     short loc_18000CCF9
0x18000cc9a  xor     r8d, r8d; psa
0x18000cc9d  mov     rdx, rdi; pszPath
0x18000cca0  xor     ecx, ecx; hwnd
0x18000cca2  call    cs:__imp_SHCreateDirectoryExW
0x18000cca8  mov     edx, eax
0x18000ccaa  test    eax, eax
0x18000ccac  jz      loc_18000CD33
0x18000ccb2  sub     edx, 5
0x18000ccb5  jz      short loc_18000CCBC
0x18000ccb7  sub     edx, 1Bh
0x18000ccba  jnz     short loc_18000CCE1
0x18000ccbc  movzx   ebx, ax
0x18000ccbf  or      ebx, 80070000h
0x18000ccc5  test    eax, eax
0x18000ccc7  cmovle  ebx, eax
0x18000ccca  mov     eax, ebp
0x18000cccc  dec     ebp
0x18000ccce  test    eax, eax
0x18000ccd0  jz      short loc_18000CCDD
0x18000ccd2  mov     ecx, 1F4h; dwMilliseconds
0x18000ccd7  call    cs:__imp_Sleep
0x18000ccdd  inc     esi
0x18000ccdf  jmp     short loc_18000CC95
0x18000cce1  sub     edx, 30h ; '0'
0x18000cce4  jz      short loc_18000CD33
0x18000cce6  cmp     edx, 67h ; 'g'
0x18000cce9  jz      short loc_18000CD33
0x18000cceb  movzx   ebx, ax
0x18000ccee  or      ebx, 80070000h
0x18000ccf4  test    eax, eax
0x18000ccf6  cmovle  ebx, eax
0x18000ccf9  test    ebx, ebx
0x18000ccfb  jns     short loc_18000CD16
0x18000ccfd  mov     edx, 33Ah; void *
0x18000cd02  mov     rcx, [rsp+28h]; this
0x18000cd07  lea     r8, aCW1SSrcClientL_25; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000cd0e  mov     r9d, ebx; char *
0x18000cd11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cd16  mov     eax, ebx
0x18000cd18  mov     rbx, [rsp+28h+arg_0]
0x18000cd1d  mov     rbp, [rsp+28h+arg_8]
0x18000cd22  mov     rsi, [rsp+28h+arg_10]
0x18000cd27  mov     rdi, [rsp+28h+arg_18]
0x18000cd2c  add     rsp, 20h
0x18000cd30  pop     r14
0x18000cd32  retn
0x18000cd33  mov     ebx, r14d
0x18000cd36  jmp     short loc_18000CD16
```
