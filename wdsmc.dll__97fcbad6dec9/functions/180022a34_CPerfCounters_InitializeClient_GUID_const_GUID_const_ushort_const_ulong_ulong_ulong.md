# CPerfCounters::InitializeClient(_GUID const &,_GUID const &,ushort const *,ulong,ulong,ulong *)

- ea: `0x180022a34`
- end: `0x180022cf0`
- name: `?InitializeClient@CPerfCounters@@QEAAKAEBU_GUID@@0PEBGKKPEAK@Z`
- size: `700`
- prototype: `unsigned int __fastcall(CPerfCounters *__hidden this, const struct _GUID *, const struct _GUID *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config, service_task`

## callers

- `0x180009400`

## callees

- `0x18001a9a8`
- `0x18002218c`
- `0x1800228e8`
- `0x18002294c`
- `0x180022a34`
- `0x180026694`
- `0x180026d46`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180022a8d`
- `KERNEL32!GetLastError` at `0x180022a8d`
- `KERNEL32!MapViewOfFile` at `0x180022aaf`
- `KERNEL32!MapViewOfFile` at `0x180022aaf`
- `KERNEL32!OpenFileMappingW` at `0x180022a7f`
- `KERNEL32!OpenFileMappingW` at `0x180022a7f`
- `ADVAPI32!RegCloseKey` at `0x180022ac8`
- `ADVAPI32!RegCloseKey` at `0x180022cd3`
- `ADVAPI32!RegCloseKey` at `0x180022ac8`
- `ADVAPI32!RegCloseKey` at `0x180022cd3`
- `ADVAPI32!RegOpenKeyExW` at `0x180022af5`
- `ADVAPI32!RegOpenKeyExW` at `0x180022af5`

## string_xrefs

- `0x180022ae7`: `System\CurrentControlSet\Services\WDSMC\Performance`

## pseudocode

```c
__int64 __fastcall CPerfCounters::InitializeClient(
        CPerfCounters *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        const unsigned __int16 *a4)
{
  unsigned int ObjectName; // edi
  HANDLE v6; // rax
  LPVOID v7; // rax
  _DWORD *v8; // r14
  _DWORD *v9; // r15
  void *v10; // rax
  void *v11; // rax
  __int64 *v12; // r10
  __int64 v13; // rdx
  unsigned int v14; // r9d
  int v15; // r8d
  int v16; // ecx
  int v17; // eax
  LPCWSTR lpName; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  lpName = 0;
  hKey = 0;
  ObjectName = CPerfCounters::CreateObjectName(this, a2, (unsigned __int16 **)&lpName);
  if ( !ObjectName )
  {
    v6 = OpenFileMappingW(4u, 0, lpName);
    *(_QWORD *)this = v6;
    if ( v6 && (v7 = MapViewOfFile(v6, 4u, 0, 0, 0x70u), (*((_QWORD *)this + 1) = v7) != 0) )
    {
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
      ObjectName = RegOpenKeyExW(
                     HKEY_LOCAL_MACHINE,
                     L"System\\CurrentControlSet\\Services\\WDSMC\\Performance",
                     0,
                     0x20119u,
                     &hKey);
      if ( !ObjectName )
      {
        v8 = (_DWORD *)((char *)this + 16);
        ObjectName = CRegKey::GetValue((CRegKey *)&hKey, L"First Counter", 4u, (char *)this + 16, 4u);
        if ( !ObjectName )
        {
          v9 = (_DWORD *)((char *)this + 20);
          ObjectName = CRegKey::GetValue((CRegKey *)&hKey, L"First Help", 4u, (char *)this + 20, 4u);
          if ( !ObjectName )
          {
            *((_DWORD *)this + 10) = 624;
            v10 = operator new[](0x270u, (const struct std::nothrow_t *)&std::nothrow);
            *((_QWORD *)this + 4) = v10;
            if ( v10
              && (memset_0(v10, 0, *((unsigned int *)this + 10)),
                  *((_DWORD *)this + 14) = 120,
                  v11 = operator new[](0x78u, (const struct std::nothrow_t *)&std::nothrow),
                  (*((_QWORD *)this + 6) = v11) != 0) )
            {
              memset_0(v11, 0, *((unsigned int *)this + 14));
              v12 = qword_180033030;
              v13 = 0;
              **((_DWORD **)this + 4) = *((_DWORD *)this + 10) + *((_DWORD *)this + 14);
              v14 = 8;
              *(_DWORD *)(*((_QWORD *)this + 4) + 4LL) = *((_DWORD *)this + 10);
              *(_DWORD *)(*((_QWORD *)this + 4) + 8LL) = 64;
              *(_DWORD *)(*((_QWORD *)this + 4) + 12LL) = *v8 + 28;
              *(_DWORD *)(*((_QWORD *)this + 4) + 20LL) = *v9 + 28;
              *(_DWORD *)(*((_QWORD *)this + 4) + 28LL) = 100;
              *(_DWORD *)(*((_QWORD *)this + 4) + 32LL) = 14;
              *(_DWORD *)(*((_QWORD *)this + 4) + 40LL) = -1;
              *(_DWORD *)(*((_QWORD *)this + 4) + 44LL) = 0;
              v15 = 0;
              do
              {
                v13 += 40;
                *(_DWORD *)(v13 + *((_QWORD *)this + 4) + 24) = 40;
                *(_DWORD *)(v13 + *((_QWORD *)this + 4) + 28) = v15 + *v8;
                v16 = v15 + *v9;
                v15 += 2;
                *(_DWORD *)(v13 + *((_QWORD *)this + 4) + 36) = v16;
                *(_DWORD *)(v13 + *((_QWORD *)this + 4) + 48) = 100;
                v17 = *(_DWORD *)v12;
                v12 = (__int64 *)((char *)v12 + 4);
                *(_DWORD *)(v13 + *((_QWORD *)this + 4) + 52) = v17;
                *(_DWORD *)(v13 + *((_QWORD *)this + 4) + 56) = 8;
                *(_DWORD *)(v13 + *((_QWORD *)this + 4) + 60) = v14;
                v14 += 8;
              }
              while ( v14 < 0x78 );
              **((_DWORD **)this + 6) = *((_DWORD *)this + 14);
              *((_DWORD *)this + 6) = 14;
              *((_DWORD *)this + 7) = 14;
            }
            else
            {
              ObjectName = 8;
            }
          }
        }
      }
    }
    else
    {
      ObjectName = GetLastError();
    }
  }
  if ( lpName )
    operator delete((void *)lpName);
  if ( ObjectName )
    CPerfCounters::Shutdown(this);
  if ( hKey )
    RegCloseKey(hKey);
  return ObjectName;
}

