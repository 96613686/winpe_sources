# WxRegNotifyCreate

- ea: `0x18001812c`
- end: `0x1800183a5`
- name: `WxRegNotifyCreate`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180017f18`

## callees

- `0x180016c84`
- `0x18001812c`
- `0x180018420`
- `0x180018ee8`
- `0x180018fe0`
- `0x1800a2660`
- `0x1800cdd7c`
- `0x1800dafac`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001827e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001827e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001822a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001822a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001817a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001817a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018328`

## pseudocode

```c
__int64 __fastcall WxRegNotifyCreate(
        _QWORD *a1,
        _WORD *a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8)
{
  _QWORD *v9; // rdi
  HANDLE v10; // rcx
  char *v11; // rax
  char *v12; // rsi
  _WORD *v13; // rcx
  __int64 v14; // r15
  int v15; // ebp
  signed int ThreadpoolWait; // ebx
  HANDLE EventW; // rax
  void *v19; // rdi
  signed int LastError; // eax
  __int64 v21; // [rsp+20h] [rbp-88h]

  v9 = a1;
  if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
    WPP_SF_qSlDdqqq((_DWORD)a1, (_DWORD)a2, a3, *a1, (__int64)a2);
  v10 = g_hWxProcessHeap;
  *a8 = 0;
  v11 = (char *)HeapAlloc(v10, 0, 0x58u);
  v12 = v11;
  if ( !v11 )
  {
    ThreadpoolWait = -2147024882;
    goto LABEL_14;
  }
  memset_0(v11, 0, 0x58u);
  *((_QWORD *)v12 + 1) = qword_1800E7D10;
  *(_QWORD *)v12 = 0;
  *((_QWORD *)v12 + 8) = 0;
  *((_QWORD *)v12 + 10) = 0;
  *((_QWORD *)v12 + 9) = 0;
  if ( *((_DWORD *)v12 + 4) )
  {
    v13 = (_WORD *)*((_QWORD *)v12 + 1);
    *((_DWORD *)v12 + 4) = 0;
    *v13 = 0;
  }
  if ( a2 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    v15 = 0;
    if ( (_DWORD)v14 )
    {
      v15 = CWxString::ExtendBuffer((CWxString *)(v12 + 8), (int)v14 + *((_DWORD *)v12 + 4) + 1);
      if ( v15 >= 0 )
      {
        v19 = (void *)(*((_QWORD *)v12 + 1) + 2LL * *((unsigned int *)v12 + 4));
        memcpy_0(v19, a2, 2LL * (unsigned int)v14);
        *((_WORD *)v19 + (unsigned int)v14) = 0;
        *((_DWORD *)v12 + 4) += v14;
        v9 = a1;
      }
    }
    ThreadpoolWait = v15;
    if ( v15 >= 0 )
    {
      *((_DWORD *)v12 + 6) = 1;
      *((_QWORD *)v12 + 6) = CHttpPolicyExtensionEntry::RegChangeCallback;
      *((_QWORD *)v12 + 7) = a7;
      *((_DWORD *)v12 + 7) = 4;
      *((_QWORD *)v12 + 5) = 0;
      EventW = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)v12 + 9) = EventW;
      if ( EventW )
      {
        ThreadpoolWait = WxCreateThreadpoolWait(
                           (void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int))FailFastThreadpoolWaitCallback<&void WxRegNotifyOnChange(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)>,
                           v12,
                           0,
                           (struct _TP_WAIT **)v12 + 10);
        if ( ThreadpoolWait >= 0 )
        {
          *(_QWORD *)v12 = *v9;
          *v9 = 0;
          WxSetThreadpoolWait(*((struct _TP_WAIT **)v12 + 10), *((void **)v12 + 9), 0);
          SetEvent(*((HANDLE *)v12 + 9));
          *a8 = v12;
LABEL_14:
          v15 = ThreadpoolWait;
          goto LABEL_15;
        }
      }
      else
      {
        LastError = GetLastError();
        ThreadpoolWait = LastError;
        if ( LastError > 0 )
          ThreadpoolWait = (unsigned __int16)LastError | 0x80070000;
        if ( ThreadpoolWait >= 0 )
          ThreadpoolWait = -2147418113;
      }
      v15 = ThreadpoolWait;
    }
  }
  else
  {
    v15 = -2147024809;
    ThreadpoolWait = -2147024809;
  }
  WxRegNotifyDestroy(v12);
LABEL_15:
  if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
    WPP_SF_d(1053, 11, WPP_6f599994933c3ba3def3ffac0e032c83_Traceguids, (unsigned int)ThreadpoolWait, v21);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001812c  mov     [rsp+arg_0], rcx
0x180018131  push    rbx
0x180018132  push    rbp
0x180018133  push    rsi
0x180018134  push    rdi
0x180018135  push    r12
0x180018137  push    r13
0x180018139  push    r14
0x18001813b  push    r15
0x18001813d  sub     rsp, 68h
0x180018141  xor     ebx, ebx
0x180018143  mov     r12, rdx
0x180018146  mov     [rsp+0A8h+arg_2C], ebx
0x18001814d  mov     rdi, rcx
0x180018150  test    byte ptr cs:xmmword_180107A60+3, 20h
0x180018157  mov     r13, [rsp+0A8h+arg_38]
0x18001815f  jnz     loc_180018353
0x180018165  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18001816c  mov     ebp, 58h ; 'X'
0x180018171  mov     r8d, ebp; dwBytes
0x180018174  mov     [r13+0], rbx
0x180018178  xor     edx, edx; dwFlags
0x18001817a  call    cs:__imp_HeapAlloc
0x180018180  mov     rsi, rax
0x180018183  test    rax, rax
0x180018186  jz      loc_180018313
0x18001818c  mov     r8d, ebp; Size
0x18001818f  xor     edx, edx; Val
0x180018191  mov     rcx, rax; void *
0x180018194  call    memset_0
0x180018199  lea     rax, qword_1800E7D10
0x1800181a0  mov     [rsi+8], rax
0x1800181a4  lea     r14, [rsi+8]
0x1800181a8  mov     [rsi], rbx
0x1800181ab  mov     [rsi+40h], rbx
0x1800181af  mov     [rsi+50h], rbx
0x1800181b3  mov     [rsi+48h], rbx
0x1800181b7  cmp     [r14+8], ebx
0x1800181bb  jz      short loc_1800181C7
0x1800181bd  mov     rcx, [r14]
0x1800181c0  mov     [r14+8], ebx
0x1800181c4  mov     [rcx], bx
0x1800181c7  test    r12, r12
0x1800181ca  jz      loc_180018377
0x1800181d0  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800181d4  inc     r15
0x1800181d7  cmp     [r12+r15*2], bx
0x1800181dc  jnz     short loc_1800181D4
0x1800181de  mov     ebp, ebx
0x1800181e0  test    r15d, r15d
0x1800181e3  jnz     loc_1800182C1
0x1800181e9  mov     ebx, ebp
0x1800181eb  test    ebp, ebp
0x1800181ed  js      loc_18001837E
0x1800181f3  lea     rax, ?RegChangeCallback@CHttpPolicyExtensionEntry@@CAHPEAXJ@Z; CHttpPolicyExtensionEntry::RegChangeCallback(void *,long)
0x1800181fa  mov     dword ptr [rsi+18h], 1
0x180018201  mov     [rsi+30h], rax
0x180018205  xor     r9d, r9d; lpName
0x180018208  mov     rax, [rsp+0A8h+arg_30]
0x180018210  xor     r8d, r8d; bInitialState
0x180018213  xor     edx, edx; bManualReset
0x180018215  mov     [rsi+38h], rax
0x180018219  xor     ecx, ecx; lpEventAttributes
0x18001821b  mov     dword ptr [rsi+1Ch], 4
0x180018222  mov     qword ptr [rsi+28h], 0
0x18001822a  call    cs:__imp_CreateEventW
0x180018230  mov     [rsi+48h], rax
0x180018234  test    rax, rax
0x180018237  jz      loc_180018328
0x18001823d  lea     r9, [rsi+50h]; struct _TP_WAIT **
0x180018241  xor     r8d, r8d; struct _TP_CALLBACK_ENVIRON_V3 *
0x180018244  mov     rdx, rsi; void *
0x180018247  lea     rcx, ??$FailFastThreadpoolWaitCallback@$1?WxRegNotifyOnChange@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int)
0x18001824e  call    ?WxCreateThreadpoolWait@@YAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z1PEAU_TP_CALLBACK_ENVIRON_V3@@PEAPEAU2@@Z; WxCreateThreadpoolWait(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long),void *,_TP_CALLBACK_ENVIRON_V3 *,_TP_WAIT * *)
0x180018253  mov     ebx, eax
0x180018255  test    eax, eax
0x180018257  js      loc_18001838B
0x18001825d  mov     rax, [rdi]
0x180018260  xor     r8d, r8d; struct _FILETIME *
0x180018263  mov     [rsi], rax
0x180018266  mov     qword ptr [rdi], 0
0x18001826d  mov     rdx, [rsi+48h]; void *
0x180018271  mov     rcx, [rsi+50h]; struct _TP_WAIT *
0x180018275  call    ?WxSetThreadpoolWait@@YAXPEAU_TP_WAIT@@PEAXPEAU_FILETIME@@@Z; WxSetThreadpoolWait(_TP_WAIT *,void *,_FILETIME *)
0x18001827a  mov     rcx, [rsi+48h]; hEvent
0x18001827e  call    cs:__imp_SetEvent
0x180018284  mov     [r13+0], rsi
0x180018288  mov     ebp, ebx
0x18001828a  test    byte ptr cs:xmmword_180107A60+3, 20h
0x180018291  jnz     short loc_1800182A6
0x180018293  mov     eax, ebp
0x180018295  add     rsp, 68h
0x180018299  pop     r15
0x18001829b  pop     r14
0x18001829d  pop     r13
0x18001829f  pop     r12
0x1800182a1  pop     rdi
0x1800182a2  pop     rsi
0x1800182a3  pop     rbp
0x1800182a4  pop     rbx
0x1800182a5  retn
0x1800182a6  mov     edx, 0Bh
0x1800182ab  lea     r8, WPP_6f599994933c3ba3def3ffac0e032c83_Traceguids
0x1800182b2  mov     ecx, 41Dh
0x1800182b7  mov     r9d, ebx
0x1800182ba  call    WPP_SF_d
0x1800182bf  jmp     short loc_180018293
0x1800182c1  mov     edx, [r14+8]
0x1800182c5  mov     rcx, r14; this
0x1800182c8  inc     edx
0x1800182ca  add     edx, r15d; unsigned int
0x1800182cd  call    ?ExtendBuffer@CWxString@@QEAAJK@Z; CWxString::ExtendBuffer(ulong)
0x1800182d2  mov     ebp, eax
0x1800182d4  test    eax, eax
0x1800182d6  js      loc_1800181E9
0x1800182dc  mov     ecx, [r14+8]
0x1800182e0  mov     rdx, r12; Src
0x1800182e3  mov     rax, [r14]
0x1800182e6  lea     rdi, [rax+rcx*2]
0x1800182ea  mov     eax, r15d
0x1800182ed  mov     rcx, rdi; void *
0x1800182f0  lea     rbx, [rax+rax]
0x1800182f4  mov     r8, rbx; Size
0x1800182f7  call    memcpy_0
0x1800182fc  xor     eax, eax
0x1800182fe  mov     [rbx+rdi], ax
0x180018302  add     [r14+8], r15d
0x180018306  mov     rdi, [rsp+0A8h+arg_0]
0x18001830e  jmp     loc_1800181E9
0x180018313  mov     ebx, 8007000Eh
0x180018318  mov     [rsp+0A8h+arg_2C], 6Fh ; 'o'
0x180018323  jmp     loc_180018288
0x180018328  call    cs:__imp_GetLastError
0x18001832e  mov     ebx, eax
0x180018330  test    eax, eax
0x180018332  jle     short loc_18001833D
0x180018334  movzx   ebx, ax
0x180018337  or      ebx, 80070000h
0x18001833d  test    ebx, ebx
0x18001833f  js      short loc_180018346
0x180018341  mov     ebx, 8000FFFFh
0x180018346  mov     [rsp+0A8h+arg_2C], 80h
0x180018351  jmp     short loc_180018396
0x180018353  mov     rax, [rsp+0A8h+arg_30]
0x18001835b  mov     r9, [rcx]
0x18001835e  mov     [rsp+0A8h+var_58], r13
0x180018363  mov     [rsp+0A8h+var_60], rax
0x180018368  mov     [rsp+0A8h+var_88], r12
0x18001836d  call    WPP_SF_qSlDdqqq
0x180018372  jmp     loc_180018165
0x180018377  mov     ebp, 80070057h
0x18001837c  mov     ebx, ebp
0x18001837e  mov     [rsp+0A8h+arg_2C], 76h ; 'v'
0x180018389  jmp     short loc_180018398
0x18001838b  mov     [rsp+0A8h+arg_2C], 85h
0x180018396  mov     ebp, ebx
0x180018398  mov     rcx, rsi; lpMem
0x18001839b  call    WxRegNotifyDestroy
0x1800183a0  jmp     loc_18001828A
```
