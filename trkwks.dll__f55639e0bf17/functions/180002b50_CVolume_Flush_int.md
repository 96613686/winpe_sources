# CVolume::Flush(int)

- ea: `0x180002b50`
- end: `0x180002c89`
- name: `?Flush@CVolume@@QEAAXH@Z`
- size: `313`
- prototype: `void __fastcall(CVolume *__hidden this, int)`
- caller_count: `6`
- callee_count: `17`
- tags: ``

## callers

- `0x180002488`
- `0x18000297c`
- `0x180003428`
- `0x18000d5e4`
- `0x18000f4bc`
- `0x18000f66c`

## callees

- `0x1800012e8`
- `0x180002b50`
- `0x1800033b0`
- `0x1800073a0`
- `0x18000c548`
- `0x18000c840`
- `0x18000cd40`
- `0x18000cebc`
- `0x18000cef8`
- `0x18000cfd0`
- `0x18000d060`
- `0x18000d0a4`
- `0x18000d790`
- `0x18000d7dc`
- `0x18000ed70`
- `0x18000edb0`
- `0x180011000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b88`

## pseudocode

```c
void __fastcall CVolume::Flush(CVolume *this, int a2)
{
  __int64 v4; // rdx
  int v5; // ecx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  ++*((_DWORD *)this + 13);
  if ( (*((_BYTE *)this + 16) & 2) != 0 )
    CVolume::SaveVolInfo(this);
  CLog::Flush((CVolume *)((char *)this + 512));
  CLogFileHeader::RaiseIfNotOpen((CVolume *)((char *)this + 392));
  v4 = *((_QWORD *)this + 51);
  v5 = *(_DWORD *)(v4 + 20);
  if ( (v5 & 1) == 0 )
  {
    *(_DWORD *)(v4 + 20) = v5 | 1;
    *((_DWORD *)this + 98) |= 1u;
    CLogFileHeader::Flush((HANDLE *)this + 49);
  }
  CLogFile::Flush((CVolume *)((char *)this + 312));
  if ( a2 )
    CLogFile::UnregisterOplockFromThreadPool((CVolume *)((char *)this + 312));
  CVolume::Unlock(this);
}

```

## disassembly

