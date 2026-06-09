# WapTcpConnectCompletionRoutine

- ea: `0x1800522a0`
- end: `0x18005276d`
- name: `WapTcpConnectCompletionRoutine`
- size: `1229`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800522a0`
- `0x180052950`

## callees

- `0x1800154c0`
- `0x1800180e0`
- `0x18002c94c`
- `0x180046370`
- `0x180051cd4`
- `0x1800522a0`
- `0x180052774`
- `0x18005307c`
- `0x1800533d0`
- `0x1800535dc`
- `0x180053f5c`
- `0x180068018`
- `0x1800722f0`
- `0x18009234c`
- `0x180092564`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005236a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005236a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005232b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005232b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052386`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052386`

## pseudocode

```c
__int64 __fastcall WapTcpConnectCompletionRoutine(__int64 a1, int a2, int a3)
{
  int updated; // esi
  char v4; // r15
  __int64 v6; // rdi
  __int64 v7; // rdx
  bool v8; // zf
  char v9; // r14
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 result; // rax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int ValidAddressForInterface; // eax
  int v16; // edx
  int started; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+28h] [rbp-D8h]
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+68h] [rbp-98h] BYREF
  __int64 v24; // [rsp+70h] [rbp-90h] BYREF
  __int64 v25; // [rsp+78h] [rbp-88h] BYREF
  __int64 v26; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v28; // [rsp+A0h] [rbp-60h]
  __int64 v29; // [rsp+A8h] [rbp-58h]
  __int64 *v30; // [rsp+B0h] [rbp-50h]
  __int64 v31; // [rsp+B8h] [rbp-48h]
  int *v32; // [rsp+C0h] [rbp-40h]
  __int64 v33; // [rsp+C8h] [rbp-38h]
  __int64 v34; // [rsp+D0h] [rbp-30h]
  __int64 v35; // [rsp+D8h] [rbp-28h]
  __int64 *v36; // [rsp+E0h] [rbp-20h]
  __int64 v37; // [rsp+E8h] [rbp-18h]
  __int64 *v38; // [rsp+F0h] [rbp-10h]
  __int64 v39; // [rsp+F8h] [rbp-8h]
  LARGE_INTEGER *p_PerformanceCount; // [rsp+100h] [rbp+0h]
  __int64 v41; // [rsp+108h] [rbp+8h]
  __int64 *v42; // [rsp+110h] [rbp+10h]
  __int64 v43; // [rsp+118h] [rbp+18h]

  updated = a2;
  v4 = 0;
  if ( (xmmword_1800AD720 & 8) != 0 )
  {
    v19 = a3;
    v18 = a2;
    WPP_SF_qDD(1027, 53, WPP_14086b36644f38024399eb8d606249d9_Traceguids);
  }
  v6 = *(_QWORD *)(a1 + 8);
  if ( (unsigned __int8)WaCancelTwTimer(a1 + 128) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 4), 0xFFFFFFFF) == 1 )
      WapTcpFreeIoContext((LPVOID)a1);
  }
  else if ( *(_DWORD *)(a1 + 220) )
  {
    WaTcpAbortRequest(*(_QWORD *)(v6 + 8), 0, 1460);
  }
  if ( !updated )
  {
    LOBYTE(v7) = *(_DWORD *)(a1 + 232) != 0;
    updated = WapTcpUpdateConnectedSocket(v6, v7);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 24));
  v8 = *(_DWORD *)(v6 + 224) == 3;
  v9 = 1;
  *(_QWORD *)(v6 + 688) = 0;
  if ( v8 )
  {
    if ( !updated )
    {
      *(_DWORD *)(v6 + 224) = 4;
      goto LABEL_11;
    }
    *(_DWORD *)(v6 + 224) = 2;
    ++*(_DWORD *)(a1 + 208);
    --*(_DWORD *)(a1 + 212);
    ++*(_DWORD *)(v6 + 344);
    v14 = WaUpdateDnsQueryResultIndexByPort(
            *(_QWORD *)(v6 + 336),
            *(unsigned __int16 *)(v6 + 352),
            0,
            *(unsigned int *)(a1 + 208));
    *(_DWORD *)(a1 + 208) = v14;
    ValidAddressForInterface = WapTcpFindValidAddressForInterface(v6, v14);
    v16 = *(_DWORD *)(a1 + 212);
    *(_DWORD *)(a1 + 208) = ValidAddressForInterface;
    if ( v16 && (unsigned __int64)ValidAddressForInterface < *(_QWORD *)(*(_QWORD *)(v6 + 336) + 40LL) )
    {
      updated = WapTcpAllocateSocket(v6, a1);
      if ( updated )
        goto LABEL_11;
      *(_QWORD *)(v6 + 688) = a1;
      *(_DWORD *)(v6 + 224) = 3;
      goto LABEL_33;
    }
    if ( *(_BYTE *)(v6 + 355) && *(_DWORD *)(v6 + 348) == 1 && v16 )
    {
      if ( (xmmword_1800AD720 & 8) != 0 )
        WPP_SF_(1027, 54, WPP_14086b36644f38024399eb8d606249d9_Traceguids);
      *(_DWORD *)(v6 + 224) = 0;
      v4 = 1;
LABEL_33:
      v9 = 0;
    }
  }
  else
  {
    updated = *(_DWORD *)(v6 + 232);
    if ( !updated )
      updated = 1359;
  }
