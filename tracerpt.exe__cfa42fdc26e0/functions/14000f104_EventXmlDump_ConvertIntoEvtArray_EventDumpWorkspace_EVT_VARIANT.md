# EventXmlDump::ConvertIntoEvtArray(EventDumpWorkspace *,_EVT_VARIANT *)

- ea: `0x14000f104`
- end: `0x14000f6ea`
- name: `?ConvertIntoEvtArray@EventXmlDump@@QEAAKPEAVEventDumpWorkspace@@PEAU_EVT_VARIANT@@@Z`
- size: `1510`
- prototype: `__int64 __fastcall(EventXmlDump *this, struct EventDumpWorkspace *, struct _EVT_VARIANT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000fd88`

## callees

- `0x14000d738`
- `0x14000d818`
- `0x14000d96c`
- `0x14000e088`
- `0x14000e214`
- `0x14000f104`
- `0x14000f6f0`
- `0x14000f88c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f565`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f565`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f1b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f290`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f368`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f3b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f47d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f557`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f60d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f1b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f290`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f368`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f3b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f47d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f557`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f60d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f1c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f29f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f378`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f3c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f490`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f61d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f1c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f29f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f378`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f3c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f490`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f61d`

## pseudocode

```c
__int64 __fastcall EventXmlDump::ConvertIntoEvtArray(
        EventXmlDump *this,
        struct EventDumpWorkspace *a2,
        struct _EVT_VARIANT *a3)
{
  unsigned __int64 v4; // r14
  unsigned int v5; // ebx
  struct _EVENT_DUMP_DATA *i; // rdi
  __int64 v7; // rsi
  DWORD v8; // eax
  bool v9; // cc
  __int64 v10; // rbx
  unsigned int v11; // ebx
  HANDLE v12; // rax
  DWORD v13; // ebx
  unsigned __int16 *v14; // rax
  int j; // edi
  unsigned __int16 *v16; // r8
  unsigned __int16 *v17; // rdx
  struct _EVENT_DUMP_DATA *NextInFrameDescent; // rax
  DWORD v19; // edi
  HANDLE ProcessHeap; // rax
  char *v21; // rax
  char *v22; // r15
  struct _EVENT_DUMP_DATA *v23; // rax
  unsigned __int16 *v24; // r8
  unsigned __int16 *v25; // rdx
  unsigned __int16 *v26; // rdx
  unsigned int v27; // eax
  HANDLE v28; // rax
  unsigned __int16 *v29; // rax
  EventXmlDump *v30; // rcx
  HANDLE v31; // rax
  LPVOID v32; // rax
  EventXmlDump *v33; // rcx
  unsigned int v34; // r13d
  int v35; // r15d
  unsigned __int16 *v36; // r8
  unsigned __int16 *v37; // rdx
  struct _EVENT_DUMP_DATA *v38; // rax
  EventXmlDump *v39; // rcx
  struct _EVENT_DUMP_DATA *v40; // rbx
  unsigned int v41; // r15d
  HANDLE v42; // rax
  LPVOID v43; // rax
  unsigned int v44; // r13d
  struct _EVENT_DUMP_DATA *v45; // rax
  unsigned __int16 *v46; // r8
  unsigned __int16 *v47; // rdx
  struct _EVENT_DUMP_DATA *v48; // rbx
  void *v49; // rbx
  HANDLE v50; // rax
  unsigned int v51; // eax
  unsigned int v52; // ebx
  struct _EVENT_DUMP_DATA *v53; // r15
  HANDLE v54; // rax
  unsigned __int16 *v55; // rax
  EventXmlDump *Int64Val; // rcx
  EventDumpIterator *v58; // rcx
  int v59; // [rsp+30h] [rbp-49h]
  LPVOID lpMem[3]; // [rsp+38h] [rbp-41h] BYREF
  _QWORD v61[3]; // [rsp+50h] [rbp-29h] BYREF
  _QWORD v62[3]; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v63[24]; // [rsp+80h] [rbp+7h] BYREF
  unsigned __int64 v64; // [rsp+98h] [rbp+1Fh]
  SIZE_T dwBytes; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int v66; // [rsp+F8h] [rbp+7Fh] BYREF

  dwBytes = (SIZE_T)this;
  EventDumpIterator::EventDumpIterator((EventDumpIterator *)v63, a2);
  v4 = 0;
  v5 = 0;
  v59 = 0;
  for ( i = EventDumpIterator::GetNextTopLevel((EventDumpIterator *)v63);
        i;
        i = EventDumpIterator::GetNextTopLevel((EventDumpIterator *)v63) )
  {
    v7 = v5;
    v8 = 163;
    v9 = *((_WORD *)i + 32) <= 1u;
    a3[v5].Count = 0;
    if ( v9 )
      v8 = 35;
    a3[v5].Type = v8;
    v10 = *((unsigned __int16 *)i + 32);
    if ( (_WORD)v10 )
    {
      if ( (_WORD)v10 == 1 )
      {
        if ( (*((_BYTE *)i + 60) & 8) != 0 )
        {
          EventDumpIterator::CopyFrom((EventDumpIterator *)lpMem, (const struct EventDumpIterator *)v63);
          for ( j = 0; lpMem[0]; j += dwBytes - 2 )
          {
            if ( *((_DWORD *)lpMem[0] + 2) == -1 )
              break;
            NextInFrameDescent = EventDumpIterator::GetNextInFrameDescent((EventDumpIterator *)lpMem, 1u);
            if ( !NextInFrameDescent )
              break;
            v16 = (unsigned __int16 *)*((_QWORD *)NextInFrameDescent + 1);
            v17 = *(unsigned __int16 **)NextInFrameDescent;
            LODWORD(dwBytes) = 0;
            v11 = EventXmlDump::ConvertPlainToXmlForStructMember(
                    (EventXmlDump *)&dwBytes,
                    v17,
                    v16,
                    0,
                    (unsigned int *)&dwBytes);
            if ( v11 != 122 )
              goto LABEL_77;
          }
          v19 = j + 2;
          ProcessHeap = GetProcessHeap();
          v21 = (char *)HeapAlloc(ProcessHeap, 8u, v19);
          v22 = v21;
          if ( !v21 )
          {
            v11 = 8;
LABEL_77:
            EventDumpIterator::~EventDumpIterator((EventDumpIterator *)lpMem);
            goto LABEL_69;
          }
          a3[v7].Int64Val = (INT64)v21;
          EventDumpIterator::CopyFrom((EventDumpIterator *)v61, (const struct EventDumpIterator *)v63);
          if ( v61[0] && *(_DWORD *)(v61[0] + 8LL) != -1 )
          {
            while ( 1 )
            {
              v23 = EventDumpIterator::GetNextInFrameDescent((EventDumpIterator *)v61, 1u);
              if ( !v23 )
              {
LABEL_27:
                v4 = 0;
                goto LABEL_28;
              }
              v24 = (unsigned __int16 *)*((_QWORD *)v23 + 1);
              v25 = *(unsigned __int16 **)v23;
              LODWORD(dwBytes) = v19 - v4;
              v11 = EventXmlDump::ConvertPlainToXmlForStructMember(
                      v23,
                      v25,
                      v24,
                      (unsigned __int16 *)&v22[(unsigned int)v4],
                      (unsigned int *)&dwBytes);
              if ( v11 )
                break;
              if ( !v61[0] || *(_DWORD *)(v61[0] + 8LL) == -1 )
                goto LABEL_27;
              LODWORD(v4) = dwBytes - 2 + v4;
            }
            v58 = (EventDumpIterator *)v61;
LABEL_76:
            EventDumpIterator::~EventDumpIterator(v58);
            goto LABEL_77;
          }
LABEL_28:
          EventDumpIterator::~EventDumpIterator((EventDumpIterator *)v61);
          EventDumpIterator::~EventDumpIterator((EventDumpIterator *)lpMem);
        }
        else
        {
          v26 = (unsigned __int16 *)*((_QWORD *)i + 1);
          LODWORD(dwBytes) = 0;
          v27 = EventXmlDump::ConvertPlainToXml((EventXmlDump *)0x23, v26, 0, (unsigned int *)&dwBytes);
          if ( v27 != 122 )
            goto LABEL_72;
          v28 = GetProcessHeap();
          v29 = (unsigned __int16 *)HeapAlloc(v28, 8u, (unsigned int)dwBytes);
          if ( !v29 )
          {
LABEL_78:
            v11 = 8;
            goto LABEL_69;
          }
          a3[v7].Int64Val = (INT64)v29;
          v27 = EventXmlDump::ConvertPlainToXml(v30, *((unsigned __int16 **)i + 1), v29, (unsigned int *)&dwBytes);
          if ( v27 )
            goto LABEL_72;
          v19 = dwBytes;
        }
        a3[v7].Count = v19;
      }
      else
      {
        v31 = GetProcessHeap();
        v32 = HeapAlloc(v31, 8u, 8 * v10);
        a3[v7].Int64Val = (INT64)v32;
        if ( !v32 )
          goto LABEL_78;
        a3[v7].Count = *((unsigned __int16 *)i + 32);
        if ( (*((_BYTE *)i + 60) & 8) != 0 )
        {
          EventDumpIterator::CopyFrom((EventDumpIterator *)lpMem, (const struct EventDumpIterator *)v63);
          v34 = 0;
          LODWORD(dwBytes) = 0;
          if ( *((_WORD *)i + 32) )
          {
            while ( 1 )
            {
              EventDumpIterator::CopyFrom((EventDumpIterator *)v62, (const struct EventDumpIterator *)lpMem);
              v35 = 0;
              do
              {
                if ( !v62[0] )
                  break;
                if ( *(_DWORD *)(v62[0] + 8LL) == -1 )
                  break;
                v38 = EventDumpIterator::GetNextInFrameDescent((EventDumpIterator *)v62, 1u);
                v40 = v38;
                if ( !v38 )
                  break;
                v36 = (unsigned __int16 *)*((_QWORD *)v38 + 1);
                v37 = *(unsigned __int16 **)v38;
                v66 = 0;
                LODWORD(v4) = EventXmlDump::ConvertPlainToXmlForStructMember(v39, v37, v36, 0, &v66);
                if ( (_DWORD)v4 != 122 )
                {
LABEL_74:
                  EventDumpIterator::~EventDumpIterator((EventDumpIterator *)v62);
                  EventDumpIterator::~EventDumpIterator((EventDumpIterator *)lpMem);
                  goto LABEL_68;
                }
                v35 += v66 - 2;
              }
              while ( (*((_BYTE *)v40 + 60) & 2) == 0 );
              v41 = v35 + 2;
              v42 = GetProcessHeap();
              v11 = 8;
              v43 = HeapAlloc(v42, 8u, v41);
              v64 = (unsigned __int64)v43;
              v4 = (unsigned __int64)v43;
              if ( !v43 )
                break;
              *(_QWORD *)(a3[v7].Int64Val + 8LL * v34) = v43;
              EventDumpIterator::CopyFrom((EventDumpIterator *)v61, (const struct EventDumpIterator *)lpMem);
              if ( v61[0] && *(_DWORD *)(v61[0] + 8LL) != -1 )
              {
                v44 = 0;
                v45 = EventDumpIterator::GetNextInFrameDescent((EventDumpIterator *)v61, 1u);
                while ( 1 )
                {
                  v48 = v45;
                  if ( !v45 )
                    break;
                  v46 = (unsigned __int16 *)*((_QWORD *)v45 + 1);
                  v47 = *(unsigned __int16 **)v45;
                  v66 = v41 - v44;
                  LODWORD(v4) = EventXmlDump::ConvertPlainToXmlForStructMember(
                                  (EventXmlDump *)(v41 - v44),
                                  v47,
                                  v46,
                                  (unsigned __int16 *)(v4 + v44),
                                  &v66);
                  if ( (_DWORD)v4 )
                  {
                    EventDumpIterator::~EventDumpIterator((EventDumpIterator *)v61);
                    goto LABEL_74;
                  }
                  if ( (*((_BYTE *)v48 + 60) & 2) != 0 )
                  {
                    v49 = lpMem[0];
                    if ( lpMem[0] )
                    {
                      v50 = GetProcessHeap();
                      HeapFree(v50, 0, v49);
                    }
                    EventDumpIterator::CopyFrom((EventDumpIterator *)lpMem, (const struct EventDumpIterator *)v61);
                    break;
                  }
                  if ( !v61[0] || *(_DWORD *)(v61[0] + 8LL) == -1 )
                    break;
                  v44 += v66 - 2;
                  v45 = EventDumpIterator::GetNextInFrameDescent((EventDumpIterator *)v61, 1u);
                  v4 = v64;
                }
              }
              EventDumpIterator::~EventDumpIterator((EventDumpIterator *)v61);
              EventDumpIterator::~EventDumpIterator((EventDumpIterator *)v62);
              v51 = *((unsigned __int16 *)i + 32);
              LODWORD(dwBytes) = dwBytes + 1;
              v34 = dwBytes;
              v4 = 0;
              if ( (unsigned int)dwBytes >= v51 )
                goto LABEL_58;
            }
            v58 = (EventDumpIterator *)v62;
            goto LABEL_76;
          }
LABEL_58:
          EventDumpIterator::~EventDumpIterator((EventDumpIterator *)lpMem);
        }
        else
        {
          v52 = 0;
          if ( *((_WORD *)i + 32) )
          {
            while ( 1 )
            {
              LODWORD(dwBytes) = 0;
              if ( v52 )
              {
                v4 = v52;
                v33 = (EventXmlDump *)(80LL * v52);
                v53 = (EventXmlDump *)((char *)v33 + *((_QWORD *)i + 9) - 80);
              }
              else
              {
                v53 = i;
              }
              v27 = EventXmlDump::ConvertPlainToXml(v33, *((unsigned __int16 **)v53 + 1), 0, (unsigned int *)&dwBytes);
              if ( v27 != 122 )
                break;
              v54 = GetProcessHeap();
              v55 = (unsigned __int16 *)HeapAlloc(v54, 8u, (unsigned int)dwBytes);
              if ( !v55 )
                goto LABEL_78;
              Int64Val = (EventXmlDump *)a3[v7].Int64Val;
              *((_QWORD *)Int64Val + v4) = v55;
              v27 = EventXmlDump::ConvertPlainToXml(
                      Int64Val,
                      *((unsigned __int16 **)v53 + 1),
                      v55,
                      (unsigned int *)&dwBytes);
              v4 = 0;
              if ( v27 )
                break;
              if ( ++v52 >= *((unsigned __int16 *)i + 32) )
                goto LABEL_67;
            }
LABEL_72:
            v11 = v27;
            goto LABEL_69;
          }
        }
      }
    }
    else if ( (*((_BYTE *)i + 60) & 8) != 0 )
    {
      LODWORD(dwBytes) = 0;
      v11 = EventXmlDump::ConvertPlainToXmlForStructMember(
              (EventXmlDump *)0x23,
              *(unsigned __int16 **)i,
              (unsigned __int16 *)&Ext,
              0,
              (unsigned int *)&dwBytes);
      if ( v11 != 122 )
        goto LABEL_69;
      v12 = GetProcessHeap();
      v13 = dwBytes;
      v14 = (unsigned __int16 *)HeapAlloc(v12, 8u, (unsigned int)dwBytes);
      if ( !v14 )
        goto LABEL_78;
      a3[v7].Int64Val = (INT64)v14;
      a3[v7].Count = v13;
      v11 = EventXmlDump::ConvertPlainToXmlForStructMember(
              (EventXmlDump *)&dwBytes,
              *(unsigned __int16 **)i,
              (unsigned __int16 *)&Ext,
              v14,
              (unsigned int *)&dwBytes);
      if ( v11 )
        goto LABEL_69;
    }
    else
    {
      a3[v7].Int64Val = (INT64)&Ext;
      a3[v7].Count = 8;
    }
LABEL_67:
    v5 = ++v59;
  }
LABEL_68:
  v11 = v4;
LABEL_69:
  EventDumpIterator::~EventDumpIterator((EventDumpIterator *)v63);
  return v11;
}

```

