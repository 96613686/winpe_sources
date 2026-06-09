# Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18002bef0`
- end: `0x18002c0dc`
- name: `?OnAfterEvents@CNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `492`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001e0a8`
- `0x18002bef0`
- `0x1800319ae`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18002c090`
- `KERNEL32!FreeLibrary` at `0x18002c0cb`
- `KERNEL32!FreeLibrary` at `0x18002c090`
- `KERNEL32!FreeLibrary` at `0x18002c0cb`

## string_xrefs

- `0x18002bf32`: `Iphlpapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v8; // edi
  unsigned int v9; // r14d
  FARPROC v10; // rax
  unsigned int *v11; // rsi
  int v12; // esi
  FARPROC v13; // rax
  __int64 v14; // rcx
  unsigned int *v16; // [rsp+30h] [rbp-D0h] BYREF
  HMODULE hLibModule[3]; // [rsp+38h] [rbp-C8h] BYREF
  char v18; // [rsp+50h] [rbp-B0h]
  __int64 v19[3]; // [rsp+58h] [rbp-A8h] BYREF
  char v20; // [rsp+70h] [rbp-90h]
  __int64 v21[3]; // [rsp+78h] [rbp-88h] BYREF
  char v22; // [rsp+90h] [rbp-70h]
  __int64 v23; // [rsp+98h] [rbp-68h]
  _WORD v24[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v25; // [rsp+A4h] [rbp-5Ch]
  union _LARGE_INTEGER v26; // [rsp+B0h] [rbp-50h]
  __int128 v27; // [rsp+B8h] [rbp-48h]
  unsigned int *v28; // [rsp+E8h] [rbp-18h]
  int v29; // [rsp+F0h] [rbp-10h]
  unsigned int v30; // [rsp+F4h] [rbp-Ch]

  v23 = -2;
  v8 = 0;
  hLibModule[0] = 0;
  hLibModule[1] = (HMODULE)L"Iphlpapi.dll";
  hLibModule[2] = 0;
  v18 = 0;
  v19[0] = (__int64)hLibModule;
  v19[1] = (__int64)"GetIfTable2Ex";
  v19[2] = 0;
  v20 = 0;
  v21[0] = (__int64)hLibModule;
  v21[1] = (__int64)"FreeMibTable";
  v21[2] = 0;
  v22 = 0;
  v9 = 1;
  if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v19) )
    goto LABEL_8;
  if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v21) )
    goto LABEL_8;
  v16 = 0;
  v10 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v19);
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int **))v10)(0, &v16) )
    goto LABEL_8;
  v11 = v16;
  if ( !*v16 )
  {
LABEL_7:
    v13 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v21);
    ((void (__fastcall *)(unsigned int *))v13)(v16);
