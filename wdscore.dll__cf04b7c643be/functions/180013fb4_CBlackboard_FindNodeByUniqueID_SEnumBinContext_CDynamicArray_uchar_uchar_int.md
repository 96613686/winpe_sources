# CBlackboard::FindNodeByUniqueID(SEnumBinContext *,CDynamicArray<uchar,uchar *> &,int)

- ea: `0x180013fb4`
- end: `0x1800142c1`
- name: `?FindNodeByUniqueID@CBlackboard@@AEAAHPEAUSEnumBinContext@@AEAV?$CDynamicArray@EPEAE@@H@Z`
- size: `781`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012d1c`
- `0x180013068`

## callees

- `0x180002250`
- `0x1800104fc`
- `0x180012408`
- `0x180012ba4`
- `0x180012bfc`
- `0x180012e78`
- `0x1800132f8`
- `0x180013fb4`
- `0x180014c50`
- `0x180017888`
- `0x180017f10`
- `0x18001dc70`
- `0x180027510`
- `0x18002a010`

## string_xrefs

- `0x18001416c`: `(sizeof(SValue) + ((SValue *)Node.GetBuffer())->uiNameSize + ((SValue *)Node.GetBuffer())->uiSize) != uiItemSize`

## pseudocode

```c
int __fastcall CBlackboard::FindNodeByUniqueID(CTypeManager **a1, __int64 a2, __int64 a3, int a4)
{
  int result; // eax
  __int64 v9; // rcx
  __int64 v10; // rsi
  int v11; // r14d
  int v12; // eax
  void *Buffer; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdx
  int v17; // ebx
  int *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned __int64 v21; // r9
  unsigned int v22[2]; // [rsp+60h] [rbp-1C8h] BYREF
  unsigned __int64 v23; // [rsp+68h] [rbp-1C0h] BYREF
  void *v24[2]; // [rsp+70h] [rbp-1B8h] BYREF
  _BYTE v25[296]; // [rsp+80h] [rbp-1A8h] BYREF
  __int128 v26; // [rsp+1A8h] [rbp-80h]
  __int128 v27; // [rsp+1B8h] [rbp-70h]
  __int128 v28; // [rsp+1C8h] [rbp-60h]
  __int128 v29; // [rsp+1D8h] [rbp-50h]
  LPCWSTR lpModuleName; // [rsp+228h] [rbp+0h]

  v24[1] = a1;
  v22[0] = 0;
  result = CTypeManager::OpenBin(a1[15], (struct CBin *)v25, *(_QWORD *)(a2 + 8), 0, v22);
  if ( result )
  {
    v9 = *(_QWORD *)(a2 + 120);
    *(_QWORD *)(a2 + 120) = v9 + 1;
    v10 = *(_QWORD *)(*(_QWORD *)(a2 + 88) + 8 * v9);
    v11 = 0;
    if ( v22[0] == *(_DWORD *)(a2 + 16) )
      v12 = CBin::EnumItemReset((CBin *)v25, (struct SBinEnumState *)(a2 + 24));
    else
      v12 = CBin::EnumItemReset((CBin *)v25, 0, 0);
    if ( !v12 )
      goto LABEL_20;
    v24[0] = 0;
    v23 = 0;
    *(_QWORD *)v22 = 0;
    if ( !(unsigned int)CDynamicArray<unsigned char,unsigned char *>::SetSize(a3, 24) )
      goto LABEL_20;
    do
    {
      v24[0] = CBin::EnumNextItem((CBin *)v25, &v23, (unsigned __int64 *)v22);
      if ( !v24[0] )
        goto LABEL_19;
      Buffer = (void *)CDynamicArray<unsigned char,unsigned char *>::GetBuffer(a3);
      if ( !(unsigned int)CBin::EnumReadWrite((CBin *)v25, 1, Buffer, 0x18u, v24, &v23, 0) )
        goto LABEL_20;
    }
    while ( v10 != *(_QWORD *)CDynamicArray<unsigned char,unsigned char *>::GetBuffer(a3) );
    if ( !*(_DWORD *)a2 && !a4 )
    {
      CDynamicArray<unsigned char,unsigned char *>::GetBuffer(a3);
      v15 = CDynamicArray<unsigned char,unsigned char *>::GetBuffer(v14);
      if ( v16 + *(unsigned int *)(v15 + 16) + 24LL != *(_QWORD *)v22 )
      {
        if ( g_bEnableDiagnosticMode )
        {
          v17 = (**(__int64 (__fastcall ***)(struct IKernel32Interface *))g_Kernel32)(g_Kernel32);
          v18 = (int *)ConstructPartialMsgW(
                         0x6A000000u,
                         "Blackboard Corruption: %s",
                         (const char *)L"(sizeof(SValue) + ((SValue *)Node.GetBuffer())->uiNameSize + ((SValue *)Node.GetB"
                                        "uffer())->uiSize) != uiItemSize");
          WdsSetupLogMessageW(
            v18,
            589824,
            (__int64)L"D",
            0,
            0x1AADu,
            L"onecore\\base\\ntsetup\\panther\\engine\\bb.cpp",
            L"CBlackboard::FindNodeByUniqueID",
            lpModuleName,
            v17,
            0,
            0);
        }
LABEL_20:
        CBin::EnumFinish((CBin *)v25);
        CTypeManager::CloseBin(a1[15], (struct CBin *)v25, 0);
        return v11;
      }
      v19 = CDynamicArray<unsigned char,unsigned char *>::GetBuffer(a3);
      *(_QWORD *)v22 -= *(unsigned int *)(v19 + 16);
    }
    if ( (unsigned int)CDynamicArray<unsigned char,unsigned char *>::SetSize(a3, *(_QWORD *)v22) )
    {
      v20 = CDynamicArray<unsigned char,unsigned char *>::GetBuffer(a3);
      if ( (unsigned int)CBin::EnumReadWrite((CBin *)v25, 1, (void *)(v20 + 24), v21, v24, &v23, 0) )
      {
        *(_OWORD *)(a2 + 24) = v26;
        *(_OWORD *)(a2 + 40) = v27;
        *(_OWORD *)(a2 + 56) = v28;
        *(_OWORD *)(a2 + 72) = v29;
LABEL_19:
        v11 = 1;
        goto LABEL_20;
      }
    }
    goto LABEL_20;
  }
  return result;
}

