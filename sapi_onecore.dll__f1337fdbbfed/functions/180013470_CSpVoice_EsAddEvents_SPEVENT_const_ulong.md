# CSpVoice::EsAddEvents(SPEVENT const *,ulong)

- ea: `0x180013470`
- end: `0x180013eb4`
- name: `?EsAddEvents@CSpVoice@@QEAAJPEBUSPEVENT@@K@Z`
- size: `2628`
- prototype: `__int64 __fastcall(CSpVoice *__hidden this, const struct SPEVENT *, unsigned int)`
- caller_count: `4`
- callee_count: `23`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800123e4`
- `0x1800125c0`
- `0x1801a7920`
- `0x1801ab32c`

## callees

- `0x18000cdb0`
- `0x180013470`
- `0x180013ec0`
- `0x180014060`
- `0x1800156f0`
- `0x180079e30`
- `0x180079e54`
- `0x180079e60`
- `0x18007a350`
- `0x18007a374`
- `0x18007d340`
- `0x18007d7a5`
- `0x18007d7b1`
- `0x18008a80c`
- `0x18008b4dc`
- `0x18009427c`
- `0x180094330`
- `0x180137550`
- `0x1801a8b18`
- `0x1801a8be4`
- `0x1801ab818`
- `0x1801ae114`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001357a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800135ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013888`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013a76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001357a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800135ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013888`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013a76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800135bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013680`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800138a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800138c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013e55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800135bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013680`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800138a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800138c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013e55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013771`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013980`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013771`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013980`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800137b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013814`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800137b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013814`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSpVoice::EsAddEvents(CSpVoice *this, const struct SPEVENT *a2, unsigned int a3)
{
  unsigned int v3; // ebx
  unsigned int v6; // r13d
  int appended; // ebp
  unsigned int v8; // edi
  __int16 *v9; // r11
  __int16 v10; // ax
  __int64 v12; // rdx
  __int64 v13; // rax
  _QWORD *v14; // rdx
  int v15; // r15d
  __int64 v16; // rcx
  __int64 v17; // r8
  int v18; // ecx
  int v19; // eax
  __int64 v20; // rax
  bool v21; // cf
  unsigned __int64 v22; // rax
  _QWORD *v23; // rax
  struct CSpEvent *v24; // rdi
  unsigned __int64 v25; // r15
  __int64 v26; // r14
  int v27; // ecx
  __int64 v28; // rbx
  int v29; // ecx
  int v30; // eax
  const void **p_lParam; // rbp
  void *v32; // rax
  LPARAM *v33; // rcx
  __int64 v34; // rax
  unsigned __int64 v35; // r14
  unsigned __int16 *v36; // rax
  unsigned int v37; // r14d
  __int64 v38; // rbx
  __int64 v39; // r12
  unsigned __int16 *v40; // r13
  unsigned __int64 v41; // r8
  unsigned __int64 v42; // rdx
  __int64 v43; // rcx
  unsigned int i; // ebp
  __int64 v45; // rax
  _QWORD *v46; // r8
  __int64 v47; // rdx
  unsigned int v48; // r14d
  __int64 v49; // rbp
  int v50; // r8d
  unsigned int j; // ebp
  __int64 v52; // rax
  __int128 v53; // xmm1
  __int64 v54; // rdx
  __int64 v55; // rcx
  double v56; // xmm2_8
  double v57; // xmm2_8
  unsigned __int64 v58; // rcx
  __int64 v59; // rax
  _OWORD *v60; // r14
  char *v61; // rcx
  __int64 v62; // r14
  int v63; // r15d
  int v64; // eax
  __int64 v65; // rax
  char *v66; // rcx
  __int64 v67; // rcx
  int v68; // eax
  unsigned __int64 v69; // r14
  LPVOID pv; // [rsp+30h] [rbp-98h] BYREF
  int v71; // [rsp+38h] [rbp-90h]
  unsigned int v72; // [rsp+3Ch] [rbp-8Ch]
  _OWORD v73[2]; // [rsp+40h] [rbp-88h] BYREF
  unsigned __int64 v74; // [rsp+60h] [rbp-68h]
  __int128 Buf1; // [rsp+68h] [rbp-60h] BYREF

  v3 = a3;
  v72 = a3;
  if ( !a3 || !a2 )
  {
LABEL_9:
    appended = -2147024809;
LABEL_10:
    DoTraceMessage(4, "CSpVoice::EsAddEvents failed, hr=0x%X", appended);
    return (unsigned int)appended;
  }
  v6 = 0;
  appended = 0;
  v8 = 0;
  while ( v8 < v3 )
  {
    appended = SpValidateEvent(&a2[v8]);
    if ( appended < 0 )
      goto LABEL_17;
    v10 = *v9;
    if ( (unsigned __int16)(*v9 - 1) > 0xEu )
      goto LABEL_9;
    if ( v10 == 3 )
    {
      if ( (*(_DWORD *)v9 & 0xFFFF0000) != 0x10000 )
        goto LABEL_9;
      goto LABEL_15;
    }
    if ( v10 == 4 )
    {
      if ( (*(_DWORD *)v9 & 0xFFFF0000) != 0x40000 )
        goto LABEL_9;
      ++v8;
    }
    else
    {
LABEL_15:
      if ( v10 == 7 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 976));
        v12 = *((_QWORD *)this + 87);
        appended = CPromptOffsetHist::AppendNewEntry(
                     (CPromptOffsetHist *)(*((_QWORD *)this + 87) + 120LL),
                     *(struct CSpeechSeg **)(v12 + 64),
                     ++*(_DWORD *)(v12 + 92),
                     *(_DWORD *)(v12 + 100),
                     *((double *)this + 138));
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 976));
        v3 = v72;
      }
LABEL_17:
      if ( appended < 0 )
        goto LABEL_10;
      ++v8;
    }
  }
  v71 = 0;
  pv = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 976));
  v13 = *((_QWORD *)this + 87);
  if ( v13 )
  {
    if ( *(_DWORD *)(v13 + 112) )
    {
      v71 = 1;
    }
    else
    {
      v14 = *(_QWORD **)(v13 + 64);
      if ( v14 )
      {
        v15 = *(_DWORD *)(v13 + 104);
        pv = (LPVOID)(unsigned int)v15;
        v16 = v14[1] - *(_QWORD *)&SPDFID_WaveFormatEx.Data1;
        if ( !v16 )
          v16 = v14[2] - *(_QWORD *)SPDFID_WaveFormatEx.Data4;
        if ( !v16 )
        {
          v17 = v14[3];
          if ( v17 )
          {
            v18 = *(_DWORD *)(v13 + 80);
            v19 = *(_DWORD *)(v17 + 8);
            if ( v19 != v18 )
              pv = (LPVOID)(unsigned int)(int)((double)v19 * (double)v15 / (double)v18);
          }
        }
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 976));
  v20 = 32LL * v3;
  if ( !is_mul_ok(v3, 0x20u) )
    v20 = -1;
  v21 = __CFADD__(v20, 8);
  v22 = v20 + 8;
  if ( v21 )
    v22 = -1;
  v23 = operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)&Buf1 = v23;
  if ( v23 )
  {
    *v23 = v3;
    v24 = (struct CSpEvent *)(v23 + 1);
    `eh vector constructor iterator'(
      v23 + 1,
      0x20u,
      v3,
      (void (*)(void *))CSpEvent::CSpEvent,
      (void (*)(void *))CSpEvent::~CSpEvent);
  }
  else
  {
    v24 = 0;
  }
  if ( !v24 )
  {
LABEL_66:
    appended = -2147024882;
    goto LABEL_10;
  }
  v25 = 0;
  if ( v3 )
  {
    do
    {
      v26 = v6;
      v27 = (int)a2[v26];
      if ( v71 == 1 && (unsigned __int16)(v27 - 1) > 1u )
        goto LABEL_61;
      DoTraceMessage(32, "EsAddEvent(TTS) eventId=%u, stream offset=%I64u", v27, a2[v26].ullAudioStreamOffset);
      v28 = 32LL * (unsigned int)v25;
      v29 = *(__int16 *)((char *)v24 + v28 + 2);
      if ( *(_WORD *)((char *)v24 + v28 + 2) )
      {
        if ( (unsigned int)(v29 - 3) <= 1 )
        {
          CoTaskMemFree(*(LPVOID *)((char *)v24 + v28 + 24));
        }
        else if ( (unsigned int)(v29 - 1) <= 1 )
        {
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)((char *)v24 + v28 + 24) + 16LL))(*(_QWORD *)((char *)v24 + v28 + 24));
        }
      }
      *(_OWORD *)((char *)v24 + v28) = 0;
      *(_OWORD *)((char *)v24 + v28 + 16) = 0;
      *(_OWORD *)((char *)v24 + v28) = a2[v26];
      *(_OWORD *)((char *)v24 + v28 + 16) = *(_OWORD *)&a2[v26].wParam;
      v30 = *((__int16 *)&a2[v26] + 1);
      p_lParam = (const void **)&a2[v26].lParam;
      if ( v30 == 3 && *p_lParam )
      {
        v32 = CoTaskMemAlloc(a2[v26].wParam);
        *(_QWORD *)((char *)v24 + v28 + 24) = v32;
        if ( !v32 )
          goto LABEL_65;
        memcpy_0(v32, *p_lParam, a2[v26].wParam);
        goto LABEL_60;
      }
      v33 = &a2[v26].lParam;
      if ( v30 == 4 )
      {
        v33 = &a2[v26].lParam;
        *(_QWORD *)&Buf1 = v33;
        if ( *v33 )
        {
          v34 = -1;
          do
            ++v34;
          while ( *(_WORD *)(*v33 + 2 * v34) );
          v35 = v34 + 1;
          v36 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v34 + 1));
          *(_QWORD *)((char *)v24 + v28 + 24) = v36;
          if ( !v36 )
          {
LABEL_65:
            *(_WORD *)((char *)v24 + v28) = 0;
            goto LABEL_66;
          }
          StringCchCopyW(v36, v35, *(const unsigned __int16 **)Buf1);
          goto LABEL_60;
        }
      }
      if ( v30 == 1 )
      {
        p_lParam = (const void **)v33;
      }
      else if ( v30 != 2 )
      {
        goto LABEL_60;
      }
      (*(void (__fastcall **)(const void *))(*(_QWORD *)*p_lParam + 8LL))(*p_lParam);
