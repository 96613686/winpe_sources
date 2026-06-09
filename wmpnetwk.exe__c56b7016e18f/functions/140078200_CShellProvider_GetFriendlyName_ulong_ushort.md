# CShellProvider::GetFriendlyName(ulong,ushort *)

- ea: `0x140078200`
- end: `0x140078527`
- name: `?GetFriendlyName@CShellProvider@@UEAAJKPEAG@Z`
- size: `807`
- prototype: `int(CShellProvider *__hidden this, unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x140003750`
- `0x14000b3b0`
- `0x14000b3f0`
- `0x14000c920`
- `0x140027660`
- `0x1400282b0`
- `0x14002eb14`
- `0x14003e5f4`
- `0x14003f17c`
- `0x14004a79c`
- `0x140054490`
- `0x14005480c`
- `0x140076f88`
- `0x140078200`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x1400782c1`
- `KERNEL32!GetComputerNameW` at `0x1400782c1`
- `KERNEL32!GetLastError` at `0x140078318`
- `KERNEL32!GetLastError` at `0x140078318`

## pseudocode

```c
__int64 __fastcall CShellProvider::GetFriendlyName(CShellProvider *this, unsigned int a2, unsigned __int16 *a3)
{
  unsigned __int64 v4; // r14
  _QWORD *v6; // rax
  WCHAR *BufferSetLength; // rax
  signed int v8; // edi
  signed int LastError; // eax
  PVOID *v10; // r10
  unsigned int v11; // r15d
  _QWORD *v12; // rax
  __int64 v13; // rbx
  unsigned int v14; // r15d
  _QWORD *v15; // rax
  unsigned __int16 *v17; // [rsp+30h] [rbp-10h] BYREF
  __int64 v18; // [rsp+38h] [rbp-8h] BYREF
  DWORD nSize; // [rsp+80h] [rbp+40h] BYREF
  __int64 v20; // [rsp+90h] [rbp+50h] BYREF
  __int64 v21; // [rsp+98h] [rbp+58h] BYREF

  v4 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids, a2, a3);
  }
  *a3 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v20);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v21);
  v6 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                   (char *)this + 88,
                   &v17,
                   64);
  ATL::CSimpleStringT<unsigned short,0>::operator=((_QWORD *)this + 104, v6);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v17);
  ATL::CSimpleStringT<unsigned short,0>::operator=(&v21, (_QWORD *)this + 11);
  nSize = 16;
  BufferSetLength = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(&v20, 16);
  if ( GetComputerNameW(BufferSetLength, &nSize) )
  {
    v8 = 0;
    ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&v20, 0xFFFFFFFFLL);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, &WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids, v20);
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v17);
    v11 = 0;
    if ( (int)v4 - 4 >= 0 )
      v11 = v4 - 4;
    v12 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                      &v20,
                      &v18,
                      v11);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v20, v12);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v18);
    v13 = v20;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        158,
        (unsigned int)&WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids,
        v20,
        v11);
    }
    v14 = 0;
    if ( (int)v4 - *(_DWORD *)(v13 - 16) - 4 >= 0 )
      v14 = v4 - *(_DWORD *)(v13 - 16) - 4;
    v15 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                      &v21,
                      &v18,
                      v14);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v21, v15);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v18);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        159,
        (unsigned int)&WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids,
        v21,
        v14);
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::FormatMessageW(
      &v17,
      L"%1!ls!: %2!ls!:",
      v13,
      v21);
    StringCchCopyW(a3, v4, v17);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        160,
        (unsigned int)&WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids,
        (_DWORD)a3,
        v4);
    }
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v17);
    v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_37:
    if ( v10 != &WPP_GLOBAL_Control
      && (*((_BYTE *)v10 + 28) & 1) != 0
      && *((unsigned __int8 *)v10 + 25) >= ((v8 >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_dS(
        (unsigned int)v10[2],
        161,
        (unsigned int)&WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids,
        v8,
        (__int64)a3);
    }
    goto LABEL_41;
  }
  ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&v20, 0);
  LastError = GetLastError();
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  else
    v8 = LastError;
  if ( v8 >= 0 )
    v8 = -2147467259;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        157,
        &WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids,
        (unsigned int)LastError);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_37;
  }
