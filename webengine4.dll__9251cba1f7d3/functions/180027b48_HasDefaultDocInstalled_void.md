# HasDefaultDocInstalled(void)

- ea: `0x180027b48`
- end: `0x180027cf9`
- name: `?HasDefaultDocInstalled@@YAHXZ`
- size: `433`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180028744`

## callees

- `0x18000b190`
- `0x18000b19c`
- `0x18000b3c4`
- `0x18000c534`
- `0x18000c598`
- `0x18000d158`
- `0x180027b48`
- `0x180027e90`
- `0x18004f024`
- `0x18004f048`
- `0x18004f0b8`
- `0x18004f1c4`
- `0x180064e08`
- `0x180064e68`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180027c8c`
- `ADVAPI32!RegCloseKey` at `0x180027c8c`
- `ADVAPI32!RegOpenKeyExW` at `0x180027b98`
- `ADVAPI32!RegOpenKeyExW` at `0x180027b98`
- `ADVAPI32!RegQueryValueExW` at `0x180027bd0`
- `ADVAPI32!RegQueryValueExW` at `0x180027bd0`

## string_xrefs

- `0x180027bb3`: `DefaultDocInstalled`

## pseudocode

```c
_BOOL8 HasDefaultDocInstalled(void)
{
  BOOL v0; // ebx
  LSTATUS v1; // eax
  int v2; // edi
  __int64 v3; // rsi
  const unsigned __int16 *Version; // rax
  _DWORD v6[4]; // [rsp+30h] [rbp-99h] BYREF
  _BYTE v7[32]; // [rsp+40h] [rbp-89h] BYREF
  _BYTE v8[192]; // [rsp+60h] [rbp-69h] BYREF
  DWORD cbData; // [rsp+130h] [rbp+67h] BYREF
  int Data; // [rsp+138h] [rbp+6Fh] BYREF
  HKEY hKey; // [rsp+140h] [rbp+77h] BYREF

  CASPNET_VER_LIST::CASPNET_VER_LIST((CASPNET_VER_LIST *)v6);
  CRegInfo::CRegInfo((CRegInfo *)v8);
  hKey = 0;
  v0 = 1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\ASP.NET", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    v1 = RegQueryValueExW(hKey, L"DefaultDocInstalled", 0, 0, (LPBYTE)&Data, &cbData);
    if ( v1 )
    {
      if ( (v1 == 1168 || v1 == 2) && !CRegInfo::GetVerInfoList((CRegInfo *)v8, 0, (struct CASPNET_VER_LIST *)v6) )
      {
        v2 = 0;
        if ( (v6[0] & 0xFFFFFFFC) != 0 )
        {
          v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
          while ( 1 )
          {
            ASPNETVER::ASPNETVER((ASPNETVER *)v7);
            if ( dword_1800922FC > *(_DWORD *)(v3 + 4) )
            {
              Init_thread_header(&dword_1800922FC);
              if ( dword_1800922FC == -1 )
              {
                ASPNETVER::ASPNETVER((ASPNETVER *)qword_1800922E8, L"1.2.0.0");
                Init_thread_footer(&dword_1800922FC);
              }
            }
            Version = CASPNET_VER_LIST::GetVersion((CASPNET_VER_LIST *)v6, v2);
            ASPNETVER::Init((ASPNETVER *)v7, Version);
            if ( (unsigned int)ASPNETVER::operator<(v7, qword_1800922E8) )
              break;
            if ( ++v2 >= v6[0] >> 2 )
              goto LABEL_12;
          }
          RegDefaultDocInstalled();
        }
        else
        {
LABEL_12:
          v0 = 0;
        }
      }
    }
    else
    {
      v0 = Data != 0;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  CRegInfo::~CRegInfo((CRegInfo *)v8);
  CASPNET_VER_LIST::~CASPNET_VER_LIST((CASPNET_VER_LIST *)v6);
  return v0;
}

```

## disassembly

