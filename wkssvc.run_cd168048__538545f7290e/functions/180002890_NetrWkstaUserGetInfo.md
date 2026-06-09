# NetrWkstaUserGetInfo

- ea: `0x180002890`
- end: `0x180002c16`
- name: `NetrWkstaUserGetInfo`
- size: `902`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001008`
- `0x180002890`
- `0x180002c20`
- `0x180005504`
- `0x180005df0`
- `0x18001fbd0`
- `0x1800204f6`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x18000294d`
- `ntdll!RtlCopyLuid` at `0x180002a4b`
- `ntdll!RtlCopyLuid` at `0x18000294d`
- `ntdll!RtlCopyLuid` at `0x180002a4b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002afb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002afb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800029ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002b5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002bf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800029ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002b5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002bf1`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18000298b`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18000298b`
- `SspiCli!LsaFreeReturnBuffer` at `0x180002b18`
- `SspiCli!LsaFreeReturnBuffer` at `0x180002b18`

## pseudocode

```c
__int64 __fastcall NetrWkstaUserGetInfo(__int64 a1, unsigned int a2, char *a3)
{
  unsigned int v3; // r14d
  int v5; // r12d
  HLOCAL v6; // rsi
  __int64 result; // rax
  unsigned int v8; // r15d
  unsigned int v9; // r13d
  unsigned int v10; // eax
  unsigned int Info; // edi
  int v12; // ecx
  unsigned int v13; // eax
  unsigned int i; // edx
  size_t v15; // r15
  char *v16; // rax
  char *v17; // rdi
  int v18; // r8d
  HLOCAL hMem; // [rsp+50h] [rbp-79h] BYREF
  PVOID Buffer; // [rsp+58h] [rbp-71h] BYREF
  ULONG ReturnBufferLength[2]; // [rsp+60h] [rbp-69h] BYREF
  struct _LUID SourceLuid; // [rsp+68h] [rbp-61h] BYREF
  char *v23; // [rsp+70h] [rbp-59h] BYREF
  int ProtocolSubmitBuffer; // [rsp+78h] [rbp-51h] BYREF
  _LUID DestinationLuid; // [rsp+7Ch] [rbp-4Dh] BYREF
  _DWORD v26[2]; // [rsp+90h] [rbp-39h] BYREF
  char v27[4]; // [rsp+98h] [rbp-31h] BYREF
  struct _LUID v28; // [rsp+9Ch] [rbp-2Dh] BYREF
  unsigned int v29; // [rsp+C8h] [rbp-1h]
  __int64 v30; // [rsp+D0h] [rbp+7h]

  v23 = a3;
  SourceLuid = 0;
  v3 = 8;
  Buffer = 0;
  v5 = 8;
  if ( a2 == 1 )
    v5 = 32;
  hMem = 0;
  v6 = 0;
  if ( a1 )
    return 87;
  if ( a2 > 1 && a2 != 1101 )
    return 124;
  result = WsImpersonateAndGetLogonId(&SourceLuid);
  if ( !(_DWORD)result )
  {
    ReturnBufferLength[0] = 0;
    if ( a2 != 1 )
    {
      v8 = 0;
      v9 = 0;
      if ( a2 != 1101 )
        goto LABEL_8;
    }
    memset_0(v27, 0, 0x58u);
    if ( WsDgReceiverDeviceHandle )
    {
      v26[1] = 6;
      v26[0] = 0;
      RtlCopyLuid(&v28, &SourceLuid);
      v30 = 0;
      Info = WsDeviceControlGetInfo(1, WsDgReceiverDeviceHandle, 1245207, v26, 96, &hMem, -1, 0);
      if ( Info )
        return Info;
      v9 = v29;
      v8 = 2;
      v6 = hMem;
      if ( v29 || !hMem )
      {
        for ( i = 0; i < v29; ++i )
        {
          if ( *((_DWORD *)hMem + 6 * i + 4) == 4 )
            v8 += *((unsigned __int16 *)hMem + 12 * i) + 2;
        }
      }
      else
      {
        LocalFree(hMem);
        v6 = 0;
      }
    }
    else
    {
      v9 = 0;
      v8 = 2;
    }
    if ( a2 == 1101 )
    {
      v13 = v8 + 8;
      if ( v8 + 8 >= v8 )
      {
LABEL_27:
        v15 = v13;
        v16 = (char *)LocalAlloc(0x40u, v13);
        v17 = v16;
        if ( v16 )
        {
          memset_0(v16, 0, v15);
          v18 = (int)Buffer;
          *(_QWORD *)ReturnBufferLength = v17;
          *(_QWORD *)v23 = v17;
          v23 = &v17[v15];
          v3 = WsPackageUserInfo(a2, v5, v18, (_DWORD)v6, v9, (__int64)ReturnBufferLength, (__int64)&v23, 0);
        }
        if ( Buffer )
          LsaFreeReturnBuffer(Buffer);
        if ( v6 )
          LocalFree(v6);
        return v3;
      }
    }
    else
    {
LABEL_8:
      LODWORD(hMem) = 0;
      DestinationLuid = 0;
      ProtocolSubmitBuffer = 3;
      RtlCopyLuid(&DestinationLuid, &SourceLuid);
      v10 = LsaCallAuthenticationPackage(
              LsaHandle,
              AuthenticationPackage,
              &ProtocolSubmitBuffer,
              0xCu,
              &Buffer,
              ReturnBufferLength,
              (PNTSTATUS)&hMem);
      if ( v10 || (v10 = (unsigned int)hMem) != 0 )
      {
        Info = WsMapStatus(v10);
        if ( Info )
        {
          LocalFree(v6);
          return Info;
        }
      }
      if ( a2 )
        v12 = *((unsigned __int16 *)Buffer + 16)
            + *((unsigned __int16 *)Buffer + 24)
            + *((unsigned __int16 *)Buffer + 8)
            + 38;
      else
        v12 = *((unsigned __int16 *)Buffer + 8) + 10;
      v13 = v12 + v8;
      if ( v12 + v8 >= v8 )
        goto LABEL_27;
    }
    return 2140;
  }
  return result;
}

```

