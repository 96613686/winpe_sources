# WaitForWERWorkers(ulong)

- ea: `0x14000d0e4`
- end: `0x14000d67d`
- name: `?WaitForWERWorkers@@YAJK@Z`
- size: `1433`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x14000cfa8`

## callees

- `0x140003224`
- `0x1400044a8`
- `0x140004af8`
- `0x140007888`
- `0x14000d0e4`
- `0x14000d968`
- `0x14000e318`
- `0x14000e340`
- `0x14000e458`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000d11c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000d138`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000d11c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000d138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d2ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d2ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d537`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d29f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d44f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d4bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d29f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d44f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d4bd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000d2f6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000d2f6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14000d1e9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14000d1e9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14000d3bc`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14000d3bc`

## pseudocode

```c
__int64 __fastcall WaitForWERWorkers(unsigned int a1)
{
  __m128i si128; // xmm6
  ULONGLONG v2; // rbx
  void *v3; // rdi
  ULONGLONG TickCount64; // rsi
  ULONGLONG v5; // rax
  __int64 v6; // r8
  ULONGLONG v7; // r13
  int WERProcesses; // eax
  unsigned int v9; // ebx
  void **v10; // rsi
  __int64 v11; // r15
  void **v12; // r12
  DWORD *v13; // rbx
  char *v14; // r14
  HANDLE v15; // rcx
  unsigned __int64 v16; // r15
  unsigned __int64 v17; // rdx
  char *v18; // rsi
  char **v19; // rcx
  HANDLE *p_hObject; // rax
  signed int v21; // eax
  __int64 v22; // rax
  void **v23; // rbx
  HANDLE *v24; // r15
  void *v25; // rcx
  HANDLE *v26; // r14
  DWORD v27; // ebx
  _QWORD *v28; // rcx
  __int64 v29; // rsi
  void *v30; // rcx
  signed int LastError; // eax
  void *v33; // rcx
  HANDLE hObject; // [rsp+20h] [rbp-49h] BYREF
  __m128i v35; // [rsp+28h] [rbp-41h] BYREF
  __int64 v36; // [rsp+38h] [rbp-31h]
  void *v37[2]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v38; // [rsp+50h] [rbp-19h]
  HANDLE *lpHandles[2]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v40; // [rsp+68h] [rbp-1h]
  ULONGLONG v42; // [rsp+D8h] [rbp+6Fh]
  ULONGLONG v43; // [rsp+E0h] [rbp+77h]
  void *v44; // [rsp+E8h] [rbp+7Fh] BYREF

  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *(__m128i *)v37 = si128;
  v2 = a1;
  v38 = -1;
  v3 = (void *)si128.m128i_i64[0];
  TickCount64 = GetTickCount64();
  v43 = TickCount64;
  v42 = v2;
LABEL_2:
  v5 = GetTickCount64();
  v7 = v5 - TickCount64;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v6, v5 - TickCount64);
  if ( v7 >= v2 )
    goto LABEL_86;
  v37[1] = v3;
  WERProcesses = GetWERProcesses((__int64)v37);
  v9 = WERProcesses;
  if ( WERProcesses < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids,
        (unsigned int)WERProcesses);
    v33 = v37[0];
    if ( v37[0] != (void *)-1LL )
