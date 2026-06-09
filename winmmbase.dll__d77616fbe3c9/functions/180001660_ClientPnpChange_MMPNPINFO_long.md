# ClientPnpChange(_MMPNPINFO *,long)

- ea: `0x180001660`
- end: `0x180001b69`
- name: `?ClientPnpChange@@YAHPEAU_MMPNPINFO@@J@Z`
- size: `1289`
- prototype: `__int64 __fastcall(struct _MMPNPINFO *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800065d0`

## callees

- `0x180001660`
- `0x1800023f0`
- `0x180002460`
- `0x180002558`
- `0x180002718`
- `0x180007d70`
- `0x18000f5d8`
- `0x180012e1c`
- `0x18001cbc8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001885`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001885`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001683`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001690`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800017d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001683`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001690`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800017d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800017fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001837`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001844`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800018c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800017fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001837`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001844`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800018c5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800018a3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800018a3`

## pseudocode

```c
__int64 __fastcall ClientPnpChange(struct _MMPNPINFO *a1)
{
  unsigned int v1; // r12d
  __int64 *v3; // rax
  int v4; // ebp
  unsigned __int64 v5; // r14
  unsigned __int64 v6; // rsi
  const WCHAR *v7; // rdi
  unsigned __int64 v8; // rbx
  PVOID *v9; // rcx
  unsigned int v10; // edi
  const unsigned __int16 *v11; // rax
  const unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  bool v14; // zf
  __int64 *v15; // rbx
  __int64 *v16; // rdi
  int i; // ebp
  int v18; // ecx
  unsigned __int64 v19; // rbx
  __int64 *v20; // rsi
  __int64 v21; // rdi
  __int64 v22; // rdx
  int v24; // edx
  int v25; // r8d
  __int64 v26; // rax
  unsigned int v27; // r9d
  unsigned int v28; // r9d

  v1 = 0;
  EnterCriticalSection(&NumDevsCritSec);
  EnterCriticalSection(&DriverLoadFreeCritSec);
  v3 = (__int64 *)wdmDevZ;
  if ( wdmDevZ )
  {
    do
    {
      *((_DWORD *)v3 + 3) = 1;
      v3 = (__int64 *)*v3;
    }
    while ( v3 );
  }
  v4 = *((_DWORD *)a1 + 2);
  v5 = ((unsigned __int64)a1 + 19) & 0xFFFFFFFFFFFFFFF8uLL;
  v6 = v5;
  if ( !v4 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  do
  {
    v7 = (const WCHAR *)wdmDevZ;
    v8 = v6 + 12;
    while ( 1 )
    {
      if ( !v7 )
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids, v6 + 12);
          v9 = (PVOID *)WPP_GLOBAL_Control;
        }
        v10 = *(_DWORD *)(v6 + 8);
        if ( (v10 & 1) != 0 )
          goto LABEL_12;
        v11 = wdmDevInterfaceInstall((const unsigned __int16 *)(v6 + 12), *(_QWORD *)v6, v10);
        v12 = v11;
        if ( v11 )
        {
          wdmDriverLoadAllClasses(v11, 0, v10);
          wdmDevInterfaceDec(v12);
        }
LABEL_11:
        v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_12:
        v1 = 1;
        goto LABEL_13;
      }
      if ( CompareStringW(0x7Fu, 1u, v7 + 16, -1, (PCNZWCH)(v6 + 12), -1) == 2 )
        break;
      v7 = *(const WCHAR **)v7;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, v25, v6 + 12, (char)v7, *((_DWORD *)v7 + 4));
    }
    v26 = *((_QWORD *)v7 + 3);
    *((_DWORD *)v7 + 3) = 0;
    if ( *(_QWORD *)v6 != v26 || *((_DWORD *)v7 + 4) )
    {
      *((_DWORD *)v7 + 4) = 0;
      wdmPnpUpdateDriver(0x8004u, (const unsigned __int16 *)(v6 + 12), 0, *(_DWORD *)(v6 + 8));
      v27 = *(_DWORD *)(v6 + 8);
      if ( (v27 & 1) == 0 )
        wdmPnpUpdateDriver(0x8000u, (const unsigned __int16 *)(v6 + 12), *(_QWORD *)v6, v27);
      goto LABEL_11;
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_13:
    v13 = -1;
    do
      v14 = *(_WORD *)(v8 + 2 * v13++ + 2) == 0;
    while ( !v14 );
    v6 = (v8 + 2 * v13 + 9) & 0xFFFFFFFFFFFFFFF8uLL;
    --v4;
  }
  while ( v4 );
LABEL_16:
  v15 = (__int64 *)wdmDevZ;
  if ( wdmDevZ )
  {
    do
    {
      v16 = (__int64 *)*v15;
      if ( *((_DWORD *)v15 + 3) )
      {
        if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x400000) != 0 && *((_BYTE *)v9 + 25) >= 4u )
          WPP_SF_S(v9[2], 20, &WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids, v15 + 4);
        v28 = *((_DWORD *)v15 + 2);
        v15[3] = 0;
        *((_DWORD *)v15 + 4) = 1;
        wdmPnpUpdateDriver(0x8004u, (const unsigned __int16 *)v15 + 16, 0, v28);
        v9 = (PVOID *)WPP_GLOBAL_Control;
        v1 = 1;
      }
      v15 = v16;
    }
    while ( v16 );
  }
  for ( i = *((_DWORD *)a1 + 2); i; --i )
  {
    v18 = *(_DWORD *)(v5 + 8);
    v19 = v5 + 12;
    if ( (v18 & 1) == 0 )
    {
      if ( (v18 & 2) != 0 )
      {
        v20 = (__int64 *)&waveindrvZ;
LABEL_23:
        EnterCriticalSection(&NumDevsCritSec);
        v21 = *v20;
        if ( (__int64 *)*v20 == v20 )
          goto LABEL_26;
        while ( (*(_BYTE *)(v21 + 112) & 2) != 0 || lstrcmpW(*(LPCWSTR *)(v21 + 96), (LPCWSTR)(v5 + 12)) )
        {
          v21 = *(_QWORD *)v21;
          if ( (__int64 *)v21 == v20 )
            goto LABEL_26;
        }
        if ( (__int64 *)v21 == v20 )
        {
LABEL_26:
          LeaveCriticalSection(&NumDevsCritSec);
        }
        else
        {
          _InterlockedIncrement((volatile signed __int32 *)(v21 + 92));
          LeaveCriticalSection(&NumDevsCritSec);
          if ( *(int *)(v5 + 8) >= 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                22,
                (unsigned int)&WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids,
                v5 + 12,
                *(int *)(v21 + 112) < 0);
            }
            *(_DWORD *)(v21 + 112) &= ~0x80000000;
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                21,
                &WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids,
                v5 + 12);
            }
            *(_DWORD *)(v21 + 112) |= 0x80000000;
          }
          if ( (*(_DWORD *)(v5 + 8) & 0x40000000) != 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                23,
                &WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids,
                v5 + 12);
            }
            *(_DWORD *)(v21 + 112) |= 0x40000000u;
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                24,
                (unsigned int)&WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids,
                v5 + 12,
                (*(_DWORD *)(v21 + 112) & 0x40000000) != 0);
            }
            *(_DWORD *)(v21 + 112) &= ~0x40000000u;
          }
          mregDecUsagePtr((struct _MMDRV *)v21);
        }
        goto LABEL_27;
      }
      if ( (v18 & 4) != 0 )
      {
        v20 = &waveoutdrvZ;
        goto LABEL_23;
      }
    }
LABEL_27:
    v22 = -1;
    do
      v14 = *(_WORD *)(v19 + 2 * v22++ + 2) == 0;
    while ( !v14 );
    v5 = (v19 + 2 * v22 + 9) & 0xFFFFFFFFFFFFFFF8uLL;
  }
  LeaveCriticalSection(&DriverLoadFreeCritSec);
  LeaveCriticalSection(&NumDevsCritSec);
  return v1;
}

```

