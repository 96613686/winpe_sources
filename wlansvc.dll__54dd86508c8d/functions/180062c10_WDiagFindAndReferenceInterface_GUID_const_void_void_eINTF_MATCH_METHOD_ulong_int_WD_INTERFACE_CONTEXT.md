# WDiagFindAndReferenceInterface(_GUID const *,void *,void *,eINTF_MATCH_METHOD,ulong,int *,_WD_INTERFACE_CONTEXT * *)

- ea: `0x180062c10`
- end: `0x180063214`
- name: `?WDiagFindAndReferenceInterface@@YAKPEBU_GUID@@PEAX1W4eINTF_MATCH_METHOD@@KPEAHPEAPEAU_WD_INTERFACE_CONTEXT@@@Z`
- size: `1540`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180011558`
- `0x1800929a8`
- `0x1800f4fd4`

## callees

- `0x18001e950`
- `0x18001ea10`
- `0x180029d14`
- `0x18005aef0`
- `0x180062c10`
- `0x1801c81ac`
- `0x1801c82e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062d71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062ddd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062e21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062d71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062ddd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062e21`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062c62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062d10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062c62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062d10`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180062c74`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180062d1f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180062c74`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180062d1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062c53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062d04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063058`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800630d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800631af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062c53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062d04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063058`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800630d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800631af`

## pseudocode

```c
__int64 __fastcall WDiagFindAndReferenceInterface(
        const struct _GUID *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        struct _WD_INTERFACE_CONTEXT *a6,
        struct _WD_INTERFACE_CONTEXT **a7)
{
  struct _WD_INTERFACE_CONTEXT *v7; // r15
  struct _WD_INTERFACE_CONTEXT **v9; // r14
  DWORD CurrentThreadId; // ebx
  int v12; // ecx
  struct _WD_INTERFACE_CONTEXT *v13; // rdi
  unsigned int v14; // esi
  DWORD v15; // ebp
  __int64 v16; // rax
  int v17; // eax
  __int64 result; // rax
  PVOID *v19; // rax
  __int64 v20; // rax
  char v21; // al
  char v22; // al
  unsigned int v23; // eax
  char v24; // al
  int v25; // [rsp+28h] [rbp-70h]
  int v28; // [rsp+C0h] [rbp+28h]

