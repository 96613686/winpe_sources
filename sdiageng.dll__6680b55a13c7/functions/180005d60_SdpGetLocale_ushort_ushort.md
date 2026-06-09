# SdpGetLocale(ushort *,ushort * *)

- ea: `0x180005d60`
- end: `0x180005ff5`
- name: `?SdpGetLocale@@YAJPEAGPEAPEAG@Z`
- size: `661`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000cf00`

## callees

- `0x1800012a4`
- `0x1800012b0`
- `0x1800020f8`
- `0x1800027f8`
- `0x180005d60`
- `0x180026fa0`
- `0x180027aa0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005de9`
- `KERNEL32!GetLastError` at `0x180005de9`
- `KERNEL32!GetThreadPreferredUILanguages` at `0x180005ddc`
- `KERNEL32!GetThreadPreferredUILanguages` at `0x180005ddc`

## pseudocode

```c
__int64 __fastcall SdpGetLocale(unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rsi
  WCHAR *v3; // rdi
  WCHAR *v4; // rax
  WCHAR *v5; // r12
  unsigned int v6; // ebx
  signed int LastError; // eax
  unsigned int v8; // r8d
  int v9; // r9d
  ULONG v10; // r13d
  const unsigned __int16 *v11; // r14
  int v12; // eax
  int v13; // eax
  __int64 v14; // rcx
  const unsigned __int16 *v15; // rax
  __int64 v16; // rdx
  int v18; // eax
  int v19; // [rsp+20h] [rbp-28h] BYREF
  LPCWSTR lpFileName; // [rsp+28h] [rbp-20h] BYREF
  unsigned __int16 *v21; // [rsp+30h] [rbp-18h] BYREF
  ULONG pcchLanguagesBuffer; // [rsp+A0h] [rbp+58h] BYREF
  ULONG pulNumLanguages; // [rsp+A8h] [rbp+60h] BYREF

  pcchLanguagesBuffer = 1024;
  v21 = 0;
  v2 = 0;
  lpFileName = 0;
  v3 = 0;
  pulNumLanguages = 0;
  v19 = 0;
  v4 = (WCHAR *)operator new[](0x800u);
  v5 = v4;
  if ( !v4 )
  {
    v6 = -2147024882;
    SdpDebugTrace(1u, L"SdpGetLocale", 0xF1u, -2147024882);
    return v6;
  }
  if ( GetThreadPreferredUILanguages(0x38u, &pulNumLanguages, v4, &pcchLanguagesBuffer) )
    goto LABEL_10;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( (v6 & 0x80000000) == 0 )
  {
LABEL_10:
    if ( pulNumLanguages )
    {
      v10 = 0;
      v11 = v5;
      while ( 1 )
      {
        if ( v3 )
        {
          operator delete(v3);
          v3 = 0;
          lpFileName = 0;
        }
        if ( v11 - v5 >= (int)pcchLanguagesBuffer || !v11 )
        {
          v6 = -2147418113;
          v8 = 262;
          goto LABEL_8;
        }
        v12 = SdpBuildPath(a1, v11, (unsigned __int16 **)&lpFileName);
        v6 = v12;
        if ( v12 < 0 )
        {
          SdpDebugTrace(1u, L"SdpGetLocale", 0x10Au, v12);
          v3 = (WCHAR *)lpFileName;
          goto LABEL_30;
        }
        v3 = (WCHAR *)lpFileName;
        v13 = SdpPathExists(lpFileName, &v19);
        v6 = v13;
        if ( v13 < 0 )
        {
          v9 = v13;
          v8 = 269;
          goto LABEL_9;
        }
        if ( v19 )
          break;
        v14 = pcchLanguagesBuffer;
        if ( pcchLanguagesBuffer > 0x7FFFFFFFuLL )
        {
          v6 = -2147024809;
LABEL_37:
          v9 = -2147024809;
          v8 = 286;
          goto LABEL_9;
        }
        v15 = v11;
        if ( pcchLanguagesBuffer )
        {
          do
          {
            if ( !*v15 )
              break;
            ++v15;
            --v14;
          }
          while ( v14 );
        }
        v6 = v14 == 0 ? 0x80070057 : 0;
        if ( v14 )
          v16 = pcchLanguagesBuffer - v14;
        else
          v16 = 0;
        if ( !v14 )
          goto LABEL_37;
        ++v10;
        v11 += v16 + 1;
        if ( v10 >= pulNumLanguages )
          goto LABEL_29;
      }
      v18 = SdpStrCpy(&v21, v11);
      v6 = v18;
      if ( v18 >= 0 )
      {
        v2 = v21;
LABEL_29:
        *a2 = v2;
        v2 = 0;
        goto LABEL_30;
      }
      SdpDebugTrace(1u, L"SdpGetLocale", 0x114u, v18);
      v2 = v21;
      goto LABEL_30;
    }
    v6 = -2147467259;
    v8 = 253;
  }
  else
  {
    v8 = 249;
  }
LABEL_8:
  v9 = v6;
LABEL_9:
  SdpDebugTrace(1u, L"SdpGetLocale", v8, v9);
LABEL_30:
  operator delete(v5);
  if ( v2 )
    operator delete(v2);
  if ( v3 )
    operator delete(v3);
  return v6;
}

