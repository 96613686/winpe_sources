# DavrDeleteConnection

- ea: `0x180007b50`
- end: `0x180007e08`
- name: `DavrDeleteConnection`
- size: `696`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800028c4`
- `0x180003cbc`
- `0x1800044a8`
- `0x180005310`
- `0x180005568`
- `0x180007b50`
- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b89c`
- `0x18000b93c`
- `0x18002cfa0`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180007cd5`
- `ntdll!RtlAcquireResourceExclusive` at `0x180007cd5`
- `ntdll!RtlReleaseResource` at `0x180007ddc`
- `ntdll!RtlReleaseResource` at `0x180007ddc`

## pseudocode

```c
__int64 __fastcall DavrDeleteConnection(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // ebx
  _WORD *v4; // rdi
  unsigned int v5; // esi
  unsigned __int64 v6; // rax
  unsigned int LogonId; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  unsigned int Use; // eax
  __int64 v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  unsigned int v18; // [rsp+30h] [rbp-38h] BYREF
  struct _LUID DestinationLuid; // [rsp+38h] [rbp-30h] BYREF
  __int64 v20; // [rsp+40h] [rbp-28h] BYREF
  __int64 v21; // [rsp+48h] [rbp-20h] BYREF
  _BYTE v22[8]; // [rsp+50h] [rbp-18h] BYREF

  v3 = a3;
  DestinationLuid = 0;
  v4 = (_WORD *)a2;
  v18 = 0;
  v20 = 0;
  v21 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, a2);
  DestinationLuid = 0;
  v5 = v3 != 0 ? 2 : 0;
  if ( !v4 )
    return 87;
  v6 = -1;
  do
    ++v6;
  while ( v4[v6] );
  if ( v6 < 2 )
    return 87;
  if ( *v4 == 92 )
    goto LABEL_19;
  if ( v4[1] != 58 )
    return 87;
  LogonId = DavCheckLocalName(v4, v22, a3);
  v8 = LogonId;
  if ( LogonId )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 59;
LABEL_14:
      WPP_SF_d(v9[2], v10, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LogonId);
      return v8;
    }
    return v8;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v22);
  v4 = v22;
LABEL_19:
  LogonId = DavImpersonateAndGetLogonId(&DestinationLuid, a2, a3);
  v8 = LogonId;
  if ( !LogonId )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids,
        (unsigned int)DestinationLuid.HighPart,
        DestinationLuid.LowPart);
    if ( !RtlAcquireResourceExclusive(&Resource, 1u) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
      return 2140;
    }
    if ( (unsigned int)DavGetUserEntry((LPVOID *)&DavUseObject, &DestinationLuid, &v18, 0) )
    {
      v12 = 0;
    }
    else
    {
      v11 = 2LL * v18;
      v12 = *(_QWORD *)(DavUseObject + 16LL * v18);
    }
    Use = DavFindUse(v11, v12, v4, &v20, &v21);
    v8 = Use;
    if ( Use )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_47;
      v16 = 64;
    }
    else
    {
      if ( !v20 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned int)(v20 + 65),
            WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
        goto LABEL_47;
      }
      Use = DavDeleteUse(v14, v5, v20, v18);
      v8 = Use;
      if ( !Use
        || (v15 = WPP_GLOBAL_Control, WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control)
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_47:
        RtlReleaseResource(&Resource);
        return v8;
      }
      v16 = 66;
    }
    WPP_SF_d(v15[2], v16, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, Use);
    goto LABEL_47;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 61;
    goto LABEL_14;
  }
  return v8;
}

