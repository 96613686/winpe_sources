# IniRegQueryValueExW

- ea: `0x383adcd50`
- end: `0x383add073`
- name: `IniRegQueryValueExW`
- size: `803`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x38387d7f0`
- `0x383add0d0`
- `0x383addca0`

## callees

- `0x3838427d0`
- `0x383adcd50`
- `0x383add590`
- `0x383addad0`

## import_xrefs

- `MSVCR100!_swscanf_s_l` at `0x383adcdf5`
- `MSVCR100!_swscanf_s_l` at `0x383adce82`
- `MSVCR100!_swscanf_s_l` at `0x383adcefd`
- `MSVCR100!_swscanf_s_l` at `0x383adcf63`
- `MSVCR100!_swscanf_s_l` at `0x383adcdf5`
- `MSVCR100!_swscanf_s_l` at `0x383adce82`
- `MSVCR100!_swscanf_s_l` at `0x383adcefd`
- `MSVCR100!_swscanf_s_l` at `0x383adcf63`
- `KERNEL32!SetLastError` at `0x383add031`
- `KERNEL32!SetLastError` at `0x383add031`
- `KERNEL32!CompareStringW` at `0x383adce2e`
- `KERNEL32!CompareStringW` at `0x383adce5d`
- `KERNEL32!CompareStringW` at `0x383adce2e`
- `KERNEL32!CompareStringW` at `0x383adce5d`
- `KERNEL32!HeapFree` at `0x383add022`
- `KERNEL32!HeapFree` at `0x383add022`
- `KERNEL32!GetProcessHeap` at `0x383add014`
- `KERNEL32!GetProcessHeap` at `0x383add014`
- `ADVAPI32!RegQueryValueExW` at `0x383add065`
- `ADVAPI32!RegQueryValueExW` at `0x383add065`

## pseudocode

```c
LSTATUS __fastcall IniRegQueryValueExW(HKEY a1, const WCHAR *a2, DWORD *a3, DWORD *a4, LPBYTE lpData, LPDWORD lpcbData)
{
  _DWORD *v6; // r14
  const wchar_t *v7; // rbx
  const WCHAR *v8; // rax
  _WORD *String; // rsi
  DWORD v10; // ebp
  int v11; // r12d
  int v12; // edi
  int *p_Src; // r13
  _WORD *v14; // rbx
  __int64 v15; // rcx
  wchar_t *v16; // rbx
  unsigned __int64 v17; // kr00_8
  int v18; // r15d
  _WORD *v19; // r14
  wchar_t i; // ax
  __int64 v21; // rcx
  HANDLE ProcessHeap; // rax
  int Src; // [rsp+30h] [rbp-38h] BYREF
  int v25; // [rsp+34h] [rbp-34h] BYREF

  v6 = a4;
  v7 = a2;
  if ( dword_383B1F178 )
  {
    v8 = (const WCHAR *)IniRegPathFromHKEY();
    if ( !v7 || !*v7 )
      v7 = L"@";
    String = (_WORD *)IniRegGetString(v8, v7);
    if ( !String )
    {
      v10 = 8;
      goto LABEL_50;
    }
    if ( *String == 0xFFFF && !String[1] )
    {
      v10 = 2;
LABEL_48:
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, String);
LABEL_50:
      SetLastError(v10);
      return v10;
    }
    v10 = 0;
    v11 = 1;
    Src = 0;
    v12 = 4;
    if ( _swscanf_s_l(String, L"dword:%08x", 0, &Src) == 1 )
    {
      v11 = 4;
      p_Src = &Src;
    }
    else
    {
      if ( CompareStringW(0x400u, 1u, String, 4, L"hex:", 4) == 2 )
      {
        v11 = 3;
      }
      else
      {
        if ( CompareStringW(0x400u, 1u, String, 4, L"hex(", 4) != 2 )
          goto LABEL_37;
        v14 = String + 4;
        if ( _swscanf_s_l(String + 4, L"%d):", 0, &v25) != 1 )
          goto LABEL_37;
        for ( ; *v14 != 58; ++v12 )
          ++v14;
        v11 = v25;
        if ( !++v12 )
        {
LABEL_37:
          v21 = -1;
          do
            ++v21;
          while ( String[v21] );
          v12 = 2 * v21 + 2;
          p_Src = (int *)String;
          goto LABEL_40;
        }
      }
      v15 = -1;
      do
        ++v15;
      while ( String[v15] );
      v16 = &String[v12];
      p_Src = (int *)String;
      v17 = v15 - v12;
      v18 = 0;
      v12 = v17 / 3 + 1;
      if ( _swscanf_s_l(v16, L"%08x", 0, &Src) == 1 )
      {
        v19 = String;
        do
        {
          for ( i = *v16; i != 44; ++v16 )
          {
            if ( !i )
              break;
            i = v16[1];
          }
          v19 = (_WORD *)((char *)v19 + 1);
          ++v18;
          *((_BYTE *)v19 - 1) = Src;
          if ( *v16 == 44 )
            ++v16;
        }
        while ( *v16 && _swscanf_s_l(v16, L"%08x", 0, &Src) == 1 );
        v6 = a4;
      }
      if ( v12 != v18 )
        goto LABEL_36;
      if ( v11 != 1 && v11 != 7 && v11 != 2 )
        goto LABEL_40;
      if ( (v12 & 1) != 0 )
      {
LABEL_36:
        v10 = 13;
        goto LABEL_48;
      }
      v12 = v17 / 3 + 3;
      *(_WORD *)((char *)String + v18) = 0;
    }
LABEL_40:
    if ( lpData )
    {
      if ( *lpcbData < v12 )
        v10 = 234;
      else
        memcpy(lpData, p_Src, (unsigned int)v12);
    }
    if ( v6 )
      *v6 = v11;
    if ( lpcbData )
      *lpcbData = v12;
    goto LABEL_48;
  }
  return RegQueryValueExW(a1, a2, a3, a4, lpData, lpcbData);
}

