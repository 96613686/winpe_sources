# FileManager::GetFile(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,unsigned __int64,FileModeFlags,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)

- ea: `0x180087370`
- end: `0x1800876a9`
- name: `?GetFile@FileManager@@QEAA?AV?$AutoRef@VFile@@@wmi@@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@_KW4FileModeFlags@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z`
- size: `825`
- prototype: `__int64 *__fastcall(RTL_SRWLOCK *, __int64 *, __int64, __int64, char, __int128 *)`
- caller_count: `5`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180048ae0`
- `0x180061724`
- `0x1800708e0`
- `0x1800872c0`
- `0x1800972c0`

## callees

- `0x180014bd0`
- `0x180016250`
- `0x180017b60`
- `0x180017e28`
- `0x18001c320`
- `0x18002ede4`
- `0x180047194`
- `0x180069f68`
- `0x180087370`
- `0x180092008`
- `0x1800b223c`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800874a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800874a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180087513`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008767a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180087513`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008767a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800874e9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800874e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall FileManager::GetFile(RTL_SRWLOCK *a1, __int64 *a2, __int64 a3, __int64 a4, char a5, __int128 *a6)
{
  __int64 *Ptr; // rbx
  __int64 *v10; // rsi
  const WCHAR *v11; // rcx
  const WCHAR *v12; // r8
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rax
  char v16; // si
  File *v17; // rax
  __int64 v18; // rbx
  _QWORD *v19; // rax
  _BYTE *v20; // rsi
  __int64 v21; // rax
  __int128 pExceptionObject; // [rsp+40h] [rbp-59h] BYREF
  __int64 v24; // [rsp+50h] [rbp-49h]
  int v25; // [rsp+58h] [rbp-41h]
  int v26; // [rsp+5Ch] [rbp-3Dh]
  int v27; // [rsp+60h] [rbp-39h]
  __int64 v28; // [rsp+68h] [rbp-31h] BYREF
  LPCWCH lpString1[2]; // [rsp+70h] [rbp-29h] BYREF
  char v30; // [rsp+80h] [rbp-19h] BYREF
  __int128 v31; // [rsp+A0h] [rbp+7h] BYREF
  __int128 v32; // [rsp+B0h] [rbp+17h] BYREF

  if ( !*(_QWORD *)(a3 + 8) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_d33d9432658b3ff029c702686d00d94e_Traceguids, 87);
    }
    pExceptionObject = 0;
    v24 = 0;
    v25 = 87;
    v26 = -1;
    v27 = 66;
    throw (EvtException *)&pExceptionObject;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpString1);
  if ( (unsigned int)ExpandEnvStringNoThrow(*(LPCWSTR *)a3) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d33d9432658b3ff029c702686d00d94e_Traceguids, 87);
    }
    pExceptionObject = 0;
    v24 = 0;
    v25 = 87;
    v26 = -1;
    v27 = 74;
    throw (EvtException *)&pExceptionObject;
  }
  AcquireSRWLockExclusive(a1 + 3);
  Ptr = (__int64 *)a1->Ptr;
  v10 = (__int64 *)a1[1].Ptr;
  v11 = lpString1[0];
  while ( Ptr != v10 )
  {
    v12 = *(const WCHAR **)(*Ptr + 680);
    v13 = (__int64)(*(_QWORD *)(*Ptr + 688) - (_QWORD)v12) >> 1;
    v14 = lpString1[1] - v11;
    if ( v14 == v13 )
    {
      if ( CompareStringOrdinal(v11, v14, v12, v13, 1) == 2 )
      {
        v15 = *Ptr;
        *a2 = *Ptr;
        if ( v15 )
          _InterlockedIncrement((volatile signed __int32 *)(v15 + 808));
        ReleaseSRWLockExclusive(a1 + 3);
        if ( (char *)lpString1[0] != &v30 )
          operator delete((void *)lpString1[0]);
        return a2;
      }
      v11 = lpString1[0];
    }
    ++Ptr;
  }
  v31 = *a6;
  v16 = IsSecurityChannel(&v31);
  v17 = (File *)operator new(0x348u);
  *(_QWORD *)&v31 = v17;
  if ( v17 )
  {
    v32 = *a6;
    v18 = File::File(v17, (__int64)&v32, (__int64)lpString1, v16);
  }
  else
  {
    v18 = 0;
  }
  v28 = v18;
  if ( v18 )
    _InterlockedIncrement((volatile signed __int32 *)(v18 + 808));
  v19 = a1[1].Ptr;
  if ( v19 == a1[2].Ptr )
  {
    v20 = a1->Ptr;
    if ( !(unsigned __int8)utl::vector<File *,utl::allocator<File *>>::_Grow(a1) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_d33d9432658b3ff029c702686d00d94e_Traceguids, 14);
      }
      pExceptionObject = 0;
      v24 = 0;
      v25 = 14;
      v26 = -1;
      v27 = 105;
      throw (EvtException *)&pExceptionObject;
    }
    if ( (PVOID)((char *)&v28 - v20) >= (PVOID)((char *)a1[1].Ptr - (char *)a1->Ptr) )
      v21 = v18;
    else
      v21 = *(_QWORD *)((char *)a1->Ptr + (char *)&v28 - v20);
    *(_QWORD *)a1[1].Ptr = v21;
  }
  else
  {
    *v19 = v18;
  }
  a1[1].Ptr = (char *)a1[1].Ptr + 8;
  *a2 = v18;
  v28 = 0;
  wmi::AutoRef<File>::Release(&v28);
  ReleaseSRWLockExclusive(a1 + 3);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpString1);
  return a2;
}

```

