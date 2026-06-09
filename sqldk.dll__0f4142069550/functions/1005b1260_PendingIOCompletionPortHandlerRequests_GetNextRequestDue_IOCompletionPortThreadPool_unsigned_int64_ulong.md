# PendingIOCompletionPortHandlerRequests::GetNextRequestDue(IOCompletionPortThreadPool *,unsigned __int64 *,ulong *)

- ea: `0x1005b1260`
- end: `0x1005b1508`
- name: `?GetNextRequestDue@PendingIOCompletionPortHandlerRequests@@QEAAXPEAVIOCompletionPortThreadPool@@PEA_KPEAK@Z`
- size: `680`
- prototype: `void __fastcall(PendingIOCompletionPortHandlerRequests *__hidden this, struct IOCompletionPortThreadPool *, unsigned __int64 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1005b1510`

## callees

- `0x1005b1260`
- `0x1005b1fc0`

## import_xrefs

- `KERNEL32!PostQueuedCompletionStatus` at `0x1005b13e7`
- `KERNEL32!PostQueuedCompletionStatus` at `0x1005b13e7`
- `KERNEL32!QueryPerformanceCounter` at `0x1005b1322`
- `KERNEL32!QueryPerformanceCounter` at `0x1005b1322`
- `KERNEL32!GetLastError` at `0x1005b13f1`
- `KERNEL32!GetLastError` at `0x1005b13f1`

## string_xrefs

- `0x1005b12a0`: `"Sql\\Common\\src\\IOCompletionPortThreadPool.cpp"`
- `0x1005b12cc`: `"Sql\\Common\\src\\IOCompletionPortThreadPool.cpp"`
- `0x1005b1409`: `"Sql\\Common\\src\\IOCompletionPortThreadPool.cpp"`
- `0x1005b1454`: `"Sql\\Common\\src\\IOCompletionPortThreadPool.cpp"`
- `0x1005b147d`: `"Sql\\Common\\src\\IOCompletionPortThreadPool.cpp"`
- `0x1005b14b0`: `"Sql\\Common\\src\\IOCompletionPortThreadPool.cpp"`
- `0x1005b14d8`: `"Sql\\Common\\src\\IOCompletionPortThreadPool.cpp"`
- `0x1005b1460`: `0 != *compKey`

## pseudocode