LABEL_60:
      *(_DWORD *)((char *)v24 + v28 + 4) = *((_DWORD *)this + 214);
      *(_QWORD *)((char *)v24 + v28 + 8) -= (unsigned int)pv;
      v25 = (unsigned int)(v25 + 1);
      appended = 0;
      v3 = v72;
LABEL_61:
      ++v6;
    }
    while ( v6 < v3 );
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  if ( !*((_DWORD *)this + 219) || *((_QWORD *)this + 108) == -1 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    v37 = 0;
    if ( (_DWORD)v25 )
    {
      v38 = 0;
      do
      {
        v39 = 32 * v38;
        if ( *((__int16 *)v24 + 16 * v38) == *((_DWORD *)this + 218) )
        {
          Buf1 = 0;
          pv = 0;
          appended = (*(__int64 (__fastcall **)(_QWORD, __int128 *, LPVOID *))(**((_QWORD **)this + 83) + 112LL))(
                       *((_QWORD *)this + 83),
                       &Buf1,
                       &pv);
          v40 = (unsigned __int16 *)pv;
          if ( appended >= 0 )
          {
            if ( !memcmp_0(&Buf1, &SPDFID_WaveFormatEx, 0x10u) )
            {
              v41 = *(_QWORD *)((char *)v24 + v39 + 8);
              v42 = v41 % v40[6];
              if ( v42 )
                v41 += v40[6] - v42;
              *((_QWORD *)this + 108) = v41;
            }
            else
            {
              *((_QWORD *)this + 108) = *(_QWORD *)((char *)v24 + v39 + 8);
            }
          }
          if ( v40 )
            CoTaskMemFree(v40);
        }
        ++v37;
        ++v38;
      }
      while ( v37 < (unsigned int)v25 );
    }
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  }
  if ( appended >= 0 )
  {
    CSpVoice::HandleEscapeCharacters(this, v24, v25);
    v43 = *((_QWORD *)this + 50);
    if ( v43 && *((_DWORD *)this + 162) && *((_DWORD *)this + 163) )
      goto LABEL_83;
    for ( i = 0; i < (unsigned int)v25; ++i )
    {
      v45 = 32LL * i;
      v46 = (_QWORD *)((char *)v24 + v45 + 8);
      if ( v46 && *((_DWORD *)this + 162) )
      {
        v47 = *(_QWORD *)((char *)v24 + v45 + 8);
        if ( *((_DWORD *)this + 163) )
        {
          (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 78) + 152LL))(*((_QWORD *)this + 78), v47);
        }
        else if ( *((_QWORD *)this + 79) )
        {
          *v46 = v47 + *((_QWORD *)this + 80);
        }
      }
    }
    v43 = *((_QWORD *)this + 50);
    if ( v43 )
    {
LABEL_83:
      appended = (*(__int64 (__fastcall **)(__int64, struct CSpEvent *, _QWORD))(*(_QWORD *)v43 + 24LL))(
                   v43,
                   v24,
                   (unsigned int)v25);
    }
    else
    {
      *(_QWORD *)&Buf1 = (char *)this + 88;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
      v48 = 0;
      while ( v48 < (unsigned int)v25 )
      {
        v49 = 32LL * v48;
        DoTraceMessage(
          32,
          "Process TTS event: EventId=%u, Offset=%I64u",
          *(__int16 *)((char *)v24 + v49),
          *(_QWORD *)((char *)v24 + v49 + 8));
        if ( *(_WORD *)((char *)v24 + v49) == 8 )
        {
          *((_DWORD *)this + 208) = *(unsigned __int16 *)((char *)v24 + v49 + 24);
LABEL_106:
          ++v48;
        }
        else
        {
          switch ( *((_WORD *)v24 + 16 * v48) )
          {
            case 1:
              v50 = *(_DWORD *)((char *)v24 + v49 + 4);
              *((_DWORD *)this + 198) = v50;
              DoTraceMessage(16, "Generate next m_VoiceStatus.ulCurrentStream on SPEI_START_INPUT_STREAM %lu", v50);
              ++v48;
              break;
            case 2:
              if ( *(_DWORD *)((char *)v24 + v49 + 4) == *((_DWORD *)this + 199) || (*((_BYTE *)this + 1132) & 1) != 0 )
                *((_DWORD *)this + 201) |= 1u;
              goto LABEL_106;
            case 4:
              CSpDynamicString::operator=((char *)this + 848, *(_QWORD *)((char *)v24 + v49 + 24));
              *((_DWORD *)this + 206) = *(_DWORD *)((char *)v24 + v49 + 16);
              ++v48;
              break;
            case 5:
              *((_DWORD *)this + 202) = *(_DWORD *)((char *)v24 + v49 + 24);
              *((_DWORD *)this + 203) = *(_DWORD *)((char *)v24 + v49 + 16);
              ++v48;
              break;
            case 6:
              *((_WORD *)this + 414) = *(_WORD *)((char *)v24 + v49 + 24);
              ++v48;
              break;
            case 7:
              *((_DWORD *)this + 204) = *(_DWORD *)((char *)v24 + v49 + 24);
              *((_DWORD *)this + 205) = *(_DWORD *)((char *)v24 + v49 + 16);
              ++v48;
              break;
            default:
              goto LABEL_106;
          }
        }
      }
      if ( *((_DWORD *)this + 305) == *((_DWORD *)this + 304) )
      {
        memset(v73, 0, sizeof(v73));
        for ( j = 0; j < (unsigned int)v25; ++j )
        {
          v52 = 32LL * j;
          v53 = *(_OWORD *)((char *)v24 + v52);
          v73[0] = v53;
          v73[1] = *(_OWORD *)((char *)v24 + v52 + 16);
          v54 = *((_QWORD *)this + 76);
          if ( v54 )
          {
            v55 = *(_QWORD *)((char *)v24 + v52 + 8);
            if ( v55 < 0 )
              v56 = (double)(int)(v55 & 1 | ((unsigned __int64)v55 >> 1))
                  + (double)(int)(v55 & 1 | ((unsigned __int64)v55 >> 1));
            else
              v56 = (double)(int)v55;
            v57 = v56 * 10000000.0 / (double)*(int *)(v54 + 8);
            v58 = 0;
            if ( v57 >= 9.223372036854776e18 )
            {
              v57 = v57 - 9.223372036854776e18;
              if ( v57 < 9.223372036854776e18 )
                v58 = 0x8000000000000000uLL;
            }
            v74 = v58 + (unsigned int)(int)v57;
          }
          else
          {
            v74 = 0;
          }
          v59 = *((_QWORD *)this + 27);
          if ( _bittest64(&v59, (unsigned int)v53) )
          {
            v60 = (_OWORD *)*((_QWORD *)this + 36);
            if ( v60 )
            {
              *((_QWORD *)this + 36) = *((_QWORD *)v60 + 5);
              --*((_DWORD *)this + 76);
            }
            else
            {
              v60 = operator new(0x30u);
              pv = v60;
              *v60 = 0;
              v60[1] = 0;
              *((_QWORD *)v60 + 4) = 0;
            }
            CSpEventExNode::Clear((CSpEventExNode *)v60);
            CSpEventExNode::CopyTo((CSpEventExNode *)v73, (struct SPEVENTEX *)v60);
            v61 = (char *)this + 240;
            if ( *((_BYTE *)this + 376) )
              CSpBasicQueue<CSpEventExNode,1,1>::InsertSorted(v61, v60);
            else
              CSpBasicQueue<CSpEventExNode,1,1>::InsertTail(v61, v60);
          }
        }
        appended = 0;
        v62 = *((_QWORD *)this + 30);
        if ( !v62 )
          goto LABEL_153;
        v63 = 0;
        while ( 1 )
        {
          *((_QWORD *)this + 30) = *(_QWORD *)(v62 + 40);
          --*((_DWORD *)this + 64);
          v64 = *(_DWORD *)(v62 + 4);
          if ( v64 != *((_DWORD *)this + 58) )
            *((_DWORD *)this + 58) = v64;
          v65 = 1LL << *(_BYTE *)v62;
          if ( (v65 & *((_QWORD *)this + 27)) != 0 )
          {
            v63 = 1;
            if ( (v65 & *((_QWORD *)this + 28)) != 0 )
            {
              v66 = (char *)this + 264;
              if ( *((_BYTE *)this + 376) )
                CSpBasicQueue<CSpEventExNode,1,1>::InsertSorted(v66, v62);
              else
                CSpBasicQueue<CSpEventExNode,1,1>::InsertTail(v66, v62);
              goto LABEL_141;
            }
            CSpEventExNode::Clear((CSpEventExNode *)v62);
            *(_QWORD *)(v62 + 40) = *((_QWORD *)this + 36);
            if ( !*((_QWORD *)this + 36) )
LABEL_139:
              *((_QWORD *)this + 37) = v62;
          }
          else
          {
            CSpEventExNode::Clear((CSpEventExNode *)v62);
            *(_QWORD *)(v62 + 40) = *((_QWORD *)this + 36);
            if ( !*((_QWORD *)this + 36) )
              goto LABEL_139;
          }
          ++*((_DWORD *)this + 76);
          *((_QWORD *)this + 36) = v62;
LABEL_141:
          v62 = *((_QWORD *)this + 30);
          if ( !v62 )
          {
            if ( v63 )
            {
              v67 = *((_QWORD *)this + 39);
              if ( v67 )
              {
                v68 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v67 + 24LL))(v67);
                goto LABEL_152;
              }
            }
            goto LABEL_153;
          }
        }
      }
      v69 = 0;
      while ( v69 < v25 )
      {
        if ( *((_WORD *)v24 + 16 * v69) == 2 )
        {
          CSpPhoneMapper::Finish(*((CSpPhoneMapper **)this + 143));
          CSpVoice::FlushEventsFromMap(this);
        }
        appended = CSpPhoneMapper::QueueEvent(*((CSpPhoneMapper **)this + 143), (const struct SPEVENT *)v24 + v69++);
        if ( appended < 0 )
          goto LABEL_153;
      }
      v68 = CSpVoice::FlushEventsFromMap(this);