```

## disassembly

```asm
0x180005d60  mov     [rsp-40h+arg_8], rdx
0x180005d65  mov     [rsp-40h+arg_0], rcx
0x180005d6a  push    rbp
0x180005d6b  push    rbx
0x180005d6c  push    rsi
0x180005d6d  push    rdi
0x180005d6e  push    r12
0x180005d70  push    r13
0x180005d72  push    r14
0x180005d74  push    r15
0x180005d76  mov     rbp, rsp
0x180005d79  sub     rsp, 48h
0x180005d7d  xor     ebx, ebx
0x180005d7f  mov     [rbp+pcchLanguagesBuffer], 400h
0x180005d86  mov     ecx, 800h; unsigned __int64
0x180005d8b  mov     [rbp+var_18], rbx
0x180005d8f  mov     esi, ebx
0x180005d91  mov     [rbp+lpFileName], rbx
0x180005d95  mov     edi, ebx
0x180005d97  mov     [rbp+pulNumLanguages], ebx
0x180005d9a  mov     [rbp+var_28], ebx
0x180005d9d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180005da2  mov     r12, rax
0x180005da5  test    rax, rax
0x180005da8  jnz     short loc_180005DCC
0x180005daa  mov     ebx, 8007000Eh
0x180005daf  lea     rdx, aSdpgetlocale; "SdpGetLocale"
0x180005db6  mov     r9d, ebx; int
0x180005db9  lea     ecx, [rdi+1]; Level
0x180005dbc  mov     r8d, 0F1h; int
0x180005dc2  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180005dc7  jmp     loc_180005F4D
0x180005dcc  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180005dd0  mov     r8, r12; pwszLanguagesBuffer
0x180005dd3  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x180005dd7  mov     ecx, 38h ; '8'; dwFlags
0x180005ddc  call    cs:__imp_GetThreadPreferredUILanguages
0x180005de2  xor     r8d, r8d
0x180005de5  test    eax, eax
0x180005de7  jnz     short loc_180005E24
0x180005de9  call    cs:__imp_GetLastError
0x180005def  xor     r8d, r8d
0x180005df2  mov     ebx, eax
0x180005df4  test    eax, eax
0x180005df6  jle     short loc_180005E01
0x180005df8  movzx   ebx, ax
0x180005dfb  or      ebx, 80070000h
0x180005e01  test    ebx, ebx
0x180005e03  jns     short loc_180005E24
0x180005e05  mov     r8d, 0F9h; int
0x180005e0b  mov     r9d, ebx; int
0x180005e0e  lea     rdx, aSdpgetlocale; "SdpGetLocale"
0x180005e15  mov     ecx, 1; Level
0x180005e1a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180005e1f  jmp     loc_180005F2B
0x180005e24  mov     eax, [rbp+pulNumLanguages]
0x180005e27  test    eax, eax
0x180005e29  jnz     short loc_180005E38
0x180005e2b  mov     ebx, 80004005h
0x180005e30  mov     r8d, 0FDh
0x180005e36  jmp     short loc_180005E0B
0x180005e38  mov     r13d, r8d
0x180005e3b  mov     r14, r12
0x180005e3e  test    eax, eax
0x180005e40  jz      loc_180005F21
0x180005e46  mov     r15d, 80070057h
0x180005e4c  test    rdi, rdi
0x180005e4f  jz      short loc_180005E63
0x180005e51  mov     rcx, rdi; Block
0x180005e54  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005e59  xor     r8d, r8d
0x180005e5c  mov     edi, r8d
0x180005e5f  mov     [rbp+lpFileName], r8
0x180005e63  movsxd  rax, [rbp+pcchLanguagesBuffer]
0x180005e67  mov     rcx, r14
0x180005e6a  sub     rcx, r12
0x180005e6d  sar     rcx, 1
0x180005e70  cmp     rcx, rax
0x180005e73  jge     loc_180005FE5
0x180005e79  test    r14, r14
0x180005e7c  jz      loc_180005FE5
0x180005e82  mov     rcx, [rbp+arg_0]; unsigned __int16 *
0x180005e86  lea     r8, [rbp+lpFileName]; unsigned __int16 **
0x180005e8a  mov     rdx, r14; unsigned __int16 *
0x180005e8d  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x180005e92  mov     ebx, eax
0x180005e94  test    eax, eax
0x180005e96  js      loc_180005FC2
0x180005e9c  mov     rdi, [rbp+lpFileName]
0x180005ea0  lea     rdx, [rbp+var_28]; int *
0x180005ea4  mov     rcx, rdi; lpFileName
0x180005ea7  call    ?SdpPathExists@@YAJPEBGPEAH@Z; SdpPathExists(ushort const *,int *)
0x180005eac  xor     r8d, r8d
0x180005eaf  mov     ebx, eax
0x180005eb1  test    eax, eax
0x180005eb3  js      loc_180005FB4
0x180005eb9  cmp     [rbp+var_28], r8d
0x180005ebd  jnz     loc_180005F76
0x180005ec3  mov     ecx, [rbp+pcchLanguagesBuffer]
0x180005ec6  cmp     rcx, 7FFFFFFFh
0x180005ecd  ja      loc_180005F65
0x180005ed3  mov     rax, r14
0x180005ed6  mov     edx, ecx
0x180005ed8  test    rcx, rcx
0x180005edb  jz      short loc_180005EED
0x180005edd  cmp     [rax], r8w
0x180005ee1  jz      short loc_180005EED
0x180005ee3  add     rax, 2
0x180005ee7  sub     rcx, 1
0x180005eeb  jnz     short loc_180005EDD
0x180005eed  mov     rax, rcx
0x180005ef0  neg     rax
0x180005ef3  sbb     ebx, ebx
0x180005ef5  not     ebx
0x180005ef7  and     ebx, r15d
0x180005efa  test    rcx, rcx
0x180005efd  jz      short loc_180005F04
0x180005eff  sub     rdx, rcx
0x180005f02  jmp     short loc_180005F07
0x180005f04  mov     rdx, r8
0x180005f07  test    rcx, rcx
0x180005f0a  jz      short loc_180005F60
0x180005f0c  lea     r14, [r14+rdx*2]
0x180005f10  inc     r13d
0x180005f13  add     r14, 2
0x180005f17  cmp     r13d, [rbp+pulNumLanguages]
0x180005f1b  jb      loc_180005E4C
0x180005f21  mov     rax, [rbp+arg_8]
0x180005f25  mov     [rax], rsi
0x180005f28  mov     rsi, r8
0x180005f2b  mov     rcx, r12; Block
0x180005f2e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005f33  test    rsi, rsi
0x180005f36  jz      short loc_180005F40
0x180005f38  mov     rcx, rsi; Block
0x180005f3b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005f40  test    rdi, rdi
0x180005f43  jz      short loc_180005F4D
0x180005f45  mov     rcx, rdi; Block
0x180005f48  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005f4d  mov     eax, ebx
0x180005f4f  add     rsp, 48h
0x180005f53  pop     r15
0x180005f55  pop     r14
0x180005f57  pop     r13
0x180005f59  pop     r12
0x180005f5b  pop     rdi
0x180005f5c  pop     rsi
0x180005f5d  pop     rbx
0x180005f5e  pop     rbp
0x180005f5f  retn
0x180005f60  mov     r15d, ebx
0x180005f63  jmp     short loc_180005F68
0x180005f65  mov     ebx, r15d
0x180005f68  mov     r9d, r15d
0x180005f6b  mov     r8d, 11Eh
0x180005f71  jmp     loc_180005E0E
0x180005f76  mov     rdx, r14; unsigned __int16 *
0x180005f79  lea     rcx, [rbp+var_18]; unsigned __int16 **
0x180005f7d  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x180005f82  xor     r8d, r8d
0x180005f85  mov     ebx, eax
0x180005f87  test    eax, eax
0x180005f89  jns     short loc_180005FAB
0x180005f8b  mov     r9d, eax; int
0x180005f8e  lea     rdx, aSdpgetlocale; "SdpGetLocale"
0x180005f95  mov     r8d, 114h; int
0x180005f9b  mov     ecx, 1; Level
0x180005fa0  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180005fa5  mov     rsi, [rbp+var_18]
0x180005fa9  jmp     short loc_180005F2B
0x180005fab  mov     rsi, [rbp+var_18]
0x180005faf  jmp     loc_180005F21
0x180005fb4  mov     r9d, eax
0x180005fb7  mov     r8d, 10Dh
0x180005fbd  jmp     loc_180005E0E
0x180005fc2  mov     r9d, eax; int
0x180005fc5  lea     rdx, aSdpgetlocale; "SdpGetLocale"
0x180005fcc  mov     r8d, 10Ah; int
0x180005fd2  mov     ecx, 1; Level
0x180005fd7  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180005fdc  mov     rdi, [rbp+lpFileName]
0x180005fe0  jmp     loc_180005F2B
0x180005fe5  mov     ebx, 8000FFFFh
0x180005fea  mov     r8d, 106h
0x180005ff0  jmp     loc_180005E0B
```
