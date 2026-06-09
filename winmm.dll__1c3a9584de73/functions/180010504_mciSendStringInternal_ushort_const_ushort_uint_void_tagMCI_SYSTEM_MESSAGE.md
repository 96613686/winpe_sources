# mciSendStringInternal(ushort const *,ushort *,uint,void *,tagMCI_SYSTEM_MESSAGE *)

- ea: `0x180010504`
- end: `0x180010c08`
- name: `?mciSendStringInternal@@YAKPEBGPEAGIPEAXPEAUtagMCI_SYSTEM_MESSAGE@@@Z`
- size: `1796`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, unsigned int@<r8d>, void *@<r9>, struct tagMCI_SYSTEM_MESSAGE *)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180011428`
- `0x180012060`

## callees

- `0x180003a2c`
- `0x180004700`
- `0x180009bb0`
- `0x18000a02c`
- `0x18000a264`
- `0x18000b6d4`
- `0x18000fb24`
- `0x18000fe40`
- `0x180010230`
- `0x180010504`
- `0x180010c10`
- `0x180010de8`
- `0x180013328`
- `0x180013408`
- `0x18001381c`
- `0x180015260`
- `0x1800153b8`
- `0x18001a408`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010739`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010739`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010790`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010879`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800108db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010790`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010879`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800108db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800105de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800105de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001083e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010850`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800108c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010be5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001083e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010850`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800108c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010be5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010700`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010a61`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010a7e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010700`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010a61`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010a7e`

## pseudocode

