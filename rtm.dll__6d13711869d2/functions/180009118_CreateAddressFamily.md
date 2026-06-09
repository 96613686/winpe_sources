# CreateAddressFamily

- ea: `0x180009118`
- end: `0x1800094a0`
- name: `CreateAddressFamily`
- size: `904`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180009c74`

## callees

- `0x180001d80`
- `0x180004300`
- `0x180009118`
- `0x18000995c`
- `0x180009c18`
- `0x18001f980`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x180009317`
- `ntdll!RtlInitializeResource` at `0x180009375`
- `ntdll!RtlInitializeResource` at `0x180009317`
- `ntdll!RtlInitializeResource` at `0x180009375`
- `KERNEL32!HeapAlloc` at `0x1800091a5`
- `KERNEL32!HeapAlloc` at `0x1800092af`
- `KERNEL32!HeapAlloc` at `0x1800093bb`
- `KERNEL32!HeapAlloc` at `0x1800091a5`
- `KERNEL32!HeapAlloc` at `0x1800092af`
- `KERNEL32!HeapAlloc` at `0x1800093bb`
- `KERNEL32!GetProcessHeap` at `0x18000918d`
- `KERNEL32!GetProcessHeap` at `0x1800092a0`
- `KERNEL32!GetProcessHeap` at `0x1800093ac`
- `KERNEL32!GetProcessHeap` at `0x18000918d`
- `KERNEL32!GetProcessHeap` at `0x1800092a0`
- `KERNEL32!GetProcessHeap` at `0x1800093ac`
- `KERNEL32!InitializeCriticalSection` at `0x1800093d8`
- `KERNEL32!InitializeCriticalSection` at `0x180009411`
- `KERNEL32!InitializeCriticalSection` at `0x1800093d8`
- `KERNEL32!InitializeCriticalSection` at `0x180009411`
- `KERNEL32!GetLastError` at `0x18000934f`
- `KERNEL32!GetLastError` at `0x18000934f`
- `KERNEL32!CreateTimerQueue` at `0x18000933d`
- `KERNEL32!CreateTimerQueue` at `0x18000935c`
- `KERNEL32!CreateTimerQueue` at `0x18000933d`
- `KERNEL32!CreateTimerQueue` at `0x18000935c`

## pseudocode

