# GetCardModuleHandle(_CARD_MATCH_DATA *,ushort *,HINSTANCE__ * *)

- ea: `0x180032318`
- end: `0x180032564`
- name: `?GetCardModuleHandle@@YAKPEAU_CARD_MATCH_DATA@@PEAGPEAPEAUHINSTANCE__@@@Z`
- size: `588`
- prototype: `unsigned int(struct _CARD_MATCH_DATA *, unsigned __int16 *, HINSTANCE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180032cf4`

## callees

- `0x18000a408`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x180032318`
- `0x180037730`
- `0x180037a4c`
- `0x18003ae44`
- `0x18003aec8`
- `0x18003c240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032440`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032440`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003241a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180032435`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003241a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180032435`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800324ee`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800324ee`

## pseudocode

```c
__int64 __fastcall GetCardModuleHandle(LPCRITICAL_SECTION *a1, unsigned __int16 *a2, HINSTANCE *a3)
{
  __int64 result; // rax
  DWORD v7; // eax
  __int64 v8; // rsi
  DWORD LastError; // ebx
  HMODULE Library; // rax
  __int64 v11; // rcx
  HMODULE v12; // rcx
  int v13; // [rsp+20h] [rbp-78h]
  int v14; // [rsp+28h] [rbp-70h]
  __int64 v15; // [rsp+40h] [rbp-58h] BYREF
  __int64 v16; // [rsp+48h] [rbp-50h] BYREF
  __int128 v17; // [rsp+50h] [rbp-48h]

  v16 = 0;
  LODWORD(v15) = 0;
  v17 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  *a3 = 0;
  result = CspEnterCriticalSection(*a1);
  if ( !(_DWORD)result )
  {
    v7 = ScCacheRead(a1[1], v13, v14, (__int64)&v16, (__int64)&v15);
    v8 = v16;
    LastError = v7;
    if ( v7 + 2146434960 > 1 )
    {
      if ( !v7 )
      {
        if ( (_DWORD)v15 == 8 )
          *a3 = *(HINSTANCE *)v16;
        else
          LastError = -2146435041;
      }
      goto LABEL_20;
    }
    Library = LoadLibraryExW(a2, 0, 0);
    if ( Library || (Library = LoadLibraryExW(a2, 0, 0x1100u)) != 0 )
    {
      *a3 = Library;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError )
      {
LABEL_20:
        CspLeaveCriticalSection(*a1);
        if ( LastError )
        {
          v12 = *a3;
          if ( *a3 )
          {
            FreeLibrary(v12);
            *a3 = 0;
          }
        }
        if ( v8 )
          CspFreeH(v8);
        WppTraceIndent(v12, 1);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
            (_DWORD)WPP_pszIndent,
            LastError);
        }
        return LastError;
      }
    }
    LastError = ScCacheWrite(a1[1], 0, 0, a3, 8);
    if ( LastError )
    {
      WppTraceIndent(v11, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          (_DWORD)WPP_pszIndent,
          LastError);
      }
    }
    goto LABEL_20;
  }
  return result;
}

```

## disassembly

