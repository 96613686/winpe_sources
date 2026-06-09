# CPerfCounters::InitializeClient(_GUID const &,_GUID const &,ushort const *,ulong,ulong,ulong *)

- ea: `0x1800201a0`
- end: `0x1800204a8`
- name: `?InitializeClient@CPerfCounters@@QEAAKAEBU_GUID@@0PEBGKKPEAK@Z`
- size: `776`
- prototype: `unsigned int __usercall@<eax>(CPerfCounters *__hidden this@<rcx>, const struct _GUID *@<rdx>, const struct _GUID *@<r8>, const unsigned __int16 *@<r9>, unsigned int, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, registry_config`

## callees

- `0x18000214c`
- `0x18000ef70`
- `0x18001fff0`
- `0x1800201a0`
- `0x1800207d0`
- `0x180030362`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002045d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002045d`
- `KERNEL32!GetLastError` at `0x180020204`
- `KERNEL32!GetLastError` at `0x180020204`
- `KERNEL32!OpenFileMappingW` at `0x1800201ed`
- `KERNEL32!OpenFileMappingW` at `0x1800201ed`
- `KERNEL32!MapViewOfFile` at `0x180020237`
- `KERNEL32!MapViewOfFile` at `0x180020237`
- `ADVAPI32!RegCloseKey` at `0x180020256`
- `ADVAPI32!RegCloseKey` at `0x18002047f`
- `ADVAPI32!RegCloseKey` at `0x180020256`
- `ADVAPI32!RegCloseKey` at `0x18002047f`
- `ADVAPI32!RegOpenKeyExW` at `0x18002027f`
- `ADVAPI32!RegOpenKeyExW` at `0x18002027f`

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
0x1800201a0  mov     rax, rsp
0x1800201a3  mov     [rax+8], rbx
0x1800201a7  mov     [rax+10h], rsi
0x1800201ab  mov     [rax+18h], rdi
0x1800201af  push    r12
0x1800201b1  push    r14
0x1800201b3  push    r15
0x1800201b5  sub     rsp, 40h
0x1800201b9  and     qword ptr [rax-20h], 0
0x1800201be  mov     rdx, r8; struct _GUID *
0x1800201c1  and     qword ptr [rax-28h], 0
0x1800201c6  lea     r8, [rax-20h]; unsigned __int16 **
0x1800201ca  mov     r15, r9
0x1800201cd  mov     rbx, rcx
0x1800201d0  call    ?CreateObjectName@CPerfCounters@@IEAAKPEBU_GUID@@PEAPEAG@Z; CPerfCounters::CreateObjectName(_GUID const *,ushort * *)
0x1800201d5  mov     edi, eax
0x1800201d7  test    eax, eax
0x1800201d9  jnz     loc_180020450
0x1800201df  mov     r8, [rsp+58h+lpName]; lpName
0x1800201e4  lea     r12d, [rax+4]
0x1800201e8  mov     ecx, r12d; dwDesiredAccess
0x1800201eb  xor     edx, edx; bInheritHandle
0x1800201ed  call    cs:__imp_OpenFileMappingW
0x1800201f4  nop     dword ptr [rax+rax+00h]
0x1800201f9  mov     [rbx], rax
0x1800201fc  mov     rcx, rax; hFileMappingObject
0x1800201ff  test    rax, rax
0x180020202  jnz     short loc_180020217
0x180020204  call    cs:__imp_GetLastError
0x18002020b  nop     dword ptr [rax+rax+00h]
0x180020210  mov     edi, eax
0x180020212  jmp     loc_180020450
0x180020217  mov     esi, [rsp+58h+arg_28]
0x18002021e  xor     r9d, r9d; dwFileOffsetLow
0x180020221  xor     r8d, r8d; dwFileOffsetHigh
0x180020224  mov     edx, r12d; dwDesiredAccess
0x180020227  lea     r14d, ds:0[rsi*8]
0x18002022f  mov     eax, r14d
0x180020232  mov     [rsp+58h+dwNumberOfBytesToMap], rax; dwNumberOfBytesToMap
0x180020237  call    cs:__imp_MapViewOfFile
0x18002023e  nop     dword ptr [rax+rax+00h]
0x180020243  mov     [rbx+8], rax
0x180020247  test    rax, rax
0x18002024a  jz      short loc_180020204
0x18002024c  mov     rcx, [rsp+58h+hKey]; hKey
0x180020251  test    rcx, rcx
0x180020254  jz      short loc_180020262
0x180020256  call    cs:__imp_RegCloseKey
0x18002025d  nop     dword ptr [rax+rax+00h]
0x180020262  lea     rax, [rsp+58h+hKey]
0x180020267  mov     r9d, 20119h; samDesired
0x18002026d  xor     r8d, r8d; ulOptions
0x180020270  mov     [rsp+58h+dwNumberOfBytesToMap], rax; phkResult
0x180020275  mov     rdx, r15; lpSubKey
0x180020278  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002027f  call    cs:__imp_RegOpenKeyExW
0x180020286  nop     dword ptr [rax+rax+00h]
0x18002028b  mov     edi, eax
0x18002028d  test    eax, eax
0x18002028f  jnz     loc_180020450
0x180020295  lea     r15, [rbx+10h]
0x180020299  mov     dword ptr [rsp+58h+dwNumberOfBytesToMap], r12d; unsigned int
0x18002029e  mov     r9, r15; void *
0x1800202a1  lea     rdx, aFirstCounter; "First Counter"
0x1800202a8  mov     r8d, r12d; unsigned int
0x1800202ab  lea     rcx, [rsp+58h+hKey]; this
0x1800202b0  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x1800202b5  mov     edi, eax
0x1800202b7  test    eax, eax
0x1800202b9  jnz     loc_180020450
0x1800202bf  lea     r12, [rbx+14h]
0x1800202c3  mov     dword ptr [rsp+58h+dwNumberOfBytesToMap], 4; unsigned int
0x1800202cb  mov     r9, r12; void *
0x1800202ce  lea     r8d, [rax+4]; unsigned int
0x1800202d2  lea     rdx, aFirstHelp; "First Help"
0x1800202d9  lea     rcx, [rsp+58h+hKey]; this
0x1800202de  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x1800202e3  mov     edi, eax
0x1800202e5  test    eax, eax
0x1800202e7  jnz     loc_180020450
0x1800202ed  lea     eax, [rsi+rsi*4]
0x1800202f0  lea     eax, ds:40h[rax*8]
0x1800202f7  mov     ecx, eax; unsigned __int64
0x1800202f9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020300  mov     [rbx+28h], eax
0x180020303  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180020308  mov     [rbx+20h], rax
0x18002030c  test    rax, rax
0x18002030f  jnz     short loc_18002031B
0x180020311  mov     edi, 8
0x180020316  jmp     loc_180020450
0x18002031b  mov     r8d, [rbx+28h]; Size
0x18002031f  xor     edx, edx; Val
0x180020321  mov     rcx, rax; void *
0x180020324  call    memset_0
0x180020329  lea     eax, [r14+8]
0x18002032d  mov     ecx, eax; unsigned __int64
0x18002032f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020336  mov     [rbx+38h], eax
0x180020339  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002033e  mov     [rbx+30h], rax
0x180020342  test    rax, rax
0x180020345  jz      short loc_180020311
0x180020347  mov     r8d, [rbx+38h]; Size
0x18002034b  xor     edx, edx; Val
0x18002034d  mov     rcx, rax; void *
0x180020350  call    memset_0
0x180020355  mov     rax, [rbx+20h]
0x180020359  mov     ecx, [rbx+38h]
0x18002035c  add     ecx, [rbx+28h]
0x18002035f  mov     r14d, [rsp+58h+arg_20]
0x180020367  mov     [rax], ecx
0x180020369  mov     rcx, [rbx+20h]
0x18002036d  mov     eax, [rbx+28h]
0x180020370  lea     edx, [r14+r14]
0x180020374  mov     [rcx+4], eax
0x180020377  mov     rax, [rbx+20h]
0x18002037b  mov     dword ptr [rax+8], 40h ; '@'
0x180020382  mov     rax, [rbx+20h]
0x180020386  mov     ecx, [r15]
0x180020389  add     ecx, edx
0x18002038b  mov     [rax+0Ch], ecx
0x18002038e  mov     rax, [rbx+20h]
0x180020392  mov     ecx, [r12]
0x180020396  add     ecx, edx
0x180020398  mov     [rax+14h], ecx
0x18002039b  mov     rax, [rbx+20h]
0x18002039f  mov     dword ptr [rax+1Ch], 64h ; 'd'
0x1800203a6  mov     rax, [rbx+20h]
0x1800203aa  mov     [rax+20h], esi
0x1800203ad  mov     rax, [rbx+20h]
0x1800203b1  or      dword ptr [rax+28h], 0FFFFFFFFh
0x1800203b5  mov     rax, [rbx+20h]
0x1800203b9  and     dword ptr [rax+2Ch], 0
0x1800203bd  test    esi, esi
0x1800203bf  jz      short loc_180020440
0x1800203c1  mov     r10, [rsp+58h+arg_30]
0x1800203c9  xor     edx, edx
0x1800203cb  xor     r8d, r8d
0x1800203ce  mov     r11, rsi
0x1800203d1  lea     r9d, [rdx+8]
0x1800203d5  mov     rax, [rbx+20h]
0x1800203d9  lea     rdx, [rdx+28h]
0x1800203dd  mov     dword ptr [rdx+rax+18h], 28h ; '('
0x1800203e5  mov     ecx, [r15]
0x1800203e8  mov     rax, [rbx+20h]
0x1800203ec  add     ecx, r8d
0x1800203ef  mov     [rdx+rax+1Ch], ecx
0x1800203f3  mov     ecx, [r12]
0x1800203f7  mov     rax, [rbx+20h]
0x1800203fb  add     ecx, r8d
0x1800203fe  add     r8d, 2
0x180020402  mov     [rdx+rax+24h], ecx
0x180020406  mov     rax, [rbx+20h]
0x18002040a  mov     dword ptr [rdx+rax+30h], 64h ; 'd'
0x180020412  mov     eax, [r10]
0x180020415  lea     r10, [r10+4]
0x180020419  mov     rcx, [rbx+20h]
0x18002041d  mov     [rdx+rcx+34h], eax
0x180020421  mov     rax, [rbx+20h]
0x180020425  mov     dword ptr [rdx+rax+38h], 8
0x18002042d  mov     rax, [rbx+20h]
0x180020431  mov     [rdx+rax+3Ch], r9d
0x180020436  add     r9d, 8
0x18002043a  sub     r11, 1
0x18002043e  jnz     short loc_1800203D5
0x180020440  mov     rdx, [rbx+30h]
0x180020444  mov     eax, [rbx+38h]
0x180020447  mov     [rdx], eax
0x180020449  mov     [rbx+18h], esi
0x18002044c  mov     [rbx+1Ch], r14d
0x180020450  cmp     [rsp+58h+lpName], 0
0x180020456  jz      short loc_180020469
0x180020458  mov     rcx, [rsp+58h+lpName]
0x18002045d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180020464  nop     dword ptr [rax+rax+00h]
0x180020469  test    edi, edi
0x18002046b  jz      short loc_180020475
0x18002046d  mov     rcx, rbx; this
0x180020470  call    ?Shutdown@CPerfCounters@@QEAAKXZ; CPerfCounters::Shutdown(void)
0x180020475  mov     rcx, [rsp+58h+hKey]; hKey
0x18002047a  test    rcx, rcx
0x18002047d  jz      short loc_18002048B
0x18002047f  call    cs:__imp_RegCloseKey
0x180020486  nop     dword ptr [rax+rax+00h]
0x18002048b  mov     rbx, [rsp+58h+arg_0]
0x180020490  mov     eax, edi
0x180020492  mov     rdi, [rsp+58h+arg_10]
0x180020497  mov     rsi, [rsp+58h+arg_8]
0x18002049c  add     rsp, 40h
0x1800204a0  pop     r15
0x1800204a2  pop     r14
0x1800204a4  pop     r12
0x1800204a6  retn
```
