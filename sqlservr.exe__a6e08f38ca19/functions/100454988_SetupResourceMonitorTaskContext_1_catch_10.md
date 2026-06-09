# _SetupResourceMonitorTaskContext_::_1_::catch$10

- ea: `0x100454988`
- end: `0x100454a73`
- name: `_SetupResourceMonitorTaskContext_::_1_::catch$10`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x10041ef70`
- `0x1004403d0`
- `0x100454988`

## import_xrefs

- `sqlTsEs!?PrintStringW@@YAHPEA_WKPEB_WZZ` at `0x100454a39`
- `sqlTsEs!?PrintStringW@@YAHPEA_WKPEB_WZZ` at `0x100454a39`
- `sqldk!SystemThread_TlsOffset` at `0x1004549f6`
- `sqldk!SystemThread_TlsIndex` at `0x1004549ed`
- `sqldk!??1ExceptionBackout@@QEAA@XZ` at `0x100454a5f`
- `sqldk!??1ExceptionBackout@@QEAA@XZ` at `0x100454a5f`
- `sqldk!??0ExceptionBackout@@QEAA@PEBVSQLError@@@Z` at `0x1004549a3`
- `sqldk!??0ExceptionBackout@@QEAA@PEBVSQLError@@@Z` at `0x1004549a3`

## pseudocode

```c
void *__fastcall SetupResourceMonitorTaskContext_::_1_::catch_10(__int64 a1, __int64 a2)
{
  int v3; // ecx

  ExceptionBackout::ExceptionBackout((ExceptionBackout *)(a2 + 280), (const struct SQLError *)(a2 + 184));
  v3 = *(_DWORD *)(a2 + 184);
  if ( v3 / 100 == 29 )
  {
    *(_DWORD *)(a2 + 48) = 0;
    if ( v3 == 2905 )
    {
      scierrlog(
        0x439Cu,
        L"resource monitor",
        (unsigned int)*(__int16 *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                               + SystemThread_TlsIndex)
                                             + SystemThread_TlsOffset
                                             + 80LL)
                                 + 72LL));
    }
    else
    {
      PrintStringW((wchar_t *)(a2 + 432), 0x100u, L"Exception 0x%X", *(unsigned int *)(a2 + 196));
      scierrlog(0x429Du, L"resource monitor", a2 + 432);
    }
  }
  else
  {
    *(_DWORD *)(a2 + 48) = 1;
  }
  ExceptionBackout::~ExceptionBackout((ExceptionBackout *)(a2 + 280));
  return &loc_10041F290;
}

```

## disassembly

```asm
0x100454988  mov     [rsp+arg_8], rdx
0x10045498d  push    rbp
0x10045498e  sub     rsp, 30h
0x100454992  mov     rbp, rdx
0x100454995  lea     rdx, [rbp+0B8h]
0x10045499c  lea     rcx, [rbp+118h]
0x1004549a3  call    cs:__imp_??0ExceptionBackout@@QEAA@PEBVSQLError@@@Z; ExceptionBackout::ExceptionBackout(SQLError const *)
0x1004549a9  nop
0x1004549aa  mov     ecx, [rbp+0B8h]
0x1004549b0  mov     eax, 51EB851Fh
0x1004549b5  imul    ecx
0x1004549b7  sar     edx, 5
0x1004549ba  mov     eax, edx
0x1004549bc  shr     eax, 1Fh
0x1004549bf  add     edx, eax
0x1004549c1  cmp     edx, 1Dh
0x1004549c4  jz      short loc_1004549D2
0x1004549c6  mov     dword ptr [rbp+30h], 1
0x1004549cd  jmp     loc_100454A58
0x1004549d2  mov     dword ptr [rbp+30h], 0
0x1004549d9  lea     eax, [rcx-0B54h]
0x1004549df  cmp     eax, 5
0x1004549e2  jnz     short loc_100454A1F
0x1004549e4  mov     r8, gs:58h
0x1004549ed  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004549f4  mov     ecx, [rax]
0x1004549f6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004549fd  mov     edx, [rax]
0x1004549ff  add     rdx, [r8+rcx*8]
0x100454a03  mov     rax, [rdx+50h]
0x100454a07  movsx   r8d, word ptr [rax+48h]
0x100454a0c  lea     rdx, aResourceMonito_0; "resource monitor"
0x100454a13  mov     ecx, 439Ch; unsigned int
0x100454a18  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100454a1d  jmp     short loc_100454A58
0x100454a1f  mov     r9d, [rbp+0C4h]
0x100454a26  lea     r8, aException0xX; "Exception 0x%X"
0x100454a2d  mov     edx, 100h
0x100454a32  lea     rcx, [rbp+1B0h]
0x100454a39  call    cs:__imp_?PrintStringW@@YAHPEA_WKPEB_WZZ; PrintStringW(wchar_t *,ulong,wchar_t const *,...)
0x100454a3f  lea     r8, [rbp+1B0h]
0x100454a46  lea     rdx, aResourceMonito_0; "resource monitor"
0x100454a4d  mov     ecx, 429Dh; unsigned int
0x100454a52  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100454a57  nop
0x100454a58  lea     rcx, [rbp+118h]
0x100454a5f  call    cs:__imp_??1ExceptionBackout@@QEAA@XZ; ExceptionBackout::~ExceptionBackout(void)
0x100454a65  nop
0x100454a66  lea     rax, loc_10041F290
0x100454a6d  add     rsp, 30h
0x100454a71  pop     rbp
0x100454a72  retn
```