## disassembly

```asm
0x14000f104  mov     [rsp-8+arg_8], rbx
0x14000f109  mov     [rsp-8+dwBytes], rcx
0x14000f10e  push    rbp
0x14000f10f  push    rsi
0x14000f110  push    rdi
0x14000f111  push    r12
0x14000f113  push    r13
0x14000f115  push    r14
0x14000f117  push    r15
0x14000f119  lea     rbp, [rsp-27h]
0x14000f11e  sub     rsp, 0A0h
0x14000f125  lea     rcx, [rbp+57h+var_50]; this
0x14000f129  mov     r12, r8
0x14000f12c  call    ??0EventDumpIterator@@QEAA@PEAVEventDumpWorkspace@@@Z; EventDumpIterator::EventDumpIterator(EventDumpWorkspace *)
0x14000f131  xor     r14d, r14d
0x14000f134  lea     rcx, [rbp+57h+var_50]; this
0x14000f138  mov     ebx, r14d
0x14000f13b  mov     [rbp+57h+var_A0], ebx
0x14000f13e  call    ?GetNextTopLevel@EventDumpIterator@@QEAAPEAU_EVENT_DUMP_DATA@@XZ; EventDumpIterator::GetNextTopLevel(void)
0x14000f143  mov     rdi, rax
0x14000f146  test    rax, rax
0x14000f149  jz      loc_14000F67C
0x14000f14f  lea     r15d, [r14+1]
0x14000f153  lea     r13d, [r14+8]
0x14000f157  mov     esi, ebx
0x14000f159  lea     rdx, Ext
0x14000f160  add     rsi, rsi
0x14000f163  mov     eax, 0A3h
0x14000f168  cmp     [rdi+40h], r15w
0x14000f16d  lea     ecx, [rax-80h]; this
0x14000f170  mov     [r12+rsi*8+8], r14d
0x14000f175  cmovbe  eax, ecx
0x14000f178  mov     [r12+rsi*8+0Ch], eax
0x14000f17d  movzx   ebx, word ptr [rdi+40h]
0x14000f181  test    bx, bx
0x14000f184  jnz     loc_14000F218
0x14000f18a  test    [rdi+3Ch], r13b
0x14000f18e  jz      short loc_14000F20A
0x14000f190  lea     rax, [rbp+57h+dwBytes]
0x14000f194  mov     dword ptr [rbp+57h+dwBytes], r14d
0x14000f198  mov     r8, rdx; unsigned __int16 *
0x14000f19b  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x14000f1a0  mov     rdx, [rdi]; unsigned __int16 *
0x14000f1a3  xor     r9d, r9d; unsigned __int16 *
0x14000f1a6  call    ?ConvertPlainToXmlForStructMember@EventXmlDump@@QEAAKPEAG00PEAK@Z; EventXmlDump::ConvertPlainToXmlForStructMember(ushort *,ushort *,ushort *,ulong *)
0x14000f1ab  mov     ebx, eax
0x14000f1ad  cmp     eax, 7Ah ; 'z'
0x14000f1b0  jnz     loc_14000F67F
0x14000f1b6  call    cs:__imp_GetProcessHeap
0x14000f1bc  mov     ebx, dword ptr [rbp+57h+dwBytes]
0x14000f1bf  mov     edx, r13d; dwFlags
0x14000f1c2  mov     r8d, ebx; dwBytes
0x14000f1c5  mov     rcx, rax; hHeap
0x14000f1c8  call    cs:__imp_HeapAlloc
0x14000f1ce  test    rax, rax
0x14000f1d1  jz      loc_14000F6E5
0x14000f1d7  mov     [r12+rsi*8], rax
0x14000f1db  lea     rcx, [rbp+57h+dwBytes]; this
0x14000f1df  mov     [r12+rsi*8+8], ebx
0x14000f1e4  lea     r8, Ext; unsigned __int16 *
0x14000f1eb  mov     rdx, [rdi]; unsigned __int16 *
0x14000f1ee  mov     r9, rax; unsigned __int16 *
0x14000f1f1  mov     [rsp+0D0h+var_B0], rcx; unsigned int *
0x14000f1f6  call    ?ConvertPlainToXmlForStructMember@EventXmlDump@@QEAAKPEAG00PEAK@Z; EventXmlDump::ConvertPlainToXmlForStructMember(ushort *,ushort *,ushort *,ulong *)
0x14000f1fb  mov     ebx, eax
0x14000f1fd  test    eax, eax
0x14000f1ff  jnz     loc_14000F67F
0x14000f205  jmp     loc_14000F65E
0x14000f20a  mov     [r12+rsi*8], rdx
0x14000f20e  mov     [r12+rsi*8+8], r13d
0x14000f213  jmp     loc_14000F65E
0x14000f218  cmp     bx, r15w
0x14000f21c  jnz     loc_14000F3B0
0x14000f222  test    [rdi+3Ch], r13b
0x14000f226  jz      loc_14000F34B
0x14000f22c  lea     rdx, [rbp+57h+var_50]; struct EventDumpIterator *
0x14000f230  lea     rcx, [rbp+57h+lpMem]; this
0x14000f234  call    ?CopyFrom@EventDumpIterator@@AEAAXAEBV1@@Z; EventDumpIterator::CopyFrom(EventDumpIterator const &)
0x14000f239  mov     edi, r14d
0x14000f23c  jmp     short loc_14000F26D
0x14000f23e  mov     r8, [rax+8]; unsigned __int16 *
0x14000f242  lea     rcx, [rbp+57h+dwBytes]; this
0x14000f246  mov     rdx, [rax]; unsigned __int16 *
0x14000f249  xor     r9d, r9d; unsigned __int16 *
0x14000f24c  mov     [rsp+0D0h+var_B0], rcx; unsigned int *
0x14000f251  mov     dword ptr [rbp+57h+dwBytes], r14d
0x14000f255  call    ?ConvertPlainToXmlForStructMember@EventXmlDump@@QEAAKPEAG00PEAK@Z; EventXmlDump::ConvertPlainToXmlForStructMember(ushort *,ushort *,ushort *,ulong *)
0x14000f25a  mov     ebx, eax
0x14000f25c  cmp     eax, 7Ah ; 'z'
0x14000f25f  jnz     loc_14000F6DA
0x14000f265  mov     eax, dword ptr [rbp+57h+dwBytes]
0x14000f268  add     eax, 0FFFFFFFEh
0x14000f26b  add     edi, eax
0x14000f26d  mov     rax, [rbp+57h+lpMem]
0x14000f271  test    rax, rax
0x14000f274  jz      short loc_14000F28D
0x14000f276  cmp     dword ptr [rax+8], 0FFFFFFFFh
0x14000f27a  jz      short loc_14000F28D
0x14000f27c  mov     edx, r15d; unsigned int
0x14000f27f  lea     rcx, [rbp+57h+lpMem]; this
0x14000f283  call    ?GetNextInFrameDescent@EventDumpIterator@@AEAAPEAU_EVENT_DUMP_DATA@@K@Z; EventDumpIterator::GetNextInFrameDescent(ulong)
0x14000f288  test    rax, rax
0x14000f28b  jnz     short loc_14000F23E
0x14000f28d  add     edi, 2
0x14000f290  call    cs:__imp_GetProcessHeap
0x14000f296  mov     r8d, edi; dwBytes
0x14000f299  mov     edx, r13d; dwFlags
0x14000f29c  mov     rcx, rax; hHeap
0x14000f29f  call    cs:__imp_HeapAlloc
0x14000f2a5  mov     r15, rax
0x14000f2a8  test    rax, rax
0x14000f2ab  jz      loc_14000F6AB
0x14000f2b1  lea     rdx, [rbp+57h+var_50]; struct EventDumpIterator *
0x14000f2b5  mov     [r12+rsi*8], rax
0x14000f2b9  lea     rcx, [rbp+57h+var_80]; this
0x14000f2bd  call    ?CopyFrom@EventDumpIterator@@AEAAXAEBV1@@Z; EventDumpIterator::CopyFrom(EventDumpIterator const &)
0x14000f2c2  mov     rcx, [rbp+57h+var_80]
0x14000f2c6  test    rcx, rcx
0x14000f2c9  jz      short loc_14000F331
0x14000f2cb  cmp     dword ptr [rcx+8], 0FFFFFFFFh
0x14000f2cf  jz      short loc_14000F331
0x14000f2d1  mov     edx, 1; unsigned int
0x14000f2d6  lea     rcx, [rbp+57h+var_80]; this
0x14000f2da  call    ?GetNextInFrameDescent@EventDumpIterator@@AEAAPEAU_EVENT_DUMP_DATA@@K@Z; EventDumpIterator::GetNextInFrameDescent(ulong)
0x14000f2df  mov     rcx, rax; this
0x14000f2e2  test    rax, rax
0x14000f2e5  jz      short loc_14000F32E
0x14000f2e7  mov     r8, [rcx+8]; unsigned __int16 *
0x14000f2eb  mov     eax, edi
0x14000f2ed  mov     rdx, [rcx]; unsigned __int16 *
0x14000f2f0  sub     eax, r14d
0x14000f2f3  mov     dword ptr [rbp+57h+dwBytes], eax
0x14000f2f6  lea     rax, [rbp+57h+dwBytes]
0x14000f2fa  mov     r9d, r14d
0x14000f2fd  add     r9, r15; unsigned __int16 *
0x14000f300  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x14000f305  call    ?ConvertPlainToXmlForStructMember@EventXmlDump@@QEAAKPEAG00PEAK@Z; EventXmlDump::ConvertPlainToXmlForStructMember(ushort *,ushort *,ushort *,ulong *)
0x14000f30a  mov     ebx, eax
0x14000f30c  test    eax, eax
0x14000f30e  jnz     loc_14000F6A5
0x14000f314  mov     rax, [rbp+57h+var_80]
0x14000f318  test    rax, rax
0x14000f31b  jz      short loc_14000F32E
0x14000f31d  cmp     dword ptr [rax+8], 0FFFFFFFFh
0x14000f321  jz      short loc_14000F32E
0x14000f323  mov     eax, dword ptr [rbp+57h+dwBytes]
0x14000f326  add     eax, 0FFFFFFFEh
0x14000f329  add     r14d, eax
0x14000f32c  jmp     short loc_14000F2D1
0x14000f32e  xor     r14d, r14d
0x14000f331  lea     rcx, [rbp+57h+var_80]; this
0x14000f335  call    ??1EventDumpIterator@@QEAA@XZ; EventDumpIterator::~EventDumpIterator(void)
0x14000f33a  lea     rcx, [rbp+57h+lpMem]; this
0x14000f33e  call    ??1EventDumpIterator@@QEAA@XZ; EventDumpIterator::~EventDumpIterator(void)
0x14000f343  mov     r15d, 1
0x14000f349  jmp     short loc_14000F3A6
0x14000f34b  mov     rdx, [rdi+8]; unsigned __int16 *
0x14000f34f  lea     r9, [rbp+57h+dwBytes]; unsigned int *
0x14000f353  xor     r8d, r8d; unsigned __int16 *
0x14000f356  mov     dword ptr [rbp+57h+dwBytes], r14d
0x14000f35a  call    ?ConvertPlainToXml@EventXmlDump@@QEAAKPEAG0PEAK@Z; EventXmlDump::ConvertPlainToXml(ushort *,ushort *,ulong *)
0x14000f35f  cmp     eax, 7Ah ; 'z'
0x14000f362  jnz     loc_14000F6B0
0x14000f368  call    cs:__imp_GetProcessHeap
0x14000f36e  mov     r8d, dword ptr [rbp+57h+dwBytes]; dwBytes
0x14000f372  mov     edx, r13d; dwFlags
0x14000f375  mov     rcx, rax; hHeap
0x14000f378  call    cs:__imp_HeapAlloc
0x14000f37e  test    rax, rax
0x14000f381  jz      loc_14000F6E5
0x14000f387  mov     [r12+rsi*8], rax
0x14000f38b  lea     r9, [rbp+57h+dwBytes]; unsigned int *
0x14000f38f  mov     rdx, [rdi+8]; unsigned __int16 *
0x14000f393  mov     r8, rax; unsigned __int16 *
0x14000f396  call    ?ConvertPlainToXml@EventXmlDump@@QEAAKPEAG0PEAK@Z; EventXmlDump::ConvertPlainToXml(ushort *,ushort *,ulong *)
0x14000f39b  test    eax, eax
0x14000f39d  jnz     loc_14000F6B0
0x14000f3a3  mov     edi, dword ptr [rbp+57h+dwBytes]
0x14000f3a6  mov     [r12+rsi*8+8], edi
0x14000f3ab  jmp     loc_14000F65E
0x14000f3b0  call    cs:__imp_GetProcessHeap
0x14000f3b6  mov     r8, rbx
0x14000f3b9  mov     edx, r13d; dwFlags
0x14000f3bc  shl     r8, 3; dwBytes
0x14000f3c0  mov     rcx, rax; hHeap
0x14000f3c3  call    cs:__imp_HeapAlloc
0x14000f3c9  mov     [r12+rsi*8], rax
0x14000f3cd  test    rax, rax
0x14000f3d0  jz      loc_14000F6E5
0x14000f3d6  movzx   eax, word ptr [rdi+40h]
0x14000f3da  mov     [r12+rsi*8+8], eax
0x14000f3df  test    [rdi+3Ch], r13b
0x14000f3e3  jz      loc_14000F5C3
0x14000f3e9  lea     rdx, [rbp+57h+var_50]; struct EventDumpIterator *
0x14000f3ed  lea     rcx, [rbp+57h+lpMem]; this
0x14000f3f1  call    ?CopyFrom@EventDumpIterator@@AEAAXAEBV1@@Z; EventDumpIterator::CopyFrom(EventDumpIterator const &)
0x14000f3f6  mov     r13d, r14d
0x14000f3f9  mov     dword ptr [rbp+57h+dwBytes], r14d
0x14000f3fd  cmp     r14w, [rdi+40h]
0x14000f402  jnb     loc_14000F5AF
0x14000f408  lea     rdx, [rbp+57h+lpMem]; struct EventDumpIterator *
0x14000f40c  lea     rcx, [rbp+57h+var_68]; this
0x14000f410  call    ?CopyFrom@EventDumpIterator@@AEAAXAEBV1@@Z; EventDumpIterator::CopyFrom(EventDumpIterator const &)
0x14000f415  mov     r15d, r14d
0x14000f418  jmp     short loc_14000F454
0x14000f41a  mov     r8, [rbx+8]; unsigned __int16 *
0x14000f41e  lea     rax, [rbp+57h+arg_18]
0x14000f422  mov     rdx, [rbx]; unsigned __int16 *
0x14000f425  xor     r9d, r9d; unsigned __int16 *
0x14000f428  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x14000f42d  mov     [rbp+57h+arg_18], r14d
0x14000f431  call    ?ConvertPlainToXmlForStructMember@EventXmlDump@@QEAAKPEAG00PEAK@Z; EventXmlDump::ConvertPlainToXmlForStructMember(ushort *,ushort *,ushort *,ulong *)
0x14000f436  mov     r14d, eax
0x14000f439  cmp     eax, 7Ah ; 'z'
0x14000f43c  jnz     loc_14000F6BD
0x14000f442  mov     eax, [rbp+57h+arg_18]
0x14000f445  add     eax, 0FFFFFFFEh
0x14000f448  add     r15d, eax
0x14000f44b  test    byte ptr [rbx+3Ch], 2
0x14000f44f  jnz     short loc_14000F479
0x14000f451  xor     r14d, r14d
0x14000f454  mov     rax, [rbp+57h+var_68]
0x14000f458  test    rax, rax
0x14000f45b  jz      short loc_14000F479
0x14000f45d  cmp     dword ptr [rax+8], 0FFFFFFFFh
0x14000f461  jz      short loc_14000F479
0x14000f463  mov     edx, 1; unsigned int
0x14000f468  lea     rcx, [rbp+57h+var_68]; this
0x14000f46c  call    ?GetNextInFrameDescent@EventDumpIterator@@AEAAPEAU_EVENT_DUMP_DATA@@K@Z; EventDumpIterator::GetNextInFrameDescent(ulong)
0x14000f471  mov     rbx, rax
0x14000f474  test    rax, rax
0x14000f477  jnz     short loc_14000F41A
0x14000f479  add     r15d, 2
0x14000f47d  call    cs:__imp_GetProcessHeap
0x14000f483  mov     ebx, 8
0x14000f488  mov     r8d, r15d; dwBytes
0x14000f48b  mov     rcx, rax; hHeap
0x14000f48e  mov     edx, ebx; dwFlags
0x14000f490  call    cs:__imp_HeapAlloc
0x14000f496  mov     [rbp+57h+var_38], rax
0x14000f49a  mov     r14, rax
0x14000f49d  test    rax, rax
0x14000f4a0  jz      loc_14000F6D1
0x14000f4a6  mov     rcx, [r12+rsi*8]
0x14000f4aa  mov     edx, r13d
0x14000f4ad  mov     [rcx+rdx*8], rax
0x14000f4b1  lea     rdx, [rbp+57h+lpMem]; struct EventDumpIterator *
0x14000f4b5  lea     rcx, [rbp+57h+var_80]; this
0x14000f4b9  call    ?CopyFrom@EventDumpIterator@@AEAAXAEBV1@@Z; EventDumpIterator::CopyFrom(EventDumpIterator const &)
0x14000f4be  mov     rcx, [rbp+57h+var_80]
0x14000f4c2  test    rcx, rcx
0x14000f4c5  jz      loc_14000F578
0x14000f4cb  cmp     dword ptr [rcx+8], 0FFFFFFFFh
0x14000f4cf  jz      loc_14000F578
0x14000f4d5  xor     r13d, r13d
0x14000f4d8  lea     edx, [rbx-7]; unsigned int
0x14000f4db  lea     rcx, [rbp+57h+var_80]; this
0x14000f4df  call    ?GetNextInFrameDescent@EventDumpIterator@@AEAAPEAU_EVENT_DUMP_DATA@@K@Z; EventDumpIterator::GetNextInFrameDescent(ulong)
0x14000f4e4  jmp     short loc_14000F544
0x14000f4e6  mov     r8, [rbx+8]; unsigned __int16 *
0x14000f4ea  lea     rax, [rbp+57h+arg_18]
0x14000f4ee  mov     rdx, [rbx]; unsigned __int16 *
0x14000f4f1  mov     ecx, r15d
0x14000f4f4  sub     ecx, r13d; this
0x14000f4f7  mov     r9d, r13d
0x14000f4fa  add     r9, r14; unsigned __int16 *
0x14000f4fd  mov     [rbp+57h+arg_18], ecx
0x14000f500  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x14000f505  call    ?ConvertPlainToXmlForStructMember@EventXmlDump@@QEAAKPEAG00PEAK@Z; EventXmlDump::ConvertPlainToXmlForStructMember(ushort *,ushort *,ushort *,ulong *)
0x14000f50a  mov     r14d, eax
0x14000f50d  test    eax, eax
0x14000f50f  jnz     loc_14000F6B4
0x14000f515  test    byte ptr [rbx+3Ch], 2
0x14000f519  jnz     short loc_14000F54E
0x14000f51b  mov     rax, [rbp+57h+var_80]
0x14000f51f  test    rax, rax
0x14000f522  jz      short loc_14000F578
0x14000f524  cmp     dword ptr [rax+8], 0FFFFFFFFh
0x14000f528  jz      short loc_14000F578
0x14000f52a  mov     eax, [rbp+57h+arg_18]
0x14000f52d  lea     edx, [r14+1]; unsigned int
0x14000f531  add     eax, 0FFFFFFFEh
0x14000f534  lea     rcx, [rbp+57h+var_80]; this
0x14000f538  add     r13d, eax
0x14000f53b  call    ?GetNextInFrameDescent@EventDumpIterator@@AEAAPEAU_EVENT_DUMP_DATA@@K@Z; EventDumpIterator::GetNextInFrameDescent(ulong)
0x14000f540  mov     r14, [rbp+57h+var_38]
0x14000f544  mov     rbx, rax
0x14000f547  test    rax, rax
0x14000f54a  jnz     short loc_14000F4E6
0x14000f54c  jmp     short loc_14000F578
0x14000f54e  mov     rbx, [rbp+57h+lpMem]
0x14000f552  test    rbx, rbx
0x14000f555  jz      short loc_14000F56B
0x14000f557  call    cs:__imp_GetProcessHeap
0x14000f55d  mov     r8, rbx; lpMem
0x14000f560  xor     edx, edx; dwFlags
0x14000f562  mov     rcx, rax; hHeap
0x14000f565  call    cs:__imp_HeapFree
0x14000f56b  lea     rdx, [rbp+57h+var_80]; struct EventDumpIterator *
0x14000f56f  lea     rcx, [rbp+57h+lpMem]; this
  ... truncated ...
```
