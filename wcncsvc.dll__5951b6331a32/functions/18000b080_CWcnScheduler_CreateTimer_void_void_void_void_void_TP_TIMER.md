# CWcnScheduler::CreateTimer(void (*)(void *,void *,void *),void *,_TP_TIMER * *)

- ea: `0x18000b080`
- end: `0x18000b1ef`
- name: `?CreateTimer@CWcnScheduler@@QEAAJP6AXPEAX00@Z0PEAPEAU_TP_TIMER@@@Z`
- size: `367`
- prototype: `__int64 __fastcall(CWcnScheduler *this, void (__stdcall *)(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer), void *, struct _TP_TIMER **)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180003dec`
- `0x180016994`
- `0x180045bc0`

## callees

- `0x180004fb8`
- `0x180005014`
- `0x18000b080`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b14c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b156`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b14c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b156`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b160`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b13e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b13e`

## pseudocode

```c
__int64 __fastcall CWcnScheduler::CreateTimer(
        CWcnScheduler *this,
        void (__stdcall *a2)(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer),
        void *a3,
        struct _TP_TIMER **a4)
{
  _BYTE *v8; // r10
  const char *Indent; // rax
  __int64 v10; // r10
  __int64 v11; // rdx
  const char *v12; // r9
  unsigned int v14; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  unsigned int LastError; // ebx
  _BYTE *v17; // r10
  unsigned int v18; // eax
  __int64 v19; // r10
  unsigned int v20; // eax
  __int64 v21; // r10

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v10 + 16), 18, WPP_476dff25f8043d358a001b332c2d8e81_Traceguids, Indent);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || v8[25] < 2u )
      return 2147500035LL;
    v11 = 19;
    v12 = "Fn";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v8 + 2), v11, WPP_476dff25f8043d358a001b332c2d8e81_Traceguids, v12);
    return 2147500035LL;
  }
  if ( !a4 )
  {
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || v8[25] < 2u )
      return 2147500035LL;
    v11 = 20;
    v12 = "phTimerItem";
    goto LABEL_12;
  }
  v14 = 0;
  *a4 = 0;
  ThreadpoolTimer = CreateThreadpoolTimer(a2, a3, (PTP_CALLBACK_ENVIRON)((char *)this + 8));
  *a4 = ThreadpoolTimer;
  if ( ThreadpoolTimer )
    goto LABEL_21;
  if ( (int)GetLastError() > 0 )
    LastError = (unsigned __int16)GetLastError() | 0x80070000;
  else
    LastError = GetLastError();
  v14 = LastError | 0x80000000;
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v14;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = (unsigned int)GetIndent(0);
    WPP_SF_sd(*(_QWORD *)(v19 + 16), 21, (unsigned int)WPP_476dff25f8043d358a001b332c2d8e81_Traceguids, v18, v14);
LABEL_21:
    v17 = WPP_GLOBAL_Control;
  }
  if ( v17 != (_BYTE *)&WPP_GLOBAL_Control && ((v14 & 0x80000000) != 0 || v17[25] >= 6u) )
  {
    v20 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v21 + 16), 22, (unsigned int)WPP_476dff25f8043d358a001b332c2d8e81_Traceguids, v20, v14);
  }
  return v14;
}

```

## disassembly

