# MSMIndicateSecurityResult(ulong,void *,void *,uchar (*)[6],ulong,ulong,int,void *,void *,void *,ulong (*)(void *,void *,uchar (*)[6],ulong,ulong))

- ea: `0x18002569c`
- end: `0x180025894`
- name: `?MSMIndicateSecurityResult@@YAKKPEAX0PEAY05EKKH000P6AK001KK@Z@Z`
- size: `504`
- prototype: `unsigned int __fastcall(unsigned int, void *, void *, unsigned __int8 (*)[6], unsigned int, unsigned int, int, void *, void *, void *, unsigned int (*)(void *, void *, unsigned __int8 (*)[6], unsigned int, unsigned int))`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180025390`
- `0x180062970`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000a4e0`
- `0x18000c730`
- `0x18000e620`
- `0x1800163e0`
- `0x18002569c`
- `0x180025a70`
- `0x180056268`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025836`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18002578d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18002578d`

## string_xrefs

- `0x180025701`: `MSMIndicateSecurityResult`
- `0x1800257f5`: `MSMIndicateSecurityResult`

## pseudocode

```c
__int64 __fastcall MSMIndicateSecurityResult(
        int a1,
        void *a2,
        void *a3,
        unsigned __int8 (*a4)[6],
        unsigned int a5,
        unsigned int a6,
        int a7,
        void *a8,
        void *a9,
        void *a10,
        unsigned int (*a11)(void *, void *, unsigned __int8 (*)[6], unsigned int, unsigned int))
{
  DWORD MSMSecMemory; // eax
  _QWORD *v16; // rdi
  DWORD v17; // ebx
  int v19; // esi
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  PVOID Context[9]; // [rsp+20h] [rbp-48h] BYREF

  Context[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 68, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids);
  MSMSecMemory = AllocateMSMSecMemory(0x50u);
  v16 = Context[0];
  v17 = MSMSecMemory;
  if ( MSMSecMemory )
  {
    v19 = 0;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v21 = 69;
LABEL_19:
      WPP_SF_d(v20[7], v21, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, MSMSecMemory);
    }
  }
  else
  {
    *(_DWORD *)Context[0] = a1;
    v16[1] = a2;
    v16[2] = a3;
    *((_DWORD *)v16 + 6) = *(_DWORD *)a4;
    *((_WORD *)v16 + 14) = *(_WORD *)&(*a4)[4];
    *((_DWORD *)v16 + 8) = a5;
    *((_DWORD *)v16 + 9) = a6;
    *((_DWORD *)v16 + 10) = a7;
    v16[6] = a8;
    v16[7] = a9;
    v16[8] = a10;
    v16[9] = a11;
    IncThreadCountEx("MSMIndicateSecurityResult", 701);
    NetTraceMarkContextActivityStart(v16, 0x12u);
    if ( QueueUserWorkItem((LPTHREAD_START_ROUTINE)IndicateSecurityResultWorker, v16, 0) )
      goto LABEL_6;
    MSMSecMemory = GetLastError();
    v17 = MSMSecMemory;
    if ( !MSMSecMemory )
      goto LABEL_6;
    v19 = 1;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v21 = 70;
      goto LABEL_19;
    }
  }
  FreeMSMSecMemory(Context);
  if ( v19 )
    DecThreadCountEx("MSMIndicateSecurityResult", 725);
LABEL_6:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 71, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v17);
  return v17;
}

```

## disassembly