```asm
0x180032318  push    rbx
0x18003231a  push    rbp
0x18003231b  push    rsi
0x18003231c  push    rdi
0x18003231d  push    r14
0x18003231f  sub     rsp, 70h
0x180032323  mov     rax, cs:__security_cookie
0x18003232a  xor     rax, rsp
0x18003232d  mov     [rsp+98h+var_38], rax
0x180032332  mov     rbp, rdx
0x180032335  mov     [rsp+98h+var_50], 0
0x18003233e  xorps   xmm0, xmm0
0x180032341  mov     dword ptr [rsp+98h+var_58], 0
0x180032349  xor     edx, edx
0x18003234b  mov     rdi, r8
0x18003234e  movups  [rsp+98h+var_48], xmm0
0x180032353  mov     r14, rcx
0x180032356  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003235b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032362  lea     rax, WPP_GLOBAL_Control
0x180032369  cmp     rcx, rax
0x18003236c  jz      short loc_180032396
0x18003236e  test    byte ptr [rcx+1Ch], 2
0x180032372  jz      short loc_180032396
0x180032374  cmp     byte ptr [rcx+19h], 5
0x180032378  jb      short loc_180032396
0x18003237a  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180032381  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180032388  mov     rcx, [rcx+10h]
0x18003238c  mov     edx, 0Ah
0x180032391  call    WPP_SF_s
0x180032396  mov     qword ptr [rdi], 0
0x18003239d  mov     rcx, [r14]
0x1800323a0  call    CspEnterCriticalSection
0x1800323a5  test    eax, eax
0x1800323a7  jnz     loc_18003254C
0x1800323ad  mov     rcx, [r14+8]; lpCriticalSection
0x1800323b1  lea     rax, [rsp+98h+var_58]
0x1800323b6  mov     [rsp+98h+var_60], rax; __int64
0x1800323bb  lea     rdx, [rsp+98h+var_48]
0x1800323c0  lea     rax, [rsp+98h+var_50]
0x1800323c5  mov     r9, rbp
0x1800323c8  xor     r8d, r8d
0x1800323cb  mov     [rsp+98h+Src], rax; __int64
0x1800323d0  call    ScCacheRead
0x1800323d5  mov     rsi, [rsp+98h+var_50]
0x1800323da  mov     ebx, eax
0x1800323dc  lea     ecx, [rax+7FEFFF90h]
0x1800323e2  cmp     ecx, 1
0x1800323e5  jbe     short loc_180032412
0x1800323e7  test    eax, eax
0x1800323e9  jnz     loc_1800324D3
0x1800323ef  cmp     dword ptr [rsp+98h+var_58], 8
0x1800323f4  lea     rbp, WPP_GLOBAL_Control
0x1800323fb  jz      short loc_180032407
0x1800323fd  mov     ebx, 8010001Fh
0x180032402  jmp     loc_1800324DA
0x180032407  mov     rax, [rsi]
0x18003240a  mov     [rdi], rax
0x18003240d  jmp     loc_1800324DA
0x180032412  xor     r8d, r8d; dwFlags
0x180032415  xor     edx, edx; hFile
0x180032417  mov     rcx, rbp; lpLibFileName
0x18003241a  call    cs:__imp_LoadLibraryExW
0x180032420  test    rax, rax
0x180032423  jz      short loc_18003242A
0x180032425  mov     [rdi], rax
0x180032428  jmp     short loc_180032450
0x18003242a  xor     edx, edx; hFile
0x18003242c  mov     r8d, 1100h; dwFlags
0x180032432  mov     rcx, rbp; lpLibFileName
0x180032435  call    cs:__imp_LoadLibraryExW
0x18003243b  test    rax, rax
0x18003243e  jnz     short loc_180032425
0x180032440  call    cs:__imp_GetLastError
0x180032446  mov     ebx, eax
0x180032448  test    eax, eax
0x18003244a  jnz     loc_1800324D3
0x180032450  mov     rcx, [r14+8]; lpCriticalSection
0x180032454  lea     rdx, [rsp+98h+var_48]
0x180032459  mov     dword ptr [rsp+98h+var_60], 8; int
0x180032461  mov     r9, rbp
0x180032464  mov     [rsp+98h+Src], rdi; Src
0x180032469  xor     r8d, r8d
0x18003246c  mov     qword ptr [rsp+98h+var_70], 0; int
0x180032475  mov     [rsp+98h+var_78], 0; int
0x18003247d  call    ScCacheWrite
0x180032482  mov     ebx, eax
0x180032484  test    eax, eax
0x180032486  jz      short loc_1800324D3
0x180032488  mov     edx, 2
0x18003248d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180032492  mov     rcx, cs:WPP_GLOBAL_Control
0x180032499  lea     rbp, WPP_GLOBAL_Control
0x1800324a0  cmp     rcx, rbp
0x1800324a3  jz      short loc_1800324DA
0x1800324a5  test    byte ptr [rcx+1Ch], 1
0x1800324a9  jz      short loc_1800324DA
0x1800324ab  cmp     byte ptr [rcx+19h], 2
0x1800324af  jb      short loc_1800324DA
0x1800324b1  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800324b8  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800324bf  mov     rcx, [rcx+10h]
0x1800324c3  mov     edx, 0Bh
0x1800324c8  mov     [rsp+98h+var_78], ebx
0x1800324cc  call    WPP_SF_sd
0x1800324d1  jmp     short loc_1800324DA
0x1800324d3  lea     rbp, WPP_GLOBAL_Control
0x1800324da  mov     rcx, [r14]
0x1800324dd  call    CspLeaveCriticalSection
0x1800324e2  test    ebx, ebx
0x1800324e4  jz      short loc_1800324FB
0x1800324e6  mov     rcx, [rdi]; hLibModule
0x1800324e9  test    rcx, rcx
0x1800324ec  jz      short loc_1800324FB
0x1800324ee  call    cs:__imp_FreeLibrary
0x1800324f4  mov     qword ptr [rdi], 0
0x1800324fb  test    rsi, rsi
0x1800324fe  jz      short loc_180032508
0x180032500  mov     rcx, rsi
0x180032503  call    CspFreeH
0x180032508  mov     edx, 1
0x18003250d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180032512  mov     rcx, cs:WPP_GLOBAL_Control
0x180032519  cmp     rcx, rbp
0x18003251c  jz      short loc_18003254A
0x18003251e  test    byte ptr [rcx+1Ch], 2
0x180032522  jz      short loc_18003254A
0x180032524  cmp     byte ptr [rcx+19h], 5
0x180032528  jb      short loc_18003254A
0x18003252a  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180032531  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180032538  mov     rcx, [rcx+10h]
0x18003253c  mov     edx, 0Ch
0x180032541  mov     [rsp+98h+var_78], ebx
0x180032545  call    WPP_SF_sd
0x18003254a  mov     eax, ebx
0x18003254c  mov     rcx, [rsp+98h+var_38]
0x180032551  xor     rcx, rsp; StackCookie
0x180032554  call    __security_check_cookie
0x180032559  add     rsp, 70h
0x18003255d  pop     r14
0x18003255f  pop     rdi
0x180032560  pop     rsi
0x180032561  pop     rbp
0x180032562  pop     rbx
0x180032563  retn
```
