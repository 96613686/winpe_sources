# WppTraceIndent(char * *,_WppTraceIndentType)

- ea: `0x18000bc48`
- end: `0x18000bdb7`
- name: `?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z`
- size: `367`
- prototype: `char *__fastcall(__int64, unsigned int)`
- caller_count: `385`
- callee_count: `2`
- tags: ``

## callers

- `0x180006038`
- `0x1800069e4`
- `0x180006a54`
- `0x180006ae8`
- `0x180006b58`
- `0x180006c74`
- `0x180006d50`
- `0x180006dc0`
- `0x180006ed8`
- `0x180006f48`
- `0x180007064`
- `0x180007100`
- `0x180007170`
- `0x18000720c`
- `0x18000727c`
- `0x1800072ec`
- `0x18000735c`
- `0x1800073cc`
- `0x180007468`
- `0x1800074d8`
- `0x180007548`
- `0x1800075b8`
- `0x180007628`
- `0x18000778c`
- `0x1800077fc`
- `0x18000786c`
- `0x1800078dc`
- `0x180007a78`
- `0x180007bcc`
- `0x1800081c0`
- `0x180008324`
- `0x1800085b8`
- `0x180008d28`
- `0x180009154`
- `0x1800093c8`
- `0x180009834`
- `0x180009d24`
- `0x180009ea4`
- `0x18000a1b8`
- `0x18000a46c`
- `0x18000a81c`
- `0x18000acb4`
- `0x18000b85c`
- `0x18000c338`
- `0x18000c394`
- `0x18000c404`
- `0x18000de0c`
- `0x18000de68`
- `0x18000ded8`
- `0x18000df48`

## callees

- `0x18000bba4`
- `0x18000bc48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bc5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bc5c`

## pseudocode

```c
char *__fastcall WppTraceIndent(__int64 a1, unsigned int a2)
{
  DWORD CurrentThreadId; // eax
  unsigned __int64 v4; // rdx
  char *i; // rcx
  int v6; // ebx
  bool v7; // zf
  int v8; // edi
  int j; // esi
  unsigned __int64 v10; // rcx
  const char *v11; // r8
  char *result; // rax

  CurrentThreadId = GetCurrentThreadId();
  v6 = `WppTraceIndent'::`2'::idxCurrentThread;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v6 = 0;
    `WppTraceIndent'::`2'::ThreadTable[0] = CurrentThreadId;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    dword_180048934 = 0;
  }
  else
  {
    if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
      || `WppTraceIndent'::`2'::ThreadTable[2 * `WppTraceIndent'::`2'::idxCurrentThread] != CurrentThreadId )
    {
      v4 = 0xFFFFFFFFLL;
      for ( i = 0; ; i = (char *)(unsigned int)((_DWORD)i + 1) )
      {
        v7 = (_DWORD)i == 32;
        if ( (unsigned int)i >= 0x20 )
          break;
        if ( `WppTraceIndent'::`2'::ThreadTable[2 * (int)i] == CurrentThreadId )
        {
          v6 = (int)i;
          `WppTraceIndent'::`2'::idxCurrentThread = (int)i;
          v7 = (_DWORD)i == 32;
          break;
        }
        if ( (_DWORD)v4 == -1 && !`WppTraceIndent'::`2'::ThreadTable[2 * (int)i] )
          v4 = (unsigned int)i;
      }
      if ( v7 )
      {
        if ( (_DWORD)v4 == -1 )
        {
          v6 = -2;
          `WppTraceIndent'::`2'::idxCurrentThread = -2;
        }
        else
        {
          v6 = v4;
          `WppTraceIndent'::`2'::idxCurrentThread = v4;
          `WppTraceIndent'::`2'::ThreadTable[2 * (int)v4] = CurrentThreadId;
          `WppTraceIndent'::`2'::ThreadTable[2 * (int)v4 + 1] = 0;
        }
      }
    }
    if ( v6 < 0 )
    {
      v8 = 0;
      goto LABEL_23;
    }
  }
  if ( !a2 )
    ++`WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1];
  v8 = `WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1];
LABEL_23:
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    for ( j = 1; j <= v8; ++j )
    {
      if ( (unsigned int)StringCbCatA(i, v4, "..") )
        break;
    }
  }
  v10 = a2;
  if ( !a2 )
  {
    v11 = ">";
    goto LABEL_34;
  }
  v10 = a2 - 1;
  if ( a2 == 1 )
  {
    v11 = "<";
    goto LABEL_34;
  }
  if ( a2 == 2 )
  {
    v11 = " ";
LABEL_34:
    StringCbCatA((char *)v10, v4, v11);
  }
  if ( v6 >= 0 && a2 == 1 )
  {
    v7 = `WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1]-- == 1;
    if ( v7 )
      `WppTraceIndent'::`2'::ThreadTable[2 * v6] = 0;
  }
  result = &`WppTraceIndent'::`2'::szIndentPrefix;
  WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  return result;
}

