# EvtIntGetClassicLogDisplayName

- ea: `0x180026a30`
- end: `0x180026e86`
- name: `EvtIntGetClassicLogDisplayName`
- size: `1110`
- prototype: `__int64 __fastcall(__int64, __int64, LCID, int, unsigned int, void *, _DWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180007940`
- `0x180007aa0`
- `0x18000a0dc`
- `0x180023548`
- `0x180026a30`
- `0x180038fa4`
- `0x180038fbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026e67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026e67`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180026b9f`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180026b9f`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180026b86`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180026b86`
- `RPCRT4!NdrClientCall3` at `0x180026bec`
- `RPCRT4!NdrClientCall3` at `0x180026bec`

## pseudocode

```c
__int64 __fastcall EvtIntGetClassicLogDisplayName(
        __int64 a1,
        __int64 a2,
        LCID a3,
        int a4,
        unsigned int a5,
        void *a6,
        _DWORD *a7)
{
  LCID ThreadUILanguage; // ebx
  unsigned int v9; // edi
  unsigned int Pointer; // ebx
  void *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // r8
  DWORD v14; // ebx
  void *Src; // [rsp+40h] [rbp-148h] BYREF
  __int64 v17; // [rsp+48h] [rbp-140h] BYREF
  _QWORD v18[3]; // [rsp+50h] [rbp-138h] BYREF
  unsigned int v19; // [rsp+68h] [rbp-120h]
  int v20; // [rsp+6Ch] [rbp-11Ch]
  int v21; // [rsp+70h] [rbp-118h]
  char v22; // [rsp+74h] [rbp-114h]
  __int128 pExceptionObject; // [rsp+78h] [rbp-110h] BYREF
  __int64 v24; // [rsp+88h] [rbp-100h]
  int v25; // [rsp+90h] [rbp-F8h]
  int v26; // [rsp+94h] [rbp-F4h]
  int v27; // [rsp+98h] [rbp-F0h]
  __int128 v28; // [rsp+A0h] [rbp-E8h] BYREF
  __int64 v29; // [rsp+B0h] [rbp-D8h]
  int v30; // [rsp+B8h] [rbp-D0h]
  int v31; // [rsp+BCh] [rbp-CCh]
  int v32; // [rsp+C0h] [rbp-C8h]
  __int128 v33; // [rsp+C8h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+D8h] [rbp-B0h]
  int v35; // [rsp+E0h] [rbp-A8h]
  int v36; // [rsp+E4h] [rbp-A4h]
  int v37; // [rsp+E8h] [rbp-A0h]
  __int128 v38; // [rsp+F0h] [rbp-98h] BYREF
  __int64 v39; // [rsp+100h] [rbp-88h]
  int v40; // [rsp+108h] [rbp-80h]
  int v41; // [rsp+10Ch] [rbp-7Ch]
  int v42; // [rsp+110h] [rbp-78h]
  __int128 v43; // [rsp+118h] [rbp-70h] BYREF
  __int64 v44; // [rsp+128h] [rbp-60h]
  int v45; // [rsp+130h] [rbp-58h]
  int v46; // [rsp+134h] [rbp-54h]
  int v47; // [rsp+138h] [rbp-50h]
  EvtException *v48; // [rsp+140h] [rbp-48h] BYREF

  try
  {
    ThreadUILanguage = a3;
    v9 = 0;
    if ( a4 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
      }
      pExceptionObject = 0;
      v24 = 0;
      v25 = 87;
      v26 = -1;
      v27 = 458;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !a2 || !a7 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
      }
      v43 = 0;
      v44 = 0;
      v45 = 87;
      v46 = -1;
      v47 = 463;
      throw (EvtException *)&v43;
    }
    if ( !a6 && a5 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
      }
      v28 = 0;
      v29 = 0;
      v30 = 87;
      v31 = -1;
      v32 = 468;
      throw (EvtException *)&v28;
    }
    if ( !a3 )
    {
      ThreadUILanguage = GetThreadUILanguage();
      if ( ThreadUILanguage == 5120 || ThreadUILanguage == 4096 )
        ThreadUILanguage = GetThreadLocale();
    }
    GetSession(&v17);
    Src = 0;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x1Cu,
                              0,
                              *(_QWORD *)(v17 + 72),
                              a2,
                              ThreadUILanguage,
                              256,
                              &Src).Pointer;
    if ( Pointer )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, Pointer);
      }
      v18[0] = &word_18004024A;
      v18[1] = 0;
      v18[2] = 0;
      v19 = Pointer;
      v20 = -1;
      v21 = -1;
      v22 = 0;
      throw (EvtException *)v18;
    }
    v11 = Src;
    if ( !Src )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 13);
      }
      v33 = 0;
      v34 = 0;
      v35 = 13;
      v36 = -1;
      v37 = 504;
      throw (EvtException *)&v33;
    }
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)Src + v12) );
    v13 = v12 + 1;
    if ( (unsigned __int64)(v12 + 1) > 0x200000 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 13);
      }
      v38 = 0;
      v39 = 0;
      v40 = 13;
      v41 = -1;
      v42 = 510;
      throw (EvtException *)&v38;
    }
    *a7 = v13;
    if ( (unsigned int)v13 > a5 )
    {
      v14 = 122;
    }
    else
    {
      memcpy_0(a6, v11, 2 * v13);
      v14 = 0;
    }
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(&Src);
    wmi::AutoRef<Object>::Release(&v17);
  }
  catch ( EvtException *v48 )
  {
    v9 = 0;
    v14 = *((_DWORD *)v48 + 6);
  }
  ThreadUILanguage = a3;
  v9 = 0;
  if ( a4 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
    }
    pExceptionObject = 0;
    v24 = 0;
    v25 = 87;
    v26 = -1;
    v27 = 458;
    throw (EvtException *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x180026a30  push    rbx
0x180026a32  push    rsi
0x180026a33  push    rdi
0x180026a34  push    r12
0x180026a36  push    r14
0x180026a38  push    r15
0x180026a3a  sub     rsp, 158h
0x180026a41  mov     ebx, r8d
0x180026a44  mov     r15, rdx
0x180026a47  mov     r12, rcx
0x180026a4a  xor     edi, edi
0x180026a4c  test    r9d, r9d
0x180026a4f  jz      short loc_180026ACA
0x180026a51  lea     rax, WPP_GLOBAL_Control
0x180026a58  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a5f  cmp     rcx, rax
0x180026a62  jz      short loc_180026A87
0x180026a64  test    byte ptr [rcx+1Ch], 1
0x180026a68  jz      short loc_180026A87
0x180026a6a  cmp     byte ptr [rcx+19h], 2
0x180026a6e  jb      short loc_180026A87
0x180026a70  lea     edx, [rdi+13h]
0x180026a73  lea     r9d, [rdi+57h]
0x180026a77  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x180026a7e  mov     rcx, [rcx+10h]
0x180026a82  call    WPP_SF_D
0x180026a87  xorps   xmm0, xmm0
0x180026a8a  movdqu  [rsp+188h+pExceptionObject], xmm0
0x180026a90  mov     [rsp+188h+var_100], rdi
0x180026a98  mov     [rsp+188h+var_F8], 57h ; 'W'
0x180026aa3  mov     [rsp+188h+var_F4], 0FFFFFFFFh
0x180026aae  mov     [rsp+188h+var_F0], 1CAh
0x180026ab9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026ac0  lea     rcx, [rsp+188h+pExceptionObject]; pExceptionObject
0x180026ac5  call    _CxxThrowException_0
0x180026aca  test    r15, r15
0x180026acd  jz      loc_180026DDA
0x180026ad3  mov     r14, [rsp+188h+arg_30]
0x180026adb  test    r14, r14
0x180026ade  jz      loc_180026DDA
0x180026ae4  mov     esi, [rsp+188h+arg_20]
0x180026aeb  cmp     [rsp+188h+arg_28], rdi
0x180026af3  jnz     loc_180026B82
0x180026af9  test    esi, esi
0x180026afb  jz      loc_180026B82
0x180026b01  lea     rax, WPP_GLOBAL_Control
0x180026b08  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b0f  cmp     rcx, rax
0x180026b12  jz      short loc_180026B39
0x180026b14  test    byte ptr [rcx+1Ch], 1
0x180026b18  jz      short loc_180026B39
0x180026b1a  cmp     byte ptr [rcx+19h], 2
0x180026b1e  jb      short loc_180026B39
0x180026b20  mov     edx, 15h
0x180026b25  lea     r9d, [rdx+42h]
0x180026b29  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x180026b30  mov     rcx, [rcx+10h]
0x180026b34  call    WPP_SF_D
0x180026b39  xorps   xmm0, xmm0
0x180026b3c  movdqu  [rsp+188h+var_E8], xmm0
0x180026b45  mov     [rsp+188h+var_D8], rdi
0x180026b4d  mov     [rsp+188h+var_D0], 57h ; 'W'
0x180026b58  mov     [rsp+188h+var_CC], 0FFFFFFFFh
0x180026b63  mov     [rsp+188h+var_C8], 1D4h
0x180026b6e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026b75  lea     rcx, [rsp+188h+var_E8]; pExceptionObject
0x180026b7d  call    _CxxThrowException_0
0x180026b82  test    ebx, ebx
0x180026b84  jnz     short loc_180026BA7
0x180026b86  call    cs:__imp_GetThreadUILanguage
0x180026b8c  movzx   ebx, ax
0x180026b8f  cmp     ebx, 1400h
0x180026b95  jz      short loc_180026B9F
0x180026b97  cmp     ebx, 1000h
0x180026b9d  jnz     short loc_180026BA7
0x180026b9f  call    cs:__imp_GetThreadLocale
0x180026ba5  mov     ebx, eax
0x180026ba7  mov     rdx, r12
0x180026baa  lea     rcx, [rsp+188h+var_140]; void *
0x180026baf  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x180026bb4  nop
0x180026bb5  mov     [rsp+188h+Src], rdi
0x180026bba  lea     rax, [rsp+188h+Src]
0x180026bbf  mov     [rsp+188h+var_150], rax
0x180026bc4  mov     [rsp+188h+var_158], 100h
0x180026bcc  mov     [rsp+188h+var_160], ebx
0x180026bd0  mov     [rsp+188h+var_168], r15
0x180026bd5  mov     r9, [rsp+188h+var_140]
0x180026bda  mov     r9, [r9+48h]
0x180026bde  xor     r8d, r8d; pReturnValue
0x180026be1  lea     edx, [r8+1Ch]; nProcNum
0x180026be5  lea     rcx, pProxyInfo; pProxyInfo
0x180026bec  call    cs:__imp_NdrClientCall3
0x180026bf2  mov     rbx, rax
0x180026bf5  test    ebx, ebx
0x180026bf7  jz      short loc_180026C70
0x180026bf9  lea     rax, WPP_GLOBAL_Control
0x180026c00  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c07  cmp     rcx, rax
0x180026c0a  jz      short loc_180026C30
0x180026c0c  test    byte ptr [rcx+1Ch], 1
0x180026c10  jz      short loc_180026C30
0x180026c12  cmp     byte ptr [rcx+19h], 2
0x180026c16  jb      short loc_180026C30
0x180026c18  mov     edx, 16h
0x180026c1d  mov     r9d, ebx
0x180026c20  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x180026c27  mov     rcx, [rcx+10h]
0x180026c2b  call    WPP_SF_D
0x180026c30  lea     rax, word_18004024A
0x180026c37  mov     [rsp+188h+var_138], rax
0x180026c3c  mov     [rsp+188h+var_130], rdi
0x180026c41  mov     [rsp+188h+var_128], rdi
0x180026c46  mov     [rsp+188h+var_120], ebx
0x180026c4a  mov     [rsp+188h+var_11C], 0FFFFFFFFh
0x180026c52  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026c56  mov     [rsp+188h+var_118], eax
0x180026c5a  mov     [rsp+188h+var_114], dil
0x180026c5f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026c66  lea     rcx, [rsp+188h+var_138]; pExceptionObject
0x180026c6b  call    _CxxThrowException_0
0x180026c70  mov     rdx, [rsp+188h+Src]; Src
0x180026c75  test    rdx, rdx
0x180026c78  jnz     loc_180026CFF
0x180026c7e  lea     rax, WPP_GLOBAL_Control
0x180026c85  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c8c  cmp     rcx, rax
0x180026c8f  jz      short loc_180026CB6
0x180026c91  test    byte ptr [rcx+1Ch], 1
0x180026c95  jz      short loc_180026CB6
0x180026c97  cmp     byte ptr [rcx+19h], 2
0x180026c9b  jb      short loc_180026CB6
0x180026c9d  mov     edx, 17h
0x180026ca2  lea     r9d, [rdx-0Ah]
0x180026ca6  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x180026cad  mov     rcx, [rcx+10h]
0x180026cb1  call    WPP_SF_D
0x180026cb6  xorps   xmm0, xmm0
0x180026cb9  movdqu  [rsp+188h+var_C0], xmm0
0x180026cc2  mov     [rsp+188h+var_B0], rdi
0x180026cca  mov     [rsp+188h+var_A8], 0Dh
0x180026cd5  mov     [rsp+188h+var_A4], 0FFFFFFFFh
0x180026ce0  mov     [rsp+188h+var_A0], 1F8h
0x180026ceb  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026cf2  lea     rcx, [rsp+188h+var_C0]; pExceptionObject
0x180026cfa  call    _CxxThrowException_0
0x180026cff  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026d03  inc     rax
0x180026d06  cmp     [rdx+rax*2], di
0x180026d0a  jnz     short loc_180026D03
0x180026d0c  lea     r8, [rax+1]
0x180026d10  cmp     r8, 200000h
0x180026d17  jbe     loc_180026D9E
0x180026d1d  lea     rax, WPP_GLOBAL_Control
0x180026d24  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d2b  cmp     rcx, rax
0x180026d2e  jz      short loc_180026D55
0x180026d30  test    byte ptr [rcx+1Ch], 1
0x180026d34  jz      short loc_180026D55
0x180026d36  cmp     byte ptr [rcx+19h], 2
0x180026d3a  jb      short loc_180026D55
0x180026d3c  mov     edx, 18h
0x180026d41  lea     r9d, [rdx-0Bh]
0x180026d45  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x180026d4c  mov     rcx, [rcx+10h]
0x180026d50  call    WPP_SF_D
0x180026d55  xorps   xmm0, xmm0
0x180026d58  movdqu  [rsp+188h+var_98], xmm0
0x180026d61  mov     [rsp+188h+var_88], rdi
0x180026d69  mov     [rsp+188h+var_80], 0Dh
0x180026d74  mov     [rsp+188h+var_7C], 0FFFFFFFFh
0x180026d7f  mov     [rsp+188h+var_78], 1FEh
0x180026d8a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026d91  lea     rcx, [rsp+188h+var_98]; pExceptionObject
0x180026d99  call    _CxxThrowException_0
0x180026d9e  mov     [r14], r8d
0x180026da1  cmp     r8d, esi
0x180026da4  ja      short loc_180026DBA
0x180026da6  add     r8, r8; Size
0x180026da9  mov     rcx, [rsp+188h+arg_28]; void *
0x180026db1  call    memcpy_0
0x180026db6  mov     ebx, edi
0x180026db8  jmp     short loc_180026DBF
0x180026dba  mov     ebx, 7Ah ; 'z'
0x180026dbf  lea     rcx, [rsp+188h+Src]
0x180026dc4  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@K@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>(void)
0x180026dc9  nop
0x180026dca  lea     rcx, [rsp+188h+var_140]; void *
0x180026dcf  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x180026dd4  nop
0x180026dd5  jmp     loc_180026E65
0x180026dda  lea     rax, WPP_GLOBAL_Control
0x180026de1  mov     rcx, cs:WPP_GLOBAL_Control
0x180026de8  cmp     rcx, rax
0x180026deb  jz      short loc_180026E12
0x180026ded  test    byte ptr [rcx+1Ch], 1
0x180026df1  jz      short loc_180026E12
0x180026df3  cmp     byte ptr [rcx+19h], 2
0x180026df7  jb      short loc_180026E12
0x180026df9  mov     edx, 14h
0x180026dfe  lea     r9d, [rdx+43h]
0x180026e02  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x180026e09  mov     rcx, [rcx+10h]
0x180026e0d  call    WPP_SF_D
0x180026e12  xorps   xmm0, xmm0
0x180026e15  movdqu  [rsp+188h+var_70], xmm0
0x180026e1e  mov     [rsp+188h+var_60], rdi
0x180026e26  mov     [rsp+188h+var_58], 57h ; 'W'
0x180026e31  mov     [rsp+188h+var_54], 0FFFFFFFFh
0x180026e3c  mov     [rsp+188h+var_50], 1CFh
0x180026e47  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026e4e  lea     rcx, [rsp+188h+var_70]; pExceptionObject
0x180026e56  call    _CxxThrowException_0
0x180026e5c  xor     edi, edi
0x180026e5e  mov     ebx, [rsp+188h+arg_18]
0x180026e65  mov     ecx, ebx; dwErrCode
0x180026e67  call    cs:__imp_SetLastError
0x180026e6d  test    ebx, ebx
0x180026e6f  setz    dil
0x180026e73  mov     eax, edi
0x180026e75  add     rsp, 158h
0x180026e7c  pop     r15
0x180026e7e  pop     r14
0x180026e80  pop     r12
0x180026e82  pop     rdi
0x180026e83  pop     rsi
0x180026e84  pop     rbx
0x180026e85  retn
```