## disassembly

```asm
0x180002890  mov     [rsp-8+arg_18], rbx
0x180002895  push    rbp
0x180002896  push    rsi
0x180002897  push    rdi
0x180002898  push    r12
0x18000289a  push    r14
0x18000289c  lea     rbp, [rsp-37h]
0x1800028a1  sub     rsp, 100h
0x1800028a8  mov     rax, cs:__security_cookie
0x1800028af  xor     rax, rsp
0x1800028b2  mov     [rbp+57h+var_30], rax
0x1800028b6  xor     edi, edi
0x1800028b8  mov     [rbp+57h+var_B0], r8
0x1800028bc  mov     qword ptr [rbp+57h+SourceLuid.LowPart], rdi
0x1800028c0  mov     r14d, 8
0x1800028c6  mov     [rbp+57h+Buffer], rdi
0x1800028ca  mov     ebx, edx
0x1800028cc  mov     r12d, r14d
0x1800028cf  test    edx, edx
0x1800028d1  jz      short loc_1800028DF
0x1800028d3  cmp     edx, 1
0x1800028d6  mov     eax, 20h ; ' '
0x1800028db  cmovz   r12d, eax
0x1800028df  mov     [rbp+57h+hMem], rdi
0x1800028e3  mov     rsi, rdi
0x1800028e6  test    rcx, rcx
0x1800028e9  jnz     loc_180002B4D
0x1800028ef  cmp     ebx, 1
0x1800028f2  ja      loc_180002BC1
0x1800028f8  lea     rcx, [rbp+57h+SourceLuid]; DestinationLuid
0x1800028fc  call    WsImpersonateAndGetLogonId
0x180002901  test    eax, eax
0x180002903  jnz     loc_1800029F7
0x180002909  mov     [rsp+120h+arg_0], r13
0x180002911  mov     [rsp+120h+arg_8], r15
0x180002919  mov     [rbp+57h+var_C0], edi
0x18000291c  cmp     ebx, 1
0x18000291f  jz      loc_180002A1B
0x180002925  mov     r15d, edi
0x180002928  mov     r13d, edi
0x18000292b  cmp     ebx, 44Dh
0x180002931  jz      loc_180002A1B
0x180002937  lea     rdx, [rbp+57h+SourceLuid]; SourceLuid
0x18000293b  mov     dword ptr [rbp+57h+hMem], edi
0x18000293e  lea     rcx, [rbp+57h+DestinationLuid]; DestinationLuid
0x180002942  mov     qword ptr [rbp+57h+DestinationLuid.LowPart], rdi
0x180002946  mov     [rbp+57h+ProtocolSubmitBuffer], 3
0x18000294d  call    cs:__imp_RtlCopyLuid
0x180002954  nop     dword ptr [rax+rax+00h]
0x180002959  mov     edx, cs:AuthenticationPackage; AuthenticationPackage
0x18000295f  lea     rax, [rbp+57h+hMem]
0x180002963  mov     rcx, cs:LsaHandle; LsaHandle
0x18000296a  lea     r8, [rbp+57h+ProtocolSubmitBuffer]; ProtocolSubmitBuffer
0x18000296e  mov     [rsp+120h+ProtocolStatus], rax; ProtocolStatus
0x180002973  mov     r9d, 0Ch; SubmitBufferLength
0x180002979  lea     rax, [rbp+57h+var_C0]
0x18000297d  mov     [rsp+120h+ReturnBufferLength], rax; ReturnBufferLength
0x180002982  lea     rax, [rbp+57h+Buffer]
0x180002986  mov     [rsp+120h+ProtocolReturnBuffer], rax; ProtocolReturnBuffer
0x18000298b  call    cs:__imp_LsaCallAuthenticationPackage
0x180002992  nop     dword ptr [rax+rax+00h]
0x180002997  test    eax, eax
0x180002999  jz      short loc_1800029B9
0x18000299b  mov     ecx, eax
0x18000299d  call    WsMapStatus
0x1800029a2  mov     edi, eax
0x1800029a4  test    eax, eax
0x1800029a6  jz      short loc_1800029C0
0x1800029a8  mov     rcx, rsi; hMem
0x1800029ab  call    cs:__imp_LocalFree
0x1800029b2  nop     dword ptr [rax+rax+00h]
0x1800029b7  jmp     short loc_1800029E5
0x1800029b9  mov     eax, dword ptr [rbp+57h+hMem]
0x1800029bc  test    eax, eax
0x1800029be  jnz     short loc_18000299B
0x1800029c0  test    ebx, ebx
0x1800029c2  jnz     loc_180002B31
0x1800029c8  mov     rax, [rbp+57h+Buffer]
0x1800029cc  movzx   ecx, word ptr [rax+10h]
0x1800029d0  add     ecx, 0Ah
0x1800029d3  lea     eax, [rcx+r15]
0x1800029d7  cmp     eax, r15d
0x1800029da  jnb     loc_180002AF1
0x1800029e0  mov     edi, 85Ch
0x1800029e5  mov     eax, edi
0x1800029e7  mov     r13, [rsp+120h+arg_0]
0x1800029ef  mov     r15, [rsp+120h+arg_8]
0x1800029f7  mov     rcx, [rbp+57h+var_30]
0x1800029fb  xor     rcx, rsp; StackCookie
0x1800029fe  call    __security_check_cookie
0x180002a03  mov     rbx, [rsp+120h+arg_18]
0x180002a0b  add     rsp, 100h
0x180002a12  pop     r14
0x180002a14  pop     r12
0x180002a16  pop     rdi
0x180002a17  pop     rsi
0x180002a18  pop     rbp
0x180002a19  retn
0x180002a1b  xor     edx, edx; Val
0x180002a1d  lea     rcx, [rbp+57h+var_88]; void *
0x180002a21  mov     r8d, 58h ; 'X'; Size
0x180002a27  call    memset_0
0x180002a2c  cmp     cs:WsDgReceiverDeviceHandle, rdi
0x180002a33  jz      loc_180002BD7
0x180002a39  lea     rdx, [rbp+57h+SourceLuid]; SourceLuid
0x180002a3d  mov     [rbp+57h+var_8C], 6
0x180002a44  lea     rcx, [rbp+57h+var_84]; DestinationLuid
0x180002a48  mov     [rbp+57h+var_90], edi
0x180002a4b  call    cs:__imp_RtlCopyLuid
0x180002a52  nop     dword ptr [rax+rax+00h]
0x180002a57  mov     rdx, cs:WsDgReceiverDeviceHandle
0x180002a5e  lea     rax, [rbp+57h+hMem]
0x180002a62  mov     dword ptr [rsp+120h+var_E8], edi
0x180002a66  lea     r9, [rbp+57h+var_90]
0x180002a6a  mov     dword ptr [rsp+120h+ProtocolStatus], 0FFFFFFFFh
0x180002a72  mov     r8d, 130017h
0x180002a78  mov     [rsp+120h+ReturnBufferLength], rax
0x180002a7d  mov     ecx, 1
0x180002a82  mov     dword ptr [rsp+120h+ProtocolReturnBuffer], 60h ; '`'
0x180002a8a  mov     [rbp+57h+var_50], rdi
0x180002a8e  call    WsDeviceControlGetInfo
0x180002a93  mov     edi, eax
0x180002a95  test    eax, eax
0x180002a97  jnz     loc_1800029E5
0x180002a9d  mov     r13d, [rbp+57h+var_58]
0x180002aa1  mov     r15d, 2
0x180002aa7  mov     rsi, [rbp+57h+hMem]
0x180002aab  test    r13d, r13d
0x180002aae  jz      loc_180002BE5
0x180002ab4  xor     edi, edi
0x180002ab6  mov     edx, edi
0x180002ab8  test    r13d, r13d
0x180002abb  jz      short loc_180002AD8
0x180002abd  nop     dword ptr [rax]
0x180002ac0  mov     eax, edx
0x180002ac2  lea     rcx, [rax+rax*2]
0x180002ac6  cmp     dword ptr [rsi+rcx*8+10h], 4
0x180002acb  jz      loc_180002C06
0x180002ad1  inc     edx
0x180002ad3  cmp     edx, r13d
0x180002ad6  jb      short loc_180002AC0
0x180002ad8  cmp     ebx, 44Dh
0x180002ade  jnz     loc_180002937
0x180002ae4  lea     eax, [r15+8]
0x180002ae8  cmp     eax, r15d
0x180002aeb  jb      loc_1800029E0
0x180002af1  mov     edx, eax; uBytes
0x180002af3  mov     ecx, 40h ; '@'; uFlags
0x180002af8  mov     r15d, eax
0x180002afb  call    cs:__imp_LocalAlloc
0x180002b02  nop     dword ptr [rax+rax+00h]
0x180002b07  mov     rdi, rax
0x180002b0a  test    rax, rax
0x180002b0d  jnz     short loc_180002B68
0x180002b0f  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180002b13  test    rcx, rcx
0x180002b16  jz      short loc_180002B24
0x180002b18  call    cs:__imp_LsaFreeReturnBuffer
0x180002b1f  nop     dword ptr [rax+rax+00h]
0x180002b24  test    rsi, rsi
0x180002b27  jnz     short loc_180002B57
0x180002b29  mov     eax, r14d
0x180002b2c  jmp     loc_1800029E7
0x180002b31  mov     rcx, [rbp+57h+Buffer]
0x180002b35  movzx   edx, word ptr [rcx+30h]
0x180002b39  movzx   eax, word ptr [rcx+20h]
0x180002b3d  movzx   ecx, word ptr [rcx+10h]
0x180002b41  add     edx, eax
0x180002b43  add     ecx, 26h ; '&'
0x180002b46  add     ecx, edx
0x180002b48  jmp     loc_1800029D3
0x180002b4d  mov     eax, 57h ; 'W'
0x180002b52  jmp     loc_1800029F7
0x180002b57  mov     rcx, rsi; hMem
0x180002b5a  call    cs:__imp_LocalFree
0x180002b61  nop     dword ptr [rax+rax+00h]
0x180002b66  jmp     short loc_180002B29
0x180002b68  mov     r8, r15; Size
0x180002b6b  xor     edx, edx; Val
0x180002b6d  mov     rcx, rdi; void *
0x180002b70  call    memset_0
0x180002b75  mov     rax, [rbp+57h+var_B0]
0x180002b79  mov     r9, rsi
0x180002b7c  mov     r8, [rbp+57h+Buffer]
0x180002b80  mov     edx, r12d
0x180002b83  mov     [rsp+120h+var_E8], 0
0x180002b8c  mov     ecx, ebx
0x180002b8e  mov     qword ptr [rbp+57h+var_C0], rdi
0x180002b92  mov     [rax], rdi
0x180002b95  lea     rax, [r15+rdi]
0x180002b99  mov     [rbp+57h+var_B0], rax
0x180002b9d  lea     rax, [rbp+57h+var_B0]
0x180002ba1  mov     [rsp+120h+ProtocolStatus], rax
0x180002ba6  lea     rax, [rbp+57h+var_C0]
0x180002baa  mov     [rsp+120h+ReturnBufferLength], rax
0x180002baf  mov     dword ptr [rsp+120h+ProtocolReturnBuffer], r13d
0x180002bb4  call    WsPackageUserInfo
0x180002bb9  mov     r14d, eax
0x180002bbc  jmp     loc_180002B0F
0x180002bc1  cmp     ebx, 44Dh
0x180002bc7  jz      loc_1800028F8
0x180002bcd  mov     eax, 7Ch ; '|'
0x180002bd2  jmp     loc_1800029F7
0x180002bd7  mov     r13d, edi
0x180002bda  mov     r15d, 2
0x180002be0  jmp     loc_180002AD8
0x180002be5  test    rsi, rsi
0x180002be8  jz      loc_180002AB4
0x180002bee  mov     rcx, rsi; hMem
0x180002bf1  call    cs:__imp_LocalFree
0x180002bf8  nop     dword ptr [rax+rax+00h]
0x180002bfd  xor     edi, edi
0x180002bff  mov     esi, edi
0x180002c01  jmp     loc_180002AD8
0x180002c06  movzx   eax, word ptr [rsi+rcx*8]
0x180002c0a  add     r15d, 2
0x180002c0e  add     r15d, eax
0x180002c11  jmp     loc_180002AD1
```
