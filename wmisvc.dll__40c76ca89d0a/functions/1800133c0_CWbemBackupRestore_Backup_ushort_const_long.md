# CWbemBackupRestore::Backup(ushort const *,long)

- ea: `0x1800133c0`
- end: `0x1800136dd`
- name: `?Backup@CWbemBackupRestore@@UEAAJPEBGJ@Z`
- size: `797`
- prototype: `__int64 __fastcall(CWbemBackupRestore *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ae04`
- `0x180010710`
- `0x180010740`
- `0x1800133c0`
- `0x1800136e4`

## import_xrefs

- `wbemcomn!??0CInsertionString@@QEAA@J@Z` at `0x18001363d`
- `wbemcomn!??0CInsertionString@@QEAA@J@Z` at `0x18001363d`
- `wbemcomn!?Close@CEventLog@@QEAAHXZ` at `0x1800136b5`
- `wbemcomn!?Close@CEventLog@@QEAAHXZ` at `0x1800136b5`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x180013552`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x1800136ac`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x180013552`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x1800136ac`
- `wbemcomn!?Open@CEventLog@@QEAAHXZ` at `0x180013429`
- `wbemcomn!?Open@CEventLog@@QEAAHXZ` at `0x180013429`
- `wbemcomn!??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z` at `0x180013412`
- `wbemcomn!??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z` at `0x180013412`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800133ee`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800133ee`

## pseudocode

```c
__int64 __fastcall CWbemBackupRestore::Backup(CWbemBackupRestore *this, const unsigned __int16 *a2, int a3)
{
  CEventLog *v3; // rax
  CInsertionString *v4; // r13
  CInsertionString *v5; // r12
  CInsertionString *v6; // r15
  CInsertionString *v7; // r14
  CInsertionString *v8; // rsi
  CInsertionString *v9; // rdi
  CInsertionString *v10; // rbx
  CInsertionString *v11; // rax
  CEventLog *v12; // rbx
  __int64 result; // rax
  CInsertionString *v14; // r13
  CInsertionString *v15; // r12
  CInsertionString *v16; // r15
  CInsertionString *v17; // r14
  CInsertionString *v18; // rsi
  CInsertionString *v19; // rdi
  CInsertionString *v20; // rbx
  CInsertionString *v21; // rax
  unsigned int v22; // edx
  CInsertionString *v23; // [rsp+28h] [rbp-E0h]
  CEventLog *v24; // [rsp+78h] [rbp-90h]
  CInsertionString *v25; // [rsp+80h] [rbp-88h]
  CInsertionString *v26; // [rsp+80h] [rbp-88h]
  CInsertionString *v27; // [rsp+88h] [rbp-80h]
  _BYTE v28[16]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v29[16]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v30[16]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v31[16]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v32[16]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v33[16]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v34[16]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v35[16]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v36[16]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE *v37; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v38[80]; // [rsp+178h] [rbp+70h] BYREF
  CInsertionString *v42; // [rsp+1F0h] [rbp+E8h]
  unsigned int v43; // [rsp+1F0h] [rbp+E8h]

  v3 = (CEventLog *)CWin32DefaultArena::WbemMemAlloc(0x58u);
  if ( v3 )
    v3 = CEventLog::CEventLog(v3, 0, (const struct _GUID *)S_WinMgmtR, 0xAu);
  v24 = v3;
  if ( v3 )
  {
    CEventLog::Open(v3);
    v42 = CInsertionString::CInsertionString((CInsertionString *)&v37);
    v25 = CInsertionString::CInsertionString((CInsertionString *)v28);
    v4 = CInsertionString::CInsertionString((CInsertionString *)v29);
    v5 = CInsertionString::CInsertionString((CInsertionString *)v30);
    v6 = CInsertionString::CInsertionString((CInsertionString *)v31);
    v7 = CInsertionString::CInsertionString((CInsertionString *)v32);
    v8 = CInsertionString::CInsertionString((CInsertionString *)v33);
    v9 = CInsertionString::CInsertionString((CInsertionString *)v34);
    v10 = CInsertionString::CInsertionString((CInsertionString *)v35);
    v11 = CInsertionString::CInsertionString((CInsertionString *)v36, a2);
    v23 = v10;
    v12 = v24;
    CEventLog::Report(v24, 4, WBEM_MC_WBEM_REPOSITORY_BACKUP_STARTED, v11, v23, v9, v8, v7, v6, v5, v4, v25, v42);
  }
  else
  {
    v12 = 0;
  }
  result = CWbemBackupRestore::BackupHelper(this, a2, a3);
  v43 = result;
  if ( v12 )
  {
    v26 = CInsertionString::CInsertionString((CInsertionString *)v36);
    v27 = CInsertionString::CInsertionString((CInsertionString *)v35);
    v14 = CInsertionString::CInsertionString((CInsertionString *)v34);
    v15 = CInsertionString::CInsertionString((CInsertionString *)v33);
    v16 = CInsertionString::CInsertionString((CInsertionString *)v32);
    v17 = CInsertionString::CInsertionString((CInsertionString *)v31);
    v18 = CInsertionString::CInsertionString((CInsertionString *)v30);
    v19 = CInsertionString::CInsertionString((CInsertionString *)v29);
    v20 = CInsertionString::CInsertionString((CInsertionString *)v28, v43);
    v37 = v38;
    v21 = CInsertionString::CInsertionString((CInsertionString *)v38, a2);
    CEventLog::Report(v24, 4, "D", v21, v20, v19, v18, v17, v16, v15, v14, v27, v26);
    CEventLog::Close(v24);
    CEventLog::`scalar deleting destructor'(v24, v22);
    return v43;
  }
  return result;
}

