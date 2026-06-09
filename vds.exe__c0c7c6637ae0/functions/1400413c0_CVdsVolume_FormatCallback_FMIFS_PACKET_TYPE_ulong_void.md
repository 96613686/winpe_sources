# CVdsVolume::FormatCallback(_FMIFS_PACKET_TYPE,ulong,void *)

- ea: `0x1400413c0`
- end: `0x1400416fd`
- name: `?FormatCallback@CVdsVolume@@SAEW4_FMIFS_PACKET_TYPE@@KPEAX@Z`
- size: `829`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400069e8`
- `0x14000e6bc`
- `0x1400411c4`
- `0x1400413c0`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140041446`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140041454`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140041446`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140041454`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004141d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004141d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400415c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400415c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004140b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004140b`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x14004153b`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x14004153b`
- `vdsutil!MountVolume` at `0x14004158b`
- `vdsutil!MountVolume` at `0x14004158b`
- `vdsutil!VdsTraceEx` at `0x1400415e0`
- `vdsutil!VdsTraceEx` at `0x1400415e0`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140041404`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140041404`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004166c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400416ce`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004166c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400416ce`
- `vdsutil!VdsTraceW` at `0x14004143c`
- `vdsutil!VdsTraceW` at `0x14004143c`

## string_xrefs

- `0x1400415d4`: `CVdsVolume::FormatCallback: failed to compress volume: %X`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CVdsVolume::FormatCallback(int a1, __int64 a2, unsigned int *a3)
{
  DWORD CurrentThreadId; // ebx
  struct _FORMAT_VOLUME_THREAD_PARAMETER *ThreadRoutine; // rbx
  CVdsAsyncObjectBase *v7; // rcx
  char v8; // si
  int v9; // edi
  int v10; // edi
  int v11; // edi
  int v12; // edi
  int v13; // edi
  int v14; // edi
  int v15; // edi
  unsigned int v16; // edi
  __int64 v17; // rax
  int v18; // edi
  DWORD LastError; // eax
  signed int v20; // eax
  int v21; // edi
  int v22; // edi
  int v23; // edi
  int v24; // edi
  int v25; // edi
  int v26; // edi
  int v27; // edi
  int v28; // edi
  _BYTE v30[16]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 v31[268]; // [rsp+30h] [rbp-D0h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v30, 0x5Eu, "CVdsVolume::FormatCallback()");
  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection(&g_GlobalCriticalSection);
  ThreadRoutine = FindThreadRoutine(CurrentThreadId);
  if ( ThreadRoutine )
  {
    LeaveCriticalSection(&g_GlobalCriticalSection);
    v7 = (CVdsAsyncObjectBase *)*((_QWORD *)ThreadRoutine + 1);
    v8 = 1;
    if ( *((_DWORD *)v7 + 30) == 1 )
    {
      *((_DWORD *)ThreadRoutine + 298) = -2147212275;
      goto LABEL_60;
    }
    if ( a1 > 11 )
    {
      v21 = a1 - 12;
      if ( !v21 )
      {
        *((_DWORD *)ThreadRoutine + 298) = -2147212247;
        goto LABEL_60;
      }
      v22 = v21 - 4;
      if ( !v22 )
      {
        *((_DWORD *)ThreadRoutine + 298) = -2147212242;
        goto LABEL_60;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        *((_DWORD *)ThreadRoutine + 298) = -2147212241;
        goto LABEL_60;
      }
      v24 = v23 - 1;
      if ( !v24 )
      {
        *((_DWORD *)ThreadRoutine + 298) = -2147212244;
        goto LABEL_60;
      }
      v25 = v24 - 1;
      if ( !v25 )
      {
        *((_DWORD *)ThreadRoutine + 298) = -2147212243;
        goto LABEL_60;
      }
      v26 = v25 - 2;
      if ( !v26 )
      {
        *((_DWORD *)ThreadRoutine + 298) = -2147212240;
        goto LABEL_60;
      }
      v27 = v26 - 3;
      if ( !v27 )
      {
        *((_DWORD *)ThreadRoutine + 298) = -2147212227;
        goto LABEL_60;
      }
      v28 = v27 - 3;
      if ( v28 )
      {
        if ( v28 == 1 )
        {
          *((_DWORD *)ThreadRoutine + 298) = -2147211886;
          goto LABEL_60;
        }
        goto LABEL_52;
      }
      *((_DWORD *)ThreadRoutine + 298) = -2147211880;
    }
    else
    {
      if ( a1 != 11 )
      {
        if ( a1 )
        {
          v9 = a1 - 2;
          if ( !v9 )
          {
            *((_DWORD *)ThreadRoutine + 298) = -2147212270;
            goto LABEL_60;
          }
          v10 = v9 - 1;
          if ( !v10 )
          {
            *((_DWORD *)ThreadRoutine + 298) = -2147212251;
            goto LABEL_60;
          }
          v11 = v10 - 2;
          if ( !v11 )
          {
            *((_DWORD *)ThreadRoutine + 298) = -2147212250;
            goto LABEL_60;
          }
          v12 = v11 - 1;
          if ( !v12 )
          {
            *((_DWORD *)ThreadRoutine + 298) = -2147024891;
            goto LABEL_60;
          }
          v13 = v12 - 1;
          if ( !v13 )
          {
            *((_DWORD *)ThreadRoutine + 298) = -2147212248;
            goto LABEL_60;
          }
          v14 = v13 - 1;
          if ( !v14 )
          {
            *((_DWORD *)ThreadRoutine + 298) = -2147212269;
            goto LABEL_60;
          }
          v15 = v14 - 1;
          if ( !v15 )
          {
            *((_DWORD *)ThreadRoutine + 298) = -2147212246;
            goto LABEL_60;
          }
          if ( v15 == 1 )
          {
            *((_DWORD *)ThreadRoutine + 298) = -2147212245;
            goto LABEL_60;
          }
        }
        else
        {
          v16 = *a3;
          CVdsAsyncObjectBase::SetCompletionStatus(v7, -2147212279, *a3);
          v17 = *((_QWORD *)ThreadRoutine + 2) - *(_QWORD *)&GUID_NULL.Data1;
          if ( !v17 )
            v17 = *((_QWORD *)ThreadRoutine + 3) - *(_QWORD *)GUID_NULL.Data4;
          if ( v17 )
            CVdsService::SendFileSystemNotification(0xCCu, (struct _GUID *)ThreadRoutine + 1, v16);
        }
LABEL_52:
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v30);
        return v8;
      }
      if ( *(_BYTE *)a3 )
      {
        v18 = 0;
        if ( *((_DWORD *)ThreadRoutine + 292) )
        {
          LastError = MountVolume((char *)ThreadRoutine + 32);
          if ( LastError
            || (StringCchPrintfW(v31, 0x105u, L"%s\\", (char *)ThreadRoutine + 32),
                (*((unsigned __int8 (__fastcall **)(unsigned __int16 *, __int64))ThreadRoutine + 147))(v31, 1) != 1)
            && (LastError = GetLastError()) != 0 )
          {
            VdsTraceEx(94, 0, "CVdsVolume::FormatCallback: failed to compress volume: %X", LastError);
            v18 = 271427;
          }
        }
        if ( !*((_DWORD *)ThreadRoutine + 298) )
          *((_DWORD *)ThreadRoutine + 298) = v18;
        goto LABEL_52;
      }
      if ( !*((_DWORD *)ThreadRoutine + 298) )
      {
        v20 = a3[1];
        if ( v20 > 0 )
          v20 = (unsigned __int16)v20 | 0x80070000;
        *((_DWORD *)ThreadRoutine + 298) = v20;
      }
    }
    v8 = 0;
    goto LABEL_52;
  }
  VdsTraceW(0, L"CVdsVolume::FormatCallback, 1");
  LeaveCriticalSection(&g_GlobalCriticalSection);