```c
__int64 __fastcall mciSendStringInternal(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        HWND a4,
        struct tagMCI_SYSTEM_MESSAGE *a5)
{
  struct tagMCI_SYSTEM_MESSAGE *v5; // r12
  unsigned __int16 *v7; // r15
  unsigned __int16 *v9; // r14
  __int64 v10; // rbx
  __int64 CurrentThreadId; // rsi
  unsigned __int64 v13; // rbx
  unsigned __int16 v14; // ax
  BOOL v15; // edx
  unsigned __int16 *v16; // rcx
  unsigned int v17; // edi
  HWND *v18; // r15
  WCHAR *v19; // rsi
  int v20; // ebx
  int v21; // edi
  unsigned int v22; // edi
  __int64 v23; // rdx
  unsigned int v24; // ebx
  unsigned int v25; // r12d
  unsigned __int16 *v26; // rbx
  int v27; // ecx
  unsigned int v28; // eax
  unsigned int v29; // r14d
  __int64 v30; // r12
  unsigned int v31; // ebx
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // r10d
  unsigned int v35; // [rsp+48h] [rbp-51h] BYREF
  unsigned int v36; // [rsp+4Ch] [rbp-4Dh] BYREF
  LPCWSTR pszDevice; // [rsp+50h] [rbp-49h] BYREF
  int v38; // [rsp+58h] [rbp-41h] BYREF
  int v39; // [rsp+5Ch] [rbp-3Dh]
  unsigned int v40; // [rsp+60h] [rbp-39h]
  LPVOID lpMem; // [rsp+68h] [rbp-31h] BYREF
  LPVOID v42; // [rsp+70h] [rbp-29h]
  int v43; // [rsp+78h] [rbp-21h] BYREF
  __int64 v44; // [rsp+80h] [rbp-19h] BYREF
  __int64 v45; // [rsp+88h] [rbp-11h]
  LPVOID v46; // [rsp+90h] [rbp-9h]
  unsigned __int16 *v47; // [rsp+98h] [rbp-1h] BYREF
  void *v48; // [rsp+A0h] [rbp+7h]
  __int64 v49; // [rsp+A8h] [rbp+Fh]
  int v50; // [rsp+B0h] [rbp+17h]
  int v51; // [rsp+B4h] [rbp+1Bh]
  unsigned __int16 *v52; // [rsp+F8h] [rbp+5Fh] BYREF
  unsigned __int16 *v53; // [rsp+100h] [rbp+67h]
  HWND v54; // [rsp+110h] [rbp+77h]

  v54 = a4;
  v53 = a2;
  v5 = a5;
  v38 = 0;
  v36 = 0;
  v7 = a2;
  v44 = 0;
  v35 = 0;
  v43 = -1;
  pszDevice = 0;
  lpMem = 0;
  v42 = 0;
  v39 = 0;
  if ( a5 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids);
    }
    v9 = *(unsigned __int16 **)v5;
    v7 = (unsigned __int16 *)*((_QWORD *)v5 + 2);
    a3 = *((_DWORD *)v5 + 6);
    v40 = *((_DWORD *)v5 + 2);
    v45 = *((_QWORD *)v5 + 4);
    v52 = v9;
    v53 = v7;
    v54 = hwndNotify;
    v46 = 0;
  }
  else
  {
    v10 = -1;
    do
      ++v10;
    while ( a1[v10] );
    CurrentThreadId = GetCurrentThreadId();
    if ( !a1 )
      return 267;
    v13 = 2 * v10 + 2;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids, a1);
    }
    v9 = (unsigned __int16 *)winmmAlloc((unsigned int)v13);
    if ( !v9 )
      return 264;
    v40 = 0;
    v45 = CurrentThreadId;
    v46 = v9;
    StringCbCopyW(v9, v13, a1);
    v14 = *v9;
    v52 = v9;
    if ( v14 )
    {
      v15 = 0;
      v16 = v9;
      do
      {
        if ( v14 == 34 )
        {
          v15 = !v15;
        }
        else if ( !v15 && v14 == 9 )
        {
          *v16 = 32;
        }
        v14 = *++v16;
      }
      while ( *v16 );
    }
  }
  if ( v7 )
    *v7 = 0;
  else
    a3 = 0;
  v17 = mciSeparateCommandParts(
          (const unsigned __int16 **)&v52,
          v5 != 0,
          (unsigned __int16 **)&lpMem,
          (unsigned __int16 **)&pszDevice);
  if ( !v17 )
  {
    v18 = 0;
    v19 = (WCHAR *)pszDevice;
    v20 = 0;
    LODWORD(a5) = mciGetDeviceIDW(pszDevice);
    v21 = (int)a5;
    if ( !(_DWORD)a5 && !lstrcmpiW(v19, wszNew) )
    {
      v20 = 1;
      *v19 = 0;
    }
    LODWORD(pszDevice) = v20;
    v22 = mciParseCommand(v21, (_DWORD)lpMem, (_DWORD)v19, (unsigned int)&v44, (__int64)&v43);
    EnterCriticalSection(&mciCritSec);
    if ( (_DWORD)a5 && (unsigned int)a5 < MCI_wNextDeviceID && *((_QWORD *)MCI_lpDeviceList + (unsigned int)a5) )
    {
      _mm_lfence();
      v23 = *((_QWORD *)MCI_lpDeviceList + (unsigned int)a5);
      if ( (*(_DWORD *)(v23 + 104) & 0x10000) != 0 )
      {
        v24 = 288;
LABEL_37:
        LeaveCriticalSection(&mciCritSec);
LABEL_38:
        v25 = (unsigned int)a5;
LABEL_39:
        HeapFree(hHeap, 0, lpMem);
        HeapFree(hHeap, 0, v19);
        if ( v18 )
          HeapFree(hHeap, 0, v18);
        mciParserFree(v42);
        if ( v24 < 0x200 )
          v17 = v24;
        else
          v17 = v24 | (v25 << 16);
        goto LABEL_117;
      }
      if ( !v5 && *(_QWORD *)(v23 + 88) != *(_QWORD *)(v23 + 80) && v22 != 2064 )
      {
        if ( !(unsigned int)mciFindNotify(v9) )
        {
          HeapFree(hHeap, 0, lpMem);
          HeapFree(hHeap, 0, v19);
          if ( a3 )
            v26 = (unsigned __int16 *)winmmAlloc(2 * a3 + 2);
          else
            v26 = 0;
          LeaveCriticalSection(&mciCritSec);
          if ( !a3 || v26 )
          {
            v17 = mciSendSystemString(v9, 0, v26, a3);
            if ( a3 )
            {
              StringCchCopyW(v53, a3, v26);
              HeapFree(hHeap, 0, v26);
            }
          }
          else
          {
            v17 = 264;
          }
          goto LABEL_117;
        }
        v24 = 300;
        goto LABEL_37;
      }
    }
    LeaveCriticalSection(&mciCritSec);
    if ( !*v19 )
    {
      if ( v22 == 2066 )
        goto LABEL_62;
      if ( !v20 )
      {
        v24 = 292;
        goto LABEL_38;
      }
    }
    if ( !v22 )
    {
      v24 = 261;
      goto LABEL_38;
    }
LABEL_62:
    if ( v20 && v22 != 2051 )
      goto LABEL_64;
    v25 = (unsigned int)a5;
    if ( (_DWORD)a5 || v22 - 2051 <= 0xF && (v27 = 40961, _bittest(&v27, v22 - 2051)) )
    {
      v29 = 0;
      v18 = (HWND *)winmmAlloc(0xA0u);
      if ( !v18 )
      {
        v24 = 264;
        goto LABEL_39;
      }
      v30 = v44;
      v24 = mciParseParams(v22, v52, v44, &v36, v18);
      if ( v24 )
        goto LABEL_38;
      v31 = v36;
      if ( (_DWORD)pszDevice && (v36 & 0x400) == 0 )
      {
        v24 = 299;
        goto LABEL_38;
      }
      if ( v22 == 2051 )
      {
        if ( (v36 & 0x2000) != 0 )
        {
          *(HWND *)((char *)v18 + 20) = (HWND)v19;
          v31 |= 0x200u;
        }
        else
        {
          if ( (_DWORD)pszDevice )
          {
LABEL_64:
            v24 = 263;
            goto LABEL_38;
          }
          *(HWND *)((char *)v18 + 12) = (HWND)v19;
          v31 |= 0x2000u;
          *(HWND *)((char *)v18 + 20) = 0;
        }
      }
      else if ( v22 == 2066 && *v19 )
      {
        if ( lstrcmpiW(v19, wszNotify) )
        {
          if ( lstrcmpiW(v19, wszWait) )
          {
            v18[1] = (HWND)v19;
            v31 |= 0x100u;
          }
          else
          {
            *v19 = 0;
            v31 |= 2u;
          }
        }
        else
        {
          *v19 = 0;
          v31 |= 1u;
        }
      }
      v32 = mciEatCommandEntry(v30, 0, 0);
      mciEatCommandEntry(v30 + v32, &v35, &v38);
      v25 = (unsigned int)a5;
      if ( v38 == 4 )
      {
        if ( (_DWORD)a5 == -1 && v22 != 2064 )
        {
          v24 = 279;
          goto LABEL_39;
        }
        if ( v35 == 1 )
        {
          v18[1] = (HWND)v53;
          *((_DWORD *)v18 + 4) = a3;
        }
        else if ( v35 == 2 || v35 == 7 || v35 == 10 || v35 == 11 || v35 - 12 <= 1 )
        {
          v29 = v35;
        }
      }
      *v18 = v54;
      if ( v22 == 2064 )
        *((_DWORD *)v18 + 6) = mciLookUpType(v19);
      v47 = v52;
      v48 = v42;
      v49 = v45;
      v50 = v39;
      v51 = 0;
      v33 = mciSendCommandInternal(
              v25,
              v22,
              v31 | (unsigned __int64)v40,
              (unsigned __int64)v18,
              (struct MCI_INTERNAL_OPEN_INFO *)&v47);
      v24 = (unsigned __int16)v33;
      v42 = v48;
      if ( (_WORD)v33 )
        goto LABEL_39;
      if ( (v33 & 0x80000) != 0 )
      {
        v34 = 2;
      }
      else
      {
        if ( !v29 )
          goto LABEL_39;
        v34 = v29;
      }
      if ( !a3 )
        goto LABEL_39;
      v28 = mciConvertReturnValue(v34, HIWORD(v33), v25, (unsigned __int64 *)v18, v53, a3);
    }
    else
    {
      if ( v22 == 2052 || v22 == 2065 )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids);
        }
        v24 = 263;
        goto LABEL_39;
      }
      v28 = mciAutoOpenDevice(v19, v9, v53, a3);
    }
    v24 = v28;
    goto LABEL_39;
  }
LABEL_117:
  if ( v46 )
    HeapFree(hHeap, 0, v46);
  return v17;
}

```