## disassembly

```asm
0x180001660  mov     [rsp+arg_10], rbx
0x180001665  push    rbp
0x180001666  push    rsi
0x180001667  push    r12
0x180001669  push    r13
0x18000166b  push    r14
0x18000166d  sub     rsp, 30h
0x180001671  mov     [rsp+58h+arg_8], r15
0x180001676  xor     r12d, r12d
0x180001679  mov     r15, rcx
0x18000167c  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180001683  call    cs:__imp_EnterCriticalSection
0x180001689  lea     rcx, DriverLoadFreeCritSec; lpCriticalSection
0x180001690  call    cs:__imp_EnterCriticalSection
0x180001696  mov     rax, qword ptr cs:?wdmDevZ@@3Utag_wdmdeviceinterface@@A; tag_wdmdeviceinterface wdmDevZ
0x18000169d  test    rax, rax
0x1800016a0  jz      short loc_1800016B1
0x1800016a2  mov     dword ptr [rax+0Ch], 1
0x1800016a9  mov     rax, [rax]
0x1800016ac  test    rax, rax
0x1800016af  jnz     short loc_1800016A2
0x1800016b1  mov     ebp, [r15+8]
0x1800016b5  lea     r14, [r15+13h]
0x1800016b9  and     r14, 0FFFFFFFFFFFFFFF8h
0x1800016bd  mov     [rsp+58h+arg_0], rdi
0x1800016c2  lea     r13, WPP_GLOBAL_Control
0x1800016c9  mov     rsi, r14
0x1800016cc  test    ebp, ebp
0x1800016ce  jz      loc_180001940
0x1800016d4  nop     dword ptr [rax+00h]
0x1800016d8  nop     dword ptr [rax+rax+00000000h]
0x1800016e0  mov     rdi, qword ptr cs:?wdmDevZ@@3Utag_wdmdeviceinterface@@A; tag_wdmdeviceinterface wdmDevZ
0x1800016e7  lea     rbx, [rsi+0Ch]
0x1800016eb  test    rdi, rdi
0x1800016ee  jnz     loc_180001864
0x1800016f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800016fb  cmp     rcx, r13
0x1800016fe  jz      short loc_18000170D
0x180001700  test    dword ptr [rcx+1Ch], 400000h
0x180001707  jnz     loc_1800019E1
0x18000170d  mov     edi, [rsi+8]
0x180001710  test    dil, 1
0x180001714  jnz     short loc_180001748
0x180001716  mov     rdx, [rsi]; unsigned __int64
0x180001719  mov     r8d, edi; unsigned int
0x18000171c  mov     rcx, rbx; unsigned __int16 *
0x18000171f  call    ?wdmDevInterfaceInstall@@YAPEBGPEBG_KK@Z; wdmDevInterfaceInstall(ushort const *,unsigned __int64,ulong)
0x180001724  mov     rsi, rax
0x180001727  test    rax, rax
0x18000172a  jz      short loc_180001741
0x18000172c  mov     r8d, edi; unsigned int
0x18000172f  xor     edx, edx; unsigned int
0x180001731  mov     rcx, rax; unsigned __int16 *
0x180001734  call    ?wdmDriverLoadAllClasses@@YAXPEBGII@Z; wdmDriverLoadAllClasses(ushort const *,uint,uint)
0x180001739  mov     rcx, rsi
0x18000173c  call    wdmDevInterfaceDec
0x180001741  mov     rcx, cs:WPP_GLOBAL_Control
0x180001748  mov     r12d, 1
0x18000174e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001755  nop     word ptr [rax+rax+00000000h]
0x180001760  cmp     word ptr [rbx+rax*2+2], 0
0x180001766  lea     rax, [rax+1]
0x18000176a  jnz     short loc_180001760
0x18000176c  lea     rsi, ds:9[rax*2]
0x180001774  add     rsi, rbx
0x180001777  and     rsi, 0FFFFFFFFFFFFFFF8h
0x18000177b  add     ebp, 0FFFFFFFFh
0x18000177e  jnz     loc_1800016E0
0x180001784  mov     rbx, qword ptr cs:?wdmDevZ@@3Utag_wdmdeviceinterface@@A; tag_wdmdeviceinterface wdmDevZ
0x18000178b  test    rbx, rbx
0x18000178e  jz      short loc_1800017A5
0x180001790  cmp     dword ptr [rbx+0Ch], 0
0x180001794  mov     rdi, [rbx]
0x180001797  jnz     loc_180001A0F
0x18000179d  mov     rbx, rdi
0x1800017a0  test    rdi, rdi
0x1800017a3  jnz     short loc_180001790
0x1800017a5  mov     ebp, [r15+8]
0x1800017a9  mov     r15, [rsp+58h+arg_8]
0x1800017ae  test    ebp, ebp
0x1800017b0  jz      short loc_180001830
0x1800017b2  mov     ecx, [r14+8]
0x1800017b6  lea     rbx, [r14+0Ch]
0x1800017ba  test    cl, 1
0x1800017bd  jnz     short loc_180001803
0x1800017bf  test    cl, 2
0x1800017c2  jz      loc_180001A72
0x1800017c8  lea     rsi, waveindrvZ
0x1800017cf  lea     rcx, NumDevsCritSec; lpCriticalSection
0x1800017d6  call    cs:__imp_EnterCriticalSection
0x1800017dc  mov     rdi, [rsi]
0x1800017df  cmp     rdi, rsi
0x1800017e2  jz      short loc_1800017F6
0x1800017e4  test    byte ptr [rdi+70h], 2
0x1800017e8  jz      loc_18000189C
0x1800017ee  mov     rdi, [rdi]
0x1800017f1  cmp     rdi, rsi
0x1800017f4  jnz     short loc_1800017E4
0x1800017f6  lea     rcx, NumDevsCritSec; lpCriticalSection
0x1800017fd  call    cs:__imp_LeaveCriticalSection
0x180001803  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000180a  nop     word ptr [rax+rax+00h]
0x180001810  cmp     word ptr [rbx+rdx*2+2], 0
0x180001816  lea     rdx, [rdx+1]
0x18000181a  jnz     short loc_180001810
0x18000181c  lea     r14, ds:9[rdx*2]
0x180001824  add     r14, rbx
0x180001827  and     r14, 0FFFFFFFFFFFFFFF8h
0x18000182b  add     ebp, 0FFFFFFFFh
0x18000182e  jnz     short loc_1800017B2
0x180001830  lea     rcx, DriverLoadFreeCritSec; lpCriticalSection
0x180001837  call    cs:__imp_LeaveCriticalSection
0x18000183d  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180001844  call    cs:__imp_LeaveCriticalSection
0x18000184a  mov     rdi, [rsp+58h+arg_0]
0x18000184f  mov     eax, r12d
0x180001852  mov     rbx, [rsp+58h+arg_10]
0x180001857  add     rsp, 30h
0x18000185b  pop     r14
0x18000185d  pop     r13
0x18000185f  pop     r12
0x180001861  pop     rsi
0x180001862  pop     rbp
0x180001863  retn
0x180001864  lea     r8, [rdi+20h]; lpString1
0x180001868  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180001870  mov     edx, 1; dwCmpFlags
0x180001875  mov     [rsp+58h+lpString2], rbx; lpString2
0x18000187a  mov     ecx, 7Fh; Locale
0x18000187f  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001885  call    cs:__imp_CompareStringW
0x18000188b  cmp     eax, 2
0x18000188e  jz      loc_18000194C
0x180001894  mov     rdi, [rdi]
0x180001897  jmp     loc_1800016EB
0x18000189c  mov     rcx, [rdi+60h]; lpString1
0x1800018a0  mov     rdx, rbx; lpString2
0x1800018a3  call    cs:__imp_lstrcmpW
0x1800018a9  test    eax, eax
0x1800018ab  jnz     loc_1800017EE
0x1800018b1  cmp     rdi, rsi
0x1800018b4  jz      loc_1800017F6
0x1800018ba  lock inc dword ptr [rdi+5Ch]
0x1800018be  lea     rcx, NumDevsCritSec; lpCriticalSection
0x1800018c5  call    cs:__imp_LeaveCriticalSection
0x1800018cb  cmp     dword ptr [r14+8], 0
0x1800018d0  jge     loc_180001ABB
0x1800018d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800018dd  cmp     rcx, r13
0x1800018e0  jnz     loc_180001A87
0x1800018e6  or      dword ptr [rdi+70h], 80000000h
0x1800018ed  test    dword ptr [r14+8], 40000000h
0x1800018f5  mov     eax, [rdi+70h]
0x1800018f8  jz      short loc_180001927
0x1800018fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180001901  cmp     rcx, r13
0x180001904  jz      short loc_180001913
0x180001906  test    dword ptr [rcx+1Ch], 400000h
0x18000190d  jnz     loc_180001B04
0x180001913  or      dword ptr [rdi+70h], 40000000h
0x18000191a  mov     rcx, rdi; struct _MMDRV *
0x18000191d  call    mregDecUsagePtr
0x180001922  jmp     loc_180001803
0x180001927  mov     rcx, cs:WPP_GLOBAL_Control
0x18000192e  cmp     rcx, r13
0x180001931  jnz     loc_180001B2B
0x180001937  and     dword ptr [rdi+70h], 0BFFFFFFFh
0x18000193e  jmp     short loc_18000191A
0x180001940  mov     rcx, cs:WPP_GLOBAL_Control
0x180001947  jmp     loc_180001784
0x18000194c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001953  cmp     rcx, r13
0x180001956  jnz     short loc_18000197A
0x180001958  mov     rax, [rdi+18h]
0x18000195c  mov     dword ptr [rdi+0Ch], 0
0x180001963  cmp     [rsi], rax
0x180001966  jnz     short loc_1800019A3
0x180001968  cmp     dword ptr [rdi+10h], 0
0x18000196c  jnz     short loc_1800019A3
0x18000196e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001975  jmp     loc_18000174E
0x18000197a  test    dword ptr [rcx+1Ch], 400000h
0x180001981  jz      short loc_180001958
0x180001983  cmp     byte ptr [rcx+19h], 4
0x180001987  jb      short loc_180001958
0x180001989  mov     eax, [rdi+10h]
0x18000198c  mov     r9, rbx
0x18000198f  mov     rcx, [rcx+10h]
0x180001993  mov     [rsp+58h+cchCount2], eax
0x180001997  mov     [rsp+58h+lpString2], rdi
0x18000199c  call    WPP_SF_Sqd
0x1800019a1  jmp     short loc_180001958
0x1800019a3  mov     dword ptr [rdi+10h], 0
0x1800019aa  xor     r8d, r8d; unsigned __int64
0x1800019ad  mov     r9d, [rsi+8]; unsigned int
0x1800019b1  mov     rdx, rbx; unsigned __int16 *
0x1800019b4  mov     ecx, 8004h; unsigned int
0x1800019b9  call    ?wdmPnpUpdateDriver@@YAXKPEBG_KK@Z; wdmPnpUpdateDriver(ulong,ushort const *,unsigned __int64,ulong)
0x1800019be  mov     r9d, [rsi+8]; unsigned int
0x1800019c2  test    r9b, 1
0x1800019c6  jnz     loc_180001741
0x1800019cc  mov     r8, [rsi]; unsigned __int64
0x1800019cf  mov     rdx, rbx; unsigned __int16 *
0x1800019d2  mov     ecx, 8000h; unsigned int
0x1800019d7  call    ?wdmPnpUpdateDriver@@YAXKPEBG_KK@Z; wdmPnpUpdateDriver(ulong,ushort const *,unsigned __int64,ulong)
0x1800019dc  jmp     loc_180001741
0x1800019e1  cmp     byte ptr [rcx+19h], 4
0x1800019e5  jb      loc_18000170D
0x1800019eb  mov     rcx, [rcx+10h]
0x1800019ef  lea     r8, WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids
0x1800019f6  mov     edx, 13h
0x1800019fb  mov     r9, rbx
0x1800019fe  call    WPP_SF_S
0x180001a03  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a0a  jmp     loc_18000170D
0x180001a0f  cmp     rcx, r13
0x180001a12  jz      short loc_180001A3C
0x180001a14  test    dword ptr [rcx+1Ch], 400000h
0x180001a1b  jz      short loc_180001A3C
0x180001a1d  cmp     byte ptr [rcx+19h], 4
0x180001a21  jb      short loc_180001A3C
0x180001a23  mov     rcx, [rcx+10h]
0x180001a27  lea     r9, [rbx+20h]
0x180001a2b  mov     edx, 14h
0x180001a30  lea     r8, WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids
0x180001a37  call    WPP_SF_S
0x180001a3c  mov     r9d, [rbx+8]; unsigned int
0x180001a40  lea     rdx, [rbx+20h]; unsigned __int16 *
0x180001a44  xor     r8d, r8d; unsigned __int64
0x180001a47  mov     qword ptr [rbx+18h], 0
0x180001a4f  mov     ecx, 8004h; unsigned int
0x180001a54  mov     dword ptr [rbx+10h], 1
0x180001a5b  call    ?wdmPnpUpdateDriver@@YAXKPEBG_KK@Z; wdmPnpUpdateDriver(ulong,ushort const *,unsigned __int64,ulong)
0x180001a60  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a67  mov     r12d, 1
0x180001a6d  jmp     loc_18000179D
0x180001a72  test    cl, 4
0x180001a75  jz      loc_180001803
0x180001a7b  lea     rsi, waveoutdrvZ
0x180001a82  jmp     loc_1800017CF
0x180001a87  test    dword ptr [rcx+1Ch], 400000h
0x180001a8e  jz      loc_1800018E6
0x180001a94  cmp     byte ptr [rcx+19h], 4
0x180001a98  jb      loc_1800018E6
0x180001a9e  mov     rcx, [rcx+10h]
0x180001aa2  lea     r8, WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids
0x180001aa9  mov     edx, 15h
0x180001aae  mov     r9, rbx
0x180001ab1  call    WPP_SF_S
0x180001ab6  jmp     loc_1800018E6
0x180001abb  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ac2  cmp     rcx, r13
0x180001ac5  jz      short loc_180001AF8
0x180001ac7  test    dword ptr [rcx+1Ch], 400000h
0x180001ace  jz      short loc_180001AF8
0x180001ad0  cmp     byte ptr [rcx+19h], 4
0x180001ad4  jb      short loc_180001AF8
0x180001ad6  mov     eax, [rdi+70h]
0x180001ad9  lea     r8, WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids
0x180001ae0  mov     rcx, [rcx+10h]
0x180001ae4  mov     edx, 16h
0x180001ae9  shr     eax, 1Fh
0x180001aec  mov     r9, rbx
0x180001aef  mov     dword ptr [rsp+58h+lpString2], eax
0x180001af3  call    WPP_SF_Sd
0x180001af8  and     dword ptr [rdi+70h], 7FFFFFFFh
0x180001aff  jmp     loc_1800018ED
0x180001b04  cmp     byte ptr [rcx+19h], 4
0x180001b08  jb      loc_180001913
0x180001b0e  mov     rcx, [rcx+10h]
0x180001b12  lea     r8, WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids
0x180001b19  mov     edx, 17h
0x180001b1e  mov     r9, rbx
0x180001b21  call    WPP_SF_S
0x180001b26  jmp     loc_180001913
0x180001b2b  test    dword ptr [rcx+1Ch], 400000h
0x180001b32  jz      loc_180001937
0x180001b38  cmp     byte ptr [rcx+19h], 4
0x180001b3c  jb      loc_180001937
0x180001b42  mov     rcx, [rcx+10h]
0x180001b46  lea     r8, WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids
0x180001b4d  shr     eax, 1Eh
0x180001b50  mov     edx, 18h
0x180001b55  and     eax, 1
0x180001b58  mov     r9, rbx
0x180001b5b  mov     dword ptr [rsp+58h+lpString2], eax
0x180001b5f  call    WPP_SF_Sd
0x180001b64  jmp     loc_180001937
```
