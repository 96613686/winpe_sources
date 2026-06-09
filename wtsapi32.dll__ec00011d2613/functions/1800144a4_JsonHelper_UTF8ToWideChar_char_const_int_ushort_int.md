# JsonHelper::UTF8ToWideChar(char const *,int,ushort * *,int *)

- ea: `0x1800144a4`
- end: `0x180014692`
- name: `?UTF8ToWideChar@JsonHelper@@AEAAJPEBDHPEAPEAGPEAH@Z`
- size: `494`
- prototype: `int(JsonHelper *__hidden this, const char *, int, unsigned __int16 **, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180013d30`
- `0x180014390`

## callees

- `0x180006734`
- `0x180007a64`
- `0x1800144a4`
- `0x180014b34`
- `0x180014bb0`
- `0x180015488`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014602`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014602`
- `KERNEL32!MultiByteToWideChar` at `0x1800144d8`
- `KERNEL32!MultiByteToWideChar` at `0x1800145f8`
- `KERNEL32!MultiByteToWideChar` at `0x1800144d8`
- `KERNEL32!MultiByteToWideChar` at `0x1800145f8`

## pseudocode

```c
__int64 __fastcall JsonHelper::UTF8ToWideChar(JsonHelper *this, const char *a2, int a3, unsigned __int16 **a4)
{
  int v7; // eax
  __int64 v8; // rsi
  signed int LastError; // eax
  __int64 v10; // rdx
  signed int v11; // ebx
  int v12; // eax
  WCHAR *lpWideCharStr; // rax
  __int64 v14; // rdx
  unsigned __int16 *v15; // rdi
  int v16; // eax
  signed int v17; // eax
  __int64 v18; // rdx
  int ActivityIdPrefix; // eax

  v7 = MultiByteToWideChar(0xFDE9u, 0, a2, a3, 0, 0);
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
    lpWideCharStr = (WCHAR *)operator new(saturated_mul((int)v8 + 1, 2u));
    v15 = lpWideCharStr;
    if ( lpWideCharStr )
    {
      if ( MultiByteToWideChar(0xFDE9u, 0, a2, a3, lpWideCharStr, v8 + 1) )
        goto LABEL_24;
      v17 = GetLastError();
      v11 = v17;
      if ( v17 > 0 )
        v11 = (unsigned __int16)v17 | 0x80070000;
      if ( v11 >= 0 )
      {
LABEL_24:
        *a4 = v15;
        v15[v8] = 0;
        return 0;
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
            59,
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
          58,
          (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
          v16,
          (__int64)"WCHAR[]");
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
      57,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      v12,
      (__int64)"MultiByteToWideChar failed!",
      v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800144a4  push    rbx
0x1800144a6  push    rbp
0x1800144a7  push    rsi
0x1800144a8  push    rdi
0x1800144a9  push    r14
0x1800144ab  push    r15
0x1800144ad  sub     rsp, 38h
0x1800144b1  mov     r15, r9
0x1800144b4  mov     [rsp+68h+cchWideChar], 0; cchWideChar
0x1800144bc  mov     r9d, r8d; cbMultiByte
0x1800144bf  mov     [rsp+68h+lpWideCharStr], 0; lpWideCharStr
0x1800144c8  mov     ebp, r8d
0x1800144cb  mov     r14, rdx
0x1800144ce  mov     r8, rdx; lpMultiByteStr
0x1800144d1  mov     ecx, 0FDE9h; CodePage
0x1800144d6  xor     edx, edx; dwFlags
0x1800144d8  call    cs:__imp_MultiByteToWideChar
0x1800144de  movsxd  rsi, eax
0x1800144e1  test    eax, eax
0x1800144e3  jnz     short loc_180014562
0x1800144e5  call    cs:__imp_GetLastError
0x1800144eb  mov     ebx, eax
0x1800144ed  test    eax, eax
0x1800144ef  jle     short loc_1800144FA
0x1800144f1  movzx   ebx, ax
0x1800144f4  or      ebx, 80070000h
0x1800144fa  test    ebx, ebx
0x1800144fc  jns     short loc_180014562
0x1800144fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180014505  lea     rax, WPP_GLOBAL_Control
0x18001450c  cmp     rcx, rax
0x18001450f  jz      loc_180014683
0x180014515  test    byte ptr [rcx+1Ch], 8
0x180014519  jz      loc_180014683
0x18001451f  cmp     byte ptr [rcx+19h], 2
0x180014523  jb      loc_180014683
0x180014529  call    RdpX_GetActivityIdPrefix
0x18001452e  lea     rcx, aMultibytetowid; "MultiByteToWideChar failed!"
0x180014535  mov     [rsp+68h+cchWideChar], ebx
0x180014539  mov     [rsp+68h+lpWideCharStr], rcx
0x18001453e  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180014545  mov     rcx, cs:WPP_GLOBAL_Control
0x18001454c  mov     edx, 39h ; '9'
0x180014551  mov     r9d, eax
0x180014554  mov     rcx, [rcx+10h]
0x180014558  call    WPP_SF_DsD
0x18001455d  jmp     loc_180014683
0x180014562  lea     ebx, [rsi+1]
0x180014565  mov     eax, 2
0x18001456a  movsxd  rcx, ebx
0x18001456d  mul     rcx
0x180014570  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180014577  cmovb   rax, rcx
0x18001457b  mov     rcx, rax; Size
0x18001457e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014583  mov     rdi, rax
0x180014586  test    rax, rax
0x180014589  jnz     short loc_1800145E2
0x18001458b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014592  lea     rax, WPP_GLOBAL_Control
0x180014599  cmp     rcx, rax
0x18001459c  jz      short loc_1800145D8
0x18001459e  test    byte ptr [rcx+1Ch], 8
0x1800145a2  jz      short loc_1800145D8
0x1800145a4  cmp     byte ptr [rcx+19h], 2
0x1800145a8  jb      short loc_1800145D8
0x1800145aa  call    RdpX_GetActivityIdPrefix
0x1800145af  lea     rcx, aWchar; "WCHAR[]"
0x1800145b6  mov     r9d, eax
0x1800145b9  mov     [rsp+68h+lpWideCharStr], rcx
0x1800145be  lea     edx, [rdi+3Ah]
0x1800145c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145c8  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x1800145cf  mov     rcx, [rcx+10h]
0x1800145d3  call    WPP_SF_Ds
0x1800145d8  mov     ebx, 8007000Eh
0x1800145dd  jmp     loc_180014683
0x1800145e2  mov     [rsp+68h+cchWideChar], ebx; cchWideChar
0x1800145e6  mov     r9d, ebp; cbMultiByte
0x1800145e9  mov     r8, r14; lpMultiByteStr
0x1800145ec  mov     [rsp+68h+lpWideCharStr], rdi; lpWideCharStr
0x1800145f1  xor     edx, edx; dwFlags
0x1800145f3  mov     ecx, 0FDE9h; CodePage
0x1800145f8  call    cs:__imp_MultiByteToWideChar
0x1800145fe  test    eax, eax
0x180014600  jnz     short loc_180014678
0x180014602  call    cs:__imp_GetLastError
0x180014608  mov     ebx, eax
0x18001460a  test    eax, eax
0x18001460c  jle     short loc_180014617
0x18001460e  movzx   ebx, ax
0x180014611  or      ebx, 80070000h
0x180014617  test    ebx, ebx
0x180014619  jns     short loc_180014678
0x18001461b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014622  lea     rax, WPP_GLOBAL_Control
0x180014629  cmp     rcx, rax
0x18001462c  jz      short loc_18001466E
0x18001462e  test    byte ptr [rcx+1Ch], 8
0x180014632  jz      short loc_18001466E
0x180014634  cmp     byte ptr [rcx+19h], 2
0x180014638  jb      short loc_18001466E
0x18001463a  call    RdpX_GetActivityIdPrefix
0x18001463f  lea     rcx, aWidechartomult; "WideCharToMultiByte failed!"
0x180014646  mov     [rsp+68h+cchWideChar], ebx
0x18001464a  mov     [rsp+68h+lpWideCharStr], rcx
0x18001464f  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180014656  mov     rcx, cs:WPP_GLOBAL_Control
0x18001465d  mov     edx, 3Bh ; ';'
0x180014662  mov     r9d, eax
0x180014665  mov     rcx, [rcx+10h]
0x180014669  call    WPP_SF_DsD
0x18001466e  mov     rcx, rdi; Block
0x180014671  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014676  jmp     short loc_180014683
0x180014678  xor     eax, eax
0x18001467a  mov     [r15], rdi
0x18001467d  mov     [rdi+rsi*2], ax
0x180014681  xor     ebx, ebx
0x180014683  mov     eax, ebx
0x180014685  add     rsp, 38h
0x180014689  pop     r15
0x18001468b  pop     r14
0x18001468d  pop     rdi
0x18001468e  pop     rsi
0x18001468f  pop     rbp
0x180014690  pop     rbx
0x180014691  retn
```
