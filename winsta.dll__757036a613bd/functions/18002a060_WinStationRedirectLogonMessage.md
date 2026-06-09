# WinStationRedirectLogonMessage

- ea: `0x18002a060`
- end: `0x18002a157`
- name: `WinStationRedirectLogonMessage`
- size: `247`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005c30`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x18002a060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0ac`
- `RPCRT4!NdrClientCall3` at `0x18002a119`
- `RPCRT4!NdrClientCall3` at `0x18002a119`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002a07f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002a07f`

## string_xrefs

- `0x18002a0cf`: `Failed to open binding failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall WinStationRedirectLogonMessage(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  signed int Pointer; // ebx
  signed int LastError; // eax
  void *v10; // rax
  int v12; // [rsp+30h] [rbp-58h]
  unsigned __int16 v13[28]; // [rsp+50h] [rbp-38h] BYREF

  Pointer = 0;
  if ( GetSystemMetrics(4096) )
  {
    CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v13, 0, 1);
    if ( CSmartPublicBinding::operator void *(v13) )
      goto LABEL_7;
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
    if ( Pointer >= 0 )
    {
LABEL_7:
      v10 = CSmartPublicBinding::operator void *(v13);
      v12 = a3;
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032170, 6u, 0, v10, a1, a2, v12, a4).Pointer;
    }
    else
    {
      _DbgPrintMessage(8, "Failed to open binding failed: 0x%x in %s", Pointer, "WinStationRedirectLogonMessage");
    }
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v13);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18002a060  push    rbx
0x18002a062  push    rsi
0x18002a063  push    rdi
0x18002a064  push    r14
0x18002a066  push    r15
0x18002a068  sub     rsp, 60h
0x18002a06c  mov     rdi, r9
0x18002a06f  mov     esi, r8d
0x18002a072  mov     r14, rdx
0x18002a075  mov     r15, rcx
0x18002a078  xor     ebx, ebx
0x18002a07a  mov     ecx, 1000h; nIndex
0x18002a07f  call    cs:__imp_GetSystemMetrics
0x18002a085  test    eax, eax
0x18002a087  jz      loc_18002A149
0x18002a08d  xor     edx, edx; void *
0x18002a08f  lea     r8d, [rbx+1]; int
0x18002a093  lea     rcx, [rsp+88h+var_38]; this
0x18002a098  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002a09d  lea     rcx, [rsp+88h+var_38]; unsigned __int16 *
0x18002a0a2  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002a0a7  test    rax, rax
0x18002a0aa  jnz     short loc_18002A0E2
0x18002a0ac  call    cs:__imp_GetLastError
0x18002a0b2  mov     ebx, eax
0x18002a0b4  test    eax, eax
0x18002a0b6  jle     short loc_18002A0C1
0x18002a0b8  movzx   ebx, ax
0x18002a0bb  or      ebx, 80070000h
0x18002a0c1  test    ebx, ebx
0x18002a0c3  jns     short loc_18002A0E2
0x18002a0c5  lea     r9, aWinstationredi_5; "WinStationRedirectLogonMessage"
0x18002a0cc  mov     r8d, ebx
0x18002a0cf  lea     rdx, aFailedToOpenBi; "Failed to open binding failed: 0x%x in "...
0x18002a0d6  mov     ecx, 8; int
0x18002a0db  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a0e0  jmp     short loc_18002A13F
0x18002a0e2  lea     rcx, [rsp+88h+var_38]; unsigned __int16 *
0x18002a0e7  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002a0ec  mov     [rsp+88h+var_40], 0
0x18002a0f5  mov     [rsp+88h+var_50], rdi
0x18002a0fa  mov     [rsp+88h+var_58], esi
0x18002a0fe  mov     [rsp+88h+var_60], r14
0x18002a103  mov     [rsp+88h+var_68], r15
0x18002a108  mov     r9, rax
0x18002a10b  xor     r8d, r8d; pReturnValue
0x18002a10e  lea     edx, [r8+6]; nProcNum
0x18002a112  lea     rcx, stru_180032170; pProxyInfo
0x18002a119  call    cs:__imp_NdrClientCall3
0x18002a11f  mov     rbx, rax
0x18002a122  mov     [rsp+88h+var_40], rax
0x18002a127  mov     [rsp+88h+var_48], eax
0x18002a12b  jmp     short loc_18002A13F
0x18002a12d  test    eax, eax
0x18002a12f  jle     short loc_18002A139
0x18002a131  movzx   eax, ax
0x18002a134  or      eax, 80070000h
0x18002a139  mov     ebx, eax
0x18002a13b  mov     [rsp+88h+var_48], eax
0x18002a13f  lea     rcx, [rsp+88h+var_38]; this
0x18002a144  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002a149  mov     eax, ebx
0x18002a14b  add     rsp, 60h
0x18002a14f  pop     r15
0x18002a151  pop     r14
0x18002a153  pop     rdi
0x18002a154  pop     rsi
0x18002a155  pop     rbx
0x18002a156  retn
0x180030873  push    rbp
0x180030875  sub     rsp, 40h
0x180030879  mov     rbp, rdx
0x18003087c  mov     rcx, [rcx]
0x18003087f  mov     ecx, [rcx]; ExceptionCode
0x180030881  call    cs:__imp_I_RpcExceptionFilter
0x180030887  nop
0x180030888  add     rsp, 40h
0x18003088c  pop     rbp
0x18003088d  retn
```
