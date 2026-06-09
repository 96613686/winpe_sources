# EventXmlDump::ProcessHeader(EventDumpWorkspace *)

- ea: `0x140011120`
- end: `0x140011607`
- name: `?ProcessHeader@EventXmlDump@@UEAAKPEAVEventDumpWorkspace@@@Z`
- size: `1255`
- prototype: `unsigned int(EventXmlDump *__hidden this, struct EventDumpWorkspace *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x14000efcc`
- `0x140011120`
- `0x140011728`
- `0x140011d94`
- `0x140032488`
- `0x140040130`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011584`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011584`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011531`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011576`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011531`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011576`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140011541`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140011541`
- `api-ms-win-eventing-tdh-l1-1-0!TdhQueryProviderFieldInformation` at `0x140011523`
- `api-ms-win-eventing-tdh-l1-1-0!TdhQueryProviderFieldInformation` at `0x140011567`
- `api-ms-win-eventing-tdh-l1-1-0!TdhQueryProviderFieldInformation` at `0x140011523`
- `api-ms-win-eventing-tdh-l1-1-0!TdhQueryProviderFieldInformation` at `0x140011567`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400113d1`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400113d1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x140011404`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x140011404`

## pseudocode

```c
__int64 __fastcall EventXmlDump::ProcessHeader(EventXmlDump *this, struct EventDumpWorkspace *a2)
{
  __int64 v2; // r14
  struct _GUID *v5; // r15
  unsigned int v6; // r9d
  __int64 v7; // rcx
  __int16 v8; // ax
  __int64 v9; // r8
  __int64 v10; // rax
  unsigned __int64 v11; // rcx
  const wchar_t *v12; // rax
  unsigned int v13; // r9d
  BOOL v14; // eax
  bool v15; // cl
  __int64 v16; // rcx
  unsigned __int16 *v17; // rdx
  __int64 v18; // rcx
  unsigned __int16 *v19; // rdx
  char *v20; // rbx
  __int64 v21; // rcx
  ULONGLONG v22; // rdx
  PROVIDER_FIELD_INFOARRAY *v23; // rbx
  TDHSTATUS v24; // eax
  ULONG v25; // ebx
  HANDLE ProcessHeap; // rax
  HANDLE v27; // rax
  ULONG pBufferSize; // [rsp+30h] [rbp-40h] BYREF
  FILETIME FileTime; // [rsp+38h] [rbp-38h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-30h] BYREF
  struct _SYSTEMTIME LocalTime; // [rsp+50h] [rbp-20h] BYREF

  v2 = *(_QWORD *)a2;
  v5 = 0;
  v6 = 0;
  if ( *(_WORD *)(*(_QWORD *)a2 + 84LL) )
  {
    do
    {
      v7 = *(_QWORD *)(v2 + 88);
      v8 = *(_WORD *)(v7 + 16LL * v6 + 2);
      switch ( v8 )
      {
        case 1:
          v5 = *(struct _GUID **)(v7 + 16LL * v6 + 8);
          break;
        case 2:
          *((_QWORD *)this + 124) = *(_QWORD *)(v7 + 16LL * v6 + 8);
          break;
        case 3:
          *((_QWORD *)this + 121) = *(_QWORD *)(v7 + 16LL * v6 + 8);
          break;
        case 4:
          *((_QWORD *)this + 133) = *(_QWORD *)(v7 + 16LL * v6 + 8);
          break;
        case 5:
          if ( *(_WORD *)(v7 + 16LL * v6 + 6) >= 8u )
          {
            *((_QWORD *)this + 129) = **(_QWORD **)(v7 + 16LL * v6 + 8);
            *((_QWORD *)this + 126) = *(_QWORD *)(*(_QWORD *)(v2 + 88) + 16LL * v6 + 8) + 8LL;
            v11 = ((unsigned __int64)*(unsigned __int16 *)(*(_QWORD *)(v2 + 88) + 16LL * v6 + 6) - 8) >> 2;
LABEL_18:
            *((_DWORD *)this + 256) = v11;
          }
          break;
        case 6:
          if ( *(_WORD *)(v7 + 16LL * v6 + 6) >= 8u )
          {
            *((_QWORD *)this + 129) = **(_QWORD **)(v7 + 16LL * v6 + 8);
            *((_QWORD *)this + 127) = *(_QWORD *)(*(_QWORD *)(v2 + 88) + 16LL * v6 + 8) + 8LL;
            v11 = ((unsigned __int64)*(unsigned __int16 *)(*(_QWORD *)(v2 + 88) + 16LL * v6 + 6) - 8) >> 3;
            goto LABEL_18;
          }
          break;
        default:
          switch ( v8 )
          {
            case 7:
              *((_QWORD *)this + 130) = *(_QWORD *)(v7 + 16LL * v6 + 8);
              break;
            case 8:
              *((_QWORD *)this + 131) = *(_QWORD *)(v7 + 16LL * v6 + 8);
              *((_DWORD *)this + 264) = *(unsigned __int16 *)(*(_QWORD *)(v2 + 88) + 16LL * v6 + 6) >> 3;
              break;
            case 9:
              if ( *(_WORD *)(v7 + 16LL * v6 + 6) )
                v12 = *(const wchar_t **)(v7 + 16LL * v6 + 8);
              else
                v12 = &Ext;
              *((_QWORD *)this + 125) = v12;
              break;
          }
          break;
      }
      ++v6;
    }
    while ( v6 < *(unsigned __int16 *)(v2 + 84) );
  }
  v9 = *((_QWORD *)a2 + 1);
  if ( v9 )
  {
    if ( *(_DWORD *)(v9 + 48) != 1 )
    {
      if ( *(_DWORD *)(v9 + 52) )
        v10 = v9 + *(unsigned int *)(v9 + 52);
      else
        v10 = 0;
      *((_QWORD *)this + 2) = v10;
      v9 = *((_QWORD *)a2 + 1);
    }
  }
  else
  {
    v9 = 0;
  }
  if ( (*(_BYTE *)(v2 + 4) & 8) == 0 )
  {
    if ( (*(_BYTE *)(v2 + 4) & 4) != 0 || (*(_WORD *)(v2 + 4) & 0x100) == 0 )
      v9 = v2 + 24;
    if ( v9 )
    {
      CpdiGuidToString((unsigned __int16 *)this + 12, 0x80u, (struct _GUID *)v9);
      *((_QWORD *)this + 35) = (char *)this + 24;
    }
  }
  FileTime = 0;
  SystemTime = 0;
  if ( (*((_DWORD *)g_TraceContext + 1604) & 0x1000) != 0 )
  {
    CalculateTimeStamp((union _LARGE_INTEGER *)&FileTime, (union _LARGE_INTEGER *)(v2 + 16));
  }
  else
  {
    FileTime = *(FILETIME *)(v2 + 16);
    if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
    {
      LocalTime = 0;
      if ( (*((_DWORD *)g_TraceContext + 1604) & 0x12000000) != 0 )
      {
        v15 = 1;
        LocalTime = SystemTime;
      }
      else
      {
        v14 = SystemTimeToTzSpecificLocalTime(
                (const TIME_ZONE_INFORMATION *)((char *)this + 1072),
                &SystemTime,
                &LocalTime);
        v15 = 0;
        if ( !v14 )
          goto LABEL_49;
      }
      if ( SystemTime.wMonth <= 0xCu )
      {
        FormatDateTimeString(
          &LocalTime,
          (const union _LARGE_INTEGER *)&FileTime,
          (unsigned __int16 *)this + 144,
          v13,
          v15);
        *((_DWORD *)this + 104) = 1;
      }
    }
  }
LABEL_49:
  v16 = *((_QWORD *)a2 + 1);
  if ( v16 && *(_DWORD *)(v16 + 92) )
  {
    v17 = (unsigned __int16 *)(v16 + *(unsigned int *)(v16 + 92));
    *((_QWORD *)this + 53) = v17;
    EventDumpWorkspace::RegisterPropertyHandler(
      a2,
      v17,
      (struct IEventDumpPropertyHandler *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)));
  }
  CpdiGuidToString((unsigned __int16 *)this + 220, 0x80u, (struct _GUID *)(v2 + 64));
  *((_QWORD *)this + 54) = (char *)this + 440;
  v18 = *((_QWORD *)a2 + 1);
  if ( v18 && *(_DWORD *)(v18 + 96) )
  {
    v19 = (unsigned __int16 *)(v18 + *(unsigned int *)(v18 + 96));
    *((_QWORD *)this + 87) = v19;
    EventDumpWorkspace::RegisterPropertyHandler(
      a2,
      v19,
      (struct IEventDumpPropertyHandler *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)));
  }
  else if ( v5 )
  {
    v20 = (char *)this + 712;
    CpdiGuidToString((unsigned __int16 *)this + 356, 0x80u, v5);
    goto LABEL_56;
  }
  v20 = 0;
