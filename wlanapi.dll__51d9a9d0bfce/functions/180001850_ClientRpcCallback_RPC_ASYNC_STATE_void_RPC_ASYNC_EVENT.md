# ClientRpcCallback(_RPC_ASYNC_STATE *,void *,_RPC_ASYNC_EVENT)

- ea: `0x180001850`
- end: `0x1800021c4`
- name: `?ClientRpcCallback@@YAXPEAU_RPC_ASYNC_STATE@@PEAXW4_RPC_ASYNC_EVENT@@@Z`
- size: `2420`
- prototype: `void __fastcall(PRPC_ASYNC_STATE pAsync, void *, enum _RPC_ASYNC_EVENT)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180001850`
- `0x1800021cc`
- `0x1800053c0`
- `0x180005610`
- `0x1800063a0`
- `0x180006934`
- `0x18001de28`
- `0x18001de80`
- `0x180060148`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800019a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800019c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800019a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800019c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800019b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800019d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800019b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800019d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800018c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800018c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001a6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001a6c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001b66`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001b66`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180001a02`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180001a02`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800018df`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800018df`
- `RPCRT4!RpcExceptionFilter` at `0x1800601ce`
- `RPCRT4!RpcExceptionFilter` at `0x1800601ce`

## pseudocode

```c
void __fastcall ClientRpcCallback(PRPC_ASYNC_STATE pAsync, void *a2, enum _RPC_ASYNC_EVENT a3)
{
  int v4; // r14d
  union DOT11_OUI_HEADER *v5; // rcx
  char *UserInfo; // rbx
  RPC_STATUS v7; // eax
  __int16 *v8; // r8
  union DOT11_OUI_HEADER *v9; // rcx
  _QWORD *v10; // r15
  unsigned int *v11; // r12
  unsigned int v12; // edx
  unsigned int *v13; // r9
  void *v14; // r12
  HANDLE ProcessHeap; // rax
  void *v16; // r12
  HANDLE v17; // rax
  unsigned int v18; // edx
  __int64 v19; // rdx
  __int64 v20; // r10
  _OWORD *v21; // rax
  int *v22; // rcx
  __int64 v23; // rax
  __int16 *v24; // rcx
  __int64 v25; // rdx
  __int16 v26; // r9
  __int16 *v27; // rcx
  __int64 v28; // r11
  unsigned int v29; // eax
  unsigned int v30; // edx
  __int64 v31; // r10
  _OWORD *v32; // rax
  int *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rax
  __int16 *v36; // r8
  __int64 v37; // rdx
  _WORD *v38; // r9
  __int16 v39; // cx
  _WORD *v40; // rcx
  __int16 *v41; // kr00_8
  __int64 v42; // rax
  int Reply; // [rsp+40h] [rbp-2B8h] BYREF
  _DWORD Size[3]; // [rsp+44h] [rbp-2B4h]
  __int64 v45; // [rsp+50h] [rbp-2A8h]
  __int64 v46; // [rsp+58h] [rbp-2A0h]
  char *v47; // [rsp+60h] [rbp-298h]
  char *v48; // [rsp+68h] [rbp-290h]
  _DWORD *v49; // [rsp+70h] [rbp-288h]
  int v50; // [rsp+80h] [rbp-278h] BYREF
  _BYTE v51[512]; // [rsp+84h] [rbp-274h] BYREF
  __int128 v52; // [rsp+284h] [rbp-74h]
  __int128 v53; // [rsp+294h] [rbp-64h]
  int v54; // [rsp+2A4h] [rbp-54h]
  int v55; // [rsp+2A8h] [rbp-50h]
  int v56; // [rsp+2B0h] [rbp-48h]
  int v57; // [rsp+2B4h] [rbp-44h]
  int v58; // [rsp+2B8h] [rbp-40h]
  int v59; // [rsp+2BCh] [rbp-3Ch]
  int v60; // [rsp+2C0h] [rbp-38h]
  int v61; // [rsp+2C4h] [rbp-34h]

  Reply = 0;
  v4 = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_797f1b088bb039a5f91226960c081484_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  if ( pAsync )
  {
    UserInfo = (char *)pAsync->UserInfo;
    v47 = UserInfo;
    if ( UserInfo )
    {
      v48 = UserInfo + 168;
      EnterCriticalSection((LPCRITICAL_SECTION)(UserInfo + 168));
      v49 = UserInfo + 152;
      *((_DWORD *)UserInfo + 38) = 0;
      v7 = RpcAsyncCompleteCall(pAsync, &Reply);
      LODWORD(pAsync) = v7;
      if ( v7 )
      {
        if ( !Reply )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
            || !*((_BYTE *)WPP_GLOBAL_Control + 105)
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
          {
            goto LABEL_78;
          }
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 13, WPP_797f1b088bb039a5f91226960c081484_Traceguids, 0, v7);
          goto LABEL_82;
        }
      }
      else if ( !Reply )
      {
        v9 = WPP_GLOBAL_Control;
        goto LABEL_8;
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 105) < 4u
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
      {
        goto LABEL_78;
      }
      WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 12), 12, WPP_797f1b088bb039a5f91226960c081484_Traceguids);
LABEL_82:
      v9 = WPP_GLOBAL_Control;
LABEL_78:
      v4 = 1;
LABEL_8:
      if ( *((_DWORD *)UserInfo + 39) )
      {
        if ( v9 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)v9 + 105) >= 4u
          && (*((_BYTE *)v9 + 108) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)v9 + 12), 14, WPP_797f1b088bb039a5f91226960c081484_Traceguids);
        }
        v4 = 1;
        goto LABEL_30;
      }
      if ( v4 )
      {
LABEL_30:
        LeaveCriticalSection((LPCRITICAL_SECTION)(UserInfo + 168));
        v5 = WPP_GLOBAL_Control;
        goto LABEL_31;
      }
      v10 = UserInfo + 160;
      v11 = (unsigned int *)*((_QWORD *)UserInfo + 20);
      if ( !v11 )
      {
LABEL_28:
        Ndr64AsyncClientCall(
          (MIDL_STUBLESS_PROXY_INFO *)&winwlan_ProxyInfo,
          0x17u,
          0,
          UserInfo + 40,
          *(_QWORD *)UserInfo,
          UserInfo + 160);
        if ( !(_DWORD)pAsync )
          *v49 = 1;
        goto LABEL_30;
      }
      pAsync = 0;
      if ( *((_WORD *)UserInfo + 8) > 2u )
      {
LABEL_18:
        v13 = v11;
        if ( (_DWORD)pAsync )
        {
          if ( v9 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
            && *((_BYTE *)v9 + 105) >= 4u
            && (*((_BYTE *)v9 + 108) & 2) != 0 )
          {
            WPP_SF_DDd(*((_QWORD *)v9 + 12), 16, WPP_797f1b088bb039a5f91226960c081484_Traceguids);
          }
        }
        else
        {
          if ( v9 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
            && *((_BYTE *)v9 + 105) >= 4u
            && (*((_BYTE *)v9 + 108) & 2) != 0 )
          {
            WPP_SF_DDqq(
              *((_QWORD *)v9 + 12),
              15,
              WPP_797f1b088bb039a5f91226960c081484_Traceguids,
              *v11,
              v11[1],
              *((_QWORD *)UserInfo + 1),
              *((_QWORD *)UserInfo + 4));
          }
          (*((void (__fastcall **)(_QWORD, _QWORD, __int16 *, unsigned int *))UserInfo + 3))(
            *v10,
            *((_QWORD *)UserInfo + 4),
            v8,
            v13);
        }
        v14 = *(void **)(*v10 + 32LL);
        if ( v14 )
        {
          ProcessHeap = GetProcessHeap();
          if ( ProcessHeap )
            HeapFree(ProcessHeap, 0, v14);
        }
        v16 = (void *)*v10;
        v17 = GetProcessHeap();
        if ( v17 )
          HeapFree(v17, 0, v16);
        *v10 = 0;
        goto LABEL_28;
      }
      if ( *v11 != 8 )
      {
        if ( *v11 == 16 )
        {
          v18 = v11[1];
          if ( v18 - 18 <= 0x27 )
          {
            v41 = v8;
            v8 = &_ImageBase;
            switch ( v18 )
            {
              case 0x12u:
                v11[1] = 1;
                v9 = WPP_GLOBAL_Control;
                goto LABEL_40;
              case 0x13u:
                v19 = 4;
                v11[1] = 4;
                v9 = WPP_GLOBAL_Control;
                break;
              case 0x14u:
                v11[1] = 9;
                v9 = WPP_GLOBAL_Control;
                goto LABEL_40;
              default:
                v8 = v41;
                LODWORD(pAsync) = 50;
                goto LABEL_40;
            }
          }
          else
          {
LABEL_40:
            v19 = 4;
          }
          if ( !(_DWORD)pAsync )
          {
            if ( v11[6] == 584 )
            {
              v20 = *((_QWORD *)v11 + 4);
              if ( v20 )
              {
                v21 = (_OWORD *)*((_QWORD *)v11 + 4);
                v22 = &v50;
                do
                {
                  *(_OWORD *)v22 = *v21;
                  *((_OWORD *)v22 + 1) = v21[1];
                  *((_OWORD *)v22 + 2) = v21[2];
                  *((_OWORD *)v22 + 3) = v21[3];
                  *((_OWORD *)v22 + 4) = v21[4];
                  *((_OWORD *)v22 + 5) = v21[5];
                  *((_OWORD *)v22 + 6) = v21[6];
                  *((_OWORD *)v22 + 7) = v21[7];
                  v22 += 32;
                  v21 += 8;
                  --v19;
                }
                while ( v19 );
                *(_OWORD *)v22 = *v21;
                *((_OWORD *)v22 + 1) = v21[1];
                *((_OWORD *)v22 + 2) = v21[2];
                *((_OWORD *)v22 + 3) = v21[3];
                *((_QWORD *)v22 + 8) = *((_QWORD *)v21 + 8);
                *(_DWORD *)v20 = v50;
                v23 = 2147483646;
                v24 = (__int16 *)v51;
                v25 = 256;
                v8 = (__int16 *)(v20 + 4);
                do
                {
                  if ( !v23 )
                    break;
                  v26 = *v24;
                  if ( !*v24 )
                    break;
                  ++v24;
                  *v8++ = v26;
                  --v23;
                  --v25;
                }
                while ( v25 );
                v27 = v8 - 1;
                if ( v25 )
                  v27 = v8;
                *v27 = 0;
                *(_OWORD *)(v20 + 516) = v52;
                *(_OWORD *)(v20 + 532) = v53;
                *(_DWORD *)(v20 + 548) = v54;
                *(_DWORD *)(v20 + 552) = v55;
                *(_DWORD *)(v20 + 556) = v56;
                *(_WORD *)(v20 + 560) = v57;
                *(_DWORD *)(v20 + 564) = v58;
                *(_DWORD *)(v20 + 568) = v59;
                *(_DWORD *)(v20 + 572) = v60;
                *(_DWORD *)(v20 + 576) = v61;
                v11[6] = 580;
                v9 = WPP_GLOBAL_Control;
              }
            }
            LODWORD(pAsync) = 0;
          }
        }
        goto LABEL_17;
      }
      v12 = v11[1];
      if ( v12 >= 0x1D && v12 < 0x22 )
      {
        if ( v12 == 29 )
        {
          v12 = 9;
          goto LABEL_111;
        }
        if ( v12 != 30 )
        {
          if ( v12 == 31 )
          {
            v12 = 11;
            goto LABEL_111;
          }
          if ( v12 == 32 )
          {
            v12 = 20;
LABEL_111:
            v11[1] = v12;
            v9 = WPP_GLOBAL_Control;
            goto LABEL_14;
          }
        }
        pAsync = (PRPC_ASYNC_STATE)50;
      }
LABEL_14:
      if ( (_DWORD)pAsync || v12 - 9 > 2 && v12 - 20 > 1 )
        goto LABEL_17;
      v28 = *((_QWORD *)v11 + 4);
      v46 = v28;
      if ( !v28 || (v29 = v11[6], v29 < 0x23C) )
      {
        LODWORD(pAsync) = 24;
        goto LABEL_17;
      }
      v8 = (__int16 *)(v29 - 572);
      Size[0] = (_DWORD)v8;
      v30 = (_DWORD)v8 + 568;
      if ( (int)v8 + 568 < (unsigned int)v8 )
      {
        LODWORD(pAsync) = 534;
        goto LABEL_17;
      }
      if ( v30 > v29 )
      {
        v42 = AllocWLMem(v30);
        *(_QWORD *)&Size[1] = v42;
        if ( !v42 )
        {
          LODWORD(pAsync) = 14;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
          {
            goto LABEL_17;
          }
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_449d2dc2504037414f629a2dca50ea60_Traceguids);
LABEL_75:
          v9 = WPP_GLOBAL_Control;
LABEL_17:
          v11 = (unsigned int *)*v10;
          goto LABEL_18;
        }
        v31 = v42;
        v28 = v46;
      }
      else
      {
        *(_QWORD *)&Size[1] = 0;
        v31 = v28;
      }
      v45 = v31;
      v32 = (_OWORD *)*((_QWORD *)v11 + 4);
      v33 = &v50;
      v34 = 4;
      do
      {
        *(_OWORD *)v33 = *v32;
        *((_OWORD *)v33 + 1) = v32[1];
        *((_OWORD *)v33 + 2) = v32[2];
        *((_OWORD *)v33 + 3) = v32[3];
        *((_OWORD *)v33 + 4) = v32[4];
        *((_OWORD *)v33 + 5) = v32[5];
        *((_OWORD *)v33 + 6) = v32[6];
        *((_OWORD *)v33 + 7) = v32[7];
        v33 += 32;
        v32 += 8;
        --v34;
      }
      while ( v34 );
      *(_OWORD *)v33 = *v32;
      *((_OWORD *)v33 + 1) = v32[1];
      *((_OWORD *)v33 + 2) = v32[2];
      *((_OWORD *)v33 + 3) = v32[3];
      *(_DWORD *)v31 = v50;
      v35 = 2147483646;
      v36 = (__int16 *)v51;
      v37 = 256;
      v38 = (_WORD *)(v31 + 4);
      do
      {
        if ( !v35 )
          break;
        v39 = *v36;
        if ( !*v36 )
          break;
        ++v36;
        *v38++ = v39;
        --v35;
        --v37;
      }
      while ( v37 );
      v40 = v38 - 1;
      if ( v37 )
        v40 = v38;
      *v40 = 0;
      *(_OWORD *)(v31 + 516) = v52;
      *(_OWORD *)(v31 + 532) = v53;
      *(_DWORD *)(v31 + 548) = v54;
      *(_DWORD *)(v31 + 552) = v55;
      *(_DWORD *)(v31 + 556) = v56;
      *(_DWORD *)(v31 + 560) = v57;
      *(_DWORD *)(v31 + 564) = v58;
      memmove_0((void *)(v31 + 568), (const void *)(v28 + 572), Size[0]);
      v11[6] = Size[0] + 568;
      if ( *(PRPC_ASYNC_STATE *)&Size[1] != pAsync )
      {
        FreeWLMem(*((_QWORD *)v11 + 4));
        *((_QWORD *)v11 + 4) = v45;
        v9 = WPP_GLOBAL_Control;
        goto LABEL_17;
      }
      goto LABEL_75;
    }
    if ( v5 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control && *((_BYTE *)v5 + 105) && (*((_BYTE *)v5 + 108) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)v5 + 12), 11, WPP_797f1b088bb039a5f91226960c081484_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
    LODWORD(pAsync) = 87;
  }
  else
  {
    UserInfo = 0;
    LODWORD(pAsync) = 87;
  }
LABEL_31:
  if ( v4 )
  {
    SetEvent(*((HANDLE *)UserInfo + 26));
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v5 + 105) >= 4u
    && (*((_BYTE *)v5 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v5 + 12), 18, WPP_797f1b088bb039a5f91226960c081484_Traceguids, (unsigned int)pAsync);
  }
}

```

