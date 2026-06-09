# CPxeProvider::Shutdown(void)

- ea: `0x180004848`
- end: `0x1800049cf`
- name: `?Shutdown@CPxeProvider@@QEAAKXZ`
- size: `391`
- prototype: `unsigned int __fastcall(CPxeProvider *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004004`
- `0x1800041c4`
- `0x180006adc`

## callees

- `0x180002a30`
- `0x180004848`
- `0x180004ab4`
- `0x180013010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000496a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004983`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000496a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004983`
- `KERNEL32!EnterCriticalSection` at `0x180004860`
- `KERNEL32!EnterCriticalSection` at `0x180004860`
- `KERNEL32!LeaveCriticalSection` at `0x1800049b0`
- `KERNEL32!LeaveCriticalSection` at `0x1800049b0`
- `KERNEL32!FreeLibrary` at `0x18000492e`
- `KERNEL32!FreeLibrary` at `0x18000492e`
- `ADVAPI32!RegCloseKey` at `0x180004948`
- `ADVAPI32!RegCloseKey` at `0x180004948`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x1800048cd`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180004919`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x1800048cd`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180004919`

## pseudocode

```c
__int64 __fastcall CPxeProvider::Shutdown(CPxeProvider *this)
{
  unsigned int v2; // edi
  __int64 (__fastcall *v3)(_QWORD); // rax
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // eax
  __int64 v8; // r8
  HMODULE v9; // rcx
  HKEY v10; // rcx
  void *v11; // rcx

  v2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  if ( *((_DWORD *)this + 6) )
  {
    v3 = (__int64 (__fastcall *)(_QWORD))*((_QWORD *)this + 8);
    if ( v3 )
    {
      v4 = v3(*((_QWORD *)this + 9));
      v7 = ElValidateWin32_1(v4, v5, v6, 348);
      v8 = *(_QWORD *)this;
      v2 = v7;
      if ( v7 )
      {
        Trace(0x80000u, L"[%s] Shutdown failed (rc=%u)", v8, v7);
        CEventLog::Log((CEventLog *)qword_18001CC40, 0xC107010A, 2);
      }
      else
      {
        Trace(0x20000u, L"[%s] Shutdown successful.", v8);
        CEventLog::Log((CEventLog *)qword_18001CC40, 0x4107010Bu, 1);
      }
    }
  }
  v9 = (HMODULE)*((_QWORD *)this + 2);
  if ( v9 )
  {
    FreeLibrary(v9);
    *((_QWORD *)this + 2) = 0;
  }
  v10 = (HKEY)*((_QWORD *)this + 5);
  if ( v10 )
  {
    RegCloseKey(v10);
    *((_QWORD *)this + 5) = 0;
  }
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  if ( *(_QWORD *)this )
  {
    operator delete(*(void **)this);
    *(_QWORD *)this = 0;
  }
  v11 = (void *)*((_QWORD *)this + 1);
  if ( v11 )
  {
    operator delete(v11);
    *((_QWORD *)this + 1) = 0;
  }
  *((_OWORD *)this + 3) = 0;
  *((_OWORD *)this + 4) = 0;
  *((_OWORD *)this + 5) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 26) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  return v2;
}

