# CreateEntity

- ea: `0x1800094a8`
- end: `0x180009953`
- name: `CreateEntity`
- size: `1195`
- prototype: `__int64 __usercall@<rax>(LPVOID lpMem@<rcx>, __int64, LPTABLEDATA *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000aef0`

## callees

- `0x180001d80`
- `0x180002cb0`
- `0x1800094a8`
- `0x18000995c`
- `0x180009adc`
- `0x180009d14`
- `0x18001f7e8`
- `0x18001f946`
- `0x18001f952`
- `0x18001f980`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x18000980e`
- `ntdll!RtlInitializeResource` at `0x180009842`
- `ntdll!RtlInitializeResource` at `0x180009875`
- `ntdll!RtlInitializeResource` at `0x18000980e`
- `ntdll!RtlInitializeResource` at `0x180009842`
- `ntdll!RtlInitializeResource` at `0x180009875`
- `KERNEL32!HeapAlloc` at `0x1800095c4`
- `KERNEL32!HeapAlloc` at `0x1800095c4`
- `KERNEL32!GetProcessHeap` at `0x1800095b1`
- `KERNEL32!GetProcessHeap` at `0x1800095b1`
- `KERNEL32!InitializeCriticalSection` at `0x180009821`
- `KERNEL32!InitializeCriticalSection` at `0x180009821`

## string_xrefs

- `0x180009657`: `CreateEntity: ReserveOpaquePtr is passed as true, Address Family Instance %d`
- `0x1800096ef`: `CreateEntity: NumOpaquePtrs(%d) >= MaxOpaquePtrs(%d). Address Family Instance %d. Returning error`
- `0x1800097a3`: `CreateEntity: Incrementing NumOpaquePointers. Current count = %d, Address Family Instace: %d`

## pseudocode

```c
void __fastcall CreateEntity(_QWORD *lpMem, struct _SPropTagArray *a2, int a3, ULONG *a4, __int64 a5, LPTABLEDATA *a6)
{
  int v10; // eax
  ULONG v11; // r14d
  unsigned __int64 v12; // rbx
  HANDLE ProcessHeap; // rax
  struct _SPropTagArray *v14; // rax
  struct _SPropTagArray *v15; // rbx
  char v16; // al
  __int128 *v17; // r9
  unsigned int v18; // edx
  __int64 v19; // r8
  __int128 *v20; // r9
  unsigned int i; // esi
  __int128 *v22; // r9
  ALLOCATEMORE *v23; // r8
  FREEBUFFER *v24; // r9
  void *lpvReserved; // [rsp+20h] [rbp-898h]
  ULONG ulTableType; // [rsp+28h] [rbp-890h]
  ULONG uliInst[2]; // [rsp+30h] [rbp-888h] BYREF
  LPSPropTagArray lpSPropTagArrayColumns; // [rsp+38h] [rbp-880h]
  LPTABLEDATA *lppTableData; // [rsp+40h] [rbp-878h]
  __int128 v30; // [rsp+48h] [rbp-870h] BYREF
  ULONG v31; // [rsp+58h] [rbp-860h] BYREF
  __int128 v32; // [rsp+5Ch] [rbp-85Ch]
  __int128 v33; // [rsp+6Ch] [rbp-84Ch]
  int v34; // [rsp+7Ch] [rbp-83Ch]
  int v35; // [rsp+80h] [rbp-838h] BYREF
  char v36[2044]; // [rsp+84h] [rbp-834h] BYREF

  lppTableData = a6;
  *(_QWORD *)uliInst = 0;
  v35 = 0;
  memset_0(v36, 0, sizeof(v36));
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v30 = 0;
  *a6 = 0;
  GetInstance((LPSPropValue)*(unsigned __int16 *)(lpMem[2] + 4LL), 0, (ULONG)uliInst);
  if ( v10 )
    return;
  if ( a4 )
    v11 = *a4;
  else
    v11 = 0;
  v12 = 8LL * (v11 != 0 ? v11 - 1 : 0);
  if ( v12 > 0xFFFFFFFF )
  {
    if ( !*((_DWORD *)lpMem + 82) && _InterlockedExchangeAdd((volatile signed __int32 *)lpMem, 0xFFFFFFFF) == 1 )
      DestroyAddressFamily((char *)lpMem);
  }
  else if ( (int)v12 + 472 < (unsigned int)v12 )
  {
    if ( !*((_DWORD *)lpMem + 82) && _InterlockedExchangeAdd((volatile signed __int32 *)lpMem, 0xFFFFFFFF) == 1 )
      DestroyAddressFamily((char *)lpMem);
  }
  else
  {
    ProcessHeap = GetProcessHeap();
    v14 = (struct _SPropTagArray *)HeapAlloc(ProcessHeap, 8u, (unsigned int)(v12 + 472));
    v15 = v14;
    lpSPropTagArrayColumns = v14;
    if ( !v14 )
    {
      if ( !*((_DWORD *)lpMem + 82) && _InterlockedExchangeAdd((volatile signed __int32 *)lpMem, 0xFFFFFFFF) == 1 )
        DestroyAddressFamily((char *)lpMem);
      return;
    }
    _InterlockedAdd((volatile signed __int32 *)v14, 1u);
    v14[1] = a2[1];
    v14[2] = (struct _SPropTagArray)lpMem;
    _InterlockedAdd((volatile signed __int32 *)lpMem, 1u);
    ++*((_DWORD *)lpMem + 82);
    v14[4] = (struct _SPropTagArray)&v14[3];
    v14[3] = (struct _SPropTagArray)&v14[3];
    v14[6].aulPropTag[0] = -1;
    if ( a3 )
    {
      v16 = byte_18002BD1A;
      if ( (byte_18002BD1A & 8) != 0 )
      {
        LOWORD(v35) = 0;
        LOWORD(v31) = 0;
        FormatRRASErrorString(
          &v35,
          L"CreateEntity: ReserveOpaquePtr is passed as true, Address Family Instance %d",
          *(unsigned __int16 *)(lpMem[2] + 4LL));
        v16 = byte_18002BD1A;
        if ( (byte_18002BD1A & 8) != 0 )
        {
          v17 = &v30;
          if ( *(_QWORD *)uliInst != -48 )
            LODWORD(v17) = uliInst[0] + 48;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
            (unsigned int)&v35,
            (_DWORD)v17,
            0,
            (__int64)&v31);
          v16 = byte_18002BD1A;
        }
      }
      v18 = *((_DWORD *)lpMem + 78);
      v19 = *((unsigned int *)lpMem + 79);
      if ( (unsigned int)v19 >= v18 )
      {
        if ( (v16 & 0x10) != 0 )
        {
          LOWORD(v35) = 0;
          LOWORD(v31) = 0;
          LODWORD(lpvReserved) = *(unsigned __int16 *)(lpMem[2] + 4LL);
          FormatRRASErrorString(
            &v35,
            L"CreateEntity: NumOpaquePtrs(%d) >= MaxOpaquePtrs(%d). Address Family Instance %d. Returning error",
            v19,
            v18,
            lpvReserved);
          if ( (byte_18002BD1A & 0x10) != 0 )
          {
            v20 = &v30;
            if ( *(_QWORD *)uliInst != -48 )
              LODWORD(v20) = uliInst[0] + 48;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RRAS_RTM_PARAM_TRACE_ERROR,
              (unsigned int)&v35,
              (_DWORD)v20,
              0,
              (__int64)&v31);
          }
        }
        goto LABEL_43;
      }
      for ( i = 0; i < v18; ++i )
      {
        if ( !*(_QWORD *)(lpMem[40] + 8LL * i) )
          break;
      }
      *(_QWORD *)(lpMem[40] + 8LL * i) = v15;
      if ( (byte_18002BD1A & 8) != 0 )
      {
        LOWORD(v35) = 0;
        LOWORD(v31) = 0;
        FormatRRASErrorString(
          &v35,
          L"CreateEntity: Incrementing NumOpaquePointers. Current count = %d, Address Family Instace: %d",
          *((unsigned int *)lpMem + 79),
          *(unsigned __int16 *)(lpMem[2] + 4LL));
        if ( (byte_18002BD1A & 8) != 0 )
        {
          v22 = &v30;
          if ( *(_QWORD *)uliInst != -48 )
            LODWORD(v22) = uliInst[0] + 48;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
            (unsigned int)&v35,
            (_DWORD)v22,
            0,
            (__int64)&v31);
        }
      }
      ++*((_DWORD *)lpMem + 79);
      v15[6].aulPropTag[0] = i;
    }
    RtlInitializeResource((PRTL_RESOURCE)&v15[7]);
    v15[19].cValues = 1;
    InitializeCriticalSection((LPCRITICAL_SECTION)&v15[20]);
    v15[25].cValues = 1;
    v15[27] = (struct _SPropTagArray)&v15[26];
    v15[26] = (struct _SPropTagArray)&v15[26];
    RtlInitializeResource((PRTL_RESOURCE)&v15[28]);
    v15[40].cValues = 1;
    if ( CreateTable(
           (LPCIID)*((unsigned int *)lpMem + 2),
           (ALLOCATEBUFFER *)&v15[41],
           v23,
           v24,
           lpvReserved,
           ulTableType,
           uliInst[0],
           lpSPropTagArrayColumns,
           lppTableData) )
    {
LABEL_43:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15, 0xFFFFFFFF) == 1 )
        DestroyEntity((char *)v15);
      return;
    }
    v15[42].cValues = 0;
    RtlInitializeResource((PRTL_RESOURCE)&v15[43]);
    v15[55].cValues = 1;
    v15[56] = (struct _SPropTagArray)a5;
    v15[57].cValues = v11;
    if ( a4 )
      memcpy_0(&v15[58], a4 + 2, 8LL * v11);
    *lppTableData = (LPTABLEDATA)v15;
  }
}

