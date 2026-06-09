# BaseHttpListener::InitListening(char const *,ulong,int,int,int,int)

- ea: `0x18001fd48`
- end: `0x18001fff3`
- name: `?InitListening@BaseHttpListener@@QEAAJPEBDKHHHH@Z`
- size: `683`
- prototype: `int(BaseHttpListener *__hidden this, const char *, unsigned int, int, int, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001f41c`

## callees

- `0x18001fd48`
- `0x180023310`
- `0x1800306a8`
- `0x180030ef0`
- `0x180039a84`
- `0x180051884`
- `0x1800519a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001fe4d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001feaf`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ff18`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001fe4d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001feaf`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ff18`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ff69`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ffa5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ff69`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ffa5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fda1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fda1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ffdf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ffdf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001fed2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001fed2`

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
    if ( ++dword_1800720EC == 1 )
      byte_1800720E8 = 1;
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
0x18001fd48  push    rbx
0x18001fd4a  push    rsi
0x18001fd4b  push    rdi
0x18001fd4c  push    r14
0x18001fd4e  push    r15
0x18001fd50  sub     rsp, 50h
0x18001fd54  mov     ebx, r8d
0x18001fd57  mov     rdi, rcx
0x18001fd5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd61  lea     r15, WPP_GLOBAL_Control
0x18001fd68  cmp     rcx, r15
0x18001fd6b  jz      short loc_18001FD97
0x18001fd6d  test    dword ptr [rcx+1Ch], 100h
0x18001fd74  jz      short loc_18001FD97
0x18001fd76  mov     rcx, [rcx+10h]
0x18001fd7a  lea     r9, asc_18005F56C; "/"
0x18001fd81  mov     edx, 3Ah ; ':'
0x18001fd86  mov     dword ptr [rsp+78h+var_50], 0; void (*)(const void *, int)
0x18001fd8e  mov     dword ptr [rsp+78h+var_58], ebx; bool (*)(unsigned __int64, unsigned __int64)
0x18001fd92  call    WPP_SF_sdd
0x18001fd97  lea     rsi, [rdi+0B8h]
0x18001fd9e  mov     rcx, rsi; lpCriticalSection
0x18001fda1  call    cs:__imp_EnterCriticalSection
0x18001fda7  mov     [rdi+0A0h], ebx
0x18001fdad  lea     rdx, asc_18005F56C; "/"
0x18001fdb4  mov     r14d, 1
0x18001fdba  mov     qword ptr [rdi+84h], 0
0x18001fdc5  lea     rbx, [rdi+98h]
0x18001fdcc  mov     [rdi+8Ch], r14d
0x18001fdd3  mov     rcx, rbx; char **
0x18001fdd6  mov     [rdi+90h], r14d
0x18001fddd  call    ?DupStr@@YAXPEAPEADPEBD@Z; DupStr(char * *,char const *)
0x18001fde2  cmp     qword ptr [rbx], 0
0x18001fde6  jnz     short loc_18001FE20
0x18001fde8  mov     ebx, 8007000Eh
0x18001fded  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fdf4  cmp     rcx, r15
0x18001fdf7  jz      loc_18001FFDC
0x18001fdfd  test    [rcx+1Ch], r14b
0x18001fe01  jz      loc_18001FFDC
0x18001fe07  lea     edx, [r14+3Ah]
0x18001fe0b  mov     rcx, [rcx+10h]
0x18001fe0f  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001fe16  call    WPP_SF_
0x18001fe1b  jmp     loc_18001FFDC
0x18001fe20  call    ?Enter@CSimpleLock@@QEAAXXZ; CSimpleLock::Enter(void)
0x18001fe25  mov     eax, cs:dword_1800720EC
0x18001fe2b  add     eax, r14d
0x18001fe2e  mov     cs:dword_1800720EC, eax
0x18001fe34  cmp     eax, r14d
0x18001fe37  jnz     short loc_18001FE40
0x18001fe39  mov     cs:byte_1800720E8, r14b
0x18001fe40  xor     eax, eax
0x18001fe42  mov     ecx, 48h ; 'H'; Size
0x18001fe47  xchg    eax, cs:?g_lckLkrInit@@3VCSimpleLock@@A; CSimpleLock g_lckLkrInit
0x18001fe4d  call    cs:__imp_malloc
0x18001fe53  mov     rbx, rax
0x18001fe56  test    rax, rax
0x18001fe59  jz      short loc_18001FE73
0x18001fe5b  movsd   xmm0, cs:__real@4010000000000000
0x18001fe63  mov     rcx, rax; this
0x18001fe66  movsd   [rsp+78h+var_48], xmm0; double
0x18001fe6c  call    ??0CLKRHashTable@LKRhash@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; LKRhash::CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x18001fe71  jmp     short loc_18001FE75
0x18001fe73  xor     ebx, ebx
0x18001fe75  mov     [rdi+0A8h], rbx
0x18001fe7c  test    rbx, rbx
0x18001fe7f  jnz     short loc_18001FEAA
0x18001fe81  mov     ebx, 8007000Eh
0x18001fe86  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe8d  cmp     rcx, r15
0x18001fe90  jz      loc_18001FFDC
0x18001fe96  test    [rcx+1Ch], r14b
0x18001fe9a  jz      loc_18001FFDC
0x18001fea0  mov     edx, 3Dh ; '='
0x18001fea5  jmp     loc_18001FE0B
0x18001feaa  mov     ecx, 14h; Size
0x18001feaf  call    cs:__imp_malloc
0x18001feb5  mov     rbx, rax
0x18001feb8  test    rax, rax
0x18001febb  jz      short loc_18001FEDC
0x18001febd  mov     dword ptr [rax+8], 50h ; 'P'
0x18001fec4  mov     dword ptr [rax+10h], 2710h
0x18001fecb  mov     dword ptr [rax+0Ch], 50h ; 'P'
0x18001fed2  call    cs:__imp_GetTickCount
0x18001fed8  mov     [rbx], eax
0x18001feda  jmp     short loc_18001FEDE
0x18001fedc  xor     ebx, ebx
0x18001fede  mov     [rdi+108h], rbx
0x18001fee5  test    rbx, rbx
0x18001fee8  jnz     short loc_18001FF13
0x18001feea  mov     ebx, 8007000Eh
0x18001feef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fef6  cmp     rcx, r15
0x18001fef9  jz      loc_18001FFDC
0x18001feff  test    [rcx+1Ch], r14b
0x18001ff03  jz      loc_18001FFDC
0x18001ff09  mov     edx, 3Eh ; '>'
0x18001ff0e  jmp     loc_18001FE0B
0x18001ff13  mov     ecx, 50h ; 'P'; Size
0x18001ff18  call    cs:__imp_malloc
0x18001ff1e  test    rax, rax
0x18001ff21  jz      short loc_18001FF2B
0x18001ff23  mov     rcx, rax; this
0x18001ff26  call    ??0CMultipleIPThrottleByTime@@QEAA@KKK@Z; CMultipleIPThrottleByTime::CMultipleIPThrottleByTime(ulong,ulong,ulong)
0x18001ff2b  mov     [rdi+110h], rax
0x18001ff32  test    rax, rax
0x18001ff35  jnz     short loc_18001FF5E
0x18001ff37  mov     ebx, 8007000Eh
0x18001ff3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff43  cmp     rcx, r15
0x18001ff46  jz      loc_18001FFDC
0x18001ff4c  test    [rcx+1Ch], r14b
0x18001ff50  jz      loc_18001FFDC
0x18001ff56  lea     edx, [rax+3Fh]
0x18001ff59  jmp     loc_18001FE0B
0x18001ff5e  xor     r9d, r9d; lpName
0x18001ff61  mov     r8d, r14d; bInitialState
0x18001ff64  mov     edx, r14d; bManualReset
0x18001ff67  xor     ecx, ecx; lpEventAttributes
0x18001ff69  call    cs:__imp_CreateEventW
0x18001ff6f  mov     [rdi+120h], rax
0x18001ff76  test    rax, rax
0x18001ff79  jnz     short loc_18001FF9A
0x18001ff7b  mov     ebx, 8007000Eh
0x18001ff80  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff87  cmp     rcx, r15
0x18001ff8a  jz      short loc_18001FFDC
0x18001ff8c  test    [rcx+1Ch], r14b
0x18001ff90  jz      short loc_18001FFDC
0x18001ff92  lea     edx, [rax+40h]
0x18001ff95  jmp     loc_18001FE0B
0x18001ff9a  xor     r9d, r9d; lpName
0x18001ff9d  xor     r8d, r8d; bInitialState
0x18001ffa0  mov     edx, r14d; bManualReset
0x18001ffa3  xor     ecx, ecx; lpEventAttributes
0x18001ffa5  call    cs:__imp_CreateEventW
0x18001ffab  mov     [rdi+138h], rax
0x18001ffb2  test    rax, rax
0x18001ffb5  jnz     short loc_18001FFD6
0x18001ffb7  mov     ebx, 8007000Eh
0x18001ffbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ffc3  cmp     rcx, r15
0x18001ffc6  jz      short loc_18001FFDC
0x18001ffc8  test    [rcx+1Ch], r14b
0x18001ffcc  jz      short loc_18001FFDC
0x18001ffce  lea     edx, [rax+41h]
0x18001ffd1  jmp     loc_18001FE0B
0x18001ffd6  xor     ebx, ebx
0x18001ffd8  mov     [rdi+68h], r14d
0x18001ffdc  mov     rcx, rsi; lpCriticalSection
0x18001ffdf  call    cs:__imp_LeaveCriticalSection
0x18001ffe5  mov     eax, ebx
0x18001ffe7  add     rsp, 50h
0x18001ffeb  pop     r15
0x18001ffed  pop     r14
0x18001ffef  pop     rdi
0x18001fff0  pop     rsi
0x18001fff1  pop     rbx
0x18001fff2  retn
```