```c
void __fastcall PendingIOCompletionPortHandlerRequests::GetNextRequestDue(
        PendingIOCompletionPortHandlerRequests *this,
        HANDLE *a2,
        unsigned __int64 *a3,
        unsigned int *a4)
{
  char v8; // al
  LARGE_INTEGER v9; // rdi
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  ULONG_PTR v12; // r8
  PendingIOCompletionPortHandlerRequests *v13; // r14
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rax
  ULONG_PTR v16; // rbp
  int v17; // eax
  LARGE_INTEGER PerformanceCount; // [rsp+60h] [rbp+8h] BYREF

  *a3 = 0;
  *a4 = -1;
  v8 = *((_BYTE *)this + 20);
  if ( *((_DWORD *)this + 4) )
  {
    if ( v8 )
    {
      *a4 = 1;
      *((_BYTE *)this + 20) = 0;
    }
    else
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&PerformanceCount);
        v9 = PerformanceCount;
      }
      else
      {
        v9.QuadPart = MEMORY[0x7FFE0008];
      }
      v10 = *((_QWORD *)this + 1);
      if ( v10 <= v9.QuadPart )
      {
        v12 = *(_QWORD *)this;
        v13 = this;
        v14 = -1;
        if ( *(_QWORD *)this )
        {
          do
          {
            v15 = *(_QWORD *)(v12 + 8);
            v16 = *(_QWORD *)(v12 + 16);
            if ( v9.QuadPart < v15 )
            {
              v13 = (PendingIOCompletionPortHandlerRequests *)(v12 + 16);
              if ( v14 <= v15 )
                v15 = v14;
              v14 = v15;
            }
            else
            {
              *(_QWORD *)v13 = v16;
              *(_QWORD *)(v12 + 16) = 0;
              if ( *a3 )
              {
                if ( !PostQueuedCompletionStatus(a2[1], 0, v12, 0) )
                  GetLastError();
              }
              else
              {
                *a3 = v12;
              }
              v17 = *((_DWORD *)this + 4);
              if ( !v17 )
              {
                utassert_fail(
                  1u,
                  "PendingCount > 0",
                  "\"Sql\\\\Common\\\\src\\\\IOCompletionPortThreadPool.cpp\"",
                  610,
                  0);
                v17 = *((_DWORD *)this + 4);
              }
              *((_DWORD *)this + 4) = v17 - 1;
            }
            v12 = v16;
          }
          while ( v16 );
        }
        if ( !*a3 )
          utassert_fail(1u, "0 != *compKey", "\"Sql\\\\Common\\\\src\\\\IOCompletionPortThreadPool.cpp\"", 626, 0);
        if ( v14 < *((_QWORD *)this + 1) )
          utassert_fail(
            1u,
            "lowest.IsGreaterOrEqual(LowestWaitUntil)",
            "\"Sql\\\\Common\\\\src\\\\IOCompletionPortThreadPool.cpp\"",
            627,
            0);
        *((_QWORD *)this + 1) = v14;
        if ( !*((_DWORD *)this + 4) )
        {
          if ( v14 != -1 )
            utassert_fail(
              1u,
              "LowestWaitUntil.IsEqual(SOS_TicksFast64::Infinite())",
              "\"Sql\\\\Common\\\\src\\\\IOCompletionPortThreadPool.cpp\"",
              632,
              0);
          if ( *(_QWORD *)this )
            utassert_fail(1u, "First == nullptr", "\"Sql\\\\Common\\\\src\\\\IOCompletionPortThreadPool.cpp\"", 633, 0);
        }
      }
      else
      {
        v11 = v10 - v9.QuadPart;
        if ( v11 == -1 )
        {
          *a4 = -1;
        }
        else if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          *a4 = 1000 * v11 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
        }
        else
        {
          *a4 = v11 / 0x2710;
        }
      }
    }
  }
  else
  {
    if ( v8 )
      utassert_fail(1u, "!RequestJustAdded", "\"Sql\\\\Common\\\\src\\\\IOCompletionPortThreadPool.cpp\"", 556, 0);
    if ( *(_QWORD *)this )
      utassert_fail(1u, "nullptr == First", "\"Sql\\\\Common\\\\src\\\\IOCompletionPortThreadPool.cpp\"", 558, 0);
  }
}

```

## disassembly

