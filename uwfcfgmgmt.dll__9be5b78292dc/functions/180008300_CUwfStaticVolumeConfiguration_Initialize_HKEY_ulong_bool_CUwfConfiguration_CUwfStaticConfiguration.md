# CUwfStaticVolumeConfiguration::Initialize(HKEY__ *,ulong,bool,CUwfConfiguration *,CUwfStaticConfiguration *)

- ea: `0x180008300`
- end: `0x180008419`
- name: `?Initialize@CUwfStaticVolumeConfiguration@@QEAAJPEAUHKEY__@@K_NPEAVCUwfConfiguration@@PEAVCUwfStaticConfiguration@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(CUwfStaticVolumeConfiguration *this, HKEY, unsigned int, char, struct CUwfConfiguration *, struct CUwfStaticConfiguration *)`
- caller_count: `11`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006c80`
- `0x180007ad0`
- `0x18000ac60`
- `0x18000b5c0`
- `0x18000b6b0`
- `0x18000b940`
- `0x180011130`
- `0x180016d84`
- `0x180018950`
- `0x1800193c0`
- `0x18001a620`

## callees

- `0x1800054d0`
- `0x180008300`
- `0x18000de30`
- `0x18000df60`
- `0x18000e96c`
- `0x18001b020`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::Initialize(
        CUwfStaticVolumeConfiguration *this,
        HKEY a2,
        unsigned int a3,
        char a4,
        struct CUwfConfiguration *a5,
        struct CUwfStaticConfiguration *a6)
{
  __int64 result; // rax
  bool v10; // di
  HKEY *v11; // rcx
  __int64 v12; // rax
  REGSAM v13; // r9d
  bool v14; // [rsp+30h] [rbp-58h] BYREF
  WCHAR SubKey[12]; // [rsp+38h] [rbp-50h] BYREF

  if ( !a2 )
    return 2147942487LL;
  if ( !a5 || !a6 )
    return 2147500035LL;
  *((_BYTE *)this + 10) = a4;
  v10 = 1;
  if ( !a4 )
  {
    v14 = 0;
    if ( CheckTokenMembershipHelper((enum WELL_KNOWN_SID_TYPE)this, &v14) >= 0 )
      v10 = !v14;
  }
  *((_BYTE *)this + 9) = v10;
  *((_QWORD *)this + 3) = a5;
  *((_QWORD *)this + 4) = a6;
  result = StringCchPrintfW(SubKey, 0xCu, L"%i", a3);
  if ( (int)result >= 0 )
  {
    v11 = (HKEY *)((char *)this + 16);
    v12 = *((_QWORD *)this + 3);
    v13 = *((_BYTE *)this + 9) != 0 ? 131097 : 131103;
    if ( *(_QWORD *)(v12 + 8) == -1 )
      result = CUwfRegKey::Open(v11, a2, SubKey, v13);
    else
      result = CUwfRegKey::OpenTransacted(v11, a2, SubKey, v13, *(HANDLE *)(v12 + 8));
    if ( (int)result >= 0 )
      *((_DWORD *)this + 3) = a3;
  }
  return result;
}

```

## disassembly

```asm
0x180008300  mov     [rsp+arg_18], rbx
0x180008305  push    rbp
0x180008306  push    rsi
0x180008307  push    rdi
0x180008308  push    r14
0x18000830a  push    r15
0x18000830c  sub     rsp, 60h
0x180008310  mov     rax, cs:__security_cookie
0x180008317  xor     rax, rsp
0x18000831a  mov     [rsp+88h+var_38], rax
0x18000831f  mov     r15d, r8d
0x180008322  mov     r14, rdx
0x180008325  mov     rbx, rcx
0x180008328  test    rdx, rdx
0x18000832b  jnz     short loc_180008337
0x18000832d  mov     eax, 80070057h
0x180008332  jmp     loc_1800083F8
0x180008337  mov     rsi, [rsp+88h+arg_20]
0x18000833f  test    rsi, rsi
0x180008342  jnz     short loc_18000834E
0x180008344  mov     eax, 80004003h
0x180008349  jmp     loc_1800083F8
0x18000834e  mov     rbp, [rsp+88h+arg_28]
0x180008356  test    rbp, rbp
0x180008359  jz      short loc_180008344
0x18000835b  mov     [rcx+0Ah], r9b
0x18000835f  mov     dil, 1
0x180008362  test    r9b, r9b
0x180008365  jnz     short loc_180008384
0x180008367  lea     rdx, [rsp+88h+var_58]; bool *
0x18000836c  mov     [rsp+88h+var_58], r9b
0x180008371  call    ?CheckTokenMembershipHelper@@YAJW4WELL_KNOWN_SID_TYPE@@PEA_N@Z; CheckTokenMembershipHelper(WELL_KNOWN_SID_TYPE,bool *)
0x180008376  test    eax, eax
0x180008378  js      short loc_180008384
0x18000837a  cmp     [rsp+88h+var_58], dil
0x18000837f  jnz     short loc_180008384
0x180008381  xor     dil, dil
0x180008384  mov     r9d, r15d
0x180008387  mov     [rbx+9], dil
0x18000838b  lea     r8, aI; "%i"
0x180008392  mov     [rbx+18h], rsi
0x180008396  mov     edx, 0Ch; unsigned __int64
0x18000839b  mov     [rbx+20h], rbp
0x18000839f  lea     rcx, [rsp+88h+SubKey]; unsigned __int16 *
0x1800083a4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800083a9  test    eax, eax
0x1800083ab  js      short loc_1800083F8
0x1800083ad  mov     al, [rbx+9]
0x1800083b0  lea     rcx, [rbx+10h]; phkResult
0x1800083b4  neg     al
0x1800083b6  mov     rdx, r14; hKey
0x1800083b9  mov     rax, [rbx+18h]
0x1800083bd  sbb     r9d, r9d
0x1800083c0  and     r9d, 0FFFFFFFAh
0x1800083c4  add     r9d, 2001Fh; samDesired
0x1800083cb  mov     r8, [rax+8]
0x1800083cf  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800083d3  jz      short loc_1800083E6
0x1800083d5  mov     [rsp+88h+var_68], r8; HANDLE
0x1800083da  lea     r8, [rsp+88h+SubKey]; lpSubKey
0x1800083df  call    ?OpenTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGKPEAX@Z; CUwfRegKey::OpenTransacted(HKEY__ *,ushort const *,ulong,void *)
0x1800083e4  jmp     short loc_1800083F0
0x1800083e6  lea     r8, [rsp+88h+SubKey]; lpSubKey
0x1800083eb  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800083f0  test    eax, eax
0x1800083f2  js      short loc_1800083F8
0x1800083f4  mov     [rbx+0Ch], r15d
0x1800083f8  mov     rcx, [rsp+88h+var_38]
0x1800083fd  xor     rcx, rsp; StackCookie
0x180008400  call    __security_check_cookie
0x180008405  mov     rbx, [rsp+88h+arg_18]
0x18000840d  add     rsp, 60h
0x180008411  pop     r15
0x180008413  pop     r14
0x180008415  pop     rdi
0x180008416  pop     rsi
0x180008417  pop     rbp
0x180008418  retn
```
