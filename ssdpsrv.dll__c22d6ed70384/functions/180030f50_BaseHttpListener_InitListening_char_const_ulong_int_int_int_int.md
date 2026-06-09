# BaseHttpListener::InitListening(char const *,ulong,int,int,int,int)

- ea: `0x180030f50`
- end: `0x1800311ec`
- name: `?InitListening@BaseHttpListener@@QEAAJPEBDKHHHH@Z`
- size: `668`
- prototype: `__int64 __fastcall(BaseHttpListener *this, const char *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b064`

## callees

- `0x1800213d4`
- `0x180028000`
- `0x180030f50`
- `0x1800314cc`
- `0x1800315ec`
- `0x1800318f4`
- `0x180033dc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003104a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800310ac`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180031115`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003104a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800310ac`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180031115`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800311d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800311d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030fab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030fab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031165`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800311a0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031165`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800311a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800310cf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800310cf`

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
    if ( ++dword_180042654 == 1 )
      byte_180042658 = 1;
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
0x180030f50  push    rbx
0x180030f52  push    rbp
0x180030f53  push    rsi
0x180030f54  push    rdi
0x180030f55  push    r14
0x180030f57  sub     rsp, 50h
0x180030f5b  mov     rdi, cs:?g_pEventHTTPListener@@3PEAVBaseHttpListener@@EA; BaseHttpListener * g_pEventHTTPListener
0x180030f62  mov     ebx, r8d
0x180030f65  mov     rcx, cs:WPP_GLOBAL_Control
0x180030f6c  lea     r14, WPP_GLOBAL_Control
0x180030f73  mov     ebp, 1
0x180030f78  cmp     rcx, r14
0x180030f7b  jz      short loc_180030FA1
0x180030f7d  test    dword ptr [rcx+1Ch], 100h
0x180030f84  jz      short loc_180030FA1
0x180030f86  mov     rcx, [rcx+10h]
0x180030f8a  lea     edx, [rbp+39h]
0x180030f8d  mov     dword ptr [rsp+78h+var_50], ebp; void (*)(const void *, int)
0x180030f91  lea     r9, aUpnpEventing; "/upnp/eventing/"
0x180030f98  mov     dword ptr [rsp+78h+var_58], ebx; bool (*)(unsigned __int64, unsigned __int64)
0x180030f9c  call    WPP_SF_sdd
0x180030fa1  lea     rsi, [rdi+0B8h]
0x180030fa8  mov     rcx, rsi; lpCriticalSection
0x180030fab  call    cs:__imp_EnterCriticalSection
0x180030fb1  mov     [rdi+0A0h], ebx
0x180030fb7  lea     rdx, aUpnpEventing; "/upnp/eventing/"
0x180030fbe  lea     rbx, [rdi+98h]
0x180030fc5  mov     [rdi+84h], ebp
0x180030fcb  mov     rcx, rbx; char **
0x180030fce  mov     [rdi+88h], ebp
0x180030fd4  mov     [rdi+8Ch], rbp
0x180030fdb  call    ?DupStr@@YAXPEAPEADPEBD@Z; DupStr(char * *,char const *)
0x180030fe0  cmp     qword ptr [rbx], 0
0x180030fe4  jnz     short loc_18003101F
0x180030fe6  mov     ebx, 8007000Eh
0x180030feb  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ff2  cmp     rcx, r14
0x180030ff5  jz      loc_1800311D6
0x180030ffb  test    [rcx+1Ch], bpl
0x180030fff  jz      loc_1800311D6
0x180031005  mov     edx, 3Bh ; ';'
0x18003100a  mov     rcx, [rcx+10h]
0x18003100e  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180031015  call    WPP_SF_
0x18003101a  jmp     loc_1800311D6
0x18003101f  call    ?Enter@CSimpleLock@@QEAAXXZ; CSimpleLock::Enter(void)
0x180031024  mov     eax, cs:dword_180042654
0x18003102a  add     eax, ebp
0x18003102c  mov     cs:dword_180042654, eax
0x180031032  cmp     eax, ebp
0x180031034  jnz     short loc_18003103D
0x180031036  mov     cs:byte_180042658, bpl
0x18003103d  xor     eax, eax
0x18003103f  mov     ecx, 48h ; 'H'; Size
0x180031044  xchg    eax, cs:?g_lckLkrInit@@3VCSimpleLock@@A; CSimpleLock g_lckLkrInit
0x18003104a  call    cs:__imp_malloc
0x180031050  mov     rbx, rax
0x180031053  test    rax, rax
0x180031056  jz      short loc_180031070
0x180031058  movsd   xmm0, cs:__real@4010000000000000
0x180031060  mov     rcx, rax; this
0x180031063  movsd   [rsp+78h+var_48], xmm0; double
0x180031069  call    ??0CLKRHashTable@LKRhash@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; LKRhash::CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x18003106e  jmp     short loc_180031072
0x180031070  xor     ebx, ebx
0x180031072  mov     [rdi+0A8h], rbx
0x180031079  test    rbx, rbx
0x18003107c  jnz     short loc_1800310A7
0x18003107e  mov     ebx, 8007000Eh
0x180031083  mov     rcx, cs:WPP_GLOBAL_Control
0x18003108a  cmp     rcx, r14
0x18003108d  jz      loc_1800311D6
0x180031093  test    [rcx+1Ch], bpl
0x180031097  jz      loc_1800311D6
0x18003109d  mov     edx, 3Dh ; '='
0x1800310a2  jmp     loc_18003100A
0x1800310a7  mov     ecx, 14h; Size
0x1800310ac  call    cs:__imp_malloc
0x1800310b2  mov     rbx, rax
0x1800310b5  test    rax, rax
0x1800310b8  jz      short loc_1800310D9
0x1800310ba  mov     dword ptr [rax+8], 50h ; 'P'
0x1800310c1  mov     dword ptr [rax+10h], 2710h
0x1800310c8  mov     dword ptr [rax+0Ch], 50h ; 'P'
0x1800310cf  call    cs:__imp_GetTickCount
0x1800310d5  mov     [rbx], eax
0x1800310d7  jmp     short loc_1800310DB
0x1800310d9  xor     ebx, ebx
0x1800310db  mov     [rdi+108h], rbx
0x1800310e2  test    rbx, rbx
0x1800310e5  jnz     short loc_180031110
0x1800310e7  mov     ebx, 8007000Eh
0x1800310ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800310f3  cmp     rcx, r14
0x1800310f6  jz      loc_1800311D6
0x1800310fc  test    [rcx+1Ch], bpl
0x180031100  jz      loc_1800311D6
0x180031106  mov     edx, 3Eh ; '>'
0x18003110b  jmp     loc_18003100A
0x180031110  mov     ecx, 50h ; 'P'; Size
0x180031115  call    cs:__imp_malloc
0x18003111b  test    rax, rax
0x18003111e  jz      short loc_180031128
0x180031120  mov     rcx, rax; this
0x180031123  call    ??0CMultipleIPThrottleByTime@@QEAA@KKK@Z; CMultipleIPThrottleByTime::CMultipleIPThrottleByTime(ulong,ulong,ulong)
0x180031128  mov     [rdi+110h], rax
0x18003112f  test    rax, rax
0x180031132  jnz     short loc_18003115B
0x180031134  mov     ebx, 8007000Eh
0x180031139  mov     rcx, cs:WPP_GLOBAL_Control
0x180031140  cmp     rcx, r14
0x180031143  jz      loc_1800311D6
0x180031149  test    [rcx+1Ch], bpl
0x18003114d  jz      loc_1800311D6
0x180031153  lea     edx, [rax+3Fh]
0x180031156  jmp     loc_18003100A
0x18003115b  xor     r9d, r9d; lpName
0x18003115e  mov     r8d, ebp; bInitialState
0x180031161  mov     edx, ebp; bManualReset
0x180031163  xor     ecx, ecx; lpEventAttributes
0x180031165  call    cs:__imp_CreateEventW
0x18003116b  mov     [rdi+120h], rax
0x180031172  test    rax, rax
0x180031175  jnz     short loc_180031196
0x180031177  mov     ebx, 8007000Eh
0x18003117c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031183  cmp     rcx, r14
0x180031186  jz      short loc_1800311D6
0x180031188  test    [rcx+1Ch], bpl
0x18003118c  jz      short loc_1800311D6
0x18003118e  lea     edx, [rax+40h]
0x180031191  jmp     loc_18003100A
0x180031196  xor     r9d, r9d; lpName
0x180031199  xor     r8d, r8d; bInitialState
0x18003119c  mov     edx, ebp; bManualReset
0x18003119e  xor     ecx, ecx; lpEventAttributes
0x1800311a0  call    cs:__imp_CreateEventW
0x1800311a6  mov     [rdi+138h], rax
0x1800311ad  test    rax, rax
0x1800311b0  jnz     short loc_1800311D1
0x1800311b2  mov     ebx, 8007000Eh
0x1800311b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800311be  cmp     rcx, r14
0x1800311c1  jz      short loc_1800311D6
0x1800311c3  test    [rcx+1Ch], bpl
0x1800311c7  jz      short loc_1800311D6
0x1800311c9  lea     edx, [rax+41h]
0x1800311cc  jmp     loc_18003100A
0x1800311d1  xor     ebx, ebx
0x1800311d3  mov     [rdi+68h], ebp
0x1800311d6  mov     rcx, rsi; lpCriticalSection
0x1800311d9  call    cs:__imp_LeaveCriticalSection
0x1800311df  mov     eax, ebx
0x1800311e1  add     rsp, 50h
0x1800311e5  pop     r14
0x1800311e7  pop     rdi
0x1800311e8  pop     rsi
0x1800311e9  pop     rbp
0x1800311ea  pop     rbx
0x1800311eb  retn
```