```asm
0x18000b080  push    rbx
0x18000b082  push    rbp
0x18000b083  push    rsi
0x18000b084  push    rdi
0x18000b085  push    r12
0x18000b087  push    r14
0x18000b089  push    r15
0x18000b08b  sub     rsp, 30h
0x18000b08f  mov     rdi, r9
0x18000b092  mov     rbp, r8
0x18000b095  mov     rsi, rdx
0x18000b098  mov     r14, rcx
0x18000b09b  mov     r10, cs:WPP_GLOBAL_Control
0x18000b0a2  lea     r15, WPP_GLOBAL_Control
0x18000b0a9  lea     r12, WPP_476dff25f8043d358a001b332c2d8e81_Traceguids
0x18000b0b0  cmp     r10, r15
0x18000b0b3  jz      short loc_18000B0E1
0x18000b0b5  cmp     byte ptr [r10+19h], 6
0x18000b0ba  jb      short loc_18000B0E1
0x18000b0bc  mov     ecx, 1; int
0x18000b0c1  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000b0c6  mov     rcx, [r10+10h]
0x18000b0ca  mov     edx, 12h
0x18000b0cf  mov     r9, rax
0x18000b0d2  mov     r8, r12
0x18000b0d5  call    WPP_SF_s
0x18000b0da  mov     r10, cs:WPP_GLOBAL_Control
0x18000b0e1  test    rsi, rsi
0x18000b0e4  jnz     short loc_18000B0FE
0x18000b0e6  cmp     r10, r15
0x18000b0e9  jz      short loc_18000B125
0x18000b0eb  cmp     byte ptr [r10+19h], 2
0x18000b0f0  jb      short loc_18000B125
0x18000b0f2  lea     edx, [rsi+13h]
0x18000b0f5  lea     r9, aFn; "Fn"
0x18000b0fc  jmp     short loc_18000B119
0x18000b0fe  test    rdi, rdi
0x18000b101  jnz     short loc_18000B12F
0x18000b103  cmp     r10, r15
0x18000b106  jz      short loc_18000B125
0x18000b108  cmp     byte ptr [r10+19h], 2
0x18000b10d  jb      short loc_18000B125
0x18000b10f  lea     edx, [rdi+14h]
0x18000b112  lea     r9, aPhtimeritem; "phTimerItem"
0x18000b119  mov     rcx, [r10+10h]
0x18000b11d  mov     r8, r12
0x18000b120  call    WPP_SF_s
0x18000b125  mov     eax, 80004003h
0x18000b12a  jmp     loc_18000B1E0
0x18000b12f  xor     ebx, ebx
0x18000b131  lea     r8, [r14+8]; pcbe
0x18000b135  mov     rdx, rbp; pv
0x18000b138  mov     [rdi], rbx
0x18000b13b  mov     rcx, rsi; pfnti
0x18000b13e  call    cs:__imp_CreateThreadpoolTimer
0x18000b144  mov     [rdi], rax
0x18000b147  test    rax, rax
0x18000b14a  jnz     short loc_18000B1A7
0x18000b14c  call    cs:__imp_GetLastError
0x18000b152  test    eax, eax
0x18000b154  jg      short loc_18000B160
0x18000b156  call    cs:__imp_GetLastError
0x18000b15c  mov     ebx, eax
0x18000b15e  jmp     short loc_18000B16F
0x18000b160  call    cs:__imp_GetLastError
0x18000b166  movzx   ebx, ax
0x18000b169  or      ebx, 80070000h
0x18000b16f  or      ebx, 80000000h
0x18000b175  mov     r10, cs:WPP_GLOBAL_Control
0x18000b17c  cmp     r10, r15
0x18000b17f  jz      short loc_18000B1DE
0x18000b181  cmp     byte ptr [r10+19h], 2
0x18000b186  jb      short loc_18000B1AE
0x18000b188  xor     ecx, ecx; int
0x18000b18a  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000b18f  mov     rcx, [r10+10h]
0x18000b193  mov     edx, 15h
0x18000b198  mov     r9, rax
0x18000b19b  mov     [rsp+68h+var_48], ebx
0x18000b19f  mov     r8, r12
0x18000b1a2  call    WPP_SF_sd
0x18000b1a7  mov     r10, cs:WPP_GLOBAL_Control
0x18000b1ae  cmp     r10, r15
0x18000b1b1  jz      short loc_18000B1DE
0x18000b1b3  test    ebx, ebx
0x18000b1b5  js      short loc_18000B1BE
0x18000b1b7  cmp     byte ptr [r10+19h], 6
0x18000b1bc  jb      short loc_18000B1DE
0x18000b1be  or      ecx, 0FFFFFFFFh; int
0x18000b1c1  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000b1c6  mov     rcx, [r10+10h]
0x18000b1ca  mov     edx, 16h
0x18000b1cf  mov     r9, rax
0x18000b1d2  mov     [rsp+68h+var_48], ebx
0x18000b1d6  mov     r8, r12
0x18000b1d9  call    WPP_SF_sd
0x18000b1de  mov     eax, ebx
0x18000b1e0  add     rsp, 30h
0x18000b1e4  pop     r15
0x18000b1e6  pop     r14
0x18000b1e8  pop     r12
0x18000b1ea  pop     rdi
0x18000b1eb  pop     rsi
0x18000b1ec  pop     rbp
0x18000b1ed  pop     rbx
0x18000b1ee  retn
```
