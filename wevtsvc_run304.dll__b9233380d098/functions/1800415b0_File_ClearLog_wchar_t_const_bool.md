# File::ClearLog(wchar_t const *,bool)

- ea: `0x1800415b0`
- end: `0x1800419fa`
- name: `?ClearLog@File@@QEAAXPEB_W_N@Z`
- size: `1098`
- prototype: `void __fastcall(File *__hidden this, const wchar_t *, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1800414c0`
- `0x1800660cc`

## callees

- `0x18000bc38`
- `0x1800402e4`
- `0x1800415b0`
- `0x180041a00`
- `0x180047a0c`
- `0x1800660ac`
- `0x180092008`
- `0x180098c50`
- `0x1800b427c`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800415db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800415db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004174b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004174b`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800417ea`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800417ea`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004176f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004186a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004176f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004186a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall File::ClearLog(RTL_SRWLOCK *this, const wchar_t *a2, char a3)
{
  ReadContext *Ptr; // rdi
  unsigned int v7; // edi
  unsigned int v8; // r14d
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-48h] BYREF
  char v10; // [rsp+38h] [rbp-40h]
  __int128 pExceptionObject; // [rsp+40h] [rbp-38h] BYREF
  __int64 v12; // [rsp+50h] [rbp-28h]
  int v13; // [rsp+58h] [rbp-20h]
  int v14; // [rsp+5Ch] [rbp-1Ch]
  int v15; // [rsp+60h] [rbp-18h]
  char v16; // [rsp+64h] [rbp-14h]

  SRWLock = this + 83;
  AcquireSRWLockExclusive(this + 83);
  v10 = 1;
  if ( !LOBYTE(this[104].Ptr) && !BYTE5(this[103].Ptr) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 110);
    }
    pExceptionObject = 0;
    v12 = 0;
    v13 = 110;
    v14 = -1;
    v15 = 2070;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !File::IsFileEmpty((File *)this) )
  {
    Ptr = (ReadContext *)this->Ptr;
    if ( *(ReadContext **)Ptr != Ptr )
    {
      do
      {
        ReadContext::Reset(Ptr, 1);
        Ptr = *(ReadContext **)Ptr;
      }
      while ( *(PVOID *)Ptr != this->Ptr );
    }
  }
  v7 = File::FlushFile(this, 0, &SRWLock);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v7);
    }
    *(_QWORD *)&pExceptionObject = &word_1800EC961;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v12 = 0;
    v13 = v7;
    v14 = -1;
    v15 = -1;
    v16 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  if ( a2 && *a2 )
    File::BackupLog((__int64)this, a2, a3, 0, (__int64)&SRWLock);
  if ( LOBYTE(this[104].Ptr) )
  {
    if ( v10 )
      ReleaseSRWLockExclusive(SRWLock);
  }
  else
  {
    BYTE5(this[103].Ptr) = 0;
    if ( SetFilePointer(this[84].Ptr, 69632, 0, 0) == -1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 110);
      }
      pExceptionObject = 0;
      v12 = 0;
      v13 = 110;
      v14 = -1;
      v15 = 2098;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !SetEndOfFile(this[84].Ptr) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 110);
      }
      pExceptionObject = 0;
      v12 = 0;
      v13 = 110;
      v14 = -1;
      v15 = 2103;
      throw (EvtException *)&pExceptionObject;
    }
    if ( SetFilePointer(this[84].Ptr, 0, 0, 0) == -1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 110);
      }
      pExceptionObject = 0;
      v12 = 0;
      v13 = 110;
      v14 = -1;
      v15 = 2108;
      throw (EvtException *)&pExceptionObject;
    }
    BYTE3(this[103].Ptr) = 0;
    HIDWORD(this[101].Ptr) = 0;
    this[97].Ptr = (PVOID)-1LL;
    this[98].Ptr = (PVOID)-1LL;
    this[21].Ptr = (PVOID)-1LL;
    this[102].Ptr = 0;
    BYTE2(this[103].Ptr) = 0;
    BYTE6(this[104].Ptr) = 0;
    this[96].Ptr = (PVOID)-1LL;
    v8 = File::InitializeEmptyFile((File *)this);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v8);
      }
      *(_QWORD *)&pExceptionObject = &word_1800EC961;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      v12 = 0;
      v13 = v8;
      v14 = -1;
      v15 = -1;
      v16 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, this[89].Ptr);
    }
    BYTE5(this[103].Ptr) = 1;
    utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(&SRWLock);
  }
}

```

## disassembly