## disassembly

```asm
0x180001850  mov     [rsp+arg_8], rbx
0x180001855  mov     [rsp+arg_10], rsi
0x18000185a  push    rdi
0x18000185b  push    r12
0x18000185d  push    r13
0x18000185f  push    r14
0x180001861  push    r15
0x180001863  sub     rsp, 2D0h
0x18000186a  mov     r15d, r8d
0x18000186d  mov     rdi, rcx
0x180001870  xor     r12d, r12d
0x180001873  mov     [rsp+2F8h+Reply], r12d
0x180001878  mov     r14d, r12d
0x18000187b  lea     rsi, WPP_GLOBAL_Control
0x180001882  mov     rcx, cs:WPP_GLOBAL_Control
0x180001889  cmp     rcx, rsi
0x18000188c  jz      short loc_180001898
0x18000188e  cmp     byte ptr [rcx+69h], 4
0x180001892  jnb     loc_180001F5F
0x180001898  test    rdi, rdi
0x18000189b  jz      loc_180001B52
0x1800018a1  mov     rbx, [rdi+18h]
0x1800018a5  mov     [rsp+2F8h+var_298], rbx
0x1800018aa  test    rbx, rbx
0x1800018ad  jz      loc_180001B78
0x1800018b3  lea     r13, [rbx+0A8h]
0x1800018ba  mov     [rsp+2F8h+var_290], r13
0x1800018bf  mov     rcx, r13; lpCriticalSection
0x1800018c2  call    cs:__imp_EnterCriticalSection
0x1800018c8  lea     rax, [rbx+98h]
0x1800018cf  mov     [rsp+2F8h+var_288], rax
0x1800018d4  mov     [rax], r12d
0x1800018d7  lea     rdx, [rsp+2F8h+Reply]; Reply
0x1800018dc  mov     rcx, rdi; pAsync
0x1800018df  call    cs:__imp_RpcAsyncCompleteCall
0x1800018e5  mov     edi, eax
0x1800018e7  mov     r9d, [rsp+2F8h+Reply]
0x1800018ec  test    eax, eax
0x1800018ee  jnz     loc_180001EEA
0x1800018f4  test    r9d, r9d
0x1800018f7  jnz     loc_180001FBF
0x1800018fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180001904  cmp     [rbx+9Ch], r12d
0x18000190b  jnz     loc_180001F3B
0x180001911  test    r14d, r14d
0x180001914  jnz     loc_180001A69
0x18000191a  lea     r15, [rbx+0A0h]
0x180001921  mov     r12, [r15]
0x180001924  test    r12, r12
0x180001927  jz      loc_1800019E2
0x18000192d  xor     edi, edi
0x18000192f  cmp     word ptr [rbx+10h], 2
0x180001934  ja      short loc_180001970
0x180001936  mov     eax, [r12]
0x18000193a  cmp     eax, 8
0x18000193d  jnz     loc_180001ACA
0x180001943  mov     edx, [r12+4]
0x180001948  cmp     edx, 1Dh
0x18000194b  jnb     loc_180002090
0x180001951  test    edi, edi
0x180001953  jnz     short loc_18000196D
0x180001955  lea     eax, [rdx-9]
0x180001958  cmp     eax, 2
0x18000195b  jbe     loc_180001D1B
0x180001961  lea     eax, [rdx-14h]
0x180001964  cmp     eax, 1
0x180001967  jbe     loc_180001D1B
0x18000196d  mov     r12, [r15]
0x180001970  mov     r9, r12
0x180001973  test    edi, edi
0x180001975  jnz     loc_180001B07
0x18000197b  cmp     rcx, rsi
0x18000197e  jz      short loc_18000198A
0x180001980  cmp     byte ptr [rcx+69h], 4
0x180001984  jnb     loc_180002168
0x18000198a  mov     rdx, [rbx+20h]
0x18000198e  mov     rcx, [r15]
0x180001991  mov     rax, [rbx+18h]
0x180001995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000199a  mov     rax, [r15]
0x18000199d  mov     r12, [rax+20h]
0x1800019a1  test    r12, r12
0x1800019a4  jz      short loc_1800019BF
0x1800019a6  call    cs:__imp_GetProcessHeap
0x1800019ac  test    rax, rax
0x1800019af  jz      short loc_1800019BF
0x1800019b1  mov     r8, r12; lpMem
0x1800019b4  xor     edx, edx; dwFlags
0x1800019b6  mov     rcx, rax; hHeap
0x1800019b9  call    cs:__imp_HeapFree
0x1800019bf  mov     r12, [r15]
0x1800019c2  call    cs:__imp_GetProcessHeap
0x1800019c8  test    rax, rax
0x1800019cb  jz      short loc_1800019DB
0x1800019cd  mov     r8, r12; lpMem
0x1800019d0  xor     edx, edx; dwFlags
0x1800019d2  mov     rcx, rax; hHeap
0x1800019d5  call    cs:__imp_HeapFree
0x1800019db  mov     qword ptr [r15], 0
0x1800019e2  lea     r9, [rbx+28h]
0x1800019e6  mov     [rsp+2F8h+var_2D0], r15
0x1800019eb  mov     rax, [rbx]
0x1800019ee  mov     [rsp+2F8h+var_2D8], rax
0x1800019f3  xor     r8d, r8d; pReturnValue
0x1800019f6  mov     edx, 17h; nProcNum
0x1800019fb  lea     rcx, ?winwlan_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180001a02  call    cs:__imp_Ndr64AsyncClientCall
0x180001a08  jmp     short loc_180001A5A
0x180001a0a  mov     edi, eax
0x180001a0c  lea     rax, WPP_GLOBAL_Control
0x180001a13  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a1a  cmp     rcx, rax
0x180001a1d  jz      short loc_180001A43
0x180001a1f  cmp     byte ptr [rcx+69h], 1
0x180001a23  jb      short loc_180001A43
0x180001a25  test    byte ptr [rcx+6Ch], 2
0x180001a29  jz      short loc_180001A43
0x180001a2b  mov     edx, 11h
0x180001a30  mov     r9d, edi
0x180001a33  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x180001a3a  mov     rcx, [rcx+60h]
0x180001a3e  call    WPP_SF_d
0x180001a43  mov     r14d, 1
0x180001a49  lea     rsi, WPP_GLOBAL_Control
0x180001a50  mov     rbx, [rsp+2F8h+var_298]
0x180001a55  mov     r13, [rsp+2F8h+var_290]
0x180001a5a  test    edi, edi
0x180001a5c  jnz     short loc_180001A69
0x180001a5e  mov     rax, [rsp+2F8h+var_288]
0x180001a63  mov     dword ptr [rax], 1
0x180001a69  mov     rcx, r13; lpCriticalSection
0x180001a6c  call    cs:__imp_LeaveCriticalSection
0x180001a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a79  test    r14d, r14d
0x180001a7c  jnz     loc_180001B5F
0x180001a82  cmp     rcx, rsi
0x180001a85  jnz     short loc_180001AA4
0x180001a87  lea     r11, [rsp+2F8h+var_28]
0x180001a8f  mov     rbx, [r11+38h]
0x180001a93  mov     rsi, [r11+40h]
0x180001a97  mov     rsp, r11
0x180001a9a  pop     r15
0x180001a9c  pop     r14
0x180001a9e  pop     r13
0x180001aa0  pop     r12
0x180001aa2  pop     rdi
0x180001aa3  retn
0x180001aa4  cmp     byte ptr [rcx+69h], 4
0x180001aa8  jb      short loc_180001A87
0x180001aaa  test    byte ptr [rcx+6Ch], 2
0x180001aae  jz      short loc_180001A87
0x180001ab0  mov     edx, 12h
0x180001ab5  mov     r9d, edi
0x180001ab8  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x180001abf  mov     rcx, [rcx+60h]
0x180001ac3  call    WPP_SF_d
0x180001ac8  jmp     short loc_180001A87
0x180001aca  cmp     eax, 10h
0x180001acd  jnz     loc_18000196D
0x180001ad3  mov     edx, [r12+4]
0x180001ad8  lea     eax, [rdx-12h]
0x180001adb  cmp     eax, 27h ; '''
0x180001ade  jbe     loc_18000202A
0x180001ae4  mov     edx, 4
0x180001ae9  test    edi, edi
0x180001aeb  jnz     loc_18000196D
0x180001af1  cmp     dword ptr [r12+18h], 248h
0x180001afa  jz      loc_180001B8B
0x180001b00  xor     edi, edi
0x180001b02  jmp     loc_18000196D
0x180001b07  cmp     rcx, rsi
0x180001b0a  jz      loc_18000199A
0x180001b10  cmp     byte ptr [rcx+69h], 4
0x180001b14  jb      loc_18000199A
0x180001b1a  test    byte ptr [rcx+6Ch], 2
0x180001b1e  jz      loc_18000199A
0x180001b24  mov     edx, 10h
0x180001b29  mov     eax, [rbx+10h]
0x180001b2c  mov     dword ptr [rsp+2F8h+var_2D0], eax
0x180001b30  mov     eax, [r12+4]
0x180001b35  mov     dword ptr [rsp+2F8h+var_2D8], eax
0x180001b39  mov     r9d, [r12]
0x180001b3d  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x180001b44  mov     rcx, [rcx+60h]
0x180001b48  call    WPP_SF_DDd
0x180001b4d  jmp     loc_18000199A
0x180001b52  mov     rbx, r12
0x180001b55  mov     edi, 57h ; 'W'
0x180001b5a  jmp     loc_180001A79
0x180001b5f  mov     rcx, [rbx+0D0h]; hEvent
0x180001b66  call    cs:__imp_SetEvent
0x180001b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b73  jmp     loc_180001A82
0x180001b78  cmp     rcx, rsi
0x180001b7b  jnz     loc_180001F8A
0x180001b81  mov     edi, 57h ; 'W'
0x180001b86  jmp     loc_180001A79
0x180001b8b  mov     r10, [r12+20h]
0x180001b90  test    r10, r10
0x180001b93  jz      loc_180001B00
0x180001b99  mov     rax, r10
0x180001b9c  lea     rcx, [rsp+2F8h+var_278]
0x180001ba4  movups  xmm0, xmmword ptr [rax]
0x180001ba7  movups  xmmword ptr [rcx], xmm0
0x180001baa  movups  xmm1, xmmword ptr [rax+10h]
0x180001bae  movups  xmmword ptr [rcx+10h], xmm1
0x180001bb2  movups  xmm0, xmmword ptr [rax+20h]
0x180001bb6  movups  xmmword ptr [rcx+20h], xmm0
0x180001bba  movups  xmm1, xmmword ptr [rax+30h]
0x180001bbe  movups  xmmword ptr [rcx+30h], xmm1
0x180001bc2  movups  xmm0, xmmword ptr [rax+40h]
0x180001bc6  movups  xmmword ptr [rcx+40h], xmm0
0x180001bca  movups  xmm1, xmmword ptr [rax+50h]
0x180001bce  movups  xmmword ptr [rcx+50h], xmm1
0x180001bd2  movups  xmm0, xmmword ptr [rax+60h]
0x180001bd6  movups  xmmword ptr [rcx+60h], xmm0
0x180001bda  movups  xmm1, xmmword ptr [rax+70h]
0x180001bde  movups  xmmword ptr [rcx+70h], xmm1
0x180001be2  lea     rcx, [rcx+80h]
0x180001be9  lea     rax, [rax+80h]
0x180001bf0  sub     rdx, 1
0x180001bf4  jnz     short loc_180001BA4
0x180001bf6  movups  xmm0, xmmword ptr [rax]
0x180001bf9  movups  xmmword ptr [rcx], xmm0
0x180001bfc  movups  xmm1, xmmword ptr [rax+10h]
0x180001c00  movups  xmmword ptr [rcx+10h], xmm1
0x180001c04  movups  xmm0, xmmword ptr [rax+20h]
0x180001c08  movups  xmmword ptr [rcx+20h], xmm0
0x180001c0c  movups  xmm1, xmmword ptr [rax+30h]
0x180001c10  movups  xmmword ptr [rcx+30h], xmm1
0x180001c14  mov     rax, [rax+40h]
0x180001c18  mov     [rcx+40h], rax
0x180001c1c  mov     eax, [rsp+2F8h+var_278]
0x180001c23  mov     [r10], eax
0x180001c26  mov     eax, 7FFFFFFEh
0x180001c2b  lea     rcx, [rsp+2F8h+var_274]
0x180001c33  mov     edx, 100h
0x180001c38  lea     r8, [r10+4]
0x180001c3c  nop     dword ptr [rax+00h]
0x180001c40  test    rax, rax
0x180001c43  jz      short loc_180001C64
0x180001c45  movzx   r9d, word ptr [rcx]
0x180001c49  test    r9w, r9w
0x180001c4d  jz      short loc_180001C64
0x180001c4f  add     rcx, 2
0x180001c53  mov     [r8], r9w
0x180001c57  add     r8, 2
0x180001c5b  dec     rax
0x180001c5e  sub     rdx, 1
0x180001c62  jnz     short loc_180001C40
0x180001c64  lea     rcx, [r8-2]
0x180001c68  test    rdx, rdx
0x180001c6b  cmovnz  rcx, r8
0x180001c6f  xor     eax, eax
0x180001c71  mov     [rcx], ax
0x180001c74  movups  xmm0, [rsp+2F8h+var_74]
0x180001c7c  movups  xmmword ptr [r10+204h], xmm0
0x180001c84  movups  xmm1, [rsp+2F8h+var_64]
0x180001c8c  movups  xmmword ptr [r10+214h], xmm1
0x180001c94  mov     eax, [rsp+2F8h+var_54]
0x180001c9b  mov     [r10+224h], eax
0x180001ca2  mov     eax, [rsp+2F8h+var_50]
0x180001ca9  mov     [r10+228h], eax
0x180001cb0  mov     eax, [rsp+2F8h+var_48]
0x180001cb7  mov     [r10+22Ch], eax
0x180001cbe  movzx   eax, word ptr [rsp+2F8h+var_44]
0x180001cc6  mov     [r10+230h], ax
0x180001cce  mov     eax, [rsp+2F8h+var_40]
0x180001cd5  mov     [r10+234h], eax
0x180001cdc  mov     eax, [rsp+2F8h+var_3C]
0x180001ce3  mov     [r10+238h], eax
0x180001cea  mov     eax, [rsp+2F8h+var_38]
0x180001cf1  mov     [r10+23Ch], eax
0x180001cf8  mov     eax, [rsp+2F8h+var_34]
0x180001cff  mov     [r10+240h], eax
0x180001d06  mov     dword ptr [r12+18h], 244h
0x180001d0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d16  jmp     loc_180001B00
0x180001d1b  mov     r11, [r12+20h]
0x180001d20  mov     [rsp+2F8h+var_2A0], r11
0x180001d25  test    r11, r11
0x180001d28  jz      loc_18000215E
0x180001d2e  mov     eax, [r12+18h]
0x180001d33  cmp     eax, 23Ch
0x180001d38  jb      loc_18000215E
0x180001d3e  lea     r8d, [rax-23Ch]
0x180001d45  mov     dword ptr [rsp+2F8h+Size], r8d
0x180001d4a  lea     edx, [r8+238h]
0x180001d51  cmp     edx, r8d
0x180001d54  jb      loc_180001F55
0x180001d5a  cmp     edx, eax
0x180001d5c  ja      loc_1800020DD
0x180001d62  xor     r8d, r8d
0x180001d65  mov     qword ptr [rsp+2F8h+Size+4], r8
0x180001d6a  mov     r10, r11
0x180001d6d  mov     [rsp+2F8h+var_2A8], r10
0x180001d72  mov     rax, [r12+20h]
0x180001d77  lea     rcx, [rsp+2F8h+var_278]
0x180001d7f  mov     edx, 4
0x180001d84  movups  xmm0, xmmword ptr [rax]
  ... truncated ...
```
