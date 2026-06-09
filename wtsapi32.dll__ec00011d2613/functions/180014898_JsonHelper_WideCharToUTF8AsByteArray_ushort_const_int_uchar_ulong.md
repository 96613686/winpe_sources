# JsonHelper::WideCharToUTF8AsByteArray(ushort const *,int,uchar * *,ulong *)

- ea: `0x180014898`
- end: `0x180014aa5`
- name: `?WideCharToUTF8AsByteArray@JsonHelper@@AEAAJPEBGHPEAPEAEPEAK@Z`
- size: `525`
- prototype: `int(JsonHelper *__hidden this, const unsigned __int16 *, int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180012e70`

## callees

- `0x180006734`
- `0x180007a64`
- `0x180014898`
- `0x180014b34`
- `0x180014bb0`
- `0x180015488`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a04`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800148de`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800149fa`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800148de`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800149fa`

## pseudocode

```c
__int64 __fastcall JsonHelper::WideCharToUTF8AsByteArray(
        JsonHelper *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  int v8; // eax
  __int64 v9; // rbp
  signed int LastError; // eax
  __int64 v11; // rdx
  signed int v12; // ebx
  int v13; // eax
  CHAR *lpMultiByteStr; // rax
  __int64 v15; // rdx
  unsigned __int8 *v16; // rdi
  int v17; // eax
  signed int v18; // eax
  __int64 v19; // rdx
  int ActivityIdPrefix; // eax

  v8 = WideCharToMultiByte(0xFDE9u, 0, a2, a3, 0, 0, 0, 0);
  v9 = v8;
  if ( v8 )
    goto LABEL_9;
  LastError = GetLastError();
  v12 = LastError;
  if ( LastError > 0 )
    v12 = (unsigned __int16)LastError | 0x80070000;
  if ( v12 >= 0 )
  {
LABEL_9:
    lpMultiByteStr = (CHAR *)operator new((int)v9 + 1);
    v16 = (unsigned __int8 *)lpMultiByteStr;
    if ( lpMultiByteStr )
    {
      if ( WideCharToMultiByte(0xFDE9u, 0, a2, a3, lpMultiByteStr, v9 + 1, 0, 0) )
        goto LABEL_24;
      v18 = GetLastError();
      v12 = v18;
      if ( v18 > 0 )
        v12 = (unsigned __int16)v18 | 0x80070000;
      if ( v12 >= 0 )
      {
LABEL_24:
        v16[v9] = 0;
        *a4 = v16;
        if ( a5 )
          *a5 = v9 + 1;
        return 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v19);
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
            ActivityIdPrefix,
            (__int64)"WideCharToMultiByte failed!",
            v12);
        }
        operator delete(v16);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v15);
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
          v17,
          (__int64)"BYTE[]");
      }
      return (unsigned int)-2147024882;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v11);
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      v13,
      (__int64)"WideCharToMultiByte failed!",
      v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180014898  mov     rax, rsp