```asm
0x18002569c  push    rbx
0x18002569e  push    rbp
0x18002569f  push    rsi
0x1800256a0  push    rdi
0x1800256a1  push    r12
0x1800256a3  push    r14
0x1800256a5  push    r15
0x1800256a7  sub     rsp, 30h
0x1800256ab  mov     rsi, r9
0x1800256ae  mov     [rsp+68h+Context], 0
0x1800256b7  mov     rbp, r8
0x1800256ba  mov     r14, rdx
0x1800256bd  mov     r15d, ecx
0x1800256c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256c7  lea     r12, WPP_GLOBAL_Control
0x1800256ce  cmp     rcx, r12
0x1800256d1  jz      short loc_1800256E0
0x1800256d3  test    dword ptr [rcx+44h], 100h
0x1800256da  jnz     loc_180025803
0x1800256e0  lea     rdx, [rsp+68h+Context]
0x1800256e5  mov     ecx, 50h ; 'P'; dwBytes
0x1800256ea  call    AllocateMSMSecMemory
0x1800256ef  mov     rdi, [rsp+68h+Context]
0x1800256f4  mov     ebx, eax
0x1800256f6  test    eax, eax
0x1800256f8  jnz     loc_18002581D
0x1800256fe  mov     [rdi], r15d
0x180025701  lea     rcx, aMsmindicatesec; "MSMIndicateSecurityResult"
0x180025708  mov     [rdi+8], r14
0x18002570c  mov     edx, 2BDh; int
0x180025711  mov     [rdi+10h], rbp
0x180025715  mov     eax, [rsi]
0x180025717  mov     [rdi+18h], eax
0x18002571a  movzx   eax, word ptr [rsi+4]
0x18002571e  mov     [rdi+1Ch], ax
0x180025722  mov     eax, [rsp+68h+arg_20]
0x180025729  mov     [rdi+20h], eax
0x18002572c  mov     eax, [rsp+68h+arg_28]
0x180025733  mov     [rdi+24h], eax
0x180025736  mov     eax, [rsp+68h+arg_30]
0x18002573d  mov     [rdi+28h], eax
0x180025740  mov     rax, [rsp+68h+arg_38]
0x180025748  mov     [rdi+30h], rax
0x18002574c  mov     rax, [rsp+68h+arg_40]
0x180025754  mov     [rdi+38h], rax
0x180025758  mov     rax, [rsp+68h+arg_48]
0x180025760  mov     [rdi+40h], rax
0x180025764  mov     rax, [rsp+68h+arg_50]
0x18002576c  mov     [rdi+48h], rax
0x180025770  call    ?IncThreadCountEx@@YAXPEBDH@Z; IncThreadCountEx(char const *,int)
0x180025775  lea     edx, [rbx+12h]; unsigned int
0x180025778  mov     rcx, rdi; void *
0x18002577b  call    ?NetTraceMarkContextActivityStart@@YAXPEAXI@Z; NetTraceMarkContextActivityStart(void *,uint)
0x180025780  xor     r8d, r8d; Flags
0x180025783  lea     rcx, ?IndicateSecurityResultWorker@@YAKPEAX@Z; Function
0x18002578a  mov     rdx, rdi; Context
0x18002578d  call    cs:__imp_QueueUserWorkItem
0x180025794  nop     dword ptr [rax+rax+00h]
0x180025799  test    eax, eax
0x18002579b  jz      loc_180025836
0x1800257a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257a8  cmp     rcx, r12
0x1800257ab  jnz     short loc_1800257BF
0x1800257ad  mov     eax, ebx
0x1800257af  add     rsp, 30h
0x1800257b3  pop     r15
0x1800257b5  pop     r14
0x1800257b7  pop     r12
0x1800257b9  pop     rdi
0x1800257ba  pop     rsi
0x1800257bb  pop     rbp
0x1800257bc  pop     rbx
0x1800257bd  retn
0x1800257bf  test    dword ptr [rcx+44h], 100h
0x1800257c6  jz      short loc_1800257AD
0x1800257c8  mov     rcx, [rcx+38h]
0x1800257cc  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x1800257d3  mov     edx, 47h ; 'G'
0x1800257d8  mov     r9d, ebx
0x1800257db  call    WPP_SF_d
0x1800257e0  jmp     short loc_1800257AD
0x1800257e2  lea     rcx, [rsp+68h+Context]
0x1800257e7  call    FreeMSMSecMemory
0x1800257ec  test    esi, esi
0x1800257ee  jz      short loc_1800257A1
0x1800257f0  mov     edx, 2D5h; int
0x1800257f5  lea     rcx, aMsmindicatesec; "MSMIndicateSecurityResult"
0x1800257fc  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x180025801  jmp     short loc_1800257A1
0x180025803  mov     rcx, [rcx+38h]
0x180025807  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x18002580e  mov     edx, 44h ; 'D'
0x180025813  call    WPP_SF_
0x180025818  jmp     loc_1800256E0
0x18002581d  xor     esi, esi
0x18002581f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025826  cmp     rcx, r12
0x180025829  jz      short loc_180025879
0x18002582b  test    byte ptr [rcx+44h], 1
0x18002582f  jz      short loc_180025879
0x180025831  lea     edx, [rsi+45h]
0x180025834  jmp     short loc_180025866
0x180025836  call    cs:__imp_GetLastError
0x18002583d  nop     dword ptr [rax+rax+00h]
0x180025842  mov     ebx, eax
0x180025844  test    eax, eax
0x180025846  jz      loc_1800257A1
0x18002584c  mov     esi, 1
0x180025851  mov     rcx, cs:WPP_GLOBAL_Control
0x180025858  cmp     rcx, r12
0x18002585b  jz      short loc_180025879
0x18002585d  test    [rcx+44h], sil
0x180025861  jz      short loc_180025879
0x180025863  lea     edx, [rsi+45h]
0x180025866  mov     rcx, [rcx+38h]
0x18002586a  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x180025871  mov     r9d, eax
0x180025874  call    WPP_SF_d
0x180025879  test    rdi, rdi
0x18002587c  jz      loc_1800257E2
0x180025882  mov     edx, 12h; unsigned int
0x180025887  mov     rcx, rdi; void *
0x18002588a  call    ?NetTraceMarkContextActivityStop@@YAXPEAXI@Z; NetTraceMarkContextActivityStop(void *,uint)
0x18002588f  jmp     loc_1800257E2
```
