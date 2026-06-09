# PerfBuff::Read(HKEY__ *,int,int)

- ea: `0x18000ed70`
- end: `0x18000ef60`
- name: `?Read@PerfBuff@@QEAAKPEAUHKEY__@@HH@Z`
- size: `496`
- prototype: `__int64 __fastcall(PerfBuff *this, HKEY, int, DWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f234`
- `0x18000f364`

## callees

- `0x18000ed70`
- `0x18000ef68`
- `0x18000ef94`
- `0x18000f4cc`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000edd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000ef3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000edd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000ef3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ee75`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ee75`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18000ee0a`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18000ee0a`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000ede8`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000ede8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000ee88`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000ee88`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000eda1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ee98`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000eda1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ee98`

## pseudocode

```c
__int64 __fastcall PerfBuff::Read(PerfBuff *this, HKEY a2, int a3, DWORD a4)
{
  void *v7; // rax
  DWORD TickCount; // r12d
  int v9; // edi
  void (__fastcall ***v10)(_QWORD, __int64); // rax
  void (__fastcall ***v11)(_QWORD, __int64); // r15
  const WCHAR *All; // rsi
  BYTE *lpData; // rax
  LSTATUS v14; // edi
  void *v15; // rax
  DWORD v17; // eax
  DWORD v18; // r8d
  __int64 v19; // rcx
  DWORD v20; // eax
  char v21[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v22; // [rsp+38h] [rbp-40h]
  unsigned int v23; // [rsp+44h] [rbp-34h]
  char v24; // [rsp+48h] [rbp-30h]
  DWORD Type; // [rsp+80h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+20h] BYREF

  cbData = a4;
  if ( !*((_DWORD *)this + 2) )
  {
    v7 = CWin32DefaultArena::WbemMemAlloc(0x61A8u);
    *((_QWORD *)this + 2) = v7;
    if ( !v7 )
      return 2147749894LL;
    *((_DWORD *)this + 2) = 25000;
  }
  *((_QWORD *)this + 17) = a2;
  if ( !(unsigned int)CIndicyList::SetUse((PerfBuff *)((char *)this + 24), a3) )
    return 2147749894LL;
  TickCount = GetTickCount();
  v9 = *((_DWORD *)this + 12);
  while ( --v9 >= 0 )
  {
    v10 = (void (__fastcall ***)(_QWORD, __int64))CFlexArray::GetAt((PerfBuff *)((char *)this + 48), v9);
    v11 = v10;
    if ( *((_DWORD *)v10 + 3) != -1 && TickCount - *((_DWORD *)v10 + 3) > 0x7530 )
    {
      CFlexArray::RemoveAt((PerfBuff *)((char *)this + 48), v9);
      (**v11)(v11, 1);
    }
  }
  All = CIndicyList::pGetAll((PerfBuff *)((char *)this + 24));
  if ( !All )
    return 2147749894LL;
  while ( 1 )
  {
    lpData = (BYTE *)*((_QWORD *)this + 2);
    cbData = *((_DWORD *)this + 2);
    Type = 0;
    v14 = RegQueryValueExW(a2, All, 0, &Type, lpData, &cbData);
    if ( v14 != 234 )
      break;
    CWin32DefaultArena::WbemMemFree(*((void **)this + 2));
    *((_DWORD *)this + 2) += 5000;
    v15 = CWin32DefaultArena::WbemMemAlloc(*((unsigned int *)this + 2));
    *((_QWORD *)this + 2) = v15;
    if ( !v15 )
    {
      *((_DWORD *)this + 2) = 0;
      return 2147749894LL;
    }
  }
  if ( v14 < 0 )
  {
    *((_DWORD *)this + 3) = 0;
    v18 = 0;
  }
  else
  {
    v17 = *((_DWORD *)this + 2);
    v18 = cbData;
    *((_DWORD *)this + 3) = v17;
    if ( v17 <= v18 )
      v18 = v17;
    else
      *((_DWORD *)this + 3) = v18;
  }
  if ( v14 )
  {
    v20 = 0;
  }
  else
  {
    CCheckedBuffer::ResetTo((CCheckedBuffer *)v21, *((unsigned __int8 **)this + 2), v18);
    if ( v24 )
      return 2147749889LL;
    if ( v23 < 0x58 )
      return 2147749889LL;
    v19 = v22;
    if ( !v22 )
      return 2147749889LL;
    *((_QWORD *)this + 19) = *(_QWORD *)(v22 + 56);
    *((_QWORD *)this + 20) = *(_QWORD *)(v19 + 72);
    *((_QWORD *)this + 21) = *(_QWORD *)(v19 + 64);
    v20 = GetTickCount();
  }
  *((_DWORD *)this + 36) = v20;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000ed70  mov     [rsp+arg_8], rbx
0x18000ed75  mov     [rsp+arg_10], rbp
0x18000ed7a  mov     [rsp+cbData], r9d
0x18000ed7f  push    rsi
0x18000ed80  push    rdi
0x18000ed81  push    r12
0x18000ed83  push    r14
0x18000ed85  push    r15
0x18000ed87  sub     rsp, 50h
0x18000ed8b  cmp     dword ptr [rcx+8], 0
0x18000ed8f  mov     edi, r8d
0x18000ed92  mov     rbp, rdx
0x18000ed95  mov     rbx, rcx
0x18000ed98  jnz     short loc_18000EDB7
0x18000ed9a  mov     esi, 61A8h
0x18000ed9f  mov     ecx, esi
0x18000eda1  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000eda7  mov     [rbx+10h], rax
0x18000edab  test    rax, rax
0x18000edae  jz      loc_18000EEAA
0x18000edb4  mov     [rbx+8], esi
0x18000edb7  mov     edx, edi; int
0x18000edb9  mov     [rbx+88h], rbp
0x18000edc0  lea     rcx, [rbx+18h]; this
0x18000edc4  call    ?SetUse@CIndicyList@@QEAAHH@Z; CIndicyList::SetUse(int)
0x18000edc9  test    eax, eax
0x18000edcb  jz      loc_18000EEAA
0x18000edd1  call    cs:__imp_GetTickCount
0x18000edd7  lea     r14, [rbx+30h]
0x18000eddb  mov     r12d, eax
0x18000edde  mov     edi, [r14]
0x18000ede1  jmp     short loc_18000EE23
0x18000ede3  mov     edx, edi
0x18000ede5  mov     rcx, r14
0x18000ede8  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18000edee  mov     r15, rax
0x18000edf1  cmp     dword ptr [rax+0Ch], 0FFFFFFFFh
0x18000edf5  jz      short loc_18000EE23
0x18000edf7  mov     ecx, r12d
0x18000edfa  sub     ecx, [rax+0Ch]
0x18000edfd  cmp     ecx, 7530h
0x18000ee03  jbe     short loc_18000EE23
0x18000ee05  mov     edx, edi
0x18000ee07  mov     rcx, r14
0x18000ee0a  call    cs:__imp_?RemoveAt@CFlexArray@@QEAAHH@Z; CFlexArray::RemoveAt(int)
0x18000ee10  mov     rdx, [r15]
0x18000ee13  mov     rcx, r15
0x18000ee16  mov     rax, [rdx]
0x18000ee19  mov     edx, 1
0x18000ee1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee23  sub     edi, 1
0x18000ee26  jns     short loc_18000EDE3
0x18000ee28  lea     rcx, [rbx+18h]; this
0x18000ee2c  call    ?pGetAll@CIndicyList@@QEAAPEBGXZ; CIndicyList::pGetAll(void)
0x18000ee31  mov     rsi, rax
0x18000ee34  test    rax, rax
0x18000ee37  jz      short loc_18000EEAA
0x18000ee39  mov     ecx, [rbx+8]
0x18000ee3c  lea     rax, [rsp+78h+cbData]
0x18000ee44  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18000ee49  lea     r9, [rsp+78h+Type]; lpType
0x18000ee51  mov     rax, [rbx+10h]
0x18000ee55  xor     r8d, r8d; lpReserved
0x18000ee58  mov     [rsp+78h+cbData], ecx
0x18000ee5f  mov     rdx, rsi; lpValueName
0x18000ee62  mov     rcx, rbp; hKey
0x18000ee65  mov     [rsp+78h+lpData], rax; lpData
0x18000ee6a  mov     [rsp+78h+Type], 0
0x18000ee75  call    cs:__imp_RegQueryValueExW
0x18000ee7b  mov     edi, eax
0x18000ee7d  cmp     eax, 0EAh
0x18000ee82  jnz     short loc_18000EEC8
0x18000ee84  mov     rcx, [rbx+10h]
0x18000ee88  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000ee8e  add     dword ptr [rbx+8], 1388h
0x18000ee95  mov     ecx, [rbx+8]
0x18000ee98  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000ee9e  mov     [rbx+10h], rax
0x18000eea2  test    rax, rax
0x18000eea5  jnz     short loc_18000EE39
0x18000eea7  mov     [rbx+8], eax
0x18000eeaa  mov     eax, 80041006h
0x18000eeaf  lea     r11, [rsp+78h+var_28]
0x18000eeb4  mov     rbx, [r11+38h]
0x18000eeb8  mov     rbp, [r11+40h]
0x18000eebc  mov     rsp, r11
0x18000eebf  pop     r15
0x18000eec1  pop     r14
0x18000eec3  pop     r12
0x18000eec5  pop     rdi
0x18000eec6  pop     rsi
0x18000eec7  retn
0x18000eec8  test    edi, edi
0x18000eeca  js      short loc_18000EEEA
0x18000eecc  mov     eax, [rbx+8]
0x18000eecf  mov     r8d, [rsp+78h+cbData]
0x18000eed7  mov     [rbx+0Ch], eax
0x18000eeda  cmp     eax, r8d
0x18000eedd  jbe     short loc_18000EEE5
0x18000eedf  mov     [rbx+0Ch], r8d
0x18000eee3  jmp     short loc_18000EEF4
0x18000eee5  mov     r8d, eax
0x18000eee8  jmp     short loc_18000EEF4
0x18000eeea  mov     dword ptr [rbx+0Ch], 0
0x18000eef1  xor     r8d, r8d; unsigned int
0x18000eef4  test    edi, edi
0x18000eef6  jnz     short loc_18000EF51
0x18000eef8  mov     rdx, [rbx+10h]; unsigned __int8 *
0x18000eefc  lea     rcx, [rsp+78h+var_48]; this
0x18000ef01  call    ?ResetTo@CCheckedBuffer@@QEAAXPEAEK@Z; CCheckedBuffer::ResetTo(uchar *,ulong)
0x18000ef06  cmp     [rsp+78h+var_30], dil
0x18000ef0b  jnz     short loc_18000EF47
0x18000ef0d  cmp     [rsp+78h+var_34], 58h ; 'X'
0x18000ef12  jb      short loc_18000EF47
0x18000ef14  mov     rcx, [rsp+78h+var_40]
0x18000ef19  test    rcx, rcx
0x18000ef1c  jz      short loc_18000EF47
0x18000ef1e  mov     rax, [rcx+38h]
0x18000ef22  mov     [rbx+98h], rax
0x18000ef29  mov     rax, [rcx+48h]
0x18000ef2d  mov     [rbx+0A0h], rax
0x18000ef34  mov     rax, [rcx+40h]
0x18000ef38  mov     [rbx+0A8h], rax
0x18000ef3f  call    cs:__imp_GetTickCount
0x18000ef45  jmp     short loc_18000EF53
0x18000ef47  mov     eax, 80041001h
0x18000ef4c  jmp     loc_18000EEAF
0x18000ef51  xor     eax, eax
0x18000ef53  mov     [rbx+90h], eax
0x18000ef59  mov     eax, edi
0x18000ef5b  jmp     loc_18000EEAF
```
