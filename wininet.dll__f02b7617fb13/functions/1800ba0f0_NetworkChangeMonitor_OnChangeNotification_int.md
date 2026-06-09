# NetworkChangeMonitor::OnChangeNotification(int)

- ea: `0x1800ba0f0`
- end: `0x1800ba6ad`
- name: `?OnChangeNotification@NetworkChangeMonitor@@AEAAJH@Z`
- size: `1469`
- prototype: `__int64 __fastcall(NetworkChangeMonitor *__hidden this, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800ba090`
- `0x1800ba0c0`
- `0x1801b1710`

## callees

- `0x180027ec0`
- `0x1800701d0`
- `0x1800b9f6c`
- `0x1800ba0f0`
- `0x1800ba6c0`
- `0x1801c9c31`
- `0x1801cc3d0`
- `0x1801e3c78`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ba2c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ba421`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ba2c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ba421`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ba140`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ba140`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800ba378`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800ba397`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800ba3b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800ba471`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800ba378`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800ba397`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800ba3b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800ba471`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ba6a2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ba6a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ba20c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ba241`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ba20c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ba241`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800ba34e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800ba34e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba25c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba27a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba2a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba5da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba5ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba604`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba25c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba27a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba2a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba5da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba5ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba604`

## pseudocode

