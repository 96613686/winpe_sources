# VidExoIoControlPartition

- ea: `0x140037fd0`
- end: `0x1400383e6`
- name: `VidExoIoControlPartition`
- size: `1046`
- prototype: `__int64 __fastcall(int, int, int, int, int, NTSTRSAFE_PWSTR, int, int, ULONGLONG)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400339c0`

## callees

- `0x140012b3c`
- `0x140035698`
- `0x140037fd0`
- `0x140077d7c`
- `0x140083ebc`
- `0x14008413c`
- `0x140084554`
- `0x1400d2a74`
- `0x1400d2c98`
- `0x1400d30d4`
- `0x1400d3340`
- `0x1400d358c`

## import_xrefs

- `winhvr!WinHvSetVpState` at `0x14003823a`
- `winhvr!WinHvSetVpState` at `0x14003823a`
- `winhvr!WinHvGetVpState` at `0x1400382ab`
- `winhvr!WinHvGetVpState` at `0x1400382ab`
- `winhvr!WinHvInstallIntercept` at `0x140038171`
- `winhvr!WinHvInstallIntercept` at `0x140038171`
- `winhvr!WinHvRegisterInterceptResult` at `0x1400382e6`
- `winhvr!WinHvRegisterInterceptResult` at `0x1400382e6`

## pseudocode

```c
__int64 __fastcall VidExoIoControlPartition(
        char *a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        unsigned int a5,
        NTSTRSAFE_PWSTR pszDest,
        unsigned int a7,
        unsigned int a8,
        unsigned int *pullResult)
{
  __int64 result; // rax

  *pullResult = 0;
  if ( a8 <= 0x22131C )
  {
    if ( a8 == 2233116 )
    {
      if ( a5 >= 0x20 )
        return VsmmExoGpaRangeIoctlAccessTrackingControl(
                 (_DWORD)a1,
                 *(_QWORD *)a4,
                 *((_QWORD *)a4 + 1),
                 *((_QWORD *)a4 + 2),
                 a4[6]);
    }
    else
    {
      if ( a8 <= 0x221274 )
      {
        if ( a8 == 2232948 || a8 == 2232388 || a8 == 2232564 || a8 == 2232568 || a8 == 2232644 || a8 == 2232784 )
          return VidIoControlPartition(a1, a2, a3, a4, a5, pszDest, a7, a8, pullResult);
        goto LABEL_57;
      }
      if ( a8 == 2232964 || a8 == 2233084 )
        return VidIoControlPartition(a1, a2, a3, a4, a5, pszDest, a7, a8, pullResult);
      if ( a8 != 2233108 )
      {
        if ( a8 == 2233112 )
        {
          if ( a5 >= 0x10 )
            return VsmmExoGpaRangeIoctlUnmap(a1, *(_QWORD *)a4, *((_QWORD *)a4 + 1));
          return 3221225507LL;
        }
LABEL_57:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_53d96694b39d3dfcc5b4a99ce18d6688_Traceguids, a8);
        }
        return 3221225474LL;
      }
      if ( a5 >= 0x28 )
        return VsmmExoGpaRangeIoctlMap(
                 (int)a1,
                 *(_QWORD *)a4,
                 *((_QWORD *)a4 + 1),
                 *((_QWORD *)a4 + 2),
                 *((HANDLE *)a4 + 3),
                 a4[8],
                 a4[9]);
    }
    return 3221225507LL;
  }
  if ( a8 > 0x22133C )
  {
    switch ( a8 )
    {
      case 0x221340u:
        if ( (a5 & 0xF) == 0 )
          return VsmmExoGpaRangeIoctlPin(a1, a4, a5 >> 4);
        break;
      case 0x221344u:
        if ( (a5 & 0xF) == 0 )
          return VsmmExoGpaRangeIoctlUnpin(a1, a4, a5 >> 4);
        break;
      case 0x221348u:
        if ( a5 >= 0x10 )
          return VidExoBrokerIoctlSend((__int64)a1, a2, a4, a5);
        break;
      case 0x22134Cu:
        if ( a7 >= 0x10 )
          return VidExoBrokerIoctlReceive((__int64)a1, a3, (unsigned int *)pszDest, a7, pullResult);
        break;
      default:
        goto LABEL_57;
    }
    return 3221225485LL;
  }
  switch ( a8 )
  {
    case 0x22133Cu:
      if ( a5 >= 0x38 )
        return WinHvRegisterInterceptResult(*((_QWORD *)a1 + 81), *a4, a4[1], a4 + 2);
      return 3221225507LL;
    case 0x221324u:
      if ( a5 < 0x20 || !a7 )
        return 3221225507LL;
      if ( a7 <= 0x1FB000 && ((a4[2] & 0x80000000) != 0 || a7 <= 0x1000) )
      {
        LOBYTE(a3) = *((_BYTE *)a4 + 4);
        result = WinHvGetVpState(*((_QWORD *)a1 + 81), *a4, a3);
        if ( (int)result >= 0 )
          *pullResult = a7;
        return result;
      }
      return 2147483653LL;
    case 0x221328u:
      if ( a5 <= 0x20 )
        return 3221225507LL;
      if ( a5 - 32 <= 0x1FB000 && ((a4[2] & 0x80000000) != 0 || a5 - 32 <= 0xFD8) )
      {
        LOBYTE(a3) = *((_BYTE *)a4 + 4);
        return WinHvSetVpState(*((_QWORD *)a1 + 81), *a4, a3);
      }
      return 2147483653LL;
    case 0x22132Cu:
      if ( a5 >= 0x20 )
        return VidExoVpIoctlCreate(a1, *a4, *((_BYTE *)a4 + 4), (__int128 *)(a4 + 2), *((HANDLE *)a4 + 3));
      return 3221225485LL;
  }
  if ( a8 != 2233140 )
  {
    if ( a8 != 2233144 )
      goto LABEL_57;
    if ( a5 >= 0x18 )
      return WinHvInstallIntercept(*((_QWORD *)a1 + 81), *a4, a4 + 2);
    return 3221225507LL;
  }
  if ( a5 < 4 )
    return 3221225485LL;
  if ( a7 < 0x20 )
    return 3221225507LL;
  result = VidExoVpIoctlMap((__int64)a1, a3, *a4, pszDest);
  if ( (int)result >= 0 )
    *pullResult = 32;
  return result;
}

```