  v7 = a6;
  v9 = a7;
  v28 = *(_DWORD *)a6;
  *a7 = 0;
  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection(&stru_1802A35F0);
  WaitForSingleObject(qword_1802A3640, 0xFFFFFFFF);
  v12 = dword_1802A3648;
  if ( (dword_1802A3648 & 4) != 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225)
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
  {
    WPP_SF_qqdsddsd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (char)&qword_1802A35E8,
      dword_1802A3650[0],
      qword_1802A3658,
      dword_1802A3654[0],
      CurrentThreadId,
      (__int64)"WDiagFindAndReferenceInterface",
      15);
    v12 = dword_1802A3648;
  }
  qword_1802A3658 = (__int64)"WDiagFindAndReferenceInterface";
  dword_1802A3648 = v12 | 4;
  v13 = (struct _WD_INTERFACE_CONTEXT *)&qword_1802A3670;
  *(_DWORD *)dword_1802A3650 = CurrentThreadId;
  *(_DWORD *)dword_1802A3654 = 271;
  *(_DWORD *)v7 = 0;
  while ( 1 )
  {
    v13 = *(struct _WD_INTERFACE_CONTEXT **)v13;
    if ( v13 == (struct _WD_INTERFACE_CONTEXT *)&qword_1802A3670 )
    {
      v14 = 1168;
      v13 = 0;
      a6 = 0;
      if ( v28 )
      {
        v23 = WDiagCreateNewInterface(a1, &a6);
        v13 = a6;
        v14 = v23;
        if ( !v23 )
        {
          WDiagAcquireExLock(
            a6,
            (struct _WD_INTERFACE_CONTEXT *)((char *)a6 + 3352),
            "WDiagFindAndReferenceInterface",
            0x177u);
          ++*((_DWORD *)v13 + 5);
          WDiagReleaseExLock(
            v13,
            (struct _WD_INTERFACE_CONTEXT *)((char *)v13 + 3352),
            "WDiagFindAndReferenceInterface",
            0x177u);
          *(_DWORD *)v7 = 1;
        }
      }
      goto LABEL_17;
    }
    v15 = GetCurrentThreadId();
    EnterCriticalSection((LPCRITICAL_SECTION)v13 + 84);
    WaitForSingleObject(*((HANDLE *)v13 + 430), 0xFFFFFFFF);
    if ( (*((_BYTE *)v13 + 3448) & 4) != 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      WPP_SF_qqdsddsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (_BYTE)v13 + 24,
        *((_DWORD *)v13 + 864),
        *((_QWORD *)v13 + 433),
        *((_DWORD *)v13 + 865),
        v15,
        (__int64)"WDiagFindAndReferenceInterface",
        25);
    }
    *((_DWORD *)v13 + 862) |= 4u;
    *((_DWORD *)v13 + 864) = v15;
    *((_QWORD *)v13 + 433) = "WDiagFindAndReferenceInterface";
    *((_DWORD *)v13 + 865) = 281;
    if ( !v13 || *((_DWORD *)v13 + 4) != 1347765833 )
    {
      *((_DWORD *)v13 + 862) &= ~4u;
      *((_DWORD *)v13 + 868) = 288;
      goto LABEL_10;
    }
    if ( !a4 )
      break;
    switch ( a4 )
    {
      case 1:
        if ( *((_QWORD *)v13 + 5) == a3 )
          goto LABEL_15;
        break;
      case 2:
        if ( *((_QWORD *)v13 + 4) == a2 )
          goto LABEL_15;
        break;
      case 3:
        v20 = *((_QWORD *)v13 + 436) - *(_QWORD *)&a1->Data1;
        if ( !v20 )
          v20 = *((_QWORD *)v13 + 437) - *(_QWORD *)a1->Data4;
        if ( !v20 )
        {
          if ( *((_QWORD *)v13 + 5) == a3 )
            goto LABEL_15;
          v19 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u
            || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) == 0 )
          {
            goto LABEL_22;
          }
          WPP_SF_qq(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            16,
            WPP_6ba1dcf276c838076ffc51ecd6e1ba00_Traceguids,
            a3,
            *((_QWORD *)v13 + 5));
        }
        break;
    }
LABEL_21:
    v19 = (PVOID *)WPP_GLOBAL_Control;
LABEL_22:
    if ( (*((_BYTE *)v13 + 3448) & 4) == 0
      && v19 != &WPP_GLOBAL_Control
      && *((_BYTE *)v19 + 225)
      && (*((_BYTE *)v19 + 228) & 0x40) != 0 )
    {
      v21 = GetCurrentThreadId();
      WPP_SF_qqDsdDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (_BYTE)v13 + 24,
        v25,
        *((_QWORD *)v13 + 435),
        *((_DWORD *)v13 + 868),
        v21,
        (__int64)"WDiagFindAndReferenceInterface",
        104);
    }
    *((_DWORD *)v13 + 862) &= ~4u;
    *((_DWORD *)v13 + 868) = 360;
LABEL_10:
    *((_QWORD *)v13 + 435) = "WDiagFindAndReferenceInterface";
    *((_DWORD *)v13 + 864) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)v13 + 84);
  }
  v16 = *((_QWORD *)v13 + 436) - *(_QWORD *)&a1->Data1;
  if ( !v16 )
    v16 = *((_QWORD *)v13 + 437) - *(_QWORD *)a1->Data4;
  if ( v16 )
    goto LABEL_21;
