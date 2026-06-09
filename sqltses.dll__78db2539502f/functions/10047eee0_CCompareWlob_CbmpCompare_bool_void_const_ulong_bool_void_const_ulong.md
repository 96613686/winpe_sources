# CCompareWlob::CbmpCompare(bool,void const *,ulong,bool,void const *,ulong)

- ea: `0x10047eee0`
- end: `0x10047f34d`
- name: `?CbmpCompare@CCompareWlob@@UEAAK_NPEBXK01K@Z`
- size: `1133`
- prototype: `unsigned int __fastcall(CCompareWlob *__hidden this, bool, const void *, unsigned int, bool, const void *Src, size_t Size)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x100401170`
- `0x100401cc0`
- `0x1004024b0`
- `0x10047eee0`
- `0x1004847a0`

## import_xrefs

- `sqldk!SystemThread_TlsIndex` at `0x10047ef42`
- `sqldk!SystemThread_TlsOffset` at `0x10047ef4c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10047ef67`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10047ef67`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10047f1b7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10047f1f9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10047f26f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10047f2bc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10047f1b7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10047f1f9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10047f26f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10047f2bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CCompareWlob::CbmpCompare(
        CCompareWlob *this,
        char a2,
        char *a3,
        unsigned int a4,
        bool a5,
        char *Src,
        size_t Size)
{
  char *v7; // r9
  char *v9; // r13
  __int64 v10; // rbx
  __int64 v11; // rax
  unsigned int v12; // r14d
  unsigned int v13; // r15d
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  void *v17; // rsp
  void *v18; // rsp
  unsigned __int64 v19; // rax
  __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  void *v22; // rsp
  void *v23; // rsp
  unsigned __int64 v24; // rax
  void *v25; // rsp
  unsigned __int64 v26; // rax
  void *v27; // rsp
  unsigned int v28; // ebx
  int v29; // esi
  struct IMemObj *v30; // r15
  int v31; // eax
  char v32; // bl
  char v33; // cl
  int v34; // eax
  bool v35; // zf
  int v36; // ebx
  unsigned int v38; // [rsp+40h] [rbp-10h]
  wchar_t v39[2]; // [rsp+50h] [rbp+0h] BYREF
  unsigned int v40; // [rsp+54h] [rbp+4h]
  unsigned int v41; // [rsp+58h] [rbp+8h]
  _BYTE v42[4]; // [rsp+5Ch] [rbp+Ch] BYREF
  _BYTE v43[4]; // [rsp+60h] [rbp+10h] BYREF
  _BYTE v44[4]; // [rsp+64h] [rbp+14h] BYREF
  _BYTE v45[8]; // [rsp+68h] [rbp+18h] BYREF
  char *v46; // [rsp+70h] [rbp+20h]
  struct IMemObj *v47; // [rsp+78h] [rbp+28h]
  wchar_t *v48; // [rsp+80h] [rbp+30h]
  __int64 v49; // [rsp+88h] [rbp+38h]
  int v50; // [rsp+90h] [rbp+40h] BYREF
  char v51; // [rsp+94h] [rbp+44h]
  __int64 v52; // [rsp+98h] [rbp+48h]
  __int64 v53; // [rsp+B0h] [rbp+60h]
  __int64 v54; // [rsp+C0h] [rbp+70h]
  __int64 v55; // [rsp+D8h] [rbp+88h]
  char v56; // [rsp+E0h] [rbp+90h]
  int v57; // [rsp+F0h] [rbp+A0h] BYREF
  char v58; // [rsp+F4h] [rbp+A4h]
  __int64 v59; // [rsp+F8h] [rbp+A8h]
  __int64 v60; // [rsp+110h] [rbp+C0h]
  __int64 v61; // [rsp+120h] [rbp+D0h]
  __int64 v62; // [rsp+138h] [rbp+E8h]
  char v63; // [rsp+140h] [rbp+F0h]

  v49 = -2;
  v40 = a4;
  v7 = a3;
  v46 = a3;
  LOBYTE(v39[0]) = a2;
  v9 = Src;
  v41 = Size;
  v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v11 = *(_QWORD *)(v10 + 256);
  if ( !v11 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v11 = *(_QWORD *)(v10 + 256);
    v7 = v46;
  }
  v47 = *(struct IMemObj **)(v11 + 1000);
  v12 = 8096;
  if ( !*((_DWORD *)this + 2) || (v13 = 8096, *((_DWORD *)this + 12)) )
    v13 = 4048;
  if ( !*((_DWORD *)this + 3) || *((_DWORD *)this + 13) )
    v12 = 4048;
  v14 = 2LL * v13;
  v15 = v14 + 15;
  if ( v14 + 15 < v14 )
    v15 = 0xFFFFFFFFFFFFFF0LL;
  v16 = v15 & 0xFFFFFFFFFFFFFFF0uLL;
  v17 = alloca(v16);
  v18 = alloca(v16);
  v48 = v39;
  v19 = 2LL * v12;
  v20 = v19 + 15;
  if ( v19 + 15 < v19 )
    v20 = 0xFFFFFFFFFFFFFF0LL;
  v21 = v20 & 0xFFFFFFFFFFFFFFF0uLL;
  v22 = alloca(v21);
  v23 = alloca(v21);
  if ( ((unsigned __int8)v7 & 7) != 0 )
  {
    v24 = v40 + 7 + 15LL;
    if ( v24 <= v40 + 7 )
      v24 = 0xFFFFFFFFFFFFFF0LL;
    v25 = alloca(v24 & 0xFFFFFFFFFFFFFFF0uLL);
    memmove(v39, v7, v40);
    v46 = (char *)v39;
  }
  if ( ((unsigned __int8)Src & 7) != 0 )
  {
    v26 = (unsigned int)(Size + 7) + 15LL;
    if ( v26 <= (unsigned int)(Size + 7) )
      v26 = 0xFFFFFFFFFFFFFF0LL;
    v27 = alloca(v26 & 0xFFFFFFFFFFFFFFF0uLL);
    memmove(v39, Src, (unsigned int)Size);
    v9 = (char *)v39;
  }
  v28 = 1;
  v57 = 1;
  v58 = 1;
  v29 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 1;
  v50 = 1;
  v51 = 1;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 1;
  if ( LOBYTE(v39[0]) )
  {
    v30 = v47;
  }
  else
  {
    v38 = v13;
    v30 = v47;
    CWCharReaderOnStr::InitReaderOnStr(
      (CWCharReaderOnStr *)&v57,
      v47,
      *((_DWORD *)this + 14),
      *((_DWORD *)this + 2),
      *((_DWORD *)this + 12),
      v46,
      v40,
      v48,
      v38);
  }
  if ( !a5 )
    CWCharReaderOnStr::InitReaderOnStr(
      (CWCharReaderOnStr *)&v50,
      v30,
      *((_DWORD *)this + 14),
      *((_DWORD *)this + 3),
      *((_DWORD *)this + 13),
      v9,
      v41,
      v39,
      v12);
  if ( !v58 )
  {
    if ( v57 )
      goto LABEL_31;
    if ( (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v60 + 152LL))(v60, v42) )
      ex_raise(71, 2, 20, 99);
    if ( (v42[0] & 1) == 0 )
    {
LABEL_31:
      if ( v51 )
        goto LABEL_46;
      if ( v50 )
        goto LABEL_36;
      if ( (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v53 + 152LL))(v53, v43) )
        ex_raise(71, 2, 20, 99);
      if ( (v43[0] & 1) == 0 )
      {
LABEL_36:
        v31 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, int *, int *))this + 5))(
                *((_QWORD *)this + 4),
                *((unsigned int *)this + 6),
                *((unsigned __int8 *)this + 60),
                &v57,
                &v50)
            - 2;
        if ( v31 >= 0 )
        {
          v28 = 4;
          if ( !v31 )
            v28 = 2;
        }
        goto LABEL_60;
      }
    }
  }
  if ( !v51 )
  {
    if ( v50 )
      goto LABEL_45;
    if ( (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v53 + 152LL))(v53, v44) )
      ex_raise(71, 2, 20, 99);
    if ( (v44[0] & 1) == 0 )
    {
LABEL_45:
      v32 = 0;
      goto LABEL_47;
    }
  }
LABEL_46:
  v32 = 1;
LABEL_47:
  if ( v58 )
    goto LABEL_53;
  if ( v57 )
    goto LABEL_52;
  if ( (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v60 + 152LL))(v60, v45) )
    ex_raise(71, 2, 20, 99);
  if ( (v45[0] & 1) != 0 )
  {
LABEL_53:
    v33 = 1;
    v29 = 8;
  }
  else
  {
LABEL_52:
    v33 = 0;
  }
  v34 = v29 | 0x10;
  if ( !v32 )
    v34 = v29;
  if ( !v33 || (v35 = v32 == 0, v36 = 64, v35) )
    v36 = 32;
  v28 = v34 | v36;
LABEL_60:
  if ( !v50 && v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  if ( !v57 && v60 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
  return v28;
}

```

