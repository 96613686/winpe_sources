# BaseHttpListener::InitListening(char const *,ulong,int,int,int,int)

- ea: `0x180014f18`
- end: `0x1800151f4`
- name: `?InitListening@BaseHttpListener@@QEAAJPEBDKHHHH@Z`
- size: `732`
- prototype: `int(BaseHttpListener *__hidden this, const char *, unsigned int, int, int, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180014580`

## callees

- `0x180014f18`
- `0x180024000`
- `0x18003222c`
- `0x180032ab0`
- `0x18003c018`
- `0x18005503c`
- `0x18005516c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015023`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001508b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015100`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015023`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001508b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015100`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015157`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015199`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015157`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015199`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014f71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014f71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800151d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800151d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800150b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800150b4`

## pseudocode

```c
__int64 __fastcall BaseHttpListener::InitListening(BaseHttpListener *this, const char *a2, int a3)
{
  CSimpleLock *v5; // rcx
  unsigned int v6; // ebx
  STRSAFE_PCNZWCH v7; // rcx
  __int64 v8; // rdx
  LKRhash::CLKRHashTable *v9; // rax
  const char *v10; // rdx
  unsigned __int64 (*v11)(const void *); // r8
  unsigned int (*v12)(unsigned __int64); // r9
  LKRhash::CLKRHashTable *v13; // rbx
  _DWORD *v14; // rax
  _DWORD *v15; // rbx
  CMultipleIPThrottleByTime *v16; // rax
  unsigned int v17; // edx
  unsigned int v18; // r8d
  unsigned int v19; // r9d
  HANDLE EventW; // rax
  HANDLE v21; // rax
  bool (*v23)(unsigned __int64, unsigned __int64); // [rsp+20h] [rbp-58h]
  void (*v24)(const void *, int); // [rsp+28h] [rbp-50h]
  unsigned int v25; // [rsp+38h] [rbp-40h]
  unsigned int v26; // [rsp+40h] [rbp-38h]
  bool v27; // [rsp+48h] [rbp-30h]

  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, a3, (unsigned int)"/", a3, 0);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  *((_DWORD *)this + 40) = a3;
  *(_QWORD *)((char *)this + 132) = 0;
  *((_DWORD *)this + 35) = 1;
  *((_DWORD *)this + 36) = 1;
  DupStr((char **)this + 19, "/");
  if ( *((_QWORD *)this + 19) )
  {
    CSimpleLock::Enter(v5);
    if ( ++dword_1800761F4 == 1 )
      byte_1800761F0 = 1;
    _InterlockedExchange(&g_lckLkrInit, 0);
    v9 = (LKRhash::CLKRHashTable *)malloc(0x48u);
    v13 = v9;
    if ( v9 )
      LKRhash::CLKRHashTable::CLKRHashTable(v9, v10, v11, v12, v23, v24, 4.0, v25, v26, v27);
    else
      v13 = 0;
    *((_QWORD *)this + 21) = v13;
    if ( v13 )
    {
      v14 = malloc(0x14u);
      v15 = v14;
      if ( v14 )
      {
        v14[2] = 80;
        v14[4] = 10000;
        v14[3] = 80;
        *v14 = GetTickCount();
      }
      else
      {
        v15 = 0;
      }
      *((_QWORD *)this + 33) = v15;
      if ( v15 )
      {
        v16 = (CMultipleIPThrottleByTime *)malloc(0x50u);
        if ( v16 )
          v16 = CMultipleIPThrottleByTime::CMultipleIPThrottleByTime(v16, v17, v18, v19);
        *((_QWORD *)this + 34) = v16;
        if ( v16 )
        {
          EventW = CreateEventW(0, 1, 1, 0);
          *((_QWORD *)this + 36) = EventW;
          if ( EventW )
          {
            v21 = CreateEventW(0, 1, 0, 0);
            *((_QWORD *)this + 39) = v21;
            if ( v21 )
            {
              v6 = 0;
              *((_DWORD *)this + 26) = 1;
              goto LABEL_40;
            }
            v6 = -2147024882;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v8 = 65;
              goto LABEL_8;
            }
          }
          else
          {
            v6 = -2147024882;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v8 = 64;
              goto LABEL_8;
            }
          }
        }
        else
        {
          v6 = -2147024882;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v8 = 63;
            goto LABEL_8;
          }
        }
      }
      else
      {
        v6 = -2147024882;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v8 = 62;
          goto LABEL_8;
        }
      }
    }
    else
    {
      v6 = -2147024882;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v8 = 61;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v6 = -2147024882;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v8 = 59;
LABEL_8:
      WPP_SF_(*((_QWORD *)v7 + 2), v8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
    }
  }
LABEL_40:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  return v6;
}

```

