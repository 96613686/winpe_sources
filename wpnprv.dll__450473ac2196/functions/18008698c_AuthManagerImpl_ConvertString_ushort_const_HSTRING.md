# AuthManagerImpl::ConvertString(ushort const *,HSTRING__ * *)

- ea: `0x18008698c`
- end: `0x180086bd2`
- name: `?ConvertString@AuthManagerImpl@@AEAAJPEBGPEAPEAUHSTRING__@@@Z`
- size: `582`
- prototype: `__int64 __fastcall(AuthManagerImpl *this, const unsigned __int16 *, HSTRING *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180087c18`

## callees

- `0x18000fddc`
- `0x18000fe54`
- `0x18001c06c`
- `0x18001c6dc`
- `0x18002e0b4`
- `0x18002f808`
- `0x18008698c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180086b19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180086b19`

## pseudocode

```c
__int64 __fastcall AuthManagerImpl::ConvertString(
        AuthManagerImpl *this,
        const unsigned __int16 *a2,
        HSTRING *a3,
        __int64 a4)
{
  PVOID v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  HRESULT String; // eax
  int v15; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  UINT32 length; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int64 v18; // [rsp+50h] [rbp+18h] BYREF

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = *((_DWORD *)this + 2) == 1;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, a4);
  }
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7);
  v18 = 0;
  length = 0;
  *a3 = 0;
  v8 = StringCchLengthW(a2, 0x400u, &v18);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v12 = ULongLongToULong(v18, &length);
    v9 = v12;
    if ( v12 >= 0 )
    {
      String = WindowsCreateString(a2, length, a3);
      v9 = String;
      if ( String >= 0 )
      {
LABEL_34:
        v10 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_35;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          122,
          WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
          (unsigned int)String);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x375,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
        (const char *)v9,
        v15);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v11 = 123;
          goto LABEL_33;
        }
        goto LABEL_35;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          120,
          WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
          (unsigned int)v12);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x371,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
        (const char *)v9,
        v15);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v11 = 121;
          goto LABEL_33;
        }
LABEL_35:
        if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x10) != 0 && *((_BYTE *)v10 + 25) >= 6u )
          WPP_SF_d(v10[2], 124, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, v9);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        118,
        WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
        (unsigned int)v8);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x36D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
      (const char *)v9,
      v15);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v11 = 119;
LABEL_33:
        WPP_SF_d(v10[2], v11, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, v9);
        goto LABEL_34;
      }
      goto LABEL_35;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18008698c  mov     [rsp+arg_0], rbx
0x180086991  mov     [rsp+arg_18], rsi
0x180086996  push    rdi
0x180086997  push    r14
0x180086999  push    r15; int
0x18008699b  sub     rsp, 20h
0x18008699f  mov     rdi, r8
0x1800869a2  mov     rsi, rdx
0x1800869a5  mov     rax, rcx
0x1800869a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800869af  lea     r14, WPP_GLOBAL_Control
0x1800869b6  lea     r15, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x1800869bd  cmp     rcx, r14
0x1800869c0  jz      short loc_1800869E7
0x1800869c2  test    byte ptr [rcx+1Ch], 10h
0x1800869c6  jz      short loc_1800869E7
0x1800869c8  cmp     byte ptr [rcx+19h], 6
0x1800869cc  jb      short loc_1800869E7
0x1800869ce  cmp     dword ptr [rax+8], 1
0x1800869d2  mov     edx, 75h ; 'u'
0x1800869d7  mov     rcx, [rcx+10h]
0x1800869db  mov     r8, r15
0x1800869de  setz    r9b
0x1800869e2  call    WPP_SF_c
0x1800869e7  test    rsi, rsi
0x1800869ea  jnz     short loc_1800869F1
0x1800869ec  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800869f1  test    rdi, rdi
0x1800869f4  jnz     short loc_1800869FB
0x1800869f6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800869fb  lea     r8, [rsp+38h+arg_10]; unsigned __int64 *
0x180086a00  mov     [rsp+38h+arg_10], 0
0x180086a09  mov     edx, 400h; unsigned __int64
0x180086a0e  mov     [rsp+38h+length], 0
0x180086a16  mov     rcx, rsi; unsigned __int16 *
0x180086a19  mov     qword ptr [rdi], 0
0x180086a20  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180086a25  mov     ebx, eax
0x180086a27  test    eax, eax
0x180086a29  jns     short loc_180086A94
0x180086a2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180086a32  cmp     rcx, r14
0x180086a35  jz      short loc_180086A57
0x180086a37  test    byte ptr [rcx+1Ch], 10h
0x180086a3b  jz      short loc_180086A57
0x180086a3d  cmp     byte ptr [rcx+19h], 2
0x180086a41  jb      short loc_180086A57
0x180086a43  mov     rcx, [rcx+10h]
0x180086a47  mov     edx, 76h ; 'v'
0x180086a4c  mov     r9d, eax
0x180086a4f  mov     r8, r15
0x180086a52  call    WPP_SF_d
0x180086a57  mov     rcx, [rsp+38h]; this
0x180086a5c  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180086a63  mov     r9d, ebx; char *
0x180086a66  mov     edx, 36Dh; void *
0x180086a6b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180086a70  mov     rcx, cs:WPP_GLOBAL_Control
0x180086a77  cmp     rcx, r14
0x180086a7a  jz      loc_180086BBC
0x180086a80  test    byte ptr [rcx+1Ch], 80h
0x180086a84  jz      loc_180086B97
0x180086a8a  mov     edx, 77h ; 'w'
0x180086a8f  jmp     loc_180086B81
0x180086a94  mov     rcx, [rsp+38h+arg_10]; unsigned __int64
0x180086a99  lea     rdx, [rsp+38h+length]; unsigned int *
0x180086a9e  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180086aa3  mov     ebx, eax
0x180086aa5  test    eax, eax
0x180086aa7  jns     short loc_180086B0F
0x180086aa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180086ab0  cmp     rcx, r14
0x180086ab3  jz      short loc_180086AD5
0x180086ab5  test    byte ptr [rcx+1Ch], 10h
0x180086ab9  jz      short loc_180086AD5
0x180086abb  cmp     byte ptr [rcx+19h], 2
0x180086abf  jb      short loc_180086AD5
0x180086ac1  mov     rcx, [rcx+10h]
0x180086ac5  mov     edx, 78h ; 'x'
0x180086aca  mov     r9d, eax
0x180086acd  mov     r8, r15
0x180086ad0  call    WPP_SF_d
0x180086ad5  mov     rcx, [rsp+38h]; this
0x180086ada  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180086ae1  mov     r9d, ebx; char *
0x180086ae4  mov     edx, 371h; void *
0x180086ae9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180086aee  mov     rcx, cs:WPP_GLOBAL_Control
0x180086af5  cmp     rcx, r14
0x180086af8  jz      loc_180086BBC
0x180086afe  test    byte ptr [rcx+1Ch], 80h
0x180086b02  jz      loc_180086B97
0x180086b08  mov     edx, 79h ; 'y'
0x180086b0d  jmp     short loc_180086B81
0x180086b0f  mov     edx, [rsp+38h+length]; length
0x180086b13  mov     r8, rdi; string
0x180086b16  mov     rcx, rsi; sourceString
0x180086b19  call    cs:__imp_WindowsCreateString
0x180086b1f  mov     ebx, eax
0x180086b21  test    eax, eax
0x180086b23  jns     short loc_180086B90
0x180086b25  mov     rcx, cs:WPP_GLOBAL_Control
0x180086b2c  cmp     rcx, r14
0x180086b2f  jz      short loc_180086B51
0x180086b31  test    byte ptr [rcx+1Ch], 10h
0x180086b35  jz      short loc_180086B51
0x180086b37  cmp     byte ptr [rcx+19h], 2
0x180086b3b  jb      short loc_180086B51
0x180086b3d  mov     rcx, [rcx+10h]
0x180086b41  mov     edx, 7Ah ; 'z'
0x180086b46  mov     r9d, eax
0x180086b49  mov     r8, r15
0x180086b4c  call    WPP_SF_d
0x180086b51  mov     rcx, [rsp+38h]; this
0x180086b56  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180086b5d  mov     r9d, ebx; char *
0x180086b60  mov     edx, 375h; void *
0x180086b65  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180086b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180086b71  cmp     rcx, r14
0x180086b74  jz      short loc_180086BBC
0x180086b76  test    byte ptr [rcx+1Ch], 80h
0x180086b7a  jz      short loc_180086B97
0x180086b7c  mov     edx, 7Bh ; '{'
0x180086b81  mov     rcx, [rcx+10h]
0x180086b85  mov     r9d, ebx
0x180086b88  mov     r8, r15
0x180086b8b  call    WPP_SF_d
0x180086b90  mov     rcx, cs:WPP_GLOBAL_Control
0x180086b97  cmp     rcx, r14
0x180086b9a  jz      short loc_180086BBC
0x180086b9c  test    byte ptr [rcx+1Ch], 10h
0x180086ba0  jz      short loc_180086BBC
0x180086ba2  cmp     byte ptr [rcx+19h], 6
0x180086ba6  jb      short loc_180086BBC
0x180086ba8  mov     rcx, [rcx+10h]
0x180086bac  mov     edx, 7Ch ; '|'
0x180086bb1  mov     r9d, ebx
0x180086bb4  mov     r8, r15
0x180086bb7  call    WPP_SF_d
0x180086bbc  mov     rsi, [rsp+38h+arg_18]
0x180086bc1  mov     eax, ebx
0x180086bc3  mov     rbx, [rsp+38h+arg_0]
0x180086bc8  add     rsp, 20h
0x180086bcc  pop     r15
0x180086bce  pop     r14
0x180086bd0  pop     rdi
0x180086bd1  retn
```
