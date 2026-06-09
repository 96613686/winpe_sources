# CTftpServer::ReadDynamicParameters(void)

- ea: `0x1800020d8`
- end: `0x1800022cb`
- name: `?ReadDynamicParameters@CTftpServer@@AEAAKXZ`
- size: `499`
- prototype: `__int64 __fastcall(CTftpServer *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001950`
- `0x180002ad0`

## callees

- `0x1800020d8`
- `0x180003170`
- `0x18003a940`
- `0x18003b1e8`
- `0x18003b238`
- `0x18003ce78`
- `0x180060e70`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000210b`
- `ADVAPI32!RegCloseKey` at `0x1800022ad`
- `ADVAPI32!RegCloseKey` at `0x18000210b`
- `ADVAPI32!RegCloseKey` at `0x1800022ad`
- `ADVAPI32!RegOpenKeyExW` at `0x180002138`
- `ADVAPI32!RegOpenKeyExW` at `0x180002138`

## string_xrefs

- `0x18000212a`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSTFTP`
- `0x1800021cc`: `CTftpServer::ReadDynamicParameters: Maximum Negotiated Block Size was configured smaller than 512 bytes; using 512 instead`
- `0x1800021ef`: `CTftpServer::ReadDynamicParameters: Maximum Negotiated Block Size=%u Bytes`
- `0x180002208`: `CTftpServer::ReadDynamicParameters: No limit on Negotiated Block Size`
- `0x18000222e`: `EnableVariableWindowExtension`
- `0x18000227f`: `CTftpServer::ReadDynamicParameters: TFTP variable window extension is %s.`

## pseudocode

```c
__int64 __fastcall CTftpServer::ReadDynamicParameters(CTftpServer *this)
{
  unsigned int Value; // ebx
  const char *v3; // rdx
  _DWORD *v4; // rdi
  const char *v5; // rdx
  const char *v6; // rdx
  __int64 v7; // r8
  void (*v8)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v9; // r8
  CMRSWLock *v11; // [rsp+30h] [rbp-18h] BYREF
  int v12; // [rsp+38h] [rbp-10h]
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF

  hKey = 0;
  v12 = 0;
  v11 = this;
  CAutoWriterLock::Lock((CAutoWriterLock *)&v11);
  if ( hKey )
    RegCloseKey(hKey);
  Value = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSTFTP",
            0,
            0x20119u,
            &hKey);
  if ( !ElValidateWin32(Value, v3, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x2BAu) )
  {
    v4 = (_DWORD *)((char *)this + 544);
    Value = CRegKey::GetValue((CRegKey *)&hKey, L"MaximumBlockSize", 4u, (char *)this + 544, 4u);
    if ( Value == 2 )
    {
      *v4 = 0;
      Value = 0;
    }
    if ( !ElValidateWin32(Value, v5, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x2C5u) )
    {
      v7 = (unsigned int)*v4;
      v8 = g_ErrLibTraceFunctionEx;
      if ( (_DWORD)v7 )
      {
        if ( (unsigned int)v7 < 0x200 )
        {
          if ( g_ErrLibTraceFunctionEx )
          {
            g_ErrLibTraceFunctionEx(
              0x40000u,
              L"CTftpServer::ReadDynamicParameters: Maximum Negotiated Block Size was configured smaller than 512 bytes; u"
               "sing 512 instead");
            v8 = g_ErrLibTraceFunctionEx;
          }
          *v4 = 512;
          v7 = 512;
        }
        if ( v8 )
          v8(0x20000u, L"CTftpServer::ReadDynamicParameters: Maximum Negotiated Block Size=%u Bytes", v7);
      }
      else if ( g_ErrLibTraceFunctionEx )
      {
        g_ErrLibTraceFunctionEx(0x20000u, L"CTftpServer::ReadDynamicParameters: No limit on Negotiated Block Size");
      }
      if ( this == (CTftpServer *)-560LL )
        Value = 87;
      else
        Value = CRegKey::GetValueBool((CRegKey *)&hKey, L"EnableVariableWindowExtension", (int *)this + 140);
      if ( !ElValidateWin32(Value, v6, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x2E1u)
        && g_ErrLibTraceFunctionEx )
      {
        v9 = L"disabled";
        if ( *((_DWORD *)this + 140) )
          v9 = L"enabled";
        g_ErrLibTraceFunctionEx(
          0x20000u,
          L"CTftpServer::ReadDynamicParameters: TFTP variable window extension is %s.",
          v9);
      }
    }
  }
  if ( v12 == 1 )
    CMRSWLock::WriterRelease(v11);
  if ( hKey )
    RegCloseKey(hKey);
  return Value;
}

```

## disassembly

