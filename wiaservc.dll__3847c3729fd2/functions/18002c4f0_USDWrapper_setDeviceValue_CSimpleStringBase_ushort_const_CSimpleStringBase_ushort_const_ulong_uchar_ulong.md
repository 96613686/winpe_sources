# USDWrapper::setDeviceValue(CSimpleStringBase<ushort> const &,CSimpleStringBase<ushort> const &,ulong,uchar *,ulong)

- ea: `0x18002c4f0`
- end: `0x18002c787`
- name: `?setDeviceValue@USDWrapper@@UEAAJAEBV?$CSimpleStringBase@G@@0KPEAEK@Z`
- size: `663`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x180011638`
- `0x1800119c8`
- `0x180011ad0`
- `0x18002c4f0`
- `0x18002c868`
- `0x18002c8b0`
- `0x180033cc0`
- `0x180078010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18002c6d7`
- `ADVAPI32!RegCloseKey` at `0x18002c6d7`
- `ADVAPI32!RegSetValueExW` at `0x18002c593`
- `ADVAPI32!RegSetValueExW` at `0x18002c593`

## string_xrefs

- `0x18002c5aa`: `Received error 0x%08X trying to write value %ws for device %ws`
- `0x18002c5f2`: `Received error 0x%08X trying to write value %ws for device %ws`

## pseudocode

```c
__int64 __fastcall USDWrapper::setDeviceValue(_QWORD *a1, __int64 a2, __int64 a3, DWORD a4, BYTE *lpData, DWORD cbData)
{
  HKEY v10; // r15
  unsigned int v11; // edi
  char *v12; // rbx
  void *v13; // rdx
  void **v14; // rax
  void *v15; // rdx
  __int64 v16; // rcx
  char *v17; // rbx
  void *v18; // rdx
  void **v19; // rax
  void *v20; // rdx
  __int64 v21; // rcx
  char *v22; // rbx
  void *v23; // rdx
  void **v24; // rax
  void *v25; // rdx
  __int64 v26; // rcx
  _BYTE v28[312]; // [rsp+30h] [rbp-1A8h] BYREF
  HKEY hKey; // [rsp+168h] [rbp-70h]

  v10 = (HKEY)(*(__int64 (__fastcall **)(_QWORD *))(*a1 + 480LL))(a1);
  if ( v10 )
  {
    CSimpleReg::CSimpleReg((CSimpleReg *)v28, 131078);
    if ( CSimpleReg::OK((CSimpleReg *)v28) )
    {
      v11 = RegSetValueExW(hKey, *(LPCWSTR *)(a3 + 264), 0, a4, lpData, cbData);
      if ( v11 )
      {
        v12 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                        4,
                        0,
                        "Received error 0x%08X trying to write value %ws for device %ws",
                        v11,
                        *(_QWORD *)(a3 + 264),
                        a1[301]);
        WriteDbgTraceInfoWI("USDWrapper::setDeviceValue", v12);
        WiaTrcLib::Free((WiaTrcLib *)v12, v13);
        v14 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                         4,
                         0,
                         "Received error 0x%08X trying to write value %ws for device %ws",
                         v11,
                         *(_QWORD *)(a3 + 264),
                         a1[301]);
        WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"USDWrapper::setDeviceValue", 4, v14);
        if ( (int)v11 > 0 )
          v11 = (unsigned __int16)v11 | 0x80070000;
      }
    }
    else
    {
      v17 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      4,
                      0,
                      "We could not set the value subkey (%ws) for  device (%ws) - key is not valid",
                      *(_QWORD *)(a3 + 264),
                      a1[301],
                      *(_QWORD *)(a2 + 264));
      WriteDbgTraceInfoWI("USDWrapper::setDeviceValue", v17);
      WiaTrcLib::Free((WiaTrcLib *)v17, v18);
      v19 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       4,
                       0,
                       "We could not set the value subkey (%ws) for  device (%ws) - key is not valid",
                       *(_QWORD *)(a3 + 264),
                       a1[301],
                       *(_QWORD *)(a2 + 264));
      WiaTrace_ProcessTrace_Ex(v21, v20, (void *)"USDWrapper::setDeviceValue", 4, v19);
      v11 = -2147467263;
    }
    RegCloseKey(v10);
    CSimpleReg::~CSimpleReg((CSimpleReg *)v28);
  }
  else
  {
    v22 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                    4,
                    0,
                    "We could not get the device value (%ws) for  device (%ws) - the operation does not appear to be supp"
                    "orted by the wrapper",
                    *(_QWORD *)(a3 + 264),
                    a1[301]);
    WriteDbgTraceInfoWI("USDWrapper::setDeviceValue", v22);
    WiaTrcLib::Free((WiaTrcLib *)v22, v23);
    v24 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                     4,
                     0,
                     "We could not get the device value (%ws) for  device (%ws) - the operation does not appear to be sup"
                     "ported by the wrapper",
                     *(_QWORD *)(a3 + 264),
                     a1[301]);
    WiaTrace_ProcessTrace_Ex(v26, v25, (void *)"USDWrapper::setDeviceValue", 4, v24);
    return (unsigned int)-2147467263;
  }
  return v11;
}

