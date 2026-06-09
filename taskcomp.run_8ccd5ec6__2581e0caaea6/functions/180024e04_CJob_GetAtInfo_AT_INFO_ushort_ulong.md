# CJob::GetAtInfo(_AT_INFO *,ushort *,ulong *)

- ea: `0x180024e04`
- end: `0x18002522e`
- name: `?GetAtInfo@CJob@@QEAAJPEAU_AT_INFO@@PEAGPEAK@Z`
- size: `1066`
- prototype: `__int64 __fastcall(CJob *__hidden this, struct _AT_INFO *, unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000dca8`
- `0x180016ea0`
- `0x180029360`

## callees

- `0x180003320`
- `0x1800040c0`
- `0x180024e04`
- `0x180025234`
- `0x180026cc8`
- `0x18002820c`
- `0x18002cfd4`
- `0x180030700`
- `0x180033010`

## import_xrefs

- `msvcrt!wcschr` at `0x180024ea8`
- `msvcrt!wcschr` at `0x180024ea8`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800250d8`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800250d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024e90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024f81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024f91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002502b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024e90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024f81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024f91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002502b`

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
    v27 = CJob::_GetTrigger(this, 1u);
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
0x180024e04  push    rbp
0x180024e06  push    rbx
0x180024e07  push    rsi
0x180024e08  push    rdi
0x180024e09  push    r12
0x180024e0b  push    r13
0x180024e0d  push    r14
0x180024e0f  push    r15
0x180024e11  lea     rbp, [rsp-1Fh]
0x180024e16  sub     rsp, 0B8h
0x180024e1d  mov     rax, cs:__security_cookie
0x180024e24  xor     rax, rsp
0x180024e27  mov     [rbp+57h+var_50], rax
0x180024e2b  test    dword ptr [rcx+58h], 200000h
0x180024e32  mov     r12, r9
0x180024e35  mov     r15, r8
0x180024e38  mov     rdi, rdx
0x180024e3b  mov     rsi, rcx
0x180024e3e  jnz     short loc_180024E4A
0x180024e40  mov     eax, 80070002h
0x180024e45  jmp     loc_18002520D
0x180024e4a  mov     rax, [rcx]
0x180024e4d  lea     rdx, [rbp+57h+pv]
0x180024e51  xor     r13d, r13d
0x180024e54  mov     [rbp+57h+pv], r13
0x180024e58  mov     [rbp+57h+var_98], r13
0x180024e5c  mov     rax, [rax+108h]
0x180024e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e68  test    eax, eax
0x180024e6a  js      loc_18002520D
0x180024e70  mov     rax, [rsi]
0x180024e73  lea     rdx, [rbp+57h+var_98]
0x180024e77  mov     rcx, rsi
0x180024e7a  mov     rax, [rax+118h]
0x180024e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e86  mov     rcx, [rbp+57h+pv]; Str
0x180024e8a  mov     ebx, eax
0x180024e8c  test    eax, eax
0x180024e8e  jns     short loc_180024EA3
0x180024e90  call    cs:__imp_CoTaskMemFree
0x180024e97  nop     dword ptr [rax+rax+00h]
0x180024e9c  mov     eax, ebx
0x180024e9e  jmp     loc_18002520D
0x180024ea3  mov     edx, 20h ; ' '; Ch
0x180024ea8  call    cs:__imp_wcschr
0x180024eaf  nop     dword ptr [rax+rax+00h]
0x180024eb4  mov     rcx, rax
0x180024eb7  mov     r9, rax
0x180024eba  neg     rcx
0x180024ebd  mov     rcx, [rbp+57h+var_98]
0x180024ec1  sbb     r8d, r8d
0x180024ec4  and     r8d, 2
0x180024ec8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180024ecc  mov     r14, rdx
0x180024ecf  inc     r14
0x180024ed2  cmp     [rcx+r14*2], r13w
0x180024ed7  jnz     short loc_180024ECF
0x180024ed9  mov     rcx, [rbp+57h+pv]
0x180024edd  inc     rdx
0x180024ee0  cmp     [rcx+rdx*2], r13w
0x180024ee5  jnz     short loc_180024EDD
0x180024ee7  test    r14d, r14d
0x180024eea  mov     eax, r13d
0x180024eed  setnz   al
0x180024ef0  inc     eax
0x180024ef2  add     eax, r8d
0x180024ef5  add     edx, eax
0x180024ef7  mov     eax, [r12]
0x180024efb  add     edx, r14d; unsigned __int64
0x180024efe  mov     [r12], edx
0x180024f02  cmp     edx, eax
0x180024f04  jbe     short loc_180024F10
0x180024f06  mov     ebx, 8007007Ah
0x180024f0b  jmp     loc_18002502B
0x180024f10  test    r9, r9
0x180024f13  jz      loc_180025012
0x180024f19  lea     r8, asc_1800569EC; "\""
0x180024f20  mov     rcx, r15; unsigned __int16 *
0x180024f23  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024f28  mov     ebx, eax
0x180024f2a  test    eax, eax
0x180024f2c  js      loc_180025027
0x180024f32  mov     edx, [r12]; unsigned __int64
0x180024f36  mov     rcx, r15; unsigned __int16 *
0x180024f39  mov     r8, [rbp+57h+pv]; unsigned __int16 *
0x180024f3d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180024f42  mov     edx, [r12]; unsigned __int64
0x180024f46  lea     r8, asc_1800569EC; "\""
0x180024f4d  mov     rcx, r15; unsigned __int16 *
0x180024f50  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180024f55  test    r14d, r14d
0x180024f58  jz      short loc_180024F7D
0x180024f5a  mov     edx, [r12]; unsigned __int64
0x180024f5e  lea     r8, asc_1800569F0; " "
0x180024f65  mov     rcx, r15; unsigned __int16 *
0x180024f68  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180024f6d  mov     edx, [r12]; unsigned __int64
0x180024f71  mov     rcx, r15; unsigned __int16 *
0x180024f74  mov     r8, [rbp+57h+var_98]; unsigned __int16 *
0x180024f78  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180024f7d  mov     rcx, [rbp+57h+pv]; pv
0x180024f81  call    cs:__imp_CoTaskMemFree
0x180024f88  nop     dword ptr [rax+rax+00h]
0x180024f8d  mov     rcx, [rbp+57h+var_98]; pv
0x180024f91  call    cs:__imp_CoTaskMemFree
0x180024f98  nop     dword ptr [rax+rax+00h]
0x180024f9d  movzx   r10d, word ptr [rsi+20h]
0x180024fa2  mov     r14d, 1
0x180024fa8  movzx   eax, r10w
0x180024fac  sub     ax, r14w
0x180024fb0  cmp     ax, r14w
0x180024fb4  ja      loc_180025208
0x180024fba  xor     edx, edx; unsigned __int16
0x180024fbc  mov     rcx, rsi; this
0x180024fbf  call    ?_GetTrigger@CJob@@AEAAPEAU_TASK_TRIGGER@@G@Z; CJob::_GetTrigger(ushort)
0x180024fc4  mov     rbx, rax
0x180024fc7  test    rax, rax
0x180024fca  jz      loc_180025208
0x180024fd0  movzx   ecx, word ptr [rax+10h]
0x180024fd4  lea     r15d, [r14+1]
0x180024fd8  imul    edx, ecx, 3Ch ; '<'
0x180024fdb  movzx   ecx, word ptr [rax+12h]
0x180024fdf  mov     [rdi+0Ch], r13b
0x180024fe3  mov     [rdi+8], r13d
0x180024fe7  add     edx, ecx
0x180024fe9  imul    ecx, edx, 0EA60h
0x180024fef  movsxd  rdx, ecx
0x180024ff2  mov     [rdi], rdx
0x180024ff5  mov     ecx, [rax+20h]
0x180024ff8  test    ecx, ecx
0x180024ffa  jz      short loc_180025055
0x180024ffc  sub     ecx, r15d
0x180024fff  jz      short loc_180025040
0x180025001  cmp     ecx, r14d
0x180025004  jnz     loc_180025208
0x18002500a  mov     eax, [rax+24h]
0x18002500d  mov     [rdi+8], eax
0x180025010  jmp     short loc_180025055
0x180025012  mov     r8, rcx; unsigned __int16 *
0x180025015  mov     rcx, r15; unsigned __int16 *
0x180025018  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002501d  mov     ebx, eax
0x18002501f  test    eax, eax
0x180025021  jns     loc_180024F55
0x180025027  mov     rcx, [rbp+57h+pv]; pv
0x18002502b  call    cs:__imp_CoTaskMemFree
0x180025032  nop     dword ptr [rax+rax+00h]
0x180025037  mov     rcx, [rbp+57h+var_98]
0x18002503b  jmp     loc_180024E90
0x180025040  movzx   eax, word ptr [rax+26h]
0x180025044  shr     ax, 1
0x180025047  mov     [rdi+0Ch], al
0x18002504a  test    [rbx+26h], r14b
0x18002504e  jz      short loc_180025055
0x180025050  or      al, 40h
0x180025052  mov     [rdi+0Ch], al
0x180025055  cmp     r10w, r15w
0x180025059  jnz     short loc_18002509E
0x18002505b  mov     edx, r14d; unsigned __int16
0x18002505e  mov     rcx, rsi; this
0x180025061  call    ?_GetTrigger@CJob@@AEAAPEAU_TASK_TRIGGER@@G@Z; CJob::_GetTrigger(ushort)
0x180025066  mov     rbx, rax
0x180025069  mov     ecx, [rax+20h]
0x18002506c  test    ecx, ecx
0x18002506e  jz      loc_180025208
0x180025074  sub     ecx, r15d
0x180025077  jz      short loc_180025089
0x180025079  cmp     ecx, edx
0x18002507b  jnz     loc_180025208
0x180025081  mov     eax, [rax+24h]
0x180025084  mov     [rdi+8], eax
0x180025087  jmp     short loc_18002509E
0x180025089  movzx   eax, word ptr [rax+26h]
0x18002508d  shr     ax, 1
0x180025090  mov     [rdi+0Ch], al
0x180025093  test    [rbx+26h], r14b
0x180025097  jz      short loc_18002509E
0x180025099  or      al, 40h
0x18002509b  mov     [rdi+0Ch], al
0x18002509e  mov     [rdi+0Dh], r13b
0x1800250a2  mov     al, r13b
0x1800250a5  test    [rsi+58h], r14b
0x1800250a9  jnz     short loc_1800250B0
0x1800250ab  mov     al, 10h
0x1800250ad  mov     [rdi+0Dh], al
0x1800250b0  test    [rbx+1Ch], r14b
0x1800250b4  jnz     short loc_1800250C2
0x1800250b6  cmp     [rbx+20h], r13d
0x1800250ba  jz      short loc_1800250C2
0x1800250bc  or      al, r14b
0x1800250bf  mov     [rdi+0Dh], al
0x1800250c2  xorps   xmm0, xmm0
0x1800250c5  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800250c9  xorps   xmm1, xmm1
0x1800250cc  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800250d0  movups  xmmword ptr [rbp+57h+var_80.wYear], xmm1
0x1800250d4  movups  xmmword ptr [rbp+57h+var_60.wYear], xmm0
0x1800250d8  call    cs:__imp_GetLocalTime
0x1800250df  nop     dword ptr [rax+rax+00h]
0x1800250e4  movaps  xmm0, xmmword ptr [rbp+57h+SystemTime.wYear]
0x1800250e8  lea     rcx, [rbp+57h+var_80]; struct _SYSTEMTIME *
0x1800250ec  movdqa  xmmword ptr [rbp+57h+var_80.wYear], xmm0
0x1800250f1  mov     qword ptr [rbp+57h+var_80.wHour], r13
0x1800250f5  mov     [rbp+57h+var_B0], r13w
0x1800250fa  call    ?IncrementDay@@YAXPEAU_SYSTEMTIME@@@Z; IncrementDay(_SYSTEMTIME *)
0x1800250ff  lea     r9, [rbp+57h+var_B0]; unsigned __int16 *
0x180025103  mov     [rsp+0F0h+var_C8], r13; struct CTimeRunList *
0x180025108  lea     r8, [rbp+57h+var_80]; struct _SYSTEMTIME *
0x18002510c  mov     [rbp+57h+var_B0], r13w
0x180025111  lea     rdx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x180025115  mov     [rsp+0F0h+var_D0], r14w; unsigned __int16
0x18002511b  mov     rcx, rsi; this
0x18002511e  call    ?GetRunTimesP@CJob@@QEAAJPEBU_SYSTEMTIME@@0PEAGGPEAVCTimeRunList@@1@Z; CJob::GetRunTimesP(_SYSTEMTIME const *,_SYSTEMTIME const *,ushort *,ushort,CTimeRunList *,ushort *)
0x180025123  test    eax, eax
0x180025125  js      loc_18002520D
0x18002512b  cmp     [rbp+57h+var_B0], r13w
0x180025130  jbe     short loc_180025136
0x180025132  or      byte ptr [rdi+0Dh], 4
0x180025136  test    dword ptr [rsi+58h], 180000h
0x18002513d  jz      short loc_180025143
0x18002513f  or      [rdi+0Dh], r15b
0x180025143  cmp     [rbx+20h], r13d
0x180025147  jnz     short loc_1800251B6
0x180025149  test    [rdi+0Dh], r15b
0x18002514d  jnz     short loc_1800251B6
0x18002514f  movaps  xmm0, xmmword ptr [rbp+57h+SystemTime.wYear]
0x180025153  lea     rcx, [rbp+57h+var_60]; struct _SYSTEMTIME *
0x180025157  movdqa  xmmword ptr [rbp+57h+var_60.wYear], xmm0
0x18002515c  call    ?IncrementDay@@YAXPEAU_SYSTEMTIME@@@Z; IncrementDay(_SYSTEMTIME *)
0x180025161  lea     r9, [rbp+57h+var_B0]; unsigned __int16 *
0x180025165  mov     [rsp+0F0h+var_C8], r13; struct CTimeRunList *
0x18002516a  lea     r8, [rbp+57h+var_60]; struct _SYSTEMTIME *
0x18002516e  mov     [rsp+0F0h+var_D0], r14w; unsigned __int16
0x180025174  lea     rdx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x180025178  mov     rcx, rsi; this
0x18002517b  call    ?GetRunTimesP@CJob@@QEAAJPEBU_SYSTEMTIME@@0PEAGGPEAVCTimeRunList@@1@Z; CJob::GetRunTimesP(_SYSTEMTIME const *,_SYSTEMTIME const *,ushort *,ushort,CTimeRunList *,ushort *)
0x180025180  test    eax, eax
0x180025182  js      loc_18002520D
0x180025188  mov     rax, [rsi]
0x18002518b  lea     rdx, [rbp+57h+var_A0]
0x18002518f  mov     rcx, rsi
0x180025192  mov     [rbp+57h+var_A0], r13d
0x180025196  mov     rax, [rax+80h]
0x18002519d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251a2  cmp     [rbp+57h+var_B0], r13w
0x1800251a7  jnz     short loc_1800251B6
0x1800251a9  cmp     [rbp+57h+var_A0], 41301h
0x1800251b0  jnz     short loc_180025208
0x1800251b2  or      byte ptr [rdi+0Dh], 4
0x1800251b6  test    [rbx+1Ch], r14b
0x1800251ba  jz      short loc_180025204
0x1800251bc  movzx   eax, word ptr [rbx+0Ah]
0x1800251c0  lea     rdx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x1800251c4  mov     [rbp+57h+var_90.wYear], ax
0x1800251c8  lea     rcx, [rbp+57h+var_90]; struct _SYSTEMTIME *
0x1800251cc  movzx   eax, word ptr [rbx+0Ch]
0x1800251d0  mov     [rbp+57h+var_90.wMonth], ax
0x1800251d4  movzx   eax, word ptr [rbx+0Eh]
0x1800251d8  mov     [rbp+57h+var_90.wDay], ax
0x1800251dc  movzx   eax, word ptr [rbx+10h]
0x1800251e0  mov     [rbp+57h+var_90.wHour], ax
0x1800251e4  movzx   eax, word ptr [rbx+12h]
0x1800251e8  mov     [rbp+57h+var_90.wMinute], ax
0x1800251ec  mov     [rbp+57h+var_90.wDayOfWeek], r13w
0x1800251f1  mov     dword ptr [rbp+57h+var_90.wSecond], r13d
0x1800251f5  call    ?IsFirstTimeEarlier@@YAHPEBU_SYSTEMTIME@@0@Z; IsFirstTimeEarlier(_SYSTEMTIME const *,_SYSTEMTIME const *)
0x1800251fa  test    eax, eax
0x1800251fc  jz      short loc_180025204
0x1800251fe  test    [rdi+0Dh], r15b
0x180025202  jz      short loc_180025208
0x180025204  xor     eax, eax
0x180025206  jmp     short loc_18002520D
0x180025208  mov     eax, 80004005h
0x18002520d  mov     rcx, [rbp+57h+var_50]
0x180025211  xor     rcx, rsp; StackCookie
0x180025214  call    __security_check_cookie
0x180025219  add     rsp, 0B8h
0x180025220  pop     r15
0x180025222  pop     r14
0x180025224  pop     r13
0x180025226  pop     r12
0x180025228  pop     rdi
0x180025229  pop     rsi
0x18002522a  pop     rbx
0x18002522b  pop     rbp
0x18002522c  retn
```
