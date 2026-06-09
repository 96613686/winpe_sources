# CHungApp::_Cleanup(utl::unique_lock<utl::recursive_mutex> &,_TP_WAIT *)

- ea: `0x180029e88`
- end: `0x18002a23d`
- name: `?_Cleanup@CHungApp@@AEAAXAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@PEAU_TP_WAIT@@@Z`
- size: `949`
- prototype: `void __fastcall(__int64, __int64, struct _TP_WAIT *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x1800266e0`
- `0x18002710c`
- `0x180027460`
- `0x18002917c`
- `0x180029280`
- `0x180029690`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180003d6c`
- `0x180029e88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a005`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a005`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029fa8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029fa8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a027`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a045`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a063`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a081`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a09f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a0bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a0db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a0f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a027`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a045`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a063`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a081`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a09f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a0bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a0db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a0f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180029f74`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180029fc3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180029f74`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180029fc3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180029fd1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180029fd1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180029f8a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180029fe2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180029f8a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180029fe2`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180029edf`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180029edf`

## pseudocode

```c
void __fastcall CHungApp::_Cleanup(__int64 a1, __int64 a2, struct _TP_WAIT *a3)
{
  const void *v6; // rcx
  PTP_WAIT *v7; // rdi
  struct _TP_WAIT *v8; // rcx
  PTP_WAIT *v9; // rdi
  struct _TP_WAIT *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  _QWORD v19[7]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v20; // [rsp+58h] [rbp-8h] BYREF

  if ( !*(_DWORD *)(a1 + 2452) )
  {
    *(_DWORD *)(a1 + 2452) = 1;
    v6 = *(const void **)(a1 + 352);
    *(_QWORD *)(a1 + 352) = 0;
    if ( v6 )
      UnmapViewOfFile(v6);
    v7 = (PTP_WAIT *)v19;
    v19[0] = *(_QWORD *)(a1 + 2384);
    v19[1] = *(_QWORD *)(a1 + 2392);
    v19[2] = *(_QWORD *)(a1 + 2400);
    v19[3] = *(_QWORD *)(a1 + 2408);
    v19[4] = *(_QWORD *)(a1 + 2416);
    v19[5] = *(_QWORD *)(a1 + 2424);
    v19[6] = *(_QWORD *)(a1 + 2432);
    *(_QWORD *)(a1 + 2384) = 0;
    *(_QWORD *)(a1 + 2392) = 0;
    *(_QWORD *)(a1 + 2400) = 0;
    *(_QWORD *)(a1 + 2408) = 0;
    *(_QWORD *)(a1 + 2416) = 0;
    *(_QWORD *)(a1 + 2424) = 0;
    *(_QWORD *)(a1 + 2432) = 0;
    do
    {
      if ( *v7 )
        SetThreadpoolWait(*v7, 0, 0);
      v8 = *v7;
      if ( *v7 == a3 )
      {
        *v7 = 0;
        if ( v8 )
          CloseThreadpoolWait(v8);
      }
      ++v7;
    }
    while ( v7 != (PTP_WAIT *)&v20 );
    if ( !*(_BYTE *)(a2 + 8) )
      __int2c();
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)a2);
    *(_BYTE *)(a2 + 8) = 0;
    v9 = (PTP_WAIT *)v19;
    do
    {
      if ( *v9 )
      {
        SetThreadpoolWait(*v9, 0, 0);
        WaitForThreadpoolWaitCallbacks(*v9, 1);
        v10 = *v9;
        *v9 = 0;
        if ( v10 )
          CloseThreadpoolWait(v10);
      }
      ++v9;
    }
    while ( v9 != (PTP_WAIT *)&v20 );
    if ( !*(_QWORD *)a2 || *(_BYTE *)(a2 + 8) )
      __int2c();
    EnterCriticalSection(*(LPCRITICAL_SECTION *)a2);
    *(_BYTE *)(a2 + 8) = 1;
    v11 = *(void **)(a1 + 368);
    *(_QWORD *)(a1 + 368) = 0;
    if ( (unsigned __int64)v11 + 1 > 1 )
      CloseHandle(v11);
    v12 = *(void **)(a1 + 376);
    *(_QWORD *)(a1 + 376) = 0;
    if ( (unsigned __int64)v12 + 1 > 1 )
      CloseHandle(v12);
    v13 = *(void **)(a1 + 344);
    *(_QWORD *)(a1 + 344) = 0;
    if ( (unsigned __int64)v13 + 1 > 1 )
      CloseHandle(v13);
    v14 = *(void **)(a1 + 384);
    *(_QWORD *)(a1 + 384) = 0;
    if ( (unsigned __int64)v14 + 1 > 1 )
      CloseHandle(v14);
    v15 = *(void **)(a1 + 360);
    *(_QWORD *)(a1 + 360) = 0;
    if ( (unsigned __int64)v15 + 1 > 1 )
      CloseHandle(v15);
    v16 = *(void **)(a1 + 1184);
    *(_QWORD *)(a1 + 1184) = 0;
    if ( (unsigned __int64)v16 + 1 > 1 )
      CloseHandle(v16);
    v17 = *(void **)(a1 + 2368);
    *(_QWORD *)(a1 + 2368) = 0;
    if ( (unsigned __int64)v17 + 1 > 1 )
      CloseHandle(v17);
    v18 = *(void **)(a1 + 2376);
    *(_QWORD *)(a1 + 2376) = 0;
    if ( (unsigned __int64)v18 + 1 > 1 )
      CloseHandle(v18);
    *(_QWORD *)(a1 + 2440) = 0;
    *(_DWORD *)(a1 + 2448) = 0;
    memset_0((void *)(a1 + 396), 0, 0x208u);
    memset_0((void *)(a1 + 920), 0, 0x104u);
    *(_OWORD *)(a1 + 56) = 0;
    *(_OWORD *)(a1 + 72) = 0;
    *(_OWORD *)(a1 + 88) = 0;
    *(_OWORD *)(a1 + 100) = 0;
    memset_0((void *)(a1 + 1192), 0, 0x80u);
    memset_0((void *)(a1 + 1320), 0, 0x208u);
    *(_QWORD *)(a1 + 1840) = 0;
    memset_0((void *)(a1 + 1848), 0, 0x100u);
    memset_0((void *)(a1 + 2104), 0, 0x84u);
    memset_0((void *)(a1 + 2236), 0, 0x80u);
    memset_0((void *)(a1 + 120), 0, 0x80u);
    *(_OWORD *)(a1 + 248) = 0;
    memset_0((void *)(a1 + 264), 0, 0x40u);
    *(_QWORD *)(a1 + 48) = 0;
    *(_DWORD *)(a1 + 392) = 0;
    *(_QWORD *)(a1 + 40) = 0;
    *(_QWORD *)(a1 + 328) = 0;
    *(_QWORD *)(a1 + 336) = 0;
    *(_DWORD *)(a1 + 916) = 0;
    *(_DWORD *)(a1 + 2452) = 0;
    `eh vector destructor iterator'(
      (char *)v19,
      8,
      7,
      (void (__fastcall *)(char *))tlx::unique_any<tlx::handle_traits<_TP_WAIT *,void (*)(_TP_WAIT *),&void CloseThreadpoolWait(_TP_WAIT *),0>>::~unique_any<tlx::handle_traits<_TP_WAIT *,void (*)(_TP_WAIT *),&void CloseThreadpoolWait(_TP_WAIT *),0>>);
  }
}

```

