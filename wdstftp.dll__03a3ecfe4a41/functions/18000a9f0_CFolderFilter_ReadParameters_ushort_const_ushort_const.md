# CFolderFilter::ReadParameters(ushort const *,ushort const *)

- ea: `0x18000a9f0`
- end: `0x18000ab40`
- name: `?ReadParameters@CFolderFilter@@QEAAKPEBG0@Z`
- size: `336`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180001950`

## callees

- `0x18000a9a8`
- `0x18000a9f0`
- `0x18003b3b8`
- `0x18003b6a4`
- `0x18003ce78`
- `0x180060e70`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000aa0f`
- `KERNEL32!EnterCriticalSection` at `0x18000aa0f`
- `KERNEL32!LeaveCriticalSection` at `0x18000ab09`
- `KERNEL32!LeaveCriticalSection` at `0x18000ab09`
- `ADVAPI32!RegCloseKey` at `0x18000aa46`
- `ADVAPI32!RegCloseKey` at `0x18000ab1f`
- `ADVAPI32!RegCloseKey` at `0x18000aa46`
- `ADVAPI32!RegCloseKey` at `0x18000ab1f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000aa73`
- `ADVAPI32!RegOpenKeyExW` at `0x18000aa73`

## string_xrefs

- `0x18000aa65`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSTFTP`
- `0x18000aae6`: `CFolderFilter::ReadParameters: Read Filter[%u] = '%s'`

## pseudocode

```c
__int64 __fastcall CFolderFilter::ReadParameters(
        LPCRITICAL_SECTION lpCriticalSection,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  LPCRITICAL_SECTION v4; // rsi
  HKEY v5; // rcx
  LSTATUS v6; // eax
  const char *v7; // rdx
  unsigned int v8; // ebx
  const unsigned __int16 *v9; // rdx
  unsigned int ValueMultiSz; // eax
  const char *v11; // rdx
  __int64 v12; // rdi
  void (*v13)(const unsigned __int16 *, ...); // rax
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  hKey = 0;
  EnterCriticalSection(lpCriticalSection);
  CFolderFilter::Shutdown(lpCriticalSection);
  v4 = lpCriticalSection + 1;
  CRegKey::FreeMultiSz(
    *(unsigned __int16 ***)&lpCriticalSection[1].LockCount,
    (unsigned int)lpCriticalSection[1].DebugInfo);
  v5 = hKey;
  *(_QWORD *)&lpCriticalSection[1].LockCount = 0;
  LODWORD(lpCriticalSection[1].DebugInfo) = 0;
  if ( v5 )
    RegCloseKey(v5);
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSTFTP",
         0,
         0x20119u,
         &hKey);
  v8 = v6;
  if ( v6 == 2 )
    goto LABEL_4;
  if ( !ElValidateWin32(v6, v7, "base\\eco\\wds\\transport\\lib\\folderfilter.cpp", 0x94u) )
  {
    ValueMultiSz = CRegKey::GetValueMultiSz(
                     (CRegKey *)&hKey,
                     v9,
                     (unsigned __int16 ***)&lpCriticalSection[1].LockCount,
                     (unsigned int *)&lpCriticalSection[1]);
    v8 = ValueMultiSz;
    if ( ValueMultiSz == 2 )
    {
LABEL_4:
      v8 = 0;
      goto LABEL_13;
    }
    if ( !ElValidateWin32(ValueMultiSz, v11, "base\\eco\\wds\\transport\\lib\\folderfilter.cpp", 0x9Du) )
    {
      v12 = 0;
      if ( LODWORD(v4->DebugInfo) )
      {
        v13 = g_ErrLibTraceFunction;
        do
        {
          if ( v13 )
          {
            v13(
              L"CFolderFilter::ReadParameters: Read Filter[%u] = '%s'",
              (unsigned int)v12,
              *(_QWORD *)(*(_QWORD *)&lpCriticalSection[1].LockCount + 8 * v12));
            v13 = g_ErrLibTraceFunction;
          }
          v12 = (unsigned int)(v12 + 1);
        }
        while ( (unsigned int)v12 < LODWORD(v4->DebugInfo) );
      }
    }
  }
