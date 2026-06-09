# WcnSysCreateFont(long,long,uchar,uchar,long,HFONT__ * *)

- ea: `0x18001b9a4`
- end: `0x18001bc81`
- name: `?WcnSysCreateFont@@YAJJJEEJPEAPEAUHFONT__@@@Z`
- size: `733`
- prototype: `__int64 __usercall@<rax>(int cHeight@<ecx>, int cWidth@<edx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, int, HFONT *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180014880`
- `0x1800187c0`
- `0x180018c14`

## callees

- `0x180001820`
- `0x180002294`
- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x18001b9a4`
- `0x18001bc88`
- `0x18001f6b8`
- `0x18002de1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bbc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bbc9`
- `GDI32!CreateFontIndirectW` at `0x18001ba92`
- `GDI32!CreateFontIndirectW` at `0x18001ba92`
- `GDI32!CreateFontW` at `0x18001bbbb`
- `GDI32!CreateFontW` at `0x18001bbbb`

## pseudocode

```c
__int64 __fastcall WcnSysCreateFont(LONG cHeight, LONG cWidth, unsigned __int8 a3, BYTE a4, LONG cWeight, HFONT *a6)
{
  DWORD iCharSet; // r15d
  _QWORD *v10; // r10
  const char *Indent; // rax
  __int64 v12; // r10
  HFONT v14; // rax
  int String; // eax
  unsigned int v16; // ebx
  _BYTE *v17; // r10
  unsigned int v18; // eax
  char v19; // r10
  HFONT FontW; // rax
  signed int LastError; // eax
  unsigned int v22; // eax
  __int64 v23; // r10
  unsigned int v24; // eax
  __int64 v25; // r10
  LOGFONTW lf; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[64]; // [rsp+D0h] [rbp-30h] BYREF

  iCharSet = a3;
  memset_0(&lf, 0, sizeof(lf));
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v12 + 16), 14, WPP_b868cf630f7a3c9ff61f3762d0795807_Traceguids, Indent);
    v10 = WPP_GLOBAL_Control;
  }
  if ( a6 )
  {
    *a6 = 0;
    lf.lfHeight = cHeight;
    lf.lfWidth = cWidth;
    lf.lfPitchAndFamily = a4;
    lf.lfCharSet = iCharSet;
    lf.lfWeight = cWeight;
    v14 = CreateFontIndirectW(&lf);
    *a6 = v14;
    if ( v14 )
    {
      v16 = 0;
    }
    else
    {
      String = WcnUxLoadString(0x1130u, 0x40u, Buffer);
      v16 = String;
      if ( String >= 0 )
      {
        Buffer[63] = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          GetLastError();
          v18 = (unsigned int)GetIndent(0);
          WPP_SF_sSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            (unsigned int)WPP_b868cf630f7a3c9ff61f3762d0795807_Traceguids,
            v18,
            (__int64)Buffer,
            v19);
        }
        FontW = CreateFontW(cHeight, cWidth, 0, 0, cWeight, 0, 0, 0, iCharSet, 0, 0, 5u, 0x31u, Buffer);
        *a6 = FontW;
        if ( !FontW )
        {
          LastError = GetLastError();
          v16 = LastError;
          if ( LastError > 0 )
            v16 = (unsigned __int16)LastError | 0x80070000;
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v16;
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_25;
          v22 = (unsigned int)GetIndent(0);
          WPP_SF_sd(*(_QWORD *)(v23 + 16), 18, (unsigned int)WPP_b868cf630f7a3c9ff61f3762d0795807_Traceguids, v22, v16);
        }
      }
      else
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v16;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_25:
          if ( v17 != (_BYTE *)&WPP_GLOBAL_Control && ((v16 & 0x80000000) != 0 || v17[25] >= 6u) )
          {
            v24 = (unsigned int)GetIndent(-1);
            WPP_SF_sd(
              *(_QWORD *)(v25 + 16),
              19,
              (unsigned int)WPP_b868cf630f7a3c9ff61f3762d0795807_Traceguids,
              v24,
              v16);
          }
          return v16;
        }
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_b868cf630f7a3c9ff61f3762d0795807_Traceguids,
          (unsigned int)String);
      }
    }
    v17 = WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  if ( v10 != &WPP_GLOBAL_Control && *((_BYTE *)v10 + 25) >= 2u )
    WPP_SF_s(v10[2], 15, WPP_b868cf630f7a3c9ff61f3762d0795807_Traceguids, "phFont");
  return 2147500035LL;
}