```

## disassembly

```asm
0x18002c4f0  push    rbx
0x18002c4f2  push    rbp
0x18002c4f3  push    rsi
0x18002c4f4  push    rdi
0x18002c4f5  push    r14
0x18002c4f7  push    r15
0x18002c4f9  sub     rsp, 1A8h
0x18002c500  mov     rax, cs:__security_cookie
0x18002c507  xor     rax, rsp
0x18002c50a  mov     [rsp+1D8h+var_48], rax
0x18002c512  mov     rax, [rcx]
0x18002c515  mov     ebx, r9d
0x18002c518  mov     rbp, [rsp+1D8h+arg_20]
0x18002c520  mov     r14, r8
0x18002c523  mov     rdi, rdx
0x18002c526  mov     rsi, rcx
0x18002c529  mov     rax, [rax+1E0h]
0x18002c530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c535  mov     r15, rax
0x18002c538  test    rax, rax
0x18002c53b  jz      loc_18002C6E9
0x18002c541  mov     r9b, 1
0x18002c544  mov     dword ptr [rsp+1D8h+lpData], 20006h; int
0x18002c54c  mov     r8, rdi
0x18002c54f  lea     rcx, [rsp+1D8h+var_1A8]; this
0x18002c554  mov     rdx, rax
0x18002c557  call    ??0CSimpleReg@@QEAA@PEAUHKEY__@@AEBV?$CSimpleStringBase@G@@_NKPEAU_SECURITY_ATTRIBUTES@@@Z; CSimpleReg::CSimpleReg(HKEY__ *,CSimpleStringBase<ushort> const &,bool,ulong,_SECURITY_ATTRIBUTES *)
0x18002c55c  lea     rcx, [rsp+1D8h+var_1A8]; this
0x18002c561  call    ?OK@CSimpleReg@@QEBA_NXZ; CSimpleReg::OK(void)
0x18002c566  test    al, al
0x18002c568  jz      loc_18002C640
0x18002c56e  mov     eax, [rsp+1D8h+arg_28]
0x18002c575  mov     r9d, ebx; dwType
0x18002c578  mov     rdx, [r14+108h]; lpValueName
0x18002c57f  xor     r8d, r8d; Reserved
0x18002c582  mov     rcx, [rsp+1D8h+hKey]; hKey
0x18002c58a  mov     [rsp+1D8h+cbData], eax; cbData
0x18002c58e  mov     [rsp+1D8h+lpData], rbp; lpData
0x18002c593  call    cs:__imp_RegSetValueExW
0x18002c599  mov     edi, eax
0x18002c59b  test    eax, eax
0x18002c59d  jz      loc_18002C6D4
0x18002c5a3  mov     rax, [rsi+968h]
0x18002c5aa  lea     r8, aReceivedError0_2; "Received error 0x%08X trying to write v"...
0x18002c5b1  mov     qword ptr [rsp+1D8h+cbData], rax
0x18002c5b6  xor     edx, edx
0x18002c5b8  mov     rax, [r14+108h]
0x18002c5bf  mov     r9d, edi
0x18002c5c2  mov     [rsp+1D8h+lpData], rax
0x18002c5c7  lea     ebp, [rdx+4]
0x18002c5ca  mov     ecx, ebp
0x18002c5cc  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18002c5d1  mov     rdx, rax; char *
0x18002c5d4  lea     rcx, aUsdwrapperSetd; "USDWrapper::setDeviceValue"
0x18002c5db  mov     rbx, rax
0x18002c5de  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18002c5e3  mov     rcx, rbx; this
0x18002c5e6  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002c5eb  mov     rax, [rsi+968h]
0x18002c5f2  lea     r8, aReceivedError0_2; "Received error 0x%08X trying to write v"...
0x18002c5f9  mov     qword ptr [rsp+1D8h+cbData], rax
0x18002c5fe  mov     r9d, edi
0x18002c601  mov     rax, [r14+108h]
0x18002c608  xor     edx, edx
0x18002c60a  mov     ecx, ebp
0x18002c60c  mov     [rsp+1D8h+lpData], rax
0x18002c611  call    WiaTrace_TraceWithSubCompTraceLevel
0x18002c616  mov     r9d, ebp; int
0x18002c619  mov     [rsp+1D8h+lpData], rax; lpMem
0x18002c61e  lea     r8, aUsdwrapperSetd; "USDWrapper::setDeviceValue"
0x18002c625  call    WiaTrace_ProcessTrace_Ex
0x18002c62a  test    edi, edi
0x18002c62c  jle     loc_18002C6D4
0x18002c632  movzx   edi, di
0x18002c635  or      edi, 80070000h
0x18002c63b  jmp     loc_18002C6D4
0x18002c640  mov     rax, [rdi+108h]
0x18002c647  lea     r8, aWeCouldNotSetT; "We could not set the value subkey (%ws)"...
0x18002c64e  mov     r9, [r14+108h]
0x18002c655  xor     edx, edx
0x18002c657  mov     qword ptr [rsp+1D8h+cbData], rax
0x18002c65c  mov     rax, [rsi+968h]
0x18002c663  mov     [rsp+1D8h+lpData], rax
0x18002c668  lea     ebp, [rdx+4]
0x18002c66b  mov     ecx, ebp
0x18002c66d  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18002c672  mov     rdx, rax; char *
0x18002c675  lea     rcx, aUsdwrapperSetd; "USDWrapper::setDeviceValue"
0x18002c67c  mov     rbx, rax
0x18002c67f  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18002c684  mov     rcx, rbx; this
0x18002c687  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002c68c  mov     rax, [rdi+108h]
0x18002c693  lea     r8, aWeCouldNotSetT; "We could not set the value subkey (%ws)"...
0x18002c69a  mov     r9, [r14+108h]
0x18002c6a1  xor     edx, edx
0x18002c6a3  mov     qword ptr [rsp+1D8h+cbData], rax
0x18002c6a8  mov     ecx, ebp
0x18002c6aa  mov     rax, [rsi+968h]
0x18002c6b1  mov     [rsp+1D8h+lpData], rax
0x18002c6b6  call    WiaTrace_TraceWithSubCompTraceLevel
0x18002c6bb  mov     r9d, ebp; int
0x18002c6be  mov     [rsp+1D8h+lpData], rax; lpMem
0x18002c6c3  lea     r8, aUsdwrapperSetd; "USDWrapper::setDeviceValue"
0x18002c6ca  call    WiaTrace_ProcessTrace_Ex
0x18002c6cf  mov     edi, 80004001h
0x18002c6d4  mov     rcx, r15; hKey
0x18002c6d7  call    cs:__imp_RegCloseKey
0x18002c6dd  lea     rcx, [rsp+1D8h+var_1A8]; this
0x18002c6e2  call    ??1CSimpleReg@@UEAA@XZ; CSimpleReg::~CSimpleReg(void)
0x18002c6e7  jmp     short loc_18002C765
0x18002c6e9  mov     rax, [rsi+968h]
0x18002c6f0  lea     r8, aWeCouldNotGetT_0; "We could not get the device value (%ws)"...
0x18002c6f7  mov     r9, [r14+108h]
0x18002c6fe  xor     edx, edx
0x18002c700  mov     [rsp+1D8h+lpData], rax
0x18002c705  lea     ebp, [rdx+4]
0x18002c708  mov     ecx, ebp
0x18002c70a  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18002c70f  mov     rdx, rax; char *
0x18002c712  lea     rcx, aUsdwrapperSetd; "USDWrapper::setDeviceValue"
0x18002c719  mov     rbx, rax
0x18002c71c  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18002c721  mov     rcx, rbx; this
0x18002c724  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002c729  mov     rax, [rsi+968h]
0x18002c730  lea     r8, aWeCouldNotGetT_0; "We could not get the device value (%ws)"...
0x18002c737  mov     r9, [r14+108h]
0x18002c73e  xor     edx, edx
0x18002c740  mov     ecx, ebp
0x18002c742  mov     [rsp+1D8h+lpData], rax
0x18002c747  call    WiaTrace_TraceWithSubCompTraceLevel
0x18002c74c  mov     r9d, ebp; int
0x18002c74f  mov     [rsp+1D8h+lpData], rax; lpMem
0x18002c754  lea     r8, aUsdwrapperSetd; "USDWrapper::setDeviceValue"
0x18002c75b  call    WiaTrace_ProcessTrace_Ex
0x18002c760  mov     edi, 80004001h
0x18002c765  mov     eax, edi
0x18002c767  mov     rcx, [rsp+1D8h+var_48]
0x18002c76f  xor     rcx, rsp; StackCookie
0x18002c772  call    __security_check_cookie
0x18002c777  add     rsp, 1A8h
0x18002c77e  pop     r15
0x18002c780  pop     r14
0x18002c782  pop     rdi
0x18002c783  pop     rsi
0x18002c784  pop     rbp
0x18002c785  pop     rbx
0x18002c786  retn
```