```

## disassembly

```asm
0x180007b50  push    rbp
0x180007b52  push    rbx
0x180007b53  push    rsi
0x180007b54  push    rdi
0x180007b55  push    r12
0x180007b57  push    r13
0x180007b59  push    r14
0x180007b5b  push    r15
0x180007b5d  mov     rbp, rsp
0x180007b60  sub     rsp, 68h
0x180007b64  mov     rax, cs:__security_cookie
0x180007b6b  xor     rax, rsp
0x180007b6e  mov     [rbp+var_10], rax
0x180007b72  xor     r14d, r14d
0x180007b75  mov     ebx, r8d
0x180007b78  mov     qword ptr [rbp+DestinationLuid.LowPart], r14
0x180007b7c  mov     rdi, rdx
0x180007b7f  mov     [rbp+var_38], r14d
0x180007b83  mov     [rbp+var_28], r14
0x180007b87  mov     [rbp+var_20], r14
0x180007b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b92  lea     r15, WPP_GLOBAL_Control
0x180007b99  lea     r13d, [r14+3Ah]
0x180007b9d  lea     r12, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180007ba4  cmp     rcx, r15
0x180007ba7  jz      short loc_180007BC1
0x180007ba9  test    byte ptr [rcx+1Ch], 2
0x180007bad  jz      short loc_180007BC1
0x180007baf  mov     rcx, [rcx+10h]
0x180007bb3  mov     edx, r13d
0x180007bb6  mov     r9, rdi
0x180007bb9  mov     r8, r12
0x180007bbc  call    WPP_SF_S
0x180007bc1  neg     ebx
0x180007bc3  mov     qword ptr [rbp+DestinationLuid.LowPart], r14
0x180007bc7  sbb     esi, esi
0x180007bc9  and     esi, 2
0x180007bcc  test    rdi, rdi
0x180007bcf  jz      loc_180007DE4
0x180007bd5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007bd9  inc     rax
0x180007bdc  cmp     [rdi+rax*2], r14w
0x180007be1  jnz     short loc_180007BD9
0x180007be3  cmp     rax, 2
0x180007be7  jb      loc_180007DE4
0x180007bed  cmp     word ptr [rdi], 5Ch ; '\'
0x180007bf1  jz      short loc_180007C6E
0x180007bf3  cmp     [rdi+2], r13w
0x180007bf8  jnz     loc_180007DE4
0x180007bfe  lea     rdx, [rbp+var_18]
0x180007c02  mov     rcx, rdi
0x180007c05  call    DavCheckLocalName
0x180007c0a  mov     ebx, eax
0x180007c0c  test    eax, eax
0x180007c0e  jz      short loc_180007C43
0x180007c10  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c17  cmp     rcx, r15
0x180007c1a  jz      loc_180007DE9
0x180007c20  test    byte ptr [rcx+1Ch], 1
0x180007c24  jz      loc_180007DE9
0x180007c2a  mov     edx, 3Bh ; ';'
0x180007c2f  mov     rcx, [rcx+10h]
0x180007c33  mov     r9d, eax
0x180007c36  mov     r8, r12
0x180007c39  call    WPP_SF_d
0x180007c3e  jmp     loc_180007DE9
0x180007c43  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c4a  cmp     rcx, r15
0x180007c4d  jz      short loc_180007C6A
0x180007c4f  test    byte ptr [rcx+1Ch], 2
0x180007c53  jz      short loc_180007C6A
0x180007c55  mov     rcx, [rcx+10h]
0x180007c59  lea     r9, [rbp+var_18]
0x180007c5d  mov     edx, 3Ch ; '<'
0x180007c62  mov     r8, r12
0x180007c65  call    WPP_SF_S
0x180007c6a  lea     rdi, [rbp+var_18]
0x180007c6e  lea     rcx, [rbp+DestinationLuid]; DestinationLuid
0x180007c72  call    DavImpersonateAndGetLogonId
0x180007c77  mov     ebx, eax
0x180007c79  test    eax, eax
0x180007c7b  jz      short loc_180007C9E
0x180007c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c84  cmp     rcx, r15
0x180007c87  jz      loc_180007DE9
0x180007c8d  test    byte ptr [rcx+1Ch], 1
0x180007c91  jz      loc_180007DE9
0x180007c97  mov     edx, 3Dh ; '='
0x180007c9c  jmp     short loc_180007C2F
0x180007c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ca5  cmp     rcx, r15
0x180007ca8  jz      short loc_180007CCC
0x180007caa  test    byte ptr [rcx+1Ch], 2
0x180007cae  jz      short loc_180007CCC
0x180007cb0  mov     eax, [rbp+DestinationLuid.LowPart]
0x180007cb3  mov     edx, 3Eh ; '>'
0x180007cb8  mov     r9d, [rbp+DestinationLuid.HighPart]
0x180007cbc  mov     r8, r12
0x180007cbf  mov     rcx, [rcx+10h]
0x180007cc3  mov     dword ptr [rsp+68h+var_48], eax
0x180007cc7  call    WPP_SF_Dd
0x180007ccc  mov     dl, 1; Wait
0x180007cce  lea     rcx, Resource; Resource
0x180007cd5  call    cs:__imp_RtlAcquireResourceExclusive
0x180007cdb  test    al, al
0x180007cdd  jnz     short loc_180007D0C
0x180007cdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ce6  cmp     rcx, r15
0x180007ce9  jz      short loc_180007D02
0x180007ceb  test    byte ptr [rcx+1Ch], 1
0x180007cef  jz      short loc_180007D02
0x180007cf1  mov     rcx, [rcx+10h]
0x180007cf5  mov     edx, 3Fh ; '?'
0x180007cfa  mov     r8, r12
0x180007cfd  call    WPP_SF_
0x180007d02  mov     ebx, 85Ch
0x180007d07  jmp     loc_180007DE9
0x180007d0c  xor     r9d, r9d
0x180007d0f  lea     r8, [rbp+var_38]
0x180007d13  lea     rdx, [rbp+DestinationLuid]
0x180007d17  lea     rcx, DavUseObject
0x180007d1e  call    DavGetUserEntry
0x180007d23  test    eax, eax
0x180007d25  jz      short loc_180007D2C
0x180007d27  mov     rdx, r14
0x180007d2a  jmp     short loc_180007D3D
0x180007d2c  mov     ecx, [rbp+var_38]
0x180007d2f  mov     rax, cs:DavUseObject
0x180007d36  add     rcx, rcx
0x180007d39  mov     rdx, [rax+rcx*8]
0x180007d3d  lea     rax, [rbp+var_20]
0x180007d41  mov     r8, rdi
0x180007d44  lea     r9, [rbp+var_28]
0x180007d48  mov     [rsp+68h+var_48], rax
0x180007d4d  call    DavFindUse
0x180007d52  mov     ebx, eax
0x180007d54  test    eax, eax
0x180007d56  jz      short loc_180007D71
0x180007d58  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d5f  cmp     rcx, r15
0x180007d62  jz      short loc_180007DD5
0x180007d64  test    byte ptr [rcx+1Ch], 1
0x180007d68  jz      short loc_180007DD5
0x180007d6a  mov     edx, 40h ; '@'
0x180007d6f  jmp     short loc_180007DC6
0x180007d71  mov     r8, [rbp+var_28]
0x180007d75  test    r8, r8
0x180007d78  jnz     short loc_180007D9E
0x180007d7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d81  cmp     rcx, r15
0x180007d84  jz      short loc_180007DD5
0x180007d86  test    byte ptr [rcx+1Ch], 2
0x180007d8a  jz      short loc_180007DD5
0x180007d8c  mov     rcx, [rcx+10h]
0x180007d90  lea     edx, [r8+41h]
0x180007d94  mov     r8, r12
0x180007d97  call    WPP_SF_
0x180007d9c  jmp     short loc_180007DD5
0x180007d9e  mov     r9d, [rbp+var_38]
0x180007da2  mov     edx, esi
0x180007da4  call    DavDeleteUse
0x180007da9  mov     ebx, eax
0x180007dab  test    eax, eax
0x180007dad  jz      short loc_180007DD5
0x180007daf  mov     rcx, cs:WPP_GLOBAL_Control
0x180007db6  cmp     rcx, r15
0x180007db9  jz      short loc_180007DD5
0x180007dbb  test    byte ptr [rcx+1Ch], 1
0x180007dbf  jz      short loc_180007DD5
0x180007dc1  mov     edx, 42h ; 'B'
0x180007dc6  mov     rcx, [rcx+10h]
0x180007dca  mov     r9d, eax
0x180007dcd  mov     r8, r12
0x180007dd0  call    WPP_SF_d
0x180007dd5  lea     rcx, Resource; Resource
0x180007ddc  call    cs:__imp_RtlReleaseResource
0x180007de2  jmp     short loc_180007DE9
0x180007de4  mov     ebx, 57h ; 'W'
0x180007de9  mov     eax, ebx
0x180007deb  mov     rcx, [rbp+var_10]
0x180007def  xor     rcx, rsp; StackCookie
0x180007df2  call    __security_check_cookie
0x180007df7  add     rsp, 68h
0x180007dfb  pop     r15
0x180007dfd  pop     r14
0x180007dff  pop     r13
0x180007e01  pop     r12
0x180007e03  pop     rdi
0x180007e04  pop     rsi
0x180007e05  pop     rbx
0x180007e06  pop     rbp
0x180007e07  retn
```