```

## disassembly

```asm
0x180013fb4  mov     [rsp+arg_18], rbx
0x180013fb9  push    rsi
0x180013fba  push    rdi
0x180013fbb  push    r13
0x180013fbd  push    r14
0x180013fbf  push    r15
0x180013fc1  sub     rsp, 200h
0x180013fc8  mov     rax, cs:__security_cookie
0x180013fcf  xor     rax, rsp
0x180013fd2  mov     [rsp+228h+var_38], rax
0x180013fda  mov     r15d, r9d
0x180013fdd  mov     rdi, r8
0x180013fe0  mov     rbx, rdx
0x180013fe3  mov     r13, rcx
0x180013fe6  mov     [rsp+228h+var_1B0], rcx
0x180013feb  mov     [rsp+228h+var_1C8], 0
0x180013ff3  lea     rax, [rsp+228h+var_1C8]
0x180013ff8  mov     [rsp+228h+var_208], rax; unsigned int *
0x180013ffd  xor     r9d, r9d; int
0x180014000  mov     r8, [rdx+8]; unsigned __int64
0x180014004  lea     rdx, [rsp+228h+var_1A8]; struct CBin *
0x18001400c  mov     rcx, [rcx+78h]; this
0x180014010  call    ?OpenBin@CTypeManager@@QEAAHAEAVCBin@@_KHPEAI@Z; CTypeManager::OpenBin(CBin &,unsigned __int64,int,uint *)
0x180014015  test    eax, eax
0x180014017  jz      loc_180014298
0x18001401d  mov     rcx, [rbx+78h]
0x180014021  lea     rax, [rcx+1]
0x180014025  mov     [rbx+78h], rax
0x180014029  mov     rax, [rbx+58h]
0x18001402d  mov     rsi, [rax+rcx*8]
0x180014031  xor     r14d, r14d
0x180014034  mov     eax, [rsp+228h+var_1C8]
0x180014038  lea     rcx, [rsp+228h+var_1A8]; this
0x180014040  cmp     eax, [rbx+10h]
0x180014043  jz      short loc_180014051
0x180014045  xor     r8d, r8d; int
0x180014048  xor     edx, edx; unsigned __int64
0x18001404a  call    ?EnumItemReset@CBin@@QEAAH_KH@Z; CBin::EnumItemReset(unsigned __int64,int)
0x18001404f  jmp     short loc_18001405A
0x180014051  lea     rdx, [rbx+18h]; struct SBinEnumState *
0x180014055  call    ?EnumItemReset@CBin@@QEAAHAEAUSBinEnumState@@@Z; CBin::EnumItemReset(SBinEnumState &)
0x18001405a  test    eax, eax
0x18001405c  jz      loc_180014274
0x180014062  mov     [rsp+228h+var_1B8], 0
0x18001406b  mov     [rsp+228h+var_1C0], 0
0x180014074  mov     qword ptr [rsp+228h+var_1C8], 0
0x18001407d  mov     edx, 18h
0x180014082  mov     rcx, rdi
0x180014085  call    ?SetSize@?$CDynamicArray@EPEAE@@QEAAH_K@Z; CDynamicArray<uchar,uchar *>::SetSize(unsigned __int64)
0x18001408a  test    eax, eax
0x18001408c  jz      loc_180014274
0x180014092  lea     r8, [rsp+228h+var_1C8]; unsigned __int64 *
0x180014097  lea     rdx, [rsp+228h+var_1C0]; unsigned __int64 *
0x18001409c  lea     rcx, [rsp+228h+var_1A8]; this
0x1800140a4  call    ?EnumNextItem@CBin@@QEAAPEAXAEA_K0@Z; CBin::EnumNextItem(unsigned __int64 &,unsigned __int64 &)
0x1800140a9  mov     [rsp+228h+var_1B8], rax
0x1800140ae  test    rax, rax
0x1800140b1  jz      loc_18001426E
0x1800140b7  mov     rcx, rdi
0x1800140ba  call    ?GetBuffer@?$CDynamicArray@EPEAE@@QEAAPEAE_K@Z; CDynamicArray<uchar,uchar *>::GetBuffer(unsigned __int64)
0x1800140bf  mov     r8, rax; void *
0x1800140c2  mov     [rsp+228h+var_1F8], 0; unsigned __int64
0x1800140cb  lea     rax, [rsp+228h+var_1C0]
0x1800140d0  mov     [rsp+228h+var_200], rax; unsigned __int64 *
0x1800140d5  lea     rax, [rsp+228h+var_1B8]
0x1800140da  mov     [rsp+228h+var_208], rax; void **
0x1800140df  mov     edx, 1; int
0x1800140e4  lea     r9d, [rdx+17h]; unsigned __int64
0x1800140e8  lea     rcx, [rsp+228h+var_1A8]; this
0x1800140f0  call    ?EnumReadWrite@CBin@@QEAAHHPEAX_KAEAPEAXAEA_K1@Z; CBin::EnumReadWrite(int,void *,unsigned __int64,void * &,unsigned __int64 &,unsigned __int64)
0x1800140f5  test    eax, eax
0x1800140f7  jz      loc_180014274
0x1800140fd  mov     rcx, rdi
0x180014100  call    ?GetBuffer@?$CDynamicArray@EPEAE@@QEAAPEAE_K@Z; CDynamicArray<uchar,uchar *>::GetBuffer(unsigned __int64)
0x180014105  cmp     rsi, [rax]
0x180014108  jz      short loc_18001410C
0x18001410a  jmp     short loc_180014092
0x18001410c  cmp     dword ptr [rbx], 0
0x18001410f  jnz     loc_1800141E7
0x180014115  test    r15d, r15d
0x180014118  jnz     loc_1800141E7
0x18001411e  mov     rcx, rdi
0x180014121  call    ?GetBuffer@?$CDynamicArray@EPEAE@@QEAAPEAE_K@Z; CDynamicArray<uchar,uchar *>::GetBuffer(unsigned __int64)
0x180014126  mov     edx, [rax+14h]
0x180014129  call    ?GetBuffer@?$CDynamicArray@EPEAE@@QEAAPEAE_K@Z; CDynamicArray<uchar,uchar *>::GetBuffer(unsigned __int64)
0x18001412e  mov     eax, [rax+10h]
0x180014131  add     rax, 18h
0x180014135  add     rax, rdx
0x180014138  cmp     rax, qword ptr [rsp+228h+var_1C8]
0x18001413d  jz      loc_1800141D7
0x180014143  cmp     cs:?g_bEnableDiagnosticMode@@3HA, r15d; int g_bEnableDiagnosticMode
0x18001414a  jz      loc_180014274
0x180014150  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180014157  mov     rax, [rcx]
0x18001415a  mov     rax, [rax]
0x18001415d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014162  mov     ebx, eax
0x180014164  mov     rdi, [rsp+228h]
0x18001416c  lea     r8, aSizeofSvalueSv; "(sizeof(SValue) + ((SValue *)Node.GetBu"...
0x180014173  lea     rdx, aBlackboardCorr; "Blackboard Corruption: %s"
0x18001417a  mov     ecx, 6A000000h; unsigned int
0x18001417f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180014184  mov     [rsp+228h+var_1D8], r15d; int
0x180014189  mov     [rsp+228h+var_1E0], 0; __int64
0x180014192  mov     [rsp+228h+var_1E8], ebx; int
0x180014196  mov     [rsp+228h+lpModuleName], rdi; lpModuleName
0x18001419b  lea     rcx, aCblackboardFin; "CBlackboard::FindNodeByUniqueID"
0x1800141a2  mov     [rsp+228h+var_1F8], rcx; __int64
0x1800141a7  lea     rcx, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\panther\\engine"...
0x1800141ae  mov     [rsp+228h+var_200], rcx; unsigned __int16 *
0x1800141b3  mov     dword ptr [rsp+228h+var_208], 1AADh; int
0x1800141bb  xor     r9d, r9d; int
0x1800141be  lea     r8, aD_1; "D"
0x1800141c5  mov     edx, 90000h; int
0x1800141ca  mov     rcx, rax; int
0x1800141cd  call    WdsSetupLogMessageW
0x1800141d2  jmp     loc_180014274
0x1800141d7  mov     rcx, rdi
0x1800141da  call    ?GetBuffer@?$CDynamicArray@EPEAE@@QEAAPEAE_K@Z; CDynamicArray<uchar,uchar *>::GetBuffer(unsigned __int64)
0x1800141df  mov     edx, [rax+10h]
0x1800141e2  sub     qword ptr [rsp+228h+var_1C8], rdx
0x1800141e7  mov     rsi, qword ptr [rsp+228h+var_1C8]
0x1800141ec  mov     rdx, rsi
0x1800141ef  mov     rcx, rdi
0x1800141f2  call    ?SetSize@?$CDynamicArray@EPEAE@@QEAAH_K@Z; CDynamicArray<uchar,uchar *>::SetSize(unsigned __int64)
0x1800141f7  test    eax, eax
0x1800141f9  jz      short loc_180014274
0x1800141fb  lea     r9, [rsi-18h]
0x1800141ff  mov     rcx, rdi
0x180014202  call    ?GetBuffer@?$CDynamicArray@EPEAE@@QEAAPEAE_K@Z; CDynamicArray<uchar,uchar *>::GetBuffer(unsigned __int64)
0x180014207  lea     r8, [rax+18h]; void *
0x18001420b  mov     [rsp+228h+var_1F8], 0; unsigned __int64
0x180014214  lea     rcx, [rsp+228h+var_1C0]
0x180014219  mov     [rsp+228h+var_200], rcx; unsigned __int64 *
0x18001421e  lea     rcx, [rsp+228h+var_1B8]
0x180014223  mov     [rsp+228h+var_208], rcx; void **
0x180014228  mov     edx, 1; int
0x18001422d  lea     rcx, [rsp+228h+var_1A8]; this
0x180014235  call    ?EnumReadWrite@CBin@@QEAAHHPEAX_KAEAPEAXAEA_K1@Z; CBin::EnumReadWrite(int,void *,unsigned __int64,void * &,unsigned __int64 &,unsigned __int64)
0x18001423a  test    eax, eax
0x18001423c  jz      short loc_180014274
0x18001423e  movups  xmm0, [rsp+228h+var_80]
0x180014246  movups  xmmword ptr [rbx+18h], xmm0
0x18001424a  movups  xmm1, [rsp+228h+var_70]
0x180014252  movups  xmmword ptr [rbx+28h], xmm1
0x180014256  movups  xmm0, [rsp+228h+var_60]
0x18001425e  movups  xmmword ptr [rbx+38h], xmm0
0x180014262  movups  xmm1, [rsp+228h+var_50]
0x18001426a  movups  xmmword ptr [rbx+48h], xmm1
0x18001426e  mov     r14d, 1
0x180014274  lea     rcx, [rsp+228h+var_1A8]; this
0x18001427c  call    ?EnumFinish@CBin@@QEAAHXZ; CBin::EnumFinish(void)
0x180014281  xor     r8d, r8d; unsigned __int64 *
0x180014284  lea     rdx, [rsp+228h+var_1A8]; struct CBin *
0x18001428c  mov     rcx, [r13+78h]; this
0x180014290  call    ?CloseBin@CTypeManager@@QEAAHAEAVCBin@@PEA_K@Z; CTypeManager::CloseBin(CBin &,unsigned __int64 *)
0x180014295  mov     eax, r14d
0x180014298  mov     rcx, [rsp+228h+var_38]
0x1800142a0  xor     rcx, rsp; StackCookie
0x1800142a3  call    __security_check_cookie
0x1800142a8  mov     rbx, [rsp+228h+arg_18]
0x1800142b0  add     rsp, 200h
0x1800142b7  pop     r15
0x1800142b9  pop     r14
0x1800142bb  pop     r13
0x1800142bd  pop     rdi
0x1800142be  pop     rsi
0x1800142bf  retn
0x180028b1d  push    rbp
0x180028b1f  sub     rsp, 60h
0x180028b23  mov     rbp, rdx
0x180028b26  lea     rcx, [rbp+80h]; this
0x180028b2d  call    ?EnumFinish@CBin@@QEAAHXZ; CBin::EnumFinish(void)
0x180028b32  xor     r8d, r8d; unsigned __int64 *
0x180028b35  lea     rdx, [rbp+80h]; struct CBin *
0x180028b3c  mov     rcx, [rbp+78h]
0x180028b40  mov     rcx, [rcx+78h]; this
0x180028b44  call    ?CloseBin@CTypeManager@@QEAAHAEAVCBin@@PEA_K@Z; CTypeManager::CloseBin(CBin &,unsigned __int64 *)
0x180028b49  nop
0x180028b4a  add     rsp, 60h
0x180028b4e  pop     rbp
0x180028b4f  retn
```