LABEL_96:
      operator delete(v33, (const struct std::nothrow_t *)&std::nothrow);
    return v9;
  }
  v3 = v37[0];
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids,
      ((char *)v37[1] - (char *)v37[0]) >> 2);
  v35 = si128;
  v10 = (void **)si128.m128i_i64[1];
  v11 = -1;
  v12 = (void **)si128.m128i_i64[0];
  v13 = (DWORD *)v3;
  v36 = -1;
  while ( 1 )
  {
    if ( v13 == v37[1] )
    {
      if ( v12 == v10 )
      {
        utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::~vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>(&v35);
        if ( v3 != (void *)-1LL )
          operator delete(v3, (const struct std::nothrow_t *)&std::nothrow);
        return 0;
      }
      v22 = -1;
      v23 = v12;
      *(__m128i *)lpHandles = si128;
      v24 = (HANDLE *)si128.m128i_i64[1];
      v40 = -1;
      while ( v23 != v10 )
      {
        v25 = *v23;
        v44 = *v23;
        if ( v24 == (HANDLE *)v22 )
        {
          if ( !(unsigned __int8)utl::vector<void *,utl::allocator<void *>>::_PushBackOne2<void *>(lpHandles, &v44) )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                19,
                &WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids,
                2147943568LL);
            if ( lpHandles[0] != (HANDLE *)-1LL )
              operator delete(lpHandles[0], (const struct std::nothrow_t *)&std::nothrow);
            goto LABEL_68;
          }
          v22 = v40;
          v24 = lpHandles[1];
        }
        else
        {
          *v24++ = v25;
          lpHandles[1] = v24;
        }
        ++v23;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids);
      v26 = lpHandles[0];
      v27 = WaitForMultipleObjects(v24 - lpHandles[0], lpHandles[0], 1, a1 - v7);
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids);
        v28 = WPP_GLOBAL_Control;
      }
      if ( v27 != 258 )
      {
        if ( v27 != -1 )
        {
          if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 4) != 0 )
            WPP_SF_d(v28[2], 24, &WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids, v27);
          v35.m128i_i64[1] = (__int64)v12;
          v29 = v10 - v12;
          while ( v29 )
          {
            v30 = v12[--v29];
            if ( (unsigned __int64)v30 + 1 > 1 )
              CloseHandle(v30);
          }
          v37[1] = v3;
          if ( v26 != (HANDLE *)-1LL )
            operator delete(v26, (const struct std::nothrow_t *)&std::nothrow);
          goto LABEL_32;
        }
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids, v9);
        if ( v26 != (HANDLE *)-1LL )
          operator delete(v26, (const struct std::nothrow_t *)&std::nothrow);
        utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::~vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>(&v35);
        if ( v3 != (void *)-1LL )
        {
          v33 = v3;
          goto LABEL_96;
        }
        return v9;
      }
      if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 1) != 0 )
        WPP_SF_(v28[2], 22, &WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids);
      if ( v26 != (HANDLE *)-1LL )
        operator delete(v26, (const struct std::nothrow_t *)&std::nothrow);
      utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::~vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>(&v35);
LABEL_86:
      if ( v3 != (void *)-1LL )
        operator delete(v3, (const struct std::nothrow_t *)&std::nothrow);
      return 2147943860LL;
    }
    v14 = (char *)OpenProcess(0x100000u, 0, *v13);
    hObject = v14;
    if ( v14 == (char *)-1LL || v14 + 1 == (char *)1 )
    {
      v21 = GetLastError();
      if ( v21 > 0 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids,
          (unsigned int)v21);
      Sleep(0xAu);
LABEL_32:
      utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::~vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>(&v35);
      v2 = v42;
      TickCount64 = v43;
      goto LABEL_2;
    }
    if ( v10 != (void **)v11 )
    {
      v15 = 0;
      *v10++ = v14;
      goto LABEL_23;
    }
    v16 = (v11 - (__int64)v12) >> 3;
    v17 = 7 * (v16 >> 2) + 8;
    if ( v17 > 0xFFFFFFFFFFFFFFFLL )
      v17 = 0xFFFFFFFFFFFFFFFLL;
    if ( v16 >= v17 )
      break;
    v18 = (char *)((char *)&hObject - (char *)v12);
    if ( !(unsigned __int8)utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::_SetCapacity(&v35) )
      break;
    v19 = (char **)v35.m128i_i64[1];
    v12 = (void **)v35.m128i_i64[0];
    if ( (unsigned __int64)v18 >= v35.m128i_i64[1] - v35.m128i_i64[0] )
    {
      p_hObject = &hObject;
    }
    else
    {
      p_hObject = (HANDLE *)&v18[v35.m128i_i64[0]];
      v14 = *(char **)&v18[v35.m128i_i64[0]];
    }
    v11 = v36;
    v10 = (void **)(v35.m128i_i64[1] + 8);
    *p_hObject = 0;
    *v19 = v14;
    v15 = hObject;
