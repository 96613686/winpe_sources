# CUmRdpDrv::HandleDriveAnnounceEvent(tagDRDEVLST *,tagRDPDR_DRIVEDEVICE_SUB *,void *)

- ea: `0x180018390`
- end: `0x180018578`
- name: `?HandleDriveAnnounceEvent@CUmRdpDrv@@QEAAHPEAUtagDRDEVLST@@PEAUtagRDPDR_DRIVEDEVICE_SUB@@PEAX@Z`
- size: `488`
- prototype: `__int64 __fastcall(CUmRdpDrv *__hidden this, struct tagDRDEVLST *, struct tagRDPDR_DRIVEDEVICE_SUB *, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010904`

## callees

- `0x18000a01c`
- `0x18000a41c`
- `0x18000c4d8`
- `0x18001294c`
- `0x1800140a4`
- `0x180018390`
- `0x180018624`
- `0x180019c20`
- `0x180019d30`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018515`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018515`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001845d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001845d`

## pseudocode

```c
__int64 __fastcall CUmRdpDrv::HandleDriveAnnounceEvent(
        CUmRdpDrv *this,
        struct tagDRDEVLST *a2,
        struct tagRDPDR_DRIVEDEVICE_SUB *a3,
        void *a4)
{
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  CUmRdpDr *v10; // rcx
  unsigned int v11; // ebx
  unsigned int v12; // r8d
  unsigned int v13; // ecx
  __int64 v14; // r9
  CUmRdpDr *v15; // rcx
  CUmRdpRpc *v17[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v18[272]; // [rsp+50h] [rbp-B0h] BYREF

  StringCchPrintfW(v18, 0x10Eu, L"\\\\%s\\%s", (char *)a3 + 500, a3);
  v8 = -1;
  do
    ++v8;
  while ( v18[v8] );
  if ( *((_WORD *)&v17[1] + v8 + 3) == 58 )
  {
    v9 = 2 * v8 - 2;
    if ( v9 >= 0x21C )
      _report_rangecheckfailure();
    *(unsigned __int16 *)((char *)v18 + v9) = 0;
  }
  v10 = *(CUmRdpDr **)this;
  v17[0] = 0;
  if ( !(unsigned int)CUmRdpDr::CreateUmRdpRpc(v10, v17) )
  {
    CUmRdpRpc::WNetAddConnection2W(v17[0], v18, (unsigned __int16 *)this + 6, a4);
    CUmRdpRpc::Release(v17[0]);
  }
  if ( !ImpersonateLoggedOnUser(*((HANDLE *)this + 67)) )
    return 0;
  v11 = DRDEVLST_Add(
          a2,
          *((_DWORD *)a3 + 166),
          -1,
          *((_DWORD *)a3 + 165),
          v18,
          (unsigned __int16 *)a3,
          (char *)a3 + 668);
  if ( !v11 )
    goto LABEL_19;
  v12 = *((_DWORD *)a2 + 2);
  v13 = 0;
  v11 = 1;
  if ( v12 )
  {
    v14 = *(_QWORD *)a2;
    while ( *(_DWORD *)(v14 + 80LL * v13) != *((_DWORD *)a3 + 166)
         || *(_DWORD *)(v14 + 80LL * v13 + 8) != *((_DWORD *)a3 + 165) )
    {
      if ( ++v13 >= v12 )
        goto LABEL_15;
    }
    goto LABEL_16;
  }
LABEL_15:
  if ( v13 < v12 )
  {
LABEL_16:
    CUmRdpDrv::CreateDriveFolder(this, v18, (unsigned __int16 *)a3 + 266, (va_list *)(*(_QWORD *)a2 + 80LL * v13));
    goto LABEL_19;
  }
  v11 = 0;
LABEL_19:
  if ( !RevertToSelf() )
    return 0;
  if ( !v11 )
  {
    v15 = *(CUmRdpDr **)this;
    v17[0] = 0;
    if ( !(unsigned int)CUmRdpDr::CreateUmRdpRpc(v15, v17) )
    {
      CUmRdpRpc::WNetCancelConnection2W(v17[0], v18);
      CUmRdpRpc::Release(v17[0]);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180018390  push    rbp
0x180018392  push    rbx
0x180018393  push    rsi
0x180018394  push    rdi
0x180018395  push    r14
0x180018397  push    r15
0x180018399  lea     rbp, [rsp-188h]
0x1800183a1  sub     rsp, 288h
0x1800183a8  mov     rax, cs:__security_cookie
0x1800183af  xor     rax, rsp
0x1800183b2  mov     [rbp+1B0h+var_40], rax
0x1800183b9  mov     rbx, r9
0x1800183bc  mov     [rsp+2B0h+var_290], r8
0x1800183c1  lea     r9, [r8+1F4h]
0x1800183c8  mov     rdi, r8
0x1800183cb  mov     r14, rdx
0x1800183ce  lea     r8, aSS_0; "\\\\%s\\%s"
0x1800183d5  mov     rsi, rcx
0x1800183d8  mov     edx, 10Eh; unsigned __int64
0x1800183dd  lea     rcx, [rsp+2B0h+var_260]; unsigned __int16 *
0x1800183e2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800183e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800183eb  lea     rcx, [rsp+2B0h+var_260]
0x1800183f0  xor     r15d, r15d
0x1800183f3  inc     rax
0x1800183f6  cmp     [rcx+rax*2], r15w
0x1800183fb  jnz     short loc_1800183F3
0x1800183fd  cmp     [rsp+rax*2+2B0h+var_262], 3Ah ; ':'
0x180018403  jnz     short loc_180018420
0x180018405  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18001840d  cmp     rcx, 21Ch
0x180018414  jnb     loc_18001850C
0x18001841a  mov     [rsp+rcx+2B0h+var_260], r15w
0x180018420  mov     rcx, [rsi]; this
0x180018423  lea     rdx, [rsp+2B0h+var_270]; struct CUmRdpRpc **
0x180018428  mov     [rsp+2B0h+var_270], r15
0x18001842d  call    ?CreateUmRdpRpc@CUmRdpDr@@QEAAJAEAPEAVCUmRdpRpc@@@Z; CUmRdpDr::CreateUmRdpRpc(CUmRdpRpc * &)
0x180018432  test    eax, eax
0x180018434  jnz     short loc_180018456
0x180018436  mov     rcx, [rsp+2B0h+var_270]; this
0x18001843b  lea     r8, [rsi+0Ch]; unsigned __int16 *
0x18001843f  mov     r9, rbx; void *
0x180018442  lea     rdx, [rsp+2B0h+var_260]; unsigned __int16 *
0x180018447  call    ?WNetAddConnection2W@CUmRdpRpc@@QEAAIPEAG0PEAX@Z; CUmRdpRpc::WNetAddConnection2W(ushort *,ushort *,void *)
0x18001844c  mov     rcx, [rsp+2B0h+var_270]; this
0x180018451  call    ?Release@CUmRdpRpc@@QEAAXXZ; CUmRdpRpc::Release(void)
0x180018456  mov     rcx, [rsi+218h]; hToken
0x18001845d  call    cs:__imp_ImpersonateLoggedOnUser
0x180018463  test    eax, eax
0x180018465  jz      loc_180018554
0x18001846b  mov     r9d, [rdi+294h]; unsigned int
0x180018472  lea     rax, [rdi+29Ch]
0x180018479  mov     edx, [rdi+298h]; unsigned int
0x18001847f  or      r8d, 0FFFFFFFFh; unsigned int
0x180018483  mov     [rsp+2B0h+var_280], rax; char *
0x180018488  mov     rcx, r14; struct tagDRDEVLST *
0x18001848b  lea     rax, [rsp+2B0h+var_260]
0x180018490  mov     [rsp+2B0h+var_288], rdi; unsigned __int16 *
0x180018495  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x18001849a  call    ?DRDEVLST_Add@@YAHPEAUtagDRDEVLST@@KKKPEBG1PEBD@Z; DRDEVLST_Add(tagDRDEVLST *,ulong,ulong,ulong,ushort const *,ushort const *,char const *)
0x18001849f  mov     ebx, eax
0x1800184a1  test    eax, eax
0x1800184a3  jz      short loc_180018515
0x1800184a5  mov     r8d, [r14+8]
0x1800184a9  mov     ecx, r15d
0x1800184ac  mov     ebx, 1
0x1800184b1  test    r8d, r8d
0x1800184b4  jz      short loc_1800184E4
0x1800184b6  mov     r10d, [rdi+294h]
0x1800184bd  mov     r11d, [rdi+298h]
0x1800184c4  mov     r9, [r14]
0x1800184c7  mov     eax, ecx
0x1800184c9  lea     rdx, [rax+rax*4]
0x1800184cd  add     rdx, rdx
0x1800184d0  cmp     [r9+rdx*8], r11d
0x1800184d4  jnz     short loc_1800184DD
0x1800184d6  cmp     [r9+rdx*8+8], r10d
0x1800184db  jz      short loc_1800184E9
0x1800184dd  add     ecx, ebx
0x1800184df  cmp     ecx, r8d
0x1800184e2  jb      short loc_1800184C7
0x1800184e4  cmp     ecx, r8d
0x1800184e7  jnb     short loc_180018512
0x1800184e9  mov     eax, ecx
0x1800184eb  lea     r8, [rdi+214h]; unsigned __int16 *
0x1800184f2  lea     rdx, [rsp+2B0h+var_260]; unsigned __int16 *
0x1800184f7  mov     rcx, rsi; this
0x1800184fa  lea     r9, [rax+rax*4]
0x1800184fe  shl     r9, 4
0x180018502  add     r9, [r14]; struct tagDRDEVLSTENTRY *
0x180018505  call    ?CreateDriveFolder@CUmRdpDrv@@AEAAHPEAG0PEAUtagDRDEVLSTENTRY@@@Z; CUmRdpDrv::CreateDriveFolder(ushort *,ushort *,tagDRDEVLSTENTRY *)
0x18001850a  jmp     short loc_180018515
0x18001850c  call    __report_rangecheckfailure
0x180018512  mov     ebx, r15d
0x180018515  call    cs:__imp_RevertToSelf
0x18001851b  test    eax, eax
0x18001851d  jz      short loc_180018554
0x18001851f  test    ebx, ebx
0x180018521  jnz     short loc_180018557
0x180018523  mov     rcx, [rsi]; this
0x180018526  lea     rdx, [rsp+2B0h+var_270]; struct CUmRdpRpc **
0x18001852b  mov     [rsp+2B0h+var_270], r15
0x180018530  call    ?CreateUmRdpRpc@CUmRdpDr@@QEAAJAEAPEAVCUmRdpRpc@@@Z; CUmRdpDr::CreateUmRdpRpc(CUmRdpRpc * &)
0x180018535  test    eax, eax
0x180018537  jnz     short loc_180018557
0x180018539  mov     rcx, [rsp+2B0h+var_270]; this
0x18001853e  lea     rdx, [rsp+2B0h+var_260]; unsigned __int16 *
0x180018543  call    ?WNetCancelConnection2W@CUmRdpRpc@@QEAAIPEAG@Z; CUmRdpRpc::WNetCancelConnection2W(ushort *)
0x180018548  mov     rcx, [rsp+2B0h+var_270]; this
0x18001854d  call    ?Release@CUmRdpRpc@@QEAAXXZ; CUmRdpRpc::Release(void)
0x180018552  jmp     short loc_180018557
0x180018554  mov     ebx, r15d
0x180018557  mov     eax, ebx
0x180018559  mov     rcx, [rbp+1B0h+var_40]
0x180018560  xor     rcx, rsp; StackCookie
0x180018563  call    __security_check_cookie
0x180018568  add     rsp, 288h
0x18001856f  pop     r15
0x180018571  pop     r14
0x180018573  pop     rdi
0x180018574  pop     rsi
0x180018575  pop     rbx
0x180018576  pop     rbp
0x180018577  retn
```