## disassembly

```asm
0x140037fd0  mov     [rsp+arg_0], rbx
0x140037fd5  push    rdi
0x140037fd6  sub     rsp, 50h
0x140037fda  mov     rdi, [rsp+58h+arg_40]
0x140037fe2  mov     r10, r9
0x140037fe5  mov     r9d, [rsp+58h+arg_38]
0x140037fed  mov     eax, 22131Ch
0x140037ff2  mov     r11, r8
0x140037ff5  mov     dword ptr [rdi], 0
0x140037ffb  cmp     r9d, eax
0x140037ffe  ja      loc_140038117
0x140038004  jz      loc_1400380F0
0x14003800a  mov     eax, 221274h
0x14003800f  cmp     r9d, eax
0x140038012  ja      short loc_140038076
0x140038014  jz      short loc_14003803C
0x140038016  mov     eax, r9d
0x140038019  sub     eax, 221044h
0x14003801e  jz      short loc_14003803C
0x140038020  sub     eax, 0B0h
0x140038025  jz      short loc_14003803C
0x140038027  sub     eax, 4
0x14003802a  jz      short loc_14003803C
0x14003802c  sub     eax, 4Ch ; 'L'
0x14003802f  jz      short loc_14003803C
0x140038031  cmp     eax, 8Ch
0x140038036  jnz     loc_140038318
0x14003803c  mov     eax, [rsp+58h+arg_30]
0x140038043  mov     [rsp+58h+pullResult], rdi; pullResult
0x140038048  mov     [rsp+58h+var_20], r9d; int
0x14003804d  mov     r9, r10
0x140038050  mov     [rsp+58h+var_28], eax; int
0x140038054  mov     rax, [rsp+58h+arg_28]
0x14003805c  mov     [rsp+58h+pszDest], rax; pszDest
0x140038061  mov     eax, [rsp+58h+arg_20]
0x140038068  mov     dword ptr [rsp+58h+Handle], eax; int
0x14003806c  call    VidIoControlPartition
0x140038071  jmp     loc_1400383DA
0x140038076  mov     eax, r9d
0x140038079  sub     eax, 221284h
0x14003807e  jz      short loc_14003803C
0x140038080  sub     eax, 78h ; 'x'
0x140038083  jz      short loc_14003803C
0x140038085  sub     eax, 18h
0x140038088  jz      short loc_1400380AE
0x14003808a  cmp     eax, 4
0x14003808d  jnz     loc_140038318
0x140038093  cmp     [rsp+58h+arg_20], 10h
0x14003809b  jb      short loc_1400380B8
0x14003809d  mov     r8, [r10+8]
0x1400380a1  mov     rdx, [r10]
0x1400380a4  call    VsmmExoGpaRangeIoctlUnmap
0x1400380a9  jmp     loc_1400383DA
0x1400380ae  cmp     [rsp+58h+arg_20], 28h ; '('
0x1400380b6  jnb     short loc_1400380C2
0x1400380b8  mov     eax, 0C0000023h
0x1400380bd  jmp     loc_1400383DA
0x1400380c2  mov     eax, [r10+24h]
0x1400380c6  mov     r9, [r10+10h]; int
0x1400380ca  mov     r8, [r10+8]; int
0x1400380ce  mov     rdx, [r10]; int
0x1400380d1  mov     [rsp+58h+var_28], eax; int
0x1400380d5  mov     eax, [r10+20h]
0x1400380d9  mov     dword ptr [rsp+58h+pszDest], eax; int
0x1400380dd  mov     rax, [r10+18h]
0x1400380e1  mov     [rsp+58h+Handle], rax; Handle
0x1400380e6  call    VsmmExoGpaRangeIoctlMap
0x1400380eb  jmp     loc_1400383DA
0x1400380f0  cmp     [rsp+58h+arg_20], 20h ; ' '
0x1400380f8  jb      short loc_1400380B8
0x1400380fa  mov     eax, [r10+18h]
0x1400380fe  mov     r9, [r10+10h]
0x140038102  mov     r8, [r10+8]
0x140038106  mov     rdx, [r10]
0x140038109  mov     dword ptr [rsp+58h+Handle], eax
0x14003810d  call    VsmmExoGpaRangeIoctlAccessTrackingControl
0x140038112  jmp     loc_1400383DA
0x140038117  mov     eax, 22133Ch
0x14003811c  cmp     r9d, eax
0x14003811f  ja      loc_1400382F7
0x140038125  jz      loc_1400382C6
0x14003812b  mov     eax, r9d
0x14003812e  sub     eax, 221324h
0x140038133  jz      loc_14003824B
0x140038139  sub     eax, 4
0x14003813c  jz      loc_1400381F2
0x140038142  sub     eax, 4
0x140038145  jz      short loc_1400381C0
0x140038147  sub     eax, 8
0x14003814a  jz      short loc_140038182
0x14003814c  cmp     eax, 4
0x14003814f  jnz     loc_140038318
0x140038155  cmp     [rsp+58h+arg_20], 18h
0x14003815d  jb      loc_1400380B8
0x140038163  mov     edx, [r10]
0x140038166  lea     r8, [r10+8]
0x14003816a  mov     rcx, [rcx+288h]
0x140038171  call    cs:__imp_WinHvInstallIntercept
0x140038178  nop     dword ptr [rax+rax+00h]
0x14003817d  jmp     loc_1400383DA
0x140038182  cmp     [rsp+58h+arg_20], 4
0x14003818a  jb      short loc_1400381CA
0x14003818c  cmp     [rsp+58h+arg_30], 20h ; ' '
0x140038194  jb      loc_1400380B8
0x14003819a  mov     r9, [rsp+58h+arg_28]
0x1400381a2  mov     rdx, r11
0x1400381a5  mov     r8d, [r10]
0x1400381a8  call    VidExoVpIoctlMap
0x1400381ad  test    eax, eax
0x1400381af  js      loc_1400383DA
0x1400381b5  mov     dword ptr [rdi], 20h ; ' '
0x1400381bb  jmp     loc_1400383DA
0x1400381c0  cmp     [rsp+58h+arg_20], 20h ; ' '
0x1400381c8  jnb     short loc_1400381D4
0x1400381ca  mov     eax, 0C000000Dh
0x1400381cf  jmp     loc_1400383DA
0x1400381d4  mov     rax, [r10+18h]
0x1400381d8  lea     r9, [r10+8]
0x1400381dc  mov     r8b, [r10+4]
0x1400381e0  mov     edx, [r10]
0x1400381e3  mov     [rsp+58h+Handle], rax; Handle
0x1400381e8  call    VidExoVpIoctlCreate
0x1400381ed  jmp     loc_1400383DA
0x1400381f2  mov     edx, [rsp+58h+arg_20]
0x1400381f9  cmp     edx, 20h ; ' '
0x1400381fc  jbe     loc_1400380B8
0x140038202  add     edx, 0FFFFFFE0h
0x140038205  cmp     edx, 1FB000h
0x14003820b  ja      short loc_140038270
0x14003820d  lea     r9, [r10+8]
0x140038211  cmp     dword ptr [r9], 0
0x140038215  jl      short loc_14003821F
0x140038217  cmp     edx, 0FD8h
0x14003821d  ja      short loc_140038270
0x14003821f  mov     r8b, [r10+4]
0x140038223  lea     rax, [r10+20h]
0x140038227  mov     rcx, [rcx+288h]
0x14003822e  mov     dword ptr [rsp+58h+pszDest], edx
0x140038232  mov     edx, [r10]
0x140038235  mov     [rsp+58h+Handle], rax
0x14003823a  call    cs:__imp_WinHvSetVpState
0x140038241  nop     dword ptr [rax+rax+00h]
0x140038246  jmp     loc_1400383DA
0x14003824b  cmp     [rsp+58h+arg_20], 20h ; ' '
0x140038253  jb      loc_1400380B8
0x140038259  mov     ebx, [rsp+58h+arg_30]
0x140038260  test    ebx, ebx
0x140038262  jz      loc_1400380B8
0x140038268  cmp     ebx, 1FB000h
0x14003826e  jbe     short loc_14003827A
0x140038270  mov     eax, 80000005h
0x140038275  jmp     loc_1400383DA
0x14003827a  lea     r9, [r10+8]
0x14003827e  cmp     dword ptr [r9], 0
0x140038282  jl      short loc_14003828C
0x140038284  cmp     ebx, 1000h
0x14003828a  ja      short loc_140038270
0x14003828c  mov     rax, [rsp+58h+arg_28]
0x140038294  mov     r8b, [r10+4]
0x140038298  mov     edx, [r10]
0x14003829b  mov     rcx, [rcx+288h]
0x1400382a2  mov     dword ptr [rsp+58h+pszDest], ebx
0x1400382a6  mov     [rsp+58h+Handle], rax
0x1400382ab  call    cs:__imp_WinHvGetVpState
0x1400382b2  nop     dword ptr [rax+rax+00h]
0x1400382b7  test    eax, eax
0x1400382b9  js      loc_1400383DA
0x1400382bf  mov     [rdi], ebx
0x1400382c1  jmp     loc_1400383DA
0x1400382c6  cmp     [rsp+58h+arg_20], 38h ; '8'
0x1400382ce  jb      loc_1400380B8
0x1400382d4  mov     r8d, [r10+4]
0x1400382d8  lea     r9, [r10+8]
0x1400382dc  mov     edx, [r10]
0x1400382df  mov     rcx, [rcx+288h]
0x1400382e6  call    cs:__imp_WinHvRegisterInterceptResult
0x1400382ed  nop     dword ptr [rax+rax+00h]
0x1400382f2  jmp     loc_1400383DA
0x1400382f7  mov     eax, r9d
0x1400382fa  sub     eax, 221340h
0x1400382ff  jz      loc_1400383BC
0x140038305  sub     eax, 4
0x140038308  jz      loc_14003839C
0x14003830e  sub     eax, 4
0x140038311  jz      short loc_140038380
0x140038313  cmp     eax, 4
0x140038316  jz      short loc_140038357
0x140038318  mov     rcx, cs:WPP_GLOBAL_Control
0x14003831f  lea     rax, WPP_GLOBAL_Control
0x140038326  cmp     rcx, rax
0x140038329  jz      short loc_14003834D
0x14003832b  mov     eax, [rcx+2Ch]
0x14003832e  test    al, 1
0x140038330  jz      short loc_14003834D
0x140038332  cmp     byte ptr [rcx+29h], 3
0x140038336  jb      short loc_14003834D
0x140038338  mov     rcx, [rcx+18h]
0x14003833c  lea     r8, WPP_53d96694b39d3dfcc5b4a99ce18d6688_Traceguids
0x140038343  mov     edx, 0Ah
0x140038348  call    WPP_SF_d
0x14003834d  mov     eax, 0C0000002h
0x140038352  jmp     loc_1400383DA
0x140038357  mov     r9d, [rsp+58h+arg_30]
0x14003835f  cmp     r9d, 10h
0x140038363  jb      loc_1400381CA
0x140038369  mov     r8, [rsp+58h+arg_28]
0x140038371  mov     rdx, r11
0x140038374  mov     [rsp+58h+Handle], rdi
0x140038379  call    VidExoBrokerIoctlReceive
0x14003837e  jmp     short loc_1400383DA
0x140038380  mov     r9d, [rsp+58h+arg_20]
0x140038388  cmp     r9d, 10h
0x14003838c  jb      loc_1400381CA
0x140038392  mov     r8, r10
0x140038395  call    VidExoBrokerIoctlSend
0x14003839a  jmp     short loc_1400383DA
0x14003839c  mov     r8d, [rsp+58h+arg_20]
0x1400383a4  test    r8b, 0Fh
0x1400383a8  jnz     loc_1400381CA
0x1400383ae  shr     r8d, 4
0x1400383b2  mov     rdx, r10
0x1400383b5  call    VsmmExoGpaRangeIoctlUnpin
0x1400383ba  jmp     short loc_1400383DA
0x1400383bc  mov     r8d, [rsp+58h+arg_20]
0x1400383c4  test    r8b, 0Fh
0x1400383c8  jnz     loc_1400381CA
0x1400383ce  shr     r8d, 4
0x1400383d2  mov     rdx, r10
0x1400383d5  call    VsmmExoGpaRangeIoctlPin
0x1400383da  mov     rbx, [rsp+58h+arg_0]
0x1400383df  add     rsp, 50h
0x1400383e3  pop     rdi
0x1400383e4  retn
```