LABEL_152:
      appended = v68;
LABEL_153:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    }
  }
  `eh vector destructor iterator'(v24, 0x20u, *((_QWORD *)v24 - 1), (void (*)(void *))CSpEvent::~CSpEvent);
  operator delete[]((char *)v24 - 8, (const struct std::nothrow_t *)(32LL * *((_QWORD *)v24 - 1) + 8));
  if ( appended < 0 )
    goto LABEL_10;
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180013470  mov     [rsp+arg_18], rbx
0x180013475  push    rbp
0x180013476  push    rsi
0x180013477  push    rdi
0x180013478  push    r12
0x18001347a  push    r13
0x18001347c  push    r14
0x18001347e  push    r15
0x180013480  sub     rsp, 90h
0x180013487  movaps  [rsp+0C8h+var_48], xmm6
0x18001348f  mov     rax, cs:__security_cookie
0x180013496  xor     rax, rsp
0x180013499  mov     [rsp+0C8h+var_50], rax
0x18001349e  mov     ebx, r8d
0x1800134a1  mov     [rsp+0C8h+var_8C], ebx
0x1800134a5  mov     r12, rdx
0x1800134a8  mov     rsi, rcx
0x1800134ab  test    r8d, r8d
0x1800134ae  jz      short loc_180013506
0x1800134b0  test    rdx, rdx
0x1800134b3  jz      short loc_180013506
0x1800134b5  xor     r13d, r13d
0x1800134b8  mov     ebp, r13d
0x1800134bb  mov     edi, r13d
0x1800134be  cmp     edi, ebx
0x1800134c0  jnb     loc_1800135D6
0x1800134c6  mov     r11d, edi
0x1800134c9  shl     r11, 5
0x1800134cd  add     r11, r12
0x1800134d0  mov     rcx, r11; struct SPEVENT *
0x1800134d3  call    ?SpValidateEvent@@YAJPEBUSPEVENT@@@Z; SpValidateEvent(SPEVENT const *)
0x1800134d8  mov     ebp, eax
0x1800134da  test    eax, eax
0x1800134dc  js      loc_1800135C7
0x1800134e2  movzx   eax, word ptr [r11]
0x1800134e6  lea     ecx, [rax-1]
0x1800134e9  cmp     cx, 0Eh
0x1800134ed  ja      short loc_180013506
0x1800134ef  cmp     ax, 3
0x1800134f3  jnz     short loc_180013551
0x1800134f5  mov     ecx, [r11]
0x1800134f8  and     ecx, 0FFFF0000h
0x1800134fe  cmp     ecx, 10000h
0x180013504  jz      short loc_18001356D
0x180013506  mov     ebp, 80070057h
0x18001350b  mov     r8d, ebp
0x18001350e  lea     rdx, aCspvoiceEsadde; "CSpVoice::EsAddEvents failed, hr=0x%X"
0x180013515  mov     ecx, 4; int
0x18001351a  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18001351f  mov     eax, ebp
0x180013521  mov     rcx, [rsp+0C8h+var_50]
0x180013526  xor     rcx, rsp; StackCookie
0x180013529  call    __security_check_cookie
0x18001352e  mov     rbx, [rsp+0C8h+arg_18]
0x180013536  movaps  xmm6, [rsp+0C8h+var_48]
0x18001353e  add     rsp, 90h
0x180013545  pop     r15
0x180013547  pop     r14
0x180013549  pop     r13
0x18001354b  pop     r12
0x18001354d  pop     rdi
0x18001354e  pop     rsi
0x18001354f  pop     rbp
0x180013550  retn
0x180013551  cmp     ax, 4
0x180013555  jnz     short loc_18001356D
0x180013557  mov     eax, [r11]
0x18001355a  and     eax, 0FFFF0000h
0x18001355f  cmp     eax, 40000h
0x180013564  jnz     short loc_180013506
0x180013566  inc     edi
0x180013568  jmp     loc_1800134BE
0x18001356d  cmp     ax, 7
0x180013571  jnz     short loc_1800135C7
0x180013573  lea     rcx, [rsi+3D0h]; lpCriticalSection
0x18001357a  call    cs:__imp_EnterCriticalSection
0x180013580  mov     rdx, [rsi+2B8h]
0x180013587  inc     dword ptr [rdx+5Ch]
0x18001358a  mov     rcx, [rsi+2B8h]
0x180013591  add     rcx, 78h ; 'x'; this
0x180013595  movsd   xmm0, qword ptr [rsi+450h]
0x18001359d  movsd   [rsp+0C8h+var_A8], xmm0; double
0x1800135a3  mov     r9d, [rdx+64h]; unsigned int
0x1800135a7  mov     r8d, [rdx+5Ch]; int
0x1800135ab  mov     rdx, [rdx+40h]; struct CSpeechSeg *
0x1800135af  call    ?AppendNewEntry@CPromptOffsetHist@@QEAAJPEAVCSpeechSeg@@HKN@Z; CPromptOffsetHist::AppendNewEntry(CSpeechSeg *,int,ulong,double)
0x1800135b4  mov     ebp, eax
0x1800135b6  lea     rcx, [rsi+3D0h]; lpCriticalSection
0x1800135bd  call    cs:__imp_LeaveCriticalSection
0x1800135c3  mov     ebx, [rsp+0C8h+var_8C]
0x1800135c7  test    ebp, ebp
0x1800135c9  js      loc_18001350B
0x1800135cf  inc     edi
0x1800135d1  jmp     loc_1800134BE
0x1800135d6  mov     [rsp+0C8h+var_90], r13d
0x1800135db  mov     r15d, r13d
0x1800135de  mov     [rsp+0C8h+pv], r15
0x1800135e3  lea     rcx, [rsi+3D0h]; lpCriticalSection
0x1800135ea  call    cs:__imp_EnterCriticalSection
0x1800135f0  mov     rax, [rsi+2B8h]
0x1800135f7  test    rax, rax
0x1800135fa  jz      short loc_180013679
0x1800135fc  cmp     [rax+70h], r13d
0x180013600  jz      short loc_18001360C
0x180013602  mov     [rsp+0C8h+var_90], 1
0x18001360a  jmp     short loc_180013679
0x18001360c  mov     rdx, [rax+40h]
0x180013610  test    rdx, rdx
0x180013613  jz      short loc_180013679
0x180013615  mov     r15d, [rax+68h]
0x180013619  mov     [rsp+0C8h+pv], r15
0x18001361e  mov     rcx, [rdx+8]
0x180013622  sub     rcx, qword ptr cs:SPDFID_WaveFormatEx.Data1
0x180013629  jnz     short loc_180013636
0x18001362b  mov     rcx, [rdx+10h]
0x18001362f  sub     rcx, qword ptr cs:SPDFID_WaveFormatEx.Data4
0x180013636  test    rcx, rcx
0x180013639  jnz     short loc_180013679
0x18001363b  mov     r8, [rdx+18h]
0x18001363f  test    r8, r8
0x180013642  jz      short loc_180013679
0x180013644  mov     ecx, [rax+50h]
0x180013647  mov     eax, [r8+8]
0x18001364b  cmp     eax, ecx
0x18001364d  jz      short loc_180013679
0x18001364f  xorps   xmm2, xmm2
0x180013652  cvtsi2sd xmm2, rax
0x180013657  xorps   xmm0, xmm0
0x18001365a  cvtsi2sd xmm0, r15
0x18001365f  mulsd   xmm2, xmm0
0x180013663  xorps   xmm1, xmm1
0x180013666  cvtsi2sd xmm1, rcx
0x18001366b  divsd   xmm2, xmm1
0x18001366f  cvttsd2si rax, xmm2
0x180013674  mov     [rsp+0C8h+pv], rax
0x180013679  lea     rcx, [rsi+3D0h]; lpCriticalSection
0x180013680  call    cs:__imp_LeaveCriticalSection
0x180013686  mov     r14d, ebx
0x180013689  mov     eax, 20h ; ' '
0x18001368e  mul     r14
0x180013691  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180013698  cmovb   rax, rcx
0x18001369c  add     rax, 8
0x1800136a0  cmovb   rax, rcx
0x1800136a4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800136ab  mov     rcx, rax; unsigned __int64
0x1800136ae  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800136b3  mov     qword ptr [rsp+0C8h+Buf1], rax
0x1800136b8  lea     rcx, ??1CSpEvent@@QEAA@XZ; CSpEvent::~CSpEvent(void)
0x1800136bf  test    rax, rax
0x1800136c2  jz      short loc_1800136E9
0x1800136c4  mov     [rax], r14
0x1800136c7  lea     rdi, [rax+8]
0x1800136cb  mov     [rsp+0C8h+var_A8], rcx; void (*)(void *)
0x1800136d0  lea     r9, ??0CSpEvent@@QEAA@XZ; void (*)(void *)
0x1800136d7  mov     r8d, r14d; unsigned __int64
0x1800136da  mov     edx, 20h ; ' '; unsigned __int64
0x1800136df  mov     rcx, rdi; void *
0x1800136e2  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800136e7  jmp     short loc_1800136EC
0x1800136e9  mov     rdi, r13
0x1800136ec  test    rdi, rdi
0x1800136ef  jz      loc_1800138B6
0x1800136f5  mov     r15d, r13d
0x1800136f8  test    ebx, ebx
0x1800136fa  jz      loc_180013884
0x180013700  mov     r14d, r13d
0x180013703  shl     r14, 5
0x180013707  movsx   ecx, word ptr [r14+r12]
0x18001370c  lea     eax, [rcx-1]
0x18001370f  cmp     [rsp+0C8h+var_90], 1
0x180013714  jnz     short loc_180013720
0x180013716  cmp     ax, 1
0x18001371a  ja      loc_180013878
0x180013720  mov     r8d, ecx
0x180013723  mov     r9, [r14+r12+8]
0x180013728  lea     rdx, aEsaddeventTtsE; "EsAddEvent(TTS) eventId=%u, stream offs"...
0x18001372f  mov     ecx, 20h ; ' '; int
0x180013734  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x180013739  mov     ebx, r15d
0x18001373c  shl     rbx, 5
0x180013740  movsx   ecx, word ptr [rbx+rdi+2]
0x180013745  test    ecx, ecx
0x180013747  jz      short loc_180013777
0x180013749  lea     eax, [rcx-3]
0x18001374c  cmp     eax, 1
0x18001374f  jbe     short loc_18001376C
0x180013751  lea     eax, [rcx-1]
0x180013754  cmp     eax, 1
0x180013757  ja      short loc_180013777
0x180013759  mov     rcx, [rbx+rdi+18h]
0x18001375e  mov     rax, [rcx]
0x180013761  mov     rax, [rax+10h]
0x180013765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001376a  jmp     short loc_180013777
0x18001376c  mov     rcx, [rbx+rdi+18h]; pv
0x180013771  call    cs:__imp_CoTaskMemFree
0x180013777  xorps   xmm0, xmm0
0x18001377a  movups  xmmword ptr [rbx+rdi], xmm0
0x18001377e  movups  xmmword ptr [rbx+rdi+10h], xmm0
0x180013783  movups  xmm0, xmmword ptr [r14+r12]
0x180013788  movups  xmmword ptr [rbx+rdi], xmm0
0x18001378c  movups  xmm1, xmmword ptr [r14+r12+10h]
0x180013792  movups  xmmword ptr [rbx+rdi+10h], xmm1
0x180013797  movsx   eax, word ptr [r14+r12+2]
0x18001379d  lea     rbp, [r12+18h]
0x1800137a2  add     rbp, r14
0x1800137a5  cmp     eax, 3
0x1800137a8  jnz     short loc_1800137DD
0x1800137aa  cmp     qword ptr [rbp+0], 0
0x1800137af  jz      short loc_1800137DD
0x1800137b1  mov     rcx, [r14+r12+10h]; cb
0x1800137b6  call    cs:__imp_CoTaskMemAlloc
0x1800137bc  mov     [rbx+rdi+18h], rax
0x1800137c1  test    rax, rax
0x1800137c4  jz      loc_1800138B0
0x1800137ca  mov     r8, [r14+r12+10h]; Size
0x1800137cf  mov     rdx, [rbp+0]; Src
0x1800137d3  mov     rcx, rax; void *
0x1800137d6  call    memcpy_0
0x1800137db  jmp     short loc_18001385C
0x1800137dd  mov     rcx, rbp
0x1800137e0  cmp     eax, 4
0x1800137e3  jnz     short loc_18001383D
0x1800137e5  lea     rcx, [r12+18h]
0x1800137ea  add     rcx, r14
0x1800137ed  mov     qword ptr [rsp+0C8h+Buf1], rcx
0x1800137f2  mov     rdx, [rcx]
0x1800137f5  test    rdx, rdx
0x1800137f8  jz      short loc_18001383D
0x1800137fa  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180013801  lea     rax, [rax+1]
0x180013805  cmp     word ptr [rdx+rax*2], 0
0x18001380a  jnz     short loc_180013801
0x18001380c  lea     r14, [rax+1]
0x180013810  lea     rcx, [r14+r14]; cb
0x180013814  call    cs:__imp_CoTaskMemAlloc
0x18001381a  mov     [rbx+rdi+18h], rax
0x18001381f  test    rax, rax
0x180013822  jz      loc_1800138B0
0x180013828  mov     r8, qword ptr [rsp+0C8h+Buf1]
0x18001382d  mov     r8, [r8]; unsigned __int16 *
0x180013830  mov     rdx, r14; unsigned __int64
0x180013833  mov     rcx, rax; unsigned __int16 *
0x180013836  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001383b  jmp     short loc_18001385C
0x18001383d  cmp     eax, 1
0x180013840  jz      short loc_180013849
0x180013842  cmp     eax, 2
0x180013845  jz      short loc_18001384C
0x180013847  jmp     short loc_18001385C
0x180013849  mov     rbp, rcx
0x18001384c  mov     rcx, [rbp+0]
0x180013850  mov     rax, [rcx]
0x180013853  mov     rax, [rax+8]
0x180013857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001385c  mov     eax, [rsi+358h]
0x180013862  mov     [rbx+rdi+4], eax
0x180013866  mov     eax, dword ptr [rsp+0C8h+pv]
0x18001386a  sub     [rbx+rdi+8], rax
0x18001386f  inc     r15d
0x180013872  xor     ebp, ebp
0x180013874  mov     ebx, [rsp+0C8h+var_8C]
0x180013878  inc     r13d
0x18001387b  cmp     r13d, ebx
0x18001387e  jb      loc_180013700
0x180013884  lea     rcx, [rsi+60h]; lpCriticalSection
0x180013888  call    cs:__imp_EnterCriticalSection
0x18001388e  cmp     dword ptr [rsi+36Ch], 0
0x180013895  jz      short loc_1800138C0
0x180013897  cmp     qword ptr [rsi+360h], 0FFFFFFFFFFFFFFFFh
0x18001389f  jz      short loc_1800138C0
0x1800138a1  lea     rcx, [rsi+60h]; lpCriticalSection
0x1800138a5  call    cs:__imp_LeaveCriticalSection
0x1800138ab  jmp     loc_180013995
0x1800138b0  xor     eax, eax
0x1800138b2  mov     [rbx+rdi], ax
0x1800138b6  mov     ebp, 8007000Eh
0x1800138bb  jmp     loc_18001350B
0x1800138c0  lea     rcx, [rsi+60h]; lpCriticalSection
0x1800138c4  call    cs:__imp_LeaveCriticalSection
0x1800138ca  xor     r14d, r14d
0x1800138cd  test    r15d, r15d
0x1800138d0  jz      loc_180013995
0x1800138d6  xor     ebx, ebx
0x1800138d8  mov     r12, rbx
0x1800138db  shl     r12, 5
0x1800138df  movsx   eax, word ptr [r12+rdi]
0x1800138e4  cmp     eax, [rsi+368h]
0x1800138ea  jnz     loc_180013986
0x1800138f0  xorps   xmm0, xmm0
0x1800138f3  movups  [rsp+0C8h+Buf1], xmm0
0x1800138f8  mov     [rsp+0C8h+pv], 0
0x180013901  mov     rcx, [rsi+298h]
0x180013908  mov     rax, [rcx]
0x18001390b  lea     r8, [rsp+0C8h+pv]
0x180013910  lea     rdx, [rsp+0C8h+Buf1]
0x180013915  mov     rax, [rax+70h]
0x180013919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001391e  mov     ebp, eax
  ... truncated ...
```
