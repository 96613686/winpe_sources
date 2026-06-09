# NetworkChangeMonitor::OnChangeNotification(int)

- ea: `0x18001b5fc`
- end: `0x18001bb10`
- name: `?OnChangeNotification@NetworkChangeMonitor@@AEAAJH@Z`
- size: `1300`
- prototype: `__int64 __fastcall(NetworkChangeMonitor *__hidden this, int)`
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001b5d0`
- `0x180028c90`
- `0x180084830`
- `0x1800c8610`

## callees

- `0x180017520`
- `0x18001b480`
- `0x18001b5fc`
- `0x18001bcd0`
- `0x1800cdd70`
- `0x1800cf008`
- `0x1800dae74`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001b835`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001b852`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001b86f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001b970`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001b835`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001b852`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001b86f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001b970`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b640`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b640`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b767`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b8e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b767`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b8e1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001baf1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001baf1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b717`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b79e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b717`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b79e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b809`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b809`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b732`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b740`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b74e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b784`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b732`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b740`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b74e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b784`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba3c`

## pseudocode

```c
__int64 __fastcall NetworkChangeMonitor::OnChangeNotification(NetworkChangeMonitor *this, int a2, int a3)
{
  void *v3; // rsi
  HANDLE v4; // r15
  NetworkChangeMonitor *v6; // r13
  _QWORD *v7; // rbx
  void *v8; // rax
  unsigned int *v9; // r14
  unsigned int v10; // edi
  signed int v11; // r12d
  BOOL v12; // edi
  void *v13; // r8
  int v14; // r13d
  HANDLE v15; // rbx
  HANDLE EventA; // rdi
  HANDLE v17; // r14
  void *v19; // rcx
  unsigned int v20; // edi
  struct _RTL_CRITICAL_SECTION *v21; // rdi
  signed int v22; // eax
  signed int v23; // eax
  signed int LastError; // eax
  signed int v25; // eax
  int CurrentNetworkKeys; // eax
  void *v27; // rcx
  void *v28; // rcx
  void *v29; // rcx
  int v30; // [rsp+30h] [rbp-48h]
  unsigned int v31; // [rsp+38h] [rbp-40h] BYREF
  int v32; // [rsp+3Ch] [rbp-3Ch]
  unsigned int v33; // [rsp+40h] [rbp-38h]
  int v34; // [rsp+44h] [rbp-34h]
  void *Buf1; // [rsp+48h] [rbp-30h] BYREF
  __int128 v36; // [rsp+50h] [rbp-28h] BYREF
  void *Buf2; // [rsp+60h] [rbp-18h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+68h] [rbp-10h]

  v32 = 0;
  v30 = 0;
  v3 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 16);
  v4 = 0;
  Buf1 = 0;
  v33 = 0;
  v31 = 0;
  v6 = this;
  if ( this != (NetworkChangeMonitor *)-16LL )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v30 = 1;
  }
  if ( a2 )
  {
    if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
      WPP_SF_(1053, 16, WPP_dfe9b3f9ae1d397b096fb7ae1e3b82b1_Traceguids);
    CurrentNetworkKeys = WxGetCurrentNetworkKeys((struct _WxNetworkKey **)&Buf1, &v31);
    v3 = Buf1;
    v11 = CurrentNetworkKeys;
    if ( CurrentNetworkKeys < 0 )
    {
      v32 = 892;
      goto LABEL_14;
    }
    v20 = v31;
    v7 = (_QWORD *)((char *)v6 + 144);
    v9 = (unsigned int *)((char *)v6 + 152);
LABEL_40:
    if ( *v7 )
      WxFreeHeapEx(v7);
    *v7 = v3;
    v3 = 0;
    *v9 = v20;
    *((_QWORD *)v6 + 17) = GetTickCount64();
    if ( *((_DWORD *)v6 + 32) )
      goto LABEL_14;
    v17 = 0;
    EventA = CreateEventA(0, 1, 0, 0);
    if ( EventA )
    {
      v15 = CreateEventA(0, 1, 0, 0);
      if ( v15 )
      {
        v17 = CreateEventA(0, 1, 0, 0);
        if ( v17 )
        {
          if ( *((_QWORD *)v6 + 11) || (v4 = CreateEventA(0, 1, 0, 0)) != 0 )
          {
            *((_DWORD *)v6 + 32) = 1;
            *((_QWORD *)v6 + 13) = EventA;
            *((_QWORD *)v6 + 12) = v15;
            *((_QWORD *)v6 + 14) = v17;
            if ( v4 )
              *((_QWORD *)v6 + 11) = v4;
            v11 = QueueRefCountWorkItem((int (*)(struct RefCountContext *))NetworkChangeMonitor::NotificationThread, v6);
            if ( v11 >= 0 )
            {
              v21 = (struct _RTL_CRITICAL_SECTION *)((char *)v6 + 16);
              v14 = v30;
              if ( v21 && v30 )
              {
                LeaveCriticalSection(v21);
                v14 = 0;
              }
              goto LABEL_15;
            }
            v27 = (void *)*((_QWORD *)v6 + 13);
            EventA = 0;
            v15 = 0;
            v17 = 0;
            if ( v27 )
            {
              CloseHandle(v27);
              *((_QWORD *)v6 + 13) = 0;
            }
            v28 = (void *)*((_QWORD *)v6 + 12);
            if ( v28 )
            {
              CloseHandle(v28);
              *((_QWORD *)v6 + 12) = 0;
            }
            v29 = (void *)*((_QWORD *)v6 + 14);
            if ( v29 )
            {
              CloseHandle(v29);
              *((_QWORD *)v6 + 14) = 0;
            }
            *((_QWORD *)v6 + 16) = 0;
            v32 = 1013;
LABEL_59:
            v14 = v30;
            goto LABEL_20;
          }
          LastError = GetLastError();
          v11 = LastError;
          if ( LastError > 0 )
            v11 = (unsigned __int16)LastError | 0x80070000;
          v32 = 986;
        }
        else
        {
          v25 = GetLastError();
          v11 = v25;
          if ( v25 > 0 )
            v11 = (unsigned __int16)v25 | 0x80070000;
          v32 = 976;
        }
      }
      else
      {
        v23 = GetLastError();
        v11 = v23;
        if ( v23 > 0 )
          v11 = (unsigned __int16)v23 | 0x80070000;
        v32 = 969;
      }
    }
    else
    {
      v15 = 0;
      v22 = GetLastError();
      v11 = v22;
      if ( v22 > 0 )
        v11 = (unsigned __int16)v22 | 0x80070000;
      v32 = 962;
    }
    if ( v11 >= 0 )
      v11 = -2147418113;
    goto LABEL_59;
  }
  v7 = (_QWORD *)((char *)v6 + 144);
  Buf1 = 0;
  v8 = (void *)*((_QWORD *)v6 + 18);
  v9 = (unsigned int *)((char *)v6 + 152);
  v10 = *((_DWORD *)v6 + 38);
  Buf2 = v8;
  v32 = 0;
  v31 = 0;
  if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
  {
    v36 = (unsigned __int64)v8;
    if ( !v8 || (LODWORD(this) = 0xFFFF, LOWORD(v8) = (_WORD)v10 << 7, WORD4(v36) = -1, v10 << 7 <= 0xFFFF) )
      WORD4(v36) = (_WORD)v8;
    WPP_SF_d_HEX_((_DWORD)this, 15, a3, v10, (__int64)&v36);
  }
  v11 = WxGetCurrentNetworkKeys((struct _WxNetworkKey **)&Buf1, &v31);
  if ( v11 < 0 )
  {
    v13 = Buf1;
    v12 = 0;
    v32 = 820;
  }
  else
  {
    v34 = 0;
    v3 = Buf1;
    v33 = v31;
    v12 = v31 <= v10 && v31 >= v10 && !memcmp_0(Buf1, Buf2, (unsigned __int64)v31 << 7);
    v11 = 0;
    v13 = 0;
  }
  if ( v13 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v13);
    else
      HeapFree(g_hWxProcessHeap, 0, v13);
  }
  if ( v11 < 0 )
  {
    v32 = 905;
    goto LABEL_14;
  }
  if ( !v12 )
  {
    if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
      WPP_SF_(1053, 17, WPP_dfe9b3f9ae1d397b096fb7ae1e3b82b1_Traceguids);
    if ( !*((_DWORD *)v6 + 33) )
    {
      v19 = (void *)*((_QWORD *)v6 + 14);
      *((_DWORD *)v6 + 33) = 1;
      if ( v19 )
        SetEvent(v19);
    }
    v20 = v33;
    goto LABEL_40;
  }
LABEL_14:
  v14 = v30;
LABEL_15:
  if ( v3 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v3);
    else
      HeapFree(g_hWxProcessHeap, 0, v3);
    v15 = 0;
    EventA = 0;
    goto LABEL_22;
  }
  v15 = 0;
  v17 = 0;
  EventA = 0;
LABEL_20:
  if ( v17 )
    CloseHandle(v17);
LABEL_22:
  if ( EventA )
    CloseHandle(EventA);
  if ( v15 )
    CloseHandle(v15);
  if ( v14 && lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001b5fc  push    rbp
0x18001b5fe  push    rbx
0x18001b5ff  push    rsi
0x18001b600  push    rdi
0x18001b601  push    r12
0x18001b603  push    r13
0x18001b605  push    r14
0x18001b607  push    r15
0x18001b609  mov     rbp, rsp
0x18001b60c  sub     rsp, 78h
0x18001b610  xor     eax, eax
0x18001b612  mov     [rbp+var_3C], 0
0x18001b619  lea     rdi, [rcx+10h]
0x18001b61d  mov     [rbp+var_48], eax
0x18001b620  xor     esi, esi
0x18001b622  mov     [rbp+lpCriticalSection], rdi
0x18001b626  xor     r15d, r15d
0x18001b629  mov     [rbp+Buf1], rsi
0x18001b62d  mov     [rbp+var_38], eax
0x18001b630  mov     ebx, edx
0x18001b632  mov     [rbp+var_40], eax
0x18001b635  mov     r13, rcx
0x18001b638  test    rdi, rdi
0x18001b63b  jz      short loc_18001B64D
0x18001b63d  mov     rcx, rdi; lpCriticalSection
0x18001b640  call    cs:__imp_EnterCriticalSection
0x18001b646  mov     [rbp+var_48], 1
0x18001b64d  test    ebx, ebx
0x18001b64f  jnz     loc_18001B9C7
0x18001b655  lea     rbx, [r13+90h]
0x18001b65c  mov     [rbp+Buf1], rsi
0x18001b660  mov     rax, [rbx]
0x18001b663  lea     r14, [r13+98h]
0x18001b66a  mov     edi, [r14]
0x18001b66d  mov     [rbp+Buf2], rax
0x18001b671  mov     [rbp+var_3C], esi
0x18001b674  mov     [rbp+var_40], esi
0x18001b677  test    byte ptr cs:xmmword_180107A60+3, 20h
0x18001b67e  jnz     loc_18001BA80
0x18001b684  lea     rdx, [rbp+var_40]; unsigned int *
0x18001b688  lea     rcx, [rbp+Buf1]; struct _WxNetworkKey **
0x18001b68c  call    ?WxGetCurrentNetworkKeys@@YAJPEAPEAU_WxNetworkKey@@PEAK@Z; WxGetCurrentNetworkKeys(_WxNetworkKey * *,ulong *)
0x18001b691  mov     r12d, eax
0x18001b694  test    eax, eax
0x18001b696  js      loc_18001B8FC
0x18001b69c  mov     eax, [rbp+var_40]
0x18001b69f  mov     [rbp+var_34], esi
0x18001b6a2  mov     [rbp+var_38], esi
0x18001b6a5  mov     [rbp+var_34], esi
0x18001b6a8  mov     [rbp+var_38], esi
0x18001b6ab  mov     rsi, [rbp+Buf1]
0x18001b6af  mov     [rbp+var_38], eax
0x18001b6b2  cmp     eax, edi
0x18001b6b4  ja      short loc_18001B6D3
0x18001b6b6  jb      short loc_18001B6D3
0x18001b6b8  mov     rdx, [rbp+Buf2]; Buf2
0x18001b6bc  mov     r8d, eax
0x18001b6bf  shl     r8, 7; Size
0x18001b6c3  mov     rcx, rsi; Buf1
0x18001b6c6  call    memcmp_0
0x18001b6cb  test    eax, eax
0x18001b6cd  jz      loc_18001B7A9
0x18001b6d3  xor     edi, edi
0x18001b6d5  xor     r12d, r12d
0x18001b6d8  xor     r8d, r8d; lpMem
0x18001b6db  test    r8, r8
0x18001b6de  jnz     loc_18001B78C
0x18001b6e4  test    r12d, r12d
0x18001b6e7  js      loc_18001BACA
0x18001b6ed  test    edi, edi
0x18001b6ef  jz      loc_18001B7C7
0x18001b6f5  mov     r13d, [rbp+var_48]
0x18001b6f9  test    rsi, rsi
0x18001b6fc  jz      short loc_18001B723
0x18001b6fe  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x18001b705  jnz     loc_18001BAFC
0x18001b70b  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18001b712  mov     r8, rsi; lpMem
0x18001b715  xor     edx, edx; dwFlags
0x18001b717  call    cs:__imp_HeapFree
0x18001b71d  xor     ebx, ebx
0x18001b71f  xor     edi, edi
0x18001b721  jmp     short loc_18001B738
0x18001b723  xor     ebx, ebx
0x18001b725  xor     r14d, r14d
0x18001b728  xor     edi, edi
0x18001b72a  test    r14, r14
0x18001b72d  jz      short loc_18001B738
0x18001b72f  mov     rcx, r14; hObject
0x18001b732  call    cs:__imp_CloseHandle
0x18001b738  test    r15, r15
0x18001b73b  jz      short loc_18001B746
0x18001b73d  mov     rcx, r15; hObject
0x18001b740  call    cs:__imp_CloseHandle
0x18001b746  test    rdi, rdi
0x18001b749  jz      short loc_18001B754
0x18001b74b  mov     rcx, rdi; hObject
0x18001b74e  call    cs:__imp_CloseHandle
0x18001b754  test    rbx, rbx
0x18001b757  jnz     short loc_18001B781
0x18001b759  test    r13d, r13d
0x18001b75c  jz      short loc_18001B76D
0x18001b75e  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18001b762  test    rcx, rcx
0x18001b765  jz      short loc_18001B76D
0x18001b767  call    cs:__imp_LeaveCriticalSection
0x18001b76d  mov     eax, r12d
0x18001b770  add     rsp, 78h
0x18001b774  pop     r15
0x18001b776  pop     r14
0x18001b778  pop     r13
0x18001b77a  pop     r12
0x18001b77c  pop     rdi
0x18001b77d  pop     rsi
0x18001b77e  pop     rbx
0x18001b77f  pop     rbp
0x18001b780  retn
0x18001b781  mov     rcx, rbx; hObject
0x18001b784  call    cs:__imp_CloseHandle
0x18001b78a  jmp     short loc_18001B759
0x18001b78c  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, r15d; int g_fWxHeapExtensionInitialized
0x18001b793  jnz     short loc_18001B7B3
0x18001b795  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18001b79c  xor     edx, edx; dwFlags
0x18001b79e  call    cs:__imp_HeapFree
0x18001b7a4  jmp     loc_18001B6E4
0x18001b7a9  mov     edi, 1
0x18001b7ae  jmp     loc_18001B6D5
0x18001b7b3  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x18001b7ba  mov     rcx, r8
0x18001b7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7c2  jmp     loc_18001B6E4
0x18001b7c7  test    byte ptr cs:xmmword_180107A60+3, 20h
0x18001b7ce  jnz     loc_18001BAD6
0x18001b7d4  cmp     [r13+84h], r15d
0x18001b7db  jnz     short loc_18001B7F5
0x18001b7dd  mov     rcx, [r13+70h]; hEvent
0x18001b7e1  mov     dword ptr [r13+84h], 1
0x18001b7ec  test    rcx, rcx
0x18001b7ef  jnz     loc_18001BAF1
0x18001b7f5  mov     edi, [rbp+var_38]
0x18001b7f8  cmp     [rbx], r15
0x18001b7fb  jnz     loc_18001B8EF
0x18001b801  mov     [rbx], rsi
0x18001b804  xor     esi, esi
0x18001b806  mov     [r14], edi
0x18001b809  call    cs:__imp_GetTickCount64
0x18001b80f  mov     [r13+88h], rax
0x18001b816  cmp     [r13+80h], esi
0x18001b81d  jnz     loc_18001B6F5
0x18001b823  lea     r12d, [rsi+1]
0x18001b827  xor     r9d, r9d; lpName
0x18001b82a  mov     edx, r12d; bManualReset
0x18001b82d  xor     r8d, r8d; bInitialState
0x18001b830  xor     ecx, ecx; lpEventAttributes
0x18001b832  xor     r14d, r14d
0x18001b835  call    cs:__imp_CreateEventA
0x18001b83b  mov     rdi, rax
0x18001b83e  test    rax, rax
0x18001b841  jz      loc_18001B90E
0x18001b847  xor     r9d, r9d; lpName
0x18001b84a  xor     r8d, r8d; bInitialState
0x18001b84d  mov     edx, r12d; bManualReset
0x18001b850  xor     ecx, ecx; lpEventAttributes
0x18001b852  call    cs:__imp_CreateEventA
0x18001b858  mov     rbx, rax
0x18001b85b  test    rax, rax
0x18001b85e  jz      loc_18001B944
0x18001b864  xor     r9d, r9d; lpName
0x18001b867  xor     r8d, r8d; bInitialState
0x18001b86a  mov     edx, r12d; bManualReset
0x18001b86d  xor     ecx, ecx; lpEventAttributes
0x18001b86f  call    cs:__imp_CreateEventA
0x18001b875  mov     r14, rax
0x18001b878  test    rax, rax
0x18001b87b  jz      loc_18001B9A3
0x18001b881  cmp     [r13+58h], rsi
0x18001b885  jz      loc_18001B965
0x18001b88b  mov     [r13+80h], r12d
0x18001b892  mov     [r13+68h], rdi
0x18001b896  mov     [r13+60h], rbx
0x18001b89a  mov     [r13+70h], r14
0x18001b89e  test    r15, r15
0x18001b8a1  jz      short loc_18001B8AA
0x18001b8a3  mov     [r13+58h], r15
0x18001b8a7  xor     r15d, r15d
0x18001b8aa  mov     rdx, r13; struct RefCountContext *
0x18001b8ad  lea     rcx, ?NotificationThread@NetworkChangeMonitor@@CAJPEAVRefCountContext@@@Z; int (*)(struct RefCountContext *)
0x18001b8b4  call    ?QueueRefCountWorkItem@@YAJP6AJPEAVRefCountContext@@@Z0@Z; QueueRefCountWorkItem(long (*)(RefCountContext *),RefCountContext *)
0x18001b8b9  mov     r12d, eax
0x18001b8bc  test    eax, eax
0x18001b8be  js      loc_18001BA06
0x18001b8c4  lea     rdi, [r13+10h]
0x18001b8c8  mov     r13d, [rbp+var_48]
0x18001b8cc  test    rdi, rdi
0x18001b8cf  jz      loc_18001B6F9
0x18001b8d5  test    r13d, r13d
0x18001b8d8  jz      loc_18001B6F9
0x18001b8de  mov     rcx, rdi; lpCriticalSection
0x18001b8e1  call    cs:__imp_LeaveCriticalSection
0x18001b8e7  xor     r13d, r13d
0x18001b8ea  jmp     loc_18001B6F9
0x18001b8ef  mov     rcx, rbx
0x18001b8f2  call    WxFreeHeapEx
0x18001b8f7  jmp     loc_18001B801
0x18001b8fc  mov     r8, [rbp+Buf1]
0x18001b900  xor     edi, edi
0x18001b902  mov     [rbp+var_3C], 334h
0x18001b909  jmp     loc_18001B6DB
0x18001b90e  xor     ebx, ebx
0x18001b910  call    cs:__imp_GetLastError
0x18001b916  mov     r12d, eax
0x18001b919  test    eax, eax
0x18001b91b  jle     short loc_18001B928
0x18001b91d  movzx   r12d, ax
0x18001b921  or      r12d, 80070000h
0x18001b928  mov     [rbp+var_3C], 3C2h
0x18001b92f  test    r12d, r12d
0x18001b932  mov     eax, 8000FFFFh
0x18001b937  cmovns  r12d, eax
0x18001b93b  mov     r13d, [rbp+var_48]
0x18001b93f  jmp     loc_18001B72A
0x18001b944  call    cs:__imp_GetLastError
0x18001b94a  mov     r12d, eax
0x18001b94d  test    eax, eax
0x18001b94f  jle     short loc_18001B95C
0x18001b951  movzx   r12d, ax
0x18001b955  or      r12d, 80070000h
0x18001b95c  mov     [rbp+var_3C], 3C9h
0x18001b963  jmp     short loc_18001B92F
0x18001b965  xor     r9d, r9d; lpName
0x18001b968  xor     r8d, r8d; bInitialState
0x18001b96b  mov     edx, r12d; bManualReset
0x18001b96e  xor     ecx, ecx; lpEventAttributes
0x18001b970  call    cs:__imp_CreateEventA
0x18001b976  mov     r15, rax
0x18001b979  test    rax, rax
0x18001b97c  jnz     loc_18001B88B
0x18001b982  call    cs:__imp_GetLastError
0x18001b988  mov     r12d, eax
0x18001b98b  test    eax, eax
0x18001b98d  jle     short loc_18001B99A
0x18001b98f  movzx   r12d, ax
0x18001b993  or      r12d, 80070000h
0x18001b99a  mov     [rbp+var_3C], 3DAh
0x18001b9a1  jmp     short loc_18001B92F
0x18001b9a3  call    cs:__imp_GetLastError
0x18001b9a9  mov     r12d, eax
0x18001b9ac  test    eax, eax
0x18001b9ae  jle     short loc_18001B9BB
0x18001b9b0  movzx   r12d, ax
0x18001b9b4  or      r12d, 80070000h
0x18001b9bb  mov     [rbp+var_3C], 3D0h
0x18001b9c2  jmp     loc_18001B92F
0x18001b9c7  test    byte ptr cs:xmmword_180107A60+3, 20h
0x18001b9ce  jnz     loc_18001BA59
0x18001b9d4  lea     rdx, [rbp+var_40]; unsigned int *
0x18001b9d8  lea     rcx, [rbp+Buf1]; struct _WxNetworkKey **
0x18001b9dc  call    ?WxGetCurrentNetworkKeys@@YAJPEAPEAU_WxNetworkKey@@PEAK@Z; WxGetCurrentNetworkKeys(_WxNetworkKey * *,ulong *)
0x18001b9e1  mov     rsi, [rbp+Buf1]
0x18001b9e5  mov     r12d, eax
0x18001b9e8  test    eax, eax
0x18001b9ea  js      loc_18001BA74
0x18001b9f0  mov     edi, [rbp+var_40]
0x18001b9f3  lea     rbx, [r13+90h]
0x18001b9fa  lea     r14, [r13+98h]
0x18001ba01  jmp     loc_18001B7F8
0x18001ba06  mov     rcx, [r13+68h]; hObject
0x18001ba0a  xor     edi, edi
0x18001ba0c  xor     ebx, ebx
0x18001ba0e  xor     r14d, r14d
0x18001ba11  test    rcx, rcx
0x18001ba14  jz      short loc_18001BA20
0x18001ba16  call    cs:__imp_CloseHandle
0x18001ba1c  mov     [r13+68h], rbx
0x18001ba20  mov     rcx, [r13+60h]; hObject
0x18001ba24  test    rcx, rcx
0x18001ba27  jz      short loc_18001BA33
0x18001ba29  call    cs:__imp_CloseHandle
0x18001ba2f  mov     [r13+60h], rbx
0x18001ba33  mov     rcx, [r13+70h]; hObject
0x18001ba37  test    rcx, rcx
0x18001ba3a  jz      short loc_18001BA46
0x18001ba3c  call    cs:__imp_CloseHandle
0x18001ba42  mov     [r13+70h], rbx
0x18001ba46  mov     [r13+80h], rbx
0x18001ba4d  mov     [rbp+var_3C], 3F5h
0x18001ba54  jmp     loc_18001B93B
0x18001ba59  mov     edx, 10h
0x18001ba5e  lea     r8, WPP_dfe9b3f9ae1d397b096fb7ae1e3b82b1_Traceguids
0x18001ba65  mov     ecx, 41Dh
0x18001ba6a  call    WPP_SF_
0x18001ba6f  jmp     loc_18001B9D4
0x18001ba74  mov     [rbp+var_3C], 37Ch
0x18001ba7b  jmp     loc_18001B6F5
0x18001ba80  xorps   xmm0, xmm0
0x18001ba83  movups  [rbp+var_28], xmm0
0x18001ba87  mov     qword ptr [rbp+var_28], rax
0x18001ba8b  test    rax, rax
0x18001ba8e  jz      short loc_18001BAA2
  ... truncated ...
```
