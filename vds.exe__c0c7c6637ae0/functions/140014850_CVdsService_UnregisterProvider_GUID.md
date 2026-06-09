# CVdsService::UnregisterProvider(_GUID)

- ea: `0x140014850`
- end: `0x140014a44`
- name: `?UnregisterProvider@CVdsService@@UEAAJU_GUID@@@Z`
- size: `500`
- prototype: `int(CVdsService *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1400069e8`
- `0x140013298`
- `0x140014850`
- `0x140052e46`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400149d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400149f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140014a15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400149d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400149f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140014a15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400148ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400148ba`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400148d8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400148d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014987`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014987`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1400149a1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1400149a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140014948`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140014948`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140014889`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140014889`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400149e3`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140014a04`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140014a21`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400149e3`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140014a04`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140014a21`
- `vdsutil!VdsTraceW` at `0x1400149bd`
- `vdsutil!VdsTraceW` at `0x1400149bd`

## string_xrefs

- `0x140014878`: `CVdsService::UnregisterProvider()`
- `0x1400149b4`: `CVdsService::UnregisterProvider: Failed to delete %s key(%lX)`
- `0x14001490e`: `System\CurrentControlSet\Services\vds`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsService::UnregisterProvider(CVdsService *this, struct _GUID *a2)
{
  unsigned int v3; // edi
  int v4; // ebx
  unsigned int i; // esi
  LSTATUS v6; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[24]; // [rsp+38h] [rbp-C8h] BYREF
  OLECHAR sz[48]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[108]; // [rsp+B0h] [rbp-50h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v9, 0x5Eu, "CVdsService::UnregisterProvider()");
  if ( !memcmp_0(a2, &GUID_NULL, 0x10u) )
  {
    v3 = -2147211929;
LABEL_17:
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v9);
    return v3;
  }
  else
  {
    EnterCriticalSection(&g_GlobalCriticalSection);
    hKey = 0;
    v4 = 0;
    StringFromGUID2(a2, sz, 45);
    v3 = 1;
    for ( i = 1; i < 4; ++i )
    {
      StringCchPrintfW(SubKey, 0x64u, L"%s\\%s\\%s", g_wszVdsKey, &(&g_wszVdsProviderKeys)[25 * i], sz);
      v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &hKey);
      v4 = v6;
      if ( !v6 )
      {
        RegCloseKey(hKey);
        hKey = 0;
        goto LABEL_10;
      }
      if ( v6 != 2 )
      {
        VdsLogError(0xC2000001, 0, 0, v6, 0x200002Du, 0, hKey);
        goto LABEL_12;
      }
    }
    if ( v4 )
    {
      LeaveCriticalSection(&g_GlobalCriticalSection);
      goto LABEL_17;
    }
LABEL_10:
    v4 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, SubKey);
    if ( !v4 )
    {
      LeaveCriticalSection(&g_GlobalCriticalSection);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v9);
      return 0;
    }
    VdsTraceW(0, L"CVdsService::UnregisterProvider: Failed to delete %s key(%lX)", SubKey, 0);
LABEL_12:
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    LeaveCriticalSection(&g_GlobalCriticalSection);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v9);
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x140014850  push    rbp
0x140014852  push    rbx
0x140014853  push    rsi
0x140014854  push    rdi
0x140014855  lea     rbp, [rsp-98h]
0x14001485d  sub     rsp, 198h
0x140014864  mov     rax, cs:__security_cookie
0x14001486b  xor     rax, rsp
0x14001486e  mov     [rbp+0B0h+var_28], rax
0x140014875  mov     rdi, rdx
0x140014878  lea     r8, aCvdsserviceUnr_1; "CVdsService::UnregisterProvider()"
0x14001487f  mov     edx, 5Eh ; '^'
0x140014884  lea     rcx, [rsp+1B0h+var_178]
0x140014889  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14001488f  nop
0x140014890  mov     r8d, 10h; Size
0x140014896  lea     rdx, GUID_NULL; Buf2
0x14001489d  mov     rcx, rdi; Buf1
0x1400148a0  call    memcmp_0
0x1400148a5  test    eax, eax
0x1400148a7  jnz     short loc_1400148B3
0x1400148a9  mov     edi, 80042567h
0x1400148ae  jmp     loc_1400149FF
0x1400148b3  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400148ba  call    cs:__imp_EnterCriticalSection
0x1400148c0  nop
0x1400148c1  mov     [rsp+1B0h+hKey], 0
0x1400148ca  xor     ebx, ebx
0x1400148cc  lea     r8d, [rbx+2Dh]; cchMax
0x1400148d0  lea     rdx, [rsp+1B0h+sz]; lpsz
0x1400148d5  mov     rcx, rdi; rguid
0x1400148d8  call    cs:__imp_StringFromGUID2
0x1400148de  lea     edi, [rbx+1]
0x1400148e1  mov     esi, edi
0x1400148e3  cmp     esi, 4
0x1400148e6  jnb     loc_1400149ED
0x1400148ec  mov     eax, esi
0x1400148ee  imul    rcx, rax, 0C8h
0x1400148f5  lea     rax, ?g_wszVdsProviderKeys@@3PAY0GE@GA; "Uknown"
0x1400148fc  add     rcx, rax
0x1400148ff  lea     rax, [rsp+1B0h+sz]
0x140014904  mov     [rsp+1B0h+var_188], rax
0x140014909  mov     [rsp+1B0h+phkResult], rcx
0x14001490e  lea     r9, ?g_wszVdsKey@@3PAGA; "System\\CurrentControlSet\\Services\\vd"...
0x140014915  lea     r8, aSSS; "%s\\%s\\%s"
0x14001491c  mov     edx, 64h ; 'd'; unsigned __int64
0x140014921  lea     rcx, [rbp+0B0h+SubKey]; unsigned __int16 *
0x140014925  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001492a  lea     rax, [rsp+1B0h+hKey]
0x14001492f  mov     [rsp+1B0h+phkResult], rax; phkResult
0x140014934  mov     r9d, 0F003Fh; samDesired
0x14001493a  xor     r8d, r8d; ulOptions
0x14001493d  lea     rdx, [rbp+0B0h+SubKey]; lpSubKey
0x140014941  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140014948  call    cs:__imp_RegOpenKeyExW
0x14001494e  mov     ebx, eax
0x140014950  test    eax, eax
0x140014952  jz      short loc_140014982
0x140014954  cmp     eax, 2
0x140014957  jnz     short loc_14001495D
0x140014959  add     esi, edi
0x14001495b  jmp     short loc_1400148E3
0x14001495d  mov     [rsp+1B0h+var_188], 0; unsigned __int16 *
0x140014966  mov     dword ptr [rsp+1B0h+phkResult], 200002Dh; unsigned int
0x14001496e  mov     r9d, ebx; unsigned int
0x140014971  xor     r8d, r8d; void *
0x140014974  xor     edx, edx; unsigned int
0x140014976  mov     ecx, 0C2000001h; unsigned int
0x14001497b  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140014980  jmp     short loc_1400149C3
0x140014982  mov     rcx, [rsp+1B0h+hKey]; hKey
0x140014987  call    cs:__imp_RegCloseKey
0x14001498d  mov     [rsp+1B0h+hKey], 0
0x140014996  lea     rdx, [rbp+0B0h+SubKey]; lpSubKey
0x14001499a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400149a1  call    cs:__imp_RegDeleteTreeW
0x1400149a7  mov     ebx, eax
0x1400149a9  test    eax, eax
0x1400149ab  jz      short loc_140014A0E
0x1400149ad  xor     r9d, r9d
0x1400149b0  lea     r8, [rbp+0B0h+SubKey]
0x1400149b4  lea     rdx, aCvdsserviceUnr; "CVdsService::UnregisterProvider: Failed"...
0x1400149bb  xor     ecx, ecx
0x1400149bd  call    cs:__imp_VdsTraceW
0x1400149c3  test    ebx, ebx
0x1400149c5  jle     short loc_1400149D0
0x1400149c7  movzx   ebx, bx
0x1400149ca  or      ebx, 80070000h
0x1400149d0  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400149d7  call    cs:__imp_LeaveCriticalSection
0x1400149dd  nop
0x1400149de  lea     rcx, [rsp+1B0h+var_178]
0x1400149e3  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400149e9  mov     eax, ebx
0x1400149eb  jmp     short loc_140014A29
0x1400149ed  test    ebx, ebx
0x1400149ef  jz      short loc_140014996
0x1400149f1  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400149f8  call    cs:__imp_LeaveCriticalSection
0x1400149fe  nop
0x1400149ff  lea     rcx, [rsp+1B0h+var_178]
0x140014a04  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140014a0a  mov     eax, edi
0x140014a0c  jmp     short loc_140014A29
0x140014a0e  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140014a15  call    cs:__imp_LeaveCriticalSection
0x140014a1b  nop
0x140014a1c  lea     rcx, [rsp+1B0h+var_178]
0x140014a21  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140014a27  xor     eax, eax
0x140014a29  mov     rcx, [rbp+0B0h+var_28]
0x140014a30  xor     rcx, rsp; StackCookie
0x140014a33  call    __security_check_cookie
0x140014a38  add     rsp, 198h
0x140014a3f  pop     rdi
0x140014a40  pop     rsi
0x140014a41  pop     rbx
0x140014a42  pop     rbp
0x140014a43  retn
```