```asm
0x1005b1260  push    rsi
0x1005b1262  push    r12
0x1005b1264  push    r13
0x1005b1266  push    r14
0x1005b1268  push    r15
0x1005b126a  sub     rsp, 30h
0x1005b126e  xor     r12d, r12d
0x1005b1271  mov     r14, r9
0x1005b1274  mov     [r8], r12
0x1005b1277  mov     r15, r8
0x1005b127a  mov     dword ptr [r9], 0FFFFFFFFh
0x1005b1281  mov     r13, rdx
0x1005b1284  mov     rsi, rcx
0x1005b1287  movzx   eax, byte ptr [rcx+14h]
0x1005b128b  cmp     [rcx+10h], r12d
0x1005b128f  jnz     short loc_1005B12F2
0x1005b1291  test    al, al
0x1005b1293  jz      short loc_1005B12B8
0x1005b1295  mov     r9d, 22Ch; int
0x1005b129b  mov     [rsp+58h+Format], r12; Format
0x1005b12a0  lea     r8, aSqlCommonSrcIo_0; "\"Sql\\\\Common\\\\src\\\\IOCompletionP"...
0x1005b12a7  lea     rdx, aRequestjustadd; "!RequestJustAdded"
0x1005b12ae  lea     ecx, [r12+1]; unsigned int
0x1005b12b3  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1005b12b8  cmp     [rsi], r12
0x1005b12bb  jz      loc_1005B14FA
0x1005b12c1  mov     r9d, 22Eh; int
0x1005b12c7  mov     [rsp+58h+Format], r12; Format
0x1005b12cc  lea     r8, aSqlCommonSrcIo_0; "\"Sql\\\\Common\\\\src\\\\IOCompletionP"...
0x1005b12d3  mov     ecx, 1; unsigned int
0x1005b12d8  lea     rdx, aNullptrFirst; "nullptr == First"
0x1005b12df  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1005b12e4  add     rsp, 30h
0x1005b12e8  pop     r15
0x1005b12ea  pop     r14
0x1005b12ec  pop     r13
0x1005b12ee  pop     r12
0x1005b12f0  pop     rsi
0x1005b12f1  retn
0x1005b12f2  test    al, al
0x1005b12f4  jz      short loc_1005B130F
0x1005b12f6  mov     dword ptr [r9], 1
0x1005b12fd  mov     [rcx+14h], r12b
0x1005b1301  add     rsp, 30h
0x1005b1305  pop     r15
0x1005b1307  pop     r14
0x1005b1309  pop     r13
0x1005b130b  pop     r12
0x1005b130d  pop     rsi
0x1005b130e  retn
0x1005b130f  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, r12d; int Base_PublicGlobals::sm_invariantTscAvailable
0x1005b1316  mov     [rsp+58h+arg_18], rdi
0x1005b131b  jz      short loc_1005B132F
0x1005b131d  lea     rcx, [rsp+58h+PerformanceCount]; lpPerformanceCount
0x1005b1322  call    cs:__imp_QueryPerformanceCounter
0x1005b1328  mov     rdi, qword ptr [rsp+58h+PerformanceCount]
0x1005b132d  jmp     short loc_1005B1337
0x1005b132f  mov     rdi, ds:7FFE0008h
0x1005b1337  mov     rcx, [rsi+8]
0x1005b133b  mov     [rsp+58h+arg_8], rbx
0x1005b1340  cmp     rcx, rdi
0x1005b1343  jbe     short loc_1005B1399
0x1005b1345  sub     rcx, rdi
0x1005b1348  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1005b134c  jnz     short loc_1005B1359
0x1005b134e  mov     rbx, rcx
0x1005b1351  mov     [r14], ebx
0x1005b1354  jmp     loc_1005B14F0
0x1005b1359  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, r12d; int Base_PublicGlobals::sm_invariantTscAvailable
0x1005b1360  jz      short loc_1005B137D
0x1005b1362  imul    rax, rcx, 3E8h
0x1005b1369  xor     edx, edx
0x1005b136b  div     cs:?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x1005b1372  mov     rbx, rax
0x1005b1375  mov     [r14], ebx
0x1005b1378  jmp     loc_1005B14F0
0x1005b137d  mov     rax, 346DC5D63886594Bh
0x1005b1387  mul     rcx
0x1005b138a  mov     rbx, rdx
0x1005b138d  shr     rbx, 0Bh
0x1005b1391  mov     [r14], ebx
0x1005b1394  jmp     loc_1005B14F0
0x1005b1399  mov     r8, [rsi]; dwCompletionKey
0x1005b139c  mov     r14, rsi
0x1005b139f  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1005b13a6  test    r8, r8
0x1005b13a9  jz      loc_1005B1444
0x1005b13af  mov     [rsp+58h+arg_10], rbp
0x1005b13b4  nop     dword ptr [rax+00h]
0x1005b13b8  nop     dword ptr [rax+rax+00000000h]
0x1005b13c0  mov     rax, [r8+8]
0x1005b13c4  mov     rbp, [r8+10h]
0x1005b13c8  cmp     rdi, rax
0x1005b13cb  jb      short loc_1005B1429
0x1005b13cd  mov     [r14], rbp
0x1005b13d0  mov     [r8+10h], r12
0x1005b13d4  cmp     [r15], r12
0x1005b13d7  jnz     short loc_1005B13DE
0x1005b13d9  mov     [r15], r8
0x1005b13dc  jmp     short loc_1005B13F7
0x1005b13de  mov     rcx, [r13+8]; CompletionPort
0x1005b13e2  xor     r9d, r9d; lpOverlapped
0x1005b13e5  xor     edx, edx; dwNumberOfBytesTransferred
0x1005b13e7  call    cs:__imp_PostQueuedCompletionStatus
0x1005b13ed  test    eax, eax
0x1005b13ef  jnz     short loc_1005B13F7
0x1005b13f1  call    cs:__imp_GetLastError
0x1005b13f7  mov     eax, [rsi+10h]
0x1005b13fa  test    eax, eax
0x1005b13fc  jnz     short loc_1005B1422
0x1005b13fe  mov     r9d, 262h; int
0x1005b1404  mov     [rsp+58h+Format], r12; Format
0x1005b1409  lea     r8, aSqlCommonSrcIo_0; "\"Sql\\\\Common\\\\src\\\\IOCompletionP"...
0x1005b1410  lea     rdx, aPendingcount0; "PendingCount > 0"
0x1005b1417  lea     ecx, [rax+1]; unsigned int
0x1005b141a  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1005b141f  mov     eax, [rsi+10h]
0x1005b1422  dec     eax
0x1005b1424  mov     [rsi+10h], eax
0x1005b1427  jmp     short loc_1005B1437
0x1005b1429  cmp     rbx, rax
0x1005b142c  lea     r14, [r8+10h]
0x1005b1430  cmovbe  rax, rbx
0x1005b1434  mov     rbx, rax
0x1005b1437  mov     r8, rbp
0x1005b143a  test    rbp, rbp
0x1005b143d  jnz     short loc_1005B13C0
0x1005b143f  mov     rbp, [rsp+58h+arg_10]
0x1005b1444  cmp     [r15], r12
0x1005b1447  jnz     short loc_1005B146C
0x1005b1449  mov     r9d, 272h; int
0x1005b144f  mov     [rsp+58h+Format], r12; Format
0x1005b1454  lea     r8, aSqlCommonSrcIo_0; "\"Sql\\\\Common\\\\src\\\\IOCompletionP"...
0x1005b145b  mov     ecx, 1; unsigned int
0x1005b1460  lea     rdx, a0Compkey; "0 != *compKey"
0x1005b1467  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1005b146c  cmp     rbx, [rsi+8]
0x1005b1470  jnb     short loc_1005B1495
0x1005b1472  mov     r9d, 273h; int
0x1005b1478  mov     [rsp+58h+Format], r12; Format
0x1005b147d  lea     r8, aSqlCommonSrcIo_0; "\"Sql\\\\Common\\\\src\\\\IOCompletionP"...
0x1005b1484  mov     ecx, 1; unsigned int
0x1005b1489  lea     rdx, aLowestIsgreate; "lowest.IsGreaterOrEqual(LowestWaitUntil"...
0x1005b1490  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1005b1495  mov     [rsi+8], rbx
0x1005b1499  cmp     [rsi+10h], r12d
0x1005b149d  jnz     short loc_1005B14F0
0x1005b149f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1005b14a3  jz      short loc_1005B14C8
0x1005b14a5  mov     r9d, 278h; int
0x1005b14ab  mov     [rsp+58h+Format], r12; Format
0x1005b14b0  lea     r8, aSqlCommonSrcIo_0; "\"Sql\\\\Common\\\\src\\\\IOCompletionP"...
0x1005b14b7  mov     ecx, 1; unsigned int
0x1005b14bc  lea     rdx, aLowestwaitunti; "LowestWaitUntil.IsEqual(SOS_TicksFast64"...
0x1005b14c3  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1005b14c8  cmp     [rsi], r12
0x1005b14cb  jz      short loc_1005B14F0
0x1005b14cd  mov     r9d, 279h; int
0x1005b14d3  mov     [rsp+58h+Format], r12; Format
0x1005b14d8  lea     r8, aSqlCommonSrcIo_0; "\"Sql\\\\Common\\\\src\\\\IOCompletionP"...
0x1005b14df  mov     ecx, 1; unsigned int
0x1005b14e4  lea     rdx, aFirstNullptr; "First == nullptr"
0x1005b14eb  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1005b14f0  mov     rbx, [rsp+58h+arg_8]
0x1005b14f5  mov     rdi, [rsp+58h+arg_18]
0x1005b14fa  add     rsp, 30h
0x1005b14fe  pop     r15
0x1005b1500  pop     r14
0x1005b1502  pop     r13
0x1005b1504  pop     r12
0x1005b1506  pop     rsi
0x1005b1507  retn
```
