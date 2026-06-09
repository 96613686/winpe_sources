# JsonHelper::WideCharToUTF8(ushort const *,int,char * *,int *)

- ea: `0x180014698`
- end: `0x180014890`
- name: `?WideCharToUTF8@JsonHelper@@AEAAJPEBGHPEAPEADPEAH@Z`
- size: `504`
- prototype: `int(JsonHelper *__hidden this, const unsigned __int16 *, int, char **, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180013290`

## callees

- `0x180006734`
- `0x180007a64`
- `0x180014698`
- `0x180014b34`
- `0x180014bb0`
- `0x180015488`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014802`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800146dc`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800147f8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800146dc`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800147f8`

## pseudocode

```c
__int64 __fastcall JsonHelper::WideCharToUTF8(JsonHelper *this, const unsigned __int16 *a2, int a3, char **a4)
{
  int v7; // eax
  __int64 v8; // rsi
  signed int LastError; // eax
  __int64 v10; // rdx
  signed int v11; // ebx
  int v12; // eax
  CHAR *lpMultiByteStr; // rax
  __int64 v14; // rdx
  char *v15; // rdi
  int v16; // eax
  signed int v17; // eax
  __int64 v18; // rdx
  int ActivityIdPrefix; // eax

  v7 = WideCharToMultiByte(0xFDE9u, 0, a2, a3, 0, 0, 0, 0);
  v8 = v7;
  if ( v7 )
    goto LABEL_9;
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( v11 >= 0 )
  {
LABEL_9:
    lpMultiByteStr = (CHAR *)operator new((int)v8 + 1);
    v15 = lpMultiByteStr;
    if ( lpMultiByteStr )
    {
      if ( WideCharToMultiByte(0xFDE9u, 0, a2, a3, lpMultiByteStr, v8 + 1, 0, 0) )
        goto LABEL_24;
      v17 = GetLastError();
      v11 = v17;
      if ( v17 > 0 )
        v11 = (unsigned __int16)v17 | 0x80070000;
      if ( v11 >= 0 )
      {
LABEL_24:
        v15[v8] = 0;
        v11 = 0;
        *a4 = v15;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v18);
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            53,
            (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
            ActivityIdPrefix,
            (__int64)"WideCharToMultiByte failed!",
            v11);
        }
        operator delete(v15);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v14);
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
          v16,
          (__int64)"CHAR[]");
      }
      return (unsigned int)-2147024882;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v10);
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      v12,
      (__int64)"WideCharToMultiByte failed!",
      v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180014698  mov     rax, rsp
0x18001469b  push    rbx
0x18001469c  push    rbp
0x18001469d  push    rsi
0x18001469e  push    rdi
0x18001469f  push    r14
0x1800146a1  push    r15
0x1800146a3  sub     rsp, 48h
0x1800146a7  mov     qword ptr [rax-40h], 0
0x1800146af  mov     r15, r9
0x1800146b2  mov     qword ptr [rax-48h], 0
0x1800146ba  mov     r9d, r8d; cchWideChar
0x1800146bd  mov     ebp, r8d
0x1800146c0  mov     dword ptr [rax-50h], 0
0x1800146c7  mov     r8, rdx; lpWideCharStr
0x1800146ca  mov     qword ptr [rax-58h], 0
0x1800146d2  mov     r14, rdx
0x1800146d5  mov     ecx, 0FDE9h; CodePage
0x1800146da  xor     edx, edx; dwFlags
0x1800146dc  call    cs:__imp_WideCharToMultiByte
0x1800146e2  movsxd  rsi, eax
0x1800146e5  test    eax, eax
0x1800146e7  jnz     short loc_180014766
0x1800146e9  call    cs:__imp_GetLastError
0x1800146ef  mov     ebx, eax
0x1800146f1  test    eax, eax
0x1800146f3  jle     short loc_1800146FE
0x1800146f5  movzx   ebx, ax
0x1800146f8  or      ebx, 80070000h
0x1800146fe  test    ebx, ebx
0x180014700  jns     short loc_180014766
0x180014702  mov     rcx, cs:WPP_GLOBAL_Control
0x180014709  lea     rax, WPP_GLOBAL_Control
0x180014710  cmp     rcx, rax
0x180014713  jz      loc_180014881
0x180014719  test    byte ptr [rcx+1Ch], 8
0x18001471d  jz      loc_180014881
0x180014723  cmp     byte ptr [rcx+19h], 2
0x180014727  jb      loc_180014881
0x18001472d  call    RdpX_GetActivityIdPrefix
0x180014732  lea     rcx, aWidechartomult; "WideCharToMultiByte failed!"
0x180014739  mov     [rsp+78h+cbMultiByte], ebx
0x18001473d  mov     [rsp+78h+lpMultiByteStr], rcx
0x180014742  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180014749  mov     rcx, cs:WPP_GLOBAL_Control
0x180014750  mov     edx, 33h ; '3'
0x180014755  mov     r9d, eax
0x180014758  mov     rcx, [rcx+10h]
0x18001475c  call    WPP_SF_DsD
0x180014761  jmp     loc_180014881
0x180014766  lea     ebx, [rsi+1]
0x180014769  movsxd  rcx, ebx; Size
0x18001476c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014771  mov     rdi, rax
0x180014774  test    rax, rax
0x180014777  jnz     short loc_1800147D0
0x180014779  mov     rcx, cs:WPP_GLOBAL_Control
0x180014780  lea     rax, WPP_GLOBAL_Control
0x180014787  cmp     rcx, rax
0x18001478a  jz      short loc_1800147C6
0x18001478c  test    byte ptr [rcx+1Ch], 8
0x180014790  jz      short loc_1800147C6
0x180014792  cmp     byte ptr [rcx+19h], 2
0x180014796  jb      short loc_1800147C6
0x180014798  call    RdpX_GetActivityIdPrefix
0x18001479d  lea     rcx, aChar; "CHAR[]"
0x1800147a4  mov     r9d, eax
0x1800147a7  mov     [rsp+78h+lpMultiByteStr], rcx
0x1800147ac  lea     edx, [rdi+34h]
0x1800147af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147b6  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x1800147bd  mov     rcx, [rcx+10h]
0x1800147c1  call    WPP_SF_Ds
0x1800147c6  mov     ebx, 8007000Eh
0x1800147cb  jmp     loc_180014881
0x1800147d0  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800147d9  mov     r9d, ebp; cchWideChar
0x1800147dc  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x1800147e5  mov     r8, r14; lpWideCharStr
0x1800147e8  mov     [rsp+78h+cbMultiByte], ebx; cbMultiByte
0x1800147ec  xor     edx, edx; dwFlags
0x1800147ee  mov     ecx, 0FDE9h; CodePage
0x1800147f3  mov     [rsp+78h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800147f8  call    cs:__imp_WideCharToMultiByte
0x1800147fe  test    eax, eax
0x180014800  jnz     short loc_180014878
0x180014802  call    cs:__imp_GetLastError
0x180014808  mov     ebx, eax
0x18001480a  test    eax, eax
0x18001480c  jle     short loc_180014817
0x18001480e  movzx   ebx, ax
0x180014811  or      ebx, 80070000h
0x180014817  test    ebx, ebx
0x180014819  jns     short loc_180014878
0x18001481b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014822  lea     rax, WPP_GLOBAL_Control
0x180014829  cmp     rcx, rax
0x18001482c  jz      short loc_18001486E
0x18001482e  test    byte ptr [rcx+1Ch], 8
0x180014832  jz      short loc_18001486E
0x180014834  cmp     byte ptr [rcx+19h], 2
0x180014838  jb      short loc_18001486E
0x18001483a  call    RdpX_GetActivityIdPrefix
0x18001483f  lea     rcx, aWidechartomult; "WideCharToMultiByte failed!"
0x180014846  mov     [rsp+78h+cbMultiByte], ebx
0x18001484a  mov     [rsp+78h+lpMultiByteStr], rcx
0x18001484f  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180014856  mov     rcx, cs:WPP_GLOBAL_Control
0x18001485d  mov     edx, 35h ; '5'
0x180014862  mov     r9d, eax
0x180014865  mov     rcx, [rcx+10h]
0x180014869  call    WPP_SF_DsD
0x18001486e  mov     rcx, rdi; Block
0x180014871  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014876  jmp     short loc_180014881
0x180014878  mov     byte ptr [rsi+rdi], 0
0x18001487c  xor     ebx, ebx
0x18001487e  mov     [r15], rdi
0x180014881  mov     eax, ebx
0x180014883  add     rsp, 48h
0x180014887  pop     r15
0x180014889  pop     r14
0x18001488b  pop     rdi
0x18001488c  pop     rsi
0x18001488d  pop     rbp
0x18001488e  pop     rbx
0x18001488f  retn
```
