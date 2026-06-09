# CSFPIntegrityCheckAndRepair::CSFPIntegrityCheckAndRepair(void)

- ea: `0x180002500`
- end: `0x180002675`
- name: `??0CSFPIntegrityCheckAndRepair@@QEAA@XZ`
- size: `373`
- prototype: `CSFPIntegrityCheckAndRepair *__fastcall(CSFPIntegrityCheckAndRepair *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180004590`

## callees

- `0x180002500`
- `0x18000267c`
- `0x1800054f0`
- `0x180007cc0`
- `0x180009410`
- `0x1800130b8`
- `0x18001a260`
- `0x18001a5e4`
- `0x18001c010`

## pseudocode

```c
CSFPIntegrityCheckAndRepair *__fastcall CSFPIntegrityCheckAndRepair::CSFPIntegrityCheckAndRepair(
        CSFPIntegrityCheckAndRepair *this)
{
  OFFLINE_REGISTRY_KEY *v1; // rdi
  __int64 v3; // rsi
  void (*v4)(void); // rax
  __int64 v5; // rcx
  HINSTANCE v6; // r8
  bool v7; // r9
  wchar_t *v8; // rcx
  unsigned __int64 v9; // rdx
  NTSTATUS v10; // eax
  __int128 v12; // [rsp+20h] [rbp-20h] BYREF
  wchar_t *v13; // [rsp+30h] [rbp-10h]

  *(_QWORD *)this = &CSFPIntegrityCheckAndRepair::`vftable';
  v1 = (CSFPIntegrityCheckAndRepair *)((char *)this + 16);
  *((_BYTE *)this + 8) = 0;
  v3 = 6;
  do
  {
    OFFLINE_REGISTRY_KEY::OFFLINE_REGISTRY_KEY(v1);
    v1 = (OFFLINE_REGISTRY_KEY *)((char *)v1 + 24);
    --v3;
  }
  while ( v3 );
  v4 = (void (*)(void))qword_18002B8C8;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 42) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_DWORD *)this + 48) = 0;
  *((_QWORD *)this + 25) = 0;
  if ( v4 )
    v4();
  *((_DWORD *)this + 3) = 1;
  if ( !*((_BYTE *)this + 8) )
  {
    v12 = 0;
    v13 = 0;
    if ( (int)Windows::COM::GetCurrentDllWin32Path((LPCWSTR)Windows::COM::GetCurrentDllWin32Path) < 0 )
    {
LABEL_7:
      v8 = v13;
LABEL_18:
      if ( v8 )
        anonymous_namespace_::OurRtlFreeStringRoutine();
      goto LABEL_20;
    }
    v9 = v12;
    if ( *((_QWORD *)&v12 + 1) - (_QWORD)v12 < 2u )
    {
      if ( (__int64)v12 + 2 < (unsigned __int64)v12 )
      {
        v10 = -1073741675;
LABEL_12:
        ConvertNtStatusToHResult(v10);
        goto LABEL_7;
      }
      v10 = RtlReallocateLUnicodeString(v5, v12 + 2, &v12);
      if ( v10 < 0 )
        goto LABEL_12;
      v9 = v12;
    }
    v13[v9 >> 1] = 0;
    if ( v13 && (*((_QWORD *)&v12 + 1) - (_QWORD)v12 < 2u || v13[(unsigned __int64)v12 >> 1]) )
      INTERNAL_ERROR_ACTION(-1073741595);
    WdsSmartLoad(v13, v13, v6, v7);
    v8 = v13;
    *((_BYTE *)this + 8) = 1;
    if ( v8 )
      goto LABEL_18;
  }
LABEL_20:
  LogAdapter::g_Logger = (struct LogAdapter::Logger *)&off_18002A040;
  return this;
}

