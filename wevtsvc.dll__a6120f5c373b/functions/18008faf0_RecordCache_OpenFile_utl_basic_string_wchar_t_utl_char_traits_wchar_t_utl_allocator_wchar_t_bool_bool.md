# RecordCache::OpenFile(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,bool,bool)

- ea: `0x18008faf0`
- end: `0x18008fc46`
- name: `?OpenFile@RecordCache@@QEAAXV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N1@Z`
- size: `342`
- prototype: `void __fastcall(RecordCache *this, void *, __int64, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x18008e3b8`

## callees

- `0x180017b60`
- `0x18003d2f8`
- `0x18005ff90`
- `0x18008faf0`
- `0x180092008`
- `0x1800b19b0`
- `0x1800b2050`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008fb1a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008fb1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008fc24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008fc24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fb8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fb8b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008fb68`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008fb68`

## pseudocode

```c
void __fastcall RecordCache::OpenFile(RecordCache *this, void *a2, __int64 a3, char a4)
{
  RTL_SRWLOCK *v7; // r15
  HANDLE FileW; // rax
  DWORD LastError; // ebx
  __int128 pExceptionObject; // [rsp+40h] [rbp-58h] BYREF
  __int64 v11; // [rsp+50h] [rbp-48h]
  DWORD v12; // [rsp+58h] [rbp-40h]
  int v13; // [rsp+5Ch] [rbp-3Ch]
  int v14; // [rsp+60h] [rbp-38h]

  v7 = (RTL_SRWLOCK *)((char *)this + 64);
  AcquireSRWLockExclusive((PSRWLOCK)this + 8);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=((char *)this + 24, a2);
  *((_BYTE *)this + 72) = 0;
  *((_QWORD *)this + 2) = 0;
  FileW = CreateFileW(*((LPCWSTR *)this + 3), 0xC0000000, 1u, 0, 2u, a4 != 0 ? 0x4000100 : 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 56, FileW);
  if ( *((_QWORD *)this + 7) == -1 || *((_QWORD *)this + 7) == 0 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, LastError);
    }
    pExceptionObject = 0;
    v11 = 0;
    v12 = LastError;
    v13 = -1;
    v14 = 466;
    throw (EvtException *)&pExceptionObject;
  }
  *((_QWORD *)this + 1) = RecordCache::GetFileSize(this);
  RecordCache::UpdateFileInfo(this);
  ReleaseSRWLockExclusive(v7);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(a2);
}

```

## disassembly

```asm
0x18008faf0  mov     rax, rsp
0x18008faf3  mov     [rax+18h], rbx
0x18008faf7  mov     [rax+10h], rdx
0x18008fafb  push    rbp
0x18008fafc  push    rsi
0x18008fafd  push    rdi
0x18008fafe  push    r14
0x18008fb00  push    r15
0x18008fb02  sub     rsp, 70h
0x18008fb06  mov     sil, r9b
0x18008fb09  mov     r14, rdx
0x18008fb0c  mov     rbp, rcx
0x18008fb0f  lea     r15, [rcx+40h]
0x18008fb13  mov     [rax+8], r15
0x18008fb17  mov     rcx, r15; SRWLock
0x18008fb1a  call    cs:__imp_AcquireSRWLockExclusive
0x18008fb20  nop
0x18008fb21  mov     rdx, r14
0x18008fb24  lea     rcx, [rbp+18h]
0x18008fb28  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18008fb2d  mov     byte ptr [rbp+48h], 0
0x18008fb31  mov     qword ptr [rbp+10h], 0
0x18008fb39  neg     sil
0x18008fb3c  sbb     eax, eax
0x18008fb3e  and     eax, 4000100h
0x18008fb43  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x18008fb4c  mov     [rsp+98h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18008fb50  mov     [rsp+98h+dwCreationDisposition], 2; dwCreationDisposition
0x18008fb58  xor     r9d, r9d; lpSecurityAttributes
0x18008fb5b  mov     edx, 0C0000000h; dwDesiredAccess
0x18008fb60  lea     r8d, [r9+1]; dwShareMode
0x18008fb64  mov     rcx, [rbp+18h]; lpFileName
0x18008fb68  call    cs:__imp_CreateFileW
0x18008fb6e  mov     rdx, rax
0x18008fb71  lea     rcx, [rbp+38h]
0x18008fb75  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18008fb7a  mov     rax, [rbp+38h]
0x18008fb7e  inc     rax
0x18008fb81  cmp     rax, 1
0x18008fb85  ja      loc_18008FC0C
0x18008fb8b  call    cs:__imp_GetLastError
0x18008fb91  mov     ebx, eax
0x18008fb93  mov     eax, 507h
0x18008fb98  test    ebx, ebx
0x18008fb9a  cmovz   ebx, eax
0x18008fb9d  lea     rax, WPP_GLOBAL_Control
0x18008fba4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fbab  cmp     rcx, rax
0x18008fbae  jz      short loc_18008FBD4
0x18008fbb0  test    byte ptr [rcx+1Ch], 1
0x18008fbb4  jz      short loc_18008FBD4
0x18008fbb6  cmp     byte ptr [rcx+19h], 2
0x18008fbba  jb      short loc_18008FBD4
0x18008fbbc  mov     edx, 15h
0x18008fbc1  mov     r9d, ebx
0x18008fbc4  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x18008fbcb  mov     rcx, [rcx+10h]
0x18008fbcf  call    WPP_SF_d
0x18008fbd4  xorps   xmm0, xmm0
0x18008fbd7  movdqu  [rsp+98h+pExceptionObject], xmm0
0x18008fbdd  mov     [rsp+98h+var_48], 0
0x18008fbe6  mov     [rsp+98h+var_40], ebx
0x18008fbea  mov     [rsp+98h+var_3C], 0FFFFFFFFh
0x18008fbf2  mov     [rsp+98h+var_38], 1D2h
0x18008fbfa  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18008fc01  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18008fc06  call    _CxxThrowException_0
0x18008fc0c  mov     rcx, rbp; this
0x18008fc0f  call    ?GetFileSize@RecordCache@@QEAA_KXZ; RecordCache::GetFileSize(void)
0x18008fc14  mov     [rbp+8], rax
0x18008fc18  mov     rcx, rbp; this
0x18008fc1b  call    ?UpdateFileInfo@RecordCache@@IEAAXXZ; RecordCache::UpdateFileInfo(void)
0x18008fc20  nop
0x18008fc21  mov     rcx, r15; SRWLock
0x18008fc24  call    cs:__imp_ReleaseSRWLockExclusive
0x18008fc2a  nop
0x18008fc2b  mov     rcx, r14; void *
0x18008fc2e  mov     rbx, [rsp+98h+arg_10]
0x18008fc36  add     rsp, 70h
0x18008fc3a  pop     r15
0x18008fc3c  pop     r14
0x18008fc3e  pop     rdi
0x18008fc3f  pop     rsi
0x18008fc40  pop     rbp
0x18008fc41  jmp     ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
```