```asm
0x1800020d8  mov     rax, rsp
0x1800020db  mov     [rax+10h], rbx
0x1800020df  mov     [rax+18h], rsi
0x1800020e3  push    rdi
0x1800020e4  sub     rsp, 40h
0x1800020e8  and     qword ptr [rax+8], 0
0x1800020ed  mov     rsi, rcx
0x1800020f0  and     dword ptr [rax-10h], 0
0x1800020f4  mov     [rax-18h], rcx
0x1800020f8  lea     rcx, [rax-18h]; this
0x1800020fc  call    ?Lock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Lock(void)
0x180002101  mov     rcx, [rsp+48h+hKey]; hKey
0x180002106  test    rcx, rcx
0x180002109  jz      short loc_180002117
0x18000210b  call    cs:__imp_RegCloseKey
0x180002112  nop     dword ptr [rax+rax+00h]
0x180002117  lea     rax, [rsp+48h+hKey]
0x18000211c  mov     r9d, 20119h; samDesired
0x180002122  xor     r8d, r8d; ulOptions
0x180002125  mov     [rsp+48h+phkResult], rax; phkResult
0x18000212a  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x180002131  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002138  call    cs:__imp_RegOpenKeyExW
0x18000213f  nop     dword ptr [rax+rax+00h]
0x180002144  mov     r9d, 2BAh; unsigned int
0x18000214a  lea     r8, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\tftp"...
0x180002151  mov     ecx, eax; unsigned int
0x180002153  mov     ebx, eax
0x180002155  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000215a  test    eax, eax
0x18000215c  jnz     loc_18000228C
0x180002162  lea     r8d, [rax+4]; unsigned int
0x180002166  lea     rdi, [rsi+220h]
0x18000216d  mov     dword ptr [rsp+48h+phkResult], r8d; unsigned int
0x180002172  mov     r9, rdi; void *
0x180002175  lea     rdx, aMaximumblocksi; "MaximumBlockSize"
0x18000217c  lea     rcx, [rsp+48h+hKey]; this
0x180002181  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x180002186  mov     ebx, eax
0x180002188  cmp     eax, 2
0x18000218b  jnz     short loc_180002192
0x18000218d  and     dword ptr [rdi], 0
0x180002190  xor     ebx, ebx
0x180002192  mov     r9d, 2C5h; unsigned int
0x180002198  lea     r8, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\tftp"...
0x18000219f  mov     ecx, ebx; unsigned int
0x1800021a1  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800021a6  test    eax, eax
0x1800021a8  jnz     loc_18000228C
0x1800021ae  mov     r8d, [rdi]
0x1800021b1  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800021b8  test    r8d, r8d
0x1800021bb  jz      short loc_180002203
0x1800021bd  mov     ebx, 200h
0x1800021c2  cmp     r8d, ebx
0x1800021c5  jnb     short loc_1800021EA
0x1800021c7  test    rax, rax
0x1800021ca  jz      short loc_1800021E5
0x1800021cc  lea     rdx, aCtftpserverRea_5; "CTftpServer::ReadDynamicParameters: Max"...
0x1800021d3  mov     ecx, 40000h
0x1800021d8  call    cs:__guard_dispatch_icall_fptr
0x1800021de  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800021e5  mov     [rdi], ebx
0x1800021e7  mov     r8d, ebx
0x1800021ea  test    rax, rax
0x1800021ed  jz      short loc_18000221A
0x1800021ef  lea     rdx, aCtftpserverRea_11; "CTftpServer::ReadDynamicParameters: Max"...
0x1800021f6  mov     ecx, 20000h
0x1800021fb  call    cs:__guard_dispatch_icall_fptr
0x180002201  jmp     short loc_18000221A
0x180002203  test    rax, rax
0x180002206  jz      short loc_18000221A
0x180002208  lea     rdx, aCtftpserverRea_6; "CTftpServer::ReadDynamicParameters: No "...
0x18000220f  mov     ecx, 20000h
0x180002214  call    cs:__guard_dispatch_icall_fptr
0x18000221a  lea     rdi, [rsi+230h]
0x180002221  test    rdi, rdi
0x180002224  jnz     short loc_18000222B
0x180002226  lea     ebx, [rdi+57h]
0x180002229  jmp     short loc_180002241
0x18000222b  mov     r8, rdi; int *
0x18000222e  lea     rdx, aEnablevariable; "EnableVariableWindowExtension"
0x180002235  lea     rcx, [rsp+48h+hKey]; this
0x18000223a  call    ?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z; CRegKey::GetValueBool(ushort const *,int *)
0x18000223f  mov     ebx, eax
0x180002241  mov     r9d, 2E1h; unsigned int
0x180002247  lea     r8, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\tftp"...
0x18000224e  mov     ecx, ebx; unsigned int
0x180002250  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002255  test    eax, eax
0x180002257  jnz     short loc_18000228C
0x180002259  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180002260  test    rax, rax
0x180002263  jz      short loc_18000228C
0x180002265  cmp     dword ptr [rdi], 0
0x180002268  lea     rdx, aEnabled; "enabled"
0x18000226f  lea     r8, aDisabled; "disabled"
0x180002276  mov     ecx, 20000h
0x18000227b  cmovnz  r8, rdx
0x18000227f  lea     rdx, aCtftpserverRea_12; "CTftpServer::ReadDynamicParameters: TFT"...
0x180002286  call    cs:__guard_dispatch_icall_fptr
0x18000228c  mov     eax, [rsp+48h+var_10]
0x180002290  test    eax, eax
0x180002292  jz      short loc_1800022A3
0x180002294  cmp     eax, 1
0x180002297  jnz     short loc_1800022A3
0x180002299  mov     rcx, [rsp+48h+var_18]; this
0x18000229e  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x1800022a3  mov     rcx, [rsp+48h+hKey]; hKey
0x1800022a8  test    rcx, rcx
0x1800022ab  jz      short loc_1800022B9
0x1800022ad  call    cs:__imp_RegCloseKey
0x1800022b4  nop     dword ptr [rax+rax+00h]
0x1800022b9  mov     rsi, [rsp+48h+arg_10]
0x1800022be  mov     eax, ebx
0x1800022c0  mov     rbx, [rsp+48h+arg_8]
0x1800022c5  add     rsp, 40h
0x1800022c9  pop     rdi
0x1800022ca  retn
```