LABEL_56:
  *((_QWORD *)this + 88) = v20;
  v21 = *((_QWORD *)a2 + 1);
  if ( v21 && *(_DWORD *)(v21 + 60) && *(unsigned int *)(v21 + 60) + v21 )
  {
    v22 = *(unsigned __int8 *)(v2 + 43);
    pBufferSize = 0;
    v23 = 0;
    v24 = TdhQueryProviderFieldInformation((LPGUID)(v2 + 24), v22, EventChannelInformation, 0, &pBufferSize);
    if ( v24 == 122 )
    {
      v25 = pBufferSize;
      ProcessHeap = GetProcessHeap();
      v23 = (PROVIDER_FIELD_INFOARRAY *)HeapAlloc(ProcessHeap, 8u, v25);
      if ( !v23 )
        goto LABEL_65;
      v24 = TdhQueryProviderFieldInformation(
              (LPGUID)(v2 + 24),
              *(unsigned __int8 *)(v2 + 43),
              EventChannelInformation,
              v23,
              &pBufferSize);
    }
    if ( v24 )
    {
      if ( v23 )
      {
LABEL_64:
        v27 = GetProcessHeap();
        HeapFree(v27, 0, v23);
      }
LABEL_65:
      *((_QWORD *)this + 122) = 0;
      return 0;
    }
    if ( !v23->NumberOfElements || !v23->FieldInfoArray[0].NameOffset && !v23->FieldInfoArray[0].DescriptionOffset )
      goto LABEL_64;
    *((_QWORD *)this + 123) = v23;
    if ( v23->FieldInfoArray[0].NameOffset )
      *((_QWORD *)this + 122) = (char *)v23 + v23->FieldInfoArray[0].NameOffset;
  }
  return 0;
}