LABEL_8:
    v14 = *((_QWORD *)this + 1);
    if ( v14 )
      v9 = (*(__int64 (__fastcall **)(__int64, union _LARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)v14 + 96LL))(
             v14,
             a2,
             a3,
             a4);
    if ( hLibModule[0] )
      FreeLibrary(hLibModule[0]);
    return v9;
  }
  while ( 1 )
  {
    memset_0(v24, 0, 0x58u);
    v24[0] = a4;
    v26 = a2;
    v27 = SystemConfigExGuid;
    v25 = 36;
    v28 = &v11[338 * v8 + 2];
    v29 = 1352;
    v30 = a3;
    v12 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
            *((_QWORD *)this + 2),
            v24,
            0,
            0);
    if ( v12 < 0 )
      break;
    ++v8;
    v11 = v16;
    if ( v8 >= *v16 )
      goto LABEL_7;
  }
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002bef0  push    rbp
0x18002bef2  push    rbx
0x18002bef3  push    rsi
0x18002bef4  push    rdi
0x18002bef5  push    r12
0x18002bef7  push    r13
0x18002bef9  push    r14
0x18002befb  push    r15
0x18002befd  lea     rbp, [rsp-18h]
0x18002bf02  sub     rsp, 118h
0x18002bf09  mov     [rbp+50h+var_B8], 0FFFFFFFFFFFFFFFEh
0x18002bf11  mov     rax, cs:__security_cookie
0x18002bf18  xor     rax, rsp
0x18002bf1b  mov     [rbp+50h+var_50], rax
0x18002bf1f  mov     r13d, r9d
0x18002bf22  mov     r12d, r8d
0x18002bf25  mov     rbx, rdx
0x18002bf28  mov     r15, rcx
0x18002bf2b  xor     edi, edi
0x18002bf2d  mov     [rsp+150h+hLibModule], rdi
0x18002bf32  lea     rax, aIphlpapiDll; "Iphlpapi.dll"
0x18002bf39  mov     [rsp+150h+var_110], rax
0x18002bf3e  mov     [rsp+150h+var_108], rdi
0x18002bf43  mov     [rsp+150h+var_100], dil
0x18002bf48  lea     rax, [rsp+150h+hLibModule]
0x18002bf4d  mov     [rsp+150h+var_F8], rax
0x18002bf52  lea     rax, aGetiftable2ex; "GetIfTable2Ex"
0x18002bf59  mov     [rsp+150h+var_F0], rax
0x18002bf5e  mov     [rsp+150h+var_E8], rdi
0x18002bf63  mov     [rsp+150h+var_E0], dil
0x18002bf68  lea     rax, [rsp+150h+hLibModule]
0x18002bf6d  mov     [rsp+150h+var_D8], rax
0x18002bf72  lea     rax, aFreemibtable; "FreeMibTable"
0x18002bf79  mov     [rbp+50h+var_D0], rax
0x18002bf7d  mov     [rbp+50h+var_C8], rdi
0x18002bf81  mov     [rbp+50h+var_C0], dil
0x18002bf85  lea     rcx, [rsp+150h+var_F8]
0x18002bf8a  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002bf8f  lea     r14d, [rdi+1]
0x18002bf93  test    rax, rax
0x18002bf96  jz      loc_18002C065
0x18002bf9c  lea     rcx, [rsp+150h+var_D8]
0x18002bfa1  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002bfa6  test    rax, rax
0x18002bfa9  jz      loc_18002C065
0x18002bfaf  mov     [rsp+150h+var_120], rdi
0x18002bfb4  lea     rcx, [rsp+150h+var_F8]
0x18002bfb9  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002bfbe  lea     rdx, [rsp+150h+var_120]
0x18002bfc3  xor     ecx, ecx
0x18002bfc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfca  test    eax, eax
0x18002bfcc  jnz     loc_18002C065
0x18002bfd2  mov     rsi, [rsp+150h+var_120]
0x18002bfd7  cmp     [rsi], edi
0x18002bfd9  jbe     short loc_18002C051
0x18002bfdb  xor     edx, edx; Val
0x18002bfdd  lea     r8d, [rdx+58h]; Size
0x18002bfe1  lea     rcx, [rbp+50h+var_B0]; void *
0x18002bfe5  call    memset_0
0x18002bfea  mov     [rbp+50h+var_B0], r13w
0x18002bfef  mov     [rbp+50h+var_A0], rbx
0x18002bff3  movups  xmm0, cs:SystemConfigExGuid
0x18002bffa  movdqu  [rbp+50h+var_98], xmm0
0x18002bfff  mov     [rbp+50h+var_AC], 24h ; '$'
0x18002c003  mov     eax, edi
0x18002c005  imul    rax, 548h
0x18002c00c  add     rax, 8
0x18002c010  add     rax, rsi
0x18002c013  mov     [rbp+50h+var_68], rax
0x18002c017  mov     [rbp+50h+var_60], 548h
0x18002c01e  mov     [rbp+50h+var_5C], r12d
0x18002c022  mov     rcx, [r15+10h]
0x18002c026  mov     rax, [rcx]
0x18002c029  xor     r9d, r9d
0x18002c02c  xor     r8d, r8d
0x18002c02f  lea     rdx, [rbp+50h+var_B0]
0x18002c033  mov     rax, [rax+0C0h]
0x18002c03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c03f  mov     esi, eax
0x18002c041  test    eax, eax
0x18002c043  js      short loc_18002C0C1
0x18002c045  add     edi, r14d
0x18002c048  mov     rsi, [rsp+150h+var_120]
0x18002c04d  cmp     edi, [rsi]
0x18002c04f  jb      short loc_18002BFDB
0x18002c051  lea     rcx, [rsp+150h+var_D8]
0x18002c056  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002c05b  mov     rcx, [rsp+150h+var_120]
0x18002c060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c065  mov     rcx, [r15+8]
0x18002c069  test    rcx, rcx
0x18002c06c  jz      short loc_18002C086
0x18002c06e  mov     rax, [rcx]
0x18002c071  mov     r9d, r13d
0x18002c074  mov     r8d, r12d
0x18002c077  mov     rdx, rbx
0x18002c07a  mov     rax, [rax+60h]
0x18002c07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c083  mov     r14d, eax
0x18002c086  mov     rcx, [rsp+150h+hLibModule]; hLibModule
0x18002c08b  test    rcx, rcx
0x18002c08e  jz      short loc_18002C09D
0x18002c090  call    cs:__imp_FreeLibrary
0x18002c097  nop     dword ptr [rax+rax+00h]
0x18002c09c  nop
0x18002c09d  mov     eax, r14d
0x18002c0a0  mov     rcx, [rbp+50h+var_50]
0x18002c0a4  xor     rcx, rsp; StackCookie
0x18002c0a7  call    __security_check_cookie
0x18002c0ac  add     rsp, 118h
0x18002c0b3  pop     r15
0x18002c0b5  pop     r14
0x18002c0b7  pop     r13
0x18002c0b9  pop     r12
0x18002c0bb  pop     rdi
0x18002c0bc  pop     rsi
0x18002c0bd  pop     rbx
0x18002c0be  pop     rbp
0x18002c0bf  retn
0x18002c0c1  mov     rcx, [rsp+150h+hLibModule]; hLibModule
0x18002c0c6  test    rcx, rcx
0x18002c0c9  jz      short loc_18002C0D8
0x18002c0cb  call    cs:__imp_FreeLibrary
0x18002c0d2  nop     dword ptr [rax+rax+00h]
0x18002c0d7  nop
0x18002c0d8  mov     eax, esi
0x18002c0da  jmp     short loc_18002C0A0
```