## disassembly

```asm
0x180014f18  push    rbx
0x180014f1a  push    rsi
0x180014f1b  push    rdi
0x180014f1c  push    r14
0x180014f1e  push    r15
0x180014f20  sub     rsp, 50h
0x180014f24  mov     ebx, r8d
0x180014f27  mov     rdi, rcx
0x180014f2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f31  lea     r15, WPP_GLOBAL_Control
0x180014f38  cmp     rcx, r15
0x180014f3b  jz      short loc_180014F67
0x180014f3d  test    dword ptr [rcx+1Ch], 100h
0x180014f44  jz      short loc_180014F67
0x180014f46  mov     rcx, [rcx+10h]
0x180014f4a  lea     r9, asc_1800646C4; "/"
0x180014f51  mov     edx, 3Ah ; ':'
0x180014f56  mov     dword ptr [rsp+78h+var_50], 0; void (*)(const void *, int)
0x180014f5e  mov     dword ptr [rsp+78h+var_58], ebx; bool (*)(unsigned __int64, unsigned __int64)
0x180014f62  call    WPP_SF_sdd
0x180014f67  lea     rsi, [rdi+0B8h]
0x180014f6e  mov     rcx, rsi; lpCriticalSection
0x180014f71  call    cs:__imp_EnterCriticalSection
0x180014f78  nop     dword ptr [rax+rax+00h]
0x180014f7d  mov     [rdi+0A0h], ebx
0x180014f83  lea     rdx, asc_1800646C4; "/"
0x180014f8a  mov     r14d, 1
0x180014f90  mov     qword ptr [rdi+84h], 0
0x180014f9b  lea     rbx, [rdi+98h]
0x180014fa2  mov     [rdi+8Ch], r14d
0x180014fa9  mov     rcx, rbx; char **
0x180014fac  mov     [rdi+90h], r14d
0x180014fb3  call    ?DupStr@@YAXPEAPEADPEBD@Z; DupStr(char * *,char const *)
0x180014fb8  cmp     qword ptr [rbx], 0
0x180014fbc  jnz     short loc_180014FF6
0x180014fbe  mov     ebx, 8007000Eh
0x180014fc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fca  cmp     rcx, r15
0x180014fcd  jz      loc_1800151D6
0x180014fd3  test    [rcx+1Ch], r14b
0x180014fd7  jz      loc_1800151D6
0x180014fdd  lea     edx, [r14+3Ah]
0x180014fe1  mov     rcx, [rcx+10h]
0x180014fe5  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180014fec  call    WPP_SF_
0x180014ff1  jmp     loc_1800151D6
0x180014ff6  call    ?Enter@CSimpleLock@@QEAAXXZ; CSimpleLock::Enter(void)
0x180014ffb  mov     eax, cs:dword_1800761F4
0x180015001  add     eax, r14d
0x180015004  mov     cs:dword_1800761F4, eax
0x18001500a  cmp     eax, r14d
0x18001500d  jnz     short loc_180015016
0x18001500f  mov     cs:byte_1800761F0, r14b
0x180015016  xor     eax, eax
0x180015018  mov     ecx, 48h ; 'H'; Size
0x18001501d  xchg    eax, cs:?g_lckLkrInit@@3VCSimpleLock@@A; CSimpleLock g_lckLkrInit
0x180015023  call    cs:__imp_malloc
0x18001502a  nop     dword ptr [rax+rax+00h]
0x18001502f  mov     rbx, rax
0x180015032  test    rax, rax
0x180015035  jz      short loc_18001504F
0x180015037  movsd   xmm0, cs:__real@4010000000000000
0x18001503f  mov     rcx, rax; this
0x180015042  movsd   [rsp+78h+var_48], xmm0; double
0x180015048  call    ??0CLKRHashTable@LKRhash@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; LKRhash::CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x18001504d  jmp     short loc_180015051
0x18001504f  xor     ebx, ebx
0x180015051  mov     [rdi+0A8h], rbx
0x180015058  test    rbx, rbx
0x18001505b  jnz     short loc_180015086
0x18001505d  mov     ebx, 8007000Eh
0x180015062  mov     rcx, cs:WPP_GLOBAL_Control
0x180015069  cmp     rcx, r15
0x18001506c  jz      loc_1800151D6
0x180015072  test    [rcx+1Ch], r14b
0x180015076  jz      loc_1800151D6
0x18001507c  mov     edx, 3Dh ; '='
0x180015081  jmp     loc_180014FE1
0x180015086  mov     ecx, 14h; Size
0x18001508b  call    cs:__imp_malloc
0x180015092  nop     dword ptr [rax+rax+00h]
0x180015097  mov     rbx, rax
0x18001509a  test    rax, rax
0x18001509d  jz      short loc_1800150C4
0x18001509f  mov     dword ptr [rax+8], 50h ; 'P'
0x1800150a6  mov     dword ptr [rax+10h], 2710h
0x1800150ad  mov     dword ptr [rax+0Ch], 50h ; 'P'
0x1800150b4  call    cs:__imp_GetTickCount
0x1800150bb  nop     dword ptr [rax+rax+00h]
0x1800150c0  mov     [rbx], eax
0x1800150c2  jmp     short loc_1800150C6
0x1800150c4  xor     ebx, ebx
0x1800150c6  mov     [rdi+108h], rbx
0x1800150cd  test    rbx, rbx
0x1800150d0  jnz     short loc_1800150FB
0x1800150d2  mov     ebx, 8007000Eh
0x1800150d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150de  cmp     rcx, r15
0x1800150e1  jz      loc_1800151D6
0x1800150e7  test    [rcx+1Ch], r14b
0x1800150eb  jz      loc_1800151D6
0x1800150f1  mov     edx, 3Eh ; '>'
0x1800150f6  jmp     loc_180014FE1
0x1800150fb  mov     ecx, 50h ; 'P'; Size
0x180015100  call    cs:__imp_malloc
0x180015107  nop     dword ptr [rax+rax+00h]
0x18001510c  test    rax, rax
0x18001510f  jz      short loc_180015119
0x180015111  mov     rcx, rax; this
0x180015114  call    ??0CMultipleIPThrottleByTime@@QEAA@KKK@Z; CMultipleIPThrottleByTime::CMultipleIPThrottleByTime(ulong,ulong,ulong)
0x180015119  mov     [rdi+110h], rax
0x180015120  test    rax, rax
0x180015123  jnz     short loc_18001514C
0x180015125  mov     ebx, 8007000Eh
0x18001512a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015131  cmp     rcx, r15
0x180015134  jz      loc_1800151D6
0x18001513a  test    [rcx+1Ch], r14b
0x18001513e  jz      loc_1800151D6
0x180015144  lea     edx, [rax+3Fh]
0x180015147  jmp     loc_180014FE1
0x18001514c  xor     r9d, r9d; lpName
0x18001514f  mov     r8d, r14d; bInitialState
0x180015152  mov     edx, r14d; bManualReset
0x180015155  xor     ecx, ecx; lpEventAttributes
0x180015157  call    cs:__imp_CreateEventW
0x18001515e  nop     dword ptr [rax+rax+00h]
0x180015163  mov     [rdi+120h], rax
0x18001516a  test    rax, rax
0x18001516d  jnz     short loc_18001518E
0x18001516f  mov     ebx, 8007000Eh
0x180015174  mov     rcx, cs:WPP_GLOBAL_Control
0x18001517b  cmp     rcx, r15
0x18001517e  jz      short loc_1800151D6
0x180015180  test    [rcx+1Ch], r14b
0x180015184  jz      short loc_1800151D6
0x180015186  lea     edx, [rax+40h]
0x180015189  jmp     loc_180014FE1
0x18001518e  xor     r9d, r9d; lpName
0x180015191  xor     r8d, r8d; bInitialState
0x180015194  mov     edx, r14d; bManualReset
0x180015197  xor     ecx, ecx; lpEventAttributes
0x180015199  call    cs:__imp_CreateEventW
0x1800151a0  nop     dword ptr [rax+rax+00h]
0x1800151a5  mov     [rdi+138h], rax
0x1800151ac  test    rax, rax
0x1800151af  jnz     short loc_1800151D0
0x1800151b1  mov     ebx, 8007000Eh
0x1800151b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151bd  cmp     rcx, r15
0x1800151c0  jz      short loc_1800151D6
0x1800151c2  test    [rcx+1Ch], r14b
0x1800151c6  jz      short loc_1800151D6
0x1800151c8  lea     edx, [rax+41h]
0x1800151cb  jmp     loc_180014FE1
0x1800151d0  xor     ebx, ebx
0x1800151d2  mov     [rdi+68h], r14d
0x1800151d6  mov     rcx, rsi; lpCriticalSection
0x1800151d9  call    cs:__imp_LeaveCriticalSection
0x1800151e0  nop     dword ptr [rax+rax+00h]
0x1800151e5  mov     eax, ebx
0x1800151e7  add     rsp, 50h
0x1800151eb  pop     r15
0x1800151ed  pop     r14
0x1800151ef  pop     rdi
0x1800151f0  pop     rsi
0x1800151f1  pop     rbx
0x1800151f2  retn
```
