# BaseHttpListener::InitListening(char const *,ulong,int,int,int,int)

- ea: `0x180033698`
- end: `0x180033965`
- name: `?InitListening@BaseHttpListener@@QEAAJPEBDKHHHH@Z`
- size: `717`
- prototype: `int(BaseHttpListener *__hidden this, const char *, unsigned int, int, int, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c9fc`

## callees

- `0x180022dd4`
- `0x180029df0`
- `0x180033698`
- `0x180033d3c`
- `0x180033e6c`
- `0x1800341cc`
- `0x180036888`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180033798`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180033800`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180033875`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180033798`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180033800`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180033875`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003394b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003394b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800336f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800336f3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800338cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003390c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800338cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003390c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033829`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033829`

## pseudocode

```c
__int64 __fastcall BaseHttpListener::InitListening(BaseHttpListener *this, const char *a2, int a3)
{
  BaseHttpListener *v3; // rdi
  CSimpleLock *v5; // rcx
  unsigned int v6; // ebx
  LPCSTR v7; // rcx
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

  v3 = g_pEventHTTPListener;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, a3, (unsigned int)"/upnp/eventing/", a3, 1);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 184));
  *((_DWORD *)v3 + 40) = a3;
  *((_DWORD *)v3 + 33) = 1;
  *((_DWORD *)v3 + 34) = 1;
  *(_QWORD *)((char *)v3 + 140) = 1;
  DupStr((char **)v3 + 19, "/upnp/eventing/");
  if ( *((_QWORD *)v3 + 19) )
  {
    CSimpleLock::Enter(v5);
    if ( ++dword_18004573C == 1 )
      byte_180045740 = 1;
    _InterlockedExchange(&g_lckLkrInit, 0);
    v9 = (LKRhash::CLKRHashTable *)malloc(0x48u);
    v13 = v9;
    if ( v9 )
      LKRhash::CLKRHashTable::CLKRHashTable(v9, v10, v11, v12, v23, v24, 4.0, v25, v26, v27);
    else
      v13 = 0;
    *((_QWORD *)v3 + 21) = v13;
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
      *((_QWORD *)v3 + 33) = v15;
      if ( v15 )
      {
        v16 = (CMultipleIPThrottleByTime *)malloc(0x50u);
        if ( v16 )
          v16 = CMultipleIPThrottleByTime::CMultipleIPThrottleByTime(v16, v17, v18, v19);
        *((_QWORD *)v3 + 34) = v16;
        if ( v16 )
        {
          EventW = CreateEventW(0, 1, 1, 0);
          *((_QWORD *)v3 + 36) = EventW;
          if ( EventW )
          {
            v21 = CreateEventW(0, 1, 0, 0);
            *((_QWORD *)v3 + 39) = v21;
            if ( v21 )
            {
              v6 = 0;
              *((_DWORD *)v3 + 26) = 1;
              goto LABEL_40;
            }
            v6 = -2147024882;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
            {
              v8 = 65;
              goto LABEL_8;
            }
          }
          else
          {
            v6 = -2147024882;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
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
          if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
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
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
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
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
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
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      v8 = 59;
LABEL_8:
      WPP_SF_(*((_QWORD *)v7 + 2), v8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
    }
  }
LABEL_40:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 184));
  return v6;
}

```

## disassembly

