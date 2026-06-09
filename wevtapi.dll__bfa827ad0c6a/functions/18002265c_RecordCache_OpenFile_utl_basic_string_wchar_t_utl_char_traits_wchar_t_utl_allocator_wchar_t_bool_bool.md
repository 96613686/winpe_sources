# RecordCache::OpenFile(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,bool,bool)

- ea: `0x18002265c`
- end: `0x1800227ab`
- name: `?OpenFile@RecordCache@@QEAAXV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N1@Z`
- size: `335`
- prototype: `__int64 __fastcall(RecordCache *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x180036578`
- `0x180037a04`

## callees

- `0x18000a724`
- `0x180013cc4`
- `0x18002265c`
- `0x180022d84`
- `0x180023548`
- `0x18003741c`
- `0x180038a3c`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022684`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022684`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022788`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226ef`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800226cc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800226cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RecordCache::OpenFile(RecordCache *this, __int64 a2)
{
  RTL_SRWLOCK *v4; // r14
  HANDLE FileW; // rax
  DWORD LastError; // ebx
  __int128 pExceptionObject; // [rsp+40h] [rbp-48h] BYREF
  __int64 v9; // [rsp+50h] [rbp-38h]
  DWORD v10; // [rsp+58h] [rbp-30h]
  int v11; // [rsp+5Ch] [rbp-2Ch]
  int v12; // [rsp+60h] [rbp-28h]

  v4 = (RTL_SRWLOCK *)((char *)this + 64);
  AcquireSRWLockExclusive((PSRWLOCK)this + 8);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=((char *)this + 24, a2);
  *((_BYTE *)this + 72) = 1;
  *((_QWORD *)this + 2) = 0;
  FileW = CreateFileW(*((LPCWSTR *)this + 3), 0x80000000, 1u, 0, 3u, 0x10000000u, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 56, FileW);
  if ( *((_QWORD *)this + 7) == -1 || *((_QWORD *)this + 7) == 0 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, LastError);
    }
    pExceptionObject = 0;
    v9 = 0;
    v10 = LastError;
    v11 = -1;
    v12 = 466;
    throw (EvtException *)&pExceptionObject;
  }
  *((_QWORD *)this + 1) = RecordCache::GetFileSize(this);
  RecordCache::UpdateFileInfo(this);
  ReleaseSRWLockExclusive(v4);
  return utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(a2);
}

```

## disassembly

```asm
0x18002265c  mov     rax, rsp
0x18002265f  mov     [rax+18h], rbx
0x180022663  mov     [rax+20h], rbp
0x180022667  mov     [rax+10h], rdx
0x18002266b  push    rsi
0x18002266c  push    rdi
0x18002266d  push    r14
0x18002266f  sub     rsp, 70h
0x180022673  mov     rbp, rdx
0x180022676  mov     rsi, rcx
0x180022679  lea     r14, [rcx+40h]
0x18002267d  mov     [rax+8], r14
0x180022681  mov     rcx, r14; SRWLock
0x180022684  call    cs:__imp_AcquireSRWLockExclusive
0x18002268a  nop
0x18002268b  mov     rdx, rbp
0x18002268e  lea     rcx, [rsi+18h]
0x180022692  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x180022697  mov     byte ptr [rsi+48h], 1
0x18002269b  mov     qword ptr [rsi+10h], 0
0x1800226a3  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x1800226ac  mov     [rsp+88h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x1800226b4  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x1800226bc  xor     r9d, r9d; lpSecurityAttributes
0x1800226bf  mov     edx, 80000000h; dwDesiredAccess
0x1800226c4  lea     r8d, [r9+1]; dwShareMode
0x1800226c8  mov     rcx, [rsi+18h]; lpFileName
0x1800226cc  call    cs:__imp_CreateFileW
0x1800226d2  mov     rdx, rax
0x1800226d5  lea     rcx, [rsi+38h]
0x1800226d9  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800226de  mov     rax, [rsi+38h]
0x1800226e2  inc     rax
0x1800226e5  cmp     rax, 1
0x1800226e9  ja      loc_180022770
0x1800226ef  call    cs:__imp_GetLastError
0x1800226f5  mov     ebx, eax
0x1800226f7  mov     eax, 507h
0x1800226fc  test    ebx, ebx
0x1800226fe  cmovz   ebx, eax
0x180022701  lea     rax, WPP_GLOBAL_Control
0x180022708  mov     rcx, cs:WPP_GLOBAL_Control
0x18002270f  cmp     rcx, rax
0x180022712  jz      short loc_180022738
0x180022714  test    byte ptr [rcx+1Ch], 1
0x180022718  jz      short loc_180022738
0x18002271a  cmp     byte ptr [rcx+19h], 2
0x18002271e  jb      short loc_180022738
0x180022720  mov     edx, 15h
0x180022725  mov     r9d, ebx
0x180022728  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x18002272f  mov     rcx, [rcx+10h]
0x180022733  call    WPP_SF_D
0x180022738  xorps   xmm0, xmm0
0x18002273b  movdqu  [rsp+88h+pExceptionObject], xmm0
0x180022741  mov     [rsp+88h+var_38], 0
0x18002274a  mov     [rsp+88h+var_30], ebx
0x18002274e  mov     [rsp+88h+var_2C], 0FFFFFFFFh
0x180022756  mov     [rsp+88h+var_28], 1D2h
0x18002275e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180022765  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18002276a  call    _CxxThrowException_0
0x180022770  mov     rcx, rsi; this
0x180022773  call    ?GetFileSize@RecordCache@@QEAA_KXZ; RecordCache::GetFileSize(void)
0x180022778  mov     [rsi+8], rax
0x18002277c  mov     rcx, rsi; this
0x18002277f  call    ?UpdateFileInfo@RecordCache@@IEAAXXZ; RecordCache::UpdateFileInfo(void)
0x180022784  nop
0x180022785  mov     rcx, r14; SRWLock
0x180022788  call    cs:__imp_ReleaseSRWLockExclusive
0x18002278e  nop
0x18002278f  mov     rcx, rbp
0x180022792  lea     r11, [rsp+88h+var_18]
0x180022797  mov     rbx, [r11+30h]
0x18002279b  mov     rbp, [r11+38h]
0x18002279f  mov     rsp, r11
0x1800227a2  pop     r14
0x1800227a4  pop     rdi
0x1800227a5  pop     rsi
0x1800227a6  jmp     ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
```