```

## disassembly

```asm
0x180004848  mov     [rsp+arg_0], rbx
0x18000484d  mov     [rsp+arg_8], rsi
0x180004852  push    rdi
0x180004853  sub     rsp, 40h
0x180004857  mov     rbx, rcx
0x18000485a  xor     edi, edi
0x18000485c  add     rcx, 70h ; 'p'; lpCriticalSection
0x180004860  call    cs:__imp_EnterCriticalSection
0x180004867  nop     dword ptr [rax+rax+00h]
0x18000486c  cmp     [rbx+18h], edi
0x18000486f  jz      loc_180004925
0x180004875  mov     rax, [rbx+40h]
0x180004879  test    rax, rax
0x18000487c  jz      loc_180004925
0x180004882  mov     rcx, [rbx+48h]
0x180004886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000488b  mov     ecx, eax
0x18000488d  mov     r9d, 15Ch
0x180004893  call    ElValidateWin32_1
0x180004898  mov     r8, [rbx]
0x18000489b  mov     edi, eax
0x18000489d  test    eax, eax
0x18000489f  jnz     short loc_1800048DB
0x1800048a1  lea     rdx, aSShutdownSucce; "[%s] Shutdown successful."
0x1800048a8  mov     ecx, 20000h; unsigned int
0x1800048ad  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x1800048b2  mov     rcx, [rbx]
0x1800048b5  lea     r9d, [rdi+1]
0x1800048b9  mov     [rsp+48h+var_28], rcx
0x1800048be  mov     edx, 4107010Bh
0x1800048c3  lea     rcx, qword_18001CC40
0x1800048ca  mov     r8d, r9d
0x1800048cd  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x1800048d4  nop     dword ptr [rax+rax+00h]
0x1800048d9  jmp     short loc_180004925
0x1800048db  mov     r9d, edi
0x1800048de  lea     rdx, aSShutdownFaile; "[%s] Shutdown failed (rc=%u)"
0x1800048e5  mov     ecx, 80000h; unsigned int
0x1800048ea  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x1800048ef  mov     rax, [rbx]
0x1800048f2  lea     rcx, qword_18001CC40
0x1800048f9  mov     r9d, 1
0x1800048ff  mov     [rsp+48h+var_18], edi
0x180004903  mov     [rsp+48h+var_20], 5
0x18000490b  mov     edx, 0C107010Ah
0x180004910  mov     [rsp+48h+var_28], rax
0x180004915  lea     r8d, [r9+1]
0x180004919  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180004920  nop     dword ptr [rax+rax+00h]
0x180004925  mov     rcx, [rbx+10h]; hLibModule
0x180004929  test    rcx, rcx
0x18000492c  jz      short loc_18000493F
0x18000492e  call    cs:__imp_FreeLibrary
0x180004935  nop     dword ptr [rax+rax+00h]
0x18000493a  and     qword ptr [rbx+10h], 0
0x18000493f  mov     rcx, [rbx+28h]; hKey
0x180004943  test    rcx, rcx
0x180004946  jz      short loc_180004959
0x180004948  call    cs:__imp_RegCloseKey
0x18000494f  nop     dword ptr [rax+rax+00h]
0x180004954  and     qword ptr [rbx+28h], 0
0x180004959  and     dword ptr [rbx+18h], 0
0x18000495d  and     qword ptr [rbx+20h], 0
0x180004962  mov     rcx, [rbx]
0x180004965  test    rcx, rcx
0x180004968  jz      short loc_18000497A
0x18000496a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004971  nop     dword ptr [rax+rax+00h]
0x180004976  and     qword ptr [rbx], 0
0x18000497a  mov     rcx, [rbx+8]
0x18000497e  test    rcx, rcx
0x180004981  jz      short loc_180004994
0x180004983  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000498a  nop     dword ptr [rax+rax+00h]
0x18000498f  and     qword ptr [rbx+8], 0
0x180004994  xorps   xmm0, xmm0
0x180004997  lea     rcx, [rbx+70h]; lpCriticalSection
0x18000499b  movups  xmmword ptr [rbx+30h], xmm0
0x18000499f  xor     eax, eax
0x1800049a1  movups  xmmword ptr [rbx+40h], xmm0
0x1800049a5  movups  xmmword ptr [rbx+50h], xmm0
0x1800049a9  mov     [rbx+60h], rax
0x1800049ad  mov     [rbx+68h], eax
0x1800049b0  call    cs:__imp_LeaveCriticalSection
0x1800049b7  nop     dword ptr [rax+rax+00h]
0x1800049bc  mov     rbx, [rsp+48h+arg_0]
0x1800049c1  mov     eax, edi
0x1800049c3  mov     rsi, [rsp+48h+arg_8]
0x1800049c8  add     rsp, 40h
0x1800049cc  pop     rdi
0x1800049cd  retn
```