```asm
0x1800415b0  push    rbp
0x1800415b2  push    rbx
0x1800415b3  push    rsi
0x1800415b4  push    rdi
0x1800415b5  push    r14
0x1800415b7  push    r15
0x1800415b9  mov     rbp, rsp
0x1800415bc  sub     rsp, 78h
0x1800415c0  mov     r14b, r8b
0x1800415c3  mov     rsi, rdx
0x1800415c6  mov     rbx, rcx
0x1800415c9  add     rcx, 298h; SRWLock
0x1800415d0  mov     [rbp+SRWLock], rcx
0x1800415d4  xor     r15d, r15d
0x1800415d7  mov     [rbp+var_40], r15b
0x1800415db  call    cs:__imp_AcquireSRWLockExclusive
0x1800415e1  mov     [rbp+var_40], 1
0x1800415e5  cmp     [rbx+340h], r15b
0x1800415ec  jnz     short loc_180041660
0x1800415ee  cmp     [rbx+33Dh], r15b
0x1800415f5  jnz     short loc_180041660
0x1800415f7  lea     rax, WPP_GLOBAL_Control
0x1800415fe  lea     ebx, [r15+6Eh]
0x180041602  mov     rcx, cs:WPP_GLOBAL_Control
0x180041609  cmp     rcx, rax
0x18004160c  jz      short loc_180041633
0x18004160e  test    dword ptr [rcx+1Ch], 8000h
0x180041615  jz      short loc_180041633
0x180041617  cmp     byte ptr [rcx+19h], 2
0x18004161b  jb      short loc_180041633
0x18004161d  lea     edx, [rbx-22h]
0x180041620  mov     r9d, ebx
0x180041623  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x18004162a  mov     rcx, [rcx+10h]
0x18004162e  call    WPP_SF_d
0x180041633  xorps   xmm0, xmm0
0x180041636  movdqu  [rbp+pExceptionObject], xmm0
0x18004163b  mov     [rbp+var_28], r15
0x18004163f  mov     [rbp+var_20], ebx
0x180041642  or      edi, 0FFFFFFFFh
0x180041645  mov     [rbp+var_1C], edi
0x180041648  mov     [rbp+var_18], 816h
0x18004164f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180041656  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004165a  call    _CxxThrowException_0
0x180041660  mov     rcx, rbx; this
0x180041663  call    ?IsFileEmpty@File@@AEAA_NXZ; File::IsFileEmpty(void)
0x180041668  test    al, al
0x18004166a  jnz     short loc_180041689
0x18004166c  mov     rdi, [rbx]
0x18004166f  cmp     [rdi], rdi
0x180041672  jz      short loc_180041689
0x180041674  mov     dl, 1; bool
0x180041676  mov     rcx, rdi; this
0x180041679  call    ?Reset@ReadContext@@QEAAX_N@Z; ReadContext::Reset(bool)
0x18004167e  mov     rdi, [rdi]
0x180041681  mov     rax, [rbx]
0x180041684  cmp     [rdi], rax
0x180041687  jnz     short loc_180041674
0x180041689  lea     r8, [rbp+SRWLock]
0x18004168d  xor     edx, edx
0x18004168f  mov     rcx, rbx
0x180041692  call    ?FlushFile@File@@AEAAKW4FlushType@@AEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::FlushFile(FlushType,utl::unique_lock<utl::shared_mutex> &)
0x180041697  mov     edi, eax
0x180041699  test    eax, eax
0x18004169b  jz      short loc_18004170F
0x18004169d  lea     rax, WPP_GLOBAL_Control
0x1800416a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800416ab  cmp     rcx, rax
0x1800416ae  jz      short loc_1800416D7
0x1800416b0  test    dword ptr [rcx+1Ch], 8000h
0x1800416b7  jz      short loc_1800416D7
0x1800416b9  cmp     byte ptr [rcx+19h], 2
0x1800416bd  jb      short loc_1800416D7
0x1800416bf  mov     edx, 4Dh ; 'M'
0x1800416c4  mov     r9d, edi
0x1800416c7  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800416ce  mov     rcx, [rcx+10h]
0x1800416d2  call    WPP_SF_d
0x1800416d7  lea     rax, word_1800EC961
0x1800416de  mov     qword ptr [rbp+pExceptionObject], rax
0x1800416e2  mov     qword ptr [rbp+pExceptionObject+8], r15
0x1800416e6  mov     [rbp+var_28], r15
0x1800416ea  mov     [rbp+var_20], edi
0x1800416ed  or      edi, 0FFFFFFFFh
0x1800416f0  mov     [rbp+var_1C], edi
0x1800416f3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800416f7  mov     [rbp+var_18], esi
0x1800416fa  mov     [rbp+var_14], r15b
0x1800416fe  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180041705  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180041709  call    _CxxThrowException_0
0x18004170f  test    rsi, rsi
0x180041712  jz      short loc_180041734
0x180041714  cmp     [rsi], r15w
0x180041718  jz      short loc_180041734
0x18004171a  lea     rax, [rbp+SRWLock]
0x18004171e  mov     [rsp+78h+var_58], rax
0x180041723  xor     r9d, r9d
0x180041726  mov     r8b, r14b
0x180041729  mov     rdx, rsi
0x18004172c  mov     rcx, rbx
0x18004172f  call    ?BackupLog@File@@AEAAXPEB_W_NPEBVOperationControl@@AEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::BackupLog(wchar_t const *,bool,OperationControl const *,utl::unique_lock<utl::shared_mutex> &)
0x180041734  cmp     [rbx+340h], r15b
0x18004173b  jz      short loc_180041756
0x18004173d  cmp     [rbp+var_40], r15b
0x180041741  jz      loc_1800419ED
0x180041747  mov     rcx, [rbp+SRWLock]; SRWLock
0x18004174b  call    cs:__imp_ReleaseSRWLockExclusive
0x180041751  jmp     loc_1800419ED
0x180041756  mov     [rbx+33Dh], r15b
0x18004175d  xor     r9d, r9d; dwMoveMethod
0x180041760  xor     r8d, r8d; lpDistanceToMoveHigh
0x180041763  mov     edx, 11000h; lDistanceToMove
0x180041768  mov     rcx, [rbx+2A0h]; hFile
0x18004176f  call    cs:__imp_SetFilePointer
0x180041775  or      edi, 0FFFFFFFFh
0x180041778  cmp     eax, edi
0x18004177a  jnz     short loc_1800417E3
0x18004177c  lea     rax, WPP_GLOBAL_Control
0x180041783  mov     ebx, 6Eh ; 'n'
0x180041788  mov     rcx, cs:WPP_GLOBAL_Control
0x18004178f  cmp     rcx, rax
0x180041792  jz      short loc_1800417B9
0x180041794  test    dword ptr [rcx+1Ch], 8000h
0x18004179b  jz      short loc_1800417B9
0x18004179d  cmp     byte ptr [rcx+19h], 2
0x1800417a1  jb      short loc_1800417B9
0x1800417a3  lea     edx, [rbx-20h]
0x1800417a6  mov     r9d, ebx
0x1800417a9  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800417b0  mov     rcx, [rcx+10h]
0x1800417b4  call    WPP_SF_d
0x1800417b9  xorps   xmm0, xmm0
0x1800417bc  movdqu  [rbp+pExceptionObject], xmm0
0x1800417c1  mov     [rbp+var_28], r15
0x1800417c5  mov     [rbp+var_20], ebx
0x1800417c8  mov     [rbp+var_1C], edi
0x1800417cb  mov     [rbp+var_18], 832h
0x1800417d2  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800417d9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800417dd  call    _CxxThrowException_0
0x1800417e3  mov     rcx, [rbx+2A0h]; hFile
0x1800417ea  call    cs:__imp_SetEndOfFile
0x1800417f0  test    eax, eax
0x1800417f2  jnz     short loc_18004185B
0x1800417f4  lea     rax, WPP_GLOBAL_Control
0x1800417fb  mov     ebx, 6Eh ; 'n'
0x180041800  mov     rcx, cs:WPP_GLOBAL_Control
0x180041807  cmp     rcx, rax
0x18004180a  jz      short loc_180041831
0x18004180c  test    dword ptr [rcx+1Ch], 8000h
0x180041813  jz      short loc_180041831
0x180041815  cmp     byte ptr [rcx+19h], 2
0x180041819  jb      short loc_180041831
0x18004181b  lea     edx, [rbx-1Fh]
0x18004181e  mov     r9d, ebx
0x180041821  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x180041828  mov     rcx, [rcx+10h]
0x18004182c  call    WPP_SF_d
0x180041831  xorps   xmm0, xmm0
0x180041834  movdqu  [rbp+pExceptionObject], xmm0
0x180041839  mov     [rbp+var_28], r15
0x18004183d  mov     [rbp+var_20], ebx
0x180041840  mov     [rbp+var_1C], edi
0x180041843  mov     [rbp+var_18], 837h
0x18004184a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180041851  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180041855  call    _CxxThrowException_0
0x18004185b  xor     r9d, r9d; dwMoveMethod
0x18004185e  xor     r8d, r8d; lpDistanceToMoveHigh
0x180041861  xor     edx, edx; lDistanceToMove
0x180041863  mov     rcx, [rbx+2A0h]; hFile
0x18004186a  call    cs:__imp_SetFilePointer
0x180041870  cmp     eax, edi
0x180041872  jnz     short loc_1800418DB
0x180041874  lea     rax, WPP_GLOBAL_Control
0x18004187b  mov     ebx, 6Eh ; 'n'
0x180041880  mov     rcx, cs:WPP_GLOBAL_Control
0x180041887  cmp     rcx, rax
0x18004188a  jz      short loc_1800418B1
0x18004188c  test    dword ptr [rcx+1Ch], 8000h
0x180041893  jz      short loc_1800418B1
0x180041895  cmp     byte ptr [rcx+19h], 2
0x180041899  jb      short loc_1800418B1
0x18004189b  lea     edx, [rbx-1Eh]
0x18004189e  mov     r9d, ebx
0x1800418a1  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800418a8  mov     rcx, [rcx+10h]
0x1800418ac  call    WPP_SF_d
0x1800418b1  xorps   xmm0, xmm0
0x1800418b4  movdqu  [rbp+pExceptionObject], xmm0
0x1800418b9  mov     [rbp+var_28], r15
0x1800418bd  mov     [rbp+var_20], ebx
0x1800418c0  mov     [rbp+var_1C], edi
0x1800418c3  mov     [rbp+var_18], 83Ch
0x1800418ca  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800418d1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800418d5  call    _CxxThrowException_0
0x1800418db  mov     [rbx+33Bh], r15b
0x1800418e2  mov     [rbx+32Ch], r15d
0x1800418e9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800418ed  mov     [rbx+308h], rsi
0x1800418f4  mov     [rbx+310h], rsi
0x1800418fb  mov     [rbx+0A8h], rsi
0x180041902  mov     [rbx+330h], r15
0x180041909  mov     [rbx+33Ah], r15b
0x180041910  mov     [rbx+346h], r15b
0x180041917  mov     [rbx+300h], rsi
0x18004191e  lea     r8, [rbp+SRWLock]
0x180041922  mov     rdx, [rbx+28h]
0x180041926  mov     rcx, rbx; this
0x180041929  call    ?InitializeEmptyFile@File@@AEAAK_KAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::InitializeEmptyFile(unsigned __int64,utl::unique_lock<utl::shared_mutex> &)
0x18004192e  mov     r14d, eax
0x180041931  test    eax, eax
0x180041933  jz      short loc_18004199F
0x180041935  lea     rax, WPP_GLOBAL_Control
0x18004193c  mov     rcx, cs:WPP_GLOBAL_Control
0x180041943  cmp     rcx, rax
0x180041946  jz      short loc_18004196D
0x180041948  test    dword ptr [rcx+1Ch], 8000h
0x18004194f  jz      short loc_18004196D
0x180041951  cmp     byte ptr [rcx+19h], 2
0x180041955  jb      short loc_18004196D
0x180041957  lea     edx, [rsi+52h]
0x18004195a  mov     r9d, r14d
0x18004195d  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x180041964  mov     rcx, [rcx+10h]
0x180041968  call    WPP_SF_d
0x18004196d  lea     rax, word_1800EC961
0x180041974  mov     qword ptr [rbp+pExceptionObject], rax
0x180041978  mov     qword ptr [rbp+pExceptionObject+8], r15
0x18004197c  mov     [rbp+var_28], r15
0x180041980  mov     [rbp+var_20], r14d
0x180041984  mov     [rbp+var_1C], edi
0x180041987  mov     [rbp+var_18], esi
0x18004198a  mov     [rbp+var_14], r15b
0x18004198e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180041995  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180041999  call    _CxxThrowException_0
0x18004199f  lea     rax, WPP_GLOBAL_Control
0x1800419a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800419ad  cmp     rcx, rax
0x1800419b0  jz      short loc_1800419DD
0x1800419b2  test    dword ptr [rcx+1Ch], 200h
0x1800419b9  jz      short loc_1800419DD
0x1800419bb  cmp     byte ptr [rcx+19h], 5
0x1800419bf  jb      short loc_1800419DD
0x1800419c1  mov     edx, 52h ; 'R'
0x1800419c6  mov     r9, [rbx+2C8h]
0x1800419cd  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800419d4  mov     rcx, [rcx+10h]
0x1800419d8  call    WPP_SF_S
0x1800419dd  mov     byte ptr [rbx+33Dh], 1
0x1800419e4  lea     rcx, [rbp+SRWLock]
0x1800419e8  call    ??1?$unique_lock@Vshared_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(void)
0x1800419ed  add     rsp, 78h
0x1800419f1  pop     r15
0x1800419f3  pop     r14
0x1800419f5  pop     rdi
0x1800419f6  pop     rsi
0x1800419f7  pop     rbx
0x1800419f8  pop     rbp
0x1800419f9  retn
```