```

## disassembly

```asm
0x1800133c0  mov     rax, rsp
0x1800133c3  mov     [rax+18h], r8d
0x1800133c7  mov     [rax+10h], rdx
0x1800133cb  mov     [rax+8], rcx
0x1800133cf  push    rbp
0x1800133d0  push    rbx
0x1800133d1  push    rsi
0x1800133d2  push    rdi
0x1800133d3  push    r12
0x1800133d5  push    r13
0x1800133d7  push    r14
0x1800133d9  push    r15
0x1800133db  lea     rbp, [rax-0C8h]
0x1800133e2  sub     rsp, 188h
0x1800133e9  mov     ecx, 58h ; 'X'
0x1800133ee  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800133f4  mov     [rbp+0C0h+arg_18], rax
0x1800133fb  test    rax, rax
0x1800133fe  jz      short loc_180013418
0x180013400  mov     r9d, 0Ah
0x180013406  lea     r8, S_WinMgmtR
0x18001340d  xor     edx, edx
0x18001340f  mov     rcx, rax
0x180013412  call    cs:__imp_??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z; CEventLog::CEventLog(ushort const *,_GUID const &,ulong)
0x180013418  mov     [rsp+1C0h+var_150], rax
0x18001341d  test    rax, rax
0x180013420  jz      loc_18001355A
0x180013426  mov     rcx, rax
0x180013429  call    cs:__imp_?Open@CEventLog@@QEAAHXZ; CEventLog::Open(void)
0x18001342f  lea     rax, [rbp+0C0h+var_60]
0x180013433  mov     [rbp+0C0h+var_140], rax
0x180013437  lea     rcx, [rbp+0C0h+var_60]; this
0x18001343b  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180013440  mov     [rbp+0C0h+arg_18], rax
0x180013447  lea     rax, [rbp+0C0h+var_F0]
0x18001344b  mov     [rbp+0C0h+var_138], rax
0x18001344f  lea     rcx, [rbp+0C0h+var_F0]; this
0x180013453  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180013458  mov     [rsp+78h], rax
0x18001345d  lea     rax, [rbp+0C0h+var_E0]
0x180013461  mov     [rbp+0C0h+var_130], rax
0x180013465  lea     rcx, [rbp+0C0h+var_E0]; this
0x180013469  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x18001346e  mov     r13, rax
0x180013471  lea     rax, [rbp+0C0h+var_D0]
0x180013475  mov     [rbp+0C0h+var_128], rax
0x180013479  lea     rcx, [rbp+0C0h+var_D0]; this
0x18001347d  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180013482  mov     r12, rax
0x180013485  lea     rax, [rbp+0C0h+var_C0]
0x180013489  mov     [rbp+0C0h+var_120], rax
0x18001348d  lea     rcx, [rbp+0C0h+var_C0]; this
0x180013491  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180013496  mov     r15, rax
0x180013499  lea     rax, [rbp+0C0h+var_B0]
0x18001349d  mov     [rbp+0C0h+var_118], rax
0x1800134a1  lea     rcx, [rbp+0C0h+var_B0]; this
0x1800134a5  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800134aa  mov     r14, rax
0x1800134ad  lea     rax, [rbp+0C0h+var_A0]
0x1800134b1  mov     [rbp+0C0h+var_110], rax
0x1800134b5  lea     rcx, [rbp+0C0h+var_A0]; this
0x1800134b9  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800134be  mov     rsi, rax
0x1800134c1  lea     rax, [rbp+0C0h+var_90]
0x1800134c5  mov     [rbp+0C0h+var_108], rax
0x1800134c9  lea     rcx, [rbp+0C0h+var_90]; this
0x1800134cd  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800134d2  mov     rdi, rax
0x1800134d5  lea     rax, [rbp+0C0h+var_80]
0x1800134d9  mov     [rbp+0C0h+var_100], rax
0x1800134dd  lea     rcx, [rbp+0C0h+var_80]; this
0x1800134e1  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800134e6  mov     rbx, rax
0x1800134e9  lea     rax, [rbp+0C0h+var_70]
0x1800134ed  mov     [rbp+0C0h+var_F8], rax
0x1800134f1  mov     rdx, [rbp+0C0h+arg_8]; unsigned __int16 *
0x1800134f8  lea     rcx, [rbp+0C0h+var_70]; this
0x1800134fc  call    ??0CInsertionString@@QEAA@PEBG@Z; CInsertionString::CInsertionString(ushort const *)
0x180013501  nop
0x180013502  mov     edx, 4
0x180013507  mov     rcx, [rbp+0C0h+arg_18]
0x18001350e  mov     [rsp+60h], rcx
0x180013513  mov     rcx, [rsp+78h]
0x180013518  mov     [rsp+1C0h+var_168], rcx
0x18001351d  mov     [rsp+1C0h+var_170], r13
0x180013522  mov     [rsp+1C0h+var_178], r12
0x180013527  mov     [rsp+1C0h+var_180], r15
0x18001352c  mov     [rsp+1C0h+var_188], r14
0x180013531  mov     [rsp+1C0h+var_190], rsi
0x180013536  mov     [rsp+1C0h+var_198], rdi
0x18001353b  mov     [rsp+1C0h+var_1A0], rbx
0x180013540  mov     r9, rax
0x180013543  lea     r8, WBEM_MC_WBEM_REPOSITORY_BACKUP_STARTED
0x18001354a  mov     rbx, [rsp+1C0h+var_150]
0x18001354f  mov     rcx, rbx
0x180013552  call    cs:__imp_?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z; CEventLog::Report(ushort,_EVENT_DESCRIPTOR const &,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString)
0x180013558  jmp     short loc_18001355F
0x18001355a  mov     rbx, [rsp+1C0h+var_150]
0x18001355f  mov     r8d, [rbp+0C0h+arg_10]; int
0x180013566  mov     rdx, [rbp+0C0h+arg_8]; unsigned __int16 *
0x18001356d  mov     rcx, [rbp+0C0h+arg_0]; this
0x180013574  call    ?BackupHelper@CWbemBackupRestore@@IEAAJPEBGJ@Z; CWbemBackupRestore::BackupHelper(ushort const *,long)
0x180013579  mov     dword ptr [rbp+0C0h+arg_18], eax
0x18001357f  test    rbx, rbx
0x180013582  jz      loc_1800136C9
0x180013588  lea     rax, [rbp+0C0h+var_70]
0x18001358c  mov     [rbp+0C0h+var_F8], rax
0x180013590  lea     rcx, [rbp+0C0h+var_70]; this
0x180013594  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180013599  mov     [rsp+78h], rax
0x18001359e  lea     rax, [rbp+0C0h+var_80]
0x1800135a2  mov     [rbp+0C0h+var_100], rax
0x1800135a6  lea     rcx, [rbp+0C0h+var_80]; this
0x1800135aa  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800135af  mov     [rbp+0C0h+var_140], rax
0x1800135b3  lea     rax, [rbp+0C0h+var_90]
0x1800135b7  mov     [rbp+0C0h+var_108], rax
0x1800135bb  lea     rcx, [rbp+0C0h+var_90]; this
0x1800135bf  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800135c4  mov     r13, rax
0x1800135c7  lea     rax, [rbp+0C0h+var_A0]
0x1800135cb  mov     [rbp+0C0h+var_110], rax
0x1800135cf  lea     rcx, [rbp+0C0h+var_A0]; this
0x1800135d3  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800135d8  mov     r12, rax
0x1800135db  lea     rax, [rbp+0C0h+var_B0]
0x1800135df  mov     [rbp+0C0h+var_118], rax
0x1800135e3  lea     rcx, [rbp+0C0h+var_B0]; this
0x1800135e7  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1800135ec  mov     r15, rax
0x1800135ef  lea     rax, [rbp+0C0h+var_C0]
0x1800135f3  mov     [rbp+0C0h+var_120], rax
0x1800135f7  lea     rcx, [rbp+0C0h+var_C0]; this
0x1800135fb  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180013600  mov     r14, rax
0x180013603  lea     rax, [rbp+0C0h+var_D0]
0x180013607  mov     [rbp+0C0h+var_128], rax
0x18001360b  lea     rcx, [rbp+0C0h+var_D0]; this
0x18001360f  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180013614  mov     rsi, rax
0x180013617  lea     rax, [rbp+0C0h+var_E0]
0x18001361b  mov     [rbp+0C0h+var_130], rax
0x18001361f  lea     rcx, [rbp+0C0h+var_E0]; this
0x180013623  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x180013628  mov     rdi, rax
0x18001362b  lea     rax, [rbp+0C0h+var_F0]
0x18001362f  mov     [rbp+0C0h+var_138], rax
0x180013633  mov     edx, dword ptr [rbp+0C0h+arg_18]
0x180013639  lea     rcx, [rbp+0C0h+var_F0]
0x18001363d  call    cs:__imp_??0CInsertionString@@QEAA@J@Z; CInsertionString::CInsertionString(long)
0x180013643  mov     rbx, rax
0x180013646  lea     rax, [rbp+0C0h+var_50]
0x18001364a  mov     [rbp+0C0h+var_60], rax
0x18001364e  mov     rdx, [rbp+0C0h+arg_8]; unsigned __int16 *
0x180013655  lea     rcx, [rbp+0C0h+var_50]; this
0x180013659  call    ??0CInsertionString@@QEAA@PEBG@Z; CInsertionString::CInsertionString(ushort const *)
0x18001365e  nop
0x18001365f  mov     edx, 4
0x180013664  mov     rcx, [rsp+78h]
0x180013669  mov     [rsp+60h], rcx
0x18001366e  mov     rcx, [rbp+0C0h+var_140]
0x180013672  mov     [rsp+1C0h+var_168], rcx
0x180013677  mov     [rsp+1C0h+var_170], r13
0x18001367c  mov     [rsp+1C0h+var_178], r12
0x180013681  mov     [rsp+1C0h+var_180], r15
0x180013686  mov     [rsp+1C0h+var_188], r14
0x18001368b  mov     [rsp+1C0h+var_190], rsi
0x180013690  mov     [rsp+1C0h+var_198], rdi
0x180013695  mov     [rsp+1C0h+var_1A0], rbx
0x18001369a  mov     r9, rax
0x18001369d  lea     r8, WBEM_MC_WBEM_REPOSITORY_BACKUP_COMPLETED; "D"
0x1800136a4  mov     rbx, [rsp+1C0h+var_150]
0x1800136a9  mov     rcx, rbx
0x1800136ac  call    cs:__imp_?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z; CEventLog::Report(ushort,_EVENT_DESCRIPTOR const &,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString)
0x1800136b2  mov     rcx, rbx
0x1800136b5  call    cs:__imp_?Close@CEventLog@@QEAAHXZ; CEventLog::Close(void)
0x1800136bb  mov     rcx, rbx; this
0x1800136be  call    ??_GCEventLog@@QEAAPEAXI@Z; CEventLog::`scalar deleting destructor'(uint)
0x1800136c3  mov     eax, dword ptr [rbp+0C0h+arg_18]
0x1800136c9  add     rsp, 188h
0x1800136d0  pop     r15
0x1800136d2  pop     r14
0x1800136d4  pop     r13
0x1800136d6  pop     r12
0x1800136d8  pop     rdi
0x1800136d9  pop     rsi
0x1800136da  pop     rbx
0x1800136db  pop     rbp
0x1800136dc  retn
```