LABEL_11:
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  *(LARGE_INTEGER *)(v6 + 1136) = PerformanceCount;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 24));
  if ( v4 )
  {
    started = WapTcpStartDnsQuery(
                v6,
                *(_QWORD *)(a1 + 192),
                *(_QWORD *)(a1 + 200),
                *(_DWORD *)(a1 + 212),
                *(_DWORD *)(a1 + 216),
                *(_DWORD *)(a1 + 220),
                *(_QWORD *)(a1 + 224),
                *(_DWORD *)(a1 + 232),
                *(_QWORD *)(a1 + 88),
                *(_QWORD *)(a1 + 96));
    if ( started == 997 )
      *(_BYTE *)(a1 + 124) = 1;
    else
      *(_DWORD *)(a1 + 104) = started;
  }
  else if ( v9 )
  {
    *(_DWORD *)(a1 + 104) = updated;
    v11 = 0;
    if ( !updated )
    {
      (*(void (__fastcall **)(_QWORD, __int64, unsigned __int64, __int64, int, int))(*(_QWORD *)(v6 + 16) + 88LL))(
        *(_QWORD *)(v6 + 8),
        1,
        *(_QWORD *)(*(_QWORD *)(v6 + 336) + 32LL) + ((unsigned __int64)*(unsigned int *)(a1 + 208) << 7),
        128,
        v18,
        v19);
      v11 = 0x80000000LL;
    }
    *(_QWORD *)(a1 + 112) = v11;
    if ( updated )
    {
      if ( (Microsoft_Windows_WebIOEnableBits & 0x8000) != 0 )
        McTemplateU0pxqzr2pxqx_EventWriteTransfer(
          (unsigned int)&WEB_ETW_PROVIDER_ID_Context,
          (unsigned int)NetSocketConnectFailed,
          *(_QWORD *)(v6 + 8),
          *(_QWORD *)(v6 + 704),
          0,
          0,
          a1 + 16,
          *(_DWORD *)(a1 + 212),
          updated,
          0);
    }
    else if ( (Microsoft_Windows_WebIOEnableBits & 0x4000) != 0 )
    {
      v25 = *(unsigned int *)(a1 + 212);
      v26 = 0;
      v21 = a1 + 16;
      v24 = *(_QWORD *)(v6 + 704);
      v20 = *(_QWORD *)(v6 + 8);
      v28 = &v20;
      v30 = &v24;
      v32 = &v23;
      v36 = &v21;
      v38 = &v25;
      p_PerformanceCount = &PerformanceCount;
      v42 = &v26;
      PerformanceCount.LowPart = 0;
      v23 = 0;
      v29 = 8;
      v31 = 8;
      v33 = 4;
      v34 = 0;
      v35 = 0;
      v37 = 8;
      v39 = 8;
      v41 = 4;
      v43 = 8;
      McGenEventWrite_EventWriteTransfer(
        &WEB_ETW_PROVIDER_ID_Context,
        (const EVENT_DESCRIPTOR *)NetSocketConnectComplete,
        v10,
        9u,
        &v27);
    }
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
    v13 = WapTcpConnectSocket(v6, a1);
    if ( v13 != 997 )
      WapTcpConnectCompletionRoutine(a1, v13, 0);
  }
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 4), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    result = WapTcpFreeIoContext((LPVOID)a1);
  if ( (xmmword_1800AD720 & 8) != 0 )
    return WPP_SF_(1027, 55, WPP_14086b36644f38024399eb8d606249d9_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1800522a0  mov     [rsp-8+arg_10], rbx
0x1800522a5  push    rbp
0x1800522a6  push    rsi
0x1800522a7  push    rdi
0x1800522a8  push    r12
0x1800522aa  push    r13
0x1800522ac  push    r14
0x1800522ae  push    r15
0x1800522b0  lea     rbp, [rsp-30h]
0x1800522b5  sub     rsp, 130h
0x1800522bc  mov     rax, cs:__security_cookie
0x1800522c3  xor     rax, rsp
0x1800522c6  mov     [rbp+60h+var_40], rax
0x1800522ca  xor     r13d, r13d
0x1800522cd  mov     esi, edx
0x1800522cf  mov     r15b, r13b
0x1800522d2  mov     rbx, rcx
0x1800522d5  test    byte ptr cs:xmmword_1800AD720, 8
0x1800522dc  jnz     loc_1800526D5
0x1800522e2  mov     rdi, [rbx+8]
0x1800522e6  lea     rcx, [rbx+80h]
0x1800522ed  call    WaCancelTwTimer
0x1800522f2  test    al, al
0x1800522f4  jz      loc_180052481
0x1800522fa  or      eax, 0FFFFFFFFh
0x1800522fd  lock xadd [rbx+4], eax
0x180052302  cmp     eax, 1
0x180052305  jnz     short loc_18005230F
0x180052307  mov     rcx, rbx; lpMem
0x18005230a  call    WapTcpFreeIoContext
0x18005230f  test    esi, esi
0x180052311  jnz     short loc_180052327
0x180052313  cmp     [rbx+0E8h], r13d
0x18005231a  mov     rcx, rdi
0x18005231d  setnz   dl
0x180052320  call    WapTcpUpdateConnectedSocket
0x180052325  mov     esi, eax
0x180052327  lea     rcx, [rdi+18h]; lpCriticalSection
0x18005232b  call    cs:__imp_EnterCriticalSection
0x180052332  nop     dword ptr [rax+rax+00h]
0x180052337  cmp     dword ptr [rdi+0E0h], 3
0x18005233e  mov     r14b, 1
0x180052341  mov     [rdi+2B0h], r13
0x180052348  jnz     loc_180052444
0x18005234e  test    esi, esi
0x180052350  jnz     loc_180052580
0x180052356  mov     dword ptr [rdi+0E0h], 4
0x180052360  lea     rcx, [rsp+160h+PerformanceCount]; lpPerformanceCount
0x180052365  mov     qword ptr [rsp+160h+PerformanceCount], r13
0x18005236a  call    cs:__imp_QueryPerformanceCounter
0x180052371  nop     dword ptr [rax+rax+00h]
0x180052376  mov     rax, qword ptr [rsp+160h+PerformanceCount]
0x18005237b  lea     rcx, [rdi+18h]; lpCriticalSection
0x18005237f  mov     [rdi+470h], rax
0x180052386  call    cs:__imp_LeaveCriticalSection
0x18005238d  nop     dword ptr [rax+rax+00h]
0x180052392  test    r15b, r15b
0x180052395  jnz     loc_1800526FC
0x18005239b  test    r14b, r14b
0x18005239e  jz      loc_180052459
0x1800523a4  mov     [rbx+68h], esi
0x1800523a7  mov     rax, r13
0x1800523aa  test    esi, esi
0x1800523ac  jnz     short loc_1800523E1
0x1800523ae  mov     rax, [rdi+150h]
0x1800523b5  lea     edx, [rsi+1]
0x1800523b8  mov     rcx, [rdi+10h]
0x1800523bc  lea     r9d, [rdx+7Fh]
0x1800523c0  mov     r8d, [rbx+0D0h]
0x1800523c7  shl     r8, 7
0x1800523cb  add     r8, [rax+20h]
0x1800523cf  mov     rax, [rcx+58h]
0x1800523d3  mov     rcx, [rdi+8]
0x1800523d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523dc  mov     eax, 80000000h
0x1800523e1  mov     [rbx+70h], rax
0x1800523e5  test    esi, esi
0x1800523e7  jnz     loc_180052663
0x1800523ed  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 40h
0x1800523f4  jnz     loc_1800524A4
0x1800523fa  or      eax, 0FFFFFFFFh
0x1800523fd  lock xadd [rbx+4], eax
0x180052402  cmp     eax, 1
0x180052405  jnz     short loc_18005240F
0x180052407  mov     rcx, rbx; lpMem
0x18005240a  call    WapTcpFreeIoContext
0x18005240f  test    byte ptr cs:xmmword_1800AD720, 8
0x180052416  jnz     loc_1800526BA
0x18005241c  mov     rcx, [rbp+60h+var_40]
0x180052420  xor     rcx, rsp; StackCookie
0x180052423  call    __security_check_cookie
0x180052428  mov     rbx, [rsp+160h+arg_10]
0x180052430  add     rsp, 130h
0x180052437  pop     r15
0x180052439  pop     r14
0x18005243b  pop     r13
0x18005243d  pop     r12
0x18005243f  pop     rdi
0x180052440  pop     rsi
0x180052441  pop     rbp
0x180052442  retn
0x180052444  mov     esi, [rdi+0E8h]
0x18005244a  mov     eax, 54Fh
0x18005244f  test    esi, esi
0x180052451  cmovz   esi, eax
0x180052454  jmp     loc_180052360
0x180052459  lock inc dword ptr [rbx+4]
0x18005245d  mov     rdx, rbx
0x180052460  mov     rcx, rdi
0x180052463  call    WapTcpConnectSocket
0x180052468  cmp     eax, 3E5h
0x18005246d  jz      short loc_1800523FA
0x18005246f  xor     r8d, r8d
0x180052472  mov     edx, eax
0x180052474  mov     rcx, rbx
0x180052477  call    WapTcpConnectCompletionRoutine
0x18005247c  jmp     loc_1800523FA
0x180052481  cmp     [rbx+0DCh], r13d
0x180052488  jz      loc_18005230F
0x18005248e  mov     rcx, [rdi+8]
0x180052492  xor     edx, edx
0x180052494  mov     r8d, 5B4h
0x18005249a  call    WaTcpAbortRequest
0x18005249f  jmp     loc_18005230F
0x1800524a4  mov     eax, [rbx+0D4h]
0x1800524aa  lea     rdx, NetSocketConnectComplete
0x1800524b1  mov     [rsp+160h+var_E8], rax
0x1800524b6  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x1800524bd  lea     rax, [rbx+10h]
0x1800524c1  mov     [rbp+60h+var_E0], r13
0x1800524c5  mov     [rsp+160h+var_108], rax
0x1800524ca  mov     r9d, 9
0x1800524d0  mov     rax, [rdi+2C0h]
0x1800524d7  mov     [rsp+160h+var_F0], rax
0x1800524dc  mov     rax, [rdi+8]
0x1800524e0  mov     [rsp+160h+var_110], rax
0x1800524e5  lea     rax, [rsp+160h+var_110]
0x1800524ea  mov     [rbp+60h+var_C0], rax
0x1800524ee  lea     rax, [rsp+160h+var_F0]
0x1800524f3  mov     [rbp+60h+var_B0], rax
0x1800524f7  lea     rax, [rsp+160h+var_F8]
0x1800524fc  mov     [rbp+60h+var_A0], rax
0x180052500  lea     rax, [rsp+160h+var_108]
0x180052505  mov     [rbp+60h+var_80], rax
0x180052509  lea     rax, [rsp+160h+var_E8]
0x18005250e  mov     [rbp+60h+var_70], rax
0x180052512  lea     rax, [rsp+160h+PerformanceCount]
0x180052517  mov     [rbp+60h+var_60], rax
0x18005251b  lea     rax, [rbp+60h+var_E0]
0x18005251f  mov     [rbp+60h+var_50], rax
0x180052523  lea     rax, [rbp+60h+var_D0]
0x180052527  mov     [rsp+160h+var_140], rax
0x18005252c  mov     dword ptr [rsp+160h+PerformanceCount], r13d
0x180052531  mov     [rsp+160h+var_F8], r13d
0x180052536  mov     [rbp+60h+var_B8], 8
0x18005253e  mov     [rbp+60h+var_A8], 8
0x180052546  mov     [rbp+60h+var_98], 4
0x18005254e  mov     [rbp+60h+var_90], r13
0x180052552  mov     [rbp+60h+var_88], r13
0x180052556  mov     [rbp+60h+var_78], 8
0x18005255e  mov     [rbp+60h+var_68], 8
0x180052566  mov     [rbp+60h+var_58], 4
0x18005256e  mov     [rbp+60h+var_48], 8
0x180052576  call    McGenEventWrite_EventWriteTransfer
0x18005257b  jmp     loc_1800523FA
0x180052580  mov     dword ptr [rdi+0E0h], 2
0x18005258a  xor     r8d, r8d
0x18005258d  inc     dword ptr [rbx+0D0h]
0x180052593  dec     dword ptr [rbx+0D4h]
0x180052599  inc     dword ptr [rdi+158h]
0x18005259f  mov     r9d, [rbx+0D0h]
0x1800525a6  movzx   edx, word ptr [rdi+160h]
0x1800525ad  mov     rcx, [rdi+150h]
0x1800525b4  call    WaUpdateDnsQueryResultIndexByPort
0x1800525b9  mov     edx, eax
0x1800525bb  mov     [rbx+0D0h], eax
0x1800525c1  mov     rcx, rdi
0x1800525c4  call    WapTcpFindValidAddressForInterface
0x1800525c9  mov     edx, [rbx+0D4h]
0x1800525cf  mov     [rbx+0D0h], eax
0x1800525d5  test    edx, edx
0x1800525d7  jz      short loc_180052616
0x1800525d9  mov     rcx, [rdi+150h]
0x1800525e0  mov     eax, eax
0x1800525e2  cmp     rax, [rcx+28h]
0x1800525e6  jnb     short loc_180052616
0x1800525e8  mov     rdx, rbx
0x1800525eb  mov     rcx, rdi
0x1800525ee  call    WapTcpAllocateSocket
0x1800525f3  mov     esi, eax
0x1800525f5  test    eax, eax
0x1800525f7  jnz     loc_180052360
0x1800525fd  mov     [rdi+2B0h], rbx
0x180052604  mov     dword ptr [rdi+0E0h], 3
0x18005260e  mov     r14b, r13b
0x180052611  jmp     loc_180052360
0x180052616  cmp     [rdi+163h], r13b
0x18005261d  jz      loc_180052360
0x180052623  cmp     dword ptr [rdi+15Ch], 1
0x18005262a  jnz     loc_180052360
0x180052630  test    edx, edx
0x180052632  jz      loc_180052360
0x180052638  test    byte ptr cs:xmmword_1800AD720, 8
0x18005263f  jz      short loc_180052657
0x180052641  mov     edx, 36h ; '6'
0x180052646  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x18005264d  mov     ecx, 403h
0x180052652  call    WPP_SF_
0x180052657  mov     [rdi+0E0h], r13d
0x18005265e  mov     r15b, 1
0x180052661  jmp     short loc_18005260E
0x180052663  cmp     byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, r13b
0x18005266a  jge     loc_1800523FA
0x180052670  mov     eax, [rbx+0D4h]
0x180052676  lea     rcx, [rbx+10h]
0x18005267a  mov     r9, [rdi+2C0h]
0x180052681  lea     rdx, NetSocketConnectFailed
0x180052688  mov     r8, [rdi+8]
0x18005268c  mov     [rsp+160h+var_118], r13
0x180052691  mov     dword ptr [rsp+160h+var_120], esi
0x180052695  mov     [rsp+160h+var_128], rax
0x18005269a  mov     [rsp+160h+var_130], rcx
0x18005269f  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x1800526a6  mov     [rsp+160h+var_138], r13
0x1800526ab  mov     dword ptr [rsp+160h+var_140], r13d
0x1800526b0  call    McTemplateU0pxqzr2pxqx_EventWriteTransfer
0x1800526b5  jmp     loc_1800523FA
0x1800526ba  mov     edx, 37h ; '7'
0x1800526bf  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x1800526c6  mov     ecx, 403h
0x1800526cb  call    WPP_SF_
0x1800526d0  jmp     loc_18005241C
0x1800526d5  mov     dword ptr [rsp+160h+var_138], r8d
0x1800526da  mov     edx, 35h ; '5'
0x1800526df  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x1800526e6  mov     dword ptr [rsp+160h+var_140], esi
0x1800526ea  mov     ecx, 403h
0x1800526ef  mov     r9, rbx
0x1800526f2  call    WPP_SF_qDD
0x1800526f7  jmp     loc_1800522E2
0x1800526fc  mov     rax, [rbx+60h]
0x180052700  mov     rcx, rdi
0x180052703  mov     r9d, [rbx+0D4h]
0x18005270a  mov     r8, [rbx+0C8h]
0x180052711  mov     rdx, [rbx+0C0h]
0x180052718  mov     [rsp+160h+var_118], rax
0x18005271d  mov     rax, [rbx+58h]
0x180052721  mov     [rsp+160h+var_120], rax
0x180052726  mov     eax, [rbx+0E8h]
0x18005272c  mov     dword ptr [rsp+160h+var_128], eax
0x180052730  mov     rax, [rbx+0E0h]
0x180052737  mov     [rsp+160h+var_130], rax
0x18005273c  mov     eax, [rbx+0DCh]
0x180052742  mov     dword ptr [rsp+160h+var_138], eax
0x180052746  mov     eax, [rbx+0D8h]
0x18005274c  mov     dword ptr [rsp+160h+var_140], eax
0x180052750  call    WapTcpStartDnsQuery
0x180052755  cmp     eax, 3E5h
0x18005275a  jnz     short loc_180052765
0x18005275c  mov     byte ptr [rbx+7Ch], 1
0x180052760  jmp     loc_1800523FA
0x180052765  mov     [rbx+68h], eax
0x180052768  jmp     loc_1800523FA
```
