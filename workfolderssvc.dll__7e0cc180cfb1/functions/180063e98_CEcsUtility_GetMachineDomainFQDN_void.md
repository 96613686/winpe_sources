# CEcsUtility::GetMachineDomainFQDN(void)

- ea: `0x180063e98`
- end: `0x1800640ae`
- name: `?GetMachineDomainFQDN@CEcsUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180068e90`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180008bdc`
- `0x180011314`
- `0x180063de4`
- `0x180063e58`
- `0x180063e98`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x180063f70`
- `KERNEL32!GetComputerNameExW` at `0x180063feb`
- `KERNEL32!GetComputerNameExW` at `0x180063f70`
- `KERNEL32!GetComputerNameExW` at `0x180063feb`
- `KERNEL32!GetLastError` at `0x180063f7e`
- `KERNEL32!GetLastError` at `0x180063f7e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CEcsUtility::GetMachineDomainFQDN(__int64 a1)
{
  _BYTE *v2; // rax
  char v3; // cl
  signed int LastError; // ecx
  int v5; // ecx
  WCHAR *v6; // rdx
  LPWSTR v7; // rdx
  signed int pExceptionObject; // [rsp+20h] [rbp-19h] BYREF
  DWORD nSize; // [rsp+24h] [rbp-15h] BYREF
  signed int LastFailureAsHRESULT; // [rsp+28h] [rbp-11h] BYREF
  int v12; // [rsp+2Ch] [rbp-Dh]
  char v13; // [rsp+30h] [rbp-9h]
  const char *v14; // [rsp+38h] [rbp-1h]
  __int64 v15; // [rsp+40h] [rbp+7h]
  int v16; // [rsp+48h] [rbp+Fh]
  __int64 v17; // [rsp+50h] [rbp+17h]
  __int64 v18; // [rsp+58h] [rbp+1Fh] BYREF
  LPWSTR lpBuffer; // [rsp+60h] [rbp+27h]
  WCHAR v20[16]; // [rsp+68h] [rbp+2Fh] BYREF

  v17 = a1;
  v16 = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_4f001c020e34317e4477aefd97702a6b_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
  }
  if ( (v2[68] & 2) != 0 && v2[65] >= 6u )
  {
    v3 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v3 = 0;
LABEL_9:
  LastFailureAsHRESULT = 0;
  v12 = 96;
  v13 = v3;
  v14 = "CEcsUtility::GetMachineDomainFQDN";
  v15 = 0;
  v18 = 15;
  lpBuffer = 0;
  memset(v20, 0, 30);
  nSize = 15;
  if ( !GetComputerNameExW(ComputerNameDnsDomain, v20, &nSize) )
  {
    LastError = GetLastError();
    if ( LastError != 234 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LastFailureAsHRESULT = LastError;
      HIWORD(v12) = 116;
      pExceptionObject = LastError;
      throw (long *)&pExceptionObject;
    }
    v5 = CEcsPreallocArray<unsigned short,15>::Alloc(&v18, nSize);
    LastFailureAsHRESULT = v5;
    if ( v5 < 0 )
    {
      HIWORD(v12) = 109;
      pExceptionObject = v5;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v12) = 109;
    nSize = v18;
    LastFailureAsHRESULT = v5;
    v6 = v20;
    if ( lpBuffer )
      v6 = lpBuffer;
    if ( !GetComputerNameExW(ComputerNameDnsDomain, v6, &nSize) )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      HIWORD(v12) = 112;
      pExceptionObject = LastFailureAsHRESULT;
      throw (long *)&pExceptionObject;
    }
    LastFailureAsHRESULT = 0;
    LOWORD(v12) = 112;
  }
  v7 = v20;
  if ( lpBuffer )
    v7 = lpBuffer;
  std::wstring::wstring(a1, v7);
  v16 = 1;
  CEcsPreallocArray<unsigned short,15>::Clear(&v18);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
  return a1;
}

```

## disassembly