```

## disassembly

```asm
0x1800094a8  mov     [rsp+arg_8], rbx
0x1800094ad  mov     [rsp+arg_10], rsi
0x1800094b2  push    rdi
0x1800094b3  push    r12
0x1800094b5  push    r13
0x1800094b7  push    r14
0x1800094b9  push    r15
0x1800094bb  sub     rsp, 890h
0x1800094c2  mov     rax, cs:__security_cookie
0x1800094c9  xor     rax, rsp
0x1800094cc  mov     [rsp+8B8h+var_38], rax
0x1800094d4  mov     r15, r9
0x1800094d7  mov     r12d, r8d
0x1800094da  mov     r13, rdx
0x1800094dd  mov     rdi, rcx
0x1800094e0  mov     rbx, [rsp+8B8h+arg_28]
0x1800094e8  mov     [rsp+8B8h+lppTableData], rbx; lppTableData
0x1800094ed  xor     esi, esi
0x1800094ef  mov     qword ptr [rsp+8B8h+uliInst], rsi; ulPropTagIndexColumn
0x1800094f4  mov     [rsp+8B8h+var_838], esi
0x1800094fb  xor     edx, edx; Val
0x1800094fd  mov     r8d, 7FCh; Size
0x180009503  lea     rcx, [rsp+8B8h+var_834]; void *
0x18000950b  call    memset_0
0x180009510  mov     [rsp+8B8h+var_860], esi
0x180009514  xorps   xmm0, xmm0
0x180009517  xor     eax, eax
0x180009519  movups  [rsp+8B8h+var_85C], xmm0
0x18000951e  movups  [rsp+8B8h+var_84C], xmm0
0x180009523  mov     [rsp+8B8h+var_83C], eax
0x180009527  movups  [rsp+8B8h+var_870], xmm0
0x18000952c  mov     [rbx], rsi
0x18000952f  mov     rcx, [rdi+10h]
0x180009533  lea     r8, [rsp+8B8h+uliInst]; uliInst
0x180009538  xor     edx, edx; lpPropSv
0x18000953a  movzx   ecx, word ptr [rcx+4]; lpPropMv
0x18000953e  call    GetInstance
0x180009543  test    eax, eax
0x180009545  jnz     loc_180009926
0x18000954b  test    r15, r15
0x18000954e  jz      short loc_180009555
0x180009550  mov     r14d, [r15]
0x180009553  jmp     short loc_180009558
0x180009555  mov     r14d, esi
0x180009558  mov     eax, r14d
0x18000955b  lea     ebx, [r14-1]
0x18000955f  neg     eax
0x180009561  sbb     ecx, ecx
0x180009563  and     ebx, ecx
0x180009565  shl     rbx, 3
0x180009569  mov     eax, 0FFFFFFFFh
0x18000956e  cmp     rbx, rax
0x180009571  ja      loc_180009905
0x180009577  lea     esi, [rbx+1D8h]
0x18000957d  cmp     esi, ebx
0x18000957f  cmovnb  eax, esi
0x180009582  jnb     short loc_1800095AF
0x180009584  cmp     dword ptr [rdi+148h], 0
0x18000958b  jnz     short loc_1800095A1
0x18000958d  or      eax, 0FFFFFFFFh
0x180009590  lock xadd [rdi], eax
0x180009594  cmp     eax, 1
0x180009597  jnz     short loc_1800095A1
0x180009599  mov     rcx, rdi; lpMem
0x18000959c  call    DestroyAddressFamily
0x1800095a1  cmp     esi, ebx
0x1800095a3  sbb     eax, eax
0x1800095a5  and     eax, 216h
0x1800095aa  jmp     loc_180009926
0x1800095af  mov     ebx, eax
0x1800095b1  call    cs:__imp_GetProcessHeap
0x1800095b7  mov     rcx, rax; hHeap
0x1800095ba  mov     r8d, ebx; dwBytes
0x1800095bd  mov     esi, 8
0x1800095c2  mov     edx, esi; dwFlags
0x1800095c4  call    cs:__imp_HeapAlloc
0x1800095ca  mov     rbx, rax
0x1800095cd  mov     [rsp+8B8h+lpSPropTagArrayColumns], rax; lpSPropTagArrayColumns
0x1800095d2  test    rax, rax
0x1800095d5  jnz     short loc_1800095FA
0x1800095d7  cmp     [rdi+148h], eax
0x1800095dd  jnz     short loc_1800095F3
0x1800095df  or      ecx, 0FFFFFFFFh
0x1800095e2  lock xadd [rdi], ecx
0x1800095e6  cmp     ecx, 1
0x1800095e9  jnz     short loc_1800095F3
0x1800095eb  mov     rcx, rdi; lpMem
0x1800095ee  call    DestroyAddressFamily
0x1800095f3  mov     eax, esi
0x1800095f5  jmp     loc_180009926
0x1800095fa  mov     esi, 1
0x1800095ff  lock add [rax], esi
0x180009602  mov     rax, [r13+8]
0x180009606  mov     [rbx+8], rax
0x18000960a  mov     [rbx+10h], rdi
0x18000960e  lock add [rdi], esi
0x180009611  add     [rdi+148h], esi
0x180009617  lea     rax, [rbx+18h]
0x18000961b  mov     [rax+8], rax
0x18000961f  mov     [rax], rax
0x180009622  mov     dword ptr [rbx+34h], 0FFFFFFFFh
0x180009629  xor     r13d, r13d
0x18000962c  test    r12d, r12d
0x18000962f  jz      loc_18000980A
0x180009635  mov     al, cs:byte_18002BD1A
0x18000963b  test    al, 8
0x18000963d  jz      short loc_1800096B7
0x18000963f  mov     word ptr [rsp+8B8h+var_838], r13w
0x180009648  mov     word ptr [rsp+8B8h+var_860], r13w
0x18000964e  mov     rax, [rdi+10h]
0x180009652  movzx   r8d, word ptr [rax+4]
0x180009657  lea     rdx, aCreateentityRe; "CreateEntity: ReserveOpaquePtr is passe"...
0x18000965e  lea     rcx, [rsp+8B8h+var_838]
0x180009666  call    FormatRRASErrorString
0x18000966b  mov     al, cs:byte_18002BD1A
0x180009671  test    al, 8
0x180009673  jz      short loc_1800096B7
0x180009675  mov     rax, qword ptr [rsp+8B8h+uliInst]
0x18000967a  lea     r9, [rsp+8B8h+var_870]
0x18000967f  add     rax, 30h ; '0'
0x180009683  cmovnz  r9, rax
0x180009687  lea     rax, [rsp+8B8h+var_860]
0x18000968c  mov     qword ptr [rsp+8B8h+ulTableType], rax
0x180009691  mov     [rsp+8B8h+lpvReserved], r13
0x180009696  lea     r8, [rsp+8B8h+var_838]
0x18000969e  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x1800096a5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800096ac  call    McTemplateU0zjzz_EventWriteTransfer
0x1800096b1  mov     al, cs:byte_18002BD1A
0x1800096b7  mov     edx, [rdi+138h]
0x1800096bd  mov     r8d, [rdi+13Ch]
0x1800096c4  cmp     r8d, edx
0x1800096c7  jb      loc_180009752
0x1800096cd  test    al, 10h
0x1800096cf  jz      short loc_180009748
0x1800096d1  mov     word ptr [rsp+8B8h+var_838], r13w
0x1800096da  mov     word ptr [rsp+8B8h+var_860], r13w
0x1800096e0  mov     rax, [rdi+10h]
0x1800096e4  movzx   ecx, word ptr [rax+4]
0x1800096e8  mov     dword ptr [rsp+8B8h+lpvReserved], ecx
0x1800096ec  mov     r9d, edx
0x1800096ef  lea     rdx, aCreateentityNu; "CreateEntity: NumOpaquePtrs(%d) >= MaxO"...
0x1800096f6  lea     rcx, [rsp+8B8h+var_838]
0x1800096fe  call    FormatRRASErrorString
0x180009703  test    cs:byte_18002BD1A, 10h
0x18000970a  jz      short loc_180009748
0x18000970c  mov     rax, qword ptr [rsp+8B8h+uliInst]
0x180009711  lea     r9, [rsp+8B8h+var_870]
0x180009716  add     rax, 30h ; '0'
0x18000971a  cmovnz  r9, rax
0x18000971e  lea     rax, [rsp+8B8h+var_860]
0x180009723  mov     qword ptr [rsp+8B8h+ulTableType], rax
0x180009728  mov     [rsp+8B8h+lpvReserved], r13
0x18000972d  lea     r8, [rsp+8B8h+var_838]
0x180009735  lea     rdx, RRAS_RTM_PARAM_TRACE_ERROR
0x18000973c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009743  call    McTemplateU0zjzz_EventWriteTransfer
0x180009748  mov     edi, 5AAh
0x18000974d  jmp     loc_1800098ED
0x180009752  mov     esi, r13d
0x180009755  test    edx, edx
0x180009757  jz      short loc_18000976E
0x180009759  mov     rcx, [rdi+140h]
0x180009760  mov     eax, esi
0x180009762  cmp     [rcx+rax*8], r13
0x180009766  jz      short loc_18000976E
0x180009768  inc     esi
0x18000976a  cmp     esi, edx
0x18000976c  jb      short loc_180009760
0x18000976e  mov     ecx, esi
0x180009770  mov     rax, [rdi+140h]
0x180009777  mov     [rax+rcx*8], rbx
0x18000977b  test    cs:byte_18002BD1A, 8
0x180009782  jz      short loc_1800097FC
0x180009784  mov     word ptr [rsp+8B8h+var_838], r13w
0x18000978d  mov     word ptr [rsp+8B8h+var_860], r13w
0x180009793  mov     rax, [rdi+10h]
0x180009797  movzx   r9d, word ptr [rax+4]
0x18000979c  mov     r8d, [rdi+13Ch]
0x1800097a3  lea     rdx, aCreateentityIn; "CreateEntity: Incrementing NumOpaquePoi"...
0x1800097aa  lea     rcx, [rsp+8B8h+var_838]
0x1800097b2  call    FormatRRASErrorString
0x1800097b7  test    cs:byte_18002BD1A, 8
0x1800097be  jz      short loc_1800097FC
0x1800097c0  mov     rax, qword ptr [rsp+8B8h+uliInst]
0x1800097c5  lea     r9, [rsp+8B8h+var_870]
0x1800097ca  add     rax, 30h ; '0'
0x1800097ce  cmovnz  r9, rax
0x1800097d2  lea     rax, [rsp+8B8h+var_860]
0x1800097d7  mov     qword ptr [rsp+8B8h+ulTableType], rax; ulTableType
0x1800097dc  mov     [rsp+8B8h+lpvReserved], r13; lpvReserved
0x1800097e1  lea     r8, [rsp+8B8h+var_838]
0x1800097e9  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x1800097f0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800097f7  call    McTemplateU0zjzz_EventWriteTransfer
0x1800097fc  inc     dword ptr [rdi+13Ch]
0x180009802  mov     [rbx+34h], esi
0x180009805  mov     esi, 1
0x18000980a  lea     rcx, [rbx+38h]; Resource
0x18000980e  call    cs:__imp_RtlInitializeResource
0x180009814  mov     [rbx+98h], esi
0x18000981a  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x180009821  call    cs:__imp_InitializeCriticalSection
0x180009827  mov     [rbx+0C8h], esi
0x18000982d  lea     rax, [rbx+0D0h]
0x180009834  mov     [rax+8], rax
0x180009838  mov     [rax], rax
0x18000983b  lea     rcx, [rbx+0E0h]; Resource
0x180009842  call    cs:__imp_RtlInitializeResource
0x180009848  mov     [rbx+140h], esi
0x18000984e  lea     rdx, [rbx+148h]; lpAllocateBuffer
0x180009855  mov     ecx, [rdi+8]; lpInterface
0x180009858  call    CreateTable
0x18000985d  mov     edi, eax
0x18000985f  test    eax, eax
0x180009861  jnz     loc_1800098ED
0x180009867  mov     [rbx+150h], r13d
0x18000986e  lea     rcx, [rbx+158h]; Resource
0x180009875  call    cs:__imp_RtlInitializeResource
0x18000987b  mov     [rbx+1B8h], esi
0x180009881  mov     rax, [rsp+8B8h+arg_20]
0x180009889  mov     [rbx+1C0h], rax
0x180009890  mov     [rbx+1C8h], r14d
0x180009897  test    r15, r15
0x18000989a  jz      short loc_1800098B3
0x18000989c  mov     r8d, r14d
0x18000989f  shl     r8, 3; Size
0x1800098a3  lea     rdx, [r15+8]; Src
0x1800098a7  lea     rcx, [rbx+1D0h]; void *
0x1800098ae  call    memcpy_0
0x1800098b3  mov     rax, [rsp+8B8h+lppTableData]
0x1800098b8  mov     [rax], rbx
0x1800098bb  xor     eax, eax
0x1800098bd  jmp     short loc_180009926
0x1800098bf  mov     edi, 8
0x1800098c4  mov     rbx, [rsp+8B8h+lpSPropTagArrayColumns]
0x1800098c9  jmp     short loc_1800098ED
0x1800098cb  mov     edi, 8
0x1800098d0  mov     rbx, [rsp+8B8h+lpSPropTagArrayColumns]
0x1800098d5  jmp     short loc_1800098ED
0x1800098d7  mov     edi, 8
0x1800098dc  mov     rbx, [rsp+8B8h+lpSPropTagArrayColumns]
0x1800098e1  jmp     short loc_1800098ED
0x1800098e3  mov     edi, 8
0x1800098e8  mov     rbx, [rsp+8B8h+lpSPropTagArrayColumns]
0x1800098ed  or      eax, 0FFFFFFFFh
0x1800098f0  lock xadd [rbx], eax
0x1800098f4  cmp     eax, 1
0x1800098f7  jnz     short loc_180009901
0x1800098f9  mov     rcx, rbx; lpMem
0x1800098fc  call    DestroyEntity
0x180009901  mov     eax, edi
0x180009903  jmp     short loc_180009926
0x180009905  cmp     [rdi+148h], esi
0x18000990b  jnz     short loc_180009921
0x18000990d  or      eax, 0FFFFFFFFh
0x180009910  lock xadd [rdi], eax
0x180009914  cmp     eax, 1
0x180009917  jnz     short loc_180009921
0x180009919  mov     rcx, rdi; lpMem
0x18000991c  call    DestroyAddressFamily
0x180009921  mov     eax, 216h
0x180009926  mov     rcx, [rsp+8B8h+var_38]
0x18000992e  xor     rcx, rsp; StackCookie
0x180009931  call    __security_check_cookie
0x180009936  lea     r11, [rsp+8B8h+var_28]
0x18000993e  mov     rbx, [r11+38h]
0x180009942  mov     rsi, [r11+40h]
0x180009946  mov     rsp, r11
0x180009949  pop     r15
0x18000994b  pop     r14
0x18000994d  pop     r13
0x18000994f  pop     r12
0x180009951  pop     rdi
0x180009952  retn
```