LABEL_13:
  LeaveCriticalSection(lpCriticalSection);
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x18000a9f0  mov     rax, rsp
0x18000a9f3  mov     [rax+8], rbx
0x18000a9f7  mov     [rax+10h], rbp
0x18000a9fb  mov     [rax+18h], r8
0x18000a9ff  push    rsi
0x18000aa00  push    rdi
0x18000aa01  push    r14
0x18000aa03  sub     rsp, 30h
0x18000aa07  and     qword ptr [rax+18h], 0
0x18000aa0c  mov     rbp, rcx
0x18000aa0f  call    cs:__imp_EnterCriticalSection
0x18000aa16  nop     dword ptr [rax+rax+00h]
0x18000aa1b  mov     rcx, rbp; lpCriticalSection
0x18000aa1e  call    ?Shutdown@CFolderFilter@@QEAAKXZ; CFolderFilter::Shutdown(void)
0x18000aa23  lea     rsi, [rbp+28h]
0x18000aa27  mov     edx, [rsi]; unsigned int
0x18000aa29  lea     r14, [rbp+30h]
0x18000aa2d  mov     rcx, [r14]; unsigned __int16 **
0x18000aa30  call    ?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z; CRegKey::FreeMultiSz(ushort * *,ulong)
0x18000aa35  mov     rcx, [rsp+48h+hKey]; hKey
0x18000aa3a  and     qword ptr [r14], 0
0x18000aa3e  and     dword ptr [rsi], 0
0x18000aa41  test    rcx, rcx
0x18000aa44  jz      short loc_18000AA52
0x18000aa46  call    cs:__imp_RegCloseKey
0x18000aa4d  nop     dword ptr [rax+rax+00h]
0x18000aa52  lea     rax, [rsp+48h+hKey]
0x18000aa57  mov     r9d, 20119h; samDesired
0x18000aa5d  xor     r8d, r8d; ulOptions
0x18000aa60  mov     [rsp+48h+phkResult], rax; phkResult
0x18000aa65  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x18000aa6c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000aa73  call    cs:__imp_RegOpenKeyExW
0x18000aa7a  nop     dword ptr [rax+rax+00h]
0x18000aa7f  mov     ebx, eax
0x18000aa81  cmp     eax, 2
0x18000aa84  jnz     short loc_18000AA8A
0x18000aa86  xor     ebx, ebx
0x18000aa88  jmp     short loc_18000AB06
0x18000aa8a  mov     r9d, 94h; unsigned int
0x18000aa90  lea     r8, aBaseEcoWdsTran_1; "base\\eco\\wds\\transport\\lib\\folderf"...
0x18000aa97  mov     ecx, eax; unsigned int
0x18000aa99  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000aa9e  test    eax, eax
0x18000aaa0  jnz     short loc_18000AB06
0x18000aaa2  mov     r9, rsi; unsigned int *
0x18000aaa5  lea     rcx, [rsp+48h+hKey]; this
0x18000aaaa  mov     r8, r14; unsigned __int16 ***
0x18000aaad  call    ?GetValueMultiSz@CRegKey@@QEAAKPEBGPEAPEAPEAGPEAK@Z; CRegKey::GetValueMultiSz(ushort const *,ushort * * *,ulong *)
0x18000aab2  mov     ebx, eax
0x18000aab4  cmp     eax, 2
0x18000aab7  jz      short loc_18000AA86
0x18000aab9  mov     r9d, 9Dh; unsigned int
0x18000aabf  lea     r8, aBaseEcoWdsTran_1; "base\\eco\\wds\\transport\\lib\\folderf"...
0x18000aac6  mov     ecx, eax; unsigned int
0x18000aac8  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000aacd  test    eax, eax
0x18000aacf  jnz     short loc_18000AB06
0x18000aad1  xor     edi, edi
0x18000aad3  cmp     [rsi], edi
0x18000aad5  jbe     short loc_18000AB06
0x18000aad7  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000aade  test    rax, rax
0x18000aae1  jz      short loc_18000AB00
0x18000aae3  mov     r8, [r14]
0x18000aae6  lea     rcx, aCfolderfilterR; "CFolderFilter::ReadParameters: Read Fil"...
0x18000aaed  mov     edx, edi
0x18000aaef  mov     r8, [r8+rdi*8]
0x18000aaf3  call    cs:__guard_dispatch_icall_fptr
0x18000aaf9  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000ab00  inc     edi
0x18000ab02  cmp     edi, [rsi]
0x18000ab04  jb      short loc_18000AADE
0x18000ab06  mov     rcx, rbp; lpCriticalSection
0x18000ab09  call    cs:__imp_LeaveCriticalSection
0x18000ab10  nop     dword ptr [rax+rax+00h]
0x18000ab15  mov     rcx, [rsp+48h+hKey]; hKey
0x18000ab1a  test    rcx, rcx
0x18000ab1d  jz      short loc_18000AB2B
0x18000ab1f  call    cs:__imp_RegCloseKey
0x18000ab26  nop     dword ptr [rax+rax+00h]
0x18000ab2b  mov     rbp, [rsp+48h+arg_8]
0x18000ab30  mov     eax, ebx
0x18000ab32  mov     rbx, [rsp+48h+arg_0]
0x18000ab37  add     rsp, 30h
0x18000ab3b  pop     r14
0x18000ab3d  pop     rdi
0x18000ab3e  pop     rsi
0x18000ab3f  retn
```