```asm
0x180063e98  mov     [rsp-8+arg_8], rbx
0x180063e9d  push    rbp
0x180063e9e  lea     rbp, [rsp-57h]
0x180063ea3  sub     rsp, 90h
0x180063eaa  mov     rax, cs:__security_cookie
0x180063eb1  xor     rax, rsp
0x180063eb4  mov     [rbp+57h+var_8], rax
0x180063eb8  mov     rbx, rcx
0x180063ebb  mov     [rbp+57h+var_40], rcx
0x180063ebf  mov     [rbp+57h+var_48], 0
0x180063ec6  lea     rcx, WPP_GLOBAL_Control
0x180063ecd  mov     rax, cs:WPP_GLOBAL_Control
0x180063ed4  cmp     rax, rcx
0x180063ed7  jz      short loc_180063F01
0x180063ed9  test    byte ptr [rax+44h], 2
0x180063edd  jz      short loc_180063F11
0x180063edf  cmp     byte ptr [rax+41h], 6
0x180063ee3  jb      short loc_180063F01
0x180063ee5  mov     edx, 0Dh
0x180063eea  lea     r8, WPP_4f001c020e34317e4477aefd97702a6b_Traceguids
0x180063ef1  mov     rcx, [rax+38h]
0x180063ef5  call    WPP_SF_
0x180063efa  mov     rax, cs:WPP_GLOBAL_Control
0x180063f01  test    byte ptr [rax+44h], 2
0x180063f05  jz      short loc_180063F11
0x180063f07  cmp     byte ptr [rax+41h], 6
0x180063f0b  jb      short loc_180063F11
0x180063f0d  mov     cl, 1
0x180063f0f  jmp     short loc_180063F13
0x180063f11  xor     cl, cl
0x180063f13  mov     [rbp+57h+var_68], 0
0x180063f1a  mov     [rbp+57h+var_64], 60h ; '`'
0x180063f21  mov     [rbp+57h+var_60], cl
0x180063f24  lea     rax, aCecsutilityGet_0; "CEcsUtility::GetMachineDomainFQDN"
0x180063f2b  mov     [rbp+57h+var_58], rax
0x180063f2f  mov     [rbp+57h+var_50], 0
0x180063f37  mov     [rbp+57h+var_38], 0Fh
0x180063f3f  mov     [rbp+57h+lpBuffer], 0
0x180063f47  xorps   xmm0, xmm0
0x180063f4a  movups  xmmword ptr [rbp+57h+var_28], xmm0
0x180063f4e  movups  xmmword ptr [rbp+57h+var_28+0Eh], xmm0
0x180063f52  mov     eax, dword ptr [rbp+57h+var_38]
0x180063f55  mov     [rbp+57h+nSize], eax
0x180063f58  lea     rdx, [rbp+57h+var_28]
0x180063f5c  mov     rax, [rbp+57h+lpBuffer]
0x180063f60  test    rax, rax
0x180063f63  cmovnz  rdx, rax; lpBuffer
0x180063f67  lea     r8, [rbp+57h+nSize]; nSize
0x180063f6b  mov     ecx, 2; NameType
0x180063f70  call    cs:__imp_GetComputerNameExW
0x180063f76  test    eax, eax
0x180063f78  jnz     loc_18006402A
0x180063f7e  call    cs:__imp_GetLastError
0x180063f84  mov     ecx, eax
0x180063f86  cmp     eax, 0EAh
0x180063f8b  jnz     loc_18006407B
0x180063f91  mov     edx, [rbp+57h+nSize]
0x180063f94  lea     rcx, [rbp+57h+var_38]
0x180063f98  call    ?Alloc@?$CEcsPreallocArray@G$0P@@@QEAAJ_K@Z; CEcsPreallocArray<ushort,15>::Alloc(unsigned __int64)
0x180063f9d  mov     ecx, eax
0x180063f9f  mov     [rbp+57h+var_68], eax
0x180063fa2  mov     [rbp+57h+var_68], eax
0x180063fa5  test    eax, eax
0x180063fa7  mov     eax, 6Dh ; 'm'
0x180063fac  jns     short loc_180063FC6
0x180063fae  mov     word ptr [rbp+57h+var_64+2], ax
0x180063fb2  mov     [rbp+57h+pExceptionObject], ecx
0x180063fb5  lea     rdx, _TI1J; pThrowInfo
0x180063fbc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180063fc0  call    _CxxThrowException_0
0x180063fc6  mov     word ptr [rbp+57h+var_64], ax
0x180063fca  mov     eax, dword ptr [rbp+57h+var_38]
0x180063fcd  mov     [rbp+57h+nSize], eax
0x180063fd0  mov     [rbp+57h+var_68], ecx
0x180063fd3  lea     rdx, [rbp+57h+var_28]
0x180063fd7  mov     rax, [rbp+57h+lpBuffer]
0x180063fdb  test    rax, rax
0x180063fde  cmovnz  rdx, rax; lpBuffer
0x180063fe2  lea     r8, [rbp+57h+nSize]; nSize
0x180063fe6  mov     ecx, 2; NameType
0x180063feb  call    cs:__imp_GetComputerNameExW
0x180063ff1  test    eax, eax
0x180063ff3  jnz     short loc_18006401A
0x180063ff5  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180063ffa  mov     [rbp+57h+var_68], eax
0x180063ffd  mov     ecx, 70h ; 'p'
0x180064002  mov     word ptr [rbp+57h+var_64+2], cx
0x180064006  mov     [rbp+57h+pExceptionObject], eax
0x180064009  lea     rdx, _TI1J; pThrowInfo
0x180064010  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180064014  call    _CxxThrowException_0
0x18006401a  mov     [rbp+57h+var_68], 0
0x180064021  mov     ecx, 70h ; 'p'
0x180064026  mov     word ptr [rbp+57h+var_64], cx
0x18006402a  lea     rdx, [rbp+57h+var_28]
0x18006402e  mov     rcx, [rbp+57h+lpBuffer]
0x180064032  test    rcx, rcx
0x180064035  cmovnz  rdx, rcx
0x180064039  mov     rcx, rbx
0x18006403c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180064041  mov     [rbp+57h+var_48], 1
0x180064048  lea     rcx, [rbp+57h+var_38]
0x18006404c  call    ?Clear@?$CEcsPreallocArray@G$0P@@@QEAAXXZ; CEcsPreallocArray<ushort,15>::Clear(void)
0x180064051  nop
0x180064052  lea     rcx, [rbp+57h+var_68]; this
0x180064056  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18006405b  mov     rax, rbx
0x18006405e  mov     rcx, [rbp+57h+var_8]
0x180064062  xor     rcx, rsp; StackCookie
0x180064065  call    __security_check_cookie
0x18006406a  mov     rbx, [rsp+90h+arg_8]
0x180064072  add     rsp, 90h
0x180064079  pop     rbp
0x18006407a  retn
0x18006407b  mov     eax, [rbp+57h+var_68]
0x18006407e  mov     [rbp+57h+var_68], eax
0x180064081  test    ecx, ecx
0x180064083  jle     short loc_18006408E
0x180064085  movzx   ecx, cx
0x180064088  or      ecx, 80070000h
0x18006408e  mov     [rbp+57h+var_68], ecx
0x180064091  mov     eax, 74h ; 't'
0x180064096  mov     word ptr [rbp+57h+var_64+2], ax
0x18006409a  mov     [rbp+57h+pExceptionObject], ecx
0x18006409d  lea     rdx, _TI1J; pThrowInfo
0x1800640a4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800640a8  call    _CxxThrowException_0
```