```

## disassembly

```asm
0x140011120  mov     [rsp-38h+arg_10], rbx
0x140011125  push    rbp
0x140011126  push    rsi
0x140011127  push    rdi
0x140011128  push    r12
0x14001112a  push    r13
0x14001112c  push    r14
0x14001112e  push    r15
0x140011130  mov     rbp, rsp
0x140011133  sub     rsp, 70h
0x140011137  mov     rax, cs:__security_cookie
0x14001113e  xor     rax, rsp
0x140011141  mov     [rbp+var_10], rax
0x140011145  mov     r14, [rdx]
0x140011148  xor     r12d, r12d
0x14001114b  mov     rdi, rcx
0x14001114e  mov     rsi, rdx
0x140011151  mov     r15d, r12d
0x140011154  mov     r9d, r12d
0x140011157  lea     ebx, [r12+1]
0x14001115c  lea     ecx, [rbx+3]
0x14001115f  lea     r10d, [r12+2]
0x140011164  lea     r11d, [r12+8]
0x140011169  cmp     r12w, [r14+54h]
0x14001116e  jnb     short loc_1400111D5
0x140011170  mov     r13d, ecx
0x140011173  mov     rcx, [r14+58h]
0x140011177  mov     edx, r9d
0x14001117a  add     rdx, rdx
0x14001117d  mov     r8d, r9d
0x140011180  movzx   eax, word ptr [rcx+rdx*8+2]
0x140011185  cmp     bx, ax
0x140011188  jnz     short loc_140011191
0x14001118a  mov     r15, [rcx+rdx*8+8]
0x14001118f  jmp     short loc_1400111C3
0x140011191  cmp     r10w, ax
0x140011195  jnz     short loc_1400111A5
0x140011197  mov     rax, [rcx+rdx*8+8]
0x14001119c  mov     [rdi+3E0h], rax
0x1400111a3  jmp     short loc_1400111C3
0x1400111a5  mov     r10d, 3
0x1400111ab  cmp     r10w, ax
0x1400111af  jnz     short loc_1400111FE
0x1400111b1  mov     rax, [rcx+rdx*8+8]
0x1400111b6  mov     [rdi+3C8h], rax
0x1400111bd  mov     r10d, 2
0x1400111c3  movzx   eax, word ptr [r14+54h]
0x1400111c8  add     r9d, ebx
0x1400111cb  cmp     r9d, eax
0x1400111ce  jb      short loc_140011173
0x1400111d0  mov     ecx, 4
0x1400111d5  mov     r8, [rsi+8]
0x1400111d9  test    r8, r8
0x1400111dc  jz      loc_140011353
0x1400111e2  cmp     [r8+30h], ebx
0x1400111e6  jz      loc_140011356
0x1400111ec  cmp     [r8+34h], r12d
0x1400111f0  jnz     loc_140011342
0x1400111f6  mov     rax, r12
0x1400111f9  jmp     loc_140011349
0x1400111fe  cmp     r13w, ax
0x140011202  jnz     short loc_140011212
0x140011204  mov     rax, [rcx+rdx*8+8]
0x140011209  mov     [rdi+428h], rax
0x140011210  jmp     short loc_1400111BD
0x140011212  mov     r10d, 5
0x140011218  cmp     r10w, ax
0x14001121c  jnz     short loc_140011269
0x14001121e  mov     r10d, 2
0x140011224  cmp     [rcx+rdx*8+6], r11w
0x14001122a  jb      short loc_1400111C3
0x14001122c  mov     rax, [rcx+rdx*8+8]
0x140011231  mov     rcx, [rax]
0x140011234  mov     [rdi+408h], rcx
0x14001123b  mov     rax, [r14+58h]
0x14001123f  mov     rcx, [rax+rdx*8+8]
0x140011244  add     rcx, r11
0x140011247  mov     [rdi+3F0h], rcx
0x14001124e  mov     rax, [r14+58h]
0x140011252  movzx   ecx, word ptr [rax+rdx*8+6]
0x140011257  sub     rcx, r11
0x14001125a  shr     rcx, 2
0x14001125e  mov     [rdi+400h], ecx
0x140011264  jmp     loc_1400111C3
0x140011269  mov     r10d, 6
0x14001126f  cmp     r10w, ax
0x140011273  jnz     short loc_1400112BB
0x140011275  mov     r10d, 2
0x14001127b  cmp     [rcx+rdx*8+6], r11w
0x140011281  jb      loc_1400111C3
0x140011287  mov     rax, [rcx+rdx*8+8]
0x14001128c  mov     rcx, [rax]
0x14001128f  mov     [rdi+408h], rcx
0x140011296  mov     rax, [r14+58h]
0x14001129a  mov     rcx, [rax+rdx*8+8]
0x14001129f  add     rcx, r11
0x1400112a2  mov     [rdi+3F8h], rcx
0x1400112a9  mov     rax, [r14+58h]
0x1400112ad  movzx   ecx, word ptr [rax+rdx*8+6]
0x1400112b2  sub     rcx, r11
0x1400112b5  shr     rcx, 3
0x1400112b9  jmp     short loc_14001125E
0x1400112bb  mov     r10d, 7
0x1400112c1  cmp     r10w, ax
0x1400112c5  jnz     short loc_1400112D8
0x1400112c7  mov     rax, [rcx+rdx*8+8]
0x1400112cc  mov     [rdi+410h], rax
0x1400112d3  jmp     loc_1400111BD
0x1400112d8  cmp     r11w, ax
0x1400112dc  jnz     short loc_140011305
0x1400112de  add     r8, r8
0x1400112e1  mov     rax, [rcx+r8*8+8]
0x1400112e6  mov     [rdi+418h], rax
0x1400112ed  mov     rax, [r14+58h]
0x1400112f1  movzx   ecx, word ptr [rax+r8*8+6]
0x1400112f7  shr     ecx, 3
0x1400112fa  mov     [rdi+420h], ecx
0x140011300  jmp     loc_1400111BD
0x140011305  mov     edx, 9
0x14001130a  cmp     dx, ax
0x14001130d  jnz     loc_1400111BD
0x140011313  mov     rax, r8
0x140011316  lea     r10d, [rdx-7]
0x14001131a  add     rax, rax
0x14001131d  cmp     [rcx+rax*8+6], r12w
0x140011323  jbe     short loc_140011339
0x140011325  add     r8, r8
0x140011328  mov     rax, [rcx+r8*8+8]
0x14001132d  mov     [rdi+3E8h], rax
0x140011334  jmp     loc_1400111C3
0x140011339  lea     rax, Ext
0x140011340  jmp     short loc_14001132D
0x140011342  mov     eax, [r8+34h]
0x140011346  add     rax, r8
0x140011349  mov     [rdi+10h], rax
0x14001134d  mov     r8, [rsi+8]
0x140011351  jmp     short loc_140011356
0x140011353  mov     r8, r12
0x140011356  mov     r13d, 80h
0x14001135c  test    [r14+4], r11b
0x140011360  jnz     short loc_140011398
0x140011362  test    [r14+4], cl
0x140011366  jnz     short loc_140011374
0x140011368  mov     eax, 100h
0x14001136d  test    [r14+4], ax
0x140011372  jnz     short loc_140011378
0x140011374  lea     r8, [r14+18h]; struct _GUID *
0x140011378  test    r8, r8
0x14001137b  jz      short loc_140011398
0x14001137d  lea     rbx, [rdi+18h]
0x140011381  mov     edx, r13d; unsigned int
0x140011384  mov     rcx, rbx; unsigned __int16 *
0x140011387  call    ?CpdiGuidToString@@YAPEAGPEAGKPEAU_GUID@@@Z; CpdiGuidToString(ushort *,ulong,_GUID *)
0x14001138c  mov     [rdi+118h], rbx
0x140011393  mov     ebx, 1
0x140011398  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x14001139f  lea     rcx, [rbp+FileTime]; union _LARGE_INTEGER *
0x1400113a3  xorps   xmm0, xmm0
0x1400113a6  mov     qword ptr [rbp+FileTime.dwLowDateTime], r12
0x1400113aa  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1400113ae  test    dword ptr [rax+1910h], 1000h
0x1400113b8  jz      short loc_1400113C5
0x1400113ba  lea     rdx, [r14+10h]; union _LARGE_INTEGER *
0x1400113be  call    ?CalculateTimeStamp@@YAXPEAT_LARGE_INTEGER@@0@Z; CalculateTimeStamp(_LARGE_INTEGER *,_LARGE_INTEGER *)
0x1400113c3  jmp     short loc_140011443
0x1400113c5  mov     rax, [r14+10h]
0x1400113c9  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x1400113cd  mov     qword ptr [rbp+FileTime.dwLowDateTime], rax
0x1400113d1  call    cs:__imp_FileTimeToSystemTime
0x1400113d7  test    eax, eax
0x1400113d9  jz      short loc_140011443
0x1400113db  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x1400113e2  xorps   xmm0, xmm0
0x1400113e5  movups  xmmword ptr [rbp+LocalTime.wYear], xmm0
0x1400113e9  test    dword ptr [rax+1910h], 12000000h
0x1400113f3  jnz     short loc_140011413
0x1400113f5  lea     rcx, [rdi+430h]; lpTimeZoneInformation
0x1400113fc  lea     r8, [rbp+LocalTime]; lpLocalTime
0x140011400  lea     rdx, [rbp+SystemTime]; lpUniversalTime
0x140011404  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x14001140a  mov     cl, r12b
0x14001140d  test    eax, eax
0x14001140f  jz      short loc_140011443
0x140011411  jmp     short loc_14001141E
0x140011413  movaps  xmm0, xmmword ptr [rbp+SystemTime.wYear]
0x140011417  mov     cl, bl
0x140011419  movdqa  xmmword ptr [rbp+LocalTime.wYear], xmm0
0x14001141e  cmp     [rbp+SystemTime.wMonth], 0Ch
0x140011423  ja      short loc_140011443
0x140011425  mov     byte ptr [rsp+70h+pBufferSize], cl; bool
0x140011429  lea     r8, [rdi+120h]; unsigned __int16 *
0x140011430  lea     rcx, [rbp+LocalTime]; lpSystemTime
0x140011434  lea     rdx, [rbp+FileTime]; union _LARGE_INTEGER *
0x140011438  call    ?FormatDateTimeString@@YAXPEBU_SYSTEMTIME@@PEBT_LARGE_INTEGER@@PEAGK_N@Z; FormatDateTimeString(_SYSTEMTIME const *,_LARGE_INTEGER const *,ushort *,ulong,bool)
0x14001143d  mov     [rdi+1A0h], ebx
0x140011443  mov     rcx, [rsi+8]
0x140011447  test    rcx, rcx
0x14001144a  jz      short loc_140011477
0x14001144c  cmp     [rcx+5Ch], r12d
0x140011450  jbe     short loc_140011477
0x140011452  mov     edx, [rcx+5Ch]
0x140011455  mov     rax, rdi
0x140011458  add     rdx, rcx; unsigned __int16 *
0x14001145b  lea     rcx, [rdi+8]
0x14001145f  neg     rax
0x140011462  mov     [rdi+1A8h], rdx
0x140011469  sbb     r8, r8
0x14001146c  and     r8, rcx; struct IEventDumpPropertyHandler *
0x14001146f  mov     rcx, rsi; this
0x140011472  call    ?RegisterPropertyHandler@EventDumpWorkspace@@QEAAKPEAGPEAVIEventDumpPropertyHandler@@@Z; EventDumpWorkspace::RegisterPropertyHandler(ushort *,IEventDumpPropertyHandler *)
0x140011477  lea     rbx, [rdi+1B8h]
0x14001147e  mov     edx, r13d; unsigned int
0x140011481  mov     rcx, rbx; unsigned __int16 *
0x140011484  lea     r8, [r14+40h]; struct _GUID *
0x140011488  call    ?CpdiGuidToString@@YAPEAGPEAGKPEAU_GUID@@@Z; CpdiGuidToString(ushort *,ulong,_GUID *)
0x14001148d  mov     [rdi+1B0h], rbx
0x140011494  mov     rcx, [rsi+8]
0x140011498  test    rcx, rcx
0x14001149b  jz      loc_1400115B7
0x1400114a1  cmp     [rcx+60h], r12d
0x1400114a5  jbe     loc_1400115B7
0x1400114ab  mov     edx, [rcx+60h]
0x1400114ae  mov     rax, rdi
0x1400114b1  add     rdx, rcx; unsigned __int16 *
0x1400114b4  lea     rcx, [rdi+8]
0x1400114b8  neg     rax
0x1400114bb  mov     [rdi+2B8h], rdx
0x1400114c2  sbb     r8, r8
0x1400114c5  and     r8, rcx; struct IEventDumpPropertyHandler *
0x1400114c8  mov     rcx, rsi; this
0x1400114cb  call    ?RegisterPropertyHandler@EventDumpWorkspace@@QEAAKPEAGPEAVIEventDumpPropertyHandler@@@Z; EventDumpWorkspace::RegisterPropertyHandler(ushort *,IEventDumpPropertyHandler *)
0x1400114d0  mov     rbx, r12
0x1400114d3  mov     rax, rdi
0x1400114d6  mov     [rax+2C0h], rbx
0x1400114dd  mov     rcx, [rsi+8]
0x1400114e1  test    rcx, rcx
0x1400114e4  jz      loc_140011591
0x1400114ea  cmp     [rcx+3Ch], r12d
0x1400114ee  jz      loc_140011591
0x1400114f4  mov     eax, [rcx+3Ch]
0x1400114f7  add     rcx, rax
0x1400114fa  jz      loc_140011591
0x140011500  movzx   edx, byte ptr [r14+2Bh]; EventFieldValue
0x140011505  lea     rax, [rbp+var_40]
0x140011509  xor     r9d, r9d; pBuffer
0x14001150c  mov     [rbp+var_40], r12d
0x140011510  lea     rcx, [r14+18h]; pGuid
0x140011514  mov     [rsp+70h+pBufferSize], rax; pBufferSize
0x140011519  mov     rbx, r12
0x14001151c  lea     r15d, [r9+2]
0x140011520  mov     r8d, r15d; EventFieldType
0x140011523  call    cs:__imp_TdhQueryProviderFieldInformation
0x140011529  cmp     eax, 7Ah ; 'z'
0x14001152c  jnz     short loc_14001156D
0x14001152e  mov     ebx, [rbp+var_40]
0x140011531  call    cs:__imp_GetProcessHeap
0x140011537  mov     r8d, ebx; dwBytes
0x14001153a  lea     edx, [r15+6]; dwFlags
0x14001153e  mov     rcx, rax; hHeap
0x140011541  call    cs:__imp_HeapAlloc
0x140011547  mov     rbx, rax
0x14001154a  test    rax, rax
0x14001154d  jz      short loc_14001158A
0x14001154f  movzx   edx, byte ptr [r14+2Bh]; EventFieldValue
0x140011554  lea     rax, [rbp+var_40]
0x140011558  mov     r9, rbx; pBuffer
0x14001155b  mov     [rsp+70h+pBufferSize], rax; pBufferSize
0x140011560  mov     r8d, r15d; EventFieldType
0x140011563  lea     rcx, [r14+18h]; pGuid
0x140011567  call    cs:__imp_TdhQueryProviderFieldInformation
0x14001156d  test    eax, eax
0x14001156f  jz      short loc_1400115DA
0x140011571  test    rbx, rbx
0x140011574  jz      short loc_14001158A
0x140011576  call    cs:__imp_GetProcessHeap
0x14001157c  mov     r8, rbx; lpMem
0x14001157f  xor     edx, edx; dwFlags
0x140011581  mov     rcx, rax; hHeap
0x140011584  call    cs:__imp_HeapFree
0x14001158a  mov     [rdi+3D0h], r12
0x140011591  xor     eax, eax
0x140011593  mov     rcx, [rbp+var_10]
0x140011597  xor     rcx, rsp; StackCookie
0x14001159a  call    __security_check_cookie
0x14001159f  mov     rbx, [rsp+70h+arg_10]
0x1400115a7  add     rsp, 70h
0x1400115ab  pop     r15
0x1400115ad  pop     r14
0x1400115af  pop     r13
0x1400115b1  pop     r12
0x1400115b3  pop     rdi
0x1400115b4  pop     rsi
0x1400115b5  pop     rbp
0x1400115b6  retn
0x1400115b7  test    r15, r15
0x1400115ba  jz      loc_1400114D0
0x1400115c0  lea     rbx, [rdi+2C8h]
0x1400115c7  mov     r8, r15; struct _GUID *
0x1400115ca  mov     rcx, rbx; unsigned __int16 *
0x1400115cd  mov     edx, r13d; unsigned int
  ... truncated ...
```