## disassembly

```asm
0x180087370  mov     [rsp-8+arg_0], rbx
0x180087375  mov     [rsp-8+arg_8], rsi
0x18008737a  push    rbp
0x18008737b  push    rdi
0x18008737c  push    r12
0x18008737e  push    r14
0x180087380  push    r15
0x180087382  lea     rbp, [rsp-27h]
0x180087387  sub     rsp, 0C0h
0x18008738e  mov     r12, r9
0x180087391  mov     rbx, r8
0x180087394  mov     r15, rdx
0x180087397  mov     r14, rcx
0x18008739a  cmp     qword ptr [r8+8], 0
0x18008739f  jnz     short loc_180087410
0x1800873a1  lea     rax, WPP_GLOBAL_Control
0x1800873a8  mov     ebx, 57h ; 'W'
0x1800873ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800873b4  cmp     rcx, rax
0x1800873b7  jz      short loc_1800873DE
0x1800873b9  test    dword ptr [rcx+1Ch], 8000h
0x1800873c0  jz      short loc_1800873DE
0x1800873c2  cmp     byte ptr [rcx+19h], 2
0x1800873c6  jb      short loc_1800873DE
0x1800873c8  lea     edx, [rbx-4Ch]
0x1800873cb  mov     r9d, ebx
0x1800873ce  lea     r8, WPP_d33d9432658b3ff029c702686d00d94e_Traceguids
0x1800873d5  mov     rcx, [rcx+10h]
0x1800873d9  call    WPP_SF_d
0x1800873de  xorps   xmm0, xmm0
0x1800873e1  movdqu  [rbp+47h+pExceptionObject], xmm0
0x1800873e6  mov     [rbp+47h+var_90], 0
0x1800873ee  mov     [rbp+47h+var_88], ebx
0x1800873f1  mov     [rbp+47h+var_84], 0FFFFFFFFh
0x1800873f8  mov     [rbp+47h+var_80], 42h ; 'B'
0x1800873ff  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180087406  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x18008740a  call    _CxxThrowException_0
0x180087410  lea     rcx, [rbp+47h+lpString1]; void *
0x180087414  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180087419  nop
0x18008741a  lea     rdx, [rbp+47h+lpString1]
0x18008741e  mov     rcx, [rbx]; lpSrc
0x180087421  call    ?ExpandEnvStringNoThrow@@YAKPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; ExpandEnvStringNoThrow(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180087426  test    eax, eax
0x180087428  jz      short loc_180087499
0x18008742a  lea     rax, WPP_GLOBAL_Control
0x180087431  mov     ebx, 57h ; 'W'
0x180087436  mov     rcx, cs:WPP_GLOBAL_Control
0x18008743d  cmp     rcx, rax
0x180087440  jz      short loc_180087467
0x180087442  test    dword ptr [rcx+1Ch], 8000h
0x180087449  jz      short loc_180087467
0x18008744b  cmp     byte ptr [rcx+19h], 2
0x18008744f  jb      short loc_180087467
0x180087451  lea     edx, [rbx-4Bh]
0x180087454  mov     r9d, ebx
0x180087457  lea     r8, WPP_d33d9432658b3ff029c702686d00d94e_Traceguids
0x18008745e  mov     rcx, [rcx+10h]
0x180087462  call    WPP_SF_d
0x180087467  xorps   xmm0, xmm0
0x18008746a  movdqu  [rbp+47h+pExceptionObject], xmm0
0x18008746f  mov     [rbp+47h+var_90], 0
0x180087477  mov     [rbp+47h+var_88], ebx
0x18008747a  mov     [rbp+47h+var_84], 0FFFFFFFFh
0x180087481  mov     [rbp+47h+var_80], 4Ah ; 'J'
0x180087488  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18008748f  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x180087493  call    _CxxThrowException_0
0x180087499  lea     rdi, [r14+18h]
0x18008749d  mov     [rbp+47h+arg_10], rdi
0x1800874a1  mov     rcx, rdi; SRWLock
0x1800874a4  call    cs:__imp_AcquireSRWLockExclusive
0x1800874aa  nop
0x1800874ab  mov     rbx, [r14]
0x1800874ae  mov     rsi, [r14+8]
0x1800874b2  mov     rcx, [rbp+47h+lpString1]; lpString1
0x1800874b6  cmp     rbx, rsi
0x1800874b9  jz      short loc_180087535
0x1800874bb  mov     rax, [rbx]
0x1800874be  mov     r8, [rax+2A8h]; lpString2
0x1800874c5  mov     r9, [rax+2B0h]
0x1800874cc  sub     r9, r8
0x1800874cf  sar     r9, 1; cchCount2
0x1800874d2  mov     rdx, [rbp+47h+var_68]
0x1800874d6  sub     rdx, rcx
0x1800874d9  sar     rdx, 1; cchCount1
0x1800874dc  cmp     rdx, r9
0x1800874df  jnz     short loc_1800874F8
0x1800874e1  mov     [rsp+0E0h+bIgnoreCase], 1; bIgnoreCase
0x1800874e9  call    cs:__imp_CompareStringOrdinal
0x1800874ef  cmp     eax, 2
0x1800874f2  jz      short loc_1800874FE
0x1800874f4  mov     rcx, [rbp+47h+lpString1]
0x1800874f8  add     rbx, 8
0x1800874fc  jmp     short loc_1800874B6
0x1800874fe  mov     rax, [rbx]
0x180087501  mov     [r15], rax
0x180087504  test    rax, rax
0x180087507  jz      short loc_180087510
0x180087509  lock inc dword ptr [rax+328h]
0x180087510  mov     rcx, rdi; SRWLock
0x180087513  call    cs:__imp_ReleaseSRWLockExclusive
0x180087519  nop
0x18008751a  lea     rax, [rbp+47h+var_60]
0x18008751e  mov     rcx, [rbp+47h+lpString1]; void *
0x180087522  cmp     rcx, rax
0x180087525  jz      loc_18008768A
0x18008752b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180087530  jmp     loc_18008768A
0x180087535  mov     rbx, [rbp+47h+arg_28]
0x180087539  movaps  xmm0, xmmword ptr [rbx]
0x18008753c  movdqa  [rbp+47h+var_40], xmm0
0x180087541  lea     rcx, [rbp+47h+var_40]
0x180087545  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18008754a  mov     sil, al
0x18008754d  mov     ecx, 348h; dwBytes
0x180087552  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180087557  mov     qword ptr [rbp+47h+var_40], rax
0x18008755b  test    rax, rax
0x18008755e  jz      short loc_180087596
0x180087560  movaps  xmm0, xmmword ptr [rbx]
0x180087563  movdqa  [rbp+47h+var_30], xmm0
0x180087568  mov     [rsp+0E0h+var_B0], sil
0x18008756d  lea     rcx, [rbp+47h+lpString1]
0x180087571  mov     [rsp+0E0h+var_B8], rcx
0x180087576  lea     rcx, [rbp+47h+var_30]
0x18008757a  mov     qword ptr [rsp+0E0h+bIgnoreCase], rcx
0x18008757f  mov     r9b, [rbp+47h+arg_20]
0x180087583  mov     r8, r12
0x180087586  mov     rdx, r14
0x180087589  mov     rcx, rax
0x18008758c  call    ??0File@@QEAA@PEAVFileManager@@_KW4FileModeFlags@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@$$QEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@4@_N@Z; File::File(FileManager *,unsigned __int64,FileModeFlags,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&,bool)
0x180087591  mov     rbx, rax
0x180087594  jmp     short loc_180087598
0x180087596  xor     ebx, ebx
0x180087598  mov     [rbp+47h+var_78], rbx
0x18008759c  test    rbx, rbx
0x18008759f  jz      short loc_1800875A8
0x1800875a1  lock inc dword ptr [rbx+328h]
0x1800875a8  mov     rax, [r14+8]
0x1800875ac  cmp     rax, [r14+10h]
0x1800875b0  jz      short loc_1800875BA
0x1800875b2  mov     [rax], rbx
0x1800875b5  jmp     loc_18008765D
0x1800875ba  mov     rsi, [r14]
0x1800875bd  mov     rcx, r14
0x1800875c0  call    ?_Grow@?$vector@PEAVFile@@V?$allocator@PEAVFile@@@utl@@@utl@@AEAA_NXZ; utl::vector<File *,utl::allocator<File *>>::_Grow(void)
0x1800875c5  test    al, al
0x1800875c7  jnz     short loc_180087638
0x1800875c9  lea     rax, WPP_GLOBAL_Control
0x1800875d0  mov     ebx, 0Eh
0x1800875d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800875dc  cmp     rcx, rax
0x1800875df  jz      short loc_180087606
0x1800875e1  test    dword ptr [rcx+1Ch], 8000h
0x1800875e8  jz      short loc_180087606
0x1800875ea  cmp     byte ptr [rcx+19h], 2
0x1800875ee  jb      short loc_180087606
0x1800875f0  lea     edx, [rbx-1]
0x1800875f3  mov     r9d, ebx
0x1800875f6  lea     r8, WPP_d33d9432658b3ff029c702686d00d94e_Traceguids
0x1800875fd  mov     rcx, [rcx+10h]
0x180087601  call    WPP_SF_d
0x180087606  xorps   xmm0, xmm0
0x180087609  movdqu  [rbp+47h+pExceptionObject], xmm0
0x18008760e  mov     [rbp+47h+var_90], 0
0x180087616  mov     [rbp+47h+var_88], ebx
0x180087619  mov     [rbp+47h+var_84], 0FFFFFFFFh
0x180087620  mov     [rbp+47h+var_80], 69h ; 'i'
0x180087627  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18008762e  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x180087632  call    _CxxThrowException_0
0x180087638  lea     rcx, [rbp+47h+var_78]
0x18008763c  sub     rcx, rsi
0x18008763f  mov     r8, [r14+8]
0x180087643  mov     rdx, [r14]
0x180087646  mov     rax, r8
0x180087649  sub     rax, rdx
0x18008764c  cmp     rcx, rax
0x18008764f  jnb     short loc_180087657
0x180087651  mov     rax, [rcx+rdx]
0x180087655  jmp     short loc_18008765A
0x180087657  mov     rax, rbx
0x18008765a  mov     [r8], rax
0x18008765d  add     qword ptr [r14+8], 8
0x180087662  mov     [r15], rbx
0x180087665  mov     [rbp+47h+var_78], 0
0x18008766d  lea     rcx, [rbp+47h+var_78]
0x180087671  call    ?Release@?$AutoRef@VFile@@@wmi@@QEAAXXZ; wmi::AutoRef<File>::Release(void)
0x180087676  nop
0x180087677  mov     rcx, rdi; SRWLock
0x18008767a  call    cs:__imp_ReleaseSRWLockExclusive
0x180087680  nop
0x180087681  lea     rcx, [rbp+47h+lpString1]; void *
0x180087685  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008768a  mov     rax, r15
0x18008768d  lea     r11, [rsp+0E0h+var_20]
0x180087695  mov     rbx, [r11+30h]
0x180087699  mov     rsi, [r11+38h]
0x18008769d  mov     rsp, r11
0x1800876a0  pop     r15
0x1800876a2  pop     r14
0x1800876a4  pop     r12
0x1800876a6  pop     rdi
0x1800876a7  pop     rbp
0x1800876a8  retn
```