0x18001489b  push    rbx
0x18001489c  push    rbp
0x18001489d  push    rsi
0x18001489e  push    rdi
0x18001489f  push    r12
0x1800148a1  push    r14
0x1800148a3  push    r15
0x1800148a5  sub     rsp, 40h
0x1800148a9  mov     qword ptr [rax-40h], 0
0x1800148b1  mov     r12, r9
0x1800148b4  mov     qword ptr [rax-48h], 0
0x1800148bc  mov     r9d, r8d; cchWideChar
0x1800148bf  mov     r14d, r8d
0x1800148c2  mov     dword ptr [rax-50h], 0
0x1800148c9  mov     r8, rdx; lpWideCharStr
0x1800148cc  mov     qword ptr [rax-58h], 0
0x1800148d4  mov     r15, rdx
0x1800148d7  mov     ecx, 0FDE9h; CodePage
0x1800148dc  xor     edx, edx; dwFlags
0x1800148de  call    cs:__imp_WideCharToMultiByte
0x1800148e4  movsxd  rbp, eax
0x1800148e7  test    eax, eax
0x1800148e9  jnz     short loc_180014968
0x1800148eb  call    cs:__imp_GetLastError
0x1800148f1  mov     ebx, eax
0x1800148f3  test    eax, eax
0x1800148f5  jle     short loc_180014900
0x1800148f7  movzx   ebx, ax
0x1800148fa  or      ebx, 80070000h
0x180014900  test    ebx, ebx
0x180014902  jns     short loc_180014968
0x180014904  mov     rcx, cs:WPP_GLOBAL_Control
0x18001490b  lea     rax, WPP_GLOBAL_Control
0x180014912  cmp     rcx, rax
0x180014915  jz      loc_180014A94
0x18001491b  test    byte ptr [rcx+1Ch], 8
0x18001491f  jz      loc_180014A94
0x180014925  cmp     byte ptr [rcx+19h], 2
0x180014929  jb      loc_180014A94
0x18001492f  call    RdpX_GetActivityIdPrefix
0x180014934  lea     rcx, aWidechartomult; "WideCharToMultiByte failed!"
0x18001493b  mov     [rsp+78h+cbMultiByte], ebx
0x18001493f  mov     [rsp+78h+lpMultiByteStr], rcx
0x180014944  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18001494b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014952  mov     edx, 36h ; '6'
0x180014957  mov     r9d, eax
0x18001495a  mov     rcx, [rcx+10h]
0x18001495e  call    WPP_SF_DsD
0x180014963  jmp     loc_180014A94
0x180014968  lea     esi, [rbp+1]
0x18001496b  movsxd  rcx, esi; Size
0x18001496e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014973  mov     rdi, rax
0x180014976  test    rax, rax
0x180014979  jnz     short loc_1800149D2
0x18001497b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014982  lea     rax, WPP_GLOBAL_Control
0x180014989  cmp     rcx, rax
0x18001498c  jz      short loc_1800149C8
0x18001498e  test    byte ptr [rcx+1Ch], 8
0x180014992  jz      short loc_1800149C8
0x180014994  cmp     byte ptr [rcx+19h], 2
0x180014998  jb      short loc_1800149C8
0x18001499a  call    RdpX_GetActivityIdPrefix
0x18001499f  lea     rcx, aByte; "BYTE[]"
0x1800149a6  mov     r9d, eax
0x1800149a9  mov     [rsp+78h+lpMultiByteStr], rcx
0x1800149ae  lea     edx, [rdi+37h]
0x1800149b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149b8  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x1800149bf  mov     rcx, [rcx+10h]
0x1800149c3  call    WPP_SF_Ds
0x1800149c8  mov     ebx, 8007000Eh
0x1800149cd  jmp     loc_180014A94
0x1800149d2  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800149db  mov     r9d, r14d; cchWideChar
0x1800149de  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x1800149e7  mov     r8, r15; lpWideCharStr
0x1800149ea  mov     [rsp+78h+cbMultiByte], esi; cbMultiByte
0x1800149ee  xor     edx, edx; dwFlags
0x1800149f0  mov     ecx, 0FDE9h; CodePage
0x1800149f5  mov     [rsp+78h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800149fa  call    cs:__imp_WideCharToMultiByte
0x180014a00  test    eax, eax
0x180014a02  jnz     short loc_180014A7A
0x180014a04  call    cs:__imp_GetLastError
0x180014a0a  mov     ebx, eax
0x180014a0c  test    eax, eax
0x180014a0e  jle     short loc_180014A19
0x180014a10  movzx   ebx, ax
0x180014a13  or      ebx, 80070000h
0x180014a19  test    ebx, ebx
0x180014a1b  jns     short loc_180014A7A
0x180014a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a24  lea     rax, WPP_GLOBAL_Control
0x180014a2b  cmp     rcx, rax
0x180014a2e  jz      short loc_180014A70
0x180014a30  test    byte ptr [rcx+1Ch], 8
0x180014a34  jz      short loc_180014A70
0x180014a36  cmp     byte ptr [rcx+19h], 2
0x180014a3a  jb      short loc_180014A70
0x180014a3c  call    RdpX_GetActivityIdPrefix
0x180014a41  lea     rcx, aWidechartomult; "WideCharToMultiByte failed!"
0x180014a48  mov     [rsp+78h+cbMultiByte], ebx
0x180014a4c  mov     [rsp+78h+lpMultiByteStr], rcx
0x180014a51  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180014a58  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a5f  mov     edx, 38h ; '8'
0x180014a64  mov     r9d, eax
0x180014a67  mov     rcx, [rcx+10h]
0x180014a6b  call    WPP_SF_DsD
0x180014a70  mov     rcx, rdi; Block
0x180014a73  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014a78  jmp     short loc_180014A94
0x180014a7a  mov     rax, [rsp+78h+arg_20]
0x180014a82  mov     byte ptr [rbp+rdi+0], 0
0x180014a87  mov     [r12], rdi
0x180014a8b  test    rax, rax
0x180014a8e  jz      short loc_180014A92
0x180014a90  mov     [rax], esi
0x180014a92  xor     ebx, ebx
0x180014a94  mov     eax, ebx
0x180014a96  add     rsp, 40h
0x180014a9a  pop     r15
0x180014a9c  pop     r14
0x180014a9e  pop     r12
0x180014aa0  pop     rdi
0x180014aa1  pop     rsi
0x180014aa2  pop     rbp
0x180014aa3  pop     rbx
0x180014aa4  retn
```