## disassembly

```asm
0x180010504  mov     rax, rsp
0x180010507  mov     [rax+18h], rbx
0x18001050b  mov     [rax+20h], r9
0x18001050f  mov     [rax+10h], rdx
0x180010513  push    rbp
0x180010514  push    rsi
0x180010515  push    rdi
0x180010516  push    r12
0x180010518  push    r13
0x18001051a  push    r14
0x18001051c  push    r15
0x18001051e  lea     rbp, [rax-57h]
0x180010522  sub     rsp, 0B0h
0x180010529  mov     r12, [rbp+4Fh+arg_20]
0x18001052d  xor     esi, esi
0x18001052f  mov     [rbp+4Fh+var_90], esi
0x180010532  mov     r13d, r8d
0x180010535  mov     [rbp+4Fh+var_9C], esi
0x180010538  mov     r15, rdx
0x18001053b  mov     [rbp+4Fh+var_68], rsi
0x18001053f  mov     rdi, rcx
0x180010542  mov     [rbp+4Fh+var_A0], esi
0x180010545  mov     [rbp+4Fh+var_70], 0FFFFFFFFh
0x18001054c  mov     [rbp+4Fh+pszDevice], rsi
0x180010550  mov     [rbp+4Fh+lpMem], rsi
0x180010554  mov     [rbp+4Fh+var_78], rsi
0x180010558  mov     [rbp+4Fh+var_8C], esi
0x18001055b  test    r12, r12
0x18001055e  jz      short loc_1800105D1
0x180010560  mov     rcx, cs:WPP_GLOBAL_Control
0x180010567  lea     r15, WPP_GLOBAL_Control
0x18001056e  cmp     rcx, r15
0x180010571  jz      short loc_180010595
0x180010573  test    dword ptr [rcx+1Ch], 400000h
0x18001057a  jz      short loc_180010595
0x18001057c  cmp     byte ptr [rcx+19h], 5
0x180010580  jb      short loc_180010595
0x180010582  mov     rcx, [rcx+10h]
0x180010586  lea     edx, [rsi+36h]
0x180010589  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x180010590  call    WPP_SF_
0x180010595  mov     r10d, [r12+8]
0x18001059a  mov     r14, [r12]
0x18001059e  mov     r15, [r12+10h]
0x1800105a3  mov     rax, cs:hwndNotify
0x1800105aa  mov     r13d, [r12+18h]
0x1800105af  mov     [rbp+4Fh+var_88], r10d
0x1800105b3  mov     r10, [r12+20h]
0x1800105b8  mov     [rbp+4Fh+var_60], r10
0x1800105bc  mov     [rbp+4Fh+arg_0], r14
0x1800105c0  mov     [rbp+4Fh+arg_8], r15
0x1800105c4  mov     [rbp+4Fh+arg_18], rax
0x1800105c8  mov     [rbp+4Fh+var_58], rsi
0x1800105cc  jmp     loc_1800106AB
0x1800105d1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800105d5  inc     rbx
0x1800105d8  cmp     [rcx+rbx*2], si
0x1800105dc  jnz     short loc_1800105D5
0x1800105de  call    cs:__imp_GetCurrentThreadId
0x1800105e4  mov     esi, eax
0x1800105e6  test    rdi, rdi
0x1800105e9  jnz     short loc_1800105F5
0x1800105eb  mov     eax, 10Bh
0x1800105f0  jmp     loc_180010BED
0x1800105f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105fc  lea     rax, WPP_GLOBAL_Control
0x180010603  lea     rbx, ds:2[rbx*2]
0x18001060b  cmp     rcx, rax
0x18001060e  jz      short loc_180010637
0x180010610  test    dword ptr [rcx+1Ch], 400000h
0x180010617  jz      short loc_180010637
0x180010619  cmp     byte ptr [rcx+19h], 4
0x18001061d  jb      short loc_180010637
0x18001061f  mov     rcx, [rcx+10h]
0x180010623  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x18001062a  mov     edx, 38h ; '8'
0x18001062f  mov     r9, rdi
0x180010632  call    WPP_SF_S
0x180010637  mov     ecx, ebx; Size
0x180010639  call    winmmAlloc
0x18001063e  mov     r14, rax
0x180010641  xor     eax, eax
0x180010643  test    r14, r14
0x180010646  jnz     short loc_180010652
0x180010648  mov     eax, 108h
0x18001064d  jmp     loc_180010BED
0x180010652  mov     r8, rdi; unsigned __int16 *
0x180010655  mov     [rbp+4Fh+var_88], eax
0x180010658  mov     rdx, rbx; unsigned __int64
0x18001065b  mov     [rbp+4Fh+var_60], rsi
0x18001065f  mov     rcx, r14; unsigned __int16 *
0x180010662  mov     [rbp+4Fh+var_58], r14
0x180010666  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18001066b  movzx   eax, word ptr [r14]
0x18001066f  xor     esi, esi
0x180010671  mov     [rbp+4Fh+arg_0], r14
0x180010675  test    ax, ax
0x180010678  jz      short loc_1800106AB
0x18001067a  mov     edx, esi
0x18001067c  mov     rcx, r14
0x18001067f  cmp     ax, 22h ; '"'
0x180010683  jnz     short loc_180010690
0x180010685  test    edx, edx
0x180010687  mov     eax, esi
0x180010689  setz    al
0x18001068c  mov     edx, eax
0x18001068e  jmp     short loc_18001069F
0x180010690  test    edx, edx
0x180010692  jnz     short loc_18001069F
0x180010694  cmp     ax, 9
0x180010698  jnz     short loc_18001069F
0x18001069a  mov     word ptr [rcx], 20h ; ' '
0x18001069f  add     rcx, 2
0x1800106a3  movzx   eax, word ptr [rcx]
0x1800106a6  test    ax, ax
0x1800106a9  jnz     short loc_18001067F
0x1800106ab  test    r15, r15
0x1800106ae  jnz     short loc_1800106B5
0x1800106b0  mov     r13d, esi
0x1800106b3  jmp     short loc_1800106B9
0x1800106b5  mov     [r15], si
0x1800106b9  mov     edx, esi
0x1800106bb  lea     r9, [rbp+4Fh+pszDevice]; unsigned __int16 **
0x1800106bf  test    r12, r12
0x1800106c2  lea     r8, [rbp+4Fh+lpMem]; unsigned __int16 **
0x1800106c6  lea     rcx, [rbp+4Fh+arg_0]; unsigned __int16 **
0x1800106ca  setnz   dl; int
0x1800106cd  call    ?mciSeparateCommandParts@@YAKPEAPEBGHPEAPEAG1@Z; mciSeparateCommandParts(ushort const * *,int,ushort * *,ushort * *)
0x1800106d2  mov     edi, eax
0x1800106d4  test    eax, eax
0x1800106d6  jnz     loc_180010BD0
0x1800106dc  mov     r15, rsi
0x1800106df  mov     rsi, [rbp+4Fh+pszDevice]
0x1800106e3  mov     rcx, rsi; pszDevice
0x1800106e6  call    mciGetDeviceIDW
0x1800106eb  xor     ebx, ebx
0x1800106ed  mov     dword ptr [rbp+4Fh+arg_20], eax
0x1800106f0  mov     edi, eax
0x1800106f2  test    eax, eax
0x1800106f4  jnz     short loc_180010712
0x1800106f6  lea     rdx, ?wszNew@@3PAGA; "new"
0x1800106fd  mov     rcx, rsi; lpString1
0x180010700  call    cs:__imp_lstrcmpiW
0x180010706  test    eax, eax
0x180010708  jnz     short loc_180010712
0x18001070a  xor     ecx, ecx
0x18001070c  lea     ebx, [rdi+1]
0x18001070f  mov     [rsi], cx
0x180010712  mov     rdx, [rbp+4Fh+lpMem]
0x180010716  lea     rax, [rbp+4Fh+var_70]
0x18001071a  lea     r9, [rbp+4Fh+var_68]
0x18001071e  mov     [rsp+0E0h+var_C0], rax
0x180010723  mov     r8, rsi
0x180010726  mov     dword ptr [rbp+4Fh+pszDevice], ebx
0x180010729  mov     ecx, edi
0x18001072b  call    mciParseCommand
0x180010730  lea     rcx, mciCritSec; lpCriticalSection
0x180010737  mov     edi, eax
0x180010739  call    cs:__imp_EnterCriticalSection
0x18001073f  mov     eax, dword ptr [rbp+4Fh+arg_20]
0x180010742  xor     r10d, r10d
0x180010745  test    eax, eax
0x180010747  jz      loc_1800108D4
0x18001074d  cmp     eax, cs:MCI_wNextDeviceID
0x180010753  jnb     loc_1800108D4
0x180010759  mov     rdx, cs:MCI_lpDeviceList
0x180010760  mov     r8d, eax
0x180010763  cmp     [rdx+rax*8], r10
0x180010767  jz      loc_1800108D4
0x18001076d  lfence
0x180010770  mov     rax, cs:MCI_lpDeviceList
0x180010777  mov     rdx, [rax+r8*8]
0x18001077b  test    dword ptr [rdx+68h], 10000h
0x180010782  jz      short loc_1800107F8
0x180010784  mov     ebx, 120h
0x180010789  lea     rcx, mciCritSec; lpCriticalSection
0x180010790  call    cs:__imp_LeaveCriticalSection
0x180010796  mov     r12d, dword ptr [rbp+4Fh+arg_20]
0x18001079a  mov     r8, [rbp+4Fh+lpMem]; lpMem
0x18001079e  xor     edx, edx; dwFlags
0x1800107a0  mov     rcx, cs:hHeap; hHeap
0x1800107a7  call    cs:__imp_HeapFree
0x1800107ad  mov     rcx, cs:hHeap; hHeap
0x1800107b4  mov     r8, rsi; lpMem
0x1800107b7  xor     edx, edx; dwFlags
0x1800107b9  call    cs:__imp_HeapFree
0x1800107bf  test    r15, r15
0x1800107c2  jz      short loc_1800107D6
0x1800107c4  mov     rcx, cs:hHeap; hHeap
0x1800107cb  mov     r8, r15; lpMem
0x1800107ce  xor     edx, edx; dwFlags
0x1800107d0  call    cs:__imp_HeapFree
0x1800107d6  mov     rcx, [rbp+4Fh+var_78]; lpMem
0x1800107da  call    mciParserFree
0x1800107df  cmp     ebx, 200h
0x1800107e5  jb      loc_180010BCE
0x1800107eb  mov     edi, r12d
0x1800107ee  shl     edi, 10h
0x1800107f1  or      edi, ebx
0x1800107f3  jmp     loc_180010BD0
0x1800107f8  test    r12, r12
0x1800107fb  jnz     loc_1800108D4
0x180010801  mov     rax, [rdx+50h]
0x180010805  cmp     [rdx+58h], rax
0x180010809  jz      loc_1800108D4
0x18001080f  cmp     edi, 810h
0x180010815  jz      loc_1800108D4
0x18001081b  mov     rcx, r14; unsigned __int16 *
0x18001081e  call    ?mciFindNotify@@YAHPEBG@Z; mciFindNotify(ushort const *)
0x180010823  test    eax, eax
0x180010825  jz      short loc_180010831
0x180010827  mov     ebx, 12Ch
0x18001082c  jmp     loc_180010789
0x180010831  mov     r8, [rbp+4Fh+lpMem]; lpMem
0x180010835  xor     edx, edx; dwFlags
0x180010837  mov     rcx, cs:hHeap; hHeap
0x18001083e  call    cs:__imp_HeapFree
0x180010844  mov     rcx, cs:hHeap; hHeap
0x18001084b  mov     r8, rsi; lpMem
0x18001084e  xor     edx, edx; dwFlags
0x180010850  call    cs:__imp_HeapFree
0x180010856  xor     esi, esi
0x180010858  test    r13d, r13d
0x18001085b  jz      short loc_18001086F
0x18001085d  lea     ecx, ds:2[r13*2]; Size
0x180010865  call    winmmAlloc
0x18001086a  mov     rbx, rax
0x18001086d  jmp     short loc_180010872
0x18001086f  mov     rbx, rsi
0x180010872  lea     rcx, mciCritSec; lpCriticalSection
0x180010879  call    cs:__imp_LeaveCriticalSection
0x18001087f  test    r13d, r13d
0x180010882  jz      short loc_180010893
0x180010884  test    rbx, rbx
0x180010887  jnz     short loc_180010893
0x180010889  mov     edi, 108h
0x18001088e  jmp     loc_180010BD0
0x180010893  mov     r9d, r13d; unsigned int
0x180010896  mov     r8, rbx; unsigned __int16 *
0x180010899  xor     edx, edx; unsigned int
0x18001089b  mov     rcx, r14; unsigned __int16 *
0x18001089e  call    ?mciSendSystemString@@YAKPEBGKPEAGI@Z; mciSendSystemString(ushort const *,ulong,ushort *,uint)
0x1800108a3  mov     edi, eax
0x1800108a5  test    r13d, r13d
0x1800108a8  jz      loc_180010BD0
0x1800108ae  mov     rcx, [rbp+4Fh+arg_8]; unsigned __int16 *
0x1800108b2  mov     r8, rbx; unsigned __int16 *
0x1800108b5  mov     edx, r13d; unsigned __int64
0x1800108b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800108bd  mov     rcx, cs:hHeap; hHeap
0x1800108c4  mov     r8, rbx; lpMem
0x1800108c7  xor     edx, edx; dwFlags
0x1800108c9  call    cs:__imp_HeapFree
0x1800108cf  jmp     loc_180010BD0
0x1800108d4  lea     rcx, mciCritSec; lpCriticalSection
0x1800108db  call    cs:__imp_LeaveCriticalSection
0x1800108e1  xor     eax, eax
0x1800108e3  cmp     [rsi], ax
0x1800108e6  jnz     short loc_1800108FE
0x1800108e8  cmp     edi, 812h
0x1800108ee  jz      short loc_18001090C
0x1800108f0  test    ebx, ebx
0x1800108f2  jnz     short loc_1800108FE
0x1800108f4  mov     ebx, 124h
0x1800108f9  jmp     loc_180010796
0x1800108fe  test    edi, edi
0x180010900  jnz     short loc_18001090C
0x180010902  mov     ebx, 105h
0x180010907  jmp     loc_180010796
0x18001090c  test    ebx, ebx
0x18001090e  jz      short loc_180010922
0x180010910  cmp     edi, 803h
0x180010916  jz      short loc_180010922
0x180010918  mov     ebx, 107h
0x18001091d  jmp     loc_180010796
0x180010922  mov     r12d, dword ptr [rbp+4Fh+arg_20]
0x180010926  test    r12d, r12d
0x180010929  jnz     short loc_1800109AA
0x18001092b  lea     eax, [rdi-803h]
0x180010931  cmp     eax, 0Fh
0x180010934  ja      short loc_180010940
0x180010936  mov     ecx, 0A001h
0x18001093b  bt      ecx, eax
0x18001093e  jb      short loc_1800109AA
0x180010940  cmp     edi, 804h
0x180010946  jz      short loc_180010969
0x180010948  cmp     edi, 811h
0x18001094e  jz      short loc_180010969
0x180010950  mov     r8, [rbp+4Fh+arg_8]; unsigned __int16 *
0x180010954  mov     r9d, r13d; unsigned int
0x180010957  mov     rdx, r14; unsigned __int16 *
0x18001095a  mov     rcx, rsi; unsigned __int16 *
0x18001095d  call    ?mciAutoOpenDevice@@YAIPEBG0PEAGI@Z; mciAutoOpenDevice(ushort const *,ushort const *,ushort *,uint)
0x180010962  mov     ebx, eax
0x180010964  jmp     loc_18001079A
0x180010969  mov     rcx, cs:WPP_GLOBAL_Control
0x180010970  lea     rax, WPP_GLOBAL_Control
0x180010977  cmp     rcx, rax
0x18001097a  jz      short loc_1800109A0
0x18001097c  test    dword ptr [rcx+1Ch], 400000h
  ... truncated ...
```