LABEL_41:
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v21);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140078200  push    rbp
0x140078202  push    rbx
0x140078203  push    rsi
0x140078204  push    rdi
0x140078205  push    r12
0x140078207  push    r14
0x140078209  push    r15
0x14007820b  mov     rbp, rsp
0x14007820e  sub     rsp, 40h
0x140078212  mov     rsi, r8
0x140078215  mov     r14d, edx
0x140078218  mov     rdi, rcx
0x14007821b  mov     rcx, cs:WPP_GLOBAL_Control
0x140078222  lea     r15, WPP_GLOBAL_Control
0x140078229  lea     r12, WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids
0x140078230  cmp     rcx, r15
0x140078233  jz      short loc_14007825A
0x140078235  test    byte ptr [rcx+1Ch], 1
0x140078239  jz      short loc_14007825A
0x14007823b  cmp     byte ptr [rcx+19h], 5
0x14007823f  jb      short loc_14007825A
0x140078241  mov     rcx, [rcx+10h]
0x140078245  mov     edx, 9Bh
0x14007824a  mov     [rsp+40h+var_20], r8
0x14007824f  mov     r9d, r14d
0x140078252  mov     r8, r12
0x140078255  call    WPP_SF_dq
0x14007825a  xor     eax, eax
0x14007825c  lea     rcx, [rbp+arg_10]
0x140078260  mov     [rsi], ax
0x140078263  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140078268  lea     rcx, [rbp+arg_18]
0x14007826c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140078271  mov     r8d, 40h ; '@'
0x140078277  lea     rdx, [rbp+var_10]
0x14007827b  lea     rcx, [rdi+58h]
0x14007827f  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Left(int)
0x140078284  lea     rcx, [rdi+340h]
0x14007828b  mov     rdx, rax
0x14007828e  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140078293  lea     rcx, [rbp+var_10]
0x140078297  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14007829c  lea     rdx, [rdi+58h]
0x1400782a0  lea     rcx, [rbp+arg_18]
0x1400782a4  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1400782a9  mov     edx, 10h
0x1400782ae  lea     rcx, [rbp+arg_10]
0x1400782b2  mov     [rbp+nSize], edx
0x1400782b5  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x1400782ba  mov     rcx, rax; lpBuffer
0x1400782bd  lea     rdx, [rbp+nSize]; nSize
0x1400782c1  call    cs:__imp_GetComputerNameW
0x1400782c7  mov     bl, 2
0x1400782c9  lea     rcx, [rbp+arg_10]
0x1400782cd  test    eax, eax
0x1400782cf  jz      short loc_140078311
0x1400782d1  xor     edi, edi
0x1400782d3  or      edx, 0FFFFFFFFh
0x1400782d6  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x1400782db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400782e2  cmp     rcx, r15
0x1400782e5  jz      loc_140078378
0x1400782eb  test    [rcx+1Ch], bl
0x1400782ee  jz      loc_140078378
0x1400782f4  cmp     byte ptr [rcx+19h], 5
0x1400782f8  jb      short loc_140078378
0x1400782fa  mov     r9, [rbp+arg_10]
0x1400782fe  mov     edx, 9Ch
0x140078303  mov     rcx, [rcx+10h]
0x140078307  mov     r8, r12
0x14007830a  call    WPP_SF_S
0x14007830f  jmp     short loc_140078378
0x140078311  xor     edx, edx
0x140078313  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x140078318  call    cs:__imp_GetLastError
0x14007831e  test    eax, eax
0x140078320  jg      short loc_140078326
0x140078322  mov     edi, eax
0x140078324  jmp     short loc_14007832F
0x140078326  movzx   edi, ax
0x140078329  or      edi, 80070000h
0x14007832f  test    edi, edi
0x140078331  mov     ecx, 80004005h
0x140078336  cmovns  edi, ecx
0x140078339  mov     r10, cs:WPP_GLOBAL_Control
0x140078340  cmp     r10, r15
0x140078343  jz      loc_140078504
0x140078349  test    [r10+1Ch], bl
0x14007834d  jz      short loc_140078370
0x14007834f  cmp     [r10+19h], bl
0x140078353  jb      short loc_140078370
0x140078355  mov     rcx, [r10+10h]
0x140078359  mov     edx, 9Dh
0x14007835e  mov     r9d, eax
0x140078361  mov     r8, r12
0x140078364  call    WPP_SF_d
0x140078369  mov     r10, cs:WPP_GLOBAL_Control
0x140078370  test    edi, edi
0x140078372  js      loc_1400784CB
0x140078378  lea     rcx, [rbp+var_10]
0x14007837c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140078381  lea     eax, [r14-4]
0x140078385  xor     r15d, r15d
0x140078388  test    eax, eax
0x14007838a  lea     rdx, [rbp+var_8]
0x14007838e  lea     rcx, [rbp+arg_10]
0x140078392  cmovns  r15d, eax
0x140078396  mov     r8d, r15d
0x140078399  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Left(int)
0x14007839e  mov     rdx, rax
0x1400783a1  lea     rcx, [rbp+arg_10]
0x1400783a5  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1400783aa  lea     rcx, [rbp+var_8]
0x1400783ae  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400783b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400783ba  lea     rax, WPP_GLOBAL_Control
0x1400783c1  mov     rbx, [rbp+arg_10]
0x1400783c5  cmp     rcx, rax
0x1400783c8  jz      short loc_1400783EF
0x1400783ca  test    byte ptr [rcx+1Ch], 2
0x1400783ce  jz      short loc_1400783EF
0x1400783d0  cmp     byte ptr [rcx+19h], 5
0x1400783d4  jb      short loc_1400783EF
0x1400783d6  mov     rcx, [rcx+10h]
0x1400783da  mov     edx, 9Eh
0x1400783df  mov     r9, rbx
0x1400783e2  mov     dword ptr [rsp+40h+var_20], r15d
0x1400783e7  mov     r8, r12
0x1400783ea  call    WPP_SF_Sd
0x1400783ef  mov     eax, r14d
0x1400783f2  lea     rdx, [rbp+var_8]
0x1400783f6  sub     eax, [rbx-10h]
0x1400783f9  lea     rcx, [rbp+arg_18]
0x1400783fd  xor     r15d, r15d
0x140078400  add     eax, 0FFFFFFFCh
0x140078403  cmovns  r15d, eax
0x140078407  mov     r8d, r15d
0x14007840a  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Left(int)
0x14007840f  mov     rdx, rax
0x140078412  lea     rcx, [rbp+arg_18]
0x140078416  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14007841b  lea     rcx, [rbp+var_8]
0x14007841f  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140078424  mov     rcx, cs:WPP_GLOBAL_Control
0x14007842b  lea     rax, WPP_GLOBAL_Control
0x140078432  cmp     rcx, rax
0x140078435  jz      short loc_14007845D
0x140078437  test    byte ptr [rcx+1Ch], 2
0x14007843b  jz      short loc_14007845D
0x14007843d  cmp     byte ptr [rcx+19h], 5
0x140078441  jb      short loc_14007845D
0x140078443  mov     r9, [rbp+arg_18]
0x140078447  mov     edx, 9Fh
0x14007844c  mov     rcx, [rcx+10h]
0x140078450  mov     r8, r12
0x140078453  mov     dword ptr [rsp+40h+var_20], r15d
0x140078458  call    WPP_SF_Sd
0x14007845d  mov     r9, [rbp+arg_18]
0x140078461  lea     rdx, a1Ls2Ls; "%1!ls!: %2!ls!:"
0x140078468  mov     r8, rbx
0x14007846b  lea     rcx, [rbp+var_10]
0x14007846f  call    ?FormatMessageW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::FormatMessageW(ushort const *,...)
0x140078474  mov     r8, [rbp+var_10]; unsigned __int16 *
0x140078478  mov     rdx, r14; unsigned __int64
0x14007847b  mov     rcx, rsi; unsigned __int16 *
0x14007847e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140078483  mov     rcx, cs:WPP_GLOBAL_Control
0x14007848a  lea     r15, WPP_GLOBAL_Control
0x140078491  cmp     rcx, r15
0x140078494  jz      short loc_1400784BB
0x140078496  test    byte ptr [rcx+1Ch], 2
0x14007849a  jz      short loc_1400784BB
0x14007849c  cmp     byte ptr [rcx+19h], 5
0x1400784a0  jb      short loc_1400784BB
0x1400784a2  mov     rcx, [rcx+10h]
0x1400784a6  mov     edx, 0A0h
0x1400784ab  mov     r9, rsi
0x1400784ae  mov     dword ptr [rsp+40h+var_20], r14d
0x1400784b3  mov     r8, r12
0x1400784b6  call    WPP_SF_Sd
0x1400784bb  lea     rcx, [rbp+var_10]
0x1400784bf  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400784c4  mov     r10, cs:WPP_GLOBAL_Control
0x1400784cb  cmp     r10, r15
0x1400784ce  jz      short loc_140078504
0x1400784d0  test    byte ptr [r10+1Ch], 1
0x1400784d5  jz      short loc_140078504
0x1400784d7  movzx   eax, byte ptr [r10+19h]
0x1400784dc  mov     ecx, edi
0x1400784de  sar     ecx, 1Fh
0x1400784e1  and     ecx, 0FFFFFFFDh
0x1400784e4  add     ecx, 5
0x1400784e7  cmp     eax, ecx
0x1400784e9  jb      short loc_140078504
0x1400784eb  mov     rcx, [r10+10h]
0x1400784ef  mov     edx, 0A1h
0x1400784f4  mov     r9d, edi
0x1400784f7  mov     [rsp+40h+var_20], rsi
0x1400784fc  mov     r8, r12
0x1400784ff  call    WPP_SF_dS
0x140078504  lea     rcx, [rbp+arg_18]
0x140078508  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14007850d  lea     rcx, [rbp+arg_10]
0x140078511  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140078516  mov     eax, edi
0x140078518  add     rsp, 40h
0x14007851c  pop     r15
0x14007851e  pop     r14
0x140078520  pop     r12
0x140078522  pop     rdi
0x140078523  pop     rsi
0x140078524  pop     rbx
0x140078525  pop     rbp
0x140078526  retn
```