```c
__int64 __fastcall NetworkChangeMonitor::OnChangeNotification(NetworkChangeMonitor *this, int a2, int a3)
{
  int v5; // ecx
  void *v6; // rbx
  struct _RTL_CRITICAL_SECTION *v7; // r13
  unsigned int v8; // edi
  unsigned int v9; // esi
  void *v10; // rax
  signed int v11; // r12d
  int v12; // esi
  void *v13; // r8
  HANDLE v14; // rdi
  HANDLE EventA; // rsi
  HANDLE v16; // r15
  unsigned int *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdx
  int (*v24)(struct RefCountContext *); // rcx
  struct RefCountContext *v25; // r12
  void *v26; // rcx
  HANDLE v27; // rax
  __int64 v28; // rdx
  int v29; // eax
  int LastError; // eax
  int v31; // eax
  int v32; // eax
  int CurrentNetworkKeys; // eax
  struct RefCountContext *v34; // rbx
  void *v35; // rcx
  void *v36; // rcx
  void *v37; // rcx
  unsigned int v38[4]; // [rsp+38h] [rbp-19h] BYREF
  __int128 v39; // [rsp+48h] [rbp-9h] BYREF
  int v40; // [rsp+58h] [rbp+7h]
  void *Buf1; // [rsp+60h] [rbp+Fh] BYREF
  unsigned int *v42; // [rsp+68h] [rbp+17h]
  struct RefCountContext *v43; // [rsp+70h] [rbp+1Fh]
  void *Buf2; // [rsp+78h] [rbp+27h]

  v43 = this;
  v5 = 0;
  DWORD1(v39) = 0;
  v40 = 0;
  v6 = 0;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  Buf1 = 0;
  v38[0] = 0;
  v8 = 0;
  if ( this != (NetworkChangeMonitor *)-16LL )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v5 = 0;
    v40 = 1;
  }
  if ( a2 )
  {
    if ( (BYTE3(xmmword_180266B60) & 0x20) != 0 )
      WPP_SF_(1053, 16, WPP_dfe9b3f9ae1d397b096fb7ae1e3b82b1_Traceguids);
    CurrentNetworkKeys = WxGetCurrentNetworkKeys((struct _WxNetworkKey **)&Buf1, v38);
    v6 = Buf1;
    v11 = CurrentNetworkKeys;
    if ( CurrentNetworkKeys < 0 )
    {
      DWORD1(v39) = 892;
      goto LABEL_16;
    }
    v8 = v38[0];
    goto LABEL_37;
  }
  Buf1 = 0;
  v9 = *((_DWORD *)this + 38);
  v42 = (unsigned int *)((char *)this + 152);
  v10 = (void *)*((_QWORD *)this + 18);
  Buf2 = v10;
  DWORD1(v39) = 0;
  v38[0] = 0;
  if ( (BYTE3(xmmword_180266B60) & 0x20) != 0 )
  {
    v39 = (unsigned __int64)v10;
    if ( v10 )
    {
      v5 = 0xFFFF;
      if ( v9 << 7 > 0xFFFF )
        WORD4(v39) = -1;
      else
        WORD4(v39) = (_WORD)v9 << 7;
    }
    else
    {
      WORD4(v39) = 0;
    }
    WPP_SF_d_HEX_(v5, 15, a3, v9, (__int64)&v39);
  }
  v11 = WxGetCurrentNetworkKeys((struct _WxNetworkKey **)&Buf1, v38);
  if ( v11 >= 0 )
  {
    v8 = v38[0];
    v11 = 0;
    *(_QWORD *)&v39 = 0;
    if ( v38[0] < v9 || v38[0] > v9 )
    {
      v6 = Buf1;
    }
    else
    {
      v6 = Buf1;
      if ( !memcmp_0(Buf1, Buf2, (unsigned __int64)v38[0] << 7) )
      {
        v12 = 1;
LABEL_10:
        v13 = 0;
        goto LABEL_11;
      }
    }
    v12 = 0;
    goto LABEL_10;
  }
  v13 = Buf1;
  v12 = 0;
  DWORD1(v39) = 820;
LABEL_11:
  if ( v13 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v13);
    else
      HeapFree(g_hWxProcessHeap, 0, v13);
  }
  if ( v11 < 0 )
  {
    DWORD1(v39) = 905;
    goto LABEL_16;
  }
  if ( !v12 )
  {
    if ( (BYTE3(xmmword_180266B60) & 0x20) != 0 )
      WPP_SF_(1053, 17, WPP_dfe9b3f9ae1d397b096fb7ae1e3b82b1_Traceguids);
    if ( !*((_DWORD *)this + 33) )
    {
      v26 = (void *)*((_QWORD *)this + 14);
      *((_DWORD *)this + 33) = 1;
      if ( !v26 )
      {
        v18 = (unsigned int *)((char *)this + 152);
LABEL_38:
        if ( *((_QWORD *)this + 18) )
        {
          WxFreeHeapEx((char *)this + 144);
          v18 = v42;
        }
        *((_QWORD *)this + 18) = v6;
        v6 = 0;
        *v18 = v8;
        *((_QWORD *)this + 17) = GetTickCount64();
        if ( !*((_DWORD *)this + 32) )
        {
          v16 = 0;
          EventA = CreateEventA(0, 1, 0, 0);
          if ( !EventA )
          {
            v14 = 0;
            LastError = WxGetLastError(v20, v19);
            v11 = LastError;
            if ( LastError > 0 )
              v11 = (unsigned __int16)LastError | 0x80070000;
            DWORD1(v39) = 962;
            if ( v11 >= 0 )
              v11 = -2147418113;
            goto LABEL_21;
          }
          v14 = CreateEventA(0, 1, 0, 0);
          if ( !v14 )
          {
            v31 = WxGetLastError(v22, v21);
            v11 = v31;
            if ( v31 > 0 )
              v11 = (unsigned __int16)v31 | 0x80070000;
            DWORD1(v39) = 969;
            if ( v11 >= 0 )
              v11 = -2147418113;
            goto LABEL_21;
          }
          v16 = CreateEventA(0, 1, 0, 0);
          if ( !v16 )
          {
            v32 = WxGetLastError(v24, v23);
            v11 = v32;
            if ( v32 > 0 )
              v11 = (unsigned __int16)v32 | 0x80070000;
            DWORD1(v39) = 976;
            if ( v11 >= 0 )
              v11 = -2147418113;
            goto LABEL_21;
          }
          v25 = v43;
          if ( !*((_QWORD *)v43 + 11) )
          {
            v27 = CreateEventA(0, 1, 0, 0);
            if ( !v27 )
            {
              v29 = WxGetLastError(v24, v28);
              v11 = v29;
              if ( v29 > 0 )
                v11 = (unsigned __int16)v29 | 0x80070000;
              DWORD1(v39) = 986;
              if ( v11 >= 0 )
                v11 = -2147418113;
              goto LABEL_21;
            }
            *((_QWORD *)v25 + 11) = v27;
          }
          *((_QWORD *)v25 + 13) = EventA;
          *((_QWORD *)v25 + 12) = v14;
          EventA = 0;
          *((_QWORD *)v25 + 14) = v16;
          v14 = 0;
          v16 = 0;
          *((_DWORD *)v25 + 32) = 1;
          v11 = QueueRefCountWorkItem(v24, v25);
          if ( v11 < 0 )
          {
            v34 = v43;
            v35 = (void *)*((_QWORD *)v43 + 13);
            if ( v35 )
            {
              CloseHandle(v35);
              *((_QWORD *)v34 + 13) = 0;
            }
            v36 = (void *)*((_QWORD *)v34 + 12);
            if ( v36 )
            {
              CloseHandle(v36);
              *((_QWORD *)v34 + 12) = 0;
            }
            v37 = (void *)*((_QWORD *)v34 + 14);
            if ( v37 )
            {
              CloseHandle(v37);
              *((_QWORD *)v34 + 14) = 0;
            }
            *((_QWORD *)v34 + 16) = 0;
            DWORD1(v39) = 1013;
            goto LABEL_21;
          }
          if ( v7 && v40 )
          {
            LeaveCriticalSection(v7);
            v40 = 0;
          }
        }
        goto LABEL_16;
      }
      SetEvent(v26);
    }
LABEL_37:
    v18 = (unsigned int *)((char *)this + 152);
    v42 = (unsigned int *)((char *)this + 152);
    goto LABEL_38;
  }
LABEL_16:
  if ( v6 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v6);
    else
      HeapFree(g_hWxProcessHeap, 0, v6);
    v14 = 0;
    EventA = 0;
    goto LABEL_23;
  }
  v14 = 0;
  v16 = 0;
  EventA = 0;
LABEL_21:
  if ( v16 )
    CloseHandle(v16);
LABEL_23:
  if ( EventA )
    CloseHandle(EventA);
  if ( v14 )
    CloseHandle(v14);
  if ( v40 && v7 )
    LeaveCriticalSection(v7);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800ba0f0  mov     rax, rsp
0x1800ba0f3  push    rbp
0x1800ba0f4  push    r13
0x1800ba0f6  lea     rbp, [rax-5Fh]
0x1800ba0fa  sub     rsp, 98h
0x1800ba101  mov     [rax+10h], rbx
0x1800ba105  mov     [rax+18h], rsi
0x1800ba109  mov     esi, edx
0x1800ba10b  mov     [rax+20h], rdi
0x1800ba10f  mov     [rax-20h], r14
0x1800ba113  mov     [rax-28h], r15
0x1800ba117  mov     r15, rcx
0x1800ba11a  mov     [rbp+57h+var_38], rcx
0x1800ba11e  xor     ecx, ecx
0x1800ba120  mov     dword ptr [rbp+57h+var_60+4], ecx
0x1800ba123  mov     r14d, ecx
0x1800ba126  mov     [rbp+57h+var_50], ecx
0x1800ba129  mov     ebx, ecx
0x1800ba12b  lea     r13, [r15+10h]
0x1800ba12f  mov     [rbp+57h+Buf1], rcx
0x1800ba133  mov     [rbp+57h+var_70], ecx
0x1800ba136  mov     edi, ecx
0x1800ba138  test    r13, r13
0x1800ba13b  jz      short loc_1800BA14F
0x1800ba13d  mov     rcx, r13; lpCriticalSection
0x1800ba140  call    cs:__imp_EnterCriticalSection
0x1800ba146  xor     ecx, ecx
0x1800ba148  mov     [rbp+57h+var_50], 1
0x1800ba14f  mov     [rsp+90h], r12
0x1800ba157  test    esi, esi
0x1800ba159  jnz     loc_1800BA541
0x1800ba15f  lea     rax, [r15+98h]
0x1800ba166  mov     [rbp+57h+Buf1], rcx
0x1800ba16a  mov     esi, [rax]
0x1800ba16c  mov     [rbp+57h+var_40], rax
0x1800ba170  mov     rax, [r15+90h]
0x1800ba177  mov     [rbp+57h+Buf2], rax
0x1800ba17b  mov     dword ptr [rbp+57h+var_60+4], ecx
0x1800ba17e  mov     [rbp+57h+var_70], ecx
0x1800ba181  test    byte ptr cs:xmmword_180266B60+3, 20h
0x1800ba188  jnz     loc_1800BA57F
0x1800ba18e  lea     rdx, [rbp+57h+var_70]; unsigned int *
0x1800ba192  lea     rcx, [rbp+57h+Buf1]; struct _WxNetworkKey **
0x1800ba196  call    ?WxGetCurrentNetworkKeys@@YAJPEAPEAU_WxNetworkKey@@PEAK@Z; WxGetCurrentNetworkKeys(_WxNetworkKey * *,ulong *)
0x1800ba19b  mov     r12d, eax
0x1800ba19e  test    eax, eax
0x1800ba1a0  js      loc_1800BA660
0x1800ba1a6  mov     edi, [rbp+57h+var_70]
0x1800ba1a9  xor     r12d, r12d
0x1800ba1ac  mov     dword ptr [rbp+57h+var_60+4], r12d
0x1800ba1b0  mov     dword ptr [rbp+57h+var_60], r12d
0x1800ba1b4  mov     dword ptr [rbp+57h+var_60+4], r12d
0x1800ba1b8  mov     dword ptr [rbp+57h+var_60], r12d
0x1800ba1bc  cmp     edi, esi
0x1800ba1be  jb      loc_1800BA672
0x1800ba1c4  ja      loc_1800BA672
0x1800ba1ca  mov     rbx, [rbp+57h+Buf1]
0x1800ba1ce  mov     r8d, edi
0x1800ba1d1  mov     rdx, [rbp+57h+Buf2]; Buf2
0x1800ba1d5  mov     rcx, rbx; Buf1
0x1800ba1d8  shl     r8, 7; Size
0x1800ba1dc  call    memcmp_0
0x1800ba1e1  test    eax, eax
0x1800ba1e3  jnz     loc_1800BA2DE
0x1800ba1e9  mov     esi, 1
0x1800ba1ee  xor     r8d, r8d; lpMem
0x1800ba1f1  test    r8, r8
0x1800ba1f4  jz      short loc_1800BA212
0x1800ba1f6  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, r14d; int g_fWxHeapExtensionInitialized
0x1800ba1fd  jnz     loc_1800BA2FE
0x1800ba203  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800ba20a  xor     edx, edx; dwFlags
0x1800ba20c  call    cs:__imp_HeapFree
0x1800ba212  test    r12d, r12d
0x1800ba215  js      loc_1800BA67B
0x1800ba21b  test    esi, esi
0x1800ba21d  jz      loc_1800BA312
0x1800ba223  test    rbx, rbx
0x1800ba226  jz      short loc_1800BA24D
0x1800ba228  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x1800ba22f  jnz     loc_1800BA2E6
0x1800ba235  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800ba23c  mov     r8, rbx; lpMem
0x1800ba23f  xor     edx, edx; dwFlags
0x1800ba241  call    cs:__imp_HeapFree
0x1800ba247  xor     edi, edi
0x1800ba249  xor     esi, esi
0x1800ba24b  jmp     short loc_1800BA262
0x1800ba24d  xor     edi, edi
0x1800ba24f  xor     r15d, r15d
0x1800ba252  xor     esi, esi
0x1800ba254  test    r15, r15
0x1800ba257  jz      short loc_1800BA262
0x1800ba259  mov     rcx, r15; hObject
0x1800ba25c  call    cs:__imp_CloseHandle
0x1800ba262  mov     r15, [rsp+0A0h+var_20]
0x1800ba26a  mov     rbx, [rsp+0A0h+arg_8]
0x1800ba272  test    r14, r14
0x1800ba275  jz      short loc_1800BA280
0x1800ba277  mov     rcx, r14; hObject
0x1800ba27a  call    cs:__imp_CloseHandle
0x1800ba280  mov     r14, [rsp+0A0h+var_18]
0x1800ba288  test    rsi, rsi
0x1800ba28b  jz      short loc_1800BA296
0x1800ba28d  mov     rcx, rsi; hObject
0x1800ba290  call    cs:__imp_CloseHandle
0x1800ba296  mov     rsi, [rsp+0A0h+arg_10]
0x1800ba29e  test    rdi, rdi
0x1800ba2a1  jz      short loc_1800BA2AC
0x1800ba2a3  mov     rcx, rdi; hObject
0x1800ba2a6  call    cs:__imp_CloseHandle
0x1800ba2ac  cmp     [rbp+57h+var_50], 0
0x1800ba2b0  mov     rdi, [rsp+0A0h+arg_18]
0x1800ba2b8  jz      short loc_1800BA2C8
0x1800ba2ba  test    r13, r13
0x1800ba2bd  jz      short loc_1800BA2C8
0x1800ba2bf  mov     rcx, r13; lpCriticalSection
0x1800ba2c2  call    cs:__imp_LeaveCriticalSection
0x1800ba2c8  mov     eax, r12d
0x1800ba2cb  mov     r12, [rsp+90h]
0x1800ba2d3  add     rsp, 98h
0x1800ba2da  pop     r13
0x1800ba2dc  pop     rbp
0x1800ba2dd  retn
0x1800ba2de  mov     esi, r12d
0x1800ba2e1  jmp     loc_1800BA1EE
0x1800ba2e6  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x1800ba2ed  mov     rcx, rbx
0x1800ba2f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba2f5  xor     edi, edi
0x1800ba2f7  xor     esi, esi
0x1800ba2f9  jmp     loc_1800BA262
0x1800ba2fe  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x1800ba305  mov     rcx, r8
0x1800ba308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba30d  jmp     loc_1800BA212
0x1800ba312  test    byte ptr cs:xmmword_180266B60+3, 20h
0x1800ba319  jnz     loc_1800BA687
0x1800ba31f  cmp     [r15+84h], r14d
0x1800ba326  jz      loc_1800BA440
0x1800ba32c  lea     rax, [r15+98h]
0x1800ba333  mov     [rbp+57h+var_40], rax
0x1800ba337  lea     rsi, [r15+90h]
0x1800ba33e  cmp     [rsi], r14
0x1800ba341  jnz     loc_1800BA42F
0x1800ba347  mov     [rsi], rbx
0x1800ba34a  xor     ebx, ebx
0x1800ba34c  mov     [rax], edi
0x1800ba34e  call    cs:__imp_GetTickCount64
0x1800ba354  mov     [r15+88h], rax
0x1800ba35b  cmp     [r15+80h], ebx
0x1800ba362  jnz     loc_1800BA223
0x1800ba368  xor     r9d, r9d; lpName
0x1800ba36b  xor     r8d, r8d; bInitialState
0x1800ba36e  mov     edx, 1; bManualReset
0x1800ba373  xor     ecx, ecx; lpEventAttributes
0x1800ba375  xor     r15d, r15d
0x1800ba378  call    cs:__imp_CreateEventA
0x1800ba37e  mov     rsi, rax
0x1800ba381  test    rax, rax
0x1800ba384  jz      loc_1800BA4B2
0x1800ba38a  xor     r9d, r9d; lpName
0x1800ba38d  xor     r8d, r8d; bInitialState
0x1800ba390  mov     edx, 1; bManualReset
0x1800ba395  xor     ecx, ecx; lpEventAttributes
0x1800ba397  call    cs:__imp_CreateEventA
0x1800ba39d  mov     rdi, rax
0x1800ba3a0  test    rax, rax
0x1800ba3a3  jz      loc_1800BA4E3
0x1800ba3a9  xor     r9d, r9d; lpName
0x1800ba3ac  xor     r8d, r8d; bInitialState
0x1800ba3af  mov     edx, 1; bManualReset
0x1800ba3b4  xor     ecx, ecx; lpEventAttributes
0x1800ba3b6  call    cs:__imp_CreateEventA
0x1800ba3bc  mov     r15, rax
0x1800ba3bf  test    rax, rax
0x1800ba3c2  jz      loc_1800BA512
0x1800ba3c8  mov     r12, [rbp+57h+var_38]
0x1800ba3cc  cmp     [r12+58h], rbx
0x1800ba3d1  jz      loc_1800BA464
0x1800ba3d7  mov     [r12+68h], rsi
0x1800ba3dc  mov     rdx, r12; struct RefCountContext *
0x1800ba3df  mov     [r12+60h], rdi
0x1800ba3e4  xor     esi, esi
0x1800ba3e6  mov     [r12+70h], r15
0x1800ba3eb  xor     edi, edi
0x1800ba3ed  xor     r15d, r15d
0x1800ba3f0  mov     dword ptr [r12+80h], 1
0x1800ba3fc  call    ?QueueRefCountWorkItem@@YAJP6AJPEAVRefCountContext@@@Z0@Z; QueueRefCountWorkItem(long (*)(RefCountContext *),RefCountContext *)
0x1800ba401  mov     r12d, eax
0x1800ba404  test    eax, eax
0x1800ba406  js      loc_1800BA5CD
0x1800ba40c  test    r13, r13
0x1800ba40f  jz      loc_1800BA223
0x1800ba415  cmp     [rbp+57h+var_50], ebx
0x1800ba418  jz      loc_1800BA223
0x1800ba41e  mov     rcx, r13; lpCriticalSection
0x1800ba421  call    cs:__imp_LeaveCriticalSection
0x1800ba427  mov     [rbp+57h+var_50], ebx
0x1800ba42a  jmp     loc_1800BA223
0x1800ba42f  mov     rcx, rsi
0x1800ba432  call    WxFreeHeapEx
0x1800ba437  mov     rax, [rbp+57h+var_40]
0x1800ba43b  jmp     loc_1800BA347
0x1800ba440  mov     rcx, [r15+70h]; hEvent
0x1800ba444  mov     dword ptr [r15+84h], 1
0x1800ba44f  test    rcx, rcx
0x1800ba452  jnz     loc_1800BA6A2
0x1800ba458  lea     rax, [r15+98h]
0x1800ba45f  jmp     loc_1800BA337
0x1800ba464  xor     r9d, r9d; lpName
0x1800ba467  xor     r8d, r8d; bInitialState
0x1800ba46a  mov     edx, 1; bManualReset
0x1800ba46f  xor     ecx, ecx; lpEventAttributes
0x1800ba471  call    cs:__imp_CreateEventA
0x1800ba477  mov     r14, rax
0x1800ba47a  test    rax, rax
0x1800ba47d  jnz     loc_1800BA572
0x1800ba483  call    WxGetLastError
0x1800ba488  mov     r12d, eax
0x1800ba48b  test    eax, eax
0x1800ba48d  jle     short loc_1800BA49A
0x1800ba48f  movzx   r12d, ax
0x1800ba493  or      r12d, 80070000h
0x1800ba49a  test    r12d, r12d
0x1800ba49d  mov     dword ptr [rbp+57h+var_60+4], 3DAh
0x1800ba4a4  mov     eax, 8000FFFFh
0x1800ba4a9  cmovns  r12d, eax
0x1800ba4ad  jmp     loc_1800BA254
0x1800ba4b2  xor     edi, edi
0x1800ba4b4  call    WxGetLastError
0x1800ba4b9  mov     r12d, eax
0x1800ba4bc  test    eax, eax
0x1800ba4be  jle     short loc_1800BA4CB
0x1800ba4c0  movzx   r12d, ax
0x1800ba4c4  or      r12d, 80070000h
0x1800ba4cb  test    r12d, r12d
0x1800ba4ce  mov     dword ptr [rbp+57h+var_60+4], 3C2h
0x1800ba4d5  mov     eax, 8000FFFFh
0x1800ba4da  cmovns  r12d, eax
0x1800ba4de  jmp     loc_1800BA254
0x1800ba4e3  call    WxGetLastError
0x1800ba4e8  mov     r12d, eax
0x1800ba4eb  test    eax, eax
0x1800ba4ed  jle     short loc_1800BA4FA
0x1800ba4ef  movzx   r12d, ax
0x1800ba4f3  or      r12d, 80070000h
0x1800ba4fa  test    r12d, r12d
0x1800ba4fd  mov     dword ptr [rbp+57h+var_60+4], 3C9h
0x1800ba504  mov     eax, 8000FFFFh
0x1800ba509  cmovns  r12d, eax
0x1800ba50d  jmp     loc_1800BA254
0x1800ba512  call    WxGetLastError
0x1800ba517  mov     r12d, eax
0x1800ba51a  test    eax, eax
0x1800ba51c  jle     short loc_1800BA529
0x1800ba51e  movzx   r12d, ax
0x1800ba522  or      r12d, 80070000h
0x1800ba529  test    r12d, r12d
0x1800ba52c  mov     dword ptr [rbp+57h+var_60+4], 3D0h
0x1800ba533  mov     eax, 8000FFFFh
0x1800ba538  cmovns  r12d, eax
0x1800ba53c  jmp     loc_1800BA254
0x1800ba541  test    byte ptr cs:xmmword_180266B60+3, 20h
0x1800ba548  jnz     loc_1800BA627
0x1800ba54e  lea     rdx, [rbp+57h+var_70]; unsigned int *
0x1800ba552  lea     rcx, [rbp+57h+Buf1]; struct _WxNetworkKey **
0x1800ba556  call    ?WxGetCurrentNetworkKeys@@YAJPEAPEAU_WxNetworkKey@@PEAK@Z; WxGetCurrentNetworkKeys(_WxNetworkKey * *,ulong *)
0x1800ba55b  mov     rbx, [rbp+57h+Buf1]
0x1800ba55f  mov     r12d, eax
0x1800ba562  test    eax, eax
0x1800ba564  js      loc_1800BA642
0x1800ba56a  mov     edi, [rbp+57h+var_70]
0x1800ba56d  jmp     loc_1800BA32C
0x1800ba572  mov     [r12+58h], rax
0x1800ba577  xor     r14d, r14d
0x1800ba57a  jmp     loc_1800BA3D7
0x1800ba57f  xorps   xmm0, xmm0
0x1800ba582  movups  [rbp+57h+var_60], xmm0
0x1800ba586  mov     qword ptr [rbp+57h+var_60], rax
0x1800ba58a  test    rax, rax
0x1800ba58d  jz      loc_1800BA64E
0x1800ba593  mov     eax, esi
0x1800ba595  mov     ecx, 0FFFFh
0x1800ba59a  shl     eax, 7
0x1800ba59d  cmp     eax, ecx
0x1800ba59f  ja      loc_1800BA657
0x1800ba5a5  mov     word ptr [rbp+57h+var_60+8], ax
0x1800ba5a9  movaps  xmm0, [rbp+57h+var_60]
0x1800ba5ad  lea     rax, [rbp+57h+var_60]
0x1800ba5b1  mov     edx, 0Fh
0x1800ba5b6  movdqa  [rbp+57h+var_60], xmm0
0x1800ba5bb  mov     r9d, esi
0x1800ba5be  mov     [rsp+20h], rax
0x1800ba5c3  call    WPP_SF_d_HEX_
0x1800ba5c8  jmp     loc_1800BA18E
0x1800ba5cd  mov     rbx, [rbp+57h+var_38]
0x1800ba5d1  mov     rcx, [rbx+68h]; hObject
0x1800ba5d5  test    rcx, rcx
0x1800ba5d8  jz      short loc_1800BA5E6
  ... truncated ...
```
