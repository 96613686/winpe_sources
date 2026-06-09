# DavConvertDriveLetterPathToUncPath

- ea: `0x180002ca0`
- end: `0x180003066`
- name: `DavConvertDriveLetterPathToUncPath`
- size: `966`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000a010`

## callees

- `0x180002ca0`
- `0x180005310`
- `0x180005568`
- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b93c`
- `0x18002cf56`
- `0x18002cfa0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180002e10`
- `msvcrt!_wcsicmp` at `0x180002e10`
- `ntdll!RtlAcquireResourceExclusive` at `0x180002d97`
- `ntdll!RtlAcquireResourceExclusive` at `0x180002d97`
- `ntdll!RtlReleaseResource` at `0x180002e2e`
- `ntdll!RtlReleaseResource` at `0x180002e2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f00`
- `KERNEL32!LocalFree` at `0x180002e48`
- `KERNEL32!LocalFree` at `0x180002e48`
- `KERNEL32!LocalAlloc` at `0x180002ef2`
- `KERNEL32!LocalAlloc` at `0x180002ef2`

## pseudocode

```c
__int64 __fastcall DavConvertDriveLetterPathToUncPath(wchar_t *a1, _QWORD *a2, __int64 a3)
{
  __int64 v5; // rbp
  unsigned __int64 v6; // rax
  wchar_t v7; // ax
  DWORD LogonId; // eax
  DWORD LastError; // ebx
  char *v10; // r14
  _QWORD *i; // rbx
  const wchar_t *v12; // rcx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ebp
  unsigned int v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  char *v19; // rax
  unsigned int v21; // [rsp+20h] [rbp-48h] BYREF
  _LUID DestinationLuid; // [rsp+28h] [rbp-40h] BYREF
  wchar_t String2; // [rsp+30h] [rbp-38h] BYREF
  int v24; // [rsp+32h] [rbp-36h]

  v21 = 0;
  DestinationLuid = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 314, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, a1);
  if ( !a1 )
    return 87;
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( a1[v6] );
  if ( v6 < 2 || a1[1] != 58 )
    return 87;
  v7 = *a1;
  v24 = 58;
  String2 = v7;
  LogonId = DavImpersonateAndGetLogonId(&DestinationLuid, (__int64)a2, a3);
  LastError = LogonId;
  if ( LogonId )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 315, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LogonId);
    return LastError;
  }
  if ( !RtlAcquireResourceExclusive(&Resource, 1u) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 316, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
    return 2140;
  }
  v10 = 0;
  if ( (unsigned int)DavGetUserEntry((LPVOID *)&DavUseObject, &DestinationLuid, &v21, 0) )
  {
LABEL_24:
    LastError = 2;
  }
  else
  {
    for ( i = *(_QWORD **)(DavUseObject + 16LL * v21); ; i = (_QWORD *)*i )
    {
      if ( !i )
        goto LABEL_24;
      v12 = (const wchar_t *)i[3];
      if ( v12 )
      {
        if ( !_wcsicmp(v12, &String2) )
          break;
      }
    }
    do
      ++v5;
    while ( a1[v5 + 2] );
    if ( (unsigned int)v5 > 0xFFFF || 2 * (unsigned __int64)(unsigned int)v5 > 0xFFFF )
    {
      LastError = 87;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v18 = 317;
        goto LABEL_38;
      }
    }
    else
    {
      v13 = *(_DWORD *)(i[2] + 4LL);
      if ( v13 > 0xFFFF || (v14 = v13 + 1, v14 > 0xFFFF) )
      {
        LastError = 87;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v18 = 318;
          goto LABEL_38;
        }
      }
      else if ( 2 * (unsigned __int64)v14 > 0xFFFF )
      {
        LastError = 87;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v18 = 319;
          goto LABEL_38;
        }
      }
      else
      {
        v15 = 2 * v5;
        v16 = v15 + 2 * v14;
        if ( v16 <= 0xFFFF )
        {
          v19 = (char *)LocalAlloc(0x40u, v16);
          v10 = v19;
          if ( v19 )
          {
            memcpy_0(v19, (const void *)(i[2] + 8LL), 2LL * *(unsigned int *)(i[2] + 4LL));
            memcpy_0(&v10[2 * *(unsigned int *)(i[2] + 4LL)], a1 + 2, v15);
            *a2 = v10;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 322, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v10);
            LastError = 0;
          }
          else
          {
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                321,
                WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids,
                LastError);
          }
        }
        else
        {
          LastError = 87;
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v18 = 320;
LABEL_38:
            WPP_SF_(v17[2], v18, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
          }
        }
      }
    }
  }
  RtlReleaseResource(&Resource);
  if ( LastError && v10 )
    LocalFree(v10);
  return LastError;
}

```