LABEL_15:
  ++*((_DWORD *)v13 + 5);
  if ( (*((_BYTE *)v13 + 3448) & 4) == 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225)
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
  {
    v22 = GetCurrentThreadId();
    WPP_SF_qqDsdDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (_BYTE)v13 + 24,
      v25,
      *((_QWORD *)v13 + 435),
      *((_DWORD *)v13 + 868),
      v22,
      (__int64)"WDiagFindAndReferenceInterface",
      98);
  }
  *((_DWORD *)v13 + 862) &= ~4u;
  *((_QWORD *)v13 + 435) = "WDiagFindAndReferenceInterface";
  *((_DWORD *)v13 + 864) = 0;
  *((_DWORD *)v13 + 868) = 354;
  LeaveCriticalSection((LPCRITICAL_SECTION)v13 + 84);
  v14 = 0;
LABEL_17:
  v17 = dword_1802A3648;
  if ( (dword_1802A3648 & 4) == 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225)
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
  {
    v24 = GetCurrentThreadId();
    WPP_SF_qqDsdDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (char)&qword_1802A35E8,
      v25,
      qword_1802A3668,
      dword_1802A3660[0],
      v24,
      (__int64)"WDiagFindAndReferenceInterface",
      126);
    v17 = dword_1802A3648;
  }
  *(_DWORD *)dword_1802A3660 = 382;
  dword_1802A3648 = v17 & 0xFFFFFFFB;
  *(_DWORD *)dword_1802A3650 = 0;
  qword_1802A3668 = (__int64)"WDiagFindAndReferenceInterface";
  LeaveCriticalSection(&stru_1802A35F0);
  result = v14;
  *v9 = v13;
  return result;
}