```

## disassembly

```asm
0x180002500  mov     [rsp-18h+arg_8], rbx
0x180002505  mov     [rsp-18h+arg_10], rsi
0x18000250a  push    rbp
0x18000250b  push    rdi
0x18000250c  push    r14
0x18000250e  mov     rbp, rsp
0x180002511  sub     rsp, 40h
0x180002515  xor     r14d, r14d
0x180002518  lea     rax, ??_7CSFPIntegrityCheckAndRepair@@6B@; const CSFPIntegrityCheckAndRepair::`vftable'
0x18000251f  mov     [rcx], rax
0x180002522  lea     rdi, [rcx+10h]
0x180002526  mov     rbx, rcx
0x180002529  mov     [rcx+8], r14b
0x18000252d  lea     esi, [r14+6]
0x180002531  mov     rcx, rdi; this
0x180002534  call    ??0OFFLINE_REGISTRY_KEY@@QEAA@XZ; OFFLINE_REGISTRY_KEY::OFFLINE_REGISTRY_KEY(void)
0x180002539  add     rdi, 18h
0x18000253d  sub     rsi, 1
0x180002541  jnz     short loc_180002531
0x180002543  mov     rax, cs:qword_18002B8C8
0x18000254a  mov     [rbx+0A0h], r14
0x180002551  mov     [rbx+0A8h], r14d
0x180002558  mov     [rbx+0B0h], r14
0x18000255f  mov     [rbx+0B8h], r14
0x180002566  mov     [rbx+0C0h], r14d
0x18000256d  mov     [rbx+0C8h], r14
0x180002574  test    rax, rax
0x180002577  jz      short loc_18000257E
0x180002579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000257e  mov     dword ptr [rbx+0Ch], 1
0x180002585  cmp     [rbx+8], r14b
0x180002589  jnz     loc_180002646
0x18000258f  xorps   xmm0, xmm0
0x180002592  lea     rdx, [rbp+var_20]
0x180002596  xor     eax, eax
0x180002598  lea     rcx, ?GetCurrentDllWin32Path@COM@Windows@@YAJPEAXPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; lpModuleName
0x18000259f  movups  [rbp+var_20], xmm0
0x1800025a3  mov     [rbp+var_10], rax
0x1800025a7  call    ?GetCurrentDllWin32Path@COM@Windows@@YAJPEAXPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::GetCurrentDllWin32Path(void *,Windows::Auto<_LUNICODE_STRING> *)
0x1800025ac  test    eax, eax
0x1800025ae  jns     short loc_1800025B9
0x1800025b0  mov     rcx, [rbp+var_10]
0x1800025b4  jmp     loc_18000263C
0x1800025b9  mov     rdx, qword ptr [rbp+var_20]
0x1800025bd  mov     rax, qword ptr [rbp+var_20+8]
0x1800025c1  sub     rax, rdx
0x1800025c4  cmp     rax, 2
0x1800025c8  jnb     short loc_1800025F7
0x1800025ca  lea     rax, [rdx+2]
0x1800025ce  cmp     rax, rdx
0x1800025d1  jnb     short loc_1800025DA
0x1800025d3  mov     eax, 0C0000095h
0x1800025d8  jmp     short loc_1800025EA
0x1800025da  lea     r8, [rbp+var_20]
0x1800025de  mov     rdx, rax
0x1800025e1  call    RtlReallocateLUnicodeString
0x1800025e6  test    eax, eax
0x1800025e8  jns     short loc_1800025F3
0x1800025ea  mov     ecx, eax; Status
0x1800025ec  call    ConvertNtStatusToHResult
0x1800025f1  jmp     short loc_1800025B0
0x1800025f3  mov     rdx, qword ptr [rbp+var_20]
0x1800025f7  mov     rax, [rbp+var_10]
0x1800025fb  shr     rdx, 1
0x1800025fe  mov     [rax+rdx*2], r14w
0x180002603  mov     rdx, [rbp+var_10]; wchar_t *
0x180002607  test    rdx, rdx
0x18000260a  jz      short loc_180002627
0x18000260c  mov     rax, qword ptr [rbp+var_20+8]
0x180002610  mov     rcx, qword ptr [rbp+var_20]
0x180002614  sub     rax, rcx
0x180002617  cmp     rax, 2
0x18000261b  jb      short loc_18000266A
0x18000261d  shr     rcx, 1
0x180002620  cmp     [rdx+rcx*2], r14w
0x180002625  jnz     short loc_18000266A
0x180002627  mov     rcx, rdx; wchar_t *
0x18000262a  call    ?WdsSmartLoad@@YAJPEB_W0PEAUHINSTANCE__@@_N@Z; WdsSmartLoad(wchar_t const *,wchar_t const *,HINSTANCE__ *,bool)
0x18000262f  mov     rcx, [rbp+var_10]
0x180002633  mov     byte ptr [rbx+8], 1
0x180002637  test    rcx, rcx
0x18000263a  jz      short loc_180002646
0x18000263c  test    rcx, rcx
0x18000263f  jz      short loc_180002646
0x180002641  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180002646  mov     rsi, [rsp+40h+arg_10]
0x18000264b  lea     rax, off_18002A040
0x180002652  mov     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, rax; LogAdapter::Logger * LogAdapter::g_Logger
0x180002659  mov     rax, rbx
0x18000265c  mov     rbx, [rsp+40h+arg_8]
0x180002661  add     rsp, 40h
0x180002665  pop     r14
0x180002667  pop     rdi
0x180002668  pop     rbp
0x180002669  retn
0x18000266a  mov     ecx, 0C00000E5h; int
0x18000266f  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
