# CJob::GetAtInfo(_AT_INFO *,ushort *,ulong *)

- ea: `0x180023794`
- end: `0x180023b99`
- name: `?GetAtInfo@CJob@@QEAAJPEAU_AT_INFO@@PEAGPEAK@Z`
- size: `1029`
- prototype: `int __fastcall(CJob *this, struct _AT_INFO *, unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d414`
- `0x180016020`
- `0x180027b30`

## callees

- `0x1800031a0`
- `0x180003ef0`
- `0x180023794`
- `0x180023ba0`
- `0x180025500`
- `0x180026a38`
- `0x18002b398`
- `0x18002e5b0`
- `0x180031010`

## import_xrefs

- `msvcrt!wcschr` at `0x180023832`
- `msvcrt!wcschr` at `0x180023832`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180023a4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180023a4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023820`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023905`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002390f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800239a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023820`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023905`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002390f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800239a3`

## pseudocode

```c
int __fastcall CJob::GetAtInfo(CJob *this, struct _AT_INFO *a2, unsigned __int16 *a3, unsigned int *a4)
{
  int result; // eax
  __int64 v9; // rax
  int v10; // eax
  void *v11; // rcx
  int v12; // ebx
  wchar_t *v13; // r9
  __int64 v14; // rdx
  __int64 v15; // r14
  void *v16; // rcx
  unsigned int v17; // eax
  unsigned __int64 v18; // rdx
  struct _TASK_TRIGGER *Trigger; // rax
  __int16 v20; // r10
  struct _TASK_TRIGGER *v21; // rbx
  int v22; // edx
  int wStartMinute; // ecx
  TASK_TRIGGER_TYPE TriggerType; // ecx
  __int32 v25; // ecx
  __int16 v26; // ax
  struct _TASK_TRIGGER *v27; // rax
  int v28; // edx
  TASK_TRIGGER_TYPE v29; // ecx
  __int32 v30; // ecx
  __int16 v31; // ax
  char v32; // al
  __int64 v33; // rax
  unsigned __int16 *v34; // [rsp+30h] [rbp-69h]
  unsigned __int16 *v35; // [rsp+30h] [rbp-69h]
  unsigned __int16 v36; // [rsp+40h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-51h] BYREF
  int v38; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 *v39; // [rsp+58h] [rbp-41h] BYREF
  struct _SYSTEMTIME v40; // [rsp+60h] [rbp-39h] BYREF
  struct _SYSTEMTIME v41; // [rsp+70h] [rbp-29h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-19h] BYREF
  struct _SYSTEMTIME v43; // [rsp+90h] [rbp-9h] BYREF

  if ( (*((_DWORD *)this + 22) & 0x200000) == 0 )
    return -2147024894;
  v9 = *(_QWORD *)this;
  pv = 0;
  v39 = 0;
  result = (*(__int64 (__fastcall **)(CJob *, LPVOID *))(v9 + 264))(this, &pv);
  if ( result < 0 )
    return result;
  v10 = (*(__int64 (__fastcall **)(CJob *, unsigned __int16 **))(*(_QWORD *)this + 280LL))(this, &v39);
  v11 = pv;
  v12 = v10;
  if ( v10 < 0 )
  {
LABEL_5:
    CoTaskMemFree(v11);
    return v12;
  }
  v13 = wcschr((const wchar_t *)pv, 0x20u);
  v14 = -1;
  v15 = -1;
  do
    ++v15;
  while ( v39[v15] );
  v16 = pv;
  do
    ++v14;
  while ( *((_WORD *)pv + v14) );
  v17 = *a4;
  v18 = (unsigned int)v15 + (v13 != 0 ? 2 : 0) + ((_DWORD)v15 != 0) + 1 + (_DWORD)v14;
  *a4 = v18;
  if ( (unsigned int)v18 > v17 )
  {
    v12 = -2147024774;
LABEL_25:
    CoTaskMemFree(v16);
    v11 = v39;
    goto LABEL_5;
  }
  if ( !v13 )
  {
    v12 = StringCchCopyW(a3, v18, (const unsigned __int16 *)v16);
    if ( v12 >= 0 )
      goto LABEL_15;
LABEL_24:
    v16 = pv;
    goto LABEL_25;
  }
  v12 = StringCchCopyW(a3, v18, L"\"");
  if ( v12 < 0 )
    goto LABEL_24;
  StringCchCatW(a3, *a4, (const unsigned __int16 *)pv);
  StringCchCatW(a3, *a4, L"\"");
LABEL_15:
  if ( (_DWORD)v15 )
  {
    StringCchCatW(a3, *a4, L" ");
    StringCchCatW(a3, *a4, v39);
  }
  CoTaskMemFree(pv);
  CoTaskMemFree(v39);
  if ( (unsigned __int16)(*((_WORD *)this + 16) - 1) > 1u )
    return -2147467259;
  Trigger = CJob::_GetTrigger(this, 0);
  v21 = Trigger;
  if ( !Trigger )
    return -2147467259;
  v22 = 60 * Trigger->wStartHour;
  wStartMinute = Trigger->wStartMinute;
  a2->DaysOfWeek = 0;
  a2->DaysOfMonth = 0;
  a2->JobTime = 60000 * (wStartMinute + v22);
  TriggerType = Trigger->TriggerType;
  if ( TriggerType )
  {
    v25 = TriggerType - 2;
    if ( v25 )
    {
      if ( v25 != 1 )
        return -2147467259;
      a2->DaysOfMonth = Trigger->Type.MonthlyDate.rgfDays;
    }
    else
    {
      v26 = Trigger->Type.Weekly.rgfDaysOfTheWeek >> 1;
      a2->DaysOfWeek = v26;
      if ( (v21->Type.Weekly.rgfDaysOfTheWeek & 1) != 0 )
        a2->DaysOfWeek = v26 | 0x40;
    }
  }
  if ( v20 == 2 )
  {
    v27 = CJob::_GetTrigger(this, 1);
    v21 = v27;
    v29 = v27->TriggerType;
    if ( v29 == TASK_TIME_TRIGGER_ONCE )
      return -2147467259;
    v30 = v29 - 2;
    if ( v30 )
    {
      if ( v30 != v28 )
        return -2147467259;
      a2->DaysOfMonth = v27->Type.MonthlyDate.rgfDays;
    }
    else
    {
      v31 = v27->Type.Weekly.rgfDaysOfTheWeek >> 1;
      a2->DaysOfWeek = v31;
      if ( (v21->Type.Weekly.rgfDaysOfTheWeek & 1) != 0 )
        a2->DaysOfWeek = v31 | 0x40;
    }
  }
  a2->Flags = 0;
  v32 = 0;
  if ( (*((_BYTE *)this + 88) & 1) == 0 )
  {
    v32 = 16;
    a2->Flags = 16;
  }
  if ( (v21->rgFlags & 1) == 0 && v21->TriggerType )
    a2->Flags = v32 | 1;
  SystemTime = 0;
  v41 = 0;
  v43 = 0;
  GetLocalTime(&SystemTime);
  *(_QWORD *)&v41.wYear = *(_QWORD *)&SystemTime.wYear;
  *(_QWORD *)&v41.wHour = 0;
  IncrementDay(&v41);
  v36 = 0;
  result = CJob::GetRunTimesP(this, &SystemTime, &v41, &v36, 1u, 0, v34);
  if ( result >= 0 )
  {
    if ( v36 )
      a2->Flags |= 4u;
    if ( (*((_DWORD *)this + 22) & 0x180000) != 0 )
      a2->Flags |= 2u;
    if ( v21->TriggerType || (a2->Flags & 2) != 0 )
      goto LABEL_51;
    v43 = SystemTime;
    IncrementDay(&v43);
    result = CJob::GetRunTimesP(this, &SystemTime, &v43, &v36, 1u, 0, v35);
    if ( result < 0 )
      return result;
    v33 = *(_QWORD *)this;
    v38 = 0;
    (*(void (__fastcall **)(CJob *, int *))(v33 + 128))(this, &v38);
    if ( v36 )
    {
LABEL_51:
      if ( (v21->rgFlags & 1) == 0 )
        return 0;
      v40.wYear = v21->wEndYear;
      v40.wMonth = v21->wEndMonth;
      v40.wDay = v21->wEndDay;
      v40.wHour = v21->wStartHour;
      v40.wMinute = v21->wStartMinute;
      v40.wDayOfWeek = 0;
      *(_DWORD *)&v40.wSecond = 0;
      if ( !IsFirstTimeEarlier(&v40, &SystemTime) || (a2->Flags & 2) != 0 )
        return 0;
      return -2147467259;
    }
    if ( v38 == 267009 )
    {
      a2->Flags |= 4u;
      goto LABEL_51;
    }
    return -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x180023794  push    rbp
0x180023796  push    rbx
0x180023797  push    rsi
0x180023798  push    rdi
0x180023799  push    r12
0x18002379b  push    r13
0x18002379d  push    r14
0x18002379f  push    r15
0x1800237a1  lea     rbp, [rsp-1Fh]
0x1800237a6  sub     rsp, 0B8h
0x1800237ad  mov     rax, cs:__security_cookie
0x1800237b4  xor     rax, rsp
0x1800237b7  mov     [rbp+57h+var_50], rax
0x1800237bb  test    dword ptr [rcx+58h], 200000h
0x1800237c2  mov     r12, r9
0x1800237c5  mov     r15, r8
0x1800237c8  mov     rdi, rdx
0x1800237cb  mov     rsi, rcx
0x1800237ce  jnz     short loc_1800237DA
0x1800237d0  mov     eax, 80070002h
0x1800237d5  jmp     loc_180023B79
0x1800237da  mov     rax, [rcx]
0x1800237dd  lea     rdx, [rbp+57h+pv]
0x1800237e1  xor     r13d, r13d
0x1800237e4  mov     [rbp+57h+pv], r13
0x1800237e8  mov     [rbp+57h+var_98], r13
0x1800237ec  mov     rax, [rax+108h]
0x1800237f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237f8  test    eax, eax
0x1800237fa  js      loc_180023B79
0x180023800  mov     rax, [rsi]
0x180023803  lea     rdx, [rbp+57h+var_98]
0x180023807  mov     rcx, rsi
0x18002380a  mov     rax, [rax+118h]
0x180023811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023816  mov     rcx, [rbp+57h+pv]; Str
0x18002381a  mov     ebx, eax
0x18002381c  test    eax, eax
0x18002381e  jns     short loc_18002382D
0x180023820  call    cs:__imp_CoTaskMemFree
0x180023826  mov     eax, ebx
0x180023828  jmp     loc_180023B79
0x18002382d  mov     edx, 20h ; ' '; Ch
0x180023832  call    cs:__imp_wcschr
0x180023838  mov     rcx, rax
0x18002383b  mov     r9, rax
0x18002383e  neg     rcx
0x180023841  mov     rcx, [rbp+57h+var_98]
0x180023845  sbb     r8d, r8d
0x180023848  and     r8d, 2
0x18002384c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180023850  mov     r14, rdx
0x180023853  inc     r14
0x180023856  cmp     [rcx+r14*2], r13w
0x18002385b  jnz     short loc_180023853
0x18002385d  mov     rcx, [rbp+57h+pv]
0x180023861  inc     rdx
0x180023864  cmp     [rcx+rdx*2], r13w
0x180023869  jnz     short loc_180023861
0x18002386b  test    r14d, r14d
0x18002386e  mov     eax, r13d
0x180023871  setnz   al
0x180023874  inc     eax
0x180023876  add     eax, r8d
0x180023879  add     edx, eax
0x18002387b  mov     eax, [r12]
0x18002387f  add     edx, r14d; unsigned __int64
0x180023882  mov     [r12], edx
0x180023886  cmp     edx, eax
0x180023888  jbe     short loc_180023894
0x18002388a  mov     ebx, 8007007Ah
0x18002388f  jmp     loc_1800239A3
0x180023894  test    r9, r9
0x180023897  jz      loc_18002398A
0x18002389d  lea     r8, asc_1800549DC; "\""
0x1800238a4  mov     rcx, r15; unsigned __int16 *
0x1800238a7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800238ac  mov     ebx, eax
0x1800238ae  test    eax, eax
0x1800238b0  js      loc_18002399F
0x1800238b6  mov     edx, [r12]; unsigned __int64
0x1800238ba  mov     rcx, r15; unsigned __int16 *
0x1800238bd  mov     r8, [rbp+57h+pv]; unsigned __int16 *
0x1800238c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800238c6  mov     edx, [r12]; unsigned __int64
0x1800238ca  lea     r8, asc_1800549DC; "\""
0x1800238d1  mov     rcx, r15; unsigned __int16 *
0x1800238d4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800238d9  test    r14d, r14d
0x1800238dc  jz      short loc_180023901
0x1800238de  mov     edx, [r12]; unsigned __int64
0x1800238e2  lea     r8, asc_1800549E0; " "
0x1800238e9  mov     rcx, r15; unsigned __int16 *
0x1800238ec  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800238f1  mov     edx, [r12]; unsigned __int64
0x1800238f5  mov     rcx, r15; unsigned __int16 *
0x1800238f8  mov     r8, [rbp+57h+var_98]; unsigned __int16 *
0x1800238fc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023901  mov     rcx, [rbp+57h+pv]; pv
0x180023905  call    cs:__imp_CoTaskMemFree
0x18002390b  mov     rcx, [rbp+57h+var_98]; pv
0x18002390f  call    cs:__imp_CoTaskMemFree
0x180023915  movzx   r10d, word ptr [rsi+20h]
0x18002391a  mov     r14d, 1
0x180023920  movzx   eax, r10w
0x180023924  sub     ax, r14w
0x180023928  cmp     ax, r14w
0x18002392c  ja      loc_180023B74
0x180023932  xor     edx, edx; unsigned __int16
0x180023934  mov     rcx, rsi; this
0x180023937  call    ?_GetTrigger@CJob@@AEAAPEAU_TASK_TRIGGER@@G@Z; CJob::_GetTrigger(ushort)
0x18002393c  mov     rbx, rax
0x18002393f  test    rax, rax
0x180023942  jz      loc_180023B74
0x180023948  movzx   ecx, word ptr [rax+10h]
0x18002394c  lea     r15d, [r14+1]
0x180023950  imul    edx, ecx, 3Ch ; '<'
0x180023953  movzx   ecx, word ptr [rax+12h]
0x180023957  mov     [rdi+0Ch], r13b
0x18002395b  mov     [rdi+8], r13d
0x18002395f  add     edx, ecx
0x180023961  imul    ecx, edx, 0EA60h
0x180023967  movsxd  rdx, ecx
0x18002396a  mov     [rdi], rdx
0x18002396d  mov     ecx, [rax+20h]
0x180023970  test    ecx, ecx
0x180023972  jz      short loc_1800239C7
0x180023974  sub     ecx, r15d
0x180023977  jz      short loc_1800239B2
0x180023979  cmp     ecx, r14d
0x18002397c  jnz     loc_180023B74
0x180023982  mov     eax, [rax+24h]
0x180023985  mov     [rdi+8], eax
0x180023988  jmp     short loc_1800239C7
0x18002398a  mov     r8, rcx; unsigned __int16 *
0x18002398d  mov     rcx, r15; unsigned __int16 *
0x180023990  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180023995  mov     ebx, eax
0x180023997  test    eax, eax
0x180023999  jns     loc_1800238D9
0x18002399f  mov     rcx, [rbp+57h+pv]; pv
0x1800239a3  call    cs:__imp_CoTaskMemFree
0x1800239a9  mov     rcx, [rbp+57h+var_98]
0x1800239ad  jmp     loc_180023820
0x1800239b2  movzx   eax, word ptr [rax+26h]
0x1800239b6  shr     ax, 1
0x1800239b9  mov     [rdi+0Ch], al
0x1800239bc  test    [rbx+26h], r14b
0x1800239c0  jz      short loc_1800239C7
0x1800239c2  or      al, 40h
0x1800239c4  mov     [rdi+0Ch], al
0x1800239c7  cmp     r10w, r15w
0x1800239cb  jnz     short loc_180023A10
0x1800239cd  mov     edx, r14d; unsigned __int16
0x1800239d0  mov     rcx, rsi; this
0x1800239d3  call    ?_GetTrigger@CJob@@AEAAPEAU_TASK_TRIGGER@@G@Z; CJob::_GetTrigger(ushort)
0x1800239d8  mov     rbx, rax
0x1800239db  mov     ecx, [rax+20h]
0x1800239de  test    ecx, ecx
0x1800239e0  jz      loc_180023B74
0x1800239e6  sub     ecx, r15d
0x1800239e9  jz      short loc_1800239FB
0x1800239eb  cmp     ecx, edx
0x1800239ed  jnz     loc_180023B74
0x1800239f3  mov     eax, [rax+24h]
0x1800239f6  mov     [rdi+8], eax
0x1800239f9  jmp     short loc_180023A10
0x1800239fb  movzx   eax, word ptr [rax+26h]
0x1800239ff  shr     ax, 1
0x180023a02  mov     [rdi+0Ch], al
0x180023a05  test    [rbx+26h], r14b
0x180023a09  jz      short loc_180023A10
0x180023a0b  or      al, 40h
0x180023a0d  mov     [rdi+0Ch], al
0x180023a10  mov     [rdi+0Dh], r13b
0x180023a14  mov     al, r13b
0x180023a17  test    [rsi+58h], r14b
0x180023a1b  jnz     short loc_180023A22
0x180023a1d  mov     al, 10h
0x180023a1f  mov     [rdi+0Dh], al
0x180023a22  test    [rbx+1Ch], r14b
0x180023a26  jnz     short loc_180023A34
0x180023a28  cmp     [rbx+20h], r13d
0x180023a2c  jz      short loc_180023A34
0x180023a2e  or      al, r14b
0x180023a31  mov     [rdi+0Dh], al
0x180023a34  xorps   xmm0, xmm0
0x180023a37  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180023a3b  xorps   xmm1, xmm1
0x180023a3e  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180023a42  movups  xmmword ptr [rbp+57h+var_80.wYear], xmm1
0x180023a46  movups  xmmword ptr [rbp+57h+var_60.wYear], xmm0
0x180023a4a  call    cs:__imp_GetLocalTime
0x180023a50  movaps  xmm0, xmmword ptr [rbp+57h+SystemTime.wYear]
0x180023a54  lea     rcx, [rbp+57h+var_80]; struct _SYSTEMTIME *
0x180023a58  movdqa  xmmword ptr [rbp+57h+var_80.wYear], xmm0
0x180023a5d  mov     qword ptr [rbp+57h+var_80.wHour], r13
0x180023a61  mov     [rbp+57h+var_B0], r13w
0x180023a66  call    ?IncrementDay@@YAXPEAU_SYSTEMTIME@@@Z; IncrementDay(_SYSTEMTIME *)
0x180023a6b  lea     r9, [rbp+57h+var_B0]; unsigned __int16 *
0x180023a6f  mov     [rsp+0F0h+var_C8], r13; struct CTimeRunList *
0x180023a74  lea     r8, [rbp+57h+var_80]; struct _SYSTEMTIME *
0x180023a78  mov     [rbp+57h+var_B0], r13w
0x180023a7d  lea     rdx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x180023a81  mov     [rsp+0F0h+var_D0], r14w; unsigned __int16
0x180023a87  mov     rcx, rsi; this
0x180023a8a  call    ?GetRunTimesP@CJob@@QEAAJPEBU_SYSTEMTIME@@0PEAGGPEAVCTimeRunList@@1@Z; CJob::GetRunTimesP(_SYSTEMTIME const *,_SYSTEMTIME const *,ushort *,ushort,CTimeRunList *,ushort *)
0x180023a8f  test    eax, eax
0x180023a91  js      loc_180023B79
0x180023a97  cmp     [rbp+57h+var_B0], r13w
0x180023a9c  jbe     short loc_180023AA2
0x180023a9e  or      byte ptr [rdi+0Dh], 4
0x180023aa2  test    dword ptr [rsi+58h], 180000h
0x180023aa9  jz      short loc_180023AAF
0x180023aab  or      [rdi+0Dh], r15b
0x180023aaf  cmp     [rbx+20h], r13d
0x180023ab3  jnz     short loc_180023B22
0x180023ab5  test    [rdi+0Dh], r15b
0x180023ab9  jnz     short loc_180023B22
0x180023abb  movaps  xmm0, xmmword ptr [rbp+57h+SystemTime.wYear]
0x180023abf  lea     rcx, [rbp+57h+var_60]; struct _SYSTEMTIME *
0x180023ac3  movdqa  xmmword ptr [rbp+57h+var_60.wYear], xmm0
0x180023ac8  call    ?IncrementDay@@YAXPEAU_SYSTEMTIME@@@Z; IncrementDay(_SYSTEMTIME *)
0x180023acd  lea     r9, [rbp+57h+var_B0]; unsigned __int16 *
0x180023ad1  mov     [rsp+0F0h+var_C8], r13; struct CTimeRunList *
0x180023ad6  lea     r8, [rbp+57h+var_60]; struct _SYSTEMTIME *
0x180023ada  mov     [rsp+0F0h+var_D0], r14w; unsigned __int16
0x180023ae0  lea     rdx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x180023ae4  mov     rcx, rsi; this
0x180023ae7  call    ?GetRunTimesP@CJob@@QEAAJPEBU_SYSTEMTIME@@0PEAGGPEAVCTimeRunList@@1@Z; CJob::GetRunTimesP(_SYSTEMTIME const *,_SYSTEMTIME const *,ushort *,ushort,CTimeRunList *,ushort *)
0x180023aec  test    eax, eax
0x180023aee  js      loc_180023B79
0x180023af4  mov     rax, [rsi]
0x180023af7  lea     rdx, [rbp+57h+var_A0]
0x180023afb  mov     rcx, rsi
0x180023afe  mov     [rbp+57h+var_A0], r13d
0x180023b02  mov     rax, [rax+80h]
0x180023b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b0e  cmp     [rbp+57h+var_B0], r13w
0x180023b13  jnz     short loc_180023B22
0x180023b15  cmp     [rbp+57h+var_A0], 41301h
0x180023b1c  jnz     short loc_180023B74
0x180023b1e  or      byte ptr [rdi+0Dh], 4
0x180023b22  test    [rbx+1Ch], r14b
0x180023b26  jz      short loc_180023B70
0x180023b28  movzx   eax, word ptr [rbx+0Ah]
0x180023b2c  lea     rdx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x180023b30  mov     [rbp+57h+var_90.wYear], ax
0x180023b34  lea     rcx, [rbp+57h+var_90]; struct _SYSTEMTIME *
0x180023b38  movzx   eax, word ptr [rbx+0Ch]
0x180023b3c  mov     [rbp+57h+var_90.wMonth], ax
0x180023b40  movzx   eax, word ptr [rbx+0Eh]
0x180023b44  mov     [rbp+57h+var_90.wDay], ax
0x180023b48  movzx   eax, word ptr [rbx+10h]
0x180023b4c  mov     [rbp+57h+var_90.wHour], ax
0x180023b50  movzx   eax, word ptr [rbx+12h]
0x180023b54  mov     [rbp+57h+var_90.wMinute], ax
0x180023b58  mov     [rbp+57h+var_90.wDayOfWeek], r13w
0x180023b5d  mov     dword ptr [rbp+57h+var_90.wSecond], r13d
0x180023b61  call    ?IsFirstTimeEarlier@@YAHPEBU_SYSTEMTIME@@0@Z; IsFirstTimeEarlier(_SYSTEMTIME const *,_SYSTEMTIME const *)
0x180023b66  test    eax, eax
0x180023b68  jz      short loc_180023B70
0x180023b6a  test    [rdi+0Dh], r15b
0x180023b6e  jz      short loc_180023B74
0x180023b70  xor     eax, eax
0x180023b72  jmp     short loc_180023B79
0x180023b74  mov     eax, 80004005h
0x180023b79  mov     rcx, [rbp+57h+var_50]
0x180023b7d  xor     rcx, rsp; StackCookie
0x180023b80  call    __security_check_cookie
0x180023b85  add     rsp, 0B8h
0x180023b8c  pop     r15
0x180023b8e  pop     r14
0x180023b90  pop     r13
0x180023b92  pop     r12
0x180023b94  pop     rdi
0x180023b95  pop     rsi
0x180023b96  pop     rbx
0x180023b97  pop     rbp
0x180023b98  retn
```
