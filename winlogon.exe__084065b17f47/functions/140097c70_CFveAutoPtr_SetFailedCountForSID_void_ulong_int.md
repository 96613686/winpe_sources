# CFveAutoPtr::SetFailedCountForSID(void *,ulong,int *)

- ea: `0x140097c70`
- end: `0x140097f36`
- name: `?SetFailedCountForSID@CFveAutoPtr@@QEAAKPEAXKPEAH@Z`
- size: `710`
- prototype: `__int64 __fastcall(CFveAutoPtr *this, void *, int, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140042bbc`
- `0x140090cf0`

## callees

- `0x140038250`
- `0x1400974b0`
- `0x140097b4c`
- `0x140097c70`
- `0x140097f3c`
- `0x14009cc54`
- `0x1400a1010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140097f1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140097f1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140097f0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140097f0c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140097db2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140097db2`

## string_xrefs

- `0x140097cd1`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x140097e04`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x140097e69`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x140097eb0`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x140097e5d`: `EasUpdateDeviceLockoutState`

## pseudocode

```c
__int64 __fastcall CFveAutoPtr::SetFailedCountForSID(CFveAutoPtr *this, void *a2, int a3, int *a4)
{
  void *v6; // rdi
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // r9
  unsigned int v11; // r8d
  PSID v12; // rcx
  __int64 v13; // rdi
  DWORD LengthSid; // eax
  unsigned int v15; // eax
  unsigned int v16; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v19; // [rsp+20h] [rbp-58h]
  unsigned int v20; // [rsp+40h] [rbp-38h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-30h] BYREF
  int v22; // [rsp+80h] [rbp+8h] BYREF
  PSID pSid; // [rsp+88h] [rbp+10h]
  int *v24; // [rsp+98h] [rbp+20h]

  v24 = a4;
  pSid = a2;
  v6 = 0;
  lpMem = 0;
  v20 = 0;
  *a4 = 0;
  if ( !*(_DWORD *)this )
  {
    v7 = 21;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      21,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
      881,
      L"Not Initialized",
      &pPassword);
    return v7;
  }
  if ( !*((_DWORD *)this + 1) )
    goto LABEL_22;
  v22 = 0;
  if ( FindEASLockOutEntryForSID(*((struct _USER_COUNT_ENTRY **)this + 3), *((_DWORD *)this + 8), a2, &v22) )
  {
    v8 = *((_QWORD *)this + 3);
    if ( *(_DWORD *)(v8 + 16LL * (unsigned int)v22) == a3 )
      goto LABEL_22;
    *(_DWORD *)(v8 + 16LL * (unsigned int)v22) = a3;
  }
  else
  {
    if ( !a3 )
      goto LABEL_22;
    v9 = *((unsigned int *)this + 8);
    if ( (unsigned int)v9 >= *((_DWORD *)this + 9) )
    {
      v7 = 8;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        8,
        L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
        913,
        L"No more room for new entry",
        &pPassword);
      return v7;
    }
    v10 = (unsigned int)v22;
    if ( (unsigned int)v9 > v22 )
    {
      do
      {
        v11 = v9 - 1;
        *(_OWORD *)(*((_QWORD *)this + 3) + 16 * v9) = *(_OWORD *)(*((_QWORD *)this + 3) + 16LL * (unsigned int)(v9 - 1));
        v9 = (unsigned int)(v9 - 1);
      }
      while ( v11 > (unsigned int)v10 );
    }
    v12 = pSid;
    v13 = 2 * v10;
    *(_DWORD *)(*((_QWORD *)this + 3) + 16 * v10) = a3;
    LengthSid = GetLengthSid(v12);
    memcpy_0((char *)this + 40, pSid, LengthSid);
    *(_QWORD *)(*((_QWORD *)this + 3) + 8 * v13 + 8) = (char *)this + 40;
    ++*((_DWORD *)this + 8);
  }
  v7 = PackEASLockoutData(*((PSID **)this + 3), *((_DWORD *)this + 8), (unsigned __int8 **)&lpMem, &v20);
  if ( v7 )
  {
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      v7,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
      941,
      L"PackEASLockoutData",
      &pPassword);
    v6 = lpMem;
    goto LABEL_25;
  }
  v6 = lpMem;
  v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID, _QWORD))(**((_QWORD **)this + 16) + 56LL))(
          *((_QWORD *)this + 16),
          *((_QWORD *)this + 15),
          lpMem,
          v20);
  v16 = v15;
  if ( v15 )
  {
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      v15,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
      946,
      L"EasUpdateDeviceLockoutState",
      &pPassword);
    if ( v16 != -2144272177 && v16 != -2013200375 )
    {
      v7 = 1127;
      LODWORD(v19) = 956;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        1127,
        L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
        v19,
        L"EasUpdateDeviceLockoutState",
        &pPassword);
      goto LABEL_25;
    }
    *v24 = 1;
  }
LABEL_22:
  v7 = SetLockoutCounter(pSid);
  if ( v7 )
  {
    LODWORD(v19) = 965;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      v7,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
      v19,
      L"SetLockoutCounter",
      &pPassword);
  }
  else
  {
    v7 = 0;
  }
LABEL_25:
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  return v7;
}

```