## disassembly

```asm
0x180029e88  mov     [rsp-28h+arg_10], rbx
0x180029e8d  push    rbp
0x180029e8e  push    rsi
0x180029e8f  push    rdi
0x180029e90  push    r14
0x180029e92  push    r15
0x180029e94  mov     rbp, rsp
0x180029e97  sub     rsp, 60h
0x180029e9b  mov     rax, cs:__security_cookie
0x180029ea2  xor     rax, rsp
0x180029ea5  mov     [rbp+var_8], rax
0x180029ea9  xor     r15d, r15d
0x180029eac  mov     r14, r8
0x180029eaf  mov     rsi, rdx
0x180029eb2  mov     rbx, rcx
0x180029eb5  cmp     [rcx+994h], r15d
0x180029ebc  jnz     loc_18002A21D
0x180029ec2  mov     dword ptr [rcx+994h], 1
0x180029ecc  mov     rcx, [rcx+160h]; lpBaseAddress
0x180029ed3  mov     [rbx+160h], r15
0x180029eda  test    rcx, rcx
0x180029edd  jz      short loc_180029EE5
0x180029edf  call    cs:__imp_UnmapViewOfFile
0x180029ee5  mov     rax, [rbx+950h]
0x180029eec  lea     rdi, [rbp+var_40]
0x180029ef0  mov     [rbp+var_40], rax
0x180029ef4  mov     rax, [rbx+958h]
0x180029efb  mov     [rbp+var_38], rax
0x180029eff  mov     rax, [rbx+960h]
0x180029f06  mov     [rbp+var_30], rax
0x180029f0a  mov     rax, [rbx+968h]
0x180029f11  mov     [rbp+var_28], rax
0x180029f15  mov     rax, [rbx+970h]
0x180029f1c  mov     [rbp+var_20], rax
0x180029f20  mov     rax, [rbx+978h]
0x180029f27  mov     [rbp+var_18], rax
0x180029f2b  mov     rax, [rbx+980h]
0x180029f32  mov     [rbp+var_10], rax
0x180029f36  mov     [rbx+950h], r15
0x180029f3d  mov     [rbx+958h], r15
0x180029f44  mov     [rbx+960h], r15
0x180029f4b  mov     [rbx+968h], r15
0x180029f52  mov     [rbx+970h], r15
0x180029f59  mov     [rbx+978h], r15
0x180029f60  mov     [rbx+980h], r15
0x180029f67  mov     rcx, [rdi]; pwa
0x180029f6a  test    rcx, rcx
0x180029f6d  jz      short loc_180029F7A
0x180029f6f  xor     r8d, r8d; pftTimeout
0x180029f72  xor     edx, edx; h
0x180029f74  call    cs:__imp_SetThreadpoolWait
0x180029f7a  mov     rcx, [rdi]; pwa
0x180029f7d  cmp     rcx, r14
0x180029f80  jnz     short loc_180029F90
0x180029f82  mov     [rdi], r15
0x180029f85  test    rcx, rcx
0x180029f88  jz      short loc_180029F90
0x180029f8a  call    cs:__imp_CloseThreadpoolWait
0x180029f90  add     rdi, 8
0x180029f94  lea     rax, [rbp+var_8]
0x180029f98  cmp     rdi, rax
0x180029f9b  jnz     short loc_180029F67
0x180029f9d  cmp     [rsi+8], r15b
0x180029fa1  jnz     short loc_180029FA5
0x180029fa3  int     2Ch; Windows NT - assertion failure
0x180029fa5  mov     rcx, [rsi]; lpCriticalSection
0x180029fa8  call    cs:__imp_LeaveCriticalSection
0x180029fae  mov     [rsi+8], r15b
0x180029fb2  lea     rdi, [rbp+var_40]
0x180029fb6  mov     rcx, [rdi]; pwa
0x180029fb9  test    rcx, rcx
0x180029fbc  jz      short loc_180029FE8
0x180029fbe  xor     r8d, r8d; pftTimeout
0x180029fc1  xor     edx, edx; h
0x180029fc3  call    cs:__imp_SetThreadpoolWait
0x180029fc9  mov     rcx, [rdi]; pwa
0x180029fcc  mov     edx, 1; fCancelPendingCallbacks
0x180029fd1  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180029fd7  mov     rcx, [rdi]; pwa
0x180029fda  mov     [rdi], r15
0x180029fdd  test    rcx, rcx
0x180029fe0  jz      short loc_180029FE8
0x180029fe2  call    cs:__imp_CloseThreadpoolWait
0x180029fe8  add     rdi, 8
0x180029fec  lea     rax, [rbp+var_8]
0x180029ff0  cmp     rdi, rax
0x180029ff3  jnz     short loc_180029FB6
0x180029ff5  mov     rcx, [rsi]; lpCriticalSection
0x180029ff8  test    rcx, rcx
0x180029ffb  jz      short loc_18002A003
0x180029ffd  cmp     [rsi+8], r15b
0x18002a001  jz      short loc_18002A005
0x18002a003  int     2Ch; Windows NT - assertion failure
0x18002a005  call    cs:__imp_EnterCriticalSection
0x18002a00b  mov     byte ptr [rsi+8], 1
0x18002a00f  mov     rcx, [rbx+170h]; hObject
0x18002a016  mov     [rbx+170h], r15
0x18002a01d  lea     rax, [rcx+1]
0x18002a021  cmp     rax, 1
0x18002a025  jbe     short loc_18002A02D
0x18002a027  call    cs:__imp_CloseHandle
0x18002a02d  mov     rcx, [rbx+178h]; hObject
0x18002a034  mov     [rbx+178h], r15
0x18002a03b  lea     rax, [rcx+1]
0x18002a03f  cmp     rax, 1
0x18002a043  jbe     short loc_18002A04B
0x18002a045  call    cs:__imp_CloseHandle
0x18002a04b  mov     rcx, [rbx+158h]; hObject
0x18002a052  mov     [rbx+158h], r15
0x18002a059  lea     rax, [rcx+1]
0x18002a05d  cmp     rax, 1
0x18002a061  jbe     short loc_18002A069
0x18002a063  call    cs:__imp_CloseHandle
0x18002a069  mov     rcx, [rbx+180h]; hObject
0x18002a070  mov     [rbx+180h], r15
0x18002a077  lea     rax, [rcx+1]
0x18002a07b  cmp     rax, 1
0x18002a07f  jbe     short loc_18002A087
0x18002a081  call    cs:__imp_CloseHandle
0x18002a087  mov     rcx, [rbx+168h]; hObject
0x18002a08e  mov     [rbx+168h], r15
0x18002a095  lea     rax, [rcx+1]
0x18002a099  cmp     rax, 1
0x18002a09d  jbe     short loc_18002A0A5
0x18002a09f  call    cs:__imp_CloseHandle
0x18002a0a5  mov     rcx, [rbx+4A0h]; hObject
0x18002a0ac  mov     [rbx+4A0h], r15
0x18002a0b3  lea     rax, [rcx+1]
0x18002a0b7  cmp     rax, 1
0x18002a0bb  jbe     short loc_18002A0C3
0x18002a0bd  call    cs:__imp_CloseHandle
0x18002a0c3  mov     rcx, [rbx+940h]; hObject
0x18002a0ca  mov     [rbx+940h], r15
0x18002a0d1  lea     rax, [rcx+1]
0x18002a0d5  cmp     rax, 1
0x18002a0d9  jbe     short loc_18002A0E1
0x18002a0db  call    cs:__imp_CloseHandle
0x18002a0e1  mov     rcx, [rbx+948h]; hObject
0x18002a0e8  mov     [rbx+948h], r15
0x18002a0ef  lea     rax, [rcx+1]
0x18002a0f3  cmp     rax, 1
0x18002a0f7  jbe     short loc_18002A0FF
0x18002a0f9  call    cs:__imp_CloseHandle
0x18002a0ff  mov     edi, 208h
0x18002a104  mov     [rbx+988h], r15
0x18002a10b  mov     r8d, edi; Size
0x18002a10e  mov     [rbx+990h], r15d
0x18002a115  lea     rcx, [rbx+18Ch]; void *
0x18002a11c  xor     edx, edx; Val
0x18002a11e  call    memset_0
0x18002a123  lea     rcx, [rbx+398h]; void *
0x18002a12a  xor     edx, edx; Val
0x18002a12c  mov     r8d, 104h; Size
0x18002a132  call    memset_0
0x18002a137  xorps   xmm0, xmm0
0x18002a13a  lea     rcx, [rbx+4A8h]; void *
0x18002a141  movups  xmmword ptr [rbx+38h], xmm0
0x18002a145  mov     esi, 80h
0x18002a14a  xor     edx, edx; Val
0x18002a14c  movups  xmmword ptr [rbx+48h], xmm0
0x18002a150  mov     r8d, esi; Size
0x18002a153  movups  xmmword ptr [rbx+58h], xmm0
0x18002a157  movups  xmmword ptr [rbx+64h], xmm0
0x18002a15b  call    memset_0
0x18002a160  lea     rcx, [rbx+528h]; void *
0x18002a167  mov     r8d, edi; Size
0x18002a16a  xor     edx, edx; Val
0x18002a16c  call    memset_0
0x18002a171  xor     eax, eax
0x18002a173  lea     rcx, [rbx+738h]; void *
0x18002a17a  xor     edx, edx; Val
0x18002a17c  mov     [rbx+730h], rax
0x18002a183  mov     r8d, 100h; Size
0x18002a189  call    memset_0
0x18002a18e  lea     rcx, [rbx+838h]; void *
0x18002a195  xor     edx, edx; Val
0x18002a197  lea     r8d, [rsi+4]; Size
0x18002a19b  call    memset_0
0x18002a1a0  lea     rcx, [rbx+8BCh]; void *
0x18002a1a7  mov     r8d, esi; Size
0x18002a1aa  xor     edx, edx; Val
0x18002a1ac  call    memset_0
0x18002a1b1  lea     rcx, [rbx+78h]; void *
0x18002a1b5  mov     r8d, esi; Size
0x18002a1b8  xor     edx, edx; Val
0x18002a1ba  call    memset_0
0x18002a1bf  xorps   xmm0, xmm0
0x18002a1c2  lea     rcx, [rbx+108h]; void *
0x18002a1c9  xor     edx, edx; Val
0x18002a1cb  lea     r8d, [rsi-40h]; Size
0x18002a1cf  movups  xmmword ptr [rbx+0F8h], xmm0
0x18002a1d6  call    memset_0
0x18002a1db  lea     r9, ??1?$unique_any@U?$handle_traits@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?CloseThreadpoolWait@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; void (*)(void *)
0x18002a1e2  mov     [rbx+30h], r15
0x18002a1e6  lea     edx, [rsi-78h]; unsigned __int64
0x18002a1e9  mov     [rbx+188h], r15d
0x18002a1f0  lea     r8d, [rsi-79h]; unsigned __int64
0x18002a1f4  mov     [rbx+28h], r15
0x18002a1f8  lea     rcx, [rbp+var_40]; void *
0x18002a1fc  mov     [rbx+148h], r15
0x18002a203  mov     [rbx+150h], r15
0x18002a20a  mov     [rbx+394h], r15d
0x18002a211  mov     [rbx+994h], r15d
0x18002a218  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002a21d  mov     rcx, [rbp+var_8]
0x18002a221  xor     rcx, rsp; StackCookie
0x18002a224  call    __security_check_cookie
0x18002a229  mov     rbx, [rsp+60h+arg_10]
0x18002a231  add     rsp, 60h
0x18002a235  pop     r15
0x18002a237  pop     r14
0x18002a239  pop     rdi
0x18002a23a  pop     rsi
0x18002a23b  pop     rbp
0x18002a23c  retn
```
