# CPerfCounters::InitializeClient(_GUID const &,_GUID const &,ushort const *,ulong,ulong,ulong *)

- ea: `0x18003c0f8`
- end: `0x18003c3d2`
- name: `?InitializeClient@CPerfCounters@@QEAAKAEBU_GUID@@0PEBGKKPEAK@Z`
- size: `730`
- prototype: `unsigned int __fastcall(CPerfCounters *__hidden this, const struct _GUID *, const struct _GUID *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config, service_task`

## callers

- `0x180008790`

## callees

- `0x18000a960`
- `0x18003b1e8`
- `0x18003bf9c`
- `0x18003c00c`
- `0x18003c0f8`
- `0x180060808`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x18003c17f`
- `KERNEL32!MapViewOfFile` at `0x18003c17f`
- `KERNEL32!GetLastError` at `0x18003c157`
- `KERNEL32!GetLastError` at `0x18003c157`
- `KERNEL32!OpenFileMappingW` at `0x18003c143`
- `KERNEL32!OpenFileMappingW` at `0x18003c143`
- `ADVAPI32!RegCloseKey` at `0x18003c19e`
- `ADVAPI32!RegCloseKey` at `0x18003c3af`
- `ADVAPI32!RegCloseKey` at `0x18003c19e`
- `ADVAPI32!RegCloseKey` at `0x18003c3af`
- `ADVAPI32!RegOpenKeyExW` at `0x18003c1cb`
- `ADVAPI32!RegOpenKeyExW` at `0x18003c1cb`

## string_xrefs

- `0x18003c1bd`: `System\CurrentControlSet\Services\WDSTFTP\Performance`

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
    if ( v6 && (v7 = MapViewOfFile(v6, 4u, 0, 0, 0x48u), (*((_QWORD *)this + 1) = v7) != 0) )
    {
      if ( hKey )
        RegCloseKey(hKey);
      ObjectName = RegOpenKeyExW(
                     HKEY_LOCAL_MACHINE,
                     L"System\\CurrentControlSet\\Services\\WDSTFTP\\Performance",
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
            *((_DWORD *)this + 10) = 424;
            v10 = operator new[](0x1A8u, (const struct std::nothrow_t *)&std::nothrow);
            *((_QWORD *)this + 4) = v10;
            if ( v10
              && (memset_0(v10, 0, *((unsigned int *)this + 10)),
                  *((_DWORD *)this + 14) = 80,
                  v11 = operator new[](0x50u, (const struct std::nothrow_t *)&std::nothrow),
                  (*((_QWORD *)this + 6) = v11) != 0) )
            {
              memset_0(v11, 0, *((unsigned int *)this + 14));
              v12 = qword_1800770A0;
              v13 = 0;
              **((_DWORD **)this + 4) = *((_DWORD *)this + 10) + *((_DWORD *)this + 14);
              v14 = 8;
              *(_DWORD *)(*((_QWORD *)this + 4) + 4LL) = *((_DWORD *)this + 10);
              *(_DWORD *)(*((_QWORD *)this + 4) + 8LL) = 64;
              *(_DWORD *)(*((_QWORD *)this + 4) + 12LL) = *v8 + 18;
              *(_DWORD *)(*((_QWORD *)this + 4) + 20LL) = *v9 + 18;
              *(_DWORD *)(*((_QWORD *)this + 4) + 28LL) = 100;
              *(_DWORD *)(*((_QWORD *)this + 4) + 32LL) = 9;
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
              while ( v14 < 0x50 );
              **((_DWORD **)this + 6) = *((_DWORD *)this + 14);
              *((_DWORD *)this + 6) = 9;
              *((_DWORD *)this + 7) = 9;
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
0x18003c0f8  mov     rax, rsp
0x18003c0fb  mov     [rax+8], rbx
0x18003c0ff  mov     [rax+10h], rdi
0x18003c103  mov     [rax+20h], r9
0x18003c107  mov     [rax+18h], r8
0x18003c10b  push    r12
0x18003c10d  push    r14
0x18003c10f  push    r15
0x18003c111  sub     rsp, 30h
0x18003c115  and     qword ptr [rax+18h], 0
0x18003c11a  lea     r8, [rax+18h]; unsigned __int16 **
0x18003c11e  and     qword ptr [rax+20h], 0
0x18003c123  mov     rbx, rcx
0x18003c126  call    ?CreateObjectName@CPerfCounters@@IEAAKPEBU_GUID@@PEAPEAG@Z; CPerfCounters::CreateObjectName(_GUID const *,ushort * *)
0x18003c12b  mov     edi, eax
0x18003c12d  test    eax, eax
0x18003c12f  jnz     loc_18003C387
0x18003c135  mov     r8, [rsp+48h+lpName]; lpName
0x18003c13a  lea     r12d, [rax+4]
0x18003c13e  mov     ecx, r12d; dwDesiredAccess
0x18003c141  xor     edx, edx; bInheritHandle
0x18003c143  call    cs:__imp_OpenFileMappingW
0x18003c14a  nop     dword ptr [rax+rax+00h]
0x18003c14f  mov     [rbx], rax
0x18003c152  test    rax, rax
0x18003c155  jnz     short loc_18003C16A
0x18003c157  call    cs:__imp_GetLastError
0x18003c15e  nop     dword ptr [rax+rax+00h]
0x18003c163  mov     edi, eax
0x18003c165  jmp     loc_18003C387
0x18003c16a  xor     r9d, r9d; dwFileOffsetLow
0x18003c16d  mov     [rsp+48h+dwNumberOfBytesToMap], 48h ; 'H'; dwNumberOfBytesToMap
0x18003c176  xor     r8d, r8d; dwFileOffsetHigh
0x18003c179  mov     edx, r12d; dwDesiredAccess
0x18003c17c  mov     rcx, rax; hFileMappingObject
0x18003c17f  call    cs:__imp_MapViewOfFile
0x18003c186  nop     dword ptr [rax+rax+00h]
0x18003c18b  mov     [rbx+8], rax
0x18003c18f  test    rax, rax
0x18003c192  jz      short loc_18003C157
0x18003c194  mov     rcx, [rsp+48h+hKey]; hKey
0x18003c199  test    rcx, rcx
0x18003c19c  jz      short loc_18003C1AA
0x18003c19e  call    cs:__imp_RegCloseKey
0x18003c1a5  nop     dword ptr [rax+rax+00h]
0x18003c1aa  lea     rax, [rsp+48h+hKey]
0x18003c1af  mov     r9d, 20119h; samDesired
0x18003c1b5  xor     r8d, r8d; ulOptions
0x18003c1b8  mov     [rsp+48h+dwNumberOfBytesToMap], rax; phkResult
0x18003c1bd  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\WD"...
0x18003c1c4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c1cb  call    cs:__imp_RegOpenKeyExW
0x18003c1d2  nop     dword ptr [rax+rax+00h]
0x18003c1d7  mov     edi, eax
0x18003c1d9  test    eax, eax
0x18003c1db  jnz     loc_18003C387
0x18003c1e1  lea     r14, [rbx+10h]
0x18003c1e5  mov     dword ptr [rsp+48h+dwNumberOfBytesToMap], r12d; unsigned int
0x18003c1ea  mov     r9, r14; void *
0x18003c1ed  lea     rdx, aFirstCounter; "First Counter"
0x18003c1f4  mov     r8d, r12d; unsigned int
0x18003c1f7  lea     rcx, [rsp+48h+hKey]; this
0x18003c1fc  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x18003c201  mov     edi, eax
0x18003c203  test    eax, eax
0x18003c205  jnz     loc_18003C387
0x18003c20b  lea     r15, [rbx+14h]
0x18003c20f  mov     dword ptr [rsp+48h+dwNumberOfBytesToMap], r12d; unsigned int
0x18003c214  mov     r9, r15; void *
0x18003c217  lea     rdx, aFirstHelp; "First Help"
0x18003c21e  mov     r8d, r12d; unsigned int
0x18003c221  lea     rcx, [rsp+48h+hKey]; this
0x18003c226  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x18003c22b  mov     edi, eax
0x18003c22d  test    eax, eax
0x18003c22f  jnz     loc_18003C387
0x18003c235  mov     ecx, 1A8h; unsigned __int64
0x18003c23a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003c241  mov     [rbx+28h], ecx
0x18003c244  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003c249  mov     [rbx+20h], rax
0x18003c24d  test    rax, rax
0x18003c250  jnz     short loc_18003C25C
0x18003c252  mov     edi, 8
0x18003c257  jmp     loc_18003C387
0x18003c25c  mov     r8d, [rbx+28h]; Size
0x18003c260  xor     edx, edx; Val
0x18003c262  mov     rcx, rax; void *
0x18003c265  call    memset_0
0x18003c26a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003c271  mov     dword ptr [rbx+38h], 50h ; 'P'
0x18003c278  mov     ecx, 50h ; 'P'; unsigned __int64
0x18003c27d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003c282  mov     [rbx+30h], rax
0x18003c286  test    rax, rax
0x18003c289  jz      short loc_18003C252
0x18003c28b  mov     r8d, [rbx+38h]; Size
0x18003c28f  xor     edx, edx; Val
0x18003c291  mov     rcx, rax; void *
0x18003c294  call    memset_0
0x18003c299  mov     rax, [rbx+20h]
0x18003c29d  lea     r10, qword_1800770A0
0x18003c2a4  mov     ecx, [rbx+38h]
0x18003c2a7  mov     r11d, 9
0x18003c2ad  add     ecx, [rbx+28h]
0x18003c2b0  xor     edx, edx
0x18003c2b2  mov     [rax], ecx
0x18003c2b4  mov     rcx, [rbx+20h]
0x18003c2b8  lea     r9d, [r11-1]
0x18003c2bc  mov     eax, [rbx+28h]
0x18003c2bf  mov     [rcx+4], eax
0x18003c2c2  mov     rax, [rbx+20h]
0x18003c2c6  mov     dword ptr [rax+8], 40h ; '@'
0x18003c2cd  mov     rax, [rbx+20h]
0x18003c2d1  mov     ecx, [r14]
0x18003c2d4  add     ecx, 12h
0x18003c2d7  mov     [rax+0Ch], ecx
0x18003c2da  mov     rax, [rbx+20h]
0x18003c2de  mov     ecx, [r15]
0x18003c2e1  add     ecx, 12h
0x18003c2e4  mov     [rax+14h], ecx
0x18003c2e7  mov     rax, [rbx+20h]
0x18003c2eb  mov     dword ptr [rax+1Ch], 64h ; 'd'
0x18003c2f2  mov     rax, [rbx+20h]
0x18003c2f6  mov     [rax+20h], r11d
0x18003c2fa  mov     rax, [rbx+20h]
0x18003c2fe  or      dword ptr [rax+28h], 0FFFFFFFFh
0x18003c302  mov     rax, [rbx+20h]
0x18003c306  and     dword ptr [rax+2Ch], 0
0x18003c30a  xor     r8d, r8d
0x18003c30d  mov     rax, [rbx+20h]
0x18003c311  lea     rdx, [rdx+28h]
0x18003c315  mov     dword ptr [rdx+rax+18h], 28h ; '('
0x18003c31d  mov     ecx, [r14]
0x18003c320  mov     rax, [rbx+20h]
0x18003c324  add     ecx, r8d
0x18003c327  mov     [rdx+rax+1Ch], ecx
0x18003c32b  mov     ecx, [r15]
0x18003c32e  mov     rax, [rbx+20h]
0x18003c332  add     ecx, r8d
0x18003c335  add     r8d, 2
0x18003c339  mov     [rdx+rax+24h], ecx
0x18003c33d  mov     rax, [rbx+20h]
0x18003c341  mov     dword ptr [rdx+rax+30h], 64h ; 'd'
0x18003c349  mov     eax, [r10]
0x18003c34c  add     r10, r12
0x18003c34f  mov     rcx, [rbx+20h]
0x18003c353  mov     [rdx+rcx+34h], eax
0x18003c357  mov     rax, [rbx+20h]
0x18003c35b  mov     dword ptr [rdx+rax+38h], 8
0x18003c363  mov     rax, [rbx+20h]
0x18003c367  mov     [rdx+rax+3Ch], r9d
0x18003c36c  add     r9d, 8
0x18003c370  cmp     r9d, 50h ; 'P'
0x18003c374  jb      short loc_18003C30D
0x18003c376  mov     rdx, [rbx+30h]
0x18003c37a  mov     eax, [rbx+38h]
0x18003c37d  mov     [rdx], eax
0x18003c37f  mov     [rbx+18h], r11d
0x18003c383  mov     [rbx+1Ch], r11d
0x18003c387  cmp     [rsp+48h+lpName], 0
0x18003c38d  jz      short loc_18003C399
0x18003c38f  mov     rcx, [rsp+48h+lpName]; void *
0x18003c394  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003c399  test    edi, edi
0x18003c39b  jz      short loc_18003C3A5
0x18003c39d  mov     rcx, rbx; this
0x18003c3a0  call    ?Shutdown@CPerfCounters@@QEAAKXZ; CPerfCounters::Shutdown(void)
0x18003c3a5  mov     rcx, [rsp+48h+hKey]; hKey
0x18003c3aa  test    rcx, rcx
0x18003c3ad  jz      short loc_18003C3BB
0x18003c3af  call    cs:__imp_RegCloseKey
0x18003c3b6  nop     dword ptr [rax+rax+00h]
0x18003c3bb  mov     rbx, [rsp+48h+arg_0]
0x18003c3c0  mov     eax, edi
0x18003c3c2  mov     rdi, [rsp+48h+arg_8]
0x18003c3c7  add     rsp, 30h
0x18003c3cb  pop     r15
0x18003c3cd  pop     r14
0x18003c3cf  pop     r12
0x18003c3d1  retn
```
