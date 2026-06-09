# CSsdpCacheEntry::HrUpdateEntry(_SSDP_REQUEST const *,int *,int *,ulong *)

- ea: `0x180005740`
- end: `0x180005c7d`
- name: `?HrUpdateEntry@CSsdpCacheEntry@@QEAAJPEBU_SSDP_REQUEST@@PEAH1PEAK@Z`
- size: `1341`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *__hidden this, const struct _SSDP_REQUEST *, int *, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003a00`

## callees

- `0x180005740`
- `0x180005c90`
- `0x180006d70`
- `0x180006eb8`
- `0x180007170`
- `0x180007360`
- `0x180008610`
- `0x18000993c`
- `0x18001e594`
- `0x1800255a8`
- `0x18002c8cc`
- `0x18002f028`
- `0x18002f0f4`
- `0x18002f768`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800057cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005852`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005998`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800057cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005852`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005998`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005767`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000577e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005767`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000577e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800057db`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800057db`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntry::HrUpdateEntry(
        CSsdpCacheEntry *this,
        const struct _SSDP_REQUEST *a2,
        int *a3,
        int *a4,
        unsigned int *a5)
{
  const char *v9; // rcx
  int MaxAgeFromCacheControl; // eax
  unsigned int v11; // eax
  unsigned int updated; // ebx
  LPCSTR v13; // rcx
  __int64 v14; // r8
  LPCSTR v15; // rcx
  char *v17; // r15
  LPCSTR v18; // rcx
  LPCSTR v19; // rcx
  int v20; // eax
  int v21; // [rsp+70h] [rbp+8h] BYREF
  int v22; // [rsp+78h] [rbp+10h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  v22 = 0;
  v21 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  v9 = *(const char **)(*((_QWORD *)a2 + 10) + 72LL);
  if ( !v9 )
  {
    updated = -2147024809;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
      goto LABEL_4;
    if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_43;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, 2147942487LL);
LABEL_42:
    v18 = WPP_GLOBAL_Control;
LABEL_43:
    if ( v18 != (LPCSTR)&WPP_GLOBAL_Control && (v18[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v18 + 2), 34, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, updated);
    goto LABEL_4;
  }
  MaxAgeFromCacheControl = GetMaxAgeFromCacheControl(v9);
  if ( MaxAgeFromCacheControl == -1 )
  {
    updated = -2147024809;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, 2147942487LL);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
    goto LABEL_38;
  }
  v11 = CTimerBase::HrResetTimer((char *)this + 120, 1000 * MaxAgeFromCacheControl);
  *(_DWORD *)this = 0;
  updated = v11;
  if ( v11 )
    goto LABEL_42;
LABEL_4:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  if ( updated )
    goto LABEL_38;
  *((_QWORD *)this + 33) = GetTickCount64();
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
  {
    v17 = (char *)this + 88;
    if ( (WPP_GLOBAL_Control[28] & 8) != 0 )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        (unsigned int)WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
        **(_QWORD **)v17,
        **((_QWORD **)a2 + 10));
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != (LPCSTR)&WPP_GLOBAL_Control )
    {
      if ( (v13[28] & 8) != 0 )
      {
        WPP_SF_ss(
          *((_QWORD *)v13 + 2),
          36,
          (unsigned int)WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
          *(_QWORD *)(*(_QWORD *)v17 + 64LL),
          *(_QWORD *)(*((_QWORD *)a2 + 10) + 64LL));
        v13 = WPP_GLOBAL_Control;
      }
      if ( v13 != (LPCSTR)&WPP_GLOBAL_Control )
      {
        if ( (v13[28] & 8) != 0 )
        {
          WPP_SF_ss(
            *((_QWORD *)v13 + 2),
            37,
            (unsigned int)WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
            *(_QWORD *)(*(_QWORD *)v17 + 8LL),
            *(_QWORD *)(*((_QWORD *)a2 + 10) + 8LL));
          v13 = WPP_GLOBAL_Control;
        }
        if ( v13 != (LPCSTR)&WPP_GLOBAL_Control )
        {
          if ( (v13[28] & 8) != 0 )
          {
            WPP_SF_ss(
              *((_QWORD *)v13 + 2),
              38,
              (unsigned int)WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
              *(_QWORD *)(*((_QWORD *)this + 11) + 48LL),
              *(_QWORD *)(*((_QWORD *)a2 + 10) + 48LL));
            v13 = WPP_GLOBAL_Control;
          }
          if ( v13 != (LPCSTR)&WPP_GLOBAL_Control )
          {
            if ( (v13[28] & 8) != 0 )
            {
              WPP_SF_ss(
                *((_QWORD *)v13 + 2),
                39,
                (unsigned int)WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
                *(_QWORD *)(*((_QWORD *)this + 11) + 152LL),
                *(_QWORD *)(*((_QWORD *)a2 + 10) + 152LL));
              v13 = WPP_GLOBAL_Control;
            }
            if ( v13 != (LPCSTR)&WPP_GLOBAL_Control && (v13[28] & 8) != 0 )
              WPP_SF_ss(
                *((_QWORD *)v13 + 2),
                40,
                (unsigned int)WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
                *((_QWORD *)this + 7),
                *((_QWORD *)a2 + 6));
          }
        }
      }
    }
  }
  if ( !(unsigned int)CompareSsdpRequest((CSsdpCacheEntry *)((char *)this + 8), a2, &v22, &v21) )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, this);
      v19 = WPP_GLOBAL_Control;
    }
    if ( v22 || v21 )
    {
      if ( v19 != (LPCSTR)&WPP_GLOBAL_Control && (v19[28] & 8) != 0 )
        WPP_SF_qdd(*((_QWORD *)v19 + 2), (unsigned int)v22, v14, this, v22, v21);
      *a4 = 1;
      v20 = CSsdpCacheEntry::NotifyByeByeForAllAddressFamily(this);
      updated = v20;
      if ( v20 < 0 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
          (unsigned int)v20);
      CSsdpCacheEntry::ClearLocationCacheEntry(this);
    }
  }
  FreeSsdpRequest((CSsdpCacheEntry *)((char *)this + 8));
  if ( (unsigned int)CopySsdpRequest((struct _NETWORK_LOCATION_INFO **)this + 1, a2) )
  {
    if ( (updated & 0x80000000) == 0 )
    {
      updated = CSsdpCacheEntry::UpdateLocationCacheEntry(this, a4, a3);
      *a5 = (*((_DWORD *)this + 27) != 0) + (*((_DWORD *)this + 28) != 0);
    }
  }
  else
  {
    updated = -2147024882;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
  {
    if ( (WPP_GLOBAL_Control[28] & 8) == 0 )
    {
LABEL_14:
      if ( v15 != (LPCSTR)&WPP_GLOBAL_Control && (v15[28] & 8) != 0 )
      {
        WPP_SF_qd(*((_QWORD *)v15 + 2), 45, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, this, *a4);
        v15 = WPP_GLOBAL_Control;
      }
      goto LABEL_11;
    }
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, this);
LABEL_38:
    v15 = WPP_GLOBAL_Control;
    goto LABEL_14;
  }
LABEL_11:
  if ( updated && v15 != (LPCSTR)&WPP_GLOBAL_Control && (v15[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v15 + 2), 46, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, updated);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  return updated;
}

```