```asm
0x180027b48  push    rbp
0x180027b4a  push    rbx
0x180027b4b  push    rsi
0x180027b4c  push    rdi
0x180027b4d  push    r14
0x180027b4f  lea     rbp, [rsp-37h]
0x180027b54  sub     rsp, 100h
0x180027b5b  lea     rcx, [rsp+120h+var_F0]; this
0x180027b60  call    ??0CASPNET_VER_LIST@@QEAA@XZ; CASPNET_VER_LIST::CASPNET_VER_LIST(void)
0x180027b65  lea     rcx, [rbp+57h+var_C0]; this
0x180027b69  call    ??0CRegInfo@@QEAA@XZ; CRegInfo::CRegInfo(void)
0x180027b6e  and     [rbp+57h+hKey], 0
0x180027b73  lea     rax, [rbp+57h+hKey]
0x180027b77  mov     r9d, 20019h; samDesired
0x180027b7d  mov     [rsp+120h+phkResult], rax; phkResult
0x180027b82  xor     r8d, r8d; ulOptions
0x180027b85  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\ASP.NET"
0x180027b8c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027b93  mov     ebx, 1
0x180027b98  call    cs:__imp_RegOpenKeyExW
0x180027b9e  test    eax, eax
0x180027ba0  jnz     loc_180027C83
0x180027ba6  mov     rcx, [rbp+57h+hKey]; hKey
0x180027baa  lea     rax, [rbp+57h+cbData]
0x180027bae  mov     [rsp+120h+lpcbData], rax; lpcbData
0x180027bb3  lea     rdx, ValueName; "DefaultDocInstalled"
0x180027bba  lea     rax, [rbp+57h+Data]
0x180027bbe  mov     [rbp+57h+cbData], 4
0x180027bc5  xor     r9d, r9d; lpType
0x180027bc8  mov     [rsp+120h+phkResult], rax; lpData
0x180027bcd  xor     r8d, r8d; lpReserved
0x180027bd0  call    cs:__imp_RegQueryValueExW
0x180027bd6  test    eax, eax
0x180027bd8  jnz     short loc_180027BE7
0x180027bda  xor     ebx, ebx
0x180027bdc  cmp     [rbp+57h+Data], ebx
0x180027bdf  setnz   bl
0x180027be2  jmp     loc_180027C83
0x180027be7  cmp     eax, 490h
0x180027bec  jz      short loc_180027BF7
0x180027bee  cmp     eax, 2
0x180027bf1  jnz     loc_180027C83
0x180027bf7  lea     r8, [rsp+120h+var_F0]; struct CASPNET_VER_LIST *
0x180027bfc  xor     edx, edx; struct ASPNETVER *
0x180027bfe  lea     rcx, [rbp+57h+var_C0]; this
0x180027c02  call    ?GetVerInfoList@CRegInfo@@QEAAJPEAVASPNETVER@@PEAVCASPNET_VER_LIST@@@Z; CRegInfo::GetVerInfoList(ASPNETVER *,CASPNET_VER_LIST *)
0x180027c07  test    eax, eax
0x180027c09  jnz     short loc_180027C83
0x180027c0b  xor     edi, edi
0x180027c0d  test    [rsp+120h+var_F0], 0FFFFFFFCh
0x180027c15  jbe     short loc_180027C81
0x180027c17  mov     ecx, cs:_tls_index
0x180027c1d  mov     rax, gs:58h
0x180027c26  mov     r14d, 4
0x180027c2c  mov     rsi, [rax+rcx*8]
0x180027c30  lea     rcx, [rsp+120h+var_E0]; this
0x180027c35  call    ??0ASPNETVER@@QEAA@XZ; ASPNETVER::ASPNETVER(void)
0x180027c3a  mov     eax, [rsi+r14]
0x180027c3e  cmp     cs:dword_1800922FC, eax
0x180027c44  jg      short loc_180027CBC
0x180027c46  mov     edx, edi; int
0x180027c48  lea     rcx, [rsp+120h+var_F0]; this
0x180027c4d  call    ?GetVersion@CASPNET_VER_LIST@@QEAAPEAGH@Z; CASPNET_VER_LIST::GetVersion(int)
0x180027c52  mov     rdx, rax; unsigned __int16 *
0x180027c55  lea     rcx, [rsp+120h+var_E0]; this
0x180027c5a  call    ?Init@ASPNETVER@@QEAAHPEBG@Z; ASPNETVER::Init(ushort const *)
0x180027c5f  lea     rdx, qword_1800922E8
0x180027c66  lea     rcx, [rsp+120h+var_E0]
0x180027c6b  call    ??MASPNETVER@@QEAAHAEAV0@@Z; ASPNETVER::operator<(ASPNETVER &)
0x180027c70  test    eax, eax
0x180027c72  jnz     short loc_180027CB5
0x180027c74  mov     eax, [rsp+120h+var_F0]
0x180027c78  add     edi, ebx
0x180027c7a  shr     eax, 2
0x180027c7d  cmp     edi, eax
0x180027c7f  jl      short loc_180027C30
0x180027c81  xor     ebx, ebx
0x180027c83  mov     rcx, [rbp+57h+hKey]; hKey
0x180027c87  test    rcx, rcx
0x180027c8a  jz      short loc_180027C92
0x180027c8c  call    cs:__imp_RegCloseKey
0x180027c92  lea     rcx, [rbp+57h+var_C0]; this
0x180027c96  call    ??1CRegInfo@@QEAA@XZ; CRegInfo::~CRegInfo(void)
0x180027c9b  lea     rcx, [rsp+120h+var_F0]; this
0x180027ca0  call    ??1CASPNET_VER_LIST@@QEAA@XZ; CASPNET_VER_LIST::~CASPNET_VER_LIST(void)
0x180027ca5  mov     eax, ebx
0x180027ca7  add     rsp, 100h
0x180027cae  pop     r14
0x180027cb0  pop     rdi
0x180027cb1  pop     rsi
0x180027cb2  pop     rbx
0x180027cb3  pop     rbp
0x180027cb4  retn
0x180027cb5  call    ?RegDefaultDocInstalled@@YAJXZ; RegDefaultDocInstalled(void)
0x180027cba  jmp     short loc_180027C83
0x180027cbc  lea     rcx, dword_1800922FC
0x180027cc3  call    _Init_thread_header
0x180027cc8  cmp     cs:dword_1800922FC, 0FFFFFFFFh
0x180027ccf  jnz     loc_180027C46
0x180027cd5  lea     rdx, a1200; "1.2.0.0"
0x180027cdc  lea     rcx, qword_1800922E8; this
0x180027ce3  call    ??0ASPNETVER@@QEAA@PEBG@Z; ASPNETVER::ASPNETVER(ushort const *)
0x180027ce8  lea     rcx, dword_1800922FC
0x180027cef  call    _Init_thread_footer
0x180027cf4  jmp     loc_180027C46
```