```c
__int64 __fastcall CreateAddressFamily(_WORD *lpMem, unsigned __int16 a2, _QWORD *a3)
{
  unsigned int v6; // eax
  unsigned int v7; // edi
  HANDLE ProcessHeap; // rax
  char *v10; // rax
  char *v11; // rdi
  ULONG v12; // r8d
  __int64 i; // rax
  __int64 v14; // rdx
  ULONG v15; // eax
  unsigned int v16; // ebx
  HANDLE v17; // rax
  LPVOID v18; // rax
  DWORD Table; // esi
  __int64 j; // rdx
  __int64 v21; // rcx
  ALLOCATEMORE *v22; // r8
  FREEBUFFER *v23; // r9
  HANDLE TimerQueue; // rax
  HANDLE v25; // rax
  unsigned int v26; // eax
  unsigned int v27; // ebx
  HANDLE v28; // rax
  LPVOID v29; // rax
  __int64 k; // rbx
  char *v31; // rax
  void *lpvReserved; // [rsp+20h] [rbp-58h]
  ULONG ulTableType; // [rsp+28h] [rbp-50h]
  ULONG ulPropTagIndexColumn[4]; // [rsp+30h] [rbp-48h] BYREF
  LPTABLEDATA *lppTableData; // [rsp+40h] [rbp-38h]

  ulTableType = (unsigned int)a3;
  *(_OWORD *)ulPropTagIndexColumn = 0;
  lppTableData = 0;
  *a3 = 0;
  RtmReadAddressFamilyConfig(lpMem[2], a2, ulPropTagIndexColumn);
  v7 = v6;
  if ( v6 )
  {
    if ( !*((_DWORD *)lpMem + 6) && _InterlockedExchangeAdd((volatile signed __int32 *)lpMem, 0xFFFFFFFF) == 1 )
      DestroyInstance(lpMem);
    return v7;
  }
  ProcessHeap = GetProcessHeap();
  v10 = (char *)HeapAlloc(ProcessHeap, 8u, 0x8B8u);
  v11 = v10;
  lpvReserved = v10;
  if ( !v10 )
  {
    if ( !*((_DWORD *)lpMem + 6) && _InterlockedExchangeAdd((volatile signed __int32 *)lpMem, 0xFFFFFFFF) == 1 )
      DestroyInstance(lpMem);
    return 8;
  }
  _InterlockedAdd((volatile signed __int32 *)v10, 1u);
  *((_WORD *)v10 + 2) = a2;
  *((_DWORD *)v10 + 2) = ulPropTagIndexColumn[0];
  *((_QWORD *)v10 + 2) = lpMem;
  _InterlockedAdd((volatile signed __int32 *)lpMem, 1u);
  ++*((_DWORD *)lpMem + 6);
  *((_QWORD *)v10 + 4) = v10 + 24;
  *((_QWORD *)v10 + 3) = v10 + 24;
  *((_DWORD *)v10 + 10) = ulPropTagIndexColumn[1];
  v12 = ulPropTagIndexColumn[1];
  *((_DWORD *)v10 + 11) = 0;
  for ( i = 0; i != 32; ++i )
  {
    *(_DWORD *)&v11[4 * i + 48] = -1;
    *(_DWORD *)&v11[4 * i + 176] = -1;
  }
  v14 = 0;
  do
  {
    if ( !v12 )
      break;
    if ( (v12 & 1) != 0 )
    {
      *(_DWORD *)&v11[4 * *((unsigned int *)v11 + 11) + 48] = v14;
      *(_DWORD *)&v11[4 * v14 + 176] = (*((_DWORD *)v11 + 11))++;
    }
    v12 >>= 1;
    v14 = (unsigned int)(v14 + 1);
  }
  while ( (unsigned int)v14 < 0x20 );
  *((_DWORD *)v11 + 76) = (_DWORD)lppTableData;
  *((_DWORD *)v11 + 77) = ulPropTagIndexColumn[3];
  v15 = ulPropTagIndexColumn[2];
  *((_DWORD *)v11 + 78) = ulPropTagIndexColumn[2];
  *((_DWORD *)v11 + 79) = 0;
  if ( 8 * (unsigned __int64)v15 > 0xFFFFFFFF )
    goto LABEL_33;
  v16 = 8 * v15;
  v17 = GetProcessHeap();
  v18 = HeapAlloc(v17, 8u, v16);
  *((_QWORD *)v11 + 40) = v18;
  if ( v18 )
  {
    *((_DWORD *)v11 + 82) = 0;
    for ( j = 0; j != 16; ++j )
    {
      v21 = (__int64)&v11[16 * j + 336];
      *(_QWORD *)&v11[16 * j + 344] = v21;
      *(_QWORD *)&v11[16 * j + 336] = v21;
    }
    *((_QWORD *)v11 + 75) = v11 + 592;
    *((_QWORD *)v11 + 74) = v11 + 592;
    RtlInitializeResource((PRTL_RESOURCE)(v11 + 608));
    *((_DWORD *)v11 + 176) = 1;
    Table = CreateTable(
              (LPCIID)*((unsigned int *)v11 + 2),
              (ALLOCATEBUFFER *)(v11 + 712),
              v22,
              v23,
              lpvReserved,
              ulTableType,
              ulPropTagIndexColumn[0],
              *(LPSPropTagArray *)&ulPropTagIndexColumn[2],
              lppTableData);
    if ( Table )
      goto LABEL_34;
    TimerQueue = CreateTimerQueue();
    *((_QWORD *)v11 + 92) = TimerQueue;
    if ( !TimerQueue || (v25 = CreateTimerQueue(), (*((_QWORD *)v11 + 91) = v25) == 0) )
    {
      Table = GetLastError();
      goto LABEL_34;
    }
    RtlInitializeResource((PRTL_RESOURCE)(v11 + 744));
    *((_DWORD *)v11 + 210) = 1;
    v26 = HIDWORD(lppTableData);
    *((_DWORD *)v11 + 211) = HIDWORD(lppTableData);
    *((_DWORD *)v11 + 212) = 0;
    if ( 8 * (unsigned __int64)v26 <= 0xFFFFFFFF )
    {
      v27 = 8 * v26;
      v28 = GetProcessHeap();
      v29 = HeapAlloc(v28, 8u, v27);
      *((_QWORD *)v11 + 107) = v29;
      if ( v29 )
      {
        InitializeCriticalSection((LPCRITICAL_SECTION)(v11 + 1016));
        *((_DWORD *)v11 + 264) = 1;
        for ( k = 0; (unsigned int)k < 0x10; k = (unsigned int)(k + 1) )
        {
          v31 = &v11[72 * k + 1136];
          *(_QWORD *)v31 = v31;
          *(_QWORD *)&v11[72 * k + 1144] = v31;
          InitializeCriticalSection((LPCRITICAL_SECTION)&v11[72 * k + 1088]);
          *(_DWORD *)&v11[72 * k + 1128] = 1;
        }
        *a3 = v11;
        return 0;
      }
      goto LABEL_20;
    }
LABEL_33:
    Table = 534;
    goto LABEL_34;
  }
LABEL_20:
  Table = 8;
LABEL_34:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11, 0xFFFFFFFF) == 1 )
    DestroyAddressFamily(v11);
  return Table;
}

```