## disassembly

```asm
0x140097c70  mov     rax, rsp
0x140097c73  mov     [rax+18h], rbx
0x140097c77  mov     [rax+20h], r9
0x140097c7b  mov     [rax+10h], rdx
0x140097c7f  push    rbp
0x140097c80  push    rsi
0x140097c81  push    rdi
0x140097c82  push    r12
0x140097c84  push    r13
0x140097c86  sub     rsp, 50h
0x140097c8a  xor     ebx, ebx
0x140097c8c  lea     r12, pPassword
0x140097c93  mov     r13d, r8d
0x140097c96  mov     rsi, rcx
0x140097c99  mov     edi, ebx
0x140097c9b  mov     [rax-30h], rbx
0x140097c9f  mov     [rax-38h], ebx
0x140097ca2  mov     [r9], ebx
0x140097ca5  cmp     [rcx], ebx
0x140097ca7  jnz     short loc_140097CE2
0x140097ca9  mov     [rax-48h], r12
0x140097cad  lea     ebx, [rdi+15h]
0x140097cb0  lea     rax, aNotInitialized; "Not Initialized"
0x140097cb7  mov     [rsp+78h+var_50], rax
0x140097cbc  lea     ecx, [rdi+1]; unsigned int
0x140097cbf  mov     dword ptr [rsp+78h+var_58], 371h
0x140097cc7  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x140097cce  mov     r8d, ebx
0x140097cd1  lea     r9, aOnecoreDsSecur_2; "onecore\\ds\\security\\eas\\policyengin"...
0x140097cd8  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x140097cdd  jmp     loc_140097F20
0x140097ce2  mov     ebp, 1
0x140097ce7  cmp     [rcx+4], ebx
0x140097cea  jz      loc_140097ED4
0x140097cf0  mov     r8, rdx; void *
0x140097cf3  mov     [rsp+78h+arg_0], ebx
0x140097cfa  mov     edx, [rcx+20h]; unsigned int
0x140097cfd  lea     r9, [rsp+78h+arg_0]; int *
0x140097d05  mov     rcx, [rcx+18h]; struct _USER_COUNT_ENTRY *
0x140097d09  call    ?FindEASLockOutEntryForSID@@YAHPEAU_USER_COUNT_ENTRY@@KPEAXPEAH@Z; FindEASLockOutEntryForSID(_USER_COUNT_ENTRY *,ulong,void *,int *)
0x140097d0e  test    eax, eax
0x140097d10  jz      short loc_140097D33
0x140097d12  mov     eax, [rsp+78h+arg_0]
0x140097d19  mov     rcx, [rsi+18h]
0x140097d1d  add     rax, rax
0x140097d20  cmp     [rcx+rax*8], r13d
0x140097d24  jz      loc_140097ED4
0x140097d2a  mov     [rcx+rax*8], r13d
0x140097d2e  jmp     loc_140097DD7
0x140097d33  test    r13d, r13d
0x140097d36  jz      loc_140097ED4
0x140097d3c  mov     eax, [rsi+20h]
0x140097d3f  cmp     eax, [rsi+24h]
0x140097d42  jb      short loc_140097D69
0x140097d44  mov     [rsp+78h+var_48], r12
0x140097d49  lea     rax, aNoMoreRoomForN; "No more room for new entry"
0x140097d50  mov     [rsp+78h+var_50], rax
0x140097d55  mov     ebx, 8
0x140097d5a  mov     dword ptr [rsp+78h+var_58], 391h
0x140097d62  mov     ecx, ebp
0x140097d64  jmp     loc_140097CC7
0x140097d69  mov     r9d, [rsp+78h+arg_0]
0x140097d71  cmp     eax, r9d
0x140097d74  jbe     short loc_140097D98
0x140097d76  mov     rdx, [rsi+18h]
0x140097d7a  lea     r8d, [rax-1]
0x140097d7e  add     rax, rax
0x140097d81  mov     ecx, r8d
0x140097d84  add     rcx, rcx
0x140097d87  movups  xmm0, xmmword ptr [rdx+rcx*8]
0x140097d8b  movdqu  xmmword ptr [rdx+rax*8], xmm0
0x140097d90  mov     eax, r8d
0x140097d93  cmp     r8d, r9d
0x140097d96  ja      short loc_140097D76
0x140097d98  mov     rax, [rsi+18h]
0x140097d9c  lea     rbx, [rsi+28h]
0x140097da0  mov     rcx, [rsp+78h+pSid]; pSid
0x140097da8  mov     rdi, r9
0x140097dab  add     rdi, rdi
0x140097dae  mov     [rax+rdi*8], r13d
0x140097db2  call    cs:__imp_GetLengthSid
0x140097db8  mov     rdx, [rsp+78h+pSid]; Src
0x140097dc0  mov     rcx, rbx; void *
0x140097dc3  mov     r8d, eax; Size
0x140097dc6  call    memcpy_0
0x140097dcb  mov     rax, [rsi+18h]
0x140097dcf  mov     [rax+rdi*8+8], rbx
0x140097dd4  add     [rsi+20h], ebp
0x140097dd7  mov     edx, [rsi+20h]; unsigned int
0x140097dda  lea     r9, [rsp+78h+var_38]; unsigned int *
0x140097ddf  mov     rcx, [rsi+18h]; struct _USER_COUNT_ENTRY *
0x140097de3  lea     r8, [rsp+78h+lpMem]; unsigned __int8 **
0x140097de8  call    ?PackEASLockoutData@@YAKPEAU_USER_COUNT_ENTRY@@KPEAPEAEPEAK@Z; PackEASLockoutData(_USER_COUNT_ENTRY *,ulong,uchar * *,ulong *)
0x140097ded  mov     ebx, eax
0x140097def  test    eax, eax
0x140097df1  jz      short loc_140097E2E
0x140097df3  lea     rax, aPackeaslockout; "PackEASLockoutData"
0x140097dfa  mov     [rsp+78h+var_48], r12
0x140097dff  mov     [rsp+78h+var_50], rax
0x140097e04  lea     r9, aOnecoreDsSecur_2; "onecore\\ds\\security\\eas\\policyengin"...
0x140097e0b  mov     r8d, ebx
0x140097e0e  mov     dword ptr [rsp+78h+var_58], 3ADh
0x140097e16  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x140097e1d  mov     ecx, ebp; unsigned int
0x140097e1f  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x140097e24  mov     rdi, [rsp+78h+lpMem]
0x140097e29  jmp     loc_140097F07
0x140097e2e  mov     rcx, [rsi+80h]
0x140097e35  mov     rdi, [rsp+78h+lpMem]
0x140097e3a  mov     r9d, [rsp+78h+var_38]
0x140097e3f  mov     r8, rdi
0x140097e42  mov     rdx, [rsi+78h]
0x140097e46  mov     rax, [rcx]
0x140097e49  mov     rax, [rax+38h]
0x140097e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097e52  mov     ebx, eax
0x140097e54  test    eax, eax
0x140097e56  jz      short loc_140097ED4
0x140097e58  mov     [rsp+78h+var_48], r12
0x140097e5d  lea     rsi, aEasupdatedevic; "EasUpdateDeviceLockoutState"
0x140097e64  mov     [rsp+78h+var_50], rsi
0x140097e69  lea     r9, aOnecoreDsSecur_2; "onecore\\ds\\security\\eas\\policyengin"...
0x140097e70  mov     r8d, eax
0x140097e73  mov     dword ptr [rsp+78h+var_58], 3B2h
0x140097e7b  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x140097e82  mov     ecx, ebp; unsigned int
0x140097e84  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x140097e89  cmp     ebx, 803100CFh
0x140097e8f  jz      short loc_140097ECA
0x140097e91  cmp     ebx, 88010009h
0x140097e97  jz      short loc_140097ECA
0x140097e99  mov     [rsp+78h+var_48], r12
0x140097e9e  mov     ebx, 467h
0x140097ea3  mov     [rsp+78h+var_50], rsi
0x140097ea8  mov     dword ptr [rsp+78h+var_58], 3BCh
0x140097eb0  lea     r9, aOnecoreDsSecur_2; "onecore\\ds\\security\\eas\\policyengin"...
0x140097eb7  mov     r8d, ebx
0x140097eba  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x140097ec1  mov     ecx, ebp; unsigned int
0x140097ec3  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x140097ec8  jmp     short loc_140097F07
0x140097eca  mov     rax, [rsp+78h+arg_18]
0x140097ed2  mov     [rax], ebp
0x140097ed4  mov     rcx, [rsp+78h+pSid]; Sid
0x140097edc  mov     edx, r13d
0x140097edf  call    SetLockoutCounter
0x140097ee4  mov     ebx, eax
0x140097ee6  test    eax, eax
0x140097ee8  jz      short loc_140097F05
0x140097eea  mov     [rsp+78h+var_48], r12
0x140097eef  lea     rax, aSetlockoutcoun; "SetLockoutCounter"
0x140097ef6  mov     [rsp+78h+var_50], rax
0x140097efb  mov     dword ptr [rsp+78h+var_58], 3C5h
0x140097f03  jmp     short loc_140097EB0
0x140097f05  xor     ebx, ebx
0x140097f07  test    rdi, rdi
0x140097f0a  jz      short loc_140097F20
0x140097f0c  call    cs:__imp_GetProcessHeap
0x140097f12  mov     r8, rdi; lpMem
0x140097f15  xor     edx, edx; dwFlags
0x140097f17  mov     rcx, rax; hHeap
0x140097f1a  call    cs:__imp_HeapFree
0x140097f20  mov     eax, ebx
0x140097f22  mov     rbx, [rsp+78h+arg_10]
0x140097f2a  add     rsp, 50h
0x140097f2e  pop     r13
0x140097f30  pop     r12
0x140097f32  pop     rdi
0x140097f33  pop     rsi
0x140097f34  pop     rbp
0x140097f35  retn
```