LABEL_60:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v30);
  return 0;
}

```

## disassembly

```asm
0x1400413c0  mov     [rsp-8+arg_0], rbx
0x1400413c5  mov     [rsp-8+arg_8], rsi
0x1400413ca  push    rbp
0x1400413cb  push    rdi
0x1400413cc  push    r14
0x1400413ce  lea     rbp, [rsp-150h]
0x1400413d6  sub     rsp, 250h
0x1400413dd  mov     rax, cs:__security_cookie
0x1400413e4  xor     rax, rsp
0x1400413e7  mov     [rbp+160h+var_18], rax
0x1400413ee  mov     r14, r8
0x1400413f1  mov     edi, ecx
0x1400413f3  lea     r8, aCvdsvolumeForm_31; "CVdsVolume::FormatCallback()"
0x1400413fa  mov     edx, 5Eh ; '^'
0x1400413ff  lea     rcx, [rsp+260h+var_240]
0x140041404  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14004140a  nop
0x14004140b  call    cs:__imp_GetCurrentThreadId
0x140041411  mov     ebx, eax
0x140041413  lea     rsi, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_GlobalCriticalSection
0x14004141a  mov     rcx, rsi; lpCriticalSection
0x14004141d  call    cs:__imp_EnterCriticalSection
0x140041423  nop
0x140041424  mov     ecx, ebx; unsigned int
0x140041426  call    ?FindThreadRoutine@@YAPEAU_FORMAT_VOLUME_THREAD_PARAMETER@@K@Z; FindThreadRoutine(ulong)
0x14004142b  mov     rbx, rax
0x14004142e  test    rax, rax
0x140041431  jnz     short loc_140041451
0x140041433  lea     rdx, aCvdsvolumeForm_23; "CVdsVolume::FormatCallback, 1"
0x14004143a  xor     ecx, ecx
0x14004143c  call    cs:__imp_VdsTraceW
0x140041442  nop
0x140041443  mov     rcx, rsi; lpCriticalSection
0x140041446  call    cs:__imp_LeaveCriticalSection
0x14004144c  jmp     loc_1400416C9
0x140041451  mov     rcx, rsi; lpCriticalSection
0x140041454  call    cs:__imp_LeaveCriticalSection
0x14004145a  mov     rcx, [rbx+8]
0x14004145e  mov     esi, 1
0x140041463  cmp     [rcx+78h], esi
0x140041466  jnz     short loc_140041477
0x140041468  mov     dword ptr [rbx+4A8h], 8004240Dh
0x140041472  jmp     loc_1400416C9
0x140041477  cmp     edi, 0Bh
0x14004147a  jg      loc_14004161D
0x140041480  jz      loc_140041577
0x140041486  test    edi, edi
0x140041488  jz      loc_140041530
0x14004148e  sub     edi, 2
0x140041491  jz      loc_140041521
0x140041497  sub     edi, esi
0x140041499  jz      short loc_140041512
0x14004149b  sub     edi, 2
0x14004149e  jz      short loc_140041503
0x1400414a0  sub     edi, esi
0x1400414a2  jz      short loc_1400414F4
0x1400414a4  sub     edi, esi
0x1400414a6  jz      short loc_1400414E5
0x1400414a8  sub     edi, esi
0x1400414aa  jz      short loc_1400414D6
0x1400414ac  sub     edi, esi
0x1400414ae  jz      short loc_1400414C7
0x1400414b0  cmp     edi, esi
0x1400414b2  jnz     loc_140041667
0x1400414b8  mov     dword ptr [rbx+4A8h], 8004242Bh
0x1400414c2  jmp     loc_1400416C9
0x1400414c7  mov     dword ptr [rbx+4A8h], 8004242Ah
0x1400414d1  jmp     loc_1400416C9
0x1400414d6  mov     dword ptr [rbx+4A8h], 80042413h
0x1400414e0  jmp     loc_1400416C9
0x1400414e5  mov     dword ptr [rbx+4A8h], 80042428h
0x1400414ef  jmp     loc_1400416C9
0x1400414f4  mov     dword ptr [rbx+4A8h], 80070005h
0x1400414fe  jmp     loc_1400416C9
0x140041503  mov     dword ptr [rbx+4A8h], 80042426h
0x14004150d  jmp     loc_1400416C9
0x140041512  mov     dword ptr [rbx+4A8h], 80042425h
0x14004151c  jmp     loc_1400416C9
0x140041521  mov     dword ptr [rbx+4A8h], 80042412h
0x14004152b  jmp     loc_1400416C9
0x140041530  mov     edi, [r14]
0x140041533  mov     r8d, edi
0x140041536  mov     edx, 80042409h
0x14004153b  call    cs:__imp_?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z; CVdsAsyncObjectBase::SetCompletionStatus(long,ulong)
0x140041541  lea     rdx, [rbx+10h]; struct _GUID *
0x140041545  mov     rax, [rdx]
0x140041548  sub     rax, qword ptr cs:GUID_NULL.Data1
0x14004154f  jnz     short loc_14004155C
0x140041551  mov     rax, [rdx+8]
0x140041555  sub     rax, qword ptr cs:GUID_NULL.Data4
0x14004155c  test    rax, rax
0x14004155f  jz      loc_140041667
0x140041565  mov     r8d, edi; unsigned int
0x140041568  mov     ecx, 0CCh; unsigned int
0x14004156d  call    ?SendFileSystemNotification@CVdsService@@SAXKAEAU_GUID@@K@Z; CVdsService::SendFileSystemNotification(ulong,_GUID &,ulong)
0x140041572  jmp     loc_140041667
0x140041577  cmp     byte ptr [r14], 0
0x14004157b  jz      short loc_1400415FC
0x14004157d  xor     edi, edi
0x14004157f  cmp     [rbx+490h], edi
0x140041585  jz      short loc_1400415EB
0x140041587  lea     rcx, [rbx+20h]
0x14004158b  call    cs:__imp_MountVolume
0x140041591  test    eax, eax
0x140041593  jnz     short loc_1400415D1
0x140041595  lea     r9, [rbx+20h]
0x140041599  lea     r8, aS_1; "%s\\"
0x1400415a0  mov     edx, 105h; unsigned __int64
0x1400415a5  lea     rcx, [rsp+260h+var_230]; unsigned __int16 *
0x1400415aa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400415af  mov     edx, esi
0x1400415b1  lea     rcx, [rsp+260h+var_230]
0x1400415b6  mov     rax, [rbx+498h]
0x1400415bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400415c2  cmp     al, sil
0x1400415c5  jz      short loc_1400415EB
0x1400415c7  call    cs:__imp_GetLastError
0x1400415cd  test    eax, eax
0x1400415cf  jz      short loc_1400415EB
0x1400415d1  mov     r9d, eax
0x1400415d4  lea     r8, aCvdsvolumeForm_35; "CVdsVolume::FormatCallback: failed to c"...
0x1400415db  xor     edx, edx
0x1400415dd  lea     ecx, [rdx+5Eh]
0x1400415e0  call    cs:__imp_VdsTraceEx
0x1400415e6  mov     edi, 42443h
0x1400415eb  cmp     dword ptr [rbx+4A8h], 0
0x1400415f2  jnz     short loc_140041667
0x1400415f4  mov     [rbx+4A8h], edi
0x1400415fa  jmp     short loc_140041667
0x1400415fc  cmp     dword ptr [rbx+4A8h], 0
0x140041603  jnz     short loc_140041664
0x140041605  mov     eax, [r14+4]
0x140041609  test    eax, eax
0x14004160b  jle     short loc_140041615
0x14004160d  movzx   eax, ax
0x140041610  or      eax, 80070000h
0x140041615  mov     [rbx+4A8h], eax
0x14004161b  jmp     short loc_140041664
0x14004161d  sub     edi, 0Ch
0x140041620  jz      loc_1400416BF
0x140041626  sub     edi, 4
0x140041629  jz      loc_1400416B3
0x14004162f  sub     edi, esi
0x140041631  jz      short loc_1400416A7
0x140041633  sub     edi, esi
0x140041635  jz      short loc_14004169B
0x140041637  sub     edi, esi
0x140041639  jz      short loc_14004168F
0x14004163b  sub     edi, 2
0x14004163e  jz      short loc_140041683
0x140041640  sub     edi, 3
0x140041643  jz      short loc_140041677
0x140041645  sub     edi, 3
0x140041648  jz      short loc_14004165A
0x14004164a  cmp     edi, esi
0x14004164c  jnz     short loc_140041667
0x14004164e  mov     dword ptr [rbx+4A8h], 80042592h
0x140041658  jmp     short loc_1400416C9
0x14004165a  mov     dword ptr [rbx+4A8h], 80042598h
0x140041664  xor     sil, sil
0x140041667  lea     rcx, [rsp+260h+var_240]
0x14004166c  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140041672  mov     al, sil
0x140041675  jmp     short loc_1400416D6
0x140041677  mov     dword ptr [rbx+4A8h], 8004243Dh
0x140041681  jmp     short loc_1400416C9
0x140041683  mov     dword ptr [rbx+4A8h], 80042430h
0x14004168d  jmp     short loc_1400416C9
0x14004168f  mov     dword ptr [rbx+4A8h], 8004242Dh
0x140041699  jmp     short loc_1400416C9
0x14004169b  mov     dword ptr [rbx+4A8h], 8004242Ch
0x1400416a5  jmp     short loc_1400416C9
0x1400416a7  mov     dword ptr [rbx+4A8h], 8004242Fh
0x1400416b1  jmp     short loc_1400416C9
0x1400416b3  mov     dword ptr [rbx+4A8h], 8004242Eh
0x1400416bd  jmp     short loc_1400416C9
0x1400416bf  mov     dword ptr [rbx+4A8h], 80042429h
0x1400416c9  lea     rcx, [rsp+260h+var_240]
0x1400416ce  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400416d4  xor     al, al
0x1400416d6  mov     rcx, [rbp+160h+var_18]
0x1400416dd  xor     rcx, rsp; StackCookie
0x1400416e0  call    __security_check_cookie
0x1400416e5  lea     r11, [rsp+260h+var_10]
0x1400416ed  mov     rbx, [r11+20h]
0x1400416f1  mov     rsi, [r11+28h]
0x1400416f5  mov     rsp, r11
0x1400416f8  pop     r14
0x1400416fa  pop     rdi
0x1400416fb  pop     rbp
0x1400416fc  retn
```
