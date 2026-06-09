# SampMuiEnterCriticalSection(void)

- ea: `0x180008830`
- end: `0x1800088b1`
- name: `?SampMuiEnterCriticalSection@@YAXXZ`
- size: `129`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008c40`

## callees

- `0x180006620`
- `0x180008830`
- `0x180008b1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x18000888c`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x18000888c`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180008860`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180008860`
- `ntdll!RtlEnterCriticalSection` at `0x180008850`
- `ntdll!RtlEnterCriticalSection` at `0x180008850`

## pseudocode

```c
void SampMuiEnterCriticalSection(void)
{
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  RtlEnterCriticalSection(&SamMuiLogLock);
  if ( GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    StringCchCatW(Buffer, 0x104u, L"\\debug\\sammui.log");
    SamMuiLogFile = _wfopen(Buffer, L"a");
  }
}

```

## disassembly

```asm
0x180008830  sub     rsp, 248h
0x180008837  mov     rax, cs:__security_cookie
0x18000883e  xor     rax, rsp
0x180008841  mov     [rsp+248h+var_18], rax
0x180008849  lea     rcx, ?SamMuiLogLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180008850  call    cs:__imp_RtlEnterCriticalSection
0x180008856  mov     edx, 104h; uSize
0x18000885b  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x180008860  call    cs:__imp_GetWindowsDirectoryW
0x180008866  test    eax, eax
0x180008868  jz      short loc_180008899
0x18000886a  lea     r8, aDebugSammuiLog; "\\debug\\sammui.log"
0x180008871  mov     edx, 104h; unsigned __int64
0x180008876  lea     rcx, [rsp+248h+Buffer]; unsigned __int16 *
0x18000887b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008880  lea     rdx, aA; "a"
0x180008887  lea     rcx, [rsp+248h+Buffer]; FileName
0x18000888c  call    cs:__imp__wfopen
0x180008892  mov     cs:?SamMuiLogFile@@3PEAU_iobuf@@EA, rax; _iobuf * SamMuiLogFile
0x180008899  mov     rcx, [rsp+248h+var_18]
0x1800088a1  xor     rcx, rsp; StackCookie
0x1800088a4  call    __security_check_cookie
0x1800088a9  add     rsp, 248h
0x1800088b0  retn
```