```asm
0x180033698  push    rbx
0x18003369a  push    rbp
0x18003369b  push    rsi
0x18003369c  push    rdi
0x18003369d  push    r14
0x18003369f  sub     rsp, 50h
0x1800336a3  mov     rdi, cs:?g_pEventHTTPListener@@3PEAVBaseHttpListener@@EA; BaseHttpListener * g_pEventHTTPListener
0x1800336aa  mov     ebx, r8d
0x1800336ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800336b4  lea     r14, WPP_GLOBAL_Control
0x1800336bb  mov     ebp, 1
0x1800336c0  cmp     rcx, r14
0x1800336c3  jz      short loc_1800336E9
0x1800336c5  test    dword ptr [rcx+1Ch], 100h
0x1800336cc  jz      short loc_1800336E9
0x1800336ce  mov     rcx, [rcx+10h]
0x1800336d2  lea     edx, [rbp+39h]
0x1800336d5  mov     dword ptr [rsp+78h+var_50], ebp; void (*)(const void *, int)
0x1800336d9  lea     r9, aUpnpEventing; "/upnp/eventing/"
0x1800336e0  mov     dword ptr [rsp+78h+var_58], ebx; bool (*)(unsigned __int64, unsigned __int64)
0x1800336e4  call    WPP_SF_sdd
0x1800336e9  lea     rsi, [rdi+0B8h]
0x1800336f0  mov     rcx, rsi; lpCriticalSection
0x1800336f3  call    cs:__imp_EnterCriticalSection
0x1800336fa  nop     dword ptr [rax+rax+00h]
0x1800336ff  mov     [rdi+0A0h], ebx
0x180033705  lea     rdx, aUpnpEventing; "/upnp/eventing/"
0x18003370c  lea     rbx, [rdi+98h]
0x180033713  mov     [rdi+84h], ebp
0x180033719  mov     rcx, rbx; char **
0x18003371c  mov     [rdi+88h], ebp
0x180033722  mov     [rdi+8Ch], rbp
0x180033729  call    ?DupStr@@YAXPEAPEADPEBD@Z; DupStr(char * *,char const *)
0x18003372e  cmp     qword ptr [rbx], 0
0x180033732  jnz     short loc_18003376D
0x180033734  mov     ebx, 8007000Eh
0x180033739  mov     rcx, cs:WPP_GLOBAL_Control
0x180033740  cmp     rcx, r14
0x180033743  jz      loc_180033948
0x180033749  test    [rcx+1Ch], bpl
0x18003374d  jz      loc_180033948
0x180033753  mov     edx, 3Bh ; ';'
0x180033758  mov     rcx, [rcx+10h]
0x18003375c  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180033763  call    WPP_SF_
0x180033768  jmp     loc_180033948
0x18003376d  call    ?Enter@CSimpleLock@@QEAAXXZ; CSimpleLock::Enter(void)
0x180033772  mov     eax, cs:dword_18004573C
0x180033778  add     eax, ebp
0x18003377a  mov     cs:dword_18004573C, eax
0x180033780  cmp     eax, ebp
0x180033782  jnz     short loc_18003378B
0x180033784  mov     cs:byte_180045740, bpl
0x18003378b  xor     eax, eax
0x18003378d  mov     ecx, 48h ; 'H'; Size
0x180033792  xchg    eax, cs:?g_lckLkrInit@@3VCSimpleLock@@A; CSimpleLock g_lckLkrInit
0x180033798  call    cs:__imp_malloc
0x18003379f  nop     dword ptr [rax+rax+00h]
0x1800337a4  mov     rbx, rax
0x1800337a7  test    rax, rax
0x1800337aa  jz      short loc_1800337C4
0x1800337ac  movsd   xmm0, cs:__real@4010000000000000
0x1800337b4  mov     rcx, rax; this
0x1800337b7  movsd   [rsp+78h+var_48], xmm0; double
0x1800337bd  call    ??0CLKRHashTable@LKRhash@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; LKRhash::CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x1800337c2  jmp     short loc_1800337C6
0x1800337c4  xor     ebx, ebx
0x1800337c6  mov     [rdi+0A8h], rbx
0x1800337cd  test    rbx, rbx
0x1800337d0  jnz     short loc_1800337FB
0x1800337d2  mov     ebx, 8007000Eh
0x1800337d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800337de  cmp     rcx, r14
0x1800337e1  jz      loc_180033948
0x1800337e7  test    [rcx+1Ch], bpl
0x1800337eb  jz      loc_180033948
0x1800337f1  mov     edx, 3Dh ; '='
0x1800337f6  jmp     loc_180033758
0x1800337fb  mov     ecx, 14h; Size
0x180033800  call    cs:__imp_malloc
0x180033807  nop     dword ptr [rax+rax+00h]
0x18003380c  mov     rbx, rax
0x18003380f  test    rax, rax
0x180033812  jz      short loc_180033839
0x180033814  mov     dword ptr [rax+8], 50h ; 'P'
0x18003381b  mov     dword ptr [rax+10h], 2710h
0x180033822  mov     dword ptr [rax+0Ch], 50h ; 'P'
0x180033829  call    cs:__imp_GetTickCount
0x180033830  nop     dword ptr [rax+rax+00h]
0x180033835  mov     [rbx], eax
0x180033837  jmp     short loc_18003383B
0x180033839  xor     ebx, ebx
0x18003383b  mov     [rdi+108h], rbx
0x180033842  test    rbx, rbx
0x180033845  jnz     short loc_180033870
0x180033847  mov     ebx, 8007000Eh
0x18003384c  mov     rcx, cs:WPP_GLOBAL_Control
0x180033853  cmp     rcx, r14
0x180033856  jz      loc_180033948
0x18003385c  test    [rcx+1Ch], bpl
0x180033860  jz      loc_180033948
0x180033866  mov     edx, 3Eh ; '>'
0x18003386b  jmp     loc_180033758
0x180033870  mov     ecx, 50h ; 'P'; Size
0x180033875  call    cs:__imp_malloc
0x18003387c  nop     dword ptr [rax+rax+00h]
0x180033881  test    rax, rax
0x180033884  jz      short loc_18003388E
0x180033886  mov     rcx, rax; this
0x180033889  call    ??0CMultipleIPThrottleByTime@@QEAA@KKK@Z; CMultipleIPThrottleByTime::CMultipleIPThrottleByTime(ulong,ulong,ulong)
0x18003388e  mov     [rdi+110h], rax
0x180033895  test    rax, rax
0x180033898  jnz     short loc_1800338C1
0x18003389a  mov     ebx, 8007000Eh
0x18003389f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800338a6  cmp     rcx, r14
0x1800338a9  jz      loc_180033948
0x1800338af  test    [rcx+1Ch], bpl
0x1800338b3  jz      loc_180033948
0x1800338b9  lea     edx, [rax+3Fh]
0x1800338bc  jmp     loc_180033758
0x1800338c1  xor     r9d, r9d; lpName
0x1800338c4  mov     r8d, ebp; bInitialState
0x1800338c7  mov     edx, ebp; bManualReset
0x1800338c9  xor     ecx, ecx; lpEventAttributes
0x1800338cb  call    cs:__imp_CreateEventW
0x1800338d2  nop     dword ptr [rax+rax+00h]
0x1800338d7  mov     [rdi+120h], rax
0x1800338de  test    rax, rax
0x1800338e1  jnz     short loc_180033902
0x1800338e3  mov     ebx, 8007000Eh
0x1800338e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800338ef  cmp     rcx, r14
0x1800338f2  jz      short loc_180033948
0x1800338f4  test    [rcx+1Ch], bpl
0x1800338f8  jz      short loc_180033948
0x1800338fa  lea     edx, [rax+40h]
0x1800338fd  jmp     loc_180033758
0x180033902  xor     r9d, r9d; lpName
0x180033905  xor     r8d, r8d; bInitialState
0x180033908  mov     edx, ebp; bManualReset
0x18003390a  xor     ecx, ecx; lpEventAttributes
0x18003390c  call    cs:__imp_CreateEventW
0x180033913  nop     dword ptr [rax+rax+00h]
0x180033918  mov     [rdi+138h], rax
0x18003391f  test    rax, rax
0x180033922  jnz     short loc_180033943
0x180033924  mov     ebx, 8007000Eh
0x180033929  mov     rcx, cs:WPP_GLOBAL_Control
0x180033930  cmp     rcx, r14
0x180033933  jz      short loc_180033948
0x180033935  test    [rcx+1Ch], bpl
0x180033939  jz      short loc_180033948
0x18003393b  lea     edx, [rax+41h]
0x18003393e  jmp     loc_180033758
0x180033943  xor     ebx, ebx
0x180033945  mov     [rdi+68h], ebp
0x180033948  mov     rcx, rsi; lpCriticalSection
0x18003394b  call    cs:__imp_LeaveCriticalSection
0x180033952  nop     dword ptr [rax+rax+00h]
0x180033957  mov     eax, ebx
0x180033959  add     rsp, 50h
0x18003395d  pop     r14
0x18003395f  pop     rdi
0x180033960  pop     rsi
0x180033961  pop     rbp
0x180033962  pop     rbx
0x180033963  retn
```