## disassembly

```asm
0x180005740  mov     [rsp+arg_10], rbx
0x180005745  push    rbp
0x180005746  push    rsi
0x180005747  push    rdi
0x180005748  push    r12
0x18000574a  push    r13
0x18000574c  push    r14
0x18000574e  push    r15
0x180005750  sub     rsp, 30h
0x180005754  mov     r14, rcx
0x180005757  mov     r13, r9
0x18000575a  add     rcx, 0D8h; lpCriticalSection
0x180005761  mov     r12, r8
0x180005764  mov     rbp, rdx
0x180005767  call    cs:__imp_EnterCriticalSection
0x18000576d  xor     esi, esi
0x18000576f  lea     rcx, [r14+0D8h]; lpCriticalSection
0x180005776  mov     [rsp+68h+arg_8], esi
0x18000577a  mov     [rsp+68h+arg_0], esi
0x18000577e  call    cs:__imp_EnterCriticalSection
0x180005784  mov     rax, [rbp+50h]
0x180005788  lea     r15, WPP_GLOBAL_Control
0x18000578f  mov     rcx, [rax+48h]; char *
0x180005793  test    rcx, rcx
0x180005796  jz      loc_1800059AA
0x18000579c  call    ?GetMaxAgeFromCacheControl@@YAHPEBD@Z; GetMaxAgeFromCacheControl(char const *)
0x1800057a1  cmp     eax, 0FFFFFFFFh
0x1800057a4  jz      loc_180005A14
0x1800057aa  imul    edx, eax, 3E8h; DueTime
0x1800057b0  lea     rcx, [r14+78h]; Parameter
0x1800057b4  call    ?HrResetTimer@CTimerBase@@QEAAJK@Z; CTimerBase::HrResetTimer(ulong)
0x1800057b9  mov     [r14], esi
0x1800057bc  mov     ebx, eax
0x1800057be  test    eax, eax
0x1800057c0  jnz     loc_1800059DD
0x1800057c6  lea     rcx, [r14+0D8h]; lpCriticalSection
0x1800057cd  call    cs:__imp_LeaveCriticalSection
0x1800057d3  test    ebx, ebx
0x1800057d5  jnz     loc_18000599E
0x1800057db  call    cs:__imp_GetTickCount64
0x1800057e1  mov     [r14+108h], rax
0x1800057e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057ef  cmp     rcx, r15
0x1800057f2  jnz     loc_1800058E3
0x1800057f8  lea     r9, [rsp+68h+arg_0]; int *
0x1800057fd  mov     rdx, rbp; struct _SSDP_REQUEST *
0x180005800  lea     r8, [rsp+68h+arg_8]; int *
0x180005805  lea     rcx, [r14+8]; struct _SSDP_REQUEST *
0x180005809  call    ?CompareSsdpRequest@@YAHPEBU_SSDP_REQUEST@@0PEAH1@Z; CompareSsdpRequest(_SSDP_REQUEST const *,_SSDP_REQUEST const *,int *,int *)
0x18000580e  test    eax, eax
0x180005810  jz      loc_180005B75
0x180005816  lea     rcx, [r14+8]; struct _SSDP_REQUEST *
0x18000581a  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x18000581f  mov     rdx, rbp; struct _SSDP_REQUEST *
0x180005822  lea     rcx, [r14+8]; struct _SSDP_REQUEST *
0x180005826  call    ?CopySsdpRequest@@YAHPEAU_SSDP_REQUEST@@PEBU1@@Z; CopySsdpRequest(_SSDP_REQUEST *,_SSDP_REQUEST const *)
0x18000582b  test    eax, eax
0x18000582d  jz      loc_180005C26
0x180005833  test    ebx, ebx
0x180005835  jns     short loc_1800058B0
0x180005837  mov     rcx, cs:WPP_GLOBAL_Control
0x18000583e  cmp     rcx, r15
0x180005841  jnz     short loc_180005872
0x180005843  test    ebx, ebx
0x180005845  jnz     loc_180005C4D
0x18000584b  lea     rcx, [r14+0D8h]; lpCriticalSection
0x180005852  call    cs:__imp_LeaveCriticalSection
0x180005858  mov     eax, ebx
0x18000585a  mov     rbx, [rsp+68h+arg_10]
0x180005862  add     rsp, 30h
0x180005866  pop     r15
0x180005868  pop     r14
0x18000586a  pop     r13
0x18000586c  pop     r12
0x18000586e  pop     rdi
0x18000586f  pop     rsi
0x180005870  pop     rbp
0x180005871  retn
0x180005872  test    byte ptr [rcx+1Ch], 8
0x180005876  jnz     loc_180005C30
0x18000587c  cmp     rcx, r15
0x18000587f  jz      short loc_180005843
0x180005881  test    byte ptr [rcx+1Ch], 8
0x180005885  jz      short loc_180005843
0x180005887  mov     eax, [r13+0]
0x18000588b  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180005892  mov     rcx, [rcx+10h]
0x180005896  mov     edx, 2Dh ; '-'
0x18000589b  mov     r9, r14
0x18000589e  mov     dword ptr [rsp+68h+var_48], eax
0x1800058a2  call    WPP_SF_qd
0x1800058a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058ae  jmp     short loc_180005843
0x1800058b0  mov     r8, r12; int *
0x1800058b3  mov     rdx, r13; int *
0x1800058b6  mov     rcx, r14; this
0x1800058b9  call    ?UpdateLocationCacheEntry@CSsdpCacheEntry@@AEAAJPEAH0@Z; CSsdpCacheEntry::UpdateLocationCacheEntry(int *,int *)
0x1800058be  xor     ecx, ecx
0x1800058c0  mov     ebx, eax
0x1800058c2  cmp     [r14+70h], ecx
0x1800058c6  setnz   cl
0x1800058c9  xor     eax, eax
0x1800058cb  cmp     [r14+6Ch], eax
0x1800058cf  setnz   al
0x1800058d2  add     ecx, eax
0x1800058d4  mov     rax, [rsp+68h+arg_20]
0x1800058dc  mov     [rax], ecx
0x1800058de  jmp     loc_180005837
0x1800058e3  test    byte ptr [rcx+1Ch], 8
0x1800058e7  lea     r15, [r14+58h]
0x1800058eb  jnz     loc_180005A4B
0x1800058f1  lea     rax, WPP_GLOBAL_Control
0x1800058f8  cmp     rcx, rax
0x1800058fb  jz      short loc_18000590F
0x1800058fd  test    byte ptr [rcx+1Ch], 8
0x180005901  jnz     loc_180005A7E
0x180005907  mov     rsi, r15
0x18000590a  cmp     rcx, rax
0x18000590d  jnz     short loc_18000591B
0x18000590f  lea     r15, WPP_GLOBAL_Control
0x180005916  jmp     loc_1800057F8
0x18000591b  test    byte ptr [rcx+1Ch], 8
0x18000591f  jnz     loc_180005ABE
0x180005925  mov     r15, rsi
0x180005928  cmp     rcx, rax
0x18000592b  jz      short loc_18000590F
0x18000592d  test    byte ptr [rcx+1Ch], 8
0x180005931  jnz     loc_180005AFE
0x180005937  cmp     rcx, rax
0x18000593a  jz      short loc_18000590F
0x18000593c  test    byte ptr [rcx+1Ch], 8
0x180005940  jnz     loc_180005B3A
0x180005946  lea     r15, WPP_GLOBAL_Control
0x18000594d  cmp     rcx, r15
0x180005950  jz      loc_1800057F8
0x180005956  test    byte ptr [rcx+1Ch], 8
0x18000595a  jz      loc_1800057F8
0x180005960  mov     rax, [rbp+30h]
0x180005964  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000596b  mov     r9, [r14+38h]
0x18000596f  mov     edx, 28h ; '('
0x180005974  mov     rcx, [rcx+10h]
0x180005978  mov     [rsp+68h+var_48], rax
0x18000597d  call    WPP_SF_ss
0x180005982  jmp     loc_1800057F8
0x180005987  test    byte ptr [rcx+1Ch], 1
0x18000598b  jnz     loc_180005A2E
0x180005991  lea     rcx, [r14+0D8h]; lpCriticalSection
0x180005998  call    cs:__imp_LeaveCriticalSection
0x18000599e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059a5  jmp     loc_18000587C
0x1800059aa  mov     ebx, 80070057h
0x1800059af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059b6  cmp     rcx, r15
0x1800059b9  jz      loc_1800057C6
0x1800059bf  test    byte ptr [rcx+1Ch], 1
0x1800059c3  jz      short loc_1800059E4
0x1800059c5  mov     rcx, [rcx+10h]
0x1800059c9  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x1800059d0  mov     edx, 20h ; ' '
0x1800059d5  mov     r9d, ebx
0x1800059d8  call    WPP_SF_d
0x1800059dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059e4  cmp     rcx, r15
0x1800059e7  jz      loc_1800057C6
0x1800059ed  test    byte ptr [rcx+1Ch], 1
0x1800059f1  jz      loc_1800057C6
0x1800059f7  mov     rcx, [rcx+10h]
0x1800059fb  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180005a02  mov     edx, 22h ; '"'
0x180005a07  mov     r9d, ebx
0x180005a0a  call    WPP_SF_d
0x180005a0f  jmp     loc_1800057C6
0x180005a14  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a1b  mov     ebx, 80070057h
0x180005a20  cmp     rcx, r15
0x180005a23  jz      loc_180005991
0x180005a29  jmp     loc_180005987
0x180005a2e  mov     rcx, [rcx+10h]
0x180005a32  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180005a39  mov     edx, 21h ; '!'
0x180005a3e  mov     r9d, ebx
0x180005a41  call    WPP_SF_d
0x180005a46  jmp     loc_180005991
0x180005a4b  mov     rax, [rbp+50h]
0x180005a4f  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180005a56  mov     r9, [r15]
0x180005a59  mov     edx, 23h ; '#'
0x180005a5e  mov     rcx, [rcx+10h]
0x180005a62  mov     rax, [rax]
0x180005a65  mov     r9, [r9]
0x180005a68  mov     [rsp+68h+var_48], rax
0x180005a6d  call    WPP_SF_ss
0x180005a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a79  jmp     loc_1800058F1
0x180005a7e  mov     rax, [rbp+50h]
0x180005a82  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180005a89  mov     r9, [r15]
0x180005a8c  mov     edx, 24h ; '$'
0x180005a91  mov     rcx, [rcx+10h]
0x180005a95  mov     rax, [rax+40h]
0x180005a99  mov     r9, [r9+40h]
0x180005a9d  mov     [rsp+68h+var_48], rax
0x180005aa2  call    WPP_SF_ss
0x180005aa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180005aae  lea     rax, WPP_GLOBAL_Control
0x180005ab5  lea     rsi, [r14+58h]
0x180005ab9  jmp     loc_18000590A
0x180005abe  mov     rax, [rbp+50h]
0x180005ac2  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180005ac9  mov     r9, [r15]
0x180005acc  mov     edx, 25h ; '%'
0x180005ad1  mov     rcx, [rcx+10h]
0x180005ad5  mov     rax, [rax+8]
0x180005ad9  mov     r9, [r9+8]
0x180005add  mov     [rsp+68h+var_48], rax
0x180005ae2  call    WPP_SF_ss
0x180005ae7  mov     rcx, cs:WPP_GLOBAL_Control
0x180005aee  lea     rax, WPP_GLOBAL_Control
0x180005af5  lea     r15, [r14+58h]
0x180005af9  jmp     loc_180005928
0x180005afe  mov     rax, [rbp+50h]
0x180005b02  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180005b09  mov     r9, [rsi]
0x180005b0c  mov     edx, 26h ; '&'
0x180005b11  mov     rcx, [rcx+10h]
0x180005b15  mov     rax, [rax+30h]
0x180005b19  mov     r9, [r9+30h]
0x180005b1d  mov     [rsp+68h+var_48], rax
0x180005b22  call    WPP_SF_ss
0x180005b27  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b2e  lea     rax, WPP_GLOBAL_Control
0x180005b35  jmp     loc_180005937
0x180005b3a  mov     rax, [rbp+50h]
0x180005b3e  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180005b45  mov     r9, [r15]
0x180005b48  mov     edx, 27h ; '''
0x180005b4d  mov     rcx, [rcx+10h]
0x180005b51  mov     rax, [rax+98h]
0x180005b58  mov     r9, [r9+98h]
0x180005b5f  mov     [rsp+68h+var_48], rax
0x180005b64  call    WPP_SF_ss
0x180005b69  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b70  jmp     loc_180005946
0x180005b75  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b7c  cmp     rcx, r15
0x180005b7f  jz      short loc_180005BA6
0x180005b81  test    byte ptr [rcx+1Ch], 8
0x180005b85  jz      short loc_180005BA6
0x180005b87  mov     rcx, [rcx+10h]
0x180005b8b  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180005b92  mov     edx, 29h ; ')'
0x180005b97  mov     r9, r14
0x180005b9a  call    WPP_SF_q
0x180005b9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ba6  mov     edx, [rsp+68h+arg_8]
0x180005baa  mov     eax, [rsp+68h+arg_0]
0x180005bae  test    edx, edx
0x180005bb0  jnz     short loc_180005BBA
0x180005bb2  test    eax, eax
0x180005bb4  jz      loc_180005816
0x180005bba  cmp     rcx, r15
0x180005bbd  jz      short loc_180005BD9
0x180005bbf  test    byte ptr [rcx+1Ch], 8
0x180005bc3  jz      short loc_180005BD9
0x180005bc5  mov     rcx, [rcx+10h]
0x180005bc9  mov     r9, r14
0x180005bcc  mov     [rsp+68h+var_40], eax
0x180005bd0  mov     dword ptr [rsp+68h+var_48], edx
0x180005bd4  call    WPP_SF_qdd
0x180005bd9  mov     rcx, r14; this
0x180005bdc  mov     dword ptr [r13+0], 1
0x180005be4  call    ?NotifyByeByeForAllAddressFamily@CSsdpCacheEntry@@QEAAJXZ; CSsdpCacheEntry::NotifyByeByeForAllAddressFamily(void)
0x180005be9  mov     ebx, eax
0x180005beb  test    eax, eax
0x180005bed  jns     short loc_180005C19
0x180005bef  mov     rcx, cs:WPP_GLOBAL_Control
0x180005bf6  cmp     rcx, r15
0x180005bf9  jz      short loc_180005C19
0x180005bfb  test    byte ptr [rcx+1Ch], 1
0x180005bff  jz      short loc_180005C19
0x180005c01  mov     rcx, [rcx+10h]
0x180005c05  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180005c0c  mov     edx, 2Bh ; '+'
0x180005c11  mov     r9d, eax
0x180005c14  call    WPP_SF_d
0x180005c19  mov     rcx, r14; this
0x180005c1c  call    ?ClearLocationCacheEntry@CSsdpCacheEntry@@AEAAXXZ; CSsdpCacheEntry::ClearLocationCacheEntry(void)
0x180005c21  jmp     loc_180005816
0x180005c26  mov     ebx, 8007000Eh
0x180005c2b  jmp     loc_180005837
0x180005c30  mov     rcx, [rcx+10h]
0x180005c34  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180005c3b  mov     edx, 2Ch ; ','
0x180005c40  mov     r9, r14
0x180005c43  call    WPP_SF_q
0x180005c48  jmp     loc_18000599E
0x180005c4d  cmp     rcx, r15
0x180005c50  jz      loc_18000584B
0x180005c56  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