```

## disassembly

```asm
0x180022a34  mov     rax, rsp
0x180022a37  mov     [rax+8], rbx
0x180022a3b  mov     [rax+10h], rdi
0x180022a3f  mov     [rax+20h], r9
0x180022a43  mov     [rax+18h], r8
0x180022a47  push    r12
0x180022a49  push    r14
0x180022a4b  push    r15
0x180022a4d  sub     rsp, 30h
0x180022a51  and     qword ptr [rax+18h], 0
0x180022a56  lea     r8, [rax+18h]; unsigned __int16 **
0x180022a5a  and     qword ptr [rax+20h], 0
0x180022a5f  mov     rbx, rcx
0x180022a62  call    ?CreateObjectName@CPerfCounters@@IEAAKPEBU_GUID@@PEAPEAG@Z; CPerfCounters::CreateObjectName(_GUID const *,ushort * *)
0x180022a67  mov     edi, eax
0x180022a69  test    eax, eax
0x180022a6b  jnz     loc_180022CAB
0x180022a71  mov     r8, [rsp+48h+lpName]; lpName
0x180022a76  lea     r12d, [rax+4]
0x180022a7a  mov     ecx, r12d; dwDesiredAccess
0x180022a7d  xor     edx, edx; bInheritHandle
0x180022a7f  call    cs:__imp_OpenFileMappingW
0x180022a85  mov     [rbx], rax
0x180022a88  test    rax, rax
0x180022a8b  jnz     short loc_180022A9A
0x180022a8d  call    cs:__imp_GetLastError
0x180022a93  mov     edi, eax
0x180022a95  jmp     loc_180022CAB
0x180022a9a  xor     r9d, r9d; dwFileOffsetLow
0x180022a9d  mov     [rsp+48h+dwNumberOfBytesToMap], 70h ; 'p'; dwNumberOfBytesToMap
0x180022aa6  xor     r8d, r8d; dwFileOffsetHigh
0x180022aa9  mov     edx, r12d; dwDesiredAccess
0x180022aac  mov     rcx, rax; hFileMappingObject
0x180022aaf  call    cs:__imp_MapViewOfFile
0x180022ab5  mov     [rbx+8], rax
0x180022ab9  test    rax, rax
0x180022abc  jz      short loc_180022A8D
0x180022abe  mov     rcx, [rsp+48h+hKey]; hKey
0x180022ac3  test    rcx, rcx
0x180022ac6  jz      short loc_180022AD4
0x180022ac8  call    cs:__imp_RegCloseKey
0x180022ace  and     [rsp+48h+hKey], 0
0x180022ad4  lea     rax, [rsp+48h+hKey]
0x180022ad9  mov     r9d, 20119h; samDesired
0x180022adf  xor     r8d, r8d; ulOptions
0x180022ae2  mov     [rsp+48h+dwNumberOfBytesToMap], rax; phkResult
0x180022ae7  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\WD"...
0x180022aee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022af5  call    cs:__imp_RegOpenKeyExW
0x180022afb  mov     edi, eax
0x180022afd  test    eax, eax
0x180022aff  jnz     loc_180022CAB
0x180022b05  lea     r14, [rbx+10h]
0x180022b09  mov     dword ptr [rsp+48h+dwNumberOfBytesToMap], r12d; unsigned int
0x180022b0e  mov     r9, r14; void *
0x180022b11  lea     rdx, aFirstCounter; "First Counter"
0x180022b18  mov     r8d, r12d; unsigned int
0x180022b1b  lea     rcx, [rsp+48h+hKey]; this
0x180022b20  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x180022b25  mov     edi, eax
0x180022b27  test    eax, eax
0x180022b29  jnz     loc_180022CAB
0x180022b2f  lea     r15, [rbx+14h]
0x180022b33  mov     dword ptr [rsp+48h+dwNumberOfBytesToMap], r12d; unsigned int
0x180022b38  mov     r9, r15; void *
0x180022b3b  lea     rdx, aFirstHelp; "First Help"
0x180022b42  mov     r8d, r12d; unsigned int
0x180022b45  lea     rcx, [rsp+48h+hKey]; this
0x180022b4a  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x180022b4f  mov     edi, eax
0x180022b51  test    eax, eax
0x180022b53  jnz     loc_180022CAB
0x180022b59  mov     ecx, 270h; unsigned __int64
0x180022b5e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180022b65  mov     [rbx+28h], ecx
0x180022b68  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180022b6d  mov     [rbx+20h], rax
0x180022b71  test    rax, rax
0x180022b74  jnz     short loc_180022B80
0x180022b76  mov     edi, 8
0x180022b7b  jmp     loc_180022CAB
0x180022b80  mov     r8d, [rbx+28h]; Size
0x180022b84  xor     edx, edx; Val
0x180022b86  mov     rcx, rax; void *
0x180022b89  call    memset_0
0x180022b8e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180022b95  mov     dword ptr [rbx+38h], 78h ; 'x'
0x180022b9c  mov     ecx, 78h ; 'x'; unsigned __int64
0x180022ba1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180022ba6  mov     [rbx+30h], rax
0x180022baa  test    rax, rax
0x180022bad  jz      short loc_180022B76
0x180022baf  mov     r8d, [rbx+38h]; Size
0x180022bb3  xor     edx, edx; Val
0x180022bb5  mov     rcx, rax; void *
0x180022bb8  call    memset_0
0x180022bbd  mov     rax, [rbx+20h]
0x180022bc1  lea     r10, qword_180033030
0x180022bc8  mov     ecx, [rbx+38h]
0x180022bcb  mov     r11d, 0Eh
0x180022bd1  add     ecx, [rbx+28h]
0x180022bd4  xor     edx, edx
0x180022bd6  mov     [rax], ecx
0x180022bd8  mov     rcx, [rbx+20h]
0x180022bdc  lea     r9d, [r11-6]
0x180022be0  mov     eax, [rbx+28h]
0x180022be3  mov     [rcx+4], eax
0x180022be6  mov     rax, [rbx+20h]
0x180022bea  mov     dword ptr [rax+8], 40h ; '@'
0x180022bf1  mov     rax, [rbx+20h]
0x180022bf5  mov     ecx, [r14]
0x180022bf8  add     ecx, 1Ch
0x180022bfb  mov     [rax+0Ch], ecx
0x180022bfe  mov     rax, [rbx+20h]
0x180022c02  mov     ecx, [r15]
0x180022c05  add     ecx, 1Ch
0x180022c08  mov     [rax+14h], ecx
0x180022c0b  mov     rax, [rbx+20h]
0x180022c0f  mov     dword ptr [rax+1Ch], 64h ; 'd'
0x180022c16  mov     rax, [rbx+20h]
0x180022c1a  mov     [rax+20h], r11d
0x180022c1e  mov     rax, [rbx+20h]
0x180022c22  or      dword ptr [rax+28h], 0FFFFFFFFh
0x180022c26  mov     rax, [rbx+20h]
0x180022c2a  and     dword ptr [rax+2Ch], 0
0x180022c2e  xor     r8d, r8d
0x180022c31  mov     rax, [rbx+20h]
0x180022c35  lea     rdx, [rdx+28h]
0x180022c39  mov     dword ptr [rdx+rax+18h], 28h ; '('
0x180022c41  mov     ecx, [r14]
0x180022c44  mov     rax, [rbx+20h]
0x180022c48  add     ecx, r8d
0x180022c4b  mov     [rdx+rax+1Ch], ecx
0x180022c4f  mov     ecx, [r15]
0x180022c52  mov     rax, [rbx+20h]
0x180022c56  add     ecx, r8d
0x180022c59  add     r8d, 2
0x180022c5d  mov     [rdx+rax+24h], ecx
0x180022c61  mov     rax, [rbx+20h]
0x180022c65  mov     dword ptr [rdx+rax+30h], 64h ; 'd'
0x180022c6d  mov     eax, [r10]
0x180022c70  add     r10, r12
0x180022c73  mov     rcx, [rbx+20h]
0x180022c77  mov     [rdx+rcx+34h], eax
0x180022c7b  mov     rax, [rbx+20h]
0x180022c7f  mov     dword ptr [rdx+rax+38h], 8
0x180022c87  mov     rax, [rbx+20h]
0x180022c8b  mov     [rdx+rax+3Ch], r9d
0x180022c90  add     r9d, 8
0x180022c94  cmp     r9d, 78h ; 'x'
0x180022c98  jb      short loc_180022C31
0x180022c9a  mov     rdx, [rbx+30h]
0x180022c9e  mov     eax, [rbx+38h]
0x180022ca1  mov     [rdx], eax
0x180022ca3  mov     [rbx+18h], r11d
0x180022ca7  mov     [rbx+1Ch], r11d
0x180022cab  cmp     [rsp+48h+lpName], 0
0x180022cb1  jz      short loc_180022CBD
0x180022cb3  mov     rcx, [rsp+48h+lpName]; void *
0x180022cb8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180022cbd  test    edi, edi
0x180022cbf  jz      short loc_180022CC9
0x180022cc1  mov     rcx, rbx; this
0x180022cc4  call    ?Shutdown@CPerfCounters@@QEAAKXZ; CPerfCounters::Shutdown(void)
0x180022cc9  mov     rcx, [rsp+48h+hKey]; hKey
0x180022cce  test    rcx, rcx
0x180022cd1  jz      short loc_180022CD9
0x180022cd3  call    cs:__imp_RegCloseKey
0x180022cd9  mov     rbx, [rsp+48h+arg_0]
0x180022cde  mov     eax, edi
0x180022ce0  mov     rdi, [rsp+48h+arg_8]
0x180022ce5  add     rsp, 30h
0x180022ce9  pop     r15
0x180022ceb  pop     r14
0x180022ced  pop     r12
0x180022cef  retn
```