```

## disassembly

```asm
0x18001b9a4  push    rbp
0x18001b9a6  push    rbx
0x18001b9a7  push    rsi
0x18001b9a8  push    rdi
0x18001b9a9  push    r12
0x18001b9ab  push    r14
0x18001b9ad  push    r15
0x18001b9af  lea     rbp, [rsp-60h]
0x18001b9b4  sub     rsp, 160h
0x18001b9bb  mov     rax, cs:__security_cookie
0x18001b9c2  xor     rax, rsp
0x18001b9c5  mov     [rbp+90h+var_40], rax
0x18001b9c9  mov     r12d, [rbp+90h+arg_20]
0x18001b9d0  mov     r14d, edx
0x18001b9d3  mov     rdi, [rbp+90h+arg_28]
0x18001b9da  xor     edx, edx; Val
0x18001b9dc  movzx   r15d, r8b
0x18001b9e0  mov     esi, ecx
0x18001b9e2  lea     rcx, [rsp+190h+lf]; void *
0x18001b9e7  mov     bl, r9b
0x18001b9ea  lea     r8d, [rdx+5Ch]; Size
0x18001b9ee  call    memset_0
0x18001b9f3  mov     r10, cs:WPP_GLOBAL_Control
0x18001b9fa  lea     rax, WPP_GLOBAL_Control
0x18001ba01  cmp     r10, rax
0x18001ba04  jz      short loc_18001BA3D
0x18001ba06  cmp     byte ptr [r10+19h], 6
0x18001ba0b  jb      short loc_18001BA3D
0x18001ba0d  mov     ecx, 1; int
0x18001ba12  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001ba17  mov     rcx, [r10+10h]
0x18001ba1b  lea     r8, WPP_b868cf630f7a3c9ff61f3762d0795807_Traceguids
0x18001ba22  mov     edx, 0Eh
0x18001ba27  mov     r9, rax
0x18001ba2a  call    WPP_SF_s
0x18001ba2f  mov     r10, cs:WPP_GLOBAL_Control
0x18001ba36  lea     rax, WPP_GLOBAL_Control
0x18001ba3d  test    rdi, rdi
0x18001ba40  jnz     short loc_18001BA72
0x18001ba42  cmp     r10, rax
0x18001ba45  jz      short loc_18001BA68
0x18001ba47  cmp     byte ptr [r10+19h], 2
0x18001ba4c  jb      short loc_18001BA68
0x18001ba4e  mov     rcx, [r10+10h]
0x18001ba52  lea     edx, [rdi+0Fh]
0x18001ba55  lea     r9, aPhfont; "phFont"
0x18001ba5c  lea     r8, WPP_b868cf630f7a3c9ff61f3762d0795807_Traceguids
0x18001ba63  call    WPP_SF_s
0x18001ba68  mov     eax, 80004003h
0x18001ba6d  jmp     loc_18001BC63
0x18001ba72  lea     rcx, [rsp+190h+lf]; lplf
0x18001ba77  mov     qword ptr [rdi], 0
0x18001ba7e  mov     [rsp+190h+lf.lfHeight], esi
0x18001ba82  mov     [rsp+190h+lf.lfWidth], r14d
0x18001ba87  mov     [rbp+90h+lf.lfPitchAndFamily], bl
0x18001ba8a  mov     [rbp+90h+lf.lfCharSet], r15b
0x18001ba8e  mov     [rbp+90h+lf.lfWeight], r12d
0x18001ba92  call    cs:__imp_CreateFontIndirectW
0x18001ba98  mov     [rdi], rax
0x18001ba9b  test    rax, rax
0x18001ba9e  jnz     loc_18001BC1D
0x18001baa4  lea     r8, [rbp+90h+Buffer]; lpBuffer
0x18001baa8  mov     ecx, 1130h; uID
0x18001baad  lea     edx, [rax+40h]; cchBufferMax
0x18001bab0  call    ?WcnUxLoadString@@YAJIKPEAG@Z; WcnUxLoadString(uint,ulong,ushort *)
0x18001bab5  mov     ebx, eax
0x18001bab7  test    eax, eax
0x18001bab9  jns     short loc_18001BAFA
0x18001babb  mov     r10, cs:WPP_GLOBAL_Control
0x18001bac2  lea     rdi, WPP_GLOBAL_Control
0x18001bac9  cmp     r10, rdi
0x18001bacc  jz      loc_18001BC61
0x18001bad2  cmp     byte ptr [r10+19h], 2
0x18001bad7  jb      loc_18001BC2D
0x18001badd  mov     rcx, [r10+10h]
0x18001bae1  lea     r8, WPP_b868cf630f7a3c9ff61f3762d0795807_Traceguids
0x18001bae8  mov     edx, 10h
0x18001baed  mov     r9d, eax
0x18001baf0  call    WPP_SF_d
0x18001baf5  jmp     loc_18001BC26
0x18001bafa  xor     eax, eax
0x18001bafc  mov     [rbp+90h+var_42], ax
0x18001bb00  mov     rax, cs:WPP_GLOBAL_Control
0x18001bb07  lea     rcx, WPP_GLOBAL_Control
0x18001bb0e  cmp     rax, rcx
0x18001bb11  jz      short loc_18001BB65
0x18001bb13  cmp     byte ptr [rax+19h], 3
0x18001bb17  jb      short loc_18001BB65
0x18001bb19  call    cs:__imp_GetLastError
0x18001bb1f  mov     r10d, eax
0x18001bb22  test    eax, eax
0x18001bb24  jle     short loc_18001BB31
0x18001bb26  movzx   r10d, ax
0x18001bb2a  or      r10d, 80070000h
0x18001bb31  xor     ecx, ecx; int
0x18001bb33  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001bb38  lea     rcx, [rbp+90h+Buffer]
0x18001bb3c  mov     [rsp+190h+bItalic], r10d
0x18001bb41  mov     qword ptr [rsp+190h+cWeight], rcx
0x18001bb46  lea     r8, WPP_b868cf630f7a3c9ff61f3762d0795807_Traceguids
0x18001bb4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb54  mov     edx, 11h
0x18001bb59  mov     r9, rax
0x18001bb5c  mov     rcx, [rcx+10h]
0x18001bb60  call    WPP_SF_sSd
0x18001bb65  lea     rcx, [rbp+90h+Buffer]
0x18001bb69  xor     r9d, r9d; cOrientation
0x18001bb6c  mov     [rsp+190h+pszFaceName], rcx; pszFaceName
0x18001bb71  xor     r8d, r8d; cEscapement
0x18001bb74  mov     [rsp+190h+iPitchAndFamily], 31h ; '1'; iPitchAndFamily
0x18001bb7c  mov     edx, r14d; cWidth
0x18001bb7f  mov     [rsp+190h+iQuality], 5; iQuality
0x18001bb87  mov     ecx, esi; cHeight
0x18001bb89  mov     [rsp+190h+iClipPrecision], 0; iClipPrecision
0x18001bb91  mov     [rsp+190h+iOutPrecision], 0; iOutPrecision
0x18001bb99  mov     [rsp+190h+iCharSet], r15d; iCharSet
0x18001bb9e  mov     [rsp+190h+bStrikeOut], 0; bStrikeOut
0x18001bba6  mov     [rsp+190h+bUnderline], 0; bUnderline
0x18001bbae  mov     [rsp+190h+bItalic], 0; bItalic
0x18001bbb6  mov     [rsp+190h+cWeight], r12d; cWeight
0x18001bbbb  call    cs:__imp_CreateFontW
0x18001bbc1  mov     [rdi], rax
0x18001bbc4  test    rax, rax
0x18001bbc7  jnz     short loc_18001BC1F
0x18001bbc9  call    cs:__imp_GetLastError
0x18001bbcf  mov     ebx, eax
0x18001bbd1  test    eax, eax
0x18001bbd3  jle     short loc_18001BBDE
0x18001bbd5  movzx   ebx, ax
0x18001bbd8  or      ebx, 80070000h
0x18001bbde  mov     r10, cs:WPP_GLOBAL_Control
0x18001bbe5  lea     rdi, WPP_GLOBAL_Control
0x18001bbec  cmp     r10, rdi
0x18001bbef  jz      short loc_18001BC61
0x18001bbf1  cmp     byte ptr [r10+19h], 2
0x18001bbf6  jb      short loc_18001BC2D
0x18001bbf8  xor     ecx, ecx; int
0x18001bbfa  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001bbff  mov     rcx, [r10+10h]
0x18001bc03  lea     r8, WPP_b868cf630f7a3c9ff61f3762d0795807_Traceguids
0x18001bc0a  mov     edx, 12h
0x18001bc0f  mov     [rsp+190h+cWeight], ebx
0x18001bc13  mov     r9, rax
0x18001bc16  call    WPP_SF_sd
0x18001bc1b  jmp     short loc_18001BC26
0x18001bc1d  xor     ebx, ebx
0x18001bc1f  lea     rdi, WPP_GLOBAL_Control
0x18001bc26  mov     r10, cs:WPP_GLOBAL_Control
0x18001bc2d  cmp     r10, rdi
0x18001bc30  jz      short loc_18001BC61
0x18001bc32  test    ebx, ebx
0x18001bc34  js      short loc_18001BC3D
0x18001bc36  cmp     byte ptr [r10+19h], 6
0x18001bc3b  jb      short loc_18001BC61
0x18001bc3d  or      ecx, 0FFFFFFFFh; int
0x18001bc40  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001bc45  mov     rcx, [r10+10h]
0x18001bc49  lea     r8, WPP_b868cf630f7a3c9ff61f3762d0795807_Traceguids
0x18001bc50  mov     edx, 13h
0x18001bc55  mov     [rsp+190h+cWeight], ebx
0x18001bc59  mov     r9, rax
0x18001bc5c  call    WPP_SF_sd
0x18001bc61  mov     eax, ebx
0x18001bc63  mov     rcx, [rbp+90h+var_40]
0x18001bc67  xor     rcx, rsp; StackCookie
0x18001bc6a  call    __security_check_cookie
0x18001bc6f  add     rsp, 160h
0x18001bc76  pop     r15
0x18001bc78  pop     r14
0x18001bc7a  pop     r12
0x18001bc7c  pop     rdi
0x18001bc7d  pop     rsi
0x18001bc7e  pop     rbx
0x18001bc7f  pop     rbp
0x18001bc80  retn
```
