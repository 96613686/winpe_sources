# CPerfCounters::InitializeClient(_GUID const &,_GUID const &,ushort const *,ulong,ulong,ulong *)

- ea: `0x18001f1d0`
- end: `0x18001f4d1`
- name: `?InitializeClient@CPerfCounters@@QEAAKAEBU_GUID@@0PEBGKKPEAK@Z`
- size: `769`
- prototype: `unsigned int __usercall@<eax>(CPerfCounters *__hidden this@<rcx>, const struct _GUID *@<rdx>, const struct _GUID *@<r8>, const unsigned __int16 *@<r9>, unsigned int, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config`

## callees

- `0x18000179c`
- `0x18000e400`
- `0x18001f020`
- `0x18001f1d0`
- `0x18001f7f0`
- `0x18002e468`
- `0x18002f3ba`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001f234`
- `KERNEL32!GetLastError` at `0x18001f234`
- `KERNEL32!OpenFileMappingW` at `0x18001f21d`
- `KERNEL32!OpenFileMappingW` at `0x18001f21d`
- `KERNEL32!MapViewOfFile` at `0x18001f267`
- `KERNEL32!MapViewOfFile` at `0x18001f267`
- `ADVAPI32!RegCloseKey` at `0x18001f286`
- `ADVAPI32!RegCloseKey` at `0x18001f4a8`
- `ADVAPI32!RegCloseKey` at `0x18001f286`
- `ADVAPI32!RegCloseKey` at `0x18001f4a8`
- `ADVAPI32!RegOpenKeyExW` at `0x18001f2af`
- `ADVAPI32!RegOpenKeyExW` at `0x18001f2af`

## pseudocode

```c
__int64 __fastcall CPerfCounters::InitializeClient(
        CPerfCounters *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int *a7)
{
  unsigned int ObjectName; // edi
  HANDLE v10; // rax
  unsigned int v11; // r14d
  LPVOID v12; // rax
  _DWORD *v13; // r15
  _DWORD *v14; // r12
  unsigned int v15; // eax
  void *v16; // rax
  void *v17; // rax
  __int64 v19; // rdx
  int v20; // r8d
  __int64 v21; // r11
  int v22; // r9d
  int v23; // ecx
  int v24; // eax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  LPCWSTR lpName; // [rsp+38h] [rbp-20h] BYREF

  lpName = 0;
  hKey = 0;
  ObjectName = CPerfCounters::CreateObjectName(this, a3, (unsigned __int16 **)&lpName);
  if ( !ObjectName )
  {
    v10 = OpenFileMappingW(4u, 0, lpName);
    *(_QWORD *)this = v10;
    if ( v10 && (v11 = 8 * a6, v12 = MapViewOfFile(v10, 4u, 0, 0, 8 * a6), (*((_QWORD *)this + 1) = v12) != 0) )
    {
      if ( hKey )
        RegCloseKey(hKey);
      ObjectName = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a4, 0, 0x20119u, &hKey);
      if ( !ObjectName )
      {
        v13 = (_DWORD *)((char *)this + 16);
        ObjectName = CRegKey::GetValue((CRegKey *)&hKey, L"First Counter", 4u, (char *)this + 16, 4u);
        if ( !ObjectName )
        {
          v14 = (_DWORD *)((char *)this + 20);
          ObjectName = CRegKey::GetValue((CRegKey *)&hKey, L"First Help", 4u, (char *)this + 20, 4u);
          if ( !ObjectName )
          {
            v15 = 40 * a6 + 64;
            *((_DWORD *)this + 10) = v15;
            v16 = operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
            *((_QWORD *)this + 4) = v16;
            if ( v16
              && (memset_0(v16, 0, *((unsigned int *)this + 10)),
                  *((_DWORD *)this + 14) = v11 + 8,
                  v17 = operator new[](v11 + 8, (const struct std::nothrow_t *)&std::nothrow),
                  (*((_QWORD *)this + 6) = v17) != 0) )
            {
              memset_0(v17, 0, *((unsigned int *)this + 14));
              **((_DWORD **)this + 4) = *((_DWORD *)this + 10) + *((_DWORD *)this + 14);
              *(_DWORD *)(*((_QWORD *)this + 4) + 4LL) = *((_DWORD *)this + 10);
              *(_DWORD *)(*((_QWORD *)this + 4) + 8LL) = 64;
              *(_DWORD *)(*((_QWORD *)this + 4) + 12LL) = 2 * a5 + *v13;
              *(_DWORD *)(*((_QWORD *)this + 4) + 20LL) = 2 * a5 + *v14;
              *(_DWORD *)(*((_QWORD *)this + 4) + 28LL) = 100;
              *(_DWORD *)(*((_QWORD *)this + 4) + 32LL) = a6;
              *(_DWORD *)(*((_QWORD *)this + 4) + 40LL) = -1;
              *(_DWORD *)(*((_QWORD *)this + 4) + 44LL) = 0;
              if ( a6 )
              {
                v19 = 0;
                v20 = 0;
                v21 = a6;
                v22 = 8;
                do
                {
                  v19 += 40;
                  *(_DWORD *)(v19 + *((_QWORD *)this + 4) + 24) = 40;
                  *(_DWORD *)(v19 + *((_QWORD *)this + 4) + 28) = v20 + *v13;
                  v23 = v20 + *v14;
                  v20 += 2;
                  *(_DWORD *)(v19 + *((_QWORD *)this + 4) + 36) = v23;
                  *(_DWORD *)(v19 + *((_QWORD *)this + 4) + 48) = 100;
                  v24 = *a7++;
                  *(_DWORD *)(v19 + *((_QWORD *)this + 4) + 52) = v24;
                  *(_DWORD *)(v19 + *((_QWORD *)this + 4) + 56) = 8;
                  *(_DWORD *)(v19 + *((_QWORD *)this + 4) + 60) = v22;
                  v22 += 8;
                  --v21;
                }
                while ( v21 );
              }
              **((_DWORD **)this + 6) = *((_DWORD *)this + 14);
              *((_DWORD *)this + 6) = a6;
              *((_DWORD *)this + 7) = a5;
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
0x18001f1d0  mov     rax, rsp
0x18001f1d3  mov     [rax+8], rbx
0x18001f1d7  mov     [rax+10h], rsi
0x18001f1db  mov     [rax+18h], rdi
0x18001f1df  push    r12
0x18001f1e1  push    r14
0x18001f1e3  push    r15
0x18001f1e5  sub     rsp, 40h
0x18001f1e9  and     qword ptr [rax-20h], 0
0x18001f1ee  mov     rdx, r8; struct _GUID *
0x18001f1f1  and     qword ptr [rax-28h], 0
0x18001f1f6  lea     r8, [rax-20h]; unsigned __int16 **
0x18001f1fa  mov     r15, r9
0x18001f1fd  mov     rbx, rcx
0x18001f200  call    ?CreateObjectName@CPerfCounters@@IEAAKPEBU_GUID@@PEAPEAG@Z; CPerfCounters::CreateObjectName(_GUID const *,ushort * *)
0x18001f205  mov     edi, eax
0x18001f207  test    eax, eax
0x18001f209  jnz     loc_18001F480
0x18001f20f  mov     r8, [rsp+58h+lpName]; lpName
0x18001f214  lea     r12d, [rax+4]
0x18001f218  mov     ecx, r12d; dwDesiredAccess
0x18001f21b  xor     edx, edx; bInheritHandle
0x18001f21d  call    cs:__imp_OpenFileMappingW
0x18001f224  nop     dword ptr [rax+rax+00h]
0x18001f229  mov     [rbx], rax
0x18001f22c  mov     rcx, rax; hFileMappingObject
0x18001f22f  test    rax, rax
0x18001f232  jnz     short loc_18001F247
0x18001f234  call    cs:__imp_GetLastError
0x18001f23b  nop     dword ptr [rax+rax+00h]
0x18001f240  mov     edi, eax
0x18001f242  jmp     loc_18001F480
0x18001f247  mov     esi, [rsp+58h+arg_28]
0x18001f24e  xor     r9d, r9d; dwFileOffsetLow
0x18001f251  xor     r8d, r8d; dwFileOffsetHigh
0x18001f254  mov     edx, r12d; dwDesiredAccess
0x18001f257  lea     r14d, ds:0[rsi*8]
0x18001f25f  mov     eax, r14d
0x18001f262  mov     [rsp+58h+dwNumberOfBytesToMap], rax; dwNumberOfBytesToMap
0x18001f267  call    cs:__imp_MapViewOfFile
0x18001f26e  nop     dword ptr [rax+rax+00h]
0x18001f273  mov     [rbx+8], rax
0x18001f277  test    rax, rax
0x18001f27a  jz      short loc_18001F234
0x18001f27c  mov     rcx, [rsp+58h+hKey]; hKey
0x18001f281  test    rcx, rcx
0x18001f284  jz      short loc_18001F292
0x18001f286  call    cs:__imp_RegCloseKey
0x18001f28d  nop     dword ptr [rax+rax+00h]
0x18001f292  lea     rax, [rsp+58h+hKey]
0x18001f297  mov     r9d, 20119h; samDesired
0x18001f29d  xor     r8d, r8d; ulOptions
0x18001f2a0  mov     [rsp+58h+dwNumberOfBytesToMap], rax; phkResult
0x18001f2a5  mov     rdx, r15; lpSubKey
0x18001f2a8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f2af  call    cs:__imp_RegOpenKeyExW
0x18001f2b6  nop     dword ptr [rax+rax+00h]
0x18001f2bb  mov     edi, eax
0x18001f2bd  test    eax, eax
0x18001f2bf  jnz     loc_18001F480
0x18001f2c5  lea     r15, [rbx+10h]
0x18001f2c9  mov     dword ptr [rsp+58h+dwNumberOfBytesToMap], r12d; unsigned int
0x18001f2ce  mov     r9, r15; void *
0x18001f2d1  lea     rdx, aFirstCounter; "First Counter"
0x18001f2d8  mov     r8d, r12d; unsigned int
0x18001f2db  lea     rcx, [rsp+58h+hKey]; this
0x18001f2e0  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x18001f2e5  mov     edi, eax
0x18001f2e7  test    eax, eax
0x18001f2e9  jnz     loc_18001F480
0x18001f2ef  lea     r12, [rbx+14h]
0x18001f2f3  mov     dword ptr [rsp+58h+dwNumberOfBytesToMap], 4; unsigned int
0x18001f2fb  mov     r9, r12; void *
0x18001f2fe  lea     r8d, [rax+4]; unsigned int
0x18001f302  lea     rdx, aFirstHelp; "First Help"
0x18001f309  lea     rcx, [rsp+58h+hKey]; this
0x18001f30e  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x18001f313  mov     edi, eax
0x18001f315  test    eax, eax
0x18001f317  jnz     loc_18001F480
0x18001f31d  lea     eax, [rsi+rsi*4]
0x18001f320  lea     eax, ds:40h[rax*8]
0x18001f327  mov     ecx, eax; unsigned __int64
0x18001f329  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f330  mov     [rbx+28h], eax
0x18001f333  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001f338  mov     [rbx+20h], rax
0x18001f33c  test    rax, rax
0x18001f33f  jnz     short loc_18001F34B
0x18001f341  mov     edi, 8
0x18001f346  jmp     loc_18001F480
0x18001f34b  mov     r8d, [rbx+28h]; Size
0x18001f34f  xor     edx, edx; Val
0x18001f351  mov     rcx, rax; void *
0x18001f354  call    memset_0
0x18001f359  lea     eax, [r14+8]
0x18001f35d  mov     ecx, eax; unsigned __int64
0x18001f35f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f366  mov     [rbx+38h], eax
0x18001f369  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001f36e  mov     [rbx+30h], rax
0x18001f372  test    rax, rax
0x18001f375  jz      short loc_18001F341
0x18001f377  mov     r8d, [rbx+38h]; Size
0x18001f37b  xor     edx, edx; Val
0x18001f37d  mov     rcx, rax; void *
0x18001f380  call    memset_0
0x18001f385  mov     rax, [rbx+20h]
0x18001f389  mov     ecx, [rbx+38h]
0x18001f38c  add     ecx, [rbx+28h]
0x18001f38f  mov     r14d, [rsp+58h+arg_20]
0x18001f397  mov     [rax], ecx
0x18001f399  mov     rcx, [rbx+20h]
0x18001f39d  mov     eax, [rbx+28h]
0x18001f3a0  lea     edx, [r14+r14]
0x18001f3a4  mov     [rcx+4], eax
0x18001f3a7  mov     rax, [rbx+20h]
0x18001f3ab  mov     dword ptr [rax+8], 40h ; '@'
0x18001f3b2  mov     rax, [rbx+20h]
0x18001f3b6  mov     ecx, [r15]
0x18001f3b9  add     ecx, edx
0x18001f3bb  mov     [rax+0Ch], ecx
0x18001f3be  mov     rax, [rbx+20h]
0x18001f3c2  mov     ecx, [r12]
0x18001f3c6  add     ecx, edx
0x18001f3c8  mov     [rax+14h], ecx
0x18001f3cb  mov     rax, [rbx+20h]
0x18001f3cf  mov     dword ptr [rax+1Ch], 64h ; 'd'
0x18001f3d6  mov     rax, [rbx+20h]
0x18001f3da  mov     [rax+20h], esi
0x18001f3dd  mov     rax, [rbx+20h]
0x18001f3e1  or      dword ptr [rax+28h], 0FFFFFFFFh
0x18001f3e5  mov     rax, [rbx+20h]
0x18001f3e9  and     dword ptr [rax+2Ch], 0
0x18001f3ed  test    esi, esi
0x18001f3ef  jz      short loc_18001F470
0x18001f3f1  mov     r10, [rsp+58h+arg_30]
0x18001f3f9  xor     edx, edx
0x18001f3fb  xor     r8d, r8d
0x18001f3fe  mov     r11, rsi
0x18001f401  lea     r9d, [rdx+8]
0x18001f405  mov     rax, [rbx+20h]
0x18001f409  lea     rdx, [rdx+28h]
0x18001f40d  mov     dword ptr [rdx+rax+18h], 28h ; '('
0x18001f415  mov     ecx, [r15]
0x18001f418  mov     rax, [rbx+20h]
0x18001f41c  add     ecx, r8d
0x18001f41f  mov     [rdx+rax+1Ch], ecx
0x18001f423  mov     ecx, [r12]
0x18001f427  mov     rax, [rbx+20h]
0x18001f42b  add     ecx, r8d
0x18001f42e  add     r8d, 2
0x18001f432  mov     [rdx+rax+24h], ecx
0x18001f436  mov     rax, [rbx+20h]
0x18001f43a  mov     dword ptr [rdx+rax+30h], 64h ; 'd'
0x18001f442  mov     eax, [r10]
0x18001f445  lea     r10, [r10+4]
0x18001f449  mov     rcx, [rbx+20h]
0x18001f44d  mov     [rdx+rcx+34h], eax
0x18001f451  mov     rax, [rbx+20h]
0x18001f455  mov     dword ptr [rdx+rax+38h], 8
0x18001f45d  mov     rax, [rbx+20h]
0x18001f461  mov     [rdx+rax+3Ch], r9d
0x18001f466  add     r9d, 8
0x18001f46a  sub     r11, 1
0x18001f46e  jnz     short loc_18001F405
0x18001f470  mov     rdx, [rbx+30h]
0x18001f474  mov     eax, [rbx+38h]
0x18001f477  mov     [rdx], eax
0x18001f479  mov     [rbx+18h], esi
0x18001f47c  mov     [rbx+1Ch], r14d
0x18001f480  cmp     [rsp+58h+lpName], 0
0x18001f486  jz      short loc_18001F492
0x18001f488  mov     rcx, [rsp+58h+lpName]; lpMem
0x18001f48d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f492  test    edi, edi
0x18001f494  jz      short loc_18001F49E
0x18001f496  mov     rcx, rbx; this
0x18001f499  call    ?Shutdown@CPerfCounters@@QEAAKXZ; CPerfCounters::Shutdown(void)
0x18001f49e  mov     rcx, [rsp+58h+hKey]; hKey
0x18001f4a3  test    rcx, rcx
0x18001f4a6  jz      short loc_18001F4B4
0x18001f4a8  call    cs:__imp_RegCloseKey
0x18001f4af  nop     dword ptr [rax+rax+00h]
0x18001f4b4  mov     rbx, [rsp+58h+arg_0]
0x18001f4b9  mov     eax, edi
0x18001f4bb  mov     rdi, [rsp+58h+arg_10]
0x18001f4c0  mov     rsi, [rsp+58h+arg_8]
0x18001f4c5  add     rsp, 40h
0x18001f4c9  pop     r15
0x18001f4cb  pop     r14
0x18001f4cd  pop     r12
0x18001f4cf  retn
```