```

## disassembly

```asm
0x383adcd50  mov     [rsp+arg_18], r9
0x383adcd55  push    rbx
0x383adcd56  push    r14
0x383adcd58  sub     rsp, 58h
0x383adcd5c  cmp     cs:dword_383B1F178, 0
0x383adcd63  mov     r14, r9
0x383adcd66  mov     rbx, rdx
0x383adcd69  jz      loc_383ADD04B
0x383adcd6f  mov     [rsp+68h+arg_0], rbp
0x383adcd74  mov     [rsp+68h+arg_8], rsi
0x383adcd79  call    IniRegPathFromHKEY
0x383adcd7e  test    rbx, rbx
0x383adcd81  jz      short loc_383ADCD89
0x383adcd83  cmp     word ptr [rbx], 0
0x383adcd87  jnz     short loc_383ADCD90
0x383adcd89  lea     rbx, asc_383ADD074; "@"
0x383adcd90  mov     rdx, rbx; lpString2
0x383adcd93  mov     rcx, rax; lpAppName
0x383adcd96  call    IniRegGetString
0x383adcd9b  mov     rsi, rax
0x383adcd9e  test    rax, rax
0x383adcda1  jz      loc_383ADD02A
0x383adcda7  mov     eax, 0FFFFh
0x383adcdac  cmp     [rsi], ax
0x383adcdaf  jnz     short loc_383ADCDC2
0x383adcdb1  cmp     word ptr [rsi+2], 0
0x383adcdb6  jnz     short loc_383ADCDC2
0x383adcdb8  mov     ebp, 2
0x383adcdbd  jmp     loc_383ADD014
0x383adcdc2  mov     [rsp+68h+arg_10], rdi
0x383adcdca  mov     [rsp+68h+var_18], r12
0x383adcdcf  xor     ebp, ebp
0x383adcdd1  lea     r9, [rsp+68h+Src]
0x383adcdd6  lea     rdx, aDword08x; "dword:%08x"
0x383adcddd  xor     r8d, r8d; Locale
0x383adcde0  mov     rcx, rsi; Buffer
0x383adcde3  mov     [rsp+68h+var_20], r13
0x383adcde8  lea     r12d, [rbp+1]
0x383adcdec  mov     [rsp+68h+var_28], r15
0x383adcdf1  mov     [rsp+68h+Src], ebp
0x383adcdf5  call    cs:__imp__swscanf_s_l
0x383adcdfb  lea     edi, [rbp+4]
0x383adcdfe  cmp     eax, r12d
0x383adce01  jnz     short loc_383ADCE10
0x383adce03  mov     r12d, edi
0x383adce06  lea     r13, [rsp+68h+Src]
0x383adce0b  jmp     loc_383ADCFC3
0x383adce10  lea     rax, aHex_0; "hex:"
0x383adce17  mov     r9d, edi; cchCount1
0x383adce1a  mov     r8, rsi; lpString1
0x383adce1d  mov     edx, r12d; dwCmpFlags
0x383adce20  mov     ecx, 400h; Locale
0x383adce25  mov     [rsp+68h+cchCount2], edi; cchCount2
0x383adce29  mov     [rsp+68h+lpString2], rax; lpString2
0x383adce2e  call    cs:__imp_CompareStringW
0x383adce34  cmp     eax, 2
0x383adce37  jnz     short loc_383ADCE3F
0x383adce39  lea     r12d, [rax+1]
0x383adce3d  jmp     short loc_383ADCEB9
0x383adce3f  lea     rax, aHex; "hex("
0x383adce46  mov     r9d, edi; cchCount1
0x383adce49  mov     r8, rsi; lpString1
0x383adce4c  mov     edx, r12d; dwCmpFlags
0x383adce4f  mov     ecx, 400h; Locale
0x383adce54  mov     [rsp+68h+cchCount2], edi; cchCount2
0x383adce58  mov     [rsp+68h+lpString2], rax; lpString2
0x383adce5d  call    cs:__imp_CompareStringW
0x383adce63  cmp     eax, 2
0x383adce66  jnz     loc_383ADCFA6
0x383adce6c  lea     rbx, [rsi+8]
0x383adce70  lea     r9, [rsp+68h+var_34]
0x383adce75  lea     rdx, aD_1; "%d):"
0x383adce7c  mov     rcx, rbx; Buffer
0x383adce7f  xor     r8d, r8d; Locale
0x383adce82  call    cs:__imp__swscanf_s_l
0x383adce88  cmp     eax, r12d
0x383adce8b  jnz     loc_383ADCFA6
0x383adce91  cmp     word ptr [rbx], 3Ah ; ':'
0x383adce95  jz      short loc_383ADCEAC
0x383adce97  nop     word ptr [rax+rax+00000000h]
0x383adcea0  add     rbx, 2
0x383adcea4  inc     edi
0x383adcea6  cmp     word ptr [rbx], 3Ah ; ':'
0x383adceaa  jnz     short loc_383ADCEA0
0x383adceac  mov     r12d, [rsp+68h+var_34]
0x383adceb1  inc     edi
0x383adceb3  jz      loc_383ADCFA6
0x383adceb9  movsxd  r8, edi
0x383adcebc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x383adcec0  inc     rcx
0x383adcec3  cmp     [rsi+rcx*2], bp
0x383adcec7  jnz     short loc_383ADCEC0
0x383adcec9  sub     rcx, r8
0x383adcecc  lea     rbx, [rsi+r8*2]
0x383adced0  mov     rax, 0AAAAAAAAAAAAAAABh
0x383adceda  lea     r9, [rsp+68h+Src]
0x383adcedf  xor     r8d, r8d; Locale
0x383adcee2  mov     r13, rsi
0x383adcee5  mul     rcx
0x383adcee8  mov     rdi, rdx
0x383adceeb  lea     rdx, a08x; "%08x"
0x383adcef2  mov     rcx, rbx; Buffer
0x383adcef5  shr     rdi, 1
0x383adcef8  mov     r15d, ebp
0x383adcefb  inc     edi
0x383adcefd  call    cs:__imp__swscanf_s_l
0x383adcf03  cmp     eax, 1
0x383adcf06  jnz     short loc_383ADCF76
0x383adcf08  mov     r14, rsi
0x383adcf0b  nop     dword ptr [rax+rax+00h]
0x383adcf10  movzx   eax, word ptr [rbx]
0x383adcf13  cmp     ax, 2Ch ; ','
0x383adcf17  jz      short loc_383ADCF33
0x383adcf19  nop     dword ptr [rax+00000000h]
0x383adcf20  test    ax, ax
0x383adcf23  jz      short loc_383ADCF33
0x383adcf25  movzx   eax, word ptr [rbx+2]
0x383adcf29  add     rbx, 2
0x383adcf2d  cmp     ax, 2Ch ; ','
0x383adcf31  jnz     short loc_383ADCF20
0x383adcf33  movzx   eax, byte ptr [rsp+68h+Src]
0x383adcf38  inc     r14
0x383adcf3b  inc     r15d
0x383adcf3e  mov     [r14-1], al
0x383adcf42  cmp     word ptr [rbx], 2Ch ; ','
0x383adcf46  jnz     short loc_383ADCF4C
0x383adcf48  add     rbx, 2
0x383adcf4c  cmp     [rbx], bp
0x383adcf4f  jz      short loc_383ADCF6E
0x383adcf51  lea     r9, [rsp+68h+Src]
0x383adcf56  lea     rdx, a08x; "%08x"
0x383adcf5d  xor     r8d, r8d; Locale
0x383adcf60  mov     rcx, rbx; Buffer
0x383adcf63  call    cs:__imp__swscanf_s_l
0x383adcf69  cmp     eax, 1
0x383adcf6c  jz      short loc_383ADCF10
0x383adcf6e  mov     r14, [rsp+68h+arg_18]
0x383adcf76  cmp     edi, r15d
0x383adcf79  jnz     short loc_383ADCF9F
0x383adcf7b  cmp     r12d, 1
0x383adcf7f  jz      short loc_383ADCF8D
0x383adcf81  cmp     r12d, 7
0x383adcf85  jz      short loc_383ADCF8D
0x383adcf87  cmp     r12d, 2
0x383adcf8b  jnz     short loc_383ADCFC3
0x383adcf8d  test    dil, 1
0x383adcf91  jnz     short loc_383ADCF9F
0x383adcf93  movsxd  rax, r15d
0x383adcf96  add     edi, 2
0x383adcf99  mov     [rax+rsi], bp
0x383adcf9d  jmp     short loc_383ADCFC3
0x383adcf9f  mov     ebp, 0Dh
0x383adcfa4  jmp     short loc_383ADCFFD
0x383adcfa6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x383adcfaa  nop     word ptr [rax+rax+00h]
0x383adcfb0  inc     rcx
0x383adcfb3  cmp     [rsi+rcx*2], bp
0x383adcfb7  jnz     short loc_383ADCFB0
0x383adcfb9  lea     edi, ds:2[rcx*2]
0x383adcfc0  mov     r13, rsi
0x383adcfc3  mov     rcx, [rsp+68h+lpData]; void *
0x383adcfcb  mov     rbx, [rsp+68h+lpcbData]
0x383adcfd3  test    rcx, rcx
0x383adcfd6  jz      short loc_383ADCFEE
0x383adcfd8  cmp     [rbx], edi
0x383adcfda  jb      short loc_383ADCFE9
0x383adcfdc  mov     r8d, edi; Size
0x383adcfdf  mov     rdx, r13; Src
0x383adcfe2  call    memcpy
0x383adcfe7  jmp     short loc_383ADCFEE
0x383adcfe9  mov     ebp, 0EAh
0x383adcfee  test    r14, r14
0x383adcff1  jz      short loc_383ADCFF6
0x383adcff3  mov     [r14], r12d
0x383adcff6  test    rbx, rbx
0x383adcff9  jz      short loc_383ADCFFD
0x383adcffb  mov     [rbx], edi
0x383adcffd  mov     r13, [rsp+68h+var_20]
0x383add002  mov     r12, [rsp+68h+var_18]
0x383add007  mov     rdi, [rsp+68h+arg_10]
0x383add00f  mov     r15, [rsp+68h+var_28]
0x383add014  call    cs:__imp_GetProcessHeap
0x383add01a  mov     r8, rsi; lpMem
0x383add01d  xor     edx, edx; dwFlags
0x383add01f  mov     rcx, rax; hHeap
0x383add022  call    cs:__imp_HeapFree
0x383add028  jmp     short loc_383ADD02F
0x383add02a  mov     ebp, 8
0x383add02f  mov     ecx, ebp; dwErrCode
0x383add031  call    cs:__imp_SetLastError
0x383add037  mov     rsi, [rsp+68h+arg_8]
0x383add03c  mov     eax, ebp
0x383add03e  mov     rbp, [rsp+68h+arg_0]
0x383add043  add     rsp, 58h
0x383add047  pop     r14
0x383add049  pop     rbx
0x383add04a  retn
0x383add04b  mov     rax, [rsp+68h+lpcbData]
0x383add053  mov     qword ptr [rsp+68h+cchCount2], rax; lpcbData
0x383add058  mov     rax, [rsp+68h+lpData]
0x383add060  mov     [rsp+68h+lpString2], rax; lpData
0x383add065  call    cs:__imp_RegQueryValueExW
0x383add06b  add     rsp, 58h
0x383add06f  pop     r14
0x383add071  pop     rbx
0x383add072  retn
```
