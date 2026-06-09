# ClientCreateContext(_WLAN_CLIENT_CONTEXT * *)

- ea: `0x180006100`
- end: `0x18000639a`
- name: `?ClientCreateContext@@YAKPEAPEAU_WLAN_CLIENT_CONTEXT@@@Z`
- size: `666`
- prototype: `unsigned int __fastcall(struct _WLAN_CLIENT_CONTEXT **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180005d50`

## callees

- `0x180005610`
- `0x180006100`
- `0x1800063a0`
- `0x180006934`
- `0x18001a5bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000614e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000614e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006135`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006135`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800061a2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800061a2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800061bf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800061bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006317`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000629d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000629d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006359`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006359`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180006187`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180006187`

## pseudocode

```c
__int64 __fastcall ClientCreateContext(struct _WLAN_CLIENT_CONTEXT **a1)
{
  union DOT11_OUI_HEADER *v2; // rcx
  char *v3; // rbx
  HANDLE ProcessHeap; // rax
  DWORD LastError; // eax
  unsigned int v6; // r14d
  HANDLE EventW; // rax
  __int64 v9; // rdx
  void *v10; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 38, WPP_797f1b088bb039a5f91226960c081484_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = 0;
  if ( a1 )
  {
    ProcessHeap = GetProcessHeap();
    if ( ProcessHeap )
    {
      v3 = (char *)HeapAlloc(ProcessHeap, 8u, 0x130u);
      if ( !v3 )
        SetLastError(8u);
    }
    if ( v3 )
    {
      memset_0(v3, 0, 0x130u);
      LastError = RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)(v3 + 40), 0x70u);
      v6 = LastError;
      if ( LastError )
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
        {
          v9 = 41;
          goto LABEL_28;
        }
      }
      else
      {
        EventW = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)v3 + 26) = EventW;
        if ( EventW )
        {
          InitializeCriticalSection((LPCRITICAL_SECTION)(v3 + 168));
          *a1 = (struct _WLAN_CLIENT_CONTEXT *)v3;
          v3 = 0;
LABEL_11:
          v2 = WPP_GLOBAL_Control;
          goto LABEL_12;
        }
        LastError = GetLastError();
        v6 = LastError;
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
        {
          v9 = 42;
          goto LABEL_28;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        v9 = 40;
LABEL_28:
        WPP_SF_d(*((_QWORD *)v2 + 12), v9, WPP_797f1b088bb039a5f91226960c081484_Traceguids, LastError);
        goto LABEL_11;
      }
    }
  }
  else
  {
    v6 = 87;
    if ( v2 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control && *((_BYTE *)v2 + 105) && (*((_BYTE *)v2 + 108) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)v2 + 12), 39, WPP_797f1b088bb039a5f91226960c081484_Traceguids);
      goto LABEL_11;
    }
  }
LABEL_12:
  if ( v3 )
  {
    v10 = (void *)*((_QWORD *)v3 + 26);
    if ( v10 )
      CloseHandle(v10);
    FreeWLMem(v3);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v2 + 105) >= 4u
    && (*((_BYTE *)v2 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v2 + 12), 44, WPP_797f1b088bb039a5f91226960c081484_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x180006100  push    rbx
0x180006102  push    rsi
0x180006103  push    rdi
0x180006104  push    r14
0x180006106  sub     rsp, 28h
0x18000610a  mov     rsi, rcx
0x18000610d  lea     rdi, WPP_GLOBAL_Control
0x180006114  mov     rcx, cs:WPP_GLOBAL_Control
0x18000611b  cmp     rcx, rdi
0x18000611e  jz      short loc_18000612A
0x180006120  cmp     byte ptr [rcx+69h], 4
0x180006124  jnb     loc_1800062E7
0x18000612a  xor     ebx, ebx
0x18000612c  test    rsi, rsi
0x18000612f  jz      loc_180006247
0x180006135  call    cs:__imp_GetProcessHeap
0x18000613b  test    rax, rax
0x18000613e  jz      short loc_180006160
0x180006140  mov     edx, 8; dwFlags
0x180006145  mov     r8d, 130h; dwBytes
0x18000614b  mov     rcx, rax; hHeap
0x18000614e  call    cs:__imp_HeapAlloc
0x180006154  mov     rbx, rax
0x180006157  test    rax, rax
0x18000615a  jz      loc_180006312
0x180006160  mov     [rsp+48h+arg_0], rbx
0x180006165  test    rbx, rbx
0x180006168  jz      loc_180006275
0x18000616e  xor     edx, edx; Val
0x180006170  mov     r8d, 130h; Size
0x180006176  mov     rcx, rbx; void *
0x180006179  call    memset_0
0x18000617e  lea     rcx, [rbx+28h]; pAsync
0x180006182  mov     edx, 70h ; 'p'; Size
0x180006187  call    cs:__imp_RpcAsyncInitializeHandle
0x18000618d  mov     r14d, eax
0x180006190  test    eax, eax
0x180006192  jnz     loc_180006322
0x180006198  xor     r9d, r9d; lpName
0x18000619b  xor     r8d, r8d; bInitialState
0x18000619e  xor     edx, edx; bManualReset
0x1800061a0  xor     ecx, ecx; lpEventAttributes
0x1800061a2  call    cs:__imp_CreateEventW
0x1800061a8  mov     [rbx+0D0h], rax
0x1800061af  test    rax, rax
0x1800061b2  jz      loc_18000629D
0x1800061b8  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x1800061bf  call    cs:__imp_InitializeCriticalSection
0x1800061c5  jmp     short loc_180006216
0x1800061c7  mov     r14d, eax
0x1800061ca  lea     rax, WPP_GLOBAL_Control
0x1800061d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061d8  cmp     rcx, rax
0x1800061db  jz      short loc_180006208
0x1800061dd  cmp     byte ptr [rcx+69h], 1
0x1800061e1  jb      short loc_180006208
0x1800061e3  test    byte ptr [rcx+6Ch], 2
0x1800061e7  jz      short loc_180006208
0x1800061e9  mov     edx, 2Bh ; '+'
0x1800061ee  mov     r9d, r14d
0x1800061f1  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x1800061f8  mov     rcx, [rcx+60h]
0x1800061fc  call    WPP_SF_d
0x180006201  mov     rcx, cs:WPP_GLOBAL_Control
0x180006208  lea     rdi, WPP_GLOBAL_Control
0x18000620f  mov     rbx, [rsp+48h+arg_0]
0x180006214  jmp     short loc_180006222
0x180006216  mov     [rsi], rbx
0x180006219  xor     ebx, ebx
0x18000621b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006222  test    rbx, rbx
0x180006225  jnz     loc_18000634D
0x18000622b  cmp     rcx, rdi
0x18000622e  jz      short loc_18000623A
0x180006230  cmp     byte ptr [rcx+69h], 4
0x180006234  jnb     loc_180006373
0x18000623a  mov     eax, r14d
0x18000623d  add     rsp, 28h
0x180006241  pop     r14
0x180006243  pop     rdi
0x180006244  pop     rsi
0x180006245  pop     rbx
0x180006246  retn
0x180006247  mov     r14d, 57h ; 'W'
0x18000624d  cmp     rcx, rdi
0x180006250  jz      short loc_180006222
0x180006252  cmp     byte ptr [rcx+69h], 1
0x180006256  jb      short loc_180006222
0x180006258  test    byte ptr [rcx+6Ch], 2
0x18000625c  jz      short loc_180006222
0x18000625e  mov     edx, 27h ; '''
0x180006263  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x18000626a  mov     rcx, [rcx+60h]
0x18000626e  call    WPP_SF_
0x180006273  jmp     short loc_18000621B
0x180006275  call    cs:__imp_GetLastError
0x18000627b  mov     r14d, eax
0x18000627e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006285  cmp     rcx, rdi
0x180006288  jz      short loc_180006222
0x18000628a  cmp     byte ptr [rcx+69h], 1
0x18000628e  jb      short loc_180006222
0x180006290  test    byte ptr [rcx+6Ch], 2
0x180006294  jz      short loc_180006222
0x180006296  mov     edx, 28h ; '('
0x18000629b  jmp     short loc_1800062CF
0x18000629d  call    cs:__imp_GetLastError
0x1800062a3  mov     r14d, eax
0x1800062a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062ad  cmp     rcx, rdi
0x1800062b0  jz      loc_180006222
0x1800062b6  cmp     byte ptr [rcx+69h], 1
0x1800062ba  jb      loc_180006222
0x1800062c0  test    byte ptr [rcx+6Ch], 2
0x1800062c4  jz      loc_180006222
0x1800062ca  mov     edx, 2Ah ; '*'
0x1800062cf  mov     r9d, eax
0x1800062d2  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x1800062d9  mov     rcx, [rcx+60h]
0x1800062dd  call    WPP_SF_d
0x1800062e2  jmp     loc_18000621B
0x1800062e7  test    byte ptr [rcx+6Ch], 2
0x1800062eb  jz      loc_18000612A
0x1800062f1  mov     edx, 26h ; '&'
0x1800062f6  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x1800062fd  mov     rcx, [rcx+60h]
0x180006301  call    WPP_SF_
0x180006306  mov     rcx, cs:WPP_GLOBAL_Control
0x18000630d  jmp     loc_18000612A
0x180006312  mov     ecx, 8; dwErrCode
0x180006317  call    cs:__imp_SetLastError
0x18000631d  jmp     loc_180006160
0x180006322  mov     rcx, cs:WPP_GLOBAL_Control
0x180006329  cmp     rcx, rdi
0x18000632c  jz      loc_180006222
0x180006332  cmp     byte ptr [rcx+69h], 1
0x180006336  jb      loc_180006222
0x18000633c  test    byte ptr [rcx+6Ch], 2
0x180006340  jz      loc_180006222
0x180006346  mov     edx, 29h ; ')'
0x18000634b  jmp     short loc_1800062CF
0x18000634d  mov     rcx, [rbx+0D0h]; hObject
0x180006354  test    rcx, rcx
0x180006357  jz      short loc_18000635F
0x180006359  call    cs:__imp_CloseHandle
0x18000635f  mov     rcx, rbx
0x180006362  call    FreeWLMem
0x180006367  mov     rcx, cs:WPP_GLOBAL_Control
0x18000636e  jmp     loc_18000622B
0x180006373  test    byte ptr [rcx+6Ch], 2
0x180006377  jz      loc_18000623A
0x18000637d  mov     edx, 2Ch ; ','
0x180006382  mov     r9d, r14d
0x180006385  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x18000638c  mov     rcx, [rcx+60h]
0x180006390  call    WPP_SF_d
0x180006395  jmp     loc_18000623A
```