```

## disassembly

```asm
0x180062c10  mov     [rsp+arg_0], rbx
0x180062c15  mov     [rsp+arg_10], r8
0x180062c1a  mov     [rsp+arg_8], rdx
0x180062c1f  push    rbp
0x180062c20  push    rsi
0x180062c21  push    rdi
0x180062c22  push    r12
0x180062c24  push    r13
0x180062c26  push    r14
0x180062c28  push    r15
0x180062c2a  sub     rsp, 60h
0x180062c2e  mov     r15, [rsp+98h+arg_28]
0x180062c36  mov     r13d, r9d
0x180062c39  mov     r14, [rsp+98h+arg_30]
0x180062c41  mov     r12, rcx
0x180062c44  mov     ebp, [r15]
0x180062c47  mov     [rsp+98h+arg_20], ebp
0x180062c4e  xor     ebp, ebp
0x180062c50  mov     [r14], rbp
0x180062c53  call    cs:__imp_GetCurrentThreadId
0x180062c59  lea     rcx, stru_1802A35F0; lpCriticalSection
0x180062c60  mov     ebx, eax
0x180062c62  call    cs:__imp_EnterCriticalSection
0x180062c68  mov     rcx, cs:qword_1802A3640; hHandle
0x180062c6f  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180062c74  call    cs:__imp_WaitForSingleObject
0x180062c7a  mov     ecx, cs:dword_1802A3648
0x180062c80  lea     rdi, aWdiagfindandre_0; "WDiagFindAndReferenceInterface"
0x180062c87  lea     r9, qword_1802A35E8
0x180062c8e  lea     r8, WPP_GLOBAL_Control
0x180062c95  test    cl, 4
0x180062c98  jnz     loc_180062E9A
0x180062c9e  or      ecx, 4
0x180062ca1  mov     cs:qword_1802A3658, rdi
0x180062ca8  lea     rax, qword_1802A3670
0x180062caf  mov     cs:dword_1802A3648, ecx
0x180062cb5  mov     rdi, rax
0x180062cb8  mov     cs:dword_1802A3650, ebx
0x180062cbe  mov     cs:dword_1802A3654, 10Fh
0x180062cc8  mov     [r15], ebp
0x180062ccb  mov     rdi, [rdi]
0x180062cce  cmp     rdi, rax
0x180062cd1  jnz     short loc_180062CFD
0x180062cd3  cmp     [rsp+98h+arg_20], 0
0x180062cdb  mov     esi, 490h
0x180062ce0  mov     rdi, rbp
0x180062ce3  mov     [rsp+98h+arg_28], rbp
0x180062ceb  jnz     loc_18006311D
0x180062cf1  lea     r15, WPP_GLOBAL_Control
0x180062cf8  jmp     loc_180062DE5
0x180062cfd  lea     rbx, [rdi+0D18h]
0x180062d04  call    cs:__imp_GetCurrentThreadId
0x180062d0a  lea     rcx, [rbx+8]; lpCriticalSection
0x180062d0e  mov     ebp, eax
0x180062d10  call    cs:__imp_EnterCriticalSection
0x180062d16  mov     rcx, [rbx+58h]; hHandle
0x180062d1a  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180062d1f  call    cs:__imp_WaitForSingleObject
0x180062d25  test    byte ptr [rbx+60h], 4
0x180062d29  jnz     loc_180062F18
0x180062d2f  or      dword ptr [rbx+60h], 4
0x180062d33  mov     [rbx+68h], ebp
0x180062d36  lea     rbp, aWdiagfindandre_0; "WDiagFindAndReferenceInterface"
0x180062d3d  mov     [rbx+70h], rbp
0x180062d41  mov     dword ptr [rbx+6Ch], 119h
0x180062d48  test    rdi, rdi
0x180062d4b  jz      short loc_180062D56
0x180062d4d  cmp     dword ptr [rdi+10h], 50554649h
0x180062d54  jz      short loc_180062D83
0x180062d56  and     dword ptr [rbx+60h], 0FFFFFFFBh
0x180062d5a  mov     dword ptr [rbx+78h], 120h
0x180062d61  mov     [rbx+80h], rbp
0x180062d68  lea     rcx, [rbx+8]; lpCriticalSection
0x180062d6c  xor     ebp, ebp
0x180062d6e  mov     [rbx+68h], ebp
0x180062d71  call    cs:__imp_LeaveCriticalSection
0x180062d77  lea     rax, qword_1802A3670
0x180062d7e  jmp     loc_180062CCB
0x180062d83  test    r13d, r13d
0x180062d86  jnz     loc_180062E7E
0x180062d8c  mov     rax, [rdi+0DA0h]
0x180062d93  sub     rax, [r12]
0x180062d97  jnz     short loc_180062DA5
0x180062d99  mov     rax, [rdi+0DA8h]
0x180062da0  sub     rax, [r12+8]
0x180062da5  test    rax, rax
0x180062da8  jnz     loc_180062E56
0x180062dae  inc     dword ptr [rdi+14h]
0x180062db1  test    byte ptr [rbx+60h], 4
0x180062db5  jz      loc_1800630A2
0x180062dbb  lea     r15, WPP_GLOBAL_Control
0x180062dc2  and     dword ptr [rbx+60h], 0FFFFFFFBh
0x180062dc6  lea     rcx, [rbx+8]; lpCriticalSection
0x180062dca  mov     [rbx+80h], rbp
0x180062dd1  xor     ebp, ebp
0x180062dd3  mov     [rbx+68h], ebp
0x180062dd6  mov     dword ptr [rbx+78h], 162h
0x180062ddd  call    cs:__imp_LeaveCriticalSection
0x180062de3  mov     esi, ebp
0x180062de5  mov     eax, cs:dword_1802A3648
0x180062deb  test    al, 4
0x180062ded  jz      loc_180063185
0x180062df3  and     eax, 0FFFFFFFBh
0x180062df6  mov     cs:dword_1802A3660, 17Eh
0x180062e00  mov     cs:dword_1802A3648, eax
0x180062e06  lea     rcx, stru_1802A35F0; lpCriticalSection
0x180062e0d  lea     rax, aWdiagfindandre_0; "WDiagFindAndReferenceInterface"
0x180062e14  mov     cs:dword_1802A3650, ebp
0x180062e1a  mov     cs:qword_1802A3668, rax
0x180062e21  call    cs:__imp_LeaveCriticalSection
0x180062e27  mov     rbx, [rsp+98h+arg_0]
0x180062e2f  mov     eax, esi
0x180062e31  mov     [r14], rdi
0x180062e34  add     rsp, 60h
0x180062e38  pop     r15
0x180062e3a  pop     r14
0x180062e3c  pop     r13
0x180062e3e  pop     r12
0x180062e40  pop     rdi
0x180062e41  pop     rsi
0x180062e42  pop     rbp
0x180062e43  retn
0x180062e44  sub     ecx, 1
0x180062e47  jz      loc_18006301E
0x180062e4d  cmp     ecx, 1
0x180062e50  jz      loc_180062F91
0x180062e56  mov     rax, cs:WPP_GLOBAL_Control
0x180062e5d  lea     rdx, WPP_GLOBAL_Control
0x180062e64  test    byte ptr [rbx+60h], 4
0x180062e68  jz      loc_180063035
0x180062e6e  and     dword ptr [rbx+60h], 0FFFFFFFBh
0x180062e72  mov     dword ptr [rbx+78h], 168h
0x180062e79  jmp     loc_180062D61
0x180062e7e  mov     ecx, r13d
0x180062e81  sub     ecx, 1
0x180062e84  jnz     short loc_180062E44
0x180062e86  mov     rax, [rsp+98h+arg_10]
0x180062e8e  cmp     [rdi+28h], rax
0x180062e92  jz      loc_180062DAE
0x180062e98  jmp     short loc_180062E56
0x180062e9a  mov     rdx, cs:WPP_GLOBAL_Control
0x180062ea1  cmp     rdx, r8
0x180062ea4  jz      loc_180062C9E
0x180062eaa  cmp     byte ptr [rdx+0E1h], 1
0x180062eb1  jb      loc_180062C9E
0x180062eb7  test    byte ptr [rdx+0E4h], 40h
0x180062ebe  jz      loc_180062C9E
0x180062ec4  mov     eax, cs:dword_1802A3654
0x180062eca  mov     rcx, [rdx+0D8h]; LoggerHandle
0x180062ed1  mov     dword ptr [rsp+98h+var_48], 10Fh; char
0x180062ed9  mov     [rsp+98h+var_50], rdi; __int64
0x180062ede  mov     dword ptr [rsp+98h+var_58], ebx; char
0x180062ee2  mov     dword ptr [rsp+98h+var_60], eax; char
0x180062ee6  mov     rax, cs:qword_1802A3658
0x180062eed  mov     [rsp+98h+var_68], rax; __int64
0x180062ef2  mov     eax, cs:dword_1802A3650
0x180062ef8  mov     dword ptr [rsp+98h+var_70], eax; char
0x180062efc  mov     qword ptr [rsp+98h+var_78], r9; char
0x180062f01  lea     r9, ?g_WDiag@@3U_WDIAG_GLOBAL_CONTEXT@@A; _WDIAG_GLOBAL_CONTEXT g_WDiag
0x180062f08  call    WPP_SF_qqdsddsd
0x180062f0d  mov     ecx, cs:dword_1802A3648
0x180062f13  jmp     loc_180062C9E
0x180062f18  mov     rcx, cs:WPP_GLOBAL_Control
0x180062f1f  lea     rax, WPP_GLOBAL_Control
0x180062f26  cmp     rcx, rax
0x180062f29  jz      loc_180062D2F
0x180062f2f  cmp     byte ptr [rcx+0E1h], 1
0x180062f36  jb      loc_180062D2F
0x180062f3c  test    byte ptr [rcx+0E4h], 40h
0x180062f43  jz      loc_180062D2F
0x180062f49  mov     eax, [rbx+6Ch]
0x180062f4c  lea     rdx, aWdiagfindandre_0; "WDiagFindAndReferenceInterface"
0x180062f53  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180062f5a  mov     r9, rdi
0x180062f5d  mov     dword ptr [rsp+98h+var_48], 119h; char
0x180062f65  mov     [rsp+98h+var_50], rdx; __int64
0x180062f6a  mov     dword ptr [rsp+98h+var_58], ebp; char
0x180062f6e  mov     dword ptr [rsp+98h+var_60], eax; char
0x180062f72  mov     rax, [rbx+70h]
0x180062f76  mov     [rsp+98h+var_68], rax; __int64
0x180062f7b  mov     eax, [rbx+68h]
0x180062f7e  mov     dword ptr [rsp+98h+var_70], eax; char
0x180062f82  mov     qword ptr [rsp+98h+var_78], rbx; char
0x180062f87  call    WPP_SF_qqdsddsd
0x180062f8c  jmp     loc_180062D2F
0x180062f91  mov     rax, [rdi+0DA0h]
0x180062f98  sub     rax, [r12]
0x180062f9c  jnz     short loc_180062FAA
0x180062f9e  mov     rax, [rdi+0DA8h]
0x180062fa5  sub     rax, [r12+8]
0x180062faa  test    rax, rax
0x180062fad  jnz     loc_180062E56
0x180062fb3  mov     rcx, [rdi+28h]
0x180062fb7  mov     r8, [rsp+98h+arg_10]
0x180062fbf  cmp     rcx, r8
0x180062fc2  jz      loc_180062DAE
0x180062fc8  mov     rax, cs:WPP_GLOBAL_Control
0x180062fcf  lea     rdx, WPP_GLOBAL_Control
0x180062fd6  cmp     rax, rdx
0x180062fd9  jz      loc_180062E64
0x180062fdf  cmp     byte ptr [rax+0E1h], 3
0x180062fe6  jb      loc_180062E64
0x180062fec  test    byte ptr [rax+0E4h], 1
0x180062ff3  jz      loc_180062E64
0x180062ff9  mov     qword ptr [rsp+98h+var_78], rcx
0x180062ffe  mov     r9, r8
0x180063001  mov     rcx, [rax+0D8h]
0x180063008  lea     r8, WPP_6ba1dcf276c838076ffc51ecd6e1ba00_Traceguids
0x18006300f  mov     edx, 10h
0x180063014  call    WPP_SF_qq
0x180063019  jmp     loc_180062E56
0x18006301e  mov     rax, [rsp+98h+arg_8]
0x180063026  cmp     [rdi+20h], rax
0x18006302a  jz      loc_180062DAE
0x180063030  jmp     loc_180062E56
0x180063035  cmp     rax, rdx
0x180063038  jz      loc_180062E6E
0x18006303e  cmp     byte ptr [rax+0E1h], 1
0x180063045  jb      loc_180062E6E
0x18006304b  test    byte ptr [rax+0E4h], 40h
0x180063052  jz      loc_180062E6E
0x180063058  call    cs:__imp_GetCurrentThreadId
0x18006305e  mov     rcx, cs:WPP_GLOBAL_Control
0x180063065  mov     r9, rdi
0x180063068  mov     dword ptr [rsp+98h+var_48], 168h; char
0x180063070  mov     [rsp+98h+var_50], rbp; __int64
0x180063075  mov     dword ptr [rsp+98h+var_58], eax; char
0x180063079  mov     eax, [rbx+78h]
0x18006307c  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180063083  mov     dword ptr [rsp+98h+var_60], eax; char
0x180063087  mov     rax, [rbx+80h]
0x18006308e  mov     [rsp+98h+var_68], rax; __int64
0x180063093  mov     qword ptr [rsp+98h+var_78], rbx; char
0x180063098  call    WPP_SF_qqDsdDsd
0x18006309d  jmp     loc_180062E6E
0x1800630a2  mov     rax, cs:WPP_GLOBAL_Control
0x1800630a9  lea     r15, WPP_GLOBAL_Control
0x1800630b0  cmp     rax, r15
0x1800630b3  jz      loc_180062DC2
0x1800630b9  cmp     byte ptr [rax+0E1h], 1
0x1800630c0  jb      loc_180062DC2
0x1800630c6  test    byte ptr [rax+0E4h], 40h
0x1800630cd  jz      loc_180062DC2
0x1800630d3  call    cs:__imp_GetCurrentThreadId
0x1800630d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800630e0  mov     r9, rdi
0x1800630e3  mov     dword ptr [rsp+98h+var_48], 162h; char
0x1800630eb  mov     [rsp+98h+var_50], rbp; __int64
0x1800630f0  mov     dword ptr [rsp+98h+var_58], eax; char
0x1800630f4  mov     eax, [rbx+78h]
0x1800630f7  mov     rcx, [rcx+0D8h]; LoggerHandle
0x1800630fe  mov     dword ptr [rsp+98h+var_60], eax; char
0x180063102  mov     rax, [rbx+80h]
0x180063109  mov     [rsp+98h+var_68], rax; __int64
0x18006310e  mov     qword ptr [rsp+98h+var_78], rbx; char
0x180063113  call    WPP_SF_qqDsdDsd
0x180063118  jmp     loc_180062DC2
0x18006311d  lea     rdx, [rsp+98h+arg_28]; struct _WD_INTERFACE_CONTEXT **
0x180063125  mov     rcx, r12; struct _GUID *
0x180063128  call    ?WDiagCreateNewInterface@@YAKPEBU_GUID@@PEAPEAU_WD_INTERFACE_CONTEXT@@@Z; WDiagCreateNewInterface(_GUID const *,_WD_INTERFACE_CONTEXT * *)
0x18006312d  mov     rdi, [rsp+98h+arg_28]
0x180063135  mov     esi, eax
0x180063137  test    eax, eax
0x180063139  jnz     loc_180062CF1
0x18006313f  lea     r12, aWdiagfindandre_0; "WDiagFindAndReferenceInterface"
0x180063146  mov     r9d, 177h; unsigned int
0x18006314c  mov     r8, r12; char *
0x18006314f  lea     rdx, [rdi+0D18h]; struct _WDIAG_RW_LOCK *
0x180063156  mov     rcx, rdi; void *
0x180063159  call    ?WDiagAcquireExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagAcquireExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18006315e  inc     dword ptr [rdi+14h]
0x180063161  lea     rdx, [rdi+0D18h]; struct _WDIAG_RW_LOCK *
0x180063168  mov     r9d, 177h; unsigned int
0x18006316e  mov     r8, r12; char *
0x180063171  mov     rcx, rdi; void *
0x180063174  call    ?WDiagReleaseExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagReleaseExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x180063179  mov     dword ptr [r15], 1
0x180063180  jmp     loc_180062CF1
0x180063185  mov     rdx, cs:WPP_GLOBAL_Control
0x18006318c  cmp     rdx, r15
0x18006318f  jz      loc_180062DF3
0x180063195  cmp     byte ptr [rdx+0E1h], 1
0x18006319c  jb      loc_180062DF3
0x1800631a2  test    byte ptr [rdx+0E4h], 40h
0x1800631a9  jz      loc_180062DF3
0x1800631af  call    cs:__imp_GetCurrentThreadId
0x1800631b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800631bc  lea     rdx, aWdiagfindandre_0; "WDiagFindAndReferenceInterface"
0x1800631c3  mov     dword ptr [rsp+98h+var_48], 17Eh; char
0x1800631cb  lea     r9, ?g_WDiag@@3U_WDIAG_GLOBAL_CONTEXT@@A; _WDIAG_GLOBAL_CONTEXT g_WDiag
0x1800631d2  mov     [rsp+98h+var_50], rdx; __int64
0x1800631d7  mov     dword ptr [rsp+98h+var_58], eax; char
0x1800631db  mov     eax, cs:dword_1802A3660
0x1800631e1  mov     rcx, [rcx+0D8h]; LoggerHandle
0x1800631e8  mov     dword ptr [rsp+98h+var_60], eax; char
0x1800631ec  mov     rax, cs:qword_1802A3668
0x1800631f3  mov     [rsp+98h+var_68], rax; __int64
0x1800631f8  lea     rax, qword_1802A35E8
0x1800631ff  mov     qword ptr [rsp+98h+var_78], rax; char
0x180063204  call    WPP_SF_qqDsdDsd
  ... truncated ...
```