```

## disassembly

```asm
0x18000bc48  mov     [rsp+arg_8], rbx
0x18000bc4d  mov     [rsp+arg_10], rbp
0x18000bc52  push    rsi
0x18000bc53  push    rdi
0x18000bc54  push    r14
0x18000bc56  sub     rsp, 20h
0x18000bc5a  mov     ebp, edx
0x18000bc5c  call    cs:__imp_GetCurrentThreadId
0x18000bc62  movsxd  rbx, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000bc69  lea     r14, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x18000bc70  mov     r8d, eax
0x18000bc73  cmp     ebx, 0FFFFFFFFh
0x18000bc76  jnz     short loc_18000BC8E
0x18000bc78  xor     ebx, ebx
0x18000bc7a  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, eax; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x18000bc80  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ebx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000bc86  mov     cs:dword_180048934, ebx
0x18000bc8c  jmp     short loc_18000BCF8
0x18000bc8e  cmp     ebx, 0FFFFFFFEh
0x18000bc91  jz      short loc_18000BC99
0x18000bc93  cmp     [r14+rbx*8], r8d
0x18000bc97  jz      short loc_18000BCF4
0x18000bc99  or      edx, 0FFFFFFFFh; unsigned __int64
0x18000bc9c  xor     ecx, ecx; char *
0x18000bc9e  cmp     ecx, 20h ; ' '
0x18000bca1  jnb     short loc_18000BCC8
0x18000bca3  movsxd  rax, ecx
0x18000bca6  cmp     [r14+rax*8], r8d
0x18000bcaa  jz      short loc_18000BCBD
0x18000bcac  cmp     edx, 0FFFFFFFFh
0x18000bcaf  jnz     short loc_18000BCB9
0x18000bcb1  cmp     dword ptr [r14+rax*8], 0
0x18000bcb6  cmovz   edx, ecx
0x18000bcb9  inc     ecx
0x18000bcbb  jmp     short loc_18000BC9E
0x18000bcbd  mov     ebx, ecx
0x18000bcbf  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ecx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000bcc5  cmp     ecx, 20h ; ' '
0x18000bcc8  jnz     short loc_18000BCF4
0x18000bcca  cmp     edx, 0FFFFFFFFh
0x18000bccd  jz      short loc_18000BCE9
0x18000bccf  movsxd  rax, edx
0x18000bcd2  mov     ebx, edx
0x18000bcd4  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, edx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000bcda  mov     [r14+rax*8], r8d
0x18000bcde  mov     dword ptr [r14+rax*8+4], 0
0x18000bce7  jmp     short loc_18000BCF4
0x18000bce9  mov     ebx, 0FFFFFFFEh
0x18000bcee  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ebx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000bcf4  test    ebx, ebx
0x18000bcf6  js      short loc_18000BD12
0x18000bcf8  movsxd  rax, ebx
0x18000bcfb  test    ebp, ebp
0x18000bcfd  jnz     short loc_18000BD0B
0x18000bcff  inc     dword ptr [r14+rax*8+4]
0x18000bd04  mov     edi, [r14+rax*8+4]
0x18000bd09  jmp     short loc_18000BD14
0x18000bd0b  mov     edi, [r14+rax*8+4]
0x18000bd10  jmp     short loc_18000BD14
0x18000bd12  xor     edi, edi
0x18000bd14  mov     rax, cs:WPP_GLOBAL_Control
0x18000bd1b  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18000bd22  test    byte ptr [rax+1Ch], 2
0x18000bd26  jz      short loc_18000BD4D
0x18000bd28  cmp     byte ptr [rax+19h], 5
0x18000bd2c  jb      short loc_18000BD4D
0x18000bd2e  mov     esi, 1
0x18000bd33  cmp     edi, esi
0x18000bd35  jl      short loc_18000BD4D
0x18000bd37  lea     r8, asc_18003AC98; ".."
0x18000bd3e  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x18000bd43  test    eax, eax
0x18000bd45  jnz     short loc_18000BD4D
0x18000bd47  inc     esi
0x18000bd49  cmp     esi, edi
0x18000bd4b  jle     short loc_18000BD37
0x18000bd4d  mov     ecx, ebp; char *
0x18000bd4f  test    ebp, ebp
0x18000bd51  jz      short loc_18000BD6F
0x18000bd53  sub     ecx, 1
0x18000bd56  jz      short loc_18000BD66
0x18000bd58  cmp     ecx, 1
0x18000bd5b  jnz     short loc_18000BD7B
0x18000bd5d  lea     r8, asc_18003ACA0; " "
0x18000bd64  jmp     short loc_18000BD76
0x18000bd66  lea     r8, asc_18003ACA4; "<"
0x18000bd6d  jmp     short loc_18000BD76
0x18000bd6f  lea     r8, asc_18003AC9C; ">"
0x18000bd76  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x18000bd7b  test    ebx, ebx
0x18000bd7d  js      short loc_18000BD96
0x18000bd7f  cmp     ebp, 1
0x18000bd82  jnz     short loc_18000BD96
0x18000bd84  movsxd  rcx, ebx
0x18000bd87  sub     [r14+rcx*8+4], ebp
0x18000bd8c  jnz     short loc_18000BD96
0x18000bd8e  mov     dword ptr [r14+rcx*8], 0
0x18000bd96  mov     rbx, [rsp+38h+arg_8]
0x18000bd9b  lea     rax, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18000bda2  mov     rbp, [rsp+38h+arg_10]
0x18000bda7  mov     cs:?WPP_pszIndent@@3PEADEA, rax; char * WPP_pszIndent
0x18000bdae  add     rsp, 20h
0x18000bdb2  pop     r14
0x18000bdb4  pop     rdi
0x18000bdb5  pop     rsi
0x18000bdb6  retn
```
