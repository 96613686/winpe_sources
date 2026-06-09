# CWcnScheduler::CreateWorkItem(void (*)(void *,void *,void *),void *,_TP_WORK * *)

- ea: `0x18000b1f8`
- end: `0x18000b367`
- name: `?CreateWorkItem@CWcnScheduler@@QEAAJP6AXPEAX00@Z0PEAPEAU_TP_WORK@@@Z`
- size: `367`
- prototype: `__int64 __fastcall(CWcnScheduler *this, void (__stdcall *)(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work), void *, struct _TP_WORK **)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180016994`
- `0x180042994`
- `0x180047544`
- `0x18004a2a4`
- `0x18004c224`
- `0x18004fbe0`
- `0x1800567e4`

## callees

- `0x180004fb8`
- `0x180005014`
- `0x18000b1f8`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2d8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000b2b6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000b2b6`

## pseudocode

```c
__int64 __fastcall CWcnScheduler::CreateWorkItem(
        CWcnScheduler *this,
        void (__stdcall *a2)(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work),
        void *a3,
        struct _TP_WORK **a4)
{
  _BYTE *v8; // r10
  const char *Indent; // rax
  __int64 v10; // r10
  __int64 v11; // rdx
  const char *v12; // r9
  unsigned int v14; // ebx
  struct _TP_WORK *ThreadpoolWork; // rax
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
    WPP_SF_s(*(_QWORD *)(v10 + 16), 13, WPP_476dff25f8043d358a001b332c2d8e81_Traceguids, Indent);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || v8[25] < 2u )
      return 2147500035LL;
    v11 = 14;
    v12 = "Fn";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v8 + 2), v11, WPP_476dff25f8043d358a001b332c2d8e81_Traceguids, v12);
    return 2147500035LL;
  }
  if ( !a4 )
  {
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || v8[25] < 2u )
      return 2147500035LL;
    v11 = 15;
    v12 = "phWorkItem";
    goto LABEL_12;
  }
  v14 = 0;
  *a4 = 0;
  ThreadpoolWork = CreateThreadpoolWork(a2, a3, (PTP_CALLBACK_ENVIRON)((char *)this + 8));
  *a4 = ThreadpoolWork;
  if ( ThreadpoolWork )
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
    WPP_SF_sd(*(_QWORD *)(v19 + 16), 16, (unsigned int)WPP_476dff25f8043d358a001b332c2d8e81_Traceguids, v18, v14);
LABEL_21:
    v17 = WPP_GLOBAL_Control;
  }
  if ( v17 != (_BYTE *)&WPP_GLOBAL_Control && ((v14 & 0x80000000) != 0 || v17[25] >= 6u) )
  {
    v20 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v21 + 16), 17, (unsigned int)WPP_476dff25f8043d358a001b332c2d8e81_Traceguids, v20, v14);
  }
  return v14;
}

