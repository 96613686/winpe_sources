# WppTraceIndent(char * *,_WppTraceIndentType)

- ea: `0x180011fd8`
- end: `0x180012141`
- name: `?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `142`
- callee_count: `2`
- tags: ``

## callers

- `0x18000eae8`
- `0x180012b24`
- `0x180012d08`
- `0x1800134fc`
- `0x1800135dc`
- `0x180013e10`
- `0x180014070`
- `0x18001423c`
- `0x1800146c4`
- `0x180014858`
- `0x180014ecc`
- `0x180015728`
- `0x18001594c`
- `0x180015a5c`
- `0x180016624`
- `0x180016adc`
- `0x180017b24`
- `0x180017f6c`
- `0x1800182fc`
- `0x1800183ec`
- `0x180018774`
- `0x180018968`
- `0x180018dc0`
- `0x180018f28`
- `0x180019220`
- `0x180019514`
- `0x180019868`
- `0x1800199b0`
- `0x180019ca0`
- `0x180019eb8`
- `0x18001a59c`
- `0x18001abb4`
- `0x18001ae5c`
- `0x18001b0c4`
- `0x18001b2b4`
- `0x18001b440`
- `0x18001b6f8`
- `0x18001bdf8`
- `0x18001c0b0`
- `0x18001c1e8`
- `0x18001c818`
- `0x18001d030`
- `0x18001d4e0`
- `0x18001dbc8`
- `0x18001e590`
- `0x18001e92c`
- `0x18001ee70`
- `0x18001f2f0`
- `0x18001f61c`
- `0x18001fea4`

## callees

- `0x180011354`
- `0x180011fd8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011fe4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011fe4`

## pseudocode

```c
char *__fastcall WppTraceIndent(__int64 a1, unsigned int a2)
{
  DWORD CurrentThreadId; // eax
  unsigned __int64 i; // rdx
  __int64 v5; // rcx
  unsigned int v6; // r8d
  bool v7; // zf
  int v8; // ebx
  int v9; // edi
  unsigned __int64 v10; // rdx
  const char *v11; // r8
  char *result; // rax

  CurrentThreadId = GetCurrentThreadId();
  v5 = (int)`WppTraceIndent'::`2'::idxCurrentThread;
  if ( (_DWORD)`WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v5 = 0;
    `WppTraceIndent'::`2'::ThreadTable[0] = CurrentThreadId;
    LODWORD(`WppTraceIndent'::`2'::idxCurrentThread) = 0;
    dword_18004C0B4 = 0;
  }
  else
  {
    if ( (_DWORD)`WppTraceIndent'::`2'::idxCurrentThread == -2
      || `WppTraceIndent'::`2'::ThreadTable[2 * (int)`WppTraceIndent'::`2'::idxCurrentThread] != CurrentThreadId )
    {
      v6 = -1;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v7 = (_DWORD)i == 32;
        if ( (unsigned int)i >= 0x20 )
          break;
        if ( `WppTraceIndent'::`2'::ThreadTable[2 * (int)i] == CurrentThreadId )
        {
          v5 = (unsigned int)i;
          LODWORD(`WppTraceIndent'::`2'::idxCurrentThread) = i;
          v7 = (_DWORD)i == 32;
          break;
        }
        if ( v6 == -1 && !`WppTraceIndent'::`2'::ThreadTable[2 * (int)i] )
          v6 = i;
      }
      if ( v7 )
      {
        if ( v6 == -1 )
        {
          v5 = 4294967294LL;
        }
        else
        {
          v5 = v6;
          `WppTraceIndent'::`2'::ThreadTable[2 * v6] = CurrentThreadId;
          `WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1] = 0;
        }
        LODWORD(`WppTraceIndent'::`2'::idxCurrentThread) = v5;
      }
    }
    if ( (int)v5 < 0 )
    {
      v8 = 0;
      goto LABEL_24;
    }
  }
  if ( !a2 )
    ++`WppTraceIndent'::`2'::ThreadTable[2 * (int)v5 + 1];
  v8 = `WppTraceIndent'::`2'::ThreadTable[2 * (int)v5 + 1];
LABEL_24:
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v9 = 1;
    if ( v8 >= 1 )
    {
      do
      {
        if ( StringCbCatA((char *)v5, i, "..") )
          break;
        ++v9;
      }
      while ( v9 <= v8 );
      v5 = (unsigned int)`WppTraceIndent'::`2'::idxCurrentThread;
    }
  }
  v10 = a2;
  if ( !a2 )
  {
    v11 = ">";
    goto LABEL_36;
  }
  v10 = a2 - 1;
  if ( a2 == 1 )
  {
    v11 = "<";
    goto LABEL_36;
  }
  if ( a2 == 2 )
  {
    v11 = " ";
LABEL_36:
    StringCbCatA((char *)v5, v10, v11);
    LODWORD(v5) = (_DWORD)`WppTraceIndent'::`2'::idxCurrentThread;
  }
  if ( (int)v5 >= 0 && a2 == 1 )
  {
    v7 = `WppTraceIndent'::`2'::ThreadTable[2 * (int)v5 + 1]-- == 1;
    if ( v7 )
      `WppTraceIndent'::`2'::ThreadTable[2 * (int)v5] = 0;
  }
  result = &`WppTraceIndent'::`2'::szIndentPrefix;
  WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  return result;
}