LABEL_23:
    v35.m128i_i64[1] = (__int64)v10;
    if ( (unsigned __int64)v15 + 1 > 1 )
      CloseHandle(v15);
    ++v13;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids, 2147943568LL);
  if ( (unsigned __int64)(v14 + 1) > 1 )
    CloseHandle(v14);
LABEL_68:
  utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::~vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>(&v35);
  if ( v3 != (void *)-1LL )
    operator delete(v3, (const struct std::nothrow_t *)&std::nothrow);
  return 2147943568LL;
}

```

## disassembly

```asm
0x14000d0e4  mov     [rsp-8+arg_0], ecx
0x14000d0e8  push    rbp
0x14000d0e9  push    rbx
0x14000d0ea  push    rsi
0x14000d0eb  push    rdi
0x14000d0ec  push    r12
0x14000d0ee  push    r13
0x14000d0f0  push    r14
0x14000d0f2  push    r15
0x14000d0f4  lea     rbp, [rsp-1Fh]
0x14000d0f9  sub     rsp, 88h
0x14000d100  movaps  [rsp+0C0h+var_50], xmm6
0x14000d105  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14000d10d  movdqu  xmmword ptr [rbp+57h+var_80], xmm6
0x14000d112  mov     ebx, ecx
0x14000d114  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFFh
0x14000d11c  call    cs:__imp_GetTickCount64
0x14000d122  mov     rdi, [rbp+57h+var_80]
0x14000d126  lea     r15, WPP_GLOBAL_Control
0x14000d12d  mov     rsi, rax
0x14000d130  mov     [rbp+57h+arg_10], rax
0x14000d134  mov     [rbp+57h+arg_8], rbx
0x14000d138  call    cs:__imp_GetTickCount64
0x14000d13e  mov     r13, rax
0x14000d141  sub     r13, rsi
0x14000d144  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d14b  cmp     rcx, r15
0x14000d14e  jz      short loc_14000D167
0x14000d150  test    byte ptr [rcx+1Ch], 4
0x14000d154  jz      short loc_14000D167
0x14000d156  mov     rcx, [rcx+10h]
0x14000d15a  mov     edx, 0Eh
0x14000d15f  mov     r9, r13
0x14000d162  call    WPP_SF_i
0x14000d167  cmp     r13, rbx
0x14000d16a  jnb     loc_14000D5E4
0x14000d170  lea     rcx, [rbp+57h+var_80]
0x14000d174  mov     [rbp+57h+var_80+8], rdi
0x14000d178  call    GetWERProcesses
0x14000d17d  mov     ebx, eax
0x14000d17f  test    eax, eax
0x14000d181  js      loc_14000D639
0x14000d187  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d18e  mov     rdi, [rbp+57h+var_80]
0x14000d192  cmp     rcx, r15
0x14000d195  jz      short loc_14000D1BD
0x14000d197  test    byte ptr [rcx+1Ch], 4
0x14000d19b  jz      short loc_14000D1BD
0x14000d19d  mov     r9, [rbp+57h+var_80+8]
0x14000d1a1  lea     r8, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids
0x14000d1a8  mov     rcx, [rcx+10h]
0x14000d1ac  sub     r9, rdi
0x14000d1af  sar     r9, 2
0x14000d1b3  mov     edx, 10h
0x14000d1b8  call    WPP_SF_d
0x14000d1bd  movdqu  [rbp+57h+var_98], xmm6
0x14000d1c2  mov     rsi, qword ptr [rbp+57h+var_98+8]
0x14000d1c6  or      r15, 0FFFFFFFFFFFFFFFFh
0x14000d1ca  mov     r12, qword ptr [rbp+57h+var_98]
0x14000d1ce  mov     rbx, rdi
0x14000d1d1  mov     [rbp+57h+var_88], r15
0x14000d1d5  cmp     rbx, [rbp+57h+var_80+8]
0x14000d1d9  jz      loc_14000D312
0x14000d1df  mov     r8d, [rbx]; dwProcessId
0x14000d1e2  xor     edx, edx; bInheritHandle
0x14000d1e4  mov     ecx, 100000h; dwDesiredAccess
0x14000d1e9  call    cs:__imp_OpenProcess
0x14000d1ef  mov     r14, rax
0x14000d1f2  mov     [rbp+57h+hObject], rax
0x14000d1f6  inc     rax
0x14000d1f9  cmp     rax, 1
0x14000d1fd  jbe     loc_14000D2AE
0x14000d203  cmp     rsi, r15
0x14000d206  jz      short loc_14000D213
0x14000d208  xor     ecx, ecx
0x14000d20a  mov     [rsi], r14
0x14000d20d  add     rsi, 8
0x14000d211  jmp     short loc_14000D291
0x14000d213  sub     r15, r12
0x14000d216  sar     r15, 3
0x14000d21a  mov     rax, r15
0x14000d21d  shr     rax, 2
0x14000d221  imul    rdx, rax, 7
0x14000d225  mov     rax, 0FFFFFFFFFFFFFFFh
0x14000d22f  add     rdx, 8
0x14000d233  cmp     rdx, rax
0x14000d236  cmova   rdx, rax
0x14000d23a  cmp     r15, rdx
0x14000d23d  jnb     loc_14000D47C
0x14000d243  lea     rsi, [rbp+57h+hObject]
0x14000d247  lea     rcx, [rbp+57h+var_98]
0x14000d24b  sub     rsi, r12
0x14000d24e  call    ?_SetCapacity@?$vector@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@V?$allocator@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::_SetCapacity(unsigned __int64)
0x14000d253  test    al, al
0x14000d255  jz      loc_14000D47C
0x14000d25b  mov     rcx, qword ptr [rbp+57h+var_98+8]
0x14000d25f  mov     r12, qword ptr [rbp+57h+var_98]
0x14000d263  mov     rax, rcx
0x14000d266  sub     rax, r12
0x14000d269  cmp     rsi, rax
0x14000d26c  jnb     short loc_14000D277
0x14000d26e  lea     rax, [r12+rsi]
0x14000d272  mov     r14, [rax]
0x14000d275  jmp     short loc_14000D27B
0x14000d277  lea     rax, [rbp+57h+hObject]
0x14000d27b  mov     r15, [rbp+57h+var_88]
0x14000d27f  lea     rsi, [rcx+8]
0x14000d283  mov     qword ptr [rax], 0
0x14000d28a  mov     [rcx], r14
0x14000d28d  mov     rcx, [rbp+57h+hObject]; hObject
0x14000d291  lea     rax, [rcx+1]
0x14000d295  mov     qword ptr [rbp+57h+var_98+8], rsi
0x14000d299  cmp     rax, 1
0x14000d29d  jbe     short loc_14000D2A5
0x14000d29f  call    cs:__imp_CloseHandle
0x14000d2a5  add     rbx, 4
0x14000d2a9  jmp     loc_14000D1D5
0x14000d2ae  call    cs:__imp_GetLastError
0x14000d2b4  test    eax, eax
0x14000d2b6  jle     short loc_14000D2C0
0x14000d2b8  movzx   eax, ax
0x14000d2bb  or      eax, 80070000h
0x14000d2c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d2c7  lea     r15, WPP_GLOBAL_Control
0x14000d2ce  cmp     rcx, r15
0x14000d2d1  jz      short loc_14000D2F1
0x14000d2d3  test    byte ptr [rcx+1Ch], 1
0x14000d2d7  jz      short loc_14000D2F1
0x14000d2d9  mov     rcx, [rcx+10h]
0x14000d2dd  lea     r8, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids
0x14000d2e4  mov     edx, 11h
0x14000d2e9  mov     r9d, eax
0x14000d2ec  call    WPP_SF_d
0x14000d2f1  mov     ecx, 0Ah; dwMilliseconds
0x14000d2f6  call    cs:__imp_Sleep
0x14000d2fc  lea     rcx, [rbp+57h+var_98]
0x14000d300  call    ??1?$vector@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@V?$allocator@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::~vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>(void)
0x14000d305  mov     rbx, [rbp+57h+arg_8]
0x14000d309  mov     rsi, [rbp+57h+arg_10]
0x14000d30d  jmp     loc_14000D138
0x14000d312  cmp     r12, rsi
0x14000d315  jz      loc_14000D617
0x14000d31b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d31f  mov     rbx, r12
0x14000d322  movdqu  xmmword ptr [rbp+57h+lpHandles], xmm6
0x14000d327  mov     r15, [rbp+57h+lpHandles+8]
0x14000d32b  mov     [rbp+57h+var_58], rax
0x14000d32f  cmp     rbx, rsi
0x14000d332  jz      short loc_14000D370
0x14000d334  mov     rcx, [rbx]
0x14000d337  mov     [rbp+57h+arg_18], rcx
0x14000d33b  cmp     r15, rax
0x14000d33e  jz      short loc_14000D34D
0x14000d340  mov     [r15], rcx
0x14000d343  add     r15, 8
0x14000d347  mov     [rbp+57h+lpHandles+8], r15
0x14000d34b  jmp     short loc_14000D36A
0x14000d34d  lea     rdx, [rbp+57h+arg_18]
0x14000d351  lea     rcx, [rbp+57h+lpHandles]
0x14000d355  call    ??$_PushBackOne2@PEAX@?$vector@PEAXV?$allocator@PEAX@utl@@@utl@@AEAA_N$$QEAPEAX@Z; utl::vector<void *,utl::allocator<void *>>::_PushBackOne2<void *>(void * &&)
0x14000d35a  test    al, al
0x14000d35c  jz      loc_14000D4C5
0x14000d362  mov     rax, [rbp+57h+var_58]
0x14000d366  mov     r15, [rbp+57h+lpHandles+8]
0x14000d36a  add     rbx, 8
0x14000d36e  jmp     short loc_14000D32F
0x14000d370  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d377  lea     rax, WPP_GLOBAL_Control
0x14000d37e  cmp     rcx, rax
0x14000d381  jz      short loc_14000D39E
0x14000d383  test    byte ptr [rcx+1Ch], 8
0x14000d387  jz      short loc_14000D39E
0x14000d389  mov     rcx, [rcx+10h]
0x14000d38d  lea     r8, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids
0x14000d394  mov     edx, 14h
0x14000d399  call    WPP_SF_
0x14000d39e  mov     r14, [rbp+57h+lpHandles]
0x14000d3a2  mov     r8d, 1; bWaitAll
0x14000d3a8  mov     r9d, [rbp+57h+arg_0]
0x14000d3ac  sub     r15, r14
0x14000d3af  sar     r15, 3
0x14000d3b3  sub     r9d, r13d; dwMilliseconds
0x14000d3b6  mov     ecx, r15d; nCount
0x14000d3b9  mov     rdx, r14; lpHandles
0x14000d3bc  call    cs:__imp_WaitForMultipleObjects
0x14000d3c2  mov     ebx, eax
0x14000d3c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d3cb  lea     r15, WPP_GLOBAL_Control
0x14000d3d2  cmp     rcx, r15
0x14000d3d5  jz      short loc_14000D3F9
0x14000d3d7  test    byte ptr [rcx+1Ch], 8
0x14000d3db  jz      short loc_14000D3F9
0x14000d3dd  mov     rcx, [rcx+10h]
0x14000d3e1  lea     r8, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids
0x14000d3e8  mov     edx, 15h
0x14000d3ed  call    WPP_SF_
0x14000d3f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d3f9  cmp     ebx, 102h
0x14000d3ff  jz      loc_14000D5A6
0x14000d405  cmp     ebx, 0FFFFFFFFh
0x14000d408  jz      loc_14000D537
0x14000d40e  cmp     rcx, r15
0x14000d411  jz      short loc_14000D431
0x14000d413  test    byte ptr [rcx+1Ch], 4
0x14000d417  jz      short loc_14000D431
0x14000d419  mov     rcx, [rcx+10h]
0x14000d41d  lea     r8, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids
0x14000d424  mov     edx, 18h
0x14000d429  mov     r9d, ebx
0x14000d42c  call    WPP_SF_d
0x14000d431  sub     rsi, r12
0x14000d434  mov     qword ptr [rbp+57h+var_98+8], r12
0x14000d438  sar     rsi, 3
0x14000d43c  jmp     short loc_14000D455
0x14000d43e  dec     rsi
0x14000d441  mov     rcx, [r12+rsi*8]; hObject
0x14000d445  lea     rax, [rcx+1]
0x14000d449  cmp     rax, 1
0x14000d44d  jbe     short loc_14000D455
0x14000d44f  call    cs:__imp_CloseHandle
0x14000d455  test    rsi, rsi
0x14000d458  jnz     short loc_14000D43E
0x14000d45a  mov     [rbp+57h+var_80+8], rdi
0x14000d45e  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14000d462  jz      loc_14000D2FC
0x14000d468  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000d46f  mov     rcx, r14; void *
0x14000d472  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d477  jmp     loc_14000D2FC
0x14000d47c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d483  lea     rax, WPP_GLOBAL_Control
0x14000d48a  cmp     rcx, rax
0x14000d48d  jz      short loc_14000D4B0
0x14000d48f  test    byte ptr [rcx+1Ch], 1
0x14000d493  jz      short loc_14000D4B0
0x14000d495  mov     rcx, [rcx+10h]
0x14000d499  lea     r8, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids
0x14000d4a0  mov     edx, 12h
0x14000d4a5  mov     r9d, 80070490h
0x14000d4ab  call    WPP_SF_d
0x14000d4b0  lea     rax, [r14+1]
0x14000d4b4  cmp     rax, 1
0x14000d4b8  jbe     short loc_14000D50F
0x14000d4ba  mov     rcx, r14; hObject
0x14000d4bd  call    cs:__imp_CloseHandle
0x14000d4c3  jmp     short loc_14000D50F
0x14000d4c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d4cc  lea     rax, WPP_GLOBAL_Control
0x14000d4d3  cmp     rcx, rax
0x14000d4d6  jz      short loc_14000D4F9
0x14000d4d8  test    byte ptr [rcx+1Ch], 1
0x14000d4dc  jz      short loc_14000D4F9
0x14000d4de  mov     rcx, [rcx+10h]
0x14000d4e2  lea     r8, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids
0x14000d4e9  mov     edx, 13h
0x14000d4ee  mov     r9d, 80070490h
0x14000d4f4  call    WPP_SF_d
0x14000d4f9  mov     rcx, [rbp+57h+lpHandles]; void *
0x14000d4fd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000d501  jz      short loc_14000D50F
0x14000d503  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000d50a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d50f  lea     rcx, [rbp+57h+var_98]
0x14000d513  call    ??1?$vector@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@V?$allocator@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::~vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>(void)
0x14000d518  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14000d51c  jz      short loc_14000D52D
0x14000d51e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000d525  mov     rcx, rdi; void *
0x14000d528  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d52d  mov     eax, 80070490h
0x14000d532  jmp     loc_14000D5FE
0x14000d537  call    cs:__imp_GetLastError
0x14000d53d  mov     ebx, eax
0x14000d53f  test    eax, eax
0x14000d541  jle     short loc_14000D54C
0x14000d543  movzx   ebx, ax
0x14000d546  or      ebx, 80070000h
0x14000d54c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d553  cmp     rcx, r15
0x14000d556  jz      short loc_14000D576
0x14000d558  test    byte ptr [rcx+1Ch], 1
0x14000d55c  jz      short loc_14000D576
0x14000d55e  mov     rcx, [rcx+10h]
0x14000d562  lea     r8, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids
0x14000d569  mov     edx, 17h
0x14000d56e  mov     r9d, ebx
0x14000d571  call    WPP_SF_d
0x14000d576  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14000d57a  jz      short loc_14000D58B
0x14000d57c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000d583  mov     rcx, r14; void *
0x14000d586  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d58b  lea     rcx, [rbp+57h+var_98]
0x14000d58f  call    ??1?$vector@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@V?$allocator@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::~vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>(void)
0x14000d594  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14000d598  jz      loc_14000D679
0x14000d59e  mov     rcx, rdi
0x14000d5a1  jmp     loc_14000D66D
0x14000d5a6  cmp     rcx, r15
0x14000d5a9  jz      short loc_14000D5C6
  ... truncated ...
```