## disassembly

```asm
0x180009118  mov     [rsp+arg_18], rbx
0x18000911d  push    rsi
0x18000911e  push    rdi
0x18000911f  push    r12
0x180009121  push    r13
0x180009123  push    r15
0x180009125  sub     rsp, 50h
0x180009129  mov     rax, cs:__security_cookie
0x180009130  xor     rax, rsp
0x180009133  mov     [rsp+78h+var_30], rax
0x180009138  mov     r12, r8
0x18000913b  movzx   esi, dx
0x18000913e  mov     rbx, rcx
0x180009141  mov     qword ptr [rsp+78h+ulTableType], r8; ulTableType
0x180009146  xorps   xmm0, xmm0
0x180009149  xor     eax, eax
0x18000914b  movups  xmmword ptr [rsp+78h+ulPropTagIndexColumn], xmm0; ulPropTagIndexColumn
0x180009150  mov     [rsp+78h+lppTableData], rax; lppTableData
0x180009155  mov     [r8], rax
0x180009158  lea     r8, [rsp+78h+ulPropTagIndexColumn]
0x18000915d  movzx   ecx, word ptr [rcx+4]
0x180009161  call    RtmReadAddressFamilyConfig
0x180009166  mov     edi, eax
0x180009168  test    eax, eax
0x18000916a  jz      short loc_18000918D
0x18000916c  cmp     dword ptr [rbx+18h], 0
0x180009170  jnz     short loc_180009186
0x180009172  or      edx, 0FFFFFFFFh
0x180009175  lock xadd [rbx], edx
0x180009179  cmp     edx, 1
0x18000917c  jnz     short loc_180009186
0x18000917e  mov     rcx, rbx; lpMem
0x180009181  call    DestroyInstance
0x180009186  mov     eax, edi
0x180009188  jmp     loc_18000947E
0x18000918d  call    cs:__imp_GetProcessHeap
0x180009193  mov     rcx, rax; hHeap
0x180009196  mov     r8d, 8B8h; dwBytes
0x18000919c  mov     r15d, 8
0x1800091a2  mov     edx, r15d; dwFlags
0x1800091a5  call    cs:__imp_HeapAlloc
0x1800091ab  mov     rdi, rax
0x1800091ae  mov     [rsp+78h+lpvReserved], rax; lpvReserved
0x1800091b3  test    rax, rax
0x1800091b6  jnz     short loc_1800091D9
0x1800091b8  cmp     [rbx+18h], eax
0x1800091bb  jnz     short loc_1800091D1
0x1800091bd  or      ecx, 0FFFFFFFFh
0x1800091c0  lock xadd [rbx], ecx
0x1800091c4  cmp     ecx, 1
0x1800091c7  jnz     short loc_1800091D1
0x1800091c9  mov     rcx, rbx; lpMem
0x1800091cc  call    DestroyInstance
0x1800091d1  mov     eax, r15d
0x1800091d4  jmp     loc_18000947E
0x1800091d9  mov     r13d, 1
0x1800091df  lock add [rax], r13d
0x1800091e3  mov     [rax+4], si
0x1800091e7  mov     eax, [rsp+78h+ulPropTagIndexColumn]
0x1800091eb  mov     [rdi+8], eax
0x1800091ee  mov     [rdi+10h], rbx
0x1800091f2  lock add [rbx], r13d
0x1800091f6  add     [rbx+18h], r13d
0x1800091fa  lea     rax, [rdi+18h]
0x1800091fe  mov     [rax+8], rax
0x180009202  mov     [rax], rax
0x180009205  mov     eax, [rsp+78h+ulPropTagIndexColumn+4]
0x180009209  mov     [rdi+28h], eax
0x18000920c  mov     r8d, [rsp+78h+ulPropTagIndexColumn+4]
0x180009211  mov     dword ptr [rdi+2Ch], 0
0x180009218  xor     eax, eax
0x18000921a  mov     dword ptr [rdi+rax*4+30h], 0FFFFFFFFh
0x180009222  mov     dword ptr [rdi+rax*4+0B0h], 0FFFFFFFFh
0x18000922d  add     rax, r13
0x180009230  cmp     rax, 20h ; ' '
0x180009234  jnz     short loc_18000921A
0x180009236  xor     edx, edx
0x180009238  test    r8d, r8d
0x18000923b  jz      short loc_180009262
0x18000923d  test    r13b, r8b
0x180009240  jz      short loc_180009257
0x180009242  mov     eax, [rdi+2Ch]
0x180009245  mov     [rdi+rax*4+30h], edx
0x180009249  mov     eax, [rdi+2Ch]
0x18000924c  mov     [rdi+rdx*4+0B0h], eax
0x180009253  add     [rdi+2Ch], r13d
0x180009257  shr     r8d, 1
0x18000925a  add     edx, r13d
0x18000925d  cmp     edx, 20h ; ' '
0x180009260  jb      short loc_180009238
0x180009262  mov     eax, dword ptr [rsp+78h+lppTableData]
0x180009266  mov     [rdi+130h], eax
0x18000926c  mov     eax, [rsp+78h+ulPropTagIndexColumn+0Ch]
0x180009270  mov     [rdi+134h], eax
0x180009276  mov     eax, [rsp+78h+ulPropTagIndexColumn+8]
0x18000927a  mov     [rdi+138h], eax
0x180009280  mov     dword ptr [rdi+13Ch], 0
0x18000928a  mov     ecx, eax
0x18000928c  shl     rcx, 3
0x180009290  mov     eax, 0FFFFFFFFh
0x180009295  cmp     rcx, rax
0x180009298  ja      loc_180009463
0x18000929e  mov     ebx, ecx
0x1800092a0  call    cs:__imp_GetProcessHeap
0x1800092a6  mov     rcx, rax; hHeap
0x1800092a9  mov     r8d, ebx; dwBytes
0x1800092ac  mov     edx, r15d; dwFlags
0x1800092af  call    cs:__imp_HeapAlloc
0x1800092b5  mov     [rdi+140h], rax
0x1800092bc  test    rax, rax
0x1800092bf  jnz     short loc_1800092C9
0x1800092c1  mov     esi, r15d
0x1800092c4  jmp     loc_180009468
0x1800092c9  mov     dword ptr [rdi+148h], 0
0x1800092d3  xor     edx, edx
0x1800092d5  mov     rax, rdx
0x1800092d8  shl     rax, 4
0x1800092dc  lea     rcx, [rdi+150h]
0x1800092e3  add     rcx, rax
0x1800092e6  mov     [rax+rdi+158h], rcx
0x1800092ee  lea     rax, [rdx+15h]
0x1800092f2  add     rax, rax
0x1800092f5  mov     [rdi+rax*8], rcx
0x1800092f9  add     rdx, r13
0x1800092fc  cmp     rdx, 10h
0x180009300  jnz     short loc_1800092D5
0x180009302  lea     rax, [rdi+250h]
0x180009309  mov     [rax+8], rax
0x18000930d  mov     [rax], rax
0x180009310  lea     rcx, [rdi+260h]; Resource
0x180009317  call    cs:__imp_RtlInitializeResource
0x18000931d  mov     [rdi+2C0h], r13d
0x180009324  lea     rdx, [rdi+2C8h]; lpAllocateBuffer
0x18000932b  mov     ecx, [rdi+8]; lpInterface
0x18000932e  call    CreateTable
0x180009333  mov     esi, eax
0x180009335  test    eax, eax
0x180009337  jnz     loc_180009468
0x18000933d  call    cs:__imp_CreateTimerQueue
0x180009343  mov     [rdi+2E0h], rax
0x18000934a  test    rax, rax
0x18000934d  jnz     short loc_18000935C
0x18000934f  call    cs:__imp_GetLastError
0x180009355  mov     esi, eax
0x180009357  jmp     loc_180009468
0x18000935c  call    cs:__imp_CreateTimerQueue
0x180009362  mov     [rdi+2D8h], rax
0x180009369  test    rax, rax
0x18000936c  jz      short loc_18000934F
0x18000936e  lea     rcx, [rdi+2E8h]; Resource
0x180009375  call    cs:__imp_RtlInitializeResource
0x18000937b  mov     [rdi+348h], r13d
0x180009382  mov     eax, dword ptr [rsp+78h+lppTableData+4]
0x180009386  mov     [rdi+34Ch], eax
0x18000938c  mov     dword ptr [rdi+350h], 0
0x180009396  mov     ecx, eax
0x180009398  shl     rcx, 3
0x18000939c  mov     eax, 0FFFFFFFFh
0x1800093a1  cmp     rcx, rax
0x1800093a4  ja      loc_180009463
0x1800093aa  mov     ebx, ecx
0x1800093ac  call    cs:__imp_GetProcessHeap
0x1800093b2  mov     rcx, rax; hHeap
0x1800093b5  mov     r8d, ebx; dwBytes
0x1800093b8  mov     edx, r15d; dwFlags
0x1800093bb  call    cs:__imp_HeapAlloc
0x1800093c1  mov     [rdi+358h], rax
0x1800093c8  test    rax, rax
0x1800093cb  jz      loc_1800092C1
0x1800093d1  lea     rcx, [rdi+3F8h]; lpCriticalSection
0x1800093d8  call    cs:__imp_InitializeCriticalSection
0x1800093de  mov     [rdi+420h], r13d
0x1800093e5  xor     ebx, ebx
0x1800093e7  cmp     ebx, 10h
0x1800093ea  jnb     short loc_180009433
0x1800093ec  lea     r15, [rbx+rbx*8]
0x1800093f0  lea     rax, [rdi+470h]
0x1800093f7  lea     rax, [rax+r15*8]
0x1800093fb  mov     [rax], rax
0x1800093fe  mov     [rdi+r15*8+478h], rax
0x180009406  lea     rcx, [rdi+440h]
0x18000940d  lea     rcx, [rcx+r15*8]; lpCriticalSection
0x180009411  call    cs:__imp_InitializeCriticalSection
0x180009417  mov     [rdi+r15*8+468h], r13d
0x18000941f  add     ebx, r13d
0x180009422  jmp     short loc_1800093E7
0x180009424  mov     esi, 8
0x180009429  mov     rdi, [rsp+78h+lpvReserved]
0x18000942e  mov     r12, qword ptr [rsp+78h+ulTableType]
0x180009433  test    esi, esi
0x180009435  jnz     short loc_180009468
0x180009437  mov     [r12], rdi
0x18000943b  xor     eax, eax
0x18000943d  jmp     short loc_18000947E
0x18000943f  mov     esi, 8
0x180009444  mov     rdi, [rsp+78h+lpvReserved]
0x180009449  jmp     short loc_180009468
0x18000944b  mov     esi, 8
0x180009450  mov     rdi, [rsp+78h+lpvReserved]
0x180009455  jmp     short loc_180009468
0x180009457  mov     esi, 8
0x18000945c  mov     rdi, [rsp+78h+lpvReserved]
0x180009461  jmp     short loc_180009468
0x180009463  mov     esi, 216h
0x180009468  or      eax, 0FFFFFFFFh
0x18000946b  lock xadd [rdi], eax
0x18000946f  cmp     eax, 1
0x180009472  jnz     short loc_18000947C
0x180009474  mov     rcx, rdi; lpMem
0x180009477  call    DestroyAddressFamily
0x18000947c  mov     eax, esi
0x18000947e  mov     rcx, [rsp+78h+var_30]
0x180009483  xor     rcx, rsp; StackCookie
0x180009486  call    __security_check_cookie
0x18000948b  mov     rbx, [rsp+78h+arg_18]
0x180009493  add     rsp, 50h
0x180009497  pop     r15
0x180009499  pop     r13
0x18000949b  pop     r12
0x18000949d  pop     rdi
0x18000949e  pop     rsi
0x18000949f  retn
```