```

## disassembly

```asm
0x180011fd8  push    rbx
0x180011fda  push    rsi
0x180011fdb  push    rdi
0x180011fdc  push    r14
0x180011fde  sub     rsp, 28h
0x180011fe2  mov     esi, edx
0x180011fe4  call    cs:__imp_GetCurrentThreadId
0x180011fea  movsxd  rcx, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180011ff1  lea     r14, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180011ff8  mov     r9d, eax
0x180011ffb  cmp     ecx, 0FFFFFFFFh
0x180011ffe  jnz     short loc_180012016
0x180012000  xor     ecx, ecx
0x180012002  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, eax; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180012008  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ecx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18001200e  mov     cs:dword_18004C0B4, ecx
0x180012014  jmp     short loc_18001207F
0x180012016  cmp     ecx, 0FFFFFFFEh
0x180012019  jz      short loc_180012021
0x18001201b  cmp     [r14+rcx*8], r9d
0x18001201f  jz      short loc_18001207B
0x180012021  or      r8d, 0FFFFFFFFh
0x180012025  xor     edx, edx; unsigned __int64
0x180012027  cmp     edx, 20h ; ' '
0x18001202a  jnb     short loc_180012053
0x18001202c  movsxd  rax, edx
0x18001202f  cmp     [r14+rax*8], r9d
0x180012033  jz      short loc_180012048
0x180012035  cmp     r8d, 0FFFFFFFFh
0x180012039  jnz     short loc_180012044
0x18001203b  cmp     dword ptr [r14+rax*8], 0
0x180012040  cmovz   r8d, edx
0x180012044  inc     edx
0x180012046  jmp     short loc_180012027
0x180012048  mov     ecx, edx
0x18001204a  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, edx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180012050  cmp     edx, 20h ; ' '
0x180012053  jnz     short loc_18001207B
0x180012055  cmp     r8d, 0FFFFFFFFh
0x180012059  jz      short loc_180012070
0x18001205b  movsxd  rax, r8d
0x18001205e  mov     ecx, r8d
0x180012061  mov     [r14+rax*8], r9d
0x180012065  mov     dword ptr [r14+rax*8+4], 0
0x18001206e  jmp     short loc_180012075
0x180012070  mov     ecx, 0FFFFFFFEh; char *
0x180012075  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ecx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18001207b  test    ecx, ecx
0x18001207d  js      short loc_180012099
0x18001207f  movsxd  rax, ecx
0x180012082  test    esi, esi
0x180012084  jnz     short loc_180012092
0x180012086  inc     dword ptr [r14+rax*8+4]
0x18001208b  mov     ebx, [r14+rax*8+4]
0x180012090  jmp     short loc_18001209B
0x180012092  mov     ebx, [r14+rax*8+4]
0x180012097  jmp     short loc_18001209B
0x180012099  xor     ebx, ebx
0x18001209b  mov     rax, cs:WPP_GLOBAL_Control
0x1800120a2  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x1800120a9  test    byte ptr [rax+1Ch], 2
0x1800120ad  jz      short loc_1800120DA
0x1800120af  cmp     byte ptr [rax+19h], 5
0x1800120b3  jb      short loc_1800120DA
0x1800120b5  mov     edi, 1
0x1800120ba  cmp     ebx, edi
0x1800120bc  jl      short loc_1800120DA
0x1800120be  lea     r8, pszSrc; ".."
0x1800120c5  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x1800120ca  test    eax, eax
0x1800120cc  jnz     short loc_1800120D4
0x1800120ce  inc     edi
0x1800120d0  cmp     edi, ebx
0x1800120d2  jle     short loc_1800120BE
0x1800120d4  mov     ecx, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; char *
0x1800120da  mov     edx, esi; unsigned __int64
0x1800120dc  test    esi, esi
0x1800120de  jz      short loc_1800120FC
0x1800120e0  sub     edx, 1
0x1800120e3  jz      short loc_1800120F3
0x1800120e5  cmp     edx, 1
0x1800120e8  jnz     short loc_18001210E
0x1800120ea  lea     r8, asc_180043464; " "
0x1800120f1  jmp     short loc_180012103
0x1800120f3  lea     r8, asc_180043468; "<"
0x1800120fa  jmp     short loc_180012103
0x1800120fc  lea     r8, asc_180043460; ">"
0x180012103  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x180012108  mov     ecx, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18001210e  test    ecx, ecx
0x180012110  js      short loc_180012129
0x180012112  cmp     esi, 1
0x180012115  jnz     short loc_180012129
0x180012117  movsxd  rdx, ecx
0x18001211a  sub     [r14+rdx*8+4], esi
0x18001211f  jnz     short loc_180012129
0x180012121  mov     dword ptr [r14+rdx*8], 0
0x180012129  lea     rax, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180012130  mov     cs:?WPP_pszIndent@@3PEADEA, rax; char * WPP_pszIndent
0x180012137  add     rsp, 28h
0x18001213b  pop     r14
0x18001213d  pop     rdi
0x18001213e  pop     rsi
0x18001213f  pop     rbx
0x180012140  retn
```
