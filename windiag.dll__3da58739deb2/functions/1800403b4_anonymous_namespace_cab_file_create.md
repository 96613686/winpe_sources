# _anonymous_namespace_::cab_file::create

- ea: `0x1800403b4`
- end: `0x180040806`
- name: `_anonymous_namespace_::cab_file::create`
- size: `1106`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003ff90`

## callees

- `0x180004510`
- `0x18000491c`
- `0x1800054e4`
- `0x180005520`
- `0x18003a52c`
- `0x18003af08`
- `0x18003f74c`
- `0x1800403b4`

## import_xrefs

- `Cabinet!__imp_FCICreate` at `0x180040617`
- `Cabinet!__imp_FCICreate` at `0x180040617`

## string_xrefs

- `0x1800406b8`: `create`
- `0x180040700`: `create`
- `0x18004073e`: `create`
- `0x180040780`: `create`
- `0x1800407c9`: `create`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::cab_file::create(__int64 a1, __int64 a2, char *a3)
{
  int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  const char *v9; // r10
  __int64 v10; // rax
  __int64 v11; // rdx
  char *szDisk; // rcx
  char v13; // r11
  __int64 v14; // r9
  char *v15; // r10
  __int64 v16; // rdx
  char *szCab; // rcx
  char v18; // r11
  __int64 v19; // rsi
  __int64 v20; // rcx
  const char *v21; // r8
  int v22; // eax
  const char *v23; // rdx
  char *szCabPath; // rcx
  char v25; // r9
  __int64 v26; // r8
  __int64 v27; // rsi
  _DWORD *v28; // rax
  HFCI v29; // rax
  _DWORD *v31; // rdx
  CCAB pccab; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+3D0h] [rbp+2D0h] BYREF

  memset_0(&pccab, 0, sizeof(pccab));
  pccab.cb = 0x7FFFFFFF;
  pccab.cbFolderThresh = 0x100000;
  v6 = 1;
  pccab.setID = 1;
  pccab.iCab = 1;
  v7 = 2147483646;
  v8 = 2147483646;
  v9 = "WinDiagData";
  v10 = 256;
  v11 = 256;
  szDisk = pccab.szDisk;
  while ( v8 )
  {
    v13 = *v9;
    if ( *v9 )
    {
      ++v9;
      *szDisk++ = v13;
      --v8;
      if ( --v11 )
        continue;
    }
    if ( !v11 )
    {
      *(szDisk - 1) = 0;
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        -2147024774,
        0,
        "[%s:%d] failed; ",
        "create",
        35);
      throw (windiag::system_exception *)pExceptionObject;
    }
    break;
  }
  *szDisk = 0;
  v14 = 2147483646;
  v15 = a3;
  v16 = 256;
  szCab = pccab.szCab;
  while ( v14 )
  {
    v18 = *v15;
    if ( *v15 )
    {
      ++v15;
      *szCab++ = v18;
      --v14;
      if ( --v16 )
        continue;
    }
    if ( !v16 )
    {
      *(szCab - 1) = 0;
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        -2147024774,
        0,
        "[%s:%d] failed; ",
        "create",
        36);
      throw (windiag::system_exception *)pExceptionObject;
    }
    break;
  }
  *szCab = 0;
  v19 = -1;
  v20 = -1;
  do
    ++v20;
  while ( *(_BYTE *)(a2 + v20) );
  if ( v20 )
  {
    v21 = "%s";
    if ( *(_BYTE *)(v20 + a2 - 1) != 92 )
      v21 = "%s\\";
    v22 = StringCchPrintfA(pccab.szCabPath, 0x100u, v21, a2);
    if ( v22 < 0 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v22,
        0,
        "[%s:%d] failed; ",
        "create",
        39);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  else
  {
    v23 = "\\";
    szCabPath = pccab.szCabPath;
    while ( v7 )
    {
      v25 = *v23;
      if ( *v23 )
      {
        ++v23;
        *szCabPath++ = v25;
        --v7;
        if ( --v10 )
          continue;
      }
      if ( !v10 )
      {
        *(szCabPath - 1) = 0;
        windiag::system_exception::system_exception(
          (windiag::system_exception *)pExceptionObject,
          -2147024774,
          0,
          "[%s:%d] failed; ",
          "create",
          41);
        throw (windiag::system_exception *)pExceptionObject;
      }
      break;
    }
    *szCabPath = 0;
  }
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v26 = -1;
  do
    ++v26;
  while ( *(_BYTE *)(a2 + v26) );
  std::string::_Construct<1,char const *>(a1, a2, v26);
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  do
    ++v19;
  while ( a3[v19] );
  std::string::_Construct<1,char const *>(a1 + 32, a3, v19);
  v27 = a1 + 64;
  v28 = operator new(0xCu);
  *(_QWORD *)v28 = 0;
  v28[2] = 0;
  *(_QWORD *)(a1 + 64) = v28;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  v29 = FCICreate(
          *(PERF *)(a1 + 64),
          (PFNFCIFILEPLACED)_scrt_stub_for_is_c_termination_complete,
          anonymous_namespace_::cab_file::fci_alloc,
          anonymous_namespace_::cab_file::fci_free,
          anonymous_namespace_::cab_file::fci_open,
          anonymous_namespace_::cab_file::fci_read,
          anonymous_namespace_::cab_file::fci_write,
          anonymous_namespace_::cab_file::fci_close,
          anonymous_namespace_::cab_file::fci_seek,
          anonymous_namespace_::cab_file::fci_delete,
          anonymous_namespace_::cab_file::fci_get_temp_file,
          &pccab,
          0);
  if ( v29 )
  {
    *(_QWORD *)(a1 + 72) = v29;
  }
  else
  {
    v31 = *(_DWORD **)v27;
    if ( *(_DWORD *)(*(_QWORD *)v27 + 8LL) )
    {
      if ( *v31 == 3 )
      {
        v6 = 8;
      }
      else if ( *v31 != 5 )
      {
        switch ( *v31 )
        {
          case 7:
            v6 = 1223;
            break;
          case 8:
            v6 = 11;
            break;
          case 9:
            v6 = 50;
            break;
          default:
            v6 = 21;
            if ( v31[1] )
              v6 = v31[1];
            break;
        }
      }
    }
    else
    {
      v6 = 0;
    }
    if ( v6 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v6,
        0,
        "[%s:%d] failed; ",
        "create",
        50);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800403b4  push    rbp
0x1800403b6  push    rbx
0x1800403b7  push    rsi
0x1800403b8  push    rdi
0x1800403b9  push    r12
0x1800403bb  push    r14
0x1800403bd  push    r15
0x1800403bf  lea     rbp, [rsp-710h]
0x1800403c7  sub     rsp, 810h
0x1800403ce  mov     rax, cs:__security_cookie
0x1800403d5  xor     rax, rsp
0x1800403d8  mov     [rbp+740h+var_40], rax
0x1800403df  mov     r15, r8
0x1800403e2  mov     r14, rdx
0x1800403e5  mov     rdi, rcx
0x1800403e8  mov     [rbp+740h+var_7C0], rcx
0x1800403ec  xor     r12d, r12d
0x1800403ef  mov     [rsp+840h+var_7D0], r12d
0x1800403f4  xor     edx, edx; Val
0x1800403f6  mov     r8d, 324h; Size
0x1800403fc  lea     rcx, [rbp+740h+var_7A0]; void *
0x180040400  call    memset_0
0x180040405  mov     [rbp+740h+var_7A0.cb], 7FFFFFFFh
0x18004040c  mov     [rbp+740h+var_7A0.cbFolderThresh], 100000h
0x180040413  lea     ebx, [r12+1]
0x180040418  mov     [rbp+740h+var_7A0.setID], bx
0x18004041c  mov     [rbp+740h+var_7A0.iCab], ebx
0x18004041f  mov     r8d, 7FFFFFFEh
0x180040425  mov     r9d, r8d
0x180040428  lea     r10, aWindiagdata; "WinDiagData"
0x18004042f  mov     eax, 100h
0x180040434  mov     edx, eax
0x180040436  lea     rcx, [rbp+740h+var_7A0.szDisk]
0x18004043a  test    r9, r9
0x18004043d  jz      short loc_180040461
0x18004043f  mov     r11b, [r10]
0x180040442  test    r11b, r11b
0x180040445  jz      short loc_180040458
0x180040447  add     r10, rbx
0x18004044a  mov     [rcx], r11b
0x18004044d  add     rcx, rbx
0x180040450  sub     r9, rbx
0x180040453  sub     rdx, rbx
0x180040456  jnz     short loc_18004043A
0x180040458  test    rdx, rdx
0x18004045b  jz      loc_180040774
0x180040461  mov     [rcx], r12b
0x180040464  mov     r9, r8
0x180040467  mov     r10, r15
0x18004046a  mov     rdx, rax
0x18004046d  lea     rcx, [rbp+740h+var_7A0.szCab]
0x180040474  test    r9, r9
0x180040477  jz      short loc_18004049B
0x180040479  mov     r11b, [r10]
0x18004047c  test    r11b, r11b
0x18004047f  jz      short loc_180040492
0x180040481  add     r10, rbx
0x180040484  mov     [rcx], r11b
0x180040487  add     rcx, rbx
0x18004048a  sub     r9, rbx
0x18004048d  sub     rdx, rbx
0x180040490  jnz     short loc_180040474
0x180040492  test    rdx, rdx
0x180040495  jz      loc_1800407BD
0x18004049b  mov     [rcx], r12b
0x18004049e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800404a2  mov     rcx, rsi
0x1800404a5  inc     rcx
0x1800404a8  cmp     [r14+rcx], r12b
0x1800404ac  jnz     short loc_1800404A5
0x1800404ae  test    rcx, rcx
0x1800404b1  jz      short loc_1800404E7
0x1800404b3  lea     rdx, aS_1; "%s\\"
0x1800404ba  lea     r8, aS_6; "%s"
0x1800404c1  cmp     byte ptr [rcx+r14-1], 5Ch ; '\'
0x1800404c7  cmovnz  r8, rdx; char *
0x1800404cb  mov     r9, r14
0x1800404ce  mov     rdx, rax; unsigned __int64
0x1800404d1  lea     rcx, [rbp+740h+var_7A0.szCabPath]; char *
0x1800404d8  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800404dd  test    eax, eax
0x1800404df  js      loc_1800406F5
0x1800404e5  jmp     short loc_18004051F
0x1800404e7  lea     rdx, asc_1800A56B4; "\\"
0x1800404ee  lea     rcx, [rbp+740h+var_7A0.szCabPath]
0x1800404f5  test    r8, r8
0x1800404f8  jz      short loc_18004051C
0x1800404fa  mov     r9b, [rdx]
0x1800404fd  test    r9b, r9b
0x180040500  jz      short loc_180040513
0x180040502  add     rdx, rbx
0x180040505  mov     [rcx], r9b
0x180040508  add     rcx, rbx
0x18004050b  sub     r8, rbx
0x18004050e  sub     rax, rbx
0x180040511  jnz     short loc_1800404F5
0x180040513  test    rax, rax
0x180040516  jz      loc_1800406AC
0x18004051c  mov     [rcx], r12b
0x18004051f  xorps   xmm0, xmm0
0x180040522  movups  xmmword ptr [rdi], xmm0
0x180040525  mov     [rdi+10h], r12
0x180040529  mov     [rdi+18h], r12
0x18004052d  mov     r8, rsi
0x180040530  inc     r8
0x180040533  cmp     [r14+r8], r12b
0x180040537  jnz     short loc_180040530
0x180040539  mov     rdx, r14
0x18004053c  mov     rcx, rdi
0x18004053f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180040544  nop
0x180040545  lea     rcx, [rdi+20h]
0x180040549  xorps   xmm0, xmm0
0x18004054c  movups  xmmword ptr [rcx], xmm0
0x18004054f  mov     [rcx+10h], r12
0x180040553  mov     [rcx+18h], r12
0x180040557  inc     rsi
0x18004055a  cmp     [r15+rsi], r12b
0x18004055e  jnz     short loc_180040557
0x180040560  mov     r8, rsi
0x180040563  mov     rdx, r15
0x180040566  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18004056b  nop
0x18004056c  lea     rsi, [rdi+40h]
0x180040570  mov     ecx, 0Ch; Size
0x180040575  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004057a  xor     ecx, ecx
0x18004057c  mov     [rax], rcx
0x18004057f  mov     [rax+8], ecx
0x180040582  mov     [rsi], rax
0x180040585  mov     [rdi+48h], r12
0x180040589  mov     [rdi+50h], r12
0x18004058d  mov     [rdi+58h], r12
0x180040591  mov     [rdi+60h], r12
0x180040595  mov     [rsp+840h+var_7D0], 3
0x18004059d  mov     [rsp+840h+pv], r12; pv
0x1800405a2  lea     rax, [rbp+740h+var_7A0]
0x1800405a6  mov     [rsp+840h+pccab], rax; pccab
0x1800405ab  lea     rax, _anonymous_namespace___cab_file__fci_get_temp_file
0x1800405b2  mov     [rsp+840h+pfnfcigtf], rax; pfnfcigtf
0x1800405b7  lea     rax, _anonymous_namespace___cab_file__fci_delete
0x1800405be  mov     [rsp+840h+pfndelete], rax; pfndelete
0x1800405c3  lea     rax, _anonymous_namespace___cab_file__fci_seek
0x1800405ca  mov     [rsp+840h+pfnseek], rax; pfnseek
0x1800405cf  lea     rax, _anonymous_namespace___cab_file__fci_close
0x1800405d6  mov     [rsp+840h+pfnclose], rax; pfnclose
0x1800405db  lea     rax, _anonymous_namespace___cab_file__fci_write
0x1800405e2  mov     [rsp+840h+pfnwrite], rax; pfnwrite
0x1800405e7  lea     rax, _anonymous_namespace___cab_file__fci_read
0x1800405ee  mov     [rsp+840h+pfnread], rax; pfnread
0x1800405f3  lea     rax, _anonymous_namespace___cab_file__fci_open
0x1800405fa  mov     [rsp+840h+pfnopen], rax; pfnopen
0x1800405ff  lea     r9, _anonymous_namespace___cab_file__fci_free; pfnf
0x180040606  lea     r8, _anonymous_namespace___cab_file__fci_alloc; pfna
0x18004060d  lea     rdx, __scrt_stub_for_is_c_termination_complete; pfnfcifp
0x180040614  mov     rcx, [rsi]; perf
0x180040617  call    cs:__imp_FCICreate
0x18004061d  test    rax, rax
0x180040620  jz      short loc_18004064A
0x180040622  mov     [rdi+48h], rax
0x180040626  mov     rax, rdi
0x180040629  mov     rcx, [rbp+740h+var_40]
0x180040630  xor     rcx, rsp; StackCookie
0x180040633  call    __security_check_cookie
0x180040638  add     rsp, 810h
0x18004063f  pop     r15
0x180040641  pop     r14
0x180040643  pop     r12
0x180040645  pop     rdi
0x180040646  pop     rsi
0x180040647  pop     rbx
0x180040648  pop     rbp
0x180040649  retn
0x18004064a  mov     rdx, [rsi]
0x18004064d  mov     r8d, 32h ; '2'
0x180040653  cmp     [rdx+8], r12d
0x180040657  jz      short loc_18004069C
0x180040659  mov     ecx, [rdx]
0x18004065b  sub     ecx, 3
0x18004065e  jz      short loc_180040695
0x180040660  sub     ecx, 2
0x180040663  jz      short loc_18004069F
0x180040665  sub     ecx, 2
0x180040668  jz      short loc_18004068E
0x18004066a  sub     ecx, 1
0x18004066d  jz      short loc_180040687
0x18004066f  cmp     ecx, 1
0x180040672  jz      short loc_180040682
0x180040674  lea     ebx, [r8-1Dh]
0x180040678  cmp     [rdx+4], r12d
0x18004067c  cmovnz  ebx, [rdx+4]
0x180040680  jmp     short loc_18004069F
0x180040682  mov     ebx, r8d
0x180040685  jmp     short loc_18004069F
0x180040687  mov     ebx, 0Bh
0x18004068c  jmp     short loc_18004069F
0x18004068e  mov     ebx, 4C7h
0x180040693  jmp     short loc_18004069F
0x180040695  mov     ebx, 8
0x18004069a  jmp     short loc_18004069F
0x18004069c  mov     ebx, r12d
0x18004069f  test    ebx, ebx
0x1800406a1  jnz     loc_180040736
0x1800406a7  jmp     loc_180040626
0x1800406ac  mov     [rcx-1], r12b
0x1800406b0  mov     dword ptr [rsp+840h+pfnread], 29h ; ')'
0x1800406b8  lea     rax, aCreate; "create"
0x1800406bf  mov     [rsp+840h+pfnopen], rax
0x1800406c4  lea     r9, aSDFailed; "[%s:%d] failed; "
0x1800406cb  xor     r8d, r8d; void *
0x1800406ce  mov     rdx, 0FFFFFFFF8007007Ah; __int64
0x1800406d5  lea     rcx, [rbp+740h+pExceptionObject]; this
0x1800406dc  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x1800406e1  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x1800406e8  lea     rcx, [rbp+740h+pExceptionObject]; pExceptionObject
0x1800406ef  call    _CxxThrowException_0
0x1800406f5  movsxd  rdx, eax; __int64
0x1800406f8  mov     dword ptr [rsp+840h+pfnread], 27h ; '''
0x180040700  lea     rax, aCreate; "create"
0x180040707  mov     [rsp+840h+pfnopen], rax
0x18004070c  lea     r9, aSDFailed; "[%s:%d] failed; "
0x180040713  xor     r8d, r8d; void *
0x180040716  lea     rcx, [rbp+740h+pExceptionObject]; this
0x18004071d  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x180040722  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x180040729  lea     rcx, [rbp+740h+pExceptionObject]; pExceptionObject
0x180040730  call    _CxxThrowException_0
0x180040736  movsxd  rdx, ebx; __int64
0x180040739  mov     dword ptr [rsp+840h+pfnread], r8d
0x18004073e  lea     rax, aCreate; "create"
0x180040745  mov     [rsp+840h+pfnopen], rax
0x18004074a  lea     r9, aSDFailed; "[%s:%d] failed; "
0x180040751  xor     r8d, r8d; void *
0x180040754  lea     rcx, [rbp+740h+pExceptionObject]; this
0x18004075b  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x180040760  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x180040767  lea     rcx, [rbp+740h+pExceptionObject]; pExceptionObject
0x18004076e  call    _CxxThrowException_0
0x180040774  mov     [rcx-1], r12b
0x180040778  mov     dword ptr [rsp+840h+pfnread], 23h ; '#'
0x180040780  lea     rax, aCreate; "create"
0x180040787  mov     [rsp+840h+pfnopen], rax
0x18004078c  lea     r9, aSDFailed; "[%s:%d] failed; "
0x180040793  xor     r8d, r8d; void *
0x180040796  mov     rdx, 0FFFFFFFF8007007Ah; __int64
0x18004079d  lea     rcx, [rbp+740h+pExceptionObject]; this
0x1800407a4  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x1800407a9  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x1800407b0  lea     rcx, [rbp+740h+pExceptionObject]; pExceptionObject
0x1800407b7  call    _CxxThrowException_0
0x1800407bd  mov     [rcx-1], r12b
0x1800407c1  mov     dword ptr [rsp+840h+pfnread], 24h ; '$'
0x1800407c9  lea     rax, aCreate; "create"
0x1800407d0  mov     [rsp+840h+pfnopen], rax
0x1800407d5  lea     r9, aSDFailed; "[%s:%d] failed; "
0x1800407dc  xor     r8d, r8d; void *
0x1800407df  mov     rdx, 0FFFFFFFF8007007Ah; __int64
0x1800407e6  lea     rcx, [rbp+740h+pExceptionObject]; this
0x1800407ed  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x1800407f2  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x1800407f9  lea     rcx, [rbp+740h+pExceptionObject]; pExceptionObject
0x180040800  call    _CxxThrowException_0
```
