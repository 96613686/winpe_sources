# WdcTraceControl::QueryThread(void *)

- ea: `0x18001fc00`
- end: `0x18001ff00`
- name: `?QueryThread@WdcTraceControl@@CAKPEAX@Z`
- size: `768`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000b854`
- `0x18001fc00`
- `0x18001ff08`
- `0x180086010`

## import_xrefs

- `pdh!PdhCloseQuery` at `0x18001fed3`
- `pdh!PdhCloseQuery` at `0x18001fed3`
- `pdh!PdhCollectQueryData` at `0x18001fd7e`
- `pdh!PdhCollectQueryData` at `0x18001fdd9`
- `pdh!PdhCollectQueryData` at `0x18001fd7e`
- `pdh!PdhCollectQueryData` at `0x18001fdd9`
- `pdh!PdhOpenQueryW` at `0x18001fc25`
- `pdh!PdhOpenQueryW` at `0x18001fc25`
- `KERNEL32!GetLastError` at `0x18001fdb8`
- `KERNEL32!GetLastError` at `0x18001fdb8`
- `KERNEL32!WaitForSingleObject` at `0x18001fda3`
- `KERNEL32!WaitForSingleObject` at `0x18001fda3`

## string_xrefs

- `0x18001fc4e`: `WdcTraceControl::QueryThread`

## pseudocode

```c
__int64 __fastcall WdcTraceControl::QueryThread(PVOID Parameter)
{
  PDH_STATUS v2; // eax
  signed int v3; // ebx
  DWORD v4; // eax
  signed int LastError; // eax
  PDH_STATUS v6; // eax
  PDH_HQUERY phQuery; // [rsp+40h] [rbp+10h] BYREF

  phQuery = 0;
  v2 = PdhOpenQueryW(0, 0, &phQuery);
  v3 = v2;
  if ( !v2 )
    goto LABEL_6;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 < 0 )
  {
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\control.cpp",
      "WdcTraceControl::QueryThread",
      0,
      L"FAILURE: 0x%08x",
      v3);
  }
  else
  {
LABEL_6:
    (*(void (__fastcall **)(_QWORD, PDH_HQUERY))(**((_QWORD **)Parameter + 24) + 80LL))(
      *((_QWORD *)Parameter + 24),
      phQuery);
    (*(void (__fastcall **)(_QWORD, PDH_HQUERY))(**((_QWORD **)Parameter + 25) + 80LL))(
      *((_QWORD *)Parameter + 25),
      phQuery);
    (*(void (__fastcall **)(_QWORD, PDH_HQUERY))(**((_QWORD **)Parameter + 26) + 80LL))(
      *((_QWORD *)Parameter + 26),
      phQuery);
    (*(void (__fastcall **)(_QWORD, PDH_HQUERY))(**((_QWORD **)Parameter + 27) + 80LL))(
      *((_QWORD *)Parameter + 27),
      phQuery);
    (*(void (__fastcall **)(_QWORD, PDH_HQUERY))(**((_QWORD **)Parameter + 16) + 80LL))(
      *((_QWORD *)Parameter + 16),
      phQuery);
    (*(void (__fastcall **)(_QWORD, PDH_HQUERY))(**((_QWORD **)Parameter + 17) + 80LL))(
      *((_QWORD *)Parameter + 17),
      phQuery);
    (*(void (__fastcall **)(_QWORD, PDH_HQUERY))(**((_QWORD **)Parameter + 18) + 80LL))(
      *((_QWORD *)Parameter + 18),
      phQuery);
    (*(void (__fastcall **)(_QWORD, PDH_HQUERY))(**((_QWORD **)Parameter + 23) + 80LL))(
      *((_QWORD *)Parameter + 23),
      phQuery);
    (*(void (__fastcall **)(_QWORD, PDH_HQUERY))(**((_QWORD **)Parameter + 19) + 80LL))(
      *((_QWORD *)Parameter + 19),
      phQuery);
    (*(void (__fastcall **)(_QWORD, PDH_HQUERY))(**((_QWORD **)Parameter + 20) + 80LL))(
      *((_QWORD *)Parameter + 20),
      phQuery);
    (*(void (__fastcall **)(_QWORD, PDH_HQUERY))(**((_QWORD **)Parameter + 21) + 80LL))(
      *((_QWORD *)Parameter + 21),
      phQuery);
    (*(void (__fastcall **)(_QWORD, PDH_HQUERY))(**((_QWORD **)Parameter + 22) + 80LL))(
      *((_QWORD *)Parameter + 22),
      phQuery);
    PdhCollectQueryData(phQuery);
    WdcProcessMonitor::StartQuery(*((WdcProcessMonitor **)Parameter + 19));
LABEL_7:
    v3 = 0;
    while ( v3 >= 0 )
    {
      v4 = WaitForSingleObject(*((HANDLE *)Parameter + 9), 0x3E8u);
      if ( !v4 )
      {
        v3 = 0;
        break;
      }
      if ( v4 == 258 )
      {
        PdhCollectQueryData(phQuery);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)Parameter + 24) + 72LL))(*((_QWORD *)Parameter + 24));
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)Parameter + 25) + 72LL))(*((_QWORD *)Parameter + 25));
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)Parameter + 26) + 72LL))(*((_QWORD *)Parameter + 26));
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)Parameter + 27) + 72LL))(*((_QWORD *)Parameter + 27));
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)Parameter + 16) + 72LL))(*((_QWORD *)Parameter + 16));
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)Parameter + 17) + 72LL))(*((_QWORD *)Parameter + 17));
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)Parameter + 18) + 72LL))(*((_QWORD *)Parameter + 18));
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)Parameter + 23) + 72LL))(*((_QWORD *)Parameter + 23));
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)Parameter + 19) + 72LL))(*((_QWORD *)Parameter + 19));
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)Parameter + 20) + 72LL))(*((_QWORD *)Parameter + 20));
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)Parameter + 21) + 72LL))(*((_QWORD *)Parameter + 21));
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)Parameter + 22) + 72LL))(*((_QWORD *)Parameter + 22));
        goto LABEL_7;
      }
      LastError = GetLastError();
      v3 = 0;
      if ( LastError )
      {
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        else
          v3 = LastError;
      }
    }
  }
  if ( phQuery )
  {
    v6 = PdhCloseQuery(phQuery);
    v3 = 0;
    if ( v6 )
    {
      if ( v6 > 0 )
        return (unsigned __int16)v6 | 0x80070000;
      else
        return (unsigned int)v6;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001fc00  mov     [rsp-8+arg_8], rbx
0x18001fc05  mov     [rsp-8+arg_10], rdi
0x18001fc0a  push    rbp
0x18001fc0b  mov     rbp, rsp
0x18001fc0e  sub     rsp, 30h
0x18001fc12  mov     rdi, rcx
0x18001fc15  mov     [rbp+phQuery], 0
0x18001fc1d  xor     ecx, ecx; szDataSource
0x18001fc1f  lea     r8, [rbp+phQuery]; phQuery
0x18001fc23  xor     edx, edx; dwUserData
0x18001fc25  call    cs:__imp_PdhOpenQueryW
0x18001fc2b  mov     ebx, eax
0x18001fc2d  test    eax, eax
0x18001fc2f  jz      short loc_18001FC66
0x18001fc31  jle     short loc_18001FC3C
0x18001fc33  movzx   ebx, ax
0x18001fc36  or      ebx, 80070000h
0x18001fc3c  test    ebx, ebx
0x18001fc3e  jns     short loc_18001FC66
0x18001fc40  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18001fc47  mov     [rsp+30h+var_10], ebx
0x18001fc4b  xor     r8d, r8d; int
0x18001fc4e  lea     rdx, aWdctracecontro_8; "WdcTraceControl::QueryThread"
0x18001fc55  lea     rcx, aBaseDiagnosisP_37; "base\\diagnosis\\pdui\\perfmon\\mon\\co"...
0x18001fc5c  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001fc61  jmp     loc_18001FECA
0x18001fc66  mov     rcx, [rdi+0C0h]
0x18001fc6d  mov     rdx, [rbp+phQuery]
0x18001fc71  mov     rax, [rcx]
0x18001fc74  mov     rax, [rax+50h]
0x18001fc78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc7d  mov     rcx, [rdi+0C8h]
0x18001fc84  mov     rdx, [rbp+phQuery]
0x18001fc88  mov     rax, [rcx]
0x18001fc8b  mov     rax, [rax+50h]
0x18001fc8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc94  mov     rcx, [rdi+0D0h]
0x18001fc9b  mov     rdx, [rbp+phQuery]
0x18001fc9f  mov     rax, [rcx]
0x18001fca2  mov     rax, [rax+50h]
0x18001fca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcab  mov     rcx, [rdi+0D8h]
0x18001fcb2  mov     rdx, [rbp+phQuery]
0x18001fcb6  mov     rax, [rcx]
0x18001fcb9  mov     rax, [rax+50h]
0x18001fcbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcc2  mov     rcx, [rdi+80h]
0x18001fcc9  mov     rdx, [rbp+phQuery]
0x18001fccd  mov     rax, [rcx]
0x18001fcd0  mov     rax, [rax+50h]
0x18001fcd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcd9  mov     rcx, [rdi+88h]
0x18001fce0  mov     rdx, [rbp+phQuery]
0x18001fce4  mov     rax, [rcx]
0x18001fce7  mov     rax, [rax+50h]
0x18001fceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcf0  mov     rcx, [rdi+90h]
0x18001fcf7  mov     rdx, [rbp+phQuery]
0x18001fcfb  mov     rax, [rcx]
0x18001fcfe  mov     rax, [rax+50h]
0x18001fd02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd07  mov     rcx, [rdi+0B8h]
0x18001fd0e  mov     rdx, [rbp+phQuery]
0x18001fd12  mov     rax, [rcx]
0x18001fd15  mov     rax, [rax+50h]
0x18001fd19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd1e  mov     rcx, [rdi+98h]
0x18001fd25  mov     rdx, [rbp+phQuery]
0x18001fd29  mov     rax, [rcx]
0x18001fd2c  mov     rax, [rax+50h]
0x18001fd30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd35  mov     rcx, [rdi+0A0h]
0x18001fd3c  mov     rdx, [rbp+phQuery]
0x18001fd40  mov     rax, [rcx]
0x18001fd43  mov     rax, [rax+50h]
0x18001fd47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd4c  mov     rcx, [rdi+0A8h]
0x18001fd53  mov     rdx, [rbp+phQuery]
0x18001fd57  mov     rax, [rcx]
0x18001fd5a  mov     rax, [rax+50h]
0x18001fd5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd63  mov     rcx, [rdi+0B0h]
0x18001fd6a  mov     rdx, [rbp+phQuery]
0x18001fd6e  mov     rax, [rcx]
0x18001fd71  mov     rax, [rax+50h]
0x18001fd75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd7a  mov     rcx, [rbp+phQuery]; hQuery
0x18001fd7e  call    cs:__imp_PdhCollectQueryData
0x18001fd84  mov     rcx, [rdi+98h]; this
0x18001fd8b  call    ?StartQuery@WdcProcessMonitor@@QEAAJXZ; WdcProcessMonitor::StartQuery(void)
0x18001fd90  xor     ebx, ebx
0x18001fd92  test    ebx, ebx
0x18001fd94  js      loc_18001FECA
0x18001fd9a  mov     rcx, [rdi+48h]; hHandle
0x18001fd9e  mov     edx, 3E8h; dwMilliseconds
0x18001fda3  call    cs:__imp_WaitForSingleObject
0x18001fda9  test    eax, eax
0x18001fdab  jz      loc_18001FEC8
0x18001fdb1  cmp     eax, 102h
0x18001fdb6  jz      short loc_18001FDD5
0x18001fdb8  call    cs:__imp_GetLastError
0x18001fdbe  xor     ebx, ebx
0x18001fdc0  test    eax, eax
0x18001fdc2  jz      short loc_18001FD92
0x18001fdc4  jg      short loc_18001FDCA
0x18001fdc6  mov     ebx, eax
0x18001fdc8  jmp     short loc_18001FD92
0x18001fdca  movzx   ebx, ax
0x18001fdcd  or      ebx, 80070000h
0x18001fdd3  jmp     short loc_18001FD92
0x18001fdd5  mov     rcx, [rbp+phQuery]; hQuery
0x18001fdd9  call    cs:__imp_PdhCollectQueryData
0x18001fddf  mov     rcx, [rdi+0C0h]
0x18001fde6  mov     rax, [rcx]
0x18001fde9  mov     rax, [rax+48h]
0x18001fded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdf2  mov     rcx, [rdi+0C8h]
0x18001fdf9  mov     rax, [rcx]
0x18001fdfc  mov     rax, [rax+48h]
0x18001fe00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe05  mov     rcx, [rdi+0D0h]
0x18001fe0c  mov     rax, [rcx]
0x18001fe0f  mov     rax, [rax+48h]
0x18001fe13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe18  mov     rcx, [rdi+0D8h]
0x18001fe1f  mov     rax, [rcx]
0x18001fe22  mov     rax, [rax+48h]
0x18001fe26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe2b  mov     rcx, [rdi+80h]
0x18001fe32  mov     rax, [rcx]
0x18001fe35  mov     rax, [rax+48h]
0x18001fe39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe3e  mov     rcx, [rdi+88h]
0x18001fe45  mov     rax, [rcx]
0x18001fe48  mov     rax, [rax+48h]
0x18001fe4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe51  mov     rcx, [rdi+90h]
0x18001fe58  mov     rax, [rcx]
0x18001fe5b  mov     rax, [rax+48h]
0x18001fe5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe64  mov     rcx, [rdi+0B8h]
0x18001fe6b  mov     rax, [rcx]
0x18001fe6e  mov     rax, [rax+48h]
0x18001fe72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe77  mov     rcx, [rdi+98h]
0x18001fe7e  mov     rax, [rcx]
0x18001fe81  mov     rax, [rax+48h]
0x18001fe85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe8a  mov     rcx, [rdi+0A0h]
0x18001fe91  mov     rax, [rcx]
0x18001fe94  mov     rax, [rax+48h]
0x18001fe98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe9d  mov     rcx, [rdi+0A8h]
0x18001fea4  mov     rax, [rcx]
0x18001fea7  mov     rax, [rax+48h]
0x18001feab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001feb0  mov     rcx, [rdi+0B0h]
0x18001feb7  mov     rax, [rcx]
0x18001feba  mov     rax, [rax+48h]
0x18001febe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fec3  jmp     loc_18001FD90
0x18001fec8  xor     ebx, ebx
0x18001feca  mov     rcx, [rbp+phQuery]; hQuery
0x18001fece  test    rcx, rcx
0x18001fed1  jz      short loc_18001FEEE
0x18001fed3  call    cs:__imp_PdhCloseQuery
0x18001fed9  xor     ebx, ebx
0x18001fedb  test    eax, eax
0x18001fedd  jz      short loc_18001FEEE
0x18001fedf  jg      short loc_18001FEE5
0x18001fee1  mov     ebx, eax
0x18001fee3  jmp     short loc_18001FEEE
0x18001fee5  movzx   ebx, ax
0x18001fee8  or      ebx, 80070000h
0x18001feee  mov     rdi, [rsp+30h+arg_10]
0x18001fef3  mov     eax, ebx
0x18001fef5  mov     rbx, [rsp+30h+arg_8]
0x18001fefa  add     rsp, 30h
0x18001fefe  pop     rbp
0x18001feff  retn
```