## disassembly

```asm
0x180002ca0  mov     r11, rsp
0x180002ca3  mov     [r11+18h], rbx
0x180002ca7  mov     [r11+20h], rbp
0x180002cab  push    rsi
0x180002cac  push    r12
0x180002cae  push    r13
0x180002cb0  push    r14
0x180002cb2  push    r15
0x180002cb4  sub     rsp, 40h
0x180002cb8  mov     rax, cs:__security_cookie
0x180002cbf  xor     rax, rsp
0x180002cc2  mov     [rsp+68h+var_30], rax
0x180002cc7  xor     r12d, r12d
0x180002cca  mov     r15, rdx
0x180002ccd  mov     [r11-48h], r12d
0x180002cd1  mov     rsi, rcx
0x180002cd4  mov     [r11-40h], r12
0x180002cd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cdf  lea     r14, WPP_GLOBAL_Control
0x180002ce6  lea     r13, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180002ced  cmp     rcx, r14
0x180002cf0  jz      short loc_180002D0C
0x180002cf2  test    byte ptr [rcx+1Ch], 2
0x180002cf6  jz      short loc_180002D0C
0x180002cf8  mov     rcx, [rcx+10h]
0x180002cfc  mov     edx, 13Ah
0x180002d01  mov     r9, rsi
0x180002d04  mov     r8, r13
0x180002d07  call    WPP_SF_S
0x180002d0c  test    rsi, rsi
0x180002d0f  jz      loc_180003038
0x180002d15  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180002d19  mov     rax, rbp
0x180002d1c  inc     rax
0x180002d1f  cmp     [rsi+rax*2], r12w
0x180002d24  jnz     short loc_180002D1C
0x180002d26  cmp     rax, 2
0x180002d2a  jb      loc_180003038
0x180002d30  mov     ecx, 3Ah ; ':'
0x180002d35  cmp     [rsi+2], cx
0x180002d39  jnz     loc_180003038
0x180002d3f  movzx   eax, word ptr [rsi]
0x180002d42  mov     [rsp+68h+var_36], ecx
0x180002d46  lea     rcx, [rsp+68h+DestinationLuid]; DestinationLuid
0x180002d4b  mov     [rsp+68h+String2], ax
0x180002d50  call    DavImpersonateAndGetLogonId
0x180002d55  mov     ebx, eax
0x180002d57  test    eax, eax
0x180002d59  jz      short loc_180002D8E
0x180002d5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d62  cmp     rcx, r14
0x180002d65  jz      loc_18000303D
0x180002d6b  test    byte ptr [rcx+1Ch], 1
0x180002d6f  jz      loc_18000303D
0x180002d75  mov     rcx, [rcx+10h]
0x180002d79  mov     edx, 13Bh
0x180002d7e  mov     r9d, eax
0x180002d81  mov     r8, r13
0x180002d84  call    WPP_SF_d
0x180002d89  jmp     loc_18000303D
0x180002d8e  mov     dl, 1; Wait
0x180002d90  lea     rcx, Resource; Resource
0x180002d97  call    cs:__imp_RtlAcquireResourceExclusive
0x180002d9d  test    al, al
0x180002d9f  jnz     short loc_180002DCE
0x180002da1  mov     rcx, cs:WPP_GLOBAL_Control
0x180002da8  cmp     rcx, r14
0x180002dab  jz      short loc_180002DC4
0x180002dad  test    byte ptr [rcx+1Ch], 1
0x180002db1  jz      short loc_180002DC4
0x180002db3  mov     rcx, [rcx+10h]
0x180002db7  mov     edx, 13Ch
0x180002dbc  mov     r8, r13
0x180002dbf  call    WPP_SF_
0x180002dc4  mov     ebx, 85Ch
0x180002dc9  jmp     loc_18000303D
0x180002dce  xor     r9d, r9d
0x180002dd1  lea     r8, [rsp+68h+var_48]
0x180002dd6  lea     rdx, [rsp+68h+DestinationLuid]
0x180002ddb  mov     r14, r12
0x180002dde  lea     rcx, DavUseObject
0x180002de5  call    DavGetUserEntry
0x180002dea  test    eax, eax
0x180002dec  jnz     short loc_180002E22
0x180002dee  mov     ecx, [rsp+68h+var_48]
0x180002df2  mov     rax, cs:DavUseObject
0x180002df9  add     rcx, rcx
0x180002dfc  mov     rbx, [rax+rcx*8]
0x180002e00  jmp     short loc_180002E1D
0x180002e02  mov     rcx, [rbx+18h]; String1
0x180002e06  test    rcx, rcx
0x180002e09  jz      short loc_180002E1A
0x180002e0b  lea     rdx, [rsp+68h+String2]; String2
0x180002e10  call    cs:__imp__wcsicmp
0x180002e16  test    eax, eax
0x180002e18  jz      short loc_180002E53
0x180002e1a  mov     rbx, [rbx]
0x180002e1d  test    rbx, rbx
0x180002e20  jnz     short loc_180002E02
0x180002e22  mov     ebx, 2
0x180002e27  lea     rcx, Resource; Resource
0x180002e2e  call    cs:__imp_RtlReleaseResource
0x180002e34  test    ebx, ebx
0x180002e36  jz      loc_18000303D
0x180002e3c  test    r14, r14
0x180002e3f  jz      loc_18000303D
0x180002e45  mov     rcx, r14; hMem
0x180002e48  call    cs:__imp_LocalFree
0x180002e4e  jmp     loc_18000303D
0x180002e53  inc     rbp
0x180002e56  cmp     [rsi+rbp*2+4], r12w
0x180002e5c  jnz     short loc_180002E53
0x180002e5e  mov     edx, 0FFFFh
0x180002e63  cmp     ebp, edx
0x180002e65  ja      loc_180003008
0x180002e6b  mov     eax, ebp
0x180002e6d  add     rax, rax
0x180002e70  cmp     rax, rdx
0x180002e73  ja      loc_180003008
0x180002e79  mov     rax, [rbx+10h]
0x180002e7d  mov     ecx, [rax+4]
0x180002e80  cmp     ecx, edx
0x180002e82  ja      loc_180002FD8
0x180002e88  inc     ecx
0x180002e8a  cmp     ecx, edx
0x180002e8c  ja      loc_180002FD8
0x180002e92  mov     eax, ecx
0x180002e94  add     rax, rax
0x180002e97  cmp     rax, rdx
0x180002e9a  ja      loc_180002FA8
0x180002ea0  add     ebp, ebp
0x180002ea2  lea     eax, ds:0[rcx*2]
0x180002ea9  add     eax, ebp
0x180002eab  cmp     eax, edx
0x180002ead  jbe     short loc_180002EEB
0x180002eaf  mov     ebx, 57h ; 'W'
0x180002eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ebb  lea     rax, WPP_GLOBAL_Control
0x180002ec2  cmp     rcx, rax
0x180002ec5  jz      loc_180002E27
0x180002ecb  test    byte ptr [rcx+1Ch], 1
0x180002ecf  jz      loc_180002E27
0x180002ed5  mov     edx, 140h
0x180002eda  mov     rcx, [rcx+10h]
0x180002ede  mov     r8, r13
0x180002ee1  call    WPP_SF_
0x180002ee6  jmp     loc_180002E27
0x180002eeb  mov     edx, eax; uBytes
0x180002eed  mov     ecx, 40h ; '@'; uFlags
0x180002ef2  call    cs:__imp_LocalAlloc
0x180002ef8  mov     r14, rax
0x180002efb  test    rax, rax
0x180002efe  jnz     short loc_180002F42
0x180002f00  call    cs:__imp_GetLastError
0x180002f06  mov     ebx, eax
0x180002f08  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f0f  lea     rax, WPP_GLOBAL_Control
0x180002f16  cmp     rcx, rax
0x180002f19  jz      loc_180002E27
0x180002f1f  test    byte ptr [rcx+1Ch], 1
0x180002f23  jz      loc_180002E27
0x180002f29  mov     rcx, [rcx+10h]
0x180002f2d  mov     edx, 141h
0x180002f32  mov     r9d, ebx
0x180002f35  mov     r8, r13
0x180002f38  call    WPP_SF_d
0x180002f3d  jmp     loc_180002E27
0x180002f42  mov     rdx, [rbx+10h]
0x180002f46  mov     rcx, r14; void *
0x180002f49  mov     r8d, [rdx+4]
0x180002f4d  add     rdx, 8; Src
0x180002f51  add     r8, r8; Size
0x180002f54  call    memcpy_0
0x180002f59  mov     rax, [rbx+10h]
0x180002f5d  lea     rdx, [rsi+4]; Src
0x180002f61  mov     r8d, ebp; Size
0x180002f64  mov     ecx, [rax+4]
0x180002f67  lea     rcx, [r14+rcx*2]; void *
0x180002f6b  call    memcpy_0
0x180002f70  mov     [r15], r14
0x180002f73  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f7a  lea     rax, WPP_GLOBAL_Control
0x180002f81  cmp     rcx, rax
0x180002f84  jz      short loc_180002FA0
0x180002f86  test    byte ptr [rcx+1Ch], 2
0x180002f8a  jz      short loc_180002FA0
0x180002f8c  mov     rcx, [rcx+10h]
0x180002f90  mov     edx, 142h
0x180002f95  mov     r9, r14
0x180002f98  mov     r8, r13
0x180002f9b  call    WPP_SF_S
0x180002fa0  mov     ebx, r12d
0x180002fa3  jmp     loc_180002E27
0x180002fa8  mov     ebx, 57h ; 'W'
0x180002fad  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fb4  lea     rax, WPP_GLOBAL_Control
0x180002fbb  cmp     rcx, rax
0x180002fbe  jz      loc_180002E27
0x180002fc4  test    byte ptr [rcx+1Ch], 1
0x180002fc8  jz      loc_180002E27
0x180002fce  mov     edx, 13Fh
0x180002fd3  jmp     loc_180002EDA
0x180002fd8  mov     ebx, 57h ; 'W'
0x180002fdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fe4  lea     rax, WPP_GLOBAL_Control
0x180002feb  cmp     rcx, rax
0x180002fee  jz      loc_180002E27
0x180002ff4  test    byte ptr [rcx+1Ch], 1
0x180002ff8  jz      loc_180002E27
0x180002ffe  mov     edx, 13Eh
0x180003003  jmp     loc_180002EDA
0x180003008  mov     ebx, 57h ; 'W'
0x18000300d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003014  lea     rax, WPP_GLOBAL_Control
0x18000301b  cmp     rcx, rax
0x18000301e  jz      loc_180002E27
0x180003024  test    byte ptr [rcx+1Ch], 1
0x180003028  jz      loc_180002E27
0x18000302e  mov     edx, 13Dh
0x180003033  jmp     loc_180002EDA
0x180003038  mov     ebx, 57h ; 'W'
0x18000303d  mov     eax, ebx
0x18000303f  mov     rcx, [rsp+68h+var_30]
0x180003044  xor     rcx, rsp; StackCookie
0x180003047  call    __security_check_cookie
0x18000304c  lea     r11, [rsp+68h+var_28]
0x180003051  mov     rbx, [r11+40h]
0x180003055  mov     rbp, [r11+48h]
0x180003059  mov     rsp, r11
0x18000305c  pop     r15
0x18000305e  pop     r14
0x180003060  pop     r13
0x180003062  pop     r12
0x180003064  pop     rsi
0x180003065  retn
```
