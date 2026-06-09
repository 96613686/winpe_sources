# CEventLog::Report(ushort,_EVENT_DESCRIPTOR const &,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString)

- ea: `0x180001220`
- end: `0x18000156b`
- name: `?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z`
- size: `843`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180001220`
- `0x180001580`
- `0x180001d10`
- `0x18000a290`
- `0x18000ab30`
- `0x180016730`
- `0x18002cad0`
- `0x18002cc60`
- `0x180032e10`
- `0x180032e80`
- `0x180032f70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800014cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800014cd`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800014b3`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800014b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
_BOOL8 __fastcall CEventLog::Report(
        __int64 a1,
        unsigned __int16 a2,
        const EVENT_DESCRIPTOR *a3,
        const struct CInsertionString *a4,
        CInsertionString *a5,
        CInsertionString *a6,
        CInsertionString *a7,
        CInsertionString *a8,
        CInsertionString *a9,
        CInsertionString *a10,
        CInsertionString *a11,
        CInsertionString *a12,
        CInsertionString *a13)
{
  REGHANDLE *v13; // r14
  BOOL v14; // ebx
  CInsertionString *v15; // r13
  CInsertionString *v16; // r12
  CInsertionString *v17; // r15
  CInsertionString *v18; // r14
  CInsertionString *v19; // rsi
  CInsertionString *v20; // rdi
  CInsertionString *v21; // rbx
  CInsertionString *v22; // rax
  unsigned __int16 *v23; // rdi
  unsigned int v24; // edx
  unsigned __int64 v25; // r12
  struct _EVENT_DATA_DESCRIPTOR *v26; // rsi
  int v27; // r15d
  const unsigned __int16 *StringAt; // rdx
  __int64 v29; // rax
  __int64 v30; // rcx
  signed int v31; // ebx
  CInsertionString *v33; // [rsp+78h] [rbp-90h]
  CInsertionString *v34; // [rsp+80h] [rbp-88h]
  void *v35; // [rsp+88h] [rbp-80h]
  LPCRITICAL_SECTION lpCriticalSection[11]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v37[16]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v38[16]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v39[16]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v40[16]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v41[16]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v42[16]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v43[16]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v44[16]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v45[16]; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v46[80]; // [rsp+178h] [rbp+70h] BYREF

  v13 = (REGHANDLE *)a1;
  CInCritSec::CInCritSec((CInCritSec *)lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)(a1 + 48));
  v35 = CWin32DefaultArena::WbemMemAlloc(0x70u);
  v14 = 0;
  if ( v35 )
  {
    lpCriticalSection[1] = (LPCRITICAL_SECTION)v37;
    v33 = CInsertionString::CInsertionString((CInsertionString *)v37, a13);
    lpCriticalSection[2] = (LPCRITICAL_SECTION)v38;
    v34 = CInsertionString::CInsertionString((CInsertionString *)v38, a12);
    lpCriticalSection[3] = (LPCRITICAL_SECTION)v39;
    v15 = CInsertionString::CInsertionString((CInsertionString *)v39, a11);
    lpCriticalSection[4] = (LPCRITICAL_SECTION)v40;
    v16 = CInsertionString::CInsertionString((CInsertionString *)v40, a10);
    lpCriticalSection[5] = (LPCRITICAL_SECTION)v41;
    v17 = CInsertionString::CInsertionString((CInsertionString *)v41, a9);
    lpCriticalSection[6] = (LPCRITICAL_SECTION)v42;
    v18 = CInsertionString::CInsertionString((CInsertionString *)v42, a8);
    lpCriticalSection[7] = (LPCRITICAL_SECTION)v43;
    v19 = CInsertionString::CInsertionString((CInsertionString *)v43, a7);
    lpCriticalSection[8] = (LPCRITICAL_SECTION)v44;
    v20 = CInsertionString::CInsertionString((CInsertionString *)v44, a6);
    lpCriticalSection[9] = (LPCRITICAL_SECTION)v45;
    v21 = CInsertionString::CInsertionString((CInsertionString *)v45, a5);
    lpCriticalSection[10] = (LPCRITICAL_SECTION)v46;
    v22 = CInsertionString::CInsertionString((CInsertionString *)v46, a4);
    v23 = (unsigned __int16 *)CEventLogRecord::CEventLogRecord(
                                v35,
                                a2,
                                a3,
                                v22,
                                v21,
                                v20,
                                v19,
                                v18,
                                v17,
                                v16,
                                v15,
                                v34,
                                v33);
    v13 = (REGHANDLE *)a1;
    v14 = 0;
  }
  else
  {
    v23 = 0;
  }
  if ( v23 )
  {
    if ( (unsigned int)CEventLog::SearchForRecord((CEventLog *)v13, (struct CEventLogRecord *)v23) )
    {
      CEventLogRecord::`scalar deleting destructor'((CEventLogRecord *)v23, v24);
      v14 = 1;
    }
    else if ( CEventLog::AddRecord((CEventLog *)v13, (struct CEventLogRecord *)v23) && v13[2] )
    {
      v25 = v23[8];
      v26 = 0;
      if ( (_WORD)v25 )
      {
        v26 = (struct _EVENT_DATA_DESCRIPTOR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v25, 0x10u));
        if ( !v26 )
          goto LABEL_17;
        v27 = 0;
        do
        {
          StringAt = CEventLogRecord::GetStringAt((CEventLogRecord *)v23, v27);
          v29 = -1;
          do
            ++v29;
          while ( StringAt[v29] );
          v30 = (unsigned int)v27;
          v26[v30].Ptr = (ULONGLONG)StringAt;
          *(_QWORD *)&v26[v30].Size = (unsigned int)(2 * v29 + 2);
          ++v27;
        }
        while ( v27 < (int)v25 );
      }
      v31 = EventWrite(v13[2], a3, v25, v26);
      CMUILocale::_Free(v26);
      v14 = v31 >= 0;
    }
  }
LABEL_17:
  LeaveCriticalSection(lpCriticalSection[0]);
  CInsertionString::~CInsertionString(a4);
  CInsertionString::~CInsertionString(a5);
  CInsertionString::~CInsertionString(a6);
  CInsertionString::~CInsertionString(a7);
  CInsertionString::~CInsertionString(a8);
  CInsertionString::~CInsertionString(a9);
  CInsertionString::~CInsertionString(a10);
  CInsertionString::~CInsertionString(a11);
  CInsertionString::~CInsertionString(a12);
  CInsertionString::~CInsertionString(a13);
  return v14;
}

```

## disassembly

```asm
0x180001220  mov     rax, rsp
0x180001223  mov     [rax+20h], r9
0x180001227  mov     [rax+18h], r8
0x18000122b  mov     [rax+10h], dx
0x18000122f  mov     [rax+8], rcx
0x180001233  push    rbp
0x180001234  push    rbx
0x180001235  push    rsi
0x180001236  push    rdi
0x180001237  push    r12
0x180001239  push    r13
0x18000123b  push    r14
0x18000123d  push    r15
0x18000123f  lea     rbp, [rax-0C8h]
0x180001246  sub     rsp, 188h
0x18000124d  mov     r14, rcx
0x180001250  lea     rdx, [rcx+30h]; struct _RTL_CRITICAL_SECTION *
0x180001254  lea     rcx, [rbp+0C0h+lpCriticalSection]; this
0x180001258  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18000125d  nop
0x18000125e  mov     ecx, 70h ; 'p'; unsigned __int64
0x180001263  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180001268  mov     [rbp+0C0h+var_140], rax
0x18000126c  xor     ebx, ebx
0x18000126e  test    rax, rax
0x180001271  jz      loc_1800013E6
0x180001277  lea     rax, [rbp+0C0h+var_E0]
0x18000127b  mov     [rbp+0C0h+var_130], rax
0x18000127f  mov     rdx, [rbp+0C0h+arg_60]; struct CInsertionString *
0x180001286  lea     rcx, [rbp+0C0h+var_E0]; this
0x18000128a  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x18000128f  mov     [rsp+1C0h+var_150], rax
0x180001294  lea     rax, [rbp+0C0h+var_D0]
0x180001298  mov     [rbp+0C0h+var_128], rax
0x18000129c  mov     rdx, [rbp+0C0h+arg_58]; struct CInsertionString *
0x1800012a3  lea     rcx, [rbp+0C0h+var_D0]; this
0x1800012a7  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x1800012ac  mov     [rsp+78h], rax
0x1800012b1  lea     rax, [rbp+0C0h+var_C0]
0x1800012b5  mov     [rbp+0C0h+var_120], rax
0x1800012b9  mov     rdx, [rbp+0C0h+arg_50]; struct CInsertionString *
0x1800012c0  lea     rcx, [rbp+0C0h+var_C0]; this
0x1800012c4  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x1800012c9  mov     r13, rax
0x1800012cc  lea     rax, [rbp+0C0h+var_B0]
0x1800012d0  mov     [rbp+0C0h+var_118], rax
0x1800012d4  mov     rdx, [rbp+0C0h+arg_48]; struct CInsertionString *
0x1800012db  lea     rcx, [rbp+0C0h+var_B0]; this
0x1800012df  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x1800012e4  mov     r12, rax
0x1800012e7  lea     rax, [rbp+0C0h+var_A0]
0x1800012eb  mov     [rbp+0C0h+var_110], rax
0x1800012ef  mov     rdx, [rbp+0C0h+arg_40]; struct CInsertionString *
0x1800012f6  lea     rcx, [rbp+0C0h+var_A0]; this
0x1800012fa  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x1800012ff  mov     r15, rax
0x180001302  lea     rax, [rbp+0C0h+var_90]
0x180001306  mov     [rbp+0C0h+var_108], rax
0x18000130a  mov     rdx, [rbp+0C0h+arg_38]; struct CInsertionString *
0x180001311  lea     rcx, [rbp+0C0h+var_90]; this
0x180001315  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x18000131a  mov     r14, rax
0x18000131d  lea     rax, [rbp+0C0h+var_80]
0x180001321  mov     [rbp+0C0h+var_100], rax
0x180001325  mov     rdx, [rbp+0C0h+arg_30]; struct CInsertionString *
0x18000132c  lea     rcx, [rbp+0C0h+var_80]; this
0x180001330  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x180001335  mov     rsi, rax
0x180001338  lea     rax, [rbp+0C0h+var_70]
0x18000133c  mov     [rbp+0C0h+var_F8], rax
0x180001340  mov     rdx, [rbp+0C0h+arg_28]; struct CInsertionString *
0x180001347  lea     rcx, [rbp+0C0h+var_70]; this
0x18000134b  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x180001350  mov     rdi, rax
0x180001353  lea     rax, [rbp+0C0h+var_60]
0x180001357  mov     [rbp+0C0h+var_F0], rax
0x18000135b  mov     rdx, [rbp+0C0h+arg_20]; struct CInsertionString *
0x180001362  lea     rcx, [rbp+0C0h+var_60]; this
0x180001366  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x18000136b  mov     rbx, rax
0x18000136e  lea     rax, [rbp+0C0h+var_50]
0x180001372  mov     [rbp+0C0h+var_E8], rax
0x180001376  mov     rdx, [rbp+0C0h+arg_18]; struct CInsertionString *
0x18000137d  lea     rcx, [rbp+0C0h+var_50]; this
0x180001381  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x180001386  nop
0x180001387  mov     rcx, [rsp+1C0h+var_150]
0x18000138c  mov     [rsp+60h], rcx
0x180001391  mov     rcx, [rsp+78h]
0x180001396  mov     [rsp+1C0h+var_168], rcx
0x18000139b  mov     [rsp+1C0h+var_170], r13
0x1800013a0  mov     [rsp+1C0h+var_178], r12
0x1800013a5  mov     [rsp+1C0h+var_180], r15
0x1800013aa  mov     [rsp+1C0h+var_188], r14
0x1800013af  mov     [rsp+1C0h+var_190], rsi
0x1800013b4  mov     [rsp+1C0h+var_198], rdi
0x1800013b9  mov     [rsp+1C0h+var_1A0], rbx
0x1800013be  mov     r9, rax
0x1800013c1  mov     r8, [rbp+0C0h+EventDescriptor]
0x1800013c8  movzx   edx, [rbp+0C0h+arg_8]
0x1800013cf  mov     rcx, [rbp+0C0h+var_140]
0x1800013d3  call    ??0CEventLogRecord@@QEAA@GAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z; CEventLogRecord::CEventLogRecord(ushort,_EVENT_DESCRIPTOR const &,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString)
0x1800013d8  mov     rdi, rax
0x1800013db  mov     r14, [rbp+0C0h+arg_0]
0x1800013e2  xor     ebx, ebx
0x1800013e4  jmp     short loc_1800013E9
0x1800013e6  mov     rdi, rbx
0x1800013e9  test    rdi, rdi
0x1800013ec  jz      short loc_180001452
0x1800013ee  mov     rdx, rdi; struct CEventLogRecord *
0x1800013f1  mov     rcx, r14; this
0x1800013f4  call    ?SearchForRecord@CEventLog@@IEAAHPEAVCEventLogRecord@@@Z; CEventLog::SearchForRecord(CEventLogRecord *)
0x1800013f9  test    eax, eax
0x1800013fb  jz      short loc_18000140C
0x1800013fd  mov     rcx, rdi; this
0x180001400  call    ??_GCEventLogRecord@@QEAAPEAXI@Z; CEventLogRecord::`scalar deleting destructor'(uint)
0x180001405  mov     ebx, 1
0x18000140a  jmp     short loc_180001452
0x18000140c  mov     rdx, rdi; struct CEventLogRecord *
0x18000140f  mov     rcx, r14; this
0x180001412  call    ?AddRecord@CEventLog@@IEAAHPEAVCEventLogRecord@@@Z; CEventLog::AddRecord(CEventLogRecord *)
0x180001417  test    eax, eax
0x180001419  jz      short loc_180001452
0x18000141b  cmp     [r14+10h], rbx
0x18000141f  jz      short loc_180001452
0x180001421  movzx   r12d, word ptr [rdi+10h]
0x180001426  mov     rsi, rbx
0x180001429  test    r12w, r12w
0x18000142d  jz      short loc_1800014A2
0x18000142f  mov     eax, 10h
0x180001434  mul     r12
0x180001437  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000143e  cmovb   rax, rcx
0x180001442  mov     rcx, rax; unsigned __int64
0x180001445  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000144a  mov     rsi, rax
0x18000144d  test    rax, rax
0x180001450  jnz     short loc_180001454
0x180001452  jmp     short loc_1800014C9
0x180001454  mov     r15d, ebx
0x180001457  test    r12d, r12d
0x18000145a  jz      short loc_1800014A2
0x18000145c  mov     ebx, 1
0x180001461  mov     edx, r15d; int
0x180001464  mov     rcx, rdi; this
0x180001467  call    ?GetStringAt@CEventLogRecord@@QEAAPEBGH@Z; CEventLogRecord::GetStringAt(int)
0x18000146c  mov     rdx, rax
0x18000146f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001473  xor     r8d, r8d
0x180001476  inc     rax
0x180001479  cmp     [rdx+rax*2], r8w
0x18000147e  jnz     short loc_180001476
0x180001480  mov     ecx, r15d
0x180001483  add     rcx, rcx
0x180001486  mov     [rsi+rcx*8], rdx
0x18000148a  lea     eax, ds:2[rax*2]
0x180001491  mov     [rsi+rcx*8+8], eax
0x180001495  mov     [rsi+rcx*8+0Ch], r8d
0x18000149a  add     r15d, ebx
0x18000149d  cmp     r15d, r12d
0x1800014a0  jl      short loc_180001461
0x1800014a2  mov     r8d, r12d; UserDataCount
0x1800014a5  mov     r9, rsi; UserData
0x1800014a8  mov     rdx, [rbp+0C0h+EventDescriptor]; EventDescriptor
0x1800014af  mov     rcx, [r14+10h]; RegHandle
0x1800014b3  call    cs:__imp_EventWrite
0x1800014b9  mov     ebx, eax
0x1800014bb  mov     rcx, rsi; void *
0x1800014be  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x1800014c3  nop
0x1800014c4  not     ebx
0x1800014c6  shr     ebx, 1Fh
0x1800014c9  mov     rcx, [rbp+0C0h+lpCriticalSection]; lpCriticalSection
0x1800014cd  call    cs:__imp_LeaveCriticalSection
0x1800014d3  nop
0x1800014d4  mov     rcx, [rbp+0C0h+arg_18]; this
0x1800014db  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x1800014e0  nop
0x1800014e1  mov     rcx, [rbp+0C0h+arg_20]; this
0x1800014e8  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x1800014ed  nop
0x1800014ee  mov     rcx, [rbp+0C0h+arg_28]; this
0x1800014f5  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x1800014fa  nop
0x1800014fb  mov     rcx, [rbp+0C0h+arg_30]; this
0x180001502  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x180001507  nop
0x180001508  mov     rcx, [rbp+0C0h+arg_38]; this
0x18000150f  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x180001514  nop
0x180001515  mov     rcx, [rbp+0C0h+arg_40]; this
0x18000151c  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x180001521  nop
0x180001522  mov     rcx, [rbp+0C0h+arg_48]; this
0x180001529  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x18000152e  nop
0x18000152f  mov     rcx, [rbp+0C0h+arg_50]; this
0x180001536  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x18000153b  nop
0x18000153c  mov     rcx, [rbp+0C0h+arg_58]; this
0x180001543  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x180001548  nop
0x180001549  mov     rcx, [rbp+0C0h+arg_60]; this
0x180001550  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x180001555  mov     eax, ebx
0x180001557  add     rsp, 188h
0x18000155e  pop     r15
0x180001560  pop     r14
0x180001562  pop     r13
0x180001564  pop     r12
0x180001566  pop     rdi
0x180001567  pop     rsi
0x180001568  pop     rbx
0x180001569  pop     rbp
0x18000156a  retn
```