## disassembly

```asm
0x10047eee0  push    rbp
0x10047eee2  push    rsi
0x10047eee3  push    rdi
0x10047eee4  push    r12
0x10047eee6  push    r13
0x10047eee8  push    r14
0x10047eeea  push    r15
0x10047eeec  sub     rsp, 160h
0x10047eef3  lea     rbp, [rsp+50h]
0x10047eef8  mov     [rbp+140h+var_108], 0FFFFFFFFFFFFFFFEh
0x10047ef00  mov     [rbp+140h+arg_8], rbx
0x10047ef07  mov     rax, cs:__security_cookie
0x10047ef0e  xor     rax, rbp
0x10047ef11  mov     [rbp+140h+var_40], rax
0x10047ef18  mov     [rbp+140h+var_13C], r9d
0x10047ef1c  mov     r9, r8
0x10047ef1f  mov     [rbp+140h+var_120], r8
0x10047ef23  mov     byte ptr [rbp+140h+var_140], dl
0x10047ef26  mov     rdi, rcx
0x10047ef29  mov     r13, [rbp+140h+Src]
0x10047ef30  mov     esi, dword ptr [rbp+140h+Size]
0x10047ef36  mov     [rbp+140h+var_138], esi
0x10047ef39  mov     r10, gs:58h
0x10047ef42  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10047ef49  mov     r8d, [rax]
0x10047ef4c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10047ef53  mov     ebx, [rax]
0x10047ef55  add     rbx, [r10+r8*8]
0x10047ef59  mov     rax, [rbx+100h]
0x10047ef60  test    rax, rax
0x10047ef63  jnz     short loc_10047EF78
0x10047ef65  xor     ecx, ecx
0x10047ef67  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10047ef6d  mov     rax, [rbx+100h]
0x10047ef74  mov     r9, [rbp+140h+var_120]
0x10047ef78  mov     rax, [rax+3E8h]
0x10047ef7f  mov     [rbp+140h+var_118], rax
0x10047ef83  mov     r14d, 1FA0h
0x10047ef89  cmp     dword ptr [rdi+8], 0
0x10047ef8d  jz      short loc_10047EF98
0x10047ef8f  cmp     dword ptr [rdi+30h], 0
0x10047ef93  mov     r15d, r14d
0x10047ef96  jz      short loc_10047EF9E
0x10047ef98  mov     r15d, 0FD0h
0x10047ef9e  cmp     dword ptr [rdi+0Ch], 0
0x10047efa2  jz      short loc_10047EFAA
0x10047efa4  cmp     dword ptr [rdi+34h], 0
0x10047efa8  jz      short loc_10047EFB0
0x10047efaa  mov     r14d, 0FD0h
0x10047efb0  mov     eax, r15d
0x10047efb3  add     rax, rax
0x10047efb6  lea     rcx, [rax+0Fh]
0x10047efba  mov     r8, 0FFFFFFFFFFFFFF0h
0x10047efc4  cmp     rcx, rax
0x10047efc7  ja      short loc_10047EFCC
0x10047efc9  mov     rcx, r8
0x10047efcc  and     rcx, 0FFFFFFFFFFFFFFF0h
0x10047efd0  mov     rax, rcx
0x10047efd3  call    _alloca_probe
0x10047efd8  sub     rsp, rcx
0x10047efdb  lea     rax, [rsp+190h+var_140]
0x10047efe0  mov     [rbp+140h+var_110], rax
0x10047efe4  mov     eax, r14d
0x10047efe7  add     rax, rax
0x10047efea  lea     rcx, [rax+0Fh]
0x10047efee  cmp     rcx, rax
0x10047eff1  ja      short loc_10047EFF6
0x10047eff3  mov     rcx, r8
0x10047eff6  and     rcx, 0FFFFFFFFFFFFFFF0h
0x10047effa  mov     rax, rcx
0x10047effd  call    _alloca_probe
0x10047f002  sub     rsp, rcx
0x10047f005  lea     r12, [rsp+190h+var_140]
0x10047f00a  test    r9b, 7
0x10047f00e  jz      short loc_10047F059
0x10047f010  mov     edx, [rbp+140h+var_13C]
0x10047f013  lea     eax, [rdx+7]
0x10047f016  mov     ecx, eax
0x10047f018  add     rax, 0Fh
0x10047f01c  cmp     rax, rcx
0x10047f01f  ja      short loc_10047F024
0x10047f021  mov     rax, r8
0x10047f024  and     rax, 0FFFFFFFFFFFFFFF0h
0x10047f028  call    _alloca_probe
0x10047f02d  sub     rsp, rax
0x10047f030  lea     rbx, [rsp+190h+var_140]
0x10047f035  add     rbx, 7
0x10047f039  and     rbx, 0FFFFFFFFFFFFFFF8h
0x10047f03d  mov     r8, rdx; Size
0x10047f040  mov     rdx, r9; Src
0x10047f043  mov     rcx, rbx; void *
0x10047f046  call    memmove
0x10047f04b  mov     [rbp+140h+var_120], rbx
0x10047f04f  mov     r8, 0FFFFFFFFFFFFFF0h
0x10047f059  test    r13b, 7
0x10047f05d  jz      short loc_10047F09A
0x10047f05f  lea     eax, [rsi+7]
0x10047f062  mov     ecx, eax
0x10047f064  add     rax, 0Fh
0x10047f068  cmp     rax, rcx
0x10047f06b  ja      short loc_10047F070
0x10047f06d  mov     rax, r8
0x10047f070  and     rax, 0FFFFFFFFFFFFFFF0h
0x10047f074  call    _alloca_probe
0x10047f079  sub     rsp, rax
0x10047f07c  lea     rbx, [rsp+190h+var_140]
0x10047f081  add     rbx, 7
0x10047f085  and     rbx, 0FFFFFFFFFFFFFFF8h
0x10047f089  mov     r8, rsi; Size
0x10047f08c  mov     rdx, r13; Src
0x10047f08f  mov     rcx, rbx; void *
0x10047f092  call    memmove
0x10047f097  mov     r13, rbx
0x10047f09a  mov     ebx, 1
0x10047f09f  mov     [rbp+140h+var_A0], ebx
0x10047f0a5  mov     [rbp+140h+var_9C], bl
0x10047f0ab  xor     esi, esi
0x10047f0ad  mov     [rbp+140h+var_98], rsi
0x10047f0b4  mov     [rbp+140h+var_80], rsi
0x10047f0bb  mov     [rbp+140h+var_70], rsi
0x10047f0c2  mov     [rbp+140h+var_58], rsi
0x10047f0c9  mov     [rbp+140h+var_50], bl
0x10047f0cf  mov     [rbp+140h+var_100], ebx
0x10047f0d2  mov     [rbp+140h+var_FC], bl
0x10047f0d5  mov     [rbp+140h+var_F8], rsi
0x10047f0d9  mov     [rbp+140h+var_E0], rsi
0x10047f0dd  mov     [rbp+140h+var_D0], rsi
0x10047f0e1  mov     [rbp+140h+var_B8], rsi
0x10047f0e8  mov     [rbp+140h+var_B0], bl
0x10047f0ee  cmp     byte ptr [rbp+140h+var_140], sil
0x10047f0f2  jnz     short loc_10047F136
0x10047f0f4  mov     [rsp+190h+var_150], r15d; unsigned int
0x10047f0f9  mov     rax, [rbp+140h+var_110]
0x10047f0fd  mov     [rsp+190h+var_158], rax; wchar_t *
0x10047f102  mov     eax, [rbp+140h+var_13C]
0x10047f105  mov     [rsp+190h+var_160], eax; unsigned int
0x10047f109  mov     rax, [rbp+140h+var_120]
0x10047f10d  mov     [rsp+190h+var_168], rax; char *
0x10047f112  mov     eax, [rdi+30h]
0x10047f115  mov     [rsp+190h+var_170], eax; int
0x10047f119  mov     r9d, [rdi+8]; int
0x10047f11d  mov     r8d, [rdi+38h]; unsigned int
0x10047f121  mov     r15, [rbp+140h+var_118]
0x10047f125  mov     rdx, r15; struct IMemObj *
0x10047f128  lea     rcx, [rbp+140h+var_A0]; this
0x10047f12f  call    ?InitReaderOnStr@CWCharReaderOnStr@@QEAAXPEAVIMemObj@@IHHPEBXKPEA_WK@Z; CWCharReaderOnStr::InitReaderOnStr(IMemObj *,uint,int,int,void const *,ulong,wchar_t *,ulong)
0x10047f134  jmp     short loc_10047F13A
0x10047f136  mov     r15, [rbp+140h+var_118]
0x10047f13a  cmp     [rbp+140h+arg_20], 0
0x10047f141  jnz     short loc_10047F174
0x10047f143  mov     [rsp+190h+var_150], r14d; unsigned int
0x10047f148  mov     [rsp+190h+var_158], r12; wchar_t *
0x10047f14d  mov     eax, [rbp+140h+var_138]
0x10047f150  mov     [rsp+190h+var_160], eax; unsigned int
0x10047f154  mov     [rsp+190h+var_168], r13; char *
0x10047f159  mov     eax, [rdi+34h]
0x10047f15c  mov     [rsp+190h+var_170], eax; int
0x10047f160  mov     r9d, [rdi+0Ch]; int
0x10047f164  mov     r8d, [rdi+38h]; unsigned int
0x10047f168  mov     rdx, r15; struct IMemObj *
0x10047f16b  lea     rcx, [rbp+140h+var_100]; this
0x10047f16f  call    ?InitReaderOnStr@CWCharReaderOnStr@@QEAAXPEAVIMemObj@@IHHPEBXKPEA_WK@Z; CWCharReaderOnStr::InitReaderOnStr(IMemObj *,uint,int,int,void const *,ulong,wchar_t *,ulong)
0x10047f174  mov     r14d, 2
0x10047f17a  cmp     [rbp+140h+var_9C], 0
0x10047f181  jnz     loc_10047F23D
0x10047f187  cmp     [rbp+140h+var_A0], 0
0x10047f18e  jnz     short loc_10047F1C3
0x10047f190  mov     rcx, [rbp+140h+var_80]
0x10047f197  mov     rax, [rcx]
0x10047f19a  lea     rdx, [rbp+140h+var_134]
0x10047f19e  call    qword ptr [rax+98h]
0x10047f1a4  test    eax, eax
0x10047f1a6  jz      short loc_10047F1BD
0x10047f1a8  lea     r9d, [r14+61h]
0x10047f1ac  lea     r8d, [r14+12h]
0x10047f1b0  mov     edx, r14d
0x10047f1b3  lea     ecx, [r14+45h]
0x10047f1b7  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10047f1bd  test    [rbp+140h+var_134], 1
0x10047f1c1  jnz     short loc_10047F23D
0x10047f1c3  cmp     [rbp+140h+var_FC], 0
0x10047f1c7  jnz     loc_10047F27F
0x10047f1cd  cmp     [rbp+140h+var_100], 0
0x10047f1d1  jnz     short loc_10047F205
0x10047f1d3  mov     rcx, [rbp+140h+var_E0]
0x10047f1d7  mov     rax, [rcx]
0x10047f1da  lea     rdx, [rbp+140h+var_130]
0x10047f1de  call    qword ptr [rax+98h]
0x10047f1e4  test    eax, eax
0x10047f1e6  jz      short loc_10047F1FF
0x10047f1e8  mov     r9d, 63h ; 'c'
0x10047f1ee  lea     r8d, [r9-4Fh]
0x10047f1f2  mov     edx, r14d
0x10047f1f5  lea     ecx, [r9-1Ch]
0x10047f1f9  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10047f1ff  test    [rbp+140h+var_130], 1
0x10047f203  jnz     short loc_10047F23D
0x10047f205  lea     rax, [rbp+140h+var_100]
0x10047f209  mov     qword ptr [rsp+190h+var_170], rax
0x10047f20e  lea     r9, [rbp+140h+var_A0]
0x10047f215  movzx   r8d, byte ptr [rdi+3Ch]
0x10047f21a  mov     edx, [rdi+18h]
0x10047f21d  mov     rcx, [rdi+20h]
0x10047f221  call    qword ptr [rdi+28h]
0x10047f224  sub     eax, r14d
0x10047f227  js      loc_10047F2F1
0x10047f22d  mov     ebx, 4
0x10047f232  test    eax, eax
0x10047f234  cmovz   ebx, r14d
0x10047f238  jmp     loc_10047F2F1
0x10047f23d  cmp     [rbp+140h+var_FC], 0
0x10047f241  jnz     short loc_10047F27F
0x10047f243  cmp     [rbp+140h+var_100], 0
0x10047f247  jnz     short loc_10047F27B
0x10047f249  mov     rcx, [rbp+140h+var_E0]
0x10047f24d  mov     rax, [rcx]
0x10047f250  lea     rdx, [rbp+140h+var_12C]
0x10047f254  call    qword ptr [rax+98h]
0x10047f25a  test    eax, eax
0x10047f25c  jz      short loc_10047F275
0x10047f25e  mov     r9d, 63h ; 'c'
0x10047f264  lea     r8d, [r9-4Fh]
0x10047f268  mov     edx, r14d
0x10047f26b  lea     ecx, [r9-1Ch]
0x10047f26f  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10047f275  test    [rbp+140h+var_12C], 1
0x10047f279  jnz     short loc_10047F27F
0x10047f27b  xor     bl, bl
0x10047f27d  jmp     short loc_10047F281
0x10047f27f  mov     bl, 1
0x10047f281  cmp     [rbp+140h+var_9C], 0
0x10047f288  jnz     short loc_10047F2CC
0x10047f28a  cmp     [rbp+140h+var_A0], 0
0x10047f291  jnz     short loc_10047F2C8
0x10047f293  mov     rcx, [rbp+140h+var_80]
0x10047f29a  mov     rax, [rcx]
0x10047f29d  lea     rdx, [rbp+140h+var_128]
0x10047f2a1  call    qword ptr [rax+98h]
0x10047f2a7  test    eax, eax
0x10047f2a9  jz      short loc_10047F2C2
0x10047f2ab  mov     r9d, 63h ; 'c'
0x10047f2b1  lea     r8d, [r9-4Fh]
0x10047f2b5  mov     edx, r14d
0x10047f2b8  lea     ecx, [r9-1Ch]
0x10047f2bc  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10047f2c2  test    [rbp+140h+var_128], 1
0x10047f2c6  jnz     short loc_10047F2CC
0x10047f2c8  xor     cl, cl
0x10047f2ca  jmp     short loc_10047F2D3
0x10047f2cc  mov     cl, 1
0x10047f2ce  mov     esi, 8
0x10047f2d3  mov     eax, esi
0x10047f2d5  or      eax, 10h
0x10047f2d8  test    bl, bl
0x10047f2da  cmovz   eax, esi
0x10047f2dd  test    cl, cl
0x10047f2df  jz      short loc_10047F2EA
0x10047f2e1  test    bl, bl
0x10047f2e3  mov     ebx, 40h ; '@'
0x10047f2e8  jnz     short loc_10047F2EF
0x10047f2ea  mov     ebx, 20h ; ' '
0x10047f2ef  or      ebx, eax
0x10047f2f1  cmp     [rbp+140h+var_100], 0
0x10047f2f5  jnz     short loc_10047F307
0x10047f2f7  mov     rcx, [rbp+140h+var_E0]
0x10047f2fb  test    rcx, rcx
0x10047f2fe  jz      short loc_10047F307
0x10047f300  mov     rax, [rcx]
0x10047f303  call    qword ptr [rax+10h]
0x10047f306  nop
0x10047f307  cmp     [rbp+140h+var_A0], 0
0x10047f30e  jnz     short loc_10047F322
0x10047f310  mov     rcx, [rbp+140h+var_80]
0x10047f317  test    rcx, rcx
0x10047f31a  jz      short loc_10047F322
0x10047f31c  mov     rdx, [rcx]
0x10047f31f  call    qword ptr [rdx+10h]
0x10047f322  mov     eax, ebx
0x10047f324  mov     rcx, [rbp+140h+var_40]
0x10047f32b  xor     rcx, rbp; StackCookie
0x10047f32e  call    __security_check_cookie
0x10047f333  mov     rbx, [rbp+140h+arg_8]
0x10047f33a  lea     rsp, [rbp+110h]
0x10047f341  pop     r15
0x10047f343  pop     r14
0x10047f345  pop     r13
0x10047f347  pop     r12
0x10047f349  pop     rdi
0x10047f34a  pop     rsi
0x10047f34b  pop     rbp
0x10047f34c  retn
```