```

## disassembly

```asm
0x18000b1f8  push    rbx
0x18000b1fa  push    rbp
0x18000b1fb  push    rsi
0x18000b1fc  push    rdi
0x18000b1fd  push    r12
0x18000b1ff  push    r14
0x18000b201  push    r15
0x18000b203  sub     rsp, 30h
0x18000b207  mov     rdi, r9
0x18000b20a  mov     rbp, r8
0x18000b20d  mov     rsi, rdx
0x18000b210  mov     r14, rcx
0x18000b213  mov     r10, cs:WPP_GLOBAL_Control
0x18000b21a  lea     r15, WPP_GLOBAL_Control
0x18000b221  lea     r12, WPP_476dff25f8043d358a001b332c2d8e81_Traceguids
0x18000b228  cmp     r10, r15
0x18000b22b  jz      short loc_18000B259
0x18000b22d  cmp     byte ptr [r10+19h], 6
0x18000b232  jb      short loc_18000B259
0x18000b234  mov     ecx, 1; int
0x18000b239  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000b23e  mov     rcx, [r10+10h]
0x18000b242  mov     edx, 0Dh
0x18000b247  mov     r9, rax
0x18000b24a  mov     r8, r12
0x18000b24d  call    WPP_SF_s
0x18000b252  mov     r10, cs:WPP_GLOBAL_Control
0x18000b259  test    rsi, rsi
0x18000b25c  jnz     short loc_18000B276
0x18000b25e  cmp     r10, r15
0x18000b261  jz      short loc_18000B29D
0x18000b263  cmp     byte ptr [r10+19h], 2
0x18000b268  jb      short loc_18000B29D
0x18000b26a  lea     edx, [rsi+0Eh]
0x18000b26d  lea     r9, aFn; "Fn"
0x18000b274  jmp     short loc_18000B291
0x18000b276  test    rdi, rdi
0x18000b279  jnz     short loc_18000B2A7
0x18000b27b  cmp     r10, r15
0x18000b27e  jz      short loc_18000B29D
0x18000b280  cmp     byte ptr [r10+19h], 2
0x18000b285  jb      short loc_18000B29D
0x18000b287  lea     edx, [rdi+0Fh]
0x18000b28a  lea     r9, aPhworkitem; "phWorkItem"
0x18000b291  mov     rcx, [r10+10h]
0x18000b295  mov     r8, r12
0x18000b298  call    WPP_SF_s
0x18000b29d  mov     eax, 80004003h
0x18000b2a2  jmp     loc_18000B358
0x18000b2a7  xor     ebx, ebx
0x18000b2a9  lea     r8, [r14+8]; pcbe
0x18000b2ad  mov     rdx, rbp; pv
0x18000b2b0  mov     [rdi], rbx
0x18000b2b3  mov     rcx, rsi; pfnwk
0x18000b2b6  call    cs:__imp_CreateThreadpoolWork
0x18000b2bc  mov     [rdi], rax
0x18000b2bf  test    rax, rax
0x18000b2c2  jnz     short loc_18000B31F
0x18000b2c4  call    cs:__imp_GetLastError
0x18000b2ca  test    eax, eax
0x18000b2cc  jg      short loc_18000B2D8
0x18000b2ce  call    cs:__imp_GetLastError
0x18000b2d4  mov     ebx, eax
0x18000b2d6  jmp     short loc_18000B2E7
0x18000b2d8  call    cs:__imp_GetLastError
0x18000b2de  movzx   ebx, ax
0x18000b2e1  or      ebx, 80070000h
0x18000b2e7  or      ebx, 80000000h
0x18000b2ed  mov     r10, cs:WPP_GLOBAL_Control
0x18000b2f4  cmp     r10, r15
0x18000b2f7  jz      short loc_18000B356
0x18000b2f9  cmp     byte ptr [r10+19h], 2
0x18000b2fe  jb      short loc_18000B326
0x18000b300  xor     ecx, ecx; int
0x18000b302  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000b307  mov     rcx, [r10+10h]
0x18000b30b  mov     edx, 10h
0x18000b310  mov     r9, rax
0x18000b313  mov     [rsp+68h+var_48], ebx
0x18000b317  mov     r8, r12
0x18000b31a  call    WPP_SF_sd
0x18000b31f  mov     r10, cs:WPP_GLOBAL_Control
0x18000b326  cmp     r10, r15
0x18000b329  jz      short loc_18000B356
0x18000b32b  test    ebx, ebx
0x18000b32d  js      short loc_18000B336
0x18000b32f  cmp     byte ptr [r10+19h], 6
0x18000b334  jb      short loc_18000B356
0x18000b336  or      ecx, 0FFFFFFFFh; int
0x18000b339  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000b33e  mov     rcx, [r10+10h]
0x18000b342  mov     edx, 11h
0x18000b347  mov     r9, rax
0x18000b34a  mov     [rsp+68h+var_48], ebx
0x18000b34e  mov     r8, r12
0x18000b351  call    WPP_SF_sd
0x18000b356  mov     eax, ebx
0x18000b358  add     rsp, 30h
0x18000b35c  pop     r15
0x18000b35e  pop     r14
0x18000b360  pop     r12
0x18000b362  pop     rdi
0x18000b363  pop     rsi
0x18000b364  pop     rbp
0x18000b365  pop     rbx
0x18000b366  retn
```