```asm
0x180002b50  mov     [rsp+arg_10], rbx
0x180002b55  mov     [rsp+arg_8], edx
0x180002b59  push    rsi
0x180002b5a  push    rdi
0x180002b5b  push    r14
0x180002b5d  sub     rsp, 460h
0x180002b64  mov     rax, cs:__security_cookie
0x180002b6b  xor     rax, rsp
0x180002b6e  mov     [rsp+478h+var_28], rax
0x180002b76  mov     r14d, edx
0x180002b79  mov     rbx, rcx
0x180002b7c  mov     [rsp+478h+var_458], rcx
0x180002b81  add     rcx, 0A8h; lpCriticalSection
0x180002b88  call    cs:__imp_EnterCriticalSection
0x180002b8e  inc     dword ptr [rbx+34h]
0x180002b91  test    byte ptr [rbx+10h], 2
0x180002b95  jz      short loc_180002BA0
0x180002b97  mov     rcx, rbx; this
0x180002b9a  call    ?SaveVolInfo@CVolume@@AEAAXXZ; CVolume::SaveVolInfo(void)
0x180002b9f  nop
0x180002ba0  lea     rcx, [rbx+200h]; this
0x180002ba7  call    ?Flush@CLog@@QEAAXXZ; CLog::Flush(void)
0x180002bac  lea     rsi, [rbx+138h]
0x180002bb3  lea     rdi, [rsi+50h]
0x180002bb7  mov     rcx, rdi; this
0x180002bba  call    ?RaiseIfNotOpen@CLogFileHeader@@AEBAXXZ; CLogFileHeader::RaiseIfNotOpen(void)
0x180002bbf  mov     rdx, [rdi+10h]
0x180002bc3  mov     ecx, [rdx+14h]
0x180002bc6  test    cl, 1
0x180002bc9  jnz     short loc_180002BDC
0x180002bcb  or      ecx, 1
0x180002bce  mov     [rdx+14h], ecx
0x180002bd1  or      dword ptr [rdi], 1
0x180002bd4  mov     rcx, rdi; this
0x180002bd7  call    ?Flush@CLogFileHeader@@QEAAXXZ; CLogFileHeader::Flush(void)
0x180002bdc  mov     rcx, rsi; this
0x180002bdf  call    ?Flush@CLogFile@@QEAAXXZ; CLogFile::Flush(void)
0x180002be4  test    r14d, r14d
0x180002be7  jz      short loc_180002BF1
0x180002be9  mov     rcx, rsi; this
0x180002bec  call    ?UnregisterOplockFromThreadPool@CLogFile@@QEAAXXZ; CLogFile::UnregisterOplockFromThreadPool(void)
0x180002bf1  jmp     short loc_180002C5D
0x180002bf3  mov     ecx, eax; int
0x180002bf5  call    ?IsErrorDueToLockedVolume@@YAHJ@Z; IsErrorDueToLockedVolume(long)
0x180002bfa  mov     rbx, [rsp+478h+var_458]
0x180002bff  test    eax, eax
0x180002c01  jz      short loc_180002C2A
0x180002c03  mov     rcx, rbx; this
0x180002c06  call    ?CloseAndReopenVolumeHandles@CVolume@@QEAAXXZ; CVolume::CloseAndReopenVolumeHandles(void)
0x180002c0b  lea     rcx, [rbx+200h]; this
0x180002c12  call    ?Flush@CLog@@QEAAXXZ; CLog::Flush(void)
0x180002c17  lea     rcx, [rbx+138h]; this
0x180002c1e  mov     edx, 1; int
0x180002c23  call    ?SetShutdown@CLogFile@@QEAAXH@Z; CLogFile::SetShutdown(int)
0x180002c28  jmp     short loc_180002C5D
0x180002c2a  mov     ecx, [rbx+30h]; int
0x180002c2d  call    ?VolChar@@YAGJ@Z; VolChar(long)
0x180002c32  movzx   edx, ax; unsigned __int16
0x180002c35  lea     rcx, [rsp+478h+var_448]; this
0x180002c3a  call    ??0CStringize@@QEAA@G@Z; CStringize::CStringize(ushort)
0x180002c3f  mov     edx, 1; unsigned __int16
0x180002c44  xor     r9d, r9d
0x180002c47  mov     r8, rax
0x180002c4a  mov     ecx, 0C00030D7h; unsigned int
0x180002c4f  call    ?TrkReportEvent@@YAJKGZZ; TrkReportEvent(ulong,ushort,...)
0x180002c54  mov     rcx, rbx; this
0x180002c57  call    ?DeleteLogAndReInitializeVolume@CVolume@@AEAAXXZ; CVolume::DeleteLogAndReInitializeVolume(void)
0x180002c5c  nop
0x180002c5d  mov     rcx, rbx; this
0x180002c60  call    ?Unlock@CVolume@@AEAAKXZ; CVolume::Unlock(void)
0x180002c65  mov     rcx, [rsp+478h+var_28]
0x180002c6d  xor     rcx, rsp; StackCookie
0x180002c70  call    __security_check_cookie
0x180002c75  mov     rbx, [rsp+478h+arg_10]
0x180002c7d  add     rsp, 460h
0x180002c84  pop     r14
0x180002c86  pop     rdi
0x180002c87  pop     rsi
0x180002c88  retn
0x1800111dc  push    rbp
0x1800111de  sub     rsp, 20h
0x1800111e2  mov     rbp, rdx
0x1800111e5  mov     rax, [rcx]
0x1800111e8  mov     ecx, [rax]; int
0x1800111ea  cmp     dword ptr [rbp+488h], 0
0x1800111f1  jnz     short loc_18001120D
0x1800111f3  mov     rax, [rbp+20h]
0x1800111f7  cmp     dword ptr [rax+38h], 0
0x1800111fb  jnz     short loc_18001120D
0x1800111fd  call    ?IsRecoverableDiskError@@YAHJ@Z; IsRecoverableDiskError(long)
0x180011202  test    eax, eax
0x180011204  jz      short loc_18001120D
0x180011206  mov     eax, 1
0x18001120b  jmp     short loc_18001120F
0x18001120d  xor     eax, eax
0x18001120f  add     rsp, 20h
0x180011213  pop     rbp
0x180011214  retn
0x180011216  push    rbp
0x180011218  sub     rsp, 20h
0x18001121c  mov     rbp, rdx
0x18001121f  mov     rcx, [rbp+20h]; this
0x180011223  add     rsp, 20h
0x180011227  pop     rbp
0x180011228  jmp     ?Unlock@CVolume@@AEAAKXZ; CVolume::Unlock(void)
```
